# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)

- ea: `0x1800010f8`
- end: `0x1800013a5`
- name: `??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456@Z`
- size: `685`
- prototype: ``
- caller_count: `13`
- callee_count: `3`
- tags: ``

## callers

- `0x1800085ac`
- `0x180009190`
- `0x1800093c0`
- `0x1800095f0`
- `0x180009820`
- `0x180013cf0`
- `0x180013f20`
- `0x180014150`
- `0x180014380`
- `0x1800145b0`
- `0x1800147e0`
- `0x180014a10`
- `0x180014c40`

## callees

- `0x180001058`
- `0x1800010f8`
- `0x180018a80`

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
        __int64 **a12,
        __int64 a13,
        const unsigned __int16 **a14,
        __int64 a15,
        const unsigned __int16 **a16,
        __int64 **a17,
        __int64 a18,
        const unsigned __int16 **a19,
        __int64 **a20)
{
  __int64 v22; // rdx
  int v24; // r9d
  __int64 *v25; // rcx
  __int64 v26; // rax
  int v27; // eax
  int v28; // r8d
  const unsigned __int16 *v29; // rcx
  __int64 v30; // rax
  int v31; // eax
  __int64 *v32; // rcx
  __int64 v33; // rax
  int v34; // eax
  const unsigned __int16 *v35; // rcx
  __int64 v36; // rax
  int v37; // eax
  const unsigned __int16 *v38; // rcx
  __int64 v39; // rax
  int v40; // eax
  __int64 *v41; // rcx
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
  __int64 *v65; // [rsp+C0h] [rbp-40h]
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
  __int64 *v78; // [rsp+110h] [rbp+10h]
  int v79; // [rsp+118h] [rbp+18h]
  int v80; // [rsp+11Ch] [rbp+1Ch]
  __int64 v81; // [rsp+120h] [rbp+20h]
  __int64 v82; // [rsp+128h] [rbp+28h]
  const unsigned __int16 *v83; // [rsp+130h] [rbp+30h]
  int v84; // [rsp+138h] [rbp+38h]
  int v85; // [rsp+13Ch] [rbp+3Ch]
  __int64 *v86; // [rsp+140h] [rbp+40h]
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
    v25 = &qword_18001E1A0;
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
    v29 = &word_18001D746;
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
    v32 = &qword_18001E1A0;
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
    v35 = &word_18001D746;
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
    v38 = &word_18001D746;
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
    v41 = &qword_18001E1A0;
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
    v43 = &word_18001D746;
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
    v46 = &word_18001D746;
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
0x1800010f8  push    rbp
0x1800010fa  push    rbx
0x1800010fb  push    rsi
0x1800010fc  push    rdi
0x1800010fd  push    r14
0x1800010ff  lea     rbp, [rsp-60h]
0x180001104  sub     rsp, 160h
0x18000110b  mov     rax, cs:__security_cookie
0x180001112  xor     rax, rsp
0x180001115  mov     [rbp+80h+var_30], rax
0x180001119  mov     rax, [rbp+80h+arg_98]
0x180001120  mov     r11, rdx
0x180001123  mov     r10, rcx
0x180001126  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18000112a  xor     edi, edi
0x18000112c  mov     rbx, r8
0x18000112f  mov     r9d, 2
0x180001135  mov     rcx, [rax]
0x180001138  test    rcx, rcx
0x18000113b  jz      short loc_180001152
0x18000113d  mov     rax, rdx
0x180001140  inc     rax
0x180001143  cmp     [rcx+rax*2], di
0x180001147  jnz     short loc_180001140
0x180001149  lea     eax, ds:2[rax*2]
0x180001150  jmp     short loc_18000115C
0x180001152  lea     rcx, qword_18001E1A0
0x180001159  mov     eax, r9d
0x18000115c  mov     [rbp+80h+var_38], eax
0x18000115f  lea     rsi, word_18001D746
0x180001166  mov     rax, [rbp+80h+arg_90]
0x18000116d  mov     r8d, 1
0x180001173  mov     [rbp+80h+var_40], rcx
0x180001177  mov     [rbp+80h+var_34], edi
0x18000117a  mov     rcx, [rax]
0x18000117d  test    rcx, rcx
0x180001180  jz      short loc_180001192
0x180001182  mov     rax, rdx
0x180001185  inc     rax
0x180001188  cmp     [rcx+rax], dil
0x18000118c  jnz     short loc_180001185
0x18000118e  inc     eax
0x180001190  jmp     short loc_180001198
0x180001192  mov     rcx, rsi
0x180001195  mov     eax, r8d
0x180001198  mov     [rbp+80h+var_48], eax
0x18000119b  mov     rax, [rbp+80h+arg_88]
0x1800011a2  mov     [rbp+80h+var_60], rax
0x1800011a6  mov     rax, [rbp+80h+arg_80]
0x1800011ad  mov     [rbp+80h+var_50], rcx
0x1800011b1  mov     [rbp+80h+var_44], edi
0x1800011b4  mov     [rbp+80h+var_58], 4
0x1800011bc  mov     rcx, [rax]
0x1800011bf  test    rcx, rcx
0x1800011c2  jz      short loc_1800011D9
0x1800011c4  mov     rax, rdx
0x1800011c7  inc     rax
0x1800011ca  cmp     [rcx+rax*2], di
0x1800011ce  jnz     short loc_1800011C7
0x1800011d0  lea     eax, ds:2[rax*2]
0x1800011d7  jmp     short loc_1800011E3
0x1800011d9  lea     rcx, qword_18001E1A0
0x1800011e0  mov     eax, r9d
0x1800011e3  mov     [rbp+80h+var_68], eax
0x1800011e6  mov     rax, [rbp+80h+arg_78]
0x1800011ed  mov     [rbp+80h+var_70], rcx
0x1800011f1  mov     [rbp+80h+var_64], edi
0x1800011f4  mov     rcx, [rax]
0x1800011f7  test    rcx, rcx
0x1800011fa  jz      short loc_18000120C
0x1800011fc  mov     rax, rdx
0x1800011ff  inc     rax
0x180001202  cmp     [rcx+rax], dil
0x180001206  jnz     short loc_1800011FF
0x180001208  inc     eax
0x18000120a  jmp     short loc_180001212
0x18000120c  mov     rcx, rsi
0x18000120f  mov     eax, r8d
0x180001212  mov     [rbp+80h+var_78], eax
0x180001215  mov     rax, [rbp+80h+arg_70]
0x18000121c  mov     [rbp+80h+var_90], rax
0x180001220  mov     rax, [rbp+80h+arg_68]
0x180001227  mov     [rbp+80h+var_80], rcx
0x18000122b  mov     [rbp+80h+var_74], edi
0x18000122e  mov     [rbp+80h+var_88], 4
0x180001236  mov     rcx, [rax]
0x180001239  test    rcx, rcx
0x18000123c  jz      short loc_18000124E
0x18000123e  mov     rax, rdx
0x180001241  inc     rax
0x180001244  cmp     [rcx+rax], dil
0x180001248  jnz     short loc_180001241
0x18000124a  inc     eax
0x18000124c  jmp     short loc_180001254
0x18000124e  mov     rcx, rsi
0x180001251  mov     eax, r8d
0x180001254  mov     [rbp+80h+var_98], eax
0x180001257  mov     rax, [rbp+80h+arg_60]
0x18000125e  mov     [rbp+80h+var_B0], rax
0x180001262  mov     rax, [rbp+80h+arg_58]
0x180001269  mov     [rbp+80h+var_A0], rcx
0x18000126d  mov     [rbp+80h+var_94], edi
0x180001270  mov     [rbp+80h+var_A8], 4
0x180001278  mov     rcx, [rax]
0x18000127b  test    rcx, rcx
0x18000127e  jz      short loc_180001296
0x180001280  mov     rax, rdx
0x180001283  inc     rax
0x180001286  cmp     [rcx+rax*2], di
0x18000128a  jnz     short loc_180001283
0x18000128c  lea     r9d, ds:2[rax*2]
0x180001294  jmp     short loc_18000129D
0x180001296  lea     rcx, qword_18001E1A0
0x18000129d  mov     rax, [rbp+80h+arg_50]
0x1800012a4  mov     [rbp+80h+var_D0], rax
0x1800012a8  mov     rax, [rbp+80h+arg_48]
0x1800012af  mov     [rbp+80h+var_C0], rcx
0x1800012b3  mov     [rbp+80h+var_B8], r9d
0x1800012b7  mov     [rbp+80h+var_B4], edi
0x1800012ba  mov     rcx, [rax]
0x1800012bd  mov     [rbp+80h+var_C8], 4
0x1800012c5  test    rcx, rcx
0x1800012c8  jz      short loc_1800012DA
0x1800012ca  mov     rax, rdx
0x1800012cd  inc     rax
0x1800012d0  cmp     [rcx+rax], dil
0x1800012d4  jnz     short loc_1800012CD
0x1800012d6  inc     eax
0x1800012d8  jmp     short loc_1800012E0
0x1800012da  mov     rcx, rsi
0x1800012dd  mov     eax, r8d
0x1800012e0  mov     [rbp+80h+var_D8], eax
0x1800012e3  mov     rax, [rbp+80h+arg_40]
0x1800012ea  mov     [rbp+80h+var_F0], rax
0x1800012ee  mov     rax, [rbp+80h+arg_38]
0x1800012f5  mov     [rbp+80h+var_E0], rcx
0x1800012f9  mov     [rbp+80h+var_D4], edi
0x1800012fc  mov     [rbp+80h+var_E8], 4
0x180001304  mov     rcx, [rax]
0x180001307  test    rcx, rcx
0x18000130a  jz      short loc_18000131B
0x18000130c  inc     rdx
0x18000130f  cmp     [rcx+rdx], dil
0x180001313  jnz     short loc_18000130C
0x180001315  lea     r8d, [rdx+1]
0x180001319  jmp     short loc_18000131E
0x18000131b  mov     rcx, rsi
0x18000131e  mov     rax, [rbp+80h+arg_30]
0x180001325  xor     r9d, r9d
0x180001328  mov     [rsp+180h+var_110], rax
0x18000132d  mov     rdx, r11
0x180001330  mov     rax, [rbp+80h+arg_28]
0x180001337  mov     [rsp+180h+var_120], rax
0x18000133c  mov     rax, [rbp+80h+arg_20]
0x180001343  mov     [rsp+180h+var_130], rax
0x180001348  lea     rax, [rsp+180h+var_150]
0x18000134d  mov     [rbp+80h+var_100], rcx
0x180001351  mov     rcx, r10
0x180001354  mov     [rbp+80h+var_F8], r8d
0x180001358  mov     r8, rbx
0x18000135b  mov     [rsp+180h+var_158], rax
0x180001360  mov     [rsp+180h+var_160], 12h
0x180001368  mov     [rbp+80h+var_F4], edi
0x18000136b  mov     [rsp+180h+var_108], 4
0x180001374  mov     [rsp+180h+var_118], 8
0x18000137d  mov     [rsp+180h+var_128], 8
0x180001386  call    _tlgWriteTransfer_EventWriteTransfer
0x18000138b  mov     rcx, [rbp+80h+var_30]
0x18000138f  xor     rcx, rsp; StackCookie
0x180001392  call    __security_check_cookie
0x180001397  add     rsp, 160h
0x18000139e  pop     r14
0x1800013a0  pop     rdi
0x1800013a1  pop     rsi
0x1800013a2  pop     rbx
0x1800013a3  pop     rbp
0x1800013a4  retn
```
