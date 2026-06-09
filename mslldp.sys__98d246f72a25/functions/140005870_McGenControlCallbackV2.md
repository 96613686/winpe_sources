# McGenControlCallbackV2

- ea: `0x140005870`
- end: `0x14000596e`
- name: `McGenControlCallbackV2`
- size: `254`
- prototype: `void __stdcall(LPCGUID SourceId, ULONG ControlCode, UCHAR Level, ULONGLONG MatchAnyKeyword, ULONGLONG MatchAllKeyword, PEVENT_FILTER_DESCRIPTOR FilterData, PVOID CallbackContext)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x140005870`
- `0x140006b40`

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
0x140005870  push    rbx
0x140005872  sub     rsp, 20h
0x140005876  mov     r10, [rsp+28h+CallbackContext]
0x14000587b  xor     ebx, ebx
0x14000587d  test    r10, r10
0x140005880  jz      loc_140005967
0x140005886  test    edx, edx
0x140005888  jz      loc_14000592F
0x14000588e  cmp     edx, 1
0x140005891  jnz     loc_140005967
0x140005897  mov     rax, [rsp+28h+MatchAllKeyword]
0x14000589c  mov     [r10+28h], r8b
0x1400058a0  mov     r8d, ebx
0x1400058a3  mov     [r10+18h], rax
0x1400058a7  mov     [r10+10h], r9
0x1400058ab  mov     [r10+24h], edx
0x1400058af  cmp     bx, [r10+2Ah]
0x1400058b4  jnb     loc_140005967
0x1400058ba  mov     rax, [r10+40h]
0x1400058be  mov     cl, [r10+28h]
0x1400058c2  mov     r9d, r8d
0x1400058c5  cmp     [r9+rax], cl
0x1400058c9  jbe     short loc_1400058CF
0x1400058cb  test    cl, cl
0x1400058cd  jnz     short loc_1400058F1
0x1400058cf  mov     rax, [r10+38h]
0x1400058d3  mov     rdx, [rax+r9*8]
0x1400058d7  test    rdx, rdx
0x1400058da  jz      short loc_1400058F6
0x1400058dc  test    [r10+10h], rdx
0x1400058e0  jz      short loc_1400058F1
0x1400058e2  mov     rcx, [r10+18h]
0x1400058e6  mov     rax, rcx
0x1400058e9  and     rax, rdx
0x1400058ec  cmp     rax, rcx
0x1400058ef  jz      short loc_1400058F6
0x1400058f1  mov     r11b, bl
0x1400058f4  jmp     short loc_1400058F9
0x1400058f6  mov     r11b, 1
0x1400058f9  mov     rax, [r10+30h]
0x1400058fd  mov     ecx, r8d
0x140005900  shr     r9, 5
0x140005904  mov     edx, 1
0x140005909  shl     edx, cl
0x14000590b  lea     rcx, [rax+r9*4]
0x14000590f  mov     eax, [rcx]
0x140005911  test    r11b, r11b
0x140005914  jz      short loc_14000591A
0x140005916  or      edx, eax
0x140005918  jmp     short loc_14000591E
0x14000591a  not     edx
0x14000591c  and     edx, eax
0x14000591e  mov     [rcx], edx
0x140005920  inc     r8d
0x140005923  movzx   eax, word ptr [r10+2Ah]
0x140005928  cmp     r8d, eax
0x14000592b  jb      short loc_1400058BA
0x14000592d  jmp     short loc_140005967
0x14000592f  movzx   eax, word ptr [r10+2Ah]
0x140005934  mov     [r10+24h], ebx
0x140005938  mov     [r10+28h], bl
0x14000593c  mov     [r10+10h], rbx
0x140005940  mov     [r10+18h], rbx
0x140005944  test    ax, ax
0x140005947  jz      short loc_140005967
0x140005949  dec     eax
0x14000594b  mov     ecx, 20h ; ' '
0x140005950  cdq
0x140005951  idiv    ecx
0x140005953  mov     rcx, [r10+30h]; void *
0x140005957  xor     edx, edx; Val
0x140005959  inc     eax
0x14000595b  movsxd  r8, eax
0x14000595e  shl     r8, 2; Size
0x140005962  call    memset
0x140005967  add     rsp, 20h
0x14000596b  pop     rbx
0x14000596c  retn
```
