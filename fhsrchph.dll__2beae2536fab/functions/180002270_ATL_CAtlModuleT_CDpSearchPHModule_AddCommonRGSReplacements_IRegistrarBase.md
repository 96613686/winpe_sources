# ATL::CAtlModuleT<CDpSearchPHModule>::AddCommonRGSReplacements(IRegistrarBase *)

- ea: `0x180002270`
- end: `0x180002297`
- name: `?AddCommonRGSReplacements@?$CAtlModuleT@VCDpSearchPHModule@@@ATL@@UEAAJPEAUIRegistrarBase@@@Z`
- size: `39`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18000c010`

## pseudocode

```c
__int64 __fastcall ATL::CAtlModuleT<CDpSearchPHModule>::AddCommonRGSReplacements(__int64 a1, __int64 a2)
{
  return (*(__int64 (__fastcall **)(__int64, const wchar_t *, __int64 *))(*(_QWORD *)a2 + 24LL))(
           a2,
           L"APPID",
           &qword_18000DFA8);
}

```

## disassembly

```asm
0x180002270  sub     rsp, 28h
0x180002274  mov     rcx, rdx
0x180002277  mov     rax, [rdx]
0x18000227a  lea     r8, qword_18000DFA8
0x180002281  lea     rdx, aAppid; "APPID"
0x180002288  mov     rax, [rax+18h]
0x18000228c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002291  nop
0x180002292  add     rsp, 28h
0x180002296  retn
```
