# McGenControlCallbackV2

- ea: `0x180008900`
- end: `0x180008a00`
- name: `McGenControlCallbackV2`
- size: `256`
- prototype: `void __fastcall(LPCGUID SourceId, ULONG IsEnabled, UCHAR Level, ULONGLONG MatchAnyKeyword, ULONGLONG MatchAllKeyword, PEVENT_FILTER_DESCRIPTOR FilterData, unsigned __int16 *CallbackContext)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180008900`
- `0x18000fdd6`

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
0x180008900  push    rbx
0x180008902  sub     rsp, 20h
0x180008906  mov     r10, [rsp+28h+CallbackContext]
0x18000890b  xor     ebx, ebx
0x18000890d  test    r10, r10
0x180008910  jz      loc_1800089FA
0x180008916  test    edx, edx
0x180008918  jz      loc_1800089BF
0x18000891e  cmp     edx, 1
0x180008921  jnz     loc_1800089FA
0x180008927  mov     rax, [rsp+28h+MatchAllKeyword]
0x18000892c  mov     [r10+28h], r8b
0x180008930  mov     r8d, ebx
0x180008933  mov     [r10+18h], rax
0x180008937  mov     [r10+10h], r9
0x18000893b  mov     [r10+24h], edx
0x18000893f  cmp     bx, [r10+2Ah]
0x180008944  jnb     loc_1800089FA
0x18000894a  mov     rax, [r10+40h]
0x18000894e  mov     cl, [r10+28h]
0x180008952  mov     r9d, r8d
0x180008955  cmp     [r9+rax], cl
0x180008959  jbe     short loc_18000895F
0x18000895b  test    cl, cl
0x18000895d  jnz     short loc_18000897F
0x18000895f  mov     rax, [r10+38h]
0x180008963  mov     rcx, [rax+r9*8]
0x180008967  test    rcx, rcx
0x18000896a  jz      short loc_180008984
0x18000896c  test    [r10+10h], rcx
0x180008970  jz      short loc_18000897F
0x180008972  mov     rax, [r10+18h]
0x180008976  and     rax, rcx
0x180008979  cmp     rax, [r10+18h]
0x18000897d  jz      short loc_180008984
0x18000897f  mov     r11b, bl
0x180008982  jmp     short loc_180008987
0x180008984  mov     r11b, 1
0x180008987  mov     rax, [r10+30h]
0x18000898b  mov     ecx, r8d
0x18000898e  shr     r9, 5
0x180008992  mov     edx, 1
0x180008997  shl     edx, cl
0x180008999  lea     rcx, [rax+r9*4]
0x18000899d  test    r11b, r11b
0x1800089a0  jz      short loc_1800089A6
0x1800089a2  or      edx, [rcx]
0x1800089a4  jmp     short loc_1800089AA
0x1800089a6  not     edx
0x1800089a8  and     edx, [rcx]
0x1800089aa  mov     [rcx], edx
0x1800089ac  inc     r8d
0x1800089af  movzx   eax, word ptr [r10+2Ah]
0x1800089b4  cmp     r8d, eax
0x1800089b7  jb      short loc_18000894A
0x1800089b9  add     rsp, 20h
0x1800089bd  pop     rbx
0x1800089be  retn
0x1800089bf  mov     [r10+24h], ebx
0x1800089c3  mov     [r10+28h], bl
0x1800089c7  mov     [r10+10h], rbx
0x1800089cb  mov     [r10+18h], rbx
0x1800089cf  cmp     [r10+2Ah], bx
0x1800089d4  jbe     short loc_1800089FA
0x1800089d6  movzx   eax, word ptr [r10+2Ah]
0x1800089db  mov     rcx, [r10+30h]; void *
0x1800089df  dec     eax
0x1800089e1  cdq
0x1800089e2  and     edx, 1Fh
0x1800089e5  add     eax, edx
0x1800089e7  xor     edx, edx; Val
0x1800089e9  sar     eax, 5
0x1800089ec  inc     eax
0x1800089ee  movsxd  r8, eax
0x1800089f1  shl     r8, 2; Size
0x1800089f5  call    memset_0
0x1800089fa  add     rsp, 20h
0x1800089fe  pop     rbx
0x1800089ff  retn
```
