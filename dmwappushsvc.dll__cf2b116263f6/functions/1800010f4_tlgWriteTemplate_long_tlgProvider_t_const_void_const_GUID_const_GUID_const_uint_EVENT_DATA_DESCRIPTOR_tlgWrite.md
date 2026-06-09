# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)

- ea: `0x1800010f4`
- end: `0x180001152`
- name: `??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z`
- size: `94`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180003e90`

## callees

- `0x180001158`
- `0x180001a70`

## pseudocode

```c
__int64 __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5)
{
  _QWORD v6[6]; // [rsp+30h] [rbp-48h] BYREF

  v6[4] = a5;
  v6[5] = 4;
  return tlgWriteTransfer_EventWriteTransfer(&dword_18001C048, a2, 0, 0, 3, v6);
}

```

## disassembly

```asm
0x1800010f4  mov     r11, rsp
0x1800010f7  sub     rsp, 78h
0x1800010fb  mov     rax, cs:__security_cookie
0x180001102  xor     rax, rsp
0x180001105  mov     [rsp+78h+var_18], rax
0x18000110a  mov     rax, [rsp+78h+arg_20]
0x180001112  lea     rcx, dword_18001C048
0x180001119  mov     [r11-28h], rax
0x18000111d  xor     r9d, r9d
0x180001120  lea     rax, [r11-48h]
0x180001124  mov     qword ptr [r11-20h], 4
0x18000112c  mov     [r11-50h], rax
0x180001130  xor     r8d, r8d
0x180001133  mov     [rsp+78h+var_58], 3
0x18000113b  call    _tlgWriteTransfer_EventWriteTransfer
0x180001140  mov     rcx, [rsp+78h+var_18]
0x180001145  xor     rcx, rsp; StackCookie
0x180001148  call    __security_check_cookie
0x18000114d  add     rsp, 78h
0x180001151  retn
```
