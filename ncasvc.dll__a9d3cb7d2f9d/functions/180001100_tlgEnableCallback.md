# _tlgEnableCallback

- ea: `0x180001100`
- end: `0x180001177`
- name: `_tlgEnableCallback`
- size: `119`
- prototype: `void __fastcall(LPCGUID SourceId, __int64 IsEnabled, __int64 Level, ULONGLONG MatchAnyKeyword, ULONGLONG MatchAllKeyword, PEVENT_FILTER_DESCRIPTOR FilterData, _QWORD *CallbackContext)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180001100`
- `0x18001e010`

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
0x180001100  sub     rsp, 48h
0x180001104  mov     r11, rcx
0x180001107  mov     rcx, [rsp+48h+CallbackContext]
0x18000110f  test    rcx, rcx
0x180001112  jz      short loc_180001171
0x180001114  mov     r10, [rsp+48h+MatchAllKeyword]
0x180001119  mov     eax, edx
0x18000111b  test    edx, edx
0x18000111d  jz      short loc_180001142
0x18000111f  cmp     eax, 1
0x180001122  jnz     short loc_180001148
0x180001124  test    r8b, r8b
0x180001127  jz      short loc_180001131
0x180001129  movzx   eax, r8b
0x18000112d  inc     eax
0x18000112f  jmp     short loc_180001136
0x180001131  mov     eax, 100h
0x180001136  mov     [rcx], eax
0x180001138  mov     [rcx+10h], r9
0x18000113c  mov     [rcx+18h], r10
0x180001140  jmp     short loc_180001148
0x180001142  mov     dword ptr [rcx], 0
0x180001148  mov     rax, [rcx+28h]
0x18000114c  test    rax, rax
0x18000114f  jz      short loc_180001171
0x180001151  mov     rcx, [rcx+30h]
0x180001155  mov     [rsp+48h+var_18], rcx
0x18000115a  mov     rcx, [rsp+48h+FilterData]
0x18000115f  mov     [rsp+48h+var_20], rcx
0x180001164  mov     rcx, r11
0x180001167  mov     [rsp+48h+var_28], r10
0x18000116c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001171  add     rsp, 48h
0x180001175  retn
```
