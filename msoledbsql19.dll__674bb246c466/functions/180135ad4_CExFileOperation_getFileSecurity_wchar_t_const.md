# CExFileOperation::_getFileSecurity(wchar_t const *)

- ea: `0x180135ad4`
- end: `0x180135bf1`
- name: `?_getFileSecurity@CExFileOperation@@AEAAJPEB_W@Z`
- size: `285`
- prototype: `int(CExFileOperation *__hidden this, const wchar_t *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180135860`

## callees

- `0x180003d80`
- `0x180135ad4`
- `0x1801ad6a0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180135bb4`
- `KERNEL32!GetLastError` at `0x180135bb4`
- `ADVAPI32!GetFileSecurityW` at `0x180135b44`
- `ADVAPI32!GetFileSecurityW` at `0x180135baa`
- `ADVAPI32!GetFileSecurityW` at `0x180135b44`
- `ADVAPI32!GetFileSecurityW` at `0x180135baa`

## pseudocode

```c
__int64 __fastcall CExFileOperation::_getFileSecurity(void **this, const wchar_t *a2)
{
  void *v3; // rax
  BOOL FileSecurityW; // eax
  __int64 v6; // rdi
  void *v7; // rax
  signed int LastError; // ecx
  __int64 result; // rax
  DWORD nLengthNeeded; // [rsp+30h] [rbp-18h] BYREF

  nLengthNeeded = 0;
  v3 = *this;
  if ( !*this )
  {
    v3 = (void *)(*(__int64 (__fastcall **)(struct ISOSHost_MemObj *, __int64))(*(_QWORD *)g_pMO + 24LL))(g_pMO, 120);
    *this = v3;
    if ( !v3 )
      return 2147942414LL;
  }
  FileSecurityW = GetFileSecurityW(a2, 4u, v3, 0x78u, &nLengthNeeded);
  v6 = nLengthNeeded;
  if ( nLengthNeeded <= 0x78 )
    goto LABEL_8;
  if ( *this )
    (*(void (__fastcall **)(struct ISOSHost_MemObj *))(*(_QWORD *)g_pMO + 40LL))(g_pMO);
  *this = 0;
  v7 = (void *)(*(__int64 (__fastcall **)(struct ISOSHost_MemObj *, __int64))(*(_QWORD *)g_pMO + 24LL))(g_pMO, v6);
  *this = v7;
  if ( !v7 )
    return 2147942414LL;
  FileSecurityW = GetFileSecurityW(a2, 4u, v7, v6, &nLengthNeeded);
LABEL_8:
  if ( FileSecurityW )
    return 0;
  LastError = GetLastError();
  result = (unsigned __int16)LastError | 0x80070000;
  if ( LastError <= 0 )
    return (unsigned int)LastError;
  return result;
}

```

## disassembly

```asm
0x180135ad4  mov     [rsp+arg_10], rbx
0x180135ad9  mov     [rsp+arg_18], rsi
0x180135ade  push    rdi
0x180135adf  sub     rsp, 40h
0x180135ae3  mov     rax, cs:__security_cookie
0x180135aea  xor     rax, rsp
0x180135aed  mov     [rsp+48h+var_10], rax
0x180135af2  and     [rsp+48h+nLengthNeeded], 0
0x180135af7  mov     rsi, rdx
0x180135afa  mov     rax, [rcx]
0x180135afd  mov     rbx, rcx
0x180135b00  test    rax, rax
0x180135b03  jnz     short loc_180135B2A
0x180135b05  mov     rcx, cs:?g_pMO@@3PEAUISOSHost_MemObj@@EA; ISOSHost_MemObj * g_pMO
0x180135b0c  mov     edx, 78h ; 'x'
0x180135b11  mov     rax, [rcx]
0x180135b14  mov     rax, [rax+18h]
0x180135b18  call    cs:__guard_dispatch_icall_fptr
0x180135b1e  mov     [rbx], rax
0x180135b21  test    rax, rax
0x180135b24  jz      loc_180135BCF
0x180135b2a  mov     r9d, 78h ; 'x'; nLength
0x180135b30  lea     rcx, [rsp+48h+nLengthNeeded]
0x180135b35  mov     [rsp+48h+lpnLengthNeeded], rcx; lpnLengthNeeded
0x180135b3a  mov     r8, rax; pSecurityDescriptor
0x180135b3d  mov     rcx, rsi; lpFileName
0x180135b40  lea     edx, [r9-74h]; RequestedInformation
0x180135b44  call    cs:__imp_GetFileSecurityW
0x180135b4a  mov     edi, [rsp+48h+nLengthNeeded]
0x180135b4e  cmp     edi, 78h ; 'x'
0x180135b51  jbe     short loc_180135BB0
0x180135b53  mov     rdx, [rbx]
0x180135b56  test    rdx, rdx
0x180135b59  jz      short loc_180135B6F
0x180135b5b  mov     rcx, cs:?g_pMO@@3PEAUISOSHost_MemObj@@EA; ISOSHost_MemObj * g_pMO
0x180135b62  mov     rax, [rcx]
0x180135b65  mov     rax, [rax+28h]
0x180135b69  call    cs:__guard_dispatch_icall_fptr
0x180135b6f  and     qword ptr [rbx], 0
0x180135b73  mov     rdx, rdi
0x180135b76  mov     rcx, cs:?g_pMO@@3PEAUISOSHost_MemObj@@EA; ISOSHost_MemObj * g_pMO
0x180135b7d  mov     rax, [rcx]
0x180135b80  mov     rax, [rax+18h]
0x180135b84  call    cs:__guard_dispatch_icall_fptr
0x180135b8a  mov     [rbx], rax
0x180135b8d  test    rax, rax
0x180135b90  jz      short loc_180135BCF
0x180135b92  lea     rcx, [rsp+48h+nLengthNeeded]
0x180135b97  mov     r9d, edi; nLength
0x180135b9a  mov     [rsp+48h+lpnLengthNeeded], rcx; lpnLengthNeeded
0x180135b9f  mov     r8, rax; pSecurityDescriptor
0x180135ba2  mov     rcx, rsi; lpFileName
0x180135ba5  mov     edx, 4; RequestedInformation
0x180135baa  call    cs:__imp_GetFileSecurityW
0x180135bb0  test    eax, eax
0x180135bb2  jnz     short loc_180135BCB
0x180135bb4  call    cs:__imp_GetLastError
0x180135bba  mov     ecx, eax
0x180135bbc  movzx   eax, ax
0x180135bbf  or      eax, 80070000h
0x180135bc4  test    ecx, ecx
0x180135bc6  cmovle  eax, ecx
0x180135bc9  jmp     short loc_180135BD4
0x180135bcb  xor     eax, eax
0x180135bcd  jmp     short loc_180135BD4
0x180135bcf  mov     eax, 8007000Eh
0x180135bd4  mov     rcx, [rsp+48h+var_10]
0x180135bd9  xor     rcx, rsp; StackCookie
0x180135bdc  call    __security_check_cookie
0x180135be1  mov     rbx, [rsp+48h+arg_10]
0x180135be6  mov     rsi, [rsp+48h+arg_18]
0x180135beb  add     rsp, 40h
0x180135bef  pop     rdi
0x180135bf0  retn
```
