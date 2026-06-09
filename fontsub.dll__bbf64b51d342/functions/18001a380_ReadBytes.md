# ReadBytes

- ea: `0x18001a380`
- end: `0x18001a3b4`
- name: `ReadBytes`
- size: `52`
- prototype: ``
- caller_count: `5`
- callee_count: `3`
- tags: ``

## callers

- `0x18000ef20`
- `0x1800109fc`
- `0x180012640`
- `0x1800198f8`
- `0x18001a3bc`

## callees

- `0x18001a208`
- `0x18001a380`
- `0x18001abe2`

## pseudocode

```c
__int64 __fastcall ReadBytes(__int64 a1, __int64 a2, unsigned int a3, __int64 a4)
{
  __int64 result; // rax
  _QWORD *v5; // rcx
  size_t v6; // r8
  unsigned int v7; // r10d
  void *v8; // r11

  result = CheckInOffset(a1, a3, a4);
  if ( !(_WORD)result )
  {
    memcpy_0(v8, (const void *)(*v5 + v7), v6);
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x18001a380  push    rbx
0x18001a382  sub     rsp, 20h
0x18001a386  mov     r10d, r8d
0x18001a389  mov     r11, rdx
0x18001a38c  mov     edx, r10d
0x18001a38f  mov     r8, r9
0x18001a392  call    CheckInOffset
0x18001a397  xor     ebx, ebx
0x18001a399  test    ax, ax
0x18001a39c  jnz     short loc_18001A3AE
0x18001a39e  mov     edx, r10d
0x18001a3a1  add     rdx, [rcx]; Src
0x18001a3a4  mov     rcx, r11; void *
0x18001a3a7  call    memcpy_0
0x18001a3ac  mov     eax, ebx
0x18001a3ae  add     rsp, 20h
0x18001a3b2  pop     rbx
0x18001a3b3  retn
```
