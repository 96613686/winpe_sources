# __GSHandlerCheckCommon

- ea: `0x18001cfc4`
- end: `0x18001d027`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18001cfa0`

## callees

- `0x180001aa0`
- `0x18001cfc4`

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
0x18001cfc4  mov     r10, rcx
0x18001cfc7  mov     r11, rdx
0x18001cfca  mov     ecx, [r8]
0x18001cfcd  and     ecx, 0FFFFFFF8h
0x18001cfd0  test    byte ptr [r8], 4
0x18001cfd4  jz      short loc_18001CFEB
0x18001cfd6  mov     eax, [r8+8]
0x18001cfda  movsxd  r9, dword ptr [r8+4]
0x18001cfde  neg     eax
0x18001cfe0  movsxd  rdx, eax
0x18001cfe3  add     r9, r10
0x18001cfe6  and     r9, rdx
0x18001cfe9  jmp     short loc_18001CFEE
0x18001cfeb  mov     r9, r10
0x18001cfee  movsxd  rax, ecx
0x18001cff1  mov     rdx, [rax+r9]
0x18001cff5  mov     rax, [r11+10h]
0x18001cff9  mov     ecx, [rax+8]
0x18001cffc  mov     rax, [r11+8]
0x18001d000  test    byte ptr [rcx+rax+3], 0Fh
0x18001d005  jz      short loc_18001D019
0x18001d007  movzx   eax, byte ptr [rcx+rax+3]
0x18001d00c  mov     ecx, 0FFFFFFF0h
0x18001d011  and     rax, rcx
0x18001d014  add     rax, r10
0x18001d017  jmp     short loc_18001D01C
0x18001d019  mov     rax, r10
0x18001d01c  xor     rdx, rax
0x18001d01f  mov     rcx, rdx; StackCookie
0x18001d022  jmp     __security_check_cookie
```
