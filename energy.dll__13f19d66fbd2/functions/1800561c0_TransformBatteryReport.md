# TransformBatteryReport

- ea: `0x1800561c0`
- end: `0x18005620f`
- name: `TransformBatteryReport`
- size: `79`
- prototype: `__int64 __fastcall(unsigned __int16 *, wchar_t *FileName)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x180049ae4`
- `0x1800561c0`

## import_xrefs

- `api-ms-win-ole32-ie-l1-1-0!CoInitialize` at `0x1800561d7`
- `api-ms-win-ole32-ie-l1-1-0!CoInitialize` at `0x1800561d7`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800561f7`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800561f7`

## string_xrefs

- `0x1800561e6`: `res://energy.dll/IDR_XML_BATTERY_TRANSFORM`

## pseudocode

```c
__int64 __fastcall TransformBatteryReport(unsigned __int16 *a1, wchar_t *FileName)
{
  HRESULT v4; // ebx

  v4 = CoInitialize(0);
  if ( v4 >= 0 )
  {
    v4 = PerformXslTransform(L"res://energy.dll/IDR_XML_BATTERY_TRANSFORM", a1, FileName);
    CoUninitialize();
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x1800561c0  mov     [rsp+arg_0], rbx
0x1800561c5  mov     [rsp+arg_8], rsi
0x1800561ca  push    rdi
0x1800561cb  sub     rsp, 20h
0x1800561cf  mov     rsi, rcx
0x1800561d2  mov     rdi, rdx
0x1800561d5  xor     ecx, ecx; pvReserved
0x1800561d7  call    cs:__imp_CoInitialize
0x1800561dd  mov     ebx, eax
0x1800561df  test    eax, eax
0x1800561e1  js      short loc_1800561FD
0x1800561e3  mov     r8, rdi; FileName
0x1800561e6  lea     rcx, aResEnergyDllId; "res://energy.dll/IDR_XML_BATTERY_TRANSF"...
0x1800561ed  mov     rdx, rsi; unsigned __int16 *
0x1800561f0  call    ?PerformXslTransform@@YAJPEBG00@Z; PerformXslTransform(ushort const *,ushort const *,ushort const *)
0x1800561f5  mov     ebx, eax
0x1800561f7  call    cs:__imp_CoUninitialize
0x1800561fd  mov     rsi, [rsp+28h+arg_8]
0x180056202  mov     eax, ebx
0x180056204  mov     rbx, [rsp+28h+arg_0]
0x180056209  add     rsp, 20h
0x18005620d  pop     rdi
0x18005620e  retn
```
