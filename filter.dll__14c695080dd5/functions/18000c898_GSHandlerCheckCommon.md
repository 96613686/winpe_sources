# __GSHandlerCheckCommon

- ea: `0x18000c898`
- end: `0x18000c8fb`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000c874`

## callees

- `0x18000c898`
- `0x18000c970`

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
0x18000c898  mov     r10, rcx
0x18000c89b  mov     r11, rdx
0x18000c89e  mov     ecx, [r8]
0x18000c8a1  and     ecx, 0FFFFFFF8h
0x18000c8a4  test    byte ptr [r8], 4
0x18000c8a8  jz      short loc_18000C8BF
0x18000c8aa  mov     eax, [r8+8]
0x18000c8ae  movsxd  r9, dword ptr [r8+4]
0x18000c8b2  neg     eax
0x18000c8b4  movsxd  rdx, eax
0x18000c8b7  add     r9, r10
0x18000c8ba  and     r9, rdx
0x18000c8bd  jmp     short loc_18000C8C2
0x18000c8bf  mov     r9, r10
0x18000c8c2  movsxd  rax, ecx
0x18000c8c5  mov     rdx, [rax+r9]
0x18000c8c9  mov     rax, [r11+10h]
0x18000c8cd  mov     ecx, [rax+8]
0x18000c8d0  mov     rax, [r11+8]
0x18000c8d4  test    byte ptr [rcx+rax+3], 0Fh
0x18000c8d9  jz      short loc_18000C8ED
0x18000c8db  movzx   eax, byte ptr [rcx+rax+3]
0x18000c8e0  mov     ecx, 0FFFFFFF0h
0x18000c8e5  and     rax, rcx
0x18000c8e8  add     rax, r10
0x18000c8eb  jmp     short loc_18000C8F0
0x18000c8ed  mov     rax, r10
0x18000c8f0  xor     rdx, rax
0x18000c8f3  mov     rcx, rdx; StackCookie
0x18000c8f6  jmp     __security_check_cookie
```
