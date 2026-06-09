# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<1>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<2> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &)

- ea: `0x1400013d8`
- end: `0x140001496`
- name: `??$Write@U?$_tlgWrapperByVal@$03@@U1@U1@U?$_tlgWrapperByVal@$01@@U?$_tlgWrapperByVal@$00@@U1@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@33AEBU?$_tlgWrapperByVal@$01@@AEBU?$_tlgWrapperByVal@$00@@3AEBU?$_tlgWrapperByVal@$07@@@Z`
- size: `190`
- prototype: `__int64 __fastcall(int, int, __int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64)`
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
__int64 __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<1>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
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
        __int64 a11)
{
  struct _EVENT_DATA_DESCRIPTOR v12; // [rsp+30h] [rbp-81h] BYREF
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
  v26 = 8;
  v24 = 4;
  v22 = 1;
  v20 = 2;
  v18 = 4;
  v16 = 4;
  v14 = 4;
  return tlgWriteTransfer_EventWriteTransfer(a1, a2, 0, 0, 9u, &v12);
}

```

## disassembly

```asm
0x1400013d8  push    rbp
0x1400013da  lea     rbp, [rsp-1Fh]
0x1400013df  sub     rsp, 0D0h
0x1400013e6  mov     rax, cs:__security_cookie
0x1400013ed  xor     rax, rsp
0x1400013f0  mov     [rbp+1Fh+var_10], rax
0x1400013f4  mov     rax, [rbp+1Fh+arg_50]
0x1400013f8  xor     r9d, r9d; int
0x1400013fb  mov     [rbp+1Fh+var_20], rax
0x1400013ff  xor     r8d, r8d; int
0x140001402  mov     rax, [rbp+1Fh+arg_48]
0x140001406  mov     [rbp+1Fh+var_30], rax
0x14000140a  mov     rax, [rbp+1Fh+arg_40]
0x14000140e  mov     [rbp+1Fh+var_40], rax
0x140001412  mov     rax, [rbp+1Fh+arg_38]
0x140001416  mov     [rbp+1Fh+var_50], rax
0x14000141a  mov     rax, [rbp+1Fh+arg_30]
0x14000141e  mov     [rbp+1Fh+var_60], rax
0x140001422  mov     rax, [rbp+1Fh+arg_28]
0x140001426  mov     [rbp+1Fh+var_70], rax
0x14000142a  mov     rax, [rbp+1Fh+arg_20]
0x14000142e  mov     [rbp+1Fh+var_80], rax
0x140001432  lea     rax, [rsp+0D0h+var_A0]
0x140001437  mov     [rsp+0D0h+var_A8], rax; PEVENT_DATA_DESCRIPTOR
0x14000143c  mov     [rsp+0D0h+var_B0], 9; ULONG
0x140001444  mov     [rbp+1Fh+var_18], 8
0x14000144c  mov     [rbp+1Fh+var_28], 4
0x140001454  mov     [rbp+1Fh+var_38], 1
0x14000145c  mov     [rbp+1Fh+var_48], 2
0x140001464  mov     [rbp+1Fh+var_58], 4
0x14000146c  mov     [rbp+1Fh+var_68], 4
0x140001474  mov     [rbp+1Fh+var_78], 4
0x14000147c  call    _tlgWriteTransfer_EventWriteTransfer
0x140001481  mov     rcx, [rbp+1Fh+var_10]
0x140001485  xor     rcx, rsp; StackCookie
0x140001488  call    __security_check_cookie
0x14000148d  add     rsp, 0D0h
0x140001494  pop     rbp
0x140001495  retn
```
