# WriteWord

- ea: `0x18001aadc`
- end: `0x18001ab38`
- name: `WriteWord`
- size: `92`
- prototype: ``
- caller_count: `14`
- callee_count: `2`
- tags: ``

## callers

- `0x1800075f4`
- `0x1800087e8`
- `0x18000b888`
- `0x18000bdd4`
- `0x18000c588`
- `0x18000d108`
- `0x18000f928`
- `0x1800109fc`
- `0x180010fd4`
- `0x180011f48`
- `0x180013ee0`
- `0x180014dc0`
- `0x180016e9c`
- `0x18001a808`

## callees

- `0x18001a234`
- `0x18001aadc`

## pseudocode

```c
__int64 __fastcall WriteWord(_QWORD *a1, __int16 a2, unsigned int a3)
{
  __int64 v3; // rbx
  unsigned __int8 v5; // di
  __int64 result; // rax
  unsigned __int8 v7; // [rsp+39h] [rbp+11h]

  v7 = HIBYTE(a2);
  v3 = a3;
  v5 = a2;
  result = CheckOutOffset(a1, a3);
  if ( !(_WORD)result )
  {
    *(_WORD *)(v3 + *a1) = v7 | (v5 << 8);
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x18001aadc  mov     [rsp+arg_0], rbx
0x18001aae1  mov     [rsp+arg_10], rsi
0x18001aae6  mov     [rsp+arg_8], dx
0x18001aaeb  push    rdi
0x18001aaec  sub     rsp, 20h
0x18001aaf0  mov     ebx, r8d
0x18001aaf3  mov     rsi, rcx
0x18001aaf6  movzx   edi, dx
0x18001aaf9  mov     r8d, 2
0x18001aaff  mov     edx, ebx
0x18001ab01  call    CheckOutOffset
0x18001ab06  xor     r8d, r8d
0x18001ab09  test    ax, ax
0x18001ab0c  jnz     short loc_18001AB28
0x18001ab0e  movzx   eax, byte ptr [rsp+28h+arg_8+1]
0x18001ab13  movzx   edx, dil
0x18001ab17  shl     dx, 8
0x18001ab1b  or      dx, ax
0x18001ab1e  mov     rax, [rsi]
0x18001ab21  mov     [rbx+rax], dx
0x18001ab25  mov     eax, r8d
0x18001ab28  mov     rbx, [rsp+28h+arg_0]
0x18001ab2d  mov     rsi, [rsp+28h+arg_10]
0x18001ab32  add     rsp, 20h
0x18001ab36  pop     rdi
0x18001ab37  retn
```
