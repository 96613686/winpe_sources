# _tlgEnableCallback

- ea: `0x180001010`
- end: `0x180001087`
- name: `_tlgEnableCallback`
- size: `119`
- prototype: `void __stdcall(LPCGUID SourceId, ULONG IsEnabled, UCHAR Level, ULONGLONG MatchAnyKeyword, ULONGLONG MatchAllKeyword, PEVENT_FILTER_DESCRIPTOR FilterData, PVOID CallbackContext)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180001010`
- `0x180016010`

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
0x180001010  sub     rsp, 48h
0x180001014  mov     r11, rcx
0x180001017  mov     rcx, [rsp+48h+CallbackContext]
0x18000101f  test    rcx, rcx
0x180001022  jz      short loc_180001081
0x180001024  mov     r10, [rsp+48h+MatchAllKeyword]
0x180001029  mov     eax, edx
0x18000102b  test    edx, edx
0x18000102d  jz      short loc_180001052
0x18000102f  cmp     eax, 1
0x180001032  jnz     short loc_180001058
0x180001034  test    r8b, r8b
0x180001037  jz      short loc_180001041
0x180001039  movzx   eax, r8b
0x18000103d  inc     eax
0x18000103f  jmp     short loc_180001046
0x180001041  mov     eax, 100h
0x180001046  mov     [rcx], eax
0x180001048  mov     [rcx+10h], r9
0x18000104c  mov     [rcx+18h], r10
0x180001050  jmp     short loc_180001058
0x180001052  mov     dword ptr [rcx], 0
0x180001058  mov     rax, [rcx+28h]
0x18000105c  test    rax, rax
0x18000105f  jz      short loc_180001081
0x180001061  mov     rcx, [rcx+30h]
0x180001065  mov     [rsp+48h+var_18], rcx
0x18000106a  mov     rcx, [rsp+48h+FilterData]
0x18000106f  mov     [rsp+48h+var_20], rcx
0x180001074  mov     rcx, r11
0x180001077  mov     [rsp+48h+var_28], r10
0x18000107c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001081  add     rsp, 48h
0x180001085  retn
```
