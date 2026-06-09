# __GSHandlerCheckCommon

- ea: `0x140007794`
- end: `0x1400077f7`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140007770`
- `0x140007800`

## callees

- `0x140001470`
- `0x140007794`

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
0x140007794  mov     r10, rcx
0x140007797  mov     r11, rdx
0x14000779a  mov     ecx, [r8]
0x14000779d  and     ecx, 0FFFFFFF8h
0x1400077a0  test    byte ptr [r8], 4
0x1400077a4  jz      short loc_1400077BB
0x1400077a6  mov     eax, [r8+8]
0x1400077aa  movsxd  r9, dword ptr [r8+4]
0x1400077ae  neg     eax
0x1400077b0  movsxd  rdx, eax
0x1400077b3  add     r9, r10
0x1400077b6  and     r9, rdx
0x1400077b9  jmp     short loc_1400077BE
0x1400077bb  mov     r9, r10
0x1400077be  movsxd  rax, ecx
0x1400077c1  mov     rdx, [rax+r9]
0x1400077c5  mov     rax, [r11+10h]
0x1400077c9  mov     ecx, [rax+8]
0x1400077cc  mov     rax, [r11+8]
0x1400077d0  test    byte ptr [rcx+rax+3], 0Fh
0x1400077d5  jz      short loc_1400077E9
0x1400077d7  movzx   eax, byte ptr [rcx+rax+3]
0x1400077dc  mov     ecx, 0FFFFFFF0h
0x1400077e1  and     rax, rcx
0x1400077e4  add     rax, r10
0x1400077e7  jmp     short loc_1400077EC
0x1400077e9  mov     rax, r10
0x1400077ec  xor     rdx, rax
0x1400077ef  mov     rcx, rdx; StackCookie
0x1400077f2  jmp     __security_check_cookie
```
