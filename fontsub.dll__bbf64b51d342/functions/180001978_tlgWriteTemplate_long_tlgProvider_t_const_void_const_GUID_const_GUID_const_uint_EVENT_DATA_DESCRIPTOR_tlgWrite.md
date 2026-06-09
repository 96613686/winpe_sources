# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)

- ea: `0x180001978`
- end: `0x180001a00`
- name: `??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z`
- size: `136`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x1800065e0`
- `0x180006820`

## callees

- `0x180001f18`
- `0x18001ac90`

## pseudocode

```c
ULONG __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        __int64 a1,
        unsigned __int8 *a2,
        const GUID *a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        __int64 a7)
{
  struct _EVENT_DATA_DESCRIPTOR v8; // [rsp+30h] [rbp-68h] BYREF
  __int64 v9; // [rsp+50h] [rbp-48h]
  __int64 v10; // [rsp+58h] [rbp-40h]
  __int64 v11; // [rsp+60h] [rbp-38h]
  __int64 v12; // [rsp+68h] [rbp-30h]
  __int64 v13; // [rsp+70h] [rbp-28h]
  __int64 v14; // [rsp+78h] [rbp-20h]

  v13 = a7;
  v11 = a6;
  v9 = a5;
  v14 = 4;
  v12 = 4;
  v10 = 8;
  return tlgWriteTransfer_EventWriteTransfer(a1, a2, a3, 0, 5u, &v8);
}

```

## disassembly

```asm
0x180001978  mov     r11, rsp
0x18000197b  sub     rsp, 98h
0x180001982  mov     rax, cs:__security_cookie
0x180001989  xor     rax, rsp
0x18000198c  mov     [rsp+98h+var_18], rax
0x180001994  mov     rax, [rsp+98h+arg_30]
0x18000199c  xor     r9d, r9d
0x18000199f  mov     [r11-28h], rax
0x1800019a3  mov     rax, [rsp+98h+arg_28]
0x1800019ab  mov     [r11-38h], rax
0x1800019af  mov     rax, [rsp+98h+arg_20]
0x1800019b7  mov     [r11-48h], rax
0x1800019bb  lea     rax, [r11-68h]
0x1800019bf  mov     [r11-70h], rax
0x1800019c3  mov     [rsp+98h+var_78], 5
0x1800019cb  mov     qword ptr [r11-20h], 4
0x1800019d3  mov     qword ptr [r11-30h], 4
0x1800019db  mov     qword ptr [r11-40h], 8
0x1800019e3  call    _tlgWriteTransfer_EventWriteTransfer
0x1800019e8  mov     rcx, [rsp+98h+var_18]
0x1800019f0  xor     rcx, rsp; StackCookie
0x1800019f3  call    __security_check_cookie
0x1800019f8  add     rsp, 98h
0x1800019ff  retn
```
