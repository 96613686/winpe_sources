# McGenControlCallbackV2

- ea: `0x14000aa60`
- end: `0x14000ab62`
- name: `McGenControlCallbackV2`
- size: `258`
- prototype: `void __stdcall(LPCGUID SourceId, ULONG IsEnabled, UCHAR Level, ULONGLONG MatchAnyKeyword, ULONGLONG MatchAllKeyword, PEVENT_FILTER_DESCRIPTOR FilterData, PVOID CallbackContext)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x14000271f`
- `0x14000aa60`

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
0x14000aa60  push    rbx
0x14000aa62  sub     rsp, 20h
0x14000aa66  mov     r10, [rsp+28h+CallbackContext]
0x14000aa6b  xor     ebx, ebx
0x14000aa6d  test    r10, r10
0x14000aa70  jz      loc_14000AB5B
0x14000aa76  test    edx, edx
0x14000aa78  jz      loc_14000AB20
0x14000aa7e  cmp     edx, 1
0x14000aa81  jnz     loc_14000AB5B
0x14000aa87  mov     rax, [rsp+28h+MatchAllKeyword]
0x14000aa8c  mov     [r10+28h], r8b
0x14000aa90  mov     r8d, ebx
0x14000aa93  mov     [r10+18h], rax
0x14000aa97  mov     [r10+10h], r9
0x14000aa9b  mov     [r10+24h], edx
0x14000aa9f  cmp     bx, [r10+2Ah]
0x14000aaa4  jnb     loc_14000AB5B
0x14000aaaa  mov     rax, [r10+40h]
0x14000aaae  mov     cl, [r10+28h]
0x14000aab2  mov     r9d, r8d
0x14000aab5  cmp     [r9+rax], cl
0x14000aab9  jbe     short loc_14000AABF
0x14000aabb  test    cl, cl
0x14000aabd  jnz     short loc_14000AADF
0x14000aabf  mov     rax, [r10+38h]
0x14000aac3  mov     rcx, [rax+r9*8]
0x14000aac7  test    rcx, rcx
0x14000aaca  jz      short loc_14000AAE4
0x14000aacc  test    [r10+10h], rcx
0x14000aad0  jz      short loc_14000AADF
0x14000aad2  mov     rax, [r10+18h]
0x14000aad6  and     rax, rcx
0x14000aad9  cmp     rax, [r10+18h]
0x14000aadd  jz      short loc_14000AAE4
0x14000aadf  mov     r11b, bl
0x14000aae2  jmp     short loc_14000AAE7
0x14000aae4  mov     r11b, 1
0x14000aae7  mov     rax, [r10+30h]
0x14000aaeb  mov     ecx, r8d
0x14000aaee  shr     r9, 5
0x14000aaf2  mov     edx, 1
0x14000aaf7  shl     edx, cl
0x14000aaf9  lea     rcx, [rax+r9*4]
0x14000aafd  test    r11b, r11b
0x14000ab00  jz      short loc_14000AB06
0x14000ab02  or      edx, [rcx]
0x14000ab04  jmp     short loc_14000AB0A
0x14000ab06  not     edx
0x14000ab08  and     edx, [rcx]
0x14000ab0a  mov     [rcx], edx
0x14000ab0c  inc     r8d
0x14000ab0f  movzx   eax, word ptr [r10+2Ah]
0x14000ab14  cmp     r8d, eax
0x14000ab17  jb      short loc_14000AAAA
0x14000ab19  add     rsp, 20h
0x14000ab1d  pop     rbx
0x14000ab1e  retn
0x14000ab20  mov     [r10+24h], ebx
0x14000ab24  mov     [r10+28h], bl
0x14000ab28  mov     [r10+10h], rbx
0x14000ab2c  mov     [r10+18h], rbx
0x14000ab30  cmp     [r10+2Ah], bx
0x14000ab35  jbe     short loc_14000AB5B
0x14000ab37  movzx   eax, word ptr [r10+2Ah]
0x14000ab3c  mov     rcx, [r10+30h]; void *
0x14000ab40  dec     eax
0x14000ab42  cdq
0x14000ab43  and     edx, 1Fh
0x14000ab46  add     eax, edx
0x14000ab48  xor     edx, edx; Val
0x14000ab4a  sar     eax, 5
0x14000ab4d  inc     eax
0x14000ab4f  movsxd  r8, eax
0x14000ab52  shl     r8, 2; Size
0x14000ab56  call    memset_0
0x14000ab5b  add     rsp, 20h
0x14000ab5f  pop     rbx
0x14000ab60  retn
```
