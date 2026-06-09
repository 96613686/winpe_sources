# _tlgEnableCallback

- ea: `0x14000dd00`
- end: `0x14000dd80`
- name: `_tlgEnableCallback`
- size: `128`
- prototype: `void __fastcall(LPCGUID SourceId, __int64 IsEnabled, __int64 Level, ULONGLONG MatchAnyKeyword, ULONGLONG MatchAllKeyword, PEVENT_FILTER_DESCRIPTOR FilterData, _QWORD *CallbackContext)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x14000dd00`
- `0x14001f010`

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
0x14000dd00  sub     rsp, 48h
0x14000dd04  mov     r11, rcx
0x14000dd07  mov     rcx, [rsp+48h+CallbackContext]
0x14000dd0f  test    rcx, rcx
0x14000dd12  jz      short loc_14000DD7B
0x14000dd14  mov     r10, [rsp+48h+MatchAllKeyword]
0x14000dd19  mov     eax, edx
0x14000dd1b  test    edx, edx
0x14000dd1d  jz      short loc_14000DD4C
0x14000dd1f  cmp     eax, 1
0x14000dd22  jnz     short loc_14000DD52
0x14000dd24  test    r8b, r8b
0x14000dd27  jz      short loc_14000DD3B
0x14000dd29  movzx   eax, r8b
0x14000dd2d  inc     eax
0x14000dd2f  mov     [rcx], eax
0x14000dd31  mov     [rcx+10h], r9
0x14000dd35  mov     [rcx+18h], r10
0x14000dd39  jmp     short loc_14000DD52
0x14000dd3b  mov     eax, 100h
0x14000dd40  mov     [rcx], eax
0x14000dd42  mov     [rcx+10h], r9
0x14000dd46  mov     [rcx+18h], r10
0x14000dd4a  jmp     short loc_14000DD52
0x14000dd4c  mov     dword ptr [rcx], 0
0x14000dd52  mov     rax, [rcx+28h]
0x14000dd56  test    rax, rax
0x14000dd59  jz      short loc_14000DD7B
0x14000dd5b  mov     rcx, [rcx+30h]
0x14000dd5f  mov     [rsp+48h+var_18], rcx
0x14000dd64  mov     rcx, [rsp+48h+FilterData]
0x14000dd69  mov     [rsp+48h+var_20], rcx
0x14000dd6e  mov     rcx, r11
0x14000dd71  mov     [rsp+48h+var_28], r10
0x14000dd76  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000dd7b  add     rsp, 48h
0x14000dd7f  retn
```
