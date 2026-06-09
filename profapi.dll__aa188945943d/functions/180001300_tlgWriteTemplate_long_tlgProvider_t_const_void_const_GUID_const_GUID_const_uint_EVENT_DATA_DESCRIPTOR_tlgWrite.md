# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &)

- ea: `0x180001300`
- end: `0x180001357`
- name: `??$Write@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@@Z`
- size: `87`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18000debc`
- `0x180012330`

## callees

- `0x18000b468`
- `0x18000fa10`

## pseudocode

```c
__int64 __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>>(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5)
{
  _QWORD v6[6]; // [rsp+30h] [rbp-48h] BYREF

  v6[4] = a5;
  v6[5] = 8;
  return tlgWriteTransfer_EventWriteTransfer(a1, a2, 0, 0, 3, v6);
}

```

## disassembly

```asm
0x180001300  mov     r11, rsp
0x180001303  sub     rsp, 78h
0x180001307  mov     rax, cs:__security_cookie
0x18000130e  xor     rax, rsp
0x180001311  mov     [rsp+78h+var_18], rax
0x180001316  mov     rax, [rsp+78h+arg_20]
0x18000131e  xor     r9d, r9d
0x180001321  mov     [r11-28h], rax
0x180001325  xor     r8d, r8d
0x180001328  lea     rax, [r11-48h]
0x18000132c  mov     qword ptr [r11-20h], 8
0x180001334  mov     [r11-50h], rax
0x180001338  mov     [rsp+78h+var_58], 3
0x180001340  call    _tlgWriteTransfer_EventWriteTransfer
0x180001345  mov     rcx, [rsp+78h+var_18]
0x18000134a  xor     rcx, rsp; StackCookie
0x18000134d  call    __security_check_cookie
0x180001352  add     rsp, 78h
0x180001356  retn
```
