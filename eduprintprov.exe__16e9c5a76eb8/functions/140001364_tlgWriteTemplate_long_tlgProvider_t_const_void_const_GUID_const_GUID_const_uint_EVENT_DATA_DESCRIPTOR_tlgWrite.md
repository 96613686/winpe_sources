# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)

- ea: `0x140001364`
- end: `0x140001654`
- name: `??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456445@Z`
- size: `752`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x14000dc4c`
- `0x1400120b4`
- `0x1400123e0`

## callees

- `0x140001364`
- `0x1400016dc`
- `0x140002600`

## pseudocode

```c
ULONG __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
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
        int **a11,
        __int64 a12,
        const unsigned __int16 **a13,
        __int64 a14,
        const unsigned __int16 **a15,
        int **a16,
        __int64 a17,
        const unsigned __int16 **a18,
        int **a19,
        __int64 a20,
        __int64 a21,
        const unsigned __int16 **a22)
{
  __int64 v24; // rdx
  int v26; // r8d
  const unsigned __int16 *v27; // rcx
  __int64 v28; // rax
  int v29; // eax
  int v30; // r9d
  int *v31; // rcx
  __int64 v32; // rax
  int v33; // eax
  const unsigned __int16 *v34; // rcx
  __int64 v35; // rax
  int v36; // eax
  int *v37; // rcx
  __int64 v38; // rax
  int v39; // eax
  const unsigned __int16 *v40; // rcx
  __int64 v41; // rax
  int v42; // eax
  const unsigned __int16 *v43; // rcx
  __int64 v44; // rax
  int v45; // eax
  int *v46; // rcx
  __int64 v47; // rax
  const unsigned __int16 *v48; // rcx
  __int64 v49; // rax
  int v50; // eax
  const unsigned __int16 *v51; // rcx
  struct _EVENT_DATA_DESCRIPTOR v53; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v54; // [rsp+50h] [rbp-B0h]
  __int64 v55; // [rsp+58h] [rbp-A8h]
  __int64 v56; // [rsp+60h] [rbp-A0h]
  __int64 v57; // [rsp+68h] [rbp-98h]
  const unsigned __int16 *v58; // [rsp+70h] [rbp-90h]
  int v59; // [rsp+78h] [rbp-88h]
  int v60; // [rsp+7Ch] [rbp-84h]
  __int64 v61; // [rsp+80h] [rbp-80h]
  __int64 v62; // [rsp+88h] [rbp-78h]
  const unsigned __int16 *v63; // [rsp+90h] [rbp-70h]
  int v64; // [rsp+98h] [rbp-68h]
  int v65; // [rsp+9Ch] [rbp-64h]
  __int64 v66; // [rsp+A0h] [rbp-60h]
  __int64 v67; // [rsp+A8h] [rbp-58h]
  int *v68; // [rsp+B0h] [rbp-50h]
  int v69; // [rsp+B8h] [rbp-48h]
  int v70; // [rsp+BCh] [rbp-44h]
  __int64 v71; // [rsp+C0h] [rbp-40h]
  __int64 v72; // [rsp+C8h] [rbp-38h]
  const unsigned __int16 *v73; // [rsp+D0h] [rbp-30h]
  int v74; // [rsp+D8h] [rbp-28h]
  int v75; // [rsp+DCh] [rbp-24h]
  __int64 v76; // [rsp+E0h] [rbp-20h]
  __int64 v77; // [rsp+E8h] [rbp-18h]
  const unsigned __int16 *v78; // [rsp+F0h] [rbp-10h]
  int v79; // [rsp+F8h] [rbp-8h]
  int v80; // [rsp+FCh] [rbp-4h]
  int *v81; // [rsp+100h] [rbp+0h]
  int v82; // [rsp+108h] [rbp+8h]
  int v83; // [rsp+10Ch] [rbp+Ch]
  __int64 v84; // [rsp+110h] [rbp+10h]
  __int64 v85; // [rsp+118h] [rbp+18h]
  const unsigned __int16 *v86; // [rsp+120h] [rbp+20h]
  int v87; // [rsp+128h] [rbp+28h]
  int v88; // [rsp+12Ch] [rbp+2Ch]
  int *v89; // [rsp+130h] [rbp+30h]
  int v90; // [rsp+138h] [rbp+38h]
  int v91; // [rsp+13Ch] [rbp+3Ch]
  __int64 v92; // [rsp+140h] [rbp+40h]
  __int64 v93; // [rsp+148h] [rbp+48h]
  __int64 v94; // [rsp+150h] [rbp+50h]
  __int64 v95; // [rsp+158h] [rbp+58h]
  const unsigned __int16 *v96; // [rsp+160h] [rbp+60h]
  int v97; // [rsp+168h] [rbp+68h]
  int v98; // [rsp+16Ch] [rbp+6Ch]

  v24 = -1;
  v26 = 1;
  v27 = *a22;
  if ( *a22 )
  {
    v28 = -1;
    do
      ++v28;
    while ( *((_BYTE *)v27 + v28) );
    v29 = v28 + 1;
  }
  else
  {
    v27 = &byte_140015CE0;
    v29 = 1;
  }
  v97 = v29;
  v30 = 2;
  v94 = a21;
  v92 = a20;
  v96 = v27;
  v98 = 0;
  v95 = 4;
  v31 = *a19;
  v93 = 4;
  if ( v31 )
  {
    v32 = -1;
    do
      ++v32;
    while ( *((_WORD *)v31 + v32) );
    v33 = 2 * v32 + 2;
  }
  else
  {
    v31 = &dword_140015CE4;
    v33 = 2;
  }
  v90 = v33;
  v89 = v31;
  v91 = 0;
  v34 = *a18;
  if ( *a18 )
  {
    v35 = -1;
    do
      ++v35;
    while ( *((_BYTE *)v34 + v35) );
    v36 = v35 + 1;
  }
  else
  {
    v34 = &byte_140015CE0;
    v36 = 1;
  }
  v87 = v36;
  v84 = a17;
  v86 = v34;
  v88 = 0;
  v85 = 4;
  v37 = *a16;
  if ( *a16 )
  {
    v38 = -1;
    do
      ++v38;
    while ( *((_WORD *)v37 + v38) );
    v39 = 2 * v38 + 2;
  }
  else
  {
    v37 = &dword_140015CE4;
    v39 = 2;
  }
  v82 = v39;
  v81 = v37;
  v83 = 0;
  v40 = *a15;
  if ( *a15 )
  {
    v41 = -1;
    do
      ++v41;
    while ( *((_BYTE *)v40 + v41) );
    v42 = v41 + 1;
  }
  else
  {
    v40 = &byte_140015CE0;
    v42 = 1;
  }
  v79 = v42;
  v76 = a14;
  v78 = v40;
  v80 = 0;
  v77 = 4;
  v43 = *a13;
  if ( *a13 )
  {
    v44 = -1;
    do
      ++v44;
    while ( *((_BYTE *)v43 + v44) );
    v45 = v44 + 1;
  }
  else
  {
    v43 = &byte_140015CE0;
    v45 = 1;
  }
  v74 = v45;
  v71 = a12;
  v73 = v43;
  v75 = 0;
  v72 = 4;
  v46 = *a11;
  if ( *a11 )
  {
    v47 = -1;
    do
      ++v47;
    while ( *((_WORD *)v46 + v47) );
    v30 = 2 * v47 + 2;
  }
  else
  {
    v46 = &dword_140015CE4;
  }
  v66 = a10;
  v68 = v46;
  v69 = v30;
  v70 = 0;
  v48 = *a9;
  v67 = 4;
  if ( v48 )
  {
    v49 = -1;
    do
      ++v49;
    while ( *((_BYTE *)v48 + v49) );
    v50 = v49 + 1;
  }
  else
  {
    v48 = &byte_140015CE0;
    v50 = 1;
  }
  v64 = v50;
  v61 = a8;
  v63 = v48;
  v65 = 0;
  v62 = 4;
  v51 = *a7;
  if ( *a7 )
  {
    do
      ++v24;
    while ( *((_BYTE *)v51 + v24) );
    v26 = v24 + 1;
  }
  else
  {
    v51 = &byte_140015CE0;
  }
  v56 = a6;
  v54 = a5;
  v58 = v51;
  v59 = v26;
  v60 = 0;
  v57 = 4;
  v55 = 8;
  return tlgWriteTransfer_EventWriteTransfer(a1, a2, a3, 0, 0x14u, &v53);
}

```

## disassembly

```asm
0x140001364  push    rbp
0x140001366  push    rbx
0x140001367  push    rsi
0x140001368  push    rdi
0x140001369  push    r15
0x14000136b  lea     rbp, [rsp-80h]
0x140001370  sub     rsp, 180h
0x140001377  mov     rax, cs:__security_cookie
0x14000137e  xor     rax, rsp
0x140001381  mov     [rbp+0A0h+var_30], rax
0x140001385  mov     rax, [rbp+0A0h+arg_A8]
0x14000138c  lea     rsi, byte_140015CE0
0x140001393  mov     r11, rdx
0x140001396  mov     r10, rcx
0x140001399  or      rdx, 0FFFFFFFFFFFFFFFFh
0x14000139d  xor     edi, edi
0x14000139f  mov     rbx, r8
0x1400013a2  mov     r8d, 1
0x1400013a8  mov     rcx, [rax]
0x1400013ab  test    rcx, rcx
0x1400013ae  jz      short loc_1400013C0
0x1400013b0  mov     rax, rdx
0x1400013b3  inc     rax
0x1400013b6  cmp     [rcx+rax], dil
0x1400013ba  jnz     short loc_1400013B3
0x1400013bc  inc     eax
0x1400013be  jmp     short loc_1400013C6
0x1400013c0  mov     rcx, rsi
0x1400013c3  mov     eax, r8d
0x1400013c6  mov     [rbp+0A0h+var_38], eax
0x1400013c9  mov     r9d, 2
0x1400013cf  mov     rax, [rbp+0A0h+arg_A0]
0x1400013d6  mov     [rbp+0A0h+var_50], rax
0x1400013da  mov     rax, [rbp+0A0h+arg_98]
0x1400013e1  mov     [rbp+0A0h+var_60], rax
0x1400013e5  mov     rax, [rbp+0A0h+arg_90]
0x1400013ec  mov     [rbp+0A0h+var_40], rcx
0x1400013f0  mov     [rbp+0A0h+var_34], edi
0x1400013f3  mov     [rbp+0A0h+var_48], 4
0x1400013fb  mov     rcx, [rax]
0x1400013fe  mov     [rbp+0A0h+var_58], 4
0x140001406  test    rcx, rcx
0x140001409  jz      short loc_140001420
0x14000140b  mov     rax, rdx
0x14000140e  inc     rax
0x140001411  cmp     [rcx+rax*2], di
0x140001415  jnz     short loc_14000140E
0x140001417  lea     eax, ds:2[rax*2]
0x14000141e  jmp     short loc_14000142A
0x140001420  lea     rcx, dword_140015CE4
0x140001427  mov     eax, r9d
0x14000142a  mov     [rbp+0A0h+var_68], eax
0x14000142d  mov     rax, [rbp+0A0h+arg_88]
0x140001434  mov     [rbp+0A0h+var_70], rcx
0x140001438  mov     [rbp+0A0h+var_64], edi
0x14000143b  mov     rcx, [rax]
0x14000143e  test    rcx, rcx
0x140001441  jz      short loc_140001453
0x140001443  mov     rax, rdx
0x140001446  inc     rax
0x140001449  cmp     [rcx+rax], dil
0x14000144d  jnz     short loc_140001446
0x14000144f  inc     eax
0x140001451  jmp     short loc_140001459
0x140001453  mov     rcx, rsi
0x140001456  mov     eax, r8d
0x140001459  mov     [rbp+0A0h+var_78], eax
0x14000145c  mov     rax, [rbp+0A0h+arg_80]
0x140001463  mov     [rbp+0A0h+var_90], rax
0x140001467  mov     rax, [rbp+0A0h+arg_78]
0x14000146e  mov     [rbp+0A0h+var_80], rcx
0x140001472  mov     [rbp+0A0h+var_74], edi
0x140001475  mov     [rbp+0A0h+var_88], 4
0x14000147d  mov     rcx, [rax]
0x140001480  test    rcx, rcx
0x140001483  jz      short loc_14000149A
0x140001485  mov     rax, rdx
0x140001488  inc     rax
0x14000148b  cmp     [rcx+rax*2], di
0x14000148f  jnz     short loc_140001488
0x140001491  lea     eax, ds:2[rax*2]
0x140001498  jmp     short loc_1400014A4
0x14000149a  lea     rcx, dword_140015CE4
0x1400014a1  mov     eax, r9d
0x1400014a4  mov     [rbp+0A0h+var_98], eax
0x1400014a7  mov     rax, [rbp+0A0h+arg_70]
0x1400014ae  mov     [rbp+0A0h+var_A0], rcx
0x1400014b2  mov     [rbp+0A0h+var_94], edi
0x1400014b5  mov     rcx, [rax]
0x1400014b8  test    rcx, rcx
0x1400014bb  jz      short loc_1400014CD
0x1400014bd  mov     rax, rdx
0x1400014c0  inc     rax
0x1400014c3  cmp     [rcx+rax], dil
0x1400014c7  jnz     short loc_1400014C0
0x1400014c9  inc     eax
0x1400014cb  jmp     short loc_1400014D3
0x1400014cd  mov     rcx, rsi
0x1400014d0  mov     eax, r8d
0x1400014d3  mov     [rbp+0A0h+var_A8], eax
0x1400014d6  mov     rax, [rbp+0A0h+arg_68]
0x1400014dd  mov     [rbp+0A0h+var_C0], rax
0x1400014e1  mov     rax, [rbp+0A0h+arg_60]
0x1400014e8  mov     [rbp+0A0h+var_B0], rcx
0x1400014ec  mov     [rbp+0A0h+var_A4], edi
0x1400014ef  mov     [rbp+0A0h+var_B8], 4
0x1400014f7  mov     rcx, [rax]
0x1400014fa  test    rcx, rcx
0x1400014fd  jz      short loc_14000150F
0x1400014ff  mov     rax, rdx
0x140001502  inc     rax
0x140001505  cmp     [rcx+rax], dil
0x140001509  jnz     short loc_140001502
0x14000150b  inc     eax
0x14000150d  jmp     short loc_140001515
0x14000150f  mov     rcx, rsi
0x140001512  mov     eax, r8d
0x140001515  mov     [rbp+0A0h+var_C8], eax
0x140001518  mov     rax, [rbp+0A0h+arg_58]
0x14000151f  mov     [rbp+0A0h+var_E0], rax
0x140001523  mov     rax, [rbp+0A0h+arg_50]
0x14000152a  mov     [rbp+0A0h+var_D0], rcx
0x14000152e  mov     [rbp+0A0h+var_C4], edi
0x140001531  mov     [rbp+0A0h+var_D8], 4
0x140001539  mov     rcx, [rax]
0x14000153c  test    rcx, rcx
0x14000153f  jz      short loc_140001557
0x140001541  mov     rax, rdx
0x140001544  inc     rax
0x140001547  cmp     [rcx+rax*2], di
0x14000154b  jnz     short loc_140001544
0x14000154d  lea     r9d, ds:2[rax*2]
0x140001555  jmp     short loc_14000155E
0x140001557  lea     rcx, dword_140015CE4
0x14000155e  mov     rax, [rbp+0A0h+arg_48]
0x140001565  mov     [rbp+0A0h+var_100], rax
0x140001569  mov     rax, [rbp+0A0h+arg_40]
0x140001570  mov     [rbp+0A0h+var_F0], rcx
0x140001574  mov     [rbp+0A0h+var_E8], r9d
0x140001578  mov     [rbp+0A0h+var_E4], edi
0x14000157b  mov     rcx, [rax]
0x14000157e  mov     [rbp+0A0h+var_F8], 4
0x140001586  test    rcx, rcx
0x140001589  jz      short loc_14000159B
0x14000158b  mov     rax, rdx
0x14000158e  inc     rax
0x140001591  cmp     [rcx+rax], dil
0x140001595  jnz     short loc_14000158E
0x140001597  inc     eax
0x140001599  jmp     short loc_1400015A1
0x14000159b  mov     rcx, rsi
0x14000159e  mov     eax, r8d
0x1400015a1  mov     [rbp+0A0h+var_108], eax
0x1400015a4  mov     rax, [rbp+0A0h+arg_38]
0x1400015ab  mov     [rbp+0A0h+var_120], rax
0x1400015af  mov     rax, [rbp+0A0h+arg_30]
0x1400015b6  mov     [rbp+0A0h+var_110], rcx
0x1400015ba  mov     [rbp+0A0h+var_104], edi
0x1400015bd  mov     [rbp+0A0h+var_118], 4
0x1400015c5  mov     rcx, [rax]
0x1400015c8  test    rcx, rcx
0x1400015cb  jz      short loc_1400015DC
0x1400015cd  inc     rdx
0x1400015d0  cmp     [rcx+rdx], dil
0x1400015d4  jnz     short loc_1400015CD
0x1400015d6  lea     r8d, [rdx+1]
0x1400015da  jmp     short loc_1400015DF
0x1400015dc  mov     rcx, rsi
0x1400015df  mov     rax, [rbp+0A0h+arg_28]
0x1400015e6  xor     r9d, r9d
0x1400015e9  mov     [rsp+1A0h+var_140], rax
0x1400015ee  mov     rdx, r11
0x1400015f1  mov     rax, [rbp+0A0h+arg_20]
0x1400015f8  mov     [rsp+1A0h+var_150], rax
0x1400015fd  lea     rax, [rsp+1A0h+var_170]
0x140001602  mov     [rsp+1A0h+var_130], rcx
0x140001607  mov     rcx, r10
0x14000160a  mov     [rsp+1A0h+var_128], r8d
0x14000160f  mov     r8, rbx
0x140001612  mov     [rsp+1A0h+var_178], rax
0x140001617  mov     [rsp+1A0h+var_180], 14h
0x14000161f  mov     [rsp+1A0h+var_124], edi
0x140001623  mov     [rsp+1A0h+var_138], 4
0x14000162c  mov     [rsp+1A0h+var_148], 8
0x140001635  call    _tlgWriteTransfer_EventWriteTransfer
0x14000163a  mov     rcx, [rbp+0A0h+var_30]
0x14000163e  xor     rcx, rsp; StackCookie
0x140001641  call    __security_check_cookie
0x140001646  add     rsp, 180h
0x14000164d  pop     r15
0x14000164f  pop     rdi
0x140001650  pop     rsi
0x140001651  pop     rbx
0x140001652  pop     rbp
0x140001653  retn
```
