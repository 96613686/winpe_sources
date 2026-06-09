# __GSHandlerCheckCommon

- ea: `0x18000ed50`
- end: `0x18000edb3`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000ed2c`

## callees

- `0x18000ed50`
- `0x18000ee10`

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
0x18000ed50  mov     r10, rcx
0x18000ed53  mov     r11, rdx
0x18000ed56  mov     ecx, [r8]
0x18000ed59  and     ecx, 0FFFFFFF8h
0x18000ed5c  test    byte ptr [r8], 4
0x18000ed60  jz      short loc_18000ED77
0x18000ed62  mov     eax, [r8+8]
0x18000ed66  movsxd  r9, dword ptr [r8+4]
0x18000ed6a  neg     eax
0x18000ed6c  movsxd  rdx, eax
0x18000ed6f  add     r9, r10
0x18000ed72  and     r9, rdx
0x18000ed75  jmp     short loc_18000ED7A
0x18000ed77  mov     r9, r10
0x18000ed7a  movsxd  rax, ecx
0x18000ed7d  mov     rdx, [rax+r9]
0x18000ed81  mov     rax, [r11+10h]
0x18000ed85  mov     ecx, [rax+8]
0x18000ed88  mov     rax, [r11+8]
0x18000ed8c  test    byte ptr [rcx+rax+3], 0Fh
0x18000ed91  jz      short loc_18000EDA5
0x18000ed93  movzx   eax, byte ptr [rcx+rax+3]
0x18000ed98  mov     ecx, 0FFFFFFF0h
0x18000ed9d  and     rax, rcx
0x18000eda0  add     rax, r10
0x18000eda3  jmp     short loc_18000EDA8
0x18000eda5  mov     rax, r10
0x18000eda8  xor     rdx, rax
0x18000edab  mov     rcx, rdx; StackCookie
0x18000edae  jmp     __security_check_cookie
```
