# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)

- ea: `0x140001098`
- end: `0x1400010ec`
- name: `??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z`
- size: `84`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x14000ca40`
- `0x14000cf10`

## callees

- `0x140001130`
- `0x14000ded0`

## pseudocode

```c
ULONG __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
        __int64 a1,
        unsigned __int8 *a2,
        const GUID *a3,
        __int64 a4,
        __int64 a5)
{
  struct _EVENT_DATA_DESCRIPTOR v6; // [rsp+30h] [rbp-48h] BYREF
  __int64 v7; // [rsp+50h] [rbp-28h]
  __int64 v8; // [rsp+58h] [rbp-20h]

  v7 = a5;
  v8 = 4;
  return tlgWriteTransfer_EventWriteTransfer(a1, a2, a3, 0, 3u, &v6);
}

```

## disassembly

```asm
0x140001098  mov     r11, rsp
0x14000109b  sub     rsp, 78h
0x14000109f  mov     rax, cs:__security_cookie
0x1400010a6  xor     rax, rsp
0x1400010a9  mov     [rsp+78h+var_18], rax
0x1400010ae  mov     rax, [rsp+78h+arg_20]
0x1400010b6  xor     r9d, r9d
0x1400010b9  mov     [r11-28h], rax
0x1400010bd  lea     rax, [r11-48h]
0x1400010c1  mov     [r11-50h], rax
0x1400010c5  mov     [rsp+78h+var_58], 3
0x1400010cd  mov     qword ptr [r11-20h], 4
0x1400010d5  call    _tlgWriteTransfer_EventWriteTransfer
0x1400010da  mov     rcx, [rsp+78h+var_18]
0x1400010df  xor     rcx, rsp; StackCookie
0x1400010e2  call    __security_check_cookie
0x1400010e7  add     rsp, 78h
0x1400010eb  retn
```
