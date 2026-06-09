# EnergyWizard_TransformReport

- ea: `0x18005e270`
- end: `0x18005e2cb`
- name: `EnergyWizard_TransformReport`
- size: `91`
- prototype: `__int64 __fastcall(__int64, const unsigned __int16 *, wchar_t *)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x180049ae4`
- `0x18005e270`

## import_xrefs

- `api-ms-win-ole32-ie-l1-1-0!CoInitialize` at `0x18005e28c`
- `api-ms-win-ole32-ie-l1-1-0!CoInitialize` at `0x18005e28c`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18005e2ac`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18005e2ac`

## string_xrefs

- `0x18005e29b`: `res://energy.dll/IDR_XML_DEFAULT_TRANSFORM.XSL`

## pseudocode

```c
__int64 __fastcall EnergyWizard_TransformReport(__int64 a1, const unsigned __int16 *a2, wchar_t *a3)
{
  HRESULT v5; // ebx

  if ( a1 )
  {
    v5 = CoInitialize(0);
    if ( v5 >= 0 )
    {
      v5 = PerformXslTransform(L"res://energy.dll/IDR_XML_DEFAULT_TRANSFORM.XSL", a2, a3);
      CoUninitialize();
    }
  }
  else
  {
    return (unsigned int)-2147024890;
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18005e270  mov     [rsp+arg_0], rbx
0x18005e275  mov     [rsp+arg_8], rsi
0x18005e27a  push    rdi
0x18005e27b  sub     rsp, 20h
0x18005e27f  mov     rdi, r8
0x18005e282  mov     rsi, rdx
0x18005e285  test    rcx, rcx
0x18005e288  jz      short loc_18005E2B4
0x18005e28a  xor     ecx, ecx; pvReserved
0x18005e28c  call    cs:__imp_CoInitialize
0x18005e292  mov     ebx, eax
0x18005e294  test    eax, eax
0x18005e296  js      short loc_18005E2B9
0x18005e298  mov     r8, rdi; FileName
0x18005e29b  lea     rcx, aResEnergyDllId_2; "res://energy.dll/IDR_XML_DEFAULT_TRANSF"...
0x18005e2a2  mov     rdx, rsi; unsigned __int16 *
0x18005e2a5  call    ?PerformXslTransform@@YAJPEBG00@Z; PerformXslTransform(ushort const *,ushort const *,ushort const *)
0x18005e2aa  mov     ebx, eax
0x18005e2ac  call    cs:__imp_CoUninitialize
0x18005e2b2  jmp     short loc_18005E2B9
0x18005e2b4  mov     ebx, 80070006h
0x18005e2b9  mov     rsi, [rsp+28h+arg_8]
0x18005e2be  mov     eax, ebx
0x18005e2c0  mov     rbx, [rsp+28h+arg_0]
0x18005e2c5  add     rsp, 20h
0x18005e2c9  pop     rdi
0x18005e2ca  retn
```
