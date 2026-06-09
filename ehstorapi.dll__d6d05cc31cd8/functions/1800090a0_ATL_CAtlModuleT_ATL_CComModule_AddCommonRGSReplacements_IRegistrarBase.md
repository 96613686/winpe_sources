# ATL::CAtlModuleT<ATL::CComModule>::AddCommonRGSReplacements(IRegistrarBase *)

- ea: `0x1800090a0`
- end: `0x1800090c7`
- name: `?AddCommonRGSReplacements@?$CAtlModuleT@VCComModule@ATL@@@ATL@@UEAAJPEAUIRegistrarBase@@@Z`
- size: `39`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18000d010`

## pseudocode

```c
__int64 __fastcall ATL::CAtlModuleT<ATL::CComModule>::AddCommonRGSReplacements(__int64 a1, __int64 a2)
{
  return (*(__int64 (__fastcall **)(__int64, const wchar_t *, __int64 *))(*(_QWORD *)a2 + 24LL))(
           a2,
           L"APPID",
           &qword_18000F700);
}

```

## disassembly

```asm
0x1800090a0  sub     rsp, 28h
0x1800090a4  mov     rcx, rdx
0x1800090a7  mov     rax, [rdx]
0x1800090aa  lea     r8, qword_18000F700
0x1800090b1  lea     rdx, aAppid; "APPID"
0x1800090b8  mov     rax, [rax+18h]
0x1800090bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800090c1  nop
0x1800090c2  add     rsp, 28h
0x1800090c6  retn
```
