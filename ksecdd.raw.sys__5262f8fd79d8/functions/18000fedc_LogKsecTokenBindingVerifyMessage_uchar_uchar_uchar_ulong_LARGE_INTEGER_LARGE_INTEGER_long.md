# LogKsecTokenBindingVerifyMessage(uchar,uchar,uchar,ulong,_LARGE_INTEGER,_LARGE_INTEGER,long)

- ea: `0x18000fedc`
- end: `0x18000ff8f`
- name: `?LogKsecTokenBindingVerifyMessage@@YAXEEEKT_LARGE_INTEGER@@0J@Z`
- size: `179`
- prototype: `void __fastcall(unsigned __int8, unsigned __int8, unsigned __int8, unsigned int, union _LARGE_INTEGER, union _LARGE_INTEGER, int)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1800237b0`

## callees

- `0x180001008`
- `0x1800010c4`
- `0x18000fedc`

## pseudocode

```c
void __fastcall LogKsecTokenBindingVerifyMessage(
        char a1,
        char a2,
        __int64 a3,
        __int64 a4,
        union _LARGE_INTEGER a5,
        union _LARGE_INTEGER a6,
        ULONG a7)
{
  int v7; // ecx
  int v8; // r8d
  int v9; // r9d
  __int64 v10; // r10
  int v11; // [rsp+50h] [rbp-10h] BYREF
  __int64 v12; // [rsp+58h] [rbp-8h] BYREF
  char v13; // [rsp+70h] [rbp+10h] BYREF
  char v14; // [rsp+78h] [rbp+18h] BYREF

  v14 = a2;
  v13 = a1;
  if ( (unsigned int)dword_1800191F0 > 5 )
  {
    if ( (unsigned __int8)tlgKeywordOn(&dword_1800191F0, 0x400000000000LL) )
    {
      a5.LowPart = a7;
      v12 = v10;
      v11 = v9;
      v14 = v8;
      v13 = 16;
      LOBYTE(a6.LowPart) = 0;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(
        v7,
        (unsigned int)&unk_180016B11,
        v8,
        v9,
        (__int64)&a6,
        (__int64)&v13,
        (__int64)&v14,
        (__int64)&v11,
        (__int64)&v12,
        (__int64)&a5);
    }
  }
}

```

## disassembly

```asm
0x18000fedc  mov     [rsp-8+arg_8], dl
0x18000fee0  mov     [rsp-8+arg_0], cl
0x18000fee4  push    rbp
0x18000fee5  mov     rbp, rsp
0x18000fee8  sub     rsp, 60h
0x18000feec  mov     rax, qword ptr [rbp+arg_28]
0x18000fef0  sub     rax, qword ptr [rbp+arg_20]
0x18000fef4  imul    rax, 3E8h
0x18000fefb  cqo
0x18000fefd  idiv    qword ptr cs:PerformanceFrequency
0x18000ff04  mov     r10, rax
0x18000ff07  mov     eax, cs:dword_1800191F0
0x18000ff0d  cmp     eax, 5
0x18000ff10  jbe     short loc_18000FF88
0x18000ff12  mov     rdx, 400000000000h
0x18000ff1c  lea     rcx, dword_1800191F0
0x18000ff23  call    _tlgKeywordOn
0x18000ff28  test    al, al
0x18000ff2a  jz      short loc_18000FF88
0x18000ff2c  mov     eax, [rbp+arg_30]
0x18000ff2f  lea     rdx, unk_180016B11
0x18000ff36  mov     dword ptr [rbp+arg_20], eax
0x18000ff39  lea     rax, [rbp+arg_20]
0x18000ff3d  mov     [rsp+60h+var_18], rax
0x18000ff42  lea     rax, [rbp+var_8]
0x18000ff46  mov     [rsp+60h+var_20], rax
0x18000ff4b  lea     rax, [rbp+var_10]
0x18000ff4f  mov     [rsp+60h+var_28], rax
0x18000ff54  lea     rax, [rbp+arg_8]
0x18000ff58  mov     [rsp+60h+var_30], rax
0x18000ff5d  lea     rax, [rbp+arg_0]
0x18000ff61  mov     [rsp+60h+var_38], rax
0x18000ff66  lea     rax, [rbp+arg_28]
0x18000ff6a  mov     [rsp+60h+var_40], rax
0x18000ff6f  mov     [rbp+var_8], r10
0x18000ff73  mov     [rbp+var_10], r9d
0x18000ff77  mov     [rbp+arg_8], r8b
0x18000ff7b  mov     [rbp+arg_0], 10h
0x18000ff7f  mov     byte ptr [rbp+arg_28], 0
0x18000ff83  call    ??$Write@U?$_tlgWrapperByVal@$00@@U1@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$07@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$00@@33AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$07@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<1> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &)
0x18000ff88  add     rsp, 60h
0x18000ff8c  pop     rbp
0x18000ff8d  retn
```
