# WriteByte

- ea: `0x18001a76c`
- end: `0x18001a7b1`
- name: `WriteByte`
- size: `69`
- prototype: ``
- caller_count: `15`
- callee_count: `2`
- tags: ``

## callers

- `0x180009010`
- `0x18000acf4`
- `0x18000b040`
- `0x18000b5d0`
- `0x18000b760`
- `0x18000c350`
- `0x18000c708`
- `0x18000fd08`
- `0x180010284`
- `0x1800115ac`
- `0x1800118bc`
- `0x180013ee0`
- `0x18001a060`
- `0x18001a0c0`
- `0x18001a808`

## callees

- `0x18001a234`
- `0x18001a76c`

## pseudocode

```c
__int64 __fastcall WriteByte(_QWORD *a1, char a2, unsigned int a3)
{
  __int64 v3; // rbx
  __int64 result; // rax

  v3 = a3;
  result = CheckOutOffset(a1, a3);
  if ( !(_WORD)result )
  {
    *(_BYTE *)(v3 + *a1) = a2;
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x18001a76c  mov     [rsp+arg_0], rbx
0x18001a771  mov     [rsp+arg_8], rsi
0x18001a776  push    rdi
0x18001a777  sub     rsp, 20h
0x18001a77b  mov     ebx, r8d
0x18001a77e  mov     sil, dl
0x18001a781  mov     edx, ebx
0x18001a783  mov     r8d, 1
0x18001a789  mov     rdi, rcx
0x18001a78c  call    CheckOutOffset
0x18001a791  xor     edx, edx
0x18001a793  test    ax, ax
0x18001a796  jnz     short loc_18001A7A1
0x18001a798  mov     rax, [rdi]
0x18001a79b  mov     [rbx+rax], sil
0x18001a79f  mov     eax, edx
0x18001a7a1  mov     rbx, [rsp+28h+arg_0]
0x18001a7a6  mov     rsi, [rsp+28h+arg_8]
0x18001a7ab  add     rsp, 20h
0x18001a7af  pop     rdi
0x18001a7b0  retn
```
