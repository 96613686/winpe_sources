# __GSHandlerCheckCommon

- ea: `0x180006410`
- end: `0x180006473`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800063ec`

## callees

- `0x180001400`
- `0x180006410`

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
0x180006410  mov     r10, rcx
0x180006413  mov     r11, rdx
0x180006416  mov     ecx, [r8]
0x180006419  and     ecx, 0FFFFFFF8h
0x18000641c  test    byte ptr [r8], 4
0x180006420  jz      short loc_180006437
0x180006422  mov     eax, [r8+8]
0x180006426  movsxd  r9, dword ptr [r8+4]
0x18000642a  neg     eax
0x18000642c  movsxd  rdx, eax
0x18000642f  add     r9, r10
0x180006432  and     r9, rdx
0x180006435  jmp     short loc_18000643A
0x180006437  mov     r9, r10
0x18000643a  movsxd  rax, ecx
0x18000643d  mov     rdx, [rax+r9]
0x180006441  mov     rax, [r11+10h]
0x180006445  mov     ecx, [rax+8]
0x180006448  mov     rax, [r11+8]
0x18000644c  test    byte ptr [rcx+rax+3], 0Fh
0x180006451  jz      short loc_180006465
0x180006453  movzx   eax, byte ptr [rcx+rax+3]
0x180006458  mov     ecx, 0FFFFFFF0h
0x18000645d  and     rax, rcx
0x180006460  add     rax, r10
0x180006463  jmp     short loc_180006468
0x180006465  mov     rax, r10
0x180006468  xor     rdx, rax
0x18000646b  mov     rcx, rdx; StackCookie
0x18000646e  jmp     __security_check_cookie
```
