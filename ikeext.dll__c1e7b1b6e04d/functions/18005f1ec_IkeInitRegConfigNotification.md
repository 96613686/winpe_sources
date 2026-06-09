# IkeInitRegConfigNotification

- ea: `0x18005f1ec`
- end: `0x18005f324`
- name: `IkeInitRegConfigNotification`
- size: `312`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, service_task`

## callers

- `0x180055d2c`

## callees

- `0x1800061ec`
- `0x180008388`
- `0x18005f1ec`
- `0x18005fd10`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005f266`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005f2e3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005f266`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005f2e3`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18005f246`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18005f246`
- `api-ms-win-core-registry-l1-1-0!RegNotifyChangeKeyValue` at `0x18005f28d`
- `api-ms-win-core-registry-l1-1-0!RegNotifyChangeKeyValue` at `0x18005f28d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18005f21f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18005f21f`
- `api-ms-win-core-threadpool-private-l1-1-0!RegisterWaitForSingleObjectEx` at `0x18005f2c6`
- `api-ms-win-core-threadpool-private-l1-1-0!RegisterWaitForSingleObjectEx` at `0x18005f2c6`

## string_xrefs

- `0x18005f26c`: `CreateEventW`
- `0x18005f229`: `RegOpenKeyExW`
- `0x18005f1fd`: `SYSTEM\CurrentControlSet\Services\IKEEXT`
- `0x18005f30b`: `IkeInitRegConfigNotification`

## pseudocode

```c
__int64 IkeInitRegConfigNotification()
{
  DWORD LastError; // eax
  __int64 v1; // rcx
  const char *v2; // rdx
  LPCRITICAL_SECTION v3; // rbx
  PRTL_CRITICAL_SECTION_DEBUG DebugInfo; // r9
  LPCRITICAL_SECTION v5; // rbx
  __int64 v6; // rsi

  LastError = RegOpenKeyExW(
                HKEY_LOCAL_MACHINE,
                L"SYSTEM\\CurrentControlSet\\Services\\IKEEXT",
                0,
                0x11u,
                (PHKEY)&gIkeExtGlobals[73].SpinCount);
  if ( LastError )
  {
    v2 = "RegOpenKeyExW";
  }
  else
  {
    v3 = gIkeExtGlobals;
    v3[74].DebugInfo = (PRTL_CRITICAL_SECTION_DEBUG)CreateEventW(0, 0, 0, 0);
    DebugInfo = gIkeExtGlobals[74].DebugInfo;
    if ( DebugInfo )
    {
      LastError = RegNotifyChangeKeyValue((HKEY)gIkeExtGlobals[73].SpinCount, 1, 5u, DebugInfo, 1);
      if ( LastError )
      {
        v2 = "RegNotifyChangeKeyValue";
      }
      else
      {
        v5 = gIkeExtGlobals;
        v6 = 0;
        *(_QWORD *)&v5[74].LockCount = RegisterWaitForSingleObjectEx(
                                         gIkeExtGlobals[74].DebugInfo,
                                         IkeRegConfigChangeNotifyCallback,
                                         0,
                                         0xFFFFFFFFLL,
                                         128);
        if ( *(_QWORD *)&gIkeExtGlobals[74].LockCount )
          return IkeReturnError(v6, "IkeInitRegConfigNotification");
        LastError = GetLastError();
        v2 = "RegisterWaitForSingleObjectEx";
      }
    }
    else
    {
      LastError = GetLastError();
      v2 = "CreateEventW";
    }
  }
  v6 = WfpReportSysErrorAsWinError(v1, v2, LastError, 1);
  if ( v6 )
    IkeShutdownRegConfigNotification();
  return IkeReturnError(v6, "IkeInitRegConfigNotification");
}

```

## disassembly

```asm
0x18005f1ec  mov     [rsp+arg_0], rbx
0x18005f1f1  push    rsi
0x18005f1f2  sub     rsp, 30h
0x18005f1f6  mov     rax, cs:gIkeExtGlobals
0x18005f1fd  lea     rdx, aSystemCurrentc_0; "SYSTEM\\CurrentControlSet\\Services\\IK"...
0x18005f204  add     rax, 0B88h
0x18005f20a  mov     r9d, 11h; samDesired
0x18005f210  xor     r8d, r8d; ulOptions
0x18005f213  mov     [rsp+38h+phkResult], rax; phkResult
0x18005f218  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18005f21f  call    cs:__imp_RegOpenKeyExW
0x18005f225  test    eax, eax
0x18005f227  jz      short loc_18005F235
0x18005f229  lea     rdx, aRegopenkeyexw; "RegOpenKeyExW"
0x18005f230  jmp     loc_18005F2F0
0x18005f235  mov     rbx, cs:gIkeExtGlobals
0x18005f23c  xor     r9d, r9d; lpName
0x18005f23f  xor     r8d, r8d; bInitialState
0x18005f242  xor     edx, edx; bManualReset
0x18005f244  xor     ecx, ecx; lpEventAttributes
0x18005f246  call    cs:__imp_CreateEventW
0x18005f24c  mov     [rbx+0B90h], rax
0x18005f253  mov     rcx, cs:gIkeExtGlobals
0x18005f25a  mov     r9, [rcx+0B90h]; hEvent
0x18005f261  test    r9, r9
0x18005f264  jnz     short loc_18005F275
0x18005f266  call    cs:__imp_GetLastError
0x18005f26c  lea     rdx, aCreateeventw; "CreateEventW"
0x18005f273  jmp     short loc_18005F2F0
0x18005f275  mov     rcx, [rcx+0B88h]; hKey
0x18005f27c  mov     edx, 1; bWatchSubtree
0x18005f281  mov     dword ptr [rsp+38h+phkResult], 1; fAsynchronous
0x18005f289  lea     r8d, [rdx+4]; dwNotifyFilter
0x18005f28d  call    cs:__imp_RegNotifyChangeKeyValue
0x18005f293  test    eax, eax
0x18005f295  jz      short loc_18005F2A0
0x18005f297  lea     rdx, aRegnotifychang_0; "RegNotifyChangeKeyValue"
0x18005f29e  jmp     short loc_18005F2F0
0x18005f2a0  mov     rbx, cs:gIkeExtGlobals
0x18005f2a7  lea     rdx, IkeRegConfigChangeNotifyCallback
0x18005f2ae  or      r9d, 0FFFFFFFFh
0x18005f2b2  mov     dword ptr [rsp+38h+phkResult], 80h
0x18005f2ba  xor     r8d, r8d
0x18005f2bd  xor     esi, esi
0x18005f2bf  mov     rcx, [rbx+0B90h]
0x18005f2c6  call    cs:__imp_RegisterWaitForSingleObjectEx
0x18005f2cc  mov     [rbx+0B98h], rax
0x18005f2d3  mov     rax, cs:gIkeExtGlobals
0x18005f2da  cmp     [rax+0B98h], rsi
0x18005f2e1  jnz     short loc_18005F30B
0x18005f2e3  call    cs:__imp_GetLastError
0x18005f2e9  lea     rdx, aRegisterwaitfo; "RegisterWaitForSingleObjectEx"
0x18005f2f0  mov     r9d, 1
0x18005f2f6  mov     r8d, eax
0x18005f2f9  call    WfpReportSysErrorAsWinError
0x18005f2fe  mov     rsi, rax
0x18005f301  test    rax, rax
0x18005f304  jz      short loc_18005F30B
0x18005f306  call    IkeShutdownRegConfigNotification
0x18005f30b  lea     rdx, aIkeinitregconf; "IkeInitRegConfigNotification"
0x18005f312  mov     rcx, rsi
0x18005f315  mov     rbx, [rsp+38h+arg_0]
0x18005f31a  add     rsp, 30h
0x18005f31e  pop     rsi
0x18005f31f  jmp     IkeReturnError
```
