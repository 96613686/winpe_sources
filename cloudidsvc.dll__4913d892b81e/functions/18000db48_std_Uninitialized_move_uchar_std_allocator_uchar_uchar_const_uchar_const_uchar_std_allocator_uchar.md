# std::_Uninitialized_move<uchar *,std::allocator<uchar>>(uchar * const,uchar * const,uchar *,std::allocator<uchar> &)

- ea: `0x18000db48`
- end: `0x18000db7c`
- name: `??$_Uninitialized_move@PEAEV?$allocator@E@std@@@std@@YAPEAEQEAE0PEAEAEAV?$allocator@E@0@@Z`
- size: `52`
- prototype: `char *__fastcall(void *, __int64, char *)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x18000d2c0`
- `0x18000d824`
- `0x180010f6c`
- `0x180010fe0`

## callees

- `0x18000d1e0`

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
0x18000db48  mov     [rsp+arg_0], rbx
0x18000db4d  mov     [rsp+arg_8], rsi
0x18000db52  push    rdi
0x18000db53  sub     rsp, 20h
0x18000db57  mov     rdi, r8
0x18000db5a  mov     rsi, rdx
0x18000db5d  mov     rbx, rcx
0x18000db60  call    ??$_Copy_memmove@PEAEPEAE@std@@YAPEAEPEAE00@Z; std::_Copy_memmove<uchar *,uchar *>(uchar *,uchar *,uchar *)
0x18000db65  sub     rsi, rbx
0x18000db68  mov     rbx, [rsp+28h+arg_0]
0x18000db6d  lea     rax, [rdi+rsi]
0x18000db71  mov     rsi, [rsp+28h+arg_8]
0x18000db76  add     rsp, 20h
0x18000db7a  pop     rdi
0x18000db7b  retn
```
