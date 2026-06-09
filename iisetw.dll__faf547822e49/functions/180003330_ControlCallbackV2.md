# ControlCallbackV2

- ea: `0x180003330`
- end: `0x180003372`
- name: `ControlCallbackV2`
- size: `66`
- prototype: `void __fastcall(LPCGUID SourceId, ULONG IsEnabled, UCHAR Level, ULONGLONG MatchAnyKeyword, ULONGLONG MatchAllKeyword, PEVENT_FILTER_DESCRIPTOR FilterData, PVOID CallbackContext)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180004010`

## pseudocode

```c
void __fastcall ControlCallbackV2(
        LPCGUID SourceId,
        ULONG IsEnabled,
        UCHAR Level,
        ULONGLONG MatchAnyKeyword,
        ULONGLONG MatchAllKeyword,
        PEVENT_FILTER_DESCRIPTOR FilterData,
        PVOID CallbackContext)
{
  ULONGLONG v7; // [rsp+20h] [rbp-28h]

  v7 = MatchAnyKeyword;
  LOBYTE(MatchAnyKeyword) = Level;
  (*(void (__fastcall **)(PVOID, LPCGUID, _QWORD, ULONGLONG, ULONGLONG, ULONGLONG, PEVENT_FILTER_DESCRIPTOR))(*(_QWORD *)CallbackContext + 16LL))(
    CallbackContext,
    SourceId,
    IsEnabled,
    MatchAnyKeyword,
    v7,
    MatchAllKeyword,
    FilterData);
}

```

## disassembly

```asm
0x180003330  sub     rsp, 48h
0x180003334  mov     r10, [rsp+48h+FilterData]
0x180003339  mov     r11, rcx
0x18000333c  mov     rcx, [rsp+48h+CallbackContext]
0x180003344  mov     [rsp+48h+var_18], r10
0x180003349  mov     r10, [rsp+48h+MatchAllKeyword]
0x18000334e  mov     [rsp+48h+var_20], r10
0x180003353  mov     rax, [rcx]
0x180003356  mov     [rsp+48h+var_28], r9
0x18000335b  mov     r9b, r8b
0x18000335e  mov     r8d, edx
0x180003361  mov     rdx, r11
0x180003364  mov     rax, [rax+10h]
0x180003368  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000336d  add     rsp, 48h
0x180003371  retn
```
