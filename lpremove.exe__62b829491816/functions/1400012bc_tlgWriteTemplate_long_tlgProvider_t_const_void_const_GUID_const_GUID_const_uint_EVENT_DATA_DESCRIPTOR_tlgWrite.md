# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<8> const &)

- ea: `0x1400012bc`
- end: `0x14000157a`
- name: `??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@454564563@Z`
- size: `702`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, __int64, __int64, __int64, const unsigned __int16 **, __int64, const unsigned __int16 **, __int64, int **, __int64, const unsigned __int16 **, __int64, const unsigned __int16 **, int **, __int64, const unsigned __int16 **, int **, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x14000b504`

## callees

- `0x1400012bc`
- `0x140001b9c`
- `0x140002190`

## pseudocode

```c
__int64 __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<8>>(
        __int64 a1,
        __int64 a2,
        __int64 a3,
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
        __int64 a21)
{
  __int64 v23; // rdx
  int v25; // r9d
  int *v26; // rcx
  __int64 v27; // rax
  int v28; // eax
  int v29; // r8d
  const unsigned __int16 *v30; // rcx
  __int64 v31; // rax
  int v32; // eax
  int *v33; // rcx
  __int64 v34; // rax
  int v35; // eax
  const unsigned __int16 *v36; // rcx
  __int64 v37; // rax
  int v38; // eax
  const unsigned __int16 *v39; // rcx
  __int64 v40; // rax
  int v41; // eax
  int *v42; // rcx
  __int64 v43; // rax
  const unsigned __int16 *v44; // rcx
  __int64 v45; // rax
  int v46; // eax
  const unsigned __int16 *v47; // rcx
  _BYTE v49[32]; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v50; // [rsp+50h] [rbp-B0h]
  __int64 v51; // [rsp+58h] [rbp-A8h]
  __int64 v52; // [rsp+60h] [rbp-A0h]
  __int64 v53; // [rsp+68h] [rbp-98h]
  __int64 v54; // [rsp+70h] [rbp-90h]
  __int64 v55; // [rsp+78h] [rbp-88h]
  const unsigned __int16 *v56; // [rsp+80h] [rbp-80h]
  int v57; // [rsp+88h] [rbp-78h]
  int v58; // [rsp+8Ch] [rbp-74h]
  __int64 v59; // [rsp+90h] [rbp-70h]
  __int64 v60; // [rsp+98h] [rbp-68h]
  const unsigned __int16 *v61; // [rsp+A0h] [rbp-60h]
  int v62; // [rsp+A8h] [rbp-58h]
  int v63; // [rsp+ACh] [rbp-54h]
  __int64 v64; // [rsp+B0h] [rbp-50h]
  __int64 v65; // [rsp+B8h] [rbp-48h]
  int *v66; // [rsp+C0h] [rbp-40h]
  int v67; // [rsp+C8h] [rbp-38h]
  int v68; // [rsp+CCh] [rbp-34h]
  __int64 v69; // [rsp+D0h] [rbp-30h]
  __int64 v70; // [rsp+D8h] [rbp-28h]
  const unsigned __int16 *v71; // [rsp+E0h] [rbp-20h]
  int v72; // [rsp+E8h] [rbp-18h]
  int v73; // [rsp+ECh] [rbp-14h]
  __int64 v74; // [rsp+F0h] [rbp-10h]
  __int64 v75; // [rsp+F8h] [rbp-8h]
  const unsigned __int16 *v76; // [rsp+100h] [rbp+0h]
  int v77; // [rsp+108h] [rbp+8h]
  int v78; // [rsp+10Ch] [rbp+Ch]
  int *v79; // [rsp+110h] [rbp+10h]
  int v80; // [rsp+118h] [rbp+18h]
  int v81; // [rsp+11Ch] [rbp+1Ch]
  __int64 v82; // [rsp+120h] [rbp+20h]
  __int64 v83; // [rsp+128h] [rbp+28h]
  const unsigned __int16 *v84; // [rsp+130h] [rbp+30h]
  int v85; // [rsp+138h] [rbp+38h]
  int v86; // [rsp+13Ch] [rbp+3Ch]
  int *v87; // [rsp+140h] [rbp+40h]
  int v88; // [rsp+148h] [rbp+48h]
  int v89; // [rsp+14Ch] [rbp+4Ch]
  __int64 v90; // [rsp+150h] [rbp+50h]
  __int64 v91; // [rsp+158h] [rbp+58h]

  v90 = a21;
  v23 = -1;
  v91 = 8;
  v25 = 2;
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
    v26 = &dword_140013804;
    v28 = 2;
  }
  v88 = v28;
  v29 = 1;
  v87 = v26;
  v89 = 0;
  v30 = *a19;
  if ( *a19 )
  {
    v31 = -1;
    do
      ++v31;
    while ( *((_BYTE *)v30 + v31) );
    v32 = v31 + 1;
  }
  else
  {
    v30 = &byte_140013800;
    v32 = 1;
  }
  v85 = v32;
  v82 = a18;
  v84 = v30;
  v86 = 0;
  v83 = 4;
  v33 = *a17;
  if ( *a17 )
  {
    v34 = -1;
    do
      ++v34;
    while ( *((_WORD *)v33 + v34) );
    v35 = 2 * v34 + 2;
  }
  else
  {
    v33 = &dword_140013804;
    v35 = 2;
  }
  v80 = v35;
  v79 = v33;
  v81 = 0;
  v36 = *a16;
  if ( *a16 )
  {
    v37 = -1;
    do
      ++v37;
    while ( *((_BYTE *)v36 + v37) );
    v38 = v37 + 1;
  }
  else
  {
    v36 = &byte_140013800;
    v38 = 1;
  }
  v77 = v38;
  v74 = a15;
  v76 = v36;
  v78 = 0;
  v75 = 4;
  v39 = *a14;
  if ( *a14 )
  {
    v40 = -1;
    do
      ++v40;
    while ( *((_BYTE *)v39 + v40) );
    v41 = v40 + 1;
  }
  else
  {
    v39 = &byte_140013800;
    v41 = 1;
  }
  v72 = v41;
  v69 = a13;
  v71 = v39;
  v73 = 0;
  v70 = 4;
  v42 = *a12;
  if ( *a12 )
  {
    v43 = -1;
    do
      ++v43;
    while ( *((_WORD *)v42 + v43) );
    v25 = 2 * v43 + 2;
  }
  else
  {
    v42 = &dword_140013804;
  }
  v64 = a11;
  v66 = v42;
  v67 = v25;
  v68 = 0;
  v44 = *a10;
  v65 = 4;
  if ( v44 )
  {
    v45 = -1;
    do
      ++v45;
    while ( *((_BYTE *)v44 + v45) );
    v46 = v45 + 1;
  }
  else
  {
    v44 = &byte_140013800;
    v46 = 1;
  }
  v62 = v46;
  v59 = a9;
  v61 = v44;
  v63 = 0;
  v60 = 4;
  v47 = *a8;
  if ( *a8 )
  {
    do
      ++v23;
    while ( *((_BYTE *)v47 + v23) );
    v29 = v23 + 1;
  }
  else
  {
    v47 = &byte_140013800;
  }
  v54 = a7;
  v52 = a6;
  v50 = a5;
  v56 = v47;
  v57 = v29;
  v58 = 0;
  v55 = 4;
  v53 = 8;
  v51 = 8;
  return tlgWriteTransfer_EventWriteTransfer(a1, a2, a3, 0, 19, v49);
}

```

## disassembly

```asm
0x1400012bc  push    rbp
0x1400012be  push    rbx
0x1400012bf  push    rsi
0x1400012c0  push    rdi
0x1400012c1  push    r14
0x1400012c3  lea     rbp, [rsp-70h]
0x1400012c8  sub     rsp, 170h
0x1400012cf  mov     rax, cs:__security_cookie
0x1400012d6  xor     rax, rsp
0x1400012d9  mov     [rbp+90h+var_30], rax
0x1400012dd  mov     rax, [rbp+90h+arg_A0]
0x1400012e4  xor     edi, edi
0x1400012e6  mov     [rbp+90h+var_40], rax
0x1400012ea  mov     r11, rdx
0x1400012ed  mov     rax, [rbp+90h+arg_98]
0x1400012f4  mov     r10, rcx
0x1400012f7  or      rdx, 0FFFFFFFFFFFFFFFFh
0x1400012fb  mov     [rbp+90h+var_38], 8
0x140001303  mov     rbx, r8
0x140001306  lea     r9d, [rdi+2]
0x14000130a  mov     rcx, [rax]
0x14000130d  test    rcx, rcx
0x140001310  jz      short loc_140001327
0x140001312  mov     rax, rdx
0x140001315  inc     rax
0x140001318  cmp     [rcx+rax*2], di
0x14000131c  jnz     short loc_140001315
0x14000131e  lea     eax, ds:2[rax*2]
0x140001325  jmp     short loc_140001331
0x140001327  lea     rcx, dword_140013804
0x14000132e  mov     eax, r9d
0x140001331  mov     [rbp+90h+var_48], eax
0x140001334  lea     rsi, byte_140013800
0x14000133b  mov     rax, [rbp+90h+arg_90]
0x140001342  mov     r8d, 1
0x140001348  mov     [rbp+90h+var_50], rcx
0x14000134c  mov     [rbp+90h+var_44], edi
0x14000134f  mov     rcx, [rax]
0x140001352  test    rcx, rcx
0x140001355  jz      short loc_140001367
0x140001357  mov     rax, rdx
0x14000135a  inc     rax
0x14000135d  cmp     [rcx+rax], dil
0x140001361  jnz     short loc_14000135A
0x140001363  inc     eax
0x140001365  jmp     short loc_14000136D
0x140001367  mov     rcx, rsi
0x14000136a  mov     eax, r8d
0x14000136d  mov     [rbp+90h+var_58], eax
0x140001370  mov     rax, [rbp+90h+arg_88]
0x140001377  mov     [rbp+90h+var_70], rax
0x14000137b  mov     rax, [rbp+90h+arg_80]
0x140001382  mov     [rbp+90h+var_60], rcx
0x140001386  mov     [rbp+90h+var_54], edi
0x140001389  mov     [rbp+90h+var_68], 4
0x140001391  mov     rcx, [rax]
0x140001394  test    rcx, rcx
0x140001397  jz      short loc_1400013AE
0x140001399  mov     rax, rdx
0x14000139c  inc     rax
0x14000139f  cmp     [rcx+rax*2], di
0x1400013a3  jnz     short loc_14000139C
0x1400013a5  lea     eax, ds:2[rax*2]
0x1400013ac  jmp     short loc_1400013B8
0x1400013ae  lea     rcx, dword_140013804
0x1400013b5  mov     eax, r9d
0x1400013b8  mov     [rbp+90h+var_78], eax
0x1400013bb  mov     rax, [rbp+90h+arg_78]
0x1400013c2  mov     [rbp+90h+var_80], rcx
0x1400013c6  mov     [rbp+90h+var_74], edi
0x1400013c9  mov     rcx, [rax]
0x1400013cc  test    rcx, rcx
0x1400013cf  jz      short loc_1400013E1
0x1400013d1  mov     rax, rdx
0x1400013d4  inc     rax
0x1400013d7  cmp     [rcx+rax], dil
0x1400013db  jnz     short loc_1400013D4
0x1400013dd  inc     eax
0x1400013df  jmp     short loc_1400013E7
0x1400013e1  mov     rcx, rsi
0x1400013e4  mov     eax, r8d
0x1400013e7  mov     [rbp+90h+var_88], eax
0x1400013ea  mov     rax, [rbp+90h+arg_70]
0x1400013f1  mov     [rbp+90h+var_A0], rax
0x1400013f5  mov     rax, [rbp+90h+arg_68]
0x1400013fc  mov     [rbp+90h+var_90], rcx
0x140001400  mov     [rbp+90h+var_84], edi
0x140001403  mov     [rbp+90h+var_98], 4
0x14000140b  mov     rcx, [rax]
0x14000140e  test    rcx, rcx
0x140001411  jz      short loc_140001423
0x140001413  mov     rax, rdx
0x140001416  inc     rax
0x140001419  cmp     [rcx+rax], dil
0x14000141d  jnz     short loc_140001416
0x14000141f  inc     eax
0x140001421  jmp     short loc_140001429
0x140001423  mov     rcx, rsi
0x140001426  mov     eax, r8d
0x140001429  mov     [rbp+90h+var_A8], eax
0x14000142c  mov     rax, [rbp+90h+arg_60]
0x140001433  mov     [rbp+90h+var_C0], rax
0x140001437  mov     rax, [rbp+90h+arg_58]
0x14000143e  mov     [rbp+90h+var_B0], rcx
0x140001442  mov     [rbp+90h+var_A4], edi
0x140001445  mov     [rbp+90h+var_B8], 4
0x14000144d  mov     rcx, [rax]
0x140001450  test    rcx, rcx
0x140001453  jz      short loc_14000146B
0x140001455  mov     rax, rdx
0x140001458  inc     rax
0x14000145b  cmp     [rcx+rax*2], di
0x14000145f  jnz     short loc_140001458
0x140001461  lea     r9d, ds:2[rax*2]
0x140001469  jmp     short loc_140001472
0x14000146b  lea     rcx, dword_140013804
0x140001472  mov     rax, [rbp+90h+arg_50]
0x140001479  mov     [rbp+90h+var_E0], rax
0x14000147d  mov     rax, [rbp+90h+arg_48]
0x140001484  mov     [rbp+90h+var_D0], rcx
0x140001488  mov     [rbp+90h+var_C8], r9d
0x14000148c  mov     [rbp+90h+var_C4], edi
0x14000148f  mov     rcx, [rax]
0x140001492  mov     [rbp+90h+var_D8], 4
0x14000149a  test    rcx, rcx
0x14000149d  jz      short loc_1400014AF
0x14000149f  mov     rax, rdx
0x1400014a2  inc     rax
0x1400014a5  cmp     [rcx+rax], dil
0x1400014a9  jnz     short loc_1400014A2
0x1400014ab  inc     eax
0x1400014ad  jmp     short loc_1400014B5
0x1400014af  mov     rcx, rsi
0x1400014b2  mov     eax, r8d
0x1400014b5  mov     [rbp+90h+var_E8], eax
0x1400014b8  mov     rax, [rbp+90h+arg_40]
0x1400014bf  mov     [rbp+90h+var_100], rax
0x1400014c3  mov     rax, [rbp+90h+arg_38]
0x1400014ca  mov     [rbp+90h+var_F0], rcx
0x1400014ce  mov     [rbp+90h+var_E4], edi
0x1400014d1  mov     [rbp+90h+var_F8], 4
0x1400014d9  mov     rcx, [rax]
0x1400014dc  test    rcx, rcx
0x1400014df  jz      short loc_1400014F0
0x1400014e1  inc     rdx
0x1400014e4  cmp     [rcx+rdx], dil
0x1400014e8  jnz     short loc_1400014E1
0x1400014ea  lea     r8d, [rdx+1]
0x1400014ee  jmp     short loc_1400014F3
0x1400014f0  mov     rcx, rsi
0x1400014f3  mov     rax, [rbp+90h+arg_30]
0x1400014fa  xor     r9d, r9d
0x1400014fd  mov     [rsp+190h+var_120], rax
0x140001502  mov     rdx, r11
0x140001505  mov     rax, [rbp+90h+arg_28]
0x14000150c  mov     [rsp+190h+var_130], rax
0x140001511  mov     rax, [rbp+90h+arg_20]
0x140001518  mov     [rsp+190h+var_140], rax
0x14000151d  lea     rax, [rsp+190h+var_160]
0x140001522  mov     [rbp+90h+var_110], rcx
0x140001526  mov     rcx, r10
0x140001529  mov     [rbp+90h+var_108], r8d
0x14000152d  mov     r8, rbx
0x140001530  mov     [rsp+190h+var_168], rax
0x140001535  mov     [rsp+190h+var_170], 13h
0x14000153d  mov     [rbp+90h+var_104], edi
0x140001540  mov     [rsp+190h+var_118], 4
0x140001549  mov     [rsp+190h+var_128], 8
0x140001552  mov     [rsp+190h+var_138], 8
0x14000155b  call    _tlgWriteTransfer_EventWriteTransfer
0x140001560  mov     rcx, [rbp+90h+var_30]
0x140001564  xor     rcx, rsp; StackCookie
0x140001567  call    __security_check_cookie
0x14000156c  add     rsp, 170h
0x140001573  pop     r14
0x140001575  pop     rdi
0x140001576  pop     rsi
0x140001577  pop     rbx
0x140001578  pop     rbp
0x140001579  retn
```
