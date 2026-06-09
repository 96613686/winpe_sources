# CManagerThread::QueueConfig(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,void *,FhBackupType,ulong,int)

- ea: `0x1800065c0`
- end: `0x180006d2f`
- name: `?QueueConfig@CManagerThread@@QEAAJV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEAXW4FhBackupType@@KH@Z`
- size: `1903`
- prototype: `__int64 __fastcall(CConfigDescriptor **, __int64 *, void *, unsigned int, int, int)`
- caller_count: `2`
- callee_count: `22`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800012d0`
- `0x1800079e0`

## callees

- `0x180004e30`
- `0x180004e50`
- `0x1800065c0`
- `0x180006d38`
- `0x180006dd0`
- `0x180007f50`
- `0x1800086e0`
- `0x180009af0`
- `0x18000aa08`
- `0x18000ac14`
- `0x18000bc98`
- `0x18000ca14`
- `0x18000d840`
- `0x18000d910`
- `0x18000d970`
- `0x18000daf0`
- `0x18000f670`
- `0x1800104d0`
- `0x180010558`
- `0x1800105ac`
- `0x1800109d4`
- `0x180013010`

## import_xrefs

- `ADVAPI32!SetThreadToken` at `0x180006ade`
- `ADVAPI32!SetThreadToken` at `0x180006beb`
- `ADVAPI32!SetThreadToken` at `0x180006ade`
- `ADVAPI32!SetThreadToken` at `0x180006beb`
- `ADVAPI32!RegGetValueW` at `0x180006b57`
- `ADVAPI32!RegGetValueW` at `0x180006b57`
- `KERNEL32!GetCurrentProcess` at `0x18000677a`
- `KERNEL32!GetCurrentProcess` at `0x180006783`
- `KERNEL32!GetCurrentProcess` at `0x18000677a`
- `KERNEL32!GetCurrentProcess` at `0x180006783`
- `KERNEL32!GetLastError` at `0x1800067b2`
- `KERNEL32!GetLastError` at `0x180006ae8`
- `KERNEL32!GetLastError` at `0x180006bf5`
- `KERNEL32!GetLastError` at `0x1800067b2`
- `KERNEL32!GetLastError` at `0x180006ae8`
- `KERNEL32!GetLastError` at `0x180006bf5`
- `KERNEL32!SetEvent` at `0x180006cd0`
- `KERNEL32!SetEvent` at `0x180006cd0`
- `KERNEL32!CloseHandle` at `0x18000676a`
- `KERNEL32!CloseHandle` at `0x18000676a`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x1800066ec`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x1800066ec`
- `KERNEL32!EnterCriticalSection` at `0x1800065f1`
- `KERNEL32!EnterCriticalSection` at `0x1800065f1`
- `KERNEL32!LeaveCriticalSection` at `0x180006655`
- `KERNEL32!LeaveCriticalSection` at `0x180006cea`
- `KERNEL32!LeaveCriticalSection` at `0x180006655`
- `KERNEL32!LeaveCriticalSection` at `0x180006cea`
- `KERNEL32!DuplicateHandle` at `0x1800067a8`
- `KERNEL32!DuplicateHandle` at `0x1800067a8`

## string_xrefs

- `0x180006629`: `ImpersonationToken`

## pseudocode

```c
__int64 __fastcall CManagerThread::QueueConfig(
        CConfigDescriptor **a1,
        __int64 *a2,
        void *a3,
        unsigned int a4,
        int a5,
        int a6)
{
  __int64 v9; // r8
  int v11; // r12d
  signed int v12; // edi
  CConfigDescriptor *v13; // rcx
  CConfigDescriptor **v14; // rbx
  __int64 v15; // rcx
  int ConfigDescriptor; // eax
  void *v17; // rcx
  CConfigDescriptor *v18; // rsi
  HANDLE CurrentProcess; // rdi
  HANDLE v20; // rax
  signed int LastError; // eax
  __int64 v22; // rdx
  __int64 v23; // rax
  __int64 v24; // rax
  int v25; // eax
  _QWORD *v26; // rax
  int v27; // ecx
  _QWORD *v28; // rax
  __int64 v29; // r9
  PVOID *v30; // r9
  _QWORD *v31; // rax
  CConfigDescriptor *v32; // rdx
  signed int v33; // eax
  LSTATUS ValueW; // eax
  PVOID *v35; // rcx
  int v36; // r8d
  signed int v37; // eax
  CConfigDescriptor *v38; // r8
  _QWORD *v39; // rax
  CWorkerThread **v40; // rcx
  CWorkerThread *v41; // rcx
  volatile signed __int32 *v42; // rdx
  struct _FILETIME SystemTimeAsFileTime; // [rsp+40h] [rbp-10h] BYREF
  CConfigDescriptor **pcbData; // [rsp+90h] [rbp+40h] BYREF
  __int64 pvData; // [rsp+A0h] [rbp+50h] BYREF
  unsigned int v46; // [rsp+A8h] [rbp+58h]

  v46 = a4;
  pcbData = a1;
  EnterCriticalSection(&CriticalSection);
  SmartPtr<CConfigDescriptor>::SmartPtr<CConfigDescriptor>(&pcbData);
  SystemTimeAsFileTime = 0;
  if ( !a3 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_s(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        44,
        &WPP_a36920fbec7731c49b02dea361b0ee02_Traceguids,
        "ImpersonationToken");
    if ( pcbData )
      SmartPtr<CConfigDescriptor>::RefCounter::Dec_nRefs(pcbData);
    LeaveCriticalSection(&CriticalSection);
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::~CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(a2);
    return 2147942487LL;
  }
  v11 = 0;
  if ( ((a4 - 1) & 0xFFFFFFFD) != 0 )
  {
    v12 = -2147024809;
    v13 = (CConfigDescriptor *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 45, v9, a4, -2147024809);
    goto LABEL_12;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_dS(*((_QWORD *)WPP_GLOBAL_Control + 2), 46, v9, a4, *a2);
  GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
  pvData = ATL::CSimpleStringT<unsigned short,0>::CloneData(*a2 - 24) + 24;
  ConfigDescriptor = CManagerThread::GetConfigDescriptor(v15, &pvData, &pcbData, 1);
  v12 = ConfigDescriptor;
  if ( ConfigDescriptor < 0 )
  {
    v13 = (CConfigDescriptor *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_Sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        47,
        (unsigned int)&WPP_a36920fbec7731c49b02dea361b0ee02_Traceguids,
        *a2,
        ConfigDescriptor);
      v14 = pcbData;
      goto LABEL_110;
    }
LABEL_12:
    v14 = pcbData;
LABEL_110:
    if ( !v14 )
      goto LABEL_118;
    v38 = *v14;
    if ( !*v14 )
      goto LABEL_118;
    v39 = (_QWORD *)*((_QWORD *)v38 + 17);
    if ( v39 )
    {
      if ( *v39 )
        goto LABEL_118;
    }
    if ( !(unsigned int)CManagerThread::MapHrToProtectionState(v13, v12, (unsigned int *)v38 + 36) )
      goto LABEL_118;
    pcbData = v14;
LABEL_116:
    ++*((_DWORD *)v14 + 2);
LABEL_117:
    CManagerThread::PublishProtectionState(v13, &pcbData);
    goto LABEL_118;
  }
  v14 = pcbData;
  v17 = (void *)*((_QWORD *)*pcbData + 1);
  if ( v17 )
  {
    CloseHandle(v17);
    *((_QWORD *)*v14 + 1) = 0;
  }
  v18 = *v14;
  CurrentProcess = GetCurrentProcess();
  v20 = GetCurrentProcess();
  if ( !DuplicateHandle(v20, a3, CurrentProcess, (LPHANDLE)v18 + 1, 0, 0, 2u) )
  {
    LastError = GetLastError();
    v12 = LastError;
    if ( LastError > 0 )
      v12 = (unsigned __int16)LastError | 0x80070000;
    v13 = (CConfigDescriptor *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v22 = 48;
LABEL_102:
      WPP_SF_d(*((_QWORD *)v13 + 2), v22, &WPP_a36920fbec7731c49b02dea361b0ee02_Traceguids, (unsigned int)v12);
      goto LABEL_103;
    }
    goto LABEL_103;
  }
  v12 = CConfigDescriptor::ReloadPolicies(*v14);
  v11 = (unsigned int)v12 >> 31;
  if ( (unsigned int)(v12 + 2147219967) <= 2 )
  {
    *((_DWORD *)*v14 + 10) = 1;
    v23 = ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
            &pcbData,
            *v14);
    CManagerThread::AddRemoveRegisteredConfig(&g_ManagerThread, v23, 0);
  }
  if ( v12 < 0 )
  {
    v13 = (CConfigDescriptor *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_Sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        49,
        (unsigned int)&WPP_a36920fbec7731c49b02dea361b0ee02_Traceguids,
        *a2,
        v12);
    goto LABEL_110;
  }
  *((_DWORD *)*v14 + 10) = 0;
  v24 = ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
          &pcbData,
          a2);
  v25 = CManagerThread::AddRemoveRegisteredConfig(&g_ManagerThread, v24, 1);
  v12 = v25;
  if ( v25 < 0 )
  {
    v13 = (CConfigDescriptor *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_Sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        50,
        (unsigned int)&WPP_a36920fbec7731c49b02dea361b0ee02_Traceguids,
        *a2,
        v25);
    goto LABEL_110;
  }
  if ( v46 == 1 )
  {
    *((_DWORD *)*v14 + 4) = 1;
  }
  else
  {
    if ( v46 != 3 )
    {
      v12 = -2147024809;
      goto LABEL_110;
    }
    *((_DWORD *)*v14 + 4) = 1;
    v13 = *v14;
    if ( *((_DWORD *)*v14 + 11) )
    {
      v13 = (CConfigDescriptor *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 51, &WPP_a36920fbec7731c49b02dea361b0ee02_Traceguids, *a2);
      v12 = -2147219968;
      goto LABEL_110;
    }
    if ( *((_DWORD *)v13 + 6) || (v26 = (_QWORD *)*((_QWORD *)v13 + 17)) != 0 && *v26 && *((_DWORD *)v13 + 22) == 3 )
    {
      v30 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 52, &WPP_a36920fbec7731c49b02dea361b0ee02_Traceguids);
        v30 = (PVOID *)WPP_GLOBAL_Control;
      }
      if ( !a6 )
      {
        if ( *((_DWORD *)*v14 + 6) )
        {
          if ( v30 != &WPP_GLOBAL_Control && (*((_BYTE *)v30 + 28) & 8) != 0 )
            WPP_SF_(v30[2], 53, &WPP_a36920fbec7731c49b02dea361b0ee02_Traceguids);
          *((_DWORD *)*v14 + 20) = 2;
          v30 = (PVOID *)WPP_GLOBAL_Control;
        }
        v13 = *v14;
        v31 = (_QWORD *)*((_QWORD *)*v14 + 17);
        if ( v31 && *v31 && *((_DWORD *)v13 + 22) == 3 )
        {
          if ( v30 != &WPP_GLOBAL_Control && (*((_BYTE *)v30 + 28) & 8) != 0 )
            WPP_SF_(v30[2], 54, &WPP_a36920fbec7731c49b02dea361b0ee02_Traceguids);
          *((_DWORD *)*v14 + 23) = 2;
          *((_DWORD *)*v14 + 24) = 2;
          CConfigDescriptor::RefreshPoliciesInEngine(*v14, *(&qword_1800199B8 + 1), qword_1800199B8);
        }
      }
    }
    else
    {
      *((_DWORD *)v13 + 6) = 1;
      v27 = 0;
      if ( !a6 )
        v27 = 2;
      *((_DWORD *)*v14 + 20) = v27;
      *((_DWORD *)*v14 + 21) = a5;
      v13 = *v14;
      v28 = (_QWORD *)*((_QWORD *)*v14 + 17);
      if ( v28 )
      {
        if ( *v28 )
        {
          v29 = *((unsigned int *)v13 + 22);
          if ( (unsigned int)(v29 - 1) <= 1 )
          {
            v13 = (CConfigDescriptor *)WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
              WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 55, &WPP_a36920fbec7731c49b02dea361b0ee02_Traceguids, v29);
            v11 = 1;
          }
        }
      }
    }
  }
  v32 = *v14;
  if ( *((_DWORD *)*v14 + 37) || *((_DWORD *)v32 + 38) )
  {
LABEL_105:
    if ( *((_DWORD *)*v14 + 36) <= 8u )
      *((_DWORD *)*v14 + 36) = 255;
    pcbData = v14;
    if ( !v14 )
      goto LABEL_117;
    goto LABEL_116;
  }
  pvData = 0;
  LODWORD(pcbData) = 8;
  if ( SetThreadToken(0, *((HANDLE *)v32 + 1)) )
  {
    ValueW = RegGetValueW(
               HKEY_CURRENT_USER,
               L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\FileHistory",
               L"ProtectedUpToTime",
               0x20000040u,
               0,
               &pvData,
               (LPDWORD)&pcbData);
    if ( ValueW )
    {
      if ( ValueW == 2 )
        goto LABEL_90;
    }
    else if ( (_DWORD)pcbData == 8 )
    {
      goto LABEL_90;
    }
    v35 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
    {
LABEL_91:
      v36 = pvData;
      if ( pvData )
      {
        if ( v35 != &WPP_GLOBAL_Control && (*((_BYTE *)v35 + 28) & 8) != 0 )
        {
          WPP_SF_i(v35[2], 58, pvData, pvData);
          v36 = pvData;
        }
        *((_DWORD *)*v14 + 37) = v36;
        *((_DWORD *)*v14 + 38) = HIDWORD(pvData);
      }
      if ( !SetThreadToken(0, 0) )
      {
        v37 = GetLastError();
        v12 = v37;
        if ( v37 > 0 )
          v12 = (unsigned __int16)v37 | 0x80070000;
        v13 = (CConfigDescriptor *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v22 = 59;
          goto LABEL_102;
        }
        goto LABEL_103;
      }
      goto LABEL_105;
    }
    WPP_SF_s(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      57,
      &WPP_a36920fbec7731c49b02dea361b0ee02_Traceguids,
      "(ret == ERROR_SUCCESS && dataSize == sizeof(data)) || (ret == ERROR_FILE_NOT_FOUND)");
LABEL_90:
    v35 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_91;
  }
  v33 = GetLastError();
  v12 = v33;
  if ( v33 > 0 )
    v12 = (unsigned __int16)v33 | 0x80070000;
  v13 = (CConfigDescriptor *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v22 = 56;
    goto LABEL_102;
  }
LABEL_103:
  if ( v12 < 0 )
    goto LABEL_110;
LABEL_118:
  if ( v11 )
  {
    v40 = (CWorkerThread **)*((_QWORD *)*v14 + 17);
    if ( v40 )
    {
      v41 = *v40;
      if ( v41 )
        CWorkerThread::Stop(v41, 0);
    }
  }
  SetEvent(hEvent);
  if ( v14 )
    SmartPtr<CConfigDescriptor>::RefCounter::Dec_nRefs(v14);
  LeaveCriticalSection(&CriticalSection);
  v42 = (volatile signed __int32 *)(*a2 - 24);
  if ( _InterlockedExchangeAdd(v42 + 4, 0xFFFFFFFF) <= 1 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v42 + 8LL))(*(_QWORD *)v42);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x1800065c0  mov     [rsp-38h+arg_8], rbx
0x1800065c5  mov     [rsp-38h+arg_18], r9d
0x1800065ca  mov     [rsp-38h+pcbData], rcx
0x1800065cf  push    rbp
0x1800065d0  push    rsi
0x1800065d1  push    rdi
0x1800065d2  push    r12
0x1800065d4  push    r13
0x1800065d6  push    r14
0x1800065d8  push    r15
0x1800065da  mov     rbp, rsp
0x1800065dd  sub     rsp, 50h
0x1800065e1  mov     ebx, r9d
0x1800065e4  mov     r13, r8
0x1800065e7  mov     r15, rdx
0x1800065ea  lea     rcx, CriticalSection; lpCriticalSection
0x1800065f1  call    cs:__imp_EnterCriticalSection
0x1800065f7  lea     rcx, [rbp+pcbData]
0x1800065fb  call    ??0?$SmartPtr@VCConfigDescriptor@@@@QEAA@PEAVCConfigDescriptor@@@Z; SmartPtr<CConfigDescriptor>::SmartPtr<CConfigDescriptor>(CConfigDescriptor *)
0x180006600  xor     esi, esi
0x180006602  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rsi
0x180006606  test    r13, r13
0x180006609  jnz     short loc_18000666D
0x18000660b  lea     r14, WPP_GLOBAL_Control
0x180006612  mov     rcx, cs:WPP_GLOBAL_Control
0x180006619  cmp     rcx, r14
0x18000661c  jz      short loc_180006640
0x18000661e  test    byte ptr [rcx+1Ch], 1
0x180006622  jz      short loc_180006640
0x180006624  mov     edx, 2Ch ; ','
0x180006629  lea     r9, aImpersonationt; "ImpersonationToken"
0x180006630  lea     r8, WPP_a36920fbec7731c49b02dea361b0ee02_Traceguids
0x180006637  mov     rcx, [rcx+10h]
0x18000663b  call    WPP_SF_s
0x180006640  mov     rcx, [rbp+pcbData]
0x180006644  test    rcx, rcx
0x180006647  jz      short loc_18000664E
0x180006649  call    ?Dec_nRefs@RefCounter@?$SmartPtr@VCConfigDescriptor@@@@QEAAHXZ; SmartPtr<CConfigDescriptor>::RefCounter::Dec_nRefs(void)
0x18000664e  lea     rcx, CriticalSection; lpCriticalSection
0x180006655  call    cs:__imp_LeaveCriticalSection
0x18000665b  mov     rcx, r15
0x18000665e  call    ??1?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::~CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x180006663  mov     eax, 80070057h
0x180006668  jmp     loc_180006D17
0x18000666d  mov     r12d, esi
0x180006670  lea     eax, [rbx-1]
0x180006673  test    eax, 0FFFFFFFDh
0x180006678  jz      short loc_1800066B6
0x18000667a  mov     edi, 80070057h
0x18000667f  lea     r14, WPP_GLOBAL_Control
0x180006686  mov     rcx, cs:WPP_GLOBAL_Control
0x18000668d  cmp     rcx, r14
0x180006690  jz      short loc_1800066AD
0x180006692  test    byte ptr [rcx+1Ch], 1
0x180006696  jz      short loc_1800066AD
0x180006698  mov     edx, 2Dh ; '-'
0x18000669d  mov     [rsp+50h+dwDesiredAccess], edi
0x1800066a1  mov     r9d, ebx
0x1800066a4  mov     rcx, [rcx+10h]
0x1800066a8  call    WPP_SF_dd
0x1800066ad  mov     rbx, [rbp+pcbData]
0x1800066b1  jmp     loc_180006C60
0x1800066b6  lea     r14, WPP_GLOBAL_Control
0x1800066bd  mov     rcx, cs:WPP_GLOBAL_Control
0x1800066c4  cmp     rcx, r14
0x1800066c7  jz      short loc_1800066E8
0x1800066c9  test    byte ptr [rcx+1Ch], 8
0x1800066cd  jz      short loc_1800066E8
0x1800066cf  mov     edx, 2Eh ; '.'
0x1800066d4  mov     rax, [r15]
0x1800066d7  mov     qword ptr [rsp+50h+dwDesiredAccess], rax
0x1800066dc  mov     r9d, ebx
0x1800066df  mov     rcx, [rcx+10h]
0x1800066e3  call    WPP_SF_dS
0x1800066e8  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1800066ec  call    cs:__imp_GetSystemTimeAsFileTime
0x1800066f2  mov     rcx, [r15]
0x1800066f5  sub     rcx, 18h
0x1800066f9  call    ?CloneData@?$CSimpleStringT@G$0A@@ATL@@CAPEAUCStringData@2@PEAU32@@Z; ATL::CSimpleStringT<ushort,0>::CloneData(ATL::CStringData *)
0x1800066fe  add     rax, 18h
0x180006702  mov     [rbp+pvData], rax
0x180006706  mov     r9d, 1
0x18000670c  lea     r8, [rbp+pcbData]
0x180006710  lea     rdx, [rbp+pvData]
0x180006714  call    ?GetConfigDescriptor@CManagerThread@@AEAAJV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@AEAV?$SmartPtr@VCConfigDescriptor@@@@H@Z; CManagerThread::GetConfigDescriptor(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,SmartPtr<CConfigDescriptor> &,int)
0x180006719  mov     edi, eax
0x18000671b  test    eax, eax
0x18000671d  jns     short loc_18000675A
0x18000671f  mov     rcx, cs:WPP_GLOBAL_Control
0x180006726  cmp     rcx, r14
0x180006729  jz      short loc_1800066AD
0x18000672b  test    byte ptr [rcx+1Ch], 1
0x18000672f  jz      loc_1800066AD
0x180006735  mov     edx, 2Fh ; '/'
0x18000673a  mov     [rsp+50h+dwDesiredAccess], eax
0x18000673e  mov     r9, [r15]
0x180006741  lea     r8, WPP_a36920fbec7731c49b02dea361b0ee02_Traceguids
0x180006748  mov     rcx, [rcx+10h]
0x18000674c  call    WPP_SF_Sd
0x180006751  mov     rbx, [rbp+pcbData]
0x180006755  jmp     loc_180006C60
0x18000675a  mov     rbx, [rbp+pcbData]
0x18000675e  mov     rax, [rbx]
0x180006761  mov     rcx, [rax+8]; hObject
0x180006765  test    rcx, rcx
0x180006768  jz      short loc_180006777
0x18000676a  call    cs:__imp_CloseHandle
0x180006770  mov     rax, [rbx]
0x180006773  mov     [rax+8], rsi
0x180006777  mov     rsi, [rbx]
0x18000677a  call    cs:__imp_GetCurrentProcess
0x180006780  mov     rdi, rax
0x180006783  call    cs:__imp_GetCurrentProcess
0x180006789  mov     [rsp+50h+dwOptions], 2; dwOptions
0x180006791  xor     ecx, ecx
0x180006793  mov     [rsp+50h+bInheritHandle], ecx; bInheritHandle
0x180006797  mov     [rsp+50h+dwDesiredAccess], ecx; dwDesiredAccess
0x18000679b  lea     r9, [rsi+8]; lpTargetHandle
0x18000679f  mov     r8, rdi; hTargetProcessHandle
0x1800067a2  mov     rdx, r13; hSourceHandle
0x1800067a5  mov     rcx, rax; hSourceProcessHandle
0x1800067a8  call    cs:__imp_DuplicateHandle
0x1800067ae  test    eax, eax
0x1800067b0  jnz     short loc_1800067EB
0x1800067b2  call    cs:__imp_GetLastError
0x1800067b8  mov     edi, eax
0x1800067ba  test    eax, eax
0x1800067bc  jle     short loc_1800067C7
0x1800067be  movzx   edi, ax
0x1800067c1  or      edi, 80070000h
0x1800067c7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800067ce  cmp     rcx, r14
0x1800067d1  jz      loc_180006C34
0x1800067d7  test    byte ptr [rcx+1Ch], 1
0x1800067db  jz      loc_180006C34
0x1800067e1  mov     edx, 30h ; '0'
0x1800067e6  jmp     loc_180006C21
0x1800067eb  mov     rcx, [rbx]; this
0x1800067ee  call    ?ReloadPolicies@CConfigDescriptor@@QEAAJXZ; CConfigDescriptor::ReloadPolicies(void)
0x1800067f3  mov     edi, eax
0x1800067f5  mov     r12d, eax
0x1800067f8  shr     r12d, 1Fh
0x1800067fc  add     eax, 7FFBF9FFh
0x180006801  cmp     eax, 2
0x180006804  ja      short loc_18000682E
0x180006806  mov     rax, [rbx]
0x180006809  mov     dword ptr [rax+28h], 1
0x180006810  mov     rdx, [rbx]
0x180006813  lea     rcx, [rbp+pcbData]
0x180006817  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@AEBV01@@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x18000681c  mov     rdx, rax
0x18000681f  xor     r8d, r8d
0x180006822  lea     rcx, ?g_ManagerThread@@3VCManagerThread@@A; CManagerThread g_ManagerThread
0x180006829  call    ?AddRemoveRegisteredConfig@CManagerThread@@AEAAJV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@H@Z; CManagerThread::AddRemoveRegisteredConfig(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,int)
0x18000682e  test    edi, edi
0x180006830  jns     short loc_18000686D
0x180006832  mov     rcx, cs:WPP_GLOBAL_Control
0x180006839  cmp     rcx, r14
0x18000683c  jz      loc_180006C60
0x180006842  test    byte ptr [rcx+1Ch], 1
0x180006846  jz      loc_180006C60
0x18000684c  mov     edx, 31h ; '1'
0x180006851  mov     [rsp+50h+dwDesiredAccess], edi
0x180006855  mov     r9, [r15]
0x180006858  lea     r8, WPP_a36920fbec7731c49b02dea361b0ee02_Traceguids
0x18000685f  mov     rcx, [rcx+10h]
0x180006863  call    WPP_SF_Sd
0x180006868  jmp     loc_180006C60
0x18000686d  mov     rax, [rbx]
0x180006870  mov     dword ptr [rax+28h], 0
0x180006877  mov     rdx, r15
0x18000687a  lea     rcx, [rbp+pcbData]
0x18000687e  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@AEBV01@@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x180006883  mov     rdx, rax
0x180006886  mov     r8d, 1
0x18000688c  lea     rcx, ?g_ManagerThread@@3VCManagerThread@@A; CManagerThread g_ManagerThread
0x180006893  call    ?AddRemoveRegisteredConfig@CManagerThread@@AEAAJV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@H@Z; CManagerThread::AddRemoveRegisteredConfig(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,int)
0x180006898  mov     edi, eax
0x18000689a  test    eax, eax
0x18000689c  jns     short loc_1800068C3
0x18000689e  mov     rcx, cs:WPP_GLOBAL_Control
0x1800068a5  cmp     rcx, r14
0x1800068a8  jz      loc_180006C60
0x1800068ae  test    byte ptr [rcx+1Ch], 1
0x1800068b2  jz      loc_180006C60
0x1800068b8  mov     edx, 32h ; '2'
0x1800068bd  mov     [rsp+50h+dwDesiredAccess], eax
0x1800068c1  jmp     short loc_180006855
0x1800068c3  mov     eax, [rbp+arg_18]
0x1800068c6  cmp     eax, 1
0x1800068c9  jnz     short loc_1800068DA
0x1800068cb  mov     rax, [rbx]
0x1800068ce  mov     dword ptr [rax+10h], 1
0x1800068d5  jmp     loc_180006AAC
0x1800068da  cmp     eax, 3
0x1800068dd  jnz     loc_180006C5B
0x1800068e3  mov     rax, [rbx]
0x1800068e6  mov     dword ptr [rax+10h], 1
0x1800068ed  mov     rcx, [rbx]
0x1800068f0  cmp     dword ptr [rcx+2Ch], 0
0x1800068f4  jz      short loc_18000692A
0x1800068f6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800068fd  cmp     rcx, r14
0x180006900  jz      short loc_180006920
0x180006902  test    byte ptr [rcx+1Ch], 1
0x180006906  jz      short loc_180006920
0x180006908  mov     edx, 33h ; '3'
0x18000690d  mov     r9, [r15]
0x180006910  lea     r8, WPP_a36920fbec7731c49b02dea361b0ee02_Traceguids
0x180006917  mov     rcx, [rcx+10h]
0x18000691b  call    WPP_SF_S
0x180006920  mov     edi, 80040600h
0x180006925  jmp     loc_180006C60
0x18000692a  cmp     dword ptr [rcx+18h], 0
0x18000692e  jnz     loc_1800069D3
0x180006934  mov     rax, [rcx+88h]
0x18000693b  test    rax, rax
0x18000693e  jz      short loc_180006950
0x180006940  cmp     qword ptr [rax], 0
0x180006944  jz      short loc_180006950
0x180006946  cmp     dword ptr [rcx+58h], 3
0x18000694a  jz      loc_1800069D3
0x180006950  mov     dword ptr [rcx+18h], 1
0x180006957  xor     ecx, ecx
0x180006959  cmp     [rbp+arg_28], ecx
0x18000695c  mov     esi, 2
0x180006961  cmovz   ecx, esi
0x180006964  mov     rax, [rbx]
0x180006967  mov     [rax+50h], ecx
0x18000696a  mov     rcx, [rbx]
0x18000696d  mov     eax, [rbp+arg_20]
0x180006970  mov     [rcx+54h], eax
0x180006973  mov     rcx, [rbx]
0x180006976  mov     rax, [rcx+88h]
0x18000697d  test    rax, rax
0x180006980  jz      loc_180006AAC
0x180006986  cmp     qword ptr [rax], 0
0x18000698a  jz      loc_180006AAC
0x180006990  mov     r9d, [rcx+58h]
0x180006994  lea     eax, [r9-1]
0x180006998  cmp     eax, 1
0x18000699b  ja      loc_180006AAC
0x1800069a1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800069a8  cmp     rcx, r14
0x1800069ab  jz      short loc_1800069C8
0x1800069ad  test    byte ptr [rcx+1Ch], 8
0x1800069b1  jz      short loc_1800069C8
0x1800069b3  mov     edx, 37h ; '7'
0x1800069b8  lea     r8, WPP_a36920fbec7731c49b02dea361b0ee02_Traceguids
0x1800069bf  mov     rcx, [rcx+10h]
0x1800069c3  call    WPP_SF_d
0x1800069c8  mov     r12d, 1
0x1800069ce  jmp     loc_180006AAC
0x1800069d3  mov     r9, cs:WPP_GLOBAL_Control
0x1800069da  cmp     r9, r14
0x1800069dd  jz      short loc_180006A02
0x1800069df  test    byte ptr [r9+1Ch], 8
0x1800069e4  jz      short loc_180006A02
0x1800069e6  mov     edx, 34h ; '4'
0x1800069eb  lea     r8, WPP_a36920fbec7731c49b02dea361b0ee02_Traceguids
0x1800069f2  mov     rcx, [r9+10h]
0x1800069f6  call    WPP_SF_
0x1800069fb  mov     r9, cs:WPP_GLOBAL_Control
0x180006a02  cmp     [rbp+arg_28], 0
0x180006a06  jnz     loc_180006AAC
0x180006a0c  mov     rax, [rbx]
0x180006a0f  cmp     dword ptr [rax+18h], 0
0x180006a13  jz      short loc_180006A4A
0x180006a15  cmp     r9, r14
0x180006a18  jz      short loc_180006A36
0x180006a1a  test    byte ptr [r9+1Ch], 8
0x180006a1f  jz      short loc_180006A36
0x180006a21  mov     edx, 35h ; '5'
0x180006a26  lea     r8, WPP_a36920fbec7731c49b02dea361b0ee02_Traceguids
0x180006a2d  mov     rcx, [r9+10h]
0x180006a31  call    WPP_SF_
0x180006a36  mov     rax, [rbx]
0x180006a39  mov     esi, 2
0x180006a3e  mov     [rax+50h], esi
0x180006a41  mov     r9, cs:WPP_GLOBAL_Control
0x180006a48  jmp     short loc_180006A4F
0x180006a4a  mov     esi, 2
0x180006a4f  mov     rcx, [rbx]
0x180006a52  mov     rax, [rcx+88h]
0x180006a59  test    rax, rax
0x180006a5c  jz      short loc_180006AAC
0x180006a5e  cmp     qword ptr [rax], 0
0x180006a62  jz      short loc_180006AAC
0x180006a64  cmp     dword ptr [rcx+58h], 3
0x180006a68  jnz     short loc_180006AAC
0x180006a6a  cmp     r9, r14
0x180006a6d  jz      short loc_180006A8B
0x180006a6f  test    byte ptr [r9+1Ch], 8
0x180006a74  jz      short loc_180006A8B
0x180006a76  mov     edx, 36h ; '6'
0x180006a7b  lea     r8, WPP_a36920fbec7731c49b02dea361b0ee02_Traceguids
0x180006a82  mov     rcx, [r9+10h]
0x180006a86  call    WPP_SF_
0x180006a8b  mov     rax, [rbx]
0x180006a8e  mov     [rax+5Ch], esi
  ... truncated ...
```
