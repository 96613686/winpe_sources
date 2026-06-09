# CreateSignatureKey(ushort const *)

- ea: `0x180018dc0`
- end: `0x180018fba`
- name: `?CreateSignatureKey@@YAJPEBG@Z`
- size: `506`
- prototype: `__int64 __fastcall(const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180019200`

## callees

- `0x18000ff04`
- `0x18000ff24`
- `0x180018dc0`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180018eea`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180018f76`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180018eea`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180018f76`
- `ncrypt!NCryptFinalizeKey` at `0x180018f54`
- `ncrypt!NCryptFinalizeKey` at `0x180018f54`
- `ncrypt!NCryptFreeObject` at `0x180018e1b`
- `ncrypt!NCryptFreeObject` at `0x180018e8f`
- `ncrypt!NCryptFreeObject` at `0x180018f8b`
- `ncrypt!NCryptFreeObject` at `0x180018fa0`
- `ncrypt!NCryptFreeObject` at `0x180018e1b`
- `ncrypt!NCryptFreeObject` at `0x180018e8f`
- `ncrypt!NCryptFreeObject` at `0x180018f8b`
- `ncrypt!NCryptFreeObject` at `0x180018fa0`
- `ncrypt!NCryptSetProperty` at `0x180018f22`
- `ncrypt!NCryptSetProperty` at `0x180018f22`
- `ncrypt!NCryptCreatePersistedKey` at `0x180018e5c`
- `ncrypt!NCryptCreatePersistedKey` at `0x180018e5c`
- `ncrypt!NCryptOpenStorageProvider` at `0x180018de8`
- `ncrypt!NCryptOpenStorageProvider` at `0x180018de8`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorLength` at `0x180018efc`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorLength` at `0x180018efc`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180018eba`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180018eba`

## string_xrefs

- `0x180018dfe`: `onecore\base\appmodel\execmodel\desktopappx\lib\processcreationextensions.cpp`
- `0x180018e72`: `onecore\base\appmodel\execmodel\desktopappx\lib\processcreationextensions.cpp`
- `0x180018ece`: `onecore\base\appmodel\execmodel\desktopappx\lib\processcreationextensions.cpp`
- `0x180018f3d`: `onecore\base\appmodel\execmodel\desktopappx\lib\processcreationextensions.cpp`
- `0x180018f0c`: `Security Descr`

## pseudocode

```c
__int64 __fastcall CreateSignatureKey(const unsigned __int16 *a1)
{
  SECURITY_STATUS v1; // eax
  SECURITY_STATUS LastError; // ebx
  SECURITY_STATUS v4; // eax
  const char *v5; // r9
  DWORD SecurityDescriptorLength; // eax
  __int64 v7; // rdx
  DWORD dwLegacyKeySpec; // [rsp+20h] [rbp-10h]
  DWORD dwLegacyKeySpeca; // [rsp+20h] [rbp-10h]
  DWORD dwLegacyKeySpecb; // [rsp+20h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+8h]
  NCRYPT_KEY_HANDLE phKey; // [rsp+40h] [rbp+10h] BYREF
  NCRYPT_PROV_HANDLE phProvider; // [rsp+48h] [rbp+18h] BYREF
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+50h] [rbp+20h] BYREF

  phKey = (NCRYPT_KEY_HANDLE)a1;
  phProvider = 0;
  v1 = NCryptOpenStorageProvider(&phProvider, L"Microsoft Software Key Storage Provider", 0);
  LastError = v1;
  if ( v1 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3DA,
      (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\processcreationextensions.cpp",
      (const char *)(unsigned int)v1,
      dwLegacyKeySpec);
LABEL_3:
    if ( phProvider )
      NCryptFreeObject(phProvider);
    return (unsigned int)LastError;
  }
  phKey = 0;
  v4 = NCryptCreatePersistedKey(phProvider, &phKey, L"ECDSA_P384", L"SparseGenerationAppxsvcKey", 0, 0xA0u);
  LastError = v4;
  if ( v4 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3DF,
      (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\processcreationextensions.cpp",
      (const char *)(unsigned int)v4,
      dwLegacyKeySpeca);
LABEL_8:
    if ( phKey )
      NCryptFreeObject(phKey);
    goto LABEL_3;
  }
  SecurityDescriptor = 0;
  if ( !ConvertStringSecurityDescriptorToSecurityDescriptorW(
          L"D:P(A;;FA;;;BA)S:(ML;;NW;;;HI)",
          1u,
          &SecurityDescriptor,
          0) )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x3E7,
                  (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\processcreationextensions.cpp",
                  v5);
    goto LABEL_12;
  }
  SecurityDescriptorLength = GetSecurityDescriptorLength(SecurityDescriptor);
  LastError = NCryptSetProperty(phKey, L"Security Descr", (PBYTE)SecurityDescriptor, SecurityDescriptorLength, 4u);
  if ( LastError < 0 )
  {
    v7 = 1003;
LABEL_16:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v7,
      (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\processcreationextensions.cpp",
      (const char *)(unsigned int)LastError,
      dwLegacyKeySpecb);
LABEL_12:
    if ( SecurityDescriptor )
      LocalFree(SecurityDescriptor);
    goto LABEL_8;
  }
  LastError = NCryptFinalizeKey(phKey, 0);
  if ( LastError < 0 )
  {
    v7 = 1005;
    goto LABEL_16;
  }
  if ( SecurityDescriptor )
    LocalFree(SecurityDescriptor);
  if ( phKey )
    NCryptFreeObject(phKey);
  if ( phProvider )
    NCryptFreeObject(phProvider);
  return 0;
}

```

## disassembly

```asm
0x180018dc0  mov     [rsp-8+arg_18], rbx
0x180018dc5  mov     [rsp-8+phKey], rcx
0x180018dca  push    rbp
0x180018dcb  mov     rbp, rsp
0x180018dce  sub     rsp, 30h
0x180018dd2  xor     r8d, r8d; dwFlags
0x180018dd5  mov     [rbp+phProvider], 0
0x180018ddd  lea     rdx, pszProviderName; "Microsoft Software Key Storage Provider"
0x180018de4  lea     rcx, [rbp+phProvider]; phProvider
0x180018de8  call    cs:__imp_NCryptOpenStorageProvider
0x180018def  nop     dword ptr [rax+rax+00h]
0x180018df4  mov     ebx, eax
0x180018df6  test    eax, eax
0x180018df8  jns     short loc_180018E2E
0x180018dfa  mov     rcx, [rbp+8]; this
0x180018dfe  lea     r8, aOnecoreBaseApp_23; "onecore\\base\\appmodel\\execmodel\\des"...
0x180018e05  mov     r9d, eax; char *
0x180018e08  mov     edx, 3DAh; void *
0x180018e0d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180018e12  mov     rcx, [rbp+phProvider]; hObject
0x180018e16  test    rcx, rcx
0x180018e19  jz      short loc_180018E27
0x180018e1b  call    cs:__imp_NCryptFreeObject
0x180018e22  nop     dword ptr [rax+rax+00h]
0x180018e27  mov     eax, ebx
0x180018e29  jmp     loc_180018FAE
0x180018e2e  mov     rcx, [rbp+phProvider]; hProvider
0x180018e32  lea     r9, pszKeyName; "SparseGenerationAppxsvcKey"
0x180018e39  mov     [rsp+30h+dwFlags], 0A0h; dwFlags
0x180018e41  lea     r8, pszAlgId; "ECDSA_P384"
0x180018e48  lea     rdx, [rbp+phKey]; phKey
0x180018e4c  mov     [rsp+30h+dwLegacyKeySpec], 0; int
0x180018e54  mov     [rbp+phKey], 0
0x180018e5c  call    cs:__imp_NCryptCreatePersistedKey
0x180018e63  nop     dword ptr [rax+rax+00h]
0x180018e68  mov     ebx, eax
0x180018e6a  test    eax, eax
0x180018e6c  jns     short loc_180018EA0
0x180018e6e  mov     rcx, [rbp+8]; this
0x180018e72  lea     r8, aOnecoreBaseApp_23; "onecore\\base\\appmodel\\execmodel\\des"...
0x180018e79  mov     r9d, eax; char *
0x180018e7c  mov     edx, 3DFh; void *
0x180018e81  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180018e86  mov     rcx, [rbp+phKey]; hObject
0x180018e8a  test    rcx, rcx
0x180018e8d  jz      short loc_180018E12
0x180018e8f  call    cs:__imp_NCryptFreeObject
0x180018e96  nop     dword ptr [rax+rax+00h]
0x180018e9b  jmp     loc_180018E12
0x180018ea0  xor     r9d, r9d; SecurityDescriptorSize
0x180018ea3  mov     [rbp+SecurityDescriptor], 0
0x180018eab  lea     r8, [rbp+SecurityDescriptor]; SecurityDescriptor
0x180018eaf  lea     rcx, StringSecurityDescriptor; "D:P(A;;FA;;;BA)S:(ML;;NW;;;HI)"
0x180018eb6  lea     edx, [r9+1]; StringSDRevision
0x180018eba  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x180018ec1  nop     dword ptr [rax+rax+00h]
0x180018ec6  test    eax, eax
0x180018ec8  jnz     short loc_180018EF8
0x180018eca  mov     rcx, [rbp+8]; this
0x180018ece  lea     r8, aOnecoreBaseApp_23; "onecore\\base\\appmodel\\execmodel\\des"...
0x180018ed5  mov     edx, 3E7h; void *
0x180018eda  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180018edf  mov     ebx, eax
0x180018ee1  mov     rcx, [rbp+SecurityDescriptor]; hMem
0x180018ee5  test    rcx, rcx
0x180018ee8  jz      short loc_180018E86
0x180018eea  call    cs:__imp_LocalFree
0x180018ef1  nop     dword ptr [rax+rax+00h]
0x180018ef6  jmp     short loc_180018E86
0x180018ef8  mov     rcx, [rbp+SecurityDescriptor]; pSecurityDescriptor
0x180018efc  call    cs:__imp_GetSecurityDescriptorLength
0x180018f03  nop     dword ptr [rax+rax+00h]
0x180018f08  mov     r8, [rbp+SecurityDescriptor]; pbInput
0x180018f0c  lea     rdx, pszProperty; "Security Descr"
0x180018f13  mov     rcx, [rbp+phKey]; hObject
0x180018f17  mov     r9d, eax; cbInput
0x180018f1a  mov     [rsp+30h+dwLegacyKeySpec], 4; int
0x180018f22  call    cs:__imp_NCryptSetProperty
0x180018f29  nop     dword ptr [rax+rax+00h]
0x180018f2e  mov     ebx, eax
0x180018f30  test    eax, eax
0x180018f32  jns     short loc_180018F4E
0x180018f34  mov     edx, 3EBh; void *
0x180018f39  mov     rcx, [rbp+8]; this
0x180018f3d  lea     r8, aOnecoreBaseApp_23; "onecore\\base\\appmodel\\execmodel\\des"...
0x180018f44  mov     r9d, ebx; char *
0x180018f47  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180018f4c  jmp     short loc_180018EE1
0x180018f4e  mov     rcx, [rbp+phKey]; hKey
0x180018f52  xor     edx, edx; dwFlags
0x180018f54  call    cs:__imp_NCryptFinalizeKey
0x180018f5b  nop     dword ptr [rax+rax+00h]
0x180018f60  mov     ebx, eax
0x180018f62  test    eax, eax
0x180018f64  jns     short loc_180018F6D
0x180018f66  mov     edx, 3EDh
0x180018f6b  jmp     short loc_180018F39
0x180018f6d  mov     rcx, [rbp+SecurityDescriptor]; hMem
0x180018f71  test    rcx, rcx
0x180018f74  jz      short loc_180018F82
0x180018f76  call    cs:__imp_LocalFree
0x180018f7d  nop     dword ptr [rax+rax+00h]
0x180018f82  mov     rcx, [rbp+phKey]; hObject
0x180018f86  test    rcx, rcx
0x180018f89  jz      short loc_180018F97
0x180018f8b  call    cs:__imp_NCryptFreeObject
0x180018f92  nop     dword ptr [rax+rax+00h]
0x180018f97  mov     rcx, [rbp+phProvider]; hObject
0x180018f9b  test    rcx, rcx
0x180018f9e  jz      short loc_180018FAC
0x180018fa0  call    cs:__imp_NCryptFreeObject
0x180018fa7  nop     dword ptr [rax+rax+00h]
0x180018fac  xor     eax, eax
0x180018fae  mov     rbx, [rsp+30h+arg_18]
0x180018fb3  add     rsp, 30h
0x180018fb7  pop     rbp
0x180018fb8  retn
```
