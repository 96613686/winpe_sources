# __GSHandlerCheckCommon

- ea: `0x180011f88`
- end: `0x180011feb`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180011f64`

## callees

- `0x180011f88`
- `0x180012040`

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
0x180011f88  mov     r10, rcx
0x180011f8b  mov     r11, rdx
0x180011f8e  mov     ecx, [r8]
0x180011f91  and     ecx, 0FFFFFFF8h
0x180011f94  test    byte ptr [r8], 4
0x180011f98  jz      short loc_180011FAF
0x180011f9a  mov     eax, [r8+8]
0x180011f9e  movsxd  r9, dword ptr [r8+4]
0x180011fa2  neg     eax
0x180011fa4  movsxd  rdx, eax
0x180011fa7  add     r9, r10
0x180011faa  and     r9, rdx
0x180011fad  jmp     short loc_180011FB2
0x180011faf  mov     r9, r10
0x180011fb2  movsxd  rax, ecx
0x180011fb5  mov     rdx, [rax+r9]
0x180011fb9  mov     rax, [r11+10h]
0x180011fbd  mov     ecx, [rax+8]
0x180011fc0  mov     rax, [r11+8]
0x180011fc4  test    byte ptr [rcx+rax+3], 0Fh
0x180011fc9  jz      short loc_180011FDD
0x180011fcb  movzx   eax, byte ptr [rcx+rax+3]
0x180011fd0  mov     ecx, 0FFFFFFF0h
0x180011fd5  and     rax, rcx
0x180011fd8  add     rax, r10
0x180011fdb  jmp     short loc_180011FE0
0x180011fdd  mov     rax, r10
0x180011fe0  xor     rdx, rax
0x180011fe3  mov     rcx, rdx; StackCookie
0x180011fe6  jmp     __security_check_cookie
```
