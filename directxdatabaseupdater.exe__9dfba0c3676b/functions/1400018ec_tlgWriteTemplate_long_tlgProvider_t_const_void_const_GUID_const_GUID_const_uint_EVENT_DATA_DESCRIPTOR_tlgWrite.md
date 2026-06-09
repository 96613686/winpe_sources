# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)

- ea: `0x1400018ec`
- end: `0x140001974`
- name: `??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z`
- size: `136`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, __int64, __int64, __int64)`
- caller_count: `7`
- callee_count: `2`
- tags: ``

## callers

- `0x14000b5fc`
- `0x14000be40`
- `0x14000c070`
- `0x14000c2a0`
- `0x14000c4d0`
- `0x14000c700`
- `0x14000c930`

## callees

- `0x140002318`
- `0x140002f40`

## pseudocode

```c
__int64 __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        __int64 a7)
{
  _QWORD v8[10]; // [rsp+30h] [rbp-68h] BYREF

  v8[8] = a7;
  v8[6] = a6;
  v8[4] = a5;
  v8[9] = 4;
  v8[7] = 4;
  v8[5] = 8;
  return tlgWriteTransfer_EventWriteTransfer(a1, a2, a3, 0, 5, v8);
}

```

## disassembly

```asm
0x1400018ec  mov     r11, rsp
0x1400018ef  sub     rsp, 98h
0x1400018f6  mov     rax, cs:__security_cookie
0x1400018fd  xor     rax, rsp
0x140001900  mov     [rsp+98h+var_18], rax
0x140001908  mov     rax, [rsp+98h+arg_30]
0x140001910  xor     r9d, r9d
0x140001913  mov     [r11-28h], rax
0x140001917  mov     rax, [rsp+98h+arg_28]
0x14000191f  mov     [r11-38h], rax
0x140001923  mov     rax, [rsp+98h+arg_20]
0x14000192b  mov     [r11-48h], rax
0x14000192f  lea     rax, [r11-68h]
0x140001933  mov     [r11-70h], rax
0x140001937  mov     [rsp+98h+var_78], 5
0x14000193f  mov     qword ptr [r11-20h], 4
0x140001947  mov     qword ptr [r11-30h], 4
0x14000194f  mov     qword ptr [r11-40h], 8
0x140001957  call    _tlgWriteTransfer_EventWriteTransfer
0x14000195c  mov     rcx, [rsp+98h+var_18]
0x140001964  xor     rcx, rsp; StackCookie
0x140001967  call    __security_check_cookie
0x14000196c  add     rsp, 98h
0x140001973  retn
```
