# I_ReaderMonitorSetReaderActionEvent

- ea: `0x180003230`
- end: `0x180003362`
- name: `I_ReaderMonitorSetReaderActionEvent`
- size: `306`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x180003510`
- `0x180011c10`

## callees

- `0x180003230`
- `0x180004600`
- `0x180018b58`
- `0x180018bb4`
- `0x18002130c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180003276`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180003276`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000325a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000325a`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180003280`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180003280`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003307`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003307`

## pseudocode

```c
__int64 __fastcall I_ReaderMonitorSetReaderActionEvent(__int64 a1)
{
  __int64 v2; // rsi
  STRSAFE_LPSTR v3; // rcx
  unsigned int v4; // ebx
  int v5; // r8d
  int v6; // r9d
  char LastError; // di
  __int64 v9; // rcx

  WppTraceIndent(a1, 0);
  if ( WPP_GLOBAL_Control != (STRSAFE_LPSTR)&WPP_GLOBAL_Control
    && (WPP_GLOBAL_Control[28] & 2) != 0
    && (unsigned __int8)WPP_GLOBAL_Control[25] >= 5u )
  {
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, &WPP_173052b9a503333cb537dada0074ae31_Traceguids, WPP_pszIndent);
  }
  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 48));
  v2 = ++*(_QWORD *)(a1 + 264);
  *(_QWORD *)(a1 + 120) = v2;
  LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 48));
  v4 = SetEvent(*(HANDLE *)(a1 + 88));
  if ( !v4 )
  {
    LastError = GetLastError();
    WppTraceIndent(v9, 2);
    v3 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (STRSAFE_LPSTR)&WPP_GLOBAL_Control
      && (WPP_GLOBAL_Control[28] & 1) != 0
      && (unsigned __int8)WPP_GLOBAL_Control[25] >= 2u )
    {
      WPP_SF_sD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        14,
        (unsigned int)&WPP_173052b9a503333cb537dada0074ae31_Traceguids,
        WPP_pszIndent,
        LastError);
    }
  }
  WppTraceIndent(v3, 1);
  if ( WPP_GLOBAL_Control != (STRSAFE_LPSTR)&WPP_GLOBAL_Control
    && (WPP_GLOBAL_Control[28] & 2) != 0
    && (unsigned __int8)WPP_GLOBAL_Control[25] >= 5u )
  {
    WPP_SF_slI(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, v5, v6, v4, v2);
  }
  return v4;
}

```

## disassembly

```asm
0x180003230  push    rbx
0x180003232  push    rbp
0x180003233  push    rsi
0x180003234  push    rdi
0x180003235  sub     rsp, 38h
0x180003239  xor     edx, edx
0x18000323b  mov     rbx, rcx
0x18000323e  call    WppTraceIndent
0x180003243  mov     rcx, cs:WPP_GLOBAL_Control
0x18000324a  lea     rbp, WPP_GLOBAL_Control
0x180003251  cmp     rcx, rbp
0x180003254  jnz     short loc_1800032D2
0x180003256  lea     rcx, [rbx+30h]; lpCriticalSection
0x18000325a  call    cs:__imp_EnterCriticalSection
0x180003260  inc     qword ptr [rbx+108h]
0x180003267  lea     rcx, [rbx+30h]; lpCriticalSection
0x18000326b  mov     rsi, [rbx+108h]
0x180003272  mov     [rbx+78h], rsi
0x180003276  call    cs:__imp_LeaveCriticalSection
0x18000327c  mov     rcx, [rbx+58h]; hEvent
0x180003280  call    cs:__imp_SetEvent
0x180003286  mov     ebx, eax
0x180003288  test    eax, eax
0x18000328a  jz      short loc_180003307
0x18000328c  mov     edx, 1
0x180003291  call    WppTraceIndent
0x180003296  mov     rcx, cs:WPP_GLOBAL_Control
0x18000329d  cmp     rcx, rbp
0x1800032a0  jnz     short loc_1800032AD
0x1800032a2  mov     eax, ebx
0x1800032a4  add     rsp, 38h
0x1800032a8  pop     rdi
0x1800032a9  pop     rsi
0x1800032aa  pop     rbp
0x1800032ab  pop     rbx
0x1800032ac  retn
0x1800032ad  test    byte ptr [rcx+1Ch], 2
0x1800032b1  jz      short loc_1800032A2
0x1800032b3  cmp     byte ptr [rcx+19h], 5
0x1800032b7  jb      short loc_1800032A2
0x1800032b9  mov     rcx, [rcx+10h]
0x1800032bd  mov     edx, 0Fh
0x1800032c2  mov     [rsp+58h+var_30], rsi
0x1800032c7  mov     [rsp+58h+var_38], ebx
0x1800032cb  call    WPP_SF_slI
0x1800032d0  jmp     short loc_1800032A2
0x1800032d2  test    byte ptr [rcx+1Ch], 2
0x1800032d6  jz      loc_180003256
0x1800032dc  cmp     byte ptr [rcx+19h], 5
0x1800032e0  jb      loc_180003256
0x1800032e6  mov     r9, cs:WPP_pszIndent
0x1800032ed  lea     r8, WPP_173052b9a503333cb537dada0074ae31_Traceguids
0x1800032f4  mov     rcx, [rcx+10h]
0x1800032f8  mov     edx, 0Dh
0x1800032fd  call    WPP_SF_s
0x180003302  jmp     loc_180003256
0x180003307  call    cs:__imp_GetLastError
0x18000330d  mov     edx, 2
0x180003312  mov     edi, eax
0x180003314  call    WppTraceIndent
0x180003319  mov     rcx, cs:WPP_GLOBAL_Control
0x180003320  cmp     rcx, rbp
0x180003323  jz      loc_18000328C
0x180003329  test    byte ptr [rcx+1Ch], 1
0x18000332d  jz      loc_18000328C
0x180003333  cmp     byte ptr [rcx+19h], 2
0x180003337  jb      loc_18000328C
0x18000333d  mov     r9, cs:WPP_pszIndent
0x180003344  lea     r8, WPP_173052b9a503333cb537dada0074ae31_Traceguids
0x18000334b  mov     rcx, [rcx+10h]
0x18000334f  mov     edx, 0Eh
0x180003354  mov     [rsp+58h+var_38], edi
0x180003358  call    WPP_SF_sD
0x18000335d  jmp     loc_18000328C
```
