# CreateSignatureKey(ushort const *)

- ea: `0x180017180`
- end: `0x18001736e`
- name: `?CreateSignatureKey@@YAJPEBG@Z`
- size: `494`
- prototype: `__int64 __fastcall(const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800175a4`

## callees

- `0x18000e214`
- `0x18000e234`
- `0x180017180`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001729e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001732a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001729e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001732a`
- `ncrypt!NCryptFreeObject` at `0x1800171d8`
- `ncrypt!NCryptFreeObject` at `0x180017246`
- `ncrypt!NCryptFreeObject` at `0x18001733f`
- `ncrypt!NCryptFreeObject` at `0x180017354`
- `ncrypt!NCryptFreeObject` at `0x1800171d8`
- `ncrypt!NCryptFreeObject` at `0x180017246`
- `ncrypt!NCryptFreeObject` at `0x18001733f`
- `ncrypt!NCryptFreeObject` at `0x180017354`
- `ncrypt!NCryptSetProperty` at `0x1800172d6`
- `ncrypt!NCryptSetProperty` at `0x1800172d6`
- `ncrypt!NCryptFinalizeKey` at `0x180017308`
- `ncrypt!NCryptFinalizeKey` at `0x180017308`
- `ncrypt!NCryptCreatePersistedKey` at `0x180017213`
- `ncrypt!NCryptCreatePersistedKey` at `0x180017213`
- `ncrypt!NCryptOpenStorageProvider` at `0x1800171a5`
- `ncrypt!NCryptOpenStorageProvider` at `0x1800171a5`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorLength` at `0x1800172b0`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorLength` at `0x1800172b0`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18001726e`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18001726e`

## string_xrefs

- `0x1800171bb`: `onecore\base\appmodel\execmodel\desktopappx\lib\processcreationextensions.cpp`
- `0x180017229`: `onecore\base\appmodel\execmodel\desktopappx\lib\processcreationextensions.cpp`
- `0x180017282`: `onecore\base\appmodel\execmodel\desktopappx\lib\processcreationextensions.cpp`
- `0x1800172f1`: `onecore\base\appmodel\execmodel\desktopappx\lib\processcreationextensions.cpp`
- `0x1800172c0`: `Security Descr`

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
  DWORD v8; // [rsp+20h] [rbp-10h]
  DWORD v9; // [rsp+20h] [rbp-10h]
  DWORD v10; // [rsp+20h] [rbp-10h]
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
      (void *)0x3D8,
      (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\processcreationextensions.cpp",
      (const char *)(unsigned int)v1,
      v8);
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
      (void *)0x3DD,
      (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\processcreationextensions.cpp",
      (const char *)(unsigned int)v4,
      v9);
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
                  (void *)0x3E5,
                  (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\processcreationextensions.cpp",
                  v5);
    goto LABEL_12;
  }
  SecurityDescriptorLength = GetSecurityDescriptorLength(SecurityDescriptor);
  LastError = NCryptSetProperty(phKey, L"Security Descr", (PBYTE)SecurityDescriptor, SecurityDescriptorLength, 4u);
  if ( LastError < 0 )
  {
    v7 = 1001;
LABEL_16:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v7,
      (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\processcreationextensions.cpp",
      (const char *)(unsigned int)LastError,
      v10);
LABEL_12:
    if ( SecurityDescriptor )
      LocalFree(SecurityDescriptor);
    goto LABEL_8;
  }
  LastError = NCryptFinalizeKey(phKey, 0);
  if ( LastError < 0 )
  {
    v7 = 1003;
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
0x180017180  mov     [rsp-8+arg_18], rbx
0x180017185  mov     [rsp-8+phKey], rcx
0x18001718a  push    rbp
0x18001718b  mov     rbp, rsp
0x18001718e  sub     rsp, 30h
0x180017192  and     [rbp+phProvider], 0
0x180017197  lea     rdx, pszProviderName; "Microsoft Software Key Storage Provider"
0x18001719e  xor     r8d, r8d; dwFlags
0x1800171a1  lea     rcx, [rbp+phProvider]; phProvider
0x1800171a5  call    cs:__imp_NCryptOpenStorageProvider
0x1800171ac  nop     dword ptr [rax+rax+00h]
0x1800171b1  mov     ebx, eax
0x1800171b3  test    eax, eax
0x1800171b5  jns     short loc_1800171EB
0x1800171b7  mov     rcx, [rbp+8]; this
0x1800171bb  lea     r8, aOnecoreBaseApp_22; "onecore\\base\\appmodel\\execmodel\\des"...
0x1800171c2  mov     r9d, eax; char *
0x1800171c5  mov     edx, 3D8h; void *
0x1800171ca  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800171cf  mov     rcx, [rbp+phProvider]; hObject
0x1800171d3  test    rcx, rcx
0x1800171d6  jz      short loc_1800171E4
0x1800171d8  call    cs:__imp_NCryptFreeObject
0x1800171df  nop     dword ptr [rax+rax+00h]
0x1800171e4  mov     eax, ebx
0x1800171e6  jmp     loc_180017362
0x1800171eb  mov     rcx, [rbp+phProvider]; hProvider
0x1800171ef  lea     r9, pszKeyName; "SparseGenerationAppxsvcKey"
0x1800171f6  and     [rbp+phKey], 0
0x1800171fb  lea     r8, pszAlgId; "ECDSA_P384"
0x180017202  mov     [rsp+30h+dwFlags], 0A0h; dwFlags
0x18001720a  lea     rdx, [rbp+phKey]; phKey
0x18001720e  and     [rsp+30h+var_10], 0
0x180017213  call    cs:__imp_NCryptCreatePersistedKey
0x18001721a  nop     dword ptr [rax+rax+00h]
0x18001721f  mov     ebx, eax
0x180017221  test    eax, eax
0x180017223  jns     short loc_180017257
0x180017225  mov     rcx, [rbp+8]; this
0x180017229  lea     r8, aOnecoreBaseApp_22; "onecore\\base\\appmodel\\execmodel\\des"...
0x180017230  mov     r9d, eax; char *
0x180017233  mov     edx, 3DDh; void *
0x180017238  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001723d  mov     rcx, [rbp+phKey]; hObject
0x180017241  test    rcx, rcx
0x180017244  jz      short loc_1800171CF
0x180017246  call    cs:__imp_NCryptFreeObject
0x18001724d  nop     dword ptr [rax+rax+00h]
0x180017252  jmp     loc_1800171CF
0x180017257  and     [rbp+SecurityDescriptor], 0
0x18001725c  lea     r8, [rbp+SecurityDescriptor]; SecurityDescriptor
0x180017260  xor     r9d, r9d; SecurityDescriptorSize
0x180017263  lea     rcx, StringSecurityDescriptor; "D:P(A;;FA;;;BA)S:(ML;;NW;;;HI)"
0x18001726a  lea     edx, [r9+1]; StringSDRevision
0x18001726e  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x180017275  nop     dword ptr [rax+rax+00h]
0x18001727a  test    eax, eax
0x18001727c  jnz     short loc_1800172AC
0x18001727e  mov     rcx, [rbp+8]; this
0x180017282  lea     r8, aOnecoreBaseApp_22; "onecore\\base\\appmodel\\execmodel\\des"...
0x180017289  mov     edx, 3E5h; void *
0x18001728e  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180017293  mov     ebx, eax
0x180017295  mov     rcx, [rbp+SecurityDescriptor]; hMem
0x180017299  test    rcx, rcx
0x18001729c  jz      short loc_18001723D
0x18001729e  call    cs:__imp_LocalFree
0x1800172a5  nop     dword ptr [rax+rax+00h]
0x1800172aa  jmp     short loc_18001723D
0x1800172ac  mov     rcx, [rbp+SecurityDescriptor]; pSecurityDescriptor
0x1800172b0  call    cs:__imp_GetSecurityDescriptorLength
0x1800172b7  nop     dword ptr [rax+rax+00h]
0x1800172bc  mov     r8, [rbp+SecurityDescriptor]; pbInput
0x1800172c0  lea     rdx, pszProperty; "Security Descr"
0x1800172c7  mov     rcx, [rbp+phKey]; hObject
0x1800172cb  mov     r9d, eax; cbInput
0x1800172ce  mov     [rsp+30h+var_10], 4; int
0x1800172d6  call    cs:__imp_NCryptSetProperty
0x1800172dd  nop     dword ptr [rax+rax+00h]
0x1800172e2  mov     ebx, eax
0x1800172e4  test    eax, eax
0x1800172e6  jns     short loc_180017302
0x1800172e8  mov     edx, 3E9h; void *
0x1800172ed  mov     rcx, [rbp+8]; this
0x1800172f1  lea     r8, aOnecoreBaseApp_22; "onecore\\base\\appmodel\\execmodel\\des"...
0x1800172f8  mov     r9d, ebx; char *
0x1800172fb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180017300  jmp     short loc_180017295
0x180017302  mov     rcx, [rbp+phKey]; hKey
0x180017306  xor     edx, edx; dwFlags
0x180017308  call    cs:__imp_NCryptFinalizeKey
0x18001730f  nop     dword ptr [rax+rax+00h]
0x180017314  mov     ebx, eax
0x180017316  test    eax, eax
0x180017318  jns     short loc_180017321
0x18001731a  mov     edx, 3EBh
0x18001731f  jmp     short loc_1800172ED
0x180017321  mov     rcx, [rbp+SecurityDescriptor]; hMem
0x180017325  test    rcx, rcx
0x180017328  jz      short loc_180017336
0x18001732a  call    cs:__imp_LocalFree
0x180017331  nop     dword ptr [rax+rax+00h]
0x180017336  mov     rcx, [rbp+phKey]; hObject
0x18001733a  test    rcx, rcx
0x18001733d  jz      short loc_18001734B
0x18001733f  call    cs:__imp_NCryptFreeObject
0x180017346  nop     dword ptr [rax+rax+00h]
0x18001734b  mov     rcx, [rbp+phProvider]; hObject
0x18001734f  test    rcx, rcx
0x180017352  jz      short loc_180017360
0x180017354  call    cs:__imp_NCryptFreeObject
0x18001735b  nop     dword ptr [rax+rax+00h]
0x180017360  xor     eax, eax
0x180017362  mov     rbx, [rsp+30h+arg_18]
0x180017367  add     rsp, 30h
0x18001736b  pop     rbp
0x18001736c  retn
```
