# DebugFlags::InitRegistry(void)

- ea: `0x18007e30c`
- end: `0x18007e47e`
- name: `?InitRegistry@DebugFlags@@CAXXZ`
- size: `370`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18007de24`

## callees

- `0x18007e174`
- `0x18007e25c`
- `0x18007e30c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18007e33d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18007e367`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18007e33d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18007e367`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18007e468`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18007e468`

## string_xrefs

- `0x18007e32f`: `Software\Microsoft\COM3\Debug`
- `0x18007e359`: `Software\Microsoft\COM3\Debug`
- `0x18007e3ae`: `DebugBreakOnInitComPlus`
- `0x18007e3c5`: `DebugBreakOnLoadComsvcs`
- `0x18007e438`: `TraceSecurity`
- `0x18007e44f`: `TraceSecurityPM`

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
0x18007e30c  push    rbp
0x18007e30e  mov     rbp, rsp
0x18007e311  sub     rsp, 30h
0x18007e315  lea     rax, [rbp+hKey]
0x18007e319  mov     [rbp+hKey], 0
0x18007e321  mov     r9d, 2001Bh; samDesired
0x18007e327  mov     [rsp+30h+phkResult], rax; phkResult
0x18007e32c  xor     r8d, r8d; ulOptions
0x18007e32f  lea     rdx, aSoftwareMicros; "Software\\Microsoft\\COM3\\Debug"
0x18007e336  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18007e33d  call    cs:__imp_RegOpenKeyExW
0x18007e343  test    eax, eax
0x18007e345  jz      short loc_18007E375
0x18007e347  lea     rax, [rbp+hKey]
0x18007e34b  mov     r9d, 20019h; samDesired
0x18007e351  xor     r8d, r8d; ulOptions
0x18007e354  mov     [rsp+30h+phkResult], rax; phkResult
0x18007e359  lea     rdx, aSoftwareMicros; "Software\\Microsoft\\COM3\\Debug"
0x18007e360  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18007e367  call    cs:__imp_RegOpenKeyExW
0x18007e36d  test    eax, eax
0x18007e36f  jnz     loc_18007E46E
0x18007e375  mov     rcx, [rbp+hKey]; hKey
0x18007e379  lea     r8, ?sm_fAutoAddTraceToContext@DebugFlags@@0HA; int *
0x18007e380  lea     rdx, aAutoaddtraceto; "AutoAddTraceToContext"
0x18007e387  call    ?InitBoolean@DebugFlags@@CAXPEAUHKEY__@@PEBGPEAH@Z; DebugFlags::InitBoolean(HKEY__ *,ushort const *,int *)
0x18007e38c  mov     rcx, [rbp+hKey]; hKey
0x18007e390  lea     r8, ?sm_fDebugBreakOnFailFast@DebugFlags@@0HA; int *
0x18007e397  lea     rdx, aDebugbreakonfa; "DebugBreakOnFailFast"
0x18007e39e  call    ?InitBoolean@DebugFlags@@CAXPEAUHKEY__@@PEBGPEAH@Z; DebugFlags::InitBoolean(HKEY__ *,ushort const *,int *)
0x18007e3a3  mov     rcx, [rbp+hKey]; hKey
0x18007e3a7  lea     r8, ?sm_fDebugBreakOnInitComPlus@DebugFlags@@0HA; int *
0x18007e3ae  lea     rdx, aDebugbreakonin; "DebugBreakOnInitComPlus"
0x18007e3b5  call    ?InitBoolean@DebugFlags@@CAXPEAUHKEY__@@PEBGPEAH@Z; DebugFlags::InitBoolean(HKEY__ *,ushort const *,int *)
0x18007e3ba  mov     rcx, [rbp+hKey]; hKey
0x18007e3be  lea     r8, ?sm_fDebugBreakOnLoadComsvcs@DebugFlags@@0HA; int *
0x18007e3c5  lea     rdx, aDebugbreakonlo; "DebugBreakOnLoadComsvcs"
0x18007e3cc  call    ?InitBoolean@DebugFlags@@CAXPEAUHKEY__@@PEBGPEAH@Z; DebugFlags::InitBoolean(HKEY__ *,ushort const *,int *)
0x18007e3d1  mov     rcx, [rbp+hKey]; hKey
0x18007e3d5  lea     r8, ?sm_fTraceActivityModule@DebugFlags@@0HA; int *
0x18007e3dc  lea     rdx, aTraceactivitym; "TraceActivityModule"
0x18007e3e3  call    ?InitBoolean@DebugFlags@@CAXPEAUHKEY__@@PEBGPEAH@Z; DebugFlags::InitBoolean(HKEY__ *,ushort const *,int *)
0x18007e3e8  mov     rcx, [rbp+hKey]; hKey
0x18007e3ec  lea     r8, ?sm_fTraceContextCreation@DebugFlags@@0HA; int *
0x18007e3f3  lea     rdx, aTracecontextcr; "TraceContextCreation"
0x18007e3fa  call    ?InitBoolean@DebugFlags@@CAXPEAUHKEY__@@PEBGPEAH@Z; DebugFlags::InitBoolean(HKEY__ *,ushort const *,int *)
0x18007e3ff  mov     rcx, [rbp+hKey]; hKey
0x18007e403  lea     r8, ?sm_fTraceInfrastructureCalls@DebugFlags@@0HA; int *
0x18007e40a  lea     rdx, aTraceinfrastru; "TraceInfrastructureCalls"
0x18007e411  call    ?InitBoolean@DebugFlags@@CAXPEAUHKEY__@@PEBGPEAH@Z; DebugFlags::InitBoolean(HKEY__ *,ushort const *,int *)
0x18007e416  mov     rcx, [rbp+hKey]; hKey
0x18007e41a  lea     r8, ?sm_fTraceSTAPool@DebugFlags@@0HA; int *
0x18007e421  lea     rdx, aTracestapool; "TraceSTAPool"
0x18007e428  call    ?InitBoolean@DebugFlags@@CAXPEAUHKEY__@@PEBGPEAH@Z; DebugFlags::InitBoolean(HKEY__ *,ushort const *,int *)
0x18007e42d  mov     rcx, [rbp+hKey]; hKey
0x18007e431  lea     r8, ?sm_fTraceSecurity@DebugFlags@@0HA; int *
0x18007e438  lea     rdx, aTracesecurity; "TraceSecurity"
0x18007e43f  call    ?InitBoolean@DebugFlags@@CAXPEAUHKEY__@@PEBGPEAH@Z; DebugFlags::InitBoolean(HKEY__ *,ushort const *,int *)
0x18007e444  mov     rcx, [rbp+hKey]; hKey
0x18007e448  lea     r8, ?sm_fTraceSecurityPM@DebugFlags@@0HA; int *
0x18007e44f  lea     rdx, aTracesecurityp; "TraceSecurityPM"
0x18007e456  call    ?InitBoolean@DebugFlags@@CAXPEAUHKEY__@@PEBGPEAH@Z; DebugFlags::InitBoolean(HKEY__ *,ushort const *,int *)
0x18007e45b  mov     rcx, [rbp+hKey]; hKey
0x18007e45f  call    ?InitDWORD@DebugFlags@@CAXPEAUHKEY__@@PEBGPEAK@Z; DebugFlags::InitDWORD(HKEY__ *,ushort const *,ulong *)
0x18007e464  mov     rcx, [rbp+hKey]; hKey
0x18007e468  call    cs:__imp_RegCloseKey
0x18007e46e  mov     cs:?sm_registryInitialized@DebugFlags@@0HA, 1; int DebugFlags::sm_registryInitialized
0x18007e478  add     rsp, 30h
0x18007e47c  pop     rbp
0x18007e47d  retn
```
