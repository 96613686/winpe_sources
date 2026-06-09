# __GSHandlerCheckCommon

- ea: `0x180008ec8`
- end: `0x180008f2b`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180008ea4`
- `0x180008f34`

## callees

- `0x180002100`
- `0x180008ec8`

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
0x180008ec8  mov     r10, rcx
0x180008ecb  mov     r11, rdx
0x180008ece  mov     ecx, [r8]
0x180008ed1  and     ecx, 0FFFFFFF8h
0x180008ed4  test    byte ptr [r8], 4
0x180008ed8  jz      short loc_180008EEF
0x180008eda  mov     eax, [r8+8]
0x180008ede  movsxd  r9, dword ptr [r8+4]
0x180008ee2  neg     eax
0x180008ee4  movsxd  rdx, eax
0x180008ee7  add     r9, r10
0x180008eea  and     r9, rdx
0x180008eed  jmp     short loc_180008EF2
0x180008eef  mov     r9, r10
0x180008ef2  movsxd  rax, ecx
0x180008ef5  mov     rdx, [rax+r9]
0x180008ef9  mov     rax, [r11+10h]
0x180008efd  mov     ecx, [rax+8]
0x180008f00  mov     rax, [r11+8]
0x180008f04  test    byte ptr [rcx+rax+3], 0Fh
0x180008f09  jz      short loc_180008F1D
0x180008f0b  movzx   eax, byte ptr [rcx+rax+3]
0x180008f10  mov     ecx, 0FFFFFFF0h
0x180008f15  and     rax, rcx
0x180008f18  add     rax, r10
0x180008f1b  jmp     short loc_180008F20
0x180008f1d  mov     rax, r10
0x180008f20  xor     rdx, rax
0x180008f23  mov     rcx, rdx; StackCookie
0x180008f26  jmp     __security_check_cookie
```
