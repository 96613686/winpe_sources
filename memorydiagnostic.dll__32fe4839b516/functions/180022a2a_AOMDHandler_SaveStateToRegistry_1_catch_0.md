# _AOMDHandler::SaveStateToRegistry_::_1_::catch$0

- ea: `0x180022a2a`
- end: `0x180022a60`
- name: `_AOMDHandler::SaveStateToRegistry_::_1_::catch$0`
- size: `54`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting`

## callees

- `0x180011364`

## pseudocode

```c
__int64 __fastcall AOMDHandler::SaveStateToRegistry_::_1_::catch_0(__int64 a1, __int64 a2, __int64 a3, const char *a4)
{
  *(_DWORD *)(a2 + 64) = wil::details::in1diag3::Return_CaughtException(
                           *(wil::details::in1diag3 **)(a2 + 56),
                           (void *)0x4AF,
                           (unsigned int)"base\\diagnosis\\memdiag\\onlinemd\\aomd.cpp",
                           a4);
  return 0;
}

```

## disassembly

```asm
0x180022a2a  mov     [rsp+arg_8], rdx
0x180022a2f  push    rbp
0x180022a30  sub     rsp, 30h
0x180022a34  mov     rbp, rdx
0x180022a37  mov     rcx, [rbp+38h]; this
0x180022a3b  lea     r8, aBaseDiagnosisM_1; "base\\diagnosis\\memdiag\\onlinemd\\aom"...
0x180022a42  mov     edx, 4AFh; void *
0x180022a47  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x180022a4c  mov     [rbp+40h], eax
0x180022a4f  mov     rax, 0
0x180022a59  add     rsp, 30h
0x180022a5d  pop     rbp
0x180022a5e  retn
```
