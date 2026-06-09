# _tlgEnableCallback

- ea: `0x180009b60`
- end: `0x180009bd6`
- name: `_tlgEnableCallback`
- size: `118`
- prototype: `void __stdcall(LPCGUID SourceId, ULONG IsEnabled, UCHAR Level, ULONGLONG MatchAnyKeyword, ULONGLONG MatchAllKeyword, PEVENT_FILTER_DESCRIPTOR FilterData, PVOID CallbackContext)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180009b60`
- `0x180015010`

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
0x180009b60  sub     rsp, 48h
0x180009b64  mov     r11, rcx
0x180009b67  mov     rcx, [rsp+48h+CallbackContext]
0x180009b6f  test    rcx, rcx
0x180009b72  jz      short loc_180009BD1
0x180009b74  mov     r10, [rsp+48h+MatchAllKeyword]
0x180009b79  mov     eax, edx
0x180009b7b  test    edx, edx
0x180009b7d  jz      short loc_180009BA2
0x180009b7f  cmp     eax, 1
0x180009b82  jnz     short loc_180009BA8
0x180009b84  test    r8b, r8b
0x180009b87  jz      short loc_180009B91
0x180009b89  movzx   eax, r8b
0x180009b8d  inc     eax
0x180009b8f  jmp     short loc_180009B96
0x180009b91  mov     eax, 100h
0x180009b96  mov     [rcx], eax
0x180009b98  mov     [rcx+10h], r9
0x180009b9c  mov     [rcx+18h], r10
0x180009ba0  jmp     short loc_180009BA8
0x180009ba2  mov     dword ptr [rcx], 0
0x180009ba8  mov     rax, [rcx+28h]
0x180009bac  test    rax, rax
0x180009baf  jz      short loc_180009BD1
0x180009bb1  mov     rcx, [rcx+30h]
0x180009bb5  mov     [rsp+48h+var_18], rcx
0x180009bba  mov     rcx, [rsp+48h+FilterData]
0x180009bbf  mov     [rsp+48h+var_20], rcx
0x180009bc4  mov     rcx, r11
0x180009bc7  mov     [rsp+48h+var_28], r10
0x180009bcc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009bd1  add     rsp, 48h
0x180009bd5  retn
```
