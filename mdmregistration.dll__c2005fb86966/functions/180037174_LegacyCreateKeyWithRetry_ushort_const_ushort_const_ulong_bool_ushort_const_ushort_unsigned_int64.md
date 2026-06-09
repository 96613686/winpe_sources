# LegacyCreateKeyWithRetry(ushort const *,ushort const *,ulong,bool,ushort const *,ushort *,unsigned __int64 *)

- ea: `0x180037174`
- end: `0x180037640`
- name: `?LegacyCreateKeyWithRetry@@YAJPEBG0K_N0PEAGPEA_K@Z`
- size: `1228`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *, unsigned int, bool, const unsigned __int16 *, unsigned __int16 *, unsigned __int64 *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180034b80`

## callees

- `0x1800026d0`
- `0x18000bd7c`
- `0x180012f70`
- `0x1800141b0`
- `0x180019f44`
- `0x180021e6c`
- `0x180037174`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18003743e`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18003743e`
- `ntdll!RtlNtStatusToDosError` at `0x18003728b`
- `ntdll!RtlNtStatusToDosError` at `0x18003728b`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180037203`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180037203`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800375a8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800375a8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800371e9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180037592`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800371e9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180037592`
- `ncrypt!NCryptSetProperty` at `0x180037405`
- `ncrypt!NCryptSetProperty` at `0x180037468`
- `ncrypt!NCryptSetProperty` at `0x180037405`
- `ncrypt!NCryptSetProperty` at `0x180037468`
- `ncrypt!NCryptFinalizeKey` at `0x1800374fb`
- `ncrypt!NCryptFinalizeKey` at `0x1800374fb`
- `ncrypt!NCryptCreatePersistedKey` at `0x1800373a2`
- `ncrypt!NCryptCreatePersistedKey` at `0x1800373a2`
- `ncrypt!NCryptFreeObject` at `0x180037316`
- `ncrypt!NCryptFreeObject` at `0x1800375c3`
- `ncrypt!NCryptFreeObject` at `0x1800375dc`
- `ncrypt!NCryptFreeObject` at `0x180037316`
- `ncrypt!NCryptFreeObject` at `0x1800375c3`
- `ncrypt!NCryptFreeObject` at `0x1800375dc`
- `ncrypt!NCryptOpenKey` at `0x180037337`
- `ncrypt!NCryptOpenKey` at `0x180037337`
- `ncrypt!NCryptOpenStorageProvider` at `0x180037235`
- `ncrypt!NCryptOpenStorageProvider` at `0x180037235`

## string_xrefs

- `0x180037255`: `NCryptOpenStorageProvider`
- `0x18003736e`: `NCryptOpenKey`
- `0x1800373c0`: `NCryptCreatePersistedKey`
- `0x1800371a0`: `LegacyCreateKeyWithRetry`
- `0x18003749c`: `LegacyCreateKeyWithRetry`
- `0x1800372e3`: `ConfigMgrEnrollment`

## pseudocode

```c
__int64 __fastcall LegacyCreateKeyWithRetry(
        const unsigned __int16 *a1,
        const unsigned __int16 *a2,
        int a3,
        unsigned __int8 a4,
        const unsigned __int16 *a5,
        unsigned __int16 *a6,
        unsigned __int64 *a7)
{
  unsigned __int64 *v7; // r15
  unsigned __int16 *v8; // r13
  int v9; // edi
  HANDLE ProcessHeap; // rax
  __int64 v11; // rcx
  SECURITY_STATUS v12; // ebx
  const wchar_t *v13; // r8
  signed int v14; // eax
  __int64 v15; // rcx
  __int64 v16; // r14
  DWORD v17; // r12d
  int v18; // r15d
  SECURITY_STATUS v19; // eax
  unsigned int PersistedKey; // eax
  __int64 v21; // rcx
  __int64 v22; // r8
  SECURITY_STATUS v23; // eax
  LPCWSTR v24; // rcx
  __int64 v25; // rax
  unsigned __int16 *v26; // rcx
  HANDLE v27; // rax
  unsigned int v28; // ebx
  DWORD dwFlags[2]; // [rsp+20h] [rbp-B8h]
  int v31; // [rsp+30h] [rbp-A8h] BYREF
  unsigned int v32; // [rsp+34h] [rbp-A4h]
  LPCWSTR pszKeyName; // [rsp+38h] [rbp-A0h]
  NCRYPT_PROV_HANDLE phProvider; // [rsp+40h] [rbp-98h] BYREF
  BYTE pbInput[8]; // [rsp+48h] [rbp-90h] BYREF
  BYTE v36[8]; // [rsp+50h] [rbp-88h] BYREF
  _QWORD v37[2]; // [rsp+58h] [rbp-80h] BYREF
  NCRYPT_KEY_HANDLE *phKey; // [rsp+68h] [rbp-70h]
  _BYTE v39[16]; // [rsp+70h] [rbp-68h] BYREF
  const unsigned __int16 *v40; // [rsp+80h] [rbp-58h]
  __int64 v41; // [rsp+88h] [rbp-50h]

  v7 = a7;
  v8 = a6;
  v37[0] = "LegacyCreateKeyWithRetry";
  v9 = a4;
  *(_DWORD *)pbInput = a3;
  *a6 = 0;
  *a7 = 0;
  phKey = a7;
  phProvider = 0;
  *(_DWORD *)v36 = 15;
  v37[1] = &v31;
  v31 = 0;
  ProcessHeap = GetProcessHeap();
  pszKeyName = (LPCWSTR)HeapAlloc(ProcessHeap, 8u, 0x200u);
  if ( !pszKeyName )
  {
    v31 = -2147024882;
    goto LABEL_53;
  }
  v12 = NCryptOpenStorageProvider(&phProvider, L"Microsoft Software Key Storage Provider", 0);
  if ( v12 )
  {
    if ( (Microsoft_Windows_DM_Enrollment_ProviderEnableBits & 4) == 0 )
      goto LABEL_7;
    v13 = L"NCryptOpenStorageProvider";
LABEL_6:
    McTemplateU0zq_EventWriteTransfer(v11, FunctionFailedEvent, v13, (unsigned int)v12);
LABEL_7:
    if ( v12 < 0 )
    {
      if ( v12 == -1073741559 )
      {
        v14 = -2147024579;
      }
      else
      {
        v14 = RtlNtStatusToDosError(v12);
        if ( !v14 || v14 == 317 )
        {
          v14 = v12 | 0x10000000;
        }
        else if ( v14 > 0 )
        {
          v14 = (unsigned __int16)v14 | 0x80070000;
        }
      }
    }
    else
    {
      v14 = 0;
    }
    goto LABEL_52;
  }
  LODWORD(v15) = 0;
  v16 = 256;
  v32 = 0;
  v17 = (32 * v9) | 0x40;
  while ( 1 )
  {
    do
    {
      dwFlags[0] = v15;
      v18 = StringCchPrintfW(
              (unsigned __int16 *)pszKeyName,
              0x100u,
              L"%s%d",
              L"ConfigMgrEnrollment",
              *(_QWORD *)dwFlags);
      if ( v18 < 0 )
      {
        EvtTraceScope::~EvtTraceScope((EvtTraceScope *)v37);
        return (unsigned int)v18;
      }
      v7 = phKey;
      if ( *phKey )
        NCryptFreeObject(*phKey);
      v19 = NCryptOpenKey(phProvider, v7, pszKeyName, 0, v17);
      v15 = v32 + 1;
      if ( (unsigned int)v15 < v32 )
      {
        EvtTraceScope::~EvtTraceScope((EvtTraceScope *)v37);
        return 2147942934LL;
      }
      ++v32;
    }
    while ( v19 >= 0 );
    if ( (Microsoft_Windows_DM_Enrollment_ProviderEnableBits & 4) != 0 )
      McTemplateU0zq_EventWriteTransfer(v15, FunctionFailedEvent, L"NCryptOpenKey", (unsigned int)v12);
    PersistedKey = NCryptCreatePersistedKey(phProvider, v7, L"RSA", pszKeyName, 0, v17);
    v12 = PersistedKey;
    if ( !PersistedKey )
      break;
    if ( (Microsoft_Windows_DM_Enrollment_ProviderEnableBits & 4) != 0 )
      McTemplateU0zq_EventWriteTransfer(v21, FunctionFailedEvent, L"NCryptCreatePersistedKey", PersistedKey);
    LODWORD(v15) = v32;
    if ( v12 != -2146893809 )
      goto LABEL_7;
  }
  v12 = NCryptSetProperty(*v7, L"Length", pbInput, 4u, 0);
  if ( v12 )
  {
    if ( (Microsoft_Windows_DM_Enrollment_ProviderEnableBits & 4) == 0 )
      goto LABEL_7;
    v13 = L"NCryptSetProperty#1";
    goto LABEL_6;
  }
  if ( (unsigned int)_o__wcsicmp(L"Microsoft Platform Crypto Provider", L"Microsoft Software Key Storage Provider") )
  {
    v12 = NCryptSetProperty(*v7, L"Export Policy", v36, 4u, 0x80000000);
    if ( v12 )
    {
      if ( (Microsoft_Windows_DM_Enrollment_ProviderEnableBits & 4) == 0 )
        goto LABEL_7;
      v13 = L"NCryptSetProperty#2";
      goto LABEL_6;
    }
  }
  else if ( (Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits & 4) != 0 )
  {
    v41 = 50;
    v40 = L"LegacyCreateKeyWithRetry";
    McGenEventWrite_EventWriteTransfer(
      &MDM_ENTERPRISE_DIAGNOSTICS_Context,
      EnterpriseDiagnosticsTPMSkipExportPrivateKey,
      v22,
      2,
      v39);
  }
  if ( (Microsoft_Windows_DM_Enrollment_ProviderEnableBits & 1) != 0 )
    McTemplateU0s_EventWriteTransfer(v11, EnteringScopeEvent, "NCryptFinalizeKey");
  v23 = NCryptFinalizeKey(*v7, 0);
  v11 = (unsigned int)Microsoft_Windows_DM_Enrollment_ProviderEnableBits;
  v12 = v23;
  if ( (Microsoft_Windows_DM_Enrollment_ProviderEnableBits & 1) != 0 )
  {
    McTemplateU0s_EventWriteTransfer(
      (unsigned int)Microsoft_Windows_DM_Enrollment_ProviderEnableBits,
      LeavingScopeEvent,
      "NCryptFinalizeKey");
    v11 = (unsigned int)Microsoft_Windows_DM_Enrollment_ProviderEnableBits;
  }
  if ( v12 )
  {
    if ( (v11 & 4) == 0 )
      goto LABEL_7;
    v13 = L"NCryptFinalizeKey";
    goto LABEL_6;
  }
  v24 = pszKeyName;
  v25 = 2147483646;
  do
  {
    if ( !v25 )
      break;
    if ( !*v24 )
      break;
    *v8++ = *v24++;
    --v25;
    --v16;
  }
  while ( v16 );
  v26 = v8 - 1;
  if ( v16 )
    v26 = v8;
  v14 = v16 == 0 ? 0x8007007A : 0;
  *v26 = 0;
LABEL_52:
  v31 = v14;
  v27 = GetProcessHeap();
  HeapFree(v27, 0, (LPVOID)pszKeyName);
  if ( v31 < 0 )
  {
LABEL_53:
    if ( *v7 )
    {
      NCryptFreeObject(*v7);
      *v7 = 0;
    }
  }
  if ( phProvider )
  {
    NCryptFreeObject(phProvider);
    phProvider = 0;
  }
  v28 = v31;
  EvtTraceScope::~EvtTraceScope((EvtTraceScope *)v37);
  return v28;
}

```

## disassembly

```asm
0x180037174  push    rbx
0x180037176  push    rdi
0x180037177  push    r12
0x180037179  push    r13
0x18003717b  push    r14
0x18003717d  push    r15
0x18003717f  sub     rsp, 0A8h
0x180037186  mov     rax, cs:__security_cookie
0x18003718d  xor     rax, rsp
0x180037190  mov     [rsp+0D8h+var_48], rax
0x180037198  mov     r15, [rsp+0D8h+arg_30]
0x1800371a0  lea     rax, aLegacycreateke_0; "LegacyCreateKeyWithRetry"
0x1800371a7  mov     r13, [rsp+0D8h+arg_28]
0x1800371af  xor     r12d, r12d
0x1800371b2  mov     [rsp+0D8h+var_80], rax
0x1800371b7  lea     rax, [rsp+0D8h+var_A8]
0x1800371bc  movzx   edi, r9b
0x1800371c0  mov     dword ptr [rsp+0D8h+pbInput], r8d
0x1800371c5  mov     [r13+0], r12w
0x1800371ca  mov     [r15], r12
0x1800371cd  mov     [rsp+0D8h+phKey], r15
0x1800371d2  mov     [rsp+0D8h+phProvider], r12
0x1800371d7  mov     dword ptr [rsp+0D8h+var_88], 0Fh
0x1800371df  mov     [rsp+0D8h+var_78], rax
0x1800371e4  mov     [rsp+0D8h+var_A8], r12d
0x1800371e9  call    cs:__imp_GetProcessHeap
0x1800371f0  nop     dword ptr [rax+rax+00h]
0x1800371f5  lea     edx, [r12+8]; dwFlags
0x1800371fa  mov     r8d, 200h; dwBytes
0x180037200  mov     rcx, rax; hHeap
0x180037203  call    cs:__imp_HeapAlloc
0x18003720a  nop     dword ptr [rax+rax+00h]
0x18003720f  mov     [rsp+0D8h+pszKeyName], rax
0x180037214  test    rax, rax
0x180037217  jnz     short loc_180037226
0x180037219  mov     [rsp+0D8h+var_A8], 8007000Eh
0x180037221  jmp     loc_1800375BB
0x180037226  xor     r8d, r8d; dwFlags
0x180037229  lea     rdx, pszProviderName; "Microsoft Software Key Storage Provider"
0x180037230  lea     rcx, [rsp+0D8h+phProvider]; phProvider
0x180037235  call    cs:__imp_NCryptOpenStorageProvider
0x18003723c  nop     dword ptr [rax+rax+00h]
0x180037241  mov     ebx, eax
0x180037243  test    eax, eax
0x180037245  jz      short loc_1800372C2
0x180037247  mov     edi, 4
0x18003724c  test    byte ptr cs:Microsoft_Windows_DM_Enrollment_ProviderEnableBits, dil
0x180037253  jz      short loc_18003726B
0x180037255  lea     r8, aNcryptopenstor_0; "NCryptOpenStorageProvider"
0x18003725c  mov     r9d, ebx
0x18003725f  lea     rdx, FunctionFailedEvent
0x180037266  call    McTemplateU0zq_EventWriteTransfer
0x18003726b  test    ebx, ebx
0x18003726d  js      short loc_180037277
0x18003726f  mov     eax, r12d
0x180037272  jmp     loc_18003758E
0x180037277  cmp     ebx, 0C0000109h
0x18003727d  jnz     short loc_180037289
0x18003727f  mov     eax, 8007013Dh
0x180037284  jmp     loc_18003758E
0x180037289  mov     ecx, ebx; Status
0x18003728b  call    cs:__imp_RtlNtStatusToDosError
0x180037292  nop     dword ptr [rax+rax+00h]
0x180037297  test    eax, eax
0x180037299  jz      short loc_1800372B7
0x18003729b  cmp     eax, 13Dh
0x1800372a0  jz      short loc_1800372B7
0x1800372a2  test    eax, eax
0x1800372a4  jle     loc_18003758E
0x1800372aa  movzx   eax, ax
0x1800372ad  or      eax, 80070000h
0x1800372b2  jmp     loc_18003758E
0x1800372b7  mov     eax, ebx
0x1800372b9  bts     eax, 1Ch
0x1800372bd  jmp     loc_18003758E
0x1800372c2  mov     ecx, r12d
0x1800372c5  mov     r14d, 100h
0x1800372cb  mov     r12d, edi
0x1800372ce  mov     [rsp+0D8h+var_A4], ecx
0x1800372d2  shl     r12d, 5
0x1800372d6  mov     edi, 4
0x1800372db  or      r12d, 40h
0x1800372df  mov     [rsp+0D8h+dwFlags], ecx
0x1800372e3  lea     r9, aConfigmgrenrol; "ConfigMgrEnrollment"
0x1800372ea  mov     rcx, [rsp+0D8h+pszKeyName]; unsigned __int16 *
0x1800372ef  lea     r8, aSD; "%s%d"
0x1800372f6  mov     rdx, r14; unsigned __int64
0x1800372f9  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800372fe  mov     r15d, eax
0x180037301  test    eax, eax
0x180037303  js      loc_180037610
0x180037309  mov     r15, [rsp+0D8h+phKey]
0x18003730e  mov     rcx, [r15]; hObject
0x180037311  test    rcx, rcx
0x180037314  jz      short loc_180037322
0x180037316  call    cs:__imp_NCryptFreeObject
0x18003731d  nop     dword ptr [rax+rax+00h]
0x180037322  mov     r8, [rsp+0D8h+pszKeyName]; pszKeyName
0x180037327  xor     r9d, r9d; dwLegacyKeySpec
0x18003732a  mov     rcx, [rsp+0D8h+phProvider]; hProvider
0x18003732f  mov     rdx, r15; phKey
0x180037332  mov     [rsp+0D8h+dwFlags], r12d; dwFlags
0x180037337  call    cs:__imp_NCryptOpenKey
0x18003733e  nop     dword ptr [rax+rax+00h]
0x180037343  mov     edx, [rsp+0D8h+var_A4]
0x180037347  lea     ecx, [rdx+1]
0x18003734a  cmp     ecx, edx
0x18003734c  jb      loc_1800375FF
0x180037352  mov     [rsp+0D8h+var_A4], ecx
0x180037356  test    eax, eax
0x180037358  jns     short loc_1800372DF
0x18003735a  cmp     ebx, 80090016h
0x180037360  jz      short loc_180037381
0x180037362  test    byte ptr cs:Microsoft_Windows_DM_Enrollment_ProviderEnableBits, dil
0x180037369  jz      short loc_180037381
0x18003736b  mov     r9d, ebx
0x18003736e  lea     r8, aNcryptopenkey_0; "NCryptOpenKey"
0x180037375  lea     rdx, FunctionFailedEvent
0x18003737c  call    McTemplateU0zq_EventWriteTransfer
0x180037381  mov     r9, [rsp+0D8h+pszKeyName]; pszKeyName
0x180037386  lea     r8, pszAlgId; "RSA"
0x18003738d  mov     rcx, [rsp+0D8h+phProvider]; hProvider
0x180037392  mov     rdx, r15; phKey
0x180037395  mov     [rsp+0D8h+var_B0], r12d; dwFlags
0x18003739a  mov     [rsp+0D8h+dwFlags], 0; dwLegacyKeySpec
0x1800373a2  call    cs:__imp_NCryptCreatePersistedKey
0x1800373a9  nop     dword ptr [rax+rax+00h]
0x1800373ae  mov     ebx, eax
0x1800373b0  test    eax, eax
0x1800373b2  jz      short loc_1800373EB
0x1800373b4  test    byte ptr cs:Microsoft_Windows_DM_Enrollment_ProviderEnableBits, dil
0x1800373bb  jz      short loc_1800373D3
0x1800373bd  mov     r9d, eax
0x1800373c0  lea     r8, aNcryptcreatepe_0; "NCryptCreatePersistedKey"
0x1800373c7  lea     rdx, FunctionFailedEvent
0x1800373ce  call    McTemplateU0zq_EventWriteTransfer
0x1800373d3  mov     ecx, [rsp+0D8h+var_A4]
0x1800373d7  cmp     ebx, 8009000Fh
0x1800373dd  jz      loc_1800372DF
0x1800373e3  xor     r12d, r12d
0x1800373e6  jmp     loc_18003726B
0x1800373eb  mov     rcx, [r15]; hObject
0x1800373ee  lea     r8, [rsp+0D8h+pbInput]; pbInput
0x1800373f3  xor     r12d, r12d
0x1800373f6  lea     rdx, aLength; "Length"
0x1800373fd  mov     r9d, edi; cbInput
0x180037400  mov     [rsp+0D8h+dwFlags], r12d; dwFlags
0x180037405  call    cs:__imp_NCryptSetProperty
0x18003740c  nop     dword ptr [rax+rax+00h]
0x180037411  mov     ebx, eax
0x180037413  test    eax, eax
0x180037415  jz      short loc_180037430
0x180037417  test    byte ptr cs:Microsoft_Windows_DM_Enrollment_ProviderEnableBits, dil
0x18003741e  jz      loc_18003726B
0x180037424  lea     r8, aNcryptsetprope_1; "NCryptSetProperty#1"
0x18003742b  jmp     loc_18003725C
0x180037430  lea     rdx, pszProviderName; "Microsoft Software Key Storage Provider"
0x180037437  lea     rcx, aMicrosoftPlatf; "Microsoft Platform Crypto Provider"
0x18003743e  call    cs:__imp__o__wcsicmp
0x180037445  nop     dword ptr [rax+rax+00h]
0x18003744a  test    eax, eax
0x18003744c  jz      short loc_180037493
0x18003744e  mov     rcx, [r15]; hObject
0x180037451  lea     r8, [rsp+0D8h+var_88]; pbInput
0x180037456  mov     r9d, edi; cbInput
0x180037459  mov     [rsp+0D8h+dwFlags], 80000000h; dwFlags
0x180037461  lea     rdx, aExportPolicy; "Export Policy"
0x180037468  call    cs:__imp_NCryptSetProperty
0x18003746f  nop     dword ptr [rax+rax+00h]
0x180037474  mov     ebx, eax
0x180037476  test    eax, eax
0x180037478  jz      short loc_1800374DA
0x18003747a  test    byte ptr cs:Microsoft_Windows_DM_Enrollment_ProviderEnableBits, dil
0x180037481  jz      loc_18003726B
0x180037487  lea     r8, aNcryptsetprope_0; "NCryptSetProperty#2"
0x18003748e  jmp     loc_18003725C
0x180037493  test    cs:Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits, dil
0x18003749a  jz      short loc_1800374DA
0x18003749c  lea     rax, aLegacycreateke; "LegacyCreateKeyWithRetry"
0x1800374a3  mov     [rsp+0D8h+var_50], 32h ; '2'
0x1800374af  mov     [rsp+0D8h+var_58], rax
0x1800374b7  lea     rdx, EnterpriseDiagnosticsTPMSkipExportPrivateKey
0x1800374be  lea     rax, [rsp+0D8h+var_68]
0x1800374c3  mov     r9d, 2
0x1800374c9  lea     rcx, MDM_ENTERPRISE_DIAGNOSTICS_Context
0x1800374d0  mov     qword ptr [rsp+0D8h+dwFlags], rax
0x1800374d5  call    McGenEventWrite_EventWriteTransfer
0x1800374da  test    byte ptr cs:Microsoft_Windows_DM_Enrollment_ProviderEnableBits, 1
0x1800374e1  jz      short loc_1800374F6
0x1800374e3  lea     r8, aNcryptfinalize_1; "NCryptFinalizeKey"
0x1800374ea  lea     rdx, EnteringScopeEvent
0x1800374f1  call    McTemplateU0s_EventWriteTransfer
0x1800374f6  mov     rcx, [r15]; hKey
0x1800374f9  xor     edx, edx; dwFlags
0x1800374fb  call    cs:__imp_NCryptFinalizeKey
0x180037502  nop     dword ptr [rax+rax+00h]
0x180037507  mov     ecx, cs:Microsoft_Windows_DM_Enrollment_ProviderEnableBits
0x18003750d  mov     ebx, eax
0x18003750f  test    cl, 1
0x180037512  jz      short loc_18003752D
0x180037514  lea     r8, aNcryptfinalize_1; "NCryptFinalizeKey"
0x18003751b  lea     rdx, LeavingScopeEvent
0x180037522  call    McTemplateU0s_EventWriteTransfer
0x180037527  mov     ecx, cs:Microsoft_Windows_DM_Enrollment_ProviderEnableBits
0x18003752d  test    ebx, ebx
0x18003752f  jz      short loc_180037546
0x180037531  test    dil, cl
0x180037534  jz      loc_18003726B
0x18003753a  lea     r8, aNcryptfinalize_0; "NCryptFinalizeKey"
0x180037541  jmp     loc_18003725C
0x180037546  mov     rcx, [rsp+0D8h+pszKeyName]
0x18003754b  mov     eax, 7FFFFFFEh
0x180037550  test    rax, rax
0x180037553  jz      short loc_180037573
0x180037555  movzx   edx, word ptr [rcx]
0x180037558  test    dx, dx
0x18003755b  jz      short loc_180037573
0x18003755d  mov     [r13+0], dx
0x180037562  add     rcx, 2
0x180037566  add     r13, 2
0x18003756a  dec     rax
0x18003756d  sub     r14, 1
0x180037571  jnz     short loc_180037550
0x180037573  test    r14, r14
0x180037576  lea     rcx, [r13-2]
0x18003757a  cmovnz  rcx, r13
0x18003757e  neg     r14
0x180037581  sbb     eax, eax
0x180037583  not     eax
0x180037585  and     eax, 8007007Ah
0x18003758a  mov     [rcx], r12w
0x18003758e  mov     [rsp+0D8h+var_A8], eax
0x180037592  call    cs:__imp_GetProcessHeap
0x180037599  nop     dword ptr [rax+rax+00h]
0x18003759e  mov     r8, [rsp+0D8h+pszKeyName]; lpMem
0x1800375a3  xor     edx, edx; dwFlags
0x1800375a5  mov     rcx, rax; hHeap
0x1800375a8  call    cs:__imp_HeapFree
0x1800375af  nop     dword ptr [rax+rax+00h]
0x1800375b4  cmp     [rsp+0D8h+var_A8], r12d
0x1800375b9  jge     short loc_1800375D2
0x1800375bb  mov     rcx, [r15]; hObject
0x1800375be  test    rcx, rcx
0x1800375c1  jz      short loc_1800375D2
0x1800375c3  call    cs:__imp_NCryptFreeObject
0x1800375ca  nop     dword ptr [rax+rax+00h]
0x1800375cf  mov     [r15], r12
0x1800375d2  mov     rcx, [rsp+0D8h+phProvider]; hObject
0x1800375d7  test    rcx, rcx
0x1800375da  jz      short loc_1800375ED
0x1800375dc  call    cs:__imp_NCryptFreeObject
0x1800375e3  nop     dword ptr [rax+rax+00h]
0x1800375e8  mov     [rsp+0D8h+phProvider], r12
0x1800375ed  mov     ebx, [rsp+0D8h+var_A8]
0x1800375f1  lea     rcx, [rsp+0D8h+var_80]; this
0x1800375f6  call    ??1EvtTraceScope@@QEAA@XZ; EvtTraceScope::~EvtTraceScope(void)
0x1800375fb  mov     eax, ebx
0x1800375fd  jmp     short loc_18003761D
0x1800375ff  lea     rcx, [rsp+0D8h+var_80]; this
0x180037604  call    ??1EvtTraceScope@@QEAA@XZ; EvtTraceScope::~EvtTraceScope(void)
0x180037609  mov     eax, 80070216h
0x18003760e  jmp     short loc_18003761D
0x180037610  lea     rcx, [rsp+0D8h+var_80]; this
0x180037615  call    ??1EvtTraceScope@@QEAA@XZ; EvtTraceScope::~EvtTraceScope(void)
0x18003761a  mov     eax, r15d
0x18003761d  mov     rcx, [rsp+0D8h+var_48]
0x180037625  xor     rcx, rsp; StackCookie
0x180037628  call    __security_check_cookie
0x18003762d  add     rsp, 0A8h
0x180037634  pop     r15
0x180037636  pop     r14
0x180037638  pop     r13
0x18003763a  pop     r12
0x18003763c  pop     rdi
0x18003763d  pop     rbx
0x18003763e  retn
```
