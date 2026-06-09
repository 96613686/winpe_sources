# McGenControlCallbackV2

- ea: `0x14000ab50`
- end: `0x14000ac4f`
- name: `McGenControlCallbackV2`
- size: `255`
- prototype: `void __stdcall(LPCGUID SourceId, ULONG ControlCode, UCHAR Level, ULONGLONG MatchAnyKeyword, ULONGLONG MatchAllKeyword, PEVENT_FILTER_DESCRIPTOR FilterData, PVOID CallbackContext)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x1400017c0`
- `0x14000ab50`

## pseudocode

```c
void __stdcall McGenControlCallbackV2(
        LPCGUID SourceId,
        ULONG ControlCode,
        UCHAR Level,
        ULONGLONG MatchAnyKeyword,
        ULONGLONG MatchAllKeyword,
        PEVENT_FILTER_DESCRIPTOR FilterData,
        PVOID CallbackContext)
{
  unsigned int v7; // r8d
  unsigned __int8 v8; // cl
  __int64 v9; // rdx
  bool v10; // r11
  int v11; // edx
  int *v12; // rcx
  int v13; // eax
  int v14; // edx
  int v15; // eax

  if ( CallbackContext )
  {
    if ( ControlCode )
    {
      if ( ControlCode == 1 )
      {
        *((_BYTE *)CallbackContext + 40) = Level;
        v7 = 0;
        *((_QWORD *)CallbackContext + 3) = MatchAllKeyword;
        *((_QWORD *)CallbackContext + 2) = MatchAnyKeyword;
        for ( *((_DWORD *)CallbackContext + 9) = 1; v7 < *((unsigned __int16 *)CallbackContext + 21); ++v7 )
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
          v13 = *v12;
          if ( v10 )
            v14 = v13 | v11;
          else
            v14 = v13 & ~v11;
          *v12 = v14;
        }
      }
    }
    else
    {
      v15 = *((unsigned __int16 *)CallbackContext + 21);
      *((_DWORD *)CallbackContext + 9) = 0;
      *((_BYTE *)CallbackContext + 40) = 0;
      *((_QWORD *)CallbackContext + 2) = 0;
      *((_QWORD *)CallbackContext + 3) = 0;
      if ( (_WORD)v15 )
        memset(*((void **)CallbackContext + 6), 0, 4LL * ((v15 - 1) / 32 + 1));
    }
  }
}

```

## disassembly

```asm
0x14000ab50  push    rbx
0x14000ab52  sub     rsp, 20h
0x14000ab56  mov     r10, [rsp+28h+CallbackContext]
0x14000ab5b  xor     ebx, ebx
0x14000ab5d  test    r10, r10
0x14000ab60  jz      loc_14000AC48
0x14000ab66  test    edx, edx
0x14000ab68  jz      loc_14000AC0F
0x14000ab6e  cmp     edx, 1
0x14000ab71  jnz     loc_14000AC48
0x14000ab77  mov     rax, [rsp+28h+MatchAllKeyword]
0x14000ab7c  mov     [r10+28h], r8b
0x14000ab80  mov     r8d, ebx
0x14000ab83  mov     [r10+18h], rax
0x14000ab87  mov     [r10+10h], r9
0x14000ab8b  mov     [r10+24h], edx
0x14000ab8f  cmp     bx, [r10+2Ah]
0x14000ab94  jnb     loc_14000AC48
0x14000ab9a  mov     rax, [r10+40h]
0x14000ab9e  mov     cl, [r10+28h]
0x14000aba2  mov     r9d, r8d
0x14000aba5  cmp     [r9+rax], cl
0x14000aba9  jbe     short loc_14000ABAF
0x14000abab  test    cl, cl
0x14000abad  jnz     short loc_14000ABD1
0x14000abaf  mov     rax, [r10+38h]
0x14000abb3  mov     rdx, [rax+r9*8]
0x14000abb7  test    rdx, rdx
0x14000abba  jz      short loc_14000ABD6
0x14000abbc  test    [r10+10h], rdx
0x14000abc0  jz      short loc_14000ABD1
0x14000abc2  mov     rcx, [r10+18h]
0x14000abc6  mov     rax, rcx
0x14000abc9  and     rax, rdx
0x14000abcc  cmp     rax, rcx
0x14000abcf  jz      short loc_14000ABD6
0x14000abd1  mov     r11b, bl
0x14000abd4  jmp     short loc_14000ABD9
0x14000abd6  mov     r11b, 1
0x14000abd9  mov     rax, [r10+30h]
0x14000abdd  mov     ecx, r8d
0x14000abe0  shr     r9, 5
0x14000abe4  mov     edx, 1
0x14000abe9  shl     edx, cl
0x14000abeb  lea     rcx, [rax+r9*4]
0x14000abef  mov     eax, [rcx]
0x14000abf1  test    r11b, r11b
0x14000abf4  jz      short loc_14000ABFA
0x14000abf6  or      edx, eax
0x14000abf8  jmp     short loc_14000ABFE
0x14000abfa  not     edx
0x14000abfc  and     edx, eax
0x14000abfe  mov     [rcx], edx
0x14000ac00  inc     r8d
0x14000ac03  movzx   eax, word ptr [r10+2Ah]
0x14000ac08  cmp     r8d, eax
0x14000ac0b  jb      short loc_14000AB9A
0x14000ac0d  jmp     short loc_14000AC48
0x14000ac0f  movzx   eax, word ptr [r10+2Ah]
0x14000ac14  mov     [r10+24h], ebx
0x14000ac18  mov     [r10+28h], bl
0x14000ac1c  mov     [r10+10h], rbx
0x14000ac20  mov     [r10+18h], rbx
0x14000ac24  test    ax, ax
0x14000ac27  jz      short loc_14000AC48
0x14000ac29  mov     rcx, [r10+30h]; void *
0x14000ac2d  dec     eax
0x14000ac2f  cdq
0x14000ac30  and     edx, 1Fh
0x14000ac33  add     eax, edx
0x14000ac35  xor     edx, edx; Val
0x14000ac37  sar     eax, 5
0x14000ac3a  inc     eax
0x14000ac3c  movsxd  r8, eax
0x14000ac3f  shl     r8, 2; Size
0x14000ac43  call    memset
0x14000ac48  add     rsp, 20h
0x14000ac4c  pop     rbx
0x14000ac4d  retn
```
