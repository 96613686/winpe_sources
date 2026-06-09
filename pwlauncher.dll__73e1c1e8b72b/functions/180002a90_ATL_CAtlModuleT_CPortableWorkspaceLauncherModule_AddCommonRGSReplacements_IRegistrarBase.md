# ATL::CAtlModuleT<CPortableWorkspaceLauncherModule>::AddCommonRGSReplacements(IRegistrarBase *)

- ea: `0x180002a90`
- end: `0x180002ab7`
- name: `?AddCommonRGSReplacements@?$CAtlModuleT@VCPortableWorkspaceLauncherModule@@@ATL@@UEAAJPEAUIRegistrarBase@@@Z`
- size: `39`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180011010`

## pseudocode

```c
__int64 __fastcall ATL::CAtlModuleT<CPortableWorkspaceLauncherModule>::AddCommonRGSReplacements(__int64 a1, __int64 a2)
{
  return (*(__int64 (__fastcall **)(__int64, const wchar_t *, const wchar_t *))(*(_QWORD *)a2 + 24LL))(
           a2,
           L"APPID",
           L"{37B73D7B-A976-43AE-97E4-BD4977B241F2}");
}

```

## disassembly

```asm
0x180002a90  sub     rsp, 28h
0x180002a94  mov     rcx, rdx
0x180002a97  mov     rax, [rdx]
0x180002a9a  lea     r8, a37b73d7bA97643; "{37B73D7B-A976-43AE-97E4-BD4977B241F2}"
0x180002aa1  lea     rdx, aAppid; "APPID"
0x180002aa8  mov     rax, [rax+18h]
0x180002aac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002ab1  nop
0x180002ab2  add     rsp, 28h
0x180002ab6  retn
```
