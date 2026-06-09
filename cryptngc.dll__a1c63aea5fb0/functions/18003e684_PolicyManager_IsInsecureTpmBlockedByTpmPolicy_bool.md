# PolicyManager::IsInsecureTpmBlockedByTpmPolicy(bool *)

- ea: `0x18003e684`
- end: `0x18003e75d`
- name: `?IsInsecureTpmBlockedByTpmPolicy@PolicyManager@@YAJPEA_N@Z`
- size: `217`
- prototype: `__int64 __fastcall(PolicyManager *__hidden this, bool *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800213c4`

## callees

- `0x1800158e0`
- `0x1800167f8`
- `0x18003e684`

## import_xrefs

- `ncrypt!NCryptOpenStorageProvider` at `0x18003e6ab`
- `ncrypt!NCryptOpenStorageProvider` at `0x18003e6ab`
- `ncrypt!NCryptGetProperty` at `0x18003e721`
- `ncrypt!NCryptGetProperty` at `0x18003e721`

## pseudocode

```c
__int64 __fastcall PolicyManager::IsInsecureTpmBlockedByTpmPolicy(PolicyManager *this, bool *a2)
{
  SECURITY_STATUS Property; // ebx
  unsigned __int8 *v4; // rdx
  int pbOutput; // [rsp+50h] [rbp+20h] BYREF
  SECURITY_STATUS v7; // [rsp+58h] [rbp+28h] BYREF
  DWORD pcbResult; // [rsp+60h] [rbp+30h] BYREF
  NCRYPT_PROV_HANDLE phProvider; // [rsp+68h] [rbp+38h] BYREF

  *(_BYTE *)this = 0;
  phProvider = 0;
  Property = NCryptOpenStorageProvider(&phProvider, L"Microsoft Platform Crypto Provider", 0);
  if ( Property >= 0 )
  {
    pbOutput = 0;
    pcbResult = 0;
    Property = NCryptGetProperty(phProvider, L"PCP_TPM_IFX_RSA_KEYGEN_PROHIBITED", (PBYTE)&pbOutput, 4u, &pcbResult, 0);
    if ( Property >= 0 )
    {
      *(_BYTE *)this = pbOutput != 0;
      goto LABEL_9;
    }
    if ( (unsigned int)dword_18006E000 > 2 )
    {
      v4 = (unsigned __int8 *)&dword_180062794;
      goto LABEL_4;
    }
  }
  else if ( (unsigned int)dword_18006E000 > 2 )
  {
    v4 = (unsigned __int8 *)&word_1800627D6;
LABEL_4:
    v7 = Property;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
      (__int64)&dword_18006E000,
      v4,
      0,
      0,
      (__int64)&v7);
  }
LABEL_9:
  wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&phProvider);
  return (unsigned int)Property;
}

```

## disassembly

```asm
0x18003e684  push    rbp
0x18003e686  push    rbx
0x18003e687  push    rdi
0x18003e688  mov     rbp, rsp
0x18003e68b  sub     rsp, 30h
0x18003e68f  mov     rdi, rcx
0x18003e692  mov     byte ptr [rcx], 0
0x18003e695  lea     rcx, [rbp+phProvider]; phProvider
0x18003e699  mov     [rbp+phProvider], 0
0x18003e6a1  xor     r8d, r8d; dwFlags
0x18003e6a4  lea     rdx, aMicrosoftPlatf; "Microsoft Platform Crypto Provider"
0x18003e6ab  call    cs:__imp_NCryptOpenStorageProvider
0x18003e6b1  mov     ebx, eax
0x18003e6b3  test    eax, eax
0x18003e6b5  jns     short loc_18003E6ED
0x18003e6b7  mov     ecx, cs:dword_18006E000
0x18003e6bd  cmp     ecx, 2
0x18003e6c0  jbe     loc_18003E74A
0x18003e6c6  lea     rdx, word_1800627D6
0x18003e6cd  xor     r9d, r9d
0x18003e6d0  lea     rax, [rbp+arg_8]
0x18003e6d4  xor     r8d, r8d
0x18003e6d7  mov     [rsp+30h+pcbResult], rax
0x18003e6dc  lea     rcx, dword_18006E000
0x18003e6e3  mov     [rbp+arg_8], ebx
0x18003e6e6  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x18003e6eb  jmp     short loc_18003E74A
0x18003e6ed  mov     rcx, [rbp+phProvider]; hObject
0x18003e6f1  lea     rax, [rbp+arg_10]
0x18003e6f5  mov     [rsp+30h+dwFlags], 0; dwFlags
0x18003e6fd  lea     r8, [rbp+pbOutput]; pbOutput
0x18003e701  mov     r9d, 4; cbOutput
0x18003e707  mov     [rsp+30h+pcbResult], rax; pcbResult
0x18003e70c  lea     rdx, aPcpTpmIfxRsaKe; "PCP_TPM_IFX_RSA_KEYGEN_PROHIBITED"
0x18003e713  mov     [rbp+pbOutput], 0
0x18003e71a  mov     [rbp+arg_10], 0
0x18003e721  call    cs:__imp_NCryptGetProperty
0x18003e727  mov     ebx, eax
0x18003e729  test    eax, eax
0x18003e72b  jns     short loc_18003E741
0x18003e72d  mov     ecx, cs:dword_18006E000
0x18003e733  cmp     ecx, 2
0x18003e736  jbe     short loc_18003E74A
0x18003e738  lea     rdx, dword_180062794
0x18003e73f  jmp     short loc_18003E6CD
0x18003e741  cmp     [rbp+pbOutput], 0
0x18003e745  setnz   al
0x18003e748  mov     [rdi], al
0x18003e74a  lea     rcx, [rbp+phProvider]
0x18003e74e  call    ??1?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(void)
0x18003e753  mov     eax, ebx
0x18003e755  add     rsp, 30h
0x18003e759  pop     rdi
0x18003e75a  pop     rbx
0x18003e75b  pop     rbp
0x18003e75c  retn
```
