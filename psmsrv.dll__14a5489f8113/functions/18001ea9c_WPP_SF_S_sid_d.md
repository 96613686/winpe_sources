# WPP_SF_S_sid_d

- ea: `0x18001ea9c`
- end: `0x18001eb80`
- name: `WPP_SF_S_sid_d`
- size: `228`
- prototype: `__int64 __usercall@<rax>(TRACEHANDLE LoggerHandle@<rcx>, PSID pSid, char)`
- caller_count: `5`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180001230`
- `0x1800078e0`
- `0x18000abf0`
- `0x18000c7b0`
- `0x18001cf00`

## callees

- `0x18001ea9c`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18001ead2`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18001ead2`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x18001eac5`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x18001eae9`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x18001eac5`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x18001eae9`
- `api-ms-win-eventing-classicprovider-l1-1-0!TraceMessage` at `0x18001eb6d`
- `api-ms-win-eventing-classicprovider-l1-1-0!TraceMessage` at `0x18001eb6d`

## pseudocode

```c
ULONG WPP_SF_S_sid_d(TRACEHANDLE LoggerHandle, USHORT a2, __int64 a3, const wchar_t *a4, char *pSid, ...)
{
  const char *v5; // rbx
  DWORD LengthSid; // esi
  __int64 v10; // rax
  __int64 v11; // rcx
  va_list va; // [rsp+C8h] [rbp+30h] BYREF

  va_start(va, pSid);
  v5 = pSid;
  if ( pSid && IsValidSid(pSid) )
  {
    LengthSid = GetLengthSid(pSid);
    goto LABEL_5;
  }
  LengthSid = 5;
  if ( pSid )
  {
LABEL_5:
    if ( IsValidSid(pSid) )
      goto LABEL_7;
  }
  v5 = "NULL";
LABEL_7:
  if ( a4 )
  {
    v10 = -1;
    do
      ++v10;
    while ( a4[v10] );
    v11 = 2 * v10 + 2;
  }
  else
  {
    v11 = 10;
  }
  if ( !a4 )
    a4 = L"NULL";
  return TraceMessage(
           LoggerHandle,
           0x2Bu,
           &WPP_7630e226a175390276defa9bbccaa0fe_Traceguids,
           a2,
           a4,
           v11,
           v5,
           LengthSid,
           va,
           4,
           0);
}

```

## disassembly

```asm
0x18001ea9c  push    rbx
0x18001ea9e  push    rbp
0x18001ea9f  push    rsi
0x18001eaa0  push    rdi
0x18001eaa1  push    r14
0x18001eaa3  push    r15
0x18001eaa5  sub     rsp, 68h
0x18001eaa9  mov     rbx, [rsp+98h+pSid]
0x18001eab1  xor     r15d, r15d
0x18001eab4  movzx   ebp, dx
0x18001eab7  mov     rdi, r9
0x18001eaba  mov     r14, rcx
0x18001eabd  test    rbx, rbx
0x18001eac0  jz      short loc_18001EADC
0x18001eac2  mov     rcx, rbx; pSid
0x18001eac5  call    cs:__imp_IsValidSid
0x18001eacb  test    eax, eax
0x18001eacd  jz      short loc_18001EADC
0x18001eacf  mov     rcx, rbx; pSid
0x18001ead2  call    cs:__imp_GetLengthSid
0x18001ead8  mov     esi, eax
0x18001eada  jmp     short loc_18001EAE6
0x18001eadc  mov     esi, 5
0x18001eae1  test    rbx, rbx
0x18001eae4  jz      short loc_18001EAF3
0x18001eae6  mov     rcx, rbx; pSid
0x18001eae9  call    cs:__imp_IsValidSid
0x18001eaef  test    eax, eax
0x18001eaf1  jnz     short loc_18001EAFA
0x18001eaf3  lea     rbx, aNull; "NULL"
0x18001eafa  test    rdi, rdi
0x18001eafd  jz      short loc_18001EB17
0x18001eaff  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001eb03  inc     rax
0x18001eb06  cmp     [rdi+rax*2], r15w
0x18001eb0b  jnz     short loc_18001EB03
0x18001eb0d  lea     rcx, ds:2[rax*2]
0x18001eb15  jmp     short loc_18001EB1C
0x18001eb17  mov     ecx, 0Ah
0x18001eb1c  mov     [rsp+98h+var_48], r15
0x18001eb21  lea     rdx, aNull_0; "NULL"
0x18001eb28  mov     [rsp+98h+var_50], 4
0x18001eb31  lea     r8, WPP_7630e226a175390276defa9bbccaa0fe_Traceguids; MessageGuid
0x18001eb38  test    rdi, rdi
0x18001eb3b  mov     eax, esi
0x18001eb3d  mov     r9d, ebp; MessageNumber
0x18001eb40  cmovz   rdi, rdx
0x18001eb44  lea     rdx, [rsp+98h+arg_28]
0x18001eb4c  mov     [rsp+98h+var_58], rdx
0x18001eb51  mov     edx, 2Bh ; '+'; MessageFlags
0x18001eb56  mov     [rsp+98h+var_60], rax
0x18001eb5b  mov     [rsp+98h+var_68], rbx
0x18001eb60  mov     [rsp+98h+var_70], rcx
0x18001eb65  mov     rcx, r14; LoggerHandle
0x18001eb68  mov     [rsp+98h+var_78], rdi
0x18001eb6d  call    cs:__imp_TraceMessage
0x18001eb73  add     rsp, 68h
0x18001eb77  pop     r15
0x18001eb79  pop     r14
0x18001eb7b  pop     rdi
0x18001eb7c  pop     rsi
0x18001eb7d  pop     rbp
0x18001eb7e  pop     rbx
0x18001eb7f  retn
```
