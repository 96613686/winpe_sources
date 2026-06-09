# McGenControlCallbackV2

- ea: `0x180005a80`
- end: `0x180005b82`
- name: `McGenControlCallbackV2`
- size: `258`
- prototype: `void __stdcall(LPCGUID SourceId, ULONG IsEnabled, UCHAR Level, ULONGLONG MatchAnyKeyword, ULONGLONG MatchAllKeyword, PEVENT_FILTER_DESCRIPTOR FilterData, PVOID CallbackContext)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180001fea`
- `0x180005a80`

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
0x180005a80  push    rbx
0x180005a82  sub     rsp, 20h
0x180005a86  mov     r10, [rsp+28h+CallbackContext]
0x180005a8b  xor     ebx, ebx
0x180005a8d  test    r10, r10
0x180005a90  jz      loc_180005B7B
0x180005a96  test    edx, edx
0x180005a98  jz      loc_180005B40
0x180005a9e  cmp     edx, 1
0x180005aa1  jnz     loc_180005B7B
0x180005aa7  mov     rax, [rsp+28h+MatchAllKeyword]
0x180005aac  mov     [r10+28h], r8b
0x180005ab0  mov     r8d, ebx
0x180005ab3  mov     [r10+18h], rax
0x180005ab7  mov     [r10+10h], r9
0x180005abb  mov     [r10+24h], edx
0x180005abf  cmp     bx, [r10+2Ah]
0x180005ac4  jnb     loc_180005B7B
0x180005aca  mov     rax, [r10+40h]
0x180005ace  mov     cl, [r10+28h]
0x180005ad2  mov     r9d, r8d
0x180005ad5  cmp     [r9+rax], cl
0x180005ad9  jbe     short loc_180005ADF
0x180005adb  test    cl, cl
0x180005add  jnz     short loc_180005AFF
0x180005adf  mov     rax, [r10+38h]
0x180005ae3  mov     rcx, [rax+r9*8]
0x180005ae7  test    rcx, rcx
0x180005aea  jz      short loc_180005B04
0x180005aec  test    [r10+10h], rcx
0x180005af0  jz      short loc_180005AFF
0x180005af2  mov     rax, [r10+18h]
0x180005af6  and     rax, rcx
0x180005af9  cmp     rax, [r10+18h]
0x180005afd  jz      short loc_180005B04
0x180005aff  mov     r11b, bl
0x180005b02  jmp     short loc_180005B07
0x180005b04  mov     r11b, 1
0x180005b07  mov     rax, [r10+30h]
0x180005b0b  mov     ecx, r8d
0x180005b0e  shr     r9, 5
0x180005b12  mov     edx, 1
0x180005b17  shl     edx, cl
0x180005b19  lea     rcx, [rax+r9*4]
0x180005b1d  test    r11b, r11b
0x180005b20  jz      short loc_180005B26
0x180005b22  or      edx, [rcx]
0x180005b24  jmp     short loc_180005B2A
0x180005b26  not     edx
0x180005b28  and     edx, [rcx]
0x180005b2a  mov     [rcx], edx
0x180005b2c  inc     r8d
0x180005b2f  movzx   eax, word ptr [r10+2Ah]
0x180005b34  cmp     r8d, eax
0x180005b37  jb      short loc_180005ACA
0x180005b39  add     rsp, 20h
0x180005b3d  pop     rbx
0x180005b3e  retn
0x180005b40  mov     [r10+24h], ebx
0x180005b44  mov     [r10+28h], bl
0x180005b48  mov     [r10+10h], rbx
0x180005b4c  mov     [r10+18h], rbx
0x180005b50  cmp     [r10+2Ah], bx
0x180005b55  jbe     short loc_180005B7B
0x180005b57  movzx   eax, word ptr [r10+2Ah]
0x180005b5c  mov     rcx, [r10+30h]; void *
0x180005b60  dec     eax
0x180005b62  cdq
0x180005b63  and     edx, 1Fh
0x180005b66  add     eax, edx
0x180005b68  xor     edx, edx; Val
0x180005b6a  sar     eax, 5
0x180005b6d  inc     eax
0x180005b6f  movsxd  r8, eax
0x180005b72  shl     r8, 2; Size
0x180005b76  call    memset_0
0x180005b7b  add     rsp, 20h
0x180005b7f  pop     rbx
0x180005b80  retn
```
