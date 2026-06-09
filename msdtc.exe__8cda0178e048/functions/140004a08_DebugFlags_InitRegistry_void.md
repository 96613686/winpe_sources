# DebugFlags::InitRegistry(void)

- ea: `0x140004a08`
- end: `0x140004b7a`
- name: `?InitRegistry@DebugFlags@@CAXXZ`
- size: `370`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140003fec`

## callees

- `0x140004870`
- `0x140004958`
- `0x140004a08`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140004b64`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140004b64`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140004a39`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140004a63`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140004a39`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140004a63`

## string_xrefs

- `0x140004a2b`: `Software\Microsoft\COM3\Debug`
- `0x140004a55`: `Software\Microsoft\COM3\Debug`
- `0x140004aaa`: `DebugBreakOnInitComPlus`
- `0x140004ac1`: `DebugBreakOnLoadComsvcs`
- `0x140004b34`: `TraceSecurity`
- `0x140004b4b`: `TraceSecurityPM`

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
0x140004a08  push    rbp
0x140004a0a  mov     rbp, rsp
0x140004a0d  sub     rsp, 30h
0x140004a11  lea     rax, [rbp+hKey]
0x140004a15  mov     [rbp+hKey], 0
0x140004a1d  mov     r9d, 2001Bh; samDesired
0x140004a23  mov     [rsp+30h+phkResult], rax; phkResult
0x140004a28  xor     r8d, r8d; ulOptions
0x140004a2b  lea     rdx, aSoftwareMicros; "Software\\Microsoft\\COM3\\Debug"
0x140004a32  mov     rcx, 0FFFFFFFF80000002h; hKey
0x140004a39  call    cs:__imp_RegOpenKeyExW
0x140004a3f  test    eax, eax
0x140004a41  jz      short loc_140004A71
0x140004a43  lea     rax, [rbp+hKey]
0x140004a47  mov     r9d, 20019h; samDesired
0x140004a4d  xor     r8d, r8d; ulOptions
0x140004a50  mov     [rsp+30h+phkResult], rax; phkResult
0x140004a55  lea     rdx, aSoftwareMicros; "Software\\Microsoft\\COM3\\Debug"
0x140004a5c  mov     rcx, 0FFFFFFFF80000002h; hKey
0x140004a63  call    cs:__imp_RegOpenKeyExW
0x140004a69  test    eax, eax
0x140004a6b  jnz     loc_140004B6A
0x140004a71  mov     rcx, [rbp+hKey]; hKey
0x140004a75  lea     r8, ?sm_fAutoAddTraceToContext@DebugFlags@@0HA; int *
0x140004a7c  lea     rdx, aAutoaddtraceto; "AutoAddTraceToContext"
0x140004a83  call    ?InitBoolean@DebugFlags@@CAXPEAUHKEY__@@PEBGPEAH@Z; DebugFlags::InitBoolean(HKEY__ *,ushort const *,int *)
0x140004a88  mov     rcx, [rbp+hKey]; hKey
0x140004a8c  lea     r8, ?sm_fDebugBreakOnFailFast@DebugFlags@@0HA; int *
0x140004a93  lea     rdx, aDebugbreakonfa; "DebugBreakOnFailFast"
0x140004a9a  call    ?InitBoolean@DebugFlags@@CAXPEAUHKEY__@@PEBGPEAH@Z; DebugFlags::InitBoolean(HKEY__ *,ushort const *,int *)
0x140004a9f  mov     rcx, [rbp+hKey]; hKey
0x140004aa3  lea     r8, ?sm_fDebugBreakOnInitComPlus@DebugFlags@@0HA; int *
0x140004aaa  lea     rdx, aDebugbreakonin; "DebugBreakOnInitComPlus"
0x140004ab1  call    ?InitBoolean@DebugFlags@@CAXPEAUHKEY__@@PEBGPEAH@Z; DebugFlags::InitBoolean(HKEY__ *,ushort const *,int *)
0x140004ab6  mov     rcx, [rbp+hKey]; hKey
0x140004aba  lea     r8, ?sm_fDebugBreakOnLoadComsvcs@DebugFlags@@0HA; int *
0x140004ac1  lea     rdx, aDebugbreakonlo; "DebugBreakOnLoadComsvcs"
0x140004ac8  call    ?InitBoolean@DebugFlags@@CAXPEAUHKEY__@@PEBGPEAH@Z; DebugFlags::InitBoolean(HKEY__ *,ushort const *,int *)
0x140004acd  mov     rcx, [rbp+hKey]; hKey
0x140004ad1  lea     r8, ?sm_fTraceActivityModule@DebugFlags@@0HA; int *
0x140004ad8  lea     rdx, aTraceactivitym; "TraceActivityModule"
0x140004adf  call    ?InitBoolean@DebugFlags@@CAXPEAUHKEY__@@PEBGPEAH@Z; DebugFlags::InitBoolean(HKEY__ *,ushort const *,int *)
0x140004ae4  mov     rcx, [rbp+hKey]; hKey
0x140004ae8  lea     r8, ?sm_fTraceContextCreation@DebugFlags@@0HA; int *
0x140004aef  lea     rdx, aTracecontextcr; "TraceContextCreation"
0x140004af6  call    ?InitBoolean@DebugFlags@@CAXPEAUHKEY__@@PEBGPEAH@Z; DebugFlags::InitBoolean(HKEY__ *,ushort const *,int *)
0x140004afb  mov     rcx, [rbp+hKey]; hKey
0x140004aff  lea     r8, ?sm_fTraceInfrastructureCalls@DebugFlags@@0HA; int *
0x140004b06  lea     rdx, aTraceinfrastru; "TraceInfrastructureCalls"
0x140004b0d  call    ?InitBoolean@DebugFlags@@CAXPEAUHKEY__@@PEBGPEAH@Z; DebugFlags::InitBoolean(HKEY__ *,ushort const *,int *)
0x140004b12  mov     rcx, [rbp+hKey]; hKey
0x140004b16  lea     r8, ?sm_fTraceSTAPool@DebugFlags@@0HA; int *
0x140004b1d  lea     rdx, aTracestapool; "TraceSTAPool"
0x140004b24  call    ?InitBoolean@DebugFlags@@CAXPEAUHKEY__@@PEBGPEAH@Z; DebugFlags::InitBoolean(HKEY__ *,ushort const *,int *)
0x140004b29  mov     rcx, [rbp+hKey]; hKey
0x140004b2d  lea     r8, ?sm_fTraceSecurity@DebugFlags@@0HA; int *
0x140004b34  lea     rdx, aTracesecurity; "TraceSecurity"
0x140004b3b  call    ?InitBoolean@DebugFlags@@CAXPEAUHKEY__@@PEBGPEAH@Z; DebugFlags::InitBoolean(HKEY__ *,ushort const *,int *)
0x140004b40  mov     rcx, [rbp+hKey]; hKey
0x140004b44  lea     r8, ?sm_fTraceSecurityPM@DebugFlags@@0HA; int *
0x140004b4b  lea     rdx, aTracesecurityp; "TraceSecurityPM"
0x140004b52  call    ?InitBoolean@DebugFlags@@CAXPEAUHKEY__@@PEBGPEAH@Z; DebugFlags::InitBoolean(HKEY__ *,ushort const *,int *)
0x140004b57  mov     rcx, [rbp+hKey]; hKey
0x140004b5b  call    ?InitDWORD@DebugFlags@@CAXPEAUHKEY__@@PEBGPEAK@Z; DebugFlags::InitDWORD(HKEY__ *,ushort const *,ulong *)
0x140004b60  mov     rcx, [rbp+hKey]; hKey
0x140004b64  call    cs:__imp_RegCloseKey
0x140004b6a  mov     cs:?sm_registryInitialized@DebugFlags@@0HA, 1; int DebugFlags::sm_registryInitialized
0x140004b74  add     rsp, 30h
0x140004b78  pop     rbp
0x140004b79  retn
```
