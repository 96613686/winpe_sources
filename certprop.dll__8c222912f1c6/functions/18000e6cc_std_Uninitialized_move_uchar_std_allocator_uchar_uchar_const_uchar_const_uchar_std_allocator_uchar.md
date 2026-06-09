# std::_Uninitialized_move<uchar *,std::allocator<uchar>>(uchar * const,uchar * const,uchar *,std::allocator<uchar> &)

- ea: `0x18000e6cc`
- end: `0x18000e700`
- name: `??$_Uninitialized_move@PEAEV?$allocator@E@std@@@std@@YAPEAEQEAE0PEAEAEAV?$allocator@E@0@@Z`
- size: `52`
- prototype: `char *__fastcall(void *, __int64, char *)`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x1800085f4`
- `0x180010c58`
- `0x180015640`
- `0x18001df84`
- `0x180024fe6`
- `0x18002505a`

## callees

- `0x18000e708`

## pseudocode

```c
char *__fastcall std::_Uninitialized_move<unsigned char *>(void *a1, __int64 a2, char *a3)
{
  std::_Copy_memmove<unsigned char *,unsigned char *>(a1, a2, a3);
  return &a3[a2 - (_QWORD)a1];
}

```

## disassembly

```asm
0x18000e6cc  mov     [rsp+arg_0], rbx
0x18000e6d1  mov     [rsp+arg_8], rsi
0x18000e6d6  push    rdi
0x18000e6d7  sub     rsp, 20h
0x18000e6db  mov     rdi, r8
0x18000e6de  mov     rsi, rdx
0x18000e6e1  mov     rbx, rcx
0x18000e6e4  call    ??$_Copy_memmove@PEAEPEAE@std@@YAPEAEPEAE00@Z; std::_Copy_memmove<uchar *,uchar *>(uchar *,uchar *,uchar *)
0x18000e6e9  sub     rsi, rbx
0x18000e6ec  mov     rbx, [rsp+28h+arg_0]
0x18000e6f1  lea     rax, [rdi+rsi]
0x18000e6f5  mov     rsi, [rsp+28h+arg_8]
0x18000e6fa  add     rsp, 20h
0x18000e6fe  pop     rdi
0x18000e6ff  retn
```
