# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)

- ea: `0x1800012bc`
- end: `0x1800015ac`
- name: `??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456445@Z`
- size: `752`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18000b49c`

## callees

- `0x1800012bc`
- `0x180001640`
- `0x18000d1c0`

## pseudocode

```c
ULONG __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        __int64 a1,
        unsigned __int8 *a2,
        __int64 a3,
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
  int v25; // r8d
  const unsigned __int16 *v26; // rcx
  __int64 v27; // rax
  int v28; // eax
  int v29; // r9d
  int *v30; // rcx
  __int64 v31; // rax
  int v32; // eax
  const unsigned __int16 *v33; // rcx
  __int64 v34; // rax
  int v35; // eax
  int *v36; // rcx
  __int64 v37; // rax
  int v38; // eax
  const unsigned __int16 *v39; // rcx
  __int64 v40; // rax
  int v41; // eax
  const unsigned __int16 *v42; // rcx
  __int64 v43; // rax
  int v44; // eax
  int *v45; // rcx
  __int64 v46; // rax
  const unsigned __int16 *v47; // rcx
  __int64 v48; // rax
  int v49; // eax
  const unsigned __int16 *v50; // rcx
  struct _EVENT_DATA_DESCRIPTOR v52; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v53; // [rsp+50h] [rbp-B0h]
  __int64 v54; // [rsp+58h] [rbp-A8h]
  __int64 v55; // [rsp+60h] [rbp-A0h]
  __int64 v56; // [rsp+68h] [rbp-98h]
  const unsigned __int16 *v57; // [rsp+70h] [rbp-90h]
  int v58; // [rsp+78h] [rbp-88h]
  int v59; // [rsp+7Ch] [rbp-84h]
  __int64 v60; // [rsp+80h] [rbp-80h]
  __int64 v61; // [rsp+88h] [rbp-78h]
  const unsigned __int16 *v62; // [rsp+90h] [rbp-70h]
  int v63; // [rsp+98h] [rbp-68h]
  int v64; // [rsp+9Ch] [rbp-64h]
  __int64 v65; // [rsp+A0h] [rbp-60h]
  __int64 v66; // [rsp+A8h] [rbp-58h]
  int *v67; // [rsp+B0h] [rbp-50h]
  int v68; // [rsp+B8h] [rbp-48h]
  int v69; // [rsp+BCh] [rbp-44h]
  __int64 v70; // [rsp+C0h] [rbp-40h]
  __int64 v71; // [rsp+C8h] [rbp-38h]
  const unsigned __int16 *v72; // [rsp+D0h] [rbp-30h]
  int v73; // [rsp+D8h] [rbp-28h]
  int v74; // [rsp+DCh] [rbp-24h]
  __int64 v75; // [rsp+E0h] [rbp-20h]
  __int64 v76; // [rsp+E8h] [rbp-18h]
  const unsigned __int16 *v77; // [rsp+F0h] [rbp-10h]
  int v78; // [rsp+F8h] [rbp-8h]
  int v79; // [rsp+FCh] [rbp-4h]
  int *v80; // [rsp+100h] [rbp+0h]
  int v81; // [rsp+108h] [rbp+8h]
  int v82; // [rsp+10Ch] [rbp+Ch]
  __int64 v83; // [rsp+110h] [rbp+10h]
  __int64 v84; // [rsp+118h] [rbp+18h]
  const unsigned __int16 *v85; // [rsp+120h] [rbp+20h]
  int v86; // [rsp+128h] [rbp+28h]
  int v87; // [rsp+12Ch] [rbp+2Ch]
  int *v88; // [rsp+130h] [rbp+30h]
  int v89; // [rsp+138h] [rbp+38h]
  int v90; // [rsp+13Ch] [rbp+3Ch]
  __int64 v91; // [rsp+140h] [rbp+40h]
  __int64 v92; // [rsp+148h] [rbp+48h]
  __int64 v93; // [rsp+150h] [rbp+50h]
  __int64 v94; // [rsp+158h] [rbp+58h]
  const unsigned __int16 *v95; // [rsp+160h] [rbp+60h]
  int v96; // [rsp+168h] [rbp+68h]
  int v97; // [rsp+16Ch] [rbp+6Ch]

  v24 = -1;
  v25 = 1;
  v26 = *a22;
  if ( *a22 )
  {
    v27 = -1;
    do
      ++v27;
    while ( *((_BYTE *)v26 + v27) );
    v28 = v27 + 1;
  }
  else
  {
    v26 = &dword_18001424C;
    v28 = 1;
  }
  v96 = v28;
  v29 = 2;
  v93 = a21;
  v91 = a20;
  v95 = v26;
  v97 = 0;
  v94 = 4;
  v30 = *a19;
  v92 = 4;
  if ( v30 )
  {
    v31 = -1;
    do
      ++v31;
    while ( *((_WORD *)v30 + v31) );
    v32 = 2 * v31 + 2;
  }
  else
  {
    v30 = &dword_180014224;
    v32 = 2;
  }
  v89 = v32;
  v88 = v30;
  v90 = 0;
  v33 = *a18;
  if ( *a18 )
  {
    v34 = -1;
    do
      ++v34;
    while ( *((_BYTE *)v33 + v34) );
    v35 = v34 + 1;
  }
  else
  {
    v33 = &dword_18001424C;
    v35 = 1;
  }
  v86 = v35;
  v83 = a17;
  v85 = v33;
  v87 = 0;
  v84 = 4;
  v36 = *a16;
  if ( *a16 )
  {
    v37 = -1;
    do
      ++v37;
    while ( *((_WORD *)v36 + v37) );
    v38 = 2 * v37 + 2;
  }
  else
  {
    v36 = &dword_180014224;
    v38 = 2;
  }
  v81 = v38;
  v80 = v36;
  v82 = 0;
  v39 = *a15;
  if ( *a15 )
  {
    v40 = -1;
    do
      ++v40;
    while ( *((_BYTE *)v39 + v40) );
    v41 = v40 + 1;
  }
  else
  {
    v39 = &dword_18001424C;
    v41 = 1;
  }
  v78 = v41;
  v75 = a14;
  v77 = v39;
  v79 = 0;
  v76 = 4;
  v42 = *a13;
  if ( *a13 )
  {
    v43 = -1;
    do
      ++v43;
    while ( *((_BYTE *)v42 + v43) );
    v44 = v43 + 1;
  }
  else
  {
    v42 = &dword_18001424C;
    v44 = 1;
  }
  v73 = v44;
  v70 = a12;
  v72 = v42;
  v74 = 0;
  v71 = 4;
  v45 = *a11;
  if ( *a11 )
  {
    v46 = -1;
    do
      ++v46;
    while ( *((_WORD *)v45 + v46) );
    v29 = 2 * v46 + 2;
  }
  else
  {
    v45 = &dword_180014224;
  }
  v65 = a10;
  v67 = v45;
  v68 = v29;
  v69 = 0;
  v47 = *a9;
  v66 = 4;
  if ( v47 )
  {
    v48 = -1;
    do
      ++v48;
    while ( *((_BYTE *)v47 + v48) );
    v49 = v48 + 1;
  }
  else
  {
    v47 = &dword_18001424C;
    v49 = 1;
  }
  v63 = v49;
  v60 = a8;
  v62 = v47;
  v64 = 0;
  v61 = 4;
  v50 = *a7;
  if ( *a7 )
  {
    do
      ++v24;
    while ( *((_BYTE *)v50 + v24) );
    v25 = v24 + 1;
  }
  else
  {
    v50 = &dword_18001424C;
  }
  v55 = a6;
  v53 = a5;
  v57 = v50;
  v58 = v25;
  v59 = 0;
  v56 = 4;
  v54 = 8;
  return tlgWriteTransfer_EventWriteTransfer(a1, a2, 0, 0, 0x14u, &v52);
}

```

## disassembly

```asm
0x1800012bc  mov     [rsp-8+arg_10], rbx
0x1800012c1  push    rbp
0x1800012c2  push    rdi
0x1800012c3  push    r14
0x1800012c5  lea     rbp, [rsp-80h]
0x1800012ca  sub     rsp, 180h
0x1800012d1  mov     rax, cs:__security_cookie
0x1800012d8  xor     rax, rsp
0x1800012db  mov     [rbp+90h+var_20], rax
0x1800012df  mov     rax, [rbp+90h+arg_A8]
0x1800012e6  lea     rdi, dword_18001424C
0x1800012ed  mov     r11, rdx
0x1800012f0  mov     r10, rcx
0x1800012f3  or      rdx, 0FFFFFFFFFFFFFFFFh
0x1800012f7  xor     ebx, ebx
0x1800012f9  mov     r8d, 1
0x1800012ff  mov     rcx, [rax]
0x180001302  test    rcx, rcx
0x180001305  jz      short loc_180001316
0x180001307  mov     rax, rdx
0x18000130a  inc     rax
0x18000130d  cmp     [rcx+rax], bl
0x180001310  jnz     short loc_18000130A
0x180001312  inc     eax
0x180001314  jmp     short loc_18000131C
0x180001316  mov     rcx, rdi
0x180001319  mov     eax, r8d
0x18000131c  mov     [rbp+90h+var_28], eax
0x18000131f  mov     r9d, 2
0x180001325  mov     rax, [rbp+90h+arg_A0]
0x18000132c  mov     [rbp+90h+var_40], rax
0x180001330  mov     rax, [rbp+90h+arg_98]
0x180001337  mov     [rbp+90h+var_50], rax
0x18000133b  mov     rax, [rbp+90h+arg_90]
0x180001342  mov     [rbp+90h+var_30], rcx
0x180001346  mov     [rbp+90h+var_24], ebx
0x180001349  mov     [rbp+90h+var_38], 4
0x180001351  mov     rcx, [rax]
0x180001354  mov     [rbp+90h+var_48], 4
0x18000135c  test    rcx, rcx
0x18000135f  jz      short loc_180001376
0x180001361  mov     rax, rdx
0x180001364  inc     rax
0x180001367  cmp     [rcx+rax*2], bx
0x18000136b  jnz     short loc_180001364
0x18000136d  lea     eax, ds:2[rax*2]
0x180001374  jmp     short loc_180001380
0x180001376  lea     rcx, dword_180014224
0x18000137d  mov     eax, r9d
0x180001380  mov     [rbp+90h+var_58], eax
0x180001383  mov     rax, [rbp+90h+arg_88]
0x18000138a  mov     [rbp+90h+var_60], rcx
0x18000138e  mov     [rbp+90h+var_54], ebx
0x180001391  mov     rcx, [rax]
0x180001394  test    rcx, rcx
0x180001397  jz      short loc_1800013A8
0x180001399  mov     rax, rdx
0x18000139c  inc     rax
0x18000139f  cmp     [rcx+rax], bl
0x1800013a2  jnz     short loc_18000139C
0x1800013a4  inc     eax
0x1800013a6  jmp     short loc_1800013AE
0x1800013a8  mov     rcx, rdi
0x1800013ab  mov     eax, r8d
0x1800013ae  mov     [rbp+90h+var_68], eax
0x1800013b1  mov     rax, [rbp+90h+arg_80]
0x1800013b8  mov     [rbp+90h+var_80], rax
0x1800013bc  mov     rax, [rbp+90h+arg_78]
0x1800013c3  mov     [rbp+90h+var_70], rcx
0x1800013c7  mov     [rbp+90h+var_64], ebx
0x1800013ca  mov     [rbp+90h+var_78], 4
0x1800013d2  mov     rcx, [rax]
0x1800013d5  test    rcx, rcx
0x1800013d8  jz      short loc_1800013EF
0x1800013da  mov     rax, rdx
0x1800013dd  inc     rax
0x1800013e0  cmp     [rcx+rax*2], bx
0x1800013e4  jnz     short loc_1800013DD
0x1800013e6  lea     eax, ds:2[rax*2]
0x1800013ed  jmp     short loc_1800013F9
0x1800013ef  lea     rcx, dword_180014224
0x1800013f6  mov     eax, r9d
0x1800013f9  mov     [rbp+90h+var_88], eax
0x1800013fc  mov     rax, [rbp+90h+arg_70]
0x180001403  mov     [rbp+90h+var_90], rcx
0x180001407  mov     [rbp+90h+var_84], ebx
0x18000140a  mov     rcx, [rax]
0x18000140d  test    rcx, rcx
0x180001410  jz      short loc_180001421
0x180001412  mov     rax, rdx
0x180001415  inc     rax
0x180001418  cmp     [rcx+rax], bl
0x18000141b  jnz     short loc_180001415
0x18000141d  inc     eax
0x18000141f  jmp     short loc_180001427
0x180001421  mov     rcx, rdi
0x180001424  mov     eax, r8d
0x180001427  mov     [rbp+90h+var_98], eax
0x18000142a  mov     rax, [rbp+90h+arg_68]
0x180001431  mov     [rbp+90h+var_B0], rax
0x180001435  mov     rax, [rbp+90h+arg_60]
0x18000143c  mov     [rbp+90h+var_A0], rcx
0x180001440  mov     [rbp+90h+var_94], ebx
0x180001443  mov     [rbp+90h+var_A8], 4
0x18000144b  mov     rcx, [rax]
0x18000144e  test    rcx, rcx
0x180001451  jz      short loc_180001462
0x180001453  mov     rax, rdx
0x180001456  inc     rax
0x180001459  cmp     [rcx+rax], bl
0x18000145c  jnz     short loc_180001456
0x18000145e  inc     eax
0x180001460  jmp     short loc_180001468
0x180001462  mov     rcx, rdi
0x180001465  mov     eax, r8d
0x180001468  mov     [rbp+90h+var_B8], eax
0x18000146b  mov     rax, [rbp+90h+arg_58]
0x180001472  mov     [rbp+90h+var_D0], rax
0x180001476  mov     rax, [rbp+90h+arg_50]
0x18000147d  mov     [rbp+90h+var_C0], rcx
0x180001481  mov     [rbp+90h+var_B4], ebx
0x180001484  mov     [rbp+90h+var_C8], 4
0x18000148c  mov     rcx, [rax]
0x18000148f  test    rcx, rcx
0x180001492  jz      short loc_1800014AA
0x180001494  mov     rax, rdx
0x180001497  inc     rax
0x18000149a  cmp     [rcx+rax*2], bx
0x18000149e  jnz     short loc_180001497
0x1800014a0  lea     r9d, ds:2[rax*2]
0x1800014a8  jmp     short loc_1800014B1
0x1800014aa  lea     rcx, dword_180014224
0x1800014b1  mov     rax, [rbp+90h+arg_48]
0x1800014b8  mov     [rbp+90h+var_F0], rax
0x1800014bc  mov     rax, [rbp+90h+arg_40]
0x1800014c3  mov     [rbp+90h+var_E0], rcx
0x1800014c7  mov     [rbp+90h+var_D8], r9d
0x1800014cb  mov     [rbp+90h+var_D4], ebx
0x1800014ce  mov     rcx, [rax]
0x1800014d1  mov     [rbp+90h+var_E8], 4
0x1800014d9  test    rcx, rcx
0x1800014dc  jz      short loc_1800014ED
0x1800014de  mov     rax, rdx
0x1800014e1  inc     rax
0x1800014e4  cmp     [rcx+rax], bl
0x1800014e7  jnz     short loc_1800014E1
0x1800014e9  inc     eax
0x1800014eb  jmp     short loc_1800014F3
0x1800014ed  mov     rcx, rdi
0x1800014f0  mov     eax, r8d
0x1800014f3  mov     [rbp+90h+var_F8], eax
0x1800014f6  mov     rax, [rbp+90h+arg_38]
0x1800014fd  mov     [rbp+90h+var_110], rax
0x180001501  mov     rax, [rbp+90h+arg_30]
0x180001508  mov     [rbp+90h+var_100], rcx
0x18000150c  mov     [rbp+90h+var_F4], ebx
0x18000150f  mov     [rbp+90h+var_108], 4
0x180001517  mov     rcx, [rax]
0x18000151a  test    rcx, rcx
0x18000151d  jz      short loc_18000152D
0x18000151f  inc     rdx
0x180001522  cmp     [rcx+rdx], bl
0x180001525  jnz     short loc_18000151F
0x180001527  lea     r8d, [rdx+1]
0x18000152b  jmp     short loc_180001530
0x18000152d  mov     rcx, rdi
0x180001530  mov     rax, [rbp+90h+arg_28]
0x180001537  xor     r9d, r9d
0x18000153a  mov     [rsp+190h+var_130], rax
0x18000153f  mov     rdx, r11
0x180001542  mov     rax, [rbp+90h+arg_20]
0x180001549  mov     [rsp+190h+var_140], rax
0x18000154e  lea     rax, [rsp+190h+var_160]
0x180001553  mov     [rsp+190h+var_120], rcx
0x180001558  mov     rcx, r10
0x18000155b  mov     [rsp+190h+var_118], r8d
0x180001560  xor     r8d, r8d
0x180001563  mov     [rsp+190h+var_168], rax
0x180001568  mov     [rsp+190h+var_170], 14h
0x180001570  mov     [rsp+190h+var_114], ebx
0x180001574  mov     [rsp+190h+var_128], 4
0x18000157d  mov     [rsp+190h+var_138], 8
0x180001586  call    _tlgWriteTransfer_EventWriteTransfer
0x18000158b  mov     rcx, [rbp+90h+var_20]
0x18000158f  xor     rcx, rsp; StackCookie
0x180001592  call    __security_check_cookie
0x180001597  mov     rbx, [rsp+190h+arg_10]
0x18000159f  add     rsp, 180h
0x1800015a6  pop     r14
0x1800015a8  pop     rdi
0x1800015a9  pop     rbp
0x1800015aa  retn
```
