# _tlgEnableCallback

- ea: `0x140001260`
- end: `0x1400012d6`
- name: `_tlgEnableCallback`
- size: `118`
- prototype: `void __stdcall(LPCGUID SourceId, ULONG IsEnabled, UCHAR Level, ULONGLONG MatchAnyKeyword, ULONGLONG MatchAllKeyword, PEVENT_FILTER_DESCRIPTOR FilterData, PVOID CallbackContext)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x140001260`
- `0x140006010`

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
0x140001260  sub     rsp, 48h
0x140001264  mov     r11, rcx
0x140001267  mov     rcx, [rsp+48h+CallbackContext]
0x14000126f  test    rcx, rcx
0x140001272  jz      short loc_1400012D1
0x140001274  mov     r10, [rsp+48h+MatchAllKeyword]
0x140001279  mov     eax, edx
0x14000127b  test    edx, edx
0x14000127d  jz      short loc_1400012A2
0x14000127f  cmp     eax, 1
0x140001282  jnz     short loc_1400012A8
0x140001284  test    r8b, r8b
0x140001287  jz      short loc_140001291
0x140001289  movzx   eax, r8b
0x14000128d  inc     eax
0x14000128f  jmp     short loc_140001296
0x140001291  mov     eax, 100h
0x140001296  mov     [rcx], eax
0x140001298  mov     [rcx+10h], r9
0x14000129c  mov     [rcx+18h], r10
0x1400012a0  jmp     short loc_1400012A8
0x1400012a2  mov     dword ptr [rcx], 0
0x1400012a8  mov     rax, [rcx+28h]
0x1400012ac  test    rax, rax
0x1400012af  jz      short loc_1400012D1
0x1400012b1  mov     rcx, [rcx+30h]
0x1400012b5  mov     [rsp+48h+var_18], rcx
0x1400012ba  mov     rcx, [rsp+48h+FilterData]
0x1400012bf  mov     [rsp+48h+var_20], rcx
0x1400012c4  mov     rcx, r11
0x1400012c7  mov     [rsp+48h+var_28], r10
0x1400012cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400012d1  add     rsp, 48h
0x1400012d5  retn
```
