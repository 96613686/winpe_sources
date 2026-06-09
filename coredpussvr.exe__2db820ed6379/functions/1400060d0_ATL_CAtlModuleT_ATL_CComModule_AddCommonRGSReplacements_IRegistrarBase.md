# ATL::CAtlModuleT<ATL::CComModule>::AddCommonRGSReplacements(IRegistrarBase *)

- ea: `0x1400060d0`
- end: `0x1400060f8`
- name: `?AddCommonRGSReplacements@?$CAtlModuleT@VCComModule@ATL@@@ATL@@UEAAJPEAUIRegistrarBase@@@Z`
- size: `40`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x14000a010`

## pseudocode

```c
__int64 __fastcall ATL::CAtlModuleT<ATL::CComModule>::AddCommonRGSReplacements(__int64 a1, __int64 a2)
{
  return (*(__int64 (__fastcall **)(__int64, const wchar_t *, __int64 *))(*(_QWORD *)a2 + 24LL))(
           a2,
           L"APPID",
           &qword_14000BE68);
}

```

## disassembly

```asm
0x1400060d0  sub     rsp, 28h
0x1400060d4  mov     rcx, rdx
0x1400060d7  mov     rax, [rdx]
0x1400060da  lea     r8, qword_14000BE68
0x1400060e1  lea     rdx, aAppid; "APPID"
0x1400060e8  mov     rax, [rax+18h]
0x1400060ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400060f1  nop
0x1400060f2  add     rsp, 28h
0x1400060f6  retn
```
