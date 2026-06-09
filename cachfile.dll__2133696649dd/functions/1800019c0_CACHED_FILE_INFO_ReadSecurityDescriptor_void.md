# CACHED_FILE_INFO::ReadSecurityDescriptor(void *)

- ea: `0x1800019c0`
- end: `0x180001aa2`
- name: `?ReadSecurityDescriptor@CACHED_FILE_INFO@@AEAAJPEAX@Z`
- size: `226`
- prototype: `int __fastcall(CACHED_FILE_INFO *this, void *)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180001630`

## callees

- `0x1800019c0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001a29`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001a4b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001a29`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001a4b`
- `api-ms-win-security-base-l1-1-0!GetKernelObjectSecurity` at `0x180001a0d`
- `api-ms-win-security-base-l1-1-0!GetKernelObjectSecurity` at `0x180001a93`
- `api-ms-win-security-base-l1-1-0!GetKernelObjectSecurity` at `0x180001a0d`
- `api-ms-win-security-base-l1-1-0!GetKernelObjectSecurity` at `0x180001a93`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x1800019ef`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180001a75`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x1800019ef`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180001a75`
- `iisutil!?Resize@BUFFER@@QEAA_NK@Z` at `0x180001a5d`
- `iisutil!?Resize@BUFFER@@QEAA_NK@Z` at `0x180001a5d`
- `iisutil!?QuerySize@BUFFER@@QEBAKXZ` at `0x1800019e4`
- `iisutil!?QuerySize@BUFFER@@QEBAKXZ` at `0x180001a6a`
- `iisutil!?QuerySize@BUFFER@@QEBAKXZ` at `0x1800019e4`
- `iisutil!?QuerySize@BUFFER@@QEBAKXZ` at `0x180001a6a`

## pseudocode

```c
int __fastcall CACHED_FILE_INFO::ReadSecurityDescriptor(CACHED_FILE_INFO *this, void *a2)
{
  BUFFER *v2; // rbx
  DWORD Size; // edi
  void *Ptr; // rax
  int result; // eax
  DWORD v7; // edi
  void *v8; // rax
  DWORD nLengthNeeded; // [rsp+40h] [rbp+8h] BYREF

  v2 = (CACHED_FILE_INFO *)((char *)this + 432);
  nLengthNeeded = 0;
  Size = BUFFER::QuerySize((CACHED_FILE_INFO *)((char *)this + 432));
  Ptr = BUFFER::QueryPtr(v2);
  if ( GetKernelObjectSecurity(a2, 7u, Ptr, Size, &nLengthNeeded) )
    return 0;
  if ( GetLastError() == 122 && BUFFER::Resize(v2, nLengthNeeded) )
  {
    v7 = BUFFER::QuerySize(v2);
    v8 = BUFFER::QueryPtr(v2);
    if ( GetKernelObjectSecurity(a2, 7u, v8, v7, &nLengthNeeded) )
      return 0;
  }
  result = GetLastError();
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x1800019c0  mov     [rsp+arg_8], rbx
0x1800019c5  mov     [rsp+arg_10], rsi
0x1800019ca  push    rdi
0x1800019cb  sub     rsp, 30h
0x1800019cf  lea     rbx, [rcx+1B0h]
0x1800019d6  mov     [rsp+38h+nLengthNeeded], 0
0x1800019de  mov     rcx, rbx
0x1800019e1  mov     rsi, rdx
0x1800019e4  call    cs:__imp_?QuerySize@BUFFER@@QEBAKXZ; BUFFER::QuerySize(void)
0x1800019ea  mov     rcx, rbx
0x1800019ed  mov     edi, eax
0x1800019ef  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x1800019f5  lea     rcx, [rsp+38h+nLengthNeeded]
0x1800019fa  mov     r9d, edi; nLength
0x1800019fd  mov     [rsp+38h+lpnLengthNeeded], rcx; lpnLengthNeeded
0x180001a02  mov     r8, rax; pSecurityDescriptor
0x180001a05  mov     rcx, rsi; Handle
0x180001a08  mov     edx, 7; RequestedInformation
0x180001a0d  call    cs:__imp_GetKernelObjectSecurity
0x180001a13  test    eax, eax
0x180001a15  jz      short loc_180001A4B
0x180001a17  xor     eax, eax
0x180001a19  mov     rbx, [rsp+38h+arg_8]
0x180001a1e  mov     rsi, [rsp+38h+arg_10]
0x180001a23  add     rsp, 30h
0x180001a27  pop     rdi
0x180001a28  retn
0x180001a29  call    cs:__imp_GetLastError
0x180001a2f  test    eax, eax
0x180001a31  jle     short loc_180001A19
0x180001a33  mov     rbx, [rsp+38h+arg_8]
0x180001a38  mov     rsi, [rsp+38h+arg_10]
0x180001a3d  movzx   eax, ax
0x180001a40  or      eax, 80070000h
0x180001a45  add     rsp, 30h
0x180001a49  pop     rdi
0x180001a4a  retn
0x180001a4b  call    cs:__imp_GetLastError
0x180001a51  cmp     eax, 7Ah ; 'z'
0x180001a54  jnz     short loc_180001A29
0x180001a56  mov     edx, [rsp+38h+nLengthNeeded]
0x180001a5a  mov     rcx, rbx
0x180001a5d  call    cs:__imp_?Resize@BUFFER@@QEAA_NK@Z; BUFFER::Resize(ulong)
0x180001a63  test    al, al
0x180001a65  jz      short loc_180001A29
0x180001a67  mov     rcx, rbx
0x180001a6a  call    cs:__imp_?QuerySize@BUFFER@@QEBAKXZ; BUFFER::QuerySize(void)
0x180001a70  mov     rcx, rbx
0x180001a73  mov     edi, eax
0x180001a75  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x180001a7b  lea     rcx, [rsp+38h+nLengthNeeded]
0x180001a80  mov     r9d, edi; nLength
0x180001a83  mov     [rsp+38h+lpnLengthNeeded], rcx; lpnLengthNeeded
0x180001a88  mov     r8, rax; pSecurityDescriptor
0x180001a8b  mov     rcx, rsi; Handle
0x180001a8e  mov     edx, 7; RequestedInformation
0x180001a93  call    cs:__imp_GetKernelObjectSecurity
0x180001a99  test    eax, eax
0x180001a9b  jz      short loc_180001A29
0x180001a9d  jmp     loc_180001A17
```
