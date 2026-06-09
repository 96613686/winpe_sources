# _tlgEnableCallback

- ea: `0x140001340`
- end: `0x1400013b6`
- name: `_tlgEnableCallback`
- size: `118`
- prototype: `void __fastcall(LPCGUID SourceId, __int64 IsEnabled, __int64 Level, ULONGLONG MatchAnyKeyword, ULONGLONG MatchAllKeyword, PEVENT_FILTER_DESCRIPTOR FilterData, _QWORD *CallbackContext)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x140001340`
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
0x140001340  sub     rsp, 48h
0x140001344  mov     r11, rcx
0x140001347  mov     rcx, [rsp+48h+CallbackContext]
0x14000134f  test    rcx, rcx
0x140001352  jz      short loc_1400013B1
0x140001354  mov     r10, [rsp+48h+MatchAllKeyword]
0x140001359  mov     eax, edx
0x14000135b  test    edx, edx
0x14000135d  jz      short loc_140001382
0x14000135f  cmp     eax, 1
0x140001362  jnz     short loc_140001388
0x140001364  test    r8b, r8b
0x140001367  jz      short loc_140001371
0x140001369  movzx   eax, r8b
0x14000136d  inc     eax
0x14000136f  jmp     short loc_140001376
0x140001371  mov     eax, 100h
0x140001376  mov     [rcx], eax
0x140001378  mov     [rcx+10h], r9
0x14000137c  mov     [rcx+18h], r10
0x140001380  jmp     short loc_140001388
0x140001382  mov     dword ptr [rcx], 0
0x140001388  mov     rax, [rcx+28h]
0x14000138c  test    rax, rax
0x14000138f  jz      short loc_1400013B1
0x140001391  mov     rcx, [rcx+30h]
0x140001395  mov     [rsp+48h+var_18], rcx
0x14000139a  mov     rcx, [rsp+48h+FilterData]
0x14000139f  mov     [rsp+48h+var_20], rcx
0x1400013a4  mov     rcx, r11
0x1400013a7  mov     [rsp+48h+var_28], r10
0x1400013ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400013b1  add     rsp, 48h
0x1400013b5  retn
```
