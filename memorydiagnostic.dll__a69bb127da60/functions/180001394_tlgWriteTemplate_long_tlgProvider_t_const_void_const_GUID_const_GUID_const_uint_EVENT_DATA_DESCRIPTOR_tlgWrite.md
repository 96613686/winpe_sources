# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)

- ea: `0x180001394`
- end: `0x18000163f`
- name: `??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456@Z`
- size: `683`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, __int64, __int64, __int64, const unsigned __int16 **, __int64, const unsigned __int16 **, __int64, int **, __int64, const unsigned __int16 **, __int64, const unsigned __int16 **, int **, __int64, const unsigned __int16 **, int **)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1800101e8`

## callees

- `0x180001394`
- `0x180001a7c`
- `0x180002e50`

## pseudocode

```c
__int64 __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
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
        int **a20)
{
  __int64 v22; // rcx
  int v23; // r9d
  int *v24; // rdx
  __int64 v25; // rax
  int v26; // eax
  int v27; // r8d
  const unsigned __int16 *v28; // rdx
  __int64 v29; // rax
  int v30; // eax
  int *v31; // rdx
  __int64 v32; // rax
  int v33; // eax
  const unsigned __int16 *v34; // rdx
  __int64 v35; // rax
  int v36; // eax
  const unsigned __int16 *v37; // rdx
  __int64 v38; // rax
  int v39; // eax
  int *v40; // rdx
  __int64 v41; // rax
  const unsigned __int16 *v42; // rdx
  __int64 v43; // rax
  int v44; // eax
  const unsigned __int16 *v45; // rdx
  _BYTE v47[32]; // [rsp+30h] [rbp-D0h] BYREF
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
  int *v64; // [rsp+C0h] [rbp-40h]
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
  int *v77; // [rsp+110h] [rbp+10h]
  int v78; // [rsp+118h] [rbp+18h]
  int v79; // [rsp+11Ch] [rbp+1Ch]
  __int64 v80; // [rsp+120h] [rbp+20h]
  __int64 v81; // [rsp+128h] [rbp+28h]
  const unsigned __int16 *v82; // [rsp+130h] [rbp+30h]
  int v83; // [rsp+138h] [rbp+38h]
  int v84; // [rsp+13Ch] [rbp+3Ch]
  int *v85; // [rsp+140h] [rbp+40h]
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
    while ( *((_WORD *)v24 + v25) );
    v26 = 2 * v25 + 2;
  }
  else
  {
    v24 = &dword_180025214;
    v26 = 2;
  }
  v86 = v26;
  v27 = 1;
  v85 = v24;
  v87 = 0;
  v28 = *a19;
  if ( *a19 )
  {
    v29 = -1;
    do
      ++v29;
    while ( *((_BYTE *)v28 + v29) );
    v30 = v29 + 1;
  }
  else
  {
    v28 = &byte_180025210;
    v30 = 1;
  }
  v83 = v30;
  v80 = a18;
  v82 = v28;
  v84 = 0;
  v81 = 4;
  v31 = *a17;
  if ( *a17 )
  {
    v32 = -1;
    do
      ++v32;
    while ( *((_WORD *)v31 + v32) );
    v33 = 2 * v32 + 2;
  }
  else
  {
    v31 = &dword_180025214;
    v33 = 2;
  }
  v78 = v33;
  v77 = v31;
  v79 = 0;
  v34 = *a16;
  if ( *a16 )
  {
    v35 = -1;
    do
      ++v35;
    while ( *((_BYTE *)v34 + v35) );
    v36 = v35 + 1;
  }
  else
  {
    v34 = &byte_180025210;
    v36 = 1;
  }
  v75 = v36;
  v72 = a15;
  v74 = v34;
  v76 = 0;
  v73 = 4;
  v37 = *a14;
  if ( *a14 )
  {
    v38 = -1;
    do
      ++v38;
    while ( *((_BYTE *)v37 + v38) );
    v39 = v38 + 1;
  }
  else
  {
    v37 = &byte_180025210;
    v39 = 1;
  }
  v70 = v39;
  v67 = a13;
  v69 = v37;
  v71 = 0;
  v68 = 4;
  v40 = *a12;
  if ( *a12 )
  {
    v41 = -1;
    do
      ++v41;
    while ( *((_WORD *)v40 + v41) );
    v23 = 2 * v41 + 2;
  }
  else
  {
    v40 = &dword_180025214;
  }
  v62 = a11;
  v64 = v40;
  v65 = v23;
  v66 = 0;
  v42 = *a10;
  v63 = 4;
  if ( v42 )
  {
    v43 = -1;
    do
      ++v43;
    while ( *((_BYTE *)v42 + v43) );
    v44 = v43 + 1;
  }
  else
  {
    v42 = &byte_180025210;
    v44 = 1;
  }
  v60 = v44;
  v57 = a9;
  v59 = v42;
  v61 = 0;
  v58 = 4;
  v45 = *a8;
  if ( *a8 )
  {
    do
      ++v22;
    while ( *((_BYTE *)v45 + v22) );
    v27 = v22 + 1;
  }
  else
  {
    v45 = &byte_180025210;
  }
  v52 = a7;
  v50 = a6;
  v48 = a5;
  v54 = v45;
  v55 = v27;
  v56 = 0;
  v53 = 4;
  v51 = 8;
  v49 = 8;
  return ((__int64 (__fastcall *)(__int64, __int64, _QWORD, _QWORD, int, _BYTE *))tlgWriteTransfer_EventWriteTransfer)(
           a1,
           a2,
           0,
           0,
           18,
           v47);
}

```

## disassembly

```asm
0x180001394  mov     [rsp-8+arg_10], rbx
0x180001399  push    rbp
0x18000139a  push    rsi
0x18000139b  push    rdi
0x18000139c  lea     rbp, [rsp-60h]
0x1800013a1  sub     rsp, 160h
0x1800013a8  mov     rax, cs:__security_cookie
0x1800013af  xor     rax, rsp
0x1800013b2  mov     [rbp+70h+var_20], rax
0x1800013b6  mov     rax, [rbp+70h+arg_98]
0x1800013bd  mov     r11, rdx
0x1800013c0  mov     r10, rcx
0x1800013c3  xor     ebx, ebx
0x1800013c5  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1800013c9  mov     r9d, 2
0x1800013cf  mov     rdx, [rax]
0x1800013d2  test    rdx, rdx
0x1800013d5  jz      short loc_1800013EC
0x1800013d7  mov     rax, rcx
0x1800013da  inc     rax
0x1800013dd  cmp     [rdx+rax*2], bx
0x1800013e1  jnz     short loc_1800013DA
0x1800013e3  lea     eax, ds:2[rax*2]
0x1800013ea  jmp     short loc_1800013F6
0x1800013ec  lea     rdx, dword_180025214
0x1800013f3  mov     eax, r9d
0x1800013f6  mov     [rbp+70h+var_28], eax
0x1800013f9  lea     rdi, byte_180025210
0x180001400  mov     rax, [rbp+70h+arg_90]
0x180001407  mov     r8d, 1
0x18000140d  mov     [rbp+70h+var_30], rdx
0x180001411  mov     [rbp+70h+var_24], ebx
0x180001414  mov     rdx, [rax]
0x180001417  test    rdx, rdx
0x18000141a  jz      short loc_18000142B
0x18000141c  mov     rax, rcx
0x18000141f  inc     rax
0x180001422  cmp     [rdx+rax], bl
0x180001425  jnz     short loc_18000141F
0x180001427  inc     eax
0x180001429  jmp     short loc_180001431
0x18000142b  mov     rdx, rdi
0x18000142e  mov     eax, r8d
0x180001431  mov     [rbp+70h+var_38], eax
0x180001434  mov     rax, [rbp+70h+arg_88]
0x18000143b  mov     [rbp+70h+var_50], rax
0x18000143f  mov     rax, [rbp+70h+arg_80]
0x180001446  mov     [rbp+70h+var_40], rdx
0x18000144a  mov     [rbp+70h+var_34], ebx
0x18000144d  mov     [rbp+70h+var_48], 4
0x180001455  mov     rdx, [rax]
0x180001458  test    rdx, rdx
0x18000145b  jz      short loc_180001472
0x18000145d  mov     rax, rcx
0x180001460  inc     rax
0x180001463  cmp     [rdx+rax*2], bx
0x180001467  jnz     short loc_180001460
0x180001469  lea     eax, ds:2[rax*2]
0x180001470  jmp     short loc_18000147C
0x180001472  lea     rdx, dword_180025214
0x180001479  mov     eax, r9d
0x18000147c  mov     [rbp+70h+var_58], eax
0x18000147f  mov     rax, [rbp+70h+arg_78]
0x180001486  mov     [rbp+70h+var_60], rdx
0x18000148a  mov     [rbp+70h+var_54], ebx
0x18000148d  mov     rdx, [rax]
0x180001490  test    rdx, rdx
0x180001493  jz      short loc_1800014A4
0x180001495  mov     rax, rcx
0x180001498  inc     rax
0x18000149b  cmp     [rdx+rax], bl
0x18000149e  jnz     short loc_180001498
0x1800014a0  inc     eax
0x1800014a2  jmp     short loc_1800014AA
0x1800014a4  mov     rdx, rdi
0x1800014a7  mov     eax, r8d
0x1800014aa  mov     [rbp+70h+var_68], eax
0x1800014ad  mov     rax, [rbp+70h+arg_70]
0x1800014b4  mov     [rbp+70h+var_80], rax
0x1800014b8  mov     rax, [rbp+70h+arg_68]
0x1800014bf  mov     [rbp+70h+var_70], rdx
0x1800014c3  mov     [rbp+70h+var_64], ebx
0x1800014c6  mov     [rbp+70h+var_78], 4
0x1800014ce  mov     rdx, [rax]
0x1800014d1  test    rdx, rdx
0x1800014d4  jz      short loc_1800014E5
0x1800014d6  mov     rax, rcx
0x1800014d9  inc     rax
0x1800014dc  cmp     [rdx+rax], bl
0x1800014df  jnz     short loc_1800014D9
0x1800014e1  inc     eax
0x1800014e3  jmp     short loc_1800014EB
0x1800014e5  mov     rdx, rdi
0x1800014e8  mov     eax, r8d
0x1800014eb  mov     [rbp+70h+var_88], eax
0x1800014ee  mov     rax, [rbp+70h+arg_60]
0x1800014f5  mov     [rbp+70h+var_A0], rax
0x1800014f9  mov     rax, [rbp+70h+arg_58]
0x180001500  mov     [rbp+70h+var_90], rdx
0x180001504  mov     [rbp+70h+var_84], ebx
0x180001507  mov     [rbp+70h+var_98], 4
0x18000150f  mov     rdx, [rax]
0x180001512  test    rdx, rdx
0x180001515  jz      short loc_18000152D
0x180001517  mov     rax, rcx
0x18000151a  inc     rax
0x18000151d  cmp     [rdx+rax*2], bx
0x180001521  jnz     short loc_18000151A
0x180001523  lea     r9d, ds:2[rax*2]
0x18000152b  jmp     short loc_180001534
0x18000152d  lea     rdx, dword_180025214
0x180001534  mov     rax, [rbp+70h+arg_50]
0x18000153b  mov     [rbp+70h+var_C0], rax
0x18000153f  mov     rax, [rbp+70h+arg_48]
0x180001546  mov     [rbp+70h+var_B0], rdx
0x18000154a  mov     [rbp+70h+var_A8], r9d
0x18000154e  mov     [rbp+70h+var_A4], ebx
0x180001551  mov     rdx, [rax]
0x180001554  mov     [rbp+70h+var_B8], 4
0x18000155c  test    rdx, rdx
0x18000155f  jz      short loc_180001570
0x180001561  mov     rax, rcx
0x180001564  inc     rax
0x180001567  cmp     [rdx+rax], bl
0x18000156a  jnz     short loc_180001564
0x18000156c  inc     eax
0x18000156e  jmp     short loc_180001576
0x180001570  mov     rdx, rdi
0x180001573  mov     eax, r8d
0x180001576  mov     [rbp+70h+var_C8], eax
0x180001579  mov     rax, [rbp+70h+arg_40]
0x180001580  mov     [rbp+70h+var_E0], rax
0x180001584  mov     rax, [rbp+70h+arg_38]
0x18000158b  mov     [rbp+70h+var_D0], rdx
0x18000158f  mov     [rbp+70h+var_C4], ebx
0x180001592  mov     [rbp+70h+var_D8], 4
0x18000159a  mov     rdx, [rax]
0x18000159d  test    rdx, rdx
0x1800015a0  jz      short loc_1800015B0
0x1800015a2  inc     rcx
0x1800015a5  cmp     [rdx+rcx], bl
0x1800015a8  jnz     short loc_1800015A2
0x1800015aa  lea     r8d, [rcx+1]
0x1800015ae  jmp     short loc_1800015B3
0x1800015b0  mov     rdx, rdi
0x1800015b3  mov     rax, [rbp+70h+arg_30]
0x1800015ba  xor     r9d, r9d
0x1800015bd  mov     [rsp+170h+var_100], rax
0x1800015c2  mov     rcx, r10
0x1800015c5  mov     rax, [rbp+70h+arg_28]
0x1800015cc  mov     [rsp+170h+var_110], rax
0x1800015d1  mov     rax, [rbp+70h+arg_20]
0x1800015d8  mov     [rsp+170h+var_120], rax
0x1800015dd  lea     rax, [rsp+170h+var_140]
0x1800015e2  mov     [rbp+70h+var_F0], rdx
0x1800015e6  mov     rdx, r11
0x1800015e9  mov     [rbp+70h+var_E8], r8d
0x1800015ed  xor     r8d, r8d
0x1800015f0  mov     [rsp+170h+var_148], rax
0x1800015f5  mov     [rsp+170h+var_150], 12h
0x1800015fd  mov     [rbp+70h+var_E4], ebx
0x180001600  mov     [rsp+170h+var_F8], 4
0x180001609  mov     [rsp+170h+var_108], 8
0x180001612  mov     [rsp+170h+var_118], 8
0x18000161b  call    _tlgWriteTransfer_EventWriteTransfer
0x180001620  mov     rcx, [rbp+70h+var_20]
0x180001624  xor     rcx, rsp; StackCookie
0x180001627  call    __security_check_cookie
0x18000162c  mov     rbx, [rsp+170h+arg_10]
0x180001634  add     rsp, 160h
0x18000163b  pop     rdi
0x18000163c  pop     rsi
0x18000163d  pop     rbp
0x18000163e  retn
```
