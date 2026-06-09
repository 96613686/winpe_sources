# CreateFileMappingWithSecurity(ushort const *,ulong,void * *)

- ea: `0x18002a77c`
- end: `0x18002a835`
- name: `?CreateFileMappingWithSecurity@@YAJPEBGKPEAPEAX@Z`
- size: `185`
- prototype: `__int64 __fastcall(LPCWSTR lpName, DWORD dwMaximumSizeLow, void **)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x18002a5ac`

## callees

- `0x18000b200`
- `0x18002a77c`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002a824`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002a824`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18002a7cc`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18002a7cc`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x18002a7fa`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x18002a7fa`

## pseudocode

```c
__int64 __fastcall CreateFileMappingWithSecurity(LPCWSTR lpName, DWORD dwMaximumSizeLow, void **a3)
{
  NCoreLibrary *v6; // rcx
  int LastErrorAsFailHR; // ebx
  HANDLE v8; // rax
  NCoreLibrary *v9; // rcx
  _SECURITY_ATTRIBUTES FileMappingAttributes; // [rsp+30h] [rbp-48h] BYREF
  ULONG v12; // [rsp+80h] [rbp+8h] BYREF

  v12 = 0;
  memset(&FileMappingAttributes, 0, sizeof(FileMappingAttributes));
  if ( lpName && a3 )
  {
    *a3 = 0;
    FileMappingAttributes.nLength = 24;
    FileMappingAttributes.bInheritHandle = 0;
    if ( ConvertStringSecurityDescriptorToSecurityDescriptorW(
           L"D:(A;OICI;GA;;;BA)",
           1u,
           &FileMappingAttributes.lpSecurityDescriptor,
           &v12)
      || (LastErrorAsFailHR = NCoreLibrary::GetLastErrorAsFailHR(v6), LastErrorAsFailHR >= 0) )
    {
      v8 = CreateFileMappingW((HANDLE)0xFFFFFFFFFFFFFFFFLL, &FileMappingAttributes, 4u, 0, dwMaximumSizeLow, lpName);
      *a3 = v8;
      if ( v8 )
        LastErrorAsFailHR = 0;
      else
        LastErrorAsFailHR = NCoreLibrary::GetLastErrorAsFailHR(v9);
    }
  }
  else
  {
    LastErrorAsFailHR = -2147024809;
  }
  if ( FileMappingAttributes.lpSecurityDescriptor )
    LocalFree(FileMappingAttributes.lpSecurityDescriptor);
  return (unsigned int)LastErrorAsFailHR;
}

```

## disassembly

```asm
0x18002a77c  mov     r11, rsp
0x18002a77f  push    rbx
0x18002a780  push    rbp
0x18002a781  push    rsi
0x18002a782  push    rdi
0x18002a783  sub     rsp, 58h
0x18002a787  xor     eax, eax
0x18002a789  xorps   xmm0, xmm0
0x18002a78c  mov     [r11+8], eax
0x18002a790  mov     rdi, r8
0x18002a793  mov     ebp, edx
0x18002a795  mov     rsi, rcx
0x18002a798  movups  xmmword ptr [rsp+78h+FileMappingAttributes.nLength], xmm0
0x18002a79d  mov     [r11-38h], rax
0x18002a7a1  test    rcx, rcx
0x18002a7a4  jz      short loc_18002A815
0x18002a7a6  test    r8, r8
0x18002a7a9  jz      short loc_18002A815
0x18002a7ab  mov     [r8], rax
0x18002a7ae  lea     r9, [r11+8]; SecurityDescriptorSize
0x18002a7b2  lea     r8, [r11-40h]; SecurityDescriptor
0x18002a7b6  mov     [rsp+78h+FileMappingAttributes.nLength], 18h
0x18002a7be  lea     edx, [rax+1]; StringSDRevision
0x18002a7c1  mov     [rsp+78h+FileMappingAttributes.bInheritHandle], eax
0x18002a7c5  lea     rcx, StringSecurityDescriptor; "D:(A;OICI;GA;;;BA)"
0x18002a7cc  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x18002a7d2  test    eax, eax
0x18002a7d4  jnz     short loc_18002A7E1
0x18002a7d6  call    ?GetLastErrorAsFailHR@NCoreLibrary@@YAJXZ; NCoreLibrary::GetLastErrorAsFailHR(void)
0x18002a7db  mov     ebx, eax
0x18002a7dd  test    eax, eax
0x18002a7df  js      short loc_18002A81A
0x18002a7e1  xor     r9d, r9d; dwMaximumSizeHigh
0x18002a7e4  mov     [rsp+78h+lpName], rsi; lpName
0x18002a7e9  lea     rdx, [rsp+78h+FileMappingAttributes]; lpFileMappingAttributes
0x18002a7ee  mov     [rsp+78h+dwMaximumSizeLow], ebp; dwMaximumSizeLow
0x18002a7f2  or      rcx, 0FFFFFFFFFFFFFFFFh; hFile
0x18002a7f6  lea     r8d, [r9+4]; flProtect
0x18002a7fa  call    cs:__imp_CreateFileMappingW
0x18002a800  mov     [rdi], rax
0x18002a803  test    rax, rax
0x18002a806  jz      short loc_18002A80C
0x18002a808  xor     ebx, ebx
0x18002a80a  jmp     short loc_18002A81A
0x18002a80c  call    ?GetLastErrorAsFailHR@NCoreLibrary@@YAJXZ; NCoreLibrary::GetLastErrorAsFailHR(void)
0x18002a811  mov     ebx, eax
0x18002a813  jmp     short loc_18002A81A
0x18002a815  mov     ebx, 80070057h
0x18002a81a  mov     rcx, [rsp+78h+FileMappingAttributes.lpSecurityDescriptor]; hMem
0x18002a81f  test    rcx, rcx
0x18002a822  jz      short loc_18002A82A
0x18002a824  call    cs:__imp_LocalFree
0x18002a82a  mov     eax, ebx
0x18002a82c  add     rsp, 58h
0x18002a830  pop     rdi
0x18002a831  pop     rsi
0x18002a832  pop     rbp
0x18002a833  pop     rbx
0x18002a834  retn
```
