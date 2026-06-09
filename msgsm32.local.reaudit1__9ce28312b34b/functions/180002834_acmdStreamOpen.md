# acmdStreamOpen

- ea: `0x180002834`
- end: `0x180002976`
- name: `acmdStreamOpen`
- size: `322`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x1800020d0`

## callees

- `0x180002834`
- `0x180002aec`
- `0x180002b54`
- `0x18000579c`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180002933`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180002933`

## pseudocode

```c
__int64 __fastcall acmdStreamOpen(__int64 a1, __int64 a2)
{
  int v3; // edi
  __int64 v5; // rbp
  __int64 v6; // r11
  __int64 (__fastcall *v7)(_QWORD, _QWORD); // rsi
  _QWORD *v9; // rax
  __int64 v10; // r9

  v3 = *(_DWORD *)(a2 + 44);
  v5 = *(_QWORD *)(a2 + 12);
  if ( **(_WORD **)(a2 + 4) == 1 )
  {
    if ( (unsigned int)pcmIsValidFormat(*(_QWORD *)(a2 + 4)) && (unsigned int)gsm610IsValidFormat(v5) )
    {
      if ( (v3 & 4) == 0
        && *((_DWORD *)&gaRateListFormat[1] + 3 * *(unsigned int *)(a1 + 56))
         / (unsigned int)*(unsigned __int16 *)(v6 + 2) < *(_DWORD *)(v6 + 4) )
      {
        return 8;
      }
      v7 = gsm610Encode;
      goto LABEL_13;
    }
    return 512;
  }
  if ( **(_WORD **)(a2 + 4) != 49
    || !(unsigned int)gsm610IsValidFormat(*(_QWORD *)(a2 + 4))
    || !(unsigned int)pcmIsValidFormat(v5) )
  {
    return 512;
  }
  if ( (v3 & 4) == 0
    && *((_DWORD *)&gaRateListFormat[1] + 3 * *(unsigned int *)(a1 + 60)) / (unsigned int)*(unsigned __int16 *)(v6 + 2) < *(_DWORD *)(v6 + 4) )
  {
    return 8;
  }
  v7 = gsm610Decode;
LABEL_13:
  if ( *(_WORD *)(v6 + 2) != *(_WORD *)(v5 + 2) || *(_DWORD *)(v6 + 4) != *(_DWORD *)(v5 + 4) )
    return 8;
  if ( (v3 & 1) != 0 )
    return 0;
  v9 = LocalAlloc(0x40u, 0x28Eu);
  if ( v9 )
  {
    *v9 = v7;
    gsm610Reset(v9);
    *(_DWORD *)(a2 + 48) = 0;
    *(_QWORD *)(a2 + 52) = v10;
    return 0;
  }
  return 7;
}

```

## disassembly

```asm
0x180002834  push    rbx
0x180002836  push    rbp
0x180002837  push    rsi
0x180002838  push    rdi
0x180002839  push    r14
0x18000283b  sub     rsp, 20h
0x18000283f  mov     r11, [rdx+4]
0x180002843  mov     rbx, rdx
0x180002846  mov     edi, [rdx+2Ch]
0x180002849  mov     r14, rcx
0x18000284c  mov     rbp, [rdx+0Ch]
0x180002850  mov     esi, edi
0x180002852  and     esi, 4
0x180002855  movzx   r8d, word ptr [r11]
0x180002859  sub     r8d, 1
0x18000285d  jz      short loc_1800028BD
0x18000285f  cmp     r8d, 30h ; '0'
0x180002863  jnz     loc_180002966
0x180002869  mov     rcx, r11
0x18000286c  call    gsm610IsValidFormat
0x180002871  test    eax, eax
0x180002873  jz      loc_180002966
0x180002879  mov     rcx, rbp
0x18000287c  call    pcmIsValidFormat
0x180002881  test    eax, eax
0x180002883  jz      loc_180002966
0x180002889  test    esi, esi
0x18000288b  jnz     short loc_1800028B4
0x18000288d  mov     eax, [r14+3Ch]
0x180002891  lea     r8, gaRateListFormat
0x180002898  movzx   ecx, word ptr [r11+2]
0x18000289d  xor     edx, edx
0x18000289f  lea     rax, [rax+rax*2]
0x1800028a3  mov     eax, [r8+rax*4+8]
0x1800028a8  div     ecx
0x1800028aa  cmp     eax, [r11+4]
0x1800028ae  jb      loc_18000295F
0x1800028b4  lea     rsi, gsm610Decode
0x1800028bb  jmp     short loc_18000290B
0x1800028bd  mov     rcx, r11
0x1800028c0  call    pcmIsValidFormat
0x1800028c5  test    eax, eax
0x1800028c7  jz      loc_180002966
0x1800028cd  mov     rcx, rbp
0x1800028d0  call    gsm610IsValidFormat
0x1800028d5  test    eax, eax
0x1800028d7  jz      loc_180002966
0x1800028dd  test    esi, esi
0x1800028df  jnz     short loc_180002904
0x1800028e1  mov     eax, [r14+38h]
0x1800028e5  lea     r8, gaRateListFormat
0x1800028ec  movzx   ecx, word ptr [r11+2]
0x1800028f1  xor     edx, edx
0x1800028f3  lea     rax, [rax+rax*2]
0x1800028f7  mov     eax, [r8+rax*4+8]
0x1800028fc  div     ecx
0x1800028fe  cmp     eax, [r11+4]
0x180002902  jb      short loc_18000295F
0x180002904  lea     rsi, gsm610Encode
0x18000290b  movzx   eax, word ptr [rbp+2]
0x18000290f  cmp     [r11+2], ax
0x180002914  jnz     short loc_18000295F
0x180002916  mov     eax, [rbp+4]
0x180002919  cmp     [r11+4], eax
0x18000291d  jnz     short loc_18000295F
0x18000291f  test    dil, 1
0x180002923  jz      short loc_180002929
0x180002925  xor     eax, eax
0x180002927  jmp     short loc_18000296B
0x180002929  mov     edx, 28Eh; uBytes
0x18000292e  mov     ecx, 40h ; '@'; uFlags
0x180002933  call    cs:__imp_LocalAlloc
0x180002939  mov     r9, rax
0x18000293c  test    rax, rax
0x18000293f  jnz     short loc_180002947
0x180002941  lea     eax, [r9+7]
0x180002945  jmp     short loc_18000296B
0x180002947  mov     rcx, r9
0x18000294a  mov     [rax], rsi
0x18000294d  call    gsm610Reset
0x180002952  mov     dword ptr [rbx+30h], 0
0x180002959  mov     [rbx+34h], r9
0x18000295d  jmp     short loc_180002925
0x18000295f  mov     eax, 8
0x180002964  jmp     short loc_18000296B
0x180002966  mov     eax, 200h
0x18000296b  add     rsp, 20h
0x18000296f  pop     r14
0x180002971  pop     rdi
0x180002972  pop     rsi
0x180002973  pop     rbp
0x180002974  pop     rbx
0x180002975  retn
```
