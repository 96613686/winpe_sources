# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &)

- ea: `0x14000197c`
- end: `0x140001a36`
- name: `??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4AEBU?$_tlgWrapSz@G@@@Z`
- size: `186`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64 **)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x14000b6e4`
- `0x14000b93c`

## callees

- `0x14000197c`
- `0x140002318`
- `0x140002f40`

## pseudocode

```c
__int64 __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>>(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        __int64 a7,
        __int64 **a8)
{
  __int64 *v9; // rcx
  __int64 v10; // rax
  int v11; // eax
  _BYTE v13[32]; // [rsp+30h] [rbp-39h] BYREF
  __int64 v14; // [rsp+50h] [rbp-19h]
  __int64 v15; // [rsp+58h] [rbp-11h]
  __int64 v16; // [rsp+60h] [rbp-9h]
  __int64 v17; // [rsp+68h] [rbp-1h]
  __int64 v18; // [rsp+70h] [rbp+7h]
  __int64 v19; // [rsp+78h] [rbp+Fh]
  __int64 *v20; // [rsp+80h] [rbp+17h]
  int v21; // [rsp+88h] [rbp+1Fh]
  int v22; // [rsp+8Ch] [rbp+23h]

  v9 = *a8;
  if ( *a8 )
  {
    v10 = -1;
    do
      ++v10;
    while ( *((_WORD *)v9 + v10) );
    v11 = 2 * v10 + 2;
  }
  else
  {
    v9 = &qword_14001C2F8;
    v11 = 2;
  }
  v21 = v11;
  v18 = a7;
  v16 = a6;
  v14 = a5;
  v20 = v9;
  v22 = 0;
  v19 = 4;
  v17 = 4;
  v15 = 8;
  return tlgWriteTransfer_EventWriteTransfer(a1, a2, a3, 0, 6, v13);
}

```

## disassembly

```asm
0x14000197c  push    rbp
0x14000197e  lea     rbp, [rsp-37h]
0x140001983  sub     rsp, 0A0h
0x14000198a  mov     rax, cs:__security_cookie
0x140001991  xor     rax, rsp
0x140001994  mov     [rbp+37h+var_10], rax
0x140001998  mov     rax, [rbp+37h+arg_38]
0x14000199c  mov     r10, rcx
0x14000199f  xor     r9d, r9d
0x1400019a2  mov     rcx, [rax]
0x1400019a5  test    rcx, rcx
0x1400019a8  jz      short loc_1400019C1
0x1400019aa  or      rax, 0FFFFFFFFFFFFFFFFh
0x1400019ae  inc     rax
0x1400019b1  cmp     [rcx+rax*2], r9w
0x1400019b6  jnz     short loc_1400019AE
0x1400019b8  lea     eax, ds:2[rax*2]
0x1400019bf  jmp     short loc_1400019CD
0x1400019c1  lea     rcx, qword_14001C2F8
0x1400019c8  mov     eax, 2
0x1400019cd  mov     [rbp+37h+var_18], eax
0x1400019d0  mov     rax, [rbp+37h+arg_30]
0x1400019d4  mov     [rbp+37h+var_30], rax
0x1400019d8  mov     rax, [rbp+37h+arg_28]
0x1400019dc  mov     [rbp+37h+var_40], rax
0x1400019e0  mov     rax, [rbp+37h+arg_20]
0x1400019e4  mov     [rbp+37h+var_50], rax
0x1400019e8  lea     rax, [rbp+37h+var_70]
0x1400019ec  mov     [rbp+37h+var_20], rcx
0x1400019f0  mov     rcx, r10
0x1400019f3  mov     [rsp+0A0h+var_78], rax
0x1400019f8  mov     [rsp+0A0h+var_80], 6
0x140001a00  mov     [rbp+37h+var_14], r9d
0x140001a04  mov     [rbp+37h+var_28], 4
0x140001a0c  mov     [rbp+37h+var_38], 4
0x140001a14  mov     [rbp+37h+var_48], 8
0x140001a1c  call    _tlgWriteTransfer_EventWriteTransfer
0x140001a21  mov     rcx, [rbp+37h+var_10]
0x140001a25  xor     rcx, rsp; StackCookie
0x140001a28  call    __security_check_cookie
0x140001a2d  add     rsp, 0A0h
0x140001a34  pop     rbp
0x140001a35  retn
```
