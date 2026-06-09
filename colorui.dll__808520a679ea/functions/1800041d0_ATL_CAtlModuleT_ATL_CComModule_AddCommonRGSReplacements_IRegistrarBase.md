# ATL::CAtlModuleT<ATL::CComModule>::AddCommonRGSReplacements(IRegistrarBase *)

- ea: `0x1800041d0`
- end: `0x1800041ed`
- name: `?AddCommonRGSReplacements@?$CAtlModuleT@VCComModule@ATL@@@ATL@@UEAAJPEAUIRegistrarBase@@@Z`
- size: `29`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180019010`

## pseudocode

```c
__int64 __fastcall ATL::CAtlModuleT<ATL::CComModule>::AddCommonRGSReplacements(__int64 a1, __int64 a2)
{
  return (*(__int64 (__fastcall **)(__int64, const wchar_t *, const unsigned __int16 *))(*(_QWORD *)a2 + 24LL))(
           a2,
           L"APPID",
           &byte_18001C2DC);
}

```

## disassembly

```asm
0x1800041d0  mov     rax, [rdx]
0x1800041d3  lea     r8, byte_18001C2DC
0x1800041da  mov     rcx, rdx
0x1800041dd  lea     rdx, aAppid; "APPID"
0x1800041e4  mov     rax, [rax+18h]
0x1800041e8  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
