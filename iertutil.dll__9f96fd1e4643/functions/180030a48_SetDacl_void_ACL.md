# SetDacl(void *,_ACL *)

- ea: `0x180030a48`
- end: `0x180030af9`
- name: `?SetDacl@@YAJPEAXPEAU_ACL@@@Z`
- size: `177`
- prototype: `__int64 __fastcall(HANDLE Handle, struct _ACL *Source)`
- caller_count: `2`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800306b0`
- `0x180065a60`

## callees

- `0x180030a48`

## import_xrefs

- `msvcrt!memcpy_s` at `0x180030aa2`
- `msvcrt!memcpy_s` at `0x180030aa2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180030ae2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180030ae2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180030ada`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180030ada`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180030a64`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180030a64`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x180030ab6`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x180030ab6`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x180030a8a`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x180030a8a`
- `api-ms-win-security-base-l1-1-0!SetKernelObjectSecurity` at `0x180030acb`
- `api-ms-win-security-base-l1-1-0!SetKernelObjectSecurity` at `0x180030acb`

## pseudocode

```c
__int64 __fastcall SetDacl(HANDLE Handle, struct _ACL *Source)
{
  struct _ACL *v4; // rax
  struct _ACL *v5; // rdi
  unsigned int v6; // ebx
  signed int LastError; // eax

  v4 = (struct _ACL *)LocalAlloc(0x40u, Source->AclSize + 40LL);
  v5 = v4;
  if ( v4 )
  {
    if ( InitializeSecurityDescriptor(v4, 1u)
      && (memcpy_s(&v5[5], Source->AclSize, Source, Source->AclSize), SetSecurityDescriptorDacl(v5, 1, v5 + 5, 0))
      && SetKernelObjectSecurity(Handle, 4u, v5) )
    {
      v6 = 0;
    }
    else
    {
      LastError = GetLastError();
      v6 = LastError;
      if ( LastError > 0 )
        v6 = (unsigned __int16)LastError | 0x80070000;
    }
    LocalFree(v5);
  }
  else
  {
    return (unsigned int)-2147024882;
  }
  return v6;
}

```

## disassembly

```asm
0x180030a48  push    rbx
0x180030a4a  push    rbp
0x180030a4b  push    rsi
0x180030a4c  push    rdi
0x180030a4d  sub     rsp, 28h
0x180030a51  mov     rsi, rdx
0x180030a54  mov     rbp, rcx
0x180030a57  movzx   edx, word ptr [rdx+2]
0x180030a5b  mov     ecx, 40h ; '@'; uFlags
0x180030a60  add     rdx, 28h ; '('; uBytes
0x180030a64  call    cs:__imp_LocalAlloc
0x180030a6a  mov     rdi, rax
0x180030a6d  test    rax, rax
0x180030a70  jnz     short loc_180030A82
0x180030a72  mov     ebx, 8007000Eh
0x180030a77  mov     eax, ebx
0x180030a79  add     rsp, 28h
0x180030a7d  pop     rdi
0x180030a7e  pop     rsi
0x180030a7f  pop     rbp
0x180030a80  pop     rbx
0x180030a81  retn
0x180030a82  mov     edx, 1; dwRevision
0x180030a87  mov     rcx, rdi; pSecurityDescriptor
0x180030a8a  call    cs:__imp_InitializeSecurityDescriptor
0x180030a90  test    eax, eax
0x180030a92  jz      short loc_180030AE2
0x180030a94  movzx   edx, word ptr [rsi+2]; DestinationSize
0x180030a98  lea     rcx, [rdi+28h]; Destination
0x180030a9c  mov     r9d, edx; SourceSize
0x180030a9f  mov     r8, rsi; Source
0x180030aa2  call    cs:__imp_memcpy_s
0x180030aa8  xor     r9d, r9d; bDaclDefaulted
0x180030aab  lea     r8, [rdi+28h]; pDacl
0x180030aaf  mov     rcx, rdi; pSecurityDescriptor
0x180030ab2  lea     edx, [r9+1]; bDaclPresent
0x180030ab6  call    cs:__imp_SetSecurityDescriptorDacl
0x180030abc  test    eax, eax
0x180030abe  jz      short loc_180030AE2
0x180030ac0  mov     r8, rdi; SecurityDescriptor
0x180030ac3  mov     edx, 4; SecurityInformation
0x180030ac8  mov     rcx, rbp; Handle
0x180030acb  call    cs:__imp_SetKernelObjectSecurity
0x180030ad1  test    eax, eax
0x180030ad3  jz      short loc_180030AE2
0x180030ad5  xor     ebx, ebx
0x180030ad7  mov     rcx, rdi; hMem
0x180030ada  call    cs:__imp_LocalFree
0x180030ae0  jmp     short loc_180030A77
0x180030ae2  call    cs:__imp_GetLastError
0x180030ae8  mov     ebx, eax
0x180030aea  test    eax, eax
0x180030aec  jle     short loc_180030AD7
0x180030aee  movzx   ebx, ax
0x180030af1  or      ebx, 80070000h
0x180030af7  jmp     short loc_180030AD7
```
