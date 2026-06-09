# McGenControlCallbackV2

- ea: `0x140009b10`
- end: `0x140009c10`
- name: `McGenControlCallbackV2`
- size: `256`
- prototype: `void __stdcall(LPCGUID SourceId, ULONG IsEnabled, UCHAR Level, ULONGLONG MatchAnyKeyword, ULONGLONG MatchAllKeyword, PEVENT_FILTER_DESCRIPTOR FilterData, PVOID CallbackContext)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x140001ebf`
- `0x140009b10`

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
0x140009b10  push    rbx
0x140009b12  sub     rsp, 20h
0x140009b16  mov     r10, [rsp+28h+CallbackContext]
0x140009b1b  xor     ebx, ebx
0x140009b1d  test    r10, r10
0x140009b20  jz      loc_140009C0A
0x140009b26  test    edx, edx
0x140009b28  jz      loc_140009BCF
0x140009b2e  cmp     edx, 1
0x140009b31  jnz     loc_140009C0A
0x140009b37  mov     rax, [rsp+28h+MatchAllKeyword]
0x140009b3c  mov     [r10+28h], r8b
0x140009b40  mov     r8d, ebx
0x140009b43  mov     [r10+18h], rax
0x140009b47  mov     [r10+10h], r9
0x140009b4b  mov     [r10+24h], edx
0x140009b4f  cmp     bx, [r10+2Ah]
0x140009b54  jnb     loc_140009C0A
0x140009b5a  mov     rax, [r10+40h]
0x140009b5e  mov     cl, [r10+28h]
0x140009b62  mov     r9d, r8d
0x140009b65  cmp     [r9+rax], cl
0x140009b69  jbe     short loc_140009B6F
0x140009b6b  test    cl, cl
0x140009b6d  jnz     short loc_140009B8F
0x140009b6f  mov     rax, [r10+38h]
0x140009b73  mov     rcx, [rax+r9*8]
0x140009b77  test    rcx, rcx
0x140009b7a  jz      short loc_140009B94
0x140009b7c  test    [r10+10h], rcx
0x140009b80  jz      short loc_140009B8F
0x140009b82  mov     rax, [r10+18h]
0x140009b86  and     rax, rcx
0x140009b89  cmp     rax, [r10+18h]
0x140009b8d  jz      short loc_140009B94
0x140009b8f  mov     r11b, bl
0x140009b92  jmp     short loc_140009B97
0x140009b94  mov     r11b, 1
0x140009b97  mov     rax, [r10+30h]
0x140009b9b  mov     ecx, r8d
0x140009b9e  shr     r9, 5
0x140009ba2  mov     edx, 1
0x140009ba7  shl     edx, cl
0x140009ba9  lea     rcx, [rax+r9*4]
0x140009bad  test    r11b, r11b
0x140009bb0  jz      short loc_140009BB6
0x140009bb2  or      edx, [rcx]
0x140009bb4  jmp     short loc_140009BBA
0x140009bb6  not     edx
0x140009bb8  and     edx, [rcx]
0x140009bba  mov     [rcx], edx
0x140009bbc  inc     r8d
0x140009bbf  movzx   eax, word ptr [r10+2Ah]
0x140009bc4  cmp     r8d, eax
0x140009bc7  jb      short loc_140009B5A
0x140009bc9  add     rsp, 20h
0x140009bcd  pop     rbx
0x140009bce  retn
0x140009bcf  mov     [r10+24h], ebx
0x140009bd3  mov     [r10+28h], bl
0x140009bd7  mov     [r10+10h], rbx
0x140009bdb  mov     [r10+18h], rbx
0x140009bdf  cmp     [r10+2Ah], bx
0x140009be4  jbe     short loc_140009C0A
0x140009be6  movzx   eax, word ptr [r10+2Ah]
0x140009beb  mov     rcx, [r10+30h]; void *
0x140009bef  dec     eax
0x140009bf1  cdq
0x140009bf2  and     edx, 1Fh
0x140009bf5  add     eax, edx
0x140009bf7  xor     edx, edx; Val
0x140009bf9  sar     eax, 5
0x140009bfc  inc     eax
0x140009bfe  movsxd  r8, eax
0x140009c01  shl     r8, 2; Size
0x140009c05  call    memset_0
0x140009c0a  add     rsp, 20h
0x140009c0e  pop     rbx
0x140009c0f  retn
```
