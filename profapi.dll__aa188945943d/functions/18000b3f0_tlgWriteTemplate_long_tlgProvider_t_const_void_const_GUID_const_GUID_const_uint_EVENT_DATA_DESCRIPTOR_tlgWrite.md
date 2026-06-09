# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &)

- ea: `0x18000b3f0`
- end: `0x18000b45f`
- name: `??$Write@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$07@@@Z`
- size: `111`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, __int64, __int64)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x180011f3c`
- `0x180011fa8`
- `0x180012014`

## callees

- `0x18000b468`
- `0x18000fa10`

## pseudocode

```c
__int64 __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
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
  v7[5] = 4;
  v7[7] = 8;
  return tlgWriteTransfer_EventWriteTransfer(a1, a2, 0, 0, 4, v7);
}

```

## disassembly

```asm
0x18000b3f0  mov     r11, rsp
0x18000b3f3  sub     rsp, 88h
0x18000b3fa  mov     rax, cs:__security_cookie
0x18000b401  xor     rax, rsp
0x18000b404  mov     [rsp+88h+var_18], rax
0x18000b409  mov     rax, [rsp+88h+arg_28]
0x18000b411  mov     r8d, 4
0x18000b417  mov     [r11-28h], rax
0x18000b41b  xor     r9d, r9d
0x18000b41e  mov     rax, [rsp+88h+arg_20]
0x18000b426  mov     [r11-38h], rax
0x18000b42a  lea     rax, [r11-58h]
0x18000b42e  mov     [r11-60h], rax
0x18000b432  mov     [r11-68h], r8d
0x18000b436  mov     [r11-30h], r8
0x18000b43a  xor     r8d, r8d
0x18000b43d  mov     qword ptr [r11-20h], 8
0x18000b445  call    _tlgWriteTransfer_EventWriteTransfer
0x18000b44a  mov     rcx, [rsp+88h+var_18]
0x18000b44f  xor     rcx, rsp; StackCookie
0x18000b452  call    __security_check_cookie
0x18000b457  add     rsp, 88h
0x18000b45e  retn
```
