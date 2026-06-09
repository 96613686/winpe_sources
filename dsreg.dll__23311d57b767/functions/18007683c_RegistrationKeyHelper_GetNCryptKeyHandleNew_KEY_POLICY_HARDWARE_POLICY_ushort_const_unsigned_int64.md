# RegistrationKeyHelper::GetNCryptKeyHandleNew(_KEY_POLICY,_HARDWARE_POLICY,ushort const *,unsigned __int64 *)

- ea: `0x18007683c`
- end: `0x180076a74`
- name: `?GetNCryptKeyHandleNew@RegistrationKeyHelper@@SAJW4_KEY_POLICY@@W4_HARDWARE_POLICY@@PEBGPEA_K@Z`
- size: `568`
- prototype: `static int __high(enum _KEY_POLICY, enum _HARDWARE_POLICY, const unsigned __int16 *, unsigned __int64 *)`
- caller_count: `3`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18005db34`
- `0x18005e604`
- `0x18005e84c`

## callees

- `0x1800084f4`
- `0x180008530`
- `0x18000bac0`
- `0x180012948`
- `0x1800307c4`
- `0x180044300`
- `0x18007683c`
- `0x180076b8c`
- `0x180076bd8`
- `0x1800b8c44`

## import_xrefs

- `ncrypt!NCryptOpenKey` at `0x1800769e4`
- `ncrypt!NCryptOpenKey` at `0x1800769e4`
- `ncrypt!NCryptFreeObject` at `0x180076955`
- `ncrypt!NCryptFreeObject` at `0x180076a3a`
- `ncrypt!NCryptFreeObject` at `0x180076955`
- `ncrypt!NCryptFreeObject` at `0x180076a3a`

## string_xrefs

- `0x180076998`: `%s: NCryptOpenStorageProvider('%s') failed with 0x%08x`
- `0x180076a0c`: `%s: Key opened successfully using '%s' provider.`
- `0x1800769f6`: `%s: NCryptOpenKey failed with 0x%08x`
- `0x180076a22`: `%s: Key could not be opened successfully. Number of providers tried: %d`

## pseudocode

```c
__int64 __fastcall RegistrationKeyHelper::GetNCryptKeyHandleNew(
        unsigned int a1,
        DWORD a2,
        __int64 a3,
        NCRYPT_KEY_HANDLE *a4)
{
  int v7; // ebx
  int AadKeyStorageProviders; // eax
  signed int i; // edi
  const unsigned __int16 *v10; // rsi
  int v11; // eax
  SECURITY_STATUS v12; // eax
  DWORD dwFlags[2]; // [rsp+20h] [rbp-40h]
  unsigned int v15; // [rsp+30h] [rbp-30h] BYREF
  int v16; // [rsp+34h] [rbp-2Ch] BYREF
  NCRYPT_HANDLE hObject; // [rsp+38h] [rbp-28h] BYREF
  unsigned __int16 *v18[2]; // [rsp+40h] [rbp-20h] BYREF
  __int64 v19; // [rsp+50h] [rbp-10h]

  Logger::TraceVerbose(
    (wchar_t *)L"%s started. %s: %s.",
    L"RegistrationKeyHelper::GetNCryptKeyHandleNew",
    L"keyContainerName",
    L"6b30069e-b381-42cc-9fae-421915a9e9f3");
  hObject = 0;
  v19 = 0;
  v15 = 3;
  *(_OWORD *)v18 = 0;
  if ( a4 )
  {
    *a4 = 0;
    AadKeyStorageProviders = GetAadKeyStorageProviders(a1, a2, 0, 1, v18, &v15);
    v7 = AadKeyStorageProviders;
    if ( AadKeyStorageProviders >= 0 )
    {
      dwFlags[0] = a2;
      Logger::TraceInformation(
        L"%s: %d KSPs to try based on key policy %lu and hardware policy %lu",
        L"RegistrationKeyHelper::GetNCryptKeyHandleNew",
        v15,
        a1,
        *(_QWORD *)dwFlags);
      for ( i = 0; i < (int)v15; ++i )
      {
        if ( hObject )
        {
          NCryptFreeObject(hObject);
          hObject = 0;
        }
        v10 = v18[i];
        Logger::TraceInformation(L"%s: Trying provider '%s'.", L"RegistrationKeyHelper::GetNCryptKeyHandleNew", v10);
        v11 = RegistrationKeyHelper::OpenNCryptStorageProvider(v10, &hObject, 1);
        v7 = v11;
        if ( v11 >= 0 )
        {
          v16 = 0;
          RegistrationKeyHelper::IsTpmProvider(v10, &v16);
          v12 = NCryptOpenKey(hObject, a4, L"6b30069e-b381-42cc-9fae-421915a9e9f3", 0, v16 != 0 ? 268435552 : 96);
          v7 = v12;
          if ( v12 >= 0 )
          {
            Logger::TraceInformation(
              L"%s: Key opened successfully using '%s' provider.",
              L"RegistrationKeyHelper::GetNCryptKeyHandleNew",
              v10);
            goto LABEL_17;
          }
          Logger::TraceWarning(
            (wchar_t *)L"%s: NCryptOpenKey failed with 0x%08x",
            L"RegistrationKeyHelper::GetNCryptKeyHandleNew",
            (unsigned int)v12);
        }
        else
        {
          Logger::TraceWarning(
            (wchar_t *)L"%s: NCryptOpenStorageProvider('%s') failed with 0x%08x",
            L"RegistrationKeyHelper::GetNCryptKeyHandleNew",
            v10,
            (unsigned int)v11);
        }
      }
      if ( v7 < 0 )
        Logger::TraceError(
          L"%s: Key could not be opened successfully. Number of providers tried: %d",
          L"RegistrationKeyHelper::GetNCryptKeyHandleNew",
          v15);
    }
    else
    {
      Logger::TraceError(
        L"%s: %s failed with error code: 0x%08x.",
        L"RegistrationKeyHelper::GetNCryptKeyHandleNew",
        L"GetAadKeyStorageProviders",
        (unsigned int)AadKeyStorageProviders);
    }
  }
  else
  {
    v7 = -2147024809;
    Logger::TraceError(L"%s: \"%s\" should not be null.", L"RegistrationKeyHelper::GetNCryptKeyHandleNew", L"handle");
    Logger::WriteNullOrEmptyParameterFailureEvent(L"RegistrationKeyHelper::GetNCryptKeyHandleNew", L"handle");
  }
LABEL_17:
  if ( hObject )
    NCryptFreeObject(hObject);
  Logger::TraceVerbose((wchar_t *)L"%s - hr: 0x%08x", L"RegistrationKeyHelper::GetNCryptKeyHandleNew", (unsigned int)v7);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18007683c  mov     [rsp-28h+arg_10], rbx
0x180076841  push    rbp
0x180076842  push    rsi
0x180076843  push    rdi
0x180076844  push    r12
0x180076846  push    r15
0x180076848  mov     rbp, rsp
0x18007684b  sub     rsp, 60h
0x18007684f  mov     rax, cs:__security_cookie
0x180076856  xor     rax, rsp
0x180076859  mov     [rbp+var_8], rax
0x18007685d  mov     r15, r9
0x180076860  lea     r12, aRegistrationke_8; "RegistrationKeyHelper::GetNCryptKeyHand"...
0x180076867  mov     esi, edx
0x180076869  lea     r9, pszKeyName; "6b30069e-b381-42cc-9fae-421915a9e9f3"
0x180076870  mov     edi, ecx
0x180076872  lea     r8, aKeycontainerna; "keyContainerName"
0x180076879  mov     rdx, r12
0x18007687c  lea     rcx, aSStartedSS; "%s started. %s: %s."
0x180076883  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x180076888  mov     [rbp+hObject], 0
0x180076890  xorps   xmm0, xmm0
0x180076893  mov     [rbp+var_10], 0
0x18007689b  mov     [rbp+var_30], 3
0x1800768a2  movdqu  xmmword ptr [rbp+var_20], xmm0
0x1800768a7  test    r15, r15
0x1800768aa  jnz     short loc_1800768DB
0x1800768ac  lea     r8, aHandle; "handle"
0x1800768b3  mov     rdx, r12
0x1800768b6  lea     rcx, aSSShouldNotBeN_0; "%s: \"%s\" should not be null."
0x1800768bd  mov     ebx, 80070057h
0x1800768c2  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x1800768c7  lea     rdx, aHandle; "handle"
0x1800768ce  mov     rcx, r12; unsigned __int16 *
0x1800768d1  call    ?WriteNullOrEmptyParameterFailureEvent@Logger@@SAJPEBG0@Z; Logger::WriteNullOrEmptyParameterFailureEvent(ushort const *,ushort const *)
0x1800768d6  jmp     loc_180076A31
0x1800768db  lea     rax, [rbp+var_30]
0x1800768df  mov     qword ptr [r15], 0
0x1800768e6  mov     [rsp+60h+var_38], rax
0x1800768eb  mov     r9d, 1
0x1800768f1  lea     rax, [rbp+var_20]
0x1800768f5  xor     r8d, r8d
0x1800768f8  mov     edx, esi
0x1800768fa  mov     qword ptr [rsp+60h+dwFlags], rax
0x1800768ff  mov     ecx, edi
0x180076901  call    ?GetAadKeyStorageProviders@@YAJW4_KEY_POLICY@@W4_HARDWARE_POLICY@@IHQEAPEBGAEAH@Z; GetAadKeyStorageProviders(_KEY_POLICY,_HARDWARE_POLICY,uint,int,ushort const * * const,int &)
0x180076906  mov     ebx, eax
0x180076908  mov     rdx, r12
0x18007690b  test    eax, eax
0x18007690d  jns     short loc_18007692A
0x18007690f  mov     r9d, eax
0x180076912  lea     r8, aGetaadkeystora; "GetAadKeyStorageProviders"
0x180076919  lea     rcx, aSSFailedWithEr_2; "%s: %s failed with error code: 0x%08x."
0x180076920  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180076925  jmp     loc_180076A31
0x18007692a  mov     r8d, [rbp+var_30]
0x18007692e  lea     rcx, aSDKspsToTryBas; "%s: %d KSPs to try based on key policy "...
0x180076935  mov     r9d, edi
0x180076938  mov     [rsp+60h+dwFlags], esi
0x18007693c  call    ?TraceInformation@Logger@@SAJPEBGZZ; Logger::TraceInformation(ushort const *,...)
0x180076941  xor     edi, edi
0x180076943  cmp     edi, [rbp+var_30]
0x180076946  jge     loc_180076A1A
0x18007694c  mov     rcx, [rbp+hObject]; hObject
0x180076950  test    rcx, rcx
0x180076953  jz      short loc_180076963
0x180076955  call    cs:__imp_NCryptFreeObject
0x18007695b  mov     [rbp+hObject], 0
0x180076963  movsxd  rax, edi
0x180076966  lea     rcx, aSTryingProvide; "%s: Trying provider '%s'."
0x18007696d  mov     rdx, r12
0x180076970  mov     rsi, [rbp+rax*8+var_20]
0x180076975  mov     r8, rsi
0x180076978  call    ?TraceInformation@Logger@@SAJPEBGZZ; Logger::TraceInformation(ushort const *,...)
0x18007697d  mov     r8d, 1; int
0x180076983  lea     rdx, [rbp+hObject]; phProvider
0x180076987  mov     rcx, rsi; unsigned __int16 *
0x18007698a  call    ?OpenNCryptStorageProvider@RegistrationKeyHelper@@SAJPEBGPEA_KH@Z; RegistrationKeyHelper::OpenNCryptStorageProvider(ushort const *,unsigned __int64 *,int)
0x18007698f  mov     ebx, eax
0x180076991  test    eax, eax
0x180076993  jns     short loc_1800769AC
0x180076995  mov     r9d, eax
0x180076998  lea     rcx, aSNcryptopensto; "%s: NCryptOpenStorageProvider('%s') fai"...
0x18007699f  mov     r8, rsi
0x1800769a2  mov     rdx, r12
0x1800769a5  call    ?TraceWarning@Logger@@SAJPEBGZZ; Logger::TraceWarning(ushort const *,...)
0x1800769aa  jmp     short loc_180076A02
0x1800769ac  lea     rdx, [rbp+var_2C]; int *
0x1800769b0  mov     [rbp+var_2C], 0
0x1800769b7  mov     rcx, rsi; unsigned __int16 *
0x1800769ba  call    ?IsTpmProvider@RegistrationKeyHelper@@SAJPEBGAEAH@Z; RegistrationKeyHelper::IsTpmProvider(ushort const *,int &)
0x1800769bf  mov     eax, [rbp+var_2C]
0x1800769c2  lea     r8, pszKeyName; "6b30069e-b381-42cc-9fae-421915a9e9f3"
0x1800769c9  neg     eax
0x1800769cb  mov     rdx, r15; phKey
0x1800769ce  sbb     ecx, ecx
0x1800769d0  xor     r9d, r9d; dwLegacyKeySpec
0x1800769d3  and     ecx, 10000000h
0x1800769d9  add     ecx, 60h ; '`'
0x1800769dc  mov     [rsp+60h+dwFlags], ecx; dwFlags
0x1800769e0  mov     rcx, [rbp+hObject]; hProvider
0x1800769e4  call    cs:__imp_NCryptOpenKey
0x1800769ea  mov     ebx, eax
0x1800769ec  mov     rdx, r12
0x1800769ef  test    eax, eax
0x1800769f1  jns     short loc_180076A09
0x1800769f3  mov     r8d, eax
0x1800769f6  lea     rcx, aSNcryptopenkey_0; "%s: NCryptOpenKey failed with 0x%08x"
0x1800769fd  call    ?TraceWarning@Logger@@SAJPEBGZZ; Logger::TraceWarning(ushort const *,...)
0x180076a02  inc     edi
0x180076a04  jmp     loc_180076943
0x180076a09  mov     r8, rsi
0x180076a0c  lea     rcx, aSKeyOpenedSucc; "%s: Key opened successfully using '%s' "...
0x180076a13  call    ?TraceInformation@Logger@@SAJPEBGZZ; Logger::TraceInformation(ushort const *,...)
0x180076a18  jmp     short loc_180076A31
0x180076a1a  test    ebx, ebx
0x180076a1c  jns     short loc_180076A31
0x180076a1e  mov     r8d, [rbp+var_30]
0x180076a22  lea     rcx, aSKeyCouldNotBe; "%s: Key could not be opened successfull"...
0x180076a29  mov     rdx, r12
0x180076a2c  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180076a31  mov     rcx, [rbp+hObject]; hObject
0x180076a35  test    rcx, rcx
0x180076a38  jz      short loc_180076A40
0x180076a3a  call    cs:__imp_NCryptFreeObject
0x180076a40  mov     r8d, ebx
0x180076a43  lea     rcx, aSHr0x08x; "%s - hr: 0x%08x"
0x180076a4a  mov     rdx, r12
0x180076a4d  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x180076a52  mov     eax, ebx
0x180076a54  mov     rcx, [rbp+var_8]
0x180076a58  xor     rcx, rsp; StackCookie
0x180076a5b  call    __security_check_cookie
0x180076a60  mov     rbx, [rsp+60h+arg_10]
0x180076a68  add     rsp, 60h
0x180076a6c  pop     r15
0x180076a6e  pop     r12
0x180076a70  pop     rdi
0x180076a71  pop     rsi
0x180076a72  pop     rbp
0x180076a73  retn
```
