# CPolicyMonitor::CPolicyMonitor(long *)

- ea: `0x18000f434`
- end: `0x18000f826`
- name: `??0CPolicyMonitor@@QEAA@PEAJ@Z`
- size: `1010`
- prototype: `CPolicyMonitor *__fastcall(CPolicyMonitor *__hidden this, int *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18002ae4c`

## callees

- `0x1800074c0`
- `0x18000f434`
- `0x180010910`
- `0x1800291d8`

## import_xrefs

- `ntdll!RtlSubscribeWnfStateChangeNotification` at `0x18000f77b`
- `ntdll!RtlSubscribeWnfStateChangeNotification` at `0x18000f77b`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000f6be`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000f6be`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f6d5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f7c0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f7cd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f6d5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f7c0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f7cd`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18000f73e`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18000f73e`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18000f7f8`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18000f7f8`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000f51c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000f56d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000f5b1`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000f5f9`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000f63d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000f680`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000f51c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000f56d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000f5b1`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000f5f9`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000f63d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000f680`
- `api-ms-win-oobe-notification-l1-1-0!RegisterWaitUntilOOBECompleted` at `0x18000f7b6`
- `api-ms-win-oobe-notification-l1-1-0!RegisterWaitUntilOOBECompleted` at `0x18000f7b6`
- `api-ms-win-oobe-notification-l1-1-0!OOBEComplete` at `0x18000f795`
- `api-ms-win-oobe-notification-l1-1-0!OOBEComplete` at `0x18000f795`

## string_xrefs

- `0x18000f7e0`: `Registration of OOBE completion notification has failed: 0x%x. Non fatal error, continuing.`
- `0x18000f586`: `RegOpenKeyEx( TS_FIPS_POLICY ) failed: 0x%x`
- `0x18000f535`: `RegOpenKeyEx( REG_CONTROL_TSERVER ) failed: 0x%x`
- `0x18000f5ca`: `RegOpenKeyEx( TS_LEGACY_FIPS_POLICY ) failed: 0x%x`
- `0x18000f615`: `RegOpenKeyEx( WINSTATION_REG_NAME ) failed: 0x%x`
- `0x18000f65a`: `RegOpenKeyEx( REG_TS_CLUSTERSETTINGS ) failed: 0x%x`
- `0x18000f697`: `RegOpenKeyEx( TS_SYSPREP_KEY ) failed: 0x%x`
- `0x18000f71b`: `StartWaitOnRegistry failed: 0x%x in %s`

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
0x18000f434  mov     [rsp+arg_18], rbx
0x18000f439  mov     [rsp+arg_8], rdx
0x18000f43e  mov     [rsp+arg_0], rcx
0x18000f443  push    rbp
0x18000f444  push    rsi
0x18000f445  push    rdi
0x18000f446  push    r12
0x18000f448  push    r13
0x18000f44a  push    r14
0x18000f44c  push    r15
0x18000f44e  sub     rsp, 70h
0x18000f452  mov     rdi, rcx
0x18000f455  lea     rdx, aPolicymonitor; "PolicyMonitor"
0x18000f45c  call    ??0?$CTSObject@UIUnknown@@@@QEAA@PEBD@Z; CTSObject<IUnknown>::CTSObject<IUnknown>(char const *)
0x18000f461  nop
0x18000f462  lea     rax, ??_7CPolicyMonitor@@6B@; const CPolicyMonitor::`vftable'
0x18000f469  mov     [rdi], rax
0x18000f46c  xor     edx, edx
0x18000f46e  mov     [rdi+6C0h], edx
0x18000f474  mov     [rsp+0A8h+arg_10], 1
0x18000f47f  xorps   xmm0, xmm0
0x18000f482  movdqu  xmmword ptr [rsp+0A8h+bManualReset], xmm0
0x18000f488  movdqa  xmm1, cs:__xmm@00000001000000000000000000000000
0x18000f490  movdqu  [rsp+0A8h+var_58], xmm1
0x18000f496  mov     [rsp+0A8h+var_48], edx
0x18000f49a  lea     rax, [rdi+638h]
0x18000f4a1  mov     [rax], rdx
0x18000f4a4  lea     rsi, [rdi+640h]
0x18000f4ab  mov     [rsi], rdx
0x18000f4ae  lea     r14, [rdi+648h]
0x18000f4b5  mov     [r14], rdx
0x18000f4b8  lea     r15, [rdi+650h]
0x18000f4bf  mov     [r15], rdx
0x18000f4c2  lea     rbp, [rdi+658h]
0x18000f4c9  mov     [rbp+0], rdx
0x18000f4cd  xor     ecx, ecx
0x18000f4cf  mov     [rdi+660h], rcx
0x18000f4d6  mov     [rdi+668h], cl
0x18000f4dc  mov     cs:?hPolicyChangeEvent@CPolicyMonitor@@0PEAXEA, rdx; void * CPolicyMonitor::hPolicyChangeEvent
0x18000f4e3  mov     [rdi+6A8h], rdx
0x18000f4ea  lea     r12, [rdi+6B0h]
0x18000f4f1  mov     [r12], rdx
0x18000f4f5  lea     r13, [rdi+6B8h]
0x18000f4fc  mov     [r13+0], rdx
0x18000f500  mov     [rsp+0A8h+phkResult], rax; phkResult
0x18000f505  mov     r9d, 20019h; samDesired
0x18000f50b  xor     r8d, r8d; ulOptions
0x18000f50e  lea     rdx, SubKey; "System\\CurrentControlSet\\Control\\Ter"...
0x18000f515  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000f51c  call    cs:__imp_RegOpenKeyExW
0x18000f522  mov     ebx, eax
0x18000f524  test    eax, eax
0x18000f526  jle     short loc_18000F531
0x18000f528  movzx   ebx, ax
0x18000f52b  or      ebx, 80070000h
0x18000f531  test    ebx, ebx
0x18000f533  jns     short loc_18000F54E
0x18000f535  lea     rdx, aRegopenkeyexRe; "RegOpenKeyEx( REG_CONTROL_TSERVER ) fai"...
0x18000f53c  mov     r8d, ebx
0x18000f53f  mov     ecx, 8; int
0x18000f544  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000f549  jmp     loc_18000F801
0x18000f54e  mov     [rsp+0A8h+phkResult], rsi; phkResult
0x18000f553  mov     r9d, 20019h; samDesired
0x18000f559  xor     r8d, r8d; ulOptions
0x18000f55c  lea     rdx, aSystemCurrentc_0; "System\\CurrentControlSet\\Control\\LSA"...
0x18000f563  mov     rbx, 0FFFFFFFF80000002h
0x18000f56a  mov     rcx, rbx; hKey
0x18000f56d  call    cs:__imp_RegOpenKeyExW
0x18000f573  test    eax, eax
0x18000f575  jle     short loc_18000F581
0x18000f577  movzx   eax, ax
0x18000f57a  or      eax, 80070000h
0x18000f57f  test    eax, eax
0x18000f581  jns     short loc_18000F5D6
0x18000f583  mov     r8d, eax
0x18000f586  lea     rdx, aRegopenkeyexTs_1; "RegOpenKeyEx( TS_FIPS_POLICY ) failed: "...
0x18000f58d  mov     ecx, 4; int
0x18000f592  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000f597  mov     [rsp+0A8h+phkResult], rsi; phkResult
0x18000f59c  mov     esi, 20019h
0x18000f5a1  mov     r9d, esi; samDesired
0x18000f5a4  xor     r8d, r8d; ulOptions
0x18000f5a7  lea     rdx, aSystemCurrentc_5; "System\\CurrentControlSet\\Control\\LSA"
0x18000f5ae  mov     rcx, rbx; hKey
0x18000f5b1  call    cs:__imp_RegOpenKeyExW
0x18000f5b7  mov     ebx, eax
0x18000f5b9  test    eax, eax
0x18000f5bb  jle     short loc_18000F5C6
0x18000f5bd  movzx   ebx, ax
0x18000f5c0  or      ebx, 80070000h
0x18000f5c6  test    ebx, ebx
0x18000f5c8  jns     short loc_18000F5DD
0x18000f5ca  lea     rdx, aRegopenkeyexTs; "RegOpenKeyEx( TS_LEGACY_FIPS_POLICY ) f"...
0x18000f5d1  jmp     loc_18000F53C
0x18000f5d6  mov     esi, 20019h
0x18000f5db  jmp     short loc_18000F5E4
0x18000f5dd  mov     rbx, 0FFFFFFFF80000002h
0x18000f5e4  mov     [rsp+0A8h+phkResult], r14; phkResult
0x18000f5e9  mov     r9d, esi; samDesired
0x18000f5ec  xor     r8d, r8d; ulOptions
0x18000f5ef  lea     rdx, aSystemCurrentc_8; "System\\CurrentControlSet\\Control\\Ter"...
0x18000f5f6  mov     rcx, rbx; hKey
0x18000f5f9  call    cs:__imp_RegOpenKeyExW
0x18000f5ff  mov     ebx, eax
0x18000f601  xor     r14d, r14d
0x18000f604  test    eax, eax
0x18000f606  jle     short loc_18000F611
0x18000f608  movzx   ebx, ax
0x18000f60b  or      ebx, 80070000h
0x18000f611  test    ebx, ebx
0x18000f613  jns     short loc_18000F621
0x18000f615  lea     rdx, aRegopenkeyexWi; "RegOpenKeyEx( WINSTATION_REG_NAME ) fai"...
0x18000f61c  jmp     loc_18000F53C
0x18000f621  mov     [rsp+0A8h+phkResult], r15; phkResult
0x18000f626  mov     r9d, esi; samDesired
0x18000f629  xor     r8d, r8d; ulOptions
0x18000f62c  lea     rdx, aSystemCurrentc_13; "System\\CurrentControlSet\\Control\\Ter"...
0x18000f633  mov     rbx, 0FFFFFFFF80000002h
0x18000f63a  mov     rcx, rbx; hKey
0x18000f63d  call    cs:__imp_RegOpenKeyExW
0x18000f643  mov     r15d, 80070000h
0x18000f649  test    eax, eax
0x18000f64b  jle     short loc_18000F655
0x18000f64d  movzx   eax, ax
0x18000f650  or      eax, r15d
0x18000f653  test    eax, eax
0x18000f655  jns     short loc_18000F66B
0x18000f657  mov     r8d, eax
0x18000f65a  lea     rdx, aRegopenkeyexRe_0; "RegOpenKeyEx( REG_TS_CLUSTERSETTINGS ) "...
0x18000f661  mov     ecx, 4; int
0x18000f666  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000f66b  mov     [rsp+0A8h+phkResult], rbp; phkResult
0x18000f670  mov     r9d, esi; samDesired
0x18000f673  xor     r8d, r8d; ulOptions
0x18000f676  lea     rdx, aSystemSetup; "SYSTEM\\Setup"
0x18000f67d  mov     rcx, rbx; hKey
0x18000f680  call    cs:__imp_RegOpenKeyExW
0x18000f686  test    eax, eax
0x18000f688  jle     short loc_18000F692
0x18000f68a  movzx   eax, ax
0x18000f68d  or      eax, r15d
0x18000f690  test    eax, eax
0x18000f692  jns     short loc_18000F6A8
0x18000f694  mov     r8d, eax
0x18000f697  lea     rdx, aRegopenkeyexTs_0; "RegOpenKeyEx( TS_SYSPREP_KEY ) failed: "...
0x18000f69e  mov     ecx, 4; int
0x18000f6a3  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000f6a8  mov     esi, r14d
0x18000f6ab  cmp     esi, 8
0x18000f6ae  jnb     short loc_18000F6F0
0x18000f6b0  mov     ebx, esi
0x18000f6b2  xor     r9d, r9d; lpName
0x18000f6b5  xor     r8d, r8d; bInitialState
0x18000f6b8  mov     edx, [rsp+rbx*4+0A8h+bManualReset]; bManualReset
0x18000f6bc  xor     ecx, ecx; lpEventAttributes
0x18000f6be  call    cs:__imp_CreateEventW
0x18000f6c4  mov     [rdi+rbx*8+660h], rax
0x18000f6cc  test    rax, rax
0x18000f6cf  jz      short loc_18000F6D5
0x18000f6d1  inc     esi
0x18000f6d3  jmp     short loc_18000F6AB
0x18000f6d5  call    cs:__imp_GetLastError
0x18000f6db  mov     ebx, eax
0x18000f6dd  test    eax, eax
0x18000f6df  jle     loc_18000F801
0x18000f6e5  movzx   ebx, ax
0x18000f6e8  or      ebx, r15d
0x18000f6eb  jmp     loc_18000F801
0x18000f6f0  mov     rax, [rdi+668h]
0x18000f6f7  mov     cs:?hPolicyChangeEvent@CPolicyMonitor@@0PEAXEA, rax; void * CPolicyMonitor::hPolicyChangeEvent
0x18000f6fe  mov     edx, 7FFFFFFFh; unsigned int
0x18000f703  mov     rcx, rdi; this
0x18000f706  call    ?StartWaitOnRegistry@CPolicyMonitor@@AEAAJK@Z; CPolicyMonitor::StartWaitOnRegistry(ulong)
0x18000f70b  mov     ebx, eax
0x18000f70d  test    eax, eax
0x18000f70f  jns     short loc_18000F731
0x18000f711  lea     r9, aCpolicymonitor; "CPolicyMonitor::CPolicyMonitor"
0x18000f718  mov     r8d, eax
0x18000f71b  lea     rdx, aStartwaitonreg; "StartWaitOnRegistry failed: 0x%x in %s"
0x18000f722  mov     ecx, 8; int
0x18000f727  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000f72c  jmp     loc_18000F801
0x18000f731  xor     r8d, r8d; pcbe
0x18000f734  mov     rdx, rdi; pv
0x18000f737  lea     rcx, ?staticPolicyMonitorWorker@CPolicyMonitor@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x18000f73e  call    cs:__imp_CreateThreadpoolWork
0x18000f744  mov     [rdi+6A8h], rax
0x18000f74b  test    rax, rax
0x18000f74e  jz      short loc_18000F6D5
0x18000f750  mov     [rsp+0A8h+var_70], 1
0x18000f758  mov     [rsp+0A8h+var_78], r14d
0x18000f75d  mov     [rsp+0A8h+var_80], r14
0x18000f762  mov     [rsp+0A8h+phkResult], r14
0x18000f767  lea     r9, ?OnNotificationTriggered@CPolicyMonitor@@CAJU_WNF_STATE_NAME@@KPEAU_WNF_TYPE_ID@@PEAXPEBXK@Z; CPolicyMonitor::OnNotificationTriggered(_WNF_STATE_NAME,ulong,_WNF_TYPE_ID *,void *,void const *,ulong)
0x18000f76e  xor     r8d, r8d
0x18000f771  mov     rdx, cs:WNF_GPOL_SYSTEM_CHANGES
0x18000f778  mov     rcx, r12
0x18000f77b  call    cs:__imp_RtlSubscribeWnfStateChangeNotification
0x18000f781  mov     ebx, eax
0x18000f783  test    eax, eax
0x18000f785  jns     short loc_18000F78D
0x18000f787  bts     ebx, 1Ch
0x18000f78b  jmp     short loc_18000F801
0x18000f78d  lea     rcx, [rsp+0A8h+arg_10]
0x18000f795  call    cs:__imp_OOBEComplete
0x18000f79b  test    eax, eax
0x18000f79d  jz      short loc_18000F7F1
0x18000f79f  cmp     [rsp+0A8h+arg_10], r14d
0x18000f7a7  jnz     short loc_18000F7F1
0x18000f7a9  mov     r8, r13
0x18000f7ac  mov     rdx, rdi
0x18000f7af  lea     rcx, ?staticOOBENotificationCallback@CPolicyMonitor@@CAXPEAX@Z; CPolicyMonitor::staticOOBENotificationCallback(void *)
0x18000f7b6  call    cs:__imp_RegisterWaitUntilOOBECompleted
0x18000f7bc  test    eax, eax
0x18000f7be  jnz     short loc_18000F7F1
0x18000f7c0  call    cs:__imp_GetLastError
0x18000f7c6  cmp     eax, 139Fh
0x18000f7cb  jz      short loc_18000F7F1
0x18000f7cd  call    cs:__imp_GetLastError
0x18000f7d3  test    eax, eax
0x18000f7d5  jle     short loc_18000F7DD
0x18000f7d7  movzx   eax, ax
0x18000f7da  or      eax, r15d
0x18000f7dd  mov     r8d, eax
0x18000f7e0  lea     rdx, aRegistrationOf; "Registration of OOBE completion notific"...
0x18000f7e7  mov     ecx, 4; int
0x18000f7ec  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000f7f1  mov     rcx, [rdi+6A8h]; pwk
0x18000f7f8  call    cs:__imp_SubmitThreadpoolWork
0x18000f7fe  mov     ebx, r14d
0x18000f801  mov     rax, [rsp+0A8h+arg_8]
0x18000f809  mov     [rax], ebx
0x18000f80b  mov     rax, rdi
0x18000f80e  mov     rbx, [rsp+0A8h+arg_18]
0x18000f816  add     rsp, 70h
0x18000f81a  pop     r15
0x18000f81c  pop     r14
0x18000f81e  pop     r13
0x18000f820  pop     r12
0x18000f822  pop     rdi
0x18000f823  pop     rsi
0x18000f824  pop     rbp
0x18000f825  retn
```
