# ConvertBinaryToString

- ea: `0x180004368`
- end: `0x180004404`
- name: `ConvertBinaryToString`
- size: `156`
- prototype: `_WORD *__fastcall(__int64, int)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x1800038d0`
- `0x180003ba0`
- `0x180003cd0`

## callees

- `0x180004368`

## import_xrefs

- `cmutil!CmMalloc` at `0x18000438d`
- `cmutil!CmMalloc` at `0x18000438d`

## pseudocode

```c
_WORD *__fastcall ConvertBinaryToString(__int64 a1, int a2)
{
  __int64 v4; // rdi
  _WORD *v5; // r9
  __int64 v6; // r10
  __int16 v7; // cx
  __int64 v8; // r8
  __int16 v9; // ax
  __int16 v10; // cx
  __int16 v11; // ax

  if ( !a1 || a2 <= 0 )
    return 0;
  v4 = 2 * a2;
  v5 = CmMalloc(2 * v4 + 4);
  if ( v5 )
  {
    v6 = 0;
    do
    {
      v7 = *(_BYTE *)(v6 + a1) >> 4;
      v8 = 2 * (int)v6;
      v9 = 48;
      if ( (unsigned __int8)v7 > 9u )
        v9 = 55;
      v5[v8] = v7 + v9;
      v10 = *(_BYTE *)(v6 + a1) & 0xF;
      v11 = 48;
      if ( (unsigned __int8)v10 > 9u )
        v11 = 55;
      v6 = (unsigned int)(v6 + 1);
      v5[v8 + 1] = v10 + v11;
    }
    while ( (int)v6 < a2 );
    v5[v4] = 0;
  }
  return v5;
}

```

## disassembly

```asm
0x180004368  push    rbx
0x18000436a  push    rbp
0x18000436b  push    rsi
0x18000436c  push    rdi
0x18000436d  sub     rsp, 28h
0x180004371  mov     ebx, edx
0x180004373  mov     rsi, rcx
0x180004376  test    rcx, rcx
0x180004379  jz      short loc_1800043F9
0x18000437b  test    edx, edx
0x18000437d  jle     short loc_1800043F9
0x18000437f  lea     eax, [rdx+rdx]
0x180004382  movsxd  rdi, eax
0x180004385  lea     rcx, ds:4[rdi*2]
0x18000438d  call    cs:__imp_?CmMalloc@@YAPEAX_K@Z; CmMalloc(unsigned __int64)
0x180004393  mov     r9, rax
0x180004396  test    rax, rax
0x180004399  jz      short loc_1800043F4
0x18000439b  xor     r10d, r10d
0x18000439e  lea     ebp, [r10+37h]
0x1800043a2  lea     r11d, [r10+30h]
0x1800043a6  mov     al, [r10+rsi]
0x1800043aa  shr     al, 4
0x1800043ad  movzx   ecx, al
0x1800043b0  lea     eax, [r10+r10]
0x1800043b4  movsxd  r8, eax
0x1800043b7  cmp     cl, 9
0x1800043ba  mov     eax, r11d
0x1800043bd  cmova   ax, bp
0x1800043c1  add     ax, cx
0x1800043c4  mov     [r9+r8*2], ax
0x1800043c9  mov     al, [r10+rsi]
0x1800043cd  and     al, 0Fh
0x1800043cf  movzx   ecx, al
0x1800043d2  mov     eax, r11d
0x1800043d5  cmp     cl, 9
0x1800043d8  cmova   ax, bp
0x1800043dc  inc     r10d
0x1800043df  add     ax, cx
0x1800043e2  mov     [r9+r8*2+2], ax
0x1800043e8  cmp     r10d, ebx
0x1800043eb  jl      short loc_1800043A6
0x1800043ed  xor     eax, eax
0x1800043ef  mov     [r9+rdi*2], ax
0x1800043f4  mov     rax, r9
0x1800043f7  jmp     short loc_1800043FB
0x1800043f9  xor     eax, eax
0x1800043fb  add     rsp, 28h
0x1800043ff  pop     rdi
0x180004400  pop     rsi
0x180004401  pop     rbp
0x180004402  pop     rbx
0x180004403  retn
```
