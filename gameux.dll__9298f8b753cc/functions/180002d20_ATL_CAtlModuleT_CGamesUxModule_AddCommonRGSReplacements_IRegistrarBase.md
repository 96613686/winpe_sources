# ATL::CAtlModuleT<CGamesUxModule>::AddCommonRGSReplacements(IRegistrarBase *)

- ea: `0x180002d20`
- end: `0x180002d3d`
- name: `?AddCommonRGSReplacements@?$CAtlModuleT@VCGamesUxModule@@@ATL@@UEAAJPEAUIRegistrarBase@@@Z`
- size: `29`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180004010`

## pseudocode

```c
__int64 __fastcall ATL::CAtlModuleT<CGamesUxModule>::AddCommonRGSReplacements(__int64 a1, __int64 a2)
{
  return (*(__int64 (__fastcall **)(__int64, const wchar_t *, __int64 *))(*(_QWORD *)a2 + 24LL))(
           a2,
           L"APPID",
           &qword_180005920);
}

```

## disassembly

```asm
0x180002d20  mov     rax, [rdx]
0x180002d23  lea     r8, qword_180005920
0x180002d2a  mov     rcx, rdx
0x180002d2d  lea     rdx, aAppid; "APPID"
0x180002d34  mov     rax, [rax+18h]
0x180002d38  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
