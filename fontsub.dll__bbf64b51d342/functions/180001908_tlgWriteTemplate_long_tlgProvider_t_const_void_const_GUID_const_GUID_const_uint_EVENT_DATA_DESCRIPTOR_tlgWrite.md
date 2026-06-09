# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &)

- ea: `0x180001908`
- end: `0x180001971`
- name: `??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@@Z`
- size: `105`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180005f70`
- `0x18000600c`

## callees

- `0x180001f18`
- `0x18001ac90`

## pseudocode

```c
ULONG __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(
        __int64 a1,
        unsigned __int8 *a2,
        const GUID *a3,
        const GUID *a4,
        __int64 a5,
        __int64 a6)
{
  struct _EVENT_DATA_DESCRIPTOR v7; // [rsp+30h] [rbp-58h] BYREF
  __int64 v8; // [rsp+50h] [rbp-38h]
  __int64 v9; // [rsp+58h] [rbp-30h]
  __int64 v10; // [rsp+60h] [rbp-28h]
  __int64 v11; // [rsp+68h] [rbp-20h]

  v10 = a6;
  v8 = a5;
  v11 = 4;
  v9 = 8;
  return tlgWriteTransfer_EventWriteTransfer(a1, a2, a3, a4, 4u, &v7);
}

```

## disassembly

```asm
0x180001908  mov     r11, rsp
0x18000190b  sub     rsp, 88h
0x180001912  mov     rax, cs:__security_cookie
0x180001919  xor     rax, rsp
0x18000191c  mov     [rsp+88h+var_18], rax
0x180001921  mov     rax, [rsp+88h+arg_28]
0x180001929  mov     r10d, 4
0x18000192f  mov     [r11-28h], rax
0x180001933  mov     rax, [rsp+88h+arg_20]
0x18000193b  mov     [r11-38h], rax
0x18000193f  lea     rax, [r11-58h]
0x180001943  mov     [r11-60h], rax
0x180001947  mov     [r11-68h], r10d
0x18000194b  mov     [r11-20h], r10
0x18000194f  mov     qword ptr [r11-30h], 8
0x180001957  call    _tlgWriteTransfer_EventWriteTransfer
0x18000195c  mov     rcx, [rsp+88h+var_18]
0x180001961  xor     rcx, rsp; StackCookie
0x180001964  call    __security_check_cookie
0x180001969  add     rsp, 88h
0x180001970  retn
```
