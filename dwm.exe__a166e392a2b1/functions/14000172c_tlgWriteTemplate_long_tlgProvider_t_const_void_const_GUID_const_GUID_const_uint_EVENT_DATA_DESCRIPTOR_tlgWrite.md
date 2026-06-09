# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)

- ea: `0x14000172c`
- end: `0x140001a1b`
- name: `??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456445@Z`
- size: `751`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x14000a660`

## callees

- `0x14000172c`
- `0x140001b88`
- `0x140005530`

## pseudocode

```c
__int64 __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
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
  int v25; // r8d
  const unsigned __int16 *v26; // rcx
  __int64 v27; // rax
  int v28; // eax
  int v29; // r9d
  __int64 *v30; // rcx
  __int64 v31; // rax
  int v32; // eax
  const unsigned __int16 *v33; // rcx
  __int64 v34; // rax
  int v35; // eax
  __int64 *v36; // rcx
  __int64 v37; // rax
  int v38; // eax
  const unsigned __int16 *v39; // rcx
  __int64 v40; // rax
  int v41; // eax
  const unsigned __int16 *v42; // rcx
  __int64 v43; // rax
  int v44; // eax
  __int64 *v45; // rcx
  __int64 v46; // rax
  const unsigned __int16 *v47; // rcx
  __int64 v48; // rax
  int v49; // eax
  const unsigned __int16 *v50; // rcx
  _BYTE v52[32]; // [rsp+30h] [rbp-D0h] BYREF
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
  __int64 *v67; // [rsp+B0h] [rbp-50h]
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
  __int64 *v80; // [rsp+100h] [rbp+0h]
  int v81; // [rsp+108h] [rbp+8h]
  int v82; // [rsp+10Ch] [rbp+Ch]
  __int64 v83; // [rsp+110h] [rbp+10h]
  __int64 v84; // [rsp+118h] [rbp+18h]
  const unsigned __int16 *v85; // [rsp+120h] [rbp+20h]
  int v86; // [rsp+128h] [rbp+28h]
  int v87; // [rsp+12Ch] [rbp+2Ch]
  __int64 *v88; // [rsp+130h] [rbp+30h]
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
    v26 = &dword_1400128B4;
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
    v30 = &qword_1400128B8;
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
    v33 = &dword_1400128B4;
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
    v36 = &qword_1400128B8;
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
    v39 = &dword_1400128B4;
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
    v42 = &dword_1400128B4;
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
    v45 = &qword_1400128B8;
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
    v47 = &dword_1400128B4;
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
    v50 = &dword_1400128B4;
  }
  v55 = a6;
  v53 = a5;
  v57 = v50;
  v58 = v25;
  v59 = 0;
  v56 = 4;
  v54 = 8;
  return tlgWriteTransfer_EtwEventWriteTransfer(a1, a2, 0, 0, 20, (__int64)v52);
}

```

## disassembly

```asm
0x14000172c  mov     [rsp-8+arg_10], rbx
0x140001731  push    rbp
0x140001732  push    rdi
0x140001733  push    r14
0x140001735  lea     rbp, [rsp-80h]
0x14000173a  sub     rsp, 180h
0x140001741  mov     rax, cs:__security_cookie
0x140001748  xor     rax, rsp
0x14000174b  mov     [rbp+90h+var_20], rax
0x14000174f  mov     rax, [rbp+90h+arg_A8]
0x140001756  lea     rdi, dword_1400128B4
0x14000175d  mov     r11, rdx
0x140001760  mov     r10, rcx
0x140001763  or      rdx, 0FFFFFFFFFFFFFFFFh
0x140001767  xor     ebx, ebx
0x140001769  mov     r8d, 1
0x14000176f  mov     rcx, [rax]
0x140001772  test    rcx, rcx
0x140001775  jz      short loc_140001786
0x140001777  mov     rax, rdx
0x14000177a  inc     rax
0x14000177d  cmp     [rcx+rax], bl
0x140001780  jnz     short loc_14000177A
0x140001782  inc     eax
0x140001784  jmp     short loc_14000178C
0x140001786  mov     rcx, rdi
0x140001789  mov     eax, r8d
0x14000178c  mov     [rbp+90h+var_28], eax
0x14000178f  mov     r9d, 2
0x140001795  mov     rax, [rbp+90h+arg_A0]
0x14000179c  mov     [rbp+90h+var_40], rax
0x1400017a0  mov     rax, [rbp+90h+arg_98]
0x1400017a7  mov     [rbp+90h+var_50], rax
0x1400017ab  mov     rax, [rbp+90h+arg_90]
0x1400017b2  mov     [rbp+90h+var_30], rcx
0x1400017b6  mov     [rbp+90h+var_24], ebx
0x1400017b9  mov     [rbp+90h+var_38], 4
0x1400017c1  mov     rcx, [rax]
0x1400017c4  mov     [rbp+90h+var_48], 4
0x1400017cc  test    rcx, rcx
0x1400017cf  jz      short loc_1400017E6
0x1400017d1  mov     rax, rdx
0x1400017d4  inc     rax
0x1400017d7  cmp     [rcx+rax*2], bx
0x1400017db  jnz     short loc_1400017D4
0x1400017dd  lea     eax, ds:2[rax*2]
0x1400017e4  jmp     short loc_1400017F0
0x1400017e6  lea     rcx, qword_1400128B8
0x1400017ed  mov     eax, r9d
0x1400017f0  mov     [rbp+90h+var_58], eax
0x1400017f3  mov     rax, [rbp+90h+arg_88]
0x1400017fa  mov     [rbp+90h+var_60], rcx
0x1400017fe  mov     [rbp+90h+var_54], ebx
0x140001801  mov     rcx, [rax]
0x140001804  test    rcx, rcx
0x140001807  jz      short loc_140001818
0x140001809  mov     rax, rdx
0x14000180c  inc     rax
0x14000180f  cmp     [rcx+rax], bl
0x140001812  jnz     short loc_14000180C
0x140001814  inc     eax
0x140001816  jmp     short loc_14000181E
0x140001818  mov     rcx, rdi
0x14000181b  mov     eax, r8d
0x14000181e  mov     [rbp+90h+var_68], eax
0x140001821  mov     rax, [rbp+90h+arg_80]
0x140001828  mov     [rbp+90h+var_80], rax
0x14000182c  mov     rax, [rbp+90h+arg_78]
0x140001833  mov     [rbp+90h+var_70], rcx
0x140001837  mov     [rbp+90h+var_64], ebx
0x14000183a  mov     [rbp+90h+var_78], 4
0x140001842  mov     rcx, [rax]
0x140001845  test    rcx, rcx
0x140001848  jz      short loc_14000185F
0x14000184a  mov     rax, rdx
0x14000184d  inc     rax
0x140001850  cmp     [rcx+rax*2], bx
0x140001854  jnz     short loc_14000184D
0x140001856  lea     eax, ds:2[rax*2]
0x14000185d  jmp     short loc_140001869
0x14000185f  lea     rcx, qword_1400128B8
0x140001866  mov     eax, r9d
0x140001869  mov     [rbp+90h+var_88], eax
0x14000186c  mov     rax, [rbp+90h+arg_70]
0x140001873  mov     [rbp+90h+var_90], rcx
0x140001877  mov     [rbp+90h+var_84], ebx
0x14000187a  mov     rcx, [rax]
0x14000187d  test    rcx, rcx
0x140001880  jz      short loc_140001891
0x140001882  mov     rax, rdx
0x140001885  inc     rax
0x140001888  cmp     [rcx+rax], bl
0x14000188b  jnz     short loc_140001885
0x14000188d  inc     eax
0x14000188f  jmp     short loc_140001897
0x140001891  mov     rcx, rdi
0x140001894  mov     eax, r8d
0x140001897  mov     [rbp+90h+var_98], eax
0x14000189a  mov     rax, [rbp+90h+arg_68]
0x1400018a1  mov     [rbp+90h+var_B0], rax
0x1400018a5  mov     rax, [rbp+90h+arg_60]
0x1400018ac  mov     [rbp+90h+var_A0], rcx
0x1400018b0  mov     [rbp+90h+var_94], ebx
0x1400018b3  mov     [rbp+90h+var_A8], 4
0x1400018bb  mov     rcx, [rax]
0x1400018be  test    rcx, rcx
0x1400018c1  jz      short loc_1400018D2
0x1400018c3  mov     rax, rdx
0x1400018c6  inc     rax
0x1400018c9  cmp     [rcx+rax], bl
0x1400018cc  jnz     short loc_1400018C6
0x1400018ce  inc     eax
0x1400018d0  jmp     short loc_1400018D8
0x1400018d2  mov     rcx, rdi
0x1400018d5  mov     eax, r8d
0x1400018d8  mov     [rbp+90h+var_B8], eax
0x1400018db  mov     rax, [rbp+90h+arg_58]
0x1400018e2  mov     [rbp+90h+var_D0], rax
0x1400018e6  mov     rax, [rbp+90h+arg_50]
0x1400018ed  mov     [rbp+90h+var_C0], rcx
0x1400018f1  mov     [rbp+90h+var_B4], ebx
0x1400018f4  mov     [rbp+90h+var_C8], 4
0x1400018fc  mov     rcx, [rax]
0x1400018ff  test    rcx, rcx
0x140001902  jz      short loc_14000191A
0x140001904  mov     rax, rdx
0x140001907  inc     rax
0x14000190a  cmp     [rcx+rax*2], bx
0x14000190e  jnz     short loc_140001907
0x140001910  lea     r9d, ds:2[rax*2]
0x140001918  jmp     short loc_140001921
0x14000191a  lea     rcx, qword_1400128B8
0x140001921  mov     rax, [rbp+90h+arg_48]
0x140001928  mov     [rbp+90h+var_F0], rax
0x14000192c  mov     rax, [rbp+90h+arg_40]
0x140001933  mov     [rbp+90h+var_E0], rcx
0x140001937  mov     [rbp+90h+var_D8], r9d
0x14000193b  mov     [rbp+90h+var_D4], ebx
0x14000193e  mov     rcx, [rax]
0x140001941  mov     [rbp+90h+var_E8], 4
0x140001949  test    rcx, rcx
0x14000194c  jz      short loc_14000195D
0x14000194e  mov     rax, rdx
0x140001951  inc     rax
0x140001954  cmp     [rcx+rax], bl
0x140001957  jnz     short loc_140001951
0x140001959  inc     eax
0x14000195b  jmp     short loc_140001963
0x14000195d  mov     rcx, rdi
0x140001960  mov     eax, r8d
0x140001963  mov     [rbp+90h+var_F8], eax
0x140001966  mov     rax, [rbp+90h+arg_38]
0x14000196d  mov     [rbp+90h+var_110], rax
0x140001971  mov     rax, [rbp+90h+arg_30]
0x140001978  mov     [rbp+90h+var_100], rcx
0x14000197c  mov     [rbp+90h+var_F4], ebx
0x14000197f  mov     [rbp+90h+var_108], 4
0x140001987  mov     rcx, [rax]
0x14000198a  test    rcx, rcx
0x14000198d  jz      short loc_14000199D
0x14000198f  inc     rdx
0x140001992  cmp     [rcx+rdx], bl
0x140001995  jnz     short loc_14000198F
0x140001997  lea     r8d, [rdx+1]
0x14000199b  jmp     short loc_1400019A0
0x14000199d  mov     rcx, rdi
0x1400019a0  mov     rax, [rbp+90h+arg_28]
0x1400019a7  xor     r9d, r9d
0x1400019aa  mov     [rsp+190h+var_130], rax
0x1400019af  mov     rdx, r11
0x1400019b2  mov     rax, [rbp+90h+arg_20]
0x1400019b9  mov     [rsp+190h+var_140], rax
0x1400019be  lea     rax, [rsp+190h+var_160]
0x1400019c3  mov     [rsp+190h+var_120], rcx
0x1400019c8  mov     rcx, r10
0x1400019cb  mov     [rsp+190h+var_118], r8d
0x1400019d0  xor     r8d, r8d
0x1400019d3  mov     [rsp+190h+var_168], rax
0x1400019d8  mov     [rsp+190h+var_170], 14h
0x1400019e0  mov     [rsp+190h+var_114], ebx
0x1400019e4  mov     [rsp+190h+var_128], 4
0x1400019ed  mov     [rsp+190h+var_138], 8
0x1400019f6  call    _tlgWriteTransfer_EtwEventWriteTransfer
0x1400019fb  mov     rcx, [rbp+90h+var_20]
0x1400019ff  xor     rcx, rsp; StackCookie
0x140001a02  call    __security_check_cookie
0x140001a07  mov     rbx, [rsp+190h+arg_10]
0x140001a0f  add     rsp, 180h
0x140001a16  pop     r14
0x140001a18  pop     rdi
0x140001a19  pop     rbp
0x140001a1a  retn
```
