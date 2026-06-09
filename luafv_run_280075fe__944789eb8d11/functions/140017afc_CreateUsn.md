# CreateUsn

- ea: `0x140017afc`
- end: `0x140017b55`
- name: `CreateUsn`
- size: `89`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1400140b4`

## callees

- `0x140005f30`
- `0x14001ea60`

## pseudocode

```c
NTSTATUS __fastcall CreateUsn(__int64 a1)
{
  __int128 v2; // [rsp+40h] [rbp-28h] BYREF

  v2 = 0;
  return SynchronousFsControl(a1, 0, 0x900E7u, &v2, 0x10u, 0, 0);
}

```

## disassembly

```asm
0x140017afc  sub     rsp, 68h
0x140017b00  mov     rax, cs:__security_cookie
0x140017b07  xor     rax, rsp
0x140017b0a  mov     [rsp+68h+var_18], rax
0x140017b0f  xorps   xmm0, xmm0
0x140017b12  mov     [rsp+68h+var_38], 0
0x140017b1a  mov     [rsp+68h+var_40], 0
0x140017b23  lea     r9, [rsp+68h+var_28]
0x140017b28  xor     edx, edx
0x140017b2a  mov     [rsp+68h+var_48], 10h
0x140017b32  mov     r8d, 900E7h
0x140017b38  movups  [rsp+68h+var_28], xmm0
0x140017b3d  call    SynchronousFsControl
0x140017b42  mov     rcx, [rsp+68h+var_18]
0x140017b47  xor     rcx, rsp; StackCookie
0x140017b4a  call    __security_check_cookie
0x140017b4f  add     rsp, 68h
0x140017b53  retn
```
