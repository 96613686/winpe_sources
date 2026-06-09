# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)

- ea: `0x180001650`
- end: `0x180001947`
- name: `??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456445@Z`
- size: `759`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180010dc8`

## callees

- `0x180001650`
- `0x180001a8c`
- `0x1800026b0`

## pseudocode

```c
ULONG __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        __int64 a1,
        unsigned __int8 *a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        const unsigned __int16 **a7,
        __int64 a8,
        const unsigned __int16 **a9,
        __int64 a10,
        void **a11,
        __int64 a12,
        const unsigned __int16 **a13,
        __int64 a14,
        const unsigned __int16 **a15,
        void **a16,
        __int64 a17,
        const unsigned __int16 **a18,
        void **a19,
        __int64 a20,
        __int64 a21,
        const unsigned __int16 **a22)
{
  __int64 v23; // rdx
  const unsigned __int16 *v24; // r8
  __int64 v25; // rax
  int v26; // eax
  int v27; // r9d
  _WORD *v28; // r8
  __int64 v29; // rax
  int v30; // eax
  const unsigned __int16 *v31; // r8
  __int64 v32; // rax
  int v33; // eax
  _WORD *v34; // r8
  __int64 v35; // rax
  int v36; // eax
  const unsigned __int16 *v37; // r8
  __int64 v38; // rax
  int v39; // eax
  const unsigned __int16 *v40; // r8
  __int64 v41; // rax
  int v42; // eax
  _WORD *v43; // r8
  __int64 v44; // rax
  const unsigned __int16 *v45; // r8
  __int64 v46; // rax
  int v47; // eax
  const unsigned __int16 *v48; // r8
  int v49; // edx
  struct _EVENT_DATA_DESCRIPTOR v51; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v52; // [rsp+50h] [rbp-B0h]
  __int64 v53; // [rsp+58h] [rbp-A8h]
  __int64 v54; // [rsp+60h] [rbp-A0h]
  __int64 v55; // [rsp+68h] [rbp-98h]
  const unsigned __int16 *v56; // [rsp+70h] [rbp-90h]
  int v57; // [rsp+78h] [rbp-88h]
  int v58; // [rsp+7Ch] [rbp-84h]
  __int64 v59; // [rsp+80h] [rbp-80h]
  __int64 v60; // [rsp+88h] [rbp-78h]
  const unsigned __int16 *v61; // [rsp+90h] [rbp-70h]
  int v62; // [rsp+98h] [rbp-68h]
  int v63; // [rsp+9Ch] [rbp-64h]
  __int64 v64; // [rsp+A0h] [rbp-60h]
  __int64 v65; // [rsp+A8h] [rbp-58h]
  _WORD *v66; // [rsp+B0h] [rbp-50h]
  int v67; // [rsp+B8h] [rbp-48h]
  int v68; // [rsp+BCh] [rbp-44h]
  __int64 v69; // [rsp+C0h] [rbp-40h]
  __int64 v70; // [rsp+C8h] [rbp-38h]
  const unsigned __int16 *v71; // [rsp+D0h] [rbp-30h]
  int v72; // [rsp+D8h] [rbp-28h]
  int v73; // [rsp+DCh] [rbp-24h]
  __int64 v74; // [rsp+E0h] [rbp-20h]
  __int64 v75; // [rsp+E8h] [rbp-18h]
  const unsigned __int16 *v76; // [rsp+F0h] [rbp-10h]
  int v77; // [rsp+F8h] [rbp-8h]
  int v78; // [rsp+FCh] [rbp-4h]
  _WORD *v79; // [rsp+100h] [rbp+0h]
  int v80; // [rsp+108h] [rbp+8h]
  int v81; // [rsp+10Ch] [rbp+Ch]
  __int64 v82; // [rsp+110h] [rbp+10h]
  __int64 v83; // [rsp+118h] [rbp+18h]
  const unsigned __int16 *v84; // [rsp+120h] [rbp+20h]
  int v85; // [rsp+128h] [rbp+28h]
  int v86; // [rsp+12Ch] [rbp+2Ch]
  _WORD *v87; // [rsp+130h] [rbp+30h]
  int v88; // [rsp+138h] [rbp+38h]
  int v89; // [rsp+13Ch] [rbp+3Ch]
  __int64 v90; // [rsp+140h] [rbp+40h]
  __int64 v91; // [rsp+148h] [rbp+48h]
  __int64 v92; // [rsp+150h] [rbp+50h]
  __int64 v93; // [rsp+158h] [rbp+58h]
  const unsigned __int16 *v94; // [rsp+160h] [rbp+60h]
  int v95; // [rsp+168h] [rbp+68h]
  int v96; // [rsp+16Ch] [rbp+6Ch]

  v23 = -1;
  v24 = *a22;
  if ( *a22 )
  {
    v25 = -1;
    do
      ++v25;
    while ( *((_BYTE *)v24 + v25) );
    v26 = v25 + 1;
  }
  else
  {
    v24 = &word_1800261C0;
    v26 = 1;
  }
  v95 = v26;
  v27 = 2;
  v92 = a21;
  v90 = a20;
  v94 = v24;
  v96 = 0;
  v93 = 4;
  v28 = *a19;
  v91 = 4;
  if ( v28 )
  {
    v29 = -1;
    do
      ++v29;
    while ( v28[v29] );
    v30 = 2 * v29 + 2;
  }
  else
  {
    v28 = &unk_1800261C4;
    v30 = 2;
  }
  v88 = v30;
  v87 = v28;
  v89 = 0;
  v31 = *a18;
  if ( *a18 )
  {
    v32 = -1;
    do
      ++v32;
    while ( *((_BYTE *)v31 + v32) );
    v33 = v32 + 1;
  }
  else
  {
    v31 = &word_1800261C0;
    v33 = 1;
  }
  v85 = v33;
  v82 = a17;
  v84 = v31;
  v86 = 0;
  v83 = 4;
  v34 = *a16;
  if ( *a16 )
  {
    v35 = -1;
    do
      ++v35;
    while ( v34[v35] );
    v36 = 2 * v35 + 2;
  }
  else
  {
    v34 = &unk_1800261C4;
    v36 = 2;
  }
  v80 = v36;
  v79 = v34;
  v81 = 0;
  v37 = *a15;
  if ( *a15 )
  {
    v38 = -1;
    do
      ++v38;
    while ( *((_BYTE *)v37 + v38) );
    v39 = v38 + 1;
  }
  else
  {
    v37 = &word_1800261C0;
    v39 = 1;
  }
  v77 = v39;
  v74 = a14;
  v76 = v37;
  v78 = 0;
  v75 = 4;
  v40 = *a13;
  if ( *a13 )
  {
    v41 = -1;
    do
      ++v41;
    while ( *((_BYTE *)v40 + v41) );
    v42 = v41 + 1;
  }
  else
  {
    v40 = &word_1800261C0;
    v42 = 1;
  }
  v72 = v42;
  v69 = a12;
  v71 = v40;
  v73 = 0;
  v70 = 4;
  v43 = *a11;
  if ( *a11 )
  {
    v44 = -1;
    do
      ++v44;
    while ( v43[v44] );
    v27 = 2 * v44 + 2;
  }
  else
  {
    v43 = &unk_1800261C4;
  }
  v64 = a10;
  v66 = v43;
  v67 = v27;
  v68 = 0;
  v45 = *a9;
  v65 = 4;
  if ( v45 )
  {
    v46 = -1;
    do
      ++v46;
    while ( *((_BYTE *)v45 + v46) );
    v47 = v46 + 1;
  }
  else
  {
    v45 = &word_1800261C0;
    v47 = 1;
  }
  v62 = v47;
  v59 = a8;
  v61 = v45;
  v63 = 0;
  v60 = 4;
  v48 = *a7;
  if ( *a7 )
  {
    do
      ++v23;
    while ( *((_BYTE *)v48 + v23) );
    v49 = v23 + 1;
  }
  else
  {
    v48 = &word_1800261C0;
    v49 = 1;
  }
  v54 = a6;
  v52 = a5;
  v56 = v48;
  v57 = v49;
  v58 = 0;
  v55 = 4;
  v53 = 8;
  return tlgWriteTransfer_EventWriteTransfer(a1, a2, 0, 0, 0x14u, &v51);
}

```

## disassembly

```asm
0x180001650  mov     [rsp-8+arg_10], rbx
0x180001655  push    rbp
0x180001656  push    rdi
0x180001657  push    r14
0x180001659  lea     rbp, [rsp-80h]
0x18000165e  sub     rsp, 180h
0x180001665  mov     rax, cs:__security_cookie
0x18000166c  xor     rax, rsp
0x18000166f  mov     [rbp+90h+var_20], rax
0x180001673  mov     rax, [rbp+90h+arg_A8]
0x18000167a  lea     rdi, word_1800261C0
0x180001681  mov     r11, rdx
0x180001684  xor     ebx, ebx
0x180001686  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18000168a  mov     r10, rcx
0x18000168d  mov     r8, [rax]
0x180001690  test    r8, r8
0x180001693  jz      short loc_1800016AA
0x180001695  mov     rax, rdx
0x180001698  inc     rax
0x18000169b  cmp     [r8+rax], bl
0x18000169f  jnz     short loc_180001698
0x1800016a1  mov     ecx, 1
0x1800016a6  add     eax, ecx
0x1800016a8  jmp     short loc_1800016B4
0x1800016aa  mov     ecx, 1
0x1800016af  mov     r8, rdi
0x1800016b2  mov     eax, ecx
0x1800016b4  mov     [rbp+90h+var_28], eax
0x1800016b7  mov     r9d, 2
0x1800016bd  mov     rax, [rbp+90h+arg_A0]
0x1800016c4  mov     [rbp+90h+var_40], rax
0x1800016c8  mov     rax, [rbp+90h+arg_98]
0x1800016cf  mov     [rbp+90h+var_50], rax
0x1800016d3  mov     rax, [rbp+90h+arg_90]
0x1800016da  mov     [rbp+90h+var_30], r8
0x1800016de  mov     [rbp+90h+var_24], ebx
0x1800016e1  mov     [rbp+90h+var_38], 4
0x1800016e9  mov     r8, [rax]
0x1800016ec  mov     [rbp+90h+var_48], 4
0x1800016f4  test    r8, r8
0x1800016f7  jz      short loc_18000170F
0x1800016f9  mov     rax, rdx
0x1800016fc  inc     rax
0x1800016ff  cmp     [r8+rax*2], bx
0x180001704  jnz     short loc_1800016FC
0x180001706  lea     eax, ds:2[rax*2]
0x18000170d  jmp     short loc_180001719
0x18000170f  lea     r8, unk_1800261C4
0x180001716  mov     eax, r9d
0x180001719  mov     [rbp+90h+var_58], eax
0x18000171c  mov     rax, [rbp+90h+arg_88]
0x180001723  mov     [rbp+90h+var_60], r8
0x180001727  mov     [rbp+90h+var_54], ebx
0x18000172a  mov     r8, [rax]
0x18000172d  test    r8, r8
0x180001730  jz      short loc_180001742
0x180001732  mov     rax, rdx
0x180001735  inc     rax
0x180001738  cmp     [r8+rax], bl
0x18000173c  jnz     short loc_180001735
0x18000173e  add     eax, ecx
0x180001740  jmp     short loc_180001747
0x180001742  mov     r8, rdi
0x180001745  mov     eax, ecx
0x180001747  mov     [rbp+90h+var_68], eax
0x18000174a  mov     rax, [rbp+90h+arg_80]
0x180001751  mov     [rbp+90h+var_80], rax
0x180001755  mov     rax, [rbp+90h+arg_78]
0x18000175c  mov     [rbp+90h+var_70], r8
0x180001760  mov     [rbp+90h+var_64], ebx
0x180001763  mov     [rbp+90h+var_78], 4
0x18000176b  mov     r8, [rax]
0x18000176e  test    r8, r8
0x180001771  jz      short loc_180001789
0x180001773  mov     rax, rdx
0x180001776  inc     rax
0x180001779  cmp     [r8+rax*2], bx
0x18000177e  jnz     short loc_180001776
0x180001780  lea     eax, ds:2[rax*2]
0x180001787  jmp     short loc_180001793
0x180001789  lea     r8, unk_1800261C4
0x180001790  mov     eax, r9d
0x180001793  mov     [rbp+90h+var_88], eax
0x180001796  mov     rax, [rbp+90h+arg_70]
0x18000179d  mov     [rbp+90h+var_90], r8
0x1800017a1  mov     [rbp+90h+var_84], ebx
0x1800017a4  mov     r8, [rax]
0x1800017a7  test    r8, r8
0x1800017aa  jz      short loc_1800017BC
0x1800017ac  mov     rax, rdx
0x1800017af  inc     rax
0x1800017b2  cmp     [r8+rax], bl
0x1800017b6  jnz     short loc_1800017AF
0x1800017b8  add     eax, ecx
0x1800017ba  jmp     short loc_1800017C1
0x1800017bc  mov     r8, rdi
0x1800017bf  mov     eax, ecx
0x1800017c1  mov     [rbp+90h+var_98], eax
0x1800017c4  mov     rax, [rbp+90h+arg_68]
0x1800017cb  mov     [rbp+90h+var_B0], rax
0x1800017cf  mov     rax, [rbp+90h+arg_60]
0x1800017d6  mov     [rbp+90h+var_A0], r8
0x1800017da  mov     [rbp+90h+var_94], ebx
0x1800017dd  mov     [rbp+90h+var_A8], 4
0x1800017e5  mov     r8, [rax]
0x1800017e8  test    r8, r8
0x1800017eb  jz      short loc_1800017FD
0x1800017ed  mov     rax, rdx
0x1800017f0  inc     rax
0x1800017f3  cmp     [r8+rax], bl
0x1800017f7  jnz     short loc_1800017F0
0x1800017f9  add     eax, ecx
0x1800017fb  jmp     short loc_180001802
0x1800017fd  mov     r8, rdi
0x180001800  mov     eax, ecx
0x180001802  mov     [rbp+90h+var_B8], eax
0x180001805  mov     rax, [rbp+90h+arg_58]
0x18000180c  mov     [rbp+90h+var_D0], rax
0x180001810  mov     rax, [rbp+90h+arg_50]
0x180001817  mov     [rbp+90h+var_C0], r8
0x18000181b  mov     [rbp+90h+var_B4], ebx
0x18000181e  mov     [rbp+90h+var_C8], 4
0x180001826  mov     r8, [rax]
0x180001829  test    r8, r8
0x18000182c  jz      short loc_180001845
0x18000182e  mov     rax, rdx
0x180001831  inc     rax
0x180001834  cmp     [r8+rax*2], bx
0x180001839  jnz     short loc_180001831
0x18000183b  lea     r9d, ds:2[rax*2]
0x180001843  jmp     short loc_18000184C
0x180001845  lea     r8, unk_1800261C4
0x18000184c  mov     rax, [rbp+90h+arg_48]
0x180001853  mov     [rbp+90h+var_F0], rax
0x180001857  mov     rax, [rbp+90h+arg_40]
0x18000185e  mov     [rbp+90h+var_E0], r8
0x180001862  mov     [rbp+90h+var_D8], r9d
0x180001866  mov     [rbp+90h+var_D4], ebx
0x180001869  mov     r8, [rax]
0x18000186c  mov     [rbp+90h+var_E8], 4
0x180001874  test    r8, r8
0x180001877  jz      short loc_180001889
0x180001879  mov     rax, rdx
0x18000187c  inc     rax
0x18000187f  cmp     [r8+rax], bl
0x180001883  jnz     short loc_18000187C
0x180001885  add     eax, ecx
0x180001887  jmp     short loc_18000188E
0x180001889  mov     r8, rdi
0x18000188c  mov     eax, ecx
0x18000188e  mov     [rbp+90h+var_F8], eax
0x180001891  mov     rax, [rbp+90h+arg_38]
0x180001898  mov     [rbp+90h+var_110], rax
0x18000189c  mov     rax, [rbp+90h+arg_30]
0x1800018a3  mov     [rbp+90h+var_100], r8
0x1800018a7  mov     [rbp+90h+var_F4], ebx
0x1800018aa  mov     [rbp+90h+var_108], 4
0x1800018b2  mov     r8, [rax]
0x1800018b5  test    r8, r8
0x1800018b8  jz      short loc_1800018C7
0x1800018ba  inc     rdx
0x1800018bd  cmp     [r8+rdx], bl
0x1800018c1  jnz     short loc_1800018BA
0x1800018c3  add     edx, ecx
0x1800018c5  jmp     short loc_1800018CC
0x1800018c7  mov     r8, rdi
0x1800018ca  mov     edx, ecx
0x1800018cc  mov     rax, [rbp+90h+arg_28]
0x1800018d3  xor     r9d, r9d
0x1800018d6  mov     [rsp+190h+var_130], rax
0x1800018db  mov     rcx, r10
0x1800018de  mov     rax, [rbp+90h+arg_20]
0x1800018e5  mov     [rsp+190h+var_140], rax
0x1800018ea  lea     rax, [rsp+190h+var_160]
0x1800018ef  mov     [rsp+190h+var_120], r8
0x1800018f4  xor     r8d, r8d
0x1800018f7  mov     [rsp+190h+var_118], edx
0x1800018fb  mov     rdx, r11
0x1800018fe  mov     [rsp+190h+var_168], rax
0x180001903  mov     [rsp+190h+var_170], 14h
0x18000190b  mov     [rsp+190h+var_114], ebx
0x18000190f  mov     [rsp+190h+var_128], 4
0x180001918  mov     [rsp+190h+var_138], 8
0x180001921  call    _tlgWriteTransfer_EventWriteTransfer
0x180001926  mov     rcx, [rbp+90h+var_20]
0x18000192a  xor     rcx, rsp; StackCookie
0x18000192d  call    __security_check_cookie
0x180001932  mov     rbx, [rsp+190h+arg_10]
0x18000193a  add     rsp, 180h
0x180001941  pop     r14
0x180001943  pop     rdi
0x180001944  pop     rbp
0x180001945  retn
```
