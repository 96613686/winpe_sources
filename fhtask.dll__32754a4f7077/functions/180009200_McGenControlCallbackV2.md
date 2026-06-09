# McGenControlCallbackV2

- ea: `0x180009200`
- end: `0x180009300`
- name: `McGenControlCallbackV2`
- size: `256`
- prototype: `void __fastcall(LPCGUID SourceId, ULONG IsEnabled, UCHAR Level, ULONGLONG MatchAnyKeyword, ULONGLONG MatchAllKeyword, PEVENT_FILTER_DESCRIPTOR FilterData, unsigned __int16 *CallbackContext)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180009200`
- `0x1800099ce`

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
0x180009200  push    rbx
0x180009202  sub     rsp, 20h
0x180009206  mov     r10, [rsp+28h+CallbackContext]
0x18000920b  xor     ebx, ebx
0x18000920d  test    r10, r10
0x180009210  jz      loc_1800092FA
0x180009216  test    edx, edx
0x180009218  jz      loc_1800092BF
0x18000921e  cmp     edx, 1
0x180009221  jnz     loc_1800092FA
0x180009227  mov     rax, [rsp+28h+MatchAllKeyword]
0x18000922c  mov     [r10+28h], r8b
0x180009230  mov     r8d, ebx
0x180009233  mov     [r10+18h], rax
0x180009237  mov     [r10+10h], r9
0x18000923b  mov     [r10+24h], edx
0x18000923f  cmp     bx, [r10+2Ah]
0x180009244  jnb     loc_1800092FA
0x18000924a  mov     rax, [r10+40h]
0x18000924e  mov     cl, [r10+28h]
0x180009252  mov     r9d, r8d
0x180009255  cmp     [r9+rax], cl
0x180009259  jbe     short loc_18000925F
0x18000925b  test    cl, cl
0x18000925d  jnz     short loc_18000927F
0x18000925f  mov     rax, [r10+38h]
0x180009263  mov     rcx, [rax+r9*8]
0x180009267  test    rcx, rcx
0x18000926a  jz      short loc_180009284
0x18000926c  test    [r10+10h], rcx
0x180009270  jz      short loc_18000927F
0x180009272  mov     rax, [r10+18h]
0x180009276  and     rax, rcx
0x180009279  cmp     rax, [r10+18h]
0x18000927d  jz      short loc_180009284
0x18000927f  mov     r11b, bl
0x180009282  jmp     short loc_180009287
0x180009284  mov     r11b, 1
0x180009287  mov     rax, [r10+30h]
0x18000928b  mov     ecx, r8d
0x18000928e  shr     r9, 5
0x180009292  mov     edx, 1
0x180009297  shl     edx, cl
0x180009299  lea     rcx, [rax+r9*4]
0x18000929d  test    r11b, r11b
0x1800092a0  jz      short loc_1800092A6
0x1800092a2  or      edx, [rcx]
0x1800092a4  jmp     short loc_1800092AA
0x1800092a6  not     edx
0x1800092a8  and     edx, [rcx]
0x1800092aa  mov     [rcx], edx
0x1800092ac  inc     r8d
0x1800092af  movzx   eax, word ptr [r10+2Ah]
0x1800092b4  cmp     r8d, eax
0x1800092b7  jb      short loc_18000924A
0x1800092b9  add     rsp, 20h
0x1800092bd  pop     rbx
0x1800092be  retn
0x1800092bf  mov     [r10+24h], ebx
0x1800092c3  mov     [r10+28h], bl
0x1800092c7  mov     [r10+10h], rbx
0x1800092cb  mov     [r10+18h], rbx
0x1800092cf  cmp     [r10+2Ah], bx
0x1800092d4  jbe     short loc_1800092FA
0x1800092d6  movzx   eax, word ptr [r10+2Ah]
0x1800092db  mov     rcx, [r10+30h]; void *
0x1800092df  dec     eax
0x1800092e1  cdq
0x1800092e2  and     edx, 1Fh
0x1800092e5  add     eax, edx
0x1800092e7  xor     edx, edx; Val
0x1800092e9  sar     eax, 5
0x1800092ec  inc     eax
0x1800092ee  movsxd  r8, eax
0x1800092f1  shl     r8, 2; Size
0x1800092f5  call    memset_0
0x1800092fa  add     rsp, 20h
0x1800092fe  pop     rbx
0x1800092ff  retn
```
