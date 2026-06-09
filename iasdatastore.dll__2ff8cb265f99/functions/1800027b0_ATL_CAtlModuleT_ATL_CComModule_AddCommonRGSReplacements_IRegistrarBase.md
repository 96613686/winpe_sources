# ATL::CAtlModuleT<ATL::CComModule>::AddCommonRGSReplacements(IRegistrarBase *)

- ea: `0x1800027b0`
- end: `0x1800027d7`
- name: `?AddCommonRGSReplacements@?$CAtlModuleT@VCComModule@ATL@@@ATL@@UEAAJPEAUIRegistrarBase@@@Z`
- size: `39`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180010010`

## pseudocode

```c
__int64 __fastcall ATL::CAtlModuleT<ATL::CComModule>::AddCommonRGSReplacements(__int64 a1, __int64 a2)
{
  return (*(__int64 (__fastcall **)(__int64, const wchar_t *, __int64 *))(*(_QWORD *)a2 + 24LL))(
           a2,
           L"APPID",
           &qword_180013DB8);
}

```

## disassembly

```asm
0x1800027b0  sub     rsp, 28h
0x1800027b4  mov     rcx, rdx
0x1800027b7  mov     rax, [rdx]
0x1800027ba  lea     r8, qword_180013DB8
0x1800027c1  lea     rdx, aAppid; "APPID"
0x1800027c8  mov     rax, [rax+18h]
0x1800027cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800027d1  nop
0x1800027d2  add     rsp, 28h
0x1800027d6  retn
```
