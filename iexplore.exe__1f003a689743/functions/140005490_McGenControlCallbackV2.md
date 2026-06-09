# McGenControlCallbackV2

- ea: `0x140005490`
- end: `0x14000558f`
- name: `McGenControlCallbackV2`
- size: `255`
- prototype: `void __stdcall(LPCGUID SourceId, ULONG IsEnabled, UCHAR Level, ULONGLONG MatchAnyKeyword, ULONGLONG MatchAllKeyword, PEVENT_FILTER_DESCRIPTOR FilterData, PVOID CallbackContext)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x140001fc3`
- `0x140005490`

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
0x140005490  push    rbx
0x140005492  sub     rsp, 20h
0x140005496  mov     r10, [rsp+28h+CallbackContext]
0x14000549b  xor     ebx, ebx
0x14000549d  test    r10, r10
0x1400054a0  jz      loc_140005589
0x1400054a6  test    edx, edx
0x1400054a8  jz      loc_14000554F
0x1400054ae  cmp     edx, 1
0x1400054b1  jnz     loc_140005589
0x1400054b7  mov     rax, [rsp+28h+MatchAllKeyword]
0x1400054bc  mov     [r10+28h], r8b
0x1400054c0  mov     r8d, ebx
0x1400054c3  mov     [r10+18h], rax
0x1400054c7  mov     [r10+10h], r9
0x1400054cb  mov     [r10+24h], edx
0x1400054cf  cmp     bx, [r10+2Ah]
0x1400054d4  jnb     loc_140005589
0x1400054da  mov     rax, [r10+40h]
0x1400054de  mov     cl, [r10+28h]
0x1400054e2  mov     r9d, r8d
0x1400054e5  cmp     [r9+rax], cl
0x1400054e9  jbe     short loc_1400054EF
0x1400054eb  test    cl, cl
0x1400054ed  jnz     short loc_14000550F
0x1400054ef  mov     rax, [r10+38h]
0x1400054f3  mov     rcx, [rax+r9*8]
0x1400054f7  test    rcx, rcx
0x1400054fa  jz      short loc_140005514
0x1400054fc  test    [r10+10h], rcx
0x140005500  jz      short loc_14000550F
0x140005502  mov     rax, [r10+18h]
0x140005506  and     rax, rcx
0x140005509  cmp     rax, [r10+18h]
0x14000550d  jz      short loc_140005514
0x14000550f  mov     r11b, bl
0x140005512  jmp     short loc_140005517
0x140005514  mov     r11b, 1
0x140005517  mov     rax, [r10+30h]
0x14000551b  mov     ecx, r8d
0x14000551e  shr     r9, 5
0x140005522  mov     edx, 1
0x140005527  shl     edx, cl
0x140005529  lea     rcx, [rax+r9*4]
0x14000552d  test    r11b, r11b
0x140005530  jz      short loc_140005536
0x140005532  or      edx, [rcx]
0x140005534  jmp     short loc_14000553A
0x140005536  not     edx
0x140005538  and     edx, [rcx]
0x14000553a  mov     [rcx], edx
0x14000553c  inc     r8d
0x14000553f  movzx   eax, word ptr [r10+2Ah]
0x140005544  cmp     r8d, eax
0x140005547  jb      short loc_1400054DA
0x140005549  add     rsp, 20h
0x14000554d  pop     rbx
0x14000554e  retn
0x14000554f  mov     [r10+24h], ebx
0x140005553  mov     [r10+28h], bl
0x140005557  mov     [r10+10h], rbx
0x14000555b  mov     [r10+18h], rbx
0x14000555f  cmp     [r10+2Ah], bx
0x140005564  jbe     short loc_140005589
0x140005566  movzx   eax, word ptr [r10+2Ah]
0x14000556b  mov     ecx, 20h ; ' '
0x140005570  dec     eax
0x140005572  cdq
0x140005573  idiv    ecx
0x140005575  mov     rcx, [r10+30h]; void *
0x140005579  xor     edx, edx; Val
0x14000557b  inc     eax
0x14000557d  movsxd  r8, eax
0x140005580  shl     r8, 2; Size
0x140005584  call    memset_0
0x140005589  add     rsp, 20h
0x14000558d  pop     rbx
0x14000558e  retn
```
