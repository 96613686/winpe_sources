# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)

- ea: `0x180001de4`
- end: `0x180001e6c`
- name: `??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z`
- size: `136`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, __int64, __int64, __int64)`
- caller_count: `12`
- callee_count: `2`
- tags: ``

## callers

- `0x1800091c4`
- `0x1800092a0`
- `0x18000bf70`
- `0x180013b38`
- `0x180013c20`
- `0x180013e50`
- `0x180014090`
- `0x1800142d0`
- `0x180014510`
- `0x180014750`
- `0x180014990`
- `0x180014bd0`

## callees

- `0x1800019e8`
- `0x180002b10`

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
0x180001de4  mov     r11, rsp
0x180001de7  sub     rsp, 98h
0x180001dee  mov     rax, cs:__security_cookie
0x180001df5  xor     rax, rsp
0x180001df8  mov     [rsp+98h+var_18], rax
0x180001e00  mov     rax, [rsp+98h+arg_30]
0x180001e08  xor     r9d, r9d
0x180001e0b  mov     [r11-28h], rax
0x180001e0f  mov     rax, [rsp+98h+arg_28]
0x180001e17  mov     [r11-38h], rax
0x180001e1b  mov     rax, [rsp+98h+arg_20]
0x180001e23  mov     [r11-48h], rax
0x180001e27  lea     rax, [r11-68h]
0x180001e2b  mov     [r11-70h], rax
0x180001e2f  mov     [rsp+98h+var_78], 5
0x180001e37  mov     qword ptr [r11-20h], 4
0x180001e3f  mov     qword ptr [r11-30h], 4
0x180001e47  mov     qword ptr [r11-40h], 8
0x180001e4f  call    _tlgWriteTransfer_EventWriteTransfer
0x180001e54  mov     rcx, [rsp+98h+var_18]
0x180001e5c  xor     rcx, rsp; StackCookie
0x180001e5f  call    __security_check_cookie
0x180001e64  add     rsp, 98h
0x180001e6b  retn
```
