# NgcUtils::IsInsecureTpm(bool *)

- ea: `0x18001aec0`
- end: `0x18001af8e`
- name: `?IsInsecureTpm@NgcUtils@@YAJPEA_N@Z`
- size: `206`
- prototype: `__int64 __fastcall(NgcUtils *__hidden this, bool *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800213c4`

## callees

- `0x180006538`
- `0x1800167f8`
- `0x18001aec0`

## import_xrefs

- `ncrypt!NCryptFreeObject` at `0x18001af17`
- `ncrypt!NCryptFreeObject` at `0x18001af17`
- `ncrypt!NCryptOpenStorageProvider` at `0x18001aee8`
- `ncrypt!NCryptOpenStorageProvider` at `0x18001aee8`
- `ncrypt!NCryptGetProperty` at `0x18001af5a`
- `ncrypt!NCryptGetProperty` at `0x18001af5a`

## string_xrefs

- `0x18001aefe`: `onecore\ds\security\ngc\utils\common\lib\tpmutils.cpp`

## pseudocode

```c
__int64 __fastcall NgcUtils::IsInsecureTpm(NgcUtils *this, bool *a2)
{
  SECURITY_STATUS Property; // ebx
  __int64 v4; // rdx
  int pcbResult; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  int pbOutput; // [rsp+40h] [rbp+8h] BYREF
  DWORD v9; // [rsp+48h] [rbp+10h] BYREF
  NCRYPT_PROV_HANDLE phProvider; // [rsp+50h] [rbp+18h] BYREF

  *(_BYTE *)this = 0;
  phProvider = 0;
  Property = NCryptOpenStorageProvider(&phProvider, L"Microsoft Platform Crypto Provider", 0);
  if ( Property >= 0 )
  {
    pbOutput = 0;
    v9 = 0;
    Property = NCryptGetProperty(phProvider, L"PCP_TPM_IFX_RSA_KEYGEN_VULNERABILITY", (PBYTE)&pbOutput, 4u, &v9, 0);
    if ( Property >= 0 )
    {
      *(_BYTE *)this = pbOutput != 0;
      wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&phProvider);
      return 0;
    }
    v4 = 77;
  }
  else
  {
    v4 = 66;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v4,
    (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\lib\\tpmutils.cpp",
    (const char *)(unsigned int)Property,
    pcbResult);
  if ( phProvider )
    NCryptFreeObject(phProvider);
  return (unsigned int)Property;
}

```

## disassembly

```asm
0x18001aec0  mov     [rsp+arg_18], rbx
0x18001aec5  push    rdi
0x18001aec6  sub     rsp, 30h
0x18001aeca  mov     rdi, rcx
0x18001aecd  mov     byte ptr [rcx], 0
0x18001aed0  lea     rcx, [rsp+38h+phProvider]; phProvider
0x18001aed5  mov     [rsp+38h+phProvider], 0
0x18001aede  xor     r8d, r8d; dwFlags
0x18001aee1  lea     rdx, aMicrosoftPlatf; "Microsoft Platform Crypto Provider"
0x18001aee8  call    cs:__imp_NCryptOpenStorageProvider
0x18001aeee  mov     ebx, eax
0x18001aef0  test    eax, eax
0x18001aef2  jns     short loc_18001AF21
0x18001aef4  mov     edx, 42h ; 'B'; void *
0x18001aef9  mov     rcx, [rsp+38h]; this
0x18001aefe  lea     r8, aOnecoreDsSecur_1; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x18001af05  mov     r9d, ebx; char *
0x18001af08  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001af0d  mov     rcx, [rsp+38h+phProvider]; hObject
0x18001af12  test    rcx, rcx
0x18001af15  jz      short loc_18001AF1D
0x18001af17  call    cs:__imp_NCryptFreeObject
0x18001af1d  mov     eax, ebx
0x18001af1f  jmp     short loc_18001AF83
0x18001af21  mov     rcx, [rsp+38h+phProvider]; hObject
0x18001af26  lea     rax, [rsp+38h+arg_8]
0x18001af2b  mov     [rsp+38h+dwFlags], 0; dwFlags
0x18001af33  lea     r8, [rsp+38h+pbOutput]; pbOutput
0x18001af38  mov     r9d, 4; cbOutput
0x18001af3e  mov     [rsp+38h+pcbResult], rax; pcbResult
0x18001af43  lea     rdx, aPcpTpmIfxRsaKe_0; "PCP_TPM_IFX_RSA_KEYGEN_VULNERABILITY"
0x18001af4a  mov     [rsp+38h+pbOutput], 0
0x18001af52  mov     [rsp+38h+arg_8], 0
0x18001af5a  call    cs:__imp_NCryptGetProperty
0x18001af60  mov     ebx, eax
0x18001af62  test    eax, eax
0x18001af64  jns     short loc_18001AF6D
0x18001af66  mov     edx, 4Dh ; 'M'
0x18001af6b  jmp     short loc_18001AEF9
0x18001af6d  cmp     [rsp+38h+pbOutput], 0
0x18001af72  lea     rcx, [rsp+38h+phProvider]
0x18001af77  setnz   al
0x18001af7a  mov     [rdi], al
0x18001af7c  call    ??1?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(void)
0x18001af81  xor     eax, eax
0x18001af83  mov     rbx, [rsp+38h+arg_18]
0x18001af88  add     rsp, 30h
0x18001af8c  pop     rdi
0x18001af8d  retn
```
