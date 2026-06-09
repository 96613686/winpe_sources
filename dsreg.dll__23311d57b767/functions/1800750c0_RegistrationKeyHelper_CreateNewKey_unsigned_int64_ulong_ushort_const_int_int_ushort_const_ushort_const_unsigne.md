# RegistrationKeyHelper::CreateNewKey(unsigned __int64,ulong,ushort const *,int,int,ushort const *,ushort const *,unsigned __int64 *)

- ea: `0x1800750c0`
- end: `0x1800752a7`
- name: `?CreateNewKey@RegistrationKeyHelper@@CAJ_KKPEBGHH11PEA_K@Z`
- size: `487`
- prototype: `static int(unsigned __int64, unsigned int, const unsigned __int16 *, int, int, const unsigned __int16 *, const unsigned __int16 *, unsigned __int64 *)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18007491c`
- `0x180074c58`

## callees

- `0x1800084f4`
- `0x1800307c4`
- `0x1800750c0`

## import_xrefs

- `ncrypt!NCryptSetProperty` at `0x1800751b7`
- `ncrypt!NCryptSetProperty` at `0x180075201`
- `ncrypt!NCryptSetProperty` at `0x18007523d`
- `ncrypt!NCryptSetProperty` at `0x1800751b7`
- `ncrypt!NCryptSetProperty` at `0x180075201`
- `ncrypt!NCryptSetProperty` at `0x18007523d`
- `ncrypt!NCryptCreatePersistedKey` at `0x18007516c`
- `ncrypt!NCryptCreatePersistedKey` at `0x18007516c`
- `ncrypt!NCryptDeleteKey` at `0x18007528d`
- `ncrypt!NCryptDeleteKey` at `0x18007528d`
- `ncrypt!NCryptFinalizeKey` at `0x18007525b`
- `ncrypt!NCryptFinalizeKey` at `0x18007525b`

## string_xrefs

- `0x180075178`: `NCryptCreatePersistedKey`
- `0x18007511e`: `RegistrationKeyHelper::CreateNewKey`
- `0x180075138`: `RegistrationKeyHelper::CreateNewKey`
- `0x180075182`: `RegistrationKeyHelper::CreateNewKey`

## pseudocode

```c
__int64 __fastcall RegistrationKeyHelper::CreateNewKey(
        NCRYPT_PROV_HANDLE a1,
        __int64 a2,
        const unsigned __int16 *a3,
        int a4,
        int a5,
        const unsigned __int16 *a6,
        const unsigned __int16 *a7,
        unsigned __int64 *a8)
{
  unsigned __int64 *v8; // rdi
  bool v9; // cf
  unsigned int v10; // ebx
  SECURITY_STATUS v11; // eax
  const wchar_t *v12; // r8
  BYTE pbInput[8]; // [rsp+30h] [rbp-30h] BYREF
  NCRYPT_KEY_HANDLE phKey; // [rsp+38h] [rbp-28h] BYREF
  BYTE v16[16]; // [rsp+40h] [rbp-20h] BYREF
  unsigned __int128 v17; // [rsp+50h] [rbp-10h]
  int v18; // [rsp+78h] [rbp+18h] BYREF

  v8 = a8;
  *(_DWORD *)pbInput = 2048;
  phKey = 0;
  v18 = 0;
  v9 = a5 != 0;
  a5 = -a5;
  *(_OWORD *)v16 = 0;
  v17 = 0;
  if ( !a8 )
  {
    v10 = -2147024809;
    Logger::TraceError(L"%s: \"%s\" should not be null.", L"RegistrationKeyHelper::CreateNewKey", L"handle");
    Logger::WriteNullOrEmptyParameterFailureEvent(L"RegistrationKeyHelper::CreateNewKey", L"handle");
    goto LABEL_15;
  }
  *a8 = 0;
  v11 = NCryptCreatePersistedKey(a1, &phKey, L"RSA", a3, 0, (a4 != 0 ? 0x20 : 0) | (v9 ? 0x80 : 0));
  v10 = v11;
  if ( v11 < 0 )
  {
    v12 = L"NCryptCreatePersistedKey";
LABEL_5:
    Logger::TraceError(
      L"%s: %s failed with error code: 0x%08x.",
      L"RegistrationKeyHelper::CreateNewKey",
      v12,
      (unsigned int)v11);
    goto LABEL_15;
  }
  v11 = NCryptSetProperty(phKey, L"Length", pbInput, 4u, 0);
  v10 = v11;
  if ( v11 < 0 )
  {
    v12 = L"NCryptSetProperty(NCRYPT_LENGTH_PROPERTY)";
    goto LABEL_5;
  }
  v17 = __PAIR128__((unsigned __int64)a7, (unsigned __int64)a6);
  *(_QWORD *)v16 = 1;
  v11 = NCryptSetProperty(phKey, L"UI Policy", v16, 0x20u, 0x80000000);
  v10 = v11;
  if ( v11 < 0 )
  {
    v12 = L"NCryptSetProperty(NCRYPT_UI_POLICY_PROPERTY)";
    goto LABEL_5;
  }
  v18 = 2;
  v11 = NCryptSetProperty(phKey, L"Key Usage", (PBYTE)&v18, 4u, 0x80000000);
  v10 = v11;
  if ( v11 < 0 )
  {
    v12 = L"NCryptSetProperty(NCRYPT_KEY_USAGE_PROPERTY)";
    goto LABEL_5;
  }
  v11 = NCryptFinalizeKey(phKey, 0);
  v10 = v11;
  if ( v11 < 0 )
  {
    v12 = L"NCryptFinalizeKey";
    goto LABEL_5;
  }
  *v8 = phKey;
  phKey = 0;
LABEL_15:
  if ( phKey )
    NCryptDeleteKey(phKey, 0);
  return v10;
}

```

## disassembly

```asm
0x1800750c0  mov     [rsp-8+arg_0], rbx
0x1800750c5  mov     [rsp-8+arg_10], rdi
0x1800750ca  mov     [rsp-8+arg_8], edx
0x1800750ce  push    rbp
0x1800750cf  mov     rbp, rsp
0x1800750d2  sub     rsp, 60h
0x1800750d6  mov     rdi, [rbp+arg_38]
0x1800750da  neg     r9d
0x1800750dd  xorps   xmm0, xmm0
0x1800750e0  mov     dword ptr [rbp+pbInput], 800h
0x1800750e7  sbb     edx, edx
0x1800750e9  mov     [rbp+phKey], 0
0x1800750f1  and     edx, 20h
0x1800750f4  mov     [rbp+arg_8], 0
0x1800750fb  neg     [rbp+arg_20]
0x1800750fe  movups  xmmword ptr [rbp+var_20], xmm0
0x180075102  sbb     eax, eax
0x180075104  and     eax, 80h
0x180075109  movups  [rbp+var_10], xmm0
0x18007510d  test    rdi, rdi
0x180075110  jnz     short loc_180075149
0x180075112  lea     r8, aHandle; "handle"
0x180075119  mov     ebx, 80070057h
0x18007511e  lea     rdx, aRegistrationke_1; "RegistrationKeyHelper::CreateNewKey"
0x180075125  lea     rcx, aSSShouldNotBeN_0; "%s: \"%s\" should not be null."
0x18007512c  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180075131  lea     rdx, aHandle; "handle"
0x180075138  lea     rcx, aRegistrationke_1; "RegistrationKeyHelper::CreateNewKey"
0x18007513f  call    ?WriteNullOrEmptyParameterFailureEvent@Logger@@SAJPEBG0@Z; Logger::WriteNullOrEmptyParameterFailureEvent(ushort const *,ushort const *)
0x180075144  jmp     loc_180075282
0x180075149  or      eax, edx
0x18007514b  mov     qword ptr [rdi], 0
0x180075152  mov     r9, r8; pszKeyName
0x180075155  mov     [rsp+60h+dwFlags], eax; dwFlags
0x180075159  lea     r8, pszAlgId; "RSA"
0x180075160  mov     [rsp+60h+dwLegacyKeySpec], 0; dwLegacyKeySpec
0x180075168  lea     rdx, [rbp+phKey]; phKey
0x18007516c  call    cs:__imp_NCryptCreatePersistedKey
0x180075172  mov     ebx, eax
0x180075174  test    eax, eax
0x180075176  jns     short loc_18007519A
0x180075178  lea     r8, aNcryptcreatepe_0; "NCryptCreatePersistedKey"
0x18007517f  mov     r9d, eax
0x180075182  lea     rdx, aRegistrationke_1; "RegistrationKeyHelper::CreateNewKey"
0x180075189  lea     rcx, aSSFailedWithEr_2; "%s: %s failed with error code: 0x%08x."
0x180075190  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180075195  jmp     loc_180075282
0x18007519a  mov     rcx, [rbp+phKey]; hObject
0x18007519e  lea     r8, [rbp+pbInput]; pbInput
0x1800751a2  mov     r9d, 4; cbInput
0x1800751a8  mov     [rsp+60h+dwLegacyKeySpec], 0; dwFlags
0x1800751b0  lea     rdx, pszProperty; "Length"
0x1800751b7  call    cs:__imp_NCryptSetProperty
0x1800751bd  mov     ebx, eax
0x1800751bf  test    eax, eax
0x1800751c1  jns     short loc_1800751CC
0x1800751c3  lea     r8, aNcryptsetprope_2; "NCryptSetProperty(NCRYPT_LENGTH_PROPERT"...
0x1800751ca  jmp     short loc_18007517F
0x1800751cc  mov     rax, [rbp+arg_28]
0x1800751d0  lea     r8, [rbp+var_20]; pbInput
0x1800751d4  mov     rcx, [rbp+phKey]; hObject
0x1800751d8  lea     rdx, aUiPolicy; "UI Policy"
0x1800751df  mov     qword ptr [rbp+var_10], rax
0x1800751e3  mov     r9d, 20h ; ' '; cbInput
0x1800751e9  mov     rax, [rbp+arg_30]
0x1800751ed  mov     qword ptr [rbp+var_10+8], rax
0x1800751f1  mov     qword ptr [rbp+var_20], 1
0x1800751f9  mov     [rsp+60h+dwLegacyKeySpec], 80000000h; dwFlags
0x180075201  call    cs:__imp_NCryptSetProperty
0x180075207  mov     ebx, eax
0x180075209  test    eax, eax
0x18007520b  jns     short loc_180075219
0x18007520d  lea     r8, aNcryptsetprope_0; "NCryptSetProperty(NCRYPT_UI_POLICY_PROP"...
0x180075214  jmp     loc_18007517F
0x180075219  mov     rcx, [rbp+phKey]; hObject
0x18007521d  lea     r8, [rbp+arg_8]; pbInput
0x180075221  mov     r9d, 4; cbInput
0x180075227  mov     [rbp+arg_8], 2
0x18007522e  lea     rdx, aKeyUsage; "Key Usage"
0x180075235  mov     [rsp+60h+dwLegacyKeySpec], 80000000h; dwFlags
0x18007523d  call    cs:__imp_NCryptSetProperty
0x180075243  mov     ebx, eax
0x180075245  test    eax, eax
0x180075247  jns     short loc_180075255
0x180075249  lea     r8, aNcryptsetprope_1; "NCryptSetProperty(NCRYPT_KEY_USAGE_PROP"...
0x180075250  jmp     loc_18007517F
0x180075255  mov     rcx, [rbp+phKey]; hKey
0x180075259  xor     edx, edx; dwFlags
0x18007525b  call    cs:__imp_NCryptFinalizeKey
0x180075261  mov     ebx, eax
0x180075263  test    eax, eax
0x180075265  jns     short loc_180075273
0x180075267  lea     r8, aNcryptfinalize_0; "NCryptFinalizeKey"
0x18007526e  jmp     loc_18007517F
0x180075273  mov     rax, [rbp+phKey]
0x180075277  mov     [rdi], rax
0x18007527a  mov     [rbp+phKey], 0
0x180075282  mov     rcx, [rbp+phKey]; hKey
0x180075286  test    rcx, rcx
0x180075289  jz      short loc_180075293
0x18007528b  xor     edx, edx; dwFlags
0x18007528d  call    cs:__imp_NCryptDeleteKey
0x180075293  lea     r11, [rsp+60h+var_s0]
0x180075298  mov     eax, ebx
0x18007529a  mov     rbx, [r11+10h]
0x18007529e  mov     rdi, [r11+20h]
0x1800752a2  mov     rsp, r11
0x1800752a5  pop     rbp
0x1800752a6  retn
```
