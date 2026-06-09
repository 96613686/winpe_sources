# EnableCallback

- ea: `0x1400013f0`
- end: `0x140001468`
- name: `EnableCallback`
- size: `120`
- prototype: `void __stdcall(LPCGUID SourceId, ULONG IsEnabled, UCHAR Level, ULONGLONG MatchAnyKeyword, ULONGLONG MatchAllKeyword, PEVENT_FILTER_DESCRIPTOR FilterData, PVOID CallbackContext)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x1400013f0`
- `0x1400c7b20`

## pseudocode

```c
void __fastcall EnableCallback(
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
0x1400013f0  sub     rsp, 48h
0x1400013f4  mov     r11, rcx
0x1400013f7  mov     rcx, [rsp+48h+CallbackContext]
0x1400013ff  test    rcx, rcx
0x140001402  jz      short loc_140001462
0x140001404  mov     r10, [rsp+48h+MatchAllKeyword]
0x140001409  mov     eax, edx
0x14000140b  test    edx, edx
0x14000140d  jz      short loc_140001432
0x14000140f  cmp     eax, 1
0x140001412  jnz     short loc_140001438
0x140001414  test    r8b, r8b
0x140001417  jz      short loc_140001421
0x140001419  movzx   eax, r8b
0x14000141d  inc     eax
0x14000141f  jmp     short loc_140001426
0x140001421  mov     eax, 100h
0x140001426  mov     [rcx], eax
0x140001428  mov     [rcx+10h], r9
0x14000142c  mov     [rcx+18h], r10
0x140001430  jmp     short loc_140001438
0x140001432  mov     dword ptr [rcx], 0
0x140001438  mov     rax, [rcx+28h]
0x14000143c  test    rax, rax
0x14000143f  jz      short loc_140001462
0x140001441  mov     rcx, [rcx+30h]
0x140001445  mov     [rsp+48h+var_18], rcx
0x14000144a  mov     rcx, [rsp+48h+FilterData]
0x14000144f  mov     [rsp+48h+var_20], rcx
0x140001454  mov     rcx, r11
0x140001457  mov     [rsp+48h+var_28], r10
0x14000145c  call    cs:__guard_dispatch_icall_fptr
0x140001462  add     rsp, 48h
0x140001466  retn
```
