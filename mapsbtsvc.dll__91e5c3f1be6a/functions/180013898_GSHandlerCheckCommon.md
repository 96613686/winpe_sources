# __GSHandlerCheckCommon

- ea: `0x180013898`
- end: `0x1800138fb`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180013874`
- `0x180013904`

## callees

- `0x180001e70`
- `0x180013898`

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
0x180013898  mov     r10, rcx
0x18001389b  mov     r11, rdx
0x18001389e  mov     ecx, [r8]
0x1800138a1  and     ecx, 0FFFFFFF8h
0x1800138a4  test    byte ptr [r8], 4
0x1800138a8  jz      short loc_1800138BF
0x1800138aa  mov     eax, [r8+8]
0x1800138ae  movsxd  r9, dword ptr [r8+4]
0x1800138b2  neg     eax
0x1800138b4  movsxd  rdx, eax
0x1800138b7  add     r9, r10
0x1800138ba  and     r9, rdx
0x1800138bd  jmp     short loc_1800138C2
0x1800138bf  mov     r9, r10
0x1800138c2  movsxd  rax, ecx
0x1800138c5  mov     rdx, [rax+r9]
0x1800138c9  mov     rax, [r11+10h]
0x1800138cd  mov     ecx, [rax+8]
0x1800138d0  mov     rax, [r11+8]
0x1800138d4  test    byte ptr [rcx+rax+3], 0Fh
0x1800138d9  jz      short loc_1800138ED
0x1800138db  movzx   eax, byte ptr [rcx+rax+3]
0x1800138e0  mov     ecx, 0FFFFFFF0h
0x1800138e5  and     rax, rcx
0x1800138e8  add     rax, r10
0x1800138eb  jmp     short loc_1800138F0
0x1800138ed  mov     rax, r10
0x1800138f0  xor     rdx, rax
0x1800138f3  mov     rcx, rdx; StackCookie
0x1800138f6  jmp     __security_check_cookie
```
