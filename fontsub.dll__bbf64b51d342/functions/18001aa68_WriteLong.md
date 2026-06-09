# WriteLong

- ea: `0x18001aa68`
- end: `0x18001aad3`
- name: `WriteLong`
- size: `107`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x1800075f4`
- `0x18000c588`
- `0x18001a808`

## callees

- `0x18001a234`
- `0x18001aa68`

## pseudocode

```c
__int64 __fastcall WriteLong(_QWORD *a1, int a2, unsigned int a3)
{
  __int64 v3; // rbx
  unsigned __int8 v4; // di
  __int64 result; // rax

  v3 = a3;
  v4 = a2;
  result = CheckOutOffset(a1, a3);
  if ( !(_WORD)result )
  {
    *(_DWORD *)(v3 + *a1) = HIBYTE(a2) | ((BYTE2(a2) | ((BYTE1(a2) | (v4 << 8)) << 8)) << 8);
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x18001aa68  mov     [rsp+arg_0], rbx
0x18001aa6d  mov     [rsp+arg_10], rsi
0x18001aa72  mov     [rsp+arg_8], edx
0x18001aa76  push    rdi
0x18001aa77  sub     rsp, 20h
0x18001aa7b  mov     ebx, r8d
0x18001aa7e  mov     edi, edx
0x18001aa80  mov     edx, ebx
0x18001aa82  mov     r8d, 4
0x18001aa88  mov     rsi, rcx
0x18001aa8b  call    CheckOutOffset
0x18001aa90  xor     r8d, r8d
0x18001aa93  test    ax, ax
0x18001aa96  jnz     short loc_18001AAC3
0x18001aa98  movzx   eax, byte ptr [rsp+28h+arg_8+1]
0x18001aa9d  movzx   edx, dil
0x18001aaa1  shl     edx, 8
0x18001aaa4  or      edx, eax
0x18001aaa6  movzx   eax, byte ptr [rsp+28h+arg_8+2]
0x18001aaab  shl     edx, 8
0x18001aaae  or      edx, eax
0x18001aab0  movzx   eax, byte ptr [rsp+28h+arg_8+3]
0x18001aab5  shl     edx, 8
0x18001aab8  or      edx, eax
0x18001aaba  mov     rax, [rsi]
0x18001aabd  mov     [rbx+rax], edx
0x18001aac0  mov     eax, r8d
0x18001aac3  mov     rbx, [rsp+28h+arg_0]
0x18001aac8  mov     rsi, [rsp+28h+arg_10]
0x18001aacd  add     rsp, 20h
0x18001aad1  pop     rdi
0x18001aad2  retn
```
