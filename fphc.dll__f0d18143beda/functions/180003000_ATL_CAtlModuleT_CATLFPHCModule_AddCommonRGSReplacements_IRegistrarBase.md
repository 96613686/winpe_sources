# ATL::CAtlModuleT<CATLFPHCModule>::AddCommonRGSReplacements(IRegistrarBase *)

- ea: `0x180003000`
- end: `0x180003027`
- name: `?AddCommonRGSReplacements@?$CAtlModuleT@VCATLFPHCModule@@@ATL@@UEAAJPEAUIRegistrarBase@@@Z`
- size: `39`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180012010`

## pseudocode

```c
__int64 __fastcall ATL::CAtlModuleT<CATLFPHCModule>::AddCommonRGSReplacements(__int64 a1, __int64 a2)
{
  return (*(__int64 (__fastcall **)(__int64, const wchar_t *, const wchar_t *))(*(_QWORD *)a2 + 24LL))(
           a2,
           L"APPID",
           L"{33AD1F2B-0DE9-429e-8529-F1FC7CAE52D0}");
}

```

## disassembly

```asm
0x180003000  sub     rsp, 28h
0x180003004  mov     rcx, rdx
0x180003007  mov     rax, [rdx]
0x18000300a  lea     r8, a33ad1f2b0de942; "{33AD1F2B-0DE9-429e-8529-F1FC7CAE52D0}"
0x180003011  lea     rdx, aAppid_0; "APPID"
0x180003018  mov     rax, [rax+18h]
0x18000301c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003021  nop
0x180003022  add     rsp, 28h
0x180003026  retn
```
