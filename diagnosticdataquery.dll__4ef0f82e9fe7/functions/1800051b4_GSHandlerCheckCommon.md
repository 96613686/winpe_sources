# __GSHandlerCheckCommon

- ea: `0x1800051b4`
- end: `0x180005217`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180005190`
- `0x1800052f4`
- `0x18000b090`

## callees

- `0x180001500`
- `0x1800051b4`

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
0x1800051b4  mov     r10, rcx
0x1800051b7  mov     r11, rdx
0x1800051ba  mov     ecx, [r8]
0x1800051bd  and     ecx, 0FFFFFFF8h
0x1800051c0  test    byte ptr [r8], 4
0x1800051c4  jz      short loc_1800051DB
0x1800051c6  mov     eax, [r8+8]
0x1800051ca  movsxd  r9, dword ptr [r8+4]
0x1800051ce  neg     eax
0x1800051d0  movsxd  rdx, eax
0x1800051d3  add     r9, r10
0x1800051d6  and     r9, rdx
0x1800051d9  jmp     short loc_1800051DE
0x1800051db  mov     r9, r10
0x1800051de  movsxd  rax, ecx
0x1800051e1  mov     rdx, [rax+r9]
0x1800051e5  mov     rax, [r11+10h]
0x1800051e9  mov     ecx, [rax+8]
0x1800051ec  mov     rax, [r11+8]
0x1800051f0  test    byte ptr [rcx+rax+3], 0Fh
0x1800051f5  jz      short loc_180005209
0x1800051f7  movzx   eax, byte ptr [rcx+rax+3]
0x1800051fc  mov     ecx, 0FFFFFFF0h
0x180005201  and     rax, rcx
0x180005204  add     rax, r10
0x180005207  jmp     short loc_18000520C
0x180005209  mov     rax, r10
0x18000520c  xor     rdx, rax
0x18000520f  mov     rcx, rdx; StackCookie
0x180005212  jmp     __security_check_cookie
```
