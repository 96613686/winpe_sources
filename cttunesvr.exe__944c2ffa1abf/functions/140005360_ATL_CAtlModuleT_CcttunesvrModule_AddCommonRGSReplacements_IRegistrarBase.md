# ATL::CAtlModuleT<CcttunesvrModule>::AddCommonRGSReplacements(IRegistrarBase *)

- ea: `0x140005360`
- end: `0x14000537d`
- name: `?AddCommonRGSReplacements@?$CAtlModuleT@VCcttunesvrModule@@@ATL@@UEAAJPEAUIRegistrarBase@@@Z`
- size: `29`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x140007010`

## pseudocode

```c
__int64 __fastcall ATL::CAtlModuleT<CcttunesvrModule>::AddCommonRGSReplacements(__int64 a1, __int64 a2)
{
  return (*(__int64 (__fastcall **)(__int64, const wchar_t *, const wchar_t *))(*(_QWORD *)a2 + 24LL))(
           a2,
           L"APPID",
           L"{C3A34354-660F-41EE-B072-2AEA5E3A80AF}");
}

```

## disassembly

```asm
0x140005360  mov     rax, [rdx]
0x140005363  lea     r8, aC3a34354660f41; "{C3A34354-660F-41EE-B072-2AEA5E3A80AF}"
0x14000536a  mov     rcx, rdx
0x14000536d  lea     rdx, aAppid; "APPID"
0x140005374  mov     rax, [rax+18h]
0x140005378  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
