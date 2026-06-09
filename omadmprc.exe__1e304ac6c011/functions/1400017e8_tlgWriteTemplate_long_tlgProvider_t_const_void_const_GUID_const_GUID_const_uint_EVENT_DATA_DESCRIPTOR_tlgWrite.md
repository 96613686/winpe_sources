# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &)

- ea: `0x1400017e8`
- end: `0x140001908`
- name: `??$Write@U?$_tlgWrapperByVal@$07@@U1@U1@U1@U?$_tlgWrapSz@G@@U1@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@333AEBU?$_tlgWrapSz@G@@34@Z`
- size: `288`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x14001490c`

## callees

- `0x140001090`
- `0x1400017e8`
- `0x140015690`

## pseudocode

```c
ULONG __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>>(
        __int64 a1,
        unsigned __int8 *a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        __int64 a7,
        __int64 a8,
        __int64 **a9,
        __int64 a10,
        __int64 **a11)
{
  __int64 v12; // rcx
  int v13; // r8d
  __int64 *v14; // rdx
  __int64 v15; // rax
  int v16; // eax
  __int64 *v17; // rdx
  struct _EVENT_DATA_DESCRIPTOR v19; // [rsp+30h] [rbp-81h] BYREF
  __int64 v20; // [rsp+50h] [rbp-61h]
  __int64 v21; // [rsp+58h] [rbp-59h]
  __int64 v22; // [rsp+60h] [rbp-51h]
  __int64 v23; // [rsp+68h] [rbp-49h]
  __int64 v24; // [rsp+70h] [rbp-41h]
  __int64 v25; // [rsp+78h] [rbp-39h]
  __int64 v26; // [rsp+80h] [rbp-31h]
  __int64 v27; // [rsp+88h] [rbp-29h]
  __int64 *v28; // [rsp+90h] [rbp-21h]
  int v29; // [rsp+98h] [rbp-19h]
  int v30; // [rsp+9Ch] [rbp-15h]
  __int64 v31; // [rsp+A0h] [rbp-11h]
  __int64 v32; // [rsp+A8h] [rbp-9h]
  __int64 *v33; // [rsp+B0h] [rbp-1h]
  int v34; // [rsp+B8h] [rbp+7h]
  int v35; // [rsp+BCh] [rbp+Bh]

  v12 = -1;
  v13 = 2;
  v14 = *a11;
  if ( *a11 )
  {
    v15 = -1;
    do
      ++v15;
    while ( *((_WORD *)v14 + v15) );
    v16 = 2 * v15 + 2;
  }
  else
  {
    v14 = &qword_14001A798;
    v16 = 2;
  }
  v34 = v16;
  v31 = a10;
  v33 = v14;
  v35 = 0;
  v32 = 8;
  v17 = *a9;
  if ( *a9 )
  {
    do
      ++v12;
    while ( *((_WORD *)v17 + v12) );
    v13 = 2 * v12 + 2;
  }
  else
  {
    v17 = &qword_14001A798;
  }
  v26 = a8;
  v24 = a7;
  v22 = a6;
  v20 = a5;
  v28 = v17;
  v29 = v13;
  v30 = 0;
  v27 = 8;
  v25 = 8;
  v23 = 8;
  v21 = 8;
  return tlgWriteTransfer_EventWriteTransfer((__int64)&dword_140023000, a2, 0, 0, 9u, &v19);
}

```

## disassembly

```asm
0x1400017e8  push    rbp
0x1400017ea  lea     rbp, [rsp-1Fh]
0x1400017ef  sub     rsp, 0D0h
0x1400017f6  mov     rax, cs:__security_cookie
0x1400017fd  xor     rax, rsp
0x140001800  mov     [rbp+1Fh+var_10], rax
0x140001804  mov     rax, [rbp+1Fh+arg_50]
0x140001808  mov     r10, rdx
0x14000180b  or      rcx, 0FFFFFFFFFFFFFFFFh
0x14000180f  xor     r9d, r9d
0x140001812  mov     r8d, 2
0x140001818  mov     rdx, [rax]
0x14000181b  test    rdx, rdx
0x14000181e  jz      short loc_140001836
0x140001820  mov     rax, rcx
0x140001823  inc     rax
0x140001826  cmp     [rdx+rax*2], r9w
0x14000182b  jnz     short loc_140001823
0x14000182d  lea     eax, ds:2[rax*2]
0x140001834  jmp     short loc_140001840
0x140001836  lea     rdx, qword_14001A798
0x14000183d  mov     eax, r8d
0x140001840  mov     [rbp+1Fh+var_18], eax
0x140001843  mov     rax, [rbp+1Fh+arg_48]
0x140001847  mov     [rbp+1Fh+var_30], rax
0x14000184b  mov     rax, [rbp+1Fh+arg_40]
0x14000184f  mov     [rbp+1Fh+var_20], rdx
0x140001853  mov     [rbp+1Fh+var_14], r9d
0x140001857  mov     [rbp+1Fh+var_28], 8
0x14000185f  mov     rdx, [rax]
0x140001862  test    rdx, rdx
0x140001865  jz      short loc_14000187B
0x140001867  inc     rcx
0x14000186a  cmp     [rdx+rcx*2], r9w
0x14000186f  jnz     short loc_140001867
0x140001871  lea     r8d, ds:2[rcx*2]
0x140001879  jmp     short loc_140001882
0x14000187b  lea     rdx, qword_14001A798
0x140001882  mov     rax, [rbp+1Fh+arg_38]
0x140001886  lea     rcx, dword_140023000
0x14000188d  mov     [rbp+1Fh+var_50], rax
0x140001891  mov     rax, [rbp+1Fh+arg_30]
0x140001895  mov     [rbp+1Fh+var_60], rax
0x140001899  mov     rax, [rbp+1Fh+arg_28]
0x14000189d  mov     [rbp+1Fh+var_70], rax
0x1400018a1  mov     rax, [rbp+1Fh+arg_20]
0x1400018a5  mov     [rbp+1Fh+var_80], rax
0x1400018a9  lea     rax, [rsp+0D0h+var_A0]
0x1400018ae  mov     [rbp+1Fh+var_40], rdx
0x1400018b2  mov     rdx, r10
0x1400018b5  mov     [rbp+1Fh+var_38], r8d
0x1400018b9  xor     r8d, r8d
0x1400018bc  mov     [rsp+0D0h+var_A8], rax
0x1400018c1  mov     [rsp+0D0h+var_B0], 9
0x1400018c9  mov     [rbp+1Fh+var_34], r9d
0x1400018cd  mov     [rbp+1Fh+var_48], 8
0x1400018d5  mov     [rbp+1Fh+var_58], 8
0x1400018dd  mov     [rbp+1Fh+var_68], 8
0x1400018e5  mov     [rbp+1Fh+var_78], 8
0x1400018ed  call    _tlgWriteTransfer_EventWriteTransfer
0x1400018f2  mov     rcx, [rbp+1Fh+var_10]
0x1400018f6  xor     rcx, rsp; StackCookie
0x1400018f9  call    __security_check_cookie
0x1400018fe  add     rsp, 0D0h
0x140001905  pop     rbp
0x140001906  retn
```
