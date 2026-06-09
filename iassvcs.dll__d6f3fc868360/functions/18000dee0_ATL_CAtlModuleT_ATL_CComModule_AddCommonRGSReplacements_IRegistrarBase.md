# ATL::CAtlModuleT<ATL::CComModule>::AddCommonRGSReplacements(IRegistrarBase *)

- ea: `0x18000dee0`
- end: `0x18000df07`
- name: `?AddCommonRGSReplacements@?$CAtlModuleT@VCComModule@ATL@@@ATL@@UEAAJPEAUIRegistrarBase@@@Z`
- size: `39`
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
  return (*(__int64 (__fastcall **)(__int64, const wchar_t *, int *))(*(_QWORD *)a2 + 24LL))(
           a2,
           L"APPID",
           &dword_18001C7CC);
}

```

## disassembly

```asm
0x18000dee0  sub     rsp, 28h
0x18000dee4  mov     rcx, rdx
0x18000dee7  mov     rax, [rdx]
0x18000deea  lea     r8, dword_18001C7CC
0x18000def1  lea     rdx, aAppid; "APPID"
0x18000def8  mov     rax, [rax+18h]
0x18000defc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000df01  nop
0x18000df02  add     rsp, 28h
0x18000df06  retn
```
