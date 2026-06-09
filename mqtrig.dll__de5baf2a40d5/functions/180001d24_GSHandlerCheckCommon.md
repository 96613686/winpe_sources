# __GSHandlerCheckCommon

- ea: `0x180001d24`
- end: `0x180001d87`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180001d00`
- `0x180001d90`
- `0x18001e2c0`

## callees

- `0x180001d24`
- `0x18001e380`

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
0x180001d24  mov     r10, rcx
0x180001d27  mov     r11, rdx
0x180001d2a  mov     ecx, [r8]
0x180001d2d  and     ecx, 0FFFFFFF8h
0x180001d30  test    byte ptr [r8], 4
0x180001d34  jz      short loc_180001D4B
0x180001d36  mov     eax, [r8+8]
0x180001d3a  movsxd  r9, dword ptr [r8+4]
0x180001d3e  neg     eax
0x180001d40  movsxd  rdx, eax
0x180001d43  add     r9, r10
0x180001d46  and     r9, rdx
0x180001d49  jmp     short loc_180001D4E
0x180001d4b  mov     r9, r10
0x180001d4e  movsxd  rax, ecx
0x180001d51  mov     rdx, [rax+r9]
0x180001d55  mov     rax, [r11+10h]
0x180001d59  mov     ecx, [rax+8]
0x180001d5c  mov     rax, [r11+8]
0x180001d60  test    byte ptr [rcx+rax+3], 0Fh
0x180001d65  jz      short loc_180001D79
0x180001d67  movzx   eax, byte ptr [rcx+rax+3]
0x180001d6c  mov     ecx, 0FFFFFFF0h
0x180001d71  and     rax, rcx
0x180001d74  add     rax, r10
0x180001d77  jmp     short loc_180001D7C
0x180001d79  mov     rax, r10
0x180001d7c  xor     rdx, rax
0x180001d7f  mov     rcx, rdx; StackCookie
0x180001d82  jmp     __security_check_cookie
```
