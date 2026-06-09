# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)

- ea: `0x14000156c`
- end: `0x14000185c`
- name: `??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456445@Z`
- size: `752`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, __int64, __int64, const unsigned __int16 **, __int64, const unsigned __int16 **, __int64, const WCHAR **, __int64, const unsigned __int16 **, __int64, const unsigned __int16 **, const WCHAR **, __int64, const unsigned __int16 **, const WCHAR **, __int64, __int64, const unsigned __int16 **)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x14000e2f0`
- `0x140010030`

## callees

- `0x14000156c`
- `0x1400019e8`
- `0x1400029a0`

## pseudocode

```c
__int64 __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        const unsigned __int16 **a7,
        __int64 a8,
        const unsigned __int16 **a9,
        __int64 a10,
        const WCHAR **a11,
        __int64 a12,
        const unsigned __int16 **a13,
        __int64 a14,
        const unsigned __int16 **a15,
        const WCHAR **a16,
        __int64 a17,
        const unsigned __int16 **a18,
        const WCHAR **a19,
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
  const WCHAR *v31; // rcx
  __int64 v32; // rax
  int v33; // eax
  const unsigned __int16 *v34; // rcx
  __int64 v35; // rax
  int v36; // eax
  const WCHAR *v37; // rcx
  __int64 v38; // rax
  int v39; // eax
  const unsigned __int16 *v40; // rcx
  __int64 v41; // rax
  int v42; // eax
  const unsigned __int16 *v43; // rcx
  __int64 v44; // rax
  int v45; // eax
  const WCHAR *v46; // rcx
  __int64 v47; // rax
  const unsigned __int16 *v48; // rcx
  __int64 v49; // rax
  int v50; // eax
  const unsigned __int16 *v51; // rcx
  _BYTE v53[32]; // [rsp+30h] [rbp-D0h] BYREF
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
  const WCHAR *v68; // [rsp+B0h] [rbp-50h]
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
  const WCHAR *v81; // [rsp+100h] [rbp+0h]
  int v82; // [rsp+108h] [rbp+8h]
  int v83; // [rsp+10Ch] [rbp+Ch]
  __int64 v84; // [rsp+110h] [rbp+10h]
  __int64 v85; // [rsp+118h] [rbp+18h]
  const unsigned __int16 *v86; // [rsp+120h] [rbp+20h]
  int v87; // [rsp+128h] [rbp+28h]
  int v88; // [rsp+12Ch] [rbp+2Ch]
  const WCHAR *v89; // [rsp+130h] [rbp+30h]
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
    v27 = &qword_14001A178;
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
    while ( v31[v32] );
    v33 = 2 * v32 + 2;
  }
  else
  {
    v31 = &String;
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
    v34 = &qword_14001A178;
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
    while ( v37[v38] );
    v39 = 2 * v38 + 2;
  }
  else
  {
    v37 = &String;
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
    v40 = &qword_14001A178;
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
    v43 = &qword_14001A178;
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
    while ( v46[v47] );
    v30 = 2 * v47 + 2;
  }
  else
  {
    v46 = &String;
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
    v48 = &qword_14001A178;
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
    v51 = &qword_14001A178;
  }
  v56 = a6;
  v54 = a5;
  v58 = v51;
  v59 = v26;
  v60 = 0;
  v57 = 4;
  v55 = 8;
  return tlgWriteTransfer_EventWriteTransfer(a1, a2, a3, 0, 20, v53);
}

```

## disassembly

```asm
0x14000156c  push    rbp
0x14000156e  push    rbx
0x14000156f  push    rsi
0x140001570  push    rdi
0x140001571  push    r15
0x140001573  lea     rbp, [rsp-80h]
0x140001578  sub     rsp, 180h
0x14000157f  mov     rax, cs:__security_cookie
0x140001586  xor     rax, rsp
0x140001589  mov     [rbp+0A0h+var_30], rax
0x14000158d  mov     rax, [rbp+0A0h+arg_A8]
0x140001594  lea     rsi, qword_14001A178
0x14000159b  mov     r11, rdx
0x14000159e  mov     r10, rcx
0x1400015a1  or      rdx, 0FFFFFFFFFFFFFFFFh
0x1400015a5  xor     edi, edi
0x1400015a7  mov     rbx, r8
0x1400015aa  mov     r8d, 1
0x1400015b0  mov     rcx, [rax]
0x1400015b3  test    rcx, rcx
0x1400015b6  jz      short loc_1400015C8
0x1400015b8  mov     rax, rdx
0x1400015bb  inc     rax
0x1400015be  cmp     [rcx+rax], dil
0x1400015c2  jnz     short loc_1400015BB
0x1400015c4  inc     eax
0x1400015c6  jmp     short loc_1400015CE
0x1400015c8  mov     rcx, rsi
0x1400015cb  mov     eax, r8d
0x1400015ce  mov     [rbp+0A0h+var_38], eax
0x1400015d1  mov     r9d, 2
0x1400015d7  mov     rax, [rbp+0A0h+arg_A0]
0x1400015de  mov     [rbp+0A0h+var_50], rax
0x1400015e2  mov     rax, [rbp+0A0h+arg_98]
0x1400015e9  mov     [rbp+0A0h+var_60], rax
0x1400015ed  mov     rax, [rbp+0A0h+arg_90]
0x1400015f4  mov     [rbp+0A0h+var_40], rcx
0x1400015f8  mov     [rbp+0A0h+var_34], edi
0x1400015fb  mov     [rbp+0A0h+var_48], 4
0x140001603  mov     rcx, [rax]
0x140001606  mov     [rbp+0A0h+var_58], 4
0x14000160e  test    rcx, rcx
0x140001611  jz      short loc_140001628
0x140001613  mov     rax, rdx
0x140001616  inc     rax
0x140001619  cmp     [rcx+rax*2], di
0x14000161d  jnz     short loc_140001616
0x14000161f  lea     eax, ds:2[rax*2]
0x140001626  jmp     short loc_140001632
0x140001628  lea     rcx, String
0x14000162f  mov     eax, r9d
0x140001632  mov     [rbp+0A0h+var_68], eax
0x140001635  mov     rax, [rbp+0A0h+arg_88]
0x14000163c  mov     [rbp+0A0h+var_70], rcx
0x140001640  mov     [rbp+0A0h+var_64], edi
0x140001643  mov     rcx, [rax]
0x140001646  test    rcx, rcx
0x140001649  jz      short loc_14000165B
0x14000164b  mov     rax, rdx
0x14000164e  inc     rax
0x140001651  cmp     [rcx+rax], dil
0x140001655  jnz     short loc_14000164E
0x140001657  inc     eax
0x140001659  jmp     short loc_140001661
0x14000165b  mov     rcx, rsi
0x14000165e  mov     eax, r8d
0x140001661  mov     [rbp+0A0h+var_78], eax
0x140001664  mov     rax, [rbp+0A0h+arg_80]
0x14000166b  mov     [rbp+0A0h+var_90], rax
0x14000166f  mov     rax, [rbp+0A0h+arg_78]
0x140001676  mov     [rbp+0A0h+var_80], rcx
0x14000167a  mov     [rbp+0A0h+var_74], edi
0x14000167d  mov     [rbp+0A0h+var_88], 4
0x140001685  mov     rcx, [rax]
0x140001688  test    rcx, rcx
0x14000168b  jz      short loc_1400016A2
0x14000168d  mov     rax, rdx
0x140001690  inc     rax
0x140001693  cmp     [rcx+rax*2], di
0x140001697  jnz     short loc_140001690
0x140001699  lea     eax, ds:2[rax*2]
0x1400016a0  jmp     short loc_1400016AC
0x1400016a2  lea     rcx, String
0x1400016a9  mov     eax, r9d
0x1400016ac  mov     [rbp+0A0h+var_98], eax
0x1400016af  mov     rax, [rbp+0A0h+arg_70]
0x1400016b6  mov     [rbp+0A0h+var_A0], rcx
0x1400016ba  mov     [rbp+0A0h+var_94], edi
0x1400016bd  mov     rcx, [rax]
0x1400016c0  test    rcx, rcx
0x1400016c3  jz      short loc_1400016D5
0x1400016c5  mov     rax, rdx
0x1400016c8  inc     rax
0x1400016cb  cmp     [rcx+rax], dil
0x1400016cf  jnz     short loc_1400016C8
0x1400016d1  inc     eax
0x1400016d3  jmp     short loc_1400016DB
0x1400016d5  mov     rcx, rsi
0x1400016d8  mov     eax, r8d
0x1400016db  mov     [rbp+0A0h+var_A8], eax
0x1400016de  mov     rax, [rbp+0A0h+arg_68]
0x1400016e5  mov     [rbp+0A0h+var_C0], rax
0x1400016e9  mov     rax, [rbp+0A0h+arg_60]
0x1400016f0  mov     [rbp+0A0h+var_B0], rcx
0x1400016f4  mov     [rbp+0A0h+var_A4], edi
0x1400016f7  mov     [rbp+0A0h+var_B8], 4
0x1400016ff  mov     rcx, [rax]
0x140001702  test    rcx, rcx
0x140001705  jz      short loc_140001717
0x140001707  mov     rax, rdx
0x14000170a  inc     rax
0x14000170d  cmp     [rcx+rax], dil
0x140001711  jnz     short loc_14000170A
0x140001713  inc     eax
0x140001715  jmp     short loc_14000171D
0x140001717  mov     rcx, rsi
0x14000171a  mov     eax, r8d
0x14000171d  mov     [rbp+0A0h+var_C8], eax
0x140001720  mov     rax, [rbp+0A0h+arg_58]
0x140001727  mov     [rbp+0A0h+var_E0], rax
0x14000172b  mov     rax, [rbp+0A0h+arg_50]
0x140001732  mov     [rbp+0A0h+var_D0], rcx
0x140001736  mov     [rbp+0A0h+var_C4], edi
0x140001739  mov     [rbp+0A0h+var_D8], 4
0x140001741  mov     rcx, [rax]
0x140001744  test    rcx, rcx
0x140001747  jz      short loc_14000175F
0x140001749  mov     rax, rdx
0x14000174c  inc     rax
0x14000174f  cmp     [rcx+rax*2], di
0x140001753  jnz     short loc_14000174C
0x140001755  lea     r9d, ds:2[rax*2]
0x14000175d  jmp     short loc_140001766
0x14000175f  lea     rcx, String
0x140001766  mov     rax, [rbp+0A0h+arg_48]
0x14000176d  mov     [rbp+0A0h+var_100], rax
0x140001771  mov     rax, [rbp+0A0h+arg_40]
0x140001778  mov     [rbp+0A0h+var_F0], rcx
0x14000177c  mov     [rbp+0A0h+var_E8], r9d
0x140001780  mov     [rbp+0A0h+var_E4], edi
0x140001783  mov     rcx, [rax]
0x140001786  mov     [rbp+0A0h+var_F8], 4
0x14000178e  test    rcx, rcx
0x140001791  jz      short loc_1400017A3
0x140001793  mov     rax, rdx
0x140001796  inc     rax
0x140001799  cmp     [rcx+rax], dil
0x14000179d  jnz     short loc_140001796
0x14000179f  inc     eax
0x1400017a1  jmp     short loc_1400017A9
0x1400017a3  mov     rcx, rsi
0x1400017a6  mov     eax, r8d
0x1400017a9  mov     [rbp+0A0h+var_108], eax
0x1400017ac  mov     rax, [rbp+0A0h+arg_38]
0x1400017b3  mov     [rbp+0A0h+var_120], rax
0x1400017b7  mov     rax, [rbp+0A0h+arg_30]
0x1400017be  mov     [rbp+0A0h+var_110], rcx
0x1400017c2  mov     [rbp+0A0h+var_104], edi
0x1400017c5  mov     [rbp+0A0h+var_118], 4
0x1400017cd  mov     rcx, [rax]
0x1400017d0  test    rcx, rcx
0x1400017d3  jz      short loc_1400017E4
0x1400017d5  inc     rdx
0x1400017d8  cmp     [rcx+rdx], dil
0x1400017dc  jnz     short loc_1400017D5
0x1400017de  lea     r8d, [rdx+1]
0x1400017e2  jmp     short loc_1400017E7
0x1400017e4  mov     rcx, rsi
0x1400017e7  mov     rax, [rbp+0A0h+arg_28]
0x1400017ee  xor     r9d, r9d
0x1400017f1  mov     [rsp+1A0h+var_140], rax
0x1400017f6  mov     rdx, r11
0x1400017f9  mov     rax, [rbp+0A0h+arg_20]
0x140001800  mov     [rsp+1A0h+var_150], rax
0x140001805  lea     rax, [rsp+1A0h+var_170]
0x14000180a  mov     [rsp+1A0h+var_130], rcx
0x14000180f  mov     rcx, r10
0x140001812  mov     [rsp+1A0h+var_128], r8d
0x140001817  mov     r8, rbx
0x14000181a  mov     [rsp+1A0h+var_178], rax
0x14000181f  mov     [rsp+1A0h+var_180], 14h
0x140001827  mov     [rsp+1A0h+var_124], edi
0x14000182b  mov     [rsp+1A0h+var_138], 4
0x140001834  mov     [rsp+1A0h+var_148], 8
0x14000183d  call    _tlgWriteTransfer_EventWriteTransfer
0x140001842  mov     rcx, [rbp+0A0h+var_30]
0x140001846  xor     rcx, rsp; StackCookie
0x140001849  call    __security_check_cookie
0x14000184e  add     rsp, 180h
0x140001855  pop     r15
0x140001857  pop     rdi
0x140001858  pop     rsi
0x140001859  pop     rbx
0x14000185a  pop     rbp
0x14000185b  retn
```
