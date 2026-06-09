# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)

- ea: `0x140001424`
- end: `0x140001510`
- name: `??$Write@U?$_tlgWrapSz@G@@U1@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@3AEBU?$_tlgWrapperByVal@$03@@4@Z`
- size: `236`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x140006e18`

## callees

- `0x1400011ac`
- `0x140001424`
- `0x14000a370`

## pseudocode

```c
ULONG __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        __int64 a1,
        unsigned __int8 *a2,
        __int64 a3,
        __int64 a4,
        int **a5,
        int **a6,
        __int64 a7,
        __int64 a8)
{
  __int64 v9; // rcx
  int v10; // r8d
  int *v11; // rdx
  __int64 v12; // rax
  int v13; // eax
  int *v14; // rdx
  struct _EVENT_DATA_DESCRIPTOR v16; // [rsp+30h] [rbp-39h] BYREF
  int *v17; // [rsp+50h] [rbp-19h]
  int v18; // [rsp+58h] [rbp-11h]
  int v19; // [rsp+5Ch] [rbp-Dh]
  int *v20; // [rsp+60h] [rbp-9h]
  int v21; // [rsp+68h] [rbp-1h]
  int v22; // [rsp+6Ch] [rbp+3h]
  __int64 v23; // [rsp+70h] [rbp+7h]
  __int64 v24; // [rsp+78h] [rbp+Fh]
  __int64 v25; // [rsp+80h] [rbp+17h]
  __int64 v26; // [rsp+88h] [rbp+1Fh]

  v25 = a8;
  v9 = -1;
  v23 = a7;
  v10 = 2;
  v26 = 4;
  v24 = 4;
  v11 = *a6;
  if ( *a6 )
  {
    v12 = -1;
    do
      ++v12;
    while ( *((_WORD *)v11 + v12) );
    v13 = 2 * v12 + 2;
  }
  else
  {
    v11 = &dword_14000C834;
    v13 = 2;
  }
  v21 = v13;
  v20 = v11;
  v22 = 0;
  v14 = *a5;
  if ( *a5 )
  {
    do
      ++v9;
    while ( *((_WORD *)v14 + v9) );
    v10 = 2 * v9 + 2;
  }
  else
  {
    v14 = &dword_14000C834;
  }
  v17 = v14;
  v18 = v10;
  v19 = 0;
  return tlgWriteTransfer_EventWriteTransfer((__int64)&dword_140010000, a2, 0, 0, 6u, &v16);
}

```

## disassembly

```asm
0x140001424  push    rbp
0x140001426  lea     rbp, [rsp-37h]
0x14000142b  sub     rsp, 0A0h
0x140001432  mov     rax, cs:__security_cookie
0x140001439  xor     rax, rsp
0x14000143c  mov     [rbp+37h+var_10], rax
0x140001440  mov     rax, [rbp+37h+arg_38]
0x140001444  xor     r9d, r9d
0x140001447  mov     [rbp+37h+var_20], rax
0x14000144b  mov     r10, rdx
0x14000144e  mov     rax, [rbp+37h+arg_30]
0x140001452  or      rcx, 0FFFFFFFFFFFFFFFFh
0x140001456  mov     [rbp+37h+var_30], rax
0x14000145a  mov     rax, [rbp+37h+arg_28]
0x14000145e  lea     r8d, [r9+2]
0x140001462  mov     [rbp+37h+var_18], 4
0x14000146a  mov     [rbp+37h+var_28], 4
0x140001472  mov     rdx, [rax]
0x140001475  test    rdx, rdx
0x140001478  jz      short loc_140001490
0x14000147a  mov     rax, rcx
0x14000147d  inc     rax
0x140001480  cmp     [rdx+rax*2], r9w
0x140001485  jnz     short loc_14000147D
0x140001487  lea     eax, ds:2[rax*2]
0x14000148e  jmp     short loc_14000149A
0x140001490  lea     rdx, dword_14000C834
0x140001497  mov     eax, r8d
0x14000149a  mov     [rbp+37h+var_38], eax
0x14000149d  mov     rax, [rbp+37h+arg_20]
0x1400014a1  mov     [rbp+37h+var_40], rdx
0x1400014a5  mov     [rbp+37h+var_34], r9d
0x1400014a9  mov     rdx, [rax]
0x1400014ac  test    rdx, rdx
0x1400014af  jz      short loc_1400014C5
0x1400014b1  inc     rcx
0x1400014b4  cmp     [rdx+rcx*2], r9w
0x1400014b9  jnz     short loc_1400014B1
0x1400014bb  lea     r8d, ds:2[rcx*2]
0x1400014c3  jmp     short loc_1400014CC
0x1400014c5  lea     rdx, dword_14000C834
0x1400014cc  lea     rax, [rbp+37h+var_70]
0x1400014d0  mov     [rbp+37h+var_50], rdx
0x1400014d4  mov     [rbp+37h+var_48], r8d
0x1400014d8  lea     rcx, dword_140010000
0x1400014df  mov     [rsp+0A0h+var_78], rax
0x1400014e4  xor     r8d, r8d
0x1400014e7  mov     rdx, r10
0x1400014ea  mov     [rsp+0A0h+var_80], 6
0x1400014f2  mov     [rbp+37h+var_44], r9d
0x1400014f6  call    _tlgWriteTransfer_EventWriteTransfer
0x1400014fb  mov     rcx, [rbp+37h+var_10]
0x1400014ff  xor     rcx, rsp; StackCookie
0x140001502  call    __security_check_cookie
0x140001507  add     rsp, 0A0h
0x14000150e  pop     rbp
0x14000150f  retn
```
