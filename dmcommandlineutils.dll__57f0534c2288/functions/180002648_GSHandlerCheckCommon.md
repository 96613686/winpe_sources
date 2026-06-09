# __GSHandlerCheckCommon

- ea: `0x180002648`
- end: `0x1800026ab`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180002624`

## callees

- `0x180002648`
- `0x1800026e0`

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
0x180002648  mov     r10, rcx
0x18000264b  mov     r11, rdx
0x18000264e  mov     ecx, [r8]
0x180002651  and     ecx, 0FFFFFFF8h
0x180002654  test    byte ptr [r8], 4
0x180002658  jz      short loc_18000266F
0x18000265a  mov     eax, [r8+8]
0x18000265e  movsxd  r9, dword ptr [r8+4]
0x180002662  neg     eax
0x180002664  movsxd  rdx, eax
0x180002667  add     r9, r10
0x18000266a  and     r9, rdx
0x18000266d  jmp     short loc_180002672
0x18000266f  mov     r9, r10
0x180002672  movsxd  rax, ecx
0x180002675  mov     rdx, [rax+r9]
0x180002679  mov     rax, [r11+10h]
0x18000267d  mov     ecx, [rax+8]
0x180002680  mov     rax, [r11+8]
0x180002684  test    byte ptr [rcx+rax+3], 0Fh
0x180002689  jz      short loc_18000269D
0x18000268b  movzx   eax, byte ptr [rcx+rax+3]
0x180002690  mov     ecx, 0FFFFFFF0h
0x180002695  and     rax, rcx
0x180002698  add     rax, r10
0x18000269b  jmp     short loc_1800026A0
0x18000269d  mov     rax, r10
0x1800026a0  xor     rdx, rax
0x1800026a3  mov     rcx, rdx; StackCookie
0x1800026a6  jmp     __security_check_cookie
```
