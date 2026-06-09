# ATL::CAtlModuleT<CATLdtshModule>::AddCommonRGSReplacements(IRegistrarBase *)

- ea: `0x1800041b0`
- end: `0x1800041cd`
- name: `?AddCommonRGSReplacements@?$CAtlModuleT@VCATLdtshModule@@@ATL@@UEAAJPEAUIRegistrarBase@@@Z`
- size: `29`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180005010`

## pseudocode

```c
__int64 __fastcall ATL::CAtlModuleT<CATLdtshModule>::AddCommonRGSReplacements(__int64 a1, __int64 a2)
{
  return (*(__int64 (__fastcall **)(__int64, const wchar_t *, __int64 *))(*(_QWORD *)a2 + 24LL))(
           a2,
           L"APPID",
           &qword_180007190);
}

```

## disassembly

```asm
0x1800041b0  mov     rax, [rdx]
0x1800041b3  lea     r8, qword_180007190
0x1800041ba  mov     rcx, rdx
0x1800041bd  lea     rdx, aAppid; "APPID"
0x1800041c4  mov     rax, [rax+18h]
0x1800041c8  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
