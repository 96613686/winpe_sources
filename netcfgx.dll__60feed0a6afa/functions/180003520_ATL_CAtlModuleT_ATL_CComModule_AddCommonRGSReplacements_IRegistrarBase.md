# ATL::CAtlModuleT<ATL::CComModule>::AddCommonRGSReplacements(IRegistrarBase *)

- ea: `0x180003520`
- end: `0x180003547`
- name: `?AddCommonRGSReplacements@?$CAtlModuleT@VCComModule@ATL@@@ATL@@UEAAJPEAUIRegistrarBase@@@Z`
- size: `39`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180013010`

## pseudocode

```c
__int64 __fastcall ATL::CAtlModuleT<ATL::CComModule>::AddCommonRGSReplacements(__int64 a1, __int64 a2)
{
  return (*(__int64 (__fastcall **)(__int64, const wchar_t *, const unsigned __int16 *))(*(_QWORD *)a2 + 24LL))(
           a2,
           L"APPID",
           &dword_18001520C);
}

```

## disassembly

```asm
0x180003520  sub     rsp, 28h
0x180003524  mov     rcx, rdx
0x180003527  mov     rax, [rdx]
0x18000352a  lea     r8, dword_18001520C
0x180003531  lea     rdx, aAppid; "APPID"
0x180003538  mov     rax, [rax+18h]
0x18000353c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003541  nop
0x180003542  add     rsp, 28h
0x180003546  retn
```
