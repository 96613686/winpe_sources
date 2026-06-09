# CalculateSHA512Hash(uchar *,uint,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x140014900`
- end: `0x140014bdb`
- name: `?CalculateSHA512Hash@@YAJPEAEIAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `731`
- prototype: `__int64 __fastcall(PUCHAR pbInput, ULONG cbInput, __int64)`
- caller_count: `1`
- callee_count: `16`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x140014db4`

## callees

- `0x140002f40`
- `0x140005364`
- `0x1400057cc`
- `0x140006320`
- `0x1400063b0`
- `0x140006484`
- `0x14000a4bc`
- `0x14000df28`
- `0x14000ea40`
- `0x140011a4c`
- `0x140014564`
- `0x140014748`
- `0x140014768`
- `0x140014900`
- `0x14001528c`
- `0x14001a010`

## import_xrefs

- `msvcp_win!?setw@std@@YA?AU?$_Smanip@_J@1@_J@Z` at `0x140014b11`
- `msvcp_win!?setw@std@@YA?AU?$_Smanip@_J@1@_J@Z` at `0x140014b11`
- `msvcp_win!?fill@?$basic_ios@GU?$char_traits@G@std@@@std@@QEAAGG@Z` at `0x140014af0`
- `msvcp_win!?fill@?$basic_ios@GU?$char_traits@G@std@@@std@@QEAAGG@Z` at `0x140014af0`
- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@P6AAEAVios_base@1@AEAV21@@Z@Z` at `0x140014adb`
- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@P6AAEAVios_base@1@AEAV21@@Z@Z` at `0x140014adb`
- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@H@Z` at `0x140014b38`
- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@H@Z` at `0x140014b38`
- `bcrypt!BCryptCreateHash` at `0x140014a3f`
- `bcrypt!BCryptCreateHash` at `0x140014a3f`
- `bcrypt!BCryptHashData` at `0x140014a5e`
- `bcrypt!BCryptHashData` at `0x140014a5e`
- `bcrypt!BCryptDestroyHash` at `0x1400149fb`
- `bcrypt!BCryptDestroyHash` at `0x1400149fb`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x140014974`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x140014974`
- `bcrypt!BCryptFinishHash` at `0x140014a81`
- `bcrypt!BCryptFinishHash` at `0x140014a81`
- `bcrypt!BCryptGetProperty` at `0x1400149ae`
- `bcrypt!BCryptGetProperty` at `0x1400149ae`

## string_xrefs

- `0x140014bab`: `onecore\windows\directx\database\updater\filecompression\filecompression.cpp`

## pseudocode

```c
__int64 __fastcall CalculateSHA512Hash(PUCHAR pbInput, ULONG cbInput, __int64 a3)
{
  NTSTATUS Property; // eax
  unsigned int v7; // r8d
  __int64 v8; // rdx
  unsigned int v9; // ebx
  BCRYPT_HASH_HANDLE v10; // rbx
  NTSTATUS v11; // eax
  unsigned int v12; // r8d
  __int64 v13; // rdx
  __int64 v14; // rax
  PUCHAR v15; // rdi
  PUCHAR v16; // rsi
  unsigned int v17; // ebx
  __int64 v18; // rax
  __int64 v19; // rax
  int pcbResult; // [rsp+20h] [rbp-E0h]
  int pcbResulta; // [rsp+20h] [rbp-E0h]
  UCHAR pbOutput[4]; // [rsp+40h] [rbp-C0h] BYREF
  BCRYPT_HASH_HANDLE hHash; // [rsp+48h] [rbp-B8h] BYREF
  BCRYPT_ALG_HANDLE phAlgorithm; // [rsp+50h] [rbp-B0h] BYREF
  ULONG v26; // [rsp+58h] [rbp-A8h] BYREF
  PUCHAR v27[4]; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v28[16]; // [rsp+80h] [rbp-80h] BYREF
  _QWORD v29[30]; // [rsp+90h] [rbp-70h] BYREF
  _BYTE v30[32]; // [rsp+180h] [rbp+80h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1D8h] [rbp+D8h]

  if ( !pbInput || !cbInput )
  {
    v9 = -2147024809;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2A,
      (unsigned int)"onecore\\windows\\directx\\database\\updater\\filecompression\\filecompression.cpp",
      (const char *)0x80070057LL,
      pcbResult);
    return v9;
  }
  hHash = 0;
  *(_DWORD *)pbOutput = 0;
  v26 = 0;
  phAlgorithm = 0;
  Property = BCryptOpenAlgorithmProvider(&phAlgorithm, L"SHA512", 0, 0);
  if ( Property < 0 )
  {
    v8 = 51;
LABEL_7:
    v9 = wil::details::in1diag3::Return_NtStatus(
           retaddr,
           (void *)v8,
           v7,
           (const char *)(unsigned int)Property,
           pcbResult);
LABEL_17:
    wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&hHash);
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_BCryptCloseAlgorithmProviderNoFlags_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&phAlgorithm);
    return v9;
  }
  Property = BCryptGetProperty(phAlgorithm, L"HashDigestLength", pbOutput, 4u, &v26, 0);
  if ( Property < 0 )
  {
    v8 = 54;
    goto LABEL_7;
  }
  std::vector<unsigned char>::vector<unsigned char>(v27, *(unsigned int *)pbOutput);
  v10 = hHash;
  if ( hHash )
  {
    wil::last_error_context::last_error_context((wil::last_error_context *)v30);
    BCryptDestroyHash(v10);
    wil::last_error_context::~last_error_context((wil::last_error_context *)v30);
  }
  hHash = 0;
  v11 = BCryptCreateHash(phAlgorithm, &hHash, 0, 0, 0, 0, 0);
  if ( v11 < 0 )
  {
    v13 = 57;
LABEL_16:
    v9 = wil::details::in1diag3::Return_NtStatus(retaddr, (void *)v13, v12, (const char *)(unsigned int)v11, pcbResulta);
    std::vector<unsigned char>::_Tidy((__int64)v27);
    goto LABEL_17;
  }
  v11 = BCryptHashData(hHash, pbInput, cbInput, 0);
  if ( v11 < 0 )
  {
    v13 = 59;
    goto LABEL_16;
  }
  v11 = BCryptFinishHash(hHash, v27[0], *(ULONG *)pbOutput, 0);
  if ( v11 < 0 )
  {
    v13 = 61;
    goto LABEL_16;
  }
  std::basic_stringstream<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>::basic_stringstream<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>(v28);
  v14 = std::basic_ostream<unsigned short>::operator<<(v29, std::hex);
  std::basic_ios<unsigned short>::fill(v14 + *(int *)(*(_QWORD *)v14 + 4LL), 48);
  v15 = v27[0];
  v16 = v27[1];
  while ( v15 != v16 )
  {
    v17 = *v15;
    v18 = std::setw(v30, 2);
    (*(void (__fastcall **)(char *, _QWORD))v18)((char *)v29 + *(int *)(v29[0] + 4LL), *(_QWORD *)(v18 + 8));
    std::basic_ostream<unsigned short>::operator<<(v29, v17);
    ++v15;
  }
  v19 = std::basic_stringstream<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>::str(
          v28,
          v30);
  std::wstring::operator=(a3, v19);
  std::wstring::_Tidy_deallocate((__int64)v30);
  std::basic_stringstream<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>::`vbase destructor'(v28);
  std::vector<unsigned char>::_Tidy((__int64)v27);
  wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&hHash);
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_BCryptCloseAlgorithmProviderNoFlags_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&phAlgorithm);
  return 0;
}

```

## disassembly

```asm
0x140014900  push    rbp
0x140014902  push    rbx
0x140014903  push    rsi
0x140014904  push    rdi
0x140014905  push    r14
0x140014907  lea     rbp, [rsp-0B0h]
0x14001490f  sub     rsp, 1B0h
0x140014916  mov     rax, cs:__security_cookie
0x14001491d  xor     rax, rsp
0x140014920  mov     [rbp+0D0h+var_30], rax
0x140014927  mov     r14, r8
0x14001492a  mov     edi, edx
0x14001492c  mov     rsi, rcx
0x14001492f  test    rcx, rcx
0x140014932  jz      loc_140014B9C
0x140014938  test    edx, edx
0x14001493a  jz      loc_140014B9C
0x140014940  mov     [rsp+1D0h+hHash], 0
0x140014949  mov     dword ptr [rsp+1D0h+pbOutput], 0
0x140014951  mov     [rsp+1D0h+var_178], 0
0x140014959  mov     [rsp+1D0h+phAlgorithm], 0
0x140014962  xor     r9d, r9d; dwFlags
0x140014965  xor     r8d, r8d; pszImplementation
0x140014968  lea     rdx, pszAlgId; "SHA512"
0x14001496f  lea     rcx, [rsp+1D0h+phAlgorithm]; phAlgorithm
0x140014974  call    cs:__imp_BCryptOpenAlgorithmProvider
0x14001497a  test    eax, eax
0x14001497c  jns     short loc_140014985
0x14001497e  mov     edx, 33h ; '3'
0x140014983  jmp     short loc_1400149BD
0x140014985  mov     [rsp+1D0h+dwFlags], 0; dwFlags
0x14001498d  lea     rax, [rsp+1D0h+var_178]
0x140014992  mov     [rsp+1D0h+pcbResult], rax; int
0x140014997  mov     r9d, 4; cbOutput
0x14001499d  lea     r8, [rsp+1D0h+pbOutput]; pbOutput
0x1400149a2  lea     rdx, pszProperty; "HashDigestLength"
0x1400149a9  mov     rcx, [rsp+1D0h+phAlgorithm]; hObject
0x1400149ae  call    cs:__imp_BCryptGetProperty
0x1400149b4  test    eax, eax
0x1400149b6  jns     short loc_1400149D3
0x1400149b8  mov     edx, 36h ; '6'; void *
0x1400149bd  mov     r9d, eax; char *
0x1400149c0  mov     rcx, [rbp+0D8h]; this
0x1400149c7  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x1400149cc  mov     ebx, eax
0x1400149ce  jmp     loc_140014AAC
0x1400149d3  mov     edx, dword ptr [rsp+1D0h+pbOutput]
0x1400149d7  lea     rcx, [rsp+1D0h+var_170]
0x1400149dc  call    ??0?$vector@EV?$allocator@E@std@@@std@@QEAA@_KAEBV?$allocator@E@1@@Z; std::vector<uchar>::vector<uchar>(unsigned __int64,std::allocator<uchar> const &)
0x1400149e1  nop
0x1400149e2  mov     rbx, [rsp+1D0h+hHash]
0x1400149e7  test    rbx, rbx
0x1400149ea  jz      short loc_140014A0D
0x1400149ec  lea     rcx, [rbp+0D0h+var_50]; this
0x1400149f3  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x1400149f8  mov     rcx, rbx; hHash
0x1400149fb  call    cs:__imp_BCryptDestroyHash
0x140014a01  lea     rcx, [rbp+0D0h+var_50]; this
0x140014a08  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x140014a0d  mov     [rsp+1D0h+hHash], 0
0x140014a16  mov     [rsp+1D0h+var_1A0], 0; dwFlags
0x140014a1e  mov     [rsp+1D0h+dwFlags], 0; cbSecret
0x140014a26  mov     [rsp+1D0h+pcbResult], 0; int
0x140014a2f  xor     r9d, r9d; cbHashObject
0x140014a32  xor     r8d, r8d; pbHashObject
0x140014a35  lea     rdx, [rsp+1D0h+hHash]; phHash
0x140014a3a  mov     rcx, [rsp+1D0h+phAlgorithm]; hAlgorithm
0x140014a3f  call    cs:__imp_BCryptCreateHash
0x140014a45  test    eax, eax
0x140014a47  jns     short loc_140014A50
0x140014a49  mov     edx, 39h ; '9'
0x140014a4e  jmp     short loc_140014A90
0x140014a50  xor     r9d, r9d; dwFlags
0x140014a53  mov     r8d, edi; cbInput
0x140014a56  mov     rdx, rsi; pbInput
0x140014a59  mov     rcx, [rsp+1D0h+hHash]; hHash
0x140014a5e  call    cs:__imp_BCryptHashData
0x140014a64  test    eax, eax
0x140014a66  jns     short loc_140014A6F
0x140014a68  mov     edx, 3Bh ; ';'
0x140014a6d  jmp     short loc_140014A90
0x140014a6f  xor     r9d, r9d; dwFlags
0x140014a72  mov     r8d, dword ptr [rsp+1D0h+pbOutput]; cbOutput
0x140014a77  mov     rdx, [rsp+1D0h+var_170]; pbOutput
0x140014a7c  mov     rcx, [rsp+1D0h+hHash]; hHash
0x140014a81  call    cs:__imp_BCryptFinishHash
0x140014a87  test    eax, eax
0x140014a89  jns     short loc_140014AC6
0x140014a8b  mov     edx, 3Dh ; '='; void *
0x140014a90  mov     r9d, eax; char *
0x140014a93  mov     rcx, [rbp+0D8h]; this
0x140014a9a  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x140014a9f  mov     ebx, eax
0x140014aa1  lea     rcx, [rsp+1D0h+var_170]
0x140014aa6  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x140014aab  nop
0x140014aac  lea     rcx, [rsp+1D0h+hHash]
0x140014ab1  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?BCryptDestroyHash@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x140014ab6  nop
0x140014ab7  lea     rcx, [rsp+1D0h+phAlgorithm]
0x140014abc  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?BCryptCloseAlgorithmProviderNoFlags@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x140014ac1  jmp     loc_140014BBC
0x140014ac6  lea     rcx, [rbp+0D0h+var_150]
0x140014aca  call    ??0?$basic_stringstream@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::basic_stringstream<ushort,std::char_traits<ushort>,std::allocator<ushort>>::basic_stringstream<ushort,std::char_traits<ushort>,std::allocator<ushort>>(void)
0x140014acf  nop
0x140014ad0  lea     rdx, ?hex@std@@YAAEAVios_base@1@AEAV21@@Z; std::hex(std::ios_base &)
0x140014ad7  lea     rcx, [rbp+0D0h+var_140]
0x140014adb  call    cs:__imp_??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@P6AAEAVios_base@1@AEAV21@@Z@Z; std::basic_ostream<ushort>::operator<<(std::ios_base & (*)(std::ios_base &))
0x140014ae1  mov     edx, 30h ; '0'
0x140014ae6  mov     rcx, [rax]
0x140014ae9  movsxd  rcx, dword ptr [rcx+4]
0x140014aed  add     rcx, rax
0x140014af0  call    cs:__imp_?fill@?$basic_ios@GU?$char_traits@G@std@@@std@@QEAAGG@Z; std::basic_ios<ushort>::fill(ushort)
0x140014af6  mov     rdi, [rsp+1D0h+var_170]
0x140014afb  mov     rsi, [rsp+1D0h+var_168]
0x140014b00  jmp     short loc_140014B41
0x140014b02  movzx   ebx, byte ptr [rdi]
0x140014b05  mov     edx, 2
0x140014b0a  lea     rcx, [rbp+0D0h+var_50]
0x140014b11  call    cs:__imp_?setw@std@@YA?AU?$_Smanip@_J@1@_J@Z; std::setw(__int64)
0x140014b17  mov     rcx, [rbp+0D0h+var_140]
0x140014b1b  movsxd  rdx, dword ptr [rcx+4]
0x140014b1f  lea     rcx, [rbp+0D0h+var_140]
0x140014b23  add     rcx, rdx
0x140014b26  mov     rdx, [rax+8]
0x140014b2a  mov     rax, [rax]
0x140014b2d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140014b32  mov     edx, ebx
0x140014b34  lea     rcx, [rbp+0D0h+var_140]
0x140014b38  call    cs:__imp_??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@H@Z; std::basic_ostream<ushort>::operator<<(int)
0x140014b3e  inc     rdi
0x140014b41  cmp     rdi, rsi
0x140014b44  jnz     short loc_140014B02
0x140014b46  lea     rdx, [rbp+0D0h+var_50]
0x140014b4d  lea     rcx, [rbp+0D0h+var_150]
0x140014b51  call    ?str@?$basic_stringstream@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@XZ; std::basic_stringstream<ushort,std::char_traits<ushort>,std::allocator<ushort>>::str(void)
0x140014b56  mov     rdx, rax
0x140014b59  mov     rcx, r14
0x140014b5c  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x140014b61  lea     rcx, [rbp+0D0h+var_50]
0x140014b68  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x140014b6d  nop
0x140014b6e  lea     rcx, [rbp+0D0h+var_150]
0x140014b72  call    ??_D?$basic_stringstream@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAXXZ; std::basic_stringstream<ushort,std::char_traits<ushort>,std::allocator<ushort>>::`vbase destructor'(void)
0x140014b77  nop
0x140014b78  lea     rcx, [rsp+1D0h+var_170]
0x140014b7d  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x140014b82  nop
0x140014b83  lea     rcx, [rsp+1D0h+hHash]
0x140014b88  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?BCryptDestroyHash@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x140014b8d  nop
0x140014b8e  lea     rcx, [rsp+1D0h+phAlgorithm]
0x140014b93  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?BCryptCloseAlgorithmProviderNoFlags@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x140014b98  xor     eax, eax
0x140014b9a  jmp     short loc_140014BBE
0x140014b9c  mov     rcx, [rbp+0D8h]; this
0x140014ba3  mov     ebx, 80070057h
0x140014ba8  mov     r9d, ebx; char *
0x140014bab  lea     r8, aOnecoreWindows_1; "onecore\\windows\\directx\\database\\up"...
0x140014bb2  mov     edx, 2Ah ; '*'; void *
0x140014bb7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140014bbc  mov     eax, ebx
0x140014bbe  mov     rcx, [rbp+0D0h+var_30]
0x140014bc5  xor     rcx, rsp; StackCookie
0x140014bc8  call    __security_check_cookie
0x140014bcd  add     rsp, 1B0h
0x140014bd4  pop     r14
0x140014bd6  pop     rdi
0x140014bd7  pop     rsi
0x140014bd8  pop     rbx
0x140014bd9  pop     rbp
0x140014bda  retn
```
