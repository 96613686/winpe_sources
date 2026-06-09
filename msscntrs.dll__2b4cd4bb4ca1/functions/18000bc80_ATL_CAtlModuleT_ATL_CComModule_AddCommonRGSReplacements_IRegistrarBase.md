# ATL::CAtlModuleT<ATL::CComModule>::AddCommonRGSReplacements(IRegistrarBase *)

- ea: `0x18000bc80`
- end: `0x18000bca7`
- name: `?AddCommonRGSReplacements@?$CAtlModuleT@VCComModule@ATL@@@ATL@@UEAAJPEAUIRegistrarBase@@@Z`
- size: `39`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180018010`

## pseudocode

```c
__int64 __fastcall ATL::CAtlModuleT<ATL::CComModule>::AddCommonRGSReplacements(__int64 a1, __int64 a2)
{
  return (*(__int64 (__fastcall **)(__int64, const wchar_t *, const WCHAR *))(*(_QWORD *)a2 + 24LL))(
           a2,
           L"APPID",
           &Class);
}

```

## disassembly

```asm
0x18000bc80  sub     rsp, 28h
0x18000bc84  mov     rcx, rdx
0x18000bc87  mov     rax, [rdx]
0x18000bc8a  lea     r8, Class
0x18000bc91  lea     rdx, aAppid; "APPID"
0x18000bc98  mov     rax, [rax+18h]
0x18000bc9c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bca1  nop
0x18000bca2  add     rsp, 28h
0x18000bca6  retn
```
