# McGenControlCallbackV2

- ea: `0x180012f50`
- end: `0x180013052`
- name: `McGenControlCallbackV2`
- size: `258`
- prototype: `void __stdcall(LPCGUID SourceId, ULONG IsEnabled, UCHAR Level, ULONGLONG MatchAnyKeyword, ULONGLONG MatchAllKeyword, PEVENT_FILTER_DESCRIPTOR FilterData, PVOID CallbackContext)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180012f50`
- `0x180013686`

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
0x180012f50  push    rbx
0x180012f52  sub     rsp, 20h
0x180012f56  mov     r10, [rsp+28h+CallbackContext]
0x180012f5b  xor     ebx, ebx
0x180012f5d  test    r10, r10
0x180012f60  jz      loc_18001304B
0x180012f66  test    edx, edx
0x180012f68  jz      loc_180013010
0x180012f6e  cmp     edx, 1
0x180012f71  jnz     loc_18001304B
0x180012f77  mov     rax, [rsp+28h+MatchAllKeyword]
0x180012f7c  mov     [r10+28h], r8b
0x180012f80  mov     r8d, ebx
0x180012f83  mov     [r10+18h], rax
0x180012f87  mov     [r10+10h], r9
0x180012f8b  mov     [r10+24h], edx
0x180012f8f  cmp     bx, [r10+2Ah]
0x180012f94  jnb     loc_18001304B
0x180012f9a  mov     rax, [r10+40h]
0x180012f9e  mov     cl, [r10+28h]
0x180012fa2  mov     r9d, r8d
0x180012fa5  cmp     [r9+rax], cl
0x180012fa9  jbe     short loc_180012FAF
0x180012fab  test    cl, cl
0x180012fad  jnz     short loc_180012FCF
0x180012faf  mov     rax, [r10+38h]
0x180012fb3  mov     rcx, [rax+r9*8]
0x180012fb7  test    rcx, rcx
0x180012fba  jz      short loc_180012FD4
0x180012fbc  test    [r10+10h], rcx
0x180012fc0  jz      short loc_180012FCF
0x180012fc2  mov     rax, [r10+18h]
0x180012fc6  and     rax, rcx
0x180012fc9  cmp     rax, [r10+18h]
0x180012fcd  jz      short loc_180012FD4
0x180012fcf  mov     r11b, bl
0x180012fd2  jmp     short loc_180012FD7
0x180012fd4  mov     r11b, 1
0x180012fd7  mov     rax, [r10+30h]
0x180012fdb  mov     ecx, r8d
0x180012fde  shr     r9, 5
0x180012fe2  mov     edx, 1
0x180012fe7  shl     edx, cl
0x180012fe9  lea     rcx, [rax+r9*4]
0x180012fed  test    r11b, r11b
0x180012ff0  jz      short loc_180012FF6
0x180012ff2  or      edx, [rcx]
0x180012ff4  jmp     short loc_180012FFA
0x180012ff6  not     edx
0x180012ff8  and     edx, [rcx]
0x180012ffa  mov     [rcx], edx
0x180012ffc  inc     r8d
0x180012fff  movzx   eax, word ptr [r10+2Ah]
0x180013004  cmp     r8d, eax
0x180013007  jb      short loc_180012F9A
0x180013009  add     rsp, 20h
0x18001300d  pop     rbx
0x18001300e  retn
0x180013010  mov     [r10+24h], ebx
0x180013014  mov     [r10+28h], bl
0x180013018  mov     [r10+10h], rbx
0x18001301c  mov     [r10+18h], rbx
0x180013020  cmp     [r10+2Ah], bx
0x180013025  jbe     short loc_18001304B
0x180013027  movzx   eax, word ptr [r10+2Ah]
0x18001302c  mov     rcx, [r10+30h]; void *
0x180013030  dec     eax
0x180013032  cdq
0x180013033  and     edx, 1Fh
0x180013036  add     eax, edx
0x180013038  xor     edx, edx; Val
0x18001303a  sar     eax, 5
0x18001303d  inc     eax
0x18001303f  movsxd  r8, eax
0x180013042  shl     r8, 2; Size
0x180013046  call    memset_0
0x18001304b  add     rsp, 20h
0x18001304f  pop     rbx
0x180013050  retn
```
