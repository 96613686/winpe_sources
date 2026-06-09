# CreateUsn

- ea: `0x140017aac`
- end: `0x140017b05`
- name: `CreateUsn`
- size: `89`
- prototype: `__int64 __fastcall(int)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1400140b4`

## callees

- `0x140005bb0`
- `0x14001ea10`

## pseudocode

```c
__int64 __fastcall CreateUsn(int a1)
{
  __int128 v2; // [rsp+40h] [rbp-28h] BYREF

  v2 = 0;
  return SynchronousFsControl(a1, 0, 590055, (unsigned int)&v2, 16, 0, 0);
}

```

## disassembly

```asm
0x140017aac  sub     rsp, 68h
0x140017ab0  mov     rax, cs:__security_cookie
0x140017ab7  xor     rax, rsp
0x140017aba  mov     [rsp+68h+var_18], rax
0x140017abf  xorps   xmm0, xmm0
0x140017ac2  mov     [rsp+68h+var_38], 0
0x140017aca  mov     [rsp+68h+var_40], 0
0x140017ad3  lea     r9, [rsp+68h+var_28]
0x140017ad8  xor     edx, edx
0x140017ada  mov     [rsp+68h+var_48], 10h
0x140017ae2  mov     r8d, 900E7h
0x140017ae8  movups  [rsp+68h+var_28], xmm0
0x140017aed  call    SynchronousFsControl
0x140017af2  mov     rcx, [rsp+68h+var_18]
0x140017af7  xor     rcx, rsp; StackCookie
0x140017afa  call    __security_check_cookie
0x140017aff  add     rsp, 68h
0x140017b03  retn
```
