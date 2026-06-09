# RealtimeProtection::DlpInjection::AutoInjectEnforcementDll(ulong)

- ea: `0x18020c1dc`
- end: `0x18020c5c9`
- name: `?AutoInjectEnforcementDll@DlpInjection@RealtimeProtection@@YAJK@Z`
- size: `1005`
- prototype: `__int64 __fastcall(RealtimeProtection::DlpInjection *__hidden this, unsigned int)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18019d7f8`

## callees

- `0x180028a10`
- `0x180040920`
- `0x180079dc0`
- `0x1800809d0`
- `0x180091f04`
- `0x1800c98a4`
- `0x1801051e8`
- `0x180105f50`
- `0x18010cb40`
- `0x18020c1dc`
- `0x18023a310`

## import_xrefs

- `KERNEL32!CreateToolhelp32Snapshot` at `0x18020c213`
- `KERNEL32!CreateToolhelp32Snapshot` at `0x18020c213`
- `KERNEL32!Process32NextW` at `0x18020c453`
- `KERNEL32!Process32NextW` at `0x18020c453`
- `KERNEL32!Process32FirstW` at `0x18020c285`
- `KERNEL32!Process32FirstW` at `0x18020c285`
- `KERNEL32!ProcessIdToSessionId` at `0x18020c3c2`
- `KERNEL32!ProcessIdToSessionId` at `0x18020c3c2`
- `KERNEL32!GetProcessTimes` at `0x18020c2fc`
- `KERNEL32!GetProcessTimes` at `0x18020c395`
- `KERNEL32!GetProcessTimes` at `0x18020c2fc`
- `KERNEL32!GetProcessTimes` at `0x18020c395`
- `KERNEL32!GetLastError` at `0x18020c53f`
- `KERNEL32!GetLastError` at `0x18020c53f`
- `KERNEL32!CloseHandle` at `0x18020c359`
- `KERNEL32!CloseHandle` at `0x18020c446`
- `KERNEL32!CloseHandle` at `0x18020c521`
- `KERNEL32!CloseHandle` at `0x18020c534`
- `KERNEL32!CloseHandle` at `0x18020c599`
- `KERNEL32!CloseHandle` at `0x18020c359`
- `KERNEL32!CloseHandle` at `0x18020c446`
- `KERNEL32!CloseHandle` at `0x18020c521`
- `KERNEL32!CloseHandle` at `0x18020c534`
- `KERNEL32!CloseHandle` at `0x18020c599`

## pseudocode

```c
__int64 __fastcall RealtimeProtection::DlpInjection::AutoInjectEnforcementDll(RealtimeProtection::DlpInjection *this)
{
  unsigned int v1; // r14d
  HANDLE Toolhelp32Snapshot; // rbx
  int v3; // eax
  int LastFailure; // edi
  BOOL i; // eax
  unsigned int Value; // eax
  unsigned int v8; // r8d
  unsigned int v9; // r9d
  unsigned int v10; // r9d
  void **th32ParentProcessID; // rdx
  int v12; // eax
  struct _FILETIME v13; // rcx
  const wchar_t *v14; // r9
  _QWORD *v15; // rcx
  __int64 v16; // rdx
  signed int LastError; // eax
  int lpUserTime; // [rsp+20h] [rbp-E0h]
  int v19; // [rsp+28h] [rbp-D8h]
  int v20; // [rsp+40h] [rbp-C0h]
  HANDLE hProcess; // [rsp+50h] [rbp-B0h] BYREF
  DWORD pSessionId; // [rsp+58h] [rbp-A8h] BYREF
  struct _FILETIME v23; // [rsp+60h] [rbp-A0h] BYREF
  DWORD v24; // [rsp+68h] [rbp-98h]
  unsigned int v25[2]; // [rsp+70h] [rbp-90h] BYREF
  DWORD th32ProcessID; // [rsp+78h] [rbp-88h]
  struct _FILETIME CreationTime; // [rsp+80h] [rbp-80h] BYREF
  struct _FILETIME v28; // [rsp+88h] [rbp-78h] BYREF
  struct _FILETIME UserTime; // [rsp+90h] [rbp-70h] BYREF
  struct _FILETIME KernelTime; // [rsp+98h] [rbp-68h] BYREF
  struct _FILETIME ExitTime; // [rsp+A0h] [rbp-60h] BYREF
  struct _FILETIME v32; // [rsp+A8h] [rbp-58h] BYREF
  struct _FILETIME v33; // [rsp+B0h] [rbp-50h] BYREF
  struct _FILETIME v34; // [rsp+B8h] [rbp-48h] BYREF
  PROCESSENTRY32W pe; // [rsp+C0h] [rbp-40h] BYREF

  v1 = (unsigned int)this;
  Toolhelp32Snapshot = CreateToolhelp32Snapshot(2u, 0);
  if ( Toolhelp32Snapshot == (HANDLE)-1LL && (v3 = HrGetLastFailure(), LastFailure = v3, v3 < 0) )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        19,
        WPP_ea50932c43b532c59b234e927a1f3fa2_Traceguids,
        (unsigned int)v3);
    return (unsigned int)LastFailure;
  }
  else
  {
    memset(&pe.cntUsage, 0, 0x234u);
    pe.dwSize = 568;
    for ( i = Process32FirstW(Toolhelp32Snapshot, &pe); i; i = Process32NextW(Toolhelp32Snapshot, &pe) )
    {
      Value = Dlp::FeatureControl::GetValue(222);
      if ( RealtimeProtection::DlpUtils::IsAutoInjectionCandidate(pe.szExeFile, (const wchar_t *)Value, v8) )
      {
        hProcess = 0;
        LastFailure = CommonUtil::UtilOpenProcess((CommonUtil *)&hProcess, (void **)pe.th32ProcessID, 0x1000u, v9);
        if ( LastFailure < 0 )
        {
          v15 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
            goto LABEL_43;
          v16 = 20;
LABEL_42:
          WPP_SF_d(v15[2], v16, WPP_ea50932c43b532c59b234e927a1f3fa2_Traceguids, (unsigned int)LastFailure);
          goto LABEL_43;
        }
        CreationTime = 0;
        ExitTime = 0;
        KernelTime = 0;
        UserTime = 0;
        if ( !GetProcessTimes(hProcess, &CreationTime, &ExitTime, &KernelTime, &UserTime) )
        {
          LastFailure = HrGetLastFailure();
          if ( LastFailure < 0 )
          {
            v15 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            {
              v16 = 21;
              goto LABEL_42;
            }
            goto LABEL_43;
          }
        }
        th32ProcessID = pe.th32ProcessID;
        *(struct _FILETIME *)v25 = CreationTime;
        v23 = 0;
        th32ParentProcessID = (void **)pe.th32ParentProcessID;
        v24 = pe.th32ParentProcessID;
        v28 = 0;
        v34 = 0;
        v33 = 0;
        v32 = 0;
        if ( hProcess )
        {
          CloseHandle(hProcess);
          hProcess = 0;
          th32ParentProcessID = (void **)pe.th32ParentProcessID;
        }
        if ( CommonUtil::UtilOpenProcess((CommonUtil *)&hProcess, th32ParentProcessID, 0x1000u, v10) >= 0
          && !GetProcessTimes(hProcess, &v28, &v34, &v33, &v32) )
        {
          v12 = HrGetLastFailure();
          v13 = v23;
          if ( v12 >= 0 )
            v13 = v28;
          v23 = v13;
        }
        pSessionId = 0;
        if ( !ProcessIdToSessionId(pe.th32ProcessID, &pSessionId) )
        {
          LastFailure = HrGetLastFailure();
          if ( LastFailure < 0 )
          {
            v15 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            {
              v16 = 22;
              goto LABEL_42;
            }
LABEL_43:
            if ( hProcess )
              CloseHandle(hProcess);
LABEL_45:
            if ( Toolhelp32Snapshot != (HANDLE)-1LL )
              CloseHandle(Toolhelp32Snapshot);
            return (unsigned int)LastFailure;
          }
        }
        RealtimeProtection::MpLogMessageImpl(
          (RealtimeProtection *)L"[DlpEngine] tracking splwow64.exe pid %lu",
          (const wchar_t *)pe.th32ProcessID);
        LOBYTE(v20) = 0;
        LOBYTE(v19) = 0;
        LOBYTE(lpUserTime) = 1;
        LastFailure = RealtimeProtection::DlpProcessCache::AddProcess(
                        v25,
                        &v23,
                        pSessionId,
                        pe.szExeFile,
                        lpUserTime,
                        v19,
                        0,
                        0,
                        v20);
        if ( LastFailure < 0 )
        {
          v15 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
            goto LABEL_43;
          v16 = 23;
          goto LABEL_42;
        }
        LastFailure = RealtimeProtection::DlpInjection::InjectEnforcementDllAsync(
                        (RealtimeProtection::DlpInjection *)v1,
                        (const struct PPID *)v25,
                        (const struct PPID *)pe.szExeFile,
                        v14);
        if ( LastFailure < 0 )
        {
          v15 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
            goto LABEL_43;
          v16 = 24;
          goto LABEL_42;
        }
        if ( hProcess )
          CloseHandle(hProcess);
      }
    }
    LastError = GetLastError();
    LastFailure = LastError;
    if ( LastError != 18 )
    {
      if ( LastError > 0 )
        LastFailure = (unsigned __int16)LastError | 0x80070000;
      if ( LastFailure < 0 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            25,
            WPP_ea50932c43b532c59b234e927a1f3fa2_Traceguids,
            (unsigned int)LastFailure);
        goto LABEL_45;
      }
    }
    if ( Toolhelp32Snapshot != (HANDLE)-1LL )
      CloseHandle(Toolhelp32Snapshot);
    return 0;
  }
}

```

## disassembly

```asm
0x18020c1dc  mov     [rsp-8+arg_8], rbx
0x18020c1e1  mov     [rsp-8+arg_10], rdi
0x18020c1e6  push    rbp
0x18020c1e7  push    r14
0x18020c1e9  push    r15
0x18020c1eb  lea     rbp, [rsp-210h]
0x18020c1f3  sub     rsp, 310h
0x18020c1fa  mov     rax, cs:__security_cookie
0x18020c201  xor     rax, rsp
0x18020c204  mov     [rbp+220h+var_20], rax
0x18020c20b  mov     r14d, ecx
0x18020c20e  xor     edx, edx; th32ProcessID
0x18020c210  lea     ecx, [rdx+2]; dwFlags
0x18020c213  call    cs:__imp_CreateToolhelp32Snapshot
0x18020c219  mov     rbx, rax
0x18020c21c  xor     r15d, r15d
0x18020c21f  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18020c223  jnz     short loc_18020C266
0x18020c225  call    HrGetLastFailure
0x18020c22a  mov     edi, eax
0x18020c22c  test    eax, eax
0x18020c22e  jns     short loc_18020C266
0x18020c230  lea     rdx, WPP_GLOBAL_Control
0x18020c237  mov     rcx, cs:WPP_GLOBAL_Control
0x18020c23e  cmp     rcx, rdx
0x18020c241  jz      short loc_18020C25F
0x18020c243  test    byte ptr [rcx+1Ch], 1
0x18020c247  jz      short loc_18020C25F
0x18020c249  lea     edx, [rbx+14h]
0x18020c24c  mov     r9d, eax
0x18020c24f  lea     r8, WPP_ea50932c43b532c59b234e927a1f3fa2_Traceguids
0x18020c256  mov     rcx, [rcx+10h]
0x18020c25a  call    WPP_SF_d
0x18020c25f  mov     eax, edi
0x18020c261  jmp     loc_18020C5A1
0x18020c266  xor     edx, edx; Val
0x18020c268  mov     r8d, 234h; Size
0x18020c26e  lea     rcx, [rbp+220h+pe.cntUsage]; void *
0x18020c272  call    memset
0x18020c277  mov     [rbp+220h+pe.dwSize], 238h
0x18020c27e  lea     rdx, [rbp+220h+pe]; lppe
0x18020c282  mov     rcx, rbx; hSnapshot
0x18020c285  call    cs:__imp_Process32FirstW
0x18020c28b  test    eax, eax
0x18020c28d  jz      loc_18020C53F
0x18020c293  mov     ecx, 0DEh
0x18020c298  call    ?GetValue@FeatureControl@Dlp@@YAIW4FeatureControlEnum@@@Z; Dlp::FeatureControl::GetValue(FeatureControlEnum)
0x18020c29d  mov     edx, eax; wchar_t *
0x18020c29f  lea     rcx, [rbp+220h+pe.szExeFile]; String1
0x18020c2a3  call    ?IsAutoInjectionCandidate@DlpUtils@RealtimeProtection@@YA_NPEB_WI@Z; RealtimeProtection::DlpUtils::IsAutoInjectionCandidate(wchar_t const *,uint)
0x18020c2a8  test    al, al
0x18020c2aa  jz      loc_18020C44C
0x18020c2b0  mov     [rsp+320h+hProcess], r15
0x18020c2b5  mov     r8d, 1000h; unsigned int
0x18020c2bb  mov     edx, [rbp+220h+pe.th32ProcessID]; void **
0x18020c2be  lea     rcx, [rsp+320h+hProcess]; this
0x18020c2c3  call    ?UtilOpenProcess@CommonUtil@@YAJPEAPEAXKK@Z; CommonUtil::UtilOpenProcess(void * *,ulong,ulong)
0x18020c2c8  mov     edi, eax
0x18020c2ca  test    eax, eax
0x18020c2cc  js      loc_18020C4E6
0x18020c2d2  mov     qword ptr [rbp+220h+CreationTime.dwLowDateTime], r15
0x18020c2d6  mov     qword ptr [rbp+220h+ExitTime.dwLowDateTime], r15
0x18020c2da  mov     qword ptr [rbp+220h+KernelTime.dwLowDateTime], r15
0x18020c2de  mov     qword ptr [rbp+220h+UserTime.dwLowDateTime], r15
0x18020c2e2  lea     rax, [rbp+220h+UserTime]
0x18020c2e6  mov     [rsp+320h+lpUserTime], rax; lpUserTime
0x18020c2eb  lea     r9, [rbp+220h+KernelTime]; lpKernelTime
0x18020c2ef  lea     r8, [rbp+220h+ExitTime]; lpExitTime
0x18020c2f3  lea     rdx, [rbp+220h+CreationTime]; lpCreationTime
0x18020c2f7  mov     rcx, [rsp+320h+hProcess]; hProcess
0x18020c2fc  call    cs:__imp_GetProcessTimes
0x18020c302  test    eax, eax
0x18020c304  jnz     short loc_18020C315
0x18020c306  call    HrGetLastFailure
0x18020c30b  mov     edi, eax
0x18020c30d  test    eax, eax
0x18020c30f  js      loc_18020C45E
0x18020c315  xor     eax, eax
0x18020c317  mov     qword ptr [rsp+320h+var_2B0+4], rax
0x18020c31c  mov     eax, [rbp+220h+pe.th32ProcessID]
0x18020c31f  mov     [rsp+320h+var_2A8], eax
0x18020c323  mov     rax, qword ptr [rbp+220h+CreationTime.dwLowDateTime]
0x18020c327  mov     qword ptr [rsp+320h+var_2B0], rax
0x18020c32c  mov     dword ptr [rsp+320h+var_2C0], r15d
0x18020c331  xor     eax, eax
0x18020c333  mov     [rsp+320h+var_2C0+4], rax
0x18020c338  mov     edx, [rbp+220h+pe.th32ParentProcessID]
0x18020c33b  mov     [rsp+320h+var_2B8], edx
0x18020c33f  mov     qword ptr [rbp+220h+var_298.dwLowDateTime], r15
0x18020c343  mov     qword ptr [rbp+220h+var_268.dwLowDateTime], r15
0x18020c347  mov     qword ptr [rbp+220h+var_270.dwLowDateTime], r15
0x18020c34b  mov     qword ptr [rbp+220h+var_278.dwLowDateTime], r15
0x18020c34f  mov     rcx, [rsp+320h+hProcess]; hObject
0x18020c354  test    rcx, rcx
0x18020c357  jz      short loc_18020C367
0x18020c359  call    cs:__imp_CloseHandle
0x18020c35f  mov     [rsp+320h+hProcess], r15
0x18020c364  mov     edx, [rbp+220h+pe.th32ParentProcessID]; void **
0x18020c367  mov     r8d, 1000h; unsigned int
0x18020c36d  lea     rcx, [rsp+320h+hProcess]; this
0x18020c372  call    ?UtilOpenProcess@CommonUtil@@YAJPEAPEAXKK@Z; CommonUtil::UtilOpenProcess(void * *,ulong,ulong)
0x18020c377  test    eax, eax
0x18020c379  js      short loc_18020C3B5
0x18020c37b  lea     rax, [rbp+220h+var_278]
0x18020c37f  mov     [rsp+320h+lpUserTime], rax; lpUserTime
0x18020c384  lea     r9, [rbp+220h+var_270]; lpKernelTime
0x18020c388  lea     r8, [rbp+220h+var_268]; lpExitTime
0x18020c38c  lea     rdx, [rbp+220h+var_298]; lpCreationTime
0x18020c390  mov     rcx, [rsp+320h+hProcess]; hProcess
0x18020c395  call    cs:__imp_GetProcessTimes
0x18020c39b  test    eax, eax
0x18020c39d  jnz     short loc_18020C3B5
0x18020c39f  call    HrGetLastFailure
0x18020c3a4  mov     rcx, [rsp+320h+var_2C0]
0x18020c3a9  test    eax, eax
0x18020c3ab  cmovns  rcx, qword ptr [rbp+220h+var_298.dwLowDateTime]
0x18020c3b0  mov     [rsp+320h+var_2C0], rcx
0x18020c3b5  mov     [rsp+320h+pSessionId], r15d
0x18020c3ba  lea     rdx, [rsp+320h+pSessionId]; pSessionId
0x18020c3bf  mov     ecx, [rbp+220h+pe.th32ProcessID]; dwProcessId
0x18020c3c2  call    cs:__imp_ProcessIdToSessionId
0x18020c3c8  test    eax, eax
0x18020c3ca  jnz     short loc_18020C3DB
0x18020c3cc  call    HrGetLastFailure
0x18020c3d1  mov     edi, eax
0x18020c3d3  test    eax, eax
0x18020c3d5  js      loc_18020C486
0x18020c3db  mov     edx, [rbp+220h+pe.th32ProcessID]; wchar_t *
0x18020c3de  lea     rcx, aDlpengineTrack; "[DlpEngine] tracking splwow64.exe pid %"...
0x18020c3e5  call    ?MpLogMessageImpl@RealtimeProtection@@YAJPEB_WZZ; RealtimeProtection::MpLogMessageImpl(wchar_t const *,...)
0x18020c3ea  mov     byte ptr [rsp+320h+var_2E0], r15b
0x18020c3ef  mov     [rsp+320h+var_2E8], r15d
0x18020c3f4  mov     [rsp+320h+var_2F0], r15d
0x18020c3f9  mov     [rsp+320h+var_2F8], r15b
0x18020c3fe  mov     byte ptr [rsp+320h+lpUserTime], 1
0x18020c403  lea     r9, [rbp+220h+pe.szExeFile]
0x18020c407  mov     r8d, [rsp+320h+pSessionId]
0x18020c40c  lea     rdx, [rsp+320h+var_2C0]
0x18020c411  lea     rcx, [rsp+320h+var_2B0]
0x18020c416  call    ?AddProcess@DlpProcessCache@RealtimeProtection@@YAJAEBUPPID@@0KPEB_W_N2W4_MP_KNOWN_PROCESS_TYPE@@W4ProcessHierarchyPolicy@2@2@Z; RealtimeProtection::DlpProcessCache::AddProcess(PPID const &,PPID const &,ulong,wchar_t const *,bool,bool,_MP_KNOWN_PROCESS_TYPE,RealtimeProtection::ProcessHierarchyPolicy,bool)
0x18020c41b  mov     edi, eax
0x18020c41d  test    eax, eax
0x18020c41f  js      loc_18020C4C6
0x18020c425  lea     r8, [rbp+220h+pe.szExeFile]; struct PPID *
0x18020c429  lea     rdx, [rsp+320h+var_2B0]; unsigned int
0x18020c42e  mov     ecx, r14d; this
0x18020c431  call    ?InjectEnforcementDllAsync@DlpInjection@RealtimeProtection@@YAJKAEBUPPID@@QEB_W@Z; RealtimeProtection::DlpInjection::InjectEnforcementDllAsync(ulong,PPID const &,wchar_t const * const)
0x18020c436  mov     edi, eax
0x18020c438  test    eax, eax
0x18020c43a  js      short loc_18020C4A6
0x18020c43c  mov     rcx, [rsp+320h+hProcess]; hObject
0x18020c441  test    rcx, rcx
0x18020c444  jz      short loc_18020C44C
0x18020c446  call    cs:__imp_CloseHandle
0x18020c44c  lea     rdx, [rbp+220h+pe]; lppe
0x18020c450  mov     rcx, rbx; hSnapshot
0x18020c453  call    cs:__imp_Process32NextW
0x18020c459  jmp     loc_18020C28B
0x18020c45e  lea     rdx, WPP_GLOBAL_Control
0x18020c465  mov     rcx, cs:WPP_GLOBAL_Control
0x18020c46c  cmp     rcx, rdx
0x18020c46f  jz      loc_18020C517
0x18020c475  test    byte ptr [rcx+1Ch], 1
0x18020c479  jz      loc_18020C517
0x18020c47f  mov     edx, 15h
0x18020c484  jmp     short loc_18020C504
0x18020c486  lea     rdx, WPP_GLOBAL_Control
0x18020c48d  mov     rcx, cs:WPP_GLOBAL_Control
0x18020c494  cmp     rcx, rdx
0x18020c497  jz      short loc_18020C517
0x18020c499  test    byte ptr [rcx+1Ch], 1
0x18020c49d  jz      short loc_18020C517
0x18020c49f  mov     edx, 16h
0x18020c4a4  jmp     short loc_18020C504
0x18020c4a6  lea     rdx, WPP_GLOBAL_Control
0x18020c4ad  mov     rcx, cs:WPP_GLOBAL_Control
0x18020c4b4  cmp     rcx, rdx
0x18020c4b7  jz      short loc_18020C517
0x18020c4b9  test    byte ptr [rcx+1Ch], 1
0x18020c4bd  jz      short loc_18020C517
0x18020c4bf  mov     edx, 18h
0x18020c4c4  jmp     short loc_18020C504
0x18020c4c6  lea     rdx, WPP_GLOBAL_Control
0x18020c4cd  mov     rcx, cs:WPP_GLOBAL_Control
0x18020c4d4  cmp     rcx, rdx
0x18020c4d7  jz      short loc_18020C517
0x18020c4d9  test    byte ptr [rcx+1Ch], 1
0x18020c4dd  jz      short loc_18020C517
0x18020c4df  mov     edx, 17h
0x18020c4e4  jmp     short loc_18020C504
0x18020c4e6  lea     rdx, WPP_GLOBAL_Control
0x18020c4ed  mov     rcx, cs:WPP_GLOBAL_Control
0x18020c4f4  cmp     rcx, rdx
0x18020c4f7  jz      short loc_18020C517
0x18020c4f9  test    byte ptr [rcx+1Ch], 1
0x18020c4fd  jz      short loc_18020C517
0x18020c4ff  mov     edx, 14h
0x18020c504  mov     r9d, edi
0x18020c507  lea     r8, WPP_ea50932c43b532c59b234e927a1f3fa2_Traceguids
0x18020c50e  mov     rcx, [rcx+10h]
0x18020c512  call    WPP_SF_d
0x18020c517  mov     rcx, [rsp+320h+hProcess]; hObject
0x18020c51c  test    rcx, rcx
0x18020c51f  jz      short loc_18020C527
0x18020c521  call    cs:__imp_CloseHandle
0x18020c527  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x18020c52b  jz      loc_18020C25F
0x18020c531  mov     rcx, rbx; hObject
0x18020c534  call    cs:__imp_CloseHandle
0x18020c53a  jmp     loc_18020C25F
0x18020c53f  call    cs:__imp_GetLastError
0x18020c545  mov     edi, eax
0x18020c547  cmp     eax, 12h
0x18020c54a  jz      short loc_18020C590
0x18020c54c  test    eax, eax
0x18020c54e  jle     short loc_18020C559
0x18020c550  movzx   edi, ax
0x18020c553  or      edi, 80070000h
0x18020c559  test    edi, edi
0x18020c55b  jns     short loc_18020C590
0x18020c55d  lea     rdx, WPP_GLOBAL_Control
0x18020c564  mov     rcx, cs:WPP_GLOBAL_Control
0x18020c56b  cmp     rcx, rdx
0x18020c56e  jz      short loc_18020C527
0x18020c570  test    byte ptr [rcx+1Ch], 1
0x18020c574  jz      short loc_18020C527
0x18020c576  mov     edx, 19h
0x18020c57b  mov     r9d, edi
0x18020c57e  lea     r8, WPP_ea50932c43b532c59b234e927a1f3fa2_Traceguids
0x18020c585  mov     rcx, [rcx+10h]
0x18020c589  call    WPP_SF_d
0x18020c58e  jmp     short loc_18020C527
0x18020c590  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x18020c594  jz      short loc_18020C59F
0x18020c596  mov     rcx, rbx; hObject
0x18020c599  call    cs:__imp_CloseHandle
0x18020c59f  xor     eax, eax
0x18020c5a1  mov     rcx, [rbp+220h+var_20]
0x18020c5a8  xor     rcx, rsp; StackCookie
0x18020c5ab  call    __security_check_cookie
0x18020c5b0  lea     r11, [rsp+320h+var_10]
0x18020c5b8  mov     rbx, [r11+28h]
0x18020c5bc  mov     rdi, [r11+30h]
0x18020c5c0  mov     rsp, r11
0x18020c5c3  pop     r15
0x18020c5c5  pop     r14
0x18020c5c7  pop     rbp
0x18020c5c8  retn
```
