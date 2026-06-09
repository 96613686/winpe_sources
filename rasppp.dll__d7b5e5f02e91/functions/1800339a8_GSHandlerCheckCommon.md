# __GSHandlerCheckCommon

- ea: `0x1800339a8`
- end: `0x180033a0b`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180033984`

## callees

- `0x180001460`
- `0x1800339a8`

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
0x1800339a8  mov     r10, rcx
0x1800339ab  mov     r11, rdx
0x1800339ae  mov     ecx, [r8]
0x1800339b1  and     ecx, 0FFFFFFF8h
0x1800339b4  test    byte ptr [r8], 4
0x1800339b8  jz      short loc_1800339CF
0x1800339ba  mov     eax, [r8+8]
0x1800339be  movsxd  r9, dword ptr [r8+4]
0x1800339c2  neg     eax
0x1800339c4  movsxd  rdx, eax
0x1800339c7  add     r9, r10
0x1800339ca  and     r9, rdx
0x1800339cd  jmp     short loc_1800339D2
0x1800339cf  mov     r9, r10
0x1800339d2  movsxd  rax, ecx
0x1800339d5  mov     rdx, [rax+r9]
0x1800339d9  mov     rax, [r11+10h]
0x1800339dd  mov     ecx, [rax+8]
0x1800339e0  mov     rax, [r11+8]
0x1800339e4  test    byte ptr [rcx+rax+3], 0Fh
0x1800339e9  jz      short loc_1800339FD
0x1800339eb  movzx   eax, byte ptr [rcx+rax+3]
0x1800339f0  mov     ecx, 0FFFFFFF0h
0x1800339f5  and     rax, rcx
0x1800339f8  add     rax, r10
0x1800339fb  jmp     short loc_180033A00
0x1800339fd  mov     rax, r10
0x180033a00  xor     rdx, rax
0x180033a03  mov     rcx, rdx; StackCookie
0x180033a06  jmp     __security_check_cookie
```
