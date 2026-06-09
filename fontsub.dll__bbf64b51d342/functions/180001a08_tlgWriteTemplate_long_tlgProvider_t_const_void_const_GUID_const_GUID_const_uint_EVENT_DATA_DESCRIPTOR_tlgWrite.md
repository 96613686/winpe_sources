# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)

- ea: `0x180001a08`
- end: `0x180001a92`
- name: `??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@44@Z`
- size: `138`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18000611c`
- `0x180006378`

## callees

- `0x180001f18`
- `0x18001ac90`

## pseudocode

```c
ULONG __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        __int64 a1,
        unsigned __int8 *a2,
        const GUID *a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        __int64 a7,
        __int64 a8)
{
  struct _EVENT_DATA_DESCRIPTOR v9; // [rsp+30h] [rbp-39h] BYREF
  __int64 v10; // [rsp+50h] [rbp-19h]
  __int64 v11; // [rsp+58h] [rbp-11h]
  __int64 v12; // [rsp+60h] [rbp-9h]
  __int64 v13; // [rsp+68h] [rbp-1h]
  __int64 v14; // [rsp+70h] [rbp+7h]
  __int64 v15; // [rsp+78h] [rbp+Fh]
  __int64 v16; // [rsp+80h] [rbp+17h]
  __int64 v17; // [rsp+88h] [rbp+1Fh]

  v16 = a8;
  v14 = a7;
  v12 = a6;
  v10 = a5;
  v17 = 4;
  v15 = 4;
  v13 = 4;
  v11 = 8;
  return tlgWriteTransfer_EventWriteTransfer(a1, a2, a3, 0, 6u, &v9);
}

```

## disassembly

```asm
0x180001a08  push    rbp
0x180001a0a  lea     rbp, [rsp-37h]
0x180001a0f  sub     rsp, 0A0h
0x180001a16  mov     rax, cs:__security_cookie
0x180001a1d  xor     rax, rsp
0x180001a20  mov     [rbp+37h+var_10], rax
0x180001a24  mov     rax, [rbp+37h+arg_38]
0x180001a28  xor     r9d, r9d
0x180001a2b  mov     [rbp+37h+var_20], rax
0x180001a2f  mov     rax, [rbp+37h+arg_30]
0x180001a33  mov     [rbp+37h+var_30], rax
0x180001a37  mov     rax, [rbp+37h+arg_28]
0x180001a3b  mov     [rbp+37h+var_40], rax
0x180001a3f  mov     rax, [rbp+37h+arg_20]
0x180001a43  mov     [rbp+37h+var_50], rax
0x180001a47  lea     rax, [rbp+37h+var_70]
0x180001a4b  mov     [rsp+0A0h+var_78], rax
0x180001a50  mov     [rsp+0A0h+var_80], 6
0x180001a58  mov     [rbp+37h+var_18], 4
0x180001a60  mov     [rbp+37h+var_28], 4
0x180001a68  mov     [rbp+37h+var_38], 4
0x180001a70  mov     [rbp+37h+var_48], 8
0x180001a78  call    _tlgWriteTransfer_EventWriteTransfer
0x180001a7d  mov     rcx, [rbp+37h+var_10]
0x180001a81  xor     rcx, rsp; StackCookie
0x180001a84  call    __security_check_cookie
0x180001a89  add     rsp, 0A0h
0x180001a90  pop     rbp
0x180001a91  retn
```
