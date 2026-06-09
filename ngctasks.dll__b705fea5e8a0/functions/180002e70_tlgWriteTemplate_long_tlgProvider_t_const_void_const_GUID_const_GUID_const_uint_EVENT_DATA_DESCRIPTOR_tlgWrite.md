# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)

- ea: `0x180002e70`
- end: `0x180002ec1`
- name: `??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z`
- size: `81`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `10`
- callee_count: `2`
- tags: ``

## callers

- `0x180010658`
- `0x180010d94`
- `0x180010ea4`
- `0x1800113a0`
- `0x1800126e4`
- `0x1800149c0`
- `0x180014ea4`
- `0x1800151a0`
- `0x18001b934`
- `0x18001baf4`

## callees

- `0x1800024a8`
- `0x180006330`

## pseudocode

```c
__int64 __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
        __int64 a1,
        __int64 a2)
{
  return tlgWriteTransfer_EventWriteTransfer(a1, a2);
}

```

## disassembly

```asm
0x180002e70  mov     r11, rsp
0x180002e73  sub     rsp, 78h
0x180002e77  mov     rax, cs:__security_cookie
0x180002e7e  xor     rax, rsp
0x180002e81  mov     [rsp+78h+var_18], rax
0x180002e86  mov     rax, [rsp+78h+arg_20]
0x180002e8e  mov     [r11-28h], rax
0x180002e92  lea     rax, [r11-48h]
0x180002e96  mov     [r11-50h], rax
0x180002e9a  mov     [rsp+78h+var_58], 3
0x180002ea2  mov     qword ptr [r11-20h], 4
0x180002eaa  call    _tlgWriteTransfer_EventWriteTransfer
0x180002eaf  mov     rcx, [rsp+78h+var_18]
0x180002eb4  xor     rcx, rsp; StackCookie
0x180002eb7  call    __security_check_cookie
0x180002ebc  add     rsp, 78h
0x180002ec0  retn
```
