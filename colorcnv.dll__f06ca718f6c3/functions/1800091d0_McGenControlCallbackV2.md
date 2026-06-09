# McGenControlCallbackV2

- ea: `0x1800091d0`
- end: `0x1800092cf`
- name: `McGenControlCallbackV2`
- size: `255`
- prototype: `void __stdcall(LPCGUID SourceId, ULONG IsEnabled, UCHAR Level, ULONGLONG MatchAnyKeyword, ULONGLONG MatchAllKeyword, PEVENT_FILTER_DESCRIPTOR FilterData, PVOID CallbackContext)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x1800091d0`
- `0x18000b468`

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
0x1800091d0  push    rbx
0x1800091d2  sub     rsp, 20h
0x1800091d6  mov     r10, [rsp+28h+CallbackContext]
0x1800091db  xor     ebx, ebx
0x1800091dd  test    r10, r10
0x1800091e0  jz      loc_1800092C9
0x1800091e6  test    edx, edx
0x1800091e8  jz      loc_18000928F
0x1800091ee  cmp     edx, 1
0x1800091f1  jnz     loc_1800092C9
0x1800091f7  mov     rax, [rsp+28h+MatchAllKeyword]
0x1800091fc  mov     [r10+28h], r8b
0x180009200  mov     r8d, ebx
0x180009203  mov     [r10+18h], rax
0x180009207  mov     [r10+10h], r9
0x18000920b  mov     [r10+24h], edx
0x18000920f  cmp     bx, [r10+2Ah]
0x180009214  jnb     loc_1800092C9
0x18000921a  mov     rax, [r10+40h]
0x18000921e  mov     cl, [r10+28h]
0x180009222  mov     r9d, r8d
0x180009225  cmp     [r9+rax], cl
0x180009229  jbe     short loc_18000922F
0x18000922b  test    cl, cl
0x18000922d  jnz     short loc_18000924F
0x18000922f  mov     rax, [r10+38h]
0x180009233  mov     rcx, [rax+r9*8]
0x180009237  test    rcx, rcx
0x18000923a  jz      short loc_180009254
0x18000923c  test    [r10+10h], rcx
0x180009240  jz      short loc_18000924F
0x180009242  mov     rax, [r10+18h]
0x180009246  and     rax, rcx
0x180009249  cmp     rax, [r10+18h]
0x18000924d  jz      short loc_180009254
0x18000924f  mov     r11b, bl
0x180009252  jmp     short loc_180009257
0x180009254  mov     r11b, 1
0x180009257  mov     rax, [r10+30h]
0x18000925b  mov     ecx, r8d
0x18000925e  shr     r9, 5
0x180009262  mov     edx, 1
0x180009267  shl     edx, cl
0x180009269  lea     rcx, [rax+r9*4]
0x18000926d  test    r11b, r11b
0x180009270  jz      short loc_180009276
0x180009272  or      edx, [rcx]
0x180009274  jmp     short loc_18000927A
0x180009276  not     edx
0x180009278  and     edx, [rcx]
0x18000927a  mov     [rcx], edx
0x18000927c  inc     r8d
0x18000927f  movzx   eax, word ptr [r10+2Ah]
0x180009284  cmp     r8d, eax
0x180009287  jb      short loc_18000921A
0x180009289  add     rsp, 20h
0x18000928d  pop     rbx
0x18000928e  retn
0x18000928f  mov     [r10+24h], ebx
0x180009293  mov     [r10+28h], bl
0x180009297  mov     [r10+10h], rbx
0x18000929b  mov     [r10+18h], rbx
0x18000929f  cmp     [r10+2Ah], bx
0x1800092a4  jbe     short loc_1800092C9
0x1800092a6  movzx   eax, word ptr [r10+2Ah]
0x1800092ab  mov     ecx, 20h ; ' '
0x1800092b0  dec     eax
0x1800092b2  cdq
0x1800092b3  idiv    ecx
0x1800092b5  mov     rcx, [r10+30h]; void *
0x1800092b9  xor     edx, edx; Val
0x1800092bb  inc     eax
0x1800092bd  movsxd  r8, eax
0x1800092c0  shl     r8, 2; Size
0x1800092c4  call    memset_0
0x1800092c9  add     rsp, 20h
0x1800092cd  pop     rbx
0x1800092ce  retn
```
