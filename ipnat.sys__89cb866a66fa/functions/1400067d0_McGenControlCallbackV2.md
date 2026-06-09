# McGenControlCallbackV2

- ea: `0x1400067d0`
- end: `0x1400068cf`
- name: `McGenControlCallbackV2`
- size: `255`
- prototype: `void __stdcall(LPCGUID SourceId, ULONG ControlCode, UCHAR Level, ULONGLONG MatchAnyKeyword, ULONGLONG MatchAllKeyword, PEVENT_FILTER_DESCRIPTOR FilterData, PVOID CallbackContext)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x1400067d0`
- `0x14002cbc0`

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
0x1400067d0  push    rbx
0x1400067d2  sub     rsp, 20h
0x1400067d6  mov     r10, [rsp+28h+CallbackContext]
0x1400067db  xor     ebx, ebx
0x1400067dd  test    r10, r10
0x1400067e0  jz      loc_1400068C8
0x1400067e6  test    edx, edx
0x1400067e8  jz      loc_14000688F
0x1400067ee  cmp     edx, 1
0x1400067f1  jnz     loc_1400068C8
0x1400067f7  mov     rax, [rsp+28h+MatchAllKeyword]
0x1400067fc  mov     [r10+28h], r8b
0x140006800  mov     r8d, ebx
0x140006803  mov     [r10+18h], rax
0x140006807  mov     [r10+10h], r9
0x14000680b  mov     [r10+24h], edx
0x14000680f  cmp     bx, [r10+2Ah]
0x140006814  jnb     loc_1400068C8
0x14000681a  mov     rax, [r10+40h]
0x14000681e  mov     cl, [r10+28h]
0x140006822  mov     r9d, r8d
0x140006825  cmp     [r9+rax], cl
0x140006829  jbe     short loc_14000682F
0x14000682b  test    cl, cl
0x14000682d  jnz     short loc_140006851
0x14000682f  mov     rax, [r10+38h]
0x140006833  mov     rdx, [rax+r9*8]
0x140006837  test    rdx, rdx
0x14000683a  jz      short loc_140006856
0x14000683c  test    [r10+10h], rdx
0x140006840  jz      short loc_140006851
0x140006842  mov     rcx, [r10+18h]
0x140006846  mov     rax, rcx
0x140006849  and     rax, rdx
0x14000684c  cmp     rax, rcx
0x14000684f  jz      short loc_140006856
0x140006851  mov     r11b, bl
0x140006854  jmp     short loc_140006859
0x140006856  mov     r11b, 1
0x140006859  mov     rax, [r10+30h]
0x14000685d  mov     ecx, r8d
0x140006860  shr     r9, 5
0x140006864  mov     edx, 1
0x140006869  shl     edx, cl
0x14000686b  lea     rcx, [rax+r9*4]
0x14000686f  mov     eax, [rcx]
0x140006871  test    r11b, r11b
0x140006874  jz      short loc_14000687A
0x140006876  or      edx, eax
0x140006878  jmp     short loc_14000687E
0x14000687a  not     edx
0x14000687c  and     edx, eax
0x14000687e  mov     [rcx], edx
0x140006880  inc     r8d
0x140006883  movzx   eax, word ptr [r10+2Ah]
0x140006888  cmp     r8d, eax
0x14000688b  jb      short loc_14000681A
0x14000688d  jmp     short loc_1400068C8
0x14000688f  movzx   eax, word ptr [r10+2Ah]
0x140006894  mov     [r10+24h], ebx
0x140006898  mov     [r10+28h], bl
0x14000689c  mov     [r10+10h], rbx
0x1400068a0  mov     [r10+18h], rbx
0x1400068a4  test    ax, ax
0x1400068a7  jz      short loc_1400068C8
0x1400068a9  mov     rcx, [r10+30h]; void *
0x1400068ad  dec     eax
0x1400068af  cdq
0x1400068b0  and     edx, 1Fh
0x1400068b3  add     eax, edx
0x1400068b5  xor     edx, edx; Val
0x1400068b7  sar     eax, 5
0x1400068ba  inc     eax
0x1400068bc  movsxd  r8, eax
0x1400068bf  shl     r8, 2; Size
0x1400068c3  call    memset
0x1400068c8  add     rsp, 20h
0x1400068cc  pop     rbx
0x1400068cd  retn
```
