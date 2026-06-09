# __GSHandlerCheckCommon

- ea: `0x18001269c`
- end: `0x1800126ff`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180012678`
- `0x180012708`
- `0x180012770`

## callees

- `0x18001269c`
- `0x180012830`

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
0x18001269c  mov     r10, rcx
0x18001269f  mov     r11, rdx
0x1800126a2  mov     ecx, [r8]
0x1800126a5  and     ecx, 0FFFFFFF8h
0x1800126a8  test    byte ptr [r8], 4
0x1800126ac  jz      short loc_1800126C3
0x1800126ae  mov     eax, [r8+8]
0x1800126b2  movsxd  r9, dword ptr [r8+4]
0x1800126b6  neg     eax
0x1800126b8  movsxd  rdx, eax
0x1800126bb  add     r9, r10
0x1800126be  and     r9, rdx
0x1800126c1  jmp     short loc_1800126C6
0x1800126c3  mov     r9, r10
0x1800126c6  movsxd  rax, ecx
0x1800126c9  mov     rdx, [rax+r9]
0x1800126cd  mov     rax, [r11+10h]
0x1800126d1  mov     ecx, [rax+8]
0x1800126d4  mov     rax, [r11+8]
0x1800126d8  test    byte ptr [rcx+rax+3], 0Fh
0x1800126dd  jz      short loc_1800126F1
0x1800126df  movzx   eax, byte ptr [rcx+rax+3]
0x1800126e4  mov     ecx, 0FFFFFFF0h
0x1800126e9  and     rax, rcx
0x1800126ec  add     rax, r10
0x1800126ef  jmp     short loc_1800126F4
0x1800126f1  mov     rax, r10
0x1800126f4  xor     rdx, rax
0x1800126f7  mov     rcx, rdx; StackCookie
0x1800126fa  jmp     __security_check_cookie
```
