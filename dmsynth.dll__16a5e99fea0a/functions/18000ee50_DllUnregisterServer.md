# DllUnregisterServer

- ea: `0x18000ee50`
- end: `0x18000ee8f`
- name: `DllUnregisterServer`
- size: `63`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x1800112a0`

## pseudocode

```c
HRESULT __stdcall DllUnregisterServer()
{
  __int64 v0; // rdx
  __int64 v1; // rdx

  UnregisterServer(&CLSID_DirectMusicSynth, v0, (__int64)&g_szSynthVerIndProgID, (__int64)&g_szSynthProgID);
  UnregisterServer(&CLSID_DirectMusicSynthSink, v1, (__int64)&g_szSinkVerIndProgID, (__int64)&g_szSinkProgID);
  return 0;
}

```

## disassembly

```asm
0x18000ee50  sub     rsp, 28h
0x18000ee54  lea     r9, ?g_szSynthProgID@@3PADA; "Microsoft.DirectMusicSynth.1"
0x18000ee5b  lea     r8, ?g_szSynthVerIndProgID@@3PADA; "Microsoft.DirectMusicSynth"
0x18000ee62  lea     rcx, CLSID_DirectMusicSynth
0x18000ee69  call    UnregisterServer
0x18000ee6e  lea     r9, ?g_szSinkProgID@@3PADA; "Microsoft.DirectMusicSynthSink.1"
0x18000ee75  lea     r8, ?g_szSinkVerIndProgID@@3PADA; "Microsoft.DirectMusicSynthSink"
0x18000ee7c  lea     rcx, CLSID_DirectMusicSynthSink
0x18000ee83  call    UnregisterServer
0x18000ee88  xor     eax, eax
0x18000ee8a  add     rsp, 28h
0x18000ee8e  retn
```
