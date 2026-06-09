# __GSHandlerCheckCommon

- ea: `0x1800129b4`
- end: `0x180012a17`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180012990`
- `0x180012a20`
- `0x180012a88`

## callees

- `0x1800129b4`
- `0x180012b40`

## pseudocode

```c
__int64 __fastcall _GSHandlerCheckCommon(__int64 a1, __int64 a2)
{
  __int64 v3; // rcx
  __int64 v4; // rax

  v3 = *(unsigned int *)(*(_QWORD *)(a2 + 16) + 8LL);
  v4 = *(_QWORD *)(a2 + 8);
  if ( (*(_BYTE *)(v3 + v4 + 3) & 0xF) != 0 )
    return a1 + (*(_BYTE *)(v3 + v4 + 3) & 0xF0);
  else
    return a1;
}

```

## disassembly

```asm
0x1800129b4  mov     r10, rcx
0x1800129b7  mov     r11, rdx
0x1800129ba  mov     ecx, [r8]
0x1800129bd  and     ecx, 0FFFFFFF8h
0x1800129c0  test    byte ptr [r8], 4
0x1800129c4  jz      short loc_1800129DB
0x1800129c6  mov     eax, [r8+8]
0x1800129ca  movsxd  r9, dword ptr [r8+4]
0x1800129ce  neg     eax
0x1800129d0  movsxd  rdx, eax
0x1800129d3  add     r9, r10
0x1800129d6  and     r9, rdx
0x1800129d9  jmp     short loc_1800129DE
0x1800129db  mov     r9, r10
0x1800129de  movsxd  rax, ecx
0x1800129e1  mov     rdx, [rax+r9]
0x1800129e5  mov     rax, [r11+10h]
0x1800129e9  mov     ecx, [rax+8]
0x1800129ec  mov     rax, [r11+8]
0x1800129f0  test    byte ptr [rcx+rax+3], 0Fh
0x1800129f5  jz      short loc_180012A09
0x1800129f7  movzx   eax, byte ptr [rcx+rax+3]
0x1800129fc  mov     ecx, 0FFFFFFF0h
0x180012a01  and     rax, rcx
0x180012a04  add     rax, r10
0x180012a07  jmp     short loc_180012A0C
0x180012a09  mov     rax, r10
0x180012a0c  xor     rdx, rax
0x180012a0f  mov     rcx, rdx; StackCookie
0x180012a12  jmp     __security_check_cookie
```
