# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &)

- ea: `0x14000187c`
- end: `0x1400018e5`
- name: `??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@@Z`
- size: `105`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, __int64, __int64)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x14000adcc`
- `0x14000ae8c`
- `0x14000af4c`
- `0x14000b00c`

## callees

- `0x140002318`
- `0x140002f40`

## pseudocode

```c
__int64 __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6)
{
  _QWORD v7[8]; // [rsp+30h] [rbp-58h] BYREF

  v7[6] = a6;
  v7[4] = a5;
  v7[7] = 4;
  v7[5] = 8;
  return tlgWriteTransfer_EventWriteTransfer(a1, a2, a3, a4, 4, v7);
}

```

## disassembly

```asm
0x14000187c  mov     r11, rsp
0x14000187f  sub     rsp, 88h
0x140001886  mov     rax, cs:__security_cookie
0x14000188d  xor     rax, rsp
0x140001890  mov     [rsp+88h+var_18], rax
0x140001895  mov     rax, [rsp+88h+arg_28]
0x14000189d  mov     r10d, 4
0x1400018a3  mov     [r11-28h], rax
0x1400018a7  mov     rax, [rsp+88h+arg_20]
0x1400018af  mov     [r11-38h], rax
0x1400018b3  lea     rax, [r11-58h]
0x1400018b7  mov     [r11-60h], rax
0x1400018bb  mov     [r11-68h], r10d
0x1400018bf  mov     [r11-20h], r10
0x1400018c3  mov     qword ptr [r11-30h], 8
0x1400018cb  call    _tlgWriteTransfer_EventWriteTransfer
0x1400018d0  mov     rcx, [rsp+88h+var_18]
0x1400018d5  xor     rcx, rsp; StackCookie
0x1400018d8  call    __security_check_cookie
0x1400018dd  add     rsp, 88h
0x1400018e4  retn
```
