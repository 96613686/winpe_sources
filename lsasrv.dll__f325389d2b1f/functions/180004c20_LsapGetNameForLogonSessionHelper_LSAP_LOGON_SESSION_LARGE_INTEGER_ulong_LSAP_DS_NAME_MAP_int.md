# LsapGetNameForLogonSessionHelper(_LSAP_LOGON_SESSION *,_LARGE_INTEGER *,ulong,_LSAP_DS_NAME_MAP * *,int)

- ea: `0x180004c20`
- end: `0x180005a98`
- name: `?LsapGetNameForLogonSessionHelper@@YAJPEAU_LSAP_LOGON_SESSION@@PEAT_LARGE_INTEGER@@KPEAPEAU_LSAP_DS_NAME_MAP@@H@Z`
- size: `3704`
- prototype: `__int64 __usercall@<rax>(struct _LSAP_LOGON_SESSION *@<rcx>, union _LARGE_INTEGER *@<rdx>, unsigned int@<r8d>, struct _LSAP_DS_NAME_MAP **@<r9>, int)`
- caller_count: `2`
- callee_count: `19`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x180004140`
- `0x180004a50`

## callees

- `0x180003890`
- `0x180003afc`
- `0x180003bd0`
- `0x180004c20`
- `0x180005aa0`
- `0x180007268`
- `0x180009330`
- `0x180009470`
- `0x18000c300`
- `0x180011278`
- `0x180016f70`
- `0x1800b86d0`
- `0x1800bb180`
- `0x1800bd6e0`
- `0x1800cbac4`
- `0x1800cd01c`
- `0x1800cd378`
- `0x18014a6b0`
- `0x18014d010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x1800059a9`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x1800059a9`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x18000591c`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x18000591c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800054cf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005542`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000589f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800054cf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005542`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000589f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800054fe`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000550c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800054fe`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000550c`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18000575d`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800057e5`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18000575d`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800057e5`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x18000517a`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x180005328`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x18000517a`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x180005328`
- `ntdll!RtlFreeHeap` at `0x180004db4`
- `ntdll!RtlFreeHeap` at `0x180004db4`
- `ntdll!RtlSetLastWin32ErrorAndNtStatusFromNtStatus` at `0x1800057c3`
- `ntdll!RtlSetLastWin32ErrorAndNtStatusFromNtStatus` at `0x1800057c3`
- `ntdll!RtlGetLastWin32Error` at `0x180005748`
- `ntdll!RtlGetLastWin32Error` at `0x180005748`
- `ntdll!RtlConvertExclusiveToShared` at `0x18000545b`
- `ntdll!RtlConvertExclusiveToShared` at `0x18000545b`
- `ntdll!RtlConvertSharedToExclusive` at `0x1800052ee`
- `ntdll!RtlConvertSharedToExclusive` at `0x180005411`
- `ntdll!RtlConvertSharedToExclusive` at `0x1800055ca`
- `ntdll!RtlConvertSharedToExclusive` at `0x1800055e1`
- `ntdll!RtlConvertSharedToExclusive` at `0x1800052ee`
- `ntdll!RtlConvertSharedToExclusive` at `0x180005411`
- `ntdll!RtlConvertSharedToExclusive` at `0x1800055ca`
- `ntdll!RtlConvertSharedToExclusive` at `0x1800055e1`
- `ntdll!RtlAcquireResourceExclusive` at `0x180005607`
- `ntdll!RtlAcquireResourceExclusive` at `0x1800057fe`
- `ntdll!RtlAcquireResourceExclusive` at `0x180005a35`
- `ntdll!RtlAcquireResourceExclusive` at `0x180005607`
- `ntdll!RtlAcquireResourceExclusive` at `0x1800057fe`
- `ntdll!RtlAcquireResourceExclusive` at `0x180005a35`
- `ntdll!RtlReleaseResource` at `0x180004ce2`
- `ntdll!RtlReleaseResource` at `0x180004d40`
- `ntdll!RtlReleaseResource` at `0x180004dee`
- `ntdll!RtlReleaseResource` at `0x180004e6e`
- `ntdll!RtlReleaseResource` at `0x180004e8e`
- `ntdll!RtlReleaseResource` at `0x18000500d`
- `ntdll!RtlReleaseResource` at `0x1800050f2`
- `ntdll!RtlReleaseResource` at `0x18000510c`
- `ntdll!RtlReleaseResource` at `0x1800051cf`
- `ntdll!RtlReleaseResource` at `0x180005239`
- `ntdll!RtlReleaseResource` at `0x18000528d`
- `ntdll!RtlReleaseResource` at `0x180005441`
- `ntdll!RtlReleaseResource` at `0x1800054a7`
- `ntdll!RtlReleaseResource` at `0x180005534`
- `ntdll!RtlReleaseResource` at `0x180005573`
- `ntdll!RtlReleaseResource` at `0x180005634`
- `ntdll!RtlReleaseResource` at `0x180005a09`
- `ntdll!RtlReleaseResource` at `0x180005a64`
- `ntdll!RtlReleaseResource` at `0x180004ce2`
- `ntdll!RtlReleaseResource` at `0x180004d40`
- `ntdll!RtlReleaseResource` at `0x180004dee`
- `ntdll!RtlReleaseResource` at `0x180004e6e`
- `ntdll!RtlReleaseResource` at `0x180004e8e`
- `ntdll!RtlReleaseResource` at `0x18000500d`
- `ntdll!RtlReleaseResource` at `0x1800050f2`
- `ntdll!RtlReleaseResource` at `0x18000510c`
- `ntdll!RtlReleaseResource` at `0x1800051cf`
- `ntdll!RtlReleaseResource` at `0x180005239`
- `ntdll!RtlReleaseResource` at `0x18000528d`
- `ntdll!RtlReleaseResource` at `0x180005441`
- `ntdll!RtlReleaseResource` at `0x1800054a7`
- `ntdll!RtlReleaseResource` at `0x180005534`
- `ntdll!RtlReleaseResource` at `0x180005573`
- `ntdll!RtlReleaseResource` at `0x180005634`
- `ntdll!RtlReleaseResource` at `0x180005a09`
- `ntdll!RtlReleaseResource` at `0x180005a64`
- `ntdll!RtlAcquireResourceShared` at `0x180004c94`
- `ntdll!RtlAcquireResourceShared` at `0x18000520c`
- `ntdll!RtlAcquireResourceShared` at `0x1800058e3`
- `ntdll!RtlAcquireResourceShared` at `0x180004c94`
- `ntdll!RtlAcquireResourceShared` at `0x18000520c`
- `ntdll!RtlAcquireResourceShared` at `0x1800058e3`
- `ntdll!RtlNtStatusToDosError` at `0x1800054f0`
- `ntdll!RtlNtStatusToDosError` at `0x1800054f0`
- `ntdll!RtlGetLastNtStatus` at `0x180005518`
- `ntdll!RtlGetLastNtStatus` at `0x180005729`
- `ntdll!RtlGetLastNtStatus` at `0x18000587a`
- `ntdll!RtlGetLastNtStatus` at `0x180005518`
- `ntdll!RtlGetLastNtStatus` at `0x180005729`
- `ntdll!RtlGetLastNtStatus` at `0x18000587a`
- `ntdll!RtlCompareUnicodeString` at `0x1800050b1`
- `ntdll!RtlCompareUnicodeString` at `0x1800050cf`
- `ntdll!RtlCompareUnicodeString` at `0x1800050b1`
- `ntdll!RtlCompareUnicodeString` at `0x1800050cf`
- `ntdll!RtlEqualUnicodeString` at `0x18000503a`
- `ntdll!RtlEqualUnicodeString` at `0x1800051b7`
- `ntdll!RtlEqualUnicodeString` at `0x18000503a`
- `ntdll!RtlEqualUnicodeString` at `0x1800051b7`
- `ntdll!RtlInitUnicodeString` at `0x180005097`
- `ntdll!RtlInitUnicodeString` at `0x180005196`
- `ntdll!RtlInitUnicodeString` at `0x180005344`
- `ntdll!RtlInitUnicodeString` at `0x18000547a`
- `ntdll!RtlInitUnicodeString` at `0x180005097`
- `ntdll!RtlInitUnicodeString` at `0x180005196`
- `ntdll!RtlInitUnicodeString` at `0x180005344`
- `ntdll!RtlInitUnicodeString` at `0x18000547a`
- `logoncli!DsGetDcNameW` at `0x1800051f7`
- `logoncli!DsGetDcNameW` at `0x1800051f7`
- `netutils!NetApiBufferFree` at `0x18000526b`
- `netutils!NetApiBufferFree` at `0x18000559f`
- `netutils!NetApiBufferFree` at `0x1800055b5`
- `netutils!NetApiBufferFree` at `0x18000526b`
- `netutils!NetApiBufferFree` at `0x18000559f`
- `netutils!NetApiBufferFree` at `0x1800055b5`
- `ext-ms-win-secur32-translatename-l1-1-0!SecpTranslateName` at `0x18000570f`
- `ext-ms-win-secur32-translatename-l1-1-0!SecpTranslateName` at `0x1800057a6`
- `ext-ms-win-secur32-translatename-l1-1-0!SecpTranslateName` at `0x18000570f`
- `ext-ms-win-secur32-translatename-l1-1-0!SecpTranslateName` at `0x1800057a6`

## pseudocode

```c
NTSTATUS __fastcall LsapGetNameForLogonSessionHelper(
        struct _LSAP_LOGON_SESSION *a1,
        union _LARGE_INTEGER *a2,
        int a3,
        struct _LSAP_DS_NAME_MAP **a4,
        int a5)
{
  __int64 v5; // rsi
  void *v9; // r9
  int v10; // ecx
  BOOL v11; // eax
  __int64 v12; // rbx
  NTSTATUS result; // eax
  char *v14; // r13
  LONGLONG *v15; // rcx
  int v16; // ebx
  __int64 v17; // r13
  int v18; // eax
  int v19; // eax
  unsigned int v20; // ecx
  __int64 v21; // rdx
  DWORD *p_nSize; // r12
  unsigned __int64 v23; // r8
  __int64 v24; // rcx
  unsigned __int64 v25; // rcx
  void *v26; // rsp
  void *v27; // rsp
  size_t v28; // r8
  const void *v29; // rdx
  size_t v30; // r8
  const void *v31; // rdx
  unsigned __int64 v32; // rcx
  int v33; // r13d
  DWORD *v34; // rcx
  int NameForInternetUserSid; // eax
  __int64 v36; // rsi
  struct _LSAP_DS_NAME_MAP *DsNameMap; // r12
  void *v38; // rcx
  int v39; // eax
  DWORD *v40; // rax
  BOOL v41; // ebx
  DWORD LastError; // ebx
  ULONG v43; // eax
  unsigned int v44; // edx
  int FormatsForLogon; // ebx
  __int64 i; // rcx
  PVOID v47; // r13
  int v48; // eax
  int v49; // eax
  DWORD v50; // eax
  char v51; // bl
  struct _RTL_BALANCED_NODE *v52; // r13
  struct _LSAP_DS_NAME_MAP *v53; // rbx
  void **v54; // rax
  void *v55; // rcx
  NTSTATUS LastNtStatus; // eax
  void *v57; // rdx
  int v58; // eax
  __int64 v59; // r13
  wchar_t *v60; // rax
  wchar_t *v61; // rax
  __int64 v62; // rbx
  __int64 v63; // rcx
  const void **v64; // rax
  __int64 v65; // rbx
  __int64 v66; // rcx
  __int64 v67; // [rsp+0h] [rbp-30h] BYREF
  int v68; // [rsp+30h] [rbp+0h] BYREF
  DWORD DcNameW; // [rsp+34h] [rbp+4h]
  DWORD nSize; // [rsp+38h] [rbp+8h] BYREF
  struct _RTL_BALANCED_NODE *v71; // [rsp+40h] [rbp+10h]
  PDOMAIN_CONTROLLER_INFOW DomainControllerInfo; // [rsp+48h] [rbp+18h] BYREF
  PVOID P[2]; // [rsp+50h] [rbp+20h] BYREF
  UNICODE_STRING String2; // [rsp+60h] [rbp+30h] BYREF
  wchar_t *v75; // [rsp+70h] [rbp+40h]
  struct _UNICODE_STRING DestinationString; // [rsp+78h] [rbp+48h] BYREF
  WCHAR Buffer[264]; // [rsp+90h] [rbp+60h] BYREF

  v5 = (unsigned __int16)a3;
  nSize = 0;
  *a4 = 0;
  String2 = 0;
  v41 = (a3 & 0x20000) != 0;
  if ( (unsigned __int16)a3 >= 0xFu )
    return -1073741811;
  if ( (unsigned __int16)a3 == 6 )
  {
    v39 = *((_DWORD *)a1 + 28);
    if ( v39 == 997 )
    {
      if ( *((_DWORD *)a1 + 29) )
        goto LABEL_3;
    }
    else if ( v39 != 995 || *((_DWORD *)a1 + 29) )
    {
      goto LABEL_3;
    }
    return -1073741601;
  }
LABEL_3:
  RtlAcquireResourceShared((PRTL_RESOURCE)((char *)a1 + 16), 1u);
  v10 = *((_DWORD *)a1 + 128);
  if ( (v10 & 0xC) == 0 && (unsigned int)(v5 - 13) <= 1 )
  {
    if ( WPP_GLOBAL_Control != (LsaHandleCache *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 37, WPP_05668a43f07036cee45d35059337a059_Traceguids, 3221225587LL);
    RtlReleaseResource((PRTL_RESOURCE)((char *)a1 + 16));
    return -1073741709;
  }
  if ( (v10 & 4) == 0 )
  {
LABEL_5:
    v11 = 0;
    if ( (*((_BYTE *)a1 + 512) & 8) == 0 )
      v11 = v41;
    v12 = *((_QWORD *)a1 + v5 + 49);
    if ( v12 && !v11 )
    {
      _InterlockedIncrement((volatile signed __int32 *)(v12 + 16));
      RtlReleaseResource((PRTL_RESOURCE)((char *)a1 + 16));
      result = 0;
      *a4 = (struct _LSAP_DS_NAME_MAP *)v12;
      return result;
    }
    v17 = *((_QWORD *)a1 + 51);
    if ( !v17 )
    {
      RtlConvertSharedToExclusive((PRTL_RESOURCE)((char *)a1 + 16));
      v17 = *((_QWORD *)a1 + 51);
      if ( !v17 )
      {
        LsapSetSamAccountNameForLogonSession(a1);
        v17 = *((_QWORD *)a1 + 51);
        if ( !v17 )
        {
          RtlReleaseResource((PRTL_RESOURCE)((char *)a1 + 16));
          return -1073741801;
        }
      }
      RtlConvertExclusiveToShared((PRTL_RESOURCE)((char *)a1 + 16));
    }
    if ( (_DWORD)v5 == 2 )
    {
      *a4 = (struct _LSAP_DS_NAME_MAP *)v17;
      _InterlockedIncrement((volatile signed __int32 *)(v17 + 16));
      RtlReleaseResource((PRTL_RESOURCE)((char *)a1 + 16));
      return 0;
    }
    if ( (unsigned int)v5 > 0xC || (v18 = 4360, !_bittest(&v18, v5)) )
    {
LABEL_32:
      v20 = *((unsigned __int16 *)a1 + 88) + 4;
      v21 = v20 + *(unsigned __int16 *)(v17 + 24);
      DcNameW = v21;
      if ( (unsigned int)v21 < v20 )
      {
        RtlReleaseResource((PRTL_RESOURCE)((char *)a1 + 16));
        return -1073741675;
      }
      p_nSize = 0;
      if ( (_DWORD)v21 )
      {
        v75 = (wchar_t *)(unsigned int)v21;
        if ( (unsigned int)v21 <= (unsigned __int64)g_ulMaxStackAllocSize )
        {
          v23 = (unsigned int)v21 + g_ulAdditionalProbeSize + 8;
          if ( v23 >= (unsigned int)v21 )
          {
            if ( (unsigned int)VerifyStackAvailable((unsigned int)v21 + g_ulAdditionalProbeSize + 8, v21, v23, v9) )
            {
              v24 = (__int64)v75 + 23;
              if ( (wchar_t *)((char *)v75 + 23) <= v75 + 4 )
                v24 = 0xFFFFFFFFFFFFFF0LL;
              v25 = v24 & 0xFFFFFFFFFFFFFFF0uLL;
              v26 = alloca(v25);
              v27 = alloca(v25);
              p_nSize = (DWORD *)&v68;
              if ( &v67 != (__int64 *)-48LL )
              {
                v68 = 1801679955;
                p_nSize = &nSize;
                if ( &nSize )
                {
LABEL_46:
                  if ( !p_nSize )
                  {
                    RtlReleaseResource((PRTL_RESOURCE)((char *)a1 + 16));
                    return -1073741670;
                  }
                  v28 = *((unsigned __int16 *)a1 + 88);
                  v29 = (const void *)*((_QWORD *)a1 + 23);
                  LODWORD(DomainControllerInfo) = 0;
                  LODWORD(v71) = 0;
                  memcpy_0(p_nSize, v29, v28);
                  *((_WORD *)p_nSize + ((unsigned __int64)*((unsigned __int16 *)a1 + 88) >> 1)) = 0;
                  v30 = *(unsigned __int16 *)(v17 + 24);
                  v31 = *(const void **)(v17 + 32);
                  P[0] = (char *)p_nSize + 2 * ((unsigned __int64)*((unsigned __int16 *)a1 + 88) >> 1) + 2;
                  memcpy_0(P[0], v31, v30);
                  v32 = *(unsigned __int16 *)(v17 + 24);
                  v33 = a5;
                  *((_WORD *)P[0] + (v32 >> 1)) = 0;
                  if ( !a5 )
                  {
                    if ( (*((_BYTE *)a1 + 512) & 0xC) != 0 )
                      goto LABEL_65;
                    DestinationString = 0;
                    if ( !dword_1801A0838 )
                    {
                      RtlInitUnicodeString(&::DestinationString, LocalizedNtAuthorityNameString);
                      dword_1801A0838 = 1;
                      stru_1801A1248 = NTAuthorityName;
                    }
                    RtlInitUnicodeString(&DestinationString, (PCWSTR)p_nSize);
                    if ( !RtlCompareUnicodeString(&DestinationString, &::DestinationString, 1u)
                      || !RtlCompareUnicodeString(&DestinationString, &stru_1801A1248, 1u) )
                    {
LABEL_65:
                      v33 = 1;
                    }
                  }
                  if ( (_DWORD)v5 != 12 )
                    goto LABEL_54;
                  if ( !v33 )
                  {
                    DomainControllerInfo = 0;
                    nSize = 260;
                    if ( !GetComputerNameExW(ComputerNameNetBIOS, Buffer, &nSize) )
                    {
                      RtlReleaseResource((PRTL_RESOURCE)((char *)a1 + 16));
                      if ( *(p_nSize - 2) == 1885431112 )
                        ((void (__fastcall *)(DWORD *))g_pfnFree)(p_nSize - 2);
                      LastError = GetLastError();
                      goto LABEL_113;
                    }
                    RtlInitUnicodeString(&String2, Buffer);
                    LODWORD(v71) = 1;
                    if ( !RtlEqualUnicodeString((PCUNICODE_STRING)a1 + 11, &String2, 1u) )
                    {
                      RtlReleaseResource((PRTL_RESOURCE)((char *)a1 + 16));
                      DcNameW = DsGetDcNameW(0, (LPCWSTR)p_nSize, 0, 0, 0x20u, &DomainControllerInfo);
                      RtlAcquireResourceShared((PRTL_RESOURCE)((char *)a1 + 16), 1u);
                      v36 = *((_QWORD *)a1 + 61);
                      if ( v36 && v36 != v12 )
                      {
                        _InterlockedIncrement((volatile signed __int32 *)(v36 + 16));
                        RtlReleaseResource((PRTL_RESOURCE)((char *)a1 + 16));
                        if ( *(p_nSize - 2) == 1885431112 )
                          ((void (__fastcall *)(DWORD *))g_pfnFree)(p_nSize - 2);
                        if ( !DcNameW )
                          NetApiBufferFree(DomainControllerInfo);
                        *a4 = (struct _LSAP_DS_NAME_MAP *)v36;
                        return 0;
                      }
                      LastError = DcNameW;
                      if ( DcNameW )
                      {
                        RtlReleaseResource((PRTL_RESOURCE)((char *)a1 + 16));
LABEL_117:
                        if ( *(p_nSize - 2) == 1885431112 )
                          ((void (*)(void))g_pfnFree)();
LABEL_113:
                        v43 = RtlNtStatusToDosError(-1073741823);
                        SetLastError(v43);
                        SetLastError(LastError);
                        return RtlGetLastNtStatus();
                      }
                      if ( (DomainControllerInfo->Flags & 0x10) == 0 )
                      {
                        RtlReleaseResource((PRTL_RESOURCE)((char *)a1 + 16));
                        if ( *(p_nSize - 2) == 1885431112 )
                          ((void (__fastcall *)(DWORD *))g_pfnFree)(p_nSize - 2);
                        NetApiBufferFree(DomainControllerInfo);
                        return -1073741709;
                      }
                      NetApiBufferFree(DomainControllerInfo);
                    }
                  }
                  if ( *((_QWORD *)a1 + 56) )
                  {
                    RtlConvertSharedToExclusive((PRTL_RESOURCE)((char *)a1 + 16));
                    v44 = 7;
                  }
                  else
                  {
                    if ( !*((_QWORD *)a1 + 58) )
                    {
                      if ( v33 )
                      {
                        RtlReleaseResource((PRTL_RESOURCE)((char *)a1 + 16));
                        goto LABEL_68;
                      }
                      LODWORD(DomainControllerInfo) = 1;
                      LODWORD(v5) = 9;
LABEL_54:
                      RtlReleaseResource((PRTL_RESOURCE)((char *)a1 + 16));
                      if ( !v33 )
                      {
                        if ( (_DWORD)v71 )
                          goto LABEL_56;
                        nSize = 260;
                        if ( GetComputerNameExW(ComputerNameNetBIOS, Buffer, &nSize) )
                        {
                          RtlInitUnicodeString(&String2, Buffer);
LABEL_56:
                          if ( RtlEqualUnicodeString((PCUNICODE_STRING)a1 + 11, &String2, 1u) )
                          {
                            v34 = p_nSize - 2;
                            if ( *(p_nSize - 2) != 1885431112 )
                              return -1073741709;
LABEL_58:
                            ((void (__fastcall *)(DWORD *))g_pfnFree)(v34);
                            return -1073741709;
                          }
                          for ( i = 0; ; i = (unsigned int)(i + 1) )
                          {
                            if ( (unsigned int)i >= 2 )
                            {
                              v47 = P[0];
                              goto LABEL_138;
                            }
                            if ( (_DWORD)v5 == *((_DWORD *)&LogonFormats + i) )
                              break;
                          }
                          v47 = P[0];
                          FormatsForLogon = LsapGetFormatsForLogon(
                                              a1,
                                              (unsigned __int16 *)p_nSize,
                                              (unsigned __int16 *)P[0],
                                              v5,
                                              a4);
                          if ( FormatsForLogon >= 0 )
                            goto LABEL_200;
LABEL_138:
                          v48 = LsapImpersonateClientEx(0);
                          LOBYTE(v68) = 1;
                          FormatsForLogon = v48;
                          if ( v48 < 0 )
                          {
                            if ( v48 != -1073741659 )
                              goto LABEL_200;
                            v49 = LsapImpersonateNetworkService();
                            LOBYTE(v68) = 1;
                            FormatsForLogon = v49;
                            if ( v49 < 0 )
                              goto LABEL_200;
                          }
                          while ( 1 )
                          {
                            nSize = 260;
                            v71 = (struct _RTL_BALANCED_NODE *)Buffer;
                            if ( !(unsigned __int8)IsSecpTranslateNameExPresent() )
                            {
                              RtlSetLastWin32ErrorAndNtStatusFromNtStatus(-1073741637);
                              v51 = v68;
                              v50 = 0;
                              DcNameW = 0;
                              goto LABEL_153;
                            }
                            v50 = (unsigned __int8)SecpTranslateName(p_nSize, v47, 2, (unsigned int)v5, Buffer, &nSize);
                            DcNameW = v50;
                            if ( (_BYTE)v50 )
                              goto LABEL_149;
                            if ( RtlGetLastNtStatus() == -1073741789 )
                              break;
                            v51 = v68;
                            if ( !(_BYTE)v68 || RtlGetLastWin32Error() != 5 )
                              goto LABEL_152;
                            RevertToSelf();
                            LOBYTE(v68) = 0;
                          }
                          v71 = (struct _RTL_BALANCED_NODE *)LsapAllocate(2LL * nSize);
                          if ( v71 )
                          {
                            v50 = (unsigned __int8)SecpTranslateName(p_nSize, v47, 2, (unsigned int)v5, v71, &nSize);
                            DcNameW = (unsigned __int8)v50;
LABEL_149:
                            v51 = v68;
                            goto LABEL_153;
                          }
                          v51 = v68;
LABEL_152:
                          v50 = DcNameW;
LABEL_153:
                          if ( v51 )
                          {
                            RevertToSelf();
                            v50 = DcNameW;
                          }
                          if ( v50 )
                          {
                            RtlAcquireResourceExclusive((PRTL_RESOURCE)((char *)a1 + 16), 1u);
                            v52 = v71;
                            goto LABEL_157;
                          }
                          DcNameW = 0;
                          LastNtStatus = RtlGetLastNtStatus();
                          FormatsForLogon = LastNtStatus;
                          if ( (_DWORD)v5 == 3 )
                          {
                            if ( LastNtStatus != -1073741709 )
                            {
                              if ( LastNtStatus != -1073741823 )
                              {
                                v58 = DcNameW;
                                goto LABEL_189;
                              }
                              if ( GetLastError() != 1355 )
                              {
                                v52 = v71;
                                goto LABEL_198;
                              }
                            }
                            v58 = 1;
                            DcNameW = 1;
                          }
                          else
                          {
                            v58 = DcNameW;
                          }
                          if ( FormatsForLogon == -1073741709 )
                          {
                            if ( (_DWORD)v5 != 8 )
                            {
                              v52 = v71;
LABEL_193:
                              if ( !v58 )
                              {
LABEL_198:
                                if ( v52 != (struct _RTL_BALANCED_NODE *)Buffer )
                                  LsapSubProv_FreeRoutine(v52, v57);
LABEL_200:
                                if ( !(_DWORD)DomainControllerInfo || FormatsForLogon < 0 )
                                {
LABEL_128:
                                  if ( *(p_nSize - 2) == 1885431112 )
                                    ((void (__fastcall *)(DWORD *))g_pfnFree)(p_nSize - 2);
                                  return FormatsForLogon;
                                }
                                RtlAcquireResourceExclusive((PRTL_RESOURCE)((char *)a1 + 16), 1u);
                                FormatsForLogon = LsapCreateDnsNameFromCanonicalName(a1, v5, a4);
                                _InterlockedDecrement((volatile signed __int32 *)(*((_QWORD *)a1 + (unsigned int)v5 + 49)
                                                                                + 16LL));
LABEL_127:
                                RtlReleaseResource((PRTL_RESOURCE)((char *)a1 + 16));
                                goto LABEL_128;
                              }
LABEL_194:
                              RtlAcquireResourceExclusive((PRTL_RESOURCE)((char *)a1 + 16), 1u);
                              if ( FormatsForLogon )
                              {
                                String2.Buffer = 0;
                                *(_DWORD *)&String2.Length = 0;
                                goto LABEL_158;
                              }
LABEL_157:
                              String2.Buffer = (PWSTR)v52;
                              String2.Length = 2 * (nSize - 1);
                              String2.MaximumLength = String2.Length + 2;
LABEL_158:
                              v53 = LsapCreateDsNameMap(&String2, 0, v5);
                              if ( v53 )
                              {
                                v54 = (void **)((char *)a1 + 8 * (unsigned int)v5 + 392);
                                v55 = *v54;
                                *(_QWORD *)&DestinationString.Length = v54;
                                if ( v55 )
                                {
                                  LsapDerefDsNameMap(v55);
                                  v54 = *(void ***)&DestinationString.Length;
                                }
                                *v54 = v53;
                                _InterlockedIncrement((volatile signed __int32 *)v53 + 4);
                                *a4 = v53;
                                FormatsForLogon = 0;
                              }
                              else
                              {
                                FormatsForLogon = -1073741801;
                              }
                              RtlReleaseResource((PRTL_RESOURCE)((char *)a1 + 16));
                              goto LABEL_198;
                            }
                            RtlAcquireResourceShared((PRTL_RESOURCE)((char *)a1 + 16), 1u);
                            v59 = *((_QWORD *)a1 + 51);
                            if ( !v59 || (P[0] = *((PVOID *)a1 + 61)) == 0 )
                            {
                              v52 = v71;
                              goto LABEL_187;
                            }
                            v60 = wcschr(*(const wchar_t **)(v59 + 32), 0x5Cu);
                            if ( v60 )
                              v61 = v60 + 1;
                            else
                              v61 = *(wchar_t **)(v59 + 32);
                            v75 = v61;
                            v62 = -1;
                            do
                              ++v62;
                            while ( v61[v62] );
                            *(_QWORD *)&DestinationString.Length = v62;
                            v63 = (unsigned int)v62 + (*((unsigned __int16 *)P[0] + 12) >> 1) + 2;
                            nSize = v63;
                            if ( (unsigned int)v63 > 0x104 )
                            {
                              if ( v71 != (struct _RTL_BALANCED_NODE *)Buffer )
                              {
                                LsapSubProv_FreeRoutine(v71, Buffer);
                                v63 = nSize;
                              }
                              v52 = (struct _RTL_BALANCED_NODE *)LsapAllocate(2 * v63);
                              if ( !v52 )
                              {
                                FormatsForLogon = -1073741801;
                                goto LABEL_187;
                              }
                              LODWORD(v63) = nSize;
                            }
                            else
                            {
                              v52 = (struct _RTL_BALANCED_NODE *)Buffer;
                            }
                            _o_wcsncpy_s(v52, (unsigned int)v63, v75, (unsigned int)v62);
                            v64 = (const void **)P[0];
                            *((_WORD *)v52->Children + (unsigned int)v62) = 64;
                            v65 = (unsigned int)(*(_DWORD *)&DestinationString.Length + 1);
                            memcpy_0((char *)v52 + 2 * v65, v64[4], *((unsigned __int16 *)v64 + 12));
                            v66 = v65 + ((unsigned __int64)*((unsigned __int16 *)P[0] + 12) >> 1);
                            FormatsForLogon = 0;
                            *((_WORD *)v52->Children + v66) = 0;
LABEL_187:
                            RtlReleaseResource((PRTL_RESOURCE)((char *)a1 + 16));
                            v58 = DcNameW;
                            goto LABEL_190;
                          }
LABEL_189:
                          v52 = v71;
LABEL_190:
                          if ( !FormatsForLogon )
                            goto LABEL_194;
                          goto LABEL_193;
                        }
                        LastError = GetLastError();
                        goto LABEL_117;
                      }
LABEL_68:
                      v34 = p_nSize - 2;
                      if ( *(p_nSize - 2) != 1885431112 )
                        return -1073741709;
                      goto LABEL_58;
                    }
                    RtlConvertSharedToExclusive((PRTL_RESOURCE)((char *)a1 + 16));
                    v44 = 9;
                  }
                  FormatsForLogon = LsapCreateDnsNameFromCanonicalName(a1, v44, a4);
                  goto LABEL_127;
                }
              }
            }
            LODWORD(v21) = DcNameW;
          }
        }
      }
      if ( (unsigned __int64)(unsigned int)v21 + 8 >= (unsigned int)v21 )
      {
        v40 = (DWORD *)((__int64 (*)(void))g_pfnAllocate)();
        p_nSize = v40;
        if ( v40 )
        {
          *v40 = 1885431112;
          p_nSize = v40 + 2;
        }
      }
      goto LABEL_46;
    }
    v19 = *((_DWORD *)a1 + 28);
    if ( v19 == 999 )
    {
      if ( !*((_DWORD *)a1 + 29) )
        goto LABEL_35;
    }
    else if ( v19 == 996 && !*((_DWORD *)a1 + 29) )
    {
      goto LABEL_35;
    }
    if ( (*((_DWORD *)a1 + 78) & 0x40000000) == 0 )
      goto LABEL_32;
LABEL_35:
    RtlReleaseResource((PRTL_RESOURCE)((char *)a1 + 16));
    return LsapCreateCachedMachineNameMap(a1, v5, a4);
  }
  v9 = (void *)*((_QWORD *)a1 + 28);
  *(_OWORD *)P = 0;
  if ( !v9 )
  {
    v16 = -1073741709;
    goto LABEL_18;
  }
  _mm_lfence();
  v14 = (char *)a1 + 8 * v5;
  v15 = (LONGLONG *)*((_QWORD *)v14 + 49);
  if ( v15 && !v41 && *v15 >= a2->QuadPart )
  {
    v16 = 0;
    goto LABEL_18;
  }
  NameForInternetUserSid = LsapGetNameForInternetUserSid(v9, v5, (struct _UNICODE_STRING *)P);
  v16 = NameForInternetUserSid;
  if ( NameForInternetUserSid < 0 )
  {
    if ( NameForInternetUserSid == -1073741637 )
    {
      v16 = -1073741709;
      goto LABEL_18;
    }
    v16 = 0;
    *(_OWORD *)P = 0;
  }
  DsNameMap = LsapCreateDsNameMap((struct _UNICODE_STRING *)P, 0, v5);
  if ( DsNameMap )
  {
    RtlConvertSharedToExclusive((PRTL_RESOURCE)((char *)a1 + 16));
    v38 = (void *)*((_QWORD *)v14 + 49);
    if ( v38 )
      LsapDerefDsNameMap(v38);
    *((_QWORD *)v14 + 49) = DsNameMap;
  }
  else
  {
    v16 = -1073741801;
  }
LABEL_18:
  if ( P[1] )
  {
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, P[1]);
    *(_OWORD *)P = 0;
  }
  if ( v16 >= 0 )
  {
    v41 = 0;
    goto LABEL_5;
  }
  if ( WPP_GLOBAL_Control != (LsaHandleCache *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      38,
      WPP_05668a43f07036cee45d35059337a059_Traceguids,
      (unsigned int)v16);
  RtlReleaseResource((PRTL_RESOURCE)((char *)a1 + 16));
  return v16;
}

```

## disassembly

```asm
0x180004c20  push    rbp
0x180004c22  push    rsi
0x180004c23  push    rdi
0x180004c24  push    r12
0x180004c26  push    r13
0x180004c28  push    r14
0x180004c2a  push    r15
0x180004c2c  sub     rsp, 2B0h
0x180004c33  lea     rbp, [rsp+30h]
0x180004c38  mov     [rbp+2B0h+arg_8], rbx
0x180004c3f  mov     rax, cs:__security_cookie
0x180004c46  xor     rax, rbp
0x180004c49  mov     [rbp+2B0h+var_40], rax
0x180004c50  xor     r13d, r13d
0x180004c53  movzx   esi, r8w
0x180004c57  mov     [rbp+2B0h+nSize], r13d
0x180004c5b  xorps   xmm0, xmm0
0x180004c5e  mov     [r9], r13
0x180004c61  mov     r15, r9
0x180004c64  mov     r12, rdx
0x180004c67  mov     rdi, rcx
0x180004c6a  mov     ebx, r13d
0x180004c6d  movups  xmmword ptr [rbp+2B0h+String2.Length], xmm0
0x180004c71  bt      r8d, 11h
0x180004c76  jb      loc_1800053C4
0x180004c7c  cmp     esi, 0Fh
0x180004c7f  jnb     loc_1800053CE
0x180004c85  cmp     esi, 6
0x180004c88  jz      loc_180005355
0x180004c8e  mov     dl, 1; Wait
0x180004c90  add     rcx, 10h; Resource
0x180004c94  call    cs:__imp_RtlAcquireResourceShared
0x180004c9b  nop     dword ptr [rax+rax+00h]
0x180004ca0  mov     ecx, [rdi+200h]
0x180004ca6  test    cl, 0Ch
0x180004ca9  jz      short loc_180004D1D
0x180004cab  test    cl, 4
0x180004cae  jnz     loc_180004D53
0x180004cb4  test    byte ptr [rdi+200h], 8
0x180004cbb  mov     eax, r13d
0x180004cbe  cmovz   eax, ebx
0x180004cc1  mov     rbx, [rdi+rsi*8+188h]
0x180004cc9  test    rbx, rbx
0x180004ccc  jz      loc_180004E08
0x180004cd2  test    eax, eax
0x180004cd4  jnz     loc_180004E08
0x180004cda  lock inc dword ptr [rbx+10h]
0x180004cde  lea     rcx, [rdi+10h]; Resource
0x180004ce2  call    cs:__imp_RtlReleaseResource
0x180004ce9  nop     dword ptr [rax+rax+00h]
0x180004cee  xor     eax, eax
0x180004cf0  mov     [r15], rbx
0x180004cf3  mov     rcx, [rbp+2B0h+var_40]
0x180004cfa  xor     rcx, rbp; StackCookie
0x180004cfd  call    __security_check_cookie
0x180004d02  mov     rbx, [rbp+2B0h+arg_8]
0x180004d09  lea     rsp, [rbp+280h]
0x180004d10  pop     r15
0x180004d12  pop     r14
0x180004d14  pop     r13
0x180004d16  pop     r12
0x180004d18  pop     rdi
0x180004d19  pop     rsi
0x180004d1a  pop     rbp
0x180004d1b  retn
0x180004d1d  lea     eax, [rsi-0Dh]
0x180004d20  cmp     eax, 1
0x180004d23  ja      short loc_180004CAB
0x180004d25  mov     rcx, cs:WPP_GLOBAL_Control
0x180004d2c  lea     rax, WPP_GLOBAL_Control
0x180004d33  cmp     rcx, rax
0x180004d36  jnz     loc_1800053E3
0x180004d3c  lea     rcx, [rdi+10h]; Resource
0x180004d40  call    cs:__imp_RtlReleaseResource
0x180004d47  nop     dword ptr [rax+rax+00h]
0x180004d4c  mov     eax, 0C0000073h
0x180004d51  jmp     short loc_180004CF3
0x180004d53  mov     r9, [rdi+0E0h]
0x180004d5a  xorps   xmm0, xmm0
0x180004d5d  movups  xmmword ptr [rbp+2B0h+P], xmm0
0x180004d61  test    r9, r9
0x180004d64  jz      loc_180004E01
0x180004d6a  lfence
0x180004d6d  lea     r13, [rdi+rsi*8]
0x180004d71  mov     rcx, [r13+188h]
0x180004d78  test    rcx, rcx
0x180004d7b  jz      loc_180005131
0x180004d81  test    ebx, ebx
0x180004d83  jnz     loc_180005131
0x180004d89  mov     rax, [r12]
0x180004d8d  cmp     [rcx], rax
0x180004d90  jl      loc_180005131
0x180004d96  xor     r13d, r13d
0x180004d99  mov     ebx, r13d
0x180004d9c  mov     r8, [rbp+2B0h+P+8]; P
0x180004da0  test    r8, r8
0x180004da3  jz      short loc_180004DC7
0x180004da5  mov     rcx, gs:60h
0x180004dae  xor     edx, edx; Flags
0x180004db0  mov     rcx, [rcx+30h]; HeapHandle
0x180004db4  call    cs:__imp_RtlFreeHeap
0x180004dbb  nop     dword ptr [rax+rax+00h]
0x180004dc0  xorps   xmm0, xmm0
0x180004dc3  movups  xmmword ptr [rbp+2B0h+P], xmm0
0x180004dc7  test    ebx, ebx
0x180004dc9  js      short loc_180004DD3
0x180004dcb  mov     ebx, r13d
0x180004dce  jmp     loc_180004CB4
0x180004dd3  mov     rcx, cs:WPP_GLOBAL_Control
0x180004dda  lea     rax, WPP_GLOBAL_Control
0x180004de1  cmp     rcx, rax
0x180004de4  jnz     loc_1800052A0
0x180004dea  lea     rcx, [rdi+10h]; Resource
0x180004dee  call    cs:__imp_RtlReleaseResource
0x180004df5  nop     dword ptr [rax+rax+00h]
0x180004dfa  mov     eax, ebx
0x180004dfc  jmp     loc_180004CF3
0x180004e01  mov     ebx, 0C0000073h
0x180004e06  jmp     short loc_180004D9C
0x180004e08  mov     r13, [rdi+198h]
0x180004e0f  test    r13, r13
0x180004e12  jz      loc_18000540D
0x180004e18  cmp     esi, 2
0x180004e1b  jz      loc_180005281
0x180004e21  cmp     esi, 0Ch
0x180004e24  ja      short loc_180004E4D
0x180004e26  mov     eax, 1108h
0x180004e2b  bt      eax, esi
0x180004e2e  jnb     short loc_180004E4D
0x180004e30  mov     eax, [rdi+70h]
0x180004e33  cmp     eax, 3E7h
0x180004e38  jz      short loc_180004E84
0x180004e3a  cmp     eax, 3E4h
0x180004e3f  jz      short loc_180004EAC
0x180004e41  test    dword ptr [rdi+138h], 40000000h
0x180004e4b  jnz     short loc_180004E8A
0x180004e4d  movzx   ecx, word ptr [rdi+0B0h]
0x180004e54  add     ecx, 4
0x180004e57  cmp     ecx, 4
0x180004e5a  jb      short loc_180004E6A
0x180004e5c  movzx   edx, word ptr [r13+18h]
0x180004e61  add     edx, ecx
0x180004e63  mov     [rbp+2B0h+var_2AC], edx
0x180004e66  cmp     edx, ecx
0x180004e68  jnb     short loc_180004EB4
0x180004e6a  lea     rcx, [rdi+10h]; Resource
0x180004e6e  call    cs:__imp_RtlReleaseResource
0x180004e75  nop     dword ptr [rax+rax+00h]
0x180004e7a  mov     eax, 0C0000095h
0x180004e7f  jmp     loc_180004CF3
0x180004e84  cmp     dword ptr [rdi+74h], 0
0x180004e88  jnz     short loc_180004E41
0x180004e8a  lea     rcx, [rdi+10h]; Resource
0x180004e8e  call    cs:__imp_RtlReleaseResource
0x180004e95  nop     dword ptr [rax+rax+00h]
0x180004e9a  mov     r8, r15; struct _LSAP_DS_NAME_MAP **
0x180004e9d  mov     edx, esi; unsigned int
0x180004e9f  mov     rcx, rdi; struct _LSAP_LOGON_SESSION *
0x180004ea2  call    ?LsapCreateCachedMachineNameMap@@YAJPEAU_LSAP_LOGON_SESSION@@KPEAPEAU_LSAP_DS_NAME_MAP@@@Z; LsapCreateCachedMachineNameMap(_LSAP_LOGON_SESSION *,ulong,_LSAP_DS_NAME_MAP * *)
0x180004ea7  jmp     loc_180004CF3
0x180004eac  cmp     dword ptr [rdi+74h], 0
0x180004eb0  jz      short loc_180004E8A
0x180004eb2  jmp     short loc_180004E41
0x180004eb4  xor     r12d, r12d
0x180004eb7  test    edx, edx
0x180004eb9  jz      loc_18000538E
0x180004ebf  mov     ecx, edx
0x180004ec1  cmp     rcx, cs:g_ulMaxStackAllocSize
0x180004ec8  mov     [rbp+2B0h+var_270], rcx
0x180004ecc  ja      loc_18000538E
0x180004ed2  mov     r8, cs:g_ulAdditionalProbeSize
0x180004ed9  add     r8, 8
0x180004edd  add     r8, rcx
0x180004ee0  cmp     r8, rcx
0x180004ee3  jb      loc_18000538E
0x180004ee9  mov     rcx, r8
0x180004eec  call    VerifyStackAvailable
0x180004ef1  test    eax, eax
0x180004ef3  jz      loc_18000538B
0x180004ef9  mov     rax, [rbp+2B0h+var_270]
0x180004efd  add     rax, 8
0x180004f01  lea     rcx, [rax+0Fh]
0x180004f05  cmp     rcx, rax
0x180004f08  ja      short loc_180004F14
0x180004f0a  mov     rcx, 0FFFFFFFFFFFFFF0h
0x180004f14  and     rcx, 0FFFFFFFFFFFFFFF0h
0x180004f18  mov     rax, rcx
0x180004f1b  call    _alloca_probe
0x180004f20  sub     rsp, rcx
0x180004f23  lea     r12, [rsp+2E0h+var_2B0]
0x180004f28  test    r12, r12
0x180004f2b  jz      loc_18000538B
0x180004f31  mov     dword ptr [r12], 6B637453h
0x180004f39  add     r12, 8
0x180004f3d  jz      loc_18000538B
0x180004f43  test    r12, r12
0x180004f46  jz      loc_1800050EE
0x180004f4c  movzx   r8d, word ptr [rdi+0B0h]; Size
0x180004f54  mov     rcx, r12; void *
0x180004f57  mov     rdx, [rdi+0B8h]; Src
0x180004f5e  mov     dword ptr [rbp+2B0h+var_298], 0
0x180004f65  mov     dword ptr [rbp+2B0h+var_2A0], 0
0x180004f6c  call    memcpy_0
0x180004f71  movzx   ecx, word ptr [rdi+0B0h]
0x180004f78  xor     eax, eax
0x180004f7a  shr     rcx, 1
0x180004f7d  mov     [r12+rcx*2], ax
0x180004f82  movzx   eax, word ptr [rdi+0B0h]
0x180004f89  movzx   r8d, word ptr [r13+18h]; Size
0x180004f8e  mov     rdx, [r13+20h]; Src
0x180004f92  shr     rax, 1
0x180004f95  inc     rax
0x180004f98  lea     rax, [r12+rax*2]
0x180004f9c  mov     rcx, rax; void *
0x180004f9f  mov     [rbp+2B0h+P], rax
0x180004fa3  call    memcpy_0
0x180004fa8  movzx   ecx, word ptr [r13+18h]
0x180004fad  xor     eax, eax
0x180004faf  mov     rdx, [rbp+2B0h+P]
0x180004fb3  mov     r13d, [rbp+2B0h+arg_20]
0x180004fba  shr     rcx, 1
0x180004fbd  mov     [rdx+rcx*2], ax
0x180004fc1  test    r13d, r13d
0x180004fc4  jz      loc_180005074
0x180004fca  cmp     esi, 0Ch
0x180004fcd  jnz     short loc_180005009
0x180004fcf  test    r13d, r13d
0x180004fd2  jz      loc_180005161
0x180004fd8  cmp     qword ptr [rdi+1C0h], 0
0x180004fe0  jnz     loc_1800055C6
0x180004fe6  cmp     qword ptr [rdi+1D0h], 0
0x180004fee  jnz     loc_1800055DD
0x180004ff4  test    r13d, r13d
0x180004ff7  jnz     loc_180005108
0x180004ffd  mov     dword ptr [rbp+2B0h+var_298], 1
0x180005004  mov     esi, 9
0x180005009  lea     rcx, [rdi+10h]; Resource
0x18000500d  call    cs:__imp_RtlReleaseResource
0x180005014  nop     dword ptr [rax+rax+00h]
0x180005019  test    r13d, r13d
0x18000501c  jnz     loc_180005118
0x180005022  cmp     dword ptr [rbp+2B0h+var_2A0], r13d
0x180005026  jz      loc_180005317
0x18000502c  lea     rcx, [rdi+0B0h]; String1
0x180005033  mov     r8b, 1; CaseInsensitive
0x180005036  lea     rdx, [rbp+2B0h+String2]; String2
0x18000503a  call    cs:__imp_RtlEqualUnicodeString
0x180005041  nop     dword ptr [rax+rax+00h]
0x180005046  test    al, al
0x180005048  jz      loc_180005663
0x18000504e  cmp     dword ptr [r12-8], 70616548h
0x180005057  lea     rcx, [r12-8]
0x18000505c  jnz     short loc_18000506A
0x18000505e  mov     rax, cs:g_pfnFree
0x180005065  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000506a  mov     eax, 0C0000073h
0x18000506f  jmp     loc_180004CF3
0x180005074  test    byte ptr [rdi+200h], 0Ch
0x18000507b  jnz     short loc_1800050E3
0x18000507d  cmp     cs:dword_1801A0838, eax
0x180005083  xorps   xmm0, xmm0
0x180005086  movups  xmmword ptr [rbp+2B0h+DestinationString.Length], xmm0
0x18000508a  jz      loc_18000546C
0x180005090  mov     rdx, r12; SourceString
0x180005093  lea     rcx, [rbp+2B0h+DestinationString]; DestinationString
0x180005097  call    cs:__imp_RtlInitUnicodeString
0x18000509e  nop     dword ptr [rax+rax+00h]
0x1800050a3  mov     r8b, 1; CaseInsensitive
0x1800050a6  lea     rdx, DestinationString; String2
0x1800050ad  lea     rcx, [rbp+2B0h+DestinationString]; String1
0x1800050b1  call    cs:__imp_RtlCompareUnicodeString
0x1800050b8  nop     dword ptr [rax+rax+00h]
0x1800050bd  test    eax, eax
0x1800050bf  jz      short loc_1800050E3
0x1800050c1  mov     r8b, 1; CaseInsensitive
0x1800050c4  lea     rdx, stru_1801A1248; String2
0x1800050cb  lea     rcx, [rbp+2B0h+DestinationString]; String1
0x1800050cf  call    cs:__imp_RtlCompareUnicodeString
0x1800050d6  nop     dword ptr [rax+rax+00h]
0x1800050db  test    eax, eax
0x1800050dd  jnz     loc_180004FCA
0x1800050e3  mov     r13d, 1
0x1800050e9  jmp     loc_180004FCA
0x1800050ee  lea     rcx, [rdi+10h]; Resource
0x1800050f2  call    cs:__imp_RtlReleaseResource
0x1800050f9  nop     dword ptr [rax+rax+00h]
0x1800050fe  mov     eax, 0C000009Ah
0x180005103  jmp     loc_180004CF3
0x180005108  lea     rcx, [rdi+10h]; Resource
0x18000510c  call    cs:__imp_RtlReleaseResource
0x180005113  nop     dword ptr [rax+rax+00h]
0x180005118  cmp     dword ptr [r12-8], 70616548h
0x180005121  lea     rcx, [r12-8]
0x180005126  jnz     loc_18000506A
0x18000512c  jmp     loc_18000505E
0x180005131  lea     r8, [rbp+2B0h+P]; struct _UNICODE_STRING *
0x180005135  mov     edx, esi; unsigned int
0x180005137  mov     rcx, r9; Sid
0x18000513a  call    ?LsapGetNameForInternetUserSid@@YAJPEAXKPEAU_UNICODE_STRING@@@Z; LsapGetNameForInternetUserSid(void *,ulong,_UNICODE_STRING *)
0x18000513f  mov     ebx, eax
  ... truncated ...
```
