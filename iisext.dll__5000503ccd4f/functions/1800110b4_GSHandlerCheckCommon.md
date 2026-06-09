# __GSHandlerCheckCommon

- ea: `0x1800110b4`
- end: `0x180011117`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180011090`
- `0x180011120`

## callees

- `0x1800110b4`
- `0x1800111e0`

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
0x1800110b4  mov     r10, rcx
0x1800110b7  mov     r11, rdx
0x1800110ba  mov     ecx, [r8]
0x1800110bd  and     ecx, 0FFFFFFF8h
0x1800110c0  test    byte ptr [r8], 4
0x1800110c4  jz      short loc_1800110DB
0x1800110c6  mov     eax, [r8+8]
0x1800110ca  movsxd  r9, dword ptr [r8+4]
0x1800110ce  neg     eax
0x1800110d0  movsxd  rdx, eax
0x1800110d3  add     r9, r10
0x1800110d6  and     r9, rdx
0x1800110d9  jmp     short loc_1800110DE
0x1800110db  mov     r9, r10
0x1800110de  movsxd  rax, ecx
0x1800110e1  mov     rdx, [rax+r9]
0x1800110e5  mov     rax, [r11+10h]
0x1800110e9  mov     ecx, [rax+8]
0x1800110ec  mov     rax, [r11+8]
0x1800110f0  test    byte ptr [rcx+rax+3], 0Fh
0x1800110f5  jz      short loc_180011109
0x1800110f7  movzx   eax, byte ptr [rcx+rax+3]
0x1800110fc  mov     ecx, 0FFFFFFF0h
0x180011101  and     rax, rcx
0x180011104  add     rax, r10
0x180011107  jmp     short loc_18001110C
0x180011109  mov     rax, r10
0x18001110c  xor     rdx, rax
0x18001110f  mov     rcx, rdx; StackCookie
0x180011112  jmp     __security_check_cookie
```
