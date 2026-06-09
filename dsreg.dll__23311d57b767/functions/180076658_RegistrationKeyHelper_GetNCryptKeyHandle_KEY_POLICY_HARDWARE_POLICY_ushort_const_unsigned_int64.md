# RegistrationKeyHelper::GetNCryptKeyHandle(_KEY_POLICY,_HARDWARE_POLICY,ushort const *,unsigned __int64 *)

- ea: `0x180076658`
- end: `0x180076833`
- name: `?GetNCryptKeyHandle@RegistrationKeyHelper@@SAJW4_KEY_POLICY@@W4_HARDWARE_POLICY@@PEBGPEA_K@Z`
- size: `475`
- prototype: ``
- caller_count: `3`
- callee_count: `8`
- tags: `file_ops, registry_config`

## callers

- `0x18005db34`
- `0x18005e604`
- `0x18005e84c`

## callees

- `0x1800084f4`
- `0x180008530`
- `0x18000bac0`
- `0x180043ef8`
- `0x180076658`
- `0x180076b8c`
- `0x180076e10`
- `0x18008b8a4`

## import_xrefs

- `ncrypt!NCryptOpenKey` at `0x180076748`
- `ncrypt!NCryptOpenKey` at `0x180076748`
- `ncrypt!NCryptFreeObject` at `0x1800767b2`
- `ncrypt!NCryptFreeObject` at `0x1800767c9`
- `ncrypt!NCryptFreeObject` at `0x1800767b2`
- `ncrypt!NCryptFreeObject` at `0x1800767c9`

## string_xrefs

- `0x1800766d4`: `TryNCryptOpenStorageProvider`
- `0x180076767`: `%s: NCryptOpenKey failed with error code 0x%08x. pszProviderName = %s, pszKeyName = %s, dwLegacyKeySpec = %lu, dwFlags = %lu`

## pseudocode

```c
__int64 __fastcall RegistrationKeyHelper::GetNCryptKeyHandle(unsigned int a1, int a2, void *a3, NCRYPT_KEY_HANDLE *a4)
{
  int v6; // esi
  BOOL v7; // r14d
  int v8; // eax
  unsigned int v9; // ebx
  int IsTpmProvider; // eax
  __int64 v12; // [rsp+30h] [rbp-20h]
  NCRYPT_PROV_HANDLE hProvider[2]; // [rsp+40h] [rbp-10h] BYREF
  int v14; // [rsp+88h] [rbp+38h] BYREF
  void *Block; // [rsp+90h] [rbp+40h] BYREF
  NCRYPT_KEY_HANDLE phKey; // [rsp+98h] [rbp+48h] BYREF

  Block = a3;
  v14 = a2;
  Logger::TraceVerbose(
    (wchar_t *)L"%s started. %s: %s.",
    L"RegistrationKeyHelper::GetNCryptKeyHandle",
    L"KeyContainerName",
    L"6b30069e-b381-42cc-9fae-421915a9e9f3");
  v6 = 0;
  v14 = 0;
  phKey = 0;
  v7 = a1 != 2;
  hProvider[0] = 0;
  Block = 0;
  *a4 = 0;
  while ( 1 )
  {
    v8 = RegistrationKeyHelper::TryNCryptOpenStorageProvider(a1, hProvider, &Block);
    v9 = v8;
    if ( v8 >= 0 )
    {
      IsTpmProvider = RegistrationKeyHelper::IsTpmProvider((const unsigned __int16 *)Block, &v14);
      v9 = IsTpmProvider;
      if ( IsTpmProvider >= 0 )
      {
        v6 = v14;
        v9 = NCryptOpenKey(hProvider[0], &phKey, L"6b30069e-b381-42cc-9fae-421915a9e9f3", 0, v14 != 0 ? 268435552 : 96);
        if ( (v9 & 0x80000000) == 0 )
        {
          *a4 = phKey;
          phKey = 0;
        }
        else
        {
          LODWORD(v12) = 96;
          Logger::TraceError(
            L"%s: NCryptOpenKey failed with error code 0x%08x. pszProviderName = %s, pszKeyName = %s, dwLegacyKeySpec = %l"
             "u, dwFlags = %lu",
            L"RegistrationKeyHelper::GetNCryptKeyHandle",
            v9,
            Block,
            L"6b30069e-b381-42cc-9fae-421915a9e9f3",
            0,
            v12);
        }
      }
      else
      {
        Logger::TraceError(
          L"%s: %s failed with error code: 0x%08x.",
          L"RegistrationKeyHelper::GetNCryptKeyHandle",
          L"RegistrationKeyHelper::IsTpmProvider",
          (unsigned int)IsTpmProvider);
        v6 = v14;
      }
    }
    else
    {
      Logger::TraceError(
        L"%s: %s failed with error code: 0x%08x.",
        L"RegistrationKeyHelper::GetNCryptKeyHandle",
        L"TryNCryptOpenStorageProvider",
        (unsigned int)v8);
    }
    operator delete(Block);
    Block = 0;
    if ( phKey )
    {
      NCryptFreeObject(phKey);
      phKey = 0;
    }
    if ( hProvider[0] )
    {
      NCryptFreeObject(hProvider[0]);
      hProvider[0] = 0;
    }
    if ( !v7 || !v6 || !(unsigned int)IsTpmError(v9) )
      break;
    Logger::TraceWarning(
      (wchar_t *)L"%s: Error 0x%08X is detected as TPM-related. Falling back to software key provider",
      L"RegistrationKeyHelper::GetNCryptKeyHandle",
      v9);
    v7 = 0;
    a1 = 3;
  }
  Logger::TraceVerbose((wchar_t *)L"%s - hr: 0x%08x", L"RegistrationKeyHelper::GetNCryptKeyHandle", v9);
  return v9;
}

```

## disassembly

```asm
0x180076658  mov     [rsp-28h+arg_0], rbx
0x18007665d  mov     [rsp-28h+Block], r8
0x180076662  mov     [rsp-28h+arg_8], edx
0x180076666  push    rbp
0x180076667  push    rsi
0x180076668  push    r13
0x18007666a  push    r14
0x18007666c  push    r15
0x18007666e  mov     rbp, rsp
0x180076671  sub     rsp, 50h
0x180076675  mov     r15, r9
0x180076678  lea     r13, aRegistrationke_2; "RegistrationKeyHelper::GetNCryptKeyHand"...
0x18007667f  mov     ebx, ecx
0x180076681  lea     r9, pszKeyName; "6b30069e-b381-42cc-9fae-421915a9e9f3"
0x180076688  mov     rdx, r13
0x18007668b  lea     r8, aKeycontainerna_0; "KeyContainerName"
0x180076692  lea     rcx, aSStartedSS; "%s started. %s: %s."
0x180076699  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x18007669e  xor     esi, esi
0x1800766a0  xor     r14d, r14d
0x1800766a3  cmp     ebx, 2
0x1800766a6  mov     [rbp+arg_8], esi
0x1800766a9  mov     [rbp+phKey], rsi
0x1800766ad  setnz   r14b
0x1800766b1  mov     [rbp+hProvider], rsi
0x1800766b5  mov     [rbp+Block], rsi
0x1800766b9  mov     [r15], rsi
0x1800766bc  lea     r8, [rbp+Block]
0x1800766c0  mov     ecx, ebx
0x1800766c2  lea     rdx, [rbp+hProvider]
0x1800766c6  call    ?TryNCryptOpenStorageProvider@RegistrationKeyHelper@@CAJW4_KEY_POLICY@@PEA_KPEAPEAG@Z; RegistrationKeyHelper::TryNCryptOpenStorageProvider(_KEY_POLICY,unsigned __int64 *,ushort * *)
0x1800766cb  mov     ebx, eax
0x1800766cd  test    eax, eax
0x1800766cf  jns     short loc_1800766EF
0x1800766d1  mov     r9d, eax
0x1800766d4  lea     r8, aTryncryptopens; "TryNCryptOpenStorageProvider"
0x1800766db  mov     rdx, r13
0x1800766de  lea     rcx, aSSFailedWithEr_2; "%s: %s failed with error code: 0x%08x."
0x1800766e5  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x1800766ea  jmp     loc_180076798
0x1800766ef  mov     rcx, [rbp+Block]; unsigned __int16 *
0x1800766f3  lea     rdx, [rbp+arg_8]; int *
0x1800766f7  call    ?IsTpmProvider@RegistrationKeyHelper@@SAJPEBGAEAH@Z; RegistrationKeyHelper::IsTpmProvider(ushort const *,int &)
0x1800766fc  mov     ebx, eax
0x1800766fe  test    eax, eax
0x180076700  jns     short loc_180076720
0x180076702  mov     r9d, eax
0x180076705  lea     r8, aRegistrationke_3; "RegistrationKeyHelper::IsTpmProvider"
0x18007670c  mov     rdx, r13
0x18007670f  lea     rcx, aSSFailedWithEr_2; "%s: %s failed with error code: 0x%08x."
0x180076716  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18007671b  mov     esi, [rbp+arg_8]
0x18007671e  jmp     short loc_180076798
0x180076720  mov     esi, [rbp+arg_8]
0x180076723  lea     r8, pszKeyName; "6b30069e-b381-42cc-9fae-421915a9e9f3"
0x18007672a  mov     eax, esi
0x18007672c  lea     rdx, [rbp+phKey]; phKey
0x180076730  neg     eax
0x180076732  sbb     ecx, ecx
0x180076734  xor     r9d, r9d; dwLegacyKeySpec
0x180076737  and     ecx, 10000000h
0x18007673d  add     ecx, 60h ; '`'
0x180076740  mov     [rsp+50h+dwFlags], ecx; dwFlags
0x180076744  mov     rcx, [rbp+hProvider]; hProvider
0x180076748  call    cs:__imp_NCryptOpenKey
0x18007674e  mov     ebx, eax
0x180076750  test    eax, eax
0x180076752  jns     short loc_180076789
0x180076754  mov     r9, [rbp+Block]
0x180076758  lea     rax, pszKeyName; "6b30069e-b381-42cc-9fae-421915a9e9f3"
0x18007675f  mov     [rsp+50h+var_20], 60h ; '`'
0x180076767  lea     rcx, aSNcryptopenkey_1; "%s: NCryptOpenKey failed with error cod"...
0x18007676e  mov     [rsp+50h+var_28], 0
0x180076777  mov     r8d, ebx
0x18007677a  mov     rdx, r13
0x18007677d  mov     qword ptr [rsp+50h+dwFlags], rax
0x180076782  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180076787  jmp     short loc_180076798
0x180076789  mov     rax, [rbp+phKey]
0x18007678d  mov     [r15], rax
0x180076790  mov     [rbp+phKey], 0
0x180076798  mov     rcx, [rbp+Block]; Block
0x18007679c  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800767a1  mov     rcx, [rbp+phKey]; hObject
0x1800767a5  mov     [rbp+Block], 0
0x1800767ad  test    rcx, rcx
0x1800767b0  jz      short loc_1800767C0
0x1800767b2  call    cs:__imp_NCryptFreeObject
0x1800767b8  mov     [rbp+phKey], 0
0x1800767c0  mov     rcx, [rbp+hProvider]; hObject
0x1800767c4  test    rcx, rcx
0x1800767c7  jz      short loc_1800767D7
0x1800767c9  call    cs:__imp_NCryptFreeObject
0x1800767cf  mov     [rbp+hProvider], 0
0x1800767d7  test    r14d, r14d
0x1800767da  jz      short loc_18007680A
0x1800767dc  test    esi, esi
0x1800767de  jz      short loc_18007680A
0x1800767e0  mov     ecx, ebx; int
0x1800767e2  call    ?IsTpmError@@YAHJ@Z; IsTpmError(long)
0x1800767e7  test    eax, eax
0x1800767e9  jz      short loc_18007680A
0x1800767eb  mov     r8d, ebx
0x1800767ee  lea     rcx, aSError0x08xIsD; "%s: Error 0x%08X is detected as TPM-rel"...
0x1800767f5  mov     rdx, r13
0x1800767f8  call    ?TraceWarning@Logger@@SAJPEBGZZ; Logger::TraceWarning(ushort const *,...)
0x1800767fd  xor     r14d, r14d
0x180076800  mov     ebx, 3
0x180076805  jmp     loc_1800766BC
0x18007680a  mov     r8d, ebx
0x18007680d  lea     rcx, aSHr0x08x; "%s - hr: 0x%08x"
0x180076814  mov     rdx, r13
0x180076817  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x18007681c  mov     eax, ebx
0x18007681e  mov     rbx, [rsp+50h+arg_0]
0x180076826  add     rsp, 50h
0x18007682a  pop     r15
0x18007682c  pop     r14
0x18007682e  pop     r13
0x180076830  pop     rsi
0x180076831  pop     rbp
0x180076832  retn
```
