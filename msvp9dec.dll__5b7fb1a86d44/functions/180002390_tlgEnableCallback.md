# _tlgEnableCallback

- ea: `0x180002390`
- end: `0x180002410`
- name: `_tlgEnableCallback`
- size: `128`
- prototype: `void __stdcall(LPCGUID SourceId, ULONG IsEnabled, UCHAR Level, ULONGLONG MatchAnyKeyword, ULONGLONG MatchAllKeyword, PEVENT_FILTER_DESCRIPTOR FilterData, PVOID CallbackContext)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180002390`
- `0x180006010`

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
  void (__fastcall *v7)(LPCGUID, __int64, __int64, ULONGLONG, ULONGLONG, PEVENT_FILTER_DESCRIPTOR, _QWORD); // rax

  if ( CallbackContext )
  {
    if ( (_DWORD)IsEnabled )
    {
      if ( (_DWORD)IsEnabled == 1 )
      {
        if ( (_BYTE)Level )
          *(_DWORD *)CallbackContext = (unsigned __int8)Level + 1;
        else
          *(_DWORD *)CallbackContext = 256;
        CallbackContext[2] = MatchAnyKeyword;
        CallbackContext[3] = MatchAllKeyword;
      }
    }
    else
    {
      *(_DWORD *)CallbackContext = 0;
    }
    v7 = (void (__fastcall *)(LPCGUID, __int64, __int64, ULONGLONG, ULONGLONG, PEVENT_FILTER_DESCRIPTOR, _QWORD))CallbackContext[5];
    if ( v7 )
      v7(SourceId, IsEnabled, Level, MatchAnyKeyword, MatchAllKeyword, FilterData, CallbackContext[6]);
  }
}

```

## disassembly

```asm
0x180002390  sub     rsp, 48h
0x180002394  mov     r11, rcx
0x180002397  mov     rcx, [rsp+48h+CallbackContext]
0x18000239f  test    rcx, rcx
0x1800023a2  jz      short loc_18000240B
0x1800023a4  mov     r10, [rsp+48h+MatchAllKeyword]
0x1800023a9  mov     eax, edx
0x1800023ab  test    edx, edx
0x1800023ad  jz      short loc_1800023DC
0x1800023af  cmp     eax, 1
0x1800023b2  jnz     short loc_1800023E2
0x1800023b4  test    r8b, r8b
0x1800023b7  jz      short loc_1800023CB
0x1800023b9  movzx   eax, r8b
0x1800023bd  inc     eax
0x1800023bf  mov     [rcx], eax
0x1800023c1  mov     [rcx+10h], r9
0x1800023c5  mov     [rcx+18h], r10
0x1800023c9  jmp     short loc_1800023E2
0x1800023cb  mov     eax, 100h
0x1800023d0  mov     [rcx], eax
0x1800023d2  mov     [rcx+10h], r9
0x1800023d6  mov     [rcx+18h], r10
0x1800023da  jmp     short loc_1800023E2
0x1800023dc  mov     dword ptr [rcx], 0
0x1800023e2  mov     rax, [rcx+28h]
0x1800023e6  test    rax, rax
0x1800023e9  jz      short loc_18000240B
0x1800023eb  mov     rcx, [rcx+30h]
0x1800023ef  mov     [rsp+48h+var_18], rcx
0x1800023f4  mov     rcx, [rsp+48h+FilterData]
0x1800023f9  mov     [rsp+48h+var_20], rcx
0x1800023fe  mov     rcx, r11
0x180002401  mov     [rsp+48h+var_28], r10
0x180002406  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000240b  add     rsp, 48h
0x18000240f  retn
```
