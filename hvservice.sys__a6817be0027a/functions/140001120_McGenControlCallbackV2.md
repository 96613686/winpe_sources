# McGenControlCallbackV2

- ea: `0x140001120`
- end: `0x140001225`
- name: `McGenControlCallbackV2`
- size: `261`
- prototype: `void __stdcall(LPCGUID SourceId, ULONG ControlCode, UCHAR Level, ULONGLONG MatchAnyKeyword, ULONGLONG MatchAllKeyword, PEVENT_FILTER_DESCRIPTOR FilterData, PVOID CallbackContext)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x140001120`
- `0x140002f00`

## pseudocode

```c
void __stdcall McGenControlCallbackV2(
        LPCGUID SourceId,
        ULONG ControlCode,
        UCHAR Level,
        ULONGLONG MatchAnyKeyword,
        ULONGLONG MatchAllKeyword,
        PEVENT_FILTER_DESCRIPTOR FilterData,
        PVOID CallbackContext)
{
  unsigned int v7; // r8d
  unsigned __int8 v8; // cl
  __int64 v9; // r9
  _DWORD *v10; // rdx
  _DWORD *v11; // rdx
  int v12; // eax

  if ( CallbackContext )
  {
    if ( ControlCode )
    {
      if ( ControlCode == 1 )
      {
        *((_BYTE *)CallbackContext + 40) = Level;
        v7 = 0;
        *((_QWORD *)CallbackContext + 2) = MatchAnyKeyword;
        *((_QWORD *)CallbackContext + 3) = MatchAllKeyword;
        for ( *((_DWORD *)CallbackContext + 9) = 1; v7 < *((unsigned __int16 *)CallbackContext + 21); ++v7 )
        {
          v8 = *((_BYTE *)CallbackContext + 40);
          if ( (*(_BYTE *)(v7 + *((_QWORD *)CallbackContext + 8)) <= v8 || !v8)
            && ((v9 = *(_QWORD *)(*((_QWORD *)CallbackContext + 7) + 8LL * v7)) == 0
             || (v9 & *((_QWORD *)CallbackContext + 2)) != 0
             && (v9 & *((_QWORD *)CallbackContext + 3)) == *((_QWORD *)CallbackContext + 3)) )
          {
            v10 = (_DWORD *)(*((_QWORD *)CallbackContext + 6) + 4 * ((unsigned __int64)v7 >> 5));
            *v10 |= 1 << v7;
          }
          else
          {
            v11 = (_DWORD *)(*((_QWORD *)CallbackContext + 6) + 4 * ((unsigned __int64)v7 >> 5));
            *v11 &= ~(1 << v7);
          }
        }
      }
    }
    else
    {
      v12 = *((unsigned __int16 *)CallbackContext + 21);
      *((_DWORD *)CallbackContext + 9) = 0;
      *((_BYTE *)CallbackContext + 40) = 0;
      *((_QWORD *)CallbackContext + 2) = 0;
      *((_QWORD *)CallbackContext + 3) = 0;
      if ( (_WORD)v12 )
        memset(*((void **)CallbackContext + 6), 0, 4LL * ((v12 - 1) / 32 + 1));
    }
  }
}

```

## disassembly

```asm
0x140001120  sub     rsp, 28h
0x140001124  mov     r10, [rsp+28h+CallbackContext]
0x140001129  test    r10, r10
0x14000112c  jnz     short loc_140001134
0x14000112e  add     rsp, 28h
0x140001132  retn
0x140001134  test    edx, edx
0x140001136  jz      loc_1400011E0
0x14000113c  cmp     edx, 1
0x14000113f  jnz     short loc_14000112E
0x140001141  mov     rax, [rsp+28h+MatchAllKeyword]
0x140001146  mov     [r10+28h], r8b
0x14000114a  xor     r8d, r8d
0x14000114d  mov     [r10+10h], r9
0x140001151  mov     [r10+18h], rax
0x140001155  mov     [r10+24h], edx
0x140001159  cmp     r8w, [r10+2Ah]
0x14000115e  jnb     short loc_14000112E
0x140001160  mov     rax, [r10+40h]
0x140001164  movzx   ecx, byte ptr [r10+28h]
0x140001169  mov     edx, r8d
0x14000116c  cmp     [rdx+rax], cl
0x14000116f  ja      short loc_1400011DA
0x140001171  mov     rax, [r10+38h]
0x140001175  mov     r9, [rax+rdx*8]
0x140001179  test    r9, r9
0x14000117c  jnz     short loc_1400011A9
0x14000117e  mov     rax, [r10+30h]
0x140001182  mov     ecx, r8d
0x140001185  shr     rdx, 5
0x140001189  lea     rdx, [rax+rdx*4]
0x14000118d  mov     eax, 1
0x140001192  shl     eax, cl
0x140001194  or      [rdx], eax
0x140001196  movzx   eax, word ptr [r10+2Ah]
0x14000119b  inc     r8d
0x14000119e  cmp     r8d, eax
0x1400011a1  jb      short loc_140001160
0x1400011a3  add     rsp, 28h
0x1400011a7  retn
0x1400011a9  test    [r10+10h], r9
0x1400011ad  jz      short loc_1400011BE
0x1400011af  mov     rcx, [r10+18h]
0x1400011b3  mov     rax, rcx
0x1400011b6  and     rax, r9
0x1400011b9  cmp     rax, rcx
0x1400011bc  jz      short loc_14000117E
0x1400011be  mov     rax, [r10+30h]
0x1400011c2  mov     ecx, r8d
0x1400011c5  shr     rdx, 5
0x1400011c9  lea     rdx, [rax+rdx*4]
0x1400011cd  mov     eax, 1
0x1400011d2  shl     eax, cl
0x1400011d4  not     eax
0x1400011d6  and     [rdx], eax
0x1400011d8  jmp     short loc_140001196
0x1400011da  test    cl, cl
0x1400011dc  jnz     short loc_1400011BE
0x1400011de  jmp     short loc_140001171
0x1400011e0  movzx   eax, word ptr [r10+2Ah]
0x1400011e5  xor     r8d, r8d
0x1400011e8  mov     [r10+24h], r8d
0x1400011ec  mov     [r10+28h], r8b
0x1400011f0  mov     [r10+10h], r8
0x1400011f4  mov     [r10+18h], r8
0x1400011f8  test    ax, ax
0x1400011fb  jz      loc_14000112E
0x140001201  mov     rcx, [r10+30h]; void *
0x140001205  dec     eax
0x140001207  cdq
0x140001208  and     edx, 1Fh
0x14000120b  add     eax, edx
0x14000120d  xor     edx, edx; Val
0x14000120f  sar     eax, 5
0x140001212  inc     eax
0x140001214  movsxd  r8, eax
0x140001217  shl     r8, 2; Size
0x14000121b  call    memset
0x140001220  jmp     loc_14000112E
```
