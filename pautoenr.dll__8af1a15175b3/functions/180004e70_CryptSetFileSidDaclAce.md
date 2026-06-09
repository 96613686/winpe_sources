# _CryptSetFileSidDaclAce

- ea: `0x180004e70`
- end: `0x180004fa6`
- name: `_CryptSetFileSidDaclAce`
- size: `310`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName, __int64, unsigned int, __int64, __int64, _DWORD *)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x180001100`

## callees

- `0x180004e70`
- `0x180005200`
- `0x1800052c0`
- `0x1800077e4`
- `0x180007994`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004ee4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004ee4`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x180004f4b`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x180004f4b`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x180004f60`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x180004f60`
- `api-ms-win-security-base-l1-1-0!GetFileSecurityW` at `0x180004eda`
- `api-ms-win-security-base-l1-1-0!GetFileSecurityW` at `0x180004eda`
- `api-ms-win-security-base-l1-1-0!SetFileSecurityW` at `0x180004f75`
- `api-ms-win-security-base-l1-1-0!SetFileSecurityW` at `0x180004f75`

## pseudocode

```c
__int64 __fastcall CryptSetFileSidDaclAce(
        LPCWSTR lpFileName,
        __int64 a2,
        unsigned int a3,
        __int64 a4,
        __int64 a5,
        _DWORD *a6)
{
  void *v8; // rdi
  __int64 v9; // rdx
  __int64 v10; // rax
  unsigned int v11; // ebx
  DWORD nLengthNeeded; // [rsp+88h] [rbp+20h] BYREF

  nLengthNeeded = 1024;
  *a6 = 0;
  v8 = (void *)PkiAlloc(0x400u);
  if ( !v8 )
    goto LABEL_8;
  while ( !GetFileSecurityW(lpFileName, 4u, v8, nLengthNeeded, &nLengthNeeded) )
  {
    if ( GetLastError() != 122 )
      goto LABEL_8;
    v10 = PkiRealloc(v8, nLengthNeeded);
    if ( !v10 )
      goto LABEL_8;
    v8 = (void *)v10;
  }
  if ( (unsigned int)CryptSetSidDaclAce(v8, v9, a3) )
    v11 = 1;
  else
LABEL_8:
    v11 = 0;
  PkiFree(v8);
  PkiFree(0);
  return v11;
}

```

## disassembly

```asm
0x180004e70  mov     rax, rsp
0x180004e73  mov     [rax+8], rbx
0x180004e77  mov     [rax+10h], rbp
0x180004e7b  mov     [rax+20h], r9d
0x180004e7f  push    rsi
0x180004e80  push    rdi
0x180004e81  push    r14
0x180004e83  sub     rsp, 50h
0x180004e87  mov     rbx, [rsp+68h+arg_28]
0x180004e8f  mov     rbp, rcx
0x180004e92  xor     esi, esi
0x180004e94  mov     dword ptr [rax+20h], 400h
0x180004e9b  mov     ecx, 400h; uBytes
0x180004ea0  mov     [rax-28h], rsi
0x180004ea4  mov     r14d, r8d
0x180004ea7  mov     [rbx], esi
0x180004ea9  call    PkiAlloc
0x180004eae  mov     rdi, rax
0x180004eb1  test    rax, rax
0x180004eb4  jz      loc_180004F7F
0x180004eba  mov     r9d, [rsp+68h+nLengthNeeded]; nLength
0x180004ec2  lea     rax, [rsp+68h+nLengthNeeded]
0x180004eca  mov     r8, rdi; pSecurityDescriptor
0x180004ecd  mov     [rsp+68h+lpnLengthNeeded], rax; lpnLengthNeeded
0x180004ed2  mov     edx, 4; RequestedInformation
0x180004ed7  mov     rcx, rbp; lpFileName
0x180004eda  call    cs:__imp_GetFileSecurityW
0x180004ee0  test    eax, eax
0x180004ee2  jnz     short loc_180004F0C
0x180004ee4  call    cs:__imp_GetLastError
0x180004eea  cmp     eax, 7Ah ; 'z'
0x180004eed  jnz     loc_180004F7F
0x180004ef3  mov     edx, [rsp+68h+nLengthNeeded]
0x180004efa  mov     rcx, rdi
0x180004efd  call    PkiRealloc
0x180004f02  test    rax, rax
0x180004f05  jz      short loc_180004F7F
0x180004f07  mov     rdi, rax
0x180004f0a  jmp     short loc_180004EBA
0x180004f0c  lea     rax, [rsp+68h+pDacl]
0x180004f11  mov     r8d, r14d
0x180004f14  mov     [rsp+68h+var_38], rax
0x180004f19  mov     rcx, rdi
0x180004f1c  mov     rax, [rsp+68h+arg_20]
0x180004f24  mov     [rsp+68h+var_40], rbx
0x180004f29  mov     [rsp+68h+lpnLengthNeeded], rax
0x180004f2e  call    _CryptSetSidDaclAce
0x180004f33  mov     rsi, [rsp+68h+pDacl]
0x180004f38  test    eax, eax
0x180004f3a  jz      short loc_180004F7F
0x180004f3c  mov     ebx, 1
0x180004f41  test    rsi, rsi
0x180004f44  jz      short loc_180004F81
0x180004f46  mov     edx, ebx; dwRevision
0x180004f48  mov     rcx, rdi; pSecurityDescriptor
0x180004f4b  call    cs:__imp_InitializeSecurityDescriptor
0x180004f51  test    eax, eax
0x180004f53  jz      short loc_180004F7F
0x180004f55  xor     r9d, r9d; bDaclDefaulted
0x180004f58  mov     r8, rsi; pDacl
0x180004f5b  mov     edx, ebx; bDaclPresent
0x180004f5d  mov     rcx, rdi; pSecurityDescriptor
0x180004f60  call    cs:__imp_SetSecurityDescriptorDacl
0x180004f66  test    eax, eax
0x180004f68  jz      short loc_180004F7F
0x180004f6a  mov     r8, rdi; pSecurityDescriptor
0x180004f6d  mov     edx, 4; SecurityInformation
0x180004f72  mov     rcx, rbp; lpFileName
0x180004f75  call    cs:__imp_SetFileSecurityW
0x180004f7b  test    eax, eax
0x180004f7d  jnz     short loc_180004F81
0x180004f7f  xor     ebx, ebx
0x180004f81  mov     rcx, rdi; hMem
0x180004f84  call    PkiFree
0x180004f89  mov     rcx, rsi; hMem
0x180004f8c  call    PkiFree
0x180004f91  mov     rbp, [rsp+68h+arg_8]
0x180004f96  mov     eax, ebx
0x180004f98  mov     rbx, [rsp+68h+arg_0]
0x180004f9d  add     rsp, 50h
0x180004fa1  pop     r14
0x180004fa3  pop     rdi
0x180004fa4  pop     rsi
0x180004fa5  retn
```
