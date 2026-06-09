# NgcUtils::GetTpm20FirmwareInformation(ushort * const,__NCRYPT_PCP_TPM_FW_VERSION_INFO *)

- ea: `0x1800133cc`
- end: `0x1800134ef`
- name: `?GetTpm20FirmwareInformation@NgcUtils@@YAJQEAGPEAU__NCRYPT_PCP_TPM_FW_VERSION_INFO@@@Z`
- size: `291`
- prototype: `__int64 __fastcall(NgcUtils *__hidden this, unsigned __int16 *const, struct __NCRYPT_PCP_TPM_FW_VERSION_INFO *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800135bc`

## callees

- `0x180004de0`
- `0x18000b0fc`
- `0x180011e48`
- `0x1800133cc`

## import_xrefs

- `ncrypt!NCryptGetProperty` at `0x180013447`
- `ncrypt!NCryptGetProperty` at `0x18001349b`
- `ncrypt!NCryptGetProperty` at `0x180013447`
- `ncrypt!NCryptGetProperty` at `0x18001349b`
- `ncrypt!NCryptOpenStorageProvider` at `0x180013405`
- `ncrypt!NCryptOpenStorageProvider` at `0x180013405`

## string_xrefs

- `0x18001345c`: `onecore\ds\security\ngc\utils\common\lib\tpmutils.cpp`

## pseudocode

```c
__int64 __fastcall NgcUtils::GetTpm20FirmwareInformation(
        NgcUtils *this,
        unsigned __int16 *const a2,
        struct __NCRYPT_PCP_TPM_FW_VERSION_INFO *a3)
{
  SECURITY_STATUS Property; // eax
  unsigned int v6; // ebx
  __int64 v7; // rdx
  __int16 v8; // ax
  int pcbResult; // [rsp+20h] [rbp-40h]
  DWORD v11; // [rsp+30h] [rbp-30h] BYREF
  NCRYPT_PROV_HANDLE phProvider; // [rsp+38h] [rbp-28h] BYREF
  BYTE v13[8]; // [rsp+40h] [rbp-20h] BYREF
  BYTE pbOutput[8]; // [rsp+48h] [rbp-18h] BYREF
  __int16 v15; // [rsp+50h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+18h]

  phProvider = 0;
  Property = NCryptOpenStorageProvider(&phProvider, L"Microsoft Platform Crypto Provider", 0);
  v6 = Property;
  if ( Property >= 0 )
  {
    *(_QWORD *)pbOutput = 0;
    v15 = 0;
    v11 = 0;
    Property = NCryptGetProperty(phProvider, L"PCP_TPM_MANUFACTURER_ID", pbOutput, 0xAu, &v11, 0);
    v6 = Property;
    if ( Property >= 0 )
    {
      *(_QWORD *)v13 = 0;
      Property = NCryptGetProperty(phProvider, L"PCP_TPM_FW_VERSION", v13, 8u, &v11, 0);
      v6 = Property;
      if ( Property >= 0 )
      {
        v8 = v15;
        v6 = 0;
        *(_QWORD *)this = *(_QWORD *)pbOutput;
        *((_WORD *)this + 4) = v8;
        *(_QWORD *)a2 = *(_QWORD *)v13;
        goto LABEL_9;
      }
      v7 = 40;
    }
    else
    {
      v7 = 31;
    }
  }
  else
  {
    v7 = 21;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v7,
    (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\lib\\tpmutils.cpp",
    (const char *)(unsigned int)Property,
    pcbResult);
LABEL_9:
  wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&phProvider);
  return v6;
}

```

## disassembly

```asm
0x1800133cc  mov     [rsp-18h+arg_10], rbx
0x1800133d1  push    rbp
0x1800133d2  push    rsi
0x1800133d3  push    rdi
0x1800133d4  mov     rbp, rsp
0x1800133d7  sub     rsp, 60h
0x1800133db  mov     rax, cs:__security_cookie
0x1800133e2  xor     rax, rsp
0x1800133e5  mov     [rbp+var_8], rax
0x1800133e9  mov     rsi, rdx
0x1800133ec  mov     [rbp+phProvider], 0
0x1800133f4  mov     rdi, rcx
0x1800133f7  lea     rdx, pszProviderName; "Microsoft Platform Crypto Provider"
0x1800133fe  lea     rcx, [rbp+phProvider]; phProvider
0x180013402  xor     r8d, r8d; dwFlags
0x180013405  call    cs:__imp_NCryptOpenStorageProvider
0x18001340b  mov     ebx, eax
0x18001340d  test    eax, eax
0x18001340f  jns     short loc_180013418
0x180013411  mov     edx, 15h
0x180013416  jmp     short loc_180013458
0x180013418  mov     rcx, [rbp+phProvider]; hObject
0x18001341c  lea     r8, [rbp+pbOutput]; pbOutput
0x180013420  xor     eax, eax
0x180013422  lea     rdx, pszProperty; "PCP_TPM_MANUFACTURER_ID"
0x180013429  mov     [rsp+60h+dwFlags], eax; dwFlags
0x18001342d  mov     r9d, 0Ah; cbOutput
0x180013433  mov     qword ptr [rbp+pbOutput], rax
0x180013437  mov     [rbp+var_10], ax
0x18001343b  mov     [rbp+var_30], eax
0x18001343e  lea     rax, [rbp+var_30]
0x180013442  mov     [rsp+60h+pcbResult], rax; int
0x180013447  call    cs:__imp_NCryptGetProperty
0x18001344d  mov     ebx, eax
0x18001344f  test    eax, eax
0x180013451  jns     short loc_18001346D
0x180013453  mov     edx, 1Fh; void *
0x180013458  mov     rcx, [rbp+18h]; this
0x18001345c  lea     r8, aOnecoreDsSecur_1; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x180013463  mov     r9d, eax; char *
0x180013466  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001346b  jmp     short loc_1800134C8
0x18001346d  mov     rcx, [rbp+phProvider]; hObject
0x180013471  lea     rax, [rbp+var_30]
0x180013475  mov     [rsp+60h+dwFlags], 0; dwFlags
0x18001347d  lea     r8, [rbp+var_20]; pbOutput
0x180013481  mov     r9d, 8; cbOutput
0x180013487  mov     [rsp+60h+pcbResult], rax; pcbResult
0x18001348c  lea     rdx, aPcpTpmFwVersio; "PCP_TPM_FW_VERSION"
0x180013493  mov     qword ptr [rbp+var_20], 0
0x18001349b  call    cs:__imp_NCryptGetProperty
0x1800134a1  mov     ebx, eax
0x1800134a3  test    eax, eax
0x1800134a5  jns     short loc_1800134AE
0x1800134a7  mov     edx, 28h ; '('
0x1800134ac  jmp     short loc_180013458
0x1800134ae  movzx   eax, [rbp+var_10]
0x1800134b2  xor     ebx, ebx
0x1800134b4  movsd   xmm0, qword ptr [rbp+pbOutput]
0x1800134b9  movsd   qword ptr [rdi], xmm0
0x1800134bd  mov     [rdi+8], ax
0x1800134c1  mov     rax, qword ptr [rbp+var_20]
0x1800134c5  mov     [rsi], rax
0x1800134c8  lea     rcx, [rbp+phProvider]
0x1800134cc  call    ??1?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(void)
0x1800134d1  mov     eax, ebx
0x1800134d3  mov     rcx, [rbp+var_8]
0x1800134d7  xor     rcx, rsp; StackCookie
0x1800134da  call    __security_check_cookie
0x1800134df  mov     rbx, [rsp+60h+arg_10]
0x1800134e7  add     rsp, 60h
0x1800134eb  pop     rdi
0x1800134ec  pop     rsi
0x1800134ed  pop     rbp
0x1800134ee  retn
```
