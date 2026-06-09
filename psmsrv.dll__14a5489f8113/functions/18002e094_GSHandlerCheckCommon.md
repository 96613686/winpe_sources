# __GSHandlerCheckCommon

- ea: `0x18002e094`
- end: `0x18002e0f7`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18002e070`

## callees

- `0x18001b7e0`
- `0x18002e094`

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
0x18002e094  mov     r10, rcx
0x18002e097  mov     r11, rdx
0x18002e09a  mov     ecx, [r8]
0x18002e09d  and     ecx, 0FFFFFFF8h
0x18002e0a0  test    byte ptr [r8], 4
0x18002e0a4  jz      short loc_18002E0BB
0x18002e0a6  mov     eax, [r8+8]
0x18002e0aa  movsxd  r9, dword ptr [r8+4]
0x18002e0ae  neg     eax
0x18002e0b0  movsxd  rdx, eax
0x18002e0b3  add     r9, r10
0x18002e0b6  and     r9, rdx
0x18002e0b9  jmp     short loc_18002E0BE
0x18002e0bb  mov     r9, r10
0x18002e0be  movsxd  rax, ecx
0x18002e0c1  mov     rdx, [rax+r9]
0x18002e0c5  mov     rax, [r11+10h]
0x18002e0c9  mov     ecx, [rax+8]
0x18002e0cc  mov     rax, [r11+8]
0x18002e0d0  test    byte ptr [rcx+rax+3], 0Fh
0x18002e0d5  jz      short loc_18002E0E9
0x18002e0d7  movzx   eax, byte ptr [rcx+rax+3]
0x18002e0dc  mov     ecx, 0FFFFFFF0h
0x18002e0e1  and     rax, rcx
0x18002e0e4  add     rax, r10
0x18002e0e7  jmp     short loc_18002E0EC
0x18002e0e9  mov     rax, r10
0x18002e0ec  xor     rdx, rax
0x18002e0ef  mov     rcx, rdx; StackCookie
0x18002e0f2  jmp     __security_check_cookie
```
