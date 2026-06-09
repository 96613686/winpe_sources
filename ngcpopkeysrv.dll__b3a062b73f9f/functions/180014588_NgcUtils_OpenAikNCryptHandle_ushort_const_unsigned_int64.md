# NgcUtils::OpenAikNCryptHandle(ushort const *,unsigned __int64 *)

- ea: `0x180014588`
- end: `0x1800146f5`
- name: `?OpenAikNCryptHandle@NgcUtils@@YAJPEBGPEA_K@Z`
- size: `365`
- prototype: `__int64 __fastcall(NgcUtils *this, unsigned __int16 *, unsigned __int64 *)`
- caller_count: `3`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180015410`
- `0x180016f58`
- `0x18001dc5c`

## callees

- `0x18000b0fc`
- `0x18000db5c`
- `0x180010730`
- `0x180011e48`
- `0x180014380`
- `0x180014588`
- `0x180014ab0`
- `0x180015000`
- `0x1800152f4`

## import_xrefs

- `ncrypt!NCryptOpenKey` at `0x180014694`
- `ncrypt!NCryptOpenKey` at `0x180014694`
- `ncrypt!NCryptOpenStorageProvider` at `0x1800145b3`
- `ncrypt!NCryptOpenStorageProvider` at `0x1800145b3`

## string_xrefs

- `0x1800145c3`: `onecore\ds\security\ngc\utils\common\lib\cryptutils.cpp`
- `0x18001462b`: `onecore\ds\security\ngc\utils\common\lib\cryptutils.cpp`
- `0x1800146a4`: `onecore\ds\security\ngc\utils\common\lib\cryptutils.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall NgcUtils::OpenAikNCryptHandle(NgcUtils *this, unsigned __int16 *a2, unsigned __int64 *a3)
{
  SECURITY_STATUS v5; // eax
  unsigned __int64 v6; // r8
  unsigned int v7; // ebx
  int v8; // ebx
  const unsigned __int16 *v9; // r8
  unsigned __int16 **v10; // rdx
  int WindowsAikAlternateLocation; // eax
  const unsigned __int16 *v12; // r9
  __int64 v13; // rdx
  SECURITY_STATUS v14; // eax
  DWORD dwFlags; // [rsp+20h] [rbp-20h]
  DWORD dwFlagsa; // [rsp+20h] [rbp-20h]
  NCRYPT_PROV_HANDLE phProvider[2]; // [rsp+30h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+18h]
  unsigned __int16 *v20; // [rsp+70h] [rbp+30h] BYREF
  NCRYPT_KEY_HANDLE phKey; // [rsp+78h] [rbp+38h] BYREF

  phProvider[0] = 0;
  v5 = NCryptOpenStorageProvider(phProvider, L"Microsoft Platform Crypto Provider", 0);
  v7 = v5;
  if ( v5 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2F,
      (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\lib\\cryptutils.cpp",
      (const char *)(unsigned int)v5,
      dwFlags);
    goto LABEL_14;
  }
  v8 = 0;
  if ( NgcUtils::IsStringNullTerminated(this, (const unsigned __int16 *)0xC, v6)
    && NgcUtils::AreStringsEqual(this, L"Windows AIK", v9) )
  {
    v20 = 0;
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
      &v20,
      0);
    WindowsAikAlternateLocation = NgcUtils::GetWindowsAikAlternateLocation((NgcUtils *)&v20, v10);
    v7 = WindowsAikAlternateLocation;
    if ( WindowsAikAlternateLocation < 0 )
    {
      v13 = 56;
LABEL_7:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v13,
        (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\lib\\cryptutils.cpp",
        (const char *)(unsigned int)WindowsAikAlternateLocation,
        dwFlags);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v20);
      goto LABEL_14;
    }
    WindowsAikAlternateLocation = NgcUtils::SetNCryptStringProperty(
                                    (NgcUtils *)phProvider[0],
                                    (unsigned __int64)L"PCP_ALTERNATE_KEY_STORAGE_LOCATION",
                                    v20,
                                    v12);
    v7 = WindowsAikAlternateLocation;
    if ( WindowsAikAlternateLocation < 0 )
    {
      v13 = 61;
      goto LABEL_7;
    }
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v20);
    v8 = 1;
  }
  phKey = 0;
  v14 = NCryptOpenKey(phProvider[0], &phKey, (LPCWSTR)this, 0, 32 * v8);
  v7 = v14;
  if ( v14 >= 0 )
  {
    *(_QWORD *)a2 = phKey;
    phKey = 0;
    wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&phKey);
    v7 = 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x46,
      (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\lib\\cryptutils.cpp",
      (const char *)(unsigned int)v14,
      dwFlagsa);
    wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&phKey);
  }
LABEL_14:
  wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(phProvider);
  return v7;
}

```

## disassembly

```asm
0x180014588  mov     [rsp-18h+arg_0], rbx
0x18001458d  push    rbp
0x18001458e  push    rsi
0x18001458f  push    rdi
0x180014590  mov     rbp, rsp
0x180014593  sub     rsp, 40h
0x180014597  mov     rsi, rdx
0x18001459a  mov     [rbp+phProvider], 0
0x1800145a2  mov     rdi, rcx
0x1800145a5  lea     rdx, pszProviderName; "Microsoft Platform Crypto Provider"
0x1800145ac  lea     rcx, [rbp+phProvider]; phProvider
0x1800145b0  xor     r8d, r8d; dwFlags
0x1800145b3  call    cs:__imp_NCryptOpenStorageProvider
0x1800145b9  mov     ebx, eax
0x1800145bb  test    eax, eax
0x1800145bd  jns     short loc_1800145DC
0x1800145bf  mov     rcx, [rbp+18h]; this
0x1800145c3  lea     r8, aOnecoreDsSecur_12; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x1800145ca  mov     r9d, eax; char *
0x1800145cd  mov     edx, 2Fh ; '/'; void *
0x1800145d2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800145d7  jmp     loc_1800146DD
0x1800145dc  xor     ebx, ebx
0x1800145de  mov     rcx, rdi; this
0x1800145e1  lea     edx, [rbx+0Ch]; unsigned __int16 *
0x1800145e4  call    ?IsStringNullTerminated@NgcUtils@@YA_NPEBG_K@Z; NgcUtils::IsStringNullTerminated(ushort const *,unsigned __int64)
0x1800145e9  test    al, al
0x1800145eb  jz      loc_180014677
0x1800145f1  lea     rdx, aWindowsAik; "Windows AIK"
0x1800145f8  mov     rcx, rdi; this
0x1800145fb  call    ?AreStringsEqual@NgcUtils@@YA_NPEBG0@Z; NgcUtils::AreStringsEqual(ushort const *,ushort const *)
0x180014600  test    al, al
0x180014602  jz      short loc_180014677
0x180014604  xor     edx, edx
0x180014606  mov     [rbp+arg_10], rbx
0x18001460a  lea     rcx, [rbp+arg_10]
0x18001460e  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180014613  lea     rcx, [rbp+arg_10]; this
0x180014617  call    ?GetWindowsAikAlternateLocation@NgcUtils@@YAJPEAPEAG@Z; NgcUtils::GetWindowsAikAlternateLocation(ushort * *)
0x18001461c  mov     ebx, eax
0x18001461e  test    eax, eax
0x180014620  jns     short loc_180014648
0x180014622  mov     edx, 38h ; '8'; void *
0x180014627  mov     rcx, [rbp+18h]; this
0x18001462b  lea     r8, aOnecoreDsSecur_12; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x180014632  mov     r9d, eax; char *
0x180014635  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001463a  lea     rcx, [rbp+arg_10]
0x18001463e  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180014643  jmp     loc_1800146DD
0x180014648  mov     r8, [rbp+arg_10]; unsigned __int16 *
0x18001464c  lea     rdx, aPcpAlternateKe; "PCP_ALTERNATE_KEY_STORAGE_LOCATION"
0x180014653  mov     rcx, [rbp+phProvider]; this
0x180014657  call    ?SetNCryptStringProperty@NgcUtils@@YAJ_KPEBG1@Z; NgcUtils::SetNCryptStringProperty(unsigned __int64,ushort const *,ushort const *)
0x18001465c  mov     ebx, eax
0x18001465e  test    eax, eax
0x180014660  jns     short loc_180014669
0x180014662  mov     edx, 3Dh ; '='
0x180014667  jmp     short loc_180014627
0x180014669  lea     rcx, [rbp+arg_10]
0x18001466d  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180014672  mov     ebx, 1
0x180014677  mov     rcx, [rbp+phProvider]; hProvider
0x18001467b  lea     rdx, [rbp+phKey]; phKey
0x18001467f  shl     ebx, 5
0x180014682  xor     r9d, r9d; dwLegacyKeySpec
0x180014685  mov     r8, rdi; pszKeyName
0x180014688  mov     [rsp+40h+dwFlags], ebx; int
0x18001468c  mov     [rbp+phKey], 0
0x180014694  call    cs:__imp_NCryptOpenKey
0x18001469a  mov     ebx, eax
0x18001469c  test    eax, eax
0x18001469e  jns     short loc_1800146C3
0x1800146a0  mov     rcx, [rbp+18h]; this
0x1800146a4  lea     r8, aOnecoreDsSecur_12; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x1800146ab  mov     r9d, eax; char *
0x1800146ae  mov     edx, 46h ; 'F'; void *
0x1800146b3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800146b8  lea     rcx, [rbp+phKey]
0x1800146bc  call    ??1?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(void)
0x1800146c1  jmp     short loc_1800146DD
0x1800146c3  mov     rax, [rbp+phKey]
0x1800146c7  lea     rcx, [rbp+phKey]
0x1800146cb  mov     [rsi], rax
0x1800146ce  mov     [rbp+phKey], 0
0x1800146d6  call    ??1?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(void)
0x1800146db  xor     ebx, ebx
0x1800146dd  lea     rcx, [rbp+phProvider]
0x1800146e1  call    ??1?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(void)
0x1800146e6  mov     eax, ebx
0x1800146e8  mov     rbx, [rsp+40h+arg_0]
0x1800146ed  add     rsp, 40h
0x1800146f1  pop     rdi
0x1800146f2  pop     rsi
0x1800146f3  pop     rbp
0x1800146f4  retn
```
