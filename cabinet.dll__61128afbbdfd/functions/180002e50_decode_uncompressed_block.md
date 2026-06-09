# decode_uncompressed_block

- ea: `0x180002e50`
- end: `0x180002f04`
- name: `decode_uncompressed_block`
- size: `180`
- prototype: `__int64 __fastcall(__int64, int, int)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18000548c`

## callees

- `0x180002e50`

## pseudocode

```c
__int64 __fastcall decode_uncompressed_block(__int64 a1, int a2, int a3)
{
  char *v3; // r9
  int v4; // r11d
  unsigned int v6; // esi
  char v7; // al
  __int64 v8; // r8
  unsigned int v9; // ebx
  __int64 v10; // rcx
  __int64 v11; // r8

  v3 = *(char **)(a1 + 11016);
  v4 = a2 + a3;
  v6 = a2;
  while ( a2 < v4 )
  {
    if ( (unsigned __int64)v3 >= *(_QWORD *)(a1 + 11024) || a2 >= *(_DWORD *)(a1 + 8) + 261 )
      return 0xFFFFFFFFLL;
    v7 = *v3;
    v8 = a2++;
    ++v3;
    *(_BYTE *)(v8 + *(_QWORD *)a1) = v7;
  }
  v9 = 257;
  *(_QWORD *)(a1 + 11016) = v3;
  if ( v4 <= 257 )
    v9 = v4;
  for ( ; v6 < v9; *(_BYTE *)(v10 + *(_QWORD *)a1) = *(_BYTE *)(v11 + *(_QWORD *)a1) )
  {
    v10 = v6 + *(_DWORD *)(a1 + 8);
    v11 = v6++;
  }
  *(_DWORD *)(a1 + 11984) = a2 & *(_DWORD *)(a1 + 12);
  return (unsigned int)(a2 - v4);
}

```

## disassembly

```asm
0x180002e50  push    rsi
0x180002e52  mov     r9, [rcx+2B08h]
0x180002e59  lea     r11d, [rdx+r8]
0x180002e5d  mov     r10, rcx
0x180002e60  mov     esi, edx
0x180002e62  cmp     edx, r11d
0x180002e65  jge     short loc_180002E96
0x180002e67  cmp     r9, [r10+2B10h]
0x180002e6e  jnb     loc_180002EF8
0x180002e74  mov     eax, [r10+8]
0x180002e78  add     eax, 105h
0x180002e7d  cmp     edx, eax
0x180002e7f  jge     short loc_180002EF8
0x180002e81  movzx   eax, byte ptr [r9]
0x180002e85  mov     rcx, [r10]
0x180002e88  movsxd  r8, edx
0x180002e8b  inc     edx
0x180002e8d  inc     r9
0x180002e90  mov     [r8+rcx], al
0x180002e94  jmp     short loc_180002E62
0x180002e96  mov     [rsp+8+arg_0], rbx
0x180002e9b  mov     rcx, r10
0x180002e9e  mov     ebx, 101h
0x180002ea3  mov     [rsp+8+arg_8], rdi
0x180002ea8  mov     [r10+2B08h], r9
0x180002eaf  mov     eax, 8
0x180002eb4  cmp     r11d, ebx
0x180002eb7  jle     short loc_180002EFF
0x180002eb9  lea     rdi, [rcx+rax]
0x180002ebd  cmp     esi, ebx
0x180002ebf  jnb     short loc_180002EDA
0x180002ec1  mov     r9, [r10]
0x180002ec4  mov     ecx, [rdi]
0x180002ec6  add     ecx, esi
0x180002ec8  mov     r8d, esi
0x180002ecb  inc     esi
0x180002ecd  movzx   eax, byte ptr [r8+r9]
0x180002ed2  mov     [rcx+r9], al
0x180002ed6  cmp     esi, ebx
0x180002ed8  jb      short loc_180002EC1
0x180002eda  mov     eax, [r10+0Ch]
0x180002ede  mov     rdi, [rsp+8+arg_8]
0x180002ee3  and     eax, edx
0x180002ee5  mov     rbx, [rsp+8+arg_0]
0x180002eea  sub     edx, r11d
0x180002eed  mov     [r10+2ED0h], eax
0x180002ef4  mov     eax, edx
0x180002ef6  pop     rsi
0x180002ef7  retn
0x180002ef8  mov     eax, 0FFFFFFFFh
0x180002efd  pop     rsi
0x180002efe  retn
0x180002eff  mov     ebx, r11d
0x180002f02  jmp     short loc_180002EB9
```
