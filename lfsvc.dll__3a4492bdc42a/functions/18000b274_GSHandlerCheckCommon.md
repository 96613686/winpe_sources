# __GSHandlerCheckCommon

- ea: `0x18000b274`
- end: `0x18000b2d7`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000b250`
- `0x18000b2e0`

## callees

- `0x180004310`
- `0x18000b274`

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
0x18000b274  mov     r10, rcx
0x18000b277  mov     r11, rdx
0x18000b27a  mov     ecx, [r8]
0x18000b27d  and     ecx, 0FFFFFFF8h
0x18000b280  test    byte ptr [r8], 4
0x18000b284  jz      short loc_18000B29B
0x18000b286  mov     eax, [r8+8]
0x18000b28a  movsxd  r9, dword ptr [r8+4]
0x18000b28e  neg     eax
0x18000b290  movsxd  rdx, eax
0x18000b293  add     r9, r10
0x18000b296  and     r9, rdx
0x18000b299  jmp     short loc_18000B29E
0x18000b29b  mov     r9, r10
0x18000b29e  movsxd  rax, ecx
0x18000b2a1  mov     rdx, [rax+r9]
0x18000b2a5  mov     rax, [r11+10h]
0x18000b2a9  mov     ecx, [rax+8]
0x18000b2ac  mov     rax, [r11+8]
0x18000b2b0  test    byte ptr [rcx+rax+3], 0Fh
0x18000b2b5  jz      short loc_18000B2C9
0x18000b2b7  movzx   eax, byte ptr [rcx+rax+3]
0x18000b2bc  mov     ecx, 0FFFFFFF0h
0x18000b2c1  and     rax, rcx
0x18000b2c4  add     rax, r10
0x18000b2c7  jmp     short loc_18000B2CC
0x18000b2c9  mov     rax, r10
0x18000b2cc  xor     rdx, rax
0x18000b2cf  mov     rcx, rdx; StackCookie
0x18000b2d2  jmp     __security_check_cookie
```
