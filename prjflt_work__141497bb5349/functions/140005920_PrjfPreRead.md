# PrjfPreRead

- ea: `0x140005920`
- end: `0x14000595a`
- name: `PrjfPreRead`
- size: `58`
- prototype: `__int64 __fastcall(struct _FLT_CALLBACK_DATA *, __int64, __int64)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x140005920`
- `0x14002b640`

## pseudocode

```c
__int64 __fastcall PrjfPreRead(struct _FLT_CALLBACK_DATA *a1, __int64 a2, __int64 a3)
{
  int v4; // [rsp+20h] [rbp-28h]
  int v5; // [rsp+28h] [rbp-20h]

  if ( (a1->Iopb->IrpFlags & 2) != 0 )
    return 1;
  else
    return PrjfSynchronizeExpansionPreopWithReason(a1, v4, v5, 18, a3);
}

```

## disassembly

```asm
0x140005920  sub     rsp, 48h
0x140005924  mov     rax, [rcx+10h]
0x140005928  mov     r9d, [rax]
0x14000592b  test    r9b, 2
0x14000592f  jz      short loc_140005938
0x140005931  mov     eax, 1
0x140005936  jmp     short loc_140005954
0x140005938  mov     [rsp+48h+var_10], r8; __int64
0x14000593d  mov     r9d, 1
0x140005943  mov     [rsp+48h+var_18], 12h; int
0x14000594b  lea     r8d, [r9+1]
0x14000594f  call    PrjfSynchronizeExpansionPreopWithReason
0x140005954  add     rsp, 48h
0x140005958  retn
```
