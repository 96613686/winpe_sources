# l3audioDecodeOpenStream

- ea: `0x1800027dc`
- end: `0x1800028eb`
- name: `l3audioDecodeOpenStream`
- size: `271`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180003218`

## callees

- `0x1800027dc`
- `0x180003980`

## pseudocode

```c
__int64 __fastcall l3audioDecodeOpenStream(__int64 a1, __int64 a2)
{
  __int64 v2; // rbx
  __int64 v3; // r10
  _WORD *v5; // r9
  unsigned int v6; // r11d
  __int64 v7; // r14
  unsigned int v8; // eax
  _BOOL8 v9; // r9

  v2 = *(_QWORD *)(a2 + 4);
  v3 = *(_QWORD *)(a2 + 12);
  v5 = (_WORD *)(v3 + 2);
  if ( *(_WORD *)(v2 + 2) == 1 && *v5 == 2 )
    return 512;
  v6 = *(_DWORD *)(v2 + 4);
  if ( *(_DWORD *)(v3 + 4) != v6 && *(_DWORD *)(v3 + 4) != v6 >> 1 && *(_DWORD *)(v3 + 4) != v6 >> 2 )
    return 512;
  v7 = *(_QWORD *)(a2 + 52);
  v8 = 1152;
  if ( v6 <= 0x5DC0 )
    v8 = 576;
  *(_DWORD *)(v7 + 40) = v8
                       / (v6
                        / *(_DWORD *)(v3 + 4))
                       * (*(unsigned __int16 *)(v3 + 14) >> 3 << ((unsigned __int16)*v5 >> 1));
  if ( (*(_BYTE *)(a2 + 44) & 1) == 0 )
  {
    v9 = *(_WORD *)(v2 + 2) == 2 && *v5 == 1;
    if ( (int)mp3decOpen(
                v7 + 32,
                (unsigned int)(__int16)((unsigned int)(*(_DWORD *)(v2 + 4) / *(_DWORD *)(v3 + 4)) >> 1),
                *(_WORD *)(v3 + 14) == 8,
                v9) < 0 )
      return 512;
    _InterlockedAdd((volatile signed __int32 *)(a1 + 52), 1u);
    *(_DWORD *)(v7 + 12) = _InterlockedIncrement(&dword_18001A14C);
  }
  return 0;
}

```

## disassembly

```asm
0x1800027dc  push    rbx
0x1800027de  push    rbp
0x1800027df  push    rsi
0x1800027e0  push    r14
0x1800027e2  push    r15
0x1800027e4  sub     rsp, 20h
0x1800027e8  mov     rbx, [rdx+4]
0x1800027ec  mov     r15d, 1
0x1800027f2  mov     r10, [rdx+0Ch]
0x1800027f6  mov     rsi, rdx
0x1800027f9  mov     rbp, rcx
0x1800027fc  lea     r9, [r10+2]
0x180002800  cmp     [rbx+2], r15w
0x180002805  jnz     short loc_180002812
0x180002807  cmp     word ptr [r9], 2
0x18000280c  jz      loc_1800028BF
0x180002812  mov     r11d, [rbx+4]
0x180002816  cmp     [r10+4], r11d
0x18000281a  jz      short loc_180002837
0x18000281c  mov     eax, r11d
0x18000281f  shr     eax, 1
0x180002821  cmp     [r10+4], eax
0x180002825  jz      short loc_180002837
0x180002827  mov     eax, r11d
0x18000282a  shr     eax, 2
0x18000282d  cmp     [r10+4], eax
0x180002831  jnz     loc_1800028BF
0x180002837  mov     r14, [rdx+34h]
0x18000283b  mov     eax, r11d
0x18000283e  movzx   ecx, word ptr [r9]
0x180002842  xor     edx, edx
0x180002844  div     dword ptr [r10+4]
0x180002848  movzx   r8d, word ptr [r10+0Eh]
0x18000284d  mov     edx, 240h
0x180002852  shr     ecx, 1
0x180002854  shr     r8d, 3
0x180002858  shl     r8d, cl
0x18000285b  mov     ecx, eax
0x18000285d  cmp     r11d, 5DC0h
0x180002864  mov     eax, 480h
0x180002869  cmovbe  eax, edx
0x18000286c  xor     edx, edx
0x18000286e  div     ecx
0x180002870  imul    r8d, eax
0x180002874  mov     [r14+28h], r8d
0x180002878  mov     eax, [rsi+2Ch]
0x18000287b  and     eax, r15d
0x18000287e  test    al, al
0x180002880  jnz     short loc_1800028DD
0x180002882  mov     eax, [rbx+4]
0x180002885  xor     edx, edx
0x180002887  div     dword ptr [r10+4]
0x18000288b  xor     r8d, r8d
0x18000288e  shr     eax, 1
0x180002890  cmp     word ptr [r10+0Eh], 8
0x180002896  movsx   edx, ax
0x180002899  setz    r8b
0x18000289d  cmp     word ptr [rbx+2], 2
0x1800028a2  jnz     short loc_1800028AF
0x1800028a4  cmp     [r9], r15w
0x1800028a8  jnz     short loc_1800028AF
0x1800028aa  mov     r9d, r15d
0x1800028ad  jmp     short loc_1800028B2
0x1800028af  xor     r9d, r9d
0x1800028b2  lea     rcx, [r14+20h]
0x1800028b6  call    mp3decOpen
0x1800028bb  test    eax, eax
0x1800028bd  jns     short loc_1800028C6
0x1800028bf  mov     eax, 200h
0x1800028c4  jmp     short loc_1800028DF
0x1800028c6  lock add [rbp+34h], r15d
0x1800028cb  mov     eax, r15d
0x1800028ce  lock xadd cs:dword_18001A14C, eax
0x1800028d6  add     eax, r15d
0x1800028d9  mov     [r14+0Ch], eax
0x1800028dd  xor     eax, eax
0x1800028df  add     rsp, 20h
0x1800028e3  pop     r15
0x1800028e5  pop     r14
0x1800028e7  pop     rsi
0x1800028e8  pop     rbp
0x1800028e9  pop     rbx
0x1800028ea  retn
```
