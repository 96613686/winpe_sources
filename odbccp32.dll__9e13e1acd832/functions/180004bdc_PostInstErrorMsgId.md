# PostInstErrorMsgId

- ea: `0x180004bdc`
- end: `0x180004c0d`
- name: `PostInstErrorMsgId`
- size: `49`
- prototype: `__int64 __fastcall(int, int)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x180006db8`
- `0x180007c0c`
- `0x1800085c8`
- `0x180013fa8`

## callees

- `0x180004bdc`

## pseudocode

```c
__int64 __fastcall PostInstErrorMsgId(int a1, int a2)
{
  __int64 result; // rax

  if ( (unsigned __int16)word_18001CA40 < 8u )
  {
    result = 2LL * (unsigned __int16)word_18001CA40++;
    LODWORD(qword_18001C9C0[result]) = a1;
    HIDWORD(qword_18001C9C0[result]) = a2;
  }
  return result;
}

```

## disassembly

```asm
0x180004bdc  movzx   r8d, cs:word_18001CA40
0x180004be4  cmp     r8d, 8
0x180004be8  jnb     short locret_180004C0C
0x180004bea  mov     eax, r8d
0x180004bed  lea     r9, qword_18001C9C0
0x180004bf4  add     rax, rax
0x180004bf7  inc     r8w
0x180004bfb  mov     cs:word_18001CA40, r8w
0x180004c03  mov     [r9+rax*8], ecx
0x180004c07  mov     [r9+rax*8+4], edx
0x180004c0c  retn
```
