# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)

- ea: `0x1800013b4`
- end: `0x1800016a3`
- name: `??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@_W@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@_W@@45456456445@Z`
- size: `751`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18001c9ec`

## callees

- `0x1800013b4`
- `0x180001838`
- `0x180014130`

## pseudocode

```c
ULONG __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        __int64 a1,
        unsigned __int8 *a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        const wchar_t **a7,
        __int64 a8,
        const wchar_t **a9,
        __int64 a10,
        __int64 **a11,
        __int64 a12,
        const wchar_t **a13,
        __int64 a14,
        const wchar_t **a15,
        __int64 **a16,
        __int64 a17,
        const wchar_t **a18,
        __int64 **a19,
        __int64 a20,
        __int64 a21,
        const wchar_t **a22)
{
  __int64 v24; // rdx
  int v25; // r8d
  const wchar_t *v26; // rcx
  __int64 v27; // rax
  int v28; // eax
  int v29; // r9d
  __int64 *v30; // rcx
  __int64 v31; // rax
  int v32; // eax
  const wchar_t *v33; // rcx
  __int64 v34; // rax
  int v35; // eax
  __int64 *v36; // rcx
  __int64 v37; // rax
  int v38; // eax
  const wchar_t *v39; // rcx
  __int64 v40; // rax
  int v41; // eax
  const wchar_t *v42; // rcx
  __int64 v43; // rax
  int v44; // eax
  __int64 *v45; // rcx
  __int64 v46; // rax
  const wchar_t *v47; // rcx
  __int64 v48; // rax
  int v49; // eax
  const wchar_t *v50; // rcx
  struct _EVENT_DATA_DESCRIPTOR v52; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v53; // [rsp+50h] [rbp-B0h]
  __int64 v54; // [rsp+58h] [rbp-A8h]
  __int64 v55; // [rsp+60h] [rbp-A0h]
  __int64 v56; // [rsp+68h] [rbp-98h]
  const wchar_t *v57; // [rsp+70h] [rbp-90h]
  int v58; // [rsp+78h] [rbp-88h]
  int v59; // [rsp+7Ch] [rbp-84h]
  __int64 v60; // [rsp+80h] [rbp-80h]
  __int64 v61; // [rsp+88h] [rbp-78h]
  const wchar_t *v62; // [rsp+90h] [rbp-70h]
  int v63; // [rsp+98h] [rbp-68h]
  int v64; // [rsp+9Ch] [rbp-64h]
  __int64 v65; // [rsp+A0h] [rbp-60h]
  __int64 v66; // [rsp+A8h] [rbp-58h]
  __int64 *v67; // [rsp+B0h] [rbp-50h]
  int v68; // [rsp+B8h] [rbp-48h]
  int v69; // [rsp+BCh] [rbp-44h]
  __int64 v70; // [rsp+C0h] [rbp-40h]
  __int64 v71; // [rsp+C8h] [rbp-38h]
  const wchar_t *v72; // [rsp+D0h] [rbp-30h]
  int v73; // [rsp+D8h] [rbp-28h]
  int v74; // [rsp+DCh] [rbp-24h]
  __int64 v75; // [rsp+E0h] [rbp-20h]
  __int64 v76; // [rsp+E8h] [rbp-18h]
  const wchar_t *v77; // [rsp+F0h] [rbp-10h]
  int v78; // [rsp+F8h] [rbp-8h]
  int v79; // [rsp+FCh] [rbp-4h]
  __int64 *v80; // [rsp+100h] [rbp+0h]
  int v81; // [rsp+108h] [rbp+8h]
  int v82; // [rsp+10Ch] [rbp+Ch]
  __int64 v83; // [rsp+110h] [rbp+10h]
  __int64 v84; // [rsp+118h] [rbp+18h]
  const wchar_t *v85; // [rsp+120h] [rbp+20h]
  int v86; // [rsp+128h] [rbp+28h]
  int v87; // [rsp+12Ch] [rbp+2Ch]
  __int64 *v88; // [rsp+130h] [rbp+30h]
  int v89; // [rsp+138h] [rbp+38h]
  int v90; // [rsp+13Ch] [rbp+3Ch]
  __int64 v91; // [rsp+140h] [rbp+40h]
  __int64 v92; // [rsp+148h] [rbp+48h]
  __int64 v93; // [rsp+150h] [rbp+50h]
  __int64 v94; // [rsp+158h] [rbp+58h]
  const wchar_t *v95; // [rsp+160h] [rbp+60h]
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
    v26 = &dword_18003138C;
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
    v30 = qword_180031880;
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
    v33 = &dword_18003138C;
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
    v36 = qword_180031880;
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
    v39 = &dword_18003138C;
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
    v42 = &dword_18003138C;
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
    v45 = qword_180031880;
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
    v47 = &dword_18003138C;
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
    v50 = &dword_18003138C;
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
0x1800013b4  mov     [rsp-8+arg_10], rbx
0x1800013b9  push    rbp
0x1800013ba  push    rdi
0x1800013bb  push    r14
0x1800013bd  lea     rbp, [rsp-80h]
0x1800013c2  sub     rsp, 180h
0x1800013c9  mov     rax, cs:__security_cookie
0x1800013d0  xor     rax, rsp
0x1800013d3  mov     [rbp+90h+var_20], rax
0x1800013d7  mov     rax, [rbp+90h+arg_A8]
0x1800013de  lea     rdi, dword_18003138C
0x1800013e5  mov     r11, rdx
0x1800013e8  mov     r10, rcx
0x1800013eb  or      rdx, 0FFFFFFFFFFFFFFFFh
0x1800013ef  xor     ebx, ebx
0x1800013f1  mov     r8d, 1
0x1800013f7  mov     rcx, [rax]
0x1800013fa  test    rcx, rcx
0x1800013fd  jz      short loc_18000140E
0x1800013ff  mov     rax, rdx
0x180001402  inc     rax
0x180001405  cmp     [rcx+rax], bl
0x180001408  jnz     short loc_180001402
0x18000140a  inc     eax
0x18000140c  jmp     short loc_180001414
0x18000140e  mov     rcx, rdi
0x180001411  mov     eax, r8d
0x180001414  mov     [rbp+90h+var_28], eax
0x180001417  mov     r9d, 2
0x18000141d  mov     rax, [rbp+90h+arg_A0]
0x180001424  mov     [rbp+90h+var_40], rax
0x180001428  mov     rax, [rbp+90h+arg_98]
0x18000142f  mov     [rbp+90h+var_50], rax
0x180001433  mov     rax, [rbp+90h+arg_90]
0x18000143a  mov     [rbp+90h+var_30], rcx
0x18000143e  mov     [rbp+90h+var_24], ebx
0x180001441  mov     [rbp+90h+var_38], 4
0x180001449  mov     rcx, [rax]
0x18000144c  mov     [rbp+90h+var_48], 4
0x180001454  test    rcx, rcx
0x180001457  jz      short loc_18000146E
0x180001459  mov     rax, rdx
0x18000145c  inc     rax
0x18000145f  cmp     [rcx+rax*2], bx
0x180001463  jnz     short loc_18000145C
0x180001465  lea     eax, ds:2[rax*2]
0x18000146c  jmp     short loc_180001478
0x18000146e  lea     rcx, qword_180031880
0x180001475  mov     eax, r9d
0x180001478  mov     [rbp+90h+var_58], eax
0x18000147b  mov     rax, [rbp+90h+arg_88]
0x180001482  mov     [rbp+90h+var_60], rcx
0x180001486  mov     [rbp+90h+var_54], ebx
0x180001489  mov     rcx, [rax]
0x18000148c  test    rcx, rcx
0x18000148f  jz      short loc_1800014A0
0x180001491  mov     rax, rdx
0x180001494  inc     rax
0x180001497  cmp     [rcx+rax], bl
0x18000149a  jnz     short loc_180001494
0x18000149c  inc     eax
0x18000149e  jmp     short loc_1800014A6
0x1800014a0  mov     rcx, rdi
0x1800014a3  mov     eax, r8d
0x1800014a6  mov     [rbp+90h+var_68], eax
0x1800014a9  mov     rax, [rbp+90h+arg_80]
0x1800014b0  mov     [rbp+90h+var_80], rax
0x1800014b4  mov     rax, [rbp+90h+arg_78]
0x1800014bb  mov     [rbp+90h+var_70], rcx
0x1800014bf  mov     [rbp+90h+var_64], ebx
0x1800014c2  mov     [rbp+90h+var_78], 4
0x1800014ca  mov     rcx, [rax]
0x1800014cd  test    rcx, rcx
0x1800014d0  jz      short loc_1800014E7
0x1800014d2  mov     rax, rdx
0x1800014d5  inc     rax
0x1800014d8  cmp     [rcx+rax*2], bx
0x1800014dc  jnz     short loc_1800014D5
0x1800014de  lea     eax, ds:2[rax*2]
0x1800014e5  jmp     short loc_1800014F1
0x1800014e7  lea     rcx, qword_180031880
0x1800014ee  mov     eax, r9d
0x1800014f1  mov     [rbp+90h+var_88], eax
0x1800014f4  mov     rax, [rbp+90h+arg_70]
0x1800014fb  mov     [rbp+90h+var_90], rcx
0x1800014ff  mov     [rbp+90h+var_84], ebx
0x180001502  mov     rcx, [rax]
0x180001505  test    rcx, rcx
0x180001508  jz      short loc_180001519
0x18000150a  mov     rax, rdx
0x18000150d  inc     rax
0x180001510  cmp     [rcx+rax], bl
0x180001513  jnz     short loc_18000150D
0x180001515  inc     eax
0x180001517  jmp     short loc_18000151F
0x180001519  mov     rcx, rdi
0x18000151c  mov     eax, r8d
0x18000151f  mov     [rbp+90h+var_98], eax
0x180001522  mov     rax, [rbp+90h+arg_68]
0x180001529  mov     [rbp+90h+var_B0], rax
0x18000152d  mov     rax, [rbp+90h+arg_60]
0x180001534  mov     [rbp+90h+var_A0], rcx
0x180001538  mov     [rbp+90h+var_94], ebx
0x18000153b  mov     [rbp+90h+var_A8], 4
0x180001543  mov     rcx, [rax]
0x180001546  test    rcx, rcx
0x180001549  jz      short loc_18000155A
0x18000154b  mov     rax, rdx
0x18000154e  inc     rax
0x180001551  cmp     [rcx+rax], bl
0x180001554  jnz     short loc_18000154E
0x180001556  inc     eax
0x180001558  jmp     short loc_180001560
0x18000155a  mov     rcx, rdi
0x18000155d  mov     eax, r8d
0x180001560  mov     [rbp+90h+var_B8], eax
0x180001563  mov     rax, [rbp+90h+arg_58]
0x18000156a  mov     [rbp+90h+var_D0], rax
0x18000156e  mov     rax, [rbp+90h+arg_50]
0x180001575  mov     [rbp+90h+var_C0], rcx
0x180001579  mov     [rbp+90h+var_B4], ebx
0x18000157c  mov     [rbp+90h+var_C8], 4
0x180001584  mov     rcx, [rax]
0x180001587  test    rcx, rcx
0x18000158a  jz      short loc_1800015A2
0x18000158c  mov     rax, rdx
0x18000158f  inc     rax
0x180001592  cmp     [rcx+rax*2], bx
0x180001596  jnz     short loc_18000158F
0x180001598  lea     r9d, ds:2[rax*2]
0x1800015a0  jmp     short loc_1800015A9
0x1800015a2  lea     rcx, qword_180031880
0x1800015a9  mov     rax, [rbp+90h+arg_48]
0x1800015b0  mov     [rbp+90h+var_F0], rax
0x1800015b4  mov     rax, [rbp+90h+arg_40]
0x1800015bb  mov     [rbp+90h+var_E0], rcx
0x1800015bf  mov     [rbp+90h+var_D8], r9d
0x1800015c3  mov     [rbp+90h+var_D4], ebx
0x1800015c6  mov     rcx, [rax]
0x1800015c9  mov     [rbp+90h+var_E8], 4
0x1800015d1  test    rcx, rcx
0x1800015d4  jz      short loc_1800015E5
0x1800015d6  mov     rax, rdx
0x1800015d9  inc     rax
0x1800015dc  cmp     [rcx+rax], bl
0x1800015df  jnz     short loc_1800015D9
0x1800015e1  inc     eax
0x1800015e3  jmp     short loc_1800015EB
0x1800015e5  mov     rcx, rdi
0x1800015e8  mov     eax, r8d
0x1800015eb  mov     [rbp+90h+var_F8], eax
0x1800015ee  mov     rax, [rbp+90h+arg_38]
0x1800015f5  mov     [rbp+90h+var_110], rax
0x1800015f9  mov     rax, [rbp+90h+arg_30]
0x180001600  mov     [rbp+90h+var_100], rcx
0x180001604  mov     [rbp+90h+var_F4], ebx
0x180001607  mov     [rbp+90h+var_108], 4
0x18000160f  mov     rcx, [rax]
0x180001612  test    rcx, rcx
0x180001615  jz      short loc_180001625
0x180001617  inc     rdx
0x18000161a  cmp     [rcx+rdx], bl
0x18000161d  jnz     short loc_180001617
0x18000161f  lea     r8d, [rdx+1]
0x180001623  jmp     short loc_180001628
0x180001625  mov     rcx, rdi
0x180001628  mov     rax, [rbp+90h+arg_28]
0x18000162f  xor     r9d, r9d
0x180001632  mov     [rsp+190h+var_130], rax
0x180001637  mov     rdx, r11
0x18000163a  mov     rax, [rbp+90h+arg_20]
0x180001641  mov     [rsp+190h+var_140], rax
0x180001646  lea     rax, [rsp+190h+var_160]
0x18000164b  mov     [rsp+190h+var_120], rcx
0x180001650  mov     rcx, r10
0x180001653  mov     [rsp+190h+var_118], r8d
0x180001658  xor     r8d, r8d
0x18000165b  mov     [rsp+190h+var_168], rax
0x180001660  mov     [rsp+190h+var_170], 14h
0x180001668  mov     [rsp+190h+var_114], ebx
0x18000166c  mov     [rsp+190h+var_128], 4
0x180001675  mov     [rsp+190h+var_138], 8
0x18000167e  call    _tlgWriteTransfer_EventWriteTransfer
0x180001683  mov     rcx, [rbp+90h+var_20]
0x180001687  xor     rcx, rsp; StackCookie
0x18000168a  call    __security_check_cookie
0x18000168f  mov     rbx, [rsp+190h+arg_10]
0x180001697  add     rsp, 180h
0x18000169e  pop     r14
0x1800016a0  pop     rdi
0x1800016a1  pop     rbp
0x1800016a2  retn
```
