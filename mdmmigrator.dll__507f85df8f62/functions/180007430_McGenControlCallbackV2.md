# McGenControlCallbackV2

- ea: `0x180007430`
- end: `0x180007530`
- name: `McGenControlCallbackV2`
- size: `256`
- prototype: `void __fastcall(LPCGUID SourceId, ULONG IsEnabled, UCHAR Level, ULONGLONG MatchAnyKeyword, ULONGLONG MatchAllKeyword, PEVENT_FILTER_DESCRIPTOR FilterData, unsigned __int16 *CallbackContext)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180002cbc`
- `0x180007430`

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
0x180007430  push    rbx
0x180007432  sub     rsp, 20h
0x180007436  mov     r10, [rsp+28h+CallbackContext]
0x18000743b  xor     ebx, ebx
0x18000743d  test    r10, r10
0x180007440  jz      loc_18000752A
0x180007446  test    edx, edx
0x180007448  jz      loc_1800074EF
0x18000744e  cmp     edx, 1
0x180007451  jnz     loc_18000752A
0x180007457  mov     rax, [rsp+28h+MatchAllKeyword]
0x18000745c  mov     [r10+28h], r8b
0x180007460  mov     r8d, ebx
0x180007463  mov     [r10+18h], rax
0x180007467  mov     [r10+10h], r9
0x18000746b  mov     [r10+24h], edx
0x18000746f  cmp     bx, [r10+2Ah]
0x180007474  jnb     loc_18000752A
0x18000747a  mov     rax, [r10+40h]
0x18000747e  mov     cl, [r10+28h]
0x180007482  mov     r9d, r8d
0x180007485  cmp     [r9+rax], cl
0x180007489  jbe     short loc_18000748F
0x18000748b  test    cl, cl
0x18000748d  jnz     short loc_1800074AF
0x18000748f  mov     rax, [r10+38h]
0x180007493  mov     rcx, [rax+r9*8]
0x180007497  test    rcx, rcx
0x18000749a  jz      short loc_1800074B4
0x18000749c  test    [r10+10h], rcx
0x1800074a0  jz      short loc_1800074AF
0x1800074a2  mov     rax, [r10+18h]
0x1800074a6  and     rax, rcx
0x1800074a9  cmp     rax, [r10+18h]
0x1800074ad  jz      short loc_1800074B4
0x1800074af  mov     r11b, bl
0x1800074b2  jmp     short loc_1800074B7
0x1800074b4  mov     r11b, 1
0x1800074b7  mov     rax, [r10+30h]
0x1800074bb  mov     ecx, r8d
0x1800074be  shr     r9, 5
0x1800074c2  mov     edx, 1
0x1800074c7  shl     edx, cl
0x1800074c9  lea     rcx, [rax+r9*4]
0x1800074cd  test    r11b, r11b
0x1800074d0  jz      short loc_1800074D6
0x1800074d2  or      edx, [rcx]
0x1800074d4  jmp     short loc_1800074DA
0x1800074d6  not     edx
0x1800074d8  and     edx, [rcx]
0x1800074da  mov     [rcx], edx
0x1800074dc  inc     r8d
0x1800074df  movzx   eax, word ptr [r10+2Ah]
0x1800074e4  cmp     r8d, eax
0x1800074e7  jb      short loc_18000747A
0x1800074e9  add     rsp, 20h
0x1800074ed  pop     rbx
0x1800074ee  retn
0x1800074ef  mov     [r10+24h], ebx
0x1800074f3  mov     [r10+28h], bl
0x1800074f7  mov     [r10+10h], rbx
0x1800074fb  mov     [r10+18h], rbx
0x1800074ff  cmp     [r10+2Ah], bx
0x180007504  jbe     short loc_18000752A
0x180007506  movzx   eax, word ptr [r10+2Ah]
0x18000750b  mov     rcx, [r10+30h]; void *
0x18000750f  dec     eax
0x180007511  cdq
0x180007512  and     edx, 1Fh
0x180007515  add     eax, edx
0x180007517  xor     edx, edx; Val
0x180007519  sar     eax, 5
0x18000751c  inc     eax
0x18000751e  movsxd  r8, eax
0x180007521  shl     r8, 2; Size
0x180007525  call    memset_0
0x18000752a  add     rsp, 20h
0x18000752e  pop     rbx
0x18000752f  retn
```
