# __GSHandlerCheckCommon

- ea: `0x180003898`
- end: `0x1800038fb`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180003874`
- `0x18003049c`

## callees

- `0x1800021d0`
- `0x180003898`

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
0x180003898  mov     r10, rcx
0x18000389b  mov     r11, rdx
0x18000389e  mov     ecx, [r8]
0x1800038a1  and     ecx, 0FFFFFFF8h
0x1800038a4  test    byte ptr [r8], 4
0x1800038a8  jz      short loc_1800038BF
0x1800038aa  mov     eax, [r8+8]
0x1800038ae  movsxd  r9, dword ptr [r8+4]
0x1800038b2  neg     eax
0x1800038b4  movsxd  rdx, eax
0x1800038b7  add     r9, r10
0x1800038ba  and     r9, rdx
0x1800038bd  jmp     short loc_1800038C2
0x1800038bf  mov     r9, r10
0x1800038c2  movsxd  rax, ecx
0x1800038c5  mov     rdx, [rax+r9]
0x1800038c9  mov     rax, [r11+10h]
0x1800038cd  mov     ecx, [rax+8]
0x1800038d0  mov     rax, [r11+8]
0x1800038d4  test    byte ptr [rcx+rax+3], 0Fh
0x1800038d9  jz      short loc_1800038ED
0x1800038db  movzx   eax, byte ptr [rcx+rax+3]
0x1800038e0  mov     ecx, 0FFFFFFF0h
0x1800038e5  and     rax, rcx
0x1800038e8  add     rax, r10
0x1800038eb  jmp     short loc_1800038F0
0x1800038ed  mov     rax, r10
0x1800038f0  xor     rdx, rax
0x1800038f3  mov     rcx, rdx; StackCookie
0x1800038f6  jmp     __security_check_cookie
```
