# HidpFdoCompletePendingS0IrpIfFastResumeDisabled

- ea: `0x18001c704`
- end: `0x18001c72d`
- name: `HidpFdoCompletePendingS0IrpIfFastResumeDisabled`
- size: `41`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18001c6e0`

## callees

- `0x180009bec`
- `0x18001c704`

## pseudocode

```c
void __fastcall HidpFdoCompletePendingS0IrpIfFastResumeDisabled(_QWORD *a1)
{
  int v1; // [rsp+30h] [rbp+8h] BYREF

  if ( *(_BYTE *)(a1[1] + 297LL) == 1 )
  {
    v1 = 0;
    HidpFdoCompleteSIrp(a1, &v1);
  }
}

```

## disassembly

```asm
0x18001c704  sub     rsp, 28h
0x18001c708  mov     rax, [rcx+8]
0x18001c70c  cmp     byte ptr [rax+129h], 1
0x18001c713  jnz     short loc_18001C727
0x18001c715  lea     rdx, [rsp+28h+arg_0]
0x18001c71a  mov     [rsp+28h+arg_0], 0
0x18001c722  call    HidpFdoCompleteSIrp
0x18001c727  add     rsp, 28h
0x18001c72b  retn
```
