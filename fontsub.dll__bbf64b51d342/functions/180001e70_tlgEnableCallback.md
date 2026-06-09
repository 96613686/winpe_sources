# _tlgEnableCallback

- ea: `0x180001e70`
- end: `0x180001ee6`
- name: `_tlgEnableCallback`
- size: `118`
- prototype: `void __stdcall(LPCGUID SourceId, ULONG IsEnabled, UCHAR Level, ULONGLONG MatchAnyKeyword, ULONGLONG MatchAllKeyword, PEVENT_FILTER_DESCRIPTOR FilterData, PVOID CallbackContext)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180001e70`
- `0x18001c010`

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
0x180001e70  sub     rsp, 48h
0x180001e74  mov     r11, rcx
0x180001e77  mov     rcx, [rsp+48h+CallbackContext]
0x180001e7f  test    rcx, rcx
0x180001e82  jz      short loc_180001EE1
0x180001e84  mov     r10, [rsp+48h+MatchAllKeyword]
0x180001e89  mov     eax, edx
0x180001e8b  test    edx, edx
0x180001e8d  jz      short loc_180001EB2
0x180001e8f  cmp     eax, 1
0x180001e92  jnz     short loc_180001EB8
0x180001e94  test    r8b, r8b
0x180001e97  jz      short loc_180001EA1
0x180001e99  movzx   eax, r8b
0x180001e9d  inc     eax
0x180001e9f  jmp     short loc_180001EA6
0x180001ea1  mov     eax, 100h
0x180001ea6  mov     [rcx], eax
0x180001ea8  mov     [rcx+10h], r9
0x180001eac  mov     [rcx+18h], r10
0x180001eb0  jmp     short loc_180001EB8
0x180001eb2  mov     dword ptr [rcx], 0
0x180001eb8  mov     rax, [rcx+28h]
0x180001ebc  test    rax, rax
0x180001ebf  jz      short loc_180001EE1
0x180001ec1  mov     rcx, [rcx+30h]
0x180001ec5  mov     [rsp+48h+var_18], rcx
0x180001eca  mov     rcx, [rsp+48h+FilterData]
0x180001ecf  mov     [rsp+48h+var_20], rcx
0x180001ed4  mov     rcx, r11
0x180001ed7  mov     [rsp+48h+var_28], r10
0x180001edc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001ee1  add     rsp, 48h
0x180001ee5  retn
```
