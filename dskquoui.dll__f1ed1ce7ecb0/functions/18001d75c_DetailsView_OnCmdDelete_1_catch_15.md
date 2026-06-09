# _DetailsView::OnCmdDelete_::_1_::catch$15

- ea: `0x18001d75c`
- end: `0x18001d799`
- name: `_DetailsView::OnCmdDelete_::_1_::catch$15`
- size: `61`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x18001ce34`
- `0x18001f010`

## import_xrefs

- `USER32!EnableWindow` at `0x18001d789`
- `USER32!EnableWindow` at `0x18001d789`

## pseudocode

```c
void __fastcall __noreturn DetailsView::OnCmdDelete_::_1_::catch_15(__int64 a1, __int64 a2)
{
  (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(a2 + 48) + 16LL))(*(_QWORD *)(a2 + 48));
  EnableWindow(*(HWND *)(*(_QWORD *)(a2 + 528) + 96LL), 1);
  throw;
}

```

## disassembly

```asm
0x18001d75c  mov     [rsp+arg_8], rdx
0x18001d761  push    rbp
0x18001d762  sub     rsp, 30h
0x18001d766  mov     rbp, rdx
0x18001d769  mov     rcx, [rbp+30h]
0x18001d76d  mov     rax, [rcx]
0x18001d770  mov     rax, [rax+10h]
0x18001d774  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d779  mov     edx, 1; bEnable
0x18001d77e  mov     rcx, [rbp+210h]
0x18001d785  mov     rcx, [rcx+60h]; hWnd
0x18001d789  call    cs:__imp_EnableWindow
0x18001d78f  xor     edx, edx; pThrowInfo
0x18001d791  xor     ecx, ecx; pExceptionObject
0x18001d793  call    _CxxThrowException_0
```
