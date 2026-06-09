# _tlgEnableCallback

- ea: `0x180001630`
- end: `0x1800016a7`
- name: `_tlgEnableCallback`
- size: `119`
- prototype: `void __stdcall(LPCGUID SourceId, ULONG IsEnabled, UCHAR Level, ULONGLONG MatchAnyKeyword, ULONGLONG MatchAllKeyword, PEVENT_FILTER_DESCRIPTOR FilterData, PVOID CallbackContext)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180001630`
- `0x18001e010`

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
0x180001630  sub     rsp, 48h
0x180001634  mov     r11, rcx
0x180001637  mov     rcx, [rsp+48h+CallbackContext]
0x18000163f  test    rcx, rcx
0x180001642  jz      short loc_1800016A1
0x180001644  mov     r10, [rsp+48h+MatchAllKeyword]
0x180001649  mov     eax, edx
0x18000164b  test    edx, edx
0x18000164d  jz      short loc_180001672
0x18000164f  cmp     eax, 1
0x180001652  jnz     short loc_180001678
0x180001654  test    r8b, r8b
0x180001657  jz      short loc_180001661
0x180001659  movzx   eax, r8b
0x18000165d  inc     eax
0x18000165f  jmp     short loc_180001666
0x180001661  mov     eax, 100h
0x180001666  mov     [rcx], eax
0x180001668  mov     [rcx+10h], r9
0x18000166c  mov     [rcx+18h], r10
0x180001670  jmp     short loc_180001678
0x180001672  mov     dword ptr [rcx], 0
0x180001678  mov     rax, [rcx+28h]
0x18000167c  test    rax, rax
0x18000167f  jz      short loc_1800016A1
0x180001681  mov     rcx, [rcx+30h]
0x180001685  mov     [rsp+48h+var_18], rcx
0x18000168a  mov     rcx, [rsp+48h+FilterData]
0x18000168f  mov     [rsp+48h+var_20], rcx
0x180001694  mov     rcx, r11
0x180001697  mov     [rsp+48h+var_28], r10
0x18000169c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800016a1  add     rsp, 48h
0x1800016a5  retn
```
