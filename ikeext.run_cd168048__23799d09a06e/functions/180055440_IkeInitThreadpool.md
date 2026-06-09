# IkeInitThreadpool

- ea: `0x180055440`
- end: `0x180055826`
- name: `IkeInitThreadpool`
- size: `998`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `service_task`

## callers

- `0x180054bf4`

## callees

- `0x180001008`
- `0x1800010c8`
- `0x1800061ec`
- `0x180008388`
- `0x1800488f0`
- `0x18004890c`
- `0x18004aa3c`
- `0x180050850`
- `0x180055440`
- `0x18005582c`
- `0x18005bce4`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemInfo` at `0x18005548b`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemInfo` at `0x18005548b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800557d2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800557d2`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x18005573a`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x180055763`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x18005578c`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x1800557b5`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x18005573a`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x180055763`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x18005578c`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x1800557b5`

## string_xrefs

- `0x180055469`: `IkeInitThreadpool`
- `0x1800557ef`: `IkeInitThreadpool`
- `0x1800557fb`: `IkeInitThreadpool`
- `0x180055549`: `Setting DH throttle max thread limit`
- `0x18005563c`: `Setting worker task threadpool max thread limit`
- `0x1800557db`: `CreateThreadpoolWait`

## pseudocode

```c
__int64 IkeInitThreadpool()
{
  __int64 v0; // rcx
  DWORD dwNumberOfProcessors; // r14d
  __int64 v2; // rsi
  LONG LockCount; // edi
  __int64 TlsPeerAddr; // rbx
  int TlsMmLuid; // eax
  __int64 v6; // rcx
  __int64 v7; // rcx
  __int64 v8; // rax
  LONG v9; // ecx
  int v10; // r8d
  int v11; // r9d
  int v12; // esi
  __int64 v13; // rdi
  __int64 v14; // rbx
  int v15; // eax
  __int64 v16; // rcx
  __int64 v17; // rax
  int v18; // r8d
  __int64 inited; // rdi
  LPCRITICAL_SECTION v20; // rbx
  LPCRITICAL_SECTION v21; // rbx
  LPCRITICAL_SECTION v22; // rbx
  LPCRITICAL_SECTION v23; // rbx
  DWORD LastError; // eax
  __int64 v25; // rcx
  LONG v27; // [rsp+30h] [rbp-59h] BYREF
  __int64 v28; // [rsp+38h] [rbp-51h] BYREF
  _SYSTEM_INFO SystemInfo; // [rsp+40h] [rbp-49h] BYREF
  _BYTE v30[16]; // [rsp+70h] [rbp-19h] BYREF
  const char *v31; // [rsp+80h] [rbp-9h]
  __int64 v32; // [rsp+88h] [rbp-1h]
  LONG *v33; // [rsp+90h] [rbp+7h]
  __int64 v34; // [rsp+98h] [rbp+Fh]

  TraceLogHelper("IkeInitThreadpool", 1);
  memset(&SystemInfo, 0, sizeof(SystemInfo));
  GetSystemInfo(&SystemInfo);
  dwNumberOfProcessors = SystemInfo.dwNumberOfProcessors;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
  {
    v2 = *((_QWORD *)WPP_GLOBAL_Control + 2);
    LockCount = gIkeExtGlobals[49].LockCount;
    TlsPeerAddr = IkeGetTlsPeerAddr(v0);
    TlsMmLuid = IkeGetTlsMmLuid();
    WPP_SF_iSL(v2, 82, (unsigned int)WPP_c3da8f174801358a223b58501d21a257_Traceguids, TlsMmLuid, TlsPeerAddr, LockCount);
  }
  v6 = 2 * dwNumberOfProcessors;
  gIkeExtGlobals[49].LockCount = v6;
  if ( (unsigned int)dword_180173278 > 4 )
  {
    v28 = IkeGetTlsMmLuid();
    *(_QWORD *)&SystemInfo.dwNumberOfProcessors = &v28;
    *(_QWORD *)&SystemInfo.dwAllocationGranularity = 8;
    v8 = IkeGetTlsPeerAddr(v7);
    tlgCreate1Sz_wchar_t(v30, v8);
    v31 = "Setting DH throttle max thread limit";
    v32 = 37;
    v9 = gIkeExtGlobals[49].LockCount;
    v33 = &v27;
    v27 = v9;
    v34 = 4;
    tlgWriteTransfer_EtwEventWriteTransfer(
      (unsigned int)&dword_180173278,
      (unsigned int)word_18014E332,
      v10,
      v11,
      6,
      (__int64)&SystemInfo);
  }
  v12 = gIkeExtGlobals[49].LockCount + 4 * dwNumberOfProcessors + 2;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
  {
    v13 = *((_QWORD *)WPP_GLOBAL_Control + 2);
    v14 = IkeGetTlsPeerAddr(v6);
    v15 = IkeGetTlsMmLuid();
    WPP_SF_iSL(v13, 83, (unsigned int)WPP_c3da8f174801358a223b58501d21a257_Traceguids, v15, v14, v12);
  }
  if ( (unsigned int)dword_180173278 > 4 )
  {
    v28 = IkeGetTlsMmLuid();
    *(_QWORD *)&SystemInfo.dwNumberOfProcessors = &v28;
    *(_QWORD *)&SystemInfo.dwAllocationGranularity = 8;
    v17 = IkeGetTlsPeerAddr(v16);
    tlgCreate1Sz_wchar_t(v30, v17);
    v32 = 48;
    v33 = &v27;
    v31 = "Setting worker task threadpool max thread limit";
    v27 = v12;
    v34 = 4;
    tlgWriteTransfer_EtwEventWriteTransfer(
      (unsigned int)&dword_180173278,
      (unsigned int)byte_18014E2D5,
      v18,
      (unsigned int)"Setting worker task threadpool max thread limit",
      6,
      (__int64)&SystemInfo);
  }
  inited = IkeInitThreadpoolHelper(v12, 1u);
  if ( !inited )
  {
    HIDWORD(gIkeExtGlobals[53].OwningThread) = 1;
    inited = IkeInitThreadpoolHelper(v12, 0);
    if ( !inited )
    {
      LODWORD(gIkeExtGlobals[53].LockSemaphore) = 1;
      inited = IkeInitThreadpoolHelper(1u, 0);
      if ( !inited )
      {
        HIDWORD(gIkeExtGlobals[53].LockSemaphore) = 1;
        v20 = gIkeExtGlobals;
        v20[82].DebugInfo = (PRTL_CRITICAL_SECTION_DEBUG)CreateThreadpoolWait(
                                                           IkeReceiveCallback,
                                                           0,
                                                           (PTP_CALLBACK_ENVIRON)&gIkeExtGlobals[80].LockCount);
        v21 = gIkeExtGlobals;
        if ( !gIkeExtGlobals[82].DebugInfo
          || (*(_QWORD *)&v21[82].LockCount = CreateThreadpoolWait(
                                                IkeReceiveCallback,
                                                0,
                                                (PTP_CALLBACK_ENVIRON)&gIkeExtGlobals[80].LockCount),
              v22 = gIkeExtGlobals,
              !*(_QWORD *)&gIkeExtGlobals[82].LockCount)
          || (v22[82].OwningThread = CreateThreadpoolWait(
                                       IkeReceiveCallback,
                                       0,
                                       (PTP_CALLBACK_ENVIRON)&gIkeExtGlobals[80].LockCount),
              v23 = gIkeExtGlobals,
              !gIkeExtGlobals[82].OwningThread)
          || (v23[82].LockSemaphore = CreateThreadpoolWait(
                                        IkeReceiveCallback,
                                        0,
                                        (PTP_CALLBACK_ENVIRON)&gIkeExtGlobals[80].LockCount),
              !gIkeExtGlobals[82].LockSemaphore) )
        {
          LastError = GetLastError();
          inited = WfpReportSysErrorAsWinError(v25, "CreateThreadpoolWait", LastError, 1);
        }
      }
    }
  }
  TraceLogHelper("IkeInitThreadpool", 0);
  return IkeReturnError(inited, "IkeInitThreadpool");
}

```

## disassembly

```asm
0x180055440  push    rbp
0x180055442  push    rbx
0x180055443  push    rsi
0x180055444  push    rdi
0x180055445  push    r14
0x180055447  push    r15
0x180055449  lea     rbp, [rsp-2Fh]
0x18005544e  sub     rsp, 0B8h
0x180055455  mov     rax, cs:__security_cookie
0x18005545c  xor     rax, rsp
0x18005545f  mov     [rbp+57h+var_40], rax
0x180055463  mov     r15d, 1
0x180055469  lea     rcx, aIkeinitthreadp_0; "IkeInitThreadpool"
0x180055470  mov     edx, r15d
0x180055473  call    TraceLogHelper
0x180055478  xorps   xmm0, xmm0
0x18005547b  lea     rcx, [rbp+57h+SystemInfo]; lpSystemInfo
0x18005547f  movups  xmmword ptr [rbp+57h+SystemInfo], xmm0
0x180055483  movups  xmmword ptr [rbp+57h+SystemInfo.lpMaximumApplicationAddress], xmm0
0x180055487  movups  xmmword ptr [rbp+57h+SystemInfo.dwNumberOfProcessors], xmm0
0x18005548b  call    cs:__imp_GetSystemInfo
0x180055491  mov     r14d, [rbp+57h+SystemInfo.dwNumberOfProcessors]
0x180055495  mov     rsi, cs:WPP_GLOBAL_Control
0x18005549c  lea     rbx, WPP_GLOBAL_Control
0x1800554a3  cmp     rsi, rbx
0x1800554a6  jz      short loc_1800554F8
0x1800554a8  cmp     byte ptr [rsi+19h], 4
0x1800554ac  jb      short loc_1800554F8
0x1800554ae  test    byte ptr [rsi+1Ch], 10h
0x1800554b2  jz      short loc_1800554F8
0x1800554b4  mov     rax, cs:gIkeExtGlobals
0x1800554bb  mov     rsi, [rsi+10h]
0x1800554bf  mov     edi, [rax+7B0h]
0x1800554c5  call    IkeGetTlsPeerAddr
0x1800554ca  mov     rbx, rax
0x1800554cd  call    IkeGetTlsMmLuid
0x1800554d2  mov     r9, rax
0x1800554d5  mov     dword ptr [rsp+0E0h+var_B8], edi
0x1800554d9  lea     edx, [r15+51h]
0x1800554dd  mov     [rsp+0E0h+var_C0], rbx
0x1800554e2  lea     r8, WPP_c3da8f174801358a223b58501d21a257_Traceguids
0x1800554e9  mov     rcx, rsi
0x1800554ec  call    WPP_SF_iSL
0x1800554f1  lea     rbx, WPP_GLOBAL_Control
0x1800554f8  mov     rax, cs:gIkeExtGlobals
0x1800554ff  lea     ecx, [r14+r14]
0x180055503  mov     [rax+7B0h], ecx
0x180055509  mov     eax, cs:dword_180173278
0x18005550f  cmp     eax, 4
0x180055512  jbe     loc_180055599
0x180055518  call    IkeGetTlsMmLuid
0x18005551d  mov     [rbp+57h+var_A8], rax
0x180055521  lea     rax, [rbp+57h+var_A8]
0x180055525  mov     qword ptr [rbp+57h+SystemInfo.dwNumberOfProcessors], rax
0x180055529  mov     qword ptr [rbp+57h+SystemInfo.dwAllocationGranularity], 8
0x180055531  call    IkeGetTlsPeerAddr
0x180055536  mov     rdx, rax
0x180055539  lea     rcx, [rbp+57h+var_70]
0x18005553d  call    _tlgCreate1Sz_wchar_t
0x180055542  mov     rax, cs:gIkeExtGlobals
0x180055549  lea     rcx, aSettingDhThrot; "Setting DH throttle max thread limit"
0x180055550  mov     [rbp+57h+var_60], rcx
0x180055554  lea     rdx, word_18014E332
0x18005555b  mov     [rbp+57h+var_58], 25h ; '%'
0x180055563  mov     ecx, [rax+7B0h]
0x180055569  lea     rax, [rbp+57h+var_B0]
0x18005556d  mov     [rbp+57h+var_50], rax
0x180055571  lea     rax, [rbp+57h+SystemInfo]
0x180055575  mov     [rbp+57h+var_B0], ecx
0x180055578  lea     rcx, dword_180173278
0x18005557f  mov     [rsp+0E0h+var_B8], rax
0x180055584  mov     dword ptr [rsp+0E0h+var_C0], 6
0x18005558c  mov     [rbp+57h+var_48], 4
0x180055594  call    _tlgWriteTransfer_EtwEventWriteTransfer
0x180055599  mov     rax, cs:gIkeExtGlobals
0x1800555a0  lea     esi, ds:2[r14*4]
0x1800555a8  add     esi, [rax+7B0h]
0x1800555ae  mov     rdi, cs:WPP_GLOBAL_Control
0x1800555b5  cmp     rdi, rbx
0x1800555b8  jz      short loc_1800555F7
0x1800555ba  cmp     byte ptr [rdi+19h], 4
0x1800555be  jb      short loc_1800555F7
0x1800555c0  test    byte ptr [rdi+1Ch], 10h
0x1800555c4  jz      short loc_1800555F7
0x1800555c6  mov     rdi, [rdi+10h]
0x1800555ca  call    IkeGetTlsPeerAddr
0x1800555cf  mov     rbx, rax
0x1800555d2  call    IkeGetTlsMmLuid
0x1800555d7  mov     r9, rax
0x1800555da  mov     dword ptr [rsp+0E0h+var_B8], esi
0x1800555de  mov     edx, 53h ; 'S'
0x1800555e3  mov     [rsp+0E0h+var_C0], rbx
0x1800555e8  lea     r8, WPP_c3da8f174801358a223b58501d21a257_Traceguids
0x1800555ef  mov     rcx, rdi
0x1800555f2  call    WPP_SF_iSL
0x1800555f7  mov     eax, cs:dword_180173278
0x1800555fd  cmp     eax, 4
0x180055600  jbe     short loc_180055676
0x180055602  call    IkeGetTlsMmLuid
0x180055607  mov     [rbp+57h+var_A8], rax
0x18005560b  lea     rax, [rbp+57h+var_A8]
0x18005560f  mov     qword ptr [rbp+57h+SystemInfo.dwNumberOfProcessors], rax
0x180055613  mov     qword ptr [rbp+57h+SystemInfo.dwAllocationGranularity], 8
0x18005561b  call    IkeGetTlsPeerAddr
0x180055620  mov     rdx, rax
0x180055623  lea     rcx, [rbp+57h+var_70]
0x180055627  call    _tlgCreate1Sz_wchar_t
0x18005562c  lea     rax, [rbp+57h+var_B0]
0x180055630  mov     [rbp+57h+var_58], 30h ; '0'
0x180055638  mov     [rbp+57h+var_50], rax
0x18005563c  lea     r9, aSettingWorkerT; "Setting worker task threadpool max thre"...
0x180055643  lea     rax, [rbp+57h+SystemInfo]
0x180055647  mov     [rbp+57h+var_60], r9
0x18005564b  mov     [rsp+0E0h+var_B8], rax
0x180055650  lea     rdx, byte_18014E2D5
0x180055657  lea     rcx, dword_180173278
0x18005565e  mov     dword ptr [rsp+0E0h+var_C0], 6
0x180055666  mov     [rbp+57h+var_B0], esi
0x180055669  mov     [rbp+57h+var_48], 4
0x180055671  call    _tlgWriteTransfer_EtwEventWriteTransfer
0x180055676  mov     r8, cs:gIkeExtGlobals
0x18005567d  mov     edx, r15d; cthrdMic
0x180055680  mov     ecx, esi; cthrdMost
0x180055682  lea     r9, [r8+0BE8h]
0x180055689  add     r8, 0BE0h
0x180055690  call    IkeInitThreadpoolHelper
0x180055695  mov     rdi, rax
0x180055698  test    rax, rax
0x18005569b  jnz     loc_1800557ED
0x1800556a1  mov     rax, cs:gIkeExtGlobals
0x1800556a8  xor     edx, edx; cthrdMic
0x1800556aa  mov     ecx, esi; cthrdMost
0x1800556ac  mov     [rax+85Ch], r15d
0x1800556b3  mov     r8, cs:gIkeExtGlobals
0x1800556ba  lea     r9, [r8+0C38h]
0x1800556c1  add     r8, 0C30h
0x1800556c8  call    IkeInitThreadpoolHelper
0x1800556cd  mov     rdi, rax
0x1800556d0  test    rax, rax
0x1800556d3  jnz     loc_1800557ED
0x1800556d9  mov     rax, cs:gIkeExtGlobals
0x1800556e0  xor     edx, edx; cthrdMic
0x1800556e2  mov     ecx, r15d; cthrdMost
0x1800556e5  mov     [rax+860h], r15d
0x1800556ec  mov     r8, cs:gIkeExtGlobals
0x1800556f3  lea     r9, [r8+0C88h]
0x1800556fa  add     r8, 0C80h
0x180055701  call    IkeInitThreadpoolHelper
0x180055706  mov     rdi, rax
0x180055709  test    rax, rax
0x18005570c  jnz     loc_1800557ED
0x180055712  mov     rax, cs:gIkeExtGlobals
0x180055719  lea     rsi, IkeReceiveCallback
0x180055720  xor     edx, edx; pv
0x180055722  mov     rcx, rsi; pfnwa
0x180055725  mov     [rax+864h], r15d
0x18005572c  mov     rbx, cs:gIkeExtGlobals
0x180055733  lea     r8, [rbx+0C88h]; pcbe
0x18005573a  call    cs:__imp_CreateThreadpoolWait
0x180055740  mov     [rbx+0CD0h], rax
0x180055747  mov     rbx, cs:gIkeExtGlobals
0x18005574e  cmp     [rbx+0CD0h], rdi
0x180055755  jz      short loc_1800557D2
0x180055757  lea     r8, [rbx+0C88h]; pcbe
0x18005575e  xor     edx, edx; pv
0x180055760  mov     rcx, rsi; pfnwa
0x180055763  call    cs:__imp_CreateThreadpoolWait
0x180055769  mov     [rbx+0CD8h], rax
0x180055770  mov     rbx, cs:gIkeExtGlobals
0x180055777  cmp     [rbx+0CD8h], rdi
0x18005577e  jz      short loc_1800557D2
0x180055780  lea     r8, [rbx+0C88h]; pcbe
0x180055787  xor     edx, edx; pv
0x180055789  mov     rcx, rsi; pfnwa
0x18005578c  call    cs:__imp_CreateThreadpoolWait
0x180055792  mov     [rbx+0CE0h], rax
0x180055799  mov     rbx, cs:gIkeExtGlobals
0x1800557a0  cmp     [rbx+0CE0h], rdi
0x1800557a7  jz      short loc_1800557D2
0x1800557a9  lea     r8, [rbx+0C88h]; pcbe
0x1800557b0  xor     edx, edx; pv
0x1800557b2  mov     rcx, rsi; pfnwa
0x1800557b5  call    cs:__imp_CreateThreadpoolWait
0x1800557bb  mov     [rbx+0CE8h], rax
0x1800557c2  mov     rax, cs:gIkeExtGlobals
0x1800557c9  cmp     [rax+0CE8h], rdi
0x1800557d0  jnz     short loc_1800557ED
0x1800557d2  call    cs:__imp_GetLastError
0x1800557d8  mov     r9d, r15d
0x1800557db  lea     rdx, aCreatethreadpo; "CreateThreadpoolWait"
0x1800557e2  mov     r8d, eax
0x1800557e5  call    WfpReportSysErrorAsWinError
0x1800557ea  mov     rdi, rax
0x1800557ed  xor     edx, edx
0x1800557ef  lea     rcx, aIkeinitthreadp_0; "IkeInitThreadpool"
0x1800557f6  call    TraceLogHelper
0x1800557fb  lea     rdx, aIkeinitthreadp_0; "IkeInitThreadpool"
0x180055802  mov     rcx, rdi
0x180055805  call    IkeReturnError
0x18005580a  mov     rcx, [rbp+57h+var_40]
0x18005580e  xor     rcx, rsp; StackCookie
0x180055811  call    __security_check_cookie
0x180055816  add     rsp, 0B8h
0x18005581d  pop     r15
0x18005581f  pop     r14
0x180055821  pop     rdi
0x180055822  pop     rsi
0x180055823  pop     rbx
0x180055824  pop     rbp
0x180055825  retn
```
