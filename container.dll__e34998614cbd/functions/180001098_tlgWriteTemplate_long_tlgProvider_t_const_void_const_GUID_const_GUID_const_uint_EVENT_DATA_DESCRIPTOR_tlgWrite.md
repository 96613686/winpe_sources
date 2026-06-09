# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)

- ea: `0x180001098`
- end: `0x180001346`
- name: `??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456@Z`
- size: `686`
- prototype: ``
- caller_count: `5`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180009eb8`
- `0x18000ac60`
- `0x180010ac0`
- `0x180011010`
- `0x180011560`

## callees

- `0x180001098`
- `0x180001e10`
- `0x180002ad0`

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
        const WCHAR **a12,
        __int64 a13,
        const unsigned __int16 **a14,
        __int64 a15,
        const unsigned __int16 **a16,
        const WCHAR **a17,
        __int64 a18,
        const unsigned __int16 **a19,
        const WCHAR **a20)
{
  __int64 v22; // rdx
  int v24; // r9d
  const WCHAR *v25; // rcx
  __int64 v26; // rax
  int v27; // eax
  int v28; // r8d
  const unsigned __int16 *v29; // rcx
  __int64 v30; // rax
  int v31; // eax
  const WCHAR *v32; // rcx
  __int64 v33; // rax
  int v34; // eax
  const unsigned __int16 *v35; // rcx
  __int64 v36; // rax
  int v37; // eax
  const unsigned __int16 *v38; // rcx
  __int64 v39; // rax
  int v40; // eax
  const WCHAR *v41; // rcx
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
  const WCHAR *v65; // [rsp+C0h] [rbp-40h]
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
  const WCHAR *v78; // [rsp+110h] [rbp+10h]
  int v79; // [rsp+118h] [rbp+18h]
  int v80; // [rsp+11Ch] [rbp+1Ch]
  __int64 v81; // [rsp+120h] [rbp+20h]
  __int64 v82; // [rsp+128h] [rbp+28h]
  const unsigned __int16 *v83; // [rsp+130h] [rbp+30h]
  int v84; // [rsp+138h] [rbp+38h]
  int v85; // [rsp+13Ch] [rbp+3Ch]
  const WCHAR *v86; // [rsp+140h] [rbp+40h]
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
    while ( v25[v26] );
    v27 = 2 * v26 + 2;
  }
  else
  {
    v25 = &pwszBaseUri;
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
    v29 = &byte_180037E05;
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
    while ( v32[v33] );
    v34 = 2 * v33 + 2;
  }
  else
  {
    v32 = &pwszBaseUri;
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
    v35 = &byte_180037E05;
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
    v38 = &byte_180037E05;
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
    while ( v41[v42] );
    v24 = 2 * v42 + 2;
  }
  else
  {
    v41 = &pwszBaseUri;
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
    v43 = &byte_180037E05;
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
    v46 = &byte_180037E05;
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
0x180001098  push    rbp
0x18000109a  push    rbx
0x18000109b  push    rsi
0x18000109c  push    rdi
0x18000109d  push    r14
0x18000109f  lea     rbp, [rsp-60h]
0x1800010a4  sub     rsp, 160h
0x1800010ab  mov     rax, cs:__security_cookie
0x1800010b2  xor     rax, rsp
0x1800010b5  mov     [rbp+80h+var_30], rax
0x1800010b9  mov     rax, [rbp+80h+arg_98]
0x1800010c0  mov     r11, rdx
0x1800010c3  mov     r10, rcx
0x1800010c6  or      rdx, 0FFFFFFFFFFFFFFFFh
0x1800010ca  xor     edi, edi
0x1800010cc  mov     rbx, r8
0x1800010cf  mov     r9d, 2
0x1800010d5  mov     rcx, [rax]
0x1800010d8  test    rcx, rcx
0x1800010db  jz      short loc_1800010F2
0x1800010dd  mov     rax, rdx
0x1800010e0  inc     rax
0x1800010e3  cmp     [rcx+rax*2], di
0x1800010e7  jnz     short loc_1800010E0
0x1800010e9  lea     eax, ds:2[rax*2]
0x1800010f0  jmp     short loc_1800010FC
0x1800010f2  lea     rcx, pwszBaseUri
0x1800010f9  mov     eax, r9d
0x1800010fc  mov     [rbp+80h+var_38], eax
0x1800010ff  lea     rsi, byte_180037E05
0x180001106  mov     rax, [rbp+80h+arg_90]
0x18000110d  mov     r8d, 1
0x180001113  mov     [rbp+80h+var_40], rcx
0x180001117  mov     [rbp+80h+var_34], edi
0x18000111a  mov     rcx, [rax]
0x18000111d  test    rcx, rcx
0x180001120  jz      short loc_180001132
0x180001122  mov     rax, rdx
0x180001125  inc     rax
0x180001128  cmp     [rcx+rax], dil
0x18000112c  jnz     short loc_180001125
0x18000112e  inc     eax
0x180001130  jmp     short loc_180001138
0x180001132  mov     rcx, rsi
0x180001135  mov     eax, r8d
0x180001138  mov     [rbp+80h+var_48], eax
0x18000113b  mov     rax, [rbp+80h+arg_88]
0x180001142  mov     [rbp+80h+var_60], rax
0x180001146  mov     rax, [rbp+80h+arg_80]
0x18000114d  mov     [rbp+80h+var_50], rcx
0x180001151  mov     [rbp+80h+var_44], edi
0x180001154  mov     [rbp+80h+var_58], 4
0x18000115c  mov     rcx, [rax]
0x18000115f  test    rcx, rcx
0x180001162  jz      short loc_180001179
0x180001164  mov     rax, rdx
0x180001167  inc     rax
0x18000116a  cmp     [rcx+rax*2], di
0x18000116e  jnz     short loc_180001167
0x180001170  lea     eax, ds:2[rax*2]
0x180001177  jmp     short loc_180001183
0x180001179  lea     rcx, pwszBaseUri
0x180001180  mov     eax, r9d
0x180001183  mov     [rbp+80h+var_68], eax
0x180001186  mov     rax, [rbp+80h+arg_78]
0x18000118d  mov     [rbp+80h+var_70], rcx
0x180001191  mov     [rbp+80h+var_64], edi
0x180001194  mov     rcx, [rax]
0x180001197  test    rcx, rcx
0x18000119a  jz      short loc_1800011AC
0x18000119c  mov     rax, rdx
0x18000119f  inc     rax
0x1800011a2  cmp     [rcx+rax], dil
0x1800011a6  jnz     short loc_18000119F
0x1800011a8  inc     eax
0x1800011aa  jmp     short loc_1800011B2
0x1800011ac  mov     rcx, rsi
0x1800011af  mov     eax, r8d
0x1800011b2  mov     [rbp+80h+var_78], eax
0x1800011b5  mov     rax, [rbp+80h+arg_70]
0x1800011bc  mov     [rbp+80h+var_90], rax
0x1800011c0  mov     rax, [rbp+80h+arg_68]
0x1800011c7  mov     [rbp+80h+var_80], rcx
0x1800011cb  mov     [rbp+80h+var_74], edi
0x1800011ce  mov     [rbp+80h+var_88], 4
0x1800011d6  mov     rcx, [rax]
0x1800011d9  test    rcx, rcx
0x1800011dc  jz      short loc_1800011EE
0x1800011de  mov     rax, rdx
0x1800011e1  inc     rax
0x1800011e4  cmp     [rcx+rax], dil
0x1800011e8  jnz     short loc_1800011E1
0x1800011ea  inc     eax
0x1800011ec  jmp     short loc_1800011F4
0x1800011ee  mov     rcx, rsi
0x1800011f1  mov     eax, r8d
0x1800011f4  mov     [rbp+80h+var_98], eax
0x1800011f7  mov     rax, [rbp+80h+arg_60]
0x1800011fe  mov     [rbp+80h+var_B0], rax
0x180001202  mov     rax, [rbp+80h+arg_58]
0x180001209  mov     [rbp+80h+var_A0], rcx
0x18000120d  mov     [rbp+80h+var_94], edi
0x180001210  mov     [rbp+80h+var_A8], 4
0x180001218  mov     rcx, [rax]
0x18000121b  test    rcx, rcx
0x18000121e  jz      short loc_180001236
0x180001220  mov     rax, rdx
0x180001223  inc     rax
0x180001226  cmp     [rcx+rax*2], di
0x18000122a  jnz     short loc_180001223
0x18000122c  lea     r9d, ds:2[rax*2]
0x180001234  jmp     short loc_18000123D
0x180001236  lea     rcx, pwszBaseUri
0x18000123d  mov     rax, [rbp+80h+arg_50]
0x180001244  mov     [rbp+80h+var_D0], rax
0x180001248  mov     rax, [rbp+80h+arg_48]
0x18000124f  mov     [rbp+80h+var_C0], rcx
0x180001253  mov     [rbp+80h+var_B8], r9d
0x180001257  mov     [rbp+80h+var_B4], edi
0x18000125a  mov     rcx, [rax]
0x18000125d  mov     [rbp+80h+var_C8], 4
0x180001265  test    rcx, rcx
0x180001268  jz      short loc_18000127A
0x18000126a  mov     rax, rdx
0x18000126d  inc     rax
0x180001270  cmp     [rcx+rax], dil
0x180001274  jnz     short loc_18000126D
0x180001276  inc     eax
0x180001278  jmp     short loc_180001280
0x18000127a  mov     rcx, rsi
0x18000127d  mov     eax, r8d
0x180001280  mov     [rbp+80h+var_D8], eax
0x180001283  mov     rax, [rbp+80h+arg_40]
0x18000128a  mov     [rbp+80h+var_F0], rax
0x18000128e  mov     rax, [rbp+80h+arg_38]
0x180001295  mov     [rbp+80h+var_E0], rcx
0x180001299  mov     [rbp+80h+var_D4], edi
0x18000129c  mov     [rbp+80h+var_E8], 4
0x1800012a4  mov     rcx, [rax]
0x1800012a7  test    rcx, rcx
0x1800012aa  jz      short loc_1800012BB
0x1800012ac  inc     rdx
0x1800012af  cmp     [rcx+rdx], dil
0x1800012b3  jnz     short loc_1800012AC
0x1800012b5  lea     r8d, [rdx+1]
0x1800012b9  jmp     short loc_1800012BE
0x1800012bb  mov     rcx, rsi
0x1800012be  mov     rax, [rbp+80h+arg_30]
0x1800012c5  xor     r9d, r9d
0x1800012c8  mov     [rsp+180h+var_110], rax
0x1800012cd  mov     rdx, r11
0x1800012d0  mov     rax, [rbp+80h+arg_28]
0x1800012d7  mov     [rsp+180h+var_120], rax
0x1800012dc  mov     rax, [rbp+80h+arg_20]
0x1800012e3  mov     [rsp+180h+var_130], rax
0x1800012e8  lea     rax, [rsp+180h+var_150]
0x1800012ed  mov     [rbp+80h+var_100], rcx
0x1800012f1  mov     rcx, r10
0x1800012f4  mov     [rbp+80h+var_F8], r8d
0x1800012f8  mov     r8, rbx
0x1800012fb  mov     [rsp+180h+var_158], rax
0x180001300  mov     [rsp+180h+var_160], 12h
0x180001308  mov     [rbp+80h+var_F4], edi
0x18000130b  mov     [rsp+180h+var_108], 4
0x180001314  mov     [rsp+180h+var_118], 8
0x18000131d  mov     [rsp+180h+var_128], 8
0x180001326  call    _tlgWriteTransfer_EventWriteTransfer
0x18000132b  mov     rcx, [rbp+80h+var_30]
0x18000132f  xor     rcx, rsp; StackCookie
0x180001332  call    __security_check_cookie
0x180001337  add     rsp, 160h
0x18000133e  pop     r14
0x180001340  pop     rdi
0x180001341  pop     rsi
0x180001342  pop     rbx
0x180001343  pop     rbp
0x180001344  retn
```
