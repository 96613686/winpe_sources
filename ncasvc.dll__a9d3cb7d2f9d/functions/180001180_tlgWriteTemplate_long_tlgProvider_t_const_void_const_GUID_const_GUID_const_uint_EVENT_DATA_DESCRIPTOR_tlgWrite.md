# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)

- ea: `0x180001180`
- end: `0x180001246`
- name: `??$Write@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$07@@U1@U1@U1@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$07@@33333@Z`
- size: `198`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180016260`

## callees

- `0x180001278`
- `0x18001cc70`

## pseudocode

```c
__int64 __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        __int64 a7,
        __int64 a8,
        __int64 a9,
        __int64 a10,
        __int64 a11)
{
  _BYTE v12[32]; // [rsp+30h] [rbp-81h] BYREF
  __int64 v13; // [rsp+50h] [rbp-61h]
  __int64 v14; // [rsp+58h] [rbp-59h]
  __int64 v15; // [rsp+60h] [rbp-51h]
  __int64 v16; // [rsp+68h] [rbp-49h]
  __int64 v17; // [rsp+70h] [rbp-41h]
  __int64 v18; // [rsp+78h] [rbp-39h]
  __int64 v19; // [rsp+80h] [rbp-31h]
  __int64 v20; // [rsp+88h] [rbp-29h]
  __int64 v21; // [rsp+90h] [rbp-21h]
  __int64 v22; // [rsp+98h] [rbp-19h]
  __int64 v23; // [rsp+A0h] [rbp-11h]
  __int64 v24; // [rsp+A8h] [rbp-9h]
  __int64 v25; // [rsp+B0h] [rbp-1h]
  __int64 v26; // [rsp+B8h] [rbp+7h]

  v25 = a11;
  v23 = a10;
  v21 = a9;
  v19 = a8;
  v17 = a7;
  v15 = a6;
  v13 = a5;
  v26 = 4;
  v24 = 4;
  v22 = 4;
  v20 = 4;
  v18 = 4;
  v16 = 8;
  v14 = 4;
  return tlgWriteTransfer_EventWriteTransfer(&dword_180028048, a2, 0, 0, 9, v12);
}

```

## disassembly

```asm
0x180001180  push    rbp
0x180001182  lea     rbp, [rsp-1Fh]
0x180001187  sub     rsp, 0D0h
0x18000118e  mov     rax, cs:__security_cookie
0x180001195  xor     rax, rsp
0x180001198  mov     [rbp+1Fh+var_10], rax
0x18000119c  mov     rax, [rbp+1Fh+arg_50]
0x1800011a0  lea     rcx, dword_180028048
0x1800011a7  mov     [rbp+1Fh+var_20], rax
0x1800011ab  xor     r9d, r9d
0x1800011ae  mov     rax, [rbp+1Fh+arg_48]
0x1800011b2  xor     r8d, r8d
0x1800011b5  mov     [rbp+1Fh+var_30], rax
0x1800011b9  mov     rax, [rbp+1Fh+arg_40]
0x1800011bd  mov     [rbp+1Fh+var_40], rax
0x1800011c1  mov     rax, [rbp+1Fh+arg_38]
0x1800011c5  mov     [rbp+1Fh+var_50], rax
0x1800011c9  mov     rax, [rbp+1Fh+arg_30]
0x1800011cd  mov     [rbp+1Fh+var_60], rax
0x1800011d1  mov     rax, [rbp+1Fh+arg_28]
0x1800011d5  mov     [rbp+1Fh+var_70], rax
0x1800011d9  mov     rax, [rbp+1Fh+arg_20]
0x1800011dd  mov     [rbp+1Fh+var_80], rax
0x1800011e1  lea     rax, [rsp+0D0h+var_A0]
0x1800011e6  mov     [rsp+0D0h+var_A8], rax
0x1800011eb  mov     [rsp+0D0h+var_B0], 9
0x1800011f3  mov     [rbp+1Fh+var_18], 4
0x1800011fb  mov     [rbp+1Fh+var_28], 4
0x180001203  mov     [rbp+1Fh+var_38], 4
0x18000120b  mov     [rbp+1Fh+var_48], 4
0x180001213  mov     [rbp+1Fh+var_58], 4
0x18000121b  mov     [rbp+1Fh+var_68], 8
0x180001223  mov     [rbp+1Fh+var_78], 4
0x18000122b  call    _tlgWriteTransfer_EventWriteTransfer
0x180001230  mov     rcx, [rbp+1Fh+var_10]
0x180001234  xor     rcx, rsp; StackCookie
0x180001237  call    __security_check_cookie
0x18000123c  add     rsp, 0D0h
0x180001243  pop     rbp
0x180001244  retn
```
