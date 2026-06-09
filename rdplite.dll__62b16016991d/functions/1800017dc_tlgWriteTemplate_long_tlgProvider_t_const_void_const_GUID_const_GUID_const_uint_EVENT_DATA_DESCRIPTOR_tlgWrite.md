# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)

- ea: `0x1800017dc`
- end: `0x180001a87`
- name: `??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456@Z`
- size: `683`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18000bc18`

## callees

- `0x180001448`
- `0x1800017dc`
- `0x1800036f0`

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
  __int64 v22; // rcx
  int v23; // r9d
  __int64 *v24; // rdx
  __int64 v25; // rax
  int v26; // eax
  int v27; // r8d
  const unsigned __int16 *v28; // rdx
  __int64 v29; // rax
  int v30; // eax
  __int64 *v31; // rdx
  __int64 v32; // rax
  int v33; // eax
  const unsigned __int16 *v34; // rdx
  __int64 v35; // rax
  int v36; // eax
  const unsigned __int16 *v37; // rdx
  __int64 v38; // rax
  int v39; // eax
  __int64 *v40; // rdx
  __int64 v41; // rax
  const unsigned __int16 *v42; // rdx
  __int64 v43; // rax
  int v44; // eax
  const unsigned __int16 *v45; // rdx
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
  __int64 *v64; // [rsp+C0h] [rbp-40h]
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
  __int64 *v77; // [rsp+110h] [rbp+10h]
  int v78; // [rsp+118h] [rbp+18h]
  int v79; // [rsp+11Ch] [rbp+1Ch]
  __int64 v80; // [rsp+120h] [rbp+20h]
  __int64 v81; // [rsp+128h] [rbp+28h]
  const unsigned __int16 *v82; // [rsp+130h] [rbp+30h]
  int v83; // [rsp+138h] [rbp+38h]
  int v84; // [rsp+13Ch] [rbp+3Ch]
  __int64 *v85; // [rsp+140h] [rbp+40h]
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
    v24 = &qword_18002E230;
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
    v28 = &qword_18002D6C0;
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
    v31 = &qword_18002E230;
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
    v34 = &qword_18002D6C0;
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
    v37 = &qword_18002D6C0;
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
    v40 = &qword_18002E230;
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
    v42 = &qword_18002D6C0;
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
    v45 = &qword_18002D6C0;
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
  return tlgWriteTransfer_EventWriteTransfer(a1, a2, 0, 0, 0x12u, &v47);
}

```

## disassembly

```asm
0x1800017dc  mov     [rsp-8+arg_10], rbx
0x1800017e1  push    rbp
0x1800017e2  push    rsi
0x1800017e3  push    rdi
0x1800017e4  lea     rbp, [rsp-60h]
0x1800017e9  sub     rsp, 160h
0x1800017f0  mov     rax, cs:__security_cookie
0x1800017f7  xor     rax, rsp
0x1800017fa  mov     [rbp+70h+var_20], rax
0x1800017fe  mov     rax, [rbp+70h+arg_98]
0x180001805  mov     r11, rdx
0x180001808  mov     r10, rcx
0x18000180b  xor     ebx, ebx
0x18000180d  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180001811  mov     r9d, 2
0x180001817  mov     rdx, [rax]
0x18000181a  test    rdx, rdx
0x18000181d  jz      short loc_180001834
0x18000181f  mov     rax, rcx
0x180001822  inc     rax
0x180001825  cmp     [rdx+rax*2], bx
0x180001829  jnz     short loc_180001822
0x18000182b  lea     eax, ds:2[rax*2]
0x180001832  jmp     short loc_18000183E
0x180001834  lea     rdx, qword_18002E230
0x18000183b  mov     eax, r9d
0x18000183e  mov     [rbp+70h+var_28], eax
0x180001841  lea     rdi, qword_18002D6C0
0x180001848  mov     rax, [rbp+70h+arg_90]
0x18000184f  mov     r8d, 1
0x180001855  mov     [rbp+70h+var_30], rdx
0x180001859  mov     [rbp+70h+var_24], ebx
0x18000185c  mov     rdx, [rax]
0x18000185f  test    rdx, rdx
0x180001862  jz      short loc_180001873
0x180001864  mov     rax, rcx
0x180001867  inc     rax
0x18000186a  cmp     [rdx+rax], bl
0x18000186d  jnz     short loc_180001867
0x18000186f  inc     eax
0x180001871  jmp     short loc_180001879
0x180001873  mov     rdx, rdi
0x180001876  mov     eax, r8d
0x180001879  mov     [rbp+70h+var_38], eax
0x18000187c  mov     rax, [rbp+70h+arg_88]
0x180001883  mov     [rbp+70h+var_50], rax
0x180001887  mov     rax, [rbp+70h+arg_80]
0x18000188e  mov     [rbp+70h+var_40], rdx
0x180001892  mov     [rbp+70h+var_34], ebx
0x180001895  mov     [rbp+70h+var_48], 4
0x18000189d  mov     rdx, [rax]
0x1800018a0  test    rdx, rdx
0x1800018a3  jz      short loc_1800018BA
0x1800018a5  mov     rax, rcx
0x1800018a8  inc     rax
0x1800018ab  cmp     [rdx+rax*2], bx
0x1800018af  jnz     short loc_1800018A8
0x1800018b1  lea     eax, ds:2[rax*2]
0x1800018b8  jmp     short loc_1800018C4
0x1800018ba  lea     rdx, qword_18002E230
0x1800018c1  mov     eax, r9d
0x1800018c4  mov     [rbp+70h+var_58], eax
0x1800018c7  mov     rax, [rbp+70h+arg_78]
0x1800018ce  mov     [rbp+70h+var_60], rdx
0x1800018d2  mov     [rbp+70h+var_54], ebx
0x1800018d5  mov     rdx, [rax]
0x1800018d8  test    rdx, rdx
0x1800018db  jz      short loc_1800018EC
0x1800018dd  mov     rax, rcx
0x1800018e0  inc     rax
0x1800018e3  cmp     [rdx+rax], bl
0x1800018e6  jnz     short loc_1800018E0
0x1800018e8  inc     eax
0x1800018ea  jmp     short loc_1800018F2
0x1800018ec  mov     rdx, rdi
0x1800018ef  mov     eax, r8d
0x1800018f2  mov     [rbp+70h+var_68], eax
0x1800018f5  mov     rax, [rbp+70h+arg_70]
0x1800018fc  mov     [rbp+70h+var_80], rax
0x180001900  mov     rax, [rbp+70h+arg_68]
0x180001907  mov     [rbp+70h+var_70], rdx
0x18000190b  mov     [rbp+70h+var_64], ebx
0x18000190e  mov     [rbp+70h+var_78], 4
0x180001916  mov     rdx, [rax]
0x180001919  test    rdx, rdx
0x18000191c  jz      short loc_18000192D
0x18000191e  mov     rax, rcx
0x180001921  inc     rax
0x180001924  cmp     [rdx+rax], bl
0x180001927  jnz     short loc_180001921
0x180001929  inc     eax
0x18000192b  jmp     short loc_180001933
0x18000192d  mov     rdx, rdi
0x180001930  mov     eax, r8d
0x180001933  mov     [rbp+70h+var_88], eax
0x180001936  mov     rax, [rbp+70h+arg_60]
0x18000193d  mov     [rbp+70h+var_A0], rax
0x180001941  mov     rax, [rbp+70h+arg_58]
0x180001948  mov     [rbp+70h+var_90], rdx
0x18000194c  mov     [rbp+70h+var_84], ebx
0x18000194f  mov     [rbp+70h+var_98], 4
0x180001957  mov     rdx, [rax]
0x18000195a  test    rdx, rdx
0x18000195d  jz      short loc_180001975
0x18000195f  mov     rax, rcx
0x180001962  inc     rax
0x180001965  cmp     [rdx+rax*2], bx
0x180001969  jnz     short loc_180001962
0x18000196b  lea     r9d, ds:2[rax*2]
0x180001973  jmp     short loc_18000197C
0x180001975  lea     rdx, qword_18002E230
0x18000197c  mov     rax, [rbp+70h+arg_50]
0x180001983  mov     [rbp+70h+var_C0], rax
0x180001987  mov     rax, [rbp+70h+arg_48]
0x18000198e  mov     [rbp+70h+var_B0], rdx
0x180001992  mov     [rbp+70h+var_A8], r9d
0x180001996  mov     [rbp+70h+var_A4], ebx
0x180001999  mov     rdx, [rax]
0x18000199c  mov     [rbp+70h+var_B8], 4
0x1800019a4  test    rdx, rdx
0x1800019a7  jz      short loc_1800019B8
0x1800019a9  mov     rax, rcx
0x1800019ac  inc     rax
0x1800019af  cmp     [rdx+rax], bl
0x1800019b2  jnz     short loc_1800019AC
0x1800019b4  inc     eax
0x1800019b6  jmp     short loc_1800019BE
0x1800019b8  mov     rdx, rdi
0x1800019bb  mov     eax, r8d
0x1800019be  mov     [rbp+70h+var_C8], eax
0x1800019c1  mov     rax, [rbp+70h+arg_40]
0x1800019c8  mov     [rbp+70h+var_E0], rax
0x1800019cc  mov     rax, [rbp+70h+arg_38]
0x1800019d3  mov     [rbp+70h+var_D0], rdx
0x1800019d7  mov     [rbp+70h+var_C4], ebx
0x1800019da  mov     [rbp+70h+var_D8], 4
0x1800019e2  mov     rdx, [rax]
0x1800019e5  test    rdx, rdx
0x1800019e8  jz      short loc_1800019F8
0x1800019ea  inc     rcx
0x1800019ed  cmp     [rdx+rcx], bl
0x1800019f0  jnz     short loc_1800019EA
0x1800019f2  lea     r8d, [rcx+1]
0x1800019f6  jmp     short loc_1800019FB
0x1800019f8  mov     rdx, rdi
0x1800019fb  mov     rax, [rbp+70h+arg_30]
0x180001a02  xor     r9d, r9d
0x180001a05  mov     [rsp+170h+var_100], rax
0x180001a0a  mov     rcx, r10
0x180001a0d  mov     rax, [rbp+70h+arg_28]
0x180001a14  mov     [rsp+170h+var_110], rax
0x180001a19  mov     rax, [rbp+70h+arg_20]
0x180001a20  mov     [rsp+170h+var_120], rax
0x180001a25  lea     rax, [rsp+170h+var_140]
0x180001a2a  mov     [rbp+70h+var_F0], rdx
0x180001a2e  mov     rdx, r11
0x180001a31  mov     [rbp+70h+var_E8], r8d
0x180001a35  xor     r8d, r8d
0x180001a38  mov     [rsp+170h+var_148], rax
0x180001a3d  mov     [rsp+170h+var_150], 12h
0x180001a45  mov     [rbp+70h+var_E4], ebx
0x180001a48  mov     [rsp+170h+var_F8], 4
0x180001a51  mov     [rsp+170h+var_108], 8
0x180001a5a  mov     [rsp+170h+var_118], 8
0x180001a63  call    _tlgWriteTransfer_EventWriteTransfer
0x180001a68  mov     rcx, [rbp+70h+var_20]
0x180001a6c  xor     rcx, rsp; StackCookie
0x180001a6f  call    __security_check_cookie
0x180001a74  mov     rbx, [rsp+170h+arg_10]
0x180001a7c  add     rsp, 160h
0x180001a83  pop     rdi
0x180001a84  pop     rsi
0x180001a85  pop     rbp
0x180001a86  retn
```
