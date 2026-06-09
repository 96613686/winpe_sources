# _std::_Packaged_state_void___cdecl(void)_::_Call_immediate_::_1_::catch$3

- ea: `0x1800446da`
- end: `0x18004472e`
- name: `_std::_Packaged_state_void___cdecl(void)_::_Call_immediate_::_1_::catch$3`
- size: `84`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180026da0`

## import_xrefs

- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x1800446f3`
- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x1800446f3`
- `msvcp_win!?__ExceptionPtrCurrentException@@YAXPEAX@Z` at `0x180044703`
- `msvcp_win!?__ExceptionPtrCurrentException@@YAXPEAX@Z` at `0x180044703`

## pseudocode

```c
__int64 __fastcall std::_Packaged_state_void___cdecl_void__::_Call_immediate_::_1_::catch_3(__int64 a1, __int64 a2)
{
  *(_OWORD *)(a2 + 40) = 0;
  __ExceptionPtrCreate((void *)(a2 + 40));
  __ExceptionPtrCurrentException((void *)(a2 + 40));
  std::_Associated_state<int>::_Set_exception(*(_BYTE **)(a2 + 32), (void *)(a2 + 40));
  return 0;
}

```

## disassembly

```asm
0x1800446da  mov     [rsp+arg_8], rdx
0x1800446df  push    rbp
0x1800446e0  sub     rsp, 20h
0x1800446e4  mov     rbp, rdx
0x1800446e7  xorps   xmm1, xmm1
0x1800446ea  movdqu  xmmword ptr [rbp+28h], xmm1
0x1800446ef  lea     rcx, [rbp+28h]
0x1800446f3  call    cs:__imp_?__ExceptionPtrCreate@@YAXPEAX@Z; __ExceptionPtrCreate(void *)
0x1800446fa  nop     dword ptr [rax+rax+00h]
0x1800446ff  lea     rcx, [rbp+28h]
0x180044703  call    cs:__imp_?__ExceptionPtrCurrentException@@YAXPEAX@Z; __ExceptionPtrCurrentException(void *)
0x18004470a  nop     dword ptr [rax+rax+00h]
0x18004470f  lea     rdx, [rbp+28h]
0x180044713  mov     rcx, [rbp+20h]
0x180044717  call    ?_Set_exception@?$_Associated_state@H@std@@QEAAXVexception_ptr@2@_N@Z; std::_Associated_state<int>::_Set_exception(std::exception_ptr,bool)
0x18004471c  nop
0x18004471d  mov     rax, 0
0x180044727  add     rsp, 20h
0x18004472b  pop     rbp
0x18004472c  retn
```
