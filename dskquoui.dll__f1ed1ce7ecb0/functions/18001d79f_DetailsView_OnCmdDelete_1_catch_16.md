# _DetailsView::OnCmdDelete_::_1_::catch$16

- ea: `0x18001d79f`
- end: `0x18001d7c6`
- name: `_DetailsView::OnCmdDelete_::_1_::catch$16`
- size: `39`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x18001ce34`
- `0x18001f010`

## pseudocode

```c
void __fastcall __noreturn DetailsView::OnCmdDelete_::_1_::catch_16(__int64 a1, __int64 a2)
{
  (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(a2 + 48) + 16LL))(*(_QWORD *)(a2 + 48));
  throw;
}

```

## disassembly

```asm
0x18001d79f  mov     [rsp+arg_8], rdx
0x18001d7a4  push    rbp
0x18001d7a5  sub     rsp, 30h
0x18001d7a9  mov     rbp, rdx
0x18001d7ac  mov     rcx, [rbp+30h]
0x18001d7b0  mov     rax, [rcx]
0x18001d7b3  mov     rax, [rax+10h]
0x18001d7b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d7bc  xor     edx, edx; pThrowInfo
0x18001d7be  xor     ecx, ecx; pExceptionObject
0x18001d7c0  call    _CxxThrowException_0
```
