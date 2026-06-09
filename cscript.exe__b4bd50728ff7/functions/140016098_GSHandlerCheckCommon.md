# __GSHandlerCheckCommon

- ea: `0x140016098`
- end: `0x1400160fb`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140016074`
- `0x140016104`

## callees

- `0x140016098`
- `0x1400161d0`

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
0x140016098  mov     r10, rcx
0x14001609b  mov     r11, rdx
0x14001609e  mov     ecx, [r8]
0x1400160a1  and     ecx, 0FFFFFFF8h
0x1400160a4  test    byte ptr [r8], 4
0x1400160a8  jz      short loc_1400160BF
0x1400160aa  mov     eax, [r8+8]
0x1400160ae  movsxd  r9, dword ptr [r8+4]
0x1400160b2  neg     eax
0x1400160b4  movsxd  rdx, eax
0x1400160b7  add     r9, r10
0x1400160ba  and     r9, rdx
0x1400160bd  jmp     short loc_1400160C2
0x1400160bf  mov     r9, r10
0x1400160c2  movsxd  rax, ecx
0x1400160c5  mov     rdx, [rax+r9]
0x1400160c9  mov     rax, [r11+10h]
0x1400160cd  mov     ecx, [rax+8]
0x1400160d0  mov     rax, [r11+8]
0x1400160d4  test    byte ptr [rcx+rax+3], 0Fh
0x1400160d9  jz      short loc_1400160ED
0x1400160db  movzx   eax, byte ptr [rcx+rax+3]
0x1400160e0  mov     ecx, 0FFFFFFF0h
0x1400160e5  and     rax, rcx
0x1400160e8  add     rax, r10
0x1400160eb  jmp     short loc_1400160F0
0x1400160ed  mov     rax, r10
0x1400160f0  xor     rdx, rax
0x1400160f3  mov     rcx, rdx; StackCookie
0x1400160f6  jmp     __security_check_cookie
```
