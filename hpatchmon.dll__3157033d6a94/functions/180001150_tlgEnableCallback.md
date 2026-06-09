# _tlgEnableCallback

- ea: `0x180001150`
- end: `0x1800011c6`
- name: `_tlgEnableCallback`
- size: `118`
- prototype: `void __fastcall(LPCGUID SourceId, __int64 IsEnabled, __int64 Level, ULONGLONG MatchAnyKeyword, ULONGLONG MatchAllKeyword, PEVENT_FILTER_DESCRIPTOR FilterData, _QWORD *CallbackContext)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180001150`
- `0x180015010`

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
0x180001150  sub     rsp, 48h
0x180001154  mov     r11, rcx
0x180001157  mov     rcx, [rsp+48h+CallbackContext]
0x18000115f  test    rcx, rcx
0x180001162  jz      short loc_1800011C1
0x180001164  mov     r10, [rsp+48h+MatchAllKeyword]
0x180001169  mov     eax, edx
0x18000116b  test    edx, edx
0x18000116d  jz      short loc_180001192
0x18000116f  cmp     eax, 1
0x180001172  jnz     short loc_180001198
0x180001174  test    r8b, r8b
0x180001177  jz      short loc_180001181
0x180001179  movzx   eax, r8b
0x18000117d  inc     eax
0x18000117f  jmp     short loc_180001186
0x180001181  mov     eax, 100h
0x180001186  mov     [rcx], eax
0x180001188  mov     [rcx+10h], r9
0x18000118c  mov     [rcx+18h], r10
0x180001190  jmp     short loc_180001198
0x180001192  mov     dword ptr [rcx], 0
0x180001198  mov     rax, [rcx+28h]
0x18000119c  test    rax, rax
0x18000119f  jz      short loc_1800011C1
0x1800011a1  mov     rcx, [rcx+30h]
0x1800011a5  mov     [rsp+48h+var_18], rcx
0x1800011aa  mov     rcx, [rsp+48h+FilterData]
0x1800011af  mov     [rsp+48h+var_20], rcx
0x1800011b4  mov     rcx, r11
0x1800011b7  mov     [rsp+48h+var_28], r10
0x1800011bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800011c1  add     rsp, 48h
0x1800011c5  retn
```
