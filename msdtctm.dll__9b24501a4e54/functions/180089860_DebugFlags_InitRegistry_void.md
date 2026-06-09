# DebugFlags::InitRegistry(void)

- ea: `0x180089860`
- end: `0x1800899d2`
- name: `?InitRegistry@DebugFlags@@CAXXZ`
- size: `370`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180089378`

## callees

- `0x1800896c8`
- `0x1800897b0`
- `0x180089860`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180089891`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800898bb`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180089891`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800898bb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800899bc`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800899bc`

## string_xrefs

- `0x180089883`: `Software\Microsoft\COM3\Debug`
- `0x1800898ad`: `Software\Microsoft\COM3\Debug`
- `0x180089919`: `DebugBreakOnLoadComsvcs`
- `0x180089902`: `DebugBreakOnInitComPlus`
- `0x1800899a3`: `TraceSecurityPM`
- `0x18008998c`: `TraceSecurity`

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
0x180089860  push    rbp
0x180089862  mov     rbp, rsp
0x180089865  sub     rsp, 30h
0x180089869  lea     rax, [rbp+hKey]
0x18008986d  mov     [rbp+hKey], 0
0x180089875  mov     r9d, 2001Bh; samDesired
0x18008987b  mov     [rsp+30h+phkResult], rax; phkResult
0x180089880  xor     r8d, r8d; ulOptions
0x180089883  lea     rdx, aSoftwareMicros_0; "Software\\Microsoft\\COM3\\Debug"
0x18008988a  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180089891  call    cs:__imp_RegOpenKeyExW
0x180089897  test    eax, eax
0x180089899  jz      short loc_1800898C9
0x18008989b  lea     rax, [rbp+hKey]
0x18008989f  mov     r9d, 20019h; samDesired
0x1800898a5  xor     r8d, r8d; ulOptions
0x1800898a8  mov     [rsp+30h+phkResult], rax; phkResult
0x1800898ad  lea     rdx, aSoftwareMicros_0; "Software\\Microsoft\\COM3\\Debug"
0x1800898b4  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800898bb  call    cs:__imp_RegOpenKeyExW
0x1800898c1  test    eax, eax
0x1800898c3  jnz     loc_1800899C2
0x1800898c9  mov     rcx, [rbp+hKey]; hKey
0x1800898cd  lea     r8, ?sm_fAutoAddTraceToContext@DebugFlags@@0HA; int *
0x1800898d4  lea     rdx, aAutoaddtraceto; "AutoAddTraceToContext"
0x1800898db  call    ?InitBoolean@DebugFlags@@CAXPEAUHKEY__@@PEBGPEAH@Z; DebugFlags::InitBoolean(HKEY__ *,ushort const *,int *)
0x1800898e0  mov     rcx, [rbp+hKey]; hKey
0x1800898e4  lea     r8, ?sm_fDebugBreakOnFailFast@DebugFlags@@0HA; int *
0x1800898eb  lea     rdx, aDebugbreakonfa; "DebugBreakOnFailFast"
0x1800898f2  call    ?InitBoolean@DebugFlags@@CAXPEAUHKEY__@@PEBGPEAH@Z; DebugFlags::InitBoolean(HKEY__ *,ushort const *,int *)
0x1800898f7  mov     rcx, [rbp+hKey]; hKey
0x1800898fb  lea     r8, ?sm_fDebugBreakOnInitComPlus@DebugFlags@@0HA; int *
0x180089902  lea     rdx, aDebugbreakonin; "DebugBreakOnInitComPlus"
0x180089909  call    ?InitBoolean@DebugFlags@@CAXPEAUHKEY__@@PEBGPEAH@Z; DebugFlags::InitBoolean(HKEY__ *,ushort const *,int *)
0x18008990e  mov     rcx, [rbp+hKey]; hKey
0x180089912  lea     r8, ?sm_fDebugBreakOnLoadComsvcs@DebugFlags@@0HA; int *
0x180089919  lea     rdx, aDebugbreakonlo; "DebugBreakOnLoadComsvcs"
0x180089920  call    ?InitBoolean@DebugFlags@@CAXPEAUHKEY__@@PEBGPEAH@Z; DebugFlags::InitBoolean(HKEY__ *,ushort const *,int *)
0x180089925  mov     rcx, [rbp+hKey]; hKey
0x180089929  lea     r8, ?sm_fTraceActivityModule@DebugFlags@@0HA; int *
0x180089930  lea     rdx, aTraceactivitym; "TraceActivityModule"
0x180089937  call    ?InitBoolean@DebugFlags@@CAXPEAUHKEY__@@PEBGPEAH@Z; DebugFlags::InitBoolean(HKEY__ *,ushort const *,int *)
0x18008993c  mov     rcx, [rbp+hKey]; hKey
0x180089940  lea     r8, ?sm_fTraceContextCreation@DebugFlags@@0HA; int *
0x180089947  lea     rdx, aTracecontextcr; "TraceContextCreation"
0x18008994e  call    ?InitBoolean@DebugFlags@@CAXPEAUHKEY__@@PEBGPEAH@Z; DebugFlags::InitBoolean(HKEY__ *,ushort const *,int *)
0x180089953  mov     rcx, [rbp+hKey]; hKey
0x180089957  lea     r8, ?sm_fTraceInfrastructureCalls@DebugFlags@@0HA; int *
0x18008995e  lea     rdx, aTraceinfrastru; "TraceInfrastructureCalls"
0x180089965  call    ?InitBoolean@DebugFlags@@CAXPEAUHKEY__@@PEBGPEAH@Z; DebugFlags::InitBoolean(HKEY__ *,ushort const *,int *)
0x18008996a  mov     rcx, [rbp+hKey]; hKey
0x18008996e  lea     r8, ?sm_fTraceSTAPool@DebugFlags@@0HA; int *
0x180089975  lea     rdx, aTracestapool; "TraceSTAPool"
0x18008997c  call    ?InitBoolean@DebugFlags@@CAXPEAUHKEY__@@PEBGPEAH@Z; DebugFlags::InitBoolean(HKEY__ *,ushort const *,int *)
0x180089981  mov     rcx, [rbp+hKey]; hKey
0x180089985  lea     r8, ?sm_fTraceSecurity@DebugFlags@@0HA; int *
0x18008998c  lea     rdx, aTracesecurity; "TraceSecurity"
0x180089993  call    ?InitBoolean@DebugFlags@@CAXPEAUHKEY__@@PEBGPEAH@Z; DebugFlags::InitBoolean(HKEY__ *,ushort const *,int *)
0x180089998  mov     rcx, [rbp+hKey]; hKey
0x18008999c  lea     r8, ?sm_fTraceSecurityPM@DebugFlags@@0HA; int *
0x1800899a3  lea     rdx, aTracesecurityp; "TraceSecurityPM"
0x1800899aa  call    ?InitBoolean@DebugFlags@@CAXPEAUHKEY__@@PEBGPEAH@Z; DebugFlags::InitBoolean(HKEY__ *,ushort const *,int *)
0x1800899af  mov     rcx, [rbp+hKey]; hKey
0x1800899b3  call    ?InitDWORD@DebugFlags@@CAXPEAUHKEY__@@PEBGPEAK@Z; DebugFlags::InitDWORD(HKEY__ *,ushort const *,ulong *)
0x1800899b8  mov     rcx, [rbp+hKey]; hKey
0x1800899bc  call    cs:__imp_RegCloseKey
0x1800899c2  mov     cs:?sm_registryInitialized@DebugFlags@@0HA, 1; int DebugFlags::sm_registryInitialized
0x1800899cc  add     rsp, 30h
0x1800899d0  pop     rbp
0x1800899d1  retn
```
