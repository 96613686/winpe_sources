# ISAPI_DLL::LoadAcl(STRU &)

- ea: `0x1800059d4`
- end: `0x180005a72`
- name: `?LoadAcl@ISAPI_DLL@@AEAAJAEAVSTRU@@@Z`
- size: `158`
- prototype: `signed int __fastcall(ISAPI_DLL *this, struct STRU *)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180005640`

## callees

- `0x1800059d4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005a36`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005a36`
- `api-ms-win-security-base-l1-1-0!GetFileSecurityW` at `0x180005a2c`
- `api-ms-win-security-base-l1-1-0!GetFileSecurityW` at `0x180005a2c`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180005a02`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180005a02`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180005a0e`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180005a0e`
- `iisutil!?QuerySize@BUFFER@@QEBAKXZ` at `0x1800059ea`
- `iisutil!?QuerySize@BUFFER@@QEBAKXZ` at `0x1800059f7`
- `iisutil!?QuerySize@BUFFER@@QEBAKXZ` at `0x1800059ea`
- `iisutil!?QuerySize@BUFFER@@QEBAKXZ` at `0x1800059f7`
- `iisutil!?Resize@BUFFER@@QEAA_NK@Z` at `0x180005a48`
- `iisutil!?Resize@BUFFER@@QEAA_NK@Z` at `0x180005a48`

## pseudocode

```c
signed int __fastcall ISAPI_DLL::LoadAcl(ISAPI_DLL *this, struct STRU *a2)
{
  BUFFER *v2; // rsi
  DWORD Size; // edi
  void *Ptr; // rbx
  const WCHAR *Str; // rax
  signed int result; // eax
  DWORD nLengthNeeded; // [rsp+60h] [rbp+8h] BYREF

  v2 = (ISAPI_DLL *)((char *)this + 200);
  nLengthNeeded = BUFFER::QuerySize((ISAPI_DLL *)((char *)this + 200));
  while ( 1 )
  {
    Size = BUFFER::QuerySize(v2);
    Ptr = BUFFER::QueryPtr(v2);
    Str = STRU::QueryStr(a2);
    if ( GetFileSecurityW(Str, 7u, Ptr, Size, &nLengthNeeded) )
      return 0;
    result = GetLastError();
    if ( result != 122 )
      break;
    if ( !BUFFER::Resize(v2, nLengthNeeded) )
      return -2147024888;
  }
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x1800059d4  push    rbx
0x1800059d6  push    rbp
0x1800059d7  push    rsi
0x1800059d8  push    rdi
0x1800059d9  sub     rsp, 38h
0x1800059dd  lea     rsi, [rcx+0C8h]
0x1800059e4  mov     rbp, rdx
0x1800059e7  mov     rcx, rsi
0x1800059ea  call    cs:__imp_?QuerySize@BUFFER@@QEBAKXZ; BUFFER::QuerySize(void)
0x1800059f0  mov     [rsp+58h+nLengthNeeded], eax
0x1800059f4  mov     rcx, rsi
0x1800059f7  call    cs:__imp_?QuerySize@BUFFER@@QEBAKXZ; BUFFER::QuerySize(void)
0x1800059fd  mov     rcx, rsi
0x180005a00  mov     edi, eax
0x180005a02  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x180005a08  mov     rcx, rbp
0x180005a0b  mov     rbx, rax
0x180005a0e  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x180005a14  lea     rcx, [rsp+58h+nLengthNeeded]
0x180005a19  mov     r9d, edi; nLength
0x180005a1c  mov     [rsp+58h+lpnLengthNeeded], rcx; lpnLengthNeeded
0x180005a21  mov     r8, rbx; pSecurityDescriptor
0x180005a24  mov     rcx, rax; lpFileName
0x180005a27  mov     edx, 7; RequestedInformation
0x180005a2c  call    cs:__imp_GetFileSecurityW
0x180005a32  test    eax, eax
0x180005a34  jnz     short loc_180005A67
0x180005a36  call    cs:__imp_GetLastError
0x180005a3c  cmp     eax, 7Ah ; 'z'
0x180005a3f  jnz     short loc_180005A59
0x180005a41  mov     edx, [rsp+58h+nLengthNeeded]
0x180005a45  mov     rcx, rsi
0x180005a48  call    cs:__imp_?Resize@BUFFER@@QEAA_NK@Z; BUFFER::Resize(ulong)
0x180005a4e  test    al, al
0x180005a50  jnz     short loc_1800059F4
0x180005a52  mov     eax, 80070008h
0x180005a57  jmp     short loc_180005A69
0x180005a59  test    eax, eax
0x180005a5b  jle     short loc_180005A69
0x180005a5d  movzx   eax, ax
0x180005a60  or      eax, 80070000h
0x180005a65  jmp     short loc_180005A69
0x180005a67  xor     eax, eax
0x180005a69  add     rsp, 38h
0x180005a6d  pop     rdi
0x180005a6e  pop     rsi
0x180005a6f  pop     rbp
0x180005a70  pop     rbx
0x180005a71  retn
```
