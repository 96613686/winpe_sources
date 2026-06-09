# McGenControlCallbackV2

- ea: `0x1400012d0`
- end: `0x1400013d6`
- name: `McGenControlCallbackV2`
- size: `262`
- prototype: `void __stdcall(LPCGUID SourceId, ULONG ControlCode, UCHAR Level, ULONGLONG MatchAnyKeyword, ULONGLONG MatchAllKeyword, PEVENT_FILTER_DESCRIPTOR FilterData, PVOID CallbackContext)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x1400012d0`
- `0x140001f40`

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
  __int64 v9; // r9
  _DWORD *v10; // rdx
  _DWORD *v11; // rdx
  int v12; // eax

  if ( CallbackContext )
  {
    if ( ControlCode )
    {
      if ( ControlCode == 1 )
      {
        *((_BYTE *)CallbackContext + 40) = Level;
        v7 = 0;
        *((_QWORD *)CallbackContext + 2) = MatchAnyKeyword;
        *((_QWORD *)CallbackContext + 3) = MatchAllKeyword;
        for ( *((_DWORD *)CallbackContext + 9) = 1; v7 < *((unsigned __int16 *)CallbackContext + 21); ++v7 )
        {
          v8 = *((_BYTE *)CallbackContext + 40);
          if ( (*(_BYTE *)(v7 + *((_QWORD *)CallbackContext + 8)) <= v8 || !v8)
            && ((v9 = *(_QWORD *)(*((_QWORD *)CallbackContext + 7) + 8LL * v7)) == 0
             || (v9 & *((_QWORD *)CallbackContext + 2)) != 0
             && (v9 & *((_QWORD *)CallbackContext + 3)) == *((_QWORD *)CallbackContext + 3)) )
          {
            v11 = (_DWORD *)(*((_QWORD *)CallbackContext + 6) + 4 * ((unsigned __int64)v7 >> 5));
            *v11 |= 1 << v7;
          }
          else
          {
            v10 = (_DWORD *)(*((_QWORD *)CallbackContext + 6) + 4 * ((unsigned __int64)v7 >> 5));
            *v10 &= ~(1 << v7);
          }
        }
      }
    }
    else
    {
      v12 = *((unsigned __int16 *)CallbackContext + 21);
      *((_DWORD *)CallbackContext + 9) = 0;
      *((_BYTE *)CallbackContext + 40) = 0;
      *((_QWORD *)CallbackContext + 2) = 0;
      *((_QWORD *)CallbackContext + 3) = 0;
      if ( (_WORD)v12 )
        memset(*((void **)CallbackContext + 6), 0, 4LL * ((v12 - 1) / 32 + 1));
    }
  }
}

```

## disassembly

```asm
0x1400012d0  sub     rsp, 28h
0x1400012d4  mov     r10, [rsp+28h+CallbackContext]
0x1400012d9  test    r10, r10
0x1400012dc  jz      loc_1400013D0
0x1400012e2  test    edx, edx
0x1400012e4  jz      loc_140001394
0x1400012ea  cmp     edx, 1
0x1400012ed  jnz     loc_1400013D0
0x1400012f3  mov     rax, [rsp+28h+MatchAllKeyword]
0x1400012f8  mov     [r10+28h], r8b
0x1400012fc  xor     r8d, r8d
0x1400012ff  mov     [r10+10h], r9
0x140001303  mov     [r10+18h], rax
0x140001307  mov     [r10+24h], edx
0x14000130b  cmp     r8w, [r10+2Ah]
0x140001310  jnb     loc_1400013D0
0x140001316  mov     rax, [r10+40h]
0x14000131a  movzx   ecx, byte ptr [r10+28h]
0x14000131f  mov     edx, r8d
0x140001322  cmp     [rdx+rax], cl
0x140001325  jbe     short loc_14000132B
0x140001327  test    cl, cl
0x140001329  jnz     short loc_14000134D
0x14000132b  mov     rax, [r10+38h]
0x14000132f  mov     r9, [rax+rdx*8]
0x140001333  test    r9, r9
0x140001336  jz      short loc_140001369
0x140001338  test    [r10+10h], r9
0x14000133c  jz      short loc_14000134D
0x14000133e  mov     rcx, [r10+18h]
0x140001342  mov     rax, rcx
0x140001345  and     rax, r9
0x140001348  cmp     rax, rcx
0x14000134b  jz      short loc_140001369
0x14000134d  mov     rax, [r10+30h]
0x140001351  mov     ecx, r8d
0x140001354  shr     rdx, 5
0x140001358  lea     rdx, [rax+rdx*4]
0x14000135c  mov     eax, 1
0x140001361  shl     eax, cl
0x140001363  not     eax
0x140001365  and     [rdx], eax
0x140001367  jmp     short loc_140001381
0x140001369  mov     rax, [r10+30h]
0x14000136d  mov     ecx, r8d
0x140001370  shr     rdx, 5
0x140001374  lea     rdx, [rax+rdx*4]
0x140001378  mov     eax, 1
0x14000137d  shl     eax, cl
0x14000137f  or      [rdx], eax
0x140001381  movzx   eax, word ptr [r10+2Ah]
0x140001386  inc     r8d
0x140001389  cmp     r8d, eax
0x14000138c  jb      short loc_140001316
0x14000138e  add     rsp, 28h
0x140001392  retn
0x140001394  movzx   eax, word ptr [r10+2Ah]
0x140001399  xor     r8d, r8d
0x14000139c  mov     [r10+24h], r8d
0x1400013a0  mov     [r10+28h], r8b
0x1400013a4  mov     [r10+10h], r8
0x1400013a8  mov     [r10+18h], r8
0x1400013ac  test    ax, ax
0x1400013af  jz      short loc_1400013D0
0x1400013b1  mov     rcx, [r10+30h]; void *
0x1400013b5  dec     eax
0x1400013b7  cdq
0x1400013b8  and     edx, 1Fh
0x1400013bb  add     eax, edx
0x1400013bd  xor     edx, edx; Val
0x1400013bf  sar     eax, 5
0x1400013c2  inc     eax
0x1400013c4  movsxd  r8, eax
0x1400013c7  shl     r8, 2; Size
0x1400013cb  call    memset
0x1400013d0  add     rsp, 28h
0x1400013d4  retn
```
