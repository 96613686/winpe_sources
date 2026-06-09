# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)

- ea: `0x1400012bc`
- end: `0x140001557`
- name: `??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456@Z`
- size: `667`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x140007170`

## callees

- `0x1400012bc`
- `0x1400018dc`
- `0x140001fa0`

## pseudocode

```c
ULONG __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
        __int64 a1,
        unsigned __int8 *a2,
        const GUID *a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        const unsigned __int16 **a7,
        __int64 a8,
        const unsigned __int16 **a9,
        __int64 a10,
        char **a11,
        __int64 a12,
        const unsigned __int16 **a13,
        __int64 a14,
        const unsigned __int16 **a15,
        char **a16,
        __int64 a17,
        const unsigned __int16 **a18,
        char **a19)
{
  __int64 v21; // rdx
  int v23; // r9d
  char *v24; // rcx
  __int64 v25; // rax
  int v26; // eax
  int v27; // r8d
  const unsigned __int16 *v28; // rcx
  __int64 v29; // rax
  int v30; // eax
  char *v31; // rcx
  __int64 v32; // rax
  int v33; // eax
  const unsigned __int16 *v34; // rcx
  __int64 v35; // rax
  int v36; // eax
  const unsigned __int16 *v37; // rcx
  __int64 v38; // rax
  int v39; // eax
  char *v40; // rcx
  __int64 v41; // rax
  const unsigned __int16 *v42; // rcx
  __int64 v43; // rax
  int v44; // eax
  const unsigned __int16 *v45; // rcx
  struct _EVENT_DATA_DESCRIPTOR v47; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v48; // [rsp+50h] [rbp-B0h]
  __int64 v49; // [rsp+58h] [rbp-A8h]
  __int64 v50; // [rsp+60h] [rbp-A0h]
  __int64 v51; // [rsp+68h] [rbp-98h]
  const unsigned __int16 *v52; // [rsp+70h] [rbp-90h]
  int v53; // [rsp+78h] [rbp-88h]
  int v54; // [rsp+7Ch] [rbp-84h]
  __int64 v55; // [rsp+80h] [rbp-80h]
  __int64 v56; // [rsp+88h] [rbp-78h]
  const unsigned __int16 *v57; // [rsp+90h] [rbp-70h]
  int v58; // [rsp+98h] [rbp-68h]
  int v59; // [rsp+9Ch] [rbp-64h]
  __int64 v60; // [rsp+A0h] [rbp-60h]
  __int64 v61; // [rsp+A8h] [rbp-58h]
  char *v62; // [rsp+B0h] [rbp-50h]
  int v63; // [rsp+B8h] [rbp-48h]
  int v64; // [rsp+BCh] [rbp-44h]
  __int64 v65; // [rsp+C0h] [rbp-40h]
  __int64 v66; // [rsp+C8h] [rbp-38h]
  const unsigned __int16 *v67; // [rsp+D0h] [rbp-30h]
  int v68; // [rsp+D8h] [rbp-28h]
  int v69; // [rsp+DCh] [rbp-24h]
  __int64 v70; // [rsp+E0h] [rbp-20h]
  __int64 v71; // [rsp+E8h] [rbp-18h]
  const unsigned __int16 *v72; // [rsp+F0h] [rbp-10h]
  int v73; // [rsp+F8h] [rbp-8h]
  int v74; // [rsp+FCh] [rbp-4h]
  char *v75; // [rsp+100h] [rbp+0h]
  int v76; // [rsp+108h] [rbp+8h]
  int v77; // [rsp+10Ch] [rbp+Ch]
  __int64 v78; // [rsp+110h] [rbp+10h]
  __int64 v79; // [rsp+118h] [rbp+18h]
  const unsigned __int16 *v80; // [rsp+120h] [rbp+20h]
  int v81; // [rsp+128h] [rbp+28h]
  int v82; // [rsp+12Ch] [rbp+2Ch]
  char *v83; // [rsp+130h] [rbp+30h]
  int v84; // [rsp+138h] [rbp+38h]
  int v85; // [rsp+13Ch] [rbp+3Ch]

  v21 = -1;
  v23 = 2;
  v24 = *a19;
  if ( *a19 )
  {
    v25 = -1;
    do
      ++v25;
    while ( *(_WORD *)&v24[2 * v25] );
    v26 = 2 * v25 + 2;
  }
  else
  {
    v24 = byte_140012698;
    v26 = 2;
  }
  v84 = v26;
  v27 = 1;
  v83 = v24;
  v85 = 0;
  v28 = *a18;
  if ( *a18 )
  {
    v29 = -1;
    do
      ++v29;
    while ( *((_BYTE *)v28 + v29) );
    v30 = v29 + 1;
  }
  else
  {
    v28 = &word_14001269A;
    v30 = 1;
  }
  v81 = v30;
  v78 = a17;
  v80 = v28;
  v82 = 0;
  v79 = 4;
  v31 = *a16;
  if ( *a16 )
  {
    v32 = -1;
    do
      ++v32;
    while ( *(_WORD *)&v31[2 * v32] );
    v33 = 2 * v32 + 2;
  }
  else
  {
    v31 = byte_140012698;
    v33 = 2;
  }
  v76 = v33;
  v75 = v31;
  v77 = 0;
  v34 = *a15;
  if ( *a15 )
  {
    v35 = -1;
    do
      ++v35;
    while ( *((_BYTE *)v34 + v35) );
    v36 = v35 + 1;
  }
  else
  {
    v34 = &word_14001269A;
    v36 = 1;
  }
  v73 = v36;
  v70 = a14;
  v72 = v34;
  v74 = 0;
  v71 = 4;
  v37 = *a13;
  if ( *a13 )
  {
    v38 = -1;
    do
      ++v38;
    while ( *((_BYTE *)v37 + v38) );
    v39 = v38 + 1;
  }
  else
  {
    v37 = &word_14001269A;
    v39 = 1;
  }
  v68 = v39;
  v65 = a12;
  v67 = v37;
  v69 = 0;
  v66 = 4;
  v40 = *a11;
  if ( *a11 )
  {
    v41 = -1;
    do
      ++v41;
    while ( *(_WORD *)&v40[2 * v41] );
    v23 = 2 * v41 + 2;
  }
  else
  {
    v40 = byte_140012698;
  }
  v60 = a10;
  v62 = v40;
  v63 = v23;
  v64 = 0;
  v42 = *a9;
  v61 = 4;
  if ( v42 )
  {
    v43 = -1;
    do
      ++v43;
    while ( *((_BYTE *)v42 + v43) );
    v44 = v43 + 1;
  }
  else
  {
    v42 = &word_14001269A;
    v44 = 1;
  }
  v58 = v44;
  v55 = a8;
  v57 = v42;
  v59 = 0;
  v56 = 4;
  v45 = *a7;
  if ( *a7 )
  {
    do
      ++v21;
    while ( *((_BYTE *)v45 + v21) );
    v27 = v21 + 1;
  }
  else
  {
    v45 = &word_14001269A;
  }
  v50 = a6;
  v48 = a5;
  v52 = v45;
  v53 = v27;
  v54 = 0;
  v51 = 4;
  v49 = 8;
  return tlgWriteTransfer_EventWriteTransfer(a1, a2, a3, 0, 0x11u, &v47);
}

```

## disassembly

```asm
0x1400012bc  push    rbp
0x1400012be  push    rbx
0x1400012bf  push    rsi
0x1400012c0  push    rdi
0x1400012c1  push    r14
0x1400012c3  lea     rbp, [rsp-50h]
0x1400012c8  sub     rsp, 150h
0x1400012cf  mov     rax, cs:__security_cookie
0x1400012d6  xor     rax, rsp
0x1400012d9  mov     [rbp+70h+var_30], rax
0x1400012dd  mov     rax, [rbp+70h+arg_90]
0x1400012e4  mov     r11, rdx
0x1400012e7  mov     r10, rcx
0x1400012ea  or      rdx, 0FFFFFFFFFFFFFFFFh
0x1400012ee  xor     edi, edi
0x1400012f0  mov     rbx, r8
0x1400012f3  mov     r9d, 2
0x1400012f9  mov     rcx, [rax]
0x1400012fc  test    rcx, rcx
0x1400012ff  jz      short loc_140001316
0x140001301  mov     rax, rdx
0x140001304  inc     rax
0x140001307  cmp     [rcx+rax*2], di
0x14000130b  jnz     short loc_140001304
0x14000130d  lea     eax, ds:2[rax*2]
0x140001314  jmp     short loc_140001320
0x140001316  lea     rcx, byte_140012698
0x14000131d  mov     eax, r9d
0x140001320  mov     [rbp+70h+var_38], eax
0x140001323  lea     rsi, word_14001269A
0x14000132a  mov     rax, [rbp+70h+arg_88]
0x140001331  mov     r8d, 1
0x140001337  mov     [rbp+70h+var_40], rcx
0x14000133b  mov     [rbp+70h+var_34], edi
0x14000133e  mov     rcx, [rax]
0x140001341  test    rcx, rcx
0x140001344  jz      short loc_140001356
0x140001346  mov     rax, rdx
0x140001349  inc     rax
0x14000134c  cmp     [rcx+rax], dil
0x140001350  jnz     short loc_140001349
0x140001352  inc     eax
0x140001354  jmp     short loc_14000135C
0x140001356  mov     rcx, rsi
0x140001359  mov     eax, r8d
0x14000135c  mov     [rbp+70h+var_48], eax
0x14000135f  mov     rax, [rbp+70h+arg_80]
0x140001366  mov     [rbp+70h+var_60], rax
0x14000136a  mov     rax, [rbp+70h+arg_78]
0x140001371  mov     [rbp+70h+var_50], rcx
0x140001375  mov     [rbp+70h+var_44], edi
0x140001378  mov     [rbp+70h+var_58], 4
0x140001380  mov     rcx, [rax]
0x140001383  test    rcx, rcx
0x140001386  jz      short loc_14000139D
0x140001388  mov     rax, rdx
0x14000138b  inc     rax
0x14000138e  cmp     [rcx+rax*2], di
0x140001392  jnz     short loc_14000138B
0x140001394  lea     eax, ds:2[rax*2]
0x14000139b  jmp     short loc_1400013A7
0x14000139d  lea     rcx, byte_140012698
0x1400013a4  mov     eax, r9d
0x1400013a7  mov     [rbp+70h+var_68], eax
0x1400013aa  mov     rax, [rbp+70h+arg_70]
0x1400013b1  mov     [rbp+70h+var_70], rcx
0x1400013b5  mov     [rbp+70h+var_64], edi
0x1400013b8  mov     rcx, [rax]
0x1400013bb  test    rcx, rcx
0x1400013be  jz      short loc_1400013D0
0x1400013c0  mov     rax, rdx
0x1400013c3  inc     rax
0x1400013c6  cmp     [rcx+rax], dil
0x1400013ca  jnz     short loc_1400013C3
0x1400013cc  inc     eax
0x1400013ce  jmp     short loc_1400013D6
0x1400013d0  mov     rcx, rsi
0x1400013d3  mov     eax, r8d
0x1400013d6  mov     [rbp+70h+var_78], eax
0x1400013d9  mov     rax, [rbp+70h+arg_68]
0x1400013e0  mov     [rbp+70h+var_90], rax
0x1400013e4  mov     rax, [rbp+70h+arg_60]
0x1400013eb  mov     [rbp+70h+var_80], rcx
0x1400013ef  mov     [rbp+70h+var_74], edi
0x1400013f2  mov     [rbp+70h+var_88], 4
0x1400013fa  mov     rcx, [rax]
0x1400013fd  test    rcx, rcx
0x140001400  jz      short loc_140001412
0x140001402  mov     rax, rdx
0x140001405  inc     rax
0x140001408  cmp     [rcx+rax], dil
0x14000140c  jnz     short loc_140001405
0x14000140e  inc     eax
0x140001410  jmp     short loc_140001418
0x140001412  mov     rcx, rsi
0x140001415  mov     eax, r8d
0x140001418  mov     [rbp+70h+var_98], eax
0x14000141b  mov     rax, [rbp+70h+arg_58]
0x140001422  mov     [rbp+70h+var_B0], rax
0x140001426  mov     rax, [rbp+70h+arg_50]
0x14000142d  mov     [rbp+70h+var_A0], rcx
0x140001431  mov     [rbp+70h+var_94], edi
0x140001434  mov     [rbp+70h+var_A8], 4
0x14000143c  mov     rcx, [rax]
0x14000143f  test    rcx, rcx
0x140001442  jz      short loc_14000145A
0x140001444  mov     rax, rdx
0x140001447  inc     rax
0x14000144a  cmp     [rcx+rax*2], di
0x14000144e  jnz     short loc_140001447
0x140001450  lea     r9d, ds:2[rax*2]
0x140001458  jmp     short loc_140001461
0x14000145a  lea     rcx, byte_140012698
0x140001461  mov     rax, [rbp+70h+arg_48]
0x140001468  mov     [rbp+70h+var_D0], rax
0x14000146c  mov     rax, [rbp+70h+arg_40]
0x140001473  mov     [rbp+70h+var_C0], rcx
0x140001477  mov     [rbp+70h+var_B8], r9d
0x14000147b  mov     [rbp+70h+var_B4], edi
0x14000147e  mov     rcx, [rax]
0x140001481  mov     [rbp+70h+var_C8], 4
0x140001489  test    rcx, rcx
0x14000148c  jz      short loc_14000149E
0x14000148e  mov     rax, rdx
0x140001491  inc     rax
0x140001494  cmp     [rcx+rax], dil
0x140001498  jnz     short loc_140001491
0x14000149a  inc     eax
0x14000149c  jmp     short loc_1400014A4
0x14000149e  mov     rcx, rsi
0x1400014a1  mov     eax, r8d
0x1400014a4  mov     [rbp+70h+var_D8], eax
0x1400014a7  mov     rax, [rbp+70h+arg_38]
0x1400014ae  mov     [rbp+70h+var_F0], rax
0x1400014b2  mov     rax, [rbp+70h+arg_30]
0x1400014b9  mov     [rbp+70h+var_E0], rcx
0x1400014bd  mov     [rbp+70h+var_D4], edi
0x1400014c0  mov     [rbp+70h+var_E8], 4
0x1400014c8  mov     rcx, [rax]
0x1400014cb  test    rcx, rcx
0x1400014ce  jz      short loc_1400014DF
0x1400014d0  inc     rdx
0x1400014d3  cmp     [rcx+rdx], dil
0x1400014d7  jnz     short loc_1400014D0
0x1400014d9  lea     r8d, [rdx+1]
0x1400014dd  jmp     short loc_1400014E2
0x1400014df  mov     rcx, rsi
0x1400014e2  mov     rax, [rbp+70h+arg_28]
0x1400014e9  xor     r9d, r9d
0x1400014ec  mov     [rsp+170h+var_110], rax
0x1400014f1  mov     rdx, r11
0x1400014f4  mov     rax, [rbp+70h+arg_20]
0x1400014fb  mov     [rsp+170h+var_120], rax
0x140001500  lea     rax, [rsp+170h+var_140]
0x140001505  mov     [rsp+170h+var_100], rcx
0x14000150a  mov     rcx, r10
0x14000150d  mov     [rsp+170h+var_F8], r8d
0x140001512  mov     r8, rbx
0x140001515  mov     [rsp+170h+var_148], rax
0x14000151a  mov     [rsp+170h+var_150], 11h
0x140001522  mov     [rsp+170h+var_F4], edi
0x140001526  mov     [rsp+170h+var_108], 4
0x14000152f  mov     [rsp+170h+var_118], 8
0x140001538  call    _tlgWriteTransfer_EventWriteTransfer
0x14000153d  mov     rcx, [rbp+70h+var_30]
0x140001541  xor     rcx, rsp; StackCookie
0x140001544  call    __security_check_cookie
0x140001549  add     rsp, 150h
0x140001550  pop     r14
0x140001552  pop     rdi
0x140001553  pop     rsi
0x140001554  pop     rbx
0x140001555  pop     rbp
0x140001556  retn
```
