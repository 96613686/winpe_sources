# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)

- ea: `0x18000134c`
- end: `0x180001658`
- name: `??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456445@Z`
- size: `780`
- prototype: ``
- caller_count: `9`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180010820`
- `0x180010d70`
- `0x1800112c0`
- `0x180011810`
- `0x180011ab0`
- `0x180011d50`
- `0x180020dc0`
- `0x18002bd20`
- `0x18002bfc0`

## callees

- `0x18000134c`
- `0x180001e10`
- `0x180002ad0`

## pseudocode

```c
ULONG __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        __int64 a1,
        unsigned __int8 *a2,
        const GUID *a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        __int64 a7,
        const unsigned __int16 **a8,
        __int64 a9,
        const unsigned __int16 **a10,
        __int64 a11,
        const WCHAR **a12,
        __int64 a13,
        const unsigned __int16 **a14,
        __int64 a15,
        const unsigned __int16 **a16,
        const WCHAR **a17,
        __int64 a18,
        const unsigned __int16 **a19,
        const WCHAR **a20,
        __int64 a21,
        __int64 a22,
        const unsigned __int16 **a23)
{
  __int64 v25; // rdx
  int v27; // r8d
  const unsigned __int16 *v28; // rcx
  __int64 v29; // rax
  int v30; // eax
  int v31; // r9d
  const WCHAR *v32; // rcx
  __int64 v33; // rax
  int v34; // eax
  const unsigned __int16 *v35; // rcx
  __int64 v36; // rax
  int v37; // eax
  const WCHAR *v38; // rcx
  __int64 v39; // rax
  int v40; // eax
  const unsigned __int16 *v41; // rcx
  __int64 v42; // rax
  int v43; // eax
  const unsigned __int16 *v44; // rcx
  __int64 v45; // rax
  int v46; // eax
  const WCHAR *v47; // rcx
  __int64 v48; // rax
  const unsigned __int16 *v49; // rcx
  __int64 v50; // rax
  int v51; // eax
  const unsigned __int16 *v52; // rcx
  struct _EVENT_DATA_DESCRIPTOR v54; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v55; // [rsp+50h] [rbp-B0h]
  __int64 v56; // [rsp+58h] [rbp-A8h]
  __int64 v57; // [rsp+60h] [rbp-A0h]
  __int64 v58; // [rsp+68h] [rbp-98h]
  __int64 v59; // [rsp+70h] [rbp-90h]
  __int64 v60; // [rsp+78h] [rbp-88h]
  const unsigned __int16 *v61; // [rsp+80h] [rbp-80h]
  int v62; // [rsp+88h] [rbp-78h]
  int v63; // [rsp+8Ch] [rbp-74h]
  __int64 v64; // [rsp+90h] [rbp-70h]
  __int64 v65; // [rsp+98h] [rbp-68h]
  const unsigned __int16 *v66; // [rsp+A0h] [rbp-60h]
  int v67; // [rsp+A8h] [rbp-58h]
  int v68; // [rsp+ACh] [rbp-54h]
  __int64 v69; // [rsp+B0h] [rbp-50h]
  __int64 v70; // [rsp+B8h] [rbp-48h]
  const WCHAR *v71; // [rsp+C0h] [rbp-40h]
  int v72; // [rsp+C8h] [rbp-38h]
  int v73; // [rsp+CCh] [rbp-34h]
  __int64 v74; // [rsp+D0h] [rbp-30h]
  __int64 v75; // [rsp+D8h] [rbp-28h]
  const unsigned __int16 *v76; // [rsp+E0h] [rbp-20h]
  int v77; // [rsp+E8h] [rbp-18h]
  int v78; // [rsp+ECh] [rbp-14h]
  __int64 v79; // [rsp+F0h] [rbp-10h]
  __int64 v80; // [rsp+F8h] [rbp-8h]
  const unsigned __int16 *v81; // [rsp+100h] [rbp+0h]
  int v82; // [rsp+108h] [rbp+8h]
  int v83; // [rsp+10Ch] [rbp+Ch]
  const WCHAR *v84; // [rsp+110h] [rbp+10h]
  int v85; // [rsp+118h] [rbp+18h]
  int v86; // [rsp+11Ch] [rbp+1Ch]
  __int64 v87; // [rsp+120h] [rbp+20h]
  __int64 v88; // [rsp+128h] [rbp+28h]
  const unsigned __int16 *v89; // [rsp+130h] [rbp+30h]
  int v90; // [rsp+138h] [rbp+38h]
  int v91; // [rsp+13Ch] [rbp+3Ch]
  const WCHAR *v92; // [rsp+140h] [rbp+40h]
  int v93; // [rsp+148h] [rbp+48h]
  int v94; // [rsp+14Ch] [rbp+4Ch]
  __int64 v95; // [rsp+150h] [rbp+50h]
  __int64 v96; // [rsp+158h] [rbp+58h]
  __int64 v97; // [rsp+160h] [rbp+60h]
  __int64 v98; // [rsp+168h] [rbp+68h]
  const unsigned __int16 *v99; // [rsp+170h] [rbp+70h]
  int v100; // [rsp+178h] [rbp+78h]
  int v101; // [rsp+17Ch] [rbp+7Ch]

  v25 = -1;
  v27 = 1;
  v28 = *a23;
  if ( *a23 )
  {
    v29 = -1;
    do
      ++v29;
    while ( *((_BYTE *)v28 + v29) );
    v30 = v29 + 1;
  }
  else
  {
    v28 = &byte_180037E05;
    v30 = 1;
  }
  v100 = v30;
  v31 = 2;
  v97 = a22;
  v95 = a21;
  v99 = v28;
  v101 = 0;
  v98 = 4;
  v32 = *a20;
  v96 = 4;
  if ( v32 )
  {
    v33 = -1;
    do
      ++v33;
    while ( v32[v33] );
    v34 = 2 * v33 + 2;
  }
  else
  {
    v32 = &pwszBaseUri;
    v34 = 2;
  }
  v93 = v34;
  v92 = v32;
  v94 = 0;
  v35 = *a19;
  if ( *a19 )
  {
    v36 = -1;
    do
      ++v36;
    while ( *((_BYTE *)v35 + v36) );
    v37 = v36 + 1;
  }
  else
  {
    v35 = &byte_180037E05;
    v37 = 1;
  }
  v90 = v37;
  v87 = a18;
  v89 = v35;
  v91 = 0;
  v88 = 4;
  v38 = *a17;
  if ( *a17 )
  {
    v39 = -1;
    do
      ++v39;
    while ( v38[v39] );
    v40 = 2 * v39 + 2;
  }
  else
  {
    v38 = &pwszBaseUri;
    v40 = 2;
  }
  v85 = v40;
  v84 = v38;
  v86 = 0;
  v41 = *a16;
  if ( *a16 )
  {
    v42 = -1;
    do
      ++v42;
    while ( *((_BYTE *)v41 + v42) );
    v43 = v42 + 1;
  }
  else
  {
    v41 = &byte_180037E05;
    v43 = 1;
  }
  v82 = v43;
  v79 = a15;
  v81 = v41;
  v83 = 0;
  v80 = 4;
  v44 = *a14;
  if ( *a14 )
  {
    v45 = -1;
    do
      ++v45;
    while ( *((_BYTE *)v44 + v45) );
    v46 = v45 + 1;
  }
  else
  {
    v44 = &byte_180037E05;
    v46 = 1;
  }
  v77 = v46;
  v74 = a13;
  v76 = v44;
  v78 = 0;
  v75 = 4;
  v47 = *a12;
  if ( *a12 )
  {
    v48 = -1;
    do
      ++v48;
    while ( v47[v48] );
    v31 = 2 * v48 + 2;
  }
  else
  {
    v47 = &pwszBaseUri;
  }
  v69 = a11;
  v71 = v47;
  v72 = v31;
  v73 = 0;
  v49 = *a10;
  v70 = 4;
  if ( v49 )
  {
    v50 = -1;
    do
      ++v50;
    while ( *((_BYTE *)v49 + v50) );
    v51 = v50 + 1;
  }
  else
  {
    v49 = &byte_180037E05;
    v51 = 1;
  }
  v67 = v51;
  v64 = a9;
  v66 = v49;
  v68 = 0;
  v65 = 4;
  v52 = *a8;
  if ( *a8 )
  {
    do
      ++v25;
    while ( *((_BYTE *)v52 + v25) );
    v27 = v25 + 1;
  }
  else
  {
    v52 = &byte_180037E05;
  }
  v59 = a7;
  v57 = a6;
  v55 = a5;
  v61 = v52;
  v62 = v27;
  v63 = 0;
  v60 = 4;
  v58 = 8;
  v56 = 8;
  return tlgWriteTransfer_EventWriteTransfer(a1, a2, a3, 0, 0x15u, &v54);
}

```

## disassembly

```asm
0x18000134c  push    rbp
0x18000134e  push    rbx
0x18000134f  push    rsi
0x180001350  push    rdi
0x180001351  push    r14
0x180001353  lea     rbp, [rsp-90h]
0x18000135b  sub     rsp, 190h
0x180001362  mov     rax, cs:__security_cookie
0x180001369  xor     rax, rsp
0x18000136c  mov     [rbp+0B0h+var_30], rax
0x180001373  mov     rax, [rbp+0B0h+arg_B0]
0x18000137a  lea     rsi, byte_180037E05
0x180001381  mov     r11, rdx
0x180001384  mov     r10, rcx
0x180001387  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18000138b  xor     edi, edi
0x18000138d  mov     rbx, r8
0x180001390  mov     r8d, 1
0x180001396  mov     rcx, [rax]
0x180001399  test    rcx, rcx
0x18000139c  jz      short loc_1800013AE
0x18000139e  mov     rax, rdx
0x1800013a1  inc     rax
0x1800013a4  cmp     [rcx+rax], dil
0x1800013a8  jnz     short loc_1800013A1
0x1800013aa  inc     eax
0x1800013ac  jmp     short loc_1800013B4
0x1800013ae  mov     rcx, rsi
0x1800013b1  mov     eax, r8d
0x1800013b4  mov     [rbp+0B0h+var_38], eax
0x1800013b7  mov     r9d, 2
0x1800013bd  mov     rax, [rbp+0B0h+arg_A8]
0x1800013c4  mov     [rbp+0B0h+var_50], rax
0x1800013c8  mov     rax, [rbp+0B0h+arg_A0]
0x1800013cf  mov     [rbp+0B0h+var_60], rax
0x1800013d3  mov     rax, [rbp+0B0h+arg_98]
0x1800013da  mov     [rbp+0B0h+var_40], rcx
0x1800013de  mov     [rbp+0B0h+var_34], edi
0x1800013e1  mov     [rbp+0B0h+var_48], 4
0x1800013e9  mov     rcx, [rax]
0x1800013ec  mov     [rbp+0B0h+var_58], 4
0x1800013f4  test    rcx, rcx
0x1800013f7  jz      short loc_18000140E
0x1800013f9  mov     rax, rdx
0x1800013fc  inc     rax
0x1800013ff  cmp     [rcx+rax*2], di
0x180001403  jnz     short loc_1800013FC
0x180001405  lea     eax, ds:2[rax*2]
0x18000140c  jmp     short loc_180001418
0x18000140e  lea     rcx, pwszBaseUri
0x180001415  mov     eax, r9d
0x180001418  mov     [rbp+0B0h+var_68], eax
0x18000141b  mov     rax, [rbp+0B0h+arg_90]
0x180001422  mov     [rbp+0B0h+var_70], rcx
0x180001426  mov     [rbp+0B0h+var_64], edi
0x180001429  mov     rcx, [rax]
0x18000142c  test    rcx, rcx
0x18000142f  jz      short loc_180001441
0x180001431  mov     rax, rdx
0x180001434  inc     rax
0x180001437  cmp     [rcx+rax], dil
0x18000143b  jnz     short loc_180001434
0x18000143d  inc     eax
0x18000143f  jmp     short loc_180001447
0x180001441  mov     rcx, rsi
0x180001444  mov     eax, r8d
0x180001447  mov     [rbp+0B0h+var_78], eax
0x18000144a  mov     rax, [rbp+0B0h+arg_88]
0x180001451  mov     [rbp+0B0h+var_90], rax
0x180001455  mov     rax, [rbp+0B0h+arg_80]
0x18000145c  mov     [rbp+0B0h+var_80], rcx
0x180001460  mov     [rbp+0B0h+var_74], edi
0x180001463  mov     [rbp+0B0h+var_88], 4
0x18000146b  mov     rcx, [rax]
0x18000146e  test    rcx, rcx
0x180001471  jz      short loc_180001488
0x180001473  mov     rax, rdx
0x180001476  inc     rax
0x180001479  cmp     [rcx+rax*2], di
0x18000147d  jnz     short loc_180001476
0x18000147f  lea     eax, ds:2[rax*2]
0x180001486  jmp     short loc_180001492
0x180001488  lea     rcx, pwszBaseUri
0x18000148f  mov     eax, r9d
0x180001492  mov     [rbp+0B0h+var_98], eax
0x180001495  mov     rax, [rbp+0B0h+arg_78]
0x18000149c  mov     [rbp+0B0h+var_A0], rcx
0x1800014a0  mov     [rbp+0B0h+var_94], edi
0x1800014a3  mov     rcx, [rax]
0x1800014a6  test    rcx, rcx
0x1800014a9  jz      short loc_1800014BB
0x1800014ab  mov     rax, rdx
0x1800014ae  inc     rax
0x1800014b1  cmp     [rcx+rax], dil
0x1800014b5  jnz     short loc_1800014AE
0x1800014b7  inc     eax
0x1800014b9  jmp     short loc_1800014C1
0x1800014bb  mov     rcx, rsi
0x1800014be  mov     eax, r8d
0x1800014c1  mov     [rbp+0B0h+var_A8], eax
0x1800014c4  mov     rax, [rbp+0B0h+arg_70]
0x1800014cb  mov     [rbp+0B0h+var_C0], rax
0x1800014cf  mov     rax, [rbp+0B0h+arg_68]
0x1800014d6  mov     [rbp+0B0h+var_B0], rcx
0x1800014da  mov     [rbp+0B0h+var_A4], edi
0x1800014dd  mov     [rbp+0B0h+var_B8], 4
0x1800014e5  mov     rcx, [rax]
0x1800014e8  test    rcx, rcx
0x1800014eb  jz      short loc_1800014FD
0x1800014ed  mov     rax, rdx
0x1800014f0  inc     rax
0x1800014f3  cmp     [rcx+rax], dil
0x1800014f7  jnz     short loc_1800014F0
0x1800014f9  inc     eax
0x1800014fb  jmp     short loc_180001503
0x1800014fd  mov     rcx, rsi
0x180001500  mov     eax, r8d
0x180001503  mov     [rbp+0B0h+var_C8], eax
0x180001506  mov     rax, [rbp+0B0h+arg_60]
0x18000150d  mov     [rbp+0B0h+var_E0], rax
0x180001511  mov     rax, [rbp+0B0h+arg_58]
0x180001518  mov     [rbp+0B0h+var_D0], rcx
0x18000151c  mov     [rbp+0B0h+var_C4], edi
0x18000151f  mov     [rbp+0B0h+var_D8], 4
0x180001527  mov     rcx, [rax]
0x18000152a  test    rcx, rcx
0x18000152d  jz      short loc_180001545
0x18000152f  mov     rax, rdx
0x180001532  inc     rax
0x180001535  cmp     [rcx+rax*2], di
0x180001539  jnz     short loc_180001532
0x18000153b  lea     r9d, ds:2[rax*2]
0x180001543  jmp     short loc_18000154C
0x180001545  lea     rcx, pwszBaseUri
0x18000154c  mov     rax, [rbp+0B0h+arg_50]
0x180001553  mov     [rbp+0B0h+var_100], rax
0x180001557  mov     rax, [rbp+0B0h+arg_48]
0x18000155e  mov     [rbp+0B0h+var_F0], rcx
0x180001562  mov     [rbp+0B0h+var_E8], r9d
0x180001566  mov     [rbp+0B0h+var_E4], edi
0x180001569  mov     rcx, [rax]
0x18000156c  mov     [rbp+0B0h+var_F8], 4
0x180001574  test    rcx, rcx
0x180001577  jz      short loc_180001589
0x180001579  mov     rax, rdx
0x18000157c  inc     rax
0x18000157f  cmp     [rcx+rax], dil
0x180001583  jnz     short loc_18000157C
0x180001585  inc     eax
0x180001587  jmp     short loc_18000158F
0x180001589  mov     rcx, rsi
0x18000158c  mov     eax, r8d
0x18000158f  mov     [rbp+0B0h+var_108], eax
0x180001592  mov     rax, [rbp+0B0h+arg_40]
0x180001599  mov     [rbp+0B0h+var_120], rax
0x18000159d  mov     rax, [rbp+0B0h+arg_38]
0x1800015a4  mov     [rbp+0B0h+var_110], rcx
0x1800015a8  mov     [rbp+0B0h+var_104], edi
0x1800015ab  mov     [rbp+0B0h+var_118], 4
0x1800015b3  mov     rcx, [rax]
0x1800015b6  test    rcx, rcx
0x1800015b9  jz      short loc_1800015CA
0x1800015bb  inc     rdx
0x1800015be  cmp     [rcx+rdx], dil
0x1800015c2  jnz     short loc_1800015BB
0x1800015c4  lea     r8d, [rdx+1]
0x1800015c8  jmp     short loc_1800015CD
0x1800015ca  mov     rcx, rsi
0x1800015cd  mov     rax, [rbp+0B0h+arg_30]
0x1800015d4  xor     r9d, r9d
0x1800015d7  mov     [rsp+1B0h+var_140], rax
0x1800015dc  mov     rdx, r11
0x1800015df  mov     rax, [rbp+0B0h+arg_28]
0x1800015e6  mov     [rsp+1B0h+var_150], rax
0x1800015eb  mov     rax, [rbp+0B0h+arg_20]
0x1800015f2  mov     [rsp+1B0h+var_160], rax
0x1800015f7  lea     rax, [rsp+1B0h+var_180]
0x1800015fc  mov     [rbp+0B0h+var_130], rcx
0x180001600  mov     rcx, r10
0x180001603  mov     [rbp+0B0h+var_128], r8d
0x180001607  mov     r8, rbx
0x18000160a  mov     [rsp+1B0h+var_188], rax
0x18000160f  mov     [rsp+1B0h+var_190], 15h
0x180001617  mov     [rbp+0B0h+var_124], edi
0x18000161a  mov     [rsp+1B0h+var_138], 4
0x180001623  mov     [rsp+1B0h+var_148], 8
0x18000162c  mov     [rsp+1B0h+var_158], 8
0x180001635  call    _tlgWriteTransfer_EventWriteTransfer
0x18000163a  mov     rcx, [rbp+0B0h+var_30]
0x180001641  xor     rcx, rsp; StackCookie
0x180001644  call    __security_check_cookie
0x180001649  add     rsp, 190h
0x180001650  pop     r14
0x180001652  pop     rdi
0x180001653  pop     rsi
0x180001654  pop     rbx
0x180001655  pop     rbp
0x180001656  retn
```
