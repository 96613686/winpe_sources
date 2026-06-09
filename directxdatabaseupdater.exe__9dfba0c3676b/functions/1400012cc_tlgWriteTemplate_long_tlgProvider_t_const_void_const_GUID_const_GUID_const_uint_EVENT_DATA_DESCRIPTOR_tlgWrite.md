# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)

- ea: `0x1400012cc`
- end: `0x14000158a`
- name: `??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@454564564@Z`
- size: `702`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, __int64, __int64, __int64, const unsigned __int16 **, __int64, const unsigned __int16 **, __int64, __int64 **, __int64, const unsigned __int16 **, __int64, const unsigned __int16 **, __int64 **, __int64, const unsigned __int16 **, __int64 **, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x14000bb94`

## callees

- `0x1400012cc`
- `0x140002318`
- `0x140002f40`

## pseudocode

```c
__int64 __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
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
        __int64 **a12,
        __int64 a13,
        const unsigned __int16 **a14,
        __int64 a15,
        const unsigned __int16 **a16,
        __int64 **a17,
        __int64 a18,
        const unsigned __int16 **a19,
        __int64 **a20,
        __int64 a21)
{
  __int64 v23; // rdx
  int v25; // r9d
  __int64 *v26; // rcx
  __int64 v27; // rax
  int v28; // eax
  int v29; // r8d
  const unsigned __int16 *v30; // rcx
  __int64 v31; // rax
  int v32; // eax
  __int64 *v33; // rcx
  __int64 v34; // rax
  int v35; // eax
  const unsigned __int16 *v36; // rcx
  __int64 v37; // rax
  int v38; // eax
  const unsigned __int16 *v39; // rcx
  __int64 v40; // rax
  int v41; // eax
  __int64 *v42; // rcx
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
  __int64 *v66; // [rsp+C0h] [rbp-40h]
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
  __int64 *v79; // [rsp+110h] [rbp+10h]
  int v80; // [rsp+118h] [rbp+18h]
  int v81; // [rsp+11Ch] [rbp+1Ch]
  __int64 v82; // [rsp+120h] [rbp+20h]
  __int64 v83; // [rsp+128h] [rbp+28h]
  const unsigned __int16 *v84; // [rsp+130h] [rbp+30h]
  int v85; // [rsp+138h] [rbp+38h]
  int v86; // [rsp+13Ch] [rbp+3Ch]
  __int64 *v87; // [rsp+140h] [rbp+40h]
  int v88; // [rsp+148h] [rbp+48h]
  int v89; // [rsp+14Ch] [rbp+4Ch]
  __int64 v90; // [rsp+150h] [rbp+50h]
  __int64 v91; // [rsp+158h] [rbp+58h]

  v90 = a21;
  v23 = -1;
  v91 = 4;
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
    v26 = &qword_14001C2F8;
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
    v30 = &byte_14001C2F5;
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
    v33 = &qword_14001C2F8;
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
    v36 = &byte_14001C2F5;
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
    v39 = &byte_14001C2F5;
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
    v42 = &qword_14001C2F8;
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
    v44 = &byte_14001C2F5;
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
    v47 = &byte_14001C2F5;
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
0x1400012cc  push    rbp
0x1400012ce  push    rbx
0x1400012cf  push    rsi
0x1400012d0  push    rdi
0x1400012d1  push    r15
0x1400012d3  lea     rbp, [rsp-70h]
0x1400012d8  sub     rsp, 170h
0x1400012df  mov     rax, cs:__security_cookie
0x1400012e6  xor     rax, rsp
0x1400012e9  mov     [rbp+90h+var_30], rax
0x1400012ed  mov     rax, [rbp+90h+arg_A0]
0x1400012f4  xor     edi, edi
0x1400012f6  mov     [rbp+90h+var_40], rax
0x1400012fa  mov     r11, rdx
0x1400012fd  mov     rax, [rbp+90h+arg_98]
0x140001304  mov     r10, rcx
0x140001307  or      rdx, 0FFFFFFFFFFFFFFFFh
0x14000130b  mov     [rbp+90h+var_38], 4
0x140001313  mov     rbx, r8
0x140001316  lea     r9d, [rdi+2]
0x14000131a  mov     rcx, [rax]
0x14000131d  test    rcx, rcx
0x140001320  jz      short loc_140001337
0x140001322  mov     rax, rdx
0x140001325  inc     rax
0x140001328  cmp     [rcx+rax*2], di
0x14000132c  jnz     short loc_140001325
0x14000132e  lea     eax, ds:2[rax*2]
0x140001335  jmp     short loc_140001341
0x140001337  lea     rcx, qword_14001C2F8
0x14000133e  mov     eax, r9d
0x140001341  mov     [rbp+90h+var_48], eax
0x140001344  lea     rsi, byte_14001C2F5
0x14000134b  mov     rax, [rbp+90h+arg_90]
0x140001352  mov     r8d, 1
0x140001358  mov     [rbp+90h+var_50], rcx
0x14000135c  mov     [rbp+90h+var_44], edi
0x14000135f  mov     rcx, [rax]
0x140001362  test    rcx, rcx
0x140001365  jz      short loc_140001377
0x140001367  mov     rax, rdx
0x14000136a  inc     rax
0x14000136d  cmp     [rcx+rax], dil
0x140001371  jnz     short loc_14000136A
0x140001373  inc     eax
0x140001375  jmp     short loc_14000137D
0x140001377  mov     rcx, rsi
0x14000137a  mov     eax, r8d
0x14000137d  mov     [rbp+90h+var_58], eax
0x140001380  mov     rax, [rbp+90h+arg_88]
0x140001387  mov     [rbp+90h+var_70], rax
0x14000138b  mov     rax, [rbp+90h+arg_80]
0x140001392  mov     [rbp+90h+var_60], rcx
0x140001396  mov     [rbp+90h+var_54], edi
0x140001399  mov     [rbp+90h+var_68], 4
0x1400013a1  mov     rcx, [rax]
0x1400013a4  test    rcx, rcx
0x1400013a7  jz      short loc_1400013BE
0x1400013a9  mov     rax, rdx
0x1400013ac  inc     rax
0x1400013af  cmp     [rcx+rax*2], di
0x1400013b3  jnz     short loc_1400013AC
0x1400013b5  lea     eax, ds:2[rax*2]
0x1400013bc  jmp     short loc_1400013C8
0x1400013be  lea     rcx, qword_14001C2F8
0x1400013c5  mov     eax, r9d
0x1400013c8  mov     [rbp+90h+var_78], eax
0x1400013cb  mov     rax, [rbp+90h+arg_78]
0x1400013d2  mov     [rbp+90h+var_80], rcx
0x1400013d6  mov     [rbp+90h+var_74], edi
0x1400013d9  mov     rcx, [rax]
0x1400013dc  test    rcx, rcx
0x1400013df  jz      short loc_1400013F1
0x1400013e1  mov     rax, rdx
0x1400013e4  inc     rax
0x1400013e7  cmp     [rcx+rax], dil
0x1400013eb  jnz     short loc_1400013E4
0x1400013ed  inc     eax
0x1400013ef  jmp     short loc_1400013F7
0x1400013f1  mov     rcx, rsi
0x1400013f4  mov     eax, r8d
0x1400013f7  mov     [rbp+90h+var_88], eax
0x1400013fa  mov     rax, [rbp+90h+arg_70]
0x140001401  mov     [rbp+90h+var_A0], rax
0x140001405  mov     rax, [rbp+90h+arg_68]
0x14000140c  mov     [rbp+90h+var_90], rcx
0x140001410  mov     [rbp+90h+var_84], edi
0x140001413  mov     [rbp+90h+var_98], 4
0x14000141b  mov     rcx, [rax]
0x14000141e  test    rcx, rcx
0x140001421  jz      short loc_140001433
0x140001423  mov     rax, rdx
0x140001426  inc     rax
0x140001429  cmp     [rcx+rax], dil
0x14000142d  jnz     short loc_140001426
0x14000142f  inc     eax
0x140001431  jmp     short loc_140001439
0x140001433  mov     rcx, rsi
0x140001436  mov     eax, r8d
0x140001439  mov     [rbp+90h+var_A8], eax
0x14000143c  mov     rax, [rbp+90h+arg_60]
0x140001443  mov     [rbp+90h+var_C0], rax
0x140001447  mov     rax, [rbp+90h+arg_58]
0x14000144e  mov     [rbp+90h+var_B0], rcx
0x140001452  mov     [rbp+90h+var_A4], edi
0x140001455  mov     [rbp+90h+var_B8], 4
0x14000145d  mov     rcx, [rax]
0x140001460  test    rcx, rcx
0x140001463  jz      short loc_14000147B
0x140001465  mov     rax, rdx
0x140001468  inc     rax
0x14000146b  cmp     [rcx+rax*2], di
0x14000146f  jnz     short loc_140001468
0x140001471  lea     r9d, ds:2[rax*2]
0x140001479  jmp     short loc_140001482
0x14000147b  lea     rcx, qword_14001C2F8
0x140001482  mov     rax, [rbp+90h+arg_50]
0x140001489  mov     [rbp+90h+var_E0], rax
0x14000148d  mov     rax, [rbp+90h+arg_48]
0x140001494  mov     [rbp+90h+var_D0], rcx
0x140001498  mov     [rbp+90h+var_C8], r9d
0x14000149c  mov     [rbp+90h+var_C4], edi
0x14000149f  mov     rcx, [rax]
0x1400014a2  mov     [rbp+90h+var_D8], 4
0x1400014aa  test    rcx, rcx
0x1400014ad  jz      short loc_1400014BF
0x1400014af  mov     rax, rdx
0x1400014b2  inc     rax
0x1400014b5  cmp     [rcx+rax], dil
0x1400014b9  jnz     short loc_1400014B2
0x1400014bb  inc     eax
0x1400014bd  jmp     short loc_1400014C5
0x1400014bf  mov     rcx, rsi
0x1400014c2  mov     eax, r8d
0x1400014c5  mov     [rbp+90h+var_E8], eax
0x1400014c8  mov     rax, [rbp+90h+arg_40]
0x1400014cf  mov     [rbp+90h+var_100], rax
0x1400014d3  mov     rax, [rbp+90h+arg_38]
0x1400014da  mov     [rbp+90h+var_F0], rcx
0x1400014de  mov     [rbp+90h+var_E4], edi
0x1400014e1  mov     [rbp+90h+var_F8], 4
0x1400014e9  mov     rcx, [rax]
0x1400014ec  test    rcx, rcx
0x1400014ef  jz      short loc_140001500
0x1400014f1  inc     rdx
0x1400014f4  cmp     [rcx+rdx], dil
0x1400014f8  jnz     short loc_1400014F1
0x1400014fa  lea     r8d, [rdx+1]
0x1400014fe  jmp     short loc_140001503
0x140001500  mov     rcx, rsi
0x140001503  mov     rax, [rbp+90h+arg_30]
0x14000150a  xor     r9d, r9d
0x14000150d  mov     [rsp+190h+var_120], rax
0x140001512  mov     rdx, r11
0x140001515  mov     rax, [rbp+90h+arg_28]
0x14000151c  mov     [rsp+190h+var_130], rax
0x140001521  mov     rax, [rbp+90h+arg_20]
0x140001528  mov     [rsp+190h+var_140], rax
0x14000152d  lea     rax, [rsp+190h+var_160]
0x140001532  mov     [rbp+90h+var_110], rcx
0x140001536  mov     rcx, r10
0x140001539  mov     [rbp+90h+var_108], r8d
0x14000153d  mov     r8, rbx
0x140001540  mov     [rsp+190h+var_168], rax
0x140001545  mov     [rsp+190h+var_170], 13h
0x14000154d  mov     [rbp+90h+var_104], edi
0x140001550  mov     [rsp+190h+var_118], 4
0x140001559  mov     [rsp+190h+var_128], 8
0x140001562  mov     [rsp+190h+var_138], 8
0x14000156b  call    _tlgWriteTransfer_EventWriteTransfer
0x140001570  mov     rcx, [rbp+90h+var_30]
0x140001574  xor     rcx, rsp; StackCookie
0x140001577  call    __security_check_cookie
0x14000157c  add     rsp, 170h
0x140001583  pop     r15
0x140001585  pop     rdi
0x140001586  pop     rsi
0x140001587  pop     rbx
0x140001588  pop     rbp
0x140001589  retn
```
