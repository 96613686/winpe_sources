# _tlgEnableCallback

- ea: `0x1800011f0`
- end: `0x180001270`
- name: `_tlgEnableCallback`
- size: `128`
- prototype: `void __stdcall(LPCGUID SourceId, ULONG IsEnabled, UCHAR Level, ULONGLONG MatchAnyKeyword, ULONGLONG MatchAllKeyword, PEVENT_FILTER_DESCRIPTOR FilterData, PVOID CallbackContext)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x1800011f0`
- `0x180012010`

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
0x1800011f0  sub     rsp, 48h
0x1800011f4  mov     r11, rcx
0x1800011f7  mov     rcx, [rsp+48h+CallbackContext]
0x1800011ff  test    rcx, rcx
0x180001202  jz      short loc_18000126B
0x180001204  mov     r10, [rsp+48h+MatchAllKeyword]
0x180001209  mov     eax, edx
0x18000120b  test    edx, edx
0x18000120d  jz      short loc_18000123C
0x18000120f  cmp     eax, 1
0x180001212  jnz     short loc_180001242
0x180001214  test    r8b, r8b
0x180001217  jz      short loc_18000122B
0x180001219  movzx   eax, r8b
0x18000121d  inc     eax
0x18000121f  mov     [rcx], eax
0x180001221  mov     [rcx+10h], r9
0x180001225  mov     [rcx+18h], r10
0x180001229  jmp     short loc_180001242
0x18000122b  mov     eax, 100h
0x180001230  mov     [rcx], eax
0x180001232  mov     [rcx+10h], r9
0x180001236  mov     [rcx+18h], r10
0x18000123a  jmp     short loc_180001242
0x18000123c  mov     dword ptr [rcx], 0
0x180001242  mov     rax, [rcx+28h]
0x180001246  test    rax, rax
0x180001249  jz      short loc_18000126B
0x18000124b  mov     rcx, [rcx+30h]
0x18000124f  mov     [rsp+48h+var_18], rcx
0x180001254  mov     rcx, [rsp+48h+FilterData]
0x180001259  mov     [rsp+48h+var_20], rcx
0x18000125e  mov     rcx, r11
0x180001261  mov     [rsp+48h+var_28], r10
0x180001266  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000126b  add     rsp, 48h
0x18000126f  retn
```
