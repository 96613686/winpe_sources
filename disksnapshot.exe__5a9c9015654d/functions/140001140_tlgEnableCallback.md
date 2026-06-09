# _tlgEnableCallback

- ea: `0x140001140`
- end: `0x1400011b6`
- name: `_tlgEnableCallback`
- size: `118`
- prototype: `void __fastcall(LPCGUID SourceId, __int64 IsEnabled, __int64 Level, ULONGLONG MatchAnyKeyword, ULONGLONG MatchAllKeyword, PEVENT_FILTER_DESCRIPTOR FilterData, _QWORD *CallbackContext)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x140001140`
- `0x14000d010`

## pseudocode

```c
void __fastcall tlgEnableCallback(
        LPCGUID SourceId,
        __int64 IsEnabled,
        __int64 Level,
        ULONGLONG MatchAnyKeyword,
        ULONGLONG MatchAllKeyword,
        PEVENT_FILTER_DESCRIPTOR FilterData,
        _QWORD *CallbackContext)
{
  int v7; // eax
  void (__fastcall *v8)(LPCGUID, __int64, __int64, ULONGLONG, ULONGLONG, PEVENT_FILTER_DESCRIPTOR, _QWORD); // rax

  if ( CallbackContext )
  {
    if ( (_DWORD)IsEnabled )
    {
      if ( (_DWORD)IsEnabled == 1 )
      {
        if ( (_BYTE)Level )
          v7 = (unsigned __int8)Level + 1;
        else
          v7 = 256;
        *(_DWORD *)CallbackContext = v7;
        CallbackContext[2] = MatchAnyKeyword;
        CallbackContext[3] = MatchAllKeyword;
      }
    }
    else
    {
      *(_DWORD *)CallbackContext = 0;
    }
    v8 = (void (__fastcall *)(LPCGUID, __int64, __int64, ULONGLONG, ULONGLONG, PEVENT_FILTER_DESCRIPTOR, _QWORD))CallbackContext[5];
    if ( v8 )
      v8(SourceId, IsEnabled, Level, MatchAnyKeyword, MatchAllKeyword, FilterData, CallbackContext[6]);
  }
}

```

## disassembly

```asm
0x140001140  sub     rsp, 48h
0x140001144  mov     r11, rcx
0x140001147  mov     rcx, [rsp+48h+CallbackContext]
0x14000114f  test    rcx, rcx
0x140001152  jz      short loc_1400011B1
0x140001154  mov     r10, [rsp+48h+MatchAllKeyword]
0x140001159  mov     eax, edx
0x14000115b  test    edx, edx
0x14000115d  jz      short loc_140001182
0x14000115f  cmp     eax, 1
0x140001162  jnz     short loc_140001188
0x140001164  test    r8b, r8b
0x140001167  jz      short loc_140001171
0x140001169  movzx   eax, r8b
0x14000116d  inc     eax
0x14000116f  jmp     short loc_140001176
0x140001171  mov     eax, 100h
0x140001176  mov     [rcx], eax
0x140001178  mov     [rcx+10h], r9
0x14000117c  mov     [rcx+18h], r10
0x140001180  jmp     short loc_140001188
0x140001182  mov     dword ptr [rcx], 0
0x140001188  mov     rax, [rcx+28h]
0x14000118c  test    rax, rax
0x14000118f  jz      short loc_1400011B1
0x140001191  mov     rcx, [rcx+30h]
0x140001195  mov     [rsp+48h+var_18], rcx
0x14000119a  mov     rcx, [rsp+48h+FilterData]
0x14000119f  mov     [rsp+48h+var_20], rcx
0x1400011a4  mov     rcx, r11
0x1400011a7  mov     [rsp+48h+var_28], r10
0x1400011ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400011b1  add     rsp, 48h
0x1400011b5  retn
```
