# ScheduleAlertTask(ushort const *,DMAlertType)

- ea: `0x180020418`
- end: `0x180020b6a`
- name: `?ScheduleAlertTask@@YAJPEBGW4DMAlertType@@@Z`
- size: `1874`
- prototype: `__int64 __fastcall(OLECHAR *, int)`
- caller_count: `1`
- callee_count: `15`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callers

- `0x180023908`

## callees

- `0x1800039f0`
- `0x18000604c`
- `0x18000c63c`
- `0x180013d4c`
- `0x18001ce6c`
- `0x18001d30c`
- `0x18001dd58`
- `0x180020418`
- `0x1800235ac`
- `0x1800245fc`
- `0x180024dac`
- `0x180024e9c`
- `0x180024f8c`
- `0x18003593c`
- `0x18003b010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002062f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800206ad`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002062f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800206ad`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180020621`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002069f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180020621`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002069f`
- `dmEnrollEngine!GetEnrollmentSID` at `0x18002064f`
- `dmEnrollEngine!GetEnrollmentSID` at `0x18002064f`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180020a10`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180020a10`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x1800206c0`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x1800206c0`
- `RPCRT4!UuidFromStringW` at `0x1800205fa`
- `RPCRT4!UuidFromStringW` at `0x1800205fa`
- `OLEAUT32!__imp_SysAllocString` at `0x18002077e`
- `OLEAUT32!__imp_SysAllocString` at `0x1800208ab`
- `OLEAUT32!__imp_SysAllocString` at `0x1800208f6`
- `OLEAUT32!__imp_SysAllocString` at `0x18002077e`
- `OLEAUT32!__imp_SysAllocString` at `0x1800208ab`
- `OLEAUT32!__imp_SysAllocString` at `0x1800208f6`
- `OLEAUT32!__imp_VariantInit` at `0x18002087e`
- `OLEAUT32!__imp_VariantInit` at `0x180020893`
- `OLEAUT32!__imp_VariantInit` at `0x18002087e`
- `OLEAUT32!__imp_VariantInit` at `0x180020893`
- `OLEAUT32!__imp_VariantClear` at `0x180020991`
- `OLEAUT32!__imp_VariantClear` at `0x1800209a3`
- `OLEAUT32!__imp_VariantClear` at `0x1800209b5`
- `OLEAUT32!__imp_VariantClear` at `0x180020991`
- `OLEAUT32!__imp_VariantClear` at `0x1800209a3`
- `OLEAUT32!__imp_VariantClear` at `0x1800209b5`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x1800204c1`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x1800204fb`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x1800204c1`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x1800204fb`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x180020a26`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x180020a41`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x180020a26`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x180020a41`
- `OLEAUT32!__imp_SafeArrayLock` at `0x1800204da`
- `OLEAUT32!__imp_SafeArrayLock` at `0x180020510`
- `OLEAUT32!__imp_SafeArrayLock` at `0x1800204da`
- `OLEAUT32!__imp_SafeArrayLock` at `0x180020510`
- `OLEAUT32!__imp_SafeArrayUnlock` at `0x180020a19`
- `OLEAUT32!__imp_SafeArrayUnlock` at `0x180020a34`
- `OLEAUT32!__imp_SafeArrayUnlock` at `0x180020a19`
- `OLEAUT32!__imp_SafeArrayUnlock` at `0x180020a34`
- `DMCmnUtils!DmDisableTask` at `0x1800209da`
- `DMCmnUtils!DmDisableTask` at `0x1800209da`

## string_xrefs

- `0x1800205d4`: `/s "%s" /c /OsEditionUpgradeAlert /SID "%s"`
- `0x1800205b9`: `/s "%s" /c /Win10SModeAlert /SID "%s"`
- `0x1800205df`: `OS Edition Upgrade event listener created by enrollment client`
- `0x1800205c4`: `Win10 S Mode event listener created by enrollment client`
- `0x180020520`: `Wsc Startup event listener created by enrollment client`
- `0x1800209c9`: `Wsc Startup event listener created by enrollment client`
- `0x180020711`: `%windir%\system32\deviceenroller.exe`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall ScheduleAlertTask(OLECHAR *a1, int a2)
{
  SAFEARRAY *v4; // rax
  SAFEARRAY *v5; // rdi
  HRESULT v6; // eax
  SAFEARRAY *v7; // rax
  SAFEARRAY *v8; // rsi
  HRESULT v9; // eax
  int v10; // ebx
  int Task; // r14d
  int v12; // r15d
  CEnrollmentLogger *Logger; // rax
  const unsigned __int16 *v14; // r12
  const wchar_t *v15; // rax
  RPC_STATUS v16; // r14d
  int EnrollmentSID; // eax
  const wchar_t *v18; // rax
  void *v19; // r12
  HANDLE ProcessHeap; // rax
  __int64 *v21; // r14
  __int64 v22; // r12
  BSTR *v23; // rbx
  BSTR v24; // rax
  unsigned int v25; // r12d
  __int128 v26; // xmm8
  IRecordInfo *pRecInfo; // xmm9_8
  __int128 v28; // xmm10
  IRecordInfo *v29; // xmm11_8
  BSTR v30; // rax
  IRecordInfo *v31; // xmm7_8
  __int128 v32; // xmm6
  BSTR *v33; // rax
  SAFEARRAYBOUND v34; // r14
  BSTR *v35; // r12
  const OLECHAR *v36; // rcx
  BSTR v37; // rax
  BSTR v38; // rdx
  __int64 (__fastcall *v39)(LPVOID *, BSTR, SAFEARRAY *, __int64, __int128 *, __int128 *, int, __int128 *, __int64 *); // rax
  HRESULT v40; // eax
  HRESULT v41; // eax
  HRESULT v42; // eax
  CEnrollmentLogger *v43; // rax
  CEnrollmentLogger *v44; // rax
  LPVOID lpMem; // [rsp+78h] [rbp-90h] BYREF
  SAFEARRAYBOUND rgsabound; // [rsp+80h] [rbp-88h] BYREF
  int v48[2]; // [rsp+88h] [rbp-80h] BYREF
  LPVOID *v49; // [rsp+90h] [rbp-78h] BYREF
  __int64 *v50; // [rsp+98h] [rbp-70h] BYREF
  SAFEARRAY *v51; // [rsp+A0h] [rbp-68h] BYREF
  __int64 v52; // [rsp+A8h] [rbp-60h] BYREF
  int v53[2]; // [rsp+B0h] [rbp-58h] BYREF
  int v54[2]; // [rsp+B8h] [rbp-50h] BYREF
  SAFEARRAYBOUND v55; // [rsp+C0h] [rbp-48h] BYREF
  __int64 v56; // [rsp+C8h] [rbp-40h] BYREF
  int v57[2]; // [rsp+D0h] [rbp-38h] BYREF
  VARIANTARG v58; // [rsp+D8h] [rbp-30h] BYREF
  VARIANTARG v59; // [rsp+F8h] [rbp-10h] BYREF
  VARIANTARG pvarg; // [rsp+110h] [rbp+8h] BYREF
  __int128 v61; // [rsp+128h] [rbp+20h] BYREF
  IRecordInfo *v62; // [rsp+138h] [rbp+30h]
  __int128 v63; // [rsp+148h] [rbp+40h] BYREF
  IRecordInfo *v64; // [rsp+158h] [rbp+50h]
  __int128 v65; // [rsp+168h] [rbp+60h] BYREF
  IRecordInfo *v66; // [rsp+178h] [rbp+70h]
  UUID Uuid; // [rsp+188h] [rbp+80h] BYREF
  unsigned __int16 v68[264]; // [rsp+198h] [rbp+90h] BYREF

  *(_QWORD *)v57 = 0;
  *(_QWORD *)v54 = 0;
  *(_QWORD *)v48 = 0;
  *(_QWORD *)v53 = 0;
  v56 = 0;
  v50 = 0;
  v52 = 0;
  rgsabound = (SAFEARRAYBOUND)8LL;
  v4 = SafeArrayCreate(0x11u, 1u, &rgsabound);
  v51 = v4;
  v5 = v4;
  if ( !v4 )
  {
    v6 = -2147024882;
LABEL_74:
    ATL::AtlThrowImpl(v6);
  }
  v6 = SafeArrayLock(v4);
  if ( v6 < 0 )
    goto LABEL_74;
  v55 = 0;
  v7 = SafeArrayCreate(0x11u, 1u, &v55);
  v8 = v7;
  if ( !v7 )
  {
    v9 = -2147024882;
LABEL_76:
    ATL::AtlThrowImpl(v9);
  }
  v9 = SafeArrayLock(v7);
  if ( v9 < 0 )
    goto LABEL_76;
  v10 = 0;
  Uuid = 0;
  if ( a2 )
  {
    if ( a2 != 1 )
    {
      if ( a2 != 2 )
      {
        Task = -2147418113;
LABEL_9:
        if ( a2 )
        {
          v12 = a2 - 1;
          if ( v12 )
          {
            if ( v12 == 1 )
            {
              Logger = CEnrollmentLogger::GetLogger();
              CEnrollmentLogger::LogWscStartupAlertScheduleSetupFail(Logger, Task);
            }
          }
          else
          {
            v43 = CEnrollmentLogger::GetLogger();
            CEnrollmentLogger::LogWin10SModeScheduleSetupFail(v43, Task);
          }
        }
        else
        {
          v44 = CEnrollmentLogger::GetLogger();
          CEnrollmentLogger::LogOsEditionUpgradeScheduleSetupFail(v44, Task);
        }
        goto LABEL_50;
      }
      rgsabound = (SAFEARRAYBOUND)L"Wsc Startup event listener created by enrollment client";
      v49 = (LPVOID *)WNF_WSC_SECURITY_CENTER_STARTUP_NOTIFICATION;
      Task = StringCchPrintfW(v68, 0x104u, L"/s \"%s\" /c /WscStartupAlert", a1);
LABEL_25:
      if ( Task >= 0 )
      {
        Task = CoInitializeEx(0, 0);
        if ( Task >= 0 )
        {
          Task = CreateTask(
                   (LPVOID *)v57,
                   (BSTR ***)v54,
                   v48,
                   v53,
                   a1,
                   L"%windir%\\system32\\deviceenroller.exe",
                   v68,
                   L"S-1-5-18",
                   0,
                   1,
                   0,
                   0,
                   0);
          v10 = 1;
          if ( Task >= 0 )
          {
            Task = (*(__int64 (__fastcall **)(_QWORD, __int64 **))(**(_QWORD **)v48 + 120LL))(*(_QWORD *)v48, &v50);
            if ( Task >= 0 )
            {
              v21 = v50;
              v22 = *v50;
              v23 = (BSTR *)operator new(0x18u);
              v23[1] = 0;
              *((_DWORD *)v23 + 4) = 1;
              v24 = SysAllocString(L"LocalSystem");
              *v23 = v24;
              if ( !v24 )
                _com_issue_error(-2147024882);
              lpMem = v23;
              Task = (*(__int64 (__fastcall **)(__int64 *, BSTR))(v22 + 64))(v21, v24);
              _bstr_t::~_bstr_t((_bstr_t *)&lpMem);
              v10 = 1;
              if ( Task >= 0 )
              {
                Task = (*(__int64 (__fastcall **)(__int64 *, __int64))(*v50 + 144))(v50, 1);
                if ( Task >= 0 )
                {
                  Task = (*(__int64 (__fastcall **)(_QWORD, __int64))(**(_QWORD **)v53 + 208LL))(
                           *(_QWORD *)v53,
                           0xFFFFFFFFLL);
                  if ( Task >= 0 )
                  {
                    Task = (*(__int64 (__fastcall **)(_QWORD, __int64 *))(**(_QWORD **)v48 + 72LL))(
                             *(_QWORD *)v48,
                             &v52);
                    if ( Task >= 0 )
                    {
                      v25 = 0;
                      while ( 1 )
                      {
                        Task = ATL::CComSafeArray<unsigned char,17>::SetAt(&v51, v25, (char *)&v49 + (int)v25);
                        if ( Task < 0 )
                          break;
                        if ( ++v25 >= 8 )
                        {
                          Task = AddTaskWNFTrigger(v52, &v51);
                          if ( Task < 0 )
                            goto LABEL_9;
                          v49 = *(LPVOID **)v54;
                          lpMem = **(LPVOID **)v54;
                          VariantInit(&pvarg);
                          v26 = *(_OWORD *)&pvarg.vt;
                          pRecInfo = pvarg.pRecInfo;
                          VariantInit(&v59);
                          v28 = *(_OWORD *)&v59.vt;
                          v29 = v59.pRecInfo;
                          v30 = SysAllocString(L"S-1-5-18");
                          if ( !v30 )
                            goto LABEL_72;
                          v31 = v58.pRecInfo;
                          v58.llVal = (LONGLONG)v30;
                          v58.vt = 8;
                          v32 = *(_OWORD *)&v58.vt;
                          v51 = *(SAFEARRAY **)v48;
                          v33 = (BSTR *)operator new(0x18u);
                          v34 = rgsabound;
                          v35 = v33;
                          v36 = (const OLECHAR *)rgsabound;
                          v33[1] = 0;
                          *((_DWORD *)v33 + 4) = 1;
                          v37 = SysAllocString(v36);
                          *v35 = v37;
                          if ( !v37 )
                          {
                            if ( v34 )
LABEL_72:
                              _com_issue_error(-2147024882);
                          }
                          v38 = v37;
                          v39 = (__int64 (__fastcall *)(LPVOID *, BSTR, SAFEARRAY *, __int64, __int128 *, __int128 *, int, __int128 *, __int64 *))*((_QWORD *)lpMem + 17);
                          rgsabound = (SAFEARRAYBOUND)v35;
                          v61 = v26;
                          v62 = pRecInfo;
                          v63 = v28;
                          v64 = v29;
                          v65 = v32;
                          v66 = v31;
                          Task = v39(v49, v38, v51, 6, &v65, &v63, 3, &v61, &v56);
                          _bstr_t::~_bstr_t((_bstr_t *)&rgsabound);
                          v40 = VariantClear(&v58);
                          if ( v40 < 0 )
                            _com_issue_error(v40);
                          v41 = VariantClear(&v59);
                          if ( v41 < 0 )
                            _com_issue_error(v41);
                          v42 = VariantClear(&pvarg);
                          if ( v42 < 0 )
                            _com_issue_error(v42);
                          if ( a2 == 2 )
                            DmDisableTask(
                              L"\\Microsoft\\Windows\\EnterpriseMgmt",
                              a1,
                              L"Wsc Startup event listener created by enrollment client");
                          goto LABEL_46;
                        }
                      }
                    }
                  }
                }
              }
            }
          }
        }
      }
      goto LABEL_9;
    }
    v14 = L"/s \"%s\" /c /Win10SModeAlert /SID \"%s\"";
    v49 = (LPVOID *)WNF_CI_SMODE_CHANGE;
    v15 = L"Win10 S Mode event listener created by enrollment client";
  }
  else
  {
    v14 = L"/s \"%s\" /c /OsEditionUpgradeAlert /SID \"%s\"";
    v49 = (LPVOID *)WNF_OLIC_OS_EDITION_CHANGE;
    v15 = L"OS Edition Upgrade event listener created by enrollment client";
  }
  rgsabound = (SAFEARRAYBOUND)v15;
  lpMem = 0;
  v16 = UuidFromStringW(a1, &Uuid);
  if ( !v16 )
  {
    *(UUID *)&v58.vt = Uuid;
    EnrollmentSID = GetEnrollmentSID(&v58, &lpMem);
    Task = EnrollmentSID;
    if ( EnrollmentSID < 0 )
    {
      if ( EnrollmentSID != -2147024894 )
        goto LABEL_23;
      v18 = L"S-1-1-0";
    }
    else
    {
      v18 = (const wchar_t *)lpMem;
    }
    Task = StringCchPrintfW(v68, 0x104u, v14, a1, v18);
LABEL_23:
    v19 = lpMem;
    lpMem = 0;
    if ( v19 )
    {
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v19);
    }
    goto LABEL_25;
  }
  Task = v16 | 0x80010000;
  lpMem = 0;
LABEL_46:
  if ( Task < 0 )
    goto LABEL_9;
LABEL_50:
  if ( v10 )
    CoUninitialize();
  if ( SafeArrayUnlock(v8) >= 0 )
    SafeArrayDestroy(v8);
  if ( v5 && SafeArrayUnlock(v5) >= 0 )
    SafeArrayDestroy(v5);
  if ( v52 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v52 + 16LL))(v52);
  if ( v50 )
    (*(void (__fastcall **)(__int64 *))(*v50 + 16))(v50);
  if ( v56 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v56 + 16LL))(v56);
  if ( *(_QWORD *)v53 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v53 + 16LL))(*(_QWORD *)v53);
  if ( *(_QWORD *)v48 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v48 + 16LL))(*(_QWORD *)v48);
  if ( *(_QWORD *)v54 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v54 + 16LL))(*(_QWORD *)v54);
  if ( *(_QWORD *)v57 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v57 + 16LL))(*(_QWORD *)v57);
  return (unsigned int)Task;
}

```

## disassembly

```asm
0x180020418  mov     rax, rsp
0x18002041b  push    rbp
0x18002041c  push    rbx
0x18002041d  push    rsi
0x18002041e  push    rdi
0x18002041f  push    r12
0x180020421  push    r13
0x180020423  push    r14
0x180020425  push    r15
0x180020427  lea     rbp, [rax-358h]
0x18002042e  sub     rsp, 418h
0x180020435  movaps  xmmword ptr [rax-58h], xmm6
0x180020439  movaps  xmmword ptr [rax-68h], xmm7
0x18002043d  movaps  xmmword ptr [rax-78h], xmm8
0x180020442  movaps  xmmword ptr [rax-88h], xmm9
0x18002044a  movaps  xmmword ptr [rax-98h], xmm10
0x180020452  movaps  xmmword ptr [rax-0A8h], xmm11
0x18002045a  mov     rax, cs:__security_cookie
0x180020461  xor     rax, rsp
0x180020464  mov     [rbp+350h+var_B0], rax
0x18002046b  mov     ebx, 11h
0x180020470  mov     qword ptr [rbp+350h+var_388], 0
0x180020478  mov     r15d, edx
0x18002047b  mov     qword ptr [rbp+350h+var_3A0], 0
0x180020483  mov     r13, rcx
0x180020486  mov     qword ptr [rbp+350h+var_3D0], 0
0x18002048e  mov     ecx, ebx; vt
0x180020490  mov     qword ptr [rbp+350h+var_3A8], 0
0x180020498  lea     edx, [rbx-10h]; cDims
0x18002049b  mov     [rbp+350h+var_390], 0
0x1800204a3  lea     r8, [rsp+450h+rgsabound]; rgsabound
0x1800204a8  mov     [rbp+350h+var_3C0], 0
0x1800204b0  mov     [rbp+350h+var_3B0], 0
0x1800204b8  mov     qword ptr [rsp+450h+rgsabound.cElements], 8
0x1800204c1  call    cs:__imp_SafeArrayCreate
0x1800204c7  mov     [rbp+350h+var_3B8], rax
0x1800204cb  mov     rdi, rax
0x1800204ce  test    rax, rax
0x1800204d1  jz      loc_180020B2D
0x1800204d7  mov     rcx, rdi; psa
0x1800204da  call    cs:__imp_SafeArrayLock
0x1800204e0  test    eax, eax
0x1800204e2  js      loc_180020B32
0x1800204e8  mov     ecx, ebx; vt
0x1800204ea  mov     qword ptr [rbp+350h+var_398.cElements], 0
0x1800204f2  lea     r8, [rbp+350h+var_398]; rgsabound
0x1800204f6  mov     edx, 1; cDims
0x1800204fb  call    cs:__imp_SafeArrayCreate
0x180020501  mov     rsi, rax
0x180020504  test    rax, rax
0x180020507  jz      loc_180020B3A
0x18002050d  mov     rcx, rsi; psa
0x180020510  call    cs:__imp_SafeArrayLock
0x180020516  test    eax, eax
0x180020518  js      loc_180020B3F
0x18002051e  xor     ebx, ebx
0x180020520  lea     rdx, aWscStartupEven; "Wsc Startup event listener created by e"...
0x180020527  xorps   xmm0, xmm0
0x18002052a  mov     ecx, r15d
0x18002052d  movups  xmmword ptr [rbp+350h+Uuid.Data1], xmm0
0x180020534  test    r15d, r15d
0x180020537  jz      loc_1800205CD
0x18002053d  sub     ecx, 1
0x180020540  jz      short loc_1800205B2
0x180020542  cmp     ecx, 1
0x180020545  jz      short loc_18002057F
0x180020547  mov     r14d, 8000FFFFh
0x18002054d  test    r15d, r15d
0x180020550  jz      loc_1800209FC
0x180020556  sub     r15d, 1
0x18002055a  jz      loc_1800209EA
0x180020560  cmp     r15d, 1
0x180020564  jnz     loc_180020A0C
0x18002056a  call    ?GetLogger@CEnrollmentLogger@@SAPEAV1@XZ; CEnrollmentLogger::GetLogger(void)
0x18002056f  mov     edx, r14d; int
0x180020572  mov     rcx, rax; this
0x180020575  call    ?LogWscStartupAlertScheduleSetupFail@CEnrollmentLogger@@QEAAXJ@Z; CEnrollmentLogger::LogWscStartupAlertScheduleSetupFail(long)
0x18002057a  jmp     loc_180020A0C
0x18002057f  mov     rax, cs:WNF_WSC_SECURITY_CENTER_STARTUP_NOTIFICATION
0x180020586  lea     r8, aSSCWscstartupa; "/s \"%s\" /c /WscStartupAlert"
0x18002058d  mov     qword ptr [rsp+450h+rgsabound.cElements], rdx
0x180020592  lea     rcx, [rbp+350h+var_2C0]; unsigned __int16 *
0x180020599  mov     edx, 104h; unsigned __int64
0x18002059e  mov     [rbp+350h+var_3C8], rax
0x1800205a2  mov     r9, r13
0x1800205a5  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800205aa  mov     r14d, eax
0x1800205ad  jmp     loc_1800206B3
0x1800205b2  mov     rax, cs:WNF_CI_SMODE_CHANGE
0x1800205b9  lea     r12, aSSCWin10smodea; "/s \"%s\" /c /Win10SModeAlert /SID \"%s"...
0x1800205c0  mov     [rbp+350h+var_3C8], rax
0x1800205c4  lea     rax, aWin10SModeEven; "Win10 S Mode event listener created by "...
0x1800205cb  jmp     short loc_1800205E6
0x1800205cd  mov     rax, cs:WNF_OLIC_OS_EDITION_CHANGE
0x1800205d4  lea     r12, aSSCOseditionup; "/s \"%s\" /c /OsEditionUpgradeAlert /SI"...
0x1800205db  mov     [rbp+350h+var_3C8], rax
0x1800205df  lea     rax, aOsEditionUpgra; "OS Edition Upgrade event listener creat"...
0x1800205e6  lea     rdx, [rbp+350h+Uuid]; Uuid
0x1800205ed  mov     qword ptr [rsp+450h+rgsabound.cElements], rax
0x1800205f2  mov     rcx, r13; StringUuid
0x1800205f5  mov     [rsp+450h+lpMem], rbx
0x1800205fa  call    cs:__imp_UuidFromStringW
0x180020600  mov     r14d, eax
0x180020603  test    eax, eax
0x180020605  jz      short loc_18002063A
0x180020607  mov     r12, [rsp+450h+lpMem]
0x18002060c  or      r14d, 80010000h
0x180020613  mov     [rsp+450h+lpMem], rbx
0x180020618  test    r12, r12
0x18002061b  jz      loc_1800209E0
0x180020621  call    cs:__imp_GetProcessHeap
0x180020627  mov     r8, r12; lpMem
0x18002062a  xor     edx, edx; dwFlags
0x18002062c  mov     rcx, rax; hHeap
0x18002062f  call    cs:__imp_HeapFree
0x180020635  jmp     loc_1800209E0
0x18002063a  movaps  xmm0, xmmword ptr [rbp+350h+Uuid.Data1]
0x180020641  lea     rdx, [rsp+450h+lpMem]
0x180020646  lea     rcx, [rbp+350h+var_380]
0x18002064a  movdqa  xmmword ptr [rbp+350h+var_380], xmm0
0x18002064f  call    cs:__imp_GetEnrollmentSID
0x180020655  mov     r14d, eax
0x180020658  test    eax, eax
0x18002065a  js      short loc_180020663
0x18002065c  mov     rax, [rsp+450h+lpMem]
0x180020661  jmp     short loc_180020671
0x180020663  cmp     eax, 80070002h
0x180020668  jnz     short loc_180020690
0x18002066a  lea     rax, aS110; "S-1-1-0"
0x180020671  mov     r9, r13
0x180020674  mov     [rsp+450h+var_430], rax
0x180020679  mov     r8, r12; unsigned __int16 *
0x18002067c  lea     rcx, [rbp+350h+var_2C0]; unsigned __int16 *
0x180020683  mov     edx, 104h; unsigned __int64
0x180020688  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18002068d  mov     r14d, eax
0x180020690  mov     r12, [rsp+450h+lpMem]
0x180020695  mov     [rsp+450h+lpMem], rbx
0x18002069a  test    r12, r12
0x18002069d  jz      short loc_1800206B3
0x18002069f  call    cs:__imp_GetProcessHeap
0x1800206a5  mov     r8, r12; lpMem
0x1800206a8  xor     edx, edx; dwFlags
0x1800206aa  mov     rcx, rax; hHeap
0x1800206ad  call    cs:__imp_HeapFree
0x1800206b3  test    r14d, r14d
0x1800206b6  js      loc_18002054D
0x1800206bc  xor     edx, edx; dwCoInit
0x1800206be  xor     ecx, ecx; pvReserved
0x1800206c0  call    cs:__imp_CoInitializeEx
0x1800206c6  mov     r14d, eax
0x1800206c9  test    eax, eax
0x1800206cb  js      loc_18002054D
0x1800206d1  mov     [rsp+450h+Data], ebx; Data
0x1800206d5  lea     rax, aS1518; "S-1-5-18"
0x1800206dc  mov     [rsp+450h+var_3F8], ebx; int
0x1800206e0  lea     r9, [rbp+350h+var_3A8]; int
0x1800206e4  mov     [rsp+450h+var_400], ebx; int
0x1800206e8  lea     r8, [rbp+350h+var_3D0]; int
0x1800206ec  mov     [rsp+450h+var_408], 1; int
0x1800206f4  lea     rdx, [rbp+350h+var_3A0]; int
0x1800206f8  mov     [rsp+450h+var_410], ebx; int
0x1800206fc  lea     rcx, [rbp+350h+var_388]; int
0x180020700  mov     [rsp+450h+var_418], rax; unsigned __int16 *
0x180020705  lea     rax, [rbp+350h+var_2C0]
0x18002070c  mov     [rsp+450h+var_420], rax; unsigned __int16 *
0x180020711  lea     rax, aWindirSystem32_0; "%windir%\\system32\\deviceenroller.exe"
0x180020718  mov     [rsp+450h+var_428], rax; unsigned __int16 *
0x18002071d  mov     [rsp+450h+var_430], r13; OLECHAR *
0x180020722  call    ?CreateTask@@YAJAEAV?$CComPtr@UITaskService@@@ATL@@AEAV?$CComPtr@UITaskFolder@@@2@AEAV?$CComPtr@UITaskDefinition@@@2@AEAV?$CComPtr@UITaskSettings3@@@2@PEBG444W4_TASK_RUNLEVEL@@HHHH@Z; CreateTask(ATL::CComPtr<ITaskService> &,ATL::CComPtr<ITaskFolder> &,ATL::CComPtr<ITaskDefinition> &,ATL::CComPtr<ITaskSettings3> &,ushort const *,ushort const *,ushort const *,ushort const *,_TASK_RUNLEVEL,int,int,int,int)
0x180020727  mov     r14d, eax
0x18002072a  mov     ebx, 1
0x18002072f  test    eax, eax
0x180020731  js      loc_18002054D
0x180020737  mov     rcx, qword ptr [rbp+350h+var_3D0]
0x18002073b  lea     rdx, [rbp+350h+var_3C0]
0x18002073f  mov     rax, [rcx]
0x180020742  mov     rax, [rax+78h]
0x180020746  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002074b  mov     r14d, eax
0x18002074e  test    eax, eax
0x180020750  js      loc_18002054D
0x180020756  mov     r14, [rbp+350h+var_3C0]
0x18002075a  lea     ecx, [rbx+17h]; Size
0x18002075d  mov     r12, [r14]
0x180020760  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180020765  lea     rcx, aLocalsystem; "LocalSystem"
0x18002076c  mov     rbx, rax
0x18002076f  mov     qword ptr [rax+8], 0
0x180020777  mov     dword ptr [rax+10h], 1
0x18002077e  call    cs:__imp_SysAllocString
0x180020784  mov     [rbx], rax
0x180020787  test    rax, rax
0x18002078a  jz      loc_180020B47
0x180020790  mov     rdx, rax
0x180020793  mov     [rsp+450h+lpMem], rbx
0x180020798  mov     rax, [r12+40h]
0x18002079d  mov     rcx, r14
0x1800207a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800207a5  lea     rcx, [rsp+450h+lpMem]; this
0x1800207aa  mov     r14d, eax
0x1800207ad  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x1800207b2  mov     r12d, 1
0x1800207b8  mov     ebx, r12d
0x1800207bb  test    r14d, r14d
0x1800207be  js      loc_18002054D
0x1800207c4  mov     rcx, [rbp+350h+var_3C0]
0x1800207c8  mov     edx, r12d
0x1800207cb  mov     rax, [rcx]
0x1800207ce  mov     rax, [rax+90h]
0x1800207d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800207da  mov     r14d, eax
0x1800207dd  test    eax, eax
0x1800207df  js      loc_18002054D
0x1800207e5  mov     rcx, qword ptr [rbp+350h+var_3A8]
0x1800207e9  or      edx, 0FFFFFFFFh
0x1800207ec  mov     rax, [rcx]
0x1800207ef  mov     rax, [rax+0D0h]
0x1800207f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800207fb  mov     r14d, eax
0x1800207fe  test    eax, eax
0x180020800  js      loc_18002054D
0x180020806  mov     rcx, qword ptr [rbp+350h+var_3D0]
0x18002080a  lea     rdx, [rbp+350h+var_3B0]
0x18002080e  mov     rax, [rcx]
0x180020811  mov     rax, [rax+48h]
0x180020815  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002081a  mov     r14d, eax
0x18002081d  test    eax, eax
0x18002081f  js      loc_18002054D
0x180020825  xor     r12d, r12d
0x180020828  movsxd  rax, r12d
0x18002082b  lea     r8, [rbp+350h+var_3C8]
0x18002082f  add     r8, rax
0x180020832  lea     rcx, [rbp+350h+var_3B8]
0x180020836  mov     edx, r12d
0x180020839  call    ?SetAt@?$CComSafeArray@E$0BB@@ATL@@QEAAJJAEBEH@Z; ATL::CComSafeArray<uchar,17>::SetAt(long,uchar const &,int)
0x18002083e  mov     r14d, eax
0x180020841  test    eax, eax
0x180020843  js      loc_18002054D
0x180020849  inc     r12d
0x18002084c  cmp     r12d, 8
0x180020850  jb      short loc_180020828
0x180020852  mov     rcx, [rbp+350h+var_3B0]
0x180020856  lea     rdx, [rbp+350h+var_3B8]
0x18002085a  call    ?AddTaskWNFTrigger@@YAJPEAUITriggerCollection@@PEAV?$CComSafeArray@E$0BB@@ATL@@@Z; AddTaskWNFTrigger(ITriggerCollection *,ATL::CComSafeArray<uchar,17> *)
0x18002085f  mov     r14d, eax
0x180020862  test    eax, eax
0x180020864  js      loc_18002054D
0x18002086a  mov     rax, qword ptr [rbp+350h+var_3A0]
0x18002086e  lea     rcx, [rbp+350h+pvarg]; pvarg
0x180020872  mov     [rbp+350h+var_3C8], rax
0x180020876  mov     rax, [rax]
0x180020879  mov     [rsp+450h+lpMem], rax
0x18002087e  call    cs:__imp_VariantInit
0x180020884  movups  xmm8, xmmword ptr [rbp+350h+pvarg]
0x180020889  lea     rcx, [rbp+350h+var_360]; pvarg
0x18002088d  movsd   xmm9, qword ptr [rbp+350h+pvarg+10h]
0x180020893  call    cs:__imp_VariantInit
0x180020899  movups  xmm10, xmmword ptr [rbp+350h+var_360]
0x18002089e  lea     rcx, aS1518; "S-1-5-18"
0x1800208a5  movsd   xmm11, qword ptr [rbp+350h+var_360+10h]
0x1800208ab  call    cs:__imp_SysAllocString
0x1800208b1  test    rax, rax
0x1800208b4  jz      loc_180020B22
0x1800208ba  movsd   xmm7, qword ptr [rbp+350h+var_380+10h]
0x1800208bf  mov     edx, 8
0x1800208c4  mov     qword ptr [rbp+350h+var_380+8], rax
0x1800208c8  mov     rax, qword ptr [rbp+350h+var_3D0]
0x1800208cc  mov     word ptr [rbp+350h+var_380], dx
0x1800208d0  movups  xmm6, xmmword ptr [rbp+350h+var_380]
0x1800208d4  lea     ecx, [rdx+10h]; Size
0x1800208d7  mov     [rbp+350h+var_3B8], rax
0x1800208db  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800208e0  mov     r14, qword ptr [rsp+450h+rgsabound.cElements]
0x1800208e5  mov     r12, rax
0x1800208e8  mov     rcx, r14; psz
0x1800208eb  mov     qword ptr [rax+8], 0
0x1800208f3  mov     [rax+10h], ebx
0x1800208f6  call    cs:__imp_SysAllocString
0x1800208fc  mov     [r12], rax
0x180020900  test    rax, rax
0x180020903  jnz     short loc_18002090E
0x180020905  test    r14, r14
0x180020908  jnz     loc_180020B22
0x18002090e  mov     r8, [rbp+350h+var_3B8]
0x180020912  lea     rcx, [rbp+350h+var_390]
0x180020916  mov     qword ptr [rsp+450h+var_410], rcx
0x18002091b  mov     rdx, rax
0x18002091e  mov     rax, [rsp+450h+lpMem]
0x180020923  lea     rcx, [rbp+350h+var_330]
0x180020927  mov     [rsp+450h+var_418], rcx
0x18002092c  mov     r9d, 6
0x180020932  lea     rcx, [rbp+350h+var_310]
0x180020936  mov     dword ptr [rsp+450h+var_420], 3
0x18002093e  mov     [rsp+450h+var_428], rcx
0x180020943  lea     rcx, [rbp+350h+var_2F0]
0x180020947  mov     rax, [rax+88h]
0x18002094e  mov     [rsp+450h+var_430], rcx
0x180020953  mov     rcx, [rbp+350h+var_3C8]
  ... truncated ...
```
