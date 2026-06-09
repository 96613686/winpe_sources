# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_BrowserWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByRef<16>,_tlgWrapperByVal<1>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &)

- ea: `0x1400010d4`
- end: `0x14000117e`
- name: `??$Write@U?$_tlgWrapperByRef@$0BA@@@U1@U?$_tlgWrapperByVal@$00@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_BrowserWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@3AEBU?$_tlgWrapperByVal@$00@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$07@@@Z`
- size: `170`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x14000237c`

## callees

- `0x140001310`
- `0x1400059b0`

## pseudocode

```c
ULONG __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_BrowserWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByRef<16>,_tlgWrapperByVal<1>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
        __int64 a1,
        unsigned __int8 *a2,
        __int64 a3,
        __int64 a4,
        __int64 *a5,
        __int64 *a6,
        __int64 a7,
        __int64 a8,
        __int64 a9)
{
  struct _EVENT_DATA_DESCRIPTOR v10; // [rsp+30h] [rbp-51h] BYREF
  __int64 v11; // [rsp+50h] [rbp-31h]
  __int64 v12; // [rsp+58h] [rbp-29h]
  __int64 v13; // [rsp+60h] [rbp-21h]
  __int64 v14; // [rsp+68h] [rbp-19h]
  __int64 v15; // [rsp+70h] [rbp-11h]
  __int64 v16; // [rsp+78h] [rbp-9h]
  __int64 v17; // [rsp+80h] [rbp-1h]
  __int64 v18; // [rsp+88h] [rbp+7h]
  __int64 v19; // [rsp+90h] [rbp+Fh]
  __int64 v20; // [rsp+98h] [rbp+17h]

  v19 = a9;
  v17 = a8;
  v15 = a7;
  v20 = 8;
  v18 = 4;
  v16 = 1;
  v13 = *a6;
  v14 = 16;
  v12 = 16;
  v11 = *a5;
  return tlgWriteTransfer_BrowserWriteTransfer((__int64)&dword_14000A000, a2, 0, 0, 7u, &v10);
}

```

## disassembly

```asm
0x1400010d4  push    rbp
0x1400010d6  lea     rbp, [rsp-2Fh]
0x1400010db  sub     rsp, 0B0h
0x1400010e2  mov     rax, cs:__security_cookie
0x1400010e9  xor     rax, rsp
0x1400010ec  mov     [rbp+2Fh+var_10], rax
0x1400010f0  mov     rax, [rbp+2Fh+arg_40]
0x1400010f4  xor     r9d, r9d
0x1400010f7  mov     [rbp+2Fh+var_20], rax
0x1400010fb  xor     r8d, r8d
0x1400010fe  mov     rax, [rbp+2Fh+arg_38]
0x140001102  mov     [rbp+2Fh+var_30], rax
0x140001106  mov     rax, [rbp+2Fh+arg_30]
0x14000110a  mov     [rbp+2Fh+var_40], rax
0x14000110e  mov     rax, [rbp+2Fh+arg_28]
0x140001112  mov     [rbp+2Fh+var_18], 8
0x14000111a  mov     [rbp+2Fh+var_28], 4
0x140001122  mov     [rbp+2Fh+var_38], 1
0x14000112a  mov     rcx, [rax]
0x14000112d  mov     rax, [rbp+2Fh+arg_20]
0x140001131  mov     [rbp+2Fh+var_50], rcx
0x140001135  mov     [rbp+2Fh+var_48], 10h
0x14000113d  mov     [rbp+2Fh+var_58], 10h
0x140001145  mov     rcx, [rax]
0x140001148  lea     rax, [rbp+2Fh+var_80]
0x14000114c  mov     [rbp+2Fh+var_60], rcx
0x140001150  lea     rcx, dword_14000A000
0x140001157  mov     [rsp+0B0h+var_88], rax
0x14000115c  mov     [rsp+0B0h+var_90], 7
0x140001164  call    _tlgWriteTransfer_BrowserWriteTransfer
0x140001169  mov     rcx, [rbp+2Fh+var_10]
0x14000116d  xor     rcx, rsp; StackCookie
0x140001170  call    __security_check_cookie
0x140001175  add     rsp, 0B0h
0x14000117c  pop     rbp
0x14000117d  retn
```
