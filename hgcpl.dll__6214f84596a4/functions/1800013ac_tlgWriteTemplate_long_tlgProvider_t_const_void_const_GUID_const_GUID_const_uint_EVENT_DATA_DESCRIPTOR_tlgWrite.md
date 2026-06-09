# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &)

- ea: `0x1800013ac`
- end: `0x180001415`
- name: `??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@@Z`
- size: `105`
- prototype: ``
- caller_count: `12`
- callee_count: `2`
- tags: ``

## callers

- `0x180008bfc`
- `0x180008cbc`
- `0x180008ddc`
- `0x180008e9c`
- `0x1800136e4`
- `0x1800137a4`
- `0x180013864`
- `0x180013924`
- `0x1800139e4`
- `0x180013aa4`
- `0x180013b64`
- `0x180013c24`

## callees

- `0x180001058`
- `0x180018a80`

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
0x1800013ac  mov     r11, rsp
0x1800013af  sub     rsp, 88h
0x1800013b6  mov     rax, cs:__security_cookie
0x1800013bd  xor     rax, rsp
0x1800013c0  mov     [rsp+88h+var_18], rax
0x1800013c5  mov     rax, [rsp+88h+arg_28]
0x1800013cd  mov     r10d, 4
0x1800013d3  mov     [r11-28h], rax
0x1800013d7  mov     rax, [rsp+88h+arg_20]
0x1800013df  mov     [r11-38h], rax
0x1800013e3  lea     rax, [r11-58h]
0x1800013e7  mov     [r11-60h], rax
0x1800013eb  mov     [r11-68h], r10d
0x1800013ef  mov     [r11-20h], r10
0x1800013f3  mov     qword ptr [r11-30h], 8
0x1800013fb  call    _tlgWriteTransfer_EventWriteTransfer
0x180001400  mov     rcx, [rsp+88h+var_18]
0x180001405  xor     rcx, rsp; StackCookie
0x180001408  call    __security_check_cookie
0x18000140d  add     rsp, 88h
0x180001414  retn
```
