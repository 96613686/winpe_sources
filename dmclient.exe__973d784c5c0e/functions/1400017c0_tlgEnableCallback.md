# _tlgEnableCallback

- ea: `0x1400017c0`
- end: `0x140001837`
- name: `_tlgEnableCallback`
- size: `119`
- prototype: `void __stdcall(LPCGUID SourceId, ULONG IsEnabled, UCHAR Level, ULONGLONG MatchAnyKeyword, ULONGLONG MatchAllKeyword, PEVENT_FILTER_DESCRIPTOR FilterData, PVOID CallbackContext)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x1400017c0`
- `0x14001a010`

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
0x1400017c0  sub     rsp, 48h
0x1400017c4  mov     r11, rcx
0x1400017c7  mov     rcx, [rsp+48h+CallbackContext]
0x1400017cf  test    rcx, rcx
0x1400017d2  jz      short loc_140001831
0x1400017d4  mov     r10, [rsp+48h+MatchAllKeyword]
0x1400017d9  mov     eax, edx
0x1400017db  test    edx, edx
0x1400017dd  jz      short loc_140001802
0x1400017df  cmp     eax, 1
0x1400017e2  jnz     short loc_140001808
0x1400017e4  test    r8b, r8b
0x1400017e7  jz      short loc_1400017F1
0x1400017e9  movzx   eax, r8b
0x1400017ed  inc     eax
0x1400017ef  jmp     short loc_1400017F6
0x1400017f1  mov     eax, 100h
0x1400017f6  mov     [rcx], eax
0x1400017f8  mov     [rcx+10h], r9
0x1400017fc  mov     [rcx+18h], r10
0x140001800  jmp     short loc_140001808
0x140001802  mov     dword ptr [rcx], 0
0x140001808  mov     rax, [rcx+28h]
0x14000180c  test    rax, rax
0x14000180f  jz      short loc_140001831
0x140001811  mov     rcx, [rcx+30h]
0x140001815  mov     [rsp+48h+var_18], rcx
0x14000181a  mov     rcx, [rsp+48h+FilterData]
0x14000181f  mov     [rsp+48h+var_20], rcx
0x140001824  mov     rcx, r11
0x140001827  mov     [rsp+48h+var_28], r10
0x14000182c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140001831  add     rsp, 48h
0x140001835  retn
```
