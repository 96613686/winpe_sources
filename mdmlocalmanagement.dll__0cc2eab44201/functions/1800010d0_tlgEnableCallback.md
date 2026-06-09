# _tlgEnableCallback

- ea: `0x1800010d0`
- end: `0x180001147`
- name: `_tlgEnableCallback`
- size: `119`
- prototype: `void __stdcall(LPCGUID SourceId, ULONG IsEnabled, UCHAR Level, ULONGLONG MatchAnyKeyword, ULONGLONG MatchAllKeyword, PEVENT_FILTER_DESCRIPTOR FilterData, PVOID CallbackContext)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x1800010d0`
- `0x180007010`

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
0x1800010d0  sub     rsp, 48h
0x1800010d4  mov     r11, rcx
0x1800010d7  mov     rcx, [rsp+48h+CallbackContext]
0x1800010df  test    rcx, rcx
0x1800010e2  jz      short loc_180001141
0x1800010e4  mov     r10, [rsp+48h+MatchAllKeyword]
0x1800010e9  mov     eax, edx
0x1800010eb  test    edx, edx
0x1800010ed  jz      short loc_180001112
0x1800010ef  cmp     eax, 1
0x1800010f2  jnz     short loc_180001118
0x1800010f4  test    r8b, r8b
0x1800010f7  jz      short loc_180001101
0x1800010f9  movzx   eax, r8b
0x1800010fd  inc     eax
0x1800010ff  jmp     short loc_180001106
0x180001101  mov     eax, 100h
0x180001106  mov     [rcx], eax
0x180001108  mov     [rcx+10h], r9
0x18000110c  mov     [rcx+18h], r10
0x180001110  jmp     short loc_180001118
0x180001112  mov     dword ptr [rcx], 0
0x180001118  mov     rax, [rcx+28h]
0x18000111c  test    rax, rax
0x18000111f  jz      short loc_180001141
0x180001121  mov     rcx, [rcx+30h]
0x180001125  mov     [rsp+48h+var_18], rcx
0x18000112a  mov     rcx, [rsp+48h+FilterData]
0x18000112f  mov     [rsp+48h+var_20], rcx
0x180001134  mov     rcx, r11
0x180001137  mov     [rsp+48h+var_28], r10
0x18000113c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001141  add     rsp, 48h
0x180001145  retn
```
