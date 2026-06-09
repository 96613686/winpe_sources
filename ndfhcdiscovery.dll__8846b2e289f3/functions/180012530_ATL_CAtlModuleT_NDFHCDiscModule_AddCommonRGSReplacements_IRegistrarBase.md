# ATL::CAtlModuleT<NDFHCDiscModule>::AddCommonRGSReplacements(IRegistrarBase *)

- ea: `0x180012530`
- end: `0x180012558`
- name: `?AddCommonRGSReplacements@?$CAtlModuleT@VNDFHCDiscModule@@@ATL@@UEAAJPEAUIRegistrarBase@@@Z`
- size: `40`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180015010`

## pseudocode

```c
__int64 __fastcall ATL::CAtlModuleT<NDFHCDiscModule>::AddCommonRGSReplacements(__int64 a1, __int64 a2)
{
  return (*(__int64 (__fastcall **)(__int64, const wchar_t *, const wchar_t *))(*(_QWORD *)a2 + 24LL))(
           a2,
           L"APPID",
           L"{51AF64B1-E07B-4e5c-AB58-D08A9F58E33B}");
}

```

## disassembly

```asm
0x180012530  sub     rsp, 28h
0x180012534  mov     rcx, rdx
0x180012537  mov     rax, [rdx]
0x18001253a  lea     r8, a51af64b1E07b4e; "{51AF64B1-E07B-4e5c-AB58-D08A9F58E33B}"
0x180012541  lea     rdx, aAppid; "APPID"
0x180012548  mov     rax, [rax+18h]
0x18001254c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012551  nop
0x180012552  add     rsp, 28h
0x180012556  retn
```
