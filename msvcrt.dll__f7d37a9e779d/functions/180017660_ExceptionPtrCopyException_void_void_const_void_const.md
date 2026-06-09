# __ExceptionPtrCopyException(void *,void const *,void const *)

- ea: `0x180017660`
- end: `0x1800176d3`
- name: `?__ExceptionPtrCopyException@@YAXPEAXPEBX1@Z`
- size: `115`
- prototype: `void __fastcall(void *, const void *, const void *)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x180017660`
- `0x180017c78`
- `0x180017fec`
- `0x18007d020`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall __ExceptionPtrCopyException(void *a1, _QWORD *a2, ThrowInfo *a3)
{
  __int64 v4; // rax
  volatile signed __int32 *v5; // rbx
  _BYTE v6[8]; // [rsp+28h] [rbp-20h] BYREF
  volatile signed __int32 *v7; // [rsp+30h] [rbp-18h]

  v4 = __ExceptionPtr::_CopyException((__int64)v6, a2, a3, 1);
  std::shared_ptr<__ExceptionPtr>::operator=(a1, v4);
  v5 = v7;
  if ( v7 && _InterlockedExchangeAdd(v7 + 2, 0xFFFFFFFF) == 1 )
  {
    (**(void (__fastcall ***)(volatile signed __int32 *))v5)(v5);
    if ( _InterlockedExchangeAdd(v5 + 3, 0xFFFFFFFF) == 1 )
      (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v5 + 8LL))(v5);
  }
}

```

## disassembly

```asm
0x180017660  push    rbx
0x180017662  sub     rsp, 40h
0x180017666  mov     [rsp+48h+var_28], 0FFFFFFFFFFFFFFFEh
0x18001766f  mov     rbx, rcx
0x180017672  mov     r9b, 1
0x180017675  lea     rcx, [rsp+48h+var_20]
0x18001767a  call    ?_CopyException@__ExceptionPtr@@SA?AV?$shared_ptr@V__ExceptionPtr@@@std@@PEBXPEBU_s_ThrowInfo@@_N@Z; __ExceptionPtr::_CopyException(void const *,_s_ThrowInfo const *,bool)
0x18001767f  mov     rdx, rax
0x180017682  mov     rcx, rbx
0x180017685  call    ??4?$shared_ptr@V__ExceptionPtr@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<__ExceptionPtr>::operator=(std::shared_ptr<__ExceptionPtr> &&)
0x18001768a  nop
0x18001768b  mov     rbx, [rsp+48h+var_18]
0x180017690  test    rbx, rbx
0x180017693  jz      short loc_1800176CD
0x180017695  or      eax, 0FFFFFFFFh
0x180017698  lock xadd [rbx+8], eax
0x18001769d  cmp     eax, 1
0x1800176a0  jnz     short loc_1800176CD
0x1800176a2  mov     rax, [rbx]
0x1800176a5  mov     rcx, rbx
0x1800176a8  mov     rax, [rax]
0x1800176ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800176b0  or      eax, 0FFFFFFFFh
0x1800176b3  lock xadd [rbx+0Ch], eax
0x1800176b8  cmp     eax, 1
0x1800176bb  jnz     short loc_1800176CD
0x1800176bd  mov     rax, [rbx]
0x1800176c0  mov     rcx, rbx
0x1800176c3  mov     rax, [rax+8]
0x1800176c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800176cc  nop
0x1800176cd  add     rsp, 40h
0x1800176d1  pop     rbx
0x1800176d2  retn
```
