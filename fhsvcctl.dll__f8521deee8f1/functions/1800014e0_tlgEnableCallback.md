# _tlgEnableCallback

- ea: `0x1800014e0`
- end: `0x180001556`
- name: `_tlgEnableCallback`
- size: `118`
- prototype: `void __fastcall(LPCGUID SourceId, __int64 IsEnabled, __int64 Level, ULONGLONG MatchAnyKeyword, ULONGLONG MatchAllKeyword, PEVENT_FILTER_DESCRIPTOR FilterData, _QWORD *CallbackContext)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x1800014e0`
- `0x180006010`

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
0x1800014e0  sub     rsp, 48h
0x1800014e4  mov     r11, rcx
0x1800014e7  mov     rcx, [rsp+48h+CallbackContext]
0x1800014ef  test    rcx, rcx
0x1800014f2  jz      short loc_180001551
0x1800014f4  mov     r10, [rsp+48h+MatchAllKeyword]
0x1800014f9  mov     eax, edx
0x1800014fb  test    edx, edx
0x1800014fd  jz      short loc_180001522
0x1800014ff  cmp     eax, 1
0x180001502  jnz     short loc_180001528
0x180001504  test    r8b, r8b
0x180001507  jz      short loc_180001511
0x180001509  movzx   eax, r8b
0x18000150d  inc     eax
0x18000150f  jmp     short loc_180001516
0x180001511  mov     eax, 100h
0x180001516  mov     [rcx], eax
0x180001518  mov     [rcx+10h], r9
0x18000151c  mov     [rcx+18h], r10
0x180001520  jmp     short loc_180001528
0x180001522  mov     dword ptr [rcx], 0
0x180001528  mov     rax, [rcx+28h]
0x18000152c  test    rax, rax
0x18000152f  jz      short loc_180001551
0x180001531  mov     rcx, [rcx+30h]
0x180001535  mov     [rsp+48h+var_18], rcx
0x18000153a  mov     rcx, [rsp+48h+FilterData]
0x18000153f  mov     [rsp+48h+var_20], rcx
0x180001544  mov     rcx, r11
0x180001547  mov     [rsp+48h+var_28], r10
0x18000154c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001551  add     rsp, 48h
0x180001555  retn
```
