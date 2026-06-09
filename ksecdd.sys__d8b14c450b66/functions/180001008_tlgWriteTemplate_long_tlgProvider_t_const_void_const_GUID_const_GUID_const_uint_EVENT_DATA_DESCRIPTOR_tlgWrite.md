# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<1> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &)

- ea: `0x180001008`
- end: `0x1800010bc`
- name: `??$Write@U?$_tlgWrapperByVal@$00@@U1@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$07@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$00@@33AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$07@@4@Z`
- size: `180`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18000fe7c`

## callees

- `0x1800010f4`
- `0x180010840`

## pseudocode

```c
NTSTATUS __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(
        __int64 a1,
        unsigned __int8 *a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        __int64 a7,
        __int64 a8,
        __int64 a9,
        __int64 a10)
{
  struct _EVENT_DATA_DESCRIPTOR v11; // [rsp+30h] [rbp-69h] BYREF
  __int64 v12; // [rsp+50h] [rbp-49h]
  __int64 v13; // [rsp+58h] [rbp-41h]
  __int64 v14; // [rsp+60h] [rbp-39h]
  __int64 v15; // [rsp+68h] [rbp-31h]
  __int64 v16; // [rsp+70h] [rbp-29h]
  __int64 v17; // [rsp+78h] [rbp-21h]
  __int64 v18; // [rsp+80h] [rbp-19h]
  __int64 v19; // [rsp+88h] [rbp-11h]
  __int64 v20; // [rsp+90h] [rbp-9h]
  __int64 v21; // [rsp+98h] [rbp-1h]
  __int64 v22; // [rsp+A0h] [rbp+7h]
  __int64 v23; // [rsp+A8h] [rbp+Fh]

  v22 = a10;
  v20 = a9;
  v18 = a8;
  v16 = a7;
  v14 = a6;
  v12 = a5;
  v21 = 8;
  v23 = 4;
  v19 = 4;
  v17 = 1;
  v15 = 1;
  v13 = 1;
  return tlgWriteTransfer_EtwWriteTransfer((__int64)&dword_1800191F0, a2, 0, 0, 8u, &v11);
}

```

## disassembly

```asm
0x180001008  push    rbp
0x18000100a  lea     rbp, [rsp-27h]
0x18000100f  sub     rsp, 0C0h
0x180001016  mov     rax, cs:__security_cookie
0x18000101d  xor     rax, rsp
0x180001020  mov     [rbp+27h+var_10], rax
0x180001024  mov     rax, [rbp+27h+arg_48]
0x180001028  lea     rcx, dword_1800191F0
0x18000102f  mov     [rbp+27h+var_20], rax
0x180001033  mov     r8d, 8
0x180001039  mov     rax, [rbp+27h+arg_40]
0x18000103d  xor     r9d, r9d
0x180001040  mov     [rbp+27h+var_30], rax
0x180001044  mov     rax, [rbp+27h+arg_38]
0x180001048  mov     [rbp+27h+var_40], rax
0x18000104c  mov     rax, [rbp+27h+arg_30]
0x180001050  mov     [rbp+27h+var_50], rax
0x180001054  mov     rax, [rbp+27h+arg_28]
0x180001058  mov     [rbp+27h+var_60], rax
0x18000105c  mov     rax, [rbp+27h+arg_20]
0x180001060  mov     [rbp+27h+var_70], rax
0x180001064  lea     rax, [rbp+27h+var_90]
0x180001068  mov     [rsp+0C0h+var_98], rax
0x18000106d  mov     [rsp+0C0h+var_A0], r8d
0x180001072  mov     [rbp+27h+var_28], r8
0x180001076  xor     r8d, r8d
0x180001079  mov     [rbp+27h+var_18], 4
0x180001081  mov     [rbp+27h+var_38], 4
0x180001089  mov     [rbp+27h+var_48], 1
0x180001091  mov     [rbp+27h+var_58], 1
0x180001099  mov     [rbp+27h+var_68], 1
0x1800010a1  call    _tlgWriteTransfer_EtwWriteTransfer
0x1800010a6  mov     rcx, [rbp+27h+var_10]
0x1800010aa  xor     rcx, rsp; StackCookie
0x1800010ad  call    __security_check_cookie
0x1800010b2  add     rsp, 0C0h
0x1800010b9  pop     rbp
0x1800010ba  retn
```
