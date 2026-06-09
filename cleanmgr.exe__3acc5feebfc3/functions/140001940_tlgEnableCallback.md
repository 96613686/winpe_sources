# _tlgEnableCallback

- ea: `0x140001940`
- end: `0x1400019b6`
- name: `_tlgEnableCallback`
- size: `118`
- prototype: `void __fastcall(LPCGUID SourceId, __int64 IsEnabled, __int64 Level, ULONGLONG MatchAnyKeyword, ULONGLONG MatchAllKeyword, PEVENT_FILTER_DESCRIPTOR FilterData, _QWORD *CallbackContext)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x140001940`
- `0x140018010`

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
0x140001940  sub     rsp, 48h
0x140001944  mov     r11, rcx
0x140001947  mov     rcx, [rsp+48h+CallbackContext]
0x14000194f  test    rcx, rcx
0x140001952  jz      short loc_1400019B1
0x140001954  mov     r10, [rsp+48h+MatchAllKeyword]
0x140001959  mov     eax, edx
0x14000195b  test    edx, edx
0x14000195d  jz      short loc_140001982
0x14000195f  cmp     eax, 1
0x140001962  jnz     short loc_140001988
0x140001964  test    r8b, r8b
0x140001967  jz      short loc_140001971
0x140001969  movzx   eax, r8b
0x14000196d  inc     eax
0x14000196f  jmp     short loc_140001976
0x140001971  mov     eax, 100h
0x140001976  mov     [rcx], eax
0x140001978  mov     [rcx+10h], r9
0x14000197c  mov     [rcx+18h], r10
0x140001980  jmp     short loc_140001988
0x140001982  mov     dword ptr [rcx], 0
0x140001988  mov     rax, [rcx+28h]
0x14000198c  test    rax, rax
0x14000198f  jz      short loc_1400019B1
0x140001991  mov     rcx, [rcx+30h]
0x140001995  mov     [rsp+48h+var_18], rcx
0x14000199a  mov     rcx, [rsp+48h+FilterData]
0x14000199f  mov     [rsp+48h+var_20], rcx
0x1400019a4  mov     rcx, r11
0x1400019a7  mov     [rsp+48h+var_28], r10
0x1400019ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400019b1  add     rsp, 48h
0x1400019b5  retn
```
