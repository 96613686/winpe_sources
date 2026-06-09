# GetPrimaryPrincipalSid(_LUID *,void * *)

- ea: `0x18006e61c`
- end: `0x18006e6df`
- name: `?GetPrimaryPrincipalSid@@YAJPEAU_LUID@@PEAPEAX@Z`
- size: `195`
- prototype: `__int64 __fastcall(struct _LUID *, void **)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800acc7c`

## callees

- `0x1800069a0`
- `0x1800093f0`
- `0x18006e61c`

## import_xrefs

- `ntdll!RtlCopySid` at `0x18006e6b9`
- `ntdll!RtlCopySid` at `0x18006e6b9`
- `ntdll!RtlLengthSid` at `0x18006e68d`
- `ntdll!RtlLengthSid` at `0x18006e68d`
- `SspiCli!LsaGetLogonSessionData` at `0x18006e652`
- `SspiCli!LsaGetLogonSessionData` at `0x18006e652`
- `SspiCli!LsaFreeReturnBuffer` at `0x18006e683`
- `SspiCli!LsaFreeReturnBuffer` at `0x18006e683`

## pseudocode

```c
__int64 __fastcall GetPrimaryPrincipalSid(struct _LUID *a1, void **a2)
{
  void *v3; // rdi
  NTSTATUS LogonSessionData; // ebx
  void *v5; // rcx
  ULONG v7; // ebx
  void *v8; // rax
  PVOID Buffer; // [rsp+38h] [rbp+10h] BYREF

  Buffer = 0;
  if ( !a2 || !a1 )
    return 3221225485LL;
  v3 = 0;
  *a2 = 0;
  LogonSessionData = LsaGetLogonSessionData(a1, (PSECURITY_LOGON_SESSION_DATA *)&Buffer);
  if ( LogonSessionData >= 0 )
  {
    v5 = (void *)*((_QWORD *)Buffer + 9);
    if ( v5 )
    {
      v7 = RtlLengthSid(v5);
      v8 = MIDL_user_allocate(v7);
      v3 = v8;
      if ( v8 )
      {
        LogonSessionData = RtlCopySid(v7, v8, *((PSID *)Buffer + 9));
        if ( LogonSessionData >= 0 )
        {
          *a2 = v3;
          goto LABEL_7;
        }
      }
      else
      {
        LogonSessionData = -1073741801;
      }
    }
    else
    {
      LogonSessionData = -1073741823;
    }
  }
  KerbFree(v3);
LABEL_7:
  if ( Buffer )
    LsaFreeReturnBuffer(Buffer);
  return (unsigned int)LogonSessionData;
}

```

## disassembly

```asm
0x18006e61c  mov     rax, rsp
0x18006e61f  mov     [rax+8], rbx
0x18006e623  mov     [rax+18h], rsi
0x18006e627  push    rdi
0x18006e628  sub     rsp, 20h
0x18006e62c  mov     qword ptr [rax+10h], 0
0x18006e634  mov     rsi, rdx
0x18006e637  test    rdx, rdx
0x18006e63a  jz      loc_18006E6CA
0x18006e640  test    rcx, rcx
0x18006e643  jz      loc_18006E6CA
0x18006e649  xor     edi, edi
0x18006e64b  mov     [rdx], rdi
0x18006e64e  lea     rdx, [rax+10h]; ppLogonSessionData
0x18006e652  call    cs:__imp_LsaGetLogonSessionData
0x18006e658  mov     ebx, eax
0x18006e65a  test    eax, eax
0x18006e65c  js      short loc_18006E671
0x18006e65e  mov     rax, [rsp+28h+Buffer]
0x18006e663  mov     rcx, [rax+48h]; Sid
0x18006e667  test    rcx, rcx
0x18006e66a  jnz     short loc_18006E68D
0x18006e66c  mov     ebx, 0C0000001h
0x18006e671  mov     rcx, rdi
0x18006e674  call    KerbFree
0x18006e679  mov     rcx, [rsp+28h+Buffer]; Buffer
0x18006e67e  test    rcx, rcx
0x18006e681  jz      short loc_18006E689
0x18006e683  call    cs:__imp_LsaFreeReturnBuffer
0x18006e689  mov     eax, ebx
0x18006e68b  jmp     short loc_18006E6CF
0x18006e68d  call    cs:__imp_RtlLengthSid
0x18006e693  mov     ecx, eax; size
0x18006e695  mov     ebx, eax
0x18006e697  call    MIDL_user_allocate
0x18006e69c  mov     rdi, rax
0x18006e69f  test    rax, rax
0x18006e6a2  jnz     short loc_18006E6AB
0x18006e6a4  mov     ebx, 0C0000017h
0x18006e6a9  jmp     short loc_18006E671
0x18006e6ab  mov     r8, [rsp+28h+Buffer]
0x18006e6b0  mov     rdx, rdi; DestinationSid
0x18006e6b3  mov     ecx, ebx; DestinationSidLength
0x18006e6b5  mov     r8, [r8+48h]; SourceSid
0x18006e6b9  call    cs:__imp_RtlCopySid
0x18006e6bf  mov     ebx, eax
0x18006e6c1  test    eax, eax
0x18006e6c3  js      short loc_18006E671
0x18006e6c5  mov     [rsi], rdi
0x18006e6c8  jmp     short loc_18006E679
0x18006e6ca  mov     eax, 0C000000Dh
0x18006e6cf  mov     rbx, [rsp+28h+arg_0]
0x18006e6d4  mov     rsi, [rsp+28h+arg_10]
0x18006e6d9  add     rsp, 20h
0x18006e6dd  pop     rdi
0x18006e6de  retn
```
