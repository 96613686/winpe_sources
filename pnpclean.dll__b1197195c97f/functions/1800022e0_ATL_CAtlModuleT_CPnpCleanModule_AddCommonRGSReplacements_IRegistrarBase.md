# ATL::CAtlModuleT<CPnpCleanModule>::AddCommonRGSReplacements(IRegistrarBase *)

- ea: `0x1800022e0`
- end: `0x1800022fd`
- name: `?AddCommonRGSReplacements@?$CAtlModuleT@VCPnpCleanModule@@@ATL@@UEAAJPEAUIRegistrarBase@@@Z`
- size: `29`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18000a010`

## pseudocode

```c
__int64 __fastcall ATL::CAtlModuleT<CPnpCleanModule>::AddCommonRGSReplacements(__int64 a1, __int64 a2)
{
  return (*(__int64 (__fastcall **)(__int64, const wchar_t *, __int64 *))(*(_QWORD *)a2 + 24LL))(
           a2,
           L"APPID",
           &qword_18000C0B8);
}

```

## disassembly

```asm
0x1800022e0  mov     rax, [rdx]
0x1800022e3  lea     r8, qword_18000C0B8
0x1800022ea  mov     rcx, rdx
0x1800022ed  lea     rdx, aAppid; "APPID"
0x1800022f4  mov     rax, [rax+18h]
0x1800022f8  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
