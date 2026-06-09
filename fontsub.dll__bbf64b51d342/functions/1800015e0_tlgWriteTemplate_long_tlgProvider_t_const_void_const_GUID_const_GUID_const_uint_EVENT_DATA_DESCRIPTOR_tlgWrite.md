# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)

- ea: `0x1800015e0`
- end: `0x180001902`
- name: `??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@454564564454@Z`
- size: `802`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x18000611c`
- `0x180006378`

## callees

- `0x1800015e0`
- `0x180001f18`
- `0x18001ac90`

## pseudocode

```c
ULONG __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
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
        int **a20,
        __int64 a21,
        __int64 a22,
        const unsigned __int16 **a23,
        __int64 a24)
{
  __int64 v26; // rdx
  int v28; // r8d
  const unsigned __int16 *v29; // rcx
  __int64 v30; // rax
  int v31; // eax
  int v32; // r9d
  int *v33; // rcx
  __int64 v34; // rax
  int v35; // eax
  const unsigned __int16 *v36; // rcx
  __int64 v37; // rax
  int v38; // eax
  int *v39; // rcx
  __int64 v40; // rax
  int v41; // eax
  const unsigned __int16 *v42; // rcx
  __int64 v43; // rax
  int v44; // eax
  const unsigned __int16 *v45; // rcx
  __int64 v46; // rax
  int v47; // eax
  int *v48; // rcx
  __int64 v49; // rax
  const unsigned __int16 *v50; // rcx
  __int64 v51; // rax
  int v52; // eax
  const unsigned __int16 *v53; // rcx
  struct _EVENT_DATA_DESCRIPTOR v55; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v56; // [rsp+50h] [rbp-B0h]
  __int64 v57; // [rsp+58h] [rbp-A8h]
  __int64 v58; // [rsp+60h] [rbp-A0h]
  __int64 v59; // [rsp+68h] [rbp-98h]
  __int64 v60; // [rsp+70h] [rbp-90h]
  __int64 v61; // [rsp+78h] [rbp-88h]
  const unsigned __int16 *v62; // [rsp+80h] [rbp-80h]
  int v63; // [rsp+88h] [rbp-78h]
  int v64; // [rsp+8Ch] [rbp-74h]
  __int64 v65; // [rsp+90h] [rbp-70h]
  __int64 v66; // [rsp+98h] [rbp-68h]
  const unsigned __int16 *v67; // [rsp+A0h] [rbp-60h]
  int v68; // [rsp+A8h] [rbp-58h]
  int v69; // [rsp+ACh] [rbp-54h]
  __int64 v70; // [rsp+B0h] [rbp-50h]
  __int64 v71; // [rsp+B8h] [rbp-48h]
  int *v72; // [rsp+C0h] [rbp-40h]
  int v73; // [rsp+C8h] [rbp-38h]
  int v74; // [rsp+CCh] [rbp-34h]
  __int64 v75; // [rsp+D0h] [rbp-30h]
  __int64 v76; // [rsp+D8h] [rbp-28h]
  const unsigned __int16 *v77; // [rsp+E0h] [rbp-20h]
  int v78; // [rsp+E8h] [rbp-18h]
  int v79; // [rsp+ECh] [rbp-14h]
  __int64 v80; // [rsp+F0h] [rbp-10h]
  __int64 v81; // [rsp+F8h] [rbp-8h]
  const unsigned __int16 *v82; // [rsp+100h] [rbp+0h]
  int v83; // [rsp+108h] [rbp+8h]
  int v84; // [rsp+10Ch] [rbp+Ch]
  int *v85; // [rsp+110h] [rbp+10h]
  int v86; // [rsp+118h] [rbp+18h]
  int v87; // [rsp+11Ch] [rbp+1Ch]
  __int64 v88; // [rsp+120h] [rbp+20h]
  __int64 v89; // [rsp+128h] [rbp+28h]
  const unsigned __int16 *v90; // [rsp+130h] [rbp+30h]
  int v91; // [rsp+138h] [rbp+38h]
  int v92; // [rsp+13Ch] [rbp+3Ch]
  int *v93; // [rsp+140h] [rbp+40h]
  int v94; // [rsp+148h] [rbp+48h]
  int v95; // [rsp+14Ch] [rbp+4Ch]
  __int64 v96; // [rsp+150h] [rbp+50h]
  __int64 v97; // [rsp+158h] [rbp+58h]
  __int64 v98; // [rsp+160h] [rbp+60h]
  __int64 v99; // [rsp+168h] [rbp+68h]
  const unsigned __int16 *v100; // [rsp+170h] [rbp+70h]
  int v101; // [rsp+178h] [rbp+78h]
  int v102; // [rsp+17Ch] [rbp+7Ch]
  __int64 v103; // [rsp+180h] [rbp+80h]
  __int64 v104; // [rsp+188h] [rbp+88h]

  v103 = a24;
  v104 = 4;
  v26 = -1;
  v28 = 1;
  v29 = *a23;
  if ( *a23 )
  {
    v30 = -1;
    do
      ++v30;
    while ( *((_BYTE *)v29 + v30) );
    v31 = v30 + 1;
  }
  else
  {
    v29 = &byte_18001D570;
    v31 = 1;
  }
  v101 = v31;
  v32 = 2;
  v98 = a22;
  v96 = a21;
  v100 = v29;
  v102 = 0;
  v99 = 4;
  v33 = *a20;
  v97 = 4;
  if ( v33 )
  {
    v34 = -1;
    do
      ++v34;
    while ( *((_WORD *)v33 + v34) );
    v35 = 2 * v34 + 2;
  }
  else
  {
    v33 = &dword_18001D574;
    v35 = 2;
  }
  v94 = v35;
  v93 = v33;
  v95 = 0;
  v36 = *a19;
  if ( *a19 )
  {
    v37 = -1;
    do
      ++v37;
    while ( *((_BYTE *)v36 + v37) );
    v38 = v37 + 1;
  }
  else
  {
    v36 = &byte_18001D570;
    v38 = 1;
  }
  v91 = v38;
  v88 = a18;
  v90 = v36;
  v92 = 0;
  v89 = 4;
  v39 = *a17;
  if ( *a17 )
  {
    v40 = -1;
    do
      ++v40;
    while ( *((_WORD *)v39 + v40) );
    v41 = 2 * v40 + 2;
  }
  else
  {
    v39 = &dword_18001D574;
    v41 = 2;
  }
  v86 = v41;
  v85 = v39;
  v87 = 0;
  v42 = *a16;
  if ( *a16 )
  {
    v43 = -1;
    do
      ++v43;
    while ( *((_BYTE *)v42 + v43) );
    v44 = v43 + 1;
  }
  else
  {
    v42 = &byte_18001D570;
    v44 = 1;
  }
  v83 = v44;
  v80 = a15;
  v82 = v42;
  v84 = 0;
  v81 = 4;
  v45 = *a14;
  if ( *a14 )
  {
    v46 = -1;
    do
      ++v46;
    while ( *((_BYTE *)v45 + v46) );
    v47 = v46 + 1;
  }
  else
  {
    v45 = &byte_18001D570;
    v47 = 1;
  }
  v78 = v47;
  v75 = a13;
  v77 = v45;
  v79 = 0;
  v76 = 4;
  v48 = *a12;
  if ( *a12 )
  {
    v49 = -1;
    do
      ++v49;
    while ( *((_WORD *)v48 + v49) );
    v32 = 2 * v49 + 2;
  }
  else
  {
    v48 = &dword_18001D574;
  }
  v70 = a11;
  v72 = v48;
  v73 = v32;
  v74 = 0;
  v50 = *a10;
  v71 = 4;
  if ( v50 )
  {
    v51 = -1;
    do
      ++v51;
    while ( *((_BYTE *)v50 + v51) );
    v52 = v51 + 1;
  }
  else
  {
    v50 = &byte_18001D570;
    v52 = 1;
  }
  v68 = v52;
  v65 = a9;
  v67 = v50;
  v69 = 0;
  v66 = 4;
  v53 = *a8;
  if ( *a8 )
  {
    do
      ++v26;
    while ( *((_BYTE *)v53 + v26) );
    v28 = v26 + 1;
  }
  else
  {
    v53 = &byte_18001D570;
  }
  v60 = a7;
  v58 = a6;
  v56 = a5;
  v62 = v53;
  v63 = v28;
  v64 = 0;
  v61 = 4;
  v59 = 8;
  v57 = 8;
  return tlgWriteTransfer_EventWriteTransfer(a1, a2, a3, 0, 0x16u, &v55);
}

```

## disassembly

```asm
0x1800015e0  push    rbp
0x1800015e2  push    rbx
0x1800015e3  push    rsi
0x1800015e4  push    rdi
0x1800015e5  push    r15
0x1800015e7  lea     rbp, [rsp-0A0h]
0x1800015ef  sub     rsp, 1A0h
0x1800015f6  mov     rax, cs:__security_cookie
0x1800015fd  xor     rax, rsp
0x180001600  mov     [rbp+0C0h+var_30], rax
0x180001607  mov     rax, [rbp+0C0h+arg_B8]
0x18000160e  lea     rsi, byte_18001D570
0x180001615  xor     edi, edi
0x180001617  mov     [rbp+0C0h+var_40], rax
0x18000161e  mov     rax, [rbp+0C0h+arg_B0]
0x180001625  mov     r11, rdx
0x180001628  mov     r10, rcx
0x18000162b  mov     [rbp+0C0h+var_38], 4
0x180001636  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18000163a  mov     rbx, r8
0x18000163d  lea     r8d, [rdi+1]
0x180001641  mov     rcx, [rax]
0x180001644  test    rcx, rcx
0x180001647  jz      short loc_180001659
0x180001649  mov     rax, rdx
0x18000164c  inc     rax
0x18000164f  cmp     [rcx+rax], dil
0x180001653  jnz     short loc_18000164C
0x180001655  inc     eax
0x180001657  jmp     short loc_18000165F
0x180001659  mov     rcx, rsi
0x18000165c  mov     eax, r8d
0x18000165f  mov     [rbp+0C0h+var_48], eax
0x180001662  mov     r9d, 2
0x180001668  mov     rax, [rbp+0C0h+arg_A8]
0x18000166f  mov     [rbp+0C0h+var_60], rax
0x180001673  mov     rax, [rbp+0C0h+arg_A0]
0x18000167a  mov     [rbp+0C0h+var_70], rax
0x18000167e  mov     rax, [rbp+0C0h+arg_98]
0x180001685  mov     [rbp+0C0h+var_50], rcx
0x180001689  mov     [rbp+0C0h+var_44], edi
0x18000168c  mov     [rbp+0C0h+var_58], 4
0x180001694  mov     rcx, [rax]
0x180001697  mov     [rbp+0C0h+var_68], 4
0x18000169f  test    rcx, rcx
0x1800016a2  jz      short loc_1800016B9
0x1800016a4  mov     rax, rdx
0x1800016a7  inc     rax
0x1800016aa  cmp     [rcx+rax*2], di
0x1800016ae  jnz     short loc_1800016A7
0x1800016b0  lea     eax, ds:2[rax*2]
0x1800016b7  jmp     short loc_1800016C3
0x1800016b9  lea     rcx, dword_18001D574
0x1800016c0  mov     eax, r9d
0x1800016c3  mov     [rbp+0C0h+var_78], eax
0x1800016c6  mov     rax, [rbp+0C0h+arg_90]
0x1800016cd  mov     [rbp+0C0h+var_80], rcx
0x1800016d1  mov     [rbp+0C0h+var_74], edi
0x1800016d4  mov     rcx, [rax]
0x1800016d7  test    rcx, rcx
0x1800016da  jz      short loc_1800016EC
0x1800016dc  mov     rax, rdx
0x1800016df  inc     rax
0x1800016e2  cmp     [rcx+rax], dil
0x1800016e6  jnz     short loc_1800016DF
0x1800016e8  inc     eax
0x1800016ea  jmp     short loc_1800016F2
0x1800016ec  mov     rcx, rsi
0x1800016ef  mov     eax, r8d
0x1800016f2  mov     [rbp+0C0h+var_88], eax
0x1800016f5  mov     rax, [rbp+0C0h+arg_88]
0x1800016fc  mov     [rbp+0C0h+var_A0], rax
0x180001700  mov     rax, [rbp+0C0h+arg_80]
0x180001707  mov     [rbp+0C0h+var_90], rcx
0x18000170b  mov     [rbp+0C0h+var_84], edi
0x18000170e  mov     [rbp+0C0h+var_98], 4
0x180001716  mov     rcx, [rax]
0x180001719  test    rcx, rcx
0x18000171c  jz      short loc_180001733
0x18000171e  mov     rax, rdx
0x180001721  inc     rax
0x180001724  cmp     [rcx+rax*2], di
0x180001728  jnz     short loc_180001721
0x18000172a  lea     eax, ds:2[rax*2]
0x180001731  jmp     short loc_18000173D
0x180001733  lea     rcx, dword_18001D574
0x18000173a  mov     eax, r9d
0x18000173d  mov     [rbp+0C0h+var_A8], eax
0x180001740  mov     rax, [rbp+0C0h+arg_78]
0x180001747  mov     [rbp+0C0h+var_B0], rcx
0x18000174b  mov     [rbp+0C0h+var_A4], edi
0x18000174e  mov     rcx, [rax]
0x180001751  test    rcx, rcx
0x180001754  jz      short loc_180001766
0x180001756  mov     rax, rdx
0x180001759  inc     rax
0x18000175c  cmp     [rcx+rax], dil
0x180001760  jnz     short loc_180001759
0x180001762  inc     eax
0x180001764  jmp     short loc_18000176C
0x180001766  mov     rcx, rsi
0x180001769  mov     eax, r8d
0x18000176c  mov     [rbp+0C0h+var_B8], eax
0x18000176f  mov     rax, [rbp+0C0h+arg_70]
0x180001776  mov     [rbp+0C0h+var_D0], rax
0x18000177a  mov     rax, [rbp+0C0h+arg_68]
0x180001781  mov     [rbp+0C0h+var_C0], rcx
0x180001785  mov     [rbp+0C0h+var_B4], edi
0x180001788  mov     [rbp+0C0h+var_C8], 4
0x180001790  mov     rcx, [rax]
0x180001793  test    rcx, rcx
0x180001796  jz      short loc_1800017A8
0x180001798  mov     rax, rdx
0x18000179b  inc     rax
0x18000179e  cmp     [rcx+rax], dil
0x1800017a2  jnz     short loc_18000179B
0x1800017a4  inc     eax
0x1800017a6  jmp     short loc_1800017AE
0x1800017a8  mov     rcx, rsi
0x1800017ab  mov     eax, r8d
0x1800017ae  mov     [rbp+0C0h+var_D8], eax
0x1800017b1  mov     rax, [rbp+0C0h+arg_60]
0x1800017b8  mov     [rbp+0C0h+var_F0], rax
0x1800017bc  mov     rax, [rbp+0C0h+arg_58]
0x1800017c3  mov     [rbp+0C0h+var_E0], rcx
0x1800017c7  mov     [rbp+0C0h+var_D4], edi
0x1800017ca  mov     [rbp+0C0h+var_E8], 4
0x1800017d2  mov     rcx, [rax]
0x1800017d5  test    rcx, rcx
0x1800017d8  jz      short loc_1800017F0
0x1800017da  mov     rax, rdx
0x1800017dd  inc     rax
0x1800017e0  cmp     [rcx+rax*2], di
0x1800017e4  jnz     short loc_1800017DD
0x1800017e6  lea     r9d, ds:2[rax*2]
0x1800017ee  jmp     short loc_1800017F7
0x1800017f0  lea     rcx, dword_18001D574
0x1800017f7  mov     rax, [rbp+0C0h+arg_50]
0x1800017fe  mov     [rbp+0C0h+var_110], rax
0x180001802  mov     rax, [rbp+0C0h+arg_48]
0x180001809  mov     [rbp+0C0h+var_100], rcx
0x18000180d  mov     [rbp+0C0h+var_F8], r9d
0x180001811  mov     [rbp+0C0h+var_F4], edi
0x180001814  mov     rcx, [rax]
0x180001817  mov     [rbp+0C0h+var_108], 4
0x18000181f  test    rcx, rcx
0x180001822  jz      short loc_180001834
0x180001824  mov     rax, rdx
0x180001827  inc     rax
0x18000182a  cmp     [rcx+rax], dil
0x18000182e  jnz     short loc_180001827
0x180001830  inc     eax
0x180001832  jmp     short loc_18000183A
0x180001834  mov     rcx, rsi
0x180001837  mov     eax, r8d
0x18000183a  mov     [rbp+0C0h+var_118], eax
0x18000183d  mov     rax, [rbp+0C0h+arg_40]
0x180001844  mov     [rbp+0C0h+var_130], rax
0x180001848  mov     rax, [rbp+0C0h+arg_38]
0x18000184f  mov     [rbp+0C0h+var_120], rcx
0x180001853  mov     [rbp+0C0h+var_114], edi
0x180001856  mov     [rbp+0C0h+var_128], 4
0x18000185e  mov     rcx, [rax]
0x180001861  test    rcx, rcx
0x180001864  jz      short loc_180001875
0x180001866  inc     rdx
0x180001869  cmp     [rcx+rdx], dil
0x18000186d  jnz     short loc_180001866
0x18000186f  lea     r8d, [rdx+1]
0x180001873  jmp     short loc_180001878
0x180001875  mov     rcx, rsi
0x180001878  mov     rax, [rbp+0C0h+arg_30]
0x18000187f  xor     r9d, r9d
0x180001882  mov     [rsp+1C0h+var_150], rax
0x180001887  mov     rdx, r11
0x18000188a  mov     rax, [rbp+0C0h+arg_28]
0x180001891  mov     [rsp+1C0h+var_160], rax
0x180001896  mov     rax, [rbp+0C0h+arg_20]
0x18000189d  mov     [rsp+1C0h+var_170], rax
0x1800018a2  lea     rax, [rsp+1C0h+var_190]
0x1800018a7  mov     [rbp+0C0h+var_140], rcx
0x1800018ab  mov     rcx, r10
0x1800018ae  mov     [rbp+0C0h+var_138], r8d
0x1800018b2  mov     r8, rbx
0x1800018b5  mov     [rsp+1C0h+var_198], rax
0x1800018ba  mov     [rsp+1C0h+var_1A0], 16h
0x1800018c2  mov     [rbp+0C0h+var_134], edi
0x1800018c5  mov     [rsp+1C0h+var_148], 4
0x1800018ce  mov     [rsp+1C0h+var_158], 8
0x1800018d7  mov     [rsp+1C0h+var_168], 8
0x1800018e0  call    _tlgWriteTransfer_EventWriteTransfer
0x1800018e5  mov     rcx, [rbp+0C0h+var_30]
0x1800018ec  xor     rcx, rsp; StackCookie
0x1800018ef  call    __security_check_cookie
0x1800018f4  add     rsp, 1A0h
0x1800018fb  pop     r15
0x1800018fd  pop     rdi
0x1800018fe  pop     rsi
0x1800018ff  pop     rbx
0x180001900  pop     rbp
0x180001901  retn
```
