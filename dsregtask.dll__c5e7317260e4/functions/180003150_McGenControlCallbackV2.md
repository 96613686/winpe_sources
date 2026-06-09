# McGenControlCallbackV2

- ea: `0x180003150`
- end: `0x180003250`
- name: `McGenControlCallbackV2`
- size: `256`
- prototype: `void __fastcall(LPCGUID SourceId, ULONG IsEnabled, UCHAR Level, ULONGLONG MatchAnyKeyword, ULONGLONG MatchAllKeyword, PEVENT_FILTER_DESCRIPTOR FilterData, unsigned __int16 *CallbackContext)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180001d96`
- `0x180003150`

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
0x180003150  push    rbx
0x180003152  sub     rsp, 20h
0x180003156  mov     r10, [rsp+28h+CallbackContext]
0x18000315b  xor     ebx, ebx
0x18000315d  test    r10, r10
0x180003160  jz      loc_18000324A
0x180003166  test    edx, edx
0x180003168  jz      loc_18000320F
0x18000316e  cmp     edx, 1
0x180003171  jnz     loc_18000324A
0x180003177  mov     rax, [rsp+28h+MatchAllKeyword]
0x18000317c  mov     [r10+28h], r8b
0x180003180  mov     r8d, ebx
0x180003183  mov     [r10+18h], rax
0x180003187  mov     [r10+10h], r9
0x18000318b  mov     [r10+24h], edx
0x18000318f  cmp     bx, [r10+2Ah]
0x180003194  jnb     loc_18000324A
0x18000319a  mov     rax, [r10+40h]
0x18000319e  mov     cl, [r10+28h]
0x1800031a2  mov     r9d, r8d
0x1800031a5  cmp     [r9+rax], cl
0x1800031a9  jbe     short loc_1800031AF
0x1800031ab  test    cl, cl
0x1800031ad  jnz     short loc_1800031CF
0x1800031af  mov     rax, [r10+38h]
0x1800031b3  mov     rcx, [rax+r9*8]
0x1800031b7  test    rcx, rcx
0x1800031ba  jz      short loc_1800031D4
0x1800031bc  test    [r10+10h], rcx
0x1800031c0  jz      short loc_1800031CF
0x1800031c2  mov     rax, [r10+18h]
0x1800031c6  and     rax, rcx
0x1800031c9  cmp     rax, [r10+18h]
0x1800031cd  jz      short loc_1800031D4
0x1800031cf  mov     r11b, bl
0x1800031d2  jmp     short loc_1800031D7
0x1800031d4  mov     r11b, 1
0x1800031d7  mov     rax, [r10+30h]
0x1800031db  mov     ecx, r8d
0x1800031de  shr     r9, 5
0x1800031e2  mov     edx, 1
0x1800031e7  shl     edx, cl
0x1800031e9  lea     rcx, [rax+r9*4]
0x1800031ed  test    r11b, r11b
0x1800031f0  jz      short loc_1800031F6
0x1800031f2  or      edx, [rcx]
0x1800031f4  jmp     short loc_1800031FA
0x1800031f6  not     edx
0x1800031f8  and     edx, [rcx]
0x1800031fa  mov     [rcx], edx
0x1800031fc  inc     r8d
0x1800031ff  movzx   eax, word ptr [r10+2Ah]
0x180003204  cmp     r8d, eax
0x180003207  jb      short loc_18000319A
0x180003209  add     rsp, 20h
0x18000320d  pop     rbx
0x18000320e  retn
0x18000320f  mov     [r10+24h], ebx
0x180003213  mov     [r10+28h], bl
0x180003217  mov     [r10+10h], rbx
0x18000321b  mov     [r10+18h], rbx
0x18000321f  cmp     [r10+2Ah], bx
0x180003224  jbe     short loc_18000324A
0x180003226  movzx   eax, word ptr [r10+2Ah]
0x18000322b  mov     rcx, [r10+30h]; void *
0x18000322f  dec     eax
0x180003231  cdq
0x180003232  and     edx, 1Fh
0x180003235  add     eax, edx
0x180003237  xor     edx, edx; Val
0x180003239  sar     eax, 5
0x18000323c  inc     eax
0x18000323e  movsxd  r8, eax
0x180003241  shl     r8, 2; Size
0x180003245  call    memset_0
0x18000324a  add     rsp, 20h
0x18000324e  pop     rbx
0x18000324f  retn
```
