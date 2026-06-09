# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<2>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<2>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<2> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<2> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<2> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)

- ea: `0x1800012cc`
- end: `0x18000159e`
- name: `??$Write@U?$_tlgWrapperByVal@$03@@U1@U1@U?$_tlgWrapperByVal@$01@@U1@U?$_tlgWrapSz@D@@U2@U3@U3@U3@U2@U3@U3@U3@U3@U1@U3@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@33AEBU?$_tlgWrapperByVal@$01@@3AEBU?$_tlgWrapSz@D@@455545555353@Z`
- size: `722`
- prototype: `__int64 __usercall@<rax>(int@<ecx>, int@<edx>, __int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18000ffc0`

## callees

- `0x1800012cc`
- `0x180001f68`
- `0x180002620`

## pseudocode

```c
ULONG __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<2>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<2>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
        __int64 a1,
        unsigned __int8 *a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        __int64 a7,
        __int64 a8,
        __int64 a9,
        const unsigned __int16 **a10,
        __int64 a11,
        const unsigned __int16 **a12,
        const unsigned __int16 **a13,
        const unsigned __int16 **a14,
        __int64 a15,
        const unsigned __int16 **a16,
        const unsigned __int16 **a17,
        const unsigned __int16 **a18,
        const unsigned __int16 **a19,
        __int64 a20,
        const unsigned __int16 **a21,
        __int64 a22)
{
  __int64 v23; // rcx
  int v25; // edx
  const unsigned __int16 *v26; // r8
  __int64 v27; // rax
  int v28; // eax
  const unsigned __int16 *v29; // r8
  __int64 v30; // rax
  int v31; // eax
  const unsigned __int16 *v32; // r8
  __int64 v33; // rax
  int v34; // eax
  const unsigned __int16 *v35; // r8
  __int64 v36; // rax
  int v37; // eax
  const unsigned __int16 *v38; // r8
  __int64 v39; // rax
  int v40; // eax
  const unsigned __int16 *v41; // r8
  __int64 v42; // rax
  int v43; // eax
  const unsigned __int16 *v44; // r8
  __int64 v45; // rax
  int v46; // eax
  const unsigned __int16 *v47; // r8
  __int64 v48; // rax
  int v49; // eax
  const unsigned __int16 *v50; // r8
  struct _EVENT_DATA_DESCRIPTOR v52; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v53; // [rsp+50h] [rbp-B0h]
  __int64 v54; // [rsp+58h] [rbp-A8h]
  __int64 v55; // [rsp+60h] [rbp-A0h]
  __int64 v56; // [rsp+68h] [rbp-98h]
  __int64 v57; // [rsp+70h] [rbp-90h]
  __int64 v58; // [rsp+78h] [rbp-88h]
  __int64 v59; // [rsp+80h] [rbp-80h]
  __int64 v60; // [rsp+88h] [rbp-78h]
  __int64 v61; // [rsp+90h] [rbp-70h]
  __int64 v62; // [rsp+98h] [rbp-68h]
  const unsigned __int16 *v63; // [rsp+A0h] [rbp-60h]
  int v64; // [rsp+A8h] [rbp-58h]
  int v65; // [rsp+ACh] [rbp-54h]
  __int64 v66; // [rsp+B0h] [rbp-50h]
  __int64 v67; // [rsp+B8h] [rbp-48h]
  const unsigned __int16 *v68; // [rsp+C0h] [rbp-40h]
  int v69; // [rsp+C8h] [rbp-38h]
  int v70; // [rsp+CCh] [rbp-34h]
  const unsigned __int16 *v71; // [rsp+D0h] [rbp-30h]
  int v72; // [rsp+D8h] [rbp-28h]
  int v73; // [rsp+DCh] [rbp-24h]
  const unsigned __int16 *v74; // [rsp+E0h] [rbp-20h]
  int v75; // [rsp+E8h] [rbp-18h]
  int v76; // [rsp+ECh] [rbp-14h]
  __int64 v77; // [rsp+F0h] [rbp-10h]
  __int64 v78; // [rsp+F8h] [rbp-8h]
  const unsigned __int16 *v79; // [rsp+100h] [rbp+0h]
  int v80; // [rsp+108h] [rbp+8h]
  int v81; // [rsp+10Ch] [rbp+Ch]
  const unsigned __int16 *v82; // [rsp+110h] [rbp+10h]
  int v83; // [rsp+118h] [rbp+18h]
  int v84; // [rsp+11Ch] [rbp+1Ch]
  const unsigned __int16 *v85; // [rsp+120h] [rbp+20h]
  int v86; // [rsp+128h] [rbp+28h]
  int v87; // [rsp+12Ch] [rbp+2Ch]
  const unsigned __int16 *v88; // [rsp+130h] [rbp+30h]
  int v89; // [rsp+138h] [rbp+38h]
  int v90; // [rsp+13Ch] [rbp+3Ch]
  __int64 v91; // [rsp+140h] [rbp+40h]
  __int64 v92; // [rsp+148h] [rbp+48h]
  const unsigned __int16 *v93; // [rsp+150h] [rbp+50h]
  int v94; // [rsp+158h] [rbp+58h]
  int v95; // [rsp+15Ch] [rbp+5Ch]
  __int64 v96; // [rsp+160h] [rbp+60h]
  __int64 v97; // [rsp+168h] [rbp+68h]

  v96 = a22;
  v23 = -1;
  v97 = 4;
  v25 = 1;
  v26 = *a21;
  if ( *a21 )
  {
    v27 = -1;
    do
      ++v27;
    while ( *((_BYTE *)v26 + v27) );
    v28 = v27 + 1;
  }
  else
  {
    v26 = &word_18001582A;
    v28 = 1;
  }
  v94 = v28;
  v91 = a20;
  v93 = v26;
  v95 = 0;
  v92 = 4;
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
    v29 = &word_18001582A;
    v31 = 1;
  }
  v89 = v31;
  v88 = v29;
  v90 = 0;
  v32 = *a18;
  if ( *a18 )
  {
    v33 = -1;
    do
      ++v33;
    while ( *((_BYTE *)v32 + v33) );
    v34 = v33 + 1;
  }
  else
  {
    v32 = &word_18001582A;
    v34 = 1;
  }
  v86 = v34;
  v85 = v32;
  v87 = 0;
  v35 = *a17;
  if ( *a17 )
  {
    v36 = -1;
    do
      ++v36;
    while ( *((_BYTE *)v35 + v36) );
    v37 = v36 + 1;
  }
  else
  {
    v35 = &word_18001582A;
    v37 = 1;
  }
  v83 = v37;
  v82 = v35;
  v84 = 0;
  v38 = *a16;
  if ( *a16 )
  {
    v39 = -1;
    do
      ++v39;
    while ( *((_BYTE *)v38 + v39) );
    v40 = v39 + 1;
  }
  else
  {
    v38 = &word_18001582A;
    v40 = 1;
  }
  v80 = v40;
  v77 = a15;
  v79 = v38;
  v81 = 0;
  v78 = 2;
  v41 = *a14;
  if ( *a14 )
  {
    v42 = -1;
    do
      ++v42;
    while ( *((_BYTE *)v41 + v42) );
    v43 = v42 + 1;
  }
  else
  {
    v41 = &word_18001582A;
    v43 = 1;
  }
  v75 = v43;
  v74 = v41;
  v76 = 0;
  v44 = *a13;
  if ( *a13 )
  {
    v45 = -1;
    do
      ++v45;
    while ( *((_BYTE *)v44 + v45) );
    v46 = v45 + 1;
  }
  else
  {
    v44 = &word_18001582A;
    v46 = 1;
  }
  v72 = v46;
  v71 = v44;
  v73 = 0;
  v47 = *a12;
  if ( *a12 )
  {
    v48 = -1;
    do
      ++v48;
    while ( *((_BYTE *)v47 + v48) );
    v49 = v48 + 1;
  }
  else
  {
    v47 = &word_18001582A;
    v49 = 1;
  }
  v69 = v49;
  v66 = a11;
  v68 = v47;
  v70 = 0;
  v67 = 2;
  v50 = *a10;
  if ( *a10 )
  {
    do
      ++v23;
    while ( *((_BYTE *)v50 + v23) );
    v25 = v23 + 1;
  }
  else
  {
    v50 = &word_18001582A;
  }
  v61 = a9;
  v59 = a8;
  v57 = a7;
  v55 = a6;
  v53 = a5;
  v63 = v50;
  v64 = v25;
  v65 = 0;
  v62 = 4;
  v60 = 2;
  v58 = 4;
  v56 = 4;
  v54 = 4;
  return tlgWriteTransfer_EventWriteTransfer(a1, a2, 0, 0, 0x14u, &v52);
}

```

## disassembly

```asm
0x1800012cc  mov     [rsp-8+arg_10], rbx
0x1800012d1  mov     [rsp-8+arg_18], rsi
0x1800012d6  push    rbp
0x1800012d7  lea     rbp, [rsp-80h]
0x1800012dc  sub     rsp, 180h
0x1800012e3  mov     rax, cs:__security_cookie
0x1800012ea  xor     rax, rsp
0x1800012ed  mov     [rbp+80h+var_10], rax
0x1800012f1  mov     rax, [rbp+80h+arg_A8]
0x1800012f8  lea     rbx, word_18001582A
0x1800012ff  xor     r9d, r9d; int
0x180001302  mov     [rbp+80h+var_20], rax
0x180001306  mov     rax, [rbp+80h+arg_A0]
0x18000130d  mov     r10, rcx
0x180001310  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180001314  mov     [rbp+80h+var_18], 4
0x18000131c  mov     r11, rdx
0x18000131f  lea     edx, [r9+1]
0x180001323  mov     r8, [rax]
0x180001326  test    r8, r8
0x180001329  jz      short loc_18000133B
0x18000132b  mov     rax, rcx
0x18000132e  inc     rax
0x180001331  cmp     [r8+rax], r9b
0x180001335  jnz     short loc_18000132E
0x180001337  inc     eax
0x180001339  jmp     short loc_180001340
0x18000133b  mov     r8, rbx
0x18000133e  mov     eax, edx
0x180001340  mov     [rbp+80h+var_28], eax
0x180001343  mov     rax, [rbp+80h+arg_98]
0x18000134a  mov     [rbp+80h+var_40], rax
0x18000134e  mov     rax, [rbp+80h+arg_90]
0x180001355  mov     [rbp+80h+var_30], r8
0x180001359  mov     [rbp+80h+var_24], r9d
0x18000135d  mov     [rbp+80h+var_38], 4
0x180001365  mov     r8, [rax]
0x180001368  test    r8, r8
0x18000136b  jz      short loc_18000137D
0x18000136d  mov     rax, rcx
0x180001370  inc     rax
0x180001373  cmp     [r8+rax], r9b
0x180001377  jnz     short loc_180001370
0x180001379  inc     eax
0x18000137b  jmp     short loc_180001382
0x18000137d  mov     r8, rbx
0x180001380  mov     eax, edx
0x180001382  mov     [rbp+80h+var_48], eax
0x180001385  mov     rax, [rbp+80h+arg_88]
0x18000138c  mov     [rbp+80h+var_50], r8
0x180001390  mov     [rbp+80h+var_44], r9d
0x180001394  mov     r8, [rax]
0x180001397  test    r8, r8
0x18000139a  jz      short loc_1800013AC
0x18000139c  mov     rax, rcx
0x18000139f  inc     rax
0x1800013a2  cmp     [r8+rax], r9b
0x1800013a6  jnz     short loc_18000139F
0x1800013a8  inc     eax
0x1800013aa  jmp     short loc_1800013B1
0x1800013ac  mov     r8, rbx
0x1800013af  mov     eax, edx
0x1800013b1  mov     [rbp+80h+var_58], eax
0x1800013b4  mov     rax, [rbp+80h+arg_80]
0x1800013bb  mov     [rbp+80h+var_60], r8
0x1800013bf  mov     [rbp+80h+var_54], r9d
0x1800013c3  mov     r8, [rax]
0x1800013c6  test    r8, r8
0x1800013c9  jz      short loc_1800013DB
0x1800013cb  mov     rax, rcx
0x1800013ce  inc     rax
0x1800013d1  cmp     [r8+rax], r9b
0x1800013d5  jnz     short loc_1800013CE
0x1800013d7  inc     eax
0x1800013d9  jmp     short loc_1800013E0
0x1800013db  mov     r8, rbx
0x1800013de  mov     eax, edx
0x1800013e0  mov     [rbp+80h+var_68], eax
0x1800013e3  mov     rax, [rbp+80h+arg_78]
0x1800013ea  mov     [rbp+80h+var_70], r8
0x1800013ee  mov     [rbp+80h+var_64], r9d
0x1800013f2  mov     r8, [rax]
0x1800013f5  test    r8, r8
0x1800013f8  jz      short loc_18000140A
0x1800013fa  mov     rax, rcx
0x1800013fd  inc     rax
0x180001400  cmp     [r8+rax], r9b
0x180001404  jnz     short loc_1800013FD
0x180001406  inc     eax
0x180001408  jmp     short loc_18000140F
0x18000140a  mov     r8, rbx
0x18000140d  mov     eax, edx
0x18000140f  mov     [rbp+80h+var_78], eax
0x180001412  mov     rax, [rbp+80h+arg_70]
0x180001419  mov     [rbp+80h+var_90], rax
0x18000141d  mov     rax, [rbp+80h+arg_68]
0x180001424  mov     [rbp+80h+var_80], r8
0x180001428  mov     [rbp+80h+var_74], r9d
0x18000142c  mov     [rbp+80h+var_88], 2
0x180001434  mov     r8, [rax]
0x180001437  test    r8, r8
0x18000143a  jz      short loc_18000144C
0x18000143c  mov     rax, rcx
0x18000143f  inc     rax
0x180001442  cmp     [r8+rax], r9b
0x180001446  jnz     short loc_18000143F
0x180001448  inc     eax
0x18000144a  jmp     short loc_180001451
0x18000144c  mov     r8, rbx
0x18000144f  mov     eax, edx
0x180001451  mov     [rbp+80h+var_98], eax
0x180001454  mov     rax, [rbp+80h+arg_60]
0x18000145b  mov     [rbp+80h+var_A0], r8
0x18000145f  mov     [rbp+80h+var_94], r9d
0x180001463  mov     r8, [rax]
0x180001466  test    r8, r8
0x180001469  jz      short loc_18000147B
0x18000146b  mov     rax, rcx
0x18000146e  inc     rax
0x180001471  cmp     [r8+rax], r9b
0x180001475  jnz     short loc_18000146E
0x180001477  inc     eax
0x180001479  jmp     short loc_180001480
0x18000147b  mov     r8, rbx
0x18000147e  mov     eax, edx
0x180001480  mov     [rbp+80h+var_A8], eax
0x180001483  mov     rax, [rbp+80h+arg_58]
0x18000148a  mov     [rbp+80h+var_B0], r8
0x18000148e  mov     [rbp+80h+var_A4], r9d
0x180001492  mov     r8, [rax]
0x180001495  test    r8, r8
0x180001498  jz      short loc_1800014AA
0x18000149a  mov     rax, rcx
0x18000149d  inc     rax
0x1800014a0  cmp     [r8+rax], r9b
0x1800014a4  jnz     short loc_18000149D
0x1800014a6  inc     eax
0x1800014a8  jmp     short loc_1800014AF
0x1800014aa  mov     r8, rbx
0x1800014ad  mov     eax, edx
0x1800014af  mov     [rbp+80h+var_B8], eax
0x1800014b2  mov     rax, [rbp+80h+arg_50]
0x1800014b9  mov     [rbp+80h+var_D0], rax
0x1800014bd  mov     rax, [rbp+80h+arg_48]
0x1800014c4  mov     [rbp+80h+var_C0], r8
0x1800014c8  mov     [rbp+80h+var_B4], r9d
0x1800014cc  mov     [rbp+80h+var_C8], 2
0x1800014d4  mov     r8, [rax]
0x1800014d7  test    r8, r8
0x1800014da  jz      short loc_1800014EA
0x1800014dc  inc     rcx
0x1800014df  cmp     [r8+rcx], r9b
0x1800014e3  jnz     short loc_1800014DC
0x1800014e5  lea     edx, [rcx+1]
0x1800014e8  jmp     short loc_1800014ED
0x1800014ea  mov     r8, rbx
0x1800014ed  mov     rax, [rbp+80h+arg_40]
0x1800014f4  mov     rcx, r10; int
0x1800014f7  mov     [rbp+80h+var_F0], rax
0x1800014fb  mov     rax, [rbp+80h+arg_38]
0x180001502  mov     [rbp+80h+var_100], rax
0x180001506  mov     rax, [rbp+80h+arg_30]
0x18000150d  mov     [rsp+180h+var_110], rax
0x180001512  mov     rax, [rbp+80h+arg_28]
0x180001519  mov     [rsp+180h+var_120], rax
0x18000151e  mov     rax, [rbp+80h+arg_20]
0x180001525  mov     [rsp+180h+var_130], rax
0x18000152a  lea     rax, [rsp+180h+var_150]
0x18000152f  mov     [rbp+80h+var_E0], r8
0x180001533  xor     r8d, r8d; int
0x180001536  mov     [rbp+80h+var_D8], edx
0x180001539  mov     rdx, r11; int
0x18000153c  mov     [rsp+180h+var_158], rax; PEVENT_DATA_DESCRIPTOR
0x180001541  mov     [rsp+180h+var_160], 14h; ULONG
0x180001549  mov     [rbp+80h+var_D4], r9d
0x18000154d  mov     [rbp+80h+var_E8], 4
0x180001555  mov     [rbp+80h+var_F8], 2
0x18000155d  mov     [rsp+180h+var_108], 4
0x180001566  mov     [rsp+180h+var_118], 4
0x18000156f  mov     [rsp+180h+var_128], 4
0x180001578  call    _tlgWriteTransfer_EventWriteTransfer
0x18000157d  mov     rcx, [rbp+80h+var_10]
0x180001581  xor     rcx, rsp; StackCookie
0x180001584  call    __security_check_cookie
0x180001589  lea     r11, [rsp+180h+var_s0]
0x180001591  mov     rbx, [r11+20h]
0x180001595  mov     rsi, [r11+28h]
0x180001599  mov     rsp, r11
0x18000159c  pop     rbp
0x18000159d  retn
```
