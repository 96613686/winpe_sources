# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)

- ea: `0x180001514`
- end: `0x180001620`
- name: `??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@5@Z`
- size: `268`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, const unsigned __int16 **, __int64, const unsigned __int16 **, const unsigned __int16 **)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180008940`

## callees

- `0x1800013c8`
- `0x180001514`
- `0x1800022e0`

## pseudocode

```c
__int64 __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        const unsigned __int16 **a5,
        __int64 a6,
        const unsigned __int16 **a7,
        const unsigned __int16 **a8)
{
  __int64 v9; // rcx
  int v10; // r8d
  const unsigned __int16 *v11; // rdx
  __int64 v12; // rax
  int v13; // eax
  const unsigned __int16 *v14; // rdx
  __int64 v15; // rax
  const unsigned __int16 *v16; // rdx
  int v17; // ecx
  _BYTE v19[32]; // [rsp+30h] [rbp-39h] BYREF
  const unsigned __int16 *v20; // [rsp+50h] [rbp-19h]
  int v21; // [rsp+58h] [rbp-11h]
  int v22; // [rsp+5Ch] [rbp-Dh]
  __int64 v23; // [rsp+60h] [rbp-9h]
  __int64 v24; // [rsp+68h] [rbp-1h]
  const unsigned __int16 *v25; // [rsp+70h] [rbp+7h]
  int v26; // [rsp+78h] [rbp+Fh]
  int v27; // [rsp+7Ch] [rbp+13h]
  const unsigned __int16 *v28; // [rsp+80h] [rbp+17h]
  int v29; // [rsp+88h] [rbp+1Fh]
  int v30; // [rsp+8Ch] [rbp+23h]

  v9 = -1;
  v10 = 1;
  v11 = *a8;
  if ( *a8 )
  {
    v12 = -1;
    do
      ++v12;
    while ( *((_BYTE *)v11 + v12) );
    v13 = v12 + 1;
  }
  else
  {
    v11 = &word_180021D5A;
    v13 = 1;
  }
  v29 = v13;
  v28 = v11;
  v30 = 0;
  v14 = *a7;
  if ( *a7 )
  {
    v15 = -1;
    do
      ++v15;
    while ( *((_BYTE *)v14 + v15) );
    v10 = v15 + 1;
  }
  else
  {
    v14 = &word_180021D5A;
  }
  v23 = a6;
  v25 = v14;
  v26 = v10;
  v27 = 0;
  v16 = *a5;
  v24 = 4;
  if ( v16 )
  {
    do
      ++v9;
    while ( v16[v9] );
    v17 = 2 * v9 + 2;
  }
  else
  {
    v16 = &dword_18002237C;
    v17 = 2;
  }
  v20 = v16;
  v21 = v17;
  v22 = 0;
  return tlgWriteTransfer_EventWriteTransfer(&dword_18002B0C0, a2, 0, 0, 6, v19);
}

```

## disassembly

```asm
0x180001514  push    rbp
0x180001516  lea     rbp, [rsp-37h]
0x18000151b  sub     rsp, 0A0h
0x180001522  mov     rax, cs:__security_cookie
0x180001529  xor     rax, rsp
0x18000152c  mov     [rbp+37h+var_10], rax
0x180001530  mov     rax, [rbp+37h+arg_38]
0x180001534  mov     r10, rdx
0x180001537  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18000153b  xor     r9d, r9d
0x18000153e  mov     r8d, 1
0x180001544  mov     rdx, [rax]
0x180001547  test    rdx, rdx
0x18000154a  jz      short loc_18000155C
0x18000154c  mov     rax, rcx
0x18000154f  inc     rax
0x180001552  cmp     [rdx+rax], r9b
0x180001556  jnz     short loc_18000154F
0x180001558  inc     eax
0x18000155a  jmp     short loc_180001566
0x18000155c  lea     rdx, word_180021D5A
0x180001563  mov     eax, r8d
0x180001566  mov     [rbp+37h+var_18], eax
0x180001569  mov     rax, [rbp+37h+arg_30]
0x18000156d  mov     [rbp+37h+var_20], rdx
0x180001571  mov     [rbp+37h+var_14], r9d
0x180001575  mov     rdx, [rax]
0x180001578  test    rdx, rdx
0x18000157b  jz      short loc_18000158F
0x18000157d  mov     rax, rcx
0x180001580  inc     rax
0x180001583  cmp     [rdx+rax], r9b
0x180001587  jnz     short loc_180001580
0x180001589  lea     r8d, [rax+1]
0x18000158d  jmp     short loc_180001596
0x18000158f  lea     rdx, word_180021D5A
0x180001596  mov     rax, [rbp+37h+arg_28]
0x18000159a  mov     [rbp+37h+var_40], rax
0x18000159e  mov     rax, [rbp+37h+arg_20]
0x1800015a2  mov     [rbp+37h+var_30], rdx
0x1800015a6  mov     [rbp+37h+var_28], r8d
0x1800015aa  mov     [rbp+37h+var_24], r9d
0x1800015ae  mov     rdx, [rax]
0x1800015b1  mov     [rbp+37h+var_38], 4
0x1800015b9  test    rdx, rdx
0x1800015bc  jz      short loc_1800015D1
0x1800015be  inc     rcx
0x1800015c1  cmp     [rdx+rcx*2], r9w
0x1800015c6  jnz     short loc_1800015BE
0x1800015c8  lea     ecx, ds:2[rcx*2]
0x1800015cf  jmp     short loc_1800015DD
0x1800015d1  lea     rdx, dword_18002237C
0x1800015d8  mov     ecx, 2
0x1800015dd  lea     rax, [rbp+37h+var_70]
0x1800015e1  mov     [rbp+37h+var_50], rdx
0x1800015e5  mov     [rbp+37h+var_48], ecx
0x1800015e8  xor     r8d, r8d
0x1800015eb  mov     [rsp+0A0h+var_78], rax
0x1800015f0  lea     rcx, dword_18002B0C0
0x1800015f7  mov     rdx, r10
0x1800015fa  mov     [rsp+0A0h+var_80], 6
0x180001602  mov     [rbp+37h+var_44], r9d
0x180001606  call    _tlgWriteTransfer_EventWriteTransfer
0x18000160b  mov     rcx, [rbp+37h+var_10]
0x18000160f  xor     rcx, rsp; StackCookie
0x180001612  call    __security_check_cookie
0x180001617  add     rsp, 0A0h
0x18000161e  pop     rbp
0x18000161f  retn
```
