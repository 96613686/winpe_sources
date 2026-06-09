# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)

- ea: `0x18000141c`
- end: `0x1800014a4`
- name: `??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z`
- size: `136`
- prototype: ``
- caller_count: `14`
- callee_count: `2`
- tags: ``

## callers

- `0x180008fd0`
- `0x1800090ac`
- `0x180009190`
- `0x1800093c0`
- `0x1800095f0`
- `0x180009820`
- `0x180013cf0`
- `0x180013f20`
- `0x180014150`
- `0x180014380`
- `0x1800145b0`
- `0x1800147e0`
- `0x180014a10`
- `0x180014c40`

## callees

- `0x180001058`
- `0x180018a80`

## pseudocode

```c
ULONG __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        __int64 a1,
        unsigned __int8 *a2,
        const GUID *a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        __int64 a7)
{
  struct _EVENT_DATA_DESCRIPTOR v8; // [rsp+30h] [rbp-68h] BYREF
  __int64 v9; // [rsp+50h] [rbp-48h]
  __int64 v10; // [rsp+58h] [rbp-40h]
  __int64 v11; // [rsp+60h] [rbp-38h]
  __int64 v12; // [rsp+68h] [rbp-30h]
  __int64 v13; // [rsp+70h] [rbp-28h]
  __int64 v14; // [rsp+78h] [rbp-20h]

  v13 = a7;
  v11 = a6;
  v9 = a5;
  v14 = 4;
  v12 = 4;
  v10 = 8;
  return tlgWriteTransfer_EventWriteTransfer(a1, a2, a3, 0, 5u, &v8);
}

```

## disassembly

```asm
0x18000141c  mov     r11, rsp
0x18000141f  sub     rsp, 98h
0x180001426  mov     rax, cs:__security_cookie
0x18000142d  xor     rax, rsp
0x180001430  mov     [rsp+98h+var_18], rax
0x180001438  mov     rax, [rsp+98h+arg_30]
0x180001440  xor     r9d, r9d
0x180001443  mov     [r11-28h], rax
0x180001447  mov     rax, [rsp+98h+arg_28]
0x18000144f  mov     [r11-38h], rax
0x180001453  mov     rax, [rsp+98h+arg_20]
0x18000145b  mov     [r11-48h], rax
0x18000145f  lea     rax, [r11-68h]
0x180001463  mov     [r11-70h], rax
0x180001467  mov     [rsp+98h+var_78], 5
0x18000146f  mov     qword ptr [r11-20h], 4
0x180001477  mov     qword ptr [r11-30h], 4
0x18000147f  mov     qword ptr [r11-40h], 8
0x180001487  call    _tlgWriteTransfer_EventWriteTransfer
0x18000148c  mov     rcx, [rsp+98h+var_18]
0x180001494  xor     rcx, rsp; StackCookie
0x180001497  call    __security_check_cookie
0x18000149c  add     rsp, 98h
0x1800014a3  retn
```
