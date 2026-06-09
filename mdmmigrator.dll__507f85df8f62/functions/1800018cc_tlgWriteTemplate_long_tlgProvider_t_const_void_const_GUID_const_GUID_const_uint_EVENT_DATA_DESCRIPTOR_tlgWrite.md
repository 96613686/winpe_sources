# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)

- ea: `0x1800018cc`
- end: `0x1800019dd`
- name: `??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@3@Z`
- size: `273`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, const unsigned __int16 **, __int64, const unsigned __int16 **, const unsigned __int16 **)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x18000c740`
- `0x18000f5c4`

## callees

- `0x1800013c8`
- `0x1800018cc`
- `0x1800022e0`

## pseudocode

```c
__int64 __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
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
  int v16; // eax
  const unsigned __int16 *v17; // rdx
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
  v10 = 2;
  v11 = *a8;
  if ( *a8 )
  {
    v12 = -1;
    do
      ++v12;
    while ( v11[v12] );
    v13 = 2 * v12 + 2;
  }
  else
  {
    v11 = &dword_18002237C;
    v13 = 2;
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
    v16 = v15 + 1;
  }
  else
  {
    v14 = &word_180021D5A;
    v16 = 1;
  }
  v26 = v16;
  v23 = a6;
  v25 = v14;
  v27 = 0;
  v24 = 4;
  v17 = *a5;
  if ( *a5 )
  {
    do
      ++v9;
    while ( v17[v9] );
    v10 = 2 * v9 + 2;
  }
  else
  {
    v17 = &dword_18002237C;
  }
  v20 = v17;
  v21 = v10;
  v22 = 0;
  return tlgWriteTransfer_EventWriteTransfer(&dword_18002B0C0, a2, 0, 0, 6, v19);
}

```

## disassembly

```asm
0x1800018cc  push    rbp
0x1800018ce  lea     rbp, [rsp-37h]
0x1800018d3  sub     rsp, 0A0h
0x1800018da  mov     rax, cs:__security_cookie
0x1800018e1  xor     rax, rsp
0x1800018e4  mov     [rbp+37h+var_10], rax
0x1800018e8  mov     rax, [rbp+37h+arg_38]
0x1800018ec  mov     r10, rdx
0x1800018ef  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1800018f3  xor     r9d, r9d
0x1800018f6  mov     r8d, 2
0x1800018fc  mov     rdx, [rax]
0x1800018ff  test    rdx, rdx
0x180001902  jz      short loc_18000191A
0x180001904  mov     rax, rcx
0x180001907  inc     rax
0x18000190a  cmp     [rdx+rax*2], r9w
0x18000190f  jnz     short loc_180001907
0x180001911  lea     eax, ds:2[rax*2]
0x180001918  jmp     short loc_180001924
0x18000191a  lea     rdx, dword_18002237C
0x180001921  mov     eax, r8d
0x180001924  mov     [rbp+37h+var_18], eax
0x180001927  mov     rax, [rbp+37h+arg_30]
0x18000192b  mov     [rbp+37h+var_20], rdx
0x18000192f  mov     [rbp+37h+var_14], r9d
0x180001933  mov     rdx, [rax]
0x180001936  test    rdx, rdx
0x180001939  jz      short loc_18000194B
0x18000193b  mov     rax, rcx
0x18000193e  inc     rax
0x180001941  cmp     [rdx+rax], r9b
0x180001945  jnz     short loc_18000193E
0x180001947  inc     eax
0x180001949  jmp     short loc_180001957
0x18000194b  lea     rdx, word_180021D5A
0x180001952  mov     eax, 1
0x180001957  mov     [rbp+37h+var_28], eax
0x18000195a  mov     rax, [rbp+37h+arg_28]
0x18000195e  mov     [rbp+37h+var_40], rax
0x180001962  mov     rax, [rbp+37h+arg_20]
0x180001966  mov     [rbp+37h+var_30], rdx
0x18000196a  mov     [rbp+37h+var_24], r9d
0x18000196e  mov     [rbp+37h+var_38], 4
0x180001976  mov     rdx, [rax]
0x180001979  test    rdx, rdx
0x18000197c  jz      short loc_180001992
0x18000197e  inc     rcx
0x180001981  cmp     [rdx+rcx*2], r9w
0x180001986  jnz     short loc_18000197E
0x180001988  lea     r8d, ds:2[rcx*2]
0x180001990  jmp     short loc_180001999
0x180001992  lea     rdx, dword_18002237C
0x180001999  lea     rax, [rbp+37h+var_70]
0x18000199d  mov     [rbp+37h+var_50], rdx
0x1800019a1  mov     [rbp+37h+var_48], r8d
0x1800019a5  lea     rcx, dword_18002B0C0
0x1800019ac  mov     [rsp+0A0h+var_78], rax
0x1800019b1  xor     r8d, r8d
0x1800019b4  mov     rdx, r10
0x1800019b7  mov     [rsp+0A0h+var_80], 6
0x1800019bf  mov     [rbp+37h+var_44], r9d
0x1800019c3  call    _tlgWriteTransfer_EventWriteTransfer
0x1800019c8  mov     rcx, [rbp+37h+var_10]
0x1800019cc  xor     rcx, rsp; StackCookie
0x1800019cf  call    __security_check_cookie
0x1800019d4  add     rsp, 0A0h
0x1800019db  pop     rbp
0x1800019dc  retn
```
