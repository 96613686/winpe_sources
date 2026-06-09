# __GSHandlerCheckCommon

- ea: `0x140013dc0`
- end: `0x140013e1b`
- name: `__GSHandlerCheckCommon`
- size: `91`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140013da0`
- `0x140013e1c`

## callees

- `0x140013200`
- `0x140013dc0`

## pseudocode

```c
__int64 __fastcall _GSHandlerCheckCommon(__int64 a1, __int64 a2)
{
  __int64 v2; // rcx
  __int64 result; // rax

  v2 = *(unsigned int *)(*(_QWORD *)(a2 + 16) + 8LL);
  result = *(_QWORD *)(a2 + 8);
  if ( (*(_BYTE *)(v2 + result + 3) & 0xF) != 0 )
    return *(_BYTE *)(v2 + result + 3) & 0xF0;
  return result;
}

```

## disassembly

```asm
0x140013dc0  push    rbx
0x140013dc2  mov     r11d, [r8]
0x140013dc5  mov     rbx, rdx
0x140013dc8  and     r11d, 0FFFFFFF8h
0x140013dcc  mov     r9, rcx
0x140013dcf  test    byte ptr [r8], 4
0x140013dd3  mov     r10, rcx
0x140013dd6  jz      short loc_140013DEB
0x140013dd8  mov     eax, [r8+8]
0x140013ddc  movsxd  r10, dword ptr [r8+4]
0x140013de0  neg     eax
0x140013de2  add     r10, rcx
0x140013de5  movsxd  rcx, eax
0x140013de8  and     r10, rcx
0x140013deb  movsxd  rax, r11d
0x140013dee  mov     rdx, [rax+r10]
0x140013df2  mov     rax, [rbx+10h]
0x140013df6  mov     ecx, [rax+8]
0x140013df9  mov     rax, [rbx+8]
0x140013dfd  test    byte ptr [rcx+rax+3], 0Fh
0x140013e02  jz      short loc_140013E0F
0x140013e04  movzx   eax, byte ptr [rcx+rax+3]
0x140013e09  and     eax, 0FFFFFFF0h
0x140013e0c  add     r9, rax
0x140013e0f  xor     r9, rdx
0x140013e12  mov     rcx, r9; StackCookie
0x140013e15  pop     rbx
0x140013e16  jmp     __security_check_cookie
```
