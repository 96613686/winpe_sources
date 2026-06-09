# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)

- ea: `0x14000177c`
- end: `0x140001a17`
- name: `??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456@Z`
- size: `667`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1400123e0`

## callees

- `0x1400016dc`
- `0x14000177c`
- `0x140002600`

## pseudocode

```c
ULONG __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
        __int64 a1,
        unsigned __int8 *a2,
        const GUID *a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        const unsigned __int16 **a7,
        __int64 a8,
        const unsigned __int16 **a9,
        __int64 a10,
        int **a11,
        __int64 a12,
        const unsigned __int16 **a13,
        __int64 a14,
        const unsigned __int16 **a15,
        int **a16,
        __int64 a17,
        const unsigned __int16 **a18,
        int **a19)
{
  __int64 v21; // rdx
  int v23; // r9d
  int *v24; // rcx
  __int64 v25; // rax
  int v26; // eax
  int v27; // r8d
  const unsigned __int16 *v28; // rcx
  __int64 v29; // rax
  int v30; // eax
  int *v31; // rcx
  __int64 v32; // rax
  int v33; // eax
  const unsigned __int16 *v34; // rcx
  __int64 v35; // rax
  int v36; // eax
  const unsigned __int16 *v37; // rcx
  __int64 v38; // rax
  int v39; // eax
  int *v40; // rcx
  __int64 v41; // rax
  const unsigned __int16 *v42; // rcx
  __int64 v43; // rax
  int v44; // eax
  const unsigned __int16 *v45; // rcx
  struct _EVENT_DATA_DESCRIPTOR v47; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v48; // [rsp+50h] [rbp-B0h]
  __int64 v49; // [rsp+58h] [rbp-A8h]
  __int64 v50; // [rsp+60h] [rbp-A0h]
  __int64 v51; // [rsp+68h] [rbp-98h]
  const unsigned __int16 *v52; // [rsp+70h] [rbp-90h]
  int v53; // [rsp+78h] [rbp-88h]
  int v54; // [rsp+7Ch] [rbp-84h]
  __int64 v55; // [rsp+80h] [rbp-80h]
  __int64 v56; // [rsp+88h] [rbp-78h]
  const unsigned __int16 *v57; // [rsp+90h] [rbp-70h]
  int v58; // [rsp+98h] [rbp-68h]
  int v59; // [rsp+9Ch] [rbp-64h]
  __int64 v60; // [rsp+A0h] [rbp-60h]
  __int64 v61; // [rsp+A8h] [rbp-58h]
  int *v62; // [rsp+B0h] [rbp-50h]
  int v63; // [rsp+B8h] [rbp-48h]
  int v64; // [rsp+BCh] [rbp-44h]
  __int64 v65; // [rsp+C0h] [rbp-40h]
  __int64 v66; // [rsp+C8h] [rbp-38h]
  const unsigned __int16 *v67; // [rsp+D0h] [rbp-30h]
  int v68; // [rsp+D8h] [rbp-28h]
  int v69; // [rsp+DCh] [rbp-24h]
  __int64 v70; // [rsp+E0h] [rbp-20h]
  __int64 v71; // [rsp+E8h] [rbp-18h]
  const unsigned __int16 *v72; // [rsp+F0h] [rbp-10h]
  int v73; // [rsp+F8h] [rbp-8h]
  int v74; // [rsp+FCh] [rbp-4h]
  int *v75; // [rsp+100h] [rbp+0h]
  int v76; // [rsp+108h] [rbp+8h]
  int v77; // [rsp+10Ch] [rbp+Ch]
  __int64 v78; // [rsp+110h] [rbp+10h]
  __int64 v79; // [rsp+118h] [rbp+18h]
  const unsigned __int16 *v80; // [rsp+120h] [rbp+20h]
  int v81; // [rsp+128h] [rbp+28h]
  int v82; // [rsp+12Ch] [rbp+2Ch]
  int *v83; // [rsp+130h] [rbp+30h]
  int v84; // [rsp+138h] [rbp+38h]
  int v85; // [rsp+13Ch] [rbp+3Ch]

  v21 = -1;
  v23 = 2;
  v24 = *a19;
  if ( *a19 )
  {
    v25 = -1;
    do
      ++v25;
    while ( *((_WORD *)v24 + v25) );
    v26 = 2 * v25 + 2;
  }
  else
  {
    v24 = &dword_140015CE4;
    v26 = 2;
  }
  v84 = v26;
  v27 = 1;
  v83 = v24;
  v85 = 0;
  v28 = *a18;
  if ( *a18 )
  {
    v29 = -1;
    do
      ++v29;
    while ( *((_BYTE *)v28 + v29) );
    v30 = v29 + 1;
  }
  else
  {
    v28 = &byte_140015CE0;
    v30 = 1;
  }
  v81 = v30;
  v78 = a17;
  v80 = v28;
  v82 = 0;
  v79 = 4;
  v31 = *a16;
  if ( *a16 )
  {
    v32 = -1;
    do
      ++v32;
    while ( *((_WORD *)v31 + v32) );
    v33 = 2 * v32 + 2;
  }
  else
  {
    v31 = &dword_140015CE4;
    v33 = 2;
  }
  v76 = v33;
  v75 = v31;
  v77 = 0;
  v34 = *a15;
  if ( *a15 )
  {
    v35 = -1;
    do
      ++v35;
    while ( *((_BYTE *)v34 + v35) );
    v36 = v35 + 1;
  }
  else
  {
    v34 = &byte_140015CE0;
    v36 = 1;
  }
  v73 = v36;
  v70 = a14;
  v72 = v34;
  v74 = 0;
  v71 = 4;
  v37 = *a13;
  if ( *a13 )
  {
    v38 = -1;
    do
      ++v38;
    while ( *((_BYTE *)v37 + v38) );
    v39 = v38 + 1;
  }
  else
  {
    v37 = &byte_140015CE0;
    v39 = 1;
  }
  v68 = v39;
  v65 = a12;
  v67 = v37;
  v69 = 0;
  v66 = 4;
  v40 = *a11;
  if ( *a11 )
  {
    v41 = -1;
    do
      ++v41;
    while ( *((_WORD *)v40 + v41) );
    v23 = 2 * v41 + 2;
  }
  else
  {
    v40 = &dword_140015CE4;
  }
  v60 = a10;
  v62 = v40;
  v63 = v23;
  v64 = 0;
  v42 = *a9;
  v61 = 4;
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
    v42 = &byte_140015CE0;
    v44 = 1;
  }
  v58 = v44;
  v55 = a8;
  v57 = v42;
  v59 = 0;
  v56 = 4;
  v45 = *a7;
  if ( *a7 )
  {
    do
      ++v21;
    while ( *((_BYTE *)v45 + v21) );
    v27 = v21 + 1;
  }
  else
  {
    v45 = &byte_140015CE0;
  }
  v50 = a6;
  v48 = a5;
  v52 = v45;
  v53 = v27;
  v54 = 0;
  v51 = 4;
  v49 = 8;
  return tlgWriteTransfer_EventWriteTransfer(a1, a2, a3, 0, 0x11u, &v47);
}

```

## disassembly

```asm
0x14000177c  push    rbp
0x14000177e  push    rbx
0x14000177f  push    rsi
0x140001780  push    rdi
0x140001781  push    r14
0x140001783  lea     rbp, [rsp-50h]
0x140001788  sub     rsp, 150h
0x14000178f  mov     rax, cs:__security_cookie
0x140001796  xor     rax, rsp
0x140001799  mov     [rbp+70h+var_30], rax
0x14000179d  mov     rax, [rbp+70h+arg_90]
0x1400017a4  mov     r11, rdx
0x1400017a7  mov     r10, rcx
0x1400017aa  or      rdx, 0FFFFFFFFFFFFFFFFh
0x1400017ae  xor     edi, edi
0x1400017b0  mov     rbx, r8
0x1400017b3  mov     r9d, 2
0x1400017b9  mov     rcx, [rax]
0x1400017bc  test    rcx, rcx
0x1400017bf  jz      short loc_1400017D6
0x1400017c1  mov     rax, rdx
0x1400017c4  inc     rax
0x1400017c7  cmp     [rcx+rax*2], di
0x1400017cb  jnz     short loc_1400017C4
0x1400017cd  lea     eax, ds:2[rax*2]
0x1400017d4  jmp     short loc_1400017E0
0x1400017d6  lea     rcx, dword_140015CE4
0x1400017dd  mov     eax, r9d
0x1400017e0  mov     [rbp+70h+var_38], eax
0x1400017e3  lea     rsi, byte_140015CE0
0x1400017ea  mov     rax, [rbp+70h+arg_88]
0x1400017f1  mov     r8d, 1
0x1400017f7  mov     [rbp+70h+var_40], rcx
0x1400017fb  mov     [rbp+70h+var_34], edi
0x1400017fe  mov     rcx, [rax]
0x140001801  test    rcx, rcx
0x140001804  jz      short loc_140001816
0x140001806  mov     rax, rdx
0x140001809  inc     rax
0x14000180c  cmp     [rcx+rax], dil
0x140001810  jnz     short loc_140001809
0x140001812  inc     eax
0x140001814  jmp     short loc_14000181C
0x140001816  mov     rcx, rsi
0x140001819  mov     eax, r8d
0x14000181c  mov     [rbp+70h+var_48], eax
0x14000181f  mov     rax, [rbp+70h+arg_80]
0x140001826  mov     [rbp+70h+var_60], rax
0x14000182a  mov     rax, [rbp+70h+arg_78]
0x140001831  mov     [rbp+70h+var_50], rcx
0x140001835  mov     [rbp+70h+var_44], edi
0x140001838  mov     [rbp+70h+var_58], 4
0x140001840  mov     rcx, [rax]
0x140001843  test    rcx, rcx
0x140001846  jz      short loc_14000185D
0x140001848  mov     rax, rdx
0x14000184b  inc     rax
0x14000184e  cmp     [rcx+rax*2], di
0x140001852  jnz     short loc_14000184B
0x140001854  lea     eax, ds:2[rax*2]
0x14000185b  jmp     short loc_140001867
0x14000185d  lea     rcx, dword_140015CE4
0x140001864  mov     eax, r9d
0x140001867  mov     [rbp+70h+var_68], eax
0x14000186a  mov     rax, [rbp+70h+arg_70]
0x140001871  mov     [rbp+70h+var_70], rcx
0x140001875  mov     [rbp+70h+var_64], edi
0x140001878  mov     rcx, [rax]
0x14000187b  test    rcx, rcx
0x14000187e  jz      short loc_140001890
0x140001880  mov     rax, rdx
0x140001883  inc     rax
0x140001886  cmp     [rcx+rax], dil
0x14000188a  jnz     short loc_140001883
0x14000188c  inc     eax
0x14000188e  jmp     short loc_140001896
0x140001890  mov     rcx, rsi
0x140001893  mov     eax, r8d
0x140001896  mov     [rbp+70h+var_78], eax
0x140001899  mov     rax, [rbp+70h+arg_68]
0x1400018a0  mov     [rbp+70h+var_90], rax
0x1400018a4  mov     rax, [rbp+70h+arg_60]
0x1400018ab  mov     [rbp+70h+var_80], rcx
0x1400018af  mov     [rbp+70h+var_74], edi
0x1400018b2  mov     [rbp+70h+var_88], 4
0x1400018ba  mov     rcx, [rax]
0x1400018bd  test    rcx, rcx
0x1400018c0  jz      short loc_1400018D2
0x1400018c2  mov     rax, rdx
0x1400018c5  inc     rax
0x1400018c8  cmp     [rcx+rax], dil
0x1400018cc  jnz     short loc_1400018C5
0x1400018ce  inc     eax
0x1400018d0  jmp     short loc_1400018D8
0x1400018d2  mov     rcx, rsi
0x1400018d5  mov     eax, r8d
0x1400018d8  mov     [rbp+70h+var_98], eax
0x1400018db  mov     rax, [rbp+70h+arg_58]
0x1400018e2  mov     [rbp+70h+var_B0], rax
0x1400018e6  mov     rax, [rbp+70h+arg_50]
0x1400018ed  mov     [rbp+70h+var_A0], rcx
0x1400018f1  mov     [rbp+70h+var_94], edi
0x1400018f4  mov     [rbp+70h+var_A8], 4
0x1400018fc  mov     rcx, [rax]
0x1400018ff  test    rcx, rcx
0x140001902  jz      short loc_14000191A
0x140001904  mov     rax, rdx
0x140001907  inc     rax
0x14000190a  cmp     [rcx+rax*2], di
0x14000190e  jnz     short loc_140001907
0x140001910  lea     r9d, ds:2[rax*2]
0x140001918  jmp     short loc_140001921
0x14000191a  lea     rcx, dword_140015CE4
0x140001921  mov     rax, [rbp+70h+arg_48]
0x140001928  mov     [rbp+70h+var_D0], rax
0x14000192c  mov     rax, [rbp+70h+arg_40]
0x140001933  mov     [rbp+70h+var_C0], rcx
0x140001937  mov     [rbp+70h+var_B8], r9d
0x14000193b  mov     [rbp+70h+var_B4], edi
0x14000193e  mov     rcx, [rax]
0x140001941  mov     [rbp+70h+var_C8], 4
0x140001949  test    rcx, rcx
0x14000194c  jz      short loc_14000195E
0x14000194e  mov     rax, rdx
0x140001951  inc     rax
0x140001954  cmp     [rcx+rax], dil
0x140001958  jnz     short loc_140001951
0x14000195a  inc     eax
0x14000195c  jmp     short loc_140001964
0x14000195e  mov     rcx, rsi
0x140001961  mov     eax, r8d
0x140001964  mov     [rbp+70h+var_D8], eax
0x140001967  mov     rax, [rbp+70h+arg_38]
0x14000196e  mov     [rbp+70h+var_F0], rax
0x140001972  mov     rax, [rbp+70h+arg_30]
0x140001979  mov     [rbp+70h+var_E0], rcx
0x14000197d  mov     [rbp+70h+var_D4], edi
0x140001980  mov     [rbp+70h+var_E8], 4
0x140001988  mov     rcx, [rax]
0x14000198b  test    rcx, rcx
0x14000198e  jz      short loc_14000199F
0x140001990  inc     rdx
0x140001993  cmp     [rcx+rdx], dil
0x140001997  jnz     short loc_140001990
0x140001999  lea     r8d, [rdx+1]
0x14000199d  jmp     short loc_1400019A2
0x14000199f  mov     rcx, rsi
0x1400019a2  mov     rax, [rbp+70h+arg_28]
0x1400019a9  xor     r9d, r9d
0x1400019ac  mov     [rsp+170h+var_110], rax
0x1400019b1  mov     rdx, r11
0x1400019b4  mov     rax, [rbp+70h+arg_20]
0x1400019bb  mov     [rsp+170h+var_120], rax
0x1400019c0  lea     rax, [rsp+170h+var_140]
0x1400019c5  mov     [rsp+170h+var_100], rcx
0x1400019ca  mov     rcx, r10
0x1400019cd  mov     [rsp+170h+var_F8], r8d
0x1400019d2  mov     r8, rbx
0x1400019d5  mov     [rsp+170h+var_148], rax
0x1400019da  mov     [rsp+170h+var_150], 11h
0x1400019e2  mov     [rsp+170h+var_F4], edi
0x1400019e6  mov     [rsp+170h+var_108], 4
0x1400019ef  mov     [rsp+170h+var_118], 8
0x1400019f8  call    _tlgWriteTransfer_EventWriteTransfer
0x1400019fd  mov     rcx, [rbp+70h+var_30]
0x140001a01  xor     rcx, rsp; StackCookie
0x140001a04  call    __security_check_cookie
0x140001a09  add     rsp, 150h
0x140001a10  pop     r14
0x140001a12  pop     rdi
0x140001a13  pop     rsi
0x140001a14  pop     rbx
0x140001a15  pop     rbp
0x140001a16  retn
```
