# ATL::CAtlModuleT<ATL::CComModule>::AddCommonRGSReplacements(IRegistrarBase *)

- ea: `0x180008070`
- end: `0x18000808d`
- name: `?AddCommonRGSReplacements@?$CAtlModuleT@VCComModule@ATL@@@ATL@@UEAAJPEAUIRegistrarBase@@@Z`
- size: `29`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180019010`

## pseudocode

```c
__int64 __fastcall ATL::CAtlModuleT<ATL::CComModule>::AddCommonRGSReplacements(__int64 a1, __int64 a2)
{
  return (*(__int64 (__fastcall **)(__int64, const wchar_t *, const OLECHAR *))(*(_QWORD *)a2 + 24LL))(
           a2,
           L"APPID",
           &word_18001BDF8);
}

```

## disassembly

```asm
0x180008070  mov     rax, [rdx]
0x180008073  lea     r8, word_18001BDF8
0x18000807a  mov     rcx, rdx
0x18000807d  lea     rdx, aAppid; "APPID"
0x180008084  mov     rax, [rax+18h]
0x180008088  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
