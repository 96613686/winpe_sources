# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)

- ea: `0x18000132c`
- end: `0x1800015d7`
- name: `??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456@Z`
- size: `683`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180005750`

## callees

- `0x18000132c`
- `0x180001f18`
- `0x18001ac90`

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
    v24 = &dword_18001D574;
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
    v28 = &byte_18001D570;
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
    v31 = &dword_18001D574;
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
    v34 = &byte_18001D570;
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
    v37 = &byte_18001D570;
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
    v40 = &dword_18001D574;
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
    v42 = &byte_18001D570;
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
    v45 = &byte_18001D570;
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
0x18000132c  mov     [rsp-8+arg_10], rbx
0x180001331  push    rbp
0x180001332  push    rsi
0x180001333  push    rdi
0x180001334  lea     rbp, [rsp-60h]
0x180001339  sub     rsp, 160h
0x180001340  mov     rax, cs:__security_cookie
0x180001347  xor     rax, rsp
0x18000134a  mov     [rbp+70h+var_20], rax
0x18000134e  mov     rax, [rbp+70h+arg_98]
0x180001355  mov     r11, rdx
0x180001358  mov     r10, rcx
0x18000135b  xor     ebx, ebx
0x18000135d  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180001361  mov     r9d, 2
0x180001367  mov     rdx, [rax]
0x18000136a  test    rdx, rdx
0x18000136d  jz      short loc_180001384
0x18000136f  mov     rax, rcx
0x180001372  inc     rax
0x180001375  cmp     [rdx+rax*2], bx
0x180001379  jnz     short loc_180001372
0x18000137b  lea     eax, ds:2[rax*2]
0x180001382  jmp     short loc_18000138E
0x180001384  lea     rdx, dword_18001D574
0x18000138b  mov     eax, r9d
0x18000138e  mov     [rbp+70h+var_28], eax
0x180001391  lea     rdi, byte_18001D570
0x180001398  mov     rax, [rbp+70h+arg_90]
0x18000139f  mov     r8d, 1
0x1800013a5  mov     [rbp+70h+var_30], rdx
0x1800013a9  mov     [rbp+70h+var_24], ebx
0x1800013ac  mov     rdx, [rax]
0x1800013af  test    rdx, rdx
0x1800013b2  jz      short loc_1800013C3
0x1800013b4  mov     rax, rcx
0x1800013b7  inc     rax
0x1800013ba  cmp     [rdx+rax], bl
0x1800013bd  jnz     short loc_1800013B7
0x1800013bf  inc     eax
0x1800013c1  jmp     short loc_1800013C9
0x1800013c3  mov     rdx, rdi
0x1800013c6  mov     eax, r8d
0x1800013c9  mov     [rbp+70h+var_38], eax
0x1800013cc  mov     rax, [rbp+70h+arg_88]
0x1800013d3  mov     [rbp+70h+var_50], rax
0x1800013d7  mov     rax, [rbp+70h+arg_80]
0x1800013de  mov     [rbp+70h+var_40], rdx
0x1800013e2  mov     [rbp+70h+var_34], ebx
0x1800013e5  mov     [rbp+70h+var_48], 4
0x1800013ed  mov     rdx, [rax]
0x1800013f0  test    rdx, rdx
0x1800013f3  jz      short loc_18000140A
0x1800013f5  mov     rax, rcx
0x1800013f8  inc     rax
0x1800013fb  cmp     [rdx+rax*2], bx
0x1800013ff  jnz     short loc_1800013F8
0x180001401  lea     eax, ds:2[rax*2]
0x180001408  jmp     short loc_180001414
0x18000140a  lea     rdx, dword_18001D574
0x180001411  mov     eax, r9d
0x180001414  mov     [rbp+70h+var_58], eax
0x180001417  mov     rax, [rbp+70h+arg_78]
0x18000141e  mov     [rbp+70h+var_60], rdx
0x180001422  mov     [rbp+70h+var_54], ebx
0x180001425  mov     rdx, [rax]
0x180001428  test    rdx, rdx
0x18000142b  jz      short loc_18000143C
0x18000142d  mov     rax, rcx
0x180001430  inc     rax
0x180001433  cmp     [rdx+rax], bl
0x180001436  jnz     short loc_180001430
0x180001438  inc     eax
0x18000143a  jmp     short loc_180001442
0x18000143c  mov     rdx, rdi
0x18000143f  mov     eax, r8d
0x180001442  mov     [rbp+70h+var_68], eax
0x180001445  mov     rax, [rbp+70h+arg_70]
0x18000144c  mov     [rbp+70h+var_80], rax
0x180001450  mov     rax, [rbp+70h+arg_68]
0x180001457  mov     [rbp+70h+var_70], rdx
0x18000145b  mov     [rbp+70h+var_64], ebx
0x18000145e  mov     [rbp+70h+var_78], 4
0x180001466  mov     rdx, [rax]
0x180001469  test    rdx, rdx
0x18000146c  jz      short loc_18000147D
0x18000146e  mov     rax, rcx
0x180001471  inc     rax
0x180001474  cmp     [rdx+rax], bl
0x180001477  jnz     short loc_180001471
0x180001479  inc     eax
0x18000147b  jmp     short loc_180001483
0x18000147d  mov     rdx, rdi
0x180001480  mov     eax, r8d
0x180001483  mov     [rbp+70h+var_88], eax
0x180001486  mov     rax, [rbp+70h+arg_60]
0x18000148d  mov     [rbp+70h+var_A0], rax
0x180001491  mov     rax, [rbp+70h+arg_58]
0x180001498  mov     [rbp+70h+var_90], rdx
0x18000149c  mov     [rbp+70h+var_84], ebx
0x18000149f  mov     [rbp+70h+var_98], 4
0x1800014a7  mov     rdx, [rax]
0x1800014aa  test    rdx, rdx
0x1800014ad  jz      short loc_1800014C5
0x1800014af  mov     rax, rcx
0x1800014b2  inc     rax
0x1800014b5  cmp     [rdx+rax*2], bx
0x1800014b9  jnz     short loc_1800014B2
0x1800014bb  lea     r9d, ds:2[rax*2]
0x1800014c3  jmp     short loc_1800014CC
0x1800014c5  lea     rdx, dword_18001D574
0x1800014cc  mov     rax, [rbp+70h+arg_50]
0x1800014d3  mov     [rbp+70h+var_C0], rax
0x1800014d7  mov     rax, [rbp+70h+arg_48]
0x1800014de  mov     [rbp+70h+var_B0], rdx
0x1800014e2  mov     [rbp+70h+var_A8], r9d
0x1800014e6  mov     [rbp+70h+var_A4], ebx
0x1800014e9  mov     rdx, [rax]
0x1800014ec  mov     [rbp+70h+var_B8], 4
0x1800014f4  test    rdx, rdx
0x1800014f7  jz      short loc_180001508
0x1800014f9  mov     rax, rcx
0x1800014fc  inc     rax
0x1800014ff  cmp     [rdx+rax], bl
0x180001502  jnz     short loc_1800014FC
0x180001504  inc     eax
0x180001506  jmp     short loc_18000150E
0x180001508  mov     rdx, rdi
0x18000150b  mov     eax, r8d
0x18000150e  mov     [rbp+70h+var_C8], eax
0x180001511  mov     rax, [rbp+70h+arg_40]
0x180001518  mov     [rbp+70h+var_E0], rax
0x18000151c  mov     rax, [rbp+70h+arg_38]
0x180001523  mov     [rbp+70h+var_D0], rdx
0x180001527  mov     [rbp+70h+var_C4], ebx
0x18000152a  mov     [rbp+70h+var_D8], 4
0x180001532  mov     rdx, [rax]
0x180001535  test    rdx, rdx
0x180001538  jz      short loc_180001548
0x18000153a  inc     rcx
0x18000153d  cmp     [rdx+rcx], bl
0x180001540  jnz     short loc_18000153A
0x180001542  lea     r8d, [rcx+1]
0x180001546  jmp     short loc_18000154B
0x180001548  mov     rdx, rdi
0x18000154b  mov     rax, [rbp+70h+arg_30]
0x180001552  xor     r9d, r9d
0x180001555  mov     [rsp+170h+var_100], rax
0x18000155a  mov     rcx, r10
0x18000155d  mov     rax, [rbp+70h+arg_28]
0x180001564  mov     [rsp+170h+var_110], rax
0x180001569  mov     rax, [rbp+70h+arg_20]
0x180001570  mov     [rsp+170h+var_120], rax
0x180001575  lea     rax, [rsp+170h+var_140]
0x18000157a  mov     [rbp+70h+var_F0], rdx
0x18000157e  mov     rdx, r11
0x180001581  mov     [rbp+70h+var_E8], r8d
0x180001585  xor     r8d, r8d
0x180001588  mov     [rsp+170h+var_148], rax
0x18000158d  mov     [rsp+170h+var_150], 12h
0x180001595  mov     [rbp+70h+var_E4], ebx
0x180001598  mov     [rsp+170h+var_F8], 4
0x1800015a1  mov     [rsp+170h+var_108], 8
0x1800015aa  mov     [rsp+170h+var_118], 8
0x1800015b3  call    _tlgWriteTransfer_EventWriteTransfer
0x1800015b8  mov     rcx, [rbp+70h+var_20]
0x1800015bc  xor     rcx, rsp; StackCookie
0x1800015bf  call    __security_check_cookie
0x1800015c4  mov     rbx, [rsp+170h+arg_10]
0x1800015cc  add     rsp, 160h
0x1800015d3  pop     rdi
0x1800015d4  pop     rsi
0x1800015d5  pop     rbp
0x1800015d6  retn
```
