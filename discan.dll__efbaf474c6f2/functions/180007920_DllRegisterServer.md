# DllRegisterServer

- ea: `0x180007920`
- end: `0x180007959`
- name: `DllRegisterServer`
- size: `57`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180007604`

## import_xrefs

- `KERNEL32!GetThreadLocale` at `0x18000792a`
- `KERNEL32!GetThreadLocale` at `0x18000792a`
- `KERNEL32!SetThreadLocale` at `0x180007937`
- `KERNEL32!SetThreadLocale` at `0x180007946`
- `KERNEL32!SetThreadLocale` at `0x180007937`
- `KERNEL32!SetThreadLocale` at `0x180007946`

## pseudocode

```c
HRESULT __stdcall DllRegisterServer()
{
  LCID ThreadLocale; // edi
  HRESULT v1; // ebx

  ThreadLocale = GetThreadLocale();
  SetThreadLocale(0x800u);
  v1 = ATL::CAtlModuleT<CDataIntegrityScanModule>::RegisterServer();
  SetThreadLocale(ThreadLocale);
  return v1;
}

```

## disassembly

```asm
0x180007920  mov     [rsp+arg_0], rbx
0x180007925  push    rdi
0x180007926  sub     rsp, 20h
0x18000792a  call    cs:__imp_GetThreadLocale
0x180007930  mov     ecx, 800h; Locale
0x180007935  mov     edi, eax
0x180007937  call    cs:__imp_SetThreadLocale
0x18000793d  call    ?RegisterServer@?$CAtlModuleT@VCDataIntegrityScanModule@@@ATL@@QEAAJHPEBU_GUID@@@Z; ATL::CAtlModuleT<CDataIntegrityScanModule>::RegisterServer(int,_GUID const *)
0x180007942  mov     ecx, edi; Locale
0x180007944  mov     ebx, eax
0x180007946  call    cs:__imp_SetThreadLocale
0x18000794c  mov     eax, ebx
0x18000794e  mov     rbx, [rsp+28h+arg_0]
0x180007953  add     rsp, 20h
0x180007957  pop     rdi
0x180007958  retn
```
