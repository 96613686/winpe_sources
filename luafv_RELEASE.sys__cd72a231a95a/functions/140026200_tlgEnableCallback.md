# _tlgEnableCallback

- ea: `0x140026200`
- end: `0x140026277`
- name: `_tlgEnableCallback`
- size: `119`
- prototype: `void __fastcall(LPCGUID SourceId, __int64 ControlCode, __int64 Level, ULONGLONG MatchAnyKeyword, ULONGLONG MatchAllKeyword, PEVENT_FILTER_DESCRIPTOR FilterData, _QWORD *CallbackContext)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x140005c90`
- `0x140026200`

## pseudocode

```c
void __fastcall tlgEnableCallback(
        LPCGUID SourceId,
        __int64 ControlCode,
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
    if ( (_DWORD)ControlCode )
    {
      if ( (_DWORD)ControlCode == 1 )
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
      v8(SourceId, ControlCode, Level, MatchAnyKeyword, MatchAllKeyword, FilterData, CallbackContext[6]);
  }
}

```

## disassembly

```asm
0x140026200  sub     rsp, 48h
0x140026204  mov     r11, rcx
0x140026207  mov     rcx, [rsp+48h+CallbackContext]
0x14002620f  test    rcx, rcx
0x140026212  jz      short loc_140026271
0x140026214  mov     r10, [rsp+48h+MatchAllKeyword]
0x140026219  mov     eax, edx
0x14002621b  test    edx, edx
0x14002621d  jz      short loc_140026242
0x14002621f  cmp     eax, 1
0x140026222  jnz     short loc_140026248
0x140026224  test    r8b, r8b
0x140026227  jz      short loc_140026231
0x140026229  movzx   eax, r8b
0x14002622d  inc     eax
0x14002622f  jmp     short loc_140026236
0x140026231  mov     eax, 100h
0x140026236  mov     [rcx], eax
0x140026238  mov     [rcx+10h], r9
0x14002623c  mov     [rcx+18h], r10
0x140026240  jmp     short loc_140026248
0x140026242  mov     dword ptr [rcx], 0
0x140026248  mov     rax, [rcx+28h]
0x14002624c  test    rax, rax
0x14002624f  jz      short loc_140026271
0x140026251  mov     rcx, [rcx+30h]
0x140026255  mov     [rsp+48h+var_18], rcx
0x14002625a  mov     rcx, [rsp+48h+FilterData]
0x14002625f  mov     [rsp+48h+var_20], rcx
0x140026264  mov     rcx, r11
0x140026267  mov     [rsp+48h+var_28], r10
0x14002626c  call    _guard_dispatch_icall
0x140026271  add     rsp, 48h
0x140026275  retn
```
