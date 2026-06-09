# ATL::CAtlModuleT<ATL::CComModule>::AddCommonRGSReplacements(IRegistrarBase *)

- ea: `0x180008dd0`
- end: `0x180008df7`
- name: `?AddCommonRGSReplacements@?$CAtlModuleT@VCComModule@ATL@@@ATL@@UEAAJPEAUIRegistrarBase@@@Z`
- size: `39`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18001c010`

## pseudocode

```c
__int64 __fastcall ATL::CAtlModuleT<ATL::CComModule>::AddCommonRGSReplacements(__int64 a1, __int64 a2)
{
  return (*(__int64 (__fastcall **)(__int64, const wchar_t *, __int64 *))(*(_QWORD *)a2 + 24LL))(
           a2,
           L"APPID",
           &qword_1800201D8);
}

```

## disassembly

```asm
0x180008dd0  sub     rsp, 28h
0x180008dd4  mov     rcx, rdx
0x180008dd7  mov     rax, [rdx]
0x180008dda  lea     r8, qword_1800201D8
0x180008de1  lea     rdx, aAppid_0; "APPID"
0x180008de8  mov     rax, [rax+18h]
0x180008dec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008df1  nop
0x180008df2  add     rsp, 28h
0x180008df6  retn
```
