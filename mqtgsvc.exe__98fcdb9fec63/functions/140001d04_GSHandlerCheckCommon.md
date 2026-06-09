# __GSHandlerCheckCommon

- ea: `0x140001d04`
- end: `0x140001d67`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140001ce0`
- `0x140001d70`
- `0x14001ce4c`

## callees

- `0x140001d04`
- `0x14001cf00`

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
0x140001d04  mov     r10, rcx
0x140001d07  mov     r11, rdx
0x140001d0a  mov     ecx, [r8]
0x140001d0d  and     ecx, 0FFFFFFF8h
0x140001d10  test    byte ptr [r8], 4
0x140001d14  jz      short loc_140001D2B
0x140001d16  mov     eax, [r8+8]
0x140001d1a  movsxd  r9, dword ptr [r8+4]
0x140001d1e  neg     eax
0x140001d20  movsxd  rdx, eax
0x140001d23  add     r9, r10
0x140001d26  and     r9, rdx
0x140001d29  jmp     short loc_140001D2E
0x140001d2b  mov     r9, r10
0x140001d2e  movsxd  rax, ecx
0x140001d31  mov     rdx, [rax+r9]
0x140001d35  mov     rax, [r11+10h]
0x140001d39  mov     ecx, [rax+8]
0x140001d3c  mov     rax, [r11+8]
0x140001d40  test    byte ptr [rcx+rax+3], 0Fh
0x140001d45  jz      short loc_140001D59
0x140001d47  movzx   eax, byte ptr [rcx+rax+3]
0x140001d4c  mov     ecx, 0FFFFFFF0h
0x140001d51  and     rax, rcx
0x140001d54  add     rax, r10
0x140001d57  jmp     short loc_140001D5C
0x140001d59  mov     rax, r10
0x140001d5c  xor     rdx, rax
0x140001d5f  mov     rcx, rdx; StackCookie
0x140001d62  jmp     __security_check_cookie
```
