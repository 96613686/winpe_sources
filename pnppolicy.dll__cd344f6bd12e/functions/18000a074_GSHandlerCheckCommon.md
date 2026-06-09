# __GSHandlerCheckCommon

- ea: `0x18000a074`
- end: `0x18000a0d7`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000a050`
- `0x18000a0e0`

## callees

- `0x18000a074`
- `0x18000a1a0`

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
0x18000a074  mov     r10, rcx
0x18000a077  mov     r11, rdx
0x18000a07a  mov     ecx, [r8]
0x18000a07d  and     ecx, 0FFFFFFF8h
0x18000a080  test    byte ptr [r8], 4
0x18000a084  jz      short loc_18000A09B
0x18000a086  mov     eax, [r8+8]
0x18000a08a  movsxd  r9, dword ptr [r8+4]
0x18000a08e  neg     eax
0x18000a090  movsxd  rdx, eax
0x18000a093  add     r9, r10
0x18000a096  and     r9, rdx
0x18000a099  jmp     short loc_18000A09E
0x18000a09b  mov     r9, r10
0x18000a09e  movsxd  rax, ecx
0x18000a0a1  mov     rdx, [rax+r9]
0x18000a0a5  mov     rax, [r11+10h]
0x18000a0a9  mov     ecx, [rax+8]
0x18000a0ac  mov     rax, [r11+8]
0x18000a0b0  test    byte ptr [rcx+rax+3], 0Fh
0x18000a0b5  jz      short loc_18000A0C9
0x18000a0b7  movzx   eax, byte ptr [rcx+rax+3]
0x18000a0bc  mov     ecx, 0FFFFFFF0h
0x18000a0c1  and     rax, rcx
0x18000a0c4  add     rax, r10
0x18000a0c7  jmp     short loc_18000A0CC
0x18000a0c9  mov     rax, r10
0x18000a0cc  xor     rdx, rax
0x18000a0cf  mov     rcx, rdx; StackCookie
0x18000a0d2  jmp     __security_check_cookie
```
