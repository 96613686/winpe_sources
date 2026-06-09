# GetCertPolicy::Execute(ActivityContext *)

- ea: `0x1800426e0`
- end: `0x180042d87`
- name: `?Execute@GetCertPolicy@@UEAAJPEAVActivityContext@@@Z`
- size: `1703`
- prototype: `int(GetCertPolicy *__hidden this, struct ActivityContext *)`
- caller_count: `0`
- callee_count: `20`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callees

- `0x180006950`
- `0x18000de50`
- `0x18000e0d0`
- `0x180010600`
- `0x1800140b4`
- `0x180019e8c`
- `0x18001a86c`
- `0x18001aec8`
- `0x18001f98c`
- `0x1800209b8`
- `0x18002e1a0`
- `0x18002ec8c`
- `0x18003ebe0`
- `0x180041420`
- `0x180041470`
- `0x1800426e0`
- `0x180042efc`
- `0x1800437a4`
- `0x18004cebc`
- `0x180071390`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x1800429bd`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x1800429bd`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800427c0`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800427c0`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180042a0b`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180042a0b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800427e6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004283a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004284a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800428a6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180042d54`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800427e6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004283a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004284a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800428a6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180042d54`
- `DMCmnUtils!OmaDmRegistryGetDWORD` at `0x1800429dd`
- `DMCmnUtils!OmaDmRegistryGetDWORD` at `0x1800429dd`
- `DMCmnUtils!DmGetTpmInfo` at `0x180042a7e`
- `DMCmnUtils!DmGetTpmInfo` at `0x180042a7e`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall GetCertPolicy::Execute(GetCertPolicy *this, struct ActivityContext *a2)
{
  signed int KeyAsString; // ebx
  HKEY v4; // rcx
  LSTATUS v5; // eax
  HKEY v6; // rcx
  HKEY v7; // rcx
  int v8; // ecx
  BOOL v9; // r14d
  int DWORD; // eax
  char v11; // di
  __int64 v12; // rdx
  int TpmInfo; // ebx
  CEnrollmentLogger *Logger; // rax
  const unsigned __int16 *v15; // rdx
  ActivityContext *v16; // rcx
  const unsigned __int16 *PolicyServiceFullURL; // rax
  __int64 v18; // r10
  int v19; // r11d
  signed int v20; // r14d
  __int64 v21; // rdi
  _QWORD *v22; // rcx
  __int64 v23; // rbx
  __int64 v24; // r8
  _QWORD *v25; // rcx
  __int64 v26; // r8
  EEDBManager *v27; // rcx
  HKEY v28; // rcx
  HKEY phkResult; // [rsp+D0h] [rbp-80h] BYREF
  _WORD *v31; // [rsp+D8h] [rbp-78h] BYREF
  _WORD *v32; // [rsp+E0h] [rbp-70h] BYREF
  _WORD *v33; // [rsp+E8h] [rbp-68h] BYREF
  unsigned __int16 *v34; // [rsp+F0h] [rbp-60h] BYREF
  void *v35; // [rsp+F8h] [rbp-58h] BYREF
  HKEY hKey; // [rsp+100h] [rbp-50h] BYREF
  __int64 v37; // [rsp+108h] [rbp-48h] BYREF
  __int64 v38; // [rsp+110h] [rbp-40h]
  unsigned int v39; // [rsp+118h] [rbp-38h] BYREF
  int v40; // [rsp+11Ch] [rbp-34h] BYREF
  unsigned int v41; // [rsp+120h] [rbp-30h] BYREF
  int v42; // [rsp+124h] [rbp-2Ch] BYREF
  unsigned int v43; // [rsp+128h] [rbp-28h] BYREF
  int v44; // [rsp+12Ch] [rbp-24h] BYREF
  int v45; // [rsp+130h] [rbp-20h] BYREF
  int v46; // [rsp+134h] [rbp-1Ch] BYREF
  unsigned __int16 *v47; // [rsp+138h] [rbp-18h] BYREF
  struct _GUID v48; // [rsp+140h] [rbp-10h] BYREF
  struct _GUID v49; // [rsp+150h] [rbp+0h] BYREF
  int v50; // [rsp+160h] [rbp+10h] BYREF
  int v51; // [rsp+164h] [rbp+14h] BYREF
  __int64 v52; // [rsp+168h] [rbp+18h] BYREF
  _WORD *v53; // [rsp+170h] [rbp+20h] BYREF
  WCHAR SubKey[40]; // [rsp+180h] [rbp+30h] BYREF
  unsigned __int16 v55[264]; // [rsp+1D0h] [rbp+80h] BYREF
  unsigned __int16 v56[264]; // [rsp+3E0h] [rbp+290h] BYREF

  v44 = 0;
  v52 = 0;
  v53 = 0;
  v47 = 0;
  phkResult = 0;
  v50 = 0;
  v35 = 0;
  v34 = 0;
  v33 = 0;
  v32 = 0;
  v31 = 0;
  v41 = 0;
  v40 = 0;
  v37 = 0;
  v38 = 0;
  v43 = 0;
  v45 = 0;
  v46 = 0;
  if ( *((char *)a2 + 72) < 0 || *((_DWORD *)a2 + 12) && *((_QWORD *)a2 + 7) && *((_DWORD *)a2 + 18) )
  {
LABEL_18:
    wil::unique_any_array_ptr<unsigned short *,wil::process_heap_deleter,wil::process_heap_deleter,unsigned __int64>::reset(&v37);
    CHeapMemPtr<unsigned short>::~CHeapMemPtr<unsigned short>((void **)&v31);
    CHeapMemPtr<unsigned short>::~CHeapMemPtr<unsigned short>((void **)&v32);
    CHeapMemPtr<unsigned short>::~CHeapMemPtr<unsigned short>((void **)&v33);
    CHeapMemPtr<unsigned short>::~CHeapMemPtr<unsigned short>((void **)&v34);
    CHeapMemPtr<unsigned short>::~CHeapMemPtr<unsigned short>(&v35);
    v7 = phkResult;
    phkResult = 0;
    if ( v7 )
      RegCloseKey(v7);
    KeyAsString = 1;
    goto LABEL_71;
  }
  KeyAsString = ActivityContext::get_KeyAsString(a2, SubKey);
  if ( KeyAsString < 0 )
    goto LABEL_13;
  hKey = 0;
  KeyAsString = EEDBManager::OpenEnrollmentsHKEY(0x2001Fu, &hKey);
  v4 = hKey;
  if ( KeyAsString < 0 )
  {
    hKey = 0;
LABEL_11:
    if ( v4 )
      RegCloseKey(v4);
    goto LABEL_13;
  }
  v5 = RegOpenKeyExW(hKey, SubKey, 0, 0x2001Fu, &phkResult);
  KeyAsString = v5;
  if ( v5 > 0 )
    KeyAsString = (unsigned __int16)v5 | 0x80070000;
  v4 = hKey;
  hKey = 0;
  if ( KeyAsString < 0 )
    goto LABEL_11;
  if ( v4 )
    RegCloseKey(v4);
  if ( !ActivityContext::get_PolicyServiceFullURL(a2) )
    goto LABEL_18;
  v49 = *(struct _GUID *)((char *)a2 + 8);
  KeyAsString = EEDBManager::GetEnrollmentAuthPolicy(&v49, (enum MDMAuthPolicy *)&v40);
  if ( KeyAsString < 0 )
  {
LABEL_13:
    wil::unique_any_array_ptr<unsigned short *,wil::process_heap_deleter,wil::process_heap_deleter,unsigned __int64>::reset(&v37);
    CHeapMemPtr<unsigned short>::~CHeapMemPtr<unsigned short>((void **)&v31);
    CHeapMemPtr<unsigned short>::~CHeapMemPtr<unsigned short>((void **)&v32);
    CHeapMemPtr<unsigned short>::~CHeapMemPtr<unsigned short>((void **)&v33);
    CHeapMemPtr<unsigned short>::~CHeapMemPtr<unsigned short>((void **)&v34);
    CHeapMemPtr<unsigned short>::~CHeapMemPtr<unsigned short>(&v35);
    v6 = phkResult;
    phkResult = 0;
    if ( v6 )
      RegCloseKey(v6);
    goto LABEL_71;
  }
  *(_QWORD *)&v49.Data1 = 0;
  v48 = *(struct _GUID *)((char *)a2 + 8);
  EEDBManager::GetEnrollmentString(&v48, L"SID", (unsigned __int16 **)&v49);
  v42 = 0;
  v48 = *(struct _GUID *)((char *)a2 + 8);
  KeyAsString = EEDBManager::GetEnrollmentType(&v48, (enum EnrollmentEnrollType *)&v42);
  if ( KeyAsString < 0 )
    goto LABEL_23;
  v8 = *((_DWORD *)a2 + 18) | 8;
  if ( ((1LL << v42) & 0x5402060) == 0 )
    v8 = *((_DWORD *)a2 + 18);
  if ( ((1LL << v42) & 0x4000040) != 0 )
    v8 |= 4u;
  *((_DWORD *)a2 + 18) = v8;
  v51 = v8;
  if ( (unsigned int)(v40 - 1) <= 1
    || (v48 = *(struct _GUID *)((char *)a2 + 8), EEDBManager::GetEnrollmentString(&v48, L"DomainUsername", &v47) < 0) )
  {
    v48 = *(struct _GUID *)((char *)a2 + 8);
    KeyAsString = EEDBManager::GetEnrollmentString(&v48, L"UPN", &v47);
    if ( KeyAsString < 0 )
    {
LABEL_23:
      CHeapMemPtr<unsigned short>::~CHeapMemPtr<unsigned short>((void **)&v49);
      goto LABEL_13;
    }
  }
  v9 = _o__wcsnicmp((char *)a2 + 448) == 0;
  DWORD = OmaDmRegistryGetDWORD(phkResult, 0, L"RenewROBOSupport", &v41);
  KeyAsString = DWORD;
  if ( DWORD == -2147024894 || DWORD == -2147023267 )
  {
    v41 = 0;
  }
  else if ( DWORD < 0 )
  {
    goto LABEL_23;
  }
  RegDeleteValueW(phkResult, L"LastSoapErrorTraceId");
  v11 = 0;
  memset_0(v56, 0, 0x208u);
  memset_0(v55, 0, 0x208u);
  LOBYTE(v12) = 1;
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_EnrollmentAttestationDebugFields>::ReportUsage(
    `wil::Feature<__WilFeatureTraits_Feature_EnrollmentAttestationDebugFields>::GetImpl'::`2'::impl,
    v12);
  if ( CheckServerIsVersionOrAbove(*((_DWORD *)a2 + 18), 5) )
  {
    v39 = 0;
    TpmInfo = DmGetTpmInfo(&v39, v56, 0x104u, v55, 0x104u);
    if ( TpmInfo < 0 || v39 < 2 )
    {
      v11 = 0;
      Logger = CEnrollmentLogger::GetLogger();
      v15 = L"DmGetTpmInfo";
      if ( TpmInfo >= 0 )
        v15 = L"No suitable TPM version found";
      CEnrollmentLogger::LogDmGetTpmInfoFailure(Logger, v15, v39, TpmInfo);
    }
    else
    {
      v11 = 1;
    }
  }
  wil::unique_any_array_ptr<unsigned short *,wil::process_heap_deleter,wil::process_heap_deleter,unsigned __int64>::reset(&v37);
  ActivityContext::get_CorrelationID(a2);
  PolicyServiceFullURL = ActivityContext::get_PolicyServiceFullURL(v16);
  v20 = RetrieveCertificatePolicyOld(
          *(_QWORD *)&v49.Data1,
          phkResult,
          v41,
          PolicyServiceFullURL,
          v47,
          *((_QWORD *)a2 + 5),
          v19,
          v9,
          *((_DWORD *)a2 + 18),
          (unsigned __int64)v56 & -(__int64)(v11 != 0),
          (unsigned __int64)v55 & -(__int64)(v11 != 0),
          v18,
          &v44,
          &v52,
          &v53,
          &v51,
          &v50,
          &v35,
          &v45,
          &v46,
          &v33,
          &v32,
          &v31,
          &v34,
          &v37,
          &v43);
  v21 = v37;
  v37 = 0;
  v38 = 0;
  wil::unique_any_array_ptr<unsigned short *,wil::process_heap_deleter,wil::process_heap_deleter,unsigned __int64>::reset((char *)a2 + 272);
  *((_QWORD *)a2 + 34) = v21;
  *((_QWORD *)a2 + 35) = v43;
  *((_DWORD *)a2 + 12) = v44;
  *((_QWORD *)a2 + 7) = v52;
  *((_DWORD *)a2 + 73) = v45;
  *((_DWORD *)a2 + 72) = v46;
  v22 = (_QWORD *)((char *)a2 + 296);
  v23 = -1;
  if ( v33 )
  {
    v24 = -1;
    do
      ++v24;
    while ( v33[v24] );
    std::wstring::_Assign<unsigned short>(v22, v33, v24);
  }
  else
  {
    *((_QWORD *)a2 + 39) = 0;
    if ( *((_QWORD *)a2 + 40) > 7u )
      v22 = (_QWORD *)*v22;
    *(_WORD *)v22 = 0;
  }
  v25 = (_QWORD *)((char *)a2 + 328);
  if ( v32 )
  {
    v26 = -1;
    do
      ++v26;
    while ( v32[v26] );
    std::wstring::_Assign<unsigned short>(v25, v32, v26);
  }
  else
  {
    *((_QWORD *)a2 + 43) = 0;
    if ( *((_QWORD *)a2 + 44) > 7u )
      v25 = (_QWORD *)*v25;
    *(_WORD *)v25 = 0;
  }
  v27 = (struct ActivityContext *)((char *)a2 + 360);
  if ( v31 )
  {
    do
      ++v23;
    while ( v31[v23] );
    std::wstring::_Assign<unsigned short>(v27, v31, v23);
  }
  else
  {
    *((_QWORD *)a2 + 47) = 0;
    if ( *((_QWORD *)a2 + 48) > 7u )
      v27 = *(EEDBManager **)v27;
    *(_WORD *)v27 = 0;
  }
  if ( v53 && *v53 )
    *((_QWORD *)a2 + 8) = v53;
  if ( v34 )
  {
    v48 = *(struct _GUID *)((char *)a2 + 8);
    EEDBManager::SetErrorContext(v27, &v48, v34);
  }
  CHeapMemPtr<unsigned short>::~CHeapMemPtr<unsigned short>((void **)&v49);
  wil::unique_any_array_ptr<unsigned short *,wil::process_heap_deleter,wil::process_heap_deleter,unsigned __int64>::reset(&v37);
  CHeapMemPtr<unsigned short>::~CHeapMemPtr<unsigned short>((void **)&v31);
  CHeapMemPtr<unsigned short>::~CHeapMemPtr<unsigned short>((void **)&v32);
  CHeapMemPtr<unsigned short>::~CHeapMemPtr<unsigned short>((void **)&v33);
  CHeapMemPtr<unsigned short>::~CHeapMemPtr<unsigned short>((void **)&v34);
  CHeapMemPtr<unsigned short>::~CHeapMemPtr<unsigned short>(&v35);
  v28 = phkResult;
  phkResult = 0;
  if ( v28 )
    RegCloseKey(v28);
  KeyAsString = v20;
LABEL_71:
  CLocalMemPtr<unsigned short>::~CLocalMemPtr<unsigned short>(&v47);
  return (unsigned int)KeyAsString;
}

```

## disassembly

```asm
0x1800426e0  push    rbp
0x1800426e2  push    rbx
0x1800426e3  push    rsi
0x1800426e4  push    rdi
0x1800426e5  push    r14
0x1800426e7  push    r15
0x1800426e9  lea     rbp, [rsp-4B8h]
0x1800426f1  sub     rsp, 608h
0x1800426f8  mov     rax, cs:__security_cookie
0x1800426ff  xor     rax, rsp
0x180042702  mov     [rbp+4E0h+var_40], rax
0x180042709  mov     rsi, rdx
0x18004270c  xor     r15d, r15d
0x18004270f  mov     [rbp+4E0h+var_504], r15d
0x180042713  mov     [rbp+4E0h+var_4C8], r15
0x180042717  mov     [rbp+4E0h+var_4C0], r15
0x18004271b  mov     [rbp+4E0h+var_4F8], r15
0x18004271f  mov     [rbp+4E0h+var_560], r15
0x180042723  mov     [rbp+4E0h+var_4D0], r15d
0x180042727  mov     [rbp+4E0h+var_538], r15
0x18004272b  mov     [rbp+4E0h+var_540], r15
0x18004272f  mov     [rbp+4E0h+var_548], r15
0x180042733  mov     [rbp+4E0h+var_550], r15
0x180042737  mov     [rbp+4E0h+var_558], r15
0x18004273b  mov     [rbp+4E0h+var_510], r15d
0x18004273f  mov     [rbp+4E0h+var_514], r15d
0x180042743  mov     [rbp+4E0h+var_528], r15
0x180042747  mov     [rbp+4E0h+var_520], r15
0x18004274b  mov     [rbp+4E0h+var_508], r15d
0x18004274f  mov     [rbp+4E0h+var_500], r15d
0x180042753  mov     [rbp+4E0h+var_4FC], r15d
0x180042757  test    byte ptr [rdx+48h], 80h
0x18004275b  jnz     loc_18004285D
0x180042761  cmp     [rdx+30h], r15d
0x180042765  jz      short loc_180042777
0x180042767  cmp     [rdx+38h], r15
0x18004276b  jz      short loc_180042777
0x18004276d  cmp     [rdx+48h], r15d
0x180042771  jnz     loc_18004285D
0x180042777  lea     rdx, [rbp+4E0h+SubKey]; unsigned __int16 *
0x18004277b  mov     rcx, rsi; this
0x18004277e  call    ?get_KeyAsString@ActivityContext@@QEAAJQEAG@Z; ActivityContext::get_KeyAsString(ushort * const)
0x180042783  mov     ebx, eax
0x180042785  test    eax, eax
0x180042787  js      short loc_1800427ED
0x180042789  mov     [rbp+4E0h+hKey], r15
0x18004278d  lea     rdx, [rbp+4E0h+hKey]; HKEY *
0x180042791  mov     edi, 2001Fh
0x180042796  mov     ecx, edi; unsigned int
0x180042798  call    ?OpenEnrollmentsHKEY@EEDBManager@@SAJKPEAPEAUHKEY__@@@Z; EEDBManager::OpenEnrollmentsHKEY(ulong,HKEY__ * *)
0x18004279d  mov     ebx, eax
0x18004279f  mov     rcx, [rbp+4E0h+hKey]; hKey
0x1800427a3  test    eax, eax
0x1800427a5  jns     short loc_1800427AD
0x1800427a7  mov     [rbp+4E0h+hKey], r15
0x1800427ab  jmp     short loc_1800427E1
0x1800427ad  lea     rax, [rbp+4E0h+var_560]
0x1800427b1  mov     [rsp+630h+phkResult], rax; phkResult
0x1800427b6  mov     r9d, edi; samDesired
0x1800427b9  xor     r8d, r8d; ulOptions
0x1800427bc  lea     rdx, [rbp+4E0h+SubKey]; lpSubKey
0x1800427c0  call    cs:__imp_RegOpenKeyExW
0x1800427c6  mov     ebx, eax
0x1800427c8  test    eax, eax
0x1800427ca  jle     short loc_1800427D5
0x1800427cc  movzx   ebx, ax
0x1800427cf  or      ebx, 80070000h
0x1800427d5  mov     rcx, [rbp+4E0h+hKey]; hKey
0x1800427d9  mov     [rbp+4E0h+hKey], r15
0x1800427dd  test    ebx, ebx
0x1800427df  jns     short loc_180042845
0x1800427e1  test    rcx, rcx
0x1800427e4  jz      short loc_1800427ED
0x1800427e6  call    cs:__imp_RegCloseKey
0x1800427ec  nop
0x1800427ed  lea     rcx, [rbp+4E0h+var_528]
0x1800427f1  call    ?reset@?$unique_any_array_ptr@PEAGUprocess_heap_deleter@wil@@U12@_K@wil@@QEAAXXZ; wil::unique_any_array_ptr<ushort *,wil::process_heap_deleter,wil::process_heap_deleter,unsigned __int64>::reset(void)
0x1800427f6  nop
0x1800427f7  lea     rcx, [rbp+4E0h+var_558]
0x1800427fb  call    ??1?$CHeapMemPtr@G@@QEAA@XZ; CHeapMemPtr<ushort>::~CHeapMemPtr<ushort>(void)
0x180042800  nop
0x180042801  lea     rcx, [rbp+4E0h+var_550]
0x180042805  call    ??1?$CHeapMemPtr@G@@QEAA@XZ; CHeapMemPtr<ushort>::~CHeapMemPtr<ushort>(void)
0x18004280a  nop
0x18004280b  lea     rcx, [rbp+4E0h+var_548]
0x18004280f  call    ??1?$CHeapMemPtr@G@@QEAA@XZ; CHeapMemPtr<ushort>::~CHeapMemPtr<ushort>(void)
0x180042814  nop
0x180042815  lea     rcx, [rbp+4E0h+var_540]
0x180042819  call    ??1?$CHeapMemPtr@G@@QEAA@XZ; CHeapMemPtr<ushort>::~CHeapMemPtr<ushort>(void)
0x18004281e  nop
0x18004281f  lea     rcx, [rbp+4E0h+var_538]
0x180042823  call    ??1?$CHeapMemPtr@G@@QEAA@XZ; CHeapMemPtr<ushort>::~CHeapMemPtr<ushort>(void)
0x180042828  nop
0x180042829  mov     rcx, [rbp+4E0h+var_560]; hKey
0x18004282d  mov     [rbp+4E0h+var_560], r15
0x180042831  test    rcx, rcx
0x180042834  jz      loc_180042D5D
0x18004283a  call    cs:__imp_RegCloseKey
0x180042840  jmp     loc_180042D5D
0x180042845  test    rcx, rcx
0x180042848  jz      short loc_180042850
0x18004284a  call    cs:__imp_RegCloseKey
0x180042850  mov     rcx, rsi; this
0x180042853  call    ?get_PolicyServiceFullURL@ActivityContext@@QEBAPEBGXZ; ActivityContext::get_PolicyServiceFullURL(void)
0x180042858  test    rax, rax
0x18004285b  jnz     short loc_1800428B6
0x18004285d  lea     rcx, [rbp+4E0h+var_528]
0x180042861  call    ?reset@?$unique_any_array_ptr@PEAGUprocess_heap_deleter@wil@@U12@_K@wil@@QEAAXXZ; wil::unique_any_array_ptr<ushort *,wil::process_heap_deleter,wil::process_heap_deleter,unsigned __int64>::reset(void)
0x180042866  nop
0x180042867  lea     rcx, [rbp+4E0h+var_558]
0x18004286b  call    ??1?$CHeapMemPtr@G@@QEAA@XZ; CHeapMemPtr<ushort>::~CHeapMemPtr<ushort>(void)
0x180042870  nop
0x180042871  lea     rcx, [rbp+4E0h+var_550]
0x180042875  call    ??1?$CHeapMemPtr@G@@QEAA@XZ; CHeapMemPtr<ushort>::~CHeapMemPtr<ushort>(void)
0x18004287a  nop
0x18004287b  lea     rcx, [rbp+4E0h+var_548]
0x18004287f  call    ??1?$CHeapMemPtr@G@@QEAA@XZ; CHeapMemPtr<ushort>::~CHeapMemPtr<ushort>(void)
0x180042884  nop
0x180042885  lea     rcx, [rbp+4E0h+var_540]
0x180042889  call    ??1?$CHeapMemPtr@G@@QEAA@XZ; CHeapMemPtr<ushort>::~CHeapMemPtr<ushort>(void)
0x18004288e  nop
0x18004288f  lea     rcx, [rbp+4E0h+var_538]
0x180042893  call    ??1?$CHeapMemPtr@G@@QEAA@XZ; CHeapMemPtr<ushort>::~CHeapMemPtr<ushort>(void)
0x180042898  nop
0x180042899  mov     rcx, [rbp+4E0h+var_560]; hKey
0x18004289d  mov     [rbp+4E0h+var_560], r15
0x1800428a1  test    rcx, rcx
0x1800428a4  jz      short loc_1800428AC
0x1800428a6  call    cs:__imp_RegCloseKey
0x1800428ac  mov     ebx, 1
0x1800428b1  jmp     loc_180042D5D
0x1800428b6  movups  xmm0, xmmword ptr [rsi+8]
0x1800428ba  movdqu  xmmword ptr [rbp+4E0h+var_4E0.Data1], xmm0
0x1800428bf  lea     rdx, [rbp+4E0h+var_514]; enum MDMAuthPolicy *
0x1800428c3  lea     rcx, [rbp+4E0h+var_4E0]; struct _GUID
0x1800428c7  call    ?GetEnrollmentAuthPolicy@EEDBManager@@SAJU_GUID@@PEAW4MDMAuthPolicy@@@Z; EEDBManager::GetEnrollmentAuthPolicy(_GUID,MDMAuthPolicy *)
0x1800428cc  mov     ebx, eax
0x1800428ce  test    eax, eax
0x1800428d0  js      loc_1800427ED
0x1800428d6  mov     qword ptr [rbp+4E0h+var_4E0.Data1], r15
0x1800428da  movups  xmm0, xmmword ptr [rsi+8]
0x1800428de  movdqu  xmmword ptr [rbp+4E0h+var_4F0.Data1], xmm0
0x1800428e3  lea     r8, [rbp+4E0h+var_4E0]; unsigned __int16 **
0x1800428e7  lea     rdx, aSid; "SID"
0x1800428ee  lea     rcx, [rbp+4E0h+var_4F0]; struct _GUID
0x1800428f2  call    ?GetEnrollmentString@EEDBManager@@CAJU_GUID@@PEBGPEAPEAG@Z; EEDBManager::GetEnrollmentString(_GUID,ushort const *,ushort * *)
0x1800428f7  mov     [rbp+4E0h+var_50C], r15d
0x1800428fb  movups  xmm0, xmmword ptr [rsi+8]
0x1800428ff  movdqu  xmmword ptr [rbp+4E0h+var_4F0.Data1], xmm0
0x180042904  lea     rdx, [rbp+4E0h+var_50C]; enum EnrollmentEnrollType *
0x180042908  lea     rcx, [rbp+4E0h+var_4F0]; struct _GUID
0x18004290c  call    ?GetEnrollmentType@EEDBManager@@SAJU_GUID@@PEAW4EnrollmentEnrollType@@@Z; EEDBManager::GetEnrollmentType(_GUID,EnrollmentEnrollType *)
0x180042911  mov     ebx, eax
0x180042913  test    eax, eax
0x180042915  jns     short loc_180042925
0x180042917  lea     rcx, [rbp+4E0h+var_4E0]
0x18004291b  call    ??1?$CHeapMemPtr@G@@QEAA@XZ; CHeapMemPtr<ushort>::~CHeapMemPtr<ushort>(void)
0x180042920  jmp     loc_1800427ED
0x180042925  mov     ecx, [rbp+4E0h+var_50C]
0x180042928  mov     edx, 1
0x18004292d  shl     rdx, cl
0x180042930  mov     rax, rdx
0x180042933  and     eax, 5402060h
0x180042938  mov     ecx, [rsi+48h]
0x18004293b  or      ecx, 8
0x18004293e  test    rax, rax
0x180042941  cmovz   ecx, [rsi+48h]
0x180042945  test    rdx, 4000040h
0x18004294c  jz      short loc_180042951
0x18004294e  or      ecx, 4
0x180042951  mov     [rsi+48h], ecx
0x180042954  mov     [rbp+4E0h+var_4CC], ecx
0x180042957  mov     eax, [rbp+4E0h+var_514]
0x18004295a  dec     eax
0x18004295c  cmp     eax, 1
0x18004295f  jbe     short loc_180042982
0x180042961  movups  xmm0, xmmword ptr [rsi+8]
0x180042965  movdqu  xmmword ptr [rbp+4E0h+var_4F0.Data1], xmm0
0x18004296a  lea     r8, [rbp+4E0h+var_4F8]; unsigned __int16 **
0x18004296e  lea     rdx, aDomainusername; "DomainUsername"
0x180042975  lea     rcx, [rbp+4E0h+var_4F0]; struct _GUID
0x180042979  call    ?GetEnrollmentString@EEDBManager@@CAJU_GUID@@PEBGPEAPEAG@Z; EEDBManager::GetEnrollmentString(_GUID,ushort const *,ushort * *)
0x18004297e  test    eax, eax
0x180042980  jns     short loc_1800429A9
0x180042982  movups  xmm0, xmmword ptr [rsi+8]
0x180042986  movdqu  xmmword ptr [rbp+4E0h+var_4F0.Data1], xmm0
0x18004298b  lea     r8, [rbp+4E0h+var_4F8]; unsigned __int16 **
0x18004298f  lea     rdx, aUpn; "UPN"
0x180042996  lea     rcx, [rbp+4E0h+var_4F0]; struct _GUID
0x18004299a  call    ?GetEnrollmentString@EEDBManager@@CAJU_GUID@@PEBGPEAPEAG@Z; EEDBManager::GetEnrollmentString(_GUID,ushort const *,ushort * *)
0x18004299f  mov     ebx, eax
0x1800429a1  test    eax, eax
0x1800429a3  js      loc_180042917
0x1800429a9  lea     rcx, [rsi+1C0h]
0x1800429b0  mov     r8d, 104h
0x1800429b6  mov     rdx, cs:off_1800AF248; "OR_RENEW"
0x1800429bd  call    cs:__imp__o__wcsnicmp
0x1800429c3  mov     r14d, r15d
0x1800429c6  test    eax, eax
0x1800429c8  setz    r14b
0x1800429cc  lea     r9, [rbp+4E0h+var_510]
0x1800429d0  lea     r8, aRenewrobosuppo; "RenewROBOSupport"
0x1800429d7  xor     edx, edx
0x1800429d9  mov     rcx, [rbp+4E0h+var_560]
0x1800429dd  call    cs:__imp_?OmaDmRegistryGetDWORD@@YAJPEAUHKEY__@@PEBG1PEAK@Z; OmaDmRegistryGetDWORD(HKEY__ *,ushort const *,ushort const *,ulong *)
0x1800429e3  mov     ebx, eax
0x1800429e5  cmp     eax, 80070002h
0x1800429ea  jz      short loc_1800429FC
0x1800429ec  cmp     eax, 8007065Dh
0x1800429f1  jz      short loc_1800429FC
0x1800429f3  test    eax, eax
0x1800429f5  jns     short loc_180042A00
0x1800429f7  jmp     loc_180042917
0x1800429fc  mov     [rbp+4E0h+var_510], r15d
0x180042a00  lea     rdx, aLastsoaperrort; "LastSoapErrorTraceId"
0x180042a07  mov     rcx, [rbp+4E0h+var_560]; hKey
0x180042a0b  call    cs:__imp_RegDeleteValueW
0x180042a11  mov     dil, r15b
0x180042a14  mov     ebx, 208h
0x180042a19  mov     r8d, ebx; Size
0x180042a1c  xor     edx, edx; Val
0x180042a1e  lea     rcx, [rbp+4E0h+var_250]; void *
0x180042a25  call    memset_0
0x180042a2a  mov     r8d, ebx; Size
0x180042a2d  xor     edx, edx; Val
0x180042a2f  lea     rcx, [rbp+4E0h+var_460]; void *
0x180042a36  call    memset_0
0x180042a3b  mov     dl, 1
0x180042a3d  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_EnrollmentAttestationDebugFields@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_EnrollmentAttestationDebugFields@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_EnrollmentAttestationDebugFields> `wil::Feature<__WilFeatureTraits_Feature_EnrollmentAttestationDebugFields>::GetImpl(void)'::`2'::impl
0x180042a44  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_EnrollmentAttestationDebugFields@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_EnrollmentAttestationDebugFields>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x180042a49  mov     edx, 5; int
0x180042a4e  mov     ecx, [rsi+48h]; unsigned int
0x180042a51  call    ?CheckServerIsVersionOrAbove@@YA_NKH@Z; CheckServerIsVersionOrAbove(ulong,int)
0x180042a56  test    al, al
0x180042a58  jz      short loc_180042AC0
0x180042a5a  mov     [rbp+4E0h+var_518], r15d
0x180042a5e  mov     dword ptr [rsp+630h+phkResult], 104h
0x180042a66  lea     r9, [rbp+4E0h+var_460]
0x180042a6d  mov     r8d, 104h
0x180042a73  lea     rdx, [rbp+4E0h+var_250]
0x180042a7a  lea     rcx, [rbp+4E0h+var_518]
0x180042a7e  call    cs:__imp_?DmGetTpmInfo@@YAJPEAKPEAGK1K@Z; DmGetTpmInfo(ulong *,ushort *,ulong,ushort *,ulong)
0x180042a84  mov     ebx, eax
0x180042a86  test    eax, eax
0x180042a88  js      short loc_180042A95
0x180042a8a  cmp     [rbp+4E0h+var_518], 2
0x180042a8e  jb      short loc_180042A95
0x180042a90  mov     dil, 1
0x180042a93  jmp     short loc_180042AC0
0x180042a95  mov     dil, r15b
0x180042a98  call    ?GetLogger@CEnrollmentLogger@@SAPEAV1@XZ; CEnrollmentLogger::GetLogger(void)
0x180042a9d  lea     rcx, aNoSuitableTpmV; "No suitable TPM version found"
0x180042aa4  lea     rdx, aDmgettpminfo_0; "DmGetTpmInfo"
0x180042aab  test    ebx, ebx
0x180042aad  cmovns  rdx, rcx; unsigned __int16 *
0x180042ab1  mov     r9d, ebx; int
0x180042ab4  mov     r8d, [rbp+4E0h+var_518]; unsigned int
0x180042ab8  mov     rcx, rax; this
0x180042abb  call    ?LogDmGetTpmInfoFailure@CEnrollmentLogger@@QEAAXPEBGKJ@Z; CEnrollmentLogger::LogDmGetTpmInfoFailure(ushort const *,ulong,long)
0x180042ac0  lea     rcx, [rbp+4E0h+var_528]
0x180042ac4  call    ?reset@?$unique_any_array_ptr@PEAGUprocess_heap_deleter@wil@@U12@_K@wil@@QEAAXXZ; wil::unique_any_array_ptr<ushort *,wil::process_heap_deleter,wil::process_heap_deleter,unsigned __int64>::reset(void)
0x180042ac9  mov     rcx, rsi; this
0x180042acc  call    ?get_CorrelationID@ActivityContext@@QEBAPEBGXZ; ActivityContext::get_CorrelationID(void)
0x180042ad1  mov     r10, rax
0x180042ad4  mov     r11d, [rbp+4E0h+var_514]
0x180042ad8  call    ?get_PolicyServiceFullURL@ActivityContext@@QEBAPEBGXZ; ActivityContext::get_PolicyServiceFullURL(void)
0x180042add  mov     rbx, rax
0x180042ae0  mov     cl, dil
0x180042ae3  neg     cl
0x180042ae5  sbb     r9, r9
0x180042ae8  lea     rax, [rbp+4E0h+var_460]
0x180042aef  and     r9, rax
0x180042af2  neg     dil
0x180042af5  sbb     rcx, rcx
0x180042af8  lea     rax, [rbp+4E0h+var_250]
0x180042aff  and     rcx, rax
0x180042b02  lea     rax, [rbp+4E0h+var_508]
0x180042b06  mov     [rsp+630h+var_568], rax
0x180042b0e  lea     rax, [rbp+4E0h+var_528]
0x180042b12  mov     [rsp+630h+var_570], rax
0x180042b1a  lea     rax, [rbp+4E0h+var_540]
0x180042b1e  mov     [rsp+630h+var_578], rax
0x180042b26  lea     rax, [rbp+4E0h+var_558]
0x180042b2a  mov     [rsp+630h+var_580], rax
0x180042b32  lea     rax, [rbp+4E0h+var_550]
0x180042b36  mov     [rsp+630h+var_588], rax
0x180042b3e  lea     rax, [rbp+4E0h+var_548]
0x180042b42  mov     [rsp+630h+var_590], rax
0x180042b4a  lea     rax, [rbp+4E0h+var_4FC]
0x180042b4e  mov     [rsp+630h+var_598], rax
0x180042b56  lea     rax, [rbp+4E0h+var_500]
0x180042b5a  mov     [rsp+630h+var_5A0], rax
0x180042b62  lea     rax, [rbp+4E0h+var_538]
0x180042b66  mov     [rsp+630h+var_5A8], rax
0x180042b6e  lea     rax, [rbp+4E0h+var_4D0]
0x180042b72  mov     [rsp+630h+var_5B0], rax
0x180042b7a  lea     rax, [rbp+4E0h+var_4CC]
0x180042b7e  mov     [rsp+630h+var_5B8], rax
0x180042b83  lea     rax, [rbp+4E0h+var_4C0]
0x180042b87  mov     [rsp+630h+var_5C0], rax
  ... truncated ...
```
