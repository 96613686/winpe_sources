# InitializeTenantRestrictionsUpdates(void)

- ea: `0x18000b080`
- end: `0x18000b16d`
- name: `?InitializeTenantRestrictionsUpdates@@YAJXZ`
- size: `237`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x180006e94`

## callees

- `0x180002334`
- `0x180006cf4`
- `0x180006d14`
- `0x180009e80`
- `0x18000b080`
- `0x18000c83c`
- `0x18000ca48`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_rand` at `0x18000b0b9`
- `api-ms-win-crt-private-l1-1-0!_o_rand` at `0x18000b0b9`
- `api-ms-win-crt-private-l1-1-0!_o_srand` at `0x18000b0b3`
- `api-ms-win-crt-private-l1-1-0!_o_srand` at `0x18000b0b3`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18000b0ab`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18000b0ab`
- `api-ms-win-core-threadpool-legacy-l1-1-0!CreateTimerQueueTimer` at `0x18000b11b`
- `api-ms-win-core-threadpool-legacy-l1-1-0!CreateTimerQueueTimer` at `0x18000b11b`

## string_xrefs

- `0x18000b12a`: `onecoreuap\ds\ext\common\ntservice\lib\tenantrestrictions.cpp`
- `0x18000b149`: `onecoreuap\ds\ext\common\ntservice\lib\tenantrestrictions.cpp`

## pseudocode

```c
__int64 InitializeTenantRestrictionsUpdates(void)
{
  TenantRestrictions *v0; // rax
  __int64 v1; // rcx
  DWORD TickCount; // eax
  int v3; // eax
  const char *v4; // r9
  int LastError; // eax
  unsigned int v6; // ebx
  __int64 result; // rax
  DWORD DueTime; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  TenantRestrictions *v10; // [rsp+50h] [rbp+8h]

  try
  {
    winrt::init_apartment();
    v10 = (TenantRestrictions *)operator new(0xD8u);
    v0 = TenantRestrictions::TenantRestrictions(v10);
    std::unique_ptr<TenantRestrictions>::reset(v1, v0);
    TickCount = GetTickCount();
    _o_srand(TickCount);
    v3 = rand();
    if ( CreateTimerQueueTimer(
           (PHANDLE)g_trGlobals + 13,
           *((HANDLE *)g_trGlobals + 14),
           UpdateTenantRestrictionsListTimerRoutine,
           0,
           0,
           60000 * (v3 % 960 + 1440),
           0)
      || (LastError = wil::details::in1diag3::Return_GetLastError(
                        retaddr,
                        (void *)0x96,
                        (unsigned int)"onecoreuap\\ds\\ext\\common\\ntservice\\lib\\tenantrestrictions.cpp",
                        v4),
          v6 = LastError,
          LastError >= 0) )
    {
      result = 0;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x26,
        (unsigned int)"onecoreuap\\ds\\ext\\common\\ntservice\\lib\\tenantrestrictions.cpp",
        (const char *)(unsigned int)LastError,
        DueTime);
      result = v6;
    }
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x2A,
                           (unsigned int)"onecoreuap\\ds\\ext\\common\\ntservice\\lib\\tenantrestrictions.cpp",
                           v4);
  }
  return result;
}

```

## disassembly

```asm
0x18000b080  push    rbx
0x18000b082  sub     rsp, 40h
0x18000b086  call    ?init_apartment@winrt@@YAXW4apartment_type@1@@Z; winrt::init_apartment(winrt::apartment_type)
0x18000b08b  mov     ecx, 0D8h; Size
0x18000b090  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000b095  mov     [rsp+48h+arg_0], rax
0x18000b09a  mov     rcx, rax; this
0x18000b09d  call    ??0TenantRestrictions@@QEAA@XZ; TenantRestrictions::TenantRestrictions(void)
0x18000b0a2  nop
0x18000b0a3  mov     rdx, rax
0x18000b0a6  call    ?reset@?$unique_ptr@VTenantRestrictions@@U?$default_delete@VTenantRestrictions@@@std@@@std@@QEAAXPEAVTenantRestrictions@@@Z; std::unique_ptr<TenantRestrictions>::reset(TenantRestrictions *)
0x18000b0ab  call    cs:__imp_GetTickCount
0x18000b0b1  mov     ecx, eax
0x18000b0b3  call    cs:__imp__o_srand
0x18000b0b9  call    cs:__imp_rand
0x18000b0bf  mov     r8d, eax
0x18000b0c2  mov     eax, 88888889h
0x18000b0c7  imul    r8d
0x18000b0ca  add     edx, r8d
0x18000b0cd  sar     edx, 9
0x18000b0d0  mov     ecx, edx
0x18000b0d2  shr     ecx, 1Fh
0x18000b0d5  add     edx, ecx
0x18000b0d7  imul    ecx, edx, 3C0h
0x18000b0dd  sub     r8d, ecx
0x18000b0e0  add     r8d, 5A0h
0x18000b0e7  imul    eax, r8d, 0EA60h
0x18000b0ee  mov     rdx, cs:?g_trGlobals@@3V?$unique_ptr@VTenantRestrictions@@U?$default_delete@VTenantRestrictions@@@std@@@std@@A; std::unique_ptr<TenantRestrictions> g_trGlobals
0x18000b0f5  lea     rcx, [rdx+68h]; phNewTimer
0x18000b0f9  mov     [rsp+48h+Flags], 0; Flags
0x18000b101  mov     [rsp+48h+Period], eax; Period
0x18000b105  mov     [rsp+48h+DueTime], 0; int
0x18000b10d  xor     r9d, r9d; Parameter
0x18000b110  lea     r8, ?UpdateTenantRestrictionsListTimerRoutine@@YAXPEAXE@Z; Callback
0x18000b117  mov     rdx, [rdx+70h]; TimerQueue
0x18000b11b  call    cs:__imp_CreateTimerQueueTimer
0x18000b121  test    eax, eax
0x18000b123  jnz     short loc_18000B15E
0x18000b125  mov     rcx, [rsp+48h]; this
0x18000b12a  lea     r8, aOnecoreuapDsEx_1; "onecoreuap\\ds\\ext\\common\\ntservice"...
0x18000b131  mov     edx, 96h; void *
0x18000b136  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000b13b  mov     ebx, eax
0x18000b13d  test    eax, eax
0x18000b13f  jns     short loc_18000B15E
0x18000b141  mov     rcx, [rsp+48h]; this
0x18000b146  mov     r9d, eax; char *
0x18000b149  lea     r8, aOnecoreuapDsEx_1; "onecoreuap\\ds\\ext\\common\\ntservice"...
0x18000b150  mov     edx, 26h ; '&'; void *
0x18000b155  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000b15a  mov     eax, ebx
0x18000b15c  jmp     short loc_18000B166
0x18000b15e  xor     eax, eax
0x18000b160  jmp     short loc_18000B166
0x18000b162  mov     eax, dword ptr [rsp+48h+arg_0]
0x18000b166  add     rsp, 40h
0x18000b16a  pop     rbx
0x18000b16b  retn
```
