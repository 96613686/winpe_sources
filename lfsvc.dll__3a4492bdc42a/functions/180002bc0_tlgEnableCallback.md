# _tlgEnableCallback

- ea: `0x180002bc0`
- end: `0x180002c40`
- name: `_tlgEnableCallback`
- size: `128`
- prototype: `void __fastcall(LPCGUID SourceId, __int64 IsEnabled, __int64 Level, ULONGLONG MatchAnyKeyword, ULONGLONG MatchAllKeyword, PEVENT_FILTER_DESCRIPTOR FilterData, _QWORD *CallbackContext)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180002bc0`
- `0x18000c010`

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
0x180002bc0  sub     rsp, 48h
0x180002bc4  mov     r11, rcx
0x180002bc7  mov     rcx, [rsp+48h+CallbackContext]
0x180002bcf  test    rcx, rcx
0x180002bd2  jz      short loc_180002C3B
0x180002bd4  mov     r10, [rsp+48h+MatchAllKeyword]
0x180002bd9  mov     eax, edx
0x180002bdb  test    edx, edx
0x180002bdd  jz      short loc_180002C0C
0x180002bdf  cmp     eax, 1
0x180002be2  jnz     short loc_180002C12
0x180002be4  test    r8b, r8b
0x180002be7  jz      short loc_180002BFB
0x180002be9  movzx   eax, r8b
0x180002bed  inc     eax
0x180002bef  mov     [rcx], eax
0x180002bf1  mov     [rcx+10h], r9
0x180002bf5  mov     [rcx+18h], r10
0x180002bf9  jmp     short loc_180002C12
0x180002bfb  mov     eax, 100h
0x180002c00  mov     [rcx], eax
0x180002c02  mov     [rcx+10h], r9
0x180002c06  mov     [rcx+18h], r10
0x180002c0a  jmp     short loc_180002C12
0x180002c0c  mov     dword ptr [rcx], 0
0x180002c12  mov     rax, [rcx+28h]
0x180002c16  test    rax, rax
0x180002c19  jz      short loc_180002C3B
0x180002c1b  mov     rcx, [rcx+30h]
0x180002c1f  mov     [rsp+48h+var_18], rcx
0x180002c24  mov     rcx, [rsp+48h+FilterData]
0x180002c29  mov     [rsp+48h+var_20], rcx
0x180002c2e  mov     rcx, r11
0x180002c31  mov     [rsp+48h+var_28], r10
0x180002c36  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002c3b  add     rsp, 48h
0x180002c3f  retn
```
