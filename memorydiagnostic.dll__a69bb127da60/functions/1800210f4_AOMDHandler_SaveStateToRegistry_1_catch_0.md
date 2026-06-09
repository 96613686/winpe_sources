# _AOMDHandler::SaveStateToRegistry_::_1_::catch$0

- ea: `0x1800210f4`
- end: `0x18002112a`
- name: `_AOMDHandler::SaveStateToRegistry_::_1_::catch$0`
- size: `54`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, const char *)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting`

## callees

- `0x180010994`

## pseudocode

```c
__int64 __fastcall AOMDHandler::SaveStateToRegistry_::_1_::catch_0(__int64 a1, __int64 a2, __int64 a3, const char *a4)
{
  *(_DWORD *)(a2 + 64) = wil::details::in1diag3::Return_CaughtException(
                           *(wil::details::in1diag3 **)(a2 + 56),
                           (void *)0x450,
                           (int)"base\\diagnosis\\memdiag\\onlinemd\\aomd.cpp",
                           a4);
  return 0;
}

```

## disassembly

```asm
0x1800210f4  mov     [rsp+arg_8], rdx
0x1800210f9  push    rbp
0x1800210fa  sub     rsp, 30h
0x1800210fe  mov     rbp, rdx
0x180021101  mov     rcx, [rbp+38h]; this
0x180021105  lea     r8, aBaseDiagnosisM_1; "base\\diagnosis\\memdiag\\onlinemd\\aom"...
0x18002110c  mov     edx, 450h; void *
0x180021111  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x180021116  mov     [rbp+40h], eax
0x180021119  mov     rax, 0
0x180021123  add     rsp, 30h
0x180021127  pop     rbp
0x180021128  retn
```
