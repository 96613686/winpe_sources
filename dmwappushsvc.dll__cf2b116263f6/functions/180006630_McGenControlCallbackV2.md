# McGenControlCallbackV2

- ea: `0x180006630`
- end: `0x18000672f`
- name: `McGenControlCallbackV2`
- size: `255`
- prototype: `void __fastcall(LPCGUID SourceId, ULONG IsEnabled, UCHAR Level, ULONGLONG MatchAnyKeyword, ULONGLONG MatchAllKeyword, PEVENT_FILTER_DESCRIPTOR FilterData, unsigned __int16 *CallbackContext)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180002554`
- `0x180006630`

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
0x180006630  push    rbx
0x180006632  sub     rsp, 20h
0x180006636  mov     r10, [rsp+28h+CallbackContext]
0x18000663b  xor     ebx, ebx
0x18000663d  test    r10, r10
0x180006640  jz      loc_180006729
0x180006646  test    edx, edx
0x180006648  jz      loc_1800066EF
0x18000664e  cmp     edx, 1
0x180006651  jnz     loc_180006729
0x180006657  mov     rax, [rsp+28h+MatchAllKeyword]
0x18000665c  mov     [r10+28h], r8b
0x180006660  mov     r8d, ebx
0x180006663  mov     [r10+18h], rax
0x180006667  mov     [r10+10h], r9
0x18000666b  mov     [r10+24h], edx
0x18000666f  cmp     bx, [r10+2Ah]
0x180006674  jnb     loc_180006729
0x18000667a  mov     rax, [r10+40h]
0x18000667e  mov     cl, [r10+28h]
0x180006682  mov     r9d, r8d
0x180006685  cmp     [r9+rax], cl
0x180006689  jbe     short loc_18000668F
0x18000668b  test    cl, cl
0x18000668d  jnz     short loc_1800066AF
0x18000668f  mov     rax, [r10+38h]
0x180006693  mov     rcx, [rax+r9*8]
0x180006697  test    rcx, rcx
0x18000669a  jz      short loc_1800066B4
0x18000669c  test    [r10+10h], rcx
0x1800066a0  jz      short loc_1800066AF
0x1800066a2  mov     rax, [r10+18h]
0x1800066a6  and     rax, rcx
0x1800066a9  cmp     rax, [r10+18h]
0x1800066ad  jz      short loc_1800066B4
0x1800066af  mov     r11b, bl
0x1800066b2  jmp     short loc_1800066B7
0x1800066b4  mov     r11b, 1
0x1800066b7  mov     rax, [r10+30h]
0x1800066bb  mov     ecx, r8d
0x1800066be  shr     r9, 5
0x1800066c2  mov     edx, 1
0x1800066c7  shl     edx, cl
0x1800066c9  lea     rcx, [rax+r9*4]
0x1800066cd  test    r11b, r11b
0x1800066d0  jz      short loc_1800066D6
0x1800066d2  or      edx, [rcx]
0x1800066d4  jmp     short loc_1800066DA
0x1800066d6  not     edx
0x1800066d8  and     edx, [rcx]
0x1800066da  mov     [rcx], edx
0x1800066dc  inc     r8d
0x1800066df  movzx   eax, word ptr [r10+2Ah]
0x1800066e4  cmp     r8d, eax
0x1800066e7  jb      short loc_18000667A
0x1800066e9  add     rsp, 20h
0x1800066ed  pop     rbx
0x1800066ee  retn
0x1800066ef  mov     [r10+24h], ebx
0x1800066f3  mov     [r10+28h], bl
0x1800066f7  mov     [r10+10h], rbx
0x1800066fb  mov     [r10+18h], rbx
0x1800066ff  cmp     [r10+2Ah], bx
0x180006704  jbe     short loc_180006729
0x180006706  movzx   eax, word ptr [r10+2Ah]
0x18000670b  mov     ecx, 20h ; ' '
0x180006710  dec     eax
0x180006712  cdq
0x180006713  idiv    ecx
0x180006715  mov     rcx, [r10+30h]; void *
0x180006719  xor     edx, edx; Val
0x18000671b  inc     eax
0x18000671d  movsxd  r8, eax
0x180006720  shl     r8, 2; Size
0x180006724  call    memset_0
0x180006729  add     rsp, 20h
0x18000672d  pop     rbx
0x18000672e  retn
```
