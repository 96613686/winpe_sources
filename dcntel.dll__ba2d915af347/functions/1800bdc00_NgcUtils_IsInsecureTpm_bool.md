# NgcUtils::IsInsecureTpm(bool *)

- ea: `0x1800bdc00`
- end: `0x1800bdce9`
- name: `?IsInsecureTpm@NgcUtils@@YAJPEA_N@Z`
- size: `233`
- prototype: `__int64 __fastcall(NgcUtils *__hidden this, bool *)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800bbdd0`

## callees

- `0x180011ce4`
- `0x1800bdc00`

## import_xrefs

- `ncrypt!NCryptOpenStorageProvider` at `0x1800bdc27`
- `ncrypt!NCryptOpenStorageProvider` at `0x1800bdc27`
- `ncrypt!NCryptGetProperty` at `0x1800bdc95`
- `ncrypt!NCryptGetProperty` at `0x1800bdc95`
- `ncrypt!NCryptFreeObject` at `0x1800bdc54`
- `ncrypt!NCryptFreeObject` at `0x1800bdcb3`
- `ncrypt!NCryptFreeObject` at `0x1800bdcd9`
- `ncrypt!NCryptFreeObject` at `0x1800bdc54`
- `ncrypt!NCryptFreeObject` at `0x1800bdcb3`
- `ncrypt!NCryptFreeObject` at `0x1800bdcd9`

## string_xrefs

- `0x1800bdc3c`: `onecore\base\appcompat\programs\devicecensus\dlls\ngchelper.cpp`

## pseudocode

```c
__int64 __fastcall NgcUtils::IsInsecureTpm(NgcUtils *this, bool *a2)
{
  SECURITY_STATUS v3; // ebx
  __int64 v4; // rdx
  SECURITY_STATUS Property; // eax
  NCRYPT_PROV_HANDLE v7; // rcx
  int pcbResult; // [rsp+20h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+18h]
  int pbOutput; // [rsp+50h] [rbp+20h] BYREF
  DWORD v11; // [rsp+58h] [rbp+28h] BYREF
  NCRYPT_PROV_HANDLE phProvider; // [rsp+60h] [rbp+30h] BYREF

  *(_BYTE *)this = 0;
  phProvider = 0;
  v3 = NCryptOpenStorageProvider(&phProvider, L"Microsoft Platform Crypto Provider", 0);
  if ( v3 < 0 )
  {
    v4 = 99;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v4,
      (unsigned int)"onecore\\base\\appcompat\\programs\\devicecensus\\dlls\\ngchelper.cpp",
      (const char *)(unsigned int)v3,
      pcbResult);
    if ( phProvider )
      NCryptFreeObject(phProvider);
    return (unsigned int)v3;
  }
  pbOutput = 0;
  v11 = 0;
  Property = NCryptGetProperty(phProvider, L"PCP_TPM_IFX_RSA_KEYGEN_VULNERABILITY", (PBYTE)&pbOutput, 4u, &v11, 0);
  v3 = Property;
  if ( Property >= 0 )
  {
    v7 = phProvider;
    *(_BYTE *)this = pbOutput != 0;
    if ( v7 )
      NCryptFreeObject(v7);
    return 0;
  }
  else
  {
    if ( Property != -2144845823 )
    {
      v4 = 110;
      goto LABEL_3;
    }
    if ( phProvider )
      NCryptFreeObject(phProvider);
    return 2150121473LL;
  }
}

```

## disassembly

```asm
0x1800bdc00  push    rbp
0x1800bdc02  push    rbx
0x1800bdc03  push    rdi
0x1800bdc04  mov     rbp, rsp
0x1800bdc07  sub     rsp, 30h
0x1800bdc0b  mov     rdi, rcx
0x1800bdc0e  mov     byte ptr [rcx], 0
0x1800bdc11  lea     rcx, [rbp+phProvider]; phProvider
0x1800bdc15  mov     [rbp+phProvider], 0
0x1800bdc1d  xor     r8d, r8d; dwFlags
0x1800bdc20  lea     rdx, pszProviderName; "Microsoft Platform Crypto Provider"
0x1800bdc27  call    cs:__imp_NCryptOpenStorageProvider
0x1800bdc2d  mov     ebx, eax
0x1800bdc2f  test    eax, eax
0x1800bdc31  jns     short loc_1800BDC61
0x1800bdc33  mov     edx, 63h ; 'c'; void *
0x1800bdc38  mov     rcx, [rbp+18h]; this
0x1800bdc3c  lea     r8, aOnecoreBaseApp_4; "onecore\\base\\appcompat\\programs\\dev"...
0x1800bdc43  mov     r9d, ebx; char *
0x1800bdc46  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800bdc4b  mov     rcx, [rbp+phProvider]; hObject
0x1800bdc4f  test    rcx, rcx
0x1800bdc52  jz      short loc_1800BDC5A
0x1800bdc54  call    cs:__imp_NCryptFreeObject
0x1800bdc5a  mov     eax, ebx
0x1800bdc5c  jmp     loc_1800BDCE1
0x1800bdc61  mov     rcx, [rbp+phProvider]; hObject
0x1800bdc65  lea     rax, [rbp+arg_8]
0x1800bdc69  mov     [rsp+30h+dwFlags], 0; dwFlags
0x1800bdc71  lea     r8, [rbp+pbOutput]; pbOutput
0x1800bdc75  mov     r9d, 4; cbOutput
0x1800bdc7b  mov     [rsp+30h+pcbResult], rax; pcbResult
0x1800bdc80  lea     rdx, aPcpTpmIfxRsaKe_0; "PCP_TPM_IFX_RSA_KEYGEN_VULNERABILITY"
0x1800bdc87  mov     [rbp+pbOutput], 0
0x1800bdc8e  mov     [rbp+arg_8], 0
0x1800bdc95  call    cs:__imp_NCryptGetProperty
0x1800bdc9b  mov     ebx, eax
0x1800bdc9d  test    eax, eax
0x1800bdc9f  jns     short loc_1800BDCC7
0x1800bdca1  mov     edi, 80284001h
0x1800bdca6  cmp     eax, edi
0x1800bdca8  jnz     short loc_1800BDCBD
0x1800bdcaa  mov     rcx, [rbp+phProvider]; hObject
0x1800bdcae  test    rcx, rcx
0x1800bdcb1  jz      short loc_1800BDCB9
0x1800bdcb3  call    cs:__imp_NCryptFreeObject
0x1800bdcb9  mov     eax, edi
0x1800bdcbb  jmp     short loc_1800BDCE1
0x1800bdcbd  mov     edx, 6Eh ; 'n'
0x1800bdcc2  jmp     loc_1800BDC38
0x1800bdcc7  cmp     [rbp+pbOutput], 0
0x1800bdccb  mov     rcx, [rbp+phProvider]; hObject
0x1800bdccf  setnz   al
0x1800bdcd2  mov     [rdi], al
0x1800bdcd4  test    rcx, rcx
0x1800bdcd7  jz      short loc_1800BDCDF
0x1800bdcd9  call    cs:__imp_NCryptFreeObject
0x1800bdcdf  xor     eax, eax
0x1800bdce1  add     rsp, 30h
0x1800bdce5  pop     rdi
0x1800bdce6  pop     rbx
0x1800bdce7  pop     rbp
0x1800bdce8  retn
```
