# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &)

- ea: `0x18000173c`
- end: `0x1800017a5`
- name: `??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@@Z`
- size: `105`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180011308`
- `0x1800113c8`

## callees

- `0x180001f68`
- `0x180002620`

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
0x18000173c  mov     r11, rsp
0x18000173f  sub     rsp, 88h
0x180001746  mov     rax, cs:__security_cookie
0x18000174d  xor     rax, rsp
0x180001750  mov     [rsp+88h+var_18], rax
0x180001755  mov     rax, [rsp+88h+arg_28]
0x18000175d  mov     r10d, 4
0x180001763  mov     [r11-28h], rax
0x180001767  mov     rax, [rsp+88h+arg_20]
0x18000176f  mov     [r11-38h], rax
0x180001773  lea     rax, [r11-58h]
0x180001777  mov     [r11-60h], rax
0x18000177b  mov     [r11-68h], r10d
0x18000177f  mov     [r11-20h], r10
0x180001783  mov     qword ptr [r11-30h], 8
0x18000178b  call    _tlgWriteTransfer_EventWriteTransfer
0x180001790  mov     rcx, [rsp+88h+var_18]
0x180001795  xor     rcx, rsp; StackCookie
0x180001798  call    __security_check_cookie
0x18000179d  add     rsp, 88h
0x1800017a4  retn
```
