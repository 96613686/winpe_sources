# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)

- ea: `0x140001834`
- end: `0x140001b24`
- name: `??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456445@Z`
- size: `752`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, __int64, __int64, const unsigned __int16 **, __int64, const unsigned __int16 **, __int64, __int64 **, __int64, const unsigned __int16 **, __int64, const unsigned __int16 **, __int64 **, __int64, const unsigned __int16 **, __int64 **, __int64, __int64, const unsigned __int16 **)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x14000a400`
- `0x14000c5c4`

## callees

- `0x140001834`
- `0x140001bac`
- `0x1400022a0`

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
        __int64 **a11,
        __int64 a12,
        const unsigned __int16 **a13,
        __int64 a14,
        const unsigned __int16 **a15,
        __int64 **a16,
        __int64 a17,
        const unsigned __int16 **a18,
        __int64 **a19,
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
  __int64 *v31; // rcx
  __int64 v32; // rax
  int v33; // eax
  const unsigned __int16 *v34; // rcx
  __int64 v35; // rax
  int v36; // eax
  __int64 *v37; // rcx
  __int64 v38; // rax
  int v39; // eax
  const unsigned __int16 *v40; // rcx
  __int64 v41; // rax
  int v42; // eax
  const unsigned __int16 *v43; // rcx
  __int64 v44; // rax
  int v45; // eax
  __int64 *v46; // rcx
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
  __int64 *v68; // [rsp+B0h] [rbp-50h]
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
  __int64 *v81; // [rsp+100h] [rbp+0h]
  int v82; // [rsp+108h] [rbp+8h]
  int v83; // [rsp+10Ch] [rbp+Ch]
  __int64 v84; // [rsp+110h] [rbp+10h]
  __int64 v85; // [rsp+118h] [rbp+18h]
  const unsigned __int16 *v86; // [rsp+120h] [rbp+20h]
  int v87; // [rsp+128h] [rbp+28h]
  int v88; // [rsp+12Ch] [rbp+2Ch]
  __int64 *v89; // [rsp+130h] [rbp+30h]
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
    v27 = &dword_140013B84;
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
    v31 = &qword_140013B88;
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
    v34 = &dword_140013B84;
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
    v37 = &qword_140013B88;
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
    v40 = &dword_140013B84;
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
    v43 = &dword_140013B84;
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
    v46 = &qword_140013B88;
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
    v48 = &dword_140013B84;
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
    v51 = &dword_140013B84;
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
0x140001834  push    rbp
0x140001836  push    rbx
0x140001837  push    rsi
0x140001838  push    rdi
0x140001839  push    r15
0x14000183b  lea     rbp, [rsp-80h]
0x140001840  sub     rsp, 180h
0x140001847  mov     rax, cs:__security_cookie
0x14000184e  xor     rax, rsp
0x140001851  mov     [rbp+0A0h+var_30], rax
0x140001855  mov     rax, [rbp+0A0h+arg_A8]
0x14000185c  lea     rsi, dword_140013B84
0x140001863  mov     r11, rdx
0x140001866  mov     r10, rcx
0x140001869  or      rdx, 0FFFFFFFFFFFFFFFFh
0x14000186d  xor     edi, edi
0x14000186f  mov     rbx, r8
0x140001872  mov     r8d, 1
0x140001878  mov     rcx, [rax]
0x14000187b  test    rcx, rcx
0x14000187e  jz      short loc_140001890
0x140001880  mov     rax, rdx
0x140001883  inc     rax
0x140001886  cmp     [rcx+rax], dil
0x14000188a  jnz     short loc_140001883
0x14000188c  inc     eax
0x14000188e  jmp     short loc_140001896
0x140001890  mov     rcx, rsi
0x140001893  mov     eax, r8d
0x140001896  mov     [rbp+0A0h+var_38], eax
0x140001899  mov     r9d, 2
0x14000189f  mov     rax, [rbp+0A0h+arg_A0]
0x1400018a6  mov     [rbp+0A0h+var_50], rax
0x1400018aa  mov     rax, [rbp+0A0h+arg_98]
0x1400018b1  mov     [rbp+0A0h+var_60], rax
0x1400018b5  mov     rax, [rbp+0A0h+arg_90]
0x1400018bc  mov     [rbp+0A0h+var_40], rcx
0x1400018c0  mov     [rbp+0A0h+var_34], edi
0x1400018c3  mov     [rbp+0A0h+var_48], 4
0x1400018cb  mov     rcx, [rax]
0x1400018ce  mov     [rbp+0A0h+var_58], 4
0x1400018d6  test    rcx, rcx
0x1400018d9  jz      short loc_1400018F0
0x1400018db  mov     rax, rdx
0x1400018de  inc     rax
0x1400018e1  cmp     [rcx+rax*2], di
0x1400018e5  jnz     short loc_1400018DE
0x1400018e7  lea     eax, ds:2[rax*2]
0x1400018ee  jmp     short loc_1400018FA
0x1400018f0  lea     rcx, qword_140013B88
0x1400018f7  mov     eax, r9d
0x1400018fa  mov     [rbp+0A0h+var_68], eax
0x1400018fd  mov     rax, [rbp+0A0h+arg_88]
0x140001904  mov     [rbp+0A0h+var_70], rcx
0x140001908  mov     [rbp+0A0h+var_64], edi
0x14000190b  mov     rcx, [rax]
0x14000190e  test    rcx, rcx
0x140001911  jz      short loc_140001923
0x140001913  mov     rax, rdx
0x140001916  inc     rax
0x140001919  cmp     [rcx+rax], dil
0x14000191d  jnz     short loc_140001916
0x14000191f  inc     eax
0x140001921  jmp     short loc_140001929
0x140001923  mov     rcx, rsi
0x140001926  mov     eax, r8d
0x140001929  mov     [rbp+0A0h+var_78], eax
0x14000192c  mov     rax, [rbp+0A0h+arg_80]
0x140001933  mov     [rbp+0A0h+var_90], rax
0x140001937  mov     rax, [rbp+0A0h+arg_78]
0x14000193e  mov     [rbp+0A0h+var_80], rcx
0x140001942  mov     [rbp+0A0h+var_74], edi
0x140001945  mov     [rbp+0A0h+var_88], 4
0x14000194d  mov     rcx, [rax]
0x140001950  test    rcx, rcx
0x140001953  jz      short loc_14000196A
0x140001955  mov     rax, rdx
0x140001958  inc     rax
0x14000195b  cmp     [rcx+rax*2], di
0x14000195f  jnz     short loc_140001958
0x140001961  lea     eax, ds:2[rax*2]
0x140001968  jmp     short loc_140001974
0x14000196a  lea     rcx, qword_140013B88
0x140001971  mov     eax, r9d
0x140001974  mov     [rbp+0A0h+var_98], eax
0x140001977  mov     rax, [rbp+0A0h+arg_70]
0x14000197e  mov     [rbp+0A0h+var_A0], rcx
0x140001982  mov     [rbp+0A0h+var_94], edi
0x140001985  mov     rcx, [rax]
0x140001988  test    rcx, rcx
0x14000198b  jz      short loc_14000199D
0x14000198d  mov     rax, rdx
0x140001990  inc     rax
0x140001993  cmp     [rcx+rax], dil
0x140001997  jnz     short loc_140001990
0x140001999  inc     eax
0x14000199b  jmp     short loc_1400019A3
0x14000199d  mov     rcx, rsi
0x1400019a0  mov     eax, r8d
0x1400019a3  mov     [rbp+0A0h+var_A8], eax
0x1400019a6  mov     rax, [rbp+0A0h+arg_68]
0x1400019ad  mov     [rbp+0A0h+var_C0], rax
0x1400019b1  mov     rax, [rbp+0A0h+arg_60]
0x1400019b8  mov     [rbp+0A0h+var_B0], rcx
0x1400019bc  mov     [rbp+0A0h+var_A4], edi
0x1400019bf  mov     [rbp+0A0h+var_B8], 4
0x1400019c7  mov     rcx, [rax]
0x1400019ca  test    rcx, rcx
0x1400019cd  jz      short loc_1400019DF
0x1400019cf  mov     rax, rdx
0x1400019d2  inc     rax
0x1400019d5  cmp     [rcx+rax], dil
0x1400019d9  jnz     short loc_1400019D2
0x1400019db  inc     eax
0x1400019dd  jmp     short loc_1400019E5
0x1400019df  mov     rcx, rsi
0x1400019e2  mov     eax, r8d
0x1400019e5  mov     [rbp+0A0h+var_C8], eax
0x1400019e8  mov     rax, [rbp+0A0h+arg_58]
0x1400019ef  mov     [rbp+0A0h+var_E0], rax
0x1400019f3  mov     rax, [rbp+0A0h+arg_50]
0x1400019fa  mov     [rbp+0A0h+var_D0], rcx
0x1400019fe  mov     [rbp+0A0h+var_C4], edi
0x140001a01  mov     [rbp+0A0h+var_D8], 4
0x140001a09  mov     rcx, [rax]
0x140001a0c  test    rcx, rcx
0x140001a0f  jz      short loc_140001A27
0x140001a11  mov     rax, rdx
0x140001a14  inc     rax
0x140001a17  cmp     [rcx+rax*2], di
0x140001a1b  jnz     short loc_140001A14
0x140001a1d  lea     r9d, ds:2[rax*2]
0x140001a25  jmp     short loc_140001A2E
0x140001a27  lea     rcx, qword_140013B88
0x140001a2e  mov     rax, [rbp+0A0h+arg_48]
0x140001a35  mov     [rbp+0A0h+var_100], rax
0x140001a39  mov     rax, [rbp+0A0h+arg_40]
0x140001a40  mov     [rbp+0A0h+var_F0], rcx
0x140001a44  mov     [rbp+0A0h+var_E8], r9d
0x140001a48  mov     [rbp+0A0h+var_E4], edi
0x140001a4b  mov     rcx, [rax]
0x140001a4e  mov     [rbp+0A0h+var_F8], 4
0x140001a56  test    rcx, rcx
0x140001a59  jz      short loc_140001A6B
0x140001a5b  mov     rax, rdx
0x140001a5e  inc     rax
0x140001a61  cmp     [rcx+rax], dil
0x140001a65  jnz     short loc_140001A5E
0x140001a67  inc     eax
0x140001a69  jmp     short loc_140001A71
0x140001a6b  mov     rcx, rsi
0x140001a6e  mov     eax, r8d
0x140001a71  mov     [rbp+0A0h+var_108], eax
0x140001a74  mov     rax, [rbp+0A0h+arg_38]
0x140001a7b  mov     [rbp+0A0h+var_120], rax
0x140001a7f  mov     rax, [rbp+0A0h+arg_30]
0x140001a86  mov     [rbp+0A0h+var_110], rcx
0x140001a8a  mov     [rbp+0A0h+var_104], edi
0x140001a8d  mov     [rbp+0A0h+var_118], 4
0x140001a95  mov     rcx, [rax]
0x140001a98  test    rcx, rcx
0x140001a9b  jz      short loc_140001AAC
0x140001a9d  inc     rdx
0x140001aa0  cmp     [rcx+rdx], dil
0x140001aa4  jnz     short loc_140001A9D
0x140001aa6  lea     r8d, [rdx+1]
0x140001aaa  jmp     short loc_140001AAF
0x140001aac  mov     rcx, rsi
0x140001aaf  mov     rax, [rbp+0A0h+arg_28]
0x140001ab6  xor     r9d, r9d
0x140001ab9  mov     [rsp+1A0h+var_140], rax
0x140001abe  mov     rdx, r11
0x140001ac1  mov     rax, [rbp+0A0h+arg_20]
0x140001ac8  mov     [rsp+1A0h+var_150], rax
0x140001acd  lea     rax, [rsp+1A0h+var_170]
0x140001ad2  mov     [rsp+1A0h+var_130], rcx
0x140001ad7  mov     rcx, r10
0x140001ada  mov     [rsp+1A0h+var_128], r8d
0x140001adf  mov     r8, rbx
0x140001ae2  mov     [rsp+1A0h+var_178], rax
0x140001ae7  mov     [rsp+1A0h+var_180], 14h
0x140001aef  mov     [rsp+1A0h+var_124], edi
0x140001af3  mov     [rsp+1A0h+var_138], 4
0x140001afc  mov     [rsp+1A0h+var_148], 8
0x140001b05  call    _tlgWriteTransfer_EventWriteTransfer
0x140001b0a  mov     rcx, [rbp+0A0h+var_30]
0x140001b0e  xor     rcx, rsp; StackCookie
0x140001b11  call    __security_check_cookie
0x140001b16  add     rsp, 180h
0x140001b1d  pop     r15
0x140001b1f  pop     rdi
0x140001b20  pop     rsi
0x140001b21  pop     rbx
0x140001b22  pop     rbp
0x140001b23  retn
```
