# McGenControlCallbackV2

- ea: `0x180008460`
- end: `0x180008560`
- name: `McGenControlCallbackV2`
- size: `256`
- prototype: `void __fastcall(LPCGUID SourceId, ULONG IsEnabled, UCHAR Level, ULONGLONG MatchAnyKeyword, ULONGLONG MatchAllKeyword, PEVENT_FILTER_DESCRIPTOR FilterData, unsigned __int16 *CallbackContext)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180001f9e`
- `0x180008460`

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
0x180008460  push    rbx
0x180008462  sub     rsp, 20h
0x180008466  mov     r10, [rsp+28h+CallbackContext]
0x18000846b  xor     ebx, ebx
0x18000846d  test    r10, r10
0x180008470  jz      loc_18000855A
0x180008476  test    edx, edx
0x180008478  jz      loc_18000851F
0x18000847e  cmp     edx, 1
0x180008481  jnz     loc_18000855A
0x180008487  mov     rax, [rsp+28h+MatchAllKeyword]
0x18000848c  mov     [r10+28h], r8b
0x180008490  mov     r8d, ebx
0x180008493  mov     [r10+18h], rax
0x180008497  mov     [r10+10h], r9
0x18000849b  mov     [r10+24h], edx
0x18000849f  cmp     bx, [r10+2Ah]
0x1800084a4  jnb     loc_18000855A
0x1800084aa  mov     rax, [r10+40h]
0x1800084ae  mov     cl, [r10+28h]
0x1800084b2  mov     r9d, r8d
0x1800084b5  cmp     [r9+rax], cl
0x1800084b9  jbe     short loc_1800084BF
0x1800084bb  test    cl, cl
0x1800084bd  jnz     short loc_1800084DF
0x1800084bf  mov     rax, [r10+38h]
0x1800084c3  mov     rcx, [rax+r9*8]
0x1800084c7  test    rcx, rcx
0x1800084ca  jz      short loc_1800084E4
0x1800084cc  test    [r10+10h], rcx
0x1800084d0  jz      short loc_1800084DF
0x1800084d2  mov     rax, [r10+18h]
0x1800084d6  and     rax, rcx
0x1800084d9  cmp     rax, [r10+18h]
0x1800084dd  jz      short loc_1800084E4
0x1800084df  mov     r11b, bl
0x1800084e2  jmp     short loc_1800084E7
0x1800084e4  mov     r11b, 1
0x1800084e7  mov     rax, [r10+30h]
0x1800084eb  mov     ecx, r8d
0x1800084ee  shr     r9, 5
0x1800084f2  mov     edx, 1
0x1800084f7  shl     edx, cl
0x1800084f9  lea     rcx, [rax+r9*4]
0x1800084fd  test    r11b, r11b
0x180008500  jz      short loc_180008506
0x180008502  or      edx, [rcx]
0x180008504  jmp     short loc_18000850A
0x180008506  not     edx
0x180008508  and     edx, [rcx]
0x18000850a  mov     [rcx], edx
0x18000850c  inc     r8d
0x18000850f  movzx   eax, word ptr [r10+2Ah]
0x180008514  cmp     r8d, eax
0x180008517  jb      short loc_1800084AA
0x180008519  add     rsp, 20h
0x18000851d  pop     rbx
0x18000851e  retn
0x18000851f  mov     [r10+24h], ebx
0x180008523  mov     [r10+28h], bl
0x180008527  mov     [r10+10h], rbx
0x18000852b  mov     [r10+18h], rbx
0x18000852f  cmp     [r10+2Ah], bx
0x180008534  jbe     short loc_18000855A
0x180008536  movzx   eax, word ptr [r10+2Ah]
0x18000853b  mov     rcx, [r10+30h]; void *
0x18000853f  dec     eax
0x180008541  cdq
0x180008542  and     edx, 1Fh
0x180008545  add     eax, edx
0x180008547  xor     edx, edx; Val
0x180008549  sar     eax, 5
0x18000854c  inc     eax
0x18000854e  movsxd  r8, eax
0x180008551  shl     r8, 2; Size
0x180008555  call    memset_0
0x18000855a  add     rsp, 20h
0x18000855e  pop     rbx
0x18000855f  retn
```
