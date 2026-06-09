# _tlgEnableCallback

- ea: `0x180001ec0`
- end: `0x180001f36`
- name: `_tlgEnableCallback`
- size: `118`
- prototype: `void __stdcall(LPCGUID SourceId, ULONG IsEnabled, UCHAR Level, ULONGLONG MatchAnyKeyword, ULONGLONG MatchAllKeyword, PEVENT_FILTER_DESCRIPTOR FilterData, PVOID CallbackContext)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180001ec0`
- `0x180013010`

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
0x180001ec0  sub     rsp, 48h
0x180001ec4  mov     r11, rcx
0x180001ec7  mov     rcx, [rsp+48h+CallbackContext]
0x180001ecf  test    rcx, rcx
0x180001ed2  jz      short loc_180001F31
0x180001ed4  mov     r10, [rsp+48h+MatchAllKeyword]
0x180001ed9  mov     eax, edx
0x180001edb  test    edx, edx
0x180001edd  jz      short loc_180001F02
0x180001edf  cmp     eax, 1
0x180001ee2  jnz     short loc_180001F08
0x180001ee4  test    r8b, r8b
0x180001ee7  jz      short loc_180001EF1
0x180001ee9  movzx   eax, r8b
0x180001eed  inc     eax
0x180001eef  jmp     short loc_180001EF6
0x180001ef1  mov     eax, 100h
0x180001ef6  mov     [rcx], eax
0x180001ef8  mov     [rcx+10h], r9
0x180001efc  mov     [rcx+18h], r10
0x180001f00  jmp     short loc_180001F08
0x180001f02  mov     dword ptr [rcx], 0
0x180001f08  mov     rax, [rcx+28h]
0x180001f0c  test    rax, rax
0x180001f0f  jz      short loc_180001F31
0x180001f11  mov     rcx, [rcx+30h]
0x180001f15  mov     [rsp+48h+var_18], rcx
0x180001f1a  mov     rcx, [rsp+48h+FilterData]
0x180001f1f  mov     [rsp+48h+var_20], rcx
0x180001f24  mov     rcx, r11
0x180001f27  mov     [rsp+48h+var_28], r10
0x180001f2c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001f31  add     rsp, 48h
0x180001f35  retn
```
