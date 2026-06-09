# __GSHandlerCheckCommon

- ea: `0x1800077c4`
- end: `0x180007827`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800077a0`

## callees

- `0x1800077c4`
- `0x180007870`

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
0x1800077c4  mov     r10, rcx
0x1800077c7  mov     r11, rdx
0x1800077ca  mov     ecx, [r8]
0x1800077cd  and     ecx, 0FFFFFFF8h
0x1800077d0  test    byte ptr [r8], 4
0x1800077d4  jz      short loc_1800077EB
0x1800077d6  mov     eax, [r8+8]
0x1800077da  movsxd  r9, dword ptr [r8+4]
0x1800077de  neg     eax
0x1800077e0  movsxd  rdx, eax
0x1800077e3  add     r9, r10
0x1800077e6  and     r9, rdx
0x1800077e9  jmp     short loc_1800077EE
0x1800077eb  mov     r9, r10
0x1800077ee  movsxd  rax, ecx
0x1800077f1  mov     rdx, [rax+r9]
0x1800077f5  mov     rax, [r11+10h]
0x1800077f9  mov     ecx, [rax+8]
0x1800077fc  mov     rax, [r11+8]
0x180007800  test    byte ptr [rcx+rax+3], 0Fh
0x180007805  jz      short loc_180007819
0x180007807  movzx   eax, byte ptr [rcx+rax+3]
0x18000780c  mov     ecx, 0FFFFFFF0h
0x180007811  and     rax, rcx
0x180007814  add     rax, r10
0x180007817  jmp     short loc_18000781C
0x180007819  mov     rax, r10
0x18000781c  xor     rdx, rax
0x18000781f  mov     rcx, rdx; StackCookie
0x180007822  jmp     __security_check_cookie
```
