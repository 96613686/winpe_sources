# McGenControlCallbackV2

- ea: `0x180018930`
- end: `0x180018a31`
- name: `McGenControlCallbackV2`
- size: `257`
- prototype: `void __fastcall(LPCGUID SourceId, ULONG IsEnabled, UCHAR Level, ULONGLONG MatchAnyKeyword, ULONGLONG MatchAllKeyword, PEVENT_FILTER_DESCRIPTOR FilterData, unsigned __int16 *CallbackContext)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180018930`
- `0x18001cc3e`

## pseudocode

```c
void __fastcall McGenControlCallbackV2(
        LPCGUID SourceId,
        ULONG IsEnabled,
        UCHAR Level,
        ULONGLONG MatchAnyKeyword,
        ULONGLONG MatchAllKeyword,
        PEVENT_FILTER_DESCRIPTOR FilterData,
        unsigned __int16 *CallbackContext)
{
  unsigned int v7; // r8d
  unsigned __int8 v8; // cl
  __int64 v9; // rcx
  bool v10; // r11
  int v11; // edx
  int *v12; // rcx
  int v13; // edx

  if ( CallbackContext )
  {
    if ( IsEnabled )
    {
      if ( IsEnabled == 1 )
      {
        *((_BYTE *)CallbackContext + 40) = Level;
        v7 = 0;
        *((_QWORD *)CallbackContext + 3) = MatchAllKeyword;
        *((_QWORD *)CallbackContext + 2) = MatchAnyKeyword;
        for ( *((_DWORD *)CallbackContext + 9) = 1; v7 < CallbackContext[21]; ++v7 )
        {
          v8 = *((_BYTE *)CallbackContext + 40);
          v10 = 0;
          if ( *(_BYTE *)(v7 + *((_QWORD *)CallbackContext + 8)) <= v8 || !v8 )
          {
            v9 = *(_QWORD *)(*((_QWORD *)CallbackContext + 7) + 8LL * v7);
            if ( !v9
              || (v9 & *((_QWORD *)CallbackContext + 2)) != 0
              && (v9 & *((_QWORD *)CallbackContext + 3)) == *((_QWORD *)CallbackContext + 3) )
            {
              v10 = 1;
            }
          }
          v11 = 1 << v7;
          v12 = (int *)(*((_QWORD *)CallbackContext + 6) + 4 * ((unsigned __int64)v7 >> 5));
          if ( v10 )
            v13 = *v12 | v11;
          else
            v13 = *v12 & ~v11;
          *v12 = v13;
        }
      }
    }
    else
    {
      *((_DWORD *)CallbackContext + 9) = 0;
      *((_BYTE *)CallbackContext + 40) = 0;
      *((_QWORD *)CallbackContext + 2) = 0;
      *((_QWORD *)CallbackContext + 3) = 0;
      if ( CallbackContext[21] )
        memset_0(*((void **)CallbackContext + 6), 0, 4LL * ((CallbackContext[21] - 1) / 32 + 1));
    }
  }
}

```

## disassembly

```asm
0x180018930  push    rbx
0x180018932  sub     rsp, 20h
0x180018936  mov     r10, [rsp+28h+CallbackContext]
0x18001893b  xor     ebx, ebx
0x18001893d  test    r10, r10
0x180018940  jz      loc_180018A2A
0x180018946  test    edx, edx
0x180018948  jz      loc_1800189F0
0x18001894e  cmp     edx, 1
0x180018951  jnz     loc_180018A2A
0x180018957  mov     rax, [rsp+28h+MatchAllKeyword]
0x18001895c  mov     [r10+28h], r8b
0x180018960  mov     r8d, ebx
0x180018963  mov     [r10+18h], rax
0x180018967  mov     [r10+10h], r9
0x18001896b  mov     [r10+24h], edx
0x18001896f  cmp     bx, [r10+2Ah]
0x180018974  jnb     loc_180018A2A
0x18001897a  mov     rax, [r10+40h]
0x18001897e  mov     cl, [r10+28h]
0x180018982  mov     r9d, r8d
0x180018985  cmp     [r9+rax], cl
0x180018989  jbe     short loc_18001898F
0x18001898b  test    cl, cl
0x18001898d  jnz     short loc_1800189AF
0x18001898f  mov     rax, [r10+38h]
0x180018993  mov     rcx, [rax+r9*8]
0x180018997  test    rcx, rcx
0x18001899a  jz      short loc_1800189B4
0x18001899c  test    [r10+10h], rcx
0x1800189a0  jz      short loc_1800189AF
0x1800189a2  mov     rax, [r10+18h]
0x1800189a6  and     rax, rcx
0x1800189a9  cmp     rax, [r10+18h]
0x1800189ad  jz      short loc_1800189B4
0x1800189af  mov     r11b, bl
0x1800189b2  jmp     short loc_1800189B7
0x1800189b4  mov     r11b, 1
0x1800189b7  mov     rax, [r10+30h]
0x1800189bb  mov     ecx, r8d
0x1800189be  shr     r9, 5
0x1800189c2  mov     edx, 1
0x1800189c7  shl     edx, cl
0x1800189c9  lea     rcx, [rax+r9*4]
0x1800189cd  test    r11b, r11b
0x1800189d0  jz      short loc_1800189D6
0x1800189d2  or      edx, [rcx]
0x1800189d4  jmp     short loc_1800189DA
0x1800189d6  not     edx
0x1800189d8  and     edx, [rcx]
0x1800189da  mov     [rcx], edx
0x1800189dc  inc     r8d
0x1800189df  movzx   eax, word ptr [r10+2Ah]
0x1800189e4  cmp     r8d, eax
0x1800189e7  jb      short loc_18001897A
0x1800189e9  add     rsp, 20h
0x1800189ed  pop     rbx
0x1800189ee  retn
0x1800189f0  mov     [r10+24h], ebx
0x1800189f4  mov     [r10+28h], bl
0x1800189f8  mov     [r10+10h], rbx
0x1800189fc  mov     [r10+18h], rbx
0x180018a00  cmp     [r10+2Ah], bx
0x180018a05  jbe     short loc_180018A2A
0x180018a07  movzx   eax, word ptr [r10+2Ah]
0x180018a0c  mov     ecx, 20h ; ' '
0x180018a11  dec     eax
0x180018a13  cdq
0x180018a14  idiv    ecx
0x180018a16  mov     rcx, [r10+30h]; void *
0x180018a1a  xor     edx, edx; Val
0x180018a1c  inc     eax
0x180018a1e  movsxd  r8, eax
0x180018a21  shl     r8, 2; Size
0x180018a25  call    memset_0
0x180018a2a  add     rsp, 20h
0x180018a2e  pop     rbx
0x180018a2f  retn
```
