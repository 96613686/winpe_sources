# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &)

- ea: `0x140001604`
- end: `0x1400016f6`
- name: `??$Write@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U1@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@43AEBU?$_tlgWrapperByVal@$07@@@Z`
- size: `242`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x140005bd4`
- `0x1400081c4`
- `0x14000a3c4`

## callees

- `0x140001604`
- `0x140001840`
- `0x140019610`

## pseudocode

```c
ULONG __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
        __int64 a1,
        unsigned __int8 *a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        const unsigned __int16 **a6,
        const unsigned __int16 **a7,
        __int64 a8,
        __int64 a9)
{
  __int64 v10; // rcx
  int v11; // r8d
  const unsigned __int16 *v12; // rdx
  __int64 v13; // rax
  int v14; // eax
  const unsigned __int16 *v15; // rdx
  struct _EVENT_DATA_DESCRIPTOR v17; // [rsp+30h] [rbp-51h] BYREF
  __int64 v18; // [rsp+50h] [rbp-31h]
  __int64 v19; // [rsp+58h] [rbp-29h]
  const unsigned __int16 *v20; // [rsp+60h] [rbp-21h]
  int v21; // [rsp+68h] [rbp-19h]
  int v22; // [rsp+6Ch] [rbp-15h]
  const unsigned __int16 *v23; // [rsp+70h] [rbp-11h]
  int v24; // [rsp+78h] [rbp-9h]
  int v25; // [rsp+7Ch] [rbp-5h]
  __int64 v26; // [rsp+80h] [rbp-1h]
  __int64 v27; // [rsp+88h] [rbp+7h]
  __int64 v28; // [rsp+90h] [rbp+Fh]
  __int64 v29; // [rsp+98h] [rbp+17h]

  v28 = a9;
  v10 = -1;
  v26 = a8;
  v11 = 1;
  v29 = 8;
  v27 = 4;
  v12 = *a7;
  if ( *a7 )
  {
    v13 = -1;
    do
      ++v13;
    while ( *((_BYTE *)v12 + v13) );
    v14 = v13 + 1;
  }
  else
  {
    v12 = &word_14001D5D2;
    v14 = 1;
  }
  v24 = v14;
  v23 = v12;
  v25 = 0;
  v15 = *a6;
  if ( *a6 )
  {
    do
      ++v10;
    while ( *((_BYTE *)v15 + v10) );
    v11 = v10 + 1;
  }
  else
  {
    v15 = &word_14001D5D2;
  }
  v18 = a5;
  v20 = v15;
  v21 = v11;
  v22 = 0;
  v19 = 4;
  return tlgWriteTransfer_EventWriteTransfer((__int64)&dword_140028000, a2, 0, 0, 7u, &v17);
}

```

## disassembly

```asm
0x140001604  push    rbp
0x140001606  lea     rbp, [rsp-2Fh]
0x14000160b  sub     rsp, 0B0h
0x140001612  mov     rax, cs:__security_cookie
0x140001619  xor     rax, rsp
0x14000161c  mov     [rbp+2Fh+var_10], rax
0x140001620  mov     rax, [rbp+2Fh+arg_40]
0x140001624  xor     r9d, r9d
0x140001627  mov     [rbp+2Fh+var_20], rax
0x14000162b  mov     r10, rdx
0x14000162e  mov     rax, [rbp+2Fh+arg_38]
0x140001632  or      rcx, 0FFFFFFFFFFFFFFFFh
0x140001636  mov     [rbp+2Fh+var_30], rax
0x14000163a  mov     rax, [rbp+2Fh+arg_30]
0x14000163e  lea     r8d, [r9+1]
0x140001642  mov     [rbp+2Fh+var_18], 8
0x14000164a  mov     [rbp+2Fh+var_28], 4
0x140001652  mov     rdx, [rax]
0x140001655  test    rdx, rdx
0x140001658  jz      short loc_14000166A
0x14000165a  mov     rax, rcx
0x14000165d  inc     rax
0x140001660  cmp     [rdx+rax], r9b
0x140001664  jnz     short loc_14000165D
0x140001666  inc     eax
0x140001668  jmp     short loc_140001674
0x14000166a  lea     rdx, word_14001D5D2
0x140001671  mov     eax, r8d
0x140001674  mov     [rbp+2Fh+var_38], eax
0x140001677  mov     rax, [rbp+2Fh+arg_28]
0x14000167b  mov     [rbp+2Fh+var_40], rdx
0x14000167f  mov     [rbp+2Fh+var_34], r9d
0x140001683  mov     rdx, [rax]
0x140001686  test    rdx, rdx
0x140001689  jz      short loc_14000169A
0x14000168b  inc     rcx
0x14000168e  cmp     [rdx+rcx], r9b
0x140001692  jnz     short loc_14000168B
0x140001694  lea     r8d, [rcx+1]
0x140001698  jmp     short loc_1400016A1
0x14000169a  lea     rdx, word_14001D5D2
0x1400016a1  mov     rax, [rbp+2Fh+arg_20]
0x1400016a5  lea     rcx, dword_140028000
0x1400016ac  mov     [rbp+2Fh+var_60], rax
0x1400016b0  lea     rax, [rbp+2Fh+var_80]
0x1400016b4  mov     [rbp+2Fh+var_50], rdx
0x1400016b8  mov     rdx, r10
0x1400016bb  mov     [rbp+2Fh+var_48], r8d
0x1400016bf  xor     r8d, r8d
0x1400016c2  mov     [rsp+0B0h+var_88], rax
0x1400016c7  mov     [rsp+0B0h+var_90], 7
0x1400016cf  mov     [rbp+2Fh+var_44], r9d
0x1400016d3  mov     [rbp+2Fh+var_58], 4
0x1400016db  call    _tlgWriteTransfer_EventWriteTransfer
0x1400016e0  mov     rcx, [rbp+2Fh+var_10]
0x1400016e4  xor     rcx, rsp; StackCookie
0x1400016e7  call    __security_check_cookie
0x1400016ec  add     rsp, 0B0h
0x1400016f3  pop     rbp
0x1400016f4  retn
```
