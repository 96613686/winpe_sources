# McGenControlCallbackV2

- ea: `0x140009880`
- end: `0x14000997f`
- name: `McGenControlCallbackV2`
- size: `255`
- prototype: `void __stdcall(LPCGUID SourceId, ULONG ControlCode, UCHAR Level, ULONGLONG MatchAnyKeyword, ULONGLONG MatchAllKeyword, PEVENT_FILTER_DESCRIPTOR FilterData, PVOID CallbackContext)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x140009880`
- `0x14000be80`

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
0x140009880  push    rbx
0x140009882  sub     rsp, 20h
0x140009886  mov     r10, [rsp+28h+CallbackContext]
0x14000988b  xor     ebx, ebx
0x14000988d  test    r10, r10
0x140009890  jz      loc_140009978
0x140009896  test    edx, edx
0x140009898  jz      loc_14000993F
0x14000989e  cmp     edx, 1
0x1400098a1  jnz     loc_140009978
0x1400098a7  mov     rax, [rsp+28h+MatchAllKeyword]
0x1400098ac  mov     [r10+28h], r8b
0x1400098b0  mov     r8d, ebx
0x1400098b3  mov     [r10+18h], rax
0x1400098b7  mov     [r10+10h], r9
0x1400098bb  mov     [r10+24h], edx
0x1400098bf  cmp     bx, [r10+2Ah]
0x1400098c4  jnb     loc_140009978
0x1400098ca  mov     rax, [r10+40h]
0x1400098ce  mov     cl, [r10+28h]
0x1400098d2  mov     r9d, r8d
0x1400098d5  cmp     [r9+rax], cl
0x1400098d9  jbe     short loc_1400098DF
0x1400098db  test    cl, cl
0x1400098dd  jnz     short loc_140009901
0x1400098df  mov     rax, [r10+38h]
0x1400098e3  mov     rdx, [rax+r9*8]
0x1400098e7  test    rdx, rdx
0x1400098ea  jz      short loc_140009906
0x1400098ec  test    [r10+10h], rdx
0x1400098f0  jz      short loc_140009901
0x1400098f2  mov     rcx, [r10+18h]
0x1400098f6  mov     rax, rcx
0x1400098f9  and     rax, rdx
0x1400098fc  cmp     rax, rcx
0x1400098ff  jz      short loc_140009906
0x140009901  mov     r11b, bl
0x140009904  jmp     short loc_140009909
0x140009906  mov     r11b, 1
0x140009909  mov     rax, [r10+30h]
0x14000990d  mov     ecx, r8d
0x140009910  shr     r9, 5
0x140009914  mov     edx, 1
0x140009919  shl     edx, cl
0x14000991b  lea     rcx, [rax+r9*4]
0x14000991f  mov     eax, [rcx]
0x140009921  test    r11b, r11b
0x140009924  jz      short loc_14000992A
0x140009926  or      edx, eax
0x140009928  jmp     short loc_14000992E
0x14000992a  not     edx
0x14000992c  and     edx, eax
0x14000992e  mov     [rcx], edx
0x140009930  inc     r8d
0x140009933  movzx   eax, word ptr [r10+2Ah]
0x140009938  cmp     r8d, eax
0x14000993b  jb      short loc_1400098CA
0x14000993d  jmp     short loc_140009978
0x14000993f  movzx   eax, word ptr [r10+2Ah]
0x140009944  mov     [r10+24h], ebx
0x140009948  mov     [r10+28h], bl
0x14000994c  mov     [r10+10h], rbx
0x140009950  mov     [r10+18h], rbx
0x140009954  test    ax, ax
0x140009957  jz      short loc_140009978
0x140009959  mov     rcx, [r10+30h]; void *
0x14000995d  dec     eax
0x14000995f  cdq
0x140009960  and     edx, 1Fh
0x140009963  add     eax, edx
0x140009965  xor     edx, edx; Val
0x140009967  sar     eax, 5
0x14000996a  inc     eax
0x14000996c  movsxd  r8, eax
0x14000996f  shl     r8, 2; Size
0x140009973  call    memset
0x140009978  add     rsp, 20h
0x14000997c  pop     rbx
0x14000997d  retn
```
