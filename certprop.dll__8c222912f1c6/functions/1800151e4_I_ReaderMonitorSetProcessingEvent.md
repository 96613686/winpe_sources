# I_ReaderMonitorSetProcessingEvent

- ea: `0x1800151e4`
- end: `0x1800152f7`
- name: `I_ReaderMonitorSetProcessingEvent`
- size: `275`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180004900`

## callees

- `0x180004600`
- `0x1800151e4`
- `0x180018b58`
- `0x180018bb4`
- `0x18002130c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180015256`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180015256`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180015237`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180015237`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180015260`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180015260`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001526c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001526c`

## pseudocode

```c
__int64 __fastcall I_ReaderMonitorSetProcessingEvent(__int64 a1)
{
  __int64 v2; // rsi
  STRSAFE_LPSTR v3; // rcx
  unsigned int v4; // ebx
  char LastError; // di
  __int64 v6; // rcx
  int v7; // r8d
  int v8; // r9d

  WppTraceIndent(a1, 0);
  if ( WPP_GLOBAL_Control != (STRSAFE_LPSTR)&WPP_GLOBAL_Control
    && (WPP_GLOBAL_Control[28] & 2) != 0
    && (unsigned __int8)WPP_GLOBAL_Control[25] >= 5u )
  {
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, &WPP_173052b9a503333cb537dada0074ae31_Traceguids, WPP_pszIndent);
  }
  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 48));
  v2 = ++*(_QWORD *)(a1 + 264);
  *(_QWORD *)(a1 + 128) = v2;
  LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 48));
  v4 = SetEvent(*(HANDLE *)(a1 + 104));
  if ( !v4 )
  {
    LastError = GetLastError();
    WppTraceIndent(v6, 2);
    v3 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (STRSAFE_LPSTR)&WPP_GLOBAL_Control
      && (WPP_GLOBAL_Control[28] & 1) != 0
      && (unsigned __int8)WPP_GLOBAL_Control[25] >= 2u )
    {
      WPP_SF_sD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        11,
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
    WPP_SF_slI(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, v7, v8, v4, v2);
  }
  return v4;
}

```

## disassembly

```asm
0x1800151e4  push    rbx
0x1800151e6  push    rsi
0x1800151e7  push    rdi
0x1800151e8  push    r14
0x1800151ea  sub     rsp, 38h
0x1800151ee  xor     edx, edx
0x1800151f0  mov     rdi, rcx
0x1800151f3  call    WppTraceIndent
0x1800151f8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800151ff  lea     r14, WPP_GLOBAL_Control
0x180015206  cmp     rcx, r14
0x180015209  jz      short loc_180015233
0x18001520b  test    byte ptr [rcx+1Ch], 2
0x18001520f  jz      short loc_180015233
0x180015211  cmp     byte ptr [rcx+19h], 5
0x180015215  jb      short loc_180015233
0x180015217  mov     r9, cs:WPP_pszIndent
0x18001521e  lea     r8, WPP_173052b9a503333cb537dada0074ae31_Traceguids
0x180015225  mov     rcx, [rcx+10h]
0x180015229  mov     edx, 0Ah
0x18001522e  call    WPP_SF_s
0x180015233  lea     rcx, [rdi+30h]; lpCriticalSection
0x180015237  call    cs:__imp_EnterCriticalSection
0x18001523d  inc     qword ptr [rdi+108h]
0x180015244  lea     rcx, [rdi+30h]; lpCriticalSection
0x180015248  mov     rsi, [rdi+108h]
0x18001524f  mov     [rdi+80h], rsi
0x180015256  call    cs:__imp_LeaveCriticalSection
0x18001525c  mov     rcx, [rdi+68h]; hEvent
0x180015260  call    cs:__imp_SetEvent
0x180015266  mov     ebx, eax
0x180015268  test    eax, eax
0x18001526a  jnz     short loc_1800152B2
0x18001526c  call    cs:__imp_GetLastError
0x180015272  lea     edx, [rbx+2]
0x180015275  mov     edi, eax
0x180015277  call    WppTraceIndent
0x18001527c  mov     rcx, cs:WPP_GLOBAL_Control
0x180015283  cmp     rcx, r14
0x180015286  jz      short loc_1800152B2
0x180015288  test    byte ptr [rcx+1Ch], 1
0x18001528c  jz      short loc_1800152B2
0x18001528e  cmp     byte ptr [rcx+19h], 2
0x180015292  jb      short loc_1800152B2
0x180015294  mov     r9, cs:WPP_pszIndent
0x18001529b  lea     edx, [rbx+0Bh]
0x18001529e  mov     rcx, [rcx+10h]
0x1800152a2  lea     r8, WPP_173052b9a503333cb537dada0074ae31_Traceguids
0x1800152a9  mov     [rsp+58h+var_38], edi
0x1800152ad  call    WPP_SF_sD
0x1800152b2  mov     edx, 1
0x1800152b7  call    WppTraceIndent
0x1800152bc  mov     rcx, cs:WPP_GLOBAL_Control
0x1800152c3  cmp     rcx, r14
0x1800152c6  jz      short loc_1800152EB
0x1800152c8  test    byte ptr [rcx+1Ch], 2
0x1800152cc  jz      short loc_1800152EB
0x1800152ce  cmp     byte ptr [rcx+19h], 5
0x1800152d2  jb      short loc_1800152EB
0x1800152d4  mov     rcx, [rcx+10h]
0x1800152d8  mov     edx, 0Ch
0x1800152dd  mov     [rsp+58h+var_30], rsi
0x1800152e2  mov     [rsp+58h+var_38], ebx
0x1800152e6  call    WPP_SF_slI
0x1800152eb  mov     eax, ebx
0x1800152ed  add     rsp, 38h
0x1800152f1  pop     r14
0x1800152f3  pop     rdi
0x1800152f4  pop     rsi
0x1800152f5  pop     rbx
0x1800152f6  retn
```
