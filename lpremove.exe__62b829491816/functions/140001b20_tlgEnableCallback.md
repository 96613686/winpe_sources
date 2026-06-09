# _tlgEnableCallback

- ea: `0x140001b20`
- end: `0x140001b96`
- name: `_tlgEnableCallback`
- size: `118`
- prototype: `void __fastcall(LPCGUID SourceId, __int64 IsEnabled, __int64 Level, ULONGLONG MatchAnyKeyword, ULONGLONG MatchAllKeyword, PEVENT_FILTER_DESCRIPTOR FilterData, _QWORD *CallbackContext)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x140001b20`
- `0x140011010`

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
0x140001b20  sub     rsp, 48h
0x140001b24  mov     r11, rcx
0x140001b27  mov     rcx, [rsp+48h+CallbackContext]
0x140001b2f  test    rcx, rcx
0x140001b32  jz      short loc_140001B91
0x140001b34  mov     r10, [rsp+48h+MatchAllKeyword]
0x140001b39  mov     eax, edx
0x140001b3b  test    edx, edx
0x140001b3d  jz      short loc_140001B62
0x140001b3f  cmp     eax, 1
0x140001b42  jnz     short loc_140001B68
0x140001b44  test    r8b, r8b
0x140001b47  jz      short loc_140001B51
0x140001b49  movzx   eax, r8b
0x140001b4d  inc     eax
0x140001b4f  jmp     short loc_140001B56
0x140001b51  mov     eax, 100h
0x140001b56  mov     [rcx], eax
0x140001b58  mov     [rcx+10h], r9
0x140001b5c  mov     [rcx+18h], r10
0x140001b60  jmp     short loc_140001B68
0x140001b62  mov     dword ptr [rcx], 0
0x140001b68  mov     rax, [rcx+28h]
0x140001b6c  test    rax, rax
0x140001b6f  jz      short loc_140001B91
0x140001b71  mov     rcx, [rcx+30h]
0x140001b75  mov     [rsp+48h+var_18], rcx
0x140001b7a  mov     rcx, [rsp+48h+FilterData]
0x140001b7f  mov     [rsp+48h+var_20], rcx
0x140001b84  mov     rcx, r11
0x140001b87  mov     [rsp+48h+var_28], r10
0x140001b8c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140001b91  add     rsp, 48h
0x140001b95  retn
```
