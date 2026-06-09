# __GSHandlerCheckCommon

- ea: `0x180002de0`
- end: `0x180002e43`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180002dbc`
- `0x180015100`
- `0x180015168`

## callees

- `0x180001770`
- `0x180002de0`

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
0x180002de0  mov     r10, rcx
0x180002de3  mov     r11, rdx
0x180002de6  mov     ecx, [r8]
0x180002de9  and     ecx, 0FFFFFFF8h
0x180002dec  test    byte ptr [r8], 4
0x180002df0  jz      short loc_180002E07
0x180002df2  mov     eax, [r8+8]
0x180002df6  movsxd  r9, dword ptr [r8+4]
0x180002dfa  neg     eax
0x180002dfc  movsxd  rdx, eax
0x180002dff  add     r9, r10
0x180002e02  and     r9, rdx
0x180002e05  jmp     short loc_180002E0A
0x180002e07  mov     r9, r10
0x180002e0a  movsxd  rax, ecx
0x180002e0d  mov     rdx, [rax+r9]
0x180002e11  mov     rax, [r11+10h]
0x180002e15  mov     ecx, [rax+8]
0x180002e18  mov     rax, [r11+8]
0x180002e1c  test    byte ptr [rcx+rax+3], 0Fh
0x180002e21  jz      short loc_180002E35
0x180002e23  movzx   eax, byte ptr [rcx+rax+3]
0x180002e28  mov     ecx, 0FFFFFFF0h
0x180002e2d  and     rax, rcx
0x180002e30  add     rax, r10
0x180002e33  jmp     short loc_180002E38
0x180002e35  mov     rax, r10
0x180002e38  xor     rdx, rax
0x180002e3b  mov     rcx, rdx; StackCookie
0x180002e3e  jmp     __security_check_cookie
```
