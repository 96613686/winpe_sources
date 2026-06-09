# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)

- ea: `0x180001008`
- end: `0x1800012f7`
- name: `??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456445@Z`
- size: `751`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, __int64, __int64, const unsigned __int16 **, __int64, const unsigned __int16 **, __int64, int **, __int64, const unsigned __int16 **, __int64, const unsigned __int16 **, int **, __int64, const unsigned __int16 **, int **, __int64, __int64, const unsigned __int16 **)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180011d04`

## callees

- `0x180001008`
- `0x18000b468`
- `0x18000fa10`

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
    v26 = &word_18001A40A;
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
    v30 = &dword_18001A40C;
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
    v33 = &word_18001A40A;
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
    v36 = &dword_18001A40C;
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
    v39 = &word_18001A40A;
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
    v42 = &word_18001A40A;
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
    v45 = &dword_18001A40C;
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
    v47 = &word_18001A40A;
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
    v50 = &word_18001A40A;
  }
  v55 = a6;
  v53 = a5;
  v57 = v50;
  v58 = v25;
  v59 = 0;
  v56 = 4;
  v54 = 8;
  return tlgWriteTransfer_EventWriteTransfer(a1, a2, 0, 0, 20, v52);
}

```

## disassembly

```asm
0x180001008  mov     [rsp-8+arg_10], rbx
0x18000100d  push    rbp
0x18000100e  push    rdi
0x18000100f  push    r14
0x180001011  lea     rbp, [rsp-80h]
0x180001016  sub     rsp, 180h
0x18000101d  mov     rax, cs:__security_cookie
0x180001024  xor     rax, rsp
0x180001027  mov     [rbp+90h+var_20], rax
0x18000102b  mov     rax, [rbp+90h+arg_A8]
0x180001032  lea     rdi, word_18001A40A
0x180001039  mov     r11, rdx
0x18000103c  mov     r10, rcx
0x18000103f  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180001043  xor     ebx, ebx
0x180001045  mov     r8d, 1
0x18000104b  mov     rcx, [rax]
0x18000104e  test    rcx, rcx
0x180001051  jz      short loc_180001062
0x180001053  mov     rax, rdx
0x180001056  inc     rax
0x180001059  cmp     [rcx+rax], bl
0x18000105c  jnz     short loc_180001056
0x18000105e  inc     eax
0x180001060  jmp     short loc_180001068
0x180001062  mov     rcx, rdi
0x180001065  mov     eax, r8d
0x180001068  mov     [rbp+90h+var_28], eax
0x18000106b  mov     r9d, 2
0x180001071  mov     rax, [rbp+90h+arg_A0]
0x180001078  mov     [rbp+90h+var_40], rax
0x18000107c  mov     rax, [rbp+90h+arg_98]
0x180001083  mov     [rbp+90h+var_50], rax
0x180001087  mov     rax, [rbp+90h+arg_90]
0x18000108e  mov     [rbp+90h+var_30], rcx
0x180001092  mov     [rbp+90h+var_24], ebx
0x180001095  mov     [rbp+90h+var_38], 4
0x18000109d  mov     rcx, [rax]
0x1800010a0  mov     [rbp+90h+var_48], 4
0x1800010a8  test    rcx, rcx
0x1800010ab  jz      short loc_1800010C2
0x1800010ad  mov     rax, rdx
0x1800010b0  inc     rax
0x1800010b3  cmp     [rcx+rax*2], bx
0x1800010b7  jnz     short loc_1800010B0
0x1800010b9  lea     eax, ds:2[rax*2]
0x1800010c0  jmp     short loc_1800010CC
0x1800010c2  lea     rcx, dword_18001A40C
0x1800010c9  mov     eax, r9d
0x1800010cc  mov     [rbp+90h+var_58], eax
0x1800010cf  mov     rax, [rbp+90h+arg_88]
0x1800010d6  mov     [rbp+90h+var_60], rcx
0x1800010da  mov     [rbp+90h+var_54], ebx
0x1800010dd  mov     rcx, [rax]
0x1800010e0  test    rcx, rcx
0x1800010e3  jz      short loc_1800010F4
0x1800010e5  mov     rax, rdx
0x1800010e8  inc     rax
0x1800010eb  cmp     [rcx+rax], bl
0x1800010ee  jnz     short loc_1800010E8
0x1800010f0  inc     eax
0x1800010f2  jmp     short loc_1800010FA
0x1800010f4  mov     rcx, rdi
0x1800010f7  mov     eax, r8d
0x1800010fa  mov     [rbp+90h+var_68], eax
0x1800010fd  mov     rax, [rbp+90h+arg_80]
0x180001104  mov     [rbp+90h+var_80], rax
0x180001108  mov     rax, [rbp+90h+arg_78]
0x18000110f  mov     [rbp+90h+var_70], rcx
0x180001113  mov     [rbp+90h+var_64], ebx
0x180001116  mov     [rbp+90h+var_78], 4
0x18000111e  mov     rcx, [rax]
0x180001121  test    rcx, rcx
0x180001124  jz      short loc_18000113B
0x180001126  mov     rax, rdx
0x180001129  inc     rax
0x18000112c  cmp     [rcx+rax*2], bx
0x180001130  jnz     short loc_180001129
0x180001132  lea     eax, ds:2[rax*2]
0x180001139  jmp     short loc_180001145
0x18000113b  lea     rcx, dword_18001A40C
0x180001142  mov     eax, r9d
0x180001145  mov     [rbp+90h+var_88], eax
0x180001148  mov     rax, [rbp+90h+arg_70]
0x18000114f  mov     [rbp+90h+var_90], rcx
0x180001153  mov     [rbp+90h+var_84], ebx
0x180001156  mov     rcx, [rax]
0x180001159  test    rcx, rcx
0x18000115c  jz      short loc_18000116D
0x18000115e  mov     rax, rdx
0x180001161  inc     rax
0x180001164  cmp     [rcx+rax], bl
0x180001167  jnz     short loc_180001161
0x180001169  inc     eax
0x18000116b  jmp     short loc_180001173
0x18000116d  mov     rcx, rdi
0x180001170  mov     eax, r8d
0x180001173  mov     [rbp+90h+var_98], eax
0x180001176  mov     rax, [rbp+90h+arg_68]
0x18000117d  mov     [rbp+90h+var_B0], rax
0x180001181  mov     rax, [rbp+90h+arg_60]
0x180001188  mov     [rbp+90h+var_A0], rcx
0x18000118c  mov     [rbp+90h+var_94], ebx
0x18000118f  mov     [rbp+90h+var_A8], 4
0x180001197  mov     rcx, [rax]
0x18000119a  test    rcx, rcx
0x18000119d  jz      short loc_1800011AE
0x18000119f  mov     rax, rdx
0x1800011a2  inc     rax
0x1800011a5  cmp     [rcx+rax], bl
0x1800011a8  jnz     short loc_1800011A2
0x1800011aa  inc     eax
0x1800011ac  jmp     short loc_1800011B4
0x1800011ae  mov     rcx, rdi
0x1800011b1  mov     eax, r8d
0x1800011b4  mov     [rbp+90h+var_B8], eax
0x1800011b7  mov     rax, [rbp+90h+arg_58]
0x1800011be  mov     [rbp+90h+var_D0], rax
0x1800011c2  mov     rax, [rbp+90h+arg_50]
0x1800011c9  mov     [rbp+90h+var_C0], rcx
0x1800011cd  mov     [rbp+90h+var_B4], ebx
0x1800011d0  mov     [rbp+90h+var_C8], 4
0x1800011d8  mov     rcx, [rax]
0x1800011db  test    rcx, rcx
0x1800011de  jz      short loc_1800011F6
0x1800011e0  mov     rax, rdx
0x1800011e3  inc     rax
0x1800011e6  cmp     [rcx+rax*2], bx
0x1800011ea  jnz     short loc_1800011E3
0x1800011ec  lea     r9d, ds:2[rax*2]
0x1800011f4  jmp     short loc_1800011FD
0x1800011f6  lea     rcx, dword_18001A40C
0x1800011fd  mov     rax, [rbp+90h+arg_48]
0x180001204  mov     [rbp+90h+var_F0], rax
0x180001208  mov     rax, [rbp+90h+arg_40]
0x18000120f  mov     [rbp+90h+var_E0], rcx
0x180001213  mov     [rbp+90h+var_D8], r9d
0x180001217  mov     [rbp+90h+var_D4], ebx
0x18000121a  mov     rcx, [rax]
0x18000121d  mov     [rbp+90h+var_E8], 4
0x180001225  test    rcx, rcx
0x180001228  jz      short loc_180001239
0x18000122a  mov     rax, rdx
0x18000122d  inc     rax
0x180001230  cmp     [rcx+rax], bl
0x180001233  jnz     short loc_18000122D
0x180001235  inc     eax
0x180001237  jmp     short loc_18000123F
0x180001239  mov     rcx, rdi
0x18000123c  mov     eax, r8d
0x18000123f  mov     [rbp+90h+var_F8], eax
0x180001242  mov     rax, [rbp+90h+arg_38]
0x180001249  mov     [rbp+90h+var_110], rax
0x18000124d  mov     rax, [rbp+90h+arg_30]
0x180001254  mov     [rbp+90h+var_100], rcx
0x180001258  mov     [rbp+90h+var_F4], ebx
0x18000125b  mov     [rbp+90h+var_108], 4
0x180001263  mov     rcx, [rax]
0x180001266  test    rcx, rcx
0x180001269  jz      short loc_180001279
0x18000126b  inc     rdx
0x18000126e  cmp     [rcx+rdx], bl
0x180001271  jnz     short loc_18000126B
0x180001273  lea     r8d, [rdx+1]
0x180001277  jmp     short loc_18000127C
0x180001279  mov     rcx, rdi
0x18000127c  mov     rax, [rbp+90h+arg_28]
0x180001283  xor     r9d, r9d
0x180001286  mov     [rsp+190h+var_130], rax
0x18000128b  mov     rdx, r11
0x18000128e  mov     rax, [rbp+90h+arg_20]
0x180001295  mov     [rsp+190h+var_140], rax
0x18000129a  lea     rax, [rsp+190h+var_160]
0x18000129f  mov     [rsp+190h+var_120], rcx
0x1800012a4  mov     rcx, r10
0x1800012a7  mov     [rsp+190h+var_118], r8d
0x1800012ac  xor     r8d, r8d
0x1800012af  mov     [rsp+190h+var_168], rax
0x1800012b4  mov     [rsp+190h+var_170], 14h
0x1800012bc  mov     [rsp+190h+var_114], ebx
0x1800012c0  mov     [rsp+190h+var_128], 4
0x1800012c9  mov     [rsp+190h+var_138], 8
0x1800012d2  call    _tlgWriteTransfer_EventWriteTransfer
0x1800012d7  mov     rcx, [rbp+90h+var_20]
0x1800012db  xor     rcx, rsp; StackCookie
0x1800012de  call    __security_check_cookie
0x1800012e3  mov     rbx, [rsp+190h+arg_10]
0x1800012eb  add     rsp, 180h
0x1800012f2  pop     r14
0x1800012f4  pop     rdi
0x1800012f5  pop     rbp
0x1800012f6  retn
```
