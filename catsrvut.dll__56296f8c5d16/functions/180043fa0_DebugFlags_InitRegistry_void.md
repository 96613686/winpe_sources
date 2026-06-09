# DebugFlags::InitRegistry(void)

- ea: `0x180043fa0`
- end: `0x180044112`
- name: `?InitRegistry@DebugFlags@@CAXXZ`
- size: `370`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180043a58`

## callees

- `0x180043e08`
- `0x180043ef0`
- `0x180043fa0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180043fd1`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180043ffb`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180043fd1`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180043ffb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800440fc`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800440fc`

## string_xrefs

- `0x180043fc3`: `Software\Microsoft\COM3\Debug`
- `0x180043fed`: `Software\Microsoft\COM3\Debug`
- `0x180044042`: `DebugBreakOnInitComPlus`
- `0x180044059`: `DebugBreakOnLoadComsvcs`
- `0x1800440cc`: `TraceSecurity`
- `0x1800440e3`: `TraceSecurityPM`

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
0x180043fa0  push    rbp
0x180043fa2  mov     rbp, rsp
0x180043fa5  sub     rsp, 30h
0x180043fa9  lea     rax, [rbp+hKey]
0x180043fad  mov     [rbp+hKey], 0
0x180043fb5  mov     r9d, 2001Bh; samDesired
0x180043fbb  mov     [rsp+30h+phkResult], rax; phkResult
0x180043fc0  xor     r8d, r8d; ulOptions
0x180043fc3  lea     rdx, aSoftwareMicros_3; "Software\\Microsoft\\COM3\\Debug"
0x180043fca  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180043fd1  call    cs:__imp_RegOpenKeyExW
0x180043fd7  test    eax, eax
0x180043fd9  jz      short loc_180044009
0x180043fdb  lea     rax, [rbp+hKey]
0x180043fdf  mov     r9d, 20019h; samDesired
0x180043fe5  xor     r8d, r8d; ulOptions
0x180043fe8  mov     [rsp+30h+phkResult], rax; phkResult
0x180043fed  lea     rdx, aSoftwareMicros_3; "Software\\Microsoft\\COM3\\Debug"
0x180043ff4  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180043ffb  call    cs:__imp_RegOpenKeyExW
0x180044001  test    eax, eax
0x180044003  jnz     loc_180044102
0x180044009  mov     rcx, [rbp+hKey]; hKey
0x18004400d  lea     r8, ?sm_fAutoAddTraceToContext@DebugFlags@@0HA; int *
0x180044014  lea     rdx, aAutoaddtraceto; "AutoAddTraceToContext"
0x18004401b  call    ?InitBoolean@DebugFlags@@CAXPEAUHKEY__@@PEBGPEAH@Z; DebugFlags::InitBoolean(HKEY__ *,ushort const *,int *)
0x180044020  mov     rcx, [rbp+hKey]; hKey
0x180044024  lea     r8, ?sm_fDebugBreakOnFailFast@DebugFlags@@0HA; int *
0x18004402b  lea     rdx, aDebugbreakonfa; "DebugBreakOnFailFast"
0x180044032  call    ?InitBoolean@DebugFlags@@CAXPEAUHKEY__@@PEBGPEAH@Z; DebugFlags::InitBoolean(HKEY__ *,ushort const *,int *)
0x180044037  mov     rcx, [rbp+hKey]; hKey
0x18004403b  lea     r8, ?sm_fDebugBreakOnInitComPlus@DebugFlags@@0HA; int *
0x180044042  lea     rdx, aDebugbreakonin; "DebugBreakOnInitComPlus"
0x180044049  call    ?InitBoolean@DebugFlags@@CAXPEAUHKEY__@@PEBGPEAH@Z; DebugFlags::InitBoolean(HKEY__ *,ushort const *,int *)
0x18004404e  mov     rcx, [rbp+hKey]; hKey
0x180044052  lea     r8, ?sm_fDebugBreakOnLoadComsvcs@DebugFlags@@0HA; int *
0x180044059  lea     rdx, aDebugbreakonlo; "DebugBreakOnLoadComsvcs"
0x180044060  call    ?InitBoolean@DebugFlags@@CAXPEAUHKEY__@@PEBGPEAH@Z; DebugFlags::InitBoolean(HKEY__ *,ushort const *,int *)
0x180044065  mov     rcx, [rbp+hKey]; hKey
0x180044069  lea     r8, ?sm_fTraceActivityModule@DebugFlags@@0HA; int *
0x180044070  lea     rdx, aTraceactivitym; "TraceActivityModule"
0x180044077  call    ?InitBoolean@DebugFlags@@CAXPEAUHKEY__@@PEBGPEAH@Z; DebugFlags::InitBoolean(HKEY__ *,ushort const *,int *)
0x18004407c  mov     rcx, [rbp+hKey]; hKey
0x180044080  lea     r8, ?sm_fTraceContextCreation@DebugFlags@@0HA; int *
0x180044087  lea     rdx, aTracecontextcr; "TraceContextCreation"
0x18004408e  call    ?InitBoolean@DebugFlags@@CAXPEAUHKEY__@@PEBGPEAH@Z; DebugFlags::InitBoolean(HKEY__ *,ushort const *,int *)
0x180044093  mov     rcx, [rbp+hKey]; hKey
0x180044097  lea     r8, ?sm_fTraceInfrastructureCalls@DebugFlags@@0HA; int *
0x18004409e  lea     rdx, aTraceinfrastru; "TraceInfrastructureCalls"
0x1800440a5  call    ?InitBoolean@DebugFlags@@CAXPEAUHKEY__@@PEBGPEAH@Z; DebugFlags::InitBoolean(HKEY__ *,ushort const *,int *)
0x1800440aa  mov     rcx, [rbp+hKey]; hKey
0x1800440ae  lea     r8, ?sm_fTraceSTAPool@DebugFlags@@0HA; int *
0x1800440b5  lea     rdx, aTracestapool; "TraceSTAPool"
0x1800440bc  call    ?InitBoolean@DebugFlags@@CAXPEAUHKEY__@@PEBGPEAH@Z; DebugFlags::InitBoolean(HKEY__ *,ushort const *,int *)
0x1800440c1  mov     rcx, [rbp+hKey]; hKey
0x1800440c5  lea     r8, ?sm_fTraceSecurity@DebugFlags@@0HA; int *
0x1800440cc  lea     rdx, aTracesecurity; "TraceSecurity"
0x1800440d3  call    ?InitBoolean@DebugFlags@@CAXPEAUHKEY__@@PEBGPEAH@Z; DebugFlags::InitBoolean(HKEY__ *,ushort const *,int *)
0x1800440d8  mov     rcx, [rbp+hKey]; hKey
0x1800440dc  lea     r8, ?sm_fTraceSecurityPM@DebugFlags@@0HA; int *
0x1800440e3  lea     rdx, aTracesecurityp; "TraceSecurityPM"
0x1800440ea  call    ?InitBoolean@DebugFlags@@CAXPEAUHKEY__@@PEBGPEAH@Z; DebugFlags::InitBoolean(HKEY__ *,ushort const *,int *)
0x1800440ef  mov     rcx, [rbp+hKey]; hKey
0x1800440f3  call    ?InitDWORD@DebugFlags@@CAXPEAUHKEY__@@PEBGPEAK@Z; DebugFlags::InitDWORD(HKEY__ *,ushort const *,ulong *)
0x1800440f8  mov     rcx, [rbp+hKey]; hKey
0x1800440fc  call    cs:__imp_RegCloseKey
0x180044102  mov     cs:?sm_registryInitialized@DebugFlags@@0HA, 1; int DebugFlags::sm_registryInitialized
0x18004410c  add     rsp, 30h
0x180044110  pop     rbp
0x180044111  retn
```
