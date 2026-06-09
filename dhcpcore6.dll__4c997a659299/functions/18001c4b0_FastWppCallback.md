# FastWppCallback

- ea: `0x18001c4b0`
- end: `0x18001c57c`
- name: `FastWppCallback`
- size: `204`
- prototype: `void __stdcall(LPCGUID SourceId, ULONG IsEnabled, UCHAR Level, ULONGLONG MatchAnyKeyword, ULONGLONG MatchAllKeyword, PEVENT_FILTER_DESCRIPTOR FilterData, PVOID CallbackContext)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18001c260`
- `0x18001c584`

## callees

- `0x18001c4b0`
- `0x18002b4b0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001c514`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001c514`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001c552`

## pseudocode

```c
void __fastcall FastWppCallback(LPCGUID SourceId, ULONG IsEnabled, UCHAR Level, ULONGLONG MatchAnyKeyword)
{
  ULONG v4; // edx
  UCHAR v5; // dl
  unsigned __int8 v6; // cl
  __int64 v7; // rax
  __int64 v8; // rax

  if ( IsEnabled )
  {
    v4 = IsEnabled - 1;
    if ( v4 )
    {
      if ( v4 != 1 )
        return;
    }
    else
    {
      v5 = 5;
      v6 = 1;
      if ( Level <= 5u )
        v5 = Level;
      if ( !v5 )
        goto LABEL_10;
      do
      {
        v7 = v6++;
        *((_QWORD *)&g_rgFastWppLevelEnabledFlags + v7) = MatchAnyKeyword;
      }
      while ( v6 <= v5 );
      while ( v6 < 5u )
      {
LABEL_10:
        v8 = v6++;
        *((_QWORD *)&g_rgFastWppLevelEnabledFlags + v8) = 0;
      }
    }
    EnterCriticalSection(&FastWppCallbackLock);
    if ( FastWppInitState == 2 )
    {
      DhcpFastWppCallback();
    }
    else if ( FastWppInitState == 1 )
    {
      FastWppInitState = 3;
    }
    LeaveCriticalSection(&FastWppCallbackLock);
  }
  else
  {
    g_rgFastWppLevelEnabledFlags = 0;
    xmmword_1800423D0 = 0;
    xmmword_1800423E0 = 0;
  }
}

```

## disassembly

```asm
0x18001c4b0  sub     rsp, 28h
0x18001c4b4  test    edx, edx
0x18001c4b6  jz      loc_18001C55E
0x18001c4bc  sub     edx, 1
0x18001c4bf  jz      short loc_18001C4CC
0x18001c4c1  cmp     edx, 1
0x18001c4c4  jnz     loc_18001C576
0x18001c4ca  jmp     short loc_18001C50D
0x18001c4cc  mov     r10d, 5
0x18001c4d2  movzx   eax, r8b
0x18001c4d6  cmp     r8b, r10b
0x18001c4d9  mov     edx, r10d
0x18001c4dc  mov     cl, 1
0x18001c4de  lea     r8, g_rgFastWppLevelEnabledFlags
0x18001c4e5  cmovbe  edx, eax
0x18001c4e8  cmp     dl, cl
0x18001c4ea  jb      short loc_18001C4FB
0x18001c4ec  movzx   eax, cl
0x18001c4ef  inc     cl
0x18001c4f1  mov     [r8+rax*8], r9
0x18001c4f5  cmp     cl, dl
0x18001c4f7  jbe     short loc_18001C4EC
0x18001c4f9  jmp     short loc_18001C508
0x18001c4fb  movzx   eax, cl
0x18001c4fe  inc     cl
0x18001c500  mov     qword ptr [r8+rax*8], 0
0x18001c508  cmp     cl, r10b
0x18001c50b  jb      short loc_18001C4FB
0x18001c50d  lea     rcx, FastWppCallbackLock; lpCriticalSection
0x18001c514  call    cs:__imp_EnterCriticalSection
0x18001c51b  nop     dword ptr [rax+rax+00h]
0x18001c520  mov     eax, cs:FastWppInitState
0x18001c526  cmp     eax, 2
0x18001c529  jnz     short loc_18001C532
0x18001c52b  call    DhcpFastWppCallback
0x18001c530  jmp     short loc_18001C547
0x18001c532  mov     eax, cs:FastWppInitState
0x18001c538  cmp     eax, 1
0x18001c53b  jnz     short loc_18001C547
0x18001c53d  mov     cs:FastWppInitState, 3
0x18001c547  lea     rcx, FastWppCallbackLock
0x18001c54e  add     rsp, 28h
0x18001c552  jmp     cs:__imp_LeaveCriticalSection
0x18001c55e  xorps   xmm0, xmm0
0x18001c561  movups  cs:g_rgFastWppLevelEnabledFlags, xmm0
0x18001c568  movups  cs:xmmword_1800423D0, xmm0
0x18001c56f  movups  cs:xmmword_1800423E0, xmm0
0x18001c576  add     rsp, 28h
0x18001c57a  retn
```
