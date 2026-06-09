# __GSHandlerCheckCommon

- ea: `0x14000540c`
- end: `0x14000546f`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1400053e8`

## callees

- `0x14000540c`
- `0x1400054c0`

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
0x14000540c  mov     r10, rcx
0x14000540f  mov     r11, rdx
0x140005412  mov     ecx, [r8]
0x140005415  and     ecx, 0FFFFFFF8h
0x140005418  test    byte ptr [r8], 4
0x14000541c  jz      short loc_140005433
0x14000541e  mov     eax, [r8+8]
0x140005422  movsxd  r9, dword ptr [r8+4]
0x140005426  neg     eax
0x140005428  movsxd  rdx, eax
0x14000542b  add     r9, r10
0x14000542e  and     r9, rdx
0x140005431  jmp     short loc_140005436
0x140005433  mov     r9, r10
0x140005436  movsxd  rax, ecx
0x140005439  mov     rdx, [rax+r9]
0x14000543d  mov     rax, [r11+10h]
0x140005441  mov     ecx, [rax+8]
0x140005444  mov     rax, [r11+8]
0x140005448  test    byte ptr [rcx+rax+3], 0Fh
0x14000544d  jz      short loc_140005461
0x14000544f  movzx   eax, byte ptr [rcx+rax+3]
0x140005454  mov     ecx, 0FFFFFFF0h
0x140005459  and     rax, rcx
0x14000545c  add     rax, r10
0x14000545f  jmp     short loc_140005464
0x140005461  mov     rax, r10
0x140005464  xor     rdx, rax
0x140005467  mov     rcx, rdx; StackCookie
0x14000546a  jmp     __security_check_cookie
```
