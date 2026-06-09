# McGenControlCallbackV2

- ea: `0x1800091a0`
- end: `0x1800092a2`
- name: `McGenControlCallbackV2`
- size: `258`
- prototype: `void __fastcall(LPCGUID SourceId, ULONG IsEnabled, UCHAR Level, ULONGLONG MatchAnyKeyword, ULONGLONG MatchAllKeyword, PEVENT_FILTER_DESCRIPTOR FilterData, unsigned __int16 *CallbackContext)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x1800091a0`
- `0x180011957`

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
  unsigned int v7; // eax
  unsigned __int8 v8; // dl
  __int64 v9; // r9
  _DWORD *v10; // r8
  _DWORD *v11; // r8
  int v12; // eax

  if ( CallbackContext )
  {
    if ( IsEnabled )
    {
      if ( IsEnabled == 1 )
      {
        *((_QWORD *)CallbackContext + 3) = MatchAllKeyword;
        v7 = 0;
        *((_BYTE *)CallbackContext + 40) = Level;
        *((_QWORD *)CallbackContext + 2) = MatchAnyKeyword;
        for ( *((_DWORD *)CallbackContext + 9) = 1; v7 < CallbackContext[21]; ++v7 )
        {
          v8 = *((_BYTE *)CallbackContext + 40);
          if ( (*(_BYTE *)(v7 + *((_QWORD *)CallbackContext + 8)) <= v8 || !v8)
            && ((v9 = *(_QWORD *)(*((_QWORD *)CallbackContext + 7) + 8LL * v7)) == 0
             || (v9 & *((_QWORD *)CallbackContext + 2)) != 0
             && (v9 & *((_QWORD *)CallbackContext + 3)) == *((_QWORD *)CallbackContext + 3)) )
          {
            v11 = (_DWORD *)(*((_QWORD *)CallbackContext + 6) + 4 * ((unsigned __int64)v7 >> 5));
            *v11 |= 1 << v7;
          }
          else
          {
            v10 = (_DWORD *)(*((_QWORD *)CallbackContext + 6) + 4 * ((unsigned __int64)v7 >> 5));
            *v10 &= ~(1 << v7);
          }
        }
      }
    }
    else
    {
      *((_DWORD *)CallbackContext + 9) = 0;
      *((_BYTE *)CallbackContext + 40) = 0;
      *((_QWORD *)CallbackContext + 2) = 0;
      *((_QWORD *)CallbackContext + 3) = 0;
      v12 = CallbackContext[21];
      if ( (_WORD)v12 )
        memset_0(*((void **)CallbackContext + 6), 0, 4LL * ((v12 - 1) / 32 + 1));
    }
  }
}

```

## disassembly

```asm
0x1800091a0  mov     r10, [rsp+CallbackContext]
0x1800091a5  test    r10, r10
0x1800091a8  jz      locret_1800092A1
0x1800091ae  test    edx, edx
0x1800091b0  jz      loc_180009266
0x1800091b6  cmp     edx, 1
0x1800091b9  jnz     locret_1800092A1
0x1800091bf  mov     rax, [rsp+MatchAllKeyword]
0x1800091c4  mov     [r10+18h], rax
0x1800091c8  xor     eax, eax
0x1800091ca  mov     [r10+28h], r8b
0x1800091ce  mov     [r10+10h], r9
0x1800091d2  mov     [r10+24h], edx
0x1800091d6  cmp     ax, [r10+2Ah]
0x1800091db  jnb     locret_1800092A1
0x1800091e1  nop     dword ptr [rax+00h]
0x1800091e5  nop     word ptr [rax+rax+00000000h]
0x1800091f0  mov     rcx, [r10+40h]
0x1800091f4  movzx   edx, byte ptr [r10+28h]
0x1800091f9  mov     r8d, eax
0x1800091fc  cmp     [r8+rcx], dl
0x180009200  jbe     short loc_180009206
0x180009202  test    dl, dl
0x180009204  jnz     short loc_180009226
0x180009206  mov     rcx, [r10+38h]
0x18000920a  mov     r9, [rcx+r8*8]
0x18000920e  test    r9, r9
0x180009211  jz      short loc_180009242
0x180009213  test    [r10+10h], r9
0x180009217  jz      short loc_180009226
0x180009219  mov     rcx, [r10+18h]
0x18000921d  and     rcx, r9
0x180009220  cmp     rcx, [r10+18h]
0x180009224  jz      short loc_180009242
0x180009226  mov     rcx, [r10+30h]
0x18000922a  mov     edx, 1
0x18000922f  shr     r8, 5
0x180009233  lea     r8, [rcx+r8*4]
0x180009237  mov     ecx, eax
0x180009239  shl     edx, cl
0x18000923b  not     edx
0x18000923d  and     [r8], edx
0x180009240  jmp     short loc_18000925A
0x180009242  mov     rcx, [r10+30h]
0x180009246  mov     edx, 1
0x18000924b  shr     r8, 5
0x18000924f  lea     r8, [rcx+r8*4]
0x180009253  mov     ecx, eax
0x180009255  shl     edx, cl
0x180009257  or      [r8], edx
0x18000925a  movzx   ecx, word ptr [r10+2Ah]
0x18000925f  inc     eax
0x180009261  cmp     eax, ecx
0x180009263  jb      short loc_1800091F0
0x180009265  retn
0x180009266  xor     eax, eax
0x180009268  mov     [r10+24h], eax
0x18000926c  mov     [r10+28h], al
0x180009270  mov     [r10+10h], rax
0x180009274  mov     [r10+18h], rax
0x180009278  movzx   eax, word ptr [r10+2Ah]
0x18000927d  test    ax, ax
0x180009280  jz      short locret_1800092A1
0x180009282  mov     rcx, [r10+30h]; void *
0x180009286  dec     eax
0x180009288  cdq
0x180009289  and     edx, 1Fh
0x18000928c  add     eax, edx
0x18000928e  xor     edx, edx; Val
0x180009290  sar     eax, 5
0x180009293  inc     eax
0x180009295  movsxd  r8, eax
0x180009298  shl     r8, 2; Size
0x18000929c  jmp     memset_0
0x1800092a1  retn
```
