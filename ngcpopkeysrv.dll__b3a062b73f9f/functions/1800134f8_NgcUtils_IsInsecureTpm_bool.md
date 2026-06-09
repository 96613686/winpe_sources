# NgcUtils::IsInsecureTpm(bool *)

- ea: `0x1800134f8`
- end: `0x1800135b6`
- name: `?IsInsecureTpm@NgcUtils@@YAJPEA_N@Z`
- size: `190`
- prototype: `__int64 __fastcall(NgcUtils *__hidden this, bool *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800135bc`

## callees

- `0x18000b0fc`
- `0x180011e48`
- `0x1800134f8`

## import_xrefs

- `ncrypt!NCryptGetProperty` at `0x18001356c`
- `ncrypt!NCryptGetProperty` at `0x18001356c`
- `ncrypt!NCryptOpenStorageProvider` at `0x180013520`
- `ncrypt!NCryptOpenStorageProvider` at `0x180013520`

## string_xrefs

- `0x180013582`: `onecore\ds\security\ngc\utils\common\lib\tpmutils.cpp`

## pseudocode

```c
__int64 __fastcall NgcUtils::IsInsecureTpm(NgcUtils *this, bool *a2)
{
  SECURITY_STATUS Property; // eax
  unsigned int v4; // ebx
  __int64 v5; // rdx
  int pcbResult; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  int pbOutput; // [rsp+40h] [rbp+8h] BYREF
  DWORD v10; // [rsp+48h] [rbp+10h] BYREF
  NCRYPT_PROV_HANDLE phProvider; // [rsp+50h] [rbp+18h] BYREF

  *(_BYTE *)this = 0;
  phProvider = 0;
  Property = NCryptOpenStorageProvider(&phProvider, L"Microsoft Platform Crypto Provider", 0);
  v4 = Property;
  if ( Property >= 0 )
  {
    pbOutput = 0;
    v10 = 0;
    Property = NCryptGetProperty(phProvider, L"PCP_TPM_IFX_RSA_KEYGEN_VULNERABILITY", (PBYTE)&pbOutput, 4u, &v10, 0);
    v4 = Property;
    if ( Property >= 0 )
    {
      v4 = 0;
      *(_BYTE *)this = pbOutput != 0;
      goto LABEL_7;
    }
    v5 = 77;
  }
  else
  {
    v5 = 66;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v5,
    (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\lib\\tpmutils.cpp",
    (const char *)(unsigned int)Property,
    pcbResult);
LABEL_7:
  wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&phProvider);
  return v4;
}

```

## disassembly

```asm
0x1800134f8  mov     [rsp+arg_18], rbx
0x1800134fd  push    rdi
0x1800134fe  sub     rsp, 30h
0x180013502  mov     rdi, rcx
0x180013505  mov     byte ptr [rcx], 0
0x180013508  lea     rcx, [rsp+38h+phProvider]; phProvider
0x18001350d  mov     [rsp+38h+phProvider], 0
0x180013516  xor     r8d, r8d; dwFlags
0x180013519  lea     rdx, pszProviderName; "Microsoft Platform Crypto Provider"
0x180013520  call    cs:__imp_NCryptOpenStorageProvider
0x180013526  mov     ebx, eax
0x180013528  test    eax, eax
0x18001352a  jns     short loc_180013533
0x18001352c  mov     edx, 42h ; 'B'
0x180013531  jmp     short loc_18001357D
0x180013533  mov     rcx, [rsp+38h+phProvider]; hObject
0x180013538  lea     rax, [rsp+38h+arg_8]
0x18001353d  mov     [rsp+38h+dwFlags], 0; dwFlags
0x180013545  lea     r8, [rsp+38h+pbOutput]; pbOutput
0x18001354a  mov     r9d, 4; cbOutput
0x180013550  mov     [rsp+38h+pcbResult], rax; int
0x180013555  lea     rdx, aPcpTpmIfxRsaKe; "PCP_TPM_IFX_RSA_KEYGEN_VULNERABILITY"
0x18001355c  mov     [rsp+38h+pbOutput], 0
0x180013564  mov     [rsp+38h+arg_8], 0
0x18001356c  call    cs:__imp_NCryptGetProperty
0x180013572  mov     ebx, eax
0x180013574  test    eax, eax
0x180013576  jns     short loc_180013593
0x180013578  mov     edx, 4Dh ; 'M'; void *
0x18001357d  mov     rcx, [rsp+38h]; this
0x180013582  lea     r8, aOnecoreDsSecur_1; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x180013589  mov     r9d, eax; char *
0x18001358c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180013591  jmp     short loc_18001359F
0x180013593  cmp     [rsp+38h+pbOutput], 0
0x180013598  setnz   al
0x18001359b  xor     ebx, ebx
0x18001359d  mov     [rdi], al
0x18001359f  lea     rcx, [rsp+38h+phProvider]
0x1800135a4  call    ??1?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(void)
0x1800135a9  mov     eax, ebx
0x1800135ab  mov     rbx, [rsp+38h+arg_18]
0x1800135b0  add     rsp, 30h
0x1800135b4  pop     rdi
0x1800135b5  retn
```
