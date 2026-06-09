# ATL::CAtlModuleT<CRasDiagHCModule>::AddCommonRGSReplacements(IRegistrarBase *)

- ea: `0x180003030`
- end: `0x180003058`
- name: `?AddCommonRGSReplacements@?$CAtlModuleT@VCRasDiagHCModule@@@ATL@@UEAAJPEAUIRegistrarBase@@@Z`
- size: `40`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18000f010`

## pseudocode

```c
__int64 __fastcall ATL::CAtlModuleT<CRasDiagHCModule>::AddCommonRGSReplacements(__int64 a1, __int64 a2)
{
  return (*(__int64 (__fastcall **)(__int64, const wchar_t *, const wchar_t *))(*(_QWORD *)a2 + 24LL))(
           a2,
           L"APPID",
           L"{6f3282b6-2b50-42b7-af7a-aae69d14a6ca}");
}

```

## disassembly

```asm
0x180003030  sub     rsp, 28h
0x180003034  mov     rcx, rdx
0x180003037  mov     rax, [rdx]
0x18000303a  lea     r8, a6f3282b62b5042; "{6f3282b6-2b50-42b7-af7a-aae69d14a6ca}"
0x180003041  lea     rdx, aAppid_0; "APPID"
0x180003048  mov     rax, [rax+18h]
0x18000304c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003051  nop
0x180003052  add     rsp, 28h
0x180003056  retn
```
