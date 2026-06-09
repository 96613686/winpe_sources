# _tlgEnableCallback

- ea: `0x180010b90`
- end: `0x180010c10`
- name: `_tlgEnableCallback`
- size: `128`
- prototype: `void __fastcall(LPCGUID SourceId, __int64 IsEnabled, __int64 Level, ULONGLONG MatchAnyKeyword, ULONGLONG MatchAllKeyword, PEVENT_FILTER_DESCRIPTOR FilterData, _QWORD *CallbackContext)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180010b90`
- `0x180026010`

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
0x180010b90  sub     rsp, 48h
0x180010b94  mov     r11, rcx
0x180010b97  mov     rcx, [rsp+48h+CallbackContext]
0x180010b9f  test    rcx, rcx
0x180010ba2  jz      short loc_180010C0B
0x180010ba4  mov     r10, [rsp+48h+MatchAllKeyword]
0x180010ba9  mov     eax, edx
0x180010bab  test    edx, edx
0x180010bad  jz      short loc_180010BDC
0x180010baf  cmp     eax, 1
0x180010bb2  jnz     short loc_180010BE2
0x180010bb4  test    r8b, r8b
0x180010bb7  jz      short loc_180010BCB
0x180010bb9  movzx   eax, r8b
0x180010bbd  inc     eax
0x180010bbf  mov     [rcx], eax
0x180010bc1  mov     [rcx+10h], r9
0x180010bc5  mov     [rcx+18h], r10
0x180010bc9  jmp     short loc_180010BE2
0x180010bcb  mov     eax, 100h
0x180010bd0  mov     [rcx], eax
0x180010bd2  mov     [rcx+10h], r9
0x180010bd6  mov     [rcx+18h], r10
0x180010bda  jmp     short loc_180010BE2
0x180010bdc  mov     dword ptr [rcx], 0
0x180010be2  mov     rax, [rcx+28h]
0x180010be6  test    rax, rax
0x180010be9  jz      short loc_180010C0B
0x180010beb  mov     rcx, [rcx+30h]
0x180010bef  mov     [rsp+48h+var_18], rcx
0x180010bf4  mov     rcx, [rsp+48h+FilterData]
0x180010bf9  mov     [rsp+48h+var_20], rcx
0x180010bfe  mov     rcx, r11
0x180010c01  mov     [rsp+48h+var_28], r10
0x180010c06  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010c0b  add     rsp, 48h
0x180010c0f  retn
```
