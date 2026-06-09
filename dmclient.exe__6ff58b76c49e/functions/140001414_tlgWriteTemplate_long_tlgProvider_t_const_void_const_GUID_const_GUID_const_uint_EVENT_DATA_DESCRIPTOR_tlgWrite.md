# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &)

- ea: `0x140001414`
- end: `0x140001531`
- name: `??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U1@U2@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@334AEBU?$_tlgWrapperByVal@$07@@@Z`
- size: `285`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, const unsigned __int16 **, __int64, const unsigned __int16 **, const unsigned __int16 **, __int64, __int64)`
- caller_count: `25`
- callee_count: `3`
- tags: ``

## callers

- `0x140004fe0`
- `0x1400052f0`
- `0x140005830`
- `0x1400076e4`
- `0x14000c47c`
- `0x14000dab4`
- `0x14000dd30`
- `0x14000e750`
- `0x14000e924`
- `0x14000f65c`
- `0x14000fc30`
- `0x14000fe20`
- `0x140010050`
- `0x140010470`
- `0x1400105d8`
- `0x1400109d0`
- `0x140010d00`
- `0x140011250`
- `0x140011fec`
- `0x140013b84`
- `0x1400144a4`
- `0x140015aec`
- `0x140015e78`
- `0x140016230`
- `0x140017094`

## callees

- `0x140001414`
- `0x14000182c`
- `0x1400187e0`

## pseudocode

```c
__int64 __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        const unsigned __int16 **a5,
        __int64 a6,
        const unsigned __int16 **a7,
        const unsigned __int16 **a8,
        __int64 a9,
        __int64 a10)
{
  __int64 v11; // rcx
  int v12; // r8d
  const unsigned __int16 *v13; // rdx
  __int64 v14; // rax
  int v15; // eax
  const unsigned __int16 *v16; // rdx
  __int64 v17; // rax
  int v18; // eax
  const unsigned __int16 *v19; // rdx
  _BYTE v21[32]; // [rsp+30h] [rbp-69h] BYREF
  const unsigned __int16 *v22; // [rsp+50h] [rbp-49h]
  int v23; // [rsp+58h] [rbp-41h]
  int v24; // [rsp+5Ch] [rbp-3Dh]
  __int64 v25; // [rsp+60h] [rbp-39h]
  __int64 v26; // [rsp+68h] [rbp-31h]
  const unsigned __int16 *v27; // [rsp+70h] [rbp-29h]
  int v28; // [rsp+78h] [rbp-21h]
  int v29; // [rsp+7Ch] [rbp-1Dh]
  const unsigned __int16 *v30; // [rsp+80h] [rbp-19h]
  int v31; // [rsp+88h] [rbp-11h]
  int v32; // [rsp+8Ch] [rbp-Dh]
  __int64 v33; // [rsp+90h] [rbp-9h]
  __int64 v34; // [rsp+98h] [rbp-1h]
  __int64 v35; // [rsp+A0h] [rbp+7h]
  __int64 v36; // [rsp+A8h] [rbp+Fh]

  v35 = a10;
  v33 = a9;
  v11 = -1;
  v36 = 8;
  v12 = 1;
  v34 = 4;
  v13 = *a8;
  if ( *a8 )
  {
    v14 = -1;
    do
      ++v14;
    while ( *((_BYTE *)v13 + v14) );
    v15 = v14 + 1;
  }
  else
  {
    v13 = &word_14001C5D2;
    v15 = 1;
  }
  v31 = v15;
  v30 = v13;
  v32 = 0;
  v16 = *a7;
  if ( *a7 )
  {
    v17 = -1;
    do
      ++v17;
    while ( *((_BYTE *)v16 + v17) );
    v18 = v17 + 1;
  }
  else
  {
    v16 = &word_14001C5D2;
    v18 = 1;
  }
  v28 = v18;
  v25 = a6;
  v27 = v16;
  v29 = 0;
  v26 = 4;
  v19 = *a5;
  if ( *a5 )
  {
    do
      ++v11;
    while ( *((_BYTE *)v19 + v11) );
    v12 = v11 + 1;
  }
  else
  {
    v19 = &word_14001C5D2;
  }
  v22 = v19;
  v23 = v12;
  v24 = 0;
  return tlgWriteTransfer_EventWriteTransfer(&dword_140027000, a2, 0, 0, 8, v21);
}

```

## disassembly

```asm
0x140001414  push    rbp
0x140001416  lea     rbp, [rsp-27h]
0x14000141b  sub     rsp, 0C0h
0x140001422  mov     rax, cs:__security_cookie
0x140001429  xor     rax, rsp
0x14000142c  mov     [rbp+27h+var_10], rax
0x140001430  mov     rax, [rbp+27h+arg_48]
0x140001434  lea     r11, word_14001C5D2
0x14000143b  mov     [rbp+27h+var_20], rax
0x14000143f  xor     r9d, r9d
0x140001442  mov     rax, [rbp+27h+arg_40]
0x140001446  mov     r10, rdx
0x140001449  mov     [rbp+27h+var_30], rax
0x14000144d  or      rcx, 0FFFFFFFFFFFFFFFFh
0x140001451  mov     rax, [rbp+27h+arg_38]
0x140001455  mov     [rbp+27h+var_18], 8
0x14000145d  lea     r8d, [r9+1]
0x140001461  mov     [rbp+27h+var_28], 4
0x140001469  mov     rdx, [rax]
0x14000146c  test    rdx, rdx
0x14000146f  jz      short loc_140001481
0x140001471  mov     rax, rcx
0x140001474  inc     rax
0x140001477  cmp     [rdx+rax], r9b
0x14000147b  jnz     short loc_140001474
0x14000147d  inc     eax
0x14000147f  jmp     short loc_140001487
0x140001481  mov     rdx, r11
0x140001484  mov     eax, r8d
0x140001487  mov     [rbp+27h+var_38], eax
0x14000148a  mov     rax, [rbp+27h+arg_30]
0x14000148e  mov     [rbp+27h+var_40], rdx
0x140001492  mov     [rbp+27h+var_34], r9d
0x140001496  mov     rdx, [rax]
0x140001499  test    rdx, rdx
0x14000149c  jz      short loc_1400014AE
0x14000149e  mov     rax, rcx
0x1400014a1  inc     rax
0x1400014a4  cmp     [rdx+rax], r9b
0x1400014a8  jnz     short loc_1400014A1
0x1400014aa  inc     eax
0x1400014ac  jmp     short loc_1400014B4
0x1400014ae  mov     rdx, r11
0x1400014b1  mov     eax, r8d
0x1400014b4  mov     [rbp+27h+var_48], eax
0x1400014b7  mov     rax, [rbp+27h+arg_28]
0x1400014bb  mov     [rbp+27h+var_60], rax
0x1400014bf  mov     rax, [rbp+27h+arg_20]
0x1400014c3  mov     [rbp+27h+var_50], rdx
0x1400014c7  mov     [rbp+27h+var_44], r9d
0x1400014cb  mov     [rbp+27h+var_58], 4
0x1400014d3  mov     rdx, [rax]
0x1400014d6  test    rdx, rdx
0x1400014d9  jz      short loc_1400014EA
0x1400014db  inc     rcx
0x1400014de  cmp     [rdx+rcx], r9b
0x1400014e2  jnz     short loc_1400014DB
0x1400014e4  lea     r8d, [rcx+1]
0x1400014e8  jmp     short loc_1400014ED
0x1400014ea  mov     rdx, r11
0x1400014ed  lea     rax, [rbp+27h+var_90]
0x1400014f1  mov     [rbp+27h+var_70], rdx
0x1400014f5  mov     [rbp+27h+var_68], r8d
0x1400014f9  lea     rcx, dword_140027000
0x140001500  mov     [rsp+0C0h+var_98], rax
0x140001505  xor     r8d, r8d
0x140001508  mov     rdx, r10
0x14000150b  mov     [rsp+0C0h+var_A0], 8
0x140001513  mov     [rbp+27h+var_64], r9d
0x140001517  call    _tlgWriteTransfer_EventWriteTransfer
0x14000151c  mov     rcx, [rbp+27h+var_10]
0x140001520  xor     rcx, rsp; StackCookie
0x140001523  call    __security_check_cookie
0x140001528  add     rsp, 0C0h
0x14000152f  pop     rbp
0x140001530  retn
```
