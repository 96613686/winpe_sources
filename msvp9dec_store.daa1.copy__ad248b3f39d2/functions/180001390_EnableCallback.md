# EnableCallback

- ea: `0x180001390`
- end: `0x180001412`
- name: `EnableCallback`
- size: `130`
- prototype: `void __stdcall(LPCGUID SourceId, ULONG IsEnabled, UCHAR Level, ULONGLONG MatchAnyKeyword, ULONGLONG MatchAllKeyword, PEVENT_FILTER_DESCRIPTOR FilterData, PVOID CallbackContext)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180001390`
- `0x180136810`

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
  void (__fastcall *v7)(LPCGUID, __int64, __int64, ULONGLONG, ULONGLONG, PEVENT_FILTER_DESCRIPTOR, _QWORD); // rax

  if ( CallbackContext )
  {
    if ( (_DWORD)IsEnabled )
    {
      if ( (_DWORD)IsEnabled == 1 )
      {
        CallbackContext[2] = MatchAnyKeyword;
        if ( (_BYTE)Level )
          *(_DWORD *)CallbackContext = (unsigned __int8)Level + 1;
        else
          *(_DWORD *)CallbackContext = 256;
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
0x180001390  sub     rsp, 48h
0x180001394  mov     r11, rcx
0x180001397  mov     rcx, [rsp+48h+CallbackContext]
0x18000139f  test    rcx, rcx
0x1800013a2  jz      short loc_18000140C
0x1800013a4  mov     r10, [rsp+48h+MatchAllKeyword]
0x1800013a9  mov     eax, edx
0x1800013ab  test    edx, edx
0x1800013ad  jz      short loc_1800013DC
0x1800013af  cmp     eax, 1
0x1800013b2  jnz     short loc_1800013E2
0x1800013b4  test    r8b, r8b
0x1800013b7  jz      short loc_1800013CB
0x1800013b9  movzx   eax, r8b
0x1800013bd  inc     eax
0x1800013bf  mov     [rcx+10h], r9
0x1800013c3  mov     [rcx], eax
0x1800013c5  mov     [rcx+18h], r10
0x1800013c9  jmp     short loc_1800013E2
0x1800013cb  mov     eax, 100h
0x1800013d0  mov     [rcx+10h], r9
0x1800013d4  mov     [rcx], eax
0x1800013d6  mov     [rcx+18h], r10
0x1800013da  jmp     short loc_1800013E2
0x1800013dc  mov     dword ptr [rcx], 0
0x1800013e2  mov     rax, [rcx+28h]
0x1800013e6  test    rax, rax
0x1800013e9  jz      short loc_18000140C
0x1800013eb  mov     rcx, [rcx+30h]
0x1800013ef  mov     [rsp+48h+var_18], rcx
0x1800013f4  mov     rcx, [rsp+48h+FilterData]
0x1800013f9  mov     [rsp+48h+var_20], rcx
0x1800013fe  mov     rcx, r11
0x180001401  mov     [rsp+48h+var_28], r10
0x180001406  call    cs:__guard_dispatch_icall_fptr
0x18000140c  add     rsp, 48h
0x180001410  retn
```
