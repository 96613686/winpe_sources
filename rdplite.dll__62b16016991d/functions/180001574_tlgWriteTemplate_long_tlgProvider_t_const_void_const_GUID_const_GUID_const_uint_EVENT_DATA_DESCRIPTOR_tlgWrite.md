# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<char> const &,_tlgWrapperByRef<16> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)

- ea: `0x180001574`
- end: `0x180001698`
- name: `??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByRef@$0BA@@@U1@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByRef@$0BA@@@3AEBU?$_tlgWrapperByVal@$03@@@Z`
- size: `292`
- prototype: ``
- caller_count: `8`
- callee_count: `3`
- tags: ``

## callers

- `0x18000c410`
- `0x18000cbc0`
- `0x180019f08`
- `0x18001a5f8`
- `0x18001e824`
- `0x18001ec84`
- `0x1800224e4`
- `0x1800227a0`

## callees

- `0x180001448`
- `0x180001574`
- `0x1800036f0`

## pseudocode

```c
ULONG __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
        __int64 a1,
        unsigned __int8 *a2,
        __int64 a3,
        __int64 a4,
        const unsigned __int16 **a5,
        __int64 a6,
        const unsigned __int16 **a7,
        __int64 *a8,
        const unsigned __int16 **a9,
        __int64 a10)
{
  __int64 v12; // rdx
  int v13; // r8d
  const unsigned __int16 *v14; // rcx
  __int64 v15; // rax
  int v16; // eax
  const unsigned __int16 *v17; // rcx
  __int64 v18; // rax
  int v19; // eax
  const unsigned __int16 *v20; // rcx
  struct _EVENT_DATA_DESCRIPTOR v22; // [rsp+30h] [rbp-69h] BYREF
  const unsigned __int16 *v23; // [rsp+50h] [rbp-49h]
  int v24; // [rsp+58h] [rbp-41h]
  int v25; // [rsp+5Ch] [rbp-3Dh]
  __int64 v26; // [rsp+60h] [rbp-39h]
  __int64 v27; // [rsp+68h] [rbp-31h]
  const unsigned __int16 *v28; // [rsp+70h] [rbp-29h]
  int v29; // [rsp+78h] [rbp-21h]
  int v30; // [rsp+7Ch] [rbp-1Dh]
  __int64 v31; // [rsp+80h] [rbp-19h]
  __int64 v32; // [rsp+88h] [rbp-11h]
  const unsigned __int16 *v33; // [rsp+90h] [rbp-9h]
  int v34; // [rsp+98h] [rbp-1h]
  int v35; // [rsp+9Ch] [rbp+3h]
  __int64 v36; // [rsp+A0h] [rbp+7h]
  __int64 v37; // [rsp+A8h] [rbp+Fh]

  v36 = a10;
  v12 = -1;
  v37 = 4;
  v13 = 1;
  v14 = *a9;
  if ( *a9 )
  {
    v15 = -1;
    do
      ++v15;
    while ( *((_BYTE *)v14 + v15) );
    v16 = v15 + 1;
  }
  else
  {
    v14 = &qword_18002D6C0;
    v16 = 1;
  }
  v34 = v16;
  v33 = v14;
  v35 = 0;
  v32 = 16;
  v31 = *a8;
  v17 = *a7;
  if ( *a7 )
  {
    v18 = -1;
    do
      ++v18;
    while ( *((_BYTE *)v17 + v18) );
    v19 = v18 + 1;
  }
  else
  {
    v17 = &qword_18002D6C0;
    v19 = 1;
  }
  v29 = v19;
  v26 = a6;
  v28 = v17;
  v30 = 0;
  v27 = 8;
  v20 = *a5;
  if ( *a5 )
  {
    do
      ++v12;
    while ( *((_BYTE *)v20 + v12) );
    v13 = v12 + 1;
  }
  else
  {
    v20 = &qword_18002D6C0;
  }
  v23 = v20;
  v24 = v13;
  v25 = 0;
  return tlgWriteTransfer_EventWriteTransfer(a1, a2, 0, 0, 8u, &v22);
}

```

## disassembly

```asm
0x180001574  push    rbp
0x180001576  lea     rbp, [rsp-27h]
0x18000157b  sub     rsp, 0C0h
0x180001582  mov     rax, cs:__security_cookie
0x180001589  xor     rax, rsp
0x18000158c  mov     [rbp+27h+var_10], rax
0x180001590  mov     rax, [rbp+27h+arg_48]
0x180001594  xor     r9d, r9d
0x180001597  mov     [rbp+27h+var_20], rax
0x18000159b  mov     r11, rdx
0x18000159e  mov     rax, [rbp+27h+arg_40]
0x1800015a2  mov     r10, rcx
0x1800015a5  or      rdx, 0FFFFFFFFFFFFFFFFh
0x1800015a9  mov     [rbp+27h+var_18], 4
0x1800015b1  lea     r8d, [r9+1]
0x1800015b5  mov     rcx, [rax]
0x1800015b8  test    rcx, rcx
0x1800015bb  jz      short loc_1800015CD
0x1800015bd  mov     rax, rdx
0x1800015c0  inc     rax
0x1800015c3  cmp     [rcx+rax], r9b
0x1800015c7  jnz     short loc_1800015C0
0x1800015c9  inc     eax
0x1800015cb  jmp     short loc_1800015D7
0x1800015cd  lea     rcx, qword_18002D6C0
0x1800015d4  mov     eax, r8d
0x1800015d7  mov     [rbp+27h+var_28], eax
0x1800015da  mov     rax, [rbp+27h+arg_38]
0x1800015de  mov     [rbp+27h+var_30], rcx
0x1800015e2  mov     [rbp+27h+var_24], r9d
0x1800015e6  mov     [rbp+27h+var_38], 10h
0x1800015ee  mov     rcx, [rax]
0x1800015f1  mov     rax, [rbp+27h+arg_30]
0x1800015f5  mov     [rbp+27h+var_40], rcx
0x1800015f9  mov     rcx, [rax]
0x1800015fc  test    rcx, rcx
0x1800015ff  jz      short loc_180001611
0x180001601  mov     rax, rdx
0x180001604  inc     rax
0x180001607  cmp     [rcx+rax], r9b
0x18000160b  jnz     short loc_180001604
0x18000160d  inc     eax
0x18000160f  jmp     short loc_18000161B
0x180001611  lea     rcx, qword_18002D6C0
0x180001618  mov     eax, r8d
0x18000161b  mov     [rbp+27h+var_48], eax
0x18000161e  mov     rax, [rbp+27h+arg_28]
0x180001622  mov     [rbp+27h+var_60], rax
0x180001626  mov     rax, [rbp+27h+arg_20]
0x18000162a  mov     [rbp+27h+var_50], rcx
0x18000162e  mov     [rbp+27h+var_44], r9d
0x180001632  mov     [rbp+27h+var_58], 8
0x18000163a  mov     rcx, [rax]
0x18000163d  test    rcx, rcx
0x180001640  jz      short loc_180001651
0x180001642  inc     rdx
0x180001645  cmp     [rcx+rdx], r9b
0x180001649  jnz     short loc_180001642
0x18000164b  lea     r8d, [rdx+1]
0x18000164f  jmp     short loc_180001658
0x180001651  lea     rcx, qword_18002D6C0
0x180001658  lea     rax, [rbp+27h+var_90]
0x18000165c  mov     [rbp+27h+var_70], rcx
0x180001660  mov     [rbp+27h+var_68], r8d
0x180001664  mov     rdx, r11
0x180001667  mov     [rsp+0C0h+var_98], rax
0x18000166c  xor     r8d, r8d
0x18000166f  mov     rcx, r10
0x180001672  mov     [rsp+0C0h+var_A0], 8
0x18000167a  mov     [rbp+27h+var_64], r9d
0x18000167e  call    _tlgWriteTransfer_EventWriteTransfer
0x180001683  mov     rcx, [rbp+27h+var_10]
0x180001687  xor     rcx, rsp; StackCookie
0x18000168a  call    __security_check_cookie
0x18000168f  add     rsp, 0C0h
0x180001696  pop     rbp
0x180001697  retn
```
