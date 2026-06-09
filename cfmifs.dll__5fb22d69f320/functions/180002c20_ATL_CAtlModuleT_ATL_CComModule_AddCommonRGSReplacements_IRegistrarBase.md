# ATL::CAtlModuleT<ATL::CComModule>::AddCommonRGSReplacements(IRegistrarBase *)

- ea: `0x180002c20`
- end: `0x180002c3d`
- name: `?AddCommonRGSReplacements@?$CAtlModuleT@VCComModule@ATL@@@ATL@@UEAAJPEAUIRegistrarBase@@@Z`
- size: `29`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180007010`

## pseudocode

```c
__int64 __fastcall ATL::CAtlModuleT<ATL::CComModule>::AddCommonRGSReplacements(__int64 a1, __int64 a2)
{
  return (*(__int64 (__fastcall **)(__int64, const wchar_t *, int *))(*(_QWORD *)a2 + 24LL))(
           a2,
           L"APPID",
           &dword_180008E24);
}

```

## disassembly

```asm
0x180002c20  mov     rax, [rdx]
0x180002c23  lea     r8, dword_180008E24
0x180002c2a  mov     rcx, rdx
0x180002c2d  lea     rdx, aAppid; "APPID"
0x180002c34  mov     rax, [rax+18h]
0x180002c38  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
