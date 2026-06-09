# __GSHandlerCheckCommon

- ea: `0x18000298c`
- end: `0x1800029ef`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180002968`
- `0x1800315c4`

## callees

- `0x18000298c`
- `0x180031680`

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
0x18000298c  mov     r10, rcx
0x18000298f  mov     r11, rdx
0x180002992  mov     ecx, [r8]
0x180002995  and     ecx, 0FFFFFFF8h
0x180002998  test    byte ptr [r8], 4
0x18000299c  jz      short loc_1800029B3
0x18000299e  mov     eax, [r8+8]
0x1800029a2  movsxd  r9, dword ptr [r8+4]
0x1800029a6  neg     eax
0x1800029a8  movsxd  rdx, eax
0x1800029ab  add     r9, r10
0x1800029ae  and     r9, rdx
0x1800029b1  jmp     short loc_1800029B6
0x1800029b3  mov     r9, r10
0x1800029b6  movsxd  rax, ecx
0x1800029b9  mov     rdx, [rax+r9]
0x1800029bd  mov     rax, [r11+10h]
0x1800029c1  mov     ecx, [rax+8]
0x1800029c4  mov     rax, [r11+8]
0x1800029c8  test    byte ptr [rcx+rax+3], 0Fh
0x1800029cd  jz      short loc_1800029E1
0x1800029cf  movzx   eax, byte ptr [rcx+rax+3]
0x1800029d4  mov     ecx, 0FFFFFFF0h
0x1800029d9  and     rax, rcx
0x1800029dc  add     rax, r10
0x1800029df  jmp     short loc_1800029E4
0x1800029e1  mov     rax, r10
0x1800029e4  xor     rdx, rax
0x1800029e7  mov     rcx, rdx; StackCookie
0x1800029ea  jmp     __security_check_cookie
```
