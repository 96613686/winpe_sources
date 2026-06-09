# ATL::CAtlModuleT<CTaskModule>::AddCommonRGSReplacements(IRegistrarBase *)

- ea: `0x180005470`
- end: `0x180005497`
- name: `?AddCommonRGSReplacements@?$CAtlModuleT@VCTaskModule@@@ATL@@UEAAJPEAUIRegistrarBase@@@Z`
- size: `39`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x18000b010`

## pseudocode

```c
__int64 __fastcall ATL::CAtlModuleT<CTaskModule>::AddCommonRGSReplacements(__int64 a1, __int64 a2)
{
  return (*(__int64 (__fastcall **)(__int64, const wchar_t *, __int64 *))(*(_QWORD *)a2 + 24LL))(
           a2,
           L"APPID",
           &qword_18000D1B8);
}

```

## disassembly

```asm
0x180005470  sub     rsp, 28h
0x180005474  mov     rcx, rdx
0x180005477  mov     rax, [rdx]
0x18000547a  lea     r8, qword_18000D1B8
0x180005481  lea     rdx, aAppid; "APPID"
0x180005488  mov     rax, [rax+18h]
0x18000548c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005491  nop
0x180005492  add     rsp, 28h
0x180005496  retn
```
