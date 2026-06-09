# __GSHandlerCheckCommon

- ea: `0x1800077b8`
- end: `0x18000781b`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180007794`
- `0x180007824`

## callees

- `0x180003a90`
- `0x1800077b8`

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
0x1800077b8  mov     r10, rcx
0x1800077bb  mov     r11, rdx
0x1800077be  mov     ecx, [r8]
0x1800077c1  and     ecx, 0FFFFFFF8h
0x1800077c4  test    byte ptr [r8], 4
0x1800077c8  jz      short loc_1800077DF
0x1800077ca  mov     eax, [r8+8]
0x1800077ce  movsxd  r9, dword ptr [r8+4]
0x1800077d2  neg     eax
0x1800077d4  movsxd  rdx, eax
0x1800077d7  add     r9, r10
0x1800077da  and     r9, rdx
0x1800077dd  jmp     short loc_1800077E2
0x1800077df  mov     r9, r10
0x1800077e2  movsxd  rax, ecx
0x1800077e5  mov     rdx, [rax+r9]
0x1800077e9  mov     rax, [r11+10h]
0x1800077ed  mov     ecx, [rax+8]
0x1800077f0  mov     rax, [r11+8]
0x1800077f4  test    byte ptr [rcx+rax+3], 0Fh
0x1800077f9  jz      short loc_18000780D
0x1800077fb  movzx   eax, byte ptr [rcx+rax+3]
0x180007800  mov     ecx, 0FFFFFFF0h
0x180007805  and     rax, rcx
0x180007808  add     rax, r10
0x18000780b  jmp     short loc_180007810
0x18000780d  mov     rax, r10
0x180007810  xor     rdx, rax
0x180007813  mov     rcx, rdx; StackCookie
0x180007816  jmp     __security_check_cookie
```
