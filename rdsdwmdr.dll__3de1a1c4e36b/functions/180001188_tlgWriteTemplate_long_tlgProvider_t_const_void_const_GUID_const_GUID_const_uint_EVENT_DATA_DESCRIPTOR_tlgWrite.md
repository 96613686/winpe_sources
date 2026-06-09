# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)

- ea: `0x180001188`
- end: `0x180001287`
- name: `??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@3@Z`
- size: `255`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, const unsigned __int16 **, const unsigned __int16 **, __int64, const unsigned __int16 **)`
- caller_count: `26`
- callee_count: `3`
- tags: ``

## callers

- `0x180004cbc`
- `0x18000a930`
- `0x18000aa80`
- `0x18000ad10`
- `0x18000b2e0`
- `0x18000b4d0`
- `0x18000b6e0`
- `0x18000b820`
- `0x18000cde8`
- `0x18000cf04`
- `0x18000d4b4`
- `0x18000dc04`
- `0x18000dd74`
- `0x18000de24`
- `0x18000e0e8`
- `0x18000ea10`
- `0x1800108a8`
- `0x180012238`
- `0x1800130c0`
- `0x180013e58`
- `0x1800149e0`
- `0x180015ff0`
- `0x180017598`
- `0x180017ed0`
- `0x180018020`
- `0x180018520`

## callees

- `0x180001188`
- `0x180001ef8`
- `0x18002b960`

## pseudocode

```c
__int64 __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        const unsigned __int16 **a5,
        const unsigned __int16 **a6,
        __int64 a7,
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
  const unsigned __int16 *v23; // [rsp+60h] [rbp-9h]
  int v24; // [rsp+68h] [rbp-1h]
  int v25; // [rsp+6Ch] [rbp+3h]
  __int64 v26; // [rsp+70h] [rbp+7h]
  __int64 v27; // [rsp+78h] [rbp+Fh]
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
    v11 = &word_18002F722;
    v13 = 1;
  }
  v29 = v13;
  v26 = a7;
  v28 = v11;
  v30 = 0;
  v27 = 4;
  v14 = *a6;
  if ( *a6 )
  {
    v15 = -1;
    do
      ++v15;
    while ( *((_BYTE *)v14 + v15) );
    v16 = v15 + 1;
  }
  else
  {
    v14 = &word_18002F722;
    v16 = 1;
  }
  v24 = v16;
  v23 = v14;
  v25 = 0;
  v17 = *a5;
  if ( *a5 )
  {
    do
      ++v9;
    while ( *((_BYTE *)v17 + v9) );
    v10 = v9 + 1;
  }
  else
  {
    v17 = &word_18002F722;
  }
  v20 = v17;
  v21 = v10;
  v22 = 0;
  return tlgWriteTransfer_EventWriteTransfer(&dword_180044008, a2, 0, 0, 6, v19);
}

```

## disassembly

```asm
0x180001188  push    rbp
0x18000118a  lea     rbp, [rsp-37h]
0x18000118f  sub     rsp, 0A0h
0x180001196  mov     rax, cs:__security_cookie
0x18000119d  xor     rax, rsp
0x1800011a0  mov     [rbp+37h+var_10], rax
0x1800011a4  mov     rax, [rbp+37h+arg_38]
0x1800011a8  lea     r11, word_18002F722
0x1800011af  mov     r10, rdx
0x1800011b2  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1800011b6  xor     r9d, r9d
0x1800011b9  mov     r8d, 1
0x1800011bf  mov     rdx, [rax]
0x1800011c2  test    rdx, rdx
0x1800011c5  jz      short loc_1800011D7
0x1800011c7  mov     rax, rcx
0x1800011ca  inc     rax
0x1800011cd  cmp     [rdx+rax], r9b
0x1800011d1  jnz     short loc_1800011CA
0x1800011d3  inc     eax
0x1800011d5  jmp     short loc_1800011DD
0x1800011d7  mov     rdx, r11
0x1800011da  mov     eax, r8d
0x1800011dd  mov     [rbp+37h+var_18], eax
0x1800011e0  mov     rax, [rbp+37h+arg_30]
0x1800011e4  mov     [rbp+37h+var_30], rax
0x1800011e8  mov     rax, [rbp+37h+arg_28]
0x1800011ec  mov     [rbp+37h+var_20], rdx
0x1800011f0  mov     [rbp+37h+var_14], r9d
0x1800011f4  mov     [rbp+37h+var_28], 4
0x1800011fc  mov     rdx, [rax]
0x1800011ff  test    rdx, rdx
0x180001202  jz      short loc_180001214
0x180001204  mov     rax, rcx
0x180001207  inc     rax
0x18000120a  cmp     [rdx+rax], r9b
0x18000120e  jnz     short loc_180001207
0x180001210  inc     eax
0x180001212  jmp     short loc_18000121A
0x180001214  mov     rdx, r11
0x180001217  mov     eax, r8d
0x18000121a  mov     [rbp+37h+var_38], eax
0x18000121d  mov     rax, [rbp+37h+arg_20]
0x180001221  mov     [rbp+37h+var_40], rdx
0x180001225  mov     [rbp+37h+var_34], r9d
0x180001229  mov     rdx, [rax]
0x18000122c  test    rdx, rdx
0x18000122f  jz      short loc_180001240
0x180001231  inc     rcx
0x180001234  cmp     [rdx+rcx], r9b
0x180001238  jnz     short loc_180001231
0x18000123a  lea     r8d, [rcx+1]
0x18000123e  jmp     short loc_180001243
0x180001240  mov     rdx, r11
0x180001243  lea     rax, [rbp+37h+var_70]
0x180001247  mov     [rbp+37h+var_50], rdx
0x18000124b  mov     [rbp+37h+var_48], r8d
0x18000124f  lea     rcx, dword_180044008
0x180001256  mov     [rsp+0A0h+var_78], rax
0x18000125b  xor     r8d, r8d
0x18000125e  mov     rdx, r10
0x180001261  mov     [rsp+0A0h+var_80], 6
0x180001269  mov     [rbp+37h+var_44], r9d
0x18000126d  call    _tlgWriteTransfer_EventWriteTransfer
0x180001272  mov     rcx, [rbp+37h+var_10]
0x180001276  xor     rcx, rsp; StackCookie
0x180001279  call    __security_check_cookie
0x18000127e  add     rsp, 0A0h
0x180001285  pop     rbp
0x180001286  retn
```
