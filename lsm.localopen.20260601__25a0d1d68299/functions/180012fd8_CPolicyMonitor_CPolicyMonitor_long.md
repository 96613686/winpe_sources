# CPolicyMonitor::CPolicyMonitor(long *)

- ea: `0x180012fd8`
- end: `0x18001342c`
- name: `??0CPolicyMonitor@@QEAA@PEAJ@Z`
- size: `1108`
- prototype: `CPolicyMonitor *__fastcall(CPolicyMonitor *__hidden this, int *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18002cf00`

## callees

- `0x1800077a0`
- `0x180012fd8`
- `0x180014430`
- `0x18002b94c`

## import_xrefs

- `ntdll!RtlSubscribeWnfStateChangeNotification` at `0x180013359`
- `ntdll!RtlSubscribeWnfStateChangeNotification` at `0x180013359`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180013286`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180013286`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800132a3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800133b3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800133c6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800132a3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800133b3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800133c6`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x180013312`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x180013312`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800133f7`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800133f7`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800130c0`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180013117`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180013161`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800131af`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800131f9`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180013242`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800130c0`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180013117`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180013161`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800131af`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800131f9`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180013242`
- `api-ms-win-oobe-notification-l1-1-0!RegisterWaitUntilOOBECompleted` at `0x1800133a3`
- `api-ms-win-oobe-notification-l1-1-0!RegisterWaitUntilOOBECompleted` at `0x1800133a3`
- `api-ms-win-oobe-notification-l1-1-0!OOBEComplete` at `0x18001337c`
- `api-ms-win-oobe-notification-l1-1-0!OOBEComplete` at `0x18001337c`

## string_xrefs

- `0x1800133df`: `Registration of OOBE completion notification has failed: 0x%x. Non fatal error, continuing.`
- `0x180013136`: `RegOpenKeyEx( TS_FIPS_POLICY ) failed: 0x%x`
- `0x1800130df`: `RegOpenKeyEx( REG_CONTROL_TSERVER ) failed: 0x%x`
- `0x180013180`: `RegOpenKeyEx( TS_LEGACY_FIPS_POLICY ) failed: 0x%x`
- `0x1800131d1`: `RegOpenKeyEx( WINSTATION_REG_NAME ) failed: 0x%x`
- `0x18001321c`: `RegOpenKeyEx( REG_TS_CLUSTERSETTINGS ) failed: 0x%x`
- `0x18001325f`: `RegOpenKeyEx( TS_SYSPREP_KEY ) failed: 0x%x`
- `0x1800132ef`: `StartWaitOnRegistry failed: 0x%x in %s`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
CPolicyMonitor *__fastcall CPolicyMonitor::CPolicyMonitor(CPolicyMonitor *this, int *a2)
{
  LSTATUS v3; // eax
  int v4; // ebx
  int v5; // eax
  bool v6; // sf
  LSTATUS v7; // eax
  LSTATUS v8; // eax
  int v9; // eax
  bool v10; // sf
  int v11; // eax
  bool v12; // sf
  unsigned int i; // esi
  HANDLE EventW; // rax
  signed int LastError; // eax
  int started; // eax
  PTP_WORK ThreadpoolWork; // rax
  int v18; // ebx
  signed int v19; // eax
  BOOL bManualReset[4]; // [rsp+40h] [rbp-68h]
  __m128i si128; // [rsp+50h] [rbp-58h]
  int v23; // [rsp+60h] [rbp-48h]
  int v25; // [rsp+C0h] [rbp+18h] BYREF

  CTSObject<IUnknown>::CTSObject<IUnknown>(this, "PolicyMonitor");
  *(_QWORD *)this = &CPolicyMonitor::`vftable';
  *((_DWORD *)this + 432) = 0;
  v25 = 1;
  *(_OWORD *)bManualReset = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  v23 = 0;
  *((_QWORD *)this + 199) = 0;
  *((_QWORD *)this + 200) = 0;
  *((_QWORD *)this + 201) = 0;
  *((_QWORD *)this + 202) = 0;
  *((_QWORD *)this + 203) = 0;
  *((_QWORD *)this + 204) = 0;
  *((_BYTE *)this + 1640) = 0;
  CPolicyMonitor::hPolicyChangeEvent = 0;
  *((_QWORD *)this + 213) = 0;
  *((_QWORD *)this + 214) = 0;
  *((_QWORD *)this + 215) = 0;
  v3 = RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"System\\CurrentControlSet\\Control\\Terminal Server",
         0,
         0x20019u,
         (PHKEY)this + 199);
  v4 = v3;
  if ( v3 > 0 )
    v4 = (unsigned __int16)v3 | 0x80070000;
  if ( v4 >= 0 )
  {
    v5 = RegOpenKeyExW(
           HKEY_LOCAL_MACHINE,
           L"System\\CurrentControlSet\\Control\\LSA\\FipsAlgorithmPolicy",
           0,
           0x20019u,
           (PHKEY)this + 200);
    v6 = v5 < 0;
    if ( v5 > 0 )
    {
      v5 = (unsigned __int16)v5 | 0x80070000;
      v6 = v5 < 0;
    }
    if ( !v6 )
      goto LABEL_12;
    _DbgPrintMessage(4, "RegOpenKeyEx( TS_FIPS_POLICY ) failed: 0x%x", v5);
    v7 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"System\\CurrentControlSet\\Control\\LSA", 0, 0x20019u, (PHKEY)this + 200);
    v4 = v7;
    if ( v7 > 0 )
      v4 = (unsigned __int16)v7 | 0x80070000;
    if ( v4 < 0 )
    {
      _DbgPrintMessage(8, "RegOpenKeyEx( TS_LEGACY_FIPS_POLICY ) failed: 0x%x", (unsigned int)v4);
    }
    else
    {
LABEL_12:
      v8 = RegOpenKeyExW(
             HKEY_LOCAL_MACHINE,
             L"System\\CurrentControlSet\\Control\\Terminal Server\\WinStations",
             0,
             0x20019u,
             (PHKEY)this + 201);
      v4 = v8;
      if ( v8 > 0 )
        v4 = (unsigned __int16)v8 | 0x80070000;
      if ( v4 >= 0 )
      {
        v9 = RegOpenKeyExW(
               HKEY_LOCAL_MACHINE,
               L"System\\CurrentControlSet\\Control\\Terminal Server\\ClusterSettings",
               0,
               0x20019u,
               (PHKEY)this + 202);
        v10 = v9 < 0;
        if ( v9 > 0 )
        {
          v9 = (unsigned __int16)v9 | 0x80070000;
          v10 = v9 < 0;
        }
        if ( v10 )
          _DbgPrintMessage(4, "RegOpenKeyEx( REG_TS_CLUSTERSETTINGS ) failed: 0x%x", v9);
        v11 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SYSTEM\\Setup", 0, 0x20019u, (PHKEY)this + 203);
        v12 = v11 < 0;
        if ( v11 > 0 )
        {
          v11 = (unsigned __int16)v11 | 0x80070000;
          v12 = v11 < 0;
        }
        if ( v12 )
          _DbgPrintMessage(4, "RegOpenKeyEx( TS_SYSPREP_KEY ) failed: 0x%x", v11);
        for ( i = 0; i < 8; ++i )
        {
          EventW = CreateEventW(0, bManualReset[i], 0, 0);
          *((_QWORD *)this + i + 204) = EventW;
          if ( !EventW )
            goto LABEL_28;
        }
        CPolicyMonitor::hPolicyChangeEvent = (HANDLE)*((_QWORD *)this + 205);
        started = CPolicyMonitor::StartWaitOnRegistry(this, 0x7FFFFFFFu);
        v4 = started;
        if ( started < 0 )
        {
          _DbgPrintMessage(8, "StartWaitOnRegistry failed: 0x%x in %s", started, "CPolicyMonitor::CPolicyMonitor");
          goto LABEL_43;
        }
        ThreadpoolWork = CreateThreadpoolWork(CPolicyMonitor::staticPolicyMonitorWorker, this, 0);
        *((_QWORD *)this + 213) = ThreadpoolWork;
        if ( !ThreadpoolWork )
        {
LABEL_28:
          LastError = GetLastError();
          v4 = LastError;
          if ( LastError > 0 )
            v4 = (unsigned __int16)LastError | 0x80070000;
          goto LABEL_43;
        }
        v18 = RtlSubscribeWnfStateChangeNotification(
                (char *)this + 1712,
                WNF_GPOL_SYSTEM_CHANGES,
                0,
                CPolicyMonitor::OnNotificationTriggered,
                0,
                0,
                0,
                1,
                *(_QWORD *)bManualReset,
                *(_QWORD *)&bManualReset[2],
                si128.m128i_i64[0],
                si128.m128i_i64[1],
                v23);
        if ( v18 >= 0 )
        {
          if ( (unsigned int)OOBEComplete(&v25)
            && !v25
            && !(unsigned int)RegisterWaitUntilOOBECompleted(
                                CPolicyMonitor::staticOOBENotificationCallback,
                                this,
                                (char *)this + 1720)
            && GetLastError() != 5023 )
          {
            v19 = GetLastError();
            if ( v19 > 0 )
              v19 = (unsigned __int16)v19 | 0x80070000;
            _DbgPrintMessage(
              4,
              "Registration of OOBE completion notification has failed: 0x%x. Non fatal error, continuing.",
              v19);
          }
          SubmitThreadpoolWork(*((PTP_WORK *)this + 213));
          v4 = 0;
        }
        else
        {
          v4 = v18 | 0x10000000;
        }
      }
      else
      {
        _DbgPrintMessage(8, "RegOpenKeyEx( WINSTATION_REG_NAME ) failed: 0x%x", (unsigned int)v4);
      }
    }
  }
  else
  {
    _DbgPrintMessage(8, "RegOpenKeyEx( REG_CONTROL_TSERVER ) failed: 0x%x", (unsigned int)v4);
  }
LABEL_43:
  *a2 = v4;
  return this;
}

```

## disassembly

```asm
0x180012fd8  mov     [rsp+arg_18], rbx
0x180012fdd  mov     [rsp+arg_8], rdx
0x180012fe2  mov     [rsp+arg_0], rcx
0x180012fe7  push    rbp
0x180012fe8  push    rsi
0x180012fe9  push    rdi
0x180012fea  push    r12
0x180012fec  push    r13
0x180012fee  push    r14
0x180012ff0  push    r15
0x180012ff2  sub     rsp, 70h
0x180012ff6  mov     rdi, rcx
0x180012ff9  lea     rdx, aPolicymonitor; "PolicyMonitor"
0x180013000  call    ??0?$CTSObject@UIUnknown@@@@QEAA@PEBD@Z; CTSObject<IUnknown>::CTSObject<IUnknown>(char const *)
0x180013005  nop
0x180013006  lea     rax, ??_7CPolicyMonitor@@6B@; const CPolicyMonitor::`vftable'
0x18001300d  mov     [rdi], rax
0x180013010  xor     edx, edx
0x180013012  mov     [rdi+6C0h], edx
0x180013018  mov     [rsp+0A8h+arg_10], 1
0x180013023  xorps   xmm0, xmm0
0x180013026  movdqu  xmmword ptr [rsp+0A8h+bManualReset], xmm0
0x18001302c  movdqa  xmm1, cs:__xmm@00000001000000000000000000000000
0x180013034  movdqu  [rsp+0A8h+var_58], xmm1
0x18001303a  mov     [rsp+0A8h+var_48], edx
0x18001303e  lea     rax, [rdi+638h]
0x180013045  mov     [rax], rdx
0x180013048  lea     rsi, [rdi+640h]
0x18001304f  mov     [rsi], rdx
0x180013052  lea     r14, [rdi+648h]
0x180013059  mov     [r14], rdx
0x18001305c  lea     r15, [rdi+650h]
0x180013063  mov     [r15], rdx
0x180013066  lea     rbp, [rdi+658h]
0x18001306d  mov     [rbp+0], rdx
0x180013071  xor     ecx, ecx
0x180013073  mov     [rdi+660h], rcx
0x18001307a  mov     [rdi+668h], cl
0x180013080  mov     cs:?hPolicyChangeEvent@CPolicyMonitor@@0PEAXEA, rdx; void * CPolicyMonitor::hPolicyChangeEvent
0x180013087  mov     [rdi+6A8h], rdx
0x18001308e  lea     r12, [rdi+6B0h]
0x180013095  mov     [r12], rdx
0x180013099  lea     r13, [rdi+6B8h]
0x1800130a0  mov     [r13+0], rdx
0x1800130a4  mov     [rsp+0A8h+phkResult], rax; phkResult
0x1800130a9  mov     r9d, 20019h; samDesired
0x1800130af  xor     r8d, r8d; ulOptions
0x1800130b2  lea     rdx, SubKey; "System\\CurrentControlSet\\Control\\Ter"...
0x1800130b9  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800130c0  call    cs:__imp_RegOpenKeyExW
0x1800130c7  nop     dword ptr [rax+rax+00h]
0x1800130cc  mov     ebx, eax
0x1800130ce  test    eax, eax
0x1800130d0  jle     short loc_1800130DB
0x1800130d2  movzx   ebx, ax
0x1800130d5  or      ebx, 80070000h
0x1800130db  test    ebx, ebx
0x1800130dd  jns     short loc_1800130F8
0x1800130df  lea     rdx, aRegopenkeyexRe; "RegOpenKeyEx( REG_CONTROL_TSERVER ) fai"...
0x1800130e6  mov     r8d, ebx
0x1800130e9  mov     ecx, 8; int
0x1800130ee  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x1800130f3  jmp     loc_180013406
0x1800130f8  mov     [rsp+0A8h+phkResult], rsi; phkResult
0x1800130fd  mov     r9d, 20019h; samDesired
0x180013103  xor     r8d, r8d; ulOptions
0x180013106  lea     rdx, aSystemCurrentc_0; "System\\CurrentControlSet\\Control\\LSA"...
0x18001310d  mov     rbx, 0FFFFFFFF80000002h
0x180013114  mov     rcx, rbx; hKey
0x180013117  call    cs:__imp_RegOpenKeyExW
0x18001311e  nop     dword ptr [rax+rax+00h]
0x180013123  test    eax, eax
0x180013125  jle     short loc_180013131
0x180013127  movzx   eax, ax
0x18001312a  or      eax, 80070000h
0x18001312f  test    eax, eax
0x180013131  jns     short loc_18001318C
0x180013133  mov     r8d, eax
0x180013136  lea     rdx, aRegopenkeyexTs_1; "RegOpenKeyEx( TS_FIPS_POLICY ) failed: "...
0x18001313d  mov     ecx, 4; int
0x180013142  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180013147  mov     [rsp+0A8h+phkResult], rsi; phkResult
0x18001314c  mov     esi, 20019h
0x180013151  mov     r9d, esi; samDesired
0x180013154  xor     r8d, r8d; ulOptions
0x180013157  lea     rdx, aSystemCurrentc_5; "System\\CurrentControlSet\\Control\\LSA"
0x18001315e  mov     rcx, rbx; hKey
0x180013161  call    cs:__imp_RegOpenKeyExW
0x180013168  nop     dword ptr [rax+rax+00h]
0x18001316d  mov     ebx, eax
0x18001316f  test    eax, eax
0x180013171  jle     short loc_18001317C
0x180013173  movzx   ebx, ax
0x180013176  or      ebx, 80070000h
0x18001317c  test    ebx, ebx
0x18001317e  jns     short loc_180013193
0x180013180  lea     rdx, aRegopenkeyexTs; "RegOpenKeyEx( TS_LEGACY_FIPS_POLICY ) f"...
0x180013187  jmp     loc_1800130E6
0x18001318c  mov     esi, 20019h
0x180013191  jmp     short loc_18001319A
0x180013193  mov     rbx, 0FFFFFFFF80000002h
0x18001319a  mov     [rsp+0A8h+phkResult], r14; phkResult
0x18001319f  mov     r9d, esi; samDesired
0x1800131a2  xor     r8d, r8d; ulOptions
0x1800131a5  lea     rdx, aSystemCurrentc_8; "System\\CurrentControlSet\\Control\\Ter"...
0x1800131ac  mov     rcx, rbx; hKey
0x1800131af  call    cs:__imp_RegOpenKeyExW
0x1800131b6  nop     dword ptr [rax+rax+00h]
0x1800131bb  mov     ebx, eax
0x1800131bd  xor     r14d, r14d
0x1800131c0  test    eax, eax
0x1800131c2  jle     short loc_1800131CD
0x1800131c4  movzx   ebx, ax
0x1800131c7  or      ebx, 80070000h
0x1800131cd  test    ebx, ebx
0x1800131cf  jns     short loc_1800131DD
0x1800131d1  lea     rdx, aRegopenkeyexWi; "RegOpenKeyEx( WINSTATION_REG_NAME ) fai"...
0x1800131d8  jmp     loc_1800130E6
0x1800131dd  mov     [rsp+0A8h+phkResult], r15; phkResult
0x1800131e2  mov     r9d, esi; samDesired
0x1800131e5  xor     r8d, r8d; ulOptions
0x1800131e8  lea     rdx, aSystemCurrentc_13; "System\\CurrentControlSet\\Control\\Ter"...
0x1800131ef  mov     rbx, 0FFFFFFFF80000002h
0x1800131f6  mov     rcx, rbx; hKey
0x1800131f9  call    cs:__imp_RegOpenKeyExW
0x180013200  nop     dword ptr [rax+rax+00h]
0x180013205  mov     r15d, 80070000h
0x18001320b  test    eax, eax
0x18001320d  jle     short loc_180013217
0x18001320f  movzx   eax, ax
0x180013212  or      eax, r15d
0x180013215  test    eax, eax
0x180013217  jns     short loc_18001322D
0x180013219  mov     r8d, eax
0x18001321c  lea     rdx, aRegopenkeyexRe_0; "RegOpenKeyEx( REG_TS_CLUSTERSETTINGS ) "...
0x180013223  mov     ecx, 4; int
0x180013228  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18001322d  mov     [rsp+0A8h+phkResult], rbp; phkResult
0x180013232  mov     r9d, esi; samDesired
0x180013235  xor     r8d, r8d; ulOptions
0x180013238  lea     rdx, aSystemSetup; "SYSTEM\\Setup"
0x18001323f  mov     rcx, rbx; hKey
0x180013242  call    cs:__imp_RegOpenKeyExW
0x180013249  nop     dword ptr [rax+rax+00h]
0x18001324e  test    eax, eax
0x180013250  jle     short loc_18001325A
0x180013252  movzx   eax, ax
0x180013255  or      eax, r15d
0x180013258  test    eax, eax
0x18001325a  jns     short loc_180013270
0x18001325c  mov     r8d, eax
0x18001325f  lea     rdx, aRegopenkeyexTs_0; "RegOpenKeyEx( TS_SYSPREP_KEY ) failed: "...
0x180013266  mov     ecx, 4; int
0x18001326b  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180013270  mov     esi, r14d
0x180013273  cmp     esi, 8
0x180013276  jnb     short loc_1800132C4
0x180013278  mov     ebx, esi
0x18001327a  xor     r9d, r9d; lpName
0x18001327d  xor     r8d, r8d; bInitialState
0x180013280  mov     edx, [rsp+rbx*4+0A8h+bManualReset]; bManualReset
0x180013284  xor     ecx, ecx; lpEventAttributes
0x180013286  call    cs:__imp_CreateEventW
0x18001328d  nop     dword ptr [rax+rax+00h]
0x180013292  mov     [rdi+rbx*8+660h], rax
0x18001329a  test    rax, rax
0x18001329d  jz      short loc_1800132A3
0x18001329f  inc     esi
0x1800132a1  jmp     short loc_180013273
0x1800132a3  call    cs:__imp_GetLastError
0x1800132aa  nop     dword ptr [rax+rax+00h]
0x1800132af  mov     ebx, eax
0x1800132b1  test    eax, eax
0x1800132b3  jle     loc_180013406
0x1800132b9  movzx   ebx, ax
0x1800132bc  or      ebx, r15d
0x1800132bf  jmp     loc_180013406
0x1800132c4  mov     rax, [rdi+668h]
0x1800132cb  mov     cs:?hPolicyChangeEvent@CPolicyMonitor@@0PEAXEA, rax; void * CPolicyMonitor::hPolicyChangeEvent
0x1800132d2  mov     edx, 7FFFFFFFh; unsigned int
0x1800132d7  mov     rcx, rdi; this
0x1800132da  call    ?StartWaitOnRegistry@CPolicyMonitor@@AEAAJK@Z; CPolicyMonitor::StartWaitOnRegistry(ulong)
0x1800132df  mov     ebx, eax
0x1800132e1  test    eax, eax
0x1800132e3  jns     short loc_180013305
0x1800132e5  lea     r9, aCpolicymonitor; "CPolicyMonitor::CPolicyMonitor"
0x1800132ec  mov     r8d, eax
0x1800132ef  lea     rdx, aStartwaitonreg; "StartWaitOnRegistry failed: 0x%x in %s"
0x1800132f6  mov     ecx, 8; int
0x1800132fb  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180013300  jmp     loc_180013406
0x180013305  xor     r8d, r8d; pcbe
0x180013308  mov     rdx, rdi; pv
0x18001330b  lea     rcx, ?staticPolicyMonitorWorker@CPolicyMonitor@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x180013312  call    cs:__imp_CreateThreadpoolWork
0x180013319  nop     dword ptr [rax+rax+00h]
0x18001331e  mov     [rdi+6A8h], rax
0x180013325  test    rax, rax
0x180013328  jz      loc_1800132A3
0x18001332e  mov     [rsp+0A8h+var_70], 1
0x180013336  mov     [rsp+0A8h+var_78], r14d
0x18001333b  mov     [rsp+0A8h+var_80], r14
0x180013340  mov     [rsp+0A8h+phkResult], r14
0x180013345  lea     r9, ?OnNotificationTriggered@CPolicyMonitor@@CAJU_WNF_STATE_NAME@@KPEAU_WNF_TYPE_ID@@PEAXPEBXK@Z; CPolicyMonitor::OnNotificationTriggered(_WNF_STATE_NAME,ulong,_WNF_TYPE_ID *,void *,void const *,ulong)
0x18001334c  xor     r8d, r8d
0x18001334f  mov     rdx, cs:WNF_GPOL_SYSTEM_CHANGES
0x180013356  mov     rcx, r12
0x180013359  call    cs:__imp_RtlSubscribeWnfStateChangeNotification
0x180013360  nop     dword ptr [rax+rax+00h]
0x180013365  mov     ebx, eax
0x180013367  test    eax, eax
0x180013369  jns     short loc_180013374
0x18001336b  bts     ebx, 1Ch
0x18001336f  jmp     loc_180013406
0x180013374  lea     rcx, [rsp+0A8h+arg_10]
0x18001337c  call    cs:__imp_OOBEComplete
0x180013383  nop     dword ptr [rax+rax+00h]
0x180013388  test    eax, eax
0x18001338a  jz      short loc_1800133F0
0x18001338c  cmp     [rsp+0A8h+arg_10], r14d
0x180013394  jnz     short loc_1800133F0
0x180013396  mov     r8, r13
0x180013399  mov     rdx, rdi
0x18001339c  lea     rcx, ?staticOOBENotificationCallback@CPolicyMonitor@@CAXPEAX@Z; CPolicyMonitor::staticOOBENotificationCallback(void *)
0x1800133a3  call    cs:__imp_RegisterWaitUntilOOBECompleted
0x1800133aa  nop     dword ptr [rax+rax+00h]
0x1800133af  test    eax, eax
0x1800133b1  jnz     short loc_1800133F0
0x1800133b3  call    cs:__imp_GetLastError
0x1800133ba  nop     dword ptr [rax+rax+00h]
0x1800133bf  cmp     eax, 139Fh
0x1800133c4  jz      short loc_1800133F0
0x1800133c6  call    cs:__imp_GetLastError
0x1800133cd  nop     dword ptr [rax+rax+00h]
0x1800133d2  test    eax, eax
0x1800133d4  jle     short loc_1800133DC
0x1800133d6  movzx   eax, ax
0x1800133d9  or      eax, r15d
0x1800133dc  mov     r8d, eax
0x1800133df  lea     rdx, aRegistrationOf; "Registration of OOBE completion notific"...
0x1800133e6  mov     ecx, 4; int
0x1800133eb  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x1800133f0  mov     rcx, [rdi+6A8h]; pwk
0x1800133f7  call    cs:__imp_SubmitThreadpoolWork
0x1800133fe  nop     dword ptr [rax+rax+00h]
0x180013403  mov     ebx, r14d
0x180013406  mov     rax, [rsp+0A8h+arg_8]
0x18001340e  mov     [rax], ebx
0x180013410  mov     rax, rdi
0x180013413  mov     rbx, [rsp+0A8h+arg_18]
0x18001341b  add     rsp, 70h
0x18001341f  pop     r15
0x180013421  pop     r14
0x180013423  pop     r13
0x180013425  pop     r12
0x180013427  pop     rdi
0x180013428  pop     rsi
0x180013429  pop     rbp
0x18001342a  retn
```
