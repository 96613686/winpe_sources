# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<1>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<2> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByVal<8> const &)

- ea: `0x140001304`
- end: `0x1400013d2`
- name: `??$Write@U?$_tlgWrapperByVal@$03@@U1@U1@U?$_tlgWrapperByVal@$01@@U?$_tlgWrapperByVal@$00@@U1@U3@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@33AEBU?$_tlgWrapperByVal@$01@@AEBU?$_tlgWrapperByVal@$00@@35AEBU?$_tlgWrapperByVal@$07@@@Z`
- size: `206`
- prototype: `__int64 __fastcall(int, int, __int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140023b70`

## callees

- `0x140001c88`
- `0x140002360`

## pseudocode

```c
__int64 __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<1>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>,_tlgWrapperByVal<8>>(
        int a1,
        int a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        __int64 a7,
        __int64 a8,
        __int64 a9,
        __int64 a10,
        __int64 a11,
        __int64 a12)
{
  struct _EVENT_DATA_DESCRIPTOR v13; // [rsp+30h] [rbp-99h] BYREF
  __int64 v14; // [rsp+50h] [rbp-79h]
  __int64 v15; // [rsp+58h] [rbp-71h]
  __int64 v16; // [rsp+60h] [rbp-69h]
  __int64 v17; // [rsp+68h] [rbp-61h]
  __int64 v18; // [rsp+70h] [rbp-59h]
  __int64 v19; // [rsp+78h] [rbp-51h]
  __int64 v20; // [rsp+80h] [rbp-49h]
  __int64 v21; // [rsp+88h] [rbp-41h]
  __int64 v22; // [rsp+90h] [rbp-39h]
  __int64 v23; // [rsp+98h] [rbp-31h]
  __int64 v24; // [rsp+A0h] [rbp-29h]
  __int64 v25; // [rsp+A8h] [rbp-21h]
  __int64 v26; // [rsp+B0h] [rbp-19h]
  __int64 v27; // [rsp+B8h] [rbp-11h]
  __int64 v28; // [rsp+C0h] [rbp-9h]
  __int64 v29; // [rsp+C8h] [rbp-1h]

  v28 = a12;
  v26 = a11;
  v24 = a10;
  v22 = a9;
  v20 = a8;
  v18 = a7;
  v16 = a6;
  v14 = a5;
  v29 = 8;
  v27 = 1;
  v25 = 4;
  v23 = 1;
  v21 = 2;
  v19 = 4;
  v17 = 4;
  v15 = 4;
  return tlgWriteTransfer_EventWriteTransfer(a1, a2, 0, 0, 0xAu, &v13);
}

```

## disassembly

```asm
0x140001304  push    rbp
0x140001306  lea     rbp, [rsp-17h]
0x14000130b  sub     rsp, 0E0h
0x140001312  mov     rax, cs:__security_cookie
0x140001319  xor     rax, rsp
0x14000131c  mov     [rbp+17h+var_10], rax
0x140001320  mov     rax, [rbp+17h+arg_58]
0x140001324  xor     r9d, r9d; int
0x140001327  mov     [rbp+17h+var_20], rax
0x14000132b  xor     r8d, r8d; int
0x14000132e  mov     rax, [rbp+17h+arg_50]
0x140001332  mov     [rbp+17h+var_30], rax
0x140001336  mov     rax, [rbp+17h+arg_48]
0x14000133a  mov     [rbp+17h+var_40], rax
0x14000133e  mov     rax, [rbp+17h+arg_40]
0x140001342  mov     [rbp+17h+var_50], rax
0x140001346  mov     rax, [rbp+17h+arg_38]
0x14000134a  mov     [rbp+17h+var_60], rax
0x14000134e  mov     rax, [rbp+17h+arg_30]
0x140001352  mov     [rbp+17h+var_70], rax
0x140001356  mov     rax, [rbp+17h+arg_28]
0x14000135a  mov     [rbp+17h+var_80], rax
0x14000135e  mov     rax, [rbp+17h+arg_20]
0x140001362  mov     [rbp+17h+var_90], rax
0x140001366  lea     rax, [rsp+0E0h+var_B0]
0x14000136b  mov     [rsp+0E0h+var_B8], rax; PEVENT_DATA_DESCRIPTOR
0x140001370  mov     [rsp+0E0h+var_C0], 0Ah; ULONG
0x140001378  mov     [rbp+17h+var_18], 8
0x140001380  mov     [rbp+17h+var_28], 1
0x140001388  mov     [rbp+17h+var_38], 4
0x140001390  mov     [rbp+17h+var_48], 1
0x140001398  mov     [rbp+17h+var_58], 2
0x1400013a0  mov     [rbp+17h+var_68], 4
0x1400013a8  mov     [rbp+17h+var_78], 4
0x1400013b0  mov     [rbp+17h+var_88], 4
0x1400013b8  call    _tlgWriteTransfer_EventWriteTransfer
0x1400013bd  mov     rcx, [rbp+17h+var_10]
0x1400013c1  xor     rcx, rsp; StackCookie
0x1400013c4  call    __security_check_cookie
0x1400013c9  add     rsp, 0E0h
0x1400013d0  pop     rbp
0x1400013d1  retn
```
