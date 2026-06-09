# __GSHandlerCheckCommon

- ea: `0x140007644`
- end: `0x1400076a7`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140007620`

## callees

- `0x140001340`
- `0x140007644`

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
0x140007644  mov     r10, rcx
0x140007647  mov     r11, rdx
0x14000764a  mov     ecx, [r8]
0x14000764d  and     ecx, 0FFFFFFF8h
0x140007650  test    byte ptr [r8], 4
0x140007654  jz      short loc_14000766B
0x140007656  mov     eax, [r8+8]
0x14000765a  movsxd  r9, dword ptr [r8+4]
0x14000765e  neg     eax
0x140007660  movsxd  rdx, eax
0x140007663  add     r9, r10
0x140007666  and     r9, rdx
0x140007669  jmp     short loc_14000766E
0x14000766b  mov     r9, r10
0x14000766e  movsxd  rax, ecx
0x140007671  mov     rdx, [rax+r9]
0x140007675  mov     rax, [r11+10h]
0x140007679  mov     ecx, [rax+8]
0x14000767c  mov     rax, [r11+8]
0x140007680  test    byte ptr [rcx+rax+3], 0Fh
0x140007685  jz      short loc_140007699
0x140007687  movzx   eax, byte ptr [rcx+rax+3]
0x14000768c  mov     ecx, 0FFFFFFF0h
0x140007691  and     rax, rcx
0x140007694  add     rax, r10
0x140007697  jmp     short loc_14000769C
0x140007699  mov     rax, r10
0x14000769c  xor     rdx, rax
0x14000769f  mov     rcx, rdx; StackCookie
0x1400076a2  jmp     __security_check_cookie
```
