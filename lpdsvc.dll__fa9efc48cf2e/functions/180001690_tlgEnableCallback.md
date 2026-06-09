# _tlgEnableCallback

- ea: `0x180001690`
- end: `0x180001706`
- name: `_tlgEnableCallback`
- size: `118`
- prototype: `void __fastcall(LPCGUID SourceId, __int64 IsEnabled, __int64 Level, ULONGLONG MatchAnyKeyword, ULONGLONG MatchAllKeyword, PEVENT_FILTER_DESCRIPTOR FilterData, _QWORD *CallbackContext)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180001690`
- `0x18000e010`

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
0x180001690  sub     rsp, 48h
0x180001694  mov     r11, rcx
0x180001697  mov     rcx, [rsp+48h+CallbackContext]
0x18000169f  test    rcx, rcx
0x1800016a2  jz      short loc_180001701
0x1800016a4  mov     r10, [rsp+48h+MatchAllKeyword]
0x1800016a9  mov     eax, edx
0x1800016ab  test    edx, edx
0x1800016ad  jz      short loc_1800016D2
0x1800016af  cmp     eax, 1
0x1800016b2  jnz     short loc_1800016D8
0x1800016b4  test    r8b, r8b
0x1800016b7  jz      short loc_1800016C1
0x1800016b9  movzx   eax, r8b
0x1800016bd  inc     eax
0x1800016bf  jmp     short loc_1800016C6
0x1800016c1  mov     eax, 100h
0x1800016c6  mov     [rcx], eax
0x1800016c8  mov     [rcx+10h], r9
0x1800016cc  mov     [rcx+18h], r10
0x1800016d0  jmp     short loc_1800016D8
0x1800016d2  mov     dword ptr [rcx], 0
0x1800016d8  mov     rax, [rcx+28h]
0x1800016dc  test    rax, rax
0x1800016df  jz      short loc_180001701
0x1800016e1  mov     rcx, [rcx+30h]
0x1800016e5  mov     [rsp+48h+var_18], rcx
0x1800016ea  mov     rcx, [rsp+48h+FilterData]
0x1800016ef  mov     [rsp+48h+var_20], rcx
0x1800016f4  mov     rcx, r11
0x1800016f7  mov     [rsp+48h+var_28], r10
0x1800016fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001701  add     rsp, 48h
0x180001705  retn
```
