# ATL::CAtlModuleT<ATL::CComModule>::AddCommonRGSReplacements(IRegistrarBase *)

- ea: `0x14000c5b0`
- end: `0x14000c5cd`
- name: `?AddCommonRGSReplacements@?$CAtlModuleT@VCComModule@ATL@@@ATL@@UEAAJPEAUIRegistrarBase@@@Z`
- size: `29`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x140010010`

## pseudocode

```c
__int64 __fastcall ATL::CAtlModuleT<ATL::CComModule>::AddCommonRGSReplacements(__int64 a1, __int64 a2)
{
  return (*(__int64 (__fastcall **)(__int64, const wchar_t *, char *))(*(_QWORD *)a2 + 24LL))(
           a2,
           L"APPID",
           byte_140012698);
}

```

## disassembly

```asm
0x14000c5b0  mov     rax, [rdx]
0x14000c5b3  lea     r8, byte_140012698
0x14000c5ba  mov     rcx, rdx
0x14000c5bd  lea     rdx, aAppid; "APPID"
0x14000c5c4  mov     rax, [rax+18h]
0x14000c5c8  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
