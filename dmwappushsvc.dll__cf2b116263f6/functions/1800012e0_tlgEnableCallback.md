# _tlgEnableCallback

- ea: `0x1800012e0`
- end: `0x180001356`
- name: `_tlgEnableCallback`
- size: `118`
- prototype: `void __fastcall(LPCGUID SourceId, __int64 IsEnabled, __int64 Level, ULONGLONG MatchAnyKeyword, ULONGLONG MatchAllKeyword, PEVENT_FILTER_DESCRIPTOR FilterData, _QWORD *CallbackContext)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x1800012e0`
- `0x180012010`

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
0x1800012e0  sub     rsp, 48h
0x1800012e4  mov     r11, rcx
0x1800012e7  mov     rcx, [rsp+48h+CallbackContext]
0x1800012ef  test    rcx, rcx
0x1800012f2  jz      short loc_180001351
0x1800012f4  mov     r10, [rsp+48h+MatchAllKeyword]
0x1800012f9  mov     eax, edx
0x1800012fb  test    edx, edx
0x1800012fd  jz      short loc_180001322
0x1800012ff  cmp     eax, 1
0x180001302  jnz     short loc_180001328
0x180001304  test    r8b, r8b
0x180001307  jz      short loc_180001311
0x180001309  movzx   eax, r8b
0x18000130d  inc     eax
0x18000130f  jmp     short loc_180001316
0x180001311  mov     eax, 100h
0x180001316  mov     [rcx], eax
0x180001318  mov     [rcx+10h], r9
0x18000131c  mov     [rcx+18h], r10
0x180001320  jmp     short loc_180001328
0x180001322  mov     dword ptr [rcx], 0
0x180001328  mov     rax, [rcx+28h]
0x18000132c  test    rax, rax
0x18000132f  jz      short loc_180001351
0x180001331  mov     rcx, [rcx+30h]
0x180001335  mov     [rsp+48h+var_18], rcx
0x18000133a  mov     rcx, [rsp+48h+FilterData]
0x18000133f  mov     [rsp+48h+var_20], rcx
0x180001344  mov     rcx, r11
0x180001347  mov     [rsp+48h+var_28], r10
0x18000134c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001351  add     rsp, 48h
0x180001355  retn
```
