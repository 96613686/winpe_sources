# _tlgEnableCallback

- ea: `0x180001a00`
- end: `0x180001a76`
- name: `_tlgEnableCallback`
- size: `118`
- prototype: `void __fastcall(LPCGUID SourceId, __int64 IsEnabled, __int64 Level, ULONGLONG MatchAnyKeyword, ULONGLONG MatchAllKeyword, PEVENT_FILTER_DESCRIPTOR FilterData, _QWORD *CallbackContext)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180001a00`
- `0x180023010`

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
0x180001a00  sub     rsp, 48h
0x180001a04  mov     r11, rcx
0x180001a07  mov     rcx, [rsp+48h+CallbackContext]
0x180001a0f  test    rcx, rcx
0x180001a12  jz      short loc_180001A71
0x180001a14  mov     r10, [rsp+48h+MatchAllKeyword]
0x180001a19  mov     eax, edx
0x180001a1b  test    edx, edx
0x180001a1d  jz      short loc_180001A42
0x180001a1f  cmp     eax, 1
0x180001a22  jnz     short loc_180001A48
0x180001a24  test    r8b, r8b
0x180001a27  jz      short loc_180001A31
0x180001a29  movzx   eax, r8b
0x180001a2d  inc     eax
0x180001a2f  jmp     short loc_180001A36
0x180001a31  mov     eax, 100h
0x180001a36  mov     [rcx], eax
0x180001a38  mov     [rcx+10h], r9
0x180001a3c  mov     [rcx+18h], r10
0x180001a40  jmp     short loc_180001A48
0x180001a42  mov     dword ptr [rcx], 0
0x180001a48  mov     rax, [rcx+28h]
0x180001a4c  test    rax, rax
0x180001a4f  jz      short loc_180001A71
0x180001a51  mov     rcx, [rcx+30h]
0x180001a55  mov     [rsp+48h+var_18], rcx
0x180001a5a  mov     rcx, [rsp+48h+FilterData]
0x180001a5f  mov     [rsp+48h+var_20], rcx
0x180001a64  mov     rcx, r11
0x180001a67  mov     [rsp+48h+var_28], r10
0x180001a6c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001a71  add     rsp, 48h
0x180001a75  retn
```
