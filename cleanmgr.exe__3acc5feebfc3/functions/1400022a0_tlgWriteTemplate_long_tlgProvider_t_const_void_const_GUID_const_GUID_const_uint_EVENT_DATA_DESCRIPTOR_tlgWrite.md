# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)

- ea: `0x1400022a0`
- end: `0x140002328`
- name: `??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z`
- size: `136`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, __int64, __int64, __int64)`
- caller_count: `7`
- callee_count: `2`
- tags: ``

## callers

- `0x140010e00`
- `0x140011030`
- `0x140011260`
- `0x140011490`
- `0x1400116c0`
- `0x1400118f0`
- `0x140011b20`

## callees

- `0x1400019e8`
- `0x1400029a0`

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
0x1400022a0  mov     r11, rsp
0x1400022a3  sub     rsp, 98h
0x1400022aa  mov     rax, cs:__security_cookie
0x1400022b1  xor     rax, rsp
0x1400022b4  mov     [rsp+98h+var_18], rax
0x1400022bc  mov     rax, [rsp+98h+arg_30]
0x1400022c4  xor     r9d, r9d
0x1400022c7  mov     [r11-28h], rax
0x1400022cb  mov     rax, [rsp+98h+arg_28]
0x1400022d3  mov     [r11-38h], rax
0x1400022d7  mov     rax, [rsp+98h+arg_20]
0x1400022df  mov     [r11-48h], rax
0x1400022e3  lea     rax, [r11-68h]
0x1400022e7  mov     [r11-70h], rax
0x1400022eb  mov     [rsp+98h+var_78], 5
0x1400022f3  mov     qword ptr [r11-20h], 4
0x1400022fb  mov     qword ptr [r11-30h], 4
0x140002303  mov     qword ptr [r11-40h], 8
0x14000230b  call    _tlgWriteTransfer_EventWriteTransfer
0x140002310  mov     rcx, [rsp+98h+var_18]
0x140002318  xor     rcx, rsp; StackCookie
0x14000231b  call    __security_check_cookie
0x140002320  add     rsp, 98h
0x140002327  retn
```
