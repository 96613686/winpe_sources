# McGenControlCallbackV2

- ea: `0x1800152b0`
- end: `0x1800153c5`
- name: `McGenControlCallbackV2`
- size: `277`
- prototype: `void __stdcall(LPCGUID SourceId, ULONG ControlCode, UCHAR Level, ULONGLONG MatchAnyKeyword, ULONGLONG MatchAllKeyword, PEVENT_FILTER_DESCRIPTOR FilterData, PVOID CallbackContext)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x1800152b0`
- `0x18001b704`
- `0x180028000`

## pseudocode

```c
// local variable allocation has failed, the output may be wrong!
void __stdcall McGenControlCallbackV2(
        LPCGUID SourceId,
        ULONG ControlCode,
        UCHAR Level,
        ULONGLONG MatchAnyKeyword,
        ULONGLONG MatchAllKeyword,
        PEVENT_FILTER_DESCRIPTOR FilterData,
        PVOID CallbackContext)
{
  unsigned __int8 v8; // cl
  __int64 v9; // rdx
  bool v10; // r11
  int v11; // edx
  unsigned int Data1; // eax
  unsigned int v13; // edx
  int v14; // eax

  if ( CallbackContext )
  {
    if ( ControlCode )
    {
      if ( ControlCode == 1 )
      {
        *((_BYTE *)CallbackContext + 40) = Level;
        *(_QWORD *)&Level = 0;
        *((_QWORD *)CallbackContext + 3) = MatchAllKeyword;
        *((_QWORD *)CallbackContext + 2) = MatchAnyKeyword;
        *((_DWORD *)CallbackContext + 9) = 1;
        if ( *((_WORD *)CallbackContext + 21) )
        {
          do
          {
            v8 = *((_BYTE *)CallbackContext + 40);
            v10 = 0;
            if ( *(_BYTE *)(Level + *((_QWORD *)CallbackContext + 8)) <= v8 || !v8 )
            {
              v9 = *(_QWORD *)(*((_QWORD *)CallbackContext + 7) + 8LL * Level);
              if ( !v9
                || (v9 & *((_QWORD *)CallbackContext + 2)) != 0
                && (v9 & *((_QWORD *)CallbackContext + 3)) == *((_QWORD *)CallbackContext + 3) )
              {
                v10 = 1;
              }
            }
            MatchAnyKeyword = (unsigned __int64)Level >> 5;
            v11 = 1 << Level;
            SourceId = (LPCGUID)(*((_QWORD *)CallbackContext + 6) + 4 * MatchAnyKeyword);
            Data1 = SourceId->Data1;
            if ( v10 )
              v13 = Data1 | v11;
            else
              v13 = Data1 & ~v11;
            SourceId->Data1 = v13;
            *(_QWORD *)&Level = (unsigned int)(Level + 1);
          }
          while ( Level < (unsigned int)*((unsigned __int16 *)CallbackContext + 21) );
        }
      }
    }
    else
    {
      v14 = *((unsigned __int16 *)CallbackContext + 21);
      *((_DWORD *)CallbackContext + 9) = 0;
      *((_BYTE *)CallbackContext + 40) = 0;
      *((_QWORD *)CallbackContext + 2) = 0;
      *((_QWORD *)CallbackContext + 3) = 0;
      if ( (_WORD)v14 )
        memset(*((void **)CallbackContext + 6), 0, 4LL * ((v14 - 1) / 32 + 1));
    }
    HidClassEtwEnableCallback(SourceId, ControlCode, Level, MatchAnyKeyword);
  }
}

```

## disassembly

```asm
0x1800152b0  mov     [rsp+arg_0], rbx
0x1800152b5  push    rdi
0x1800152b6  sub     rsp, 40h
0x1800152ba  mov     r10, [rsp+48h+CallbackContext]
0x1800152c2  xor     edi, edi
0x1800152c4  mov     ebx, edx
0x1800152c6  test    r10, r10
0x1800152c9  jz      loc_1800153B9
0x1800152cf  mov     eax, edx
0x1800152d1  test    edx, edx
0x1800152d3  jz      loc_18001537A
0x1800152d9  cmp     eax, 1
0x1800152dc  jnz     loc_1800153B2
0x1800152e2  mov     rax, [rsp+48h+MatchAllKeyword]
0x1800152e7  mov     [r10+28h], r8b
0x1800152eb  mov     r8d, edi
0x1800152ee  mov     [r10+18h], rax
0x1800152f2  mov     [r10+10h], r9
0x1800152f6  mov     [r10+24h], edx
0x1800152fa  cmp     di, [r10+2Ah]
0x1800152ff  jnb     loc_1800153B2
0x180015305  mov     rax, [r10+40h]
0x180015309  mov     cl, [r10+28h]
0x18001530d  mov     r9d, r8d
0x180015310  cmp     [r9+rax], cl
0x180015314  jbe     short loc_18001531A
0x180015316  test    cl, cl
0x180015318  jnz     short loc_18001533C
0x18001531a  mov     rax, [r10+38h]
0x18001531e  mov     rdx, [rax+r9*8]
0x180015322  test    rdx, rdx
0x180015325  jz      short loc_180015341
0x180015327  test    [r10+10h], rdx
0x18001532b  jz      short loc_18001533C
0x18001532d  mov     rcx, [r10+18h]
0x180015331  mov     rax, rcx
0x180015334  and     rax, rdx
0x180015337  cmp     rax, rcx
0x18001533a  jz      short loc_180015341
0x18001533c  mov     r11b, dil
0x18001533f  jmp     short loc_180015344
0x180015341  mov     r11b, 1
0x180015344  mov     rax, [r10+30h]
0x180015348  mov     ecx, r8d
0x18001534b  shr     r9, 5
0x18001534f  mov     edx, 1
0x180015354  shl     edx, cl
0x180015356  lea     rcx, [rax+r9*4]
0x18001535a  mov     eax, [rcx]
0x18001535c  test    r11b, r11b
0x18001535f  jz      short loc_180015365
0x180015361  or      edx, eax
0x180015363  jmp     short loc_180015369
0x180015365  not     edx
0x180015367  and     edx, eax
0x180015369  mov     [rcx], edx
0x18001536b  inc     r8d
0x18001536e  movzx   eax, word ptr [r10+2Ah]
0x180015373  cmp     r8d, eax
0x180015376  jb      short loc_180015305
0x180015378  jmp     short loc_1800153B2
0x18001537a  movzx   eax, word ptr [r10+2Ah]
0x18001537f  mov     [r10+24h], edi
0x180015383  mov     [r10+28h], dil
0x180015387  mov     [r10+10h], rdi
0x18001538b  mov     [r10+18h], rdi
0x18001538f  test    ax, ax
0x180015392  jz      short loc_1800153B2
0x180015394  dec     eax
0x180015396  mov     ecx, 20h ; ' '
0x18001539b  cdq
0x18001539c  idiv    ecx
0x18001539e  mov     rcx, [r10+30h]; void *
0x1800153a2  xor     edx, edx; Val
0x1800153a4  inc     eax
0x1800153a6  movsxd  r8, eax
0x1800153a9  shl     r8, 2; Size
0x1800153ad  call    memset
0x1800153b2  mov     edx, ebx
0x1800153b4  call    HidClassEtwEnableCallback
0x1800153b9  mov     rbx, [rsp+48h+arg_0]
0x1800153be  add     rsp, 40h
0x1800153c2  pop     rdi
0x1800153c3  retn
```
