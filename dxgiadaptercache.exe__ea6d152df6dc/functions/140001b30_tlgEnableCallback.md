# _tlgEnableCallback

- ea: `0x140001b30`
- end: `0x140001ba6`
- name: `_tlgEnableCallback`
- size: `118`
- prototype: `void __fastcall(LPCGUID SourceId, __int64 IsEnabled, __int64 Level, ULONGLONG MatchAnyKeyword, ULONGLONG MatchAllKeyword, PEVENT_FILTER_DESCRIPTOR FilterData, _QWORD *CallbackContext)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x140001b30`
- `0x140012010`

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
0x140001b30  sub     rsp, 48h
0x140001b34  mov     r11, rcx
0x140001b37  mov     rcx, [rsp+48h+CallbackContext]
0x140001b3f  test    rcx, rcx
0x140001b42  jz      short loc_140001BA1
0x140001b44  mov     r10, [rsp+48h+MatchAllKeyword]
0x140001b49  mov     eax, edx
0x140001b4b  test    edx, edx
0x140001b4d  jz      short loc_140001B72
0x140001b4f  cmp     eax, 1
0x140001b52  jnz     short loc_140001B78
0x140001b54  test    r8b, r8b
0x140001b57  jz      short loc_140001B61
0x140001b59  movzx   eax, r8b
0x140001b5d  inc     eax
0x140001b5f  jmp     short loc_140001B66
0x140001b61  mov     eax, 100h
0x140001b66  mov     [rcx], eax
0x140001b68  mov     [rcx+10h], r9
0x140001b6c  mov     [rcx+18h], r10
0x140001b70  jmp     short loc_140001B78
0x140001b72  mov     dword ptr [rcx], 0
0x140001b78  mov     rax, [rcx+28h]
0x140001b7c  test    rax, rax
0x140001b7f  jz      short loc_140001BA1
0x140001b81  mov     rcx, [rcx+30h]
0x140001b85  mov     [rsp+48h+var_18], rcx
0x140001b8a  mov     rcx, [rsp+48h+FilterData]
0x140001b8f  mov     [rsp+48h+var_20], rcx
0x140001b94  mov     rcx, r11
0x140001b97  mov     [rsp+48h+var_28], r10
0x140001b9c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140001ba1  add     rsp, 48h
0x140001ba5  retn
```
