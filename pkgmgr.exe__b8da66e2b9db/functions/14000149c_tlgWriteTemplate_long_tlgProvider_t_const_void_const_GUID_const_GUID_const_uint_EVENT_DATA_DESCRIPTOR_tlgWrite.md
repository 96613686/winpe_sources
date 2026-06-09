# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<wchar_t> const &)

- ea: `0x14000149c`
- end: `0x140001747`
- name: `??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@_W@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@_W@@45456456@Z`
- size: `683`
- prototype: `__int64 __fastcall(int, int, __int64, __int64, __int64, __int64, __int64, const wchar_t **, __int64, const wchar_t **, __int64, int **, __int64, const wchar_t **, __int64, const wchar_t **, int **, __int64, const wchar_t **, int **)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x14002403c`

## callees

- `0x14000149c`
- `0x140001c88`
- `0x140002360`

## pseudocode

```c
__int64 __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>>(
        int a1,
        int a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        __int64 a7,
        const wchar_t **a8,
        __int64 a9,
        const wchar_t **a10,
        __int64 a11,
        int **a12,
        __int64 a13,
        const wchar_t **a14,
        __int64 a15,
        const wchar_t **a16,
        int **a17,
        __int64 a18,
        const wchar_t **a19,
        int **a20)
{
  __int64 v22; // rcx
  int v23; // r9d
  int *v24; // rdx
  __int64 v25; // rax
  int v26; // eax
  int v27; // r8d
  const wchar_t *v28; // rdx
  __int64 v29; // rax
  int v30; // eax
  int *v31; // rdx
  __int64 v32; // rax
  int v33; // eax
  const wchar_t *v34; // rdx
  __int64 v35; // rax
  int v36; // eax
  const wchar_t *v37; // rdx
  __int64 v38; // rax
  int v39; // eax
  int *v40; // rdx
  __int64 v41; // rax
  const wchar_t *v42; // rdx
  __int64 v43; // rax
  int v44; // eax
  const wchar_t *v45; // rdx
  struct _EVENT_DATA_DESCRIPTOR v47; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v48; // [rsp+50h] [rbp-B0h]
  __int64 v49; // [rsp+58h] [rbp-A8h]
  __int64 v50; // [rsp+60h] [rbp-A0h]
  __int64 v51; // [rsp+68h] [rbp-98h]
  __int64 v52; // [rsp+70h] [rbp-90h]
  __int64 v53; // [rsp+78h] [rbp-88h]
  const wchar_t *v54; // [rsp+80h] [rbp-80h]
  int v55; // [rsp+88h] [rbp-78h]
  int v56; // [rsp+8Ch] [rbp-74h]
  __int64 v57; // [rsp+90h] [rbp-70h]
  __int64 v58; // [rsp+98h] [rbp-68h]
  const wchar_t *v59; // [rsp+A0h] [rbp-60h]
  int v60; // [rsp+A8h] [rbp-58h]
  int v61; // [rsp+ACh] [rbp-54h]
  __int64 v62; // [rsp+B0h] [rbp-50h]
  __int64 v63; // [rsp+B8h] [rbp-48h]
  int *v64; // [rsp+C0h] [rbp-40h]
  int v65; // [rsp+C8h] [rbp-38h]
  int v66; // [rsp+CCh] [rbp-34h]
  __int64 v67; // [rsp+D0h] [rbp-30h]
  __int64 v68; // [rsp+D8h] [rbp-28h]
  const wchar_t *v69; // [rsp+E0h] [rbp-20h]
  int v70; // [rsp+E8h] [rbp-18h]
  int v71; // [rsp+ECh] [rbp-14h]
  __int64 v72; // [rsp+F0h] [rbp-10h]
  __int64 v73; // [rsp+F8h] [rbp-8h]
  const wchar_t *v74; // [rsp+100h] [rbp+0h]
  int v75; // [rsp+108h] [rbp+8h]
  int v76; // [rsp+10Ch] [rbp+Ch]
  int *v77; // [rsp+110h] [rbp+10h]
  int v78; // [rsp+118h] [rbp+18h]
  int v79; // [rsp+11Ch] [rbp+1Ch]
  __int64 v80; // [rsp+120h] [rbp+20h]
  __int64 v81; // [rsp+128h] [rbp+28h]
  const wchar_t *v82; // [rsp+130h] [rbp+30h]
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
    v24 = &dword_14002EB1C;
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
    v28 = &qword_14002D1C8;
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
    v31 = &dword_14002EB1C;
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
    v34 = &qword_14002D1C8;
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
    v37 = &qword_14002D1C8;
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
    v40 = &dword_14002EB1C;
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
    v42 = &qword_14002D1C8;
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
    v45 = &qword_14002D1C8;
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
0x14000149c  mov     [rsp-8+arg_10], rbx
0x1400014a1  push    rbp
0x1400014a2  push    rsi
0x1400014a3  push    rdi
0x1400014a4  lea     rbp, [rsp-60h]
0x1400014a9  sub     rsp, 160h
0x1400014b0  mov     rax, cs:__security_cookie
0x1400014b7  xor     rax, rsp
0x1400014ba  mov     [rbp+70h+var_20], rax
0x1400014be  mov     rax, [rbp+70h+arg_98]
0x1400014c5  mov     r11, rdx
0x1400014c8  mov     r10, rcx
0x1400014cb  xor     ebx, ebx
0x1400014cd  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1400014d1  mov     r9d, 2
0x1400014d7  mov     rdx, [rax]
0x1400014da  test    rdx, rdx
0x1400014dd  jz      short loc_1400014F4
0x1400014df  mov     rax, rcx
0x1400014e2  inc     rax
0x1400014e5  cmp     [rdx+rax*2], bx
0x1400014e9  jnz     short loc_1400014E2
0x1400014eb  lea     eax, ds:2[rax*2]
0x1400014f2  jmp     short loc_1400014FE
0x1400014f4  lea     rdx, dword_14002EB1C
0x1400014fb  mov     eax, r9d
0x1400014fe  mov     [rbp+70h+var_28], eax
0x140001501  lea     rdi, qword_14002D1C8
0x140001508  mov     rax, [rbp+70h+arg_90]
0x14000150f  mov     r8d, 1
0x140001515  mov     [rbp+70h+var_30], rdx
0x140001519  mov     [rbp+70h+var_24], ebx
0x14000151c  mov     rdx, [rax]
0x14000151f  test    rdx, rdx
0x140001522  jz      short loc_140001533
0x140001524  mov     rax, rcx
0x140001527  inc     rax
0x14000152a  cmp     [rdx+rax], bl
0x14000152d  jnz     short loc_140001527
0x14000152f  inc     eax
0x140001531  jmp     short loc_140001539
0x140001533  mov     rdx, rdi
0x140001536  mov     eax, r8d
0x140001539  mov     [rbp+70h+var_38], eax
0x14000153c  mov     rax, [rbp+70h+arg_88]
0x140001543  mov     [rbp+70h+var_50], rax
0x140001547  mov     rax, [rbp+70h+arg_80]
0x14000154e  mov     [rbp+70h+var_40], rdx
0x140001552  mov     [rbp+70h+var_34], ebx
0x140001555  mov     [rbp+70h+var_48], 4
0x14000155d  mov     rdx, [rax]
0x140001560  test    rdx, rdx
0x140001563  jz      short loc_14000157A
0x140001565  mov     rax, rcx
0x140001568  inc     rax
0x14000156b  cmp     [rdx+rax*2], bx
0x14000156f  jnz     short loc_140001568
0x140001571  lea     eax, ds:2[rax*2]
0x140001578  jmp     short loc_140001584
0x14000157a  lea     rdx, dword_14002EB1C
0x140001581  mov     eax, r9d
0x140001584  mov     [rbp+70h+var_58], eax
0x140001587  mov     rax, [rbp+70h+arg_78]
0x14000158e  mov     [rbp+70h+var_60], rdx
0x140001592  mov     [rbp+70h+var_54], ebx
0x140001595  mov     rdx, [rax]
0x140001598  test    rdx, rdx
0x14000159b  jz      short loc_1400015AC
0x14000159d  mov     rax, rcx
0x1400015a0  inc     rax
0x1400015a3  cmp     [rdx+rax], bl
0x1400015a6  jnz     short loc_1400015A0
0x1400015a8  inc     eax
0x1400015aa  jmp     short loc_1400015B2
0x1400015ac  mov     rdx, rdi
0x1400015af  mov     eax, r8d
0x1400015b2  mov     [rbp+70h+var_68], eax
0x1400015b5  mov     rax, [rbp+70h+arg_70]
0x1400015bc  mov     [rbp+70h+var_80], rax
0x1400015c0  mov     rax, [rbp+70h+arg_68]
0x1400015c7  mov     [rbp+70h+var_70], rdx
0x1400015cb  mov     [rbp+70h+var_64], ebx
0x1400015ce  mov     [rbp+70h+var_78], 4
0x1400015d6  mov     rdx, [rax]
0x1400015d9  test    rdx, rdx
0x1400015dc  jz      short loc_1400015ED
0x1400015de  mov     rax, rcx
0x1400015e1  inc     rax
0x1400015e4  cmp     [rdx+rax], bl
0x1400015e7  jnz     short loc_1400015E1
0x1400015e9  inc     eax
0x1400015eb  jmp     short loc_1400015F3
0x1400015ed  mov     rdx, rdi
0x1400015f0  mov     eax, r8d
0x1400015f3  mov     [rbp+70h+var_88], eax
0x1400015f6  mov     rax, [rbp+70h+arg_60]
0x1400015fd  mov     [rbp+70h+var_A0], rax
0x140001601  mov     rax, [rbp+70h+arg_58]
0x140001608  mov     [rbp+70h+var_90], rdx
0x14000160c  mov     [rbp+70h+var_84], ebx
0x14000160f  mov     [rbp+70h+var_98], 4
0x140001617  mov     rdx, [rax]
0x14000161a  test    rdx, rdx
0x14000161d  jz      short loc_140001635
0x14000161f  mov     rax, rcx
0x140001622  inc     rax
0x140001625  cmp     [rdx+rax*2], bx
0x140001629  jnz     short loc_140001622
0x14000162b  lea     r9d, ds:2[rax*2]
0x140001633  jmp     short loc_14000163C
0x140001635  lea     rdx, dword_14002EB1C
0x14000163c  mov     rax, [rbp+70h+arg_50]
0x140001643  mov     [rbp+70h+var_C0], rax
0x140001647  mov     rax, [rbp+70h+arg_48]
0x14000164e  mov     [rbp+70h+var_B0], rdx
0x140001652  mov     [rbp+70h+var_A8], r9d
0x140001656  mov     [rbp+70h+var_A4], ebx
0x140001659  mov     rdx, [rax]
0x14000165c  mov     [rbp+70h+var_B8], 4
0x140001664  test    rdx, rdx
0x140001667  jz      short loc_140001678
0x140001669  mov     rax, rcx
0x14000166c  inc     rax
0x14000166f  cmp     [rdx+rax], bl
0x140001672  jnz     short loc_14000166C
0x140001674  inc     eax
0x140001676  jmp     short loc_14000167E
0x140001678  mov     rdx, rdi
0x14000167b  mov     eax, r8d
0x14000167e  mov     [rbp+70h+var_C8], eax
0x140001681  mov     rax, [rbp+70h+arg_40]
0x140001688  mov     [rbp+70h+var_E0], rax
0x14000168c  mov     rax, [rbp+70h+arg_38]
0x140001693  mov     [rbp+70h+var_D0], rdx
0x140001697  mov     [rbp+70h+var_C4], ebx
0x14000169a  mov     [rbp+70h+var_D8], 4
0x1400016a2  mov     rdx, [rax]
0x1400016a5  test    rdx, rdx
0x1400016a8  jz      short loc_1400016B8
0x1400016aa  inc     rcx
0x1400016ad  cmp     [rdx+rcx], bl
0x1400016b0  jnz     short loc_1400016AA
0x1400016b2  lea     r8d, [rcx+1]
0x1400016b6  jmp     short loc_1400016BB
0x1400016b8  mov     rdx, rdi
0x1400016bb  mov     rax, [rbp+70h+arg_30]
0x1400016c2  xor     r9d, r9d; int
0x1400016c5  mov     [rsp+170h+var_100], rax
0x1400016ca  mov     rcx, r10; int
0x1400016cd  mov     rax, [rbp+70h+arg_28]
0x1400016d4  mov     [rsp+170h+var_110], rax
0x1400016d9  mov     rax, [rbp+70h+arg_20]
0x1400016e0  mov     [rsp+170h+var_120], rax
0x1400016e5  lea     rax, [rsp+170h+var_140]
0x1400016ea  mov     [rbp+70h+var_F0], rdx
0x1400016ee  mov     rdx, r11; int
0x1400016f1  mov     [rbp+70h+var_E8], r8d
0x1400016f5  xor     r8d, r8d; int
0x1400016f8  mov     [rsp+170h+var_148], rax; PEVENT_DATA_DESCRIPTOR
0x1400016fd  mov     [rsp+170h+var_150], 12h; ULONG
0x140001705  mov     [rbp+70h+var_E4], ebx
0x140001708  mov     [rsp+170h+var_F8], 4
0x140001711  mov     [rsp+170h+var_108], 8
0x14000171a  mov     [rsp+170h+var_118], 8
0x140001723  call    _tlgWriteTransfer_EventWriteTransfer
0x140001728  mov     rcx, [rbp+70h+var_20]
0x14000172c  xor     rcx, rsp; StackCookie
0x14000172f  call    __security_check_cookie
0x140001734  mov     rbx, [rsp+170h+arg_10]
0x14000173c  add     rsp, 160h
0x140001743  pop     rdi
0x140001744  pop     rsi
0x140001745  pop     rbp
0x140001746  retn
```
