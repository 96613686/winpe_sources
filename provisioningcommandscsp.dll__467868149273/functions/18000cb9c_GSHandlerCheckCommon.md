# __GSHandlerCheckCommon

- ea: `0x18000cb9c`
- end: `0x18000cbff`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000cb78`
- `0x18000cc08`

## callees

- `0x18000cb9c`
- `0x18000ccc0`

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
0x18000cb9c  mov     r10, rcx
0x18000cb9f  mov     r11, rdx
0x18000cba2  mov     ecx, [r8]
0x18000cba5  and     ecx, 0FFFFFFF8h
0x18000cba8  test    byte ptr [r8], 4
0x18000cbac  jz      short loc_18000CBC3
0x18000cbae  mov     eax, [r8+8]
0x18000cbb2  movsxd  r9, dword ptr [r8+4]
0x18000cbb6  neg     eax
0x18000cbb8  movsxd  rdx, eax
0x18000cbbb  add     r9, r10
0x18000cbbe  and     r9, rdx
0x18000cbc1  jmp     short loc_18000CBC6
0x18000cbc3  mov     r9, r10
0x18000cbc6  movsxd  rax, ecx
0x18000cbc9  mov     rdx, [rax+r9]
0x18000cbcd  mov     rax, [r11+10h]
0x18000cbd1  mov     ecx, [rax+8]
0x18000cbd4  mov     rax, [r11+8]
0x18000cbd8  test    byte ptr [rcx+rax+3], 0Fh
0x18000cbdd  jz      short loc_18000CBF1
0x18000cbdf  movzx   eax, byte ptr [rcx+rax+3]
0x18000cbe4  mov     ecx, 0FFFFFFF0h
0x18000cbe9  and     rax, rcx
0x18000cbec  add     rax, r10
0x18000cbef  jmp     short loc_18000CBF4
0x18000cbf1  mov     rax, r10
0x18000cbf4  xor     rdx, rax
0x18000cbf7  mov     rcx, rdx; StackCookie
0x18000cbfa  jmp     __security_check_cookie
```
