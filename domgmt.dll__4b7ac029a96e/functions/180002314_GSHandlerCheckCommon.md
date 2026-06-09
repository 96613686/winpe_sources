# __GSHandlerCheckCommon

- ea: `0x180002314`
- end: `0x180002377`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800022f0`
- `0x18000d4ec`

## callees

- `0x180001ba0`
- `0x180002314`

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
0x180002314  mov     r10, rcx
0x180002317  mov     r11, rdx
0x18000231a  mov     ecx, [r8]
0x18000231d  and     ecx, 0FFFFFFF8h
0x180002320  test    byte ptr [r8], 4
0x180002324  jz      short loc_18000233B
0x180002326  mov     eax, [r8+8]
0x18000232a  movsxd  r9, dword ptr [r8+4]
0x18000232e  neg     eax
0x180002330  movsxd  rdx, eax
0x180002333  add     r9, r10
0x180002336  and     r9, rdx
0x180002339  jmp     short loc_18000233E
0x18000233b  mov     r9, r10
0x18000233e  movsxd  rax, ecx
0x180002341  mov     rdx, [rax+r9]
0x180002345  mov     rax, [r11+10h]
0x180002349  mov     ecx, [rax+8]
0x18000234c  mov     rax, [r11+8]
0x180002350  test    byte ptr [rcx+rax+3], 0Fh
0x180002355  jz      short loc_180002369
0x180002357  movzx   eax, byte ptr [rcx+rax+3]
0x18000235c  mov     ecx, 0FFFFFFF0h
0x180002361  and     rax, rcx
0x180002364  add     rax, r10
0x180002367  jmp     short loc_18000236C
0x180002369  mov     rax, r10
0x18000236c  xor     rdx, rax
0x18000236f  mov     rcx, rdx; StackCookie
0x180002372  jmp     __security_check_cookie
```
