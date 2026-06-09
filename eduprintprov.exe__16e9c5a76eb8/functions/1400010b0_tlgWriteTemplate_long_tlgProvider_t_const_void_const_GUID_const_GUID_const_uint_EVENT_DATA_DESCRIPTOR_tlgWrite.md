# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)

- ea: `0x1400010b0`
- end: `0x14000135d`
- name: `??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456@Z`
- size: `685`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x14000dae4`
- `0x140012ae0`

## callees

- `0x1400010b0`
- `0x1400016dc`
- `0x140002600`

## pseudocode

```c
ULONG __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
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
        int **a12,
        __int64 a13,
        const unsigned __int16 **a14,
        __int64 a15,
        const unsigned __int16 **a16,
        int **a17,
        __int64 a18,
        const unsigned __int16 **a19,
        int **a20)
{
  __int64 v22; // rdx
  int v24; // r9d
  int *v25; // rcx
  __int64 v26; // rax
  int v27; // eax
  int v28; // r8d
  const unsigned __int16 *v29; // rcx
  __int64 v30; // rax
  int v31; // eax
  int *v32; // rcx
  __int64 v33; // rax
  int v34; // eax
  const unsigned __int16 *v35; // rcx
  __int64 v36; // rax
  int v37; // eax
  const unsigned __int16 *v38; // rcx
  __int64 v39; // rax
  int v40; // eax
  int *v41; // rcx
  __int64 v42; // rax
  const unsigned __int16 *v43; // rcx
  __int64 v44; // rax
  int v45; // eax
  const unsigned __int16 *v46; // rcx
  struct _EVENT_DATA_DESCRIPTOR v48; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v49; // [rsp+50h] [rbp-B0h]
  __int64 v50; // [rsp+58h] [rbp-A8h]
  __int64 v51; // [rsp+60h] [rbp-A0h]
  __int64 v52; // [rsp+68h] [rbp-98h]
  __int64 v53; // [rsp+70h] [rbp-90h]
  __int64 v54; // [rsp+78h] [rbp-88h]
  const unsigned __int16 *v55; // [rsp+80h] [rbp-80h]
  int v56; // [rsp+88h] [rbp-78h]
  int v57; // [rsp+8Ch] [rbp-74h]
  __int64 v58; // [rsp+90h] [rbp-70h]
  __int64 v59; // [rsp+98h] [rbp-68h]
  const unsigned __int16 *v60; // [rsp+A0h] [rbp-60h]
  int v61; // [rsp+A8h] [rbp-58h]
  int v62; // [rsp+ACh] [rbp-54h]
  __int64 v63; // [rsp+B0h] [rbp-50h]
  __int64 v64; // [rsp+B8h] [rbp-48h]
  int *v65; // [rsp+C0h] [rbp-40h]
  int v66; // [rsp+C8h] [rbp-38h]
  int v67; // [rsp+CCh] [rbp-34h]
  __int64 v68; // [rsp+D0h] [rbp-30h]
  __int64 v69; // [rsp+D8h] [rbp-28h]
  const unsigned __int16 *v70; // [rsp+E0h] [rbp-20h]
  int v71; // [rsp+E8h] [rbp-18h]
  int v72; // [rsp+ECh] [rbp-14h]
  __int64 v73; // [rsp+F0h] [rbp-10h]
  __int64 v74; // [rsp+F8h] [rbp-8h]
  const unsigned __int16 *v75; // [rsp+100h] [rbp+0h]
  int v76; // [rsp+108h] [rbp+8h]
  int v77; // [rsp+10Ch] [rbp+Ch]
  int *v78; // [rsp+110h] [rbp+10h]
  int v79; // [rsp+118h] [rbp+18h]
  int v80; // [rsp+11Ch] [rbp+1Ch]
  __int64 v81; // [rsp+120h] [rbp+20h]
  __int64 v82; // [rsp+128h] [rbp+28h]
  const unsigned __int16 *v83; // [rsp+130h] [rbp+30h]
  int v84; // [rsp+138h] [rbp+38h]
  int v85; // [rsp+13Ch] [rbp+3Ch]
  int *v86; // [rsp+140h] [rbp+40h]
  int v87; // [rsp+148h] [rbp+48h]
  int v88; // [rsp+14Ch] [rbp+4Ch]

  v22 = -1;
  v24 = 2;
  v25 = *a20;
  if ( *a20 )
  {
    v26 = -1;
    do
      ++v26;
    while ( *((_WORD *)v25 + v26) );
    v27 = 2 * v26 + 2;
  }
  else
  {
    v25 = &dword_140015CE4;
    v27 = 2;
  }
  v87 = v27;
  v28 = 1;
  v86 = v25;
  v88 = 0;
  v29 = *a19;
  if ( *a19 )
  {
    v30 = -1;
    do
      ++v30;
    while ( *((_BYTE *)v29 + v30) );
    v31 = v30 + 1;
  }
  else
  {
    v29 = &byte_140015CE0;
    v31 = 1;
  }
  v84 = v31;
  v81 = a18;
  v83 = v29;
  v85 = 0;
  v82 = 4;
  v32 = *a17;
  if ( *a17 )
  {
    v33 = -1;
    do
      ++v33;
    while ( *((_WORD *)v32 + v33) );
    v34 = 2 * v33 + 2;
  }
  else
  {
    v32 = &dword_140015CE4;
    v34 = 2;
  }
  v79 = v34;
  v78 = v32;
  v80 = 0;
  v35 = *a16;
  if ( *a16 )
  {
    v36 = -1;
    do
      ++v36;
    while ( *((_BYTE *)v35 + v36) );
    v37 = v36 + 1;
  }
  else
  {
    v35 = &byte_140015CE0;
    v37 = 1;
  }
  v76 = v37;
  v73 = a15;
  v75 = v35;
  v77 = 0;
  v74 = 4;
  v38 = *a14;
  if ( *a14 )
  {
    v39 = -1;
    do
      ++v39;
    while ( *((_BYTE *)v38 + v39) );
    v40 = v39 + 1;
  }
  else
  {
    v38 = &byte_140015CE0;
    v40 = 1;
  }
  v71 = v40;
  v68 = a13;
  v70 = v38;
  v72 = 0;
  v69 = 4;
  v41 = *a12;
  if ( *a12 )
  {
    v42 = -1;
    do
      ++v42;
    while ( *((_WORD *)v41 + v42) );
    v24 = 2 * v42 + 2;
  }
  else
  {
    v41 = &dword_140015CE4;
  }
  v63 = a11;
  v65 = v41;
  v66 = v24;
  v67 = 0;
  v43 = *a10;
  v64 = 4;
  if ( v43 )
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
  v61 = v45;
  v58 = a9;
  v60 = v43;
  v62 = 0;
  v59 = 4;
  v46 = *a8;
  if ( *a8 )
  {
    do
      ++v22;
    while ( *((_BYTE *)v46 + v22) );
    v28 = v22 + 1;
  }
  else
  {
    v46 = &byte_140015CE0;
  }
  v53 = a7;
  v51 = a6;
  v49 = a5;
  v55 = v46;
  v56 = v28;
  v57 = 0;
  v54 = 4;
  v52 = 8;
  v50 = 8;
  return tlgWriteTransfer_EventWriteTransfer(a1, a2, a3, 0, 0x12u, &v48);
}

```

## disassembly

```asm
0x1400010b0  push    rbp
0x1400010b2  push    rbx
0x1400010b3  push    rsi
0x1400010b4  push    rdi
0x1400010b5  push    r14
0x1400010b7  lea     rbp, [rsp-60h]
0x1400010bc  sub     rsp, 160h
0x1400010c3  mov     rax, cs:__security_cookie
0x1400010ca  xor     rax, rsp
0x1400010cd  mov     [rbp+80h+var_30], rax
0x1400010d1  mov     rax, [rbp+80h+arg_98]
0x1400010d8  mov     r11, rdx
0x1400010db  mov     r10, rcx
0x1400010de  or      rdx, 0FFFFFFFFFFFFFFFFh
0x1400010e2  xor     edi, edi
0x1400010e4  mov     rbx, r8
0x1400010e7  mov     r9d, 2
0x1400010ed  mov     rcx, [rax]
0x1400010f0  test    rcx, rcx
0x1400010f3  jz      short loc_14000110A
0x1400010f5  mov     rax, rdx
0x1400010f8  inc     rax
0x1400010fb  cmp     [rcx+rax*2], di
0x1400010ff  jnz     short loc_1400010F8
0x140001101  lea     eax, ds:2[rax*2]
0x140001108  jmp     short loc_140001114
0x14000110a  lea     rcx, dword_140015CE4
0x140001111  mov     eax, r9d
0x140001114  mov     [rbp+80h+var_38], eax
0x140001117  lea     rsi, byte_140015CE0
0x14000111e  mov     rax, [rbp+80h+arg_90]
0x140001125  mov     r8d, 1
0x14000112b  mov     [rbp+80h+var_40], rcx
0x14000112f  mov     [rbp+80h+var_34], edi
0x140001132  mov     rcx, [rax]
0x140001135  test    rcx, rcx
0x140001138  jz      short loc_14000114A
0x14000113a  mov     rax, rdx
0x14000113d  inc     rax
0x140001140  cmp     [rcx+rax], dil
0x140001144  jnz     short loc_14000113D
0x140001146  inc     eax
0x140001148  jmp     short loc_140001150
0x14000114a  mov     rcx, rsi
0x14000114d  mov     eax, r8d
0x140001150  mov     [rbp+80h+var_48], eax
0x140001153  mov     rax, [rbp+80h+arg_88]
0x14000115a  mov     [rbp+80h+var_60], rax
0x14000115e  mov     rax, [rbp+80h+arg_80]
0x140001165  mov     [rbp+80h+var_50], rcx
0x140001169  mov     [rbp+80h+var_44], edi
0x14000116c  mov     [rbp+80h+var_58], 4
0x140001174  mov     rcx, [rax]
0x140001177  test    rcx, rcx
0x14000117a  jz      short loc_140001191
0x14000117c  mov     rax, rdx
0x14000117f  inc     rax
0x140001182  cmp     [rcx+rax*2], di
0x140001186  jnz     short loc_14000117F
0x140001188  lea     eax, ds:2[rax*2]
0x14000118f  jmp     short loc_14000119B
0x140001191  lea     rcx, dword_140015CE4
0x140001198  mov     eax, r9d
0x14000119b  mov     [rbp+80h+var_68], eax
0x14000119e  mov     rax, [rbp+80h+arg_78]
0x1400011a5  mov     [rbp+80h+var_70], rcx
0x1400011a9  mov     [rbp+80h+var_64], edi
0x1400011ac  mov     rcx, [rax]
0x1400011af  test    rcx, rcx
0x1400011b2  jz      short loc_1400011C4
0x1400011b4  mov     rax, rdx
0x1400011b7  inc     rax
0x1400011ba  cmp     [rcx+rax], dil
0x1400011be  jnz     short loc_1400011B7
0x1400011c0  inc     eax
0x1400011c2  jmp     short loc_1400011CA
0x1400011c4  mov     rcx, rsi
0x1400011c7  mov     eax, r8d
0x1400011ca  mov     [rbp+80h+var_78], eax
0x1400011cd  mov     rax, [rbp+80h+arg_70]
0x1400011d4  mov     [rbp+80h+var_90], rax
0x1400011d8  mov     rax, [rbp+80h+arg_68]
0x1400011df  mov     [rbp+80h+var_80], rcx
0x1400011e3  mov     [rbp+80h+var_74], edi
0x1400011e6  mov     [rbp+80h+var_88], 4
0x1400011ee  mov     rcx, [rax]
0x1400011f1  test    rcx, rcx
0x1400011f4  jz      short loc_140001206
0x1400011f6  mov     rax, rdx
0x1400011f9  inc     rax
0x1400011fc  cmp     [rcx+rax], dil
0x140001200  jnz     short loc_1400011F9
0x140001202  inc     eax
0x140001204  jmp     short loc_14000120C
0x140001206  mov     rcx, rsi
0x140001209  mov     eax, r8d
0x14000120c  mov     [rbp+80h+var_98], eax
0x14000120f  mov     rax, [rbp+80h+arg_60]
0x140001216  mov     [rbp+80h+var_B0], rax
0x14000121a  mov     rax, [rbp+80h+arg_58]
0x140001221  mov     [rbp+80h+var_A0], rcx
0x140001225  mov     [rbp+80h+var_94], edi
0x140001228  mov     [rbp+80h+var_A8], 4
0x140001230  mov     rcx, [rax]
0x140001233  test    rcx, rcx
0x140001236  jz      short loc_14000124E
0x140001238  mov     rax, rdx
0x14000123b  inc     rax
0x14000123e  cmp     [rcx+rax*2], di
0x140001242  jnz     short loc_14000123B
0x140001244  lea     r9d, ds:2[rax*2]
0x14000124c  jmp     short loc_140001255
0x14000124e  lea     rcx, dword_140015CE4
0x140001255  mov     rax, [rbp+80h+arg_50]
0x14000125c  mov     [rbp+80h+var_D0], rax
0x140001260  mov     rax, [rbp+80h+arg_48]
0x140001267  mov     [rbp+80h+var_C0], rcx
0x14000126b  mov     [rbp+80h+var_B8], r9d
0x14000126f  mov     [rbp+80h+var_B4], edi
0x140001272  mov     rcx, [rax]
0x140001275  mov     [rbp+80h+var_C8], 4
0x14000127d  test    rcx, rcx
0x140001280  jz      short loc_140001292
0x140001282  mov     rax, rdx
0x140001285  inc     rax
0x140001288  cmp     [rcx+rax], dil
0x14000128c  jnz     short loc_140001285
0x14000128e  inc     eax
0x140001290  jmp     short loc_140001298
0x140001292  mov     rcx, rsi
0x140001295  mov     eax, r8d
0x140001298  mov     [rbp+80h+var_D8], eax
0x14000129b  mov     rax, [rbp+80h+arg_40]
0x1400012a2  mov     [rbp+80h+var_F0], rax
0x1400012a6  mov     rax, [rbp+80h+arg_38]
0x1400012ad  mov     [rbp+80h+var_E0], rcx
0x1400012b1  mov     [rbp+80h+var_D4], edi
0x1400012b4  mov     [rbp+80h+var_E8], 4
0x1400012bc  mov     rcx, [rax]
0x1400012bf  test    rcx, rcx
0x1400012c2  jz      short loc_1400012D3
0x1400012c4  inc     rdx
0x1400012c7  cmp     [rcx+rdx], dil
0x1400012cb  jnz     short loc_1400012C4
0x1400012cd  lea     r8d, [rdx+1]
0x1400012d1  jmp     short loc_1400012D6
0x1400012d3  mov     rcx, rsi
0x1400012d6  mov     rax, [rbp+80h+arg_30]
0x1400012dd  xor     r9d, r9d
0x1400012e0  mov     [rsp+180h+var_110], rax
0x1400012e5  mov     rdx, r11
0x1400012e8  mov     rax, [rbp+80h+arg_28]
0x1400012ef  mov     [rsp+180h+var_120], rax
0x1400012f4  mov     rax, [rbp+80h+arg_20]
0x1400012fb  mov     [rsp+180h+var_130], rax
0x140001300  lea     rax, [rsp+180h+var_150]
0x140001305  mov     [rbp+80h+var_100], rcx
0x140001309  mov     rcx, r10
0x14000130c  mov     [rbp+80h+var_F8], r8d
0x140001310  mov     r8, rbx
0x140001313  mov     [rsp+180h+var_158], rax
0x140001318  mov     [rsp+180h+var_160], 12h
0x140001320  mov     [rbp+80h+var_F4], edi
0x140001323  mov     [rsp+180h+var_108], 4
0x14000132c  mov     [rsp+180h+var_118], 8
0x140001335  mov     [rsp+180h+var_128], 8
0x14000133e  call    _tlgWriteTransfer_EventWriteTransfer
0x140001343  mov     rcx, [rbp+80h+var_30]
0x140001347  xor     rcx, rsp; StackCookie
0x14000134a  call    __security_check_cookie
0x14000134f  add     rsp, 160h
0x140001356  pop     r14
0x140001358  pop     rdi
0x140001359  pop     rsi
0x14000135a  pop     rbx
0x14000135b  pop     rbp
0x14000135c  retn
```
