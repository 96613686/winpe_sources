# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<1> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)

- ea: `0x1400012bc`
- end: `0x140001588`
- name: `??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$00@@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@U3@U4@U3@U4@U4@U4@U3@U3@U4@U3@U4@U3@U4@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$00@@AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@56566655656566@Z`
- size: `716`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, __int64, __int64, __int64 **, __int64, __int64 **, __int64, __int64 **, __int64, __int64, __int64, __int64 **, __int64 **, __int64, __int64 **, __int64, __int64 **, __int64, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x140008214`

## callees

- `0x1400012bc`
- `0x140001bac`
- `0x1400022a0`

## pseudocode

```c
__int64 __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        __int64 **a7,
        __int64 a8,
        __int64 **a9,
        __int64 a10,
        __int64 **a11,
        __int64 a12,
        __int64 a13,
        __int64 a14,
        __int64 **a15,
        __int64 **a16,
        __int64 a17,
        __int64 **a18,
        __int64 a19,
        __int64 **a20,
        __int64 a21,
        __int64 a22)
{
  __int64 v24; // rcx
  int v25; // r8d
  __int64 *v26; // rdx
  __int64 v27; // rax
  int v28; // eax
  __int64 *v29; // rdx
  __int64 v30; // rax
  int v31; // eax
  __int64 *v32; // rdx
  __int64 v33; // rax
  int v34; // eax
  __int64 *v35; // rdx
  __int64 v36; // rax
  int v37; // eax
  __int64 *v38; // rdx
  __int64 v39; // rax
  int v40; // eax
  __int64 *v41; // rdx
  __int64 v42; // rax
  int v43; // eax
  __int64 *v44; // rdx
  _BYTE v46[32]; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v47; // [rsp+50h] [rbp-B0h]
  __int64 v48; // [rsp+58h] [rbp-A8h]
  __int64 v49; // [rsp+60h] [rbp-A0h]
  __int64 v50; // [rsp+68h] [rbp-98h]
  __int64 *v51; // [rsp+70h] [rbp-90h]
  int v52; // [rsp+78h] [rbp-88h]
  int v53; // [rsp+7Ch] [rbp-84h]
  __int64 v54; // [rsp+80h] [rbp-80h]
  __int64 v55; // [rsp+88h] [rbp-78h]
  __int64 *v56; // [rsp+90h] [rbp-70h]
  int v57; // [rsp+98h] [rbp-68h]
  int v58; // [rsp+9Ch] [rbp-64h]
  __int64 v59; // [rsp+A0h] [rbp-60h]
  __int64 v60; // [rsp+A8h] [rbp-58h]
  __int64 *v61; // [rsp+B0h] [rbp-50h]
  int v62; // [rsp+B8h] [rbp-48h]
  int v63; // [rsp+BCh] [rbp-44h]
  __int64 v64; // [rsp+C0h] [rbp-40h]
  __int64 v65; // [rsp+C8h] [rbp-38h]
  __int64 v66; // [rsp+D0h] [rbp-30h]
  __int64 v67; // [rsp+D8h] [rbp-28h]
  __int64 v68; // [rsp+E0h] [rbp-20h]
  __int64 v69; // [rsp+E8h] [rbp-18h]
  __int64 *v70; // [rsp+F0h] [rbp-10h]
  int v71; // [rsp+F8h] [rbp-8h]
  int v72; // [rsp+FCh] [rbp-4h]
  __int64 *v73; // [rsp+100h] [rbp+0h]
  int v74; // [rsp+108h] [rbp+8h]
  int v75; // [rsp+10Ch] [rbp+Ch]
  __int64 v76; // [rsp+110h] [rbp+10h]
  __int64 v77; // [rsp+118h] [rbp+18h]
  __int64 *v78; // [rsp+120h] [rbp+20h]
  int v79; // [rsp+128h] [rbp+28h]
  int v80; // [rsp+12Ch] [rbp+2Ch]
  __int64 v81; // [rsp+130h] [rbp+30h]
  __int64 v82; // [rsp+138h] [rbp+38h]
  __int64 *v83; // [rsp+140h] [rbp+40h]
  int v84; // [rsp+148h] [rbp+48h]
  int v85; // [rsp+14Ch] [rbp+4Ch]
  __int64 v86; // [rsp+150h] [rbp+50h]
  __int64 v87; // [rsp+158h] [rbp+58h]
  __int64 v88; // [rsp+160h] [rbp+60h]
  __int64 v89; // [rsp+168h] [rbp+68h]

  v88 = a22;
  v86 = a21;
  v24 = -1;
  v89 = 4;
  v25 = 2;
  v87 = 4;
  v26 = *a20;
  if ( *a20 )
  {
    v27 = -1;
    do
      ++v27;
    while ( *((_WORD *)v26 + v27) );
    v28 = 2 * v27 + 2;
  }
  else
  {
    v26 = &qword_140013B88;
    v28 = 2;
  }
  v84 = v28;
  v81 = a19;
  v83 = v26;
  v85 = 0;
  v82 = 4;
  v29 = *a18;
  if ( *a18 )
  {
    v30 = -1;
    do
      ++v30;
    while ( *((_WORD *)v29 + v30) );
    v31 = 2 * v30 + 2;
  }
  else
  {
    v29 = &qword_140013B88;
    v31 = 2;
  }
  v79 = v31;
  v76 = a17;
  v78 = v29;
  v80 = 0;
  v77 = 4;
  v32 = *a16;
  if ( *a16 )
  {
    v33 = -1;
    do
      ++v33;
    while ( *((_WORD *)v32 + v33) );
    v34 = 2 * v33 + 2;
  }
  else
  {
    v32 = &qword_140013B88;
    v34 = 2;
  }
  v74 = v34;
  v73 = v32;
  v75 = 0;
  v35 = *a15;
  if ( *a15 )
  {
    v36 = -1;
    do
      ++v36;
    while ( *((_WORD *)v35 + v36) );
    v37 = 2 * v36 + 2;
  }
  else
  {
    v35 = &qword_140013B88;
    v37 = 2;
  }
  v71 = v37;
  v68 = a14;
  v66 = a13;
  v64 = a12;
  v70 = v35;
  v72 = 0;
  v69 = 4;
  v38 = *a11;
  v67 = 4;
  v65 = 4;
  if ( v38 )
  {
    v39 = -1;
    do
      ++v39;
    while ( *((_WORD *)v38 + v39) );
    v40 = 2 * v39 + 2;
  }
  else
  {
    v38 = &qword_140013B88;
    v40 = 2;
  }
  v62 = v40;
  v59 = a10;
  v61 = v38;
  v63 = 0;
  v60 = 4;
  v41 = *a9;
  if ( *a9 )
  {
    v42 = -1;
    do
      ++v42;
    while ( *((_WORD *)v41 + v42) );
    v43 = 2 * v42 + 2;
  }
  else
  {
    v41 = &qword_140013B88;
    v43 = 2;
  }
  v57 = v43;
  v54 = a8;
  v56 = v41;
  v58 = 0;
  v55 = 4;
  v44 = *a7;
  if ( *a7 )
  {
    do
      ++v24;
    while ( *((_WORD *)v44 + v24) );
    v25 = 2 * v24 + 2;
  }
  else
  {
    v44 = &qword_140013B88;
  }
  v49 = a6;
  v47 = a5;
  v51 = v44;
  v52 = v25;
  v53 = 0;
  v50 = 1;
  v48 = 8;
  return tlgWriteTransfer_EventWriteTransfer(a1, a2, 0, 0, 20, v46);
}

```

## disassembly

```asm
0x1400012bc  mov     [rsp-8+arg_10], rbx
0x1400012c1  mov     [rsp-8+arg_18], rdi
0x1400012c6  push    rbp
0x1400012c7  lea     rbp, [rsp-80h]
0x1400012cc  sub     rsp, 180h
0x1400012d3  mov     rax, cs:__security_cookie
0x1400012da  xor     rax, rsp
0x1400012dd  mov     [rbp+80h+var_10], rax
0x1400012e1  mov     rax, [rbp+80h+arg_A8]
0x1400012e8  lea     rbx, qword_140013B88
0x1400012ef  mov     [rbp+80h+var_20], rax
0x1400012f3  xor     r9d, r9d
0x1400012f6  mov     rax, [rbp+80h+arg_A0]
0x1400012fd  mov     r11, rdx
0x140001300  mov     [rbp+80h+var_30], rax
0x140001304  mov     r10, rcx
0x140001307  mov     rax, [rbp+80h+arg_98]
0x14000130e  or      rcx, 0FFFFFFFFFFFFFFFFh
0x140001312  mov     [rbp+80h+var_18], 4
0x14000131a  lea     r8d, [r9+2]
0x14000131e  mov     [rbp+80h+var_28], 4
0x140001326  mov     rdx, [rax]
0x140001329  test    rdx, rdx
0x14000132c  jz      short loc_140001344
0x14000132e  mov     rax, rcx
0x140001331  inc     rax
0x140001334  cmp     [rdx+rax*2], r9w
0x140001339  jnz     short loc_140001331
0x14000133b  lea     eax, ds:2[rax*2]
0x140001342  jmp     short loc_14000134A
0x140001344  mov     rdx, rbx
0x140001347  mov     eax, r8d
0x14000134a  mov     [rbp+80h+var_38], eax
0x14000134d  mov     rax, [rbp+80h+arg_90]
0x140001354  mov     [rbp+80h+var_50], rax
0x140001358  mov     rax, [rbp+80h+arg_88]
0x14000135f  mov     [rbp+80h+var_40], rdx
0x140001363  mov     [rbp+80h+var_34], r9d
0x140001367  mov     [rbp+80h+var_48], 4
0x14000136f  mov     rdx, [rax]
0x140001372  test    rdx, rdx
0x140001375  jz      short loc_14000138D
0x140001377  mov     rax, rcx
0x14000137a  inc     rax
0x14000137d  cmp     [rdx+rax*2], r9w
0x140001382  jnz     short loc_14000137A
0x140001384  lea     eax, ds:2[rax*2]
0x14000138b  jmp     short loc_140001393
0x14000138d  mov     rdx, rbx
0x140001390  mov     eax, r8d
0x140001393  mov     [rbp+80h+var_58], eax
0x140001396  mov     rax, [rbp+80h+arg_80]
0x14000139d  mov     [rbp+80h+var_70], rax
0x1400013a1  mov     rax, [rbp+80h+arg_78]
0x1400013a8  mov     [rbp+80h+var_60], rdx
0x1400013ac  mov     [rbp+80h+var_54], r9d
0x1400013b0  mov     [rbp+80h+var_68], 4
0x1400013b8  mov     rdx, [rax]
0x1400013bb  test    rdx, rdx
0x1400013be  jz      short loc_1400013D6
0x1400013c0  mov     rax, rcx
0x1400013c3  inc     rax
0x1400013c6  cmp     [rdx+rax*2], r9w
0x1400013cb  jnz     short loc_1400013C3
0x1400013cd  lea     eax, ds:2[rax*2]
0x1400013d4  jmp     short loc_1400013DC
0x1400013d6  mov     rdx, rbx
0x1400013d9  mov     eax, r8d
0x1400013dc  mov     [rbp+80h+var_78], eax
0x1400013df  mov     rax, [rbp+80h+arg_70]
0x1400013e6  mov     [rbp+80h+var_80], rdx
0x1400013ea  mov     [rbp+80h+var_74], r9d
0x1400013ee  mov     rdx, [rax]
0x1400013f1  test    rdx, rdx
0x1400013f4  jz      short loc_14000140C
0x1400013f6  mov     rax, rcx
0x1400013f9  inc     rax
0x1400013fc  cmp     [rdx+rax*2], r9w
0x140001401  jnz     short loc_1400013F9
0x140001403  lea     eax, ds:2[rax*2]
0x14000140a  jmp     short loc_140001412
0x14000140c  mov     rdx, rbx
0x14000140f  mov     eax, r8d
0x140001412  mov     [rbp+80h+var_88], eax
0x140001415  mov     rax, [rbp+80h+arg_68]
0x14000141c  mov     [rbp+80h+var_A0], rax
0x140001420  mov     rax, [rbp+80h+arg_60]
0x140001427  mov     [rbp+80h+var_B0], rax
0x14000142b  mov     rax, [rbp+80h+arg_58]
0x140001432  mov     [rbp+80h+var_C0], rax
0x140001436  mov     rax, [rbp+80h+arg_50]
0x14000143d  mov     [rbp+80h+var_90], rdx
0x140001441  mov     [rbp+80h+var_84], r9d
0x140001445  mov     [rbp+80h+var_98], 4
0x14000144d  mov     rdx, [rax]
0x140001450  mov     [rbp+80h+var_A8], 4
0x140001458  mov     [rbp+80h+var_B8], 4
0x140001460  test    rdx, rdx
0x140001463  jz      short loc_14000147B
0x140001465  mov     rax, rcx
0x140001468  inc     rax
0x14000146b  cmp     [rdx+rax*2], r9w
0x140001470  jnz     short loc_140001468
0x140001472  lea     eax, ds:2[rax*2]
0x140001479  jmp     short loc_140001481
0x14000147b  mov     rdx, rbx
0x14000147e  mov     eax, r8d
0x140001481  mov     [rbp+80h+var_C8], eax
0x140001484  mov     rax, [rbp+80h+arg_48]
0x14000148b  mov     [rbp+80h+var_E0], rax
0x14000148f  mov     rax, [rbp+80h+arg_40]
0x140001496  mov     [rbp+80h+var_D0], rdx
0x14000149a  mov     [rbp+80h+var_C4], r9d
0x14000149e  mov     [rbp+80h+var_D8], 4
0x1400014a6  mov     rdx, [rax]
0x1400014a9  test    rdx, rdx
0x1400014ac  jz      short loc_1400014C4
0x1400014ae  mov     rax, rcx
0x1400014b1  inc     rax
0x1400014b4  cmp     [rdx+rax*2], r9w
0x1400014b9  jnz     short loc_1400014B1
0x1400014bb  lea     eax, ds:2[rax*2]
0x1400014c2  jmp     short loc_1400014CA
0x1400014c4  mov     rdx, rbx
0x1400014c7  mov     eax, r8d
0x1400014ca  mov     [rbp+80h+var_E8], eax
0x1400014cd  mov     rax, [rbp+80h+arg_38]
0x1400014d4  mov     [rbp+80h+var_100], rax
0x1400014d8  mov     rax, [rbp+80h+arg_30]
0x1400014df  mov     [rbp+80h+var_F0], rdx
0x1400014e3  mov     [rbp+80h+var_E4], r9d
0x1400014e7  mov     [rbp+80h+var_F8], 4
0x1400014ef  mov     rdx, [rax]
0x1400014f2  test    rdx, rdx
0x1400014f5  jz      short loc_14000150B
0x1400014f7  inc     rcx
0x1400014fa  cmp     [rdx+rcx*2], r9w
0x1400014ff  jnz     short loc_1400014F7
0x140001501  lea     r8d, ds:2[rcx*2]
0x140001509  jmp     short loc_14000150E
0x14000150b  mov     rdx, rbx
0x14000150e  mov     rax, [rbp+80h+arg_28]
0x140001515  mov     rcx, r10
0x140001518  mov     [rsp+180h+var_120], rax
0x14000151d  mov     rax, [rbp+80h+arg_20]
0x140001524  mov     [rsp+180h+var_130], rax
0x140001529  lea     rax, [rsp+180h+var_150]
0x14000152e  mov     [rsp+180h+var_110], rdx
0x140001533  mov     rdx, r11
0x140001536  mov     [rsp+180h+var_108], r8d
0x14000153b  xor     r8d, r8d
0x14000153e  mov     [rsp+180h+var_158], rax
0x140001543  mov     [rsp+180h+var_160], 14h
0x14000154b  mov     [rsp+180h+var_104], r9d
0x140001550  mov     [rsp+180h+var_118], 1
0x140001559  mov     [rsp+180h+var_128], 8
0x140001562  call    _tlgWriteTransfer_EventWriteTransfer
0x140001567  mov     rcx, [rbp+80h+var_10]
0x14000156b  xor     rcx, rsp; StackCookie
0x14000156e  call    __security_check_cookie
0x140001573  lea     r11, [rsp+180h+var_s0]
0x14000157b  mov     rbx, [r11+20h]
0x14000157f  mov     rdi, [r11+28h]
0x140001583  mov     rsp, r11
0x140001586  pop     rbp
0x140001587  retn
```
