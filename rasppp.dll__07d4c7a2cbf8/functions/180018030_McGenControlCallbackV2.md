# McGenControlCallbackV2

- ea: `0x180018030`
- end: `0x180018163`
- name: `McGenControlCallbackV2`
- size: `307`
- prototype: `void __stdcall(LPCGUID SourceId, ULONG IsEnabled, UCHAR Level, ULONGLONG MatchAnyKeyword, ULONGLONG MatchAllKeyword, PEVENT_FILTER_DESCRIPTOR FilterData, PVOID CallbackContext)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x180001d3e`
- `0x180018030`
- `0x180018360`
- `0x1800184ac`

## pseudocode

```c
void __fastcall McGenControlCallbackV2(
        ULONGLONG SourceId,
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
      SourceId = CallbackContext[6] + 4 * MatchAnyKeyword;
      if ( v9 )
        IsEnabled = *(_DWORD *)SourceId | (unsigned int)v10;
      else
        IsEnabled = *(_DWORD *)SourceId & (unsigned int)~v10;
      *(_DWORD *)SourceId = IsEnabled;
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
0x180018030  push    rbx
0x180018032  sub     rsp, 20h
0x180018036  mov     r10, [rsp+28h+CallbackContext]
0x18001803b  xor     ebx, ebx
0x18001803d  test    r10, r10
0x180018040  jz      loc_18001815D
0x180018046  mov     eax, edx
0x180018048  test    edx, edx
0x18001804a  jz      loc_180018119
0x180018050  cmp     eax, 1
0x180018053  jz      short loc_180018075
0x180018055  test    edx, edx
0x180018057  jz      loc_180018153
0x18001805d  sub     edx, 1
0x180018060  jz      loc_180018107
0x180018066  cmp     edx, 1
0x180018069  jz      loc_180018107
0x18001806f  add     rsp, 20h
0x180018073  pop     rbx
0x180018074  retn
0x180018075  mov     rax, [rsp+28h+MatchAllKeyword]
0x18001807a  mov     [r10+28h], r8b
0x18001807e  mov     r8d, ebx
0x180018081  mov     [r10+18h], rax
0x180018085  mov     [r10+10h], r9
0x180018089  mov     dword ptr [r10+24h], 1
0x180018091  cmp     bx, [r10+2Ah]
0x180018096  jnb     short loc_180018107
0x180018098  mov     rax, [r10+40h]
0x18001809c  mov     cl, [r10+28h]
0x1800180a0  mov     r9d, r8d
0x1800180a3  cmp     [r9+rax], cl
0x1800180a7  jbe     short loc_1800180AD
0x1800180a9  test    cl, cl
0x1800180ab  jnz     short loc_1800180CD
0x1800180ad  mov     rax, [r10+38h]
0x1800180b1  mov     rcx, [rax+r9*8]
0x1800180b5  test    rcx, rcx
0x1800180b8  jz      short loc_1800180D2
0x1800180ba  test    [r10+10h], rcx
0x1800180be  jz      short loc_1800180CD
0x1800180c0  mov     rax, [r10+18h]
0x1800180c4  and     rax, rcx
0x1800180c7  cmp     rax, [r10+18h]
0x1800180cb  jz      short loc_1800180D2
0x1800180cd  mov     r11b, bl
0x1800180d0  jmp     short loc_1800180D5
0x1800180d2  mov     r11b, 1
0x1800180d5  mov     rax, [r10+30h]
0x1800180d9  mov     ecx, r8d
0x1800180dc  shr     r9, 5
0x1800180e0  mov     edx, 1
0x1800180e5  shl     edx, cl
0x1800180e7  lea     rcx, [rax+r9*4]
0x1800180eb  test    r11b, r11b
0x1800180ee  jz      short loc_1800180F4
0x1800180f0  or      edx, [rcx]
0x1800180f2  jmp     short loc_1800180F8
0x1800180f4  not     edx
0x1800180f6  and     edx, [rcx]
0x1800180f8  mov     [rcx], edx
0x1800180fa  inc     r8d
0x1800180fd  movzx   eax, word ptr [r10+2Ah]
0x180018102  cmp     r8d, eax
0x180018105  jb      short loc_180018098
0x180018107  lea     rax, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18001810e  cmp     r10, rax
0x180018111  jz      short loc_180018153
0x180018113  add     rsp, 20h
0x180018117  pop     rbx
0x180018118  retn
0x180018119  mov     [r10+24h], ebx
0x18001811d  mov     [r10+28h], bl
0x180018121  mov     [r10+10h], rbx
0x180018125  mov     [r10+18h], rbx
0x180018129  cmp     [r10+2Ah], bx
0x18001812e  jbe     short loc_180018153
0x180018130  movzx   eax, word ptr [r10+2Ah]
0x180018135  mov     ecx, 20h ; ' '
0x18001813a  dec     eax
0x18001813c  cdq
0x18001813d  idiv    ecx
0x18001813f  mov     rcx, [r10+30h]; void *
0x180018143  xor     edx, edx; Val
0x180018145  inc     eax
0x180018147  movsxd  r8, eax
0x18001814a  shl     r8, 2; Size
0x18001814e  call    memset_0
0x180018153  call    SetLibParams
0x180018158  call    SetLibParamsWithBuffer
0x18001815d  add     rsp, 20h
0x180018161  pop     rbx
0x180018162  retn
```
