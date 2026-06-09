# DebugFlags::InitRegistry(void)

- ea: `0x180032f34`
- end: `0x1800330a6`
- name: `?InitRegistry@DebugFlags@@CAXXZ`
- size: `370`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800328a0`

## callees

- `0x180032d9c`
- `0x180032e84`
- `0x180032f34`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180032f65`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180032f8f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180032f65`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180032f8f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180033090`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180033090`

## string_xrefs

- `0x180032f57`: `Software\Microsoft\COM3\Debug`
- `0x180032f81`: `Software\Microsoft\COM3\Debug`
- `0x180032fd6`: `DebugBreakOnInitComPlus`
- `0x180032fed`: `DebugBreakOnLoadComsvcs`
- `0x180033060`: `TraceSecurity`
- `0x180033077`: `TraceSecurityPM`

## pseudocode

```c
void DebugFlags::InitRegistry(void)
{
  const unsigned __int16 *v0; // rdx
  unsigned int *v1; // r8
  HKEY hKey; // [rsp+40h] [rbp+10h] BYREF

  hKey = 0;
  if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\COM3\\Debug", 0, 0x2001Bu, &hKey)
    || !RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\COM3\\Debug", 0, 0x20019u, &hKey) )
  {
    DebugFlags::InitBoolean(hKey, L"AutoAddTraceToContext", &DebugFlags::sm_fAutoAddTraceToContext);
    DebugFlags::InitBoolean(hKey, L"DebugBreakOnFailFast", &DebugFlags::sm_fDebugBreakOnFailFast);
    DebugFlags::InitBoolean(hKey, L"DebugBreakOnInitComPlus", &DebugFlags::sm_fDebugBreakOnInitComPlus);
    DebugFlags::InitBoolean(hKey, L"DebugBreakOnLoadComsvcs", &DebugFlags::sm_fDebugBreakOnLoadComsvcs);
    DebugFlags::InitBoolean(hKey, L"TraceActivityModule", &DebugFlags::sm_fTraceActivityModule);
    DebugFlags::InitBoolean(hKey, L"TraceContextCreation", &DebugFlags::sm_fTraceContextCreation);
    DebugFlags::InitBoolean(hKey, L"TraceInfrastructureCalls", &DebugFlags::sm_fTraceInfrastructureCalls);
    DebugFlags::InitBoolean(hKey, L"TraceSTAPool", &DebugFlags::sm_fTraceSTAPool);
    DebugFlags::InitBoolean(hKey, L"TraceSecurity", &DebugFlags::sm_fTraceSecurity);
    DebugFlags::InitBoolean(hKey, L"TraceSecurityPM", &DebugFlags::sm_fTraceSecurityPM);
    DebugFlags::InitDWORD(hKey, v0, v1);
    RegCloseKey(hKey);
  }
  DebugFlags::sm_registryInitialized = 1;
}

```

## disassembly

```asm
0x180032f34  push    rbp
0x180032f36  mov     rbp, rsp
0x180032f39  sub     rsp, 30h
0x180032f3d  lea     rax, [rbp+hKey]
0x180032f41  mov     [rbp+hKey], 0
0x180032f49  mov     r9d, 2001Bh; samDesired
0x180032f4f  mov     [rsp+30h+phkResult], rax; phkResult
0x180032f54  xor     r8d, r8d; ulOptions
0x180032f57  lea     rdx, aSoftwareMicros_0; "Software\\Microsoft\\COM3\\Debug"
0x180032f5e  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180032f65  call    cs:__imp_RegOpenKeyExW
0x180032f6b  test    eax, eax
0x180032f6d  jz      short loc_180032F9D
0x180032f6f  lea     rax, [rbp+hKey]
0x180032f73  mov     r9d, 20019h; samDesired
0x180032f79  xor     r8d, r8d; ulOptions
0x180032f7c  mov     [rsp+30h+phkResult], rax; phkResult
0x180032f81  lea     rdx, aSoftwareMicros_0; "Software\\Microsoft\\COM3\\Debug"
0x180032f88  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180032f8f  call    cs:__imp_RegOpenKeyExW
0x180032f95  test    eax, eax
0x180032f97  jnz     loc_180033096
0x180032f9d  mov     rcx, [rbp+hKey]; hKey
0x180032fa1  lea     r8, ?sm_fAutoAddTraceToContext@DebugFlags@@0HA; int *
0x180032fa8  lea     rdx, aAutoaddtraceto; "AutoAddTraceToContext"
0x180032faf  call    ?InitBoolean@DebugFlags@@CAXPEAUHKEY__@@PEBGPEAH@Z; DebugFlags::InitBoolean(HKEY__ *,ushort const *,int *)
0x180032fb4  mov     rcx, [rbp+hKey]; hKey
0x180032fb8  lea     r8, ?sm_fDebugBreakOnFailFast@DebugFlags@@0HA; int *
0x180032fbf  lea     rdx, aDebugbreakonfa; "DebugBreakOnFailFast"
0x180032fc6  call    ?InitBoolean@DebugFlags@@CAXPEAUHKEY__@@PEBGPEAH@Z; DebugFlags::InitBoolean(HKEY__ *,ushort const *,int *)
0x180032fcb  mov     rcx, [rbp+hKey]; hKey
0x180032fcf  lea     r8, ?sm_fDebugBreakOnInitComPlus@DebugFlags@@0HA; int *
0x180032fd6  lea     rdx, aDebugbreakonin; "DebugBreakOnInitComPlus"
0x180032fdd  call    ?InitBoolean@DebugFlags@@CAXPEAUHKEY__@@PEBGPEAH@Z; DebugFlags::InitBoolean(HKEY__ *,ushort const *,int *)
0x180032fe2  mov     rcx, [rbp+hKey]; hKey
0x180032fe6  lea     r8, ?sm_fDebugBreakOnLoadComsvcs@DebugFlags@@0HA; int *
0x180032fed  lea     rdx, aDebugbreakonlo; "DebugBreakOnLoadComsvcs"
0x180032ff4  call    ?InitBoolean@DebugFlags@@CAXPEAUHKEY__@@PEBGPEAH@Z; DebugFlags::InitBoolean(HKEY__ *,ushort const *,int *)
0x180032ff9  mov     rcx, [rbp+hKey]; hKey
0x180032ffd  lea     r8, ?sm_fTraceActivityModule@DebugFlags@@0HA; int *
0x180033004  lea     rdx, aTraceactivitym; "TraceActivityModule"
0x18003300b  call    ?InitBoolean@DebugFlags@@CAXPEAUHKEY__@@PEBGPEAH@Z; DebugFlags::InitBoolean(HKEY__ *,ushort const *,int *)
0x180033010  mov     rcx, [rbp+hKey]; hKey
0x180033014  lea     r8, ?sm_fTraceContextCreation@DebugFlags@@0HA; int *
0x18003301b  lea     rdx, aTracecontextcr; "TraceContextCreation"
0x180033022  call    ?InitBoolean@DebugFlags@@CAXPEAUHKEY__@@PEBGPEAH@Z; DebugFlags::InitBoolean(HKEY__ *,ushort const *,int *)
0x180033027  mov     rcx, [rbp+hKey]; hKey
0x18003302b  lea     r8, ?sm_fTraceInfrastructureCalls@DebugFlags@@0HA; int *
0x180033032  lea     rdx, aTraceinfrastru; "TraceInfrastructureCalls"
0x180033039  call    ?InitBoolean@DebugFlags@@CAXPEAUHKEY__@@PEBGPEAH@Z; DebugFlags::InitBoolean(HKEY__ *,ushort const *,int *)
0x18003303e  mov     rcx, [rbp+hKey]; hKey
0x180033042  lea     r8, ?sm_fTraceSTAPool@DebugFlags@@0HA; int *
0x180033049  lea     rdx, aTracestapool; "TraceSTAPool"
0x180033050  call    ?InitBoolean@DebugFlags@@CAXPEAUHKEY__@@PEBGPEAH@Z; DebugFlags::InitBoolean(HKEY__ *,ushort const *,int *)
0x180033055  mov     rcx, [rbp+hKey]; hKey
0x180033059  lea     r8, ?sm_fTraceSecurity@DebugFlags@@0HA; int *
0x180033060  lea     rdx, aTracesecurity; "TraceSecurity"
0x180033067  call    ?InitBoolean@DebugFlags@@CAXPEAUHKEY__@@PEBGPEAH@Z; DebugFlags::InitBoolean(HKEY__ *,ushort const *,int *)
0x18003306c  mov     rcx, [rbp+hKey]; hKey
0x180033070  lea     r8, ?sm_fTraceSecurityPM@DebugFlags@@0HA; int *
0x180033077  lea     rdx, aTracesecurityp; "TraceSecurityPM"
0x18003307e  call    ?InitBoolean@DebugFlags@@CAXPEAUHKEY__@@PEBGPEAH@Z; DebugFlags::InitBoolean(HKEY__ *,ushort const *,int *)
0x180033083  mov     rcx, [rbp+hKey]; hKey
0x180033087  call    ?InitDWORD@DebugFlags@@CAXPEAUHKEY__@@PEBGPEAK@Z; DebugFlags::InitDWORD(HKEY__ *,ushort const *,ulong *)
0x18003308c  mov     rcx, [rbp+hKey]; hKey
0x180033090  call    cs:__imp_RegCloseKey
0x180033096  mov     cs:?sm_registryInitialized@DebugFlags@@0HA, 1; int DebugFlags::sm_registryInitialized
0x1800330a0  add     rsp, 30h
0x1800330a4  pop     rbp
0x1800330a5  retn
```
