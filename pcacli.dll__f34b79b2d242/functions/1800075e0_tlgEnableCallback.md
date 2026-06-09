# _tlgEnableCallback

- ea: `0x1800075e0`
- end: `0x180007660`
- name: `_tlgEnableCallback`
- size: `128`
- prototype: `void __stdcall(LPCGUID SourceId, ULONG IsEnabled, UCHAR Level, ULONGLONG MatchAnyKeyword, ULONGLONG MatchAllKeyword, PEVENT_FILTER_DESCRIPTOR FilterData, PVOID CallbackContext)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x1800075e0`
- `0x18000d010`

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
0x1800075e0  sub     rsp, 48h
0x1800075e4  mov     r11, rcx
0x1800075e7  mov     rcx, [rsp+48h+CallbackContext]
0x1800075ef  test    rcx, rcx
0x1800075f2  jz      short loc_18000765B
0x1800075f4  mov     r10, [rsp+48h+MatchAllKeyword]
0x1800075f9  mov     eax, edx
0x1800075fb  test    edx, edx
0x1800075fd  jz      short loc_18000762C
0x1800075ff  cmp     eax, 1
0x180007602  jnz     short loc_180007632
0x180007604  test    r8b, r8b
0x180007607  jz      short loc_18000761B
0x180007609  movzx   eax, r8b
0x18000760d  inc     eax
0x18000760f  mov     [rcx], eax
0x180007611  mov     [rcx+10h], r9
0x180007615  mov     [rcx+18h], r10
0x180007619  jmp     short loc_180007632
0x18000761b  mov     eax, 100h
0x180007620  mov     [rcx], eax
0x180007622  mov     [rcx+10h], r9
0x180007626  mov     [rcx+18h], r10
0x18000762a  jmp     short loc_180007632
0x18000762c  mov     dword ptr [rcx], 0
0x180007632  mov     rax, [rcx+28h]
0x180007636  test    rax, rax
0x180007639  jz      short loc_18000765B
0x18000763b  mov     rcx, [rcx+30h]
0x18000763f  mov     [rsp+48h+var_18], rcx
0x180007644  mov     rcx, [rsp+48h+FilterData]
0x180007649  mov     [rsp+48h+var_20], rcx
0x18000764e  mov     rcx, r11
0x180007651  mov     [rsp+48h+var_28], r10
0x180007656  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000765b  add     rsp, 48h
0x18000765f  retn
```
