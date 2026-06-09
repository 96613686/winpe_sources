# WPP_SF_S_sid_dd

- ea: `0x18001eb88`
- end: `0x18001ec80`
- name: `WPP_SF_S_sid_dd`
- size: `248`
- prototype: `__int64 __usercall@<rax>(TRACEHANDLE LoggerHandle@<rcx>, PSID pSid, char, char)`
- caller_count: `2`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180001230`
- `0x180017768`

## callees

- `0x18001eb88`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18001ebbe`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18001ebbe`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x18001ebb1`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x18001ebd5`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x18001ebb1`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x18001ebd5`
- `api-ms-win-eventing-classicprovider-l1-1-0!TraceMessage` at `0x18001ec6d`
- `api-ms-win-eventing-classicprovider-l1-1-0!TraceMessage` at `0x18001ec6d`

## pseudocode

```c
ULONG WPP_SF_S_sid_dd(TRACEHANDLE LoggerHandle, USHORT a2, __int64 a3, const wchar_t *a4, char *pSid, ...)
{
  const char *v5; // rbx
  DWORD LengthSid; // esi
  __int64 v10; // rax
  __int64 v11; // rcx
  __int64 v13; // [rsp+D8h] [rbp+30h] BYREF
  va_list va; // [rsp+D8h] [rbp+30h]
  va_list va1; // [rsp+E0h] [rbp+38h] BYREF

  va_start(va1, pSid);
  va_start(va, pSid);
  v13 = va_arg(va1, _QWORD);
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
           va1,
           4,
           0);
}

```

## disassembly

```asm
0x18001eb88  push    rbx
0x18001eb8a  push    rbp
0x18001eb8b  push    rsi
0x18001eb8c  push    rdi
0x18001eb8d  push    r14
0x18001eb8f  push    r15
0x18001eb91  sub     rsp, 78h
0x18001eb95  mov     rbx, [rsp+0A8h+pSid]
0x18001eb9d  xor     r15d, r15d
0x18001eba0  movzx   ebp, dx
0x18001eba3  mov     rdi, r9
0x18001eba6  mov     r14, rcx
0x18001eba9  test    rbx, rbx
0x18001ebac  jz      short loc_18001EBC8
0x18001ebae  mov     rcx, rbx; pSid
0x18001ebb1  call    cs:__imp_IsValidSid
0x18001ebb7  test    eax, eax
0x18001ebb9  jz      short loc_18001EBC8
0x18001ebbb  mov     rcx, rbx; pSid
0x18001ebbe  call    cs:__imp_GetLengthSid
0x18001ebc4  mov     esi, eax
0x18001ebc6  jmp     short loc_18001EBD2
0x18001ebc8  mov     esi, 5
0x18001ebcd  test    rbx, rbx
0x18001ebd0  jz      short loc_18001EBDF
0x18001ebd2  mov     rcx, rbx; pSid
0x18001ebd5  call    cs:__imp_IsValidSid
0x18001ebdb  test    eax, eax
0x18001ebdd  jnz     short loc_18001EBE6
0x18001ebdf  lea     rbx, aNull; "NULL"
0x18001ebe6  test    rdi, rdi
0x18001ebe9  jz      short loc_18001EC03
0x18001ebeb  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001ebef  inc     rax
0x18001ebf2  cmp     [rdi+rax*2], r15w
0x18001ebf7  jnz     short loc_18001EBEF
0x18001ebf9  lea     rcx, ds:2[rax*2]
0x18001ec01  jmp     short loc_18001EC08
0x18001ec03  mov     ecx, 0Ah
0x18001ec08  mov     [rsp+0A8h+var_48], r15
0x18001ec0d  lea     rdx, aNull_0; "NULL"
0x18001ec14  mov     r8d, 4
0x18001ec1a  mov     eax, esi
0x18001ec1c  mov     [rsp+0A8h+var_50], r8
0x18001ec21  test    rdi, rdi
0x18001ec24  mov     r9d, ebp; MessageNumber
0x18001ec27  cmovz   rdi, rdx
0x18001ec2b  lea     rdx, [rsp+0A8h+arg_30]
0x18001ec33  mov     [rsp+0A8h+var_58], rdx
0x18001ec38  lea     rdx, [rsp+0A8h+arg_28]
0x18001ec40  mov     [rsp+0A8h+var_60], r8
0x18001ec45  lea     r8, WPP_7630e226a175390276defa9bbccaa0fe_Traceguids; MessageGuid
0x18001ec4c  mov     [rsp+0A8h+var_68], rdx
0x18001ec51  mov     edx, 2Bh ; '+'; MessageFlags
0x18001ec56  mov     [rsp+0A8h+var_70], rax
0x18001ec5b  mov     [rsp+0A8h+var_78], rbx
0x18001ec60  mov     [rsp+0A8h+var_80], rcx
0x18001ec65  mov     rcx, r14; LoggerHandle
0x18001ec68  mov     [rsp+0A8h+var_88], rdi
0x18001ec6d  call    cs:__imp_TraceMessage
0x18001ec73  add     rsp, 78h
0x18001ec77  pop     r15
0x18001ec79  pop     r14
0x18001ec7b  pop     rdi
0x18001ec7c  pop     rsi
0x18001ec7d  pop     rbp
0x18001ec7e  pop     rbx
0x18001ec7f  retn
```
