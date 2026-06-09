# DllRegisterServer

- ea: `0x18000ede0`
- end: `0x18000ee3c`
- name: `DllRegisterServer`
- size: `92`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x18000e930`
- `0x180010fc0`

## pseudocode

```c
HRESULT __stdcall DllRegisterServer()
{
  __int64 v0; // rcx
  __int64 v1; // rcx
  const char *v2; // rdx
  const struct _GUID *v3; // rcx

  RegisterServer(
    v0,
    &CLSID_DirectMusicSynth,
    (const BYTE *)&g_szSynthFriendlyName,
    (const CHAR *)&g_szSynthVerIndProgID,
    (const CHAR *)&g_szSynthProgID);
  RegisterServer(
    v1,
    &CLSID_DirectMusicSynthSink,
    (const BYTE *)&g_szSinkFriendlyName,
    (const CHAR *)&g_szSinkVerIndProgID,
    (const CHAR *)&g_szSinkProgID);
  RegisterSynth(v3, v2);
  return 0;
}

```

## disassembly

```asm
0x18000ede0  sub     rsp, 38h
0x18000ede4  lea     rax, ?g_szSynthProgID@@3PADA; "Microsoft.DirectMusicSynth.1"
0x18000edeb  lea     r9, ?g_szSynthVerIndProgID@@3PADA; "Microsoft.DirectMusicSynth"
0x18000edf2  mov     [rsp+38h+var_18], rax
0x18000edf7  lea     r8, ?g_szSynthFriendlyName@@3PADA; "DirectMusicSynth"
0x18000edfe  lea     rdx, CLSID_DirectMusicSynth
0x18000ee05  call    RegisterServer
0x18000ee0a  lea     rax, ?g_szSinkProgID@@3PADA; "Microsoft.DirectMusicSynthSink.1"
0x18000ee11  lea     r9, ?g_szSinkVerIndProgID@@3PADA; "Microsoft.DirectMusicSynthSink"
0x18000ee18  mov     [rsp+38h+var_18], rax
0x18000ee1d  lea     r8, ?g_szSinkFriendlyName@@3PADA; "DirectMusicSynthSink"
0x18000ee24  lea     rdx, CLSID_DirectMusicSynthSink
0x18000ee2b  call    RegisterServer
0x18000ee30  call    ?RegisterSynth@@YAJAEBU_GUID@@QEBD@Z; RegisterSynth(_GUID const &,char const * const)
0x18000ee35  xor     eax, eax
0x18000ee37  add     rsp, 38h
0x18000ee3b  retn
```
