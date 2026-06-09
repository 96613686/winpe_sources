# HvSysConfigTimer::UpdateSysConfigTimer(void)

- ea: `0x180008908`
- end: `0x180008a21`
- name: `?UpdateSysConfigTimer@HvSysConfigTimer@@AEAAXXZ`
- size: `281`
- prototype: `void __fastcall(HvSysConfigTimer *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180008370`
- `0x1800084f4`

## callees

- `0x180008250`
- `0x180008908`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800089a2`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800089a2`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180008a07`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180008a07`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800089de`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800089ee`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800089de`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800089ee`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800089fd`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800089fd`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180008947`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180008947`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000897b`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000897b`

## string_xrefs

- `0x18000895e`: `VmConfigLogIntervalSeconds`

## pseudocode

```c
void __fastcall HvSysConfigTimer::UpdateSysConfigTimer(HvSysConfigTimer *this)
{
  struct _TP_TIMER *v2; // rcx
  unsigned int Data; // [rsp+40h] [rbp+10h] BYREF
  __int64 cbData; // [rsp+48h] [rbp+18h] BYREF
  HKEY hKey; // [rsp+50h] [rbp+20h] BYREF

  Data = 86400;
  hKey = 0;
  if ( !RegOpenKeyExW(
          HKEY_LOCAL_MACHINE,
          L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\Virtualization\\Worker",
          0,
          0x20019u,
          &hKey) )
  {
    LODWORD(cbData) = 4;
    if ( !RegQueryValueExW(hKey, L"VmConfigLogIntervalSeconds", 0, 0, (LPBYTE)&Data, (LPDWORD)&cbData)
      && Data - 300 > 0x278BD4 )
    {
      Data = 86400;
    }
  }
  if ( !WaitForSingleObject(*((HANDLE *)this + 2), 0xFFFFFFFF) )
  {
    v2 = (struct _TP_TIMER *)*((_QWORD *)this + 3);
    if ( Data )
    {
      cbData = -10000000LL * Data;
      SetThreadpoolTimer(v2, (PFILETIME)&cbData, 1000 * Data, 0xEA60u);
    }
    else
    {
      SetThreadpoolTimer(v2, 0, 0, 0);
      WaitForThreadpoolTimerCallbacks(*((PTP_TIMER *)this + 3), 1);
    }
    ReleaseMutex(*((HANDLE *)this + 2));
  }
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
}

```

## disassembly

```asm
0x180008908  mov     [rsp-8+arg_18], rbx
0x18000890d  push    rbp
0x18000890e  mov     rbp, rsp
0x180008911  sub     rsp, 30h
0x180008915  mov     rbx, rcx
0x180008918  mov     [rbp+Data], 15180h
0x18000891f  lea     rax, [rbp+hKey]
0x180008923  mov     [rbp+hKey], 0
0x18000892b  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180008932  mov     [rsp+30h+phkResult], rax; phkResult
0x180008937  mov     r9d, 20019h; samDesired
0x18000893d  lea     rdx, SubKey; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x180008944  xor     r8d, r8d; ulOptions
0x180008947  call    cs:__imp_RegOpenKeyExW
0x18000894d  test    eax, eax
0x18000894f  jnz     short loc_18000899B
0x180008951  mov     rcx, [rbp+hKey]; hKey
0x180008955  lea     rax, [rbp+cbData]
0x180008959  mov     [rsp+30h+lpcbData], rax; lpcbData
0x18000895e  lea     rdx, ValueName; "VmConfigLogIntervalSeconds"
0x180008965  lea     rax, [rbp+Data]
0x180008969  mov     dword ptr [rbp+cbData], 4
0x180008970  xor     r9d, r9d; lpType
0x180008973  mov     [rsp+30h+phkResult], rax; lpData
0x180008978  xor     r8d, r8d; lpReserved
0x18000897b  call    cs:__imp_RegQueryValueExW
0x180008981  test    eax, eax
0x180008983  jnz     short loc_18000899B
0x180008985  mov     eax, [rbp+Data]
0x180008988  add     eax, 0FFFFFED4h
0x18000898d  cmp     eax, 278BD4h
0x180008992  jbe     short loc_18000899B
0x180008994  mov     [rbp+Data], 15180h
0x18000899b  mov     rcx, [rbx+10h]; hHandle
0x18000899f  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1800089a2  call    cs:__imp_WaitForSingleObject
0x1800089a8  test    eax, eax
0x1800089aa  jnz     short loc_180008A0D
0x1800089ac  mov     r8d, [rbp+Data]
0x1800089b0  mov     rcx, [rbx+18h]; pti
0x1800089b4  test    r8d, r8d
0x1800089b7  jz      short loc_1800089E6
0x1800089b9  imul    rax, r8, 0FFFFFFFFFF676980h
0x1800089c0  imul    r8d, 3E8h; msPeriod
0x1800089c7  mov     r9d, 0EA60h; msWindowLength
0x1800089cd  mov     rdx, rax
0x1800089d0  mov     dword ptr [rbp+cbData], eax
0x1800089d3  shr     rdx, 20h
0x1800089d7  mov     dword ptr [rbp+cbData+4], edx
0x1800089da  lea     rdx, [rbp+cbData]; pftDueTime
0x1800089de  call    cs:__imp_SetThreadpoolTimer
0x1800089e4  jmp     short loc_180008A03
0x1800089e6  xor     r9d, r9d; msWindowLength
0x1800089e9  xor     r8d, r8d; msPeriod
0x1800089ec  xor     edx, edx; pftDueTime
0x1800089ee  call    cs:__imp_SetThreadpoolTimer
0x1800089f4  mov     rcx, [rbx+18h]; pti
0x1800089f8  mov     edx, 1; fCancelPendingCallbacks
0x1800089fd  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180008a03  mov     rcx, [rbx+10h]; hMutex
0x180008a07  call    cs:__imp_ReleaseMutex
0x180008a0d  lea     rcx, [rbp+hKey]
0x180008a11  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180008a16  mov     rbx, [rsp+30h+arg_18]
0x180008a1b  add     rsp, 30h
0x180008a1f  pop     rbp
0x180008a20  retn
```
