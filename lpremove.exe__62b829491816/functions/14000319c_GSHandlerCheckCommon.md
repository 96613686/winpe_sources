# __GSHandlerCheckCommon

- ea: `0x14000319c`
- end: `0x1400031ff`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140003178`
- `0x14000fd8c`

## callees

- `0x140002190`
- `0x14000319c`

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
0x14000319c  mov     r10, rcx
0x14000319f  mov     r11, rdx
0x1400031a2  mov     ecx, [r8]
0x1400031a5  and     ecx, 0FFFFFFF8h
0x1400031a8  test    byte ptr [r8], 4
0x1400031ac  jz      short loc_1400031C3
0x1400031ae  mov     eax, [r8+8]
0x1400031b2  movsxd  r9, dword ptr [r8+4]
0x1400031b6  neg     eax
0x1400031b8  movsxd  rdx, eax
0x1400031bb  add     r9, r10
0x1400031be  and     r9, rdx
0x1400031c1  jmp     short loc_1400031C6
0x1400031c3  mov     r9, r10
0x1400031c6  movsxd  rax, ecx
0x1400031c9  mov     rdx, [rax+r9]
0x1400031cd  mov     rax, [r11+10h]
0x1400031d1  mov     ecx, [rax+8]
0x1400031d4  mov     rax, [r11+8]
0x1400031d8  test    byte ptr [rcx+rax+3], 0Fh
0x1400031dd  jz      short loc_1400031F1
0x1400031df  movzx   eax, byte ptr [rcx+rax+3]
0x1400031e4  mov     ecx, 0FFFFFFF0h
0x1400031e9  and     rax, rcx
0x1400031ec  add     rax, r10
0x1400031ef  jmp     short loc_1400031F4
0x1400031f1  mov     rax, r10
0x1400031f4  xor     rdx, rax
0x1400031f7  mov     rcx, rdx; StackCookie
0x1400031fa  jmp     __security_check_cookie
```
