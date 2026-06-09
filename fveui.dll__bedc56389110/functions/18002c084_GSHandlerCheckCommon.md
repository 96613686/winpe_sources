# __GSHandlerCheckCommon

- ea: `0x18002c084`
- end: `0x18002c0e7`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18002c060`
- `0x18002c0f0`
- `0x18002c158`

## callees

- `0x180001bb0`
- `0x18002c084`

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
0x18002c084  mov     r10, rcx
0x18002c087  mov     r11, rdx
0x18002c08a  mov     ecx, [r8]
0x18002c08d  and     ecx, 0FFFFFFF8h
0x18002c090  test    byte ptr [r8], 4
0x18002c094  jz      short loc_18002C0AB
0x18002c096  mov     eax, [r8+8]
0x18002c09a  movsxd  r9, dword ptr [r8+4]
0x18002c09e  neg     eax
0x18002c0a0  movsxd  rdx, eax
0x18002c0a3  add     r9, r10
0x18002c0a6  and     r9, rdx
0x18002c0a9  jmp     short loc_18002C0AE
0x18002c0ab  mov     r9, r10
0x18002c0ae  movsxd  rax, ecx
0x18002c0b1  mov     rdx, [rax+r9]
0x18002c0b5  mov     rax, [r11+10h]
0x18002c0b9  mov     ecx, [rax+8]
0x18002c0bc  mov     rax, [r11+8]
0x18002c0c0  test    byte ptr [rcx+rax+3], 0Fh
0x18002c0c5  jz      short loc_18002C0D9
0x18002c0c7  movzx   eax, byte ptr [rcx+rax+3]
0x18002c0cc  mov     ecx, 0FFFFFFF0h
0x18002c0d1  and     rax, rcx
0x18002c0d4  add     rax, r10
0x18002c0d7  jmp     short loc_18002C0DC
0x18002c0d9  mov     rax, r10
0x18002c0dc  xor     rdx, rax
0x18002c0df  mov     rcx, rdx; StackCookie
0x18002c0e2  jmp     __security_check_cookie
```
