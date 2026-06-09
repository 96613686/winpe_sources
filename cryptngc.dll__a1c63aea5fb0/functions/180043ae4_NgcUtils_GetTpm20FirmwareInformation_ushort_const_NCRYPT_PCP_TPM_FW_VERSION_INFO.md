# NgcUtils::GetTpm20FirmwareInformation(ushort * const,__NCRYPT_PCP_TPM_FW_VERSION_INFO *)

- ea: `0x180043ae4`
- end: `0x180043c07`
- name: `?GetTpm20FirmwareInformation@NgcUtils@@YAJQEAGPEAU__NCRYPT_PCP_TPM_FW_VERSION_INFO@@@Z`
- size: `291`
- prototype: `__int64 __fastcall(NgcUtils *__hidden this, unsigned __int16 *const, struct __NCRYPT_PCP_TPM_FW_VERSION_INFO *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18003e8dc`

## callees

- `0x180006538`
- `0x1800167f8`
- `0x180043ae4`
- `0x180046ce0`

## import_xrefs

- `ncrypt!NCryptOpenStorageProvider` at `0x180043b1d`
- `ncrypt!NCryptOpenStorageProvider` at `0x180043b1d`
- `ncrypt!NCryptGetProperty` at `0x180043b5f`
- `ncrypt!NCryptGetProperty` at `0x180043bb3`
- `ncrypt!NCryptGetProperty` at `0x180043b5f`
- `ncrypt!NCryptGetProperty` at `0x180043bb3`

## string_xrefs

- `0x180043b74`: `onecore\ds\security\ngc\utils\common\lib\tpmutils.cpp`

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
0x180043ae4  mov     [rsp-18h+arg_10], rbx
0x180043ae9  push    rbp
0x180043aea  push    rsi
0x180043aeb  push    rdi
0x180043aec  mov     rbp, rsp
0x180043aef  sub     rsp, 60h
0x180043af3  mov     rax, cs:__security_cookie
0x180043afa  xor     rax, rsp
0x180043afd  mov     [rbp+var_8], rax
0x180043b01  mov     rsi, rdx
0x180043b04  mov     [rbp+phProvider], 0
0x180043b0c  mov     rdi, rcx
0x180043b0f  lea     rdx, aMicrosoftPlatf; "Microsoft Platform Crypto Provider"
0x180043b16  lea     rcx, [rbp+phProvider]; phProvider
0x180043b1a  xor     r8d, r8d; dwFlags
0x180043b1d  call    cs:__imp_NCryptOpenStorageProvider
0x180043b23  mov     ebx, eax
0x180043b25  test    eax, eax
0x180043b27  jns     short loc_180043B30
0x180043b29  mov     edx, 15h
0x180043b2e  jmp     short loc_180043B70
0x180043b30  mov     rcx, [rbp+phProvider]; hObject
0x180043b34  lea     r8, [rbp+pbOutput]; pbOutput
0x180043b38  xor     eax, eax
0x180043b3a  lea     rdx, aPcpTpmManufact; "PCP_TPM_MANUFACTURER_ID"
0x180043b41  mov     [rsp+60h+dwFlags], eax; dwFlags
0x180043b45  mov     r9d, 0Ah; cbOutput
0x180043b4b  mov     qword ptr [rbp+pbOutput], rax
0x180043b4f  mov     [rbp+var_10], ax
0x180043b53  mov     [rbp+var_30], eax
0x180043b56  lea     rax, [rbp+var_30]
0x180043b5a  mov     [rsp+60h+pcbResult], rax; int
0x180043b5f  call    cs:__imp_NCryptGetProperty
0x180043b65  mov     ebx, eax
0x180043b67  test    eax, eax
0x180043b69  jns     short loc_180043B85
0x180043b6b  mov     edx, 1Fh; void *
0x180043b70  mov     rcx, [rbp+18h]; this
0x180043b74  lea     r8, aOnecoreDsSecur_1; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x180043b7b  mov     r9d, eax; char *
0x180043b7e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180043b83  jmp     short loc_180043BE0
0x180043b85  mov     rcx, [rbp+phProvider]; hObject
0x180043b89  lea     rax, [rbp+var_30]
0x180043b8d  mov     [rsp+60h+dwFlags], 0; dwFlags
0x180043b95  lea     r8, [rbp+var_20]; pbOutput
0x180043b99  mov     r9d, 8; cbOutput
0x180043b9f  mov     [rsp+60h+pcbResult], rax; pcbResult
0x180043ba4  lea     rdx, aPcpTpmFwVersio; "PCP_TPM_FW_VERSION"
0x180043bab  mov     qword ptr [rbp+var_20], 0
0x180043bb3  call    cs:__imp_NCryptGetProperty
0x180043bb9  mov     ebx, eax
0x180043bbb  test    eax, eax
0x180043bbd  jns     short loc_180043BC6
0x180043bbf  mov     edx, 28h ; '('
0x180043bc4  jmp     short loc_180043B70
0x180043bc6  movzx   eax, [rbp+var_10]
0x180043bca  xor     ebx, ebx
0x180043bcc  movsd   xmm0, qword ptr [rbp+pbOutput]
0x180043bd1  movsd   qword ptr [rdi], xmm0
0x180043bd5  mov     [rdi+8], ax
0x180043bd9  mov     rax, qword ptr [rbp+var_20]
0x180043bdd  mov     [rsi], rax
0x180043be0  lea     rcx, [rbp+phProvider]
0x180043be4  call    ??1?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(void)
0x180043be9  mov     eax, ebx
0x180043beb  mov     rcx, [rbp+var_8]
0x180043bef  xor     rcx, rsp; StackCookie
0x180043bf2  call    __security_check_cookie
0x180043bf7  mov     rbx, [rsp+60h+arg_10]
0x180043bff  add     rsp, 60h
0x180043c03  pop     rdi
0x180043c04  pop     rsi
0x180043c05  pop     rbp
0x180043c06  retn
```
