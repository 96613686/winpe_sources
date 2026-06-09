# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)

- ea: `0x180001398`
- end: `0x18000164a`
- name: `??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456@Z`
- size: `690`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180010c68`

## callees

- `0x180001398`
- `0x180001a8c`
- `0x1800026b0`

## pseudocode

```c
ULONG __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
        __int64 a1,
        unsigned __int8 *a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        __int64 a7,
        const unsigned __int16 **a8,
        __int64 a9,
        const unsigned __int16 **a10,
        __int64 a11,
        void **a12,
        __int64 a13,
        const unsigned __int16 **a14,
        __int64 a15,
        const unsigned __int16 **a16,
        void **a17,
        __int64 a18,
        const unsigned __int16 **a19,
        void **a20)
{
  __int64 v22; // rcx
  int v23; // r9d
  _WORD *v24; // rdx
  __int64 v25; // rax
  int v26; // eax
  const unsigned __int16 *v27; // r8
  __int64 v28; // rax
  int v29; // eax
  _WORD *v30; // r8
  __int64 v31; // rax
  int v32; // eax
  const unsigned __int16 *v33; // r8
  __int64 v34; // rax
  int v35; // eax
  const unsigned __int16 *v36; // r8
  __int64 v37; // rax
  int v38; // eax
  _WORD *v39; // r8
  __int64 v40; // rax
  const unsigned __int16 *v41; // r8
  __int64 v42; // rax
  int v43; // eax
  const unsigned __int16 *v44; // r8
  int v45; // ecx
  struct _EVENT_DATA_DESCRIPTOR v47; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v48; // [rsp+50h] [rbp-B0h]
  __int64 v49; // [rsp+58h] [rbp-A8h]
  __int64 v50; // [rsp+60h] [rbp-A0h]
  __int64 v51; // [rsp+68h] [rbp-98h]
  __int64 v52; // [rsp+70h] [rbp-90h]
  __int64 v53; // [rsp+78h] [rbp-88h]
  const unsigned __int16 *v54; // [rsp+80h] [rbp-80h]
  int v55; // [rsp+88h] [rbp-78h]
  int v56; // [rsp+8Ch] [rbp-74h]
  __int64 v57; // [rsp+90h] [rbp-70h]
  __int64 v58; // [rsp+98h] [rbp-68h]
  const unsigned __int16 *v59; // [rsp+A0h] [rbp-60h]
  int v60; // [rsp+A8h] [rbp-58h]
  int v61; // [rsp+ACh] [rbp-54h]
  __int64 v62; // [rsp+B0h] [rbp-50h]
  __int64 v63; // [rsp+B8h] [rbp-48h]
  _WORD *v64; // [rsp+C0h] [rbp-40h]
  int v65; // [rsp+C8h] [rbp-38h]
  int v66; // [rsp+CCh] [rbp-34h]
  __int64 v67; // [rsp+D0h] [rbp-30h]
  __int64 v68; // [rsp+D8h] [rbp-28h]
  const unsigned __int16 *v69; // [rsp+E0h] [rbp-20h]
  int v70; // [rsp+E8h] [rbp-18h]
  int v71; // [rsp+ECh] [rbp-14h]
  __int64 v72; // [rsp+F0h] [rbp-10h]
  __int64 v73; // [rsp+F8h] [rbp-8h]
  const unsigned __int16 *v74; // [rsp+100h] [rbp+0h]
  int v75; // [rsp+108h] [rbp+8h]
  int v76; // [rsp+10Ch] [rbp+Ch]
  _WORD *v77; // [rsp+110h] [rbp+10h]
  int v78; // [rsp+118h] [rbp+18h]
  int v79; // [rsp+11Ch] [rbp+1Ch]
  __int64 v80; // [rsp+120h] [rbp+20h]
  __int64 v81; // [rsp+128h] [rbp+28h]
  const unsigned __int16 *v82; // [rsp+130h] [rbp+30h]
  int v83; // [rsp+138h] [rbp+38h]
  int v84; // [rsp+13Ch] [rbp+3Ch]
  _WORD *v85; // [rsp+140h] [rbp+40h]
  int v86; // [rsp+148h] [rbp+48h]
  int v87; // [rsp+14Ch] [rbp+4Ch]

  v22 = -1;
  v23 = 2;
  v24 = *a20;
  if ( *a20 )
  {
    v25 = -1;
    do
      ++v25;
    while ( v24[v25] );
    v26 = 2 * v25 + 2;
  }
  else
  {
    v24 = &unk_1800261C4;
    v26 = 2;
  }
  v86 = v26;
  v85 = v24;
  v87 = 0;
  v27 = *a19;
  if ( *a19 )
  {
    v28 = -1;
    do
      ++v28;
    while ( *((_BYTE *)v27 + v28) );
    v29 = v28 + 1;
  }
  else
  {
    v27 = &word_1800261C0;
    v29 = 1;
  }
  v83 = v29;
  v80 = a18;
  v82 = v27;
  v84 = 0;
  v81 = 4;
  v30 = *a17;
  if ( *a17 )
  {
    v31 = -1;
    do
      ++v31;
    while ( v30[v31] );
    v32 = 2 * v31 + 2;
  }
  else
  {
    v30 = &unk_1800261C4;
    v32 = 2;
  }
  v78 = v32;
  v77 = v30;
  v79 = 0;
  v33 = *a16;
  if ( *a16 )
  {
    v34 = -1;
    do
      ++v34;
    while ( *((_BYTE *)v33 + v34) );
    v35 = v34 + 1;
  }
  else
  {
    v33 = &word_1800261C0;
    v35 = 1;
  }
  v75 = v35;
  v72 = a15;
  v74 = v33;
  v76 = 0;
  v73 = 4;
  v36 = *a14;
  if ( *a14 )
  {
    v37 = -1;
    do
      ++v37;
    while ( *((_BYTE *)v36 + v37) );
    v38 = v37 + 1;
  }
  else
  {
    v36 = &word_1800261C0;
    v38 = 1;
  }
  v70 = v38;
  v67 = a13;
  v69 = v36;
  v71 = 0;
  v68 = 4;
  v39 = *a12;
  if ( *a12 )
  {
    v40 = -1;
    do
      ++v40;
    while ( v39[v40] );
    v23 = 2 * v40 + 2;
  }
  else
  {
    v39 = &unk_1800261C4;
  }
  v62 = a11;
  v64 = v39;
  v65 = v23;
  v66 = 0;
  v41 = *a10;
  v63 = 4;
  if ( v41 )
  {
    v42 = -1;
    do
      ++v42;
    while ( *((_BYTE *)v41 + v42) );
    v43 = v42 + 1;
  }
  else
  {
    v41 = &word_1800261C0;
    v43 = 1;
  }
  v60 = v43;
  v57 = a9;
  v59 = v41;
  v61 = 0;
  v58 = 4;
  v44 = *a8;
  if ( *a8 )
  {
    do
      ++v22;
    while ( *((_BYTE *)v44 + v22) );
    v45 = v22 + 1;
  }
  else
  {
    v44 = &word_1800261C0;
    v45 = 1;
  }
  v52 = a7;
  v50 = a6;
  v48 = a5;
  v54 = v44;
  v55 = v45;
  v56 = 0;
  v53 = 4;
  v51 = 8;
  v49 = 8;
  return tlgWriteTransfer_EventWriteTransfer(a1, a2, 0, 0, 0x12u, &v47);
}

```

## disassembly

```asm
0x180001398  mov     [rsp-8+arg_10], rbx
0x18000139d  push    rbp
0x18000139e  push    rsi
0x18000139f  push    rdi
0x1800013a0  lea     rbp, [rsp-60h]
0x1800013a5  sub     rsp, 160h
0x1800013ac  mov     rax, cs:__security_cookie
0x1800013b3  xor     rax, rsp
0x1800013b6  mov     [rbp+70h+var_20], rax
0x1800013ba  mov     rax, [rbp+70h+arg_98]
0x1800013c1  mov     r11, rdx
0x1800013c4  mov     r10, rcx
0x1800013c7  xor     ebx, ebx
0x1800013c9  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1800013cd  mov     r9d, 2
0x1800013d3  mov     rdx, [rax]
0x1800013d6  test    rdx, rdx
0x1800013d9  jz      short loc_1800013F0
0x1800013db  mov     rax, rcx
0x1800013de  inc     rax
0x1800013e1  cmp     [rdx+rax*2], bx
0x1800013e5  jnz     short loc_1800013DE
0x1800013e7  lea     eax, ds:2[rax*2]
0x1800013ee  jmp     short loc_1800013FA
0x1800013f0  lea     rdx, unk_1800261C4
0x1800013f7  mov     eax, r9d
0x1800013fa  mov     [rbp+70h+var_28], eax
0x1800013fd  lea     rdi, word_1800261C0
0x180001404  mov     rax, [rbp+70h+arg_90]
0x18000140b  mov     [rbp+70h+var_30], rdx
0x18000140f  mov     [rbp+70h+var_24], ebx
0x180001412  mov     r8, [rax]
0x180001415  test    r8, r8
0x180001418  jz      short loc_18000142F
0x18000141a  mov     rax, rcx
0x18000141d  inc     rax
0x180001420  cmp     [r8+rax], bl
0x180001424  jnz     short loc_18000141D
0x180001426  mov     edx, 1
0x18000142b  add     eax, edx
0x18000142d  jmp     short loc_180001439
0x18000142f  mov     edx, 1
0x180001434  mov     r8, rdi
0x180001437  mov     eax, edx
0x180001439  mov     [rbp+70h+var_38], eax
0x18000143c  mov     rax, [rbp+70h+arg_88]
0x180001443  mov     [rbp+70h+var_50], rax
0x180001447  mov     rax, [rbp+70h+arg_80]
0x18000144e  mov     [rbp+70h+var_40], r8
0x180001452  mov     [rbp+70h+var_34], ebx
0x180001455  mov     [rbp+70h+var_48], 4
0x18000145d  mov     r8, [rax]
0x180001460  test    r8, r8
0x180001463  jz      short loc_18000147B
0x180001465  mov     rax, rcx
0x180001468  inc     rax
0x18000146b  cmp     [r8+rax*2], bx
0x180001470  jnz     short loc_180001468
0x180001472  lea     eax, ds:2[rax*2]
0x180001479  jmp     short loc_180001485
0x18000147b  lea     r8, unk_1800261C4
0x180001482  mov     eax, r9d
0x180001485  mov     [rbp+70h+var_58], eax
0x180001488  mov     rax, [rbp+70h+arg_78]
0x18000148f  mov     [rbp+70h+var_60], r8
0x180001493  mov     [rbp+70h+var_54], ebx
0x180001496  mov     r8, [rax]
0x180001499  test    r8, r8
0x18000149c  jz      short loc_1800014AE
0x18000149e  mov     rax, rcx
0x1800014a1  inc     rax
0x1800014a4  cmp     [r8+rax], bl
0x1800014a8  jnz     short loc_1800014A1
0x1800014aa  add     eax, edx
0x1800014ac  jmp     short loc_1800014B3
0x1800014ae  mov     r8, rdi
0x1800014b1  mov     eax, edx
0x1800014b3  mov     [rbp+70h+var_68], eax
0x1800014b6  mov     rax, [rbp+70h+arg_70]
0x1800014bd  mov     [rbp+70h+var_80], rax
0x1800014c1  mov     rax, [rbp+70h+arg_68]
0x1800014c8  mov     [rbp+70h+var_70], r8
0x1800014cc  mov     [rbp+70h+var_64], ebx
0x1800014cf  mov     [rbp+70h+var_78], 4
0x1800014d7  mov     r8, [rax]
0x1800014da  test    r8, r8
0x1800014dd  jz      short loc_1800014EF
0x1800014df  mov     rax, rcx
0x1800014e2  inc     rax
0x1800014e5  cmp     [r8+rax], bl
0x1800014e9  jnz     short loc_1800014E2
0x1800014eb  add     eax, edx
0x1800014ed  jmp     short loc_1800014F4
0x1800014ef  mov     r8, rdi
0x1800014f2  mov     eax, edx
0x1800014f4  mov     [rbp+70h+var_88], eax
0x1800014f7  mov     rax, [rbp+70h+arg_60]
0x1800014fe  mov     [rbp+70h+var_A0], rax
0x180001502  mov     rax, [rbp+70h+arg_58]
0x180001509  mov     [rbp+70h+var_90], r8
0x18000150d  mov     [rbp+70h+var_84], ebx
0x180001510  mov     [rbp+70h+var_98], 4
0x180001518  mov     r8, [rax]
0x18000151b  test    r8, r8
0x18000151e  jz      short loc_180001537
0x180001520  mov     rax, rcx
0x180001523  inc     rax
0x180001526  cmp     [r8+rax*2], bx
0x18000152b  jnz     short loc_180001523
0x18000152d  lea     r9d, ds:2[rax*2]
0x180001535  jmp     short loc_18000153E
0x180001537  lea     r8, unk_1800261C4
0x18000153e  mov     rax, [rbp+70h+arg_50]
0x180001545  mov     [rbp+70h+var_C0], rax
0x180001549  mov     rax, [rbp+70h+arg_48]
0x180001550  mov     [rbp+70h+var_B0], r8
0x180001554  mov     [rbp+70h+var_A8], r9d
0x180001558  mov     [rbp+70h+var_A4], ebx
0x18000155b  mov     r8, [rax]
0x18000155e  mov     [rbp+70h+var_B8], 4
0x180001566  test    r8, r8
0x180001569  jz      short loc_18000157B
0x18000156b  mov     rax, rcx
0x18000156e  inc     rax
0x180001571  cmp     [r8+rax], bl
0x180001575  jnz     short loc_18000156E
0x180001577  add     eax, edx
0x180001579  jmp     short loc_180001580
0x18000157b  mov     r8, rdi
0x18000157e  mov     eax, edx
0x180001580  mov     [rbp+70h+var_C8], eax
0x180001583  mov     rax, [rbp+70h+arg_40]
0x18000158a  mov     [rbp+70h+var_E0], rax
0x18000158e  mov     rax, [rbp+70h+arg_38]
0x180001595  mov     [rbp+70h+var_D0], r8
0x180001599  mov     [rbp+70h+var_C4], ebx
0x18000159c  mov     [rbp+70h+var_D8], 4
0x1800015a4  mov     r8, [rax]
0x1800015a7  test    r8, r8
0x1800015aa  jz      short loc_1800015B9
0x1800015ac  inc     rcx
0x1800015af  cmp     [r8+rcx], bl
0x1800015b3  jnz     short loc_1800015AC
0x1800015b5  add     ecx, edx
0x1800015b7  jmp     short loc_1800015BE
0x1800015b9  mov     r8, rdi
0x1800015bc  mov     ecx, edx
0x1800015be  mov     rax, [rbp+70h+arg_30]
0x1800015c5  xor     r9d, r9d
0x1800015c8  mov     [rsp+170h+var_100], rax
0x1800015cd  mov     rdx, r11
0x1800015d0  mov     rax, [rbp+70h+arg_28]
0x1800015d7  mov     [rsp+170h+var_110], rax
0x1800015dc  mov     rax, [rbp+70h+arg_20]
0x1800015e3  mov     [rsp+170h+var_120], rax
0x1800015e8  lea     rax, [rsp+170h+var_140]
0x1800015ed  mov     [rbp+70h+var_F0], r8
0x1800015f1  xor     r8d, r8d
0x1800015f4  mov     [rbp+70h+var_E8], ecx
0x1800015f7  mov     rcx, r10
0x1800015fa  mov     [rsp+170h+var_148], rax
0x1800015ff  mov     [rsp+170h+var_150], 12h
0x180001607  mov     [rbp+70h+var_E4], ebx
0x18000160a  mov     [rsp+170h+var_F8], 4
0x180001613  mov     [rsp+170h+var_108], 8
0x18000161c  mov     [rsp+170h+var_118], 8
0x180001625  call    _tlgWriteTransfer_EventWriteTransfer
0x18000162a  mov     rcx, [rbp+70h+var_20]
0x18000162e  xor     rcx, rsp; StackCookie
0x180001631  call    __security_check_cookie
0x180001636  mov     rbx, [rsp+170h+arg_10]
0x18000163e  add     rsp, 160h
0x180001645  pop     rdi
0x180001646  pop     rsi
0x180001647  pop     rbp
0x180001648  retn
```
