# FastWppCallback

- ea: `0x180003ce0`
- end: `0x180003d4a`
- name: `FastWppCallback`
- size: `106`
- prototype: `void __stdcall(LPCGUID SourceId, ULONG IsEnabled, UCHAR Level, ULONGLONG MatchAnyKeyword, ULONGLONG MatchAllKeyword, PEVENT_FILTER_DESCRIPTOR FilterData, PVOID CallbackContext)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180003c78`

## callees

- `0x180003ce0`

## pseudocode

```c
void __fastcall FastWppCallback(LPCGUID SourceId, ULONG IsEnabled, UCHAR Level, ULONGLONG MatchAnyKeyword)
{
  UCHAR v4; // dl
  unsigned __int8 v5; // al
  __int64 v6; // rcx
  __int64 v7; // rcx

  if ( IsEnabled )
  {
    if ( IsEnabled == 1 )
    {
      v4 = 5;
      if ( Level <= 5u )
        v4 = Level;
      v5 = 1;
      if ( !v4 )
        goto LABEL_13;
      do
      {
        v6 = v5++;
        *((_QWORD *)&g_rgFastWppLevelEnabledFlags + v6) = MatchAnyKeyword;
      }
      while ( v5 <= v4 );
      if ( v5 < 5u )
      {
LABEL_13:
        do
        {
          v7 = v5++;
          *((_QWORD *)&g_rgFastWppLevelEnabledFlags + v7) = 0;
        }
        while ( v5 < 5u );
      }
    }
  }
  else
  {
    g_rgFastWppLevelEnabledFlags = 0;
    xmmword_18001E1D0 = 0;
    xmmword_18001E1E0 = 0;
  }
}

```

## disassembly

```asm
0x180003ce0  test    edx, edx
0x180003ce2  jz      short loc_180003D31
0x180003ce4  cmp     edx, 1
0x180003ce7  jnz     short locret_180003D49
0x180003ce9  movzx   eax, r8b
0x180003ced  mov     edx, 5
0x180003cf2  cmp     r8b, dl
0x180003cf5  lea     r8, g_rgFastWppLevelEnabledFlags
0x180003cfc  cmovbe  edx, eax
0x180003cff  mov     al, 1
0x180003d01  cmp     dl, al
0x180003d03  jb      short loc_180003D21
0x180003d05  nop     word ptr [rax+rax+00000000h]
0x180003d10  movzx   ecx, al
0x180003d13  inc     al
0x180003d15  mov     [r8+rcx*8], r9
0x180003d19  cmp     al, dl
0x180003d1b  jbe     short loc_180003D10
0x180003d1d  cmp     al, 5
0x180003d1f  jnb     short locret_180003D49
0x180003d21  xor     edx, edx
0x180003d23  movzx   ecx, al
0x180003d26  inc     al
0x180003d28  mov     [r8+rcx*8], rdx
0x180003d2c  cmp     al, 5
0x180003d2e  jb      short loc_180003D23
0x180003d30  retn
0x180003d31  xorps   xmm0, xmm0
0x180003d34  movups  cs:g_rgFastWppLevelEnabledFlags, xmm0
0x180003d3b  movups  cs:xmmword_18001E1D0, xmm0
0x180003d42  movups  cs:xmmword_18001E1E0, xmm0
0x180003d49  retn
```
