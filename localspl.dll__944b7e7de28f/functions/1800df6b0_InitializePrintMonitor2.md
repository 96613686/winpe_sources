# InitializePrintMonitor2

- ea: `0x1800df6b0`
- end: `0x1800df89a`
- name: `InitializePrintMonitor2`
- size: `490`
- prototype: `LPMONITOR2 __stdcall(PMONITORINIT pMonitorInit, PHANDLE phMonitor)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x1800ddfe8`
- `0x1800df488`
- `0x1800df6b0`
- `0x1800e1be8`
- `0x1800e1e54`
- `0x1800e6010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x1800df79f`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x1800df79f`
- `api-ms-win-crt-private-l1-1-0!_o_iswdigit` at `0x1800df7c7`
- `api-ms-win-crt-private-l1-1-0!_o_iswdigit` at `0x1800df7c7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800df76b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800df76b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800df80e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800df80e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800df72a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800df72a`
- `SPOOLSS!DllFreeSplMem` at `0x1800df73b`
- `SPOOLSS!DllFreeSplMem` at `0x1800df744`
- `SPOOLSS!DllFreeSplMem` at `0x1800df801`
- `SPOOLSS!DllFreeSplMem` at `0x1800df73b`
- `SPOOLSS!DllFreeSplMem` at `0x1800df744`
- `SPOOLSS!DllFreeSplMem` at `0x1800df801`
- `SPOOLSS!DllAllocSplMem` at `0x1800df6ff`
- `SPOOLSS!DllAllocSplMem` at `0x1800df6ff`

## string_xrefs

- `0x1800df839`: `COMWriteTimeoutConstant`

## pseudocode

```c
LPMONITOR2 __stdcall InitializePrintMonitor2(PMONITORINIT pMonitorInit, PHANDLE phMonitor)
{
  unsigned __int16 *v4; // rbx
  struct _INILOCALMON *v5; // rsi
  __int64 v6; // rax
  DWORD PortStrings; // eax
  unsigned __int16 *i; // rbx
  __int64 v10; // rbp
  unsigned int v11; // edi
  __int64 v12; // r14
  HANDLE hSpooler; // [rsp+28h] [rbp-50h]
  unsigned __int16 *v14; // [rsp+88h] [rbp+10h] BYREF
  int v15; // [rsp+90h] [rbp+18h] BYREF
  int v16; // [rsp+98h] [rbp+20h] BYREF

  v4 = 0;
  v14 = 0;
  v5 = 0;
  LocalMonTelemetry::WriteDbgTraceInfo("InitializePrintMonitor2", L"Entering");
  if ( !phMonitor )
    goto LABEL_6;
  if ( !pMonitorInit->bLocal )
    goto LABEL_6;
  *phMonitor = 0;
  v6 = DllAllocSplMem(32);
  v5 = (struct _INILOCALMON *)v6;
  if ( !v6 )
    goto LABEL_6;
  *(_DWORD *)v6 = 5065801;
  *(_QWORD *)(v6 + 8) = pMonitorInit;
  PortStrings = GetPortStrings(&v14);
  if ( PortStrings )
  {
    SetLastError(PortStrings);
    v4 = v14;
LABEL_6:
    DllFreeSplMem(v4);
    DllFreeSplMem(v5);
    return 0;
  }
  EnterCriticalSection(&LcmSpoolerSection);
  for ( i = v14; i && *i; i += (unsigned int)(v10 + 1) )
  {
    v10 = -1;
    do
      ++v10;
    while ( i[v10] );
    if ( (unsigned int)_o__wcsnicmp(i, L"Ne", 2) )
      goto LABEL_21;
    v11 = 2;
    if ( (unsigned int)v10 > 2 && i[2] == 45 )
      v11 = 3;
    v12 = (unsigned int)(v10 - 1);
    while ( v11 < (unsigned int)v12 )
    {
      if ( !(unsigned int)_o_iswdigit(i[v11]) )
        goto LABEL_21;
      ++v11;
    }
    if ( v11 != (_DWORD)v12 || i[v12] != 58 )
LABEL_21:
      LcmCreatePortEntry(v5, i);
  }
  DllFreeSplMem(v14);
  LeaveCriticalSection(&LcmSpoolerSection);
  CheckAndAddIrdaPort(v5);
  *phMonitor = v5;
  hSpooler = pMonitorInit->hSpooler;
  LODWORD(v14) = 0;
  v16 = 4;
  v15 = 4;
  if ( !((unsigned int (__fastcall *)(HKEY, const wchar_t *, int *, unsigned __int16 **, int *, HANDLE))pMonitorInit->pMonitorReg->fpQueryValue)(
          pMonitorInit->hckRegistryRoot,
          L"COMWriteTimeoutConstant",
          &v16,
          &v14,
          &v15,
          hSpooler) )
    g_COMWriteTimeoutConstant_ms = 1000 * (_DWORD)v14;
  return &Monitor2;
}

```

## disassembly

```asm
0x1800df6b0  mov     rax, rsp
0x1800df6b3  mov     [rax+8], rbx
0x1800df6b7  push    rbp
0x1800df6b8  push    rsi
0x1800df6b9  push    rdi
0x1800df6ba  push    r12
0x1800df6bc  push    r13
0x1800df6be  push    r14
0x1800df6c0  push    r15
0x1800df6c2  sub     rsp, 40h
0x1800df6c6  xor     r13d, r13d
0x1800df6c9  mov     r12, rdx
0x1800df6cc  mov     r15, rcx
0x1800df6cf  lea     rdx, aEntering; "Entering"
0x1800df6d6  mov     ebx, r13d
0x1800df6d9  lea     rcx, aInitializeprin_4; "InitializePrintMonitor2"
0x1800df6e0  mov     [rax+10h], rbx
0x1800df6e4  mov     esi, r13d
0x1800df6e7  call    ?WriteDbgTraceInfo@LocalMonTelemetry@@SAXPEADPEAGZZ; LocalMonTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x1800df6ec  test    r12, r12
0x1800df6ef  jz      short loc_1800DF738
0x1800df6f1  cmp     [r15+20h], r13d
0x1800df6f5  jz      short loc_1800DF738
0x1800df6f7  lea     ecx, [r13+20h]
0x1800df6fb  mov     [r12], r13
0x1800df6ff  call    cs:__imp_DllAllocSplMem
0x1800df705  mov     rsi, rax
0x1800df708  test    rax, rax
0x1800df70b  jz      short loc_1800DF738
0x1800df70d  lea     rcx, [rsp+78h+arg_8]; unsigned __int16 **
0x1800df715  mov     dword ptr [rax], 4D4C49h
0x1800df71b  mov     [rax+8], r15
0x1800df71f  call    ?GetPortStrings@@YAKPEAPEAG@Z; GetPortStrings(ushort * *)
0x1800df724  test    eax, eax
0x1800df726  jz      short loc_1800DF764
0x1800df728  mov     ecx, eax; dwErrCode
0x1800df72a  call    cs:__imp_SetLastError
0x1800df730  mov     rbx, [rsp+78h+arg_8]
0x1800df738  mov     rcx, rbx
0x1800df73b  call    cs:__imp_DllFreeSplMem
0x1800df741  mov     rcx, rsi
0x1800df744  call    cs:__imp_DllFreeSplMem
0x1800df74a  xor     eax, eax
0x1800df74c  mov     rbx, [rsp+78h+arg_0]
0x1800df754  add     rsp, 40h
0x1800df758  pop     r15
0x1800df75a  pop     r14
0x1800df75c  pop     r13
0x1800df75e  pop     r12
0x1800df760  pop     rdi
0x1800df761  pop     rsi
0x1800df762  pop     rbp
0x1800df763  retn
0x1800df764  lea     rcx, ?LcmSpoolerSection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1800df76b  call    cs:__imp_EnterCriticalSection
0x1800df771  mov     rbx, [rsp+78h+arg_8]
0x1800df779  jmp     short loc_1800DF7F4
0x1800df77b  cmp     [rbx], r13w
0x1800df77f  jz      short loc_1800DF7F9
0x1800df781  or      rbp, 0FFFFFFFFFFFFFFFFh
0x1800df785  inc     rbp
0x1800df788  cmp     [rbx+rbp*2], r13w
0x1800df78d  jnz     short loc_1800DF785
0x1800df78f  mov     r8d, 2
0x1800df795  lea     rdx, aNe; "Ne"
0x1800df79c  mov     rcx, rbx
0x1800df79f  call    cs:__imp__o__wcsnicmp
0x1800df7a5  test    eax, eax
0x1800df7a7  jnz     short loc_1800DF7E2
0x1800df7a9  lea     edi, [rax+2]
0x1800df7ac  cmp     ebp, edi
0x1800df7ae  jbe     short loc_1800DF7BB
0x1800df7b0  cmp     word ptr [rbx+4], 2Dh ; '-'
0x1800df7b5  lea     eax, [rdi+1]
0x1800df7b8  cmovz   edi, eax
0x1800df7bb  lea     r14d, [rbp-1]
0x1800df7bf  jmp     short loc_1800DF7D3
0x1800df7c1  mov     ecx, edi
0x1800df7c3  movzx   ecx, word ptr [rbx+rcx*2]
0x1800df7c7  call    cs:__imp__o_iswdigit
0x1800df7cd  test    eax, eax
0x1800df7cf  jz      short loc_1800DF7E2
0x1800df7d1  inc     edi
0x1800df7d3  cmp     edi, r14d
0x1800df7d6  jb      short loc_1800DF7C1
0x1800df7d8  jnz     short loc_1800DF7E2
0x1800df7da  cmp     word ptr [rbx+r14*2], 3Ah ; ':'
0x1800df7e0  jz      short loc_1800DF7ED
0x1800df7e2  mov     rdx, rbx; unsigned __int16 *
0x1800df7e5  mov     rcx, rsi; struct _INILOCALMON *
0x1800df7e8  call    ?LcmCreatePortEntry@@YAPEAU_LCMINIPORT@@PEAU_INILOCALMON@@PEBG@Z; LcmCreatePortEntry(_INILOCALMON *,ushort const *)
0x1800df7ed  lea     eax, [rbp+1]
0x1800df7f0  lea     rbx, [rbx+rax*2]
0x1800df7f4  test    rbx, rbx
0x1800df7f7  jnz     short loc_1800DF77B
0x1800df7f9  mov     rcx, [rsp+78h+arg_8]
0x1800df801  call    cs:__imp_DllFreeSplMem
0x1800df807  lea     rcx, ?LcmSpoolerSection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1800df80e  call    cs:__imp_LeaveCriticalSection
0x1800df814  mov     rcx, rsi; struct _INILOCALMON *
0x1800df817  call    ?CheckAndAddIrdaPort@@YAXPEAU_INILOCALMON@@@Z; CheckAndAddIrdaPort(_INILOCALMON *)
0x1800df81c  mov     [r12], rsi
0x1800df820  lea     r9, [rsp+78h+arg_8]
0x1800df828  mov     rcx, [r15+8]
0x1800df82c  lea     r8, [rsp+78h+arg_18]
0x1800df834  mov     [rsp+78h+var_50], rcx
0x1800df839  lea     rdx, aComwritetimeou; "COMWriteTimeoutConstant"
0x1800df840  mov     eax, 4
0x1800df845  mov     dword ptr [rsp+78h+arg_8], r13d
0x1800df84d  mov     [rsp+78h+arg_18], eax
0x1800df854  lea     rcx, [rsp+78h+arg_10]
0x1800df85c  mov     [rsp+78h+arg_10], eax
0x1800df863  mov     rax, [r15+18h]
0x1800df867  mov     [rsp+78h+var_58], rcx
0x1800df86c  mov     rcx, [r15+10h]
0x1800df870  mov     rax, [rax+50h]
0x1800df874  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800df879  test    eax, eax
0x1800df87b  jnz     short loc_1800DF88E
0x1800df87d  imul    eax, dword ptr [rsp+78h+arg_8], 3E8h
0x1800df888  mov     cs:?g_COMWriteTimeoutConstant_ms@@3KA, eax; ulong g_COMWriteTimeoutConstant_ms
0x1800df88e  lea     rax, ?Monitor2@@3U_MONITOR2@@A; _MONITOR2 Monitor2
0x1800df895  jmp     loc_1800DF74C
```
