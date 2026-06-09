# NcaTelemetryEventWriteDirectAccessDiag(NCA_DAP_USER_EVSNPSHT_ * const,NCA_STATUS_EVENT_ const *,ulong)

- ea: `0x180016260`
- end: `0x18001632f`
- name: `?NcaTelemetryEventWriteDirectAccessDiag@@YAXQEAUNCA_DAP_USER_EVSNPSHT_@@PEBUNCA_STATUS_EVENT_@@K@Z`
- size: `207`
- prototype: `void __fastcall(struct NCA_DAP_USER_EVSNPSHT_ *const, const struct NCA_STATUS_EVENT_ *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180015f20`

## callees

- `0x180001180`
- `0x18000124c`
- `0x180016260`

## pseudocode

```c
void __fastcall NcaTelemetryEventWriteDirectAccessDiag(
        struct NCA_DAP_USER_EVSNPSHT_ *const a1,
        const struct NCA_STATUS_EVENT_ *a2)
{
  __int64 v2; // rcx
  __int64 v3; // r8
  __int64 v4; // r9
  int *v5; // r10
  int v6; // [rsp+60h] [rbp-20h] BYREF
  int v7; // [rsp+64h] [rbp-1Ch] BYREF
  int v8; // [rsp+68h] [rbp-18h] BYREF
  int v9; // [rsp+6Ch] [rbp-14h] BYREF
  __int64 v10; // [rsp+70h] [rbp-10h] BYREF
  int v11; // [rsp+90h] [rbp+10h] BYREF
  int v12; // [rsp+A8h] [rbp+28h] BYREF

  if ( a1 && (unsigned int)dword_180028048 > 5 )
  {
    if ( (unsigned __int8)tlgKeywordOn(a1, 0x400000000000LL) )
    {
      v12 = v5[1];
      v6 = *v5;
      v7 = *(_DWORD *)(v4 + 636);
      v8 = *(_DWORD *)(v4 + 632);
      v10 = *(_QWORD *)(v4 + 616);
      v9 = *(_DWORD *)(v4 + 612);
      v11 = v3;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v2,
        (__int64)byte_1800243B1,
        v3,
        v4,
        (__int64)&v9,
        (__int64)&v10,
        (__int64)&v8,
        (__int64)&v7,
        (__int64)&v6,
        (__int64)&v12,
        (__int64)&v11);
    }
  }
}

```

## disassembly

```asm
0x180016260  test    rcx, rcx
0x180016263  jz      locret_18001632D
0x180016269  push    rbp
0x18001626a  mov     rbp, rsp
0x18001626d  sub     rsp, 80h
0x180016274  mov     eax, cs:dword_180028048
0x18001627a  mov     r10, rdx
0x18001627d  mov     r9, rcx
0x180016280  cmp     eax, 5
0x180016283  jbe     loc_180016325
0x180016289  mov     rdx, 400000000000h
0x180016293  call    _tlgKeywordOn
0x180016298  test    al, al
0x18001629a  jz      loc_180016325
0x1800162a0  mov     eax, [r10+4]
0x1800162a4  lea     rdx, byte_1800243B1
0x1800162ab  mov     [rbp+arg_18], eax
0x1800162ae  mov     eax, [r10]
0x1800162b1  mov     [rbp+var_20], eax
0x1800162b4  mov     eax, [r9+27Ch]
0x1800162bb  mov     [rbp+var_1C], eax
0x1800162be  mov     eax, [r9+278h]
0x1800162c5  mov     [rbp+var_18], eax
0x1800162c8  mov     rax, [r9+268h]
0x1800162cf  mov     [rbp+var_10], rax
0x1800162d3  mov     eax, [r9+264h]
0x1800162da  mov     [rbp+var_14], eax
0x1800162dd  lea     rax, [rbp+arg_0]
0x1800162e1  mov     [rsp+80h+var_30], rax
0x1800162e6  lea     rax, [rbp+arg_18]
0x1800162ea  mov     [rsp+80h+var_38], rax
0x1800162ef  lea     rax, [rbp+var_20]
0x1800162f3  mov     [rsp+80h+var_40], rax
0x1800162f8  lea     rax, [rbp+var_1C]
0x1800162fc  mov     [rsp+80h+var_48], rax
0x180016301  lea     rax, [rbp+var_18]
0x180016305  mov     [rsp+80h+var_50], rax
0x18001630a  lea     rax, [rbp+var_10]
0x18001630e  mov     [rsp+80h+var_58], rax
0x180016313  lea     rax, [rbp+var_14]
0x180016317  mov     [rsp+80h+var_60], rax
0x18001631c  mov     [rbp+arg_0], r8d
0x180016320  call    ??$Write@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$07@@U1@U1@U1@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$07@@33333@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180016325  add     rsp, 80h
0x18001632c  pop     rbp
0x18001632d  retn
```
