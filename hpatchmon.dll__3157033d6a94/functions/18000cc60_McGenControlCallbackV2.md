# McGenControlCallbackV2

- ea: `0x18000cc60`
- end: `0x18000cd60`
- name: `McGenControlCallbackV2`
- size: `256`
- prototype: `void __fastcall(LPCGUID SourceId, ULONG IsEnabled, UCHAR Level, ULONGLONG MatchAnyKeyword, ULONGLONG MatchAllKeyword, PEVENT_FILTER_DESCRIPTOR FilterData, unsigned __int16 *CallbackContext)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180002be8`
- `0x18000cc60`

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
0x18000cc60  push    rbx
0x18000cc62  sub     rsp, 20h
0x18000cc66  mov     r10, [rsp+28h+CallbackContext]
0x18000cc6b  xor     ebx, ebx
0x18000cc6d  test    r10, r10
0x18000cc70  jz      loc_18000CD5A
0x18000cc76  test    edx, edx
0x18000cc78  jz      loc_18000CD1F
0x18000cc7e  cmp     edx, 1
0x18000cc81  jnz     loc_18000CD5A
0x18000cc87  mov     rax, [rsp+28h+MatchAllKeyword]
0x18000cc8c  mov     [r10+28h], r8b
0x18000cc90  mov     r8d, ebx
0x18000cc93  mov     [r10+18h], rax
0x18000cc97  mov     [r10+10h], r9
0x18000cc9b  mov     [r10+24h], edx
0x18000cc9f  cmp     bx, [r10+2Ah]
0x18000cca4  jnb     loc_18000CD5A
0x18000ccaa  mov     rax, [r10+40h]
0x18000ccae  mov     cl, [r10+28h]
0x18000ccb2  mov     r9d, r8d
0x18000ccb5  cmp     [r9+rax], cl
0x18000ccb9  jbe     short loc_18000CCBF
0x18000ccbb  test    cl, cl
0x18000ccbd  jnz     short loc_18000CCDF
0x18000ccbf  mov     rax, [r10+38h]
0x18000ccc3  mov     rcx, [rax+r9*8]
0x18000ccc7  test    rcx, rcx
0x18000ccca  jz      short loc_18000CCE4
0x18000cccc  test    [r10+10h], rcx
0x18000ccd0  jz      short loc_18000CCDF
0x18000ccd2  mov     rax, [r10+18h]
0x18000ccd6  and     rax, rcx
0x18000ccd9  cmp     rax, [r10+18h]
0x18000ccdd  jz      short loc_18000CCE4
0x18000ccdf  mov     r11b, bl
0x18000cce2  jmp     short loc_18000CCE7
0x18000cce4  mov     r11b, 1
0x18000cce7  mov     rax, [r10+30h]
0x18000cceb  mov     ecx, r8d
0x18000ccee  shr     r9, 5
0x18000ccf2  mov     edx, 1
0x18000ccf7  shl     edx, cl
0x18000ccf9  lea     rcx, [rax+r9*4]
0x18000ccfd  test    r11b, r11b
0x18000cd00  jz      short loc_18000CD06
0x18000cd02  or      edx, [rcx]
0x18000cd04  jmp     short loc_18000CD0A
0x18000cd06  not     edx
0x18000cd08  and     edx, [rcx]
0x18000cd0a  mov     [rcx], edx
0x18000cd0c  inc     r8d
0x18000cd0f  movzx   eax, word ptr [r10+2Ah]
0x18000cd14  cmp     r8d, eax
0x18000cd17  jb      short loc_18000CCAA
0x18000cd19  add     rsp, 20h
0x18000cd1d  pop     rbx
0x18000cd1e  retn
0x18000cd1f  mov     [r10+24h], ebx
0x18000cd23  mov     [r10+28h], bl
0x18000cd27  mov     [r10+10h], rbx
0x18000cd2b  mov     [r10+18h], rbx
0x18000cd2f  cmp     [r10+2Ah], bx
0x18000cd34  jbe     short loc_18000CD5A
0x18000cd36  movzx   eax, word ptr [r10+2Ah]
0x18000cd3b  mov     rcx, [r10+30h]; void *
0x18000cd3f  dec     eax
0x18000cd41  cdq
0x18000cd42  and     edx, 1Fh
0x18000cd45  add     eax, edx
0x18000cd47  xor     edx, edx; Val
0x18000cd49  sar     eax, 5
0x18000cd4c  inc     eax
0x18000cd4e  movsxd  r8, eax
0x18000cd51  shl     r8, 2; Size
0x18000cd55  call    memset_0
0x18000cd5a  add     rsp, 20h
0x18000cd5e  pop     rbx
0x18000cd5f  retn
```
