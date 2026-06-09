# TransformSystemSleepDiagnosticsReport(ushort const *,ushort const *)

- ea: `0x18008a4f0`
- end: `0x18008a53f`
- name: `?TransformSystemSleepDiagnosticsReport@@YAJPEBG0@Z`
- size: `79`
- prototype: `__int64 __fastcall(const unsigned __int16 *, wchar_t *FileName)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x180049ae4`
- `0x18008a4f0`

## import_xrefs

- `api-ms-win-ole32-ie-l1-1-0!CoInitialize` at `0x18008a507`
- `api-ms-win-ole32-ie-l1-1-0!CoInitialize` at `0x18008a507`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18008a527`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18008a527`

## string_xrefs

- `0x18008a516`: `res://energy.dll/IDR_XML_SLEEPDIAGNOSTICS_TRANSFORM`

## pseudocode

```c
__int64 __fastcall TransformSystemSleepDiagnosticsReport(const unsigned __int16 *a1, wchar_t *FileName)
{
  HRESULT v4; // ebx

  v4 = CoInitialize(0);
  if ( v4 >= 0 )
  {
    v4 = PerformXslTransform(L"res://energy.dll/IDR_XML_SLEEPDIAGNOSTICS_TRANSFORM", a1, FileName);
    CoUninitialize();
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18008a4f0  mov     [rsp+arg_0], rbx
0x18008a4f5  mov     [rsp+arg_8], rsi
0x18008a4fa  push    rdi
0x18008a4fb  sub     rsp, 20h
0x18008a4ff  mov     rsi, rcx
0x18008a502  mov     rdi, rdx
0x18008a505  xor     ecx, ecx; pvReserved
0x18008a507  call    cs:__imp_CoInitialize
0x18008a50d  mov     ebx, eax
0x18008a50f  test    eax, eax
0x18008a511  js      short loc_18008A52D
0x18008a513  mov     r8, rdi; FileName
0x18008a516  lea     rcx, aResEnergyDllId_1; "res://energy.dll/IDR_XML_SLEEPDIAGNOSTI"...
0x18008a51d  mov     rdx, rsi; unsigned __int16 *
0x18008a520  call    ?PerformXslTransform@@YAJPEBG00@Z; PerformXslTransform(ushort const *,ushort const *,ushort const *)
0x18008a525  mov     ebx, eax
0x18008a527  call    cs:__imp_CoUninitialize
0x18008a52d  mov     rsi, [rsp+28h+arg_8]
0x18008a532  mov     eax, ebx
0x18008a534  mov     rbx, [rsp+28h+arg_0]
0x18008a539  add     rsp, 20h
0x18008a53d  pop     rdi
0x18008a53e  retn
```
