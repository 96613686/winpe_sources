# LegacyCreateKeyWithRetry(ushort const *,ushort const *,ulong,bool,ushort const *,ushort *,unsigned __int64 *)

- ea: `0x1800132ec`
- end: `0x180013673`
- name: `?LegacyCreateKeyWithRetry@@YAJPEBG0K_N0PEAGPEA_K@Z`
- size: `903`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *, unsigned int, bool, NCRYPT_HANDLE hObject, unsigned __int16 *, NCRYPT_KEY_HANDLE *phKey)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18001b3ac`

## callees

- `0x1800067a0`
- `0x180007040`
- `0x18000dd20`
- `0x1800128c4`
- `0x1800132ec`
- `0x1800140d0`
- `0x180014148`
- `0x1800206a8`
- `0x18003b170`
- `0x18003dba8`
- `0x18004e314`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800135a8`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800135a8`
- `ntdll!RtlNtStatusToDosError` at `0x180013426`
- `ntdll!RtlNtStatusToDosError` at `0x180013426`
- `ncrypt!NCryptFinalizeKey` at `0x180013625`
- `ncrypt!NCryptFinalizeKey` at `0x180013625`
- `ncrypt!NCryptSetProperty` at `0x180013576`
- `ncrypt!NCryptSetProperty` at `0x1800135cb`
- `ncrypt!NCryptSetProperty` at `0x180013576`
- `ncrypt!NCryptSetProperty` at `0x1800135cb`
- `ncrypt!NCryptFreeObject` at `0x18001338e`
- `ncrypt!NCryptFreeObject` at `0x1800133a0`
- `ncrypt!NCryptFreeObject` at `0x1800134a3`
- `ncrypt!NCryptFreeObject` at `0x18001338e`
- `ncrypt!NCryptFreeObject` at `0x1800133a0`
- `ncrypt!NCryptFreeObject` at `0x1800134a3`
- `ncrypt!NCryptOpenKey` at `0x1800134bf`
- `ncrypt!NCryptOpenKey` at `0x1800134bf`
- `ncrypt!NCryptCreatePersistedKey` at `0x18001351a`
- `ncrypt!NCryptCreatePersistedKey` at `0x18001351a`
- `ncrypt!NCryptOpenStorageProvider` at `0x1800133d7`
- `ncrypt!NCryptOpenStorageProvider` at `0x1800133d7`

## string_xrefs

- `0x1800134ed`: `NCryptOpenKey`
- `0x1800133f5`: `NCryptOpenStorageProvider`
- `0x180013532`: `NCryptCreatePersistedKey`
- `0x180013312`: `LegacyCreateKeyWithRetry`
- `0x1800135f6`: `LegacyCreateKeyWithRetry`
- `0x180013471`: `ConfigMgrEnrollment`

## pseudocode

```c
__int64 __fastcall LegacyCreateKeyWithRetry(
        const unsigned __int16 *a1,
        const unsigned __int16 *a2,
        int a3,
        unsigned __int8 a4,
        NCRYPT_HANDLE hObject,
        unsigned __int16 *a6,
        NCRYPT_KEY_HANDLE *phKey)
{
  NCRYPT_KEY_HANDLE *v7; // r15
  int v8; // edi
  __int64 v9; // rdx
  int v10; // esi
  __int64 v12; // rcx
  SECURITY_STATUS v13; // ebx
  const wchar_t *v14; // r8
  int v15; // eax
  unsigned __int16 *v16; // rsi
  unsigned int v17; // r13d
  DWORD v18; // r12d
  SECURITY_STATUS v19; // eax
  __int64 v20; // rcx
  unsigned int PersistedKey; // eax
  __int64 v22; // rcx
  __int64 dwFlags; // [rsp+20h] [rbp-38h]
  WCHAR *pszKeyName; // [rsp+30h] [rbp-28h]
  _QWORD v25[4]; // [rsp+38h] [rbp-20h] BYREF
  int v26; // [rsp+A0h] [rbp+48h] BYREF
  int v27; // [rsp+A4h] [rbp+4Ch]
  unsigned int v28; // [rsp+A8h] [rbp+50h] BYREF
  int v29; // [rsp+ACh] [rbp+54h]
  int pbInput; // [rsp+B0h] [rbp+58h] BYREF
  int v31; // [rsp+B8h] [rbp+60h] BYREF

  pbInput = a3;
  v29 = HIDWORD(a2);
  v27 = HIDWORD(a1);
  v7 = phKey;
  v25[0] = "LegacyCreateKeyWithRetry";
  v8 = a4;
  *a6 = 0;
  hObject = 0;
  pszKeyName = 0;
  v28 = 0;
  v26 = 15;
  v25[1] = &v31;
  *v7 = 0;
  v31 = ULongLongToULong(0x200u, &v28);
  if ( v31 < 0 )
    goto LABEL_4;
  pszKeyName = (WCHAR *)SafeHeapAlloc(v28);
  if ( !pszKeyName )
  {
    v31 = -2147024882;
LABEL_4:
    SafeHeapFree(pszKeyName);
    if ( v31 < 0 && *v7 )
    {
      NCryptFreeObject(*v7);
      *v7 = 0;
    }
    if ( hObject )
    {
      NCryptFreeObject(hObject);
      hObject = 0;
    }
    v10 = v31;
    goto LABEL_10;
  }
  v13 = NCryptOpenStorageProvider(&hObject, L"Microsoft Software Key Storage Provider", 0);
  if ( v13 )
  {
    if ( (Microsoft_Windows_DM_Enrollment_ProviderEnableBits & 4) != 0 )
    {
      v14 = L"NCryptOpenStorageProvider";
LABEL_14:
      McTemplateU0zq_EventWriteTransfer(v12, FunctionFailedEvent, v14, (unsigned int)v13);
    }
LABEL_36:
    if ( v13 >= 0 )
    {
      v15 = 0;
    }
    else if ( v13 == -1073741559 )
    {
      v15 = -2147024579;
    }
    else
    {
      v15 = RtlNtStatusToDosError(v13);
      if ( !v15 || v15 == 317 )
      {
        v15 = v13 | 0x10000000;
      }
      else if ( v15 > 0 )
      {
        v15 = (unsigned __int16)v15 | 0x80070000;
      }
    }
LABEL_23:
    v31 = v15;
    goto LABEL_4;
  }
  v16 = pszKeyName;
  v17 = 0;
  v18 = (32 * v8) | 0x40;
  while ( 1 )
  {
    LODWORD(dwFlags) = v17;
    v10 = StringCchPrintfW(v16, 0x100u, L"%s%d", L"ConfigMgrEnrollment", dwFlags);
    if ( v10 < 0 )
      break;
    if ( *v7 )
      NCryptFreeObject(*v7);
    v16 = pszKeyName;
    v19 = NCryptOpenKey(hObject, v7, pszKeyName, 0, v18);
    v20 = v17 + 1;
    if ( (unsigned int)v20 < v17 )
    {
      v10 = -2147024362;
      break;
    }
    ++v17;
    if ( v19 < 0 )
    {
      if ( (Microsoft_Windows_DM_Enrollment_ProviderEnableBits & 4) != 0 )
        McTemplateU0zq_EventWriteTransfer(v20, FunctionFailedEvent, L"NCryptOpenKey", (unsigned int)v13);
      PersistedKey = NCryptCreatePersistedKey(hObject, v7, L"RSA", pszKeyName, 0, v18);
      v13 = PersistedKey;
      if ( !PersistedKey )
      {
        v13 = NCryptSetProperty(*v7, L"Length", (PBYTE)&pbInput, 4u, 0);
        if ( v13 )
        {
          if ( (Microsoft_Windows_DM_Enrollment_ProviderEnableBits & 4) == 0 )
            goto LABEL_36;
          v14 = L"NCryptSetProperty#1";
          goto LABEL_14;
        }
        if ( (unsigned int)_o__wcsicmp(
                             L"Microsoft Platform Crypto Provider",
                             L"Microsoft Software Key Storage Provider") )
        {
          v13 = NCryptSetProperty(*v7, L"Export Policy", (PBYTE)&v26, 4u, 0x80000000);
          if ( v13 )
          {
            if ( (Microsoft_Windows_DM_Enrollment_ProviderEnableBits & 4) == 0 )
              goto LABEL_36;
            v14 = L"NCryptSetProperty#2";
            goto LABEL_14;
          }
        }
        else if ( (Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits & 4) != 0 )
        {
          McTemplateU0z_EventWriteTransfer(
            MDM_ENTERPRISE_DIAGNOSTICS_Context,
            EnterpriseDiagnosticsTPMSkipExportPrivateKey,
            L"LegacyCreateKeyWithRetry");
        }
        EvtPerfTraceScope::EvtPerfTraceScope((EvtPerfTraceScope *)&v28, "NCryptFinalizeKey");
        v13 = NCryptFinalizeKey(*v7, 0);
        EvtPerfTraceScope::~EvtPerfTraceScope((EvtPerfTraceScope *)&v28);
        if ( !v13 )
        {
          v15 = StringCchCopyW(a6, 0x100u, pszKeyName);
          goto LABEL_23;
        }
        if ( (Microsoft_Windows_DM_Enrollment_ProviderEnableBits & 4) == 0 )
          goto LABEL_36;
        v14 = L"NCryptFinalizeKey";
        goto LABEL_14;
      }
      if ( (Microsoft_Windows_DM_Enrollment_ProviderEnableBits & 4) != 0 )
        McTemplateU0zq_EventWriteTransfer(v22, FunctionFailedEvent, L"NCryptCreatePersistedKey", PersistedKey);
      if ( v13 != -2146893809 )
        goto LABEL_36;
    }
  }
LABEL_10:
  EvtTraceScope::~EvtTraceScope((EvtTraceScope *)v25, v9);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x1800132ec  mov     [rsp-40h+pbInput], r8d
0x1800132f1  mov     qword ptr [rsp-40h+arg_8], rdx
0x1800132f6  mov     qword ptr [rsp-40h+arg_0], rcx
0x1800132fb  push    rbp
0x1800132fc  push    rbx
0x1800132fd  push    rsi
0x1800132fe  push    rdi
0x1800132ff  push    r12
0x180013301  push    r13
0x180013303  push    r14
0x180013305  push    r15
0x180013307  mov     rbp, rsp
0x18001330a  sub     rsp, 58h
0x18001330e  mov     rcx, [rbp+arg_28]
0x180013312  lea     rax, aLegacycreateke_0; "LegacyCreateKeyWithRetry"
0x180013319  mov     r15, [rbp+phKey]
0x18001331d  lea     rdx, [rbp+arg_8]; unsigned int *
0x180013321  xor     r12d, r12d
0x180013324  mov     [rbp+var_20], rax
0x180013328  lea     rax, [rbp+arg_18]
0x18001332c  movzx   edi, r9b
0x180013330  mov     [rcx], r12w
0x180013334  mov     ecx, 200h; unsigned __int64
0x180013339  mov     [rbp+hObject], r12
0x18001333d  mov     [rbp+pszKeyName], r12
0x180013341  mov     [rbp+arg_8], r12d
0x180013345  mov     [rbp+arg_0], 0Fh
0x18001334c  mov     [rbp+var_18], rax
0x180013350  mov     [r15], r12
0x180013353  call    ?ULongLongToULong@@YAJ_KPEAK@Z; ULongLongToULong(unsigned __int64,ulong *)
0x180013358  mov     [rbp+arg_18], eax
0x18001335b  test    eax, eax
0x18001335d  js      short loc_180013377
0x18001335f  mov     ecx, [rbp+arg_8]; unsigned __int64
0x180013362  call    ?SafeHeapAlloc@@YAPEAX_K@Z; SafeHeapAlloc(unsigned __int64)
0x180013367  mov     [rbp+pszKeyName], rax
0x18001336b  test    rax, rax
0x18001336e  jnz     short loc_1800133C9
0x180013370  mov     [rbp+arg_18], 8007000Eh
0x180013377  mov     rcx, [rbp+pszKeyName]; void *
0x18001337b  call    ?SafeHeapFree@@YAHPEAX@Z; SafeHeapFree(void *)
0x180013380  cmp     [rbp+arg_18], r12d
0x180013384  jge     short loc_180013397
0x180013386  mov     rcx, [r15]; hObject
0x180013389  test    rcx, rcx
0x18001338c  jz      short loc_180013397
0x18001338e  call    cs:__imp_NCryptFreeObject
0x180013394  mov     [r15], r12
0x180013397  mov     rcx, [rbp+hObject]; hObject
0x18001339b  test    rcx, rcx
0x18001339e  jz      short loc_1800133AA
0x1800133a0  call    cs:__imp_NCryptFreeObject
0x1800133a6  mov     [rbp+hObject], r12
0x1800133aa  mov     esi, [rbp+arg_18]
0x1800133ad  lea     rcx, [rbp+var_20]; this
0x1800133b1  call    ??1EvtTraceScope@@QEAA@XZ; EvtTraceScope::~EvtTraceScope(void)
0x1800133b6  mov     eax, esi
0x1800133b8  add     rsp, 58h
0x1800133bc  pop     r15
0x1800133be  pop     r14
0x1800133c0  pop     r13
0x1800133c2  pop     r12
0x1800133c4  pop     rdi
0x1800133c5  pop     rsi
0x1800133c6  pop     rbx
0x1800133c7  pop     rbp
0x1800133c8  retn
0x1800133c9  xor     r8d, r8d; dwFlags
0x1800133cc  lea     rdx, pszProviderName; "Microsoft Software Key Storage Provider"
0x1800133d3  lea     rcx, [rbp+hObject]; phProvider
0x1800133d7  call    cs:__imp_NCryptOpenStorageProvider
0x1800133dd  mov     ebx, eax
0x1800133df  test    eax, eax
0x1800133e1  jz      short loc_180013453
0x1800133e3  mov     edi, 4
0x1800133e8  test    byte ptr cs:Microsoft_Windows_DM_Enrollment_ProviderEnableBits, dil
0x1800133ef  jz      loc_180013550
0x1800133f5  lea     r8, aNcryptopenstor_0; "NCryptOpenStorageProvider"
0x1800133fc  lea     rdx, FunctionFailedEvent
0x180013403  mov     r9d, ebx
0x180013406  call    McTemplateU0zq_EventWriteTransfer
0x18001340b  jmp     loc_180013550
0x180013410  mov     eax, r12d
0x180013413  jmp     short loc_18001344B
0x180013415  cmp     ebx, 0C0000109h
0x18001341b  jnz     short loc_180013424
0x18001341d  mov     eax, 8007013Dh
0x180013422  jmp     short loc_18001344B
0x180013424  mov     ecx, ebx; Status
0x180013426  call    cs:__imp_RtlNtStatusToDosError
0x18001342c  test    eax, eax
0x18001342e  jz      short loc_180013445
0x180013430  cmp     eax, 13Dh
0x180013435  jz      short loc_180013445
0x180013437  test    eax, eax
0x180013439  jle     short loc_18001344B
0x18001343b  movzx   eax, ax
0x18001343e  or      eax, 80070000h
0x180013443  jmp     short loc_18001344B
0x180013445  mov     eax, ebx
0x180013447  bts     eax, 1Ch
0x18001344b  mov     [rbp+arg_18], eax
0x18001344e  jmp     loc_180013377
0x180013453  mov     rsi, [rbp+pszKeyName]
0x180013457  lea     r14, FunctionFailedEvent
0x18001345e  mov     r13d, r12d
0x180013461  mov     r12d, edi
0x180013464  shl     r12d, 5
0x180013468  mov     edi, 4
0x18001346d  or      r12d, 40h
0x180013471  lea     r9, aConfigmgrenrol; "ConfigMgrEnrollment"
0x180013478  mov     dword ptr [rsp+58h+dwFlags], r13d
0x18001347d  lea     r8, aSD; "%s%d"
0x180013484  mov     edx, 100h; unsigned __int64
0x180013489  mov     rcx, rsi; unsigned __int16 *
0x18001348c  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180013491  mov     esi, eax
0x180013493  test    eax, eax
0x180013495  js      loc_1800133AD
0x18001349b  mov     rcx, [r15]; hObject
0x18001349e  test    rcx, rcx
0x1800134a1  jz      short loc_1800134A9
0x1800134a3  call    cs:__imp_NCryptFreeObject
0x1800134a9  mov     rsi, [rbp+pszKeyName]
0x1800134ad  xor     r9d, r9d; dwLegacyKeySpec
0x1800134b0  mov     rcx, [rbp+hObject]; hProvider
0x1800134b4  mov     r8, rsi; pszKeyName
0x1800134b7  mov     rdx, r15; phKey
0x1800134ba  mov     dword ptr [rsp+58h+dwFlags], r12d; dwFlags
0x1800134bf  call    cs:__imp_NCryptOpenKey
0x1800134c5  lea     ecx, [r13+1]
0x1800134c9  cmp     ecx, r13d
0x1800134cc  jb      loc_180013669
0x1800134d2  mov     r13d, ecx
0x1800134d5  test    eax, eax
0x1800134d7  jns     short loc_180013471
0x1800134d9  cmp     ebx, 80090016h
0x1800134df  jz      short loc_1800134FC
0x1800134e1  test    byte ptr cs:Microsoft_Windows_DM_Enrollment_ProviderEnableBits, dil
0x1800134e8  jz      short loc_1800134FC
0x1800134ea  mov     r9d, ebx
0x1800134ed  lea     r8, aNcryptopenkey_0; "NCryptOpenKey"
0x1800134f4  mov     rdx, r14
0x1800134f7  call    McTemplateU0zq_EventWriteTransfer
0x1800134fc  mov     rcx, [rbp+hObject]; hProvider
0x180013500  lea     r8, pszAlgId; "RSA"
0x180013507  mov     [rsp+58h+var_30], r12d; dwFlags
0x18001350c  mov     r9, rsi; pszKeyName
0x18001350f  mov     rdx, r15; phKey
0x180013512  mov     dword ptr [rsp+58h+dwFlags], 0; dwLegacyKeySpec
0x18001351a  call    cs:__imp_NCryptCreatePersistedKey
0x180013520  mov     ebx, eax
0x180013522  test    eax, eax
0x180013524  jz      short loc_18001355D
0x180013526  test    byte ptr cs:Microsoft_Windows_DM_Enrollment_ProviderEnableBits, dil
0x18001352d  jz      short loc_180013541
0x18001352f  mov     r9d, eax
0x180013532  lea     r8, aNcryptcreatepe_0; "NCryptCreatePersistedKey"
0x180013539  mov     rdx, r14
0x18001353c  call    McTemplateU0zq_EventWriteTransfer
0x180013541  cmp     ebx, 8009000Fh
0x180013547  jz      loc_180013471
0x18001354d  xor     r12d, r12d
0x180013550  test    ebx, ebx
0x180013552  jns     loc_180013410
0x180013558  jmp     loc_180013415
0x18001355d  mov     rcx, [r15]; hObject
0x180013560  lea     r8, [rbp+pbInput]; pbInput
0x180013564  xor     r12d, r12d
0x180013567  lea     rdx, pszProperty; "Length"
0x18001356e  mov     r9d, edi; cbInput
0x180013571  mov     dword ptr [rsp+58h+dwFlags], r12d; dwFlags
0x180013576  call    cs:__imp_NCryptSetProperty
0x18001357c  mov     ebx, eax
0x18001357e  test    eax, eax
0x180013580  jz      short loc_18001359A
0x180013582  test    byte ptr cs:Microsoft_Windows_DM_Enrollment_ProviderEnableBits, dil
0x180013589  jz      short loc_180013550
0x18001358b  lea     r8, aNcryptsetprope_1; "NCryptSetProperty#1"
0x180013592  mov     rdx, r14
0x180013595  jmp     loc_180013403
0x18001359a  lea     rdx, pszProviderName; "Microsoft Software Key Storage Provider"
0x1800135a1  lea     rcx, aMicrosoftPlatf; "Microsoft Platform Crypto Provider"
0x1800135a8  call    cs:__imp__o__wcsicmp
0x1800135ae  test    eax, eax
0x1800135b0  jz      short loc_1800135ED
0x1800135b2  mov     rcx, [r15]; hObject
0x1800135b5  lea     r8, [rbp+arg_0]; pbInput
0x1800135b9  mov     r9d, edi; cbInput
0x1800135bc  mov     dword ptr [rsp+58h+dwFlags], 80000000h; dwFlags
0x1800135c4  lea     rdx, aExportPolicy; "Export Policy"
0x1800135cb  call    cs:__imp_NCryptSetProperty
0x1800135d1  mov     ebx, eax
0x1800135d3  test    eax, eax
0x1800135d5  jz      short loc_180013610
0x1800135d7  test    byte ptr cs:Microsoft_Windows_DM_Enrollment_ProviderEnableBits, dil
0x1800135de  jz      loc_180013550
0x1800135e4  lea     r8, aNcryptsetprope_0; "NCryptSetProperty#2"
0x1800135eb  jmp     short loc_180013592
0x1800135ed  test    cs:Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits, dil
0x1800135f4  jz      short loc_180013610
0x1800135f6  lea     r8, aLegacycreateke; "LegacyCreateKeyWithRetry"
0x1800135fd  lea     rdx, EnterpriseDiagnosticsTPMSkipExportPrivateKey
0x180013604  lea     rcx, MDM_ENTERPRISE_DIAGNOSTICS_Context
0x18001360b  call    McTemplateU0z_EventWriteTransfer
0x180013610  lea     rdx, aNcryptfinalize_1; "NCryptFinalizeKey"
0x180013617  lea     rcx, [rbp+arg_8]; this
0x18001361b  call    ??0EvtPerfTraceScope@@QEAA@PEBD@Z; EvtPerfTraceScope::EvtPerfTraceScope(char const *)
0x180013620  mov     rcx, [r15]; hKey
0x180013623  xor     edx, edx; dwFlags
0x180013625  call    cs:__imp_NCryptFinalizeKey
0x18001362b  lea     rcx, [rbp+arg_8]; this
0x18001362f  mov     ebx, eax
0x180013631  call    ??1EvtPerfTraceScope@@QEAA@XZ; EvtPerfTraceScope::~EvtPerfTraceScope(void)
0x180013636  test    ebx, ebx
0x180013638  jz      short loc_180013653
0x18001363a  test    byte ptr cs:Microsoft_Windows_DM_Enrollment_ProviderEnableBits, dil
0x180013641  jz      loc_180013550
0x180013647  lea     r8, aNcryptfinalize_0; "NCryptFinalizeKey"
0x18001364e  jmp     loc_180013592
0x180013653  mov     rcx, [rbp+arg_28]; unsigned __int16 *
0x180013657  mov     r8, rsi; unsigned __int16 *
0x18001365a  mov     edx, 100h; unsigned __int64
0x18001365f  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180013664  jmp     loc_18001344B
0x180013669  mov     esi, 80070216h
0x18001366e  jmp     loc_1800133AD
```
