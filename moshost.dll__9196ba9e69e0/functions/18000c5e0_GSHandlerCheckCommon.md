# __GSHandlerCheckCommon

- ea: `0x18000c5e0`
- end: `0x18000c643`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000c5bc`
- `0x18000c64c`

## callees

- `0x180001d00`
- `0x18000c5e0`

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
0x18000c5e0  mov     r10, rcx
0x18000c5e3  mov     r11, rdx
0x18000c5e6  mov     ecx, [r8]
0x18000c5e9  and     ecx, 0FFFFFFF8h
0x18000c5ec  test    byte ptr [r8], 4
0x18000c5f0  jz      short loc_18000C607
0x18000c5f2  mov     eax, [r8+8]
0x18000c5f6  movsxd  r9, dword ptr [r8+4]
0x18000c5fa  neg     eax
0x18000c5fc  movsxd  rdx, eax
0x18000c5ff  add     r9, r10
0x18000c602  and     r9, rdx
0x18000c605  jmp     short loc_18000C60A
0x18000c607  mov     r9, r10
0x18000c60a  movsxd  rax, ecx
0x18000c60d  mov     rdx, [rax+r9]
0x18000c611  mov     rax, [r11+10h]
0x18000c615  mov     ecx, [rax+8]
0x18000c618  mov     rax, [r11+8]
0x18000c61c  test    byte ptr [rcx+rax+3], 0Fh
0x18000c621  jz      short loc_18000C635
0x18000c623  movzx   eax, byte ptr [rcx+rax+3]
0x18000c628  mov     ecx, 0FFFFFFF0h
0x18000c62d  and     rax, rcx
0x18000c630  add     rax, r10
0x18000c633  jmp     short loc_18000C638
0x18000c635  mov     rax, r10
0x18000c638  xor     rdx, rax
0x18000c63b  mov     rcx, rdx; StackCookie
0x18000c63e  jmp     __security_check_cookie
```
