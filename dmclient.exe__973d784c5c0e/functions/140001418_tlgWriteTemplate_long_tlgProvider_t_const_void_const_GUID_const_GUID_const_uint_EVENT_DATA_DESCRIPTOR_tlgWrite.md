# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &)

- ea: `0x140001418`
- end: `0x140001536`
- name: `??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U1@U2@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@334AEBU?$_tlgWrapperByVal@$07@@@Z`
- size: `286`
- prototype: ``
- caller_count: `25`
- callee_count: `3`
- tags: ``

## callers

- `0x140005100`
- `0x140005420`
- `0x14000588c`
- `0x14000784c`
- `0x14000c928`
- `0x14000dff4`
- `0x14000e290`
- `0x14000ecc0`
- `0x14000ee98`
- `0x14000fbf8`
- `0x1400101fc`
- `0x1400103f8`
- `0x140010638`
- `0x140010acc`
- `0x140010c40`
- `0x14001108c`
- `0x1400113f4`
- `0x1400119f0`
- `0x140012928`
- `0x1400135d4`
- `0x140013ebc`
- `0x1400143cc`
- `0x140014774`
- `0x140014a40`
- `0x140014e08`

## callees

- `0x140001418`
- `0x140001840`
- `0x140019610`

## pseudocode

```c
ULONG __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
        __int64 a1,
        unsigned __int8 *a2,
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
  struct _EVENT_DATA_DESCRIPTOR v21; // [rsp+30h] [rbp-69h] BYREF
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
    v13 = &word_14001D5D2;
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
    v16 = &word_14001D5D2;
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
    v19 = &word_14001D5D2;
  }
  v22 = v19;
  v23 = v12;
  v24 = 0;
  return tlgWriteTransfer_EventWriteTransfer((__int64)&dword_140028000, a2, 0, 0, 8u, &v21);
}

```

## disassembly

```asm
0x140001418  push    rbp
0x14000141a  lea     rbp, [rsp-27h]
0x14000141f  sub     rsp, 0C0h
0x140001426  mov     rax, cs:__security_cookie
0x14000142d  xor     rax, rsp
0x140001430  mov     [rbp+27h+var_10], rax
0x140001434  mov     rax, [rbp+27h+arg_48]
0x140001438  lea     r11, word_14001D5D2
0x14000143f  mov     [rbp+27h+var_20], rax
0x140001443  xor     r9d, r9d
0x140001446  mov     rax, [rbp+27h+arg_40]
0x14000144a  mov     r10, rdx
0x14000144d  mov     [rbp+27h+var_30], rax
0x140001451  or      rcx, 0FFFFFFFFFFFFFFFFh
0x140001455  mov     rax, [rbp+27h+arg_38]
0x140001459  mov     [rbp+27h+var_18], 8
0x140001461  lea     r8d, [r9+1]
0x140001465  mov     [rbp+27h+var_28], 4
0x14000146d  mov     rdx, [rax]
0x140001470  test    rdx, rdx
0x140001473  jz      short loc_140001485
0x140001475  mov     rax, rcx
0x140001478  inc     rax
0x14000147b  cmp     [rdx+rax], r9b
0x14000147f  jnz     short loc_140001478
0x140001481  inc     eax
0x140001483  jmp     short loc_14000148B
0x140001485  mov     rdx, r11
0x140001488  mov     eax, r8d
0x14000148b  mov     [rbp+27h+var_38], eax
0x14000148e  mov     rax, [rbp+27h+arg_30]
0x140001492  mov     [rbp+27h+var_40], rdx
0x140001496  mov     [rbp+27h+var_34], r9d
0x14000149a  mov     rdx, [rax]
0x14000149d  test    rdx, rdx
0x1400014a0  jz      short loc_1400014B2
0x1400014a2  mov     rax, rcx
0x1400014a5  inc     rax
0x1400014a8  cmp     [rdx+rax], r9b
0x1400014ac  jnz     short loc_1400014A5
0x1400014ae  inc     eax
0x1400014b0  jmp     short loc_1400014B8
0x1400014b2  mov     rdx, r11
0x1400014b5  mov     eax, r8d
0x1400014b8  mov     [rbp+27h+var_48], eax
0x1400014bb  mov     rax, [rbp+27h+arg_28]
0x1400014bf  mov     [rbp+27h+var_60], rax
0x1400014c3  mov     rax, [rbp+27h+arg_20]
0x1400014c7  mov     [rbp+27h+var_50], rdx
0x1400014cb  mov     [rbp+27h+var_44], r9d
0x1400014cf  mov     [rbp+27h+var_58], 4
0x1400014d7  mov     rdx, [rax]
0x1400014da  test    rdx, rdx
0x1400014dd  jz      short loc_1400014EE
0x1400014df  inc     rcx
0x1400014e2  cmp     [rdx+rcx], r9b
0x1400014e6  jnz     short loc_1400014DF
0x1400014e8  lea     r8d, [rcx+1]
0x1400014ec  jmp     short loc_1400014F1
0x1400014ee  mov     rdx, r11
0x1400014f1  lea     rax, [rbp+27h+var_90]
0x1400014f5  mov     [rbp+27h+var_70], rdx
0x1400014f9  mov     [rbp+27h+var_68], r8d
0x1400014fd  lea     rcx, dword_140028000
0x140001504  mov     [rsp+0C0h+var_98], rax
0x140001509  xor     r8d, r8d
0x14000150c  mov     rdx, r10
0x14000150f  mov     [rsp+0C0h+var_A0], 8
0x140001517  mov     [rbp+27h+var_64], r9d
0x14000151b  call    _tlgWriteTransfer_EventWriteTransfer
0x140001520  mov     rcx, [rbp+27h+var_10]
0x140001524  xor     rcx, rsp; StackCookie
0x140001527  call    __security_check_cookie
0x14000152c  add     rsp, 0C0h
0x140001533  pop     rbp
0x140001534  retn
```
