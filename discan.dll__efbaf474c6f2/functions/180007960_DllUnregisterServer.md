# DllUnregisterServer

- ea: `0x180007960`
- end: `0x18000799e`
- name: `DllUnregisterServer`
- size: `62`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1800077a4`

## import_xrefs

- `KERNEL32!GetThreadLocale` at `0x18000796a`
- `KERNEL32!GetThreadLocale` at `0x18000796a`
- `KERNEL32!SetThreadLocale` at `0x180007977`
- `KERNEL32!SetThreadLocale` at `0x18000798b`
- `KERNEL32!SetThreadLocale` at `0x180007977`
- `KERNEL32!SetThreadLocale` at `0x18000798b`

## pseudocode

```c
HRESULT __stdcall DllUnregisterServer()
{
  LCID ThreadLocale; // edi
  int v1; // eax
  HRESULT v2; // ebx

  ThreadLocale = GetThreadLocale();
  SetThreadLocale(0x800u);
  v1 = ATL::CAtlModuleT<CDataIntegrityScanModule>::UnregisterServer();
  v2 = 0;
  if ( v1 < 0 )
    v2 = v1;
  SetThreadLocale(ThreadLocale);
  return v2;
}

```

## disassembly

```asm
0x180007960  mov     [rsp+arg_0], rbx
0x180007965  push    rdi
0x180007966  sub     rsp, 20h
0x18000796a  call    cs:__imp_GetThreadLocale
0x180007970  mov     ecx, 800h; Locale
0x180007975  mov     edi, eax
0x180007977  call    cs:__imp_SetThreadLocale
0x18000797d  call    ?UnregisterServer@?$CAtlModuleT@VCDataIntegrityScanModule@@@ATL@@QEAAJHPEBU_GUID@@@Z; ATL::CAtlModuleT<CDataIntegrityScanModule>::UnregisterServer(int,_GUID const *)
0x180007982  xor     ebx, ebx
0x180007984  mov     ecx, edi; Locale
0x180007986  test    eax, eax
0x180007988  cmovs   ebx, eax
0x18000798b  call    cs:__imp_SetThreadLocale
0x180007991  mov     eax, ebx
0x180007993  mov     rbx, [rsp+28h+arg_0]
0x180007998  add     rsp, 20h
0x18000799c  pop     rdi
0x18000799d  retn
```
