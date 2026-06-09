# McGenControlCallbackV2

- ea: `0x1800188a0`
- end: `0x1800189d6`
- name: `McGenControlCallbackV2`
- size: `310`
- prototype: `void __fastcall(ULONGLONG SourceId, __int64 IsEnabled, __int64 Level, ULONGLONG MatchAnyKeyword, ULONGLONG MatchAllKeyword, PEVENT_FILTER_DESCRIPTOR FilterData, ULONGLONG *CallbackContext)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x180001d3e`
- `0x1800188a0`
- `0x180018be0`
- `0x180018d2c`

## pseudocode

```c
void __fastcall McGenControlCallbackV2(
        _DWORD *SourceId,
        __int64 IsEnabled,
        __int64 Level,
        ULONGLONG MatchAnyKeyword,
        ULONGLONG MatchAllKeyword,
        PEVENT_FILTER_DESCRIPTOR FilterData,
        ULONGLONG *CallbackContext)
{
  unsigned __int8 v7; // cl
  __int64 v8; // rcx
  bool v9; // r11
  int v10; // edx

  if ( !CallbackContext )
    return;
  if ( !(_DWORD)IsEnabled )
  {
    *((_DWORD *)CallbackContext + 9) = 0;
    *((_BYTE *)CallbackContext + 40) = 0;
    CallbackContext[2] = 0;
    CallbackContext[3] = 0;
    if ( *((_WORD *)CallbackContext + 21) )
      memset_0((void *)CallbackContext[6], 0, 4LL * ((*((unsigned __int16 *)CallbackContext + 21) - 1) / 32 + 1));
    goto LABEL_22;
  }
  if ( (_DWORD)IsEnabled == 1 )
  {
    *((_BYTE *)CallbackContext + 40) = Level;
    Level = 0;
    CallbackContext[3] = MatchAllKeyword;
    CallbackContext[2] = MatchAnyKeyword;
    for ( *((_DWORD *)CallbackContext + 9) = 1;
          (unsigned int)Level < *((unsigned __int16 *)CallbackContext + 21);
          Level = (unsigned int)(Level + 1) )
    {
      v7 = *((_BYTE *)CallbackContext + 40);
      v9 = 0;
      if ( *(_BYTE *)((unsigned int)Level + CallbackContext[8]) <= v7 || !v7 )
      {
        v8 = *(_QWORD *)(CallbackContext[7] + 8LL * (unsigned int)Level);
        if ( !v8 || (v8 & CallbackContext[2]) != 0 && (v8 & CallbackContext[3]) == CallbackContext[3] )
          v9 = 1;
      }
      MatchAnyKeyword = (unsigned __int64)(unsigned int)Level >> 5;
      v10 = 1 << Level;
      SourceId = (_DWORD *)(CallbackContext[6] + 4 * MatchAnyKeyword);
      if ( v9 )
        IsEnabled = *SourceId | (unsigned int)v10;
      else
        IsEnabled = *SourceId & (unsigned int)~v10;
      *SourceId = IsEnabled;
    }
  }
  else
  {
    IsEnabled = (unsigned int)(IsEnabled - 1);
    if ( (unsigned int)IsEnabled >= 2 )
      return;
  }
  if ( CallbackContext == &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context )
  {
LABEL_22:
    SetLibParams(SourceId, IsEnabled, Level, MatchAnyKeyword);
    SetLibParamsWithBuffer();
  }
}

```

## disassembly

```asm
0x1800188a0  push    rbx
0x1800188a2  sub     rsp, 20h
0x1800188a6  mov     r10, [rsp+28h+CallbackContext]
0x1800188ab  xor     ebx, ebx
0x1800188ad  test    r10, r10
0x1800188b0  jz      loc_1800189CF
0x1800188b6  mov     eax, edx
0x1800188b8  test    edx, edx
0x1800188ba  jz      loc_18001898B
0x1800188c0  cmp     eax, 1
0x1800188c3  jz      short loc_1800188E6
0x1800188c5  test    edx, edx
0x1800188c7  jz      loc_1800189C5
0x1800188cd  sub     edx, 1
0x1800188d0  jz      loc_180018978
0x1800188d6  cmp     edx, 1
0x1800188d9  jz      loc_180018978
0x1800188df  add     rsp, 20h
0x1800188e3  pop     rbx
0x1800188e4  retn
0x1800188e6  mov     rax, [rsp+28h+MatchAllKeyword]
0x1800188eb  mov     [r10+28h], r8b
0x1800188ef  mov     r8d, ebx
0x1800188f2  mov     [r10+18h], rax
0x1800188f6  mov     [r10+10h], r9
0x1800188fa  mov     dword ptr [r10+24h], 1
0x180018902  cmp     bx, [r10+2Ah]
0x180018907  jnb     short loc_180018978
0x180018909  mov     rax, [r10+40h]
0x18001890d  mov     cl, [r10+28h]
0x180018911  mov     r9d, r8d
0x180018914  cmp     [r9+rax], cl
0x180018918  jbe     short loc_18001891E
0x18001891a  test    cl, cl
0x18001891c  jnz     short loc_18001893E
0x18001891e  mov     rax, [r10+38h]
0x180018922  mov     rcx, [rax+r9*8]
0x180018926  test    rcx, rcx
0x180018929  jz      short loc_180018943
0x18001892b  test    [r10+10h], rcx
0x18001892f  jz      short loc_18001893E
0x180018931  mov     rax, [r10+18h]
0x180018935  and     rax, rcx
0x180018938  cmp     rax, [r10+18h]
0x18001893c  jz      short loc_180018943
0x18001893e  mov     r11b, bl
0x180018941  jmp     short loc_180018946
0x180018943  mov     r11b, 1
0x180018946  mov     rax, [r10+30h]
0x18001894a  mov     ecx, r8d
0x18001894d  shr     r9, 5
0x180018951  mov     edx, 1
0x180018956  shl     edx, cl
0x180018958  lea     rcx, [rax+r9*4]
0x18001895c  test    r11b, r11b
0x18001895f  jz      short loc_180018965
0x180018961  or      edx, [rcx]
0x180018963  jmp     short loc_180018969
0x180018965  not     edx
0x180018967  and     edx, [rcx]
0x180018969  mov     [rcx], edx
0x18001896b  inc     r8d
0x18001896e  movzx   eax, word ptr [r10+2Ah]
0x180018973  cmp     r8d, eax
0x180018976  jb      short loc_180018909
0x180018978  lea     rax, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18001897f  cmp     r10, rax
0x180018982  jz      short loc_1800189C5
0x180018984  add     rsp, 20h
0x180018988  pop     rbx
0x180018989  retn
0x18001898b  mov     [r10+24h], ebx
0x18001898f  mov     [r10+28h], bl
0x180018993  mov     [r10+10h], rbx
0x180018997  mov     [r10+18h], rbx
0x18001899b  cmp     [r10+2Ah], bx
0x1800189a0  jbe     short loc_1800189C5
0x1800189a2  movzx   eax, word ptr [r10+2Ah]
0x1800189a7  mov     ecx, 20h ; ' '
0x1800189ac  dec     eax
0x1800189ae  cdq
0x1800189af  idiv    ecx
0x1800189b1  mov     rcx, [r10+30h]; void *
0x1800189b5  xor     edx, edx; Val
0x1800189b7  inc     eax
0x1800189b9  movsxd  r8, eax
0x1800189bc  shl     r8, 2; Size
0x1800189c0  call    memset_0
0x1800189c5  call    SetLibParams
0x1800189ca  call    SetLibParamsWithBuffer
0x1800189cf  add     rsp, 20h
0x1800189d3  pop     rbx
0x1800189d4  retn
```
