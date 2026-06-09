# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)

- ea: `0x180001ae0`
- end: `0x180001dd0`
- name: `??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456445@Z`
- size: `752`
- prototype: `__int64 __usercall@<rax>(int@<ecx>, int@<edx>, int@<r8d>, __int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x180010790`
- `0x180010edc`

## callees

- `0x180001ae0`
- `0x180001f68`
- `0x180002620`

## pseudocode

```c
ULONG __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
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
        const WCHAR **a11,
        __int64 a12,
        const unsigned __int16 **a13,
        __int64 a14,
        const unsigned __int16 **a15,
        const WCHAR **a16,
        __int64 a17,
        const unsigned __int16 **a18,
        const WCHAR **a19,
        __int64 a20,
        __int64 a21,
        const unsigned __int16 **a22)
{
  __int64 v24; // rdx
  int v26; // r8d
  const unsigned __int16 *v27; // rcx
  __int64 v28; // rax
  int v29; // eax
  int v30; // r9d
  const WCHAR *v31; // rcx
  __int64 v32; // rax
  int v33; // eax
  const unsigned __int16 *v34; // rcx
  __int64 v35; // rax
  int v36; // eax
  const WCHAR *v37; // rcx
  __int64 v38; // rax
  int v39; // eax
  const unsigned __int16 *v40; // rcx
  __int64 v41; // rax
  int v42; // eax
  const unsigned __int16 *v43; // rcx
  __int64 v44; // rax
  int v45; // eax
  const WCHAR *v46; // rcx
  __int64 v47; // rax
  const unsigned __int16 *v48; // rcx
  __int64 v49; // rax
  int v50; // eax
  const unsigned __int16 *v51; // rcx
  struct _EVENT_DATA_DESCRIPTOR v53; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v54; // [rsp+50h] [rbp-B0h]
  __int64 v55; // [rsp+58h] [rbp-A8h]
  __int64 v56; // [rsp+60h] [rbp-A0h]
  __int64 v57; // [rsp+68h] [rbp-98h]
  const unsigned __int16 *v58; // [rsp+70h] [rbp-90h]
  int v59; // [rsp+78h] [rbp-88h]
  int v60; // [rsp+7Ch] [rbp-84h]
  __int64 v61; // [rsp+80h] [rbp-80h]
  __int64 v62; // [rsp+88h] [rbp-78h]
  const unsigned __int16 *v63; // [rsp+90h] [rbp-70h]
  int v64; // [rsp+98h] [rbp-68h]
  int v65; // [rsp+9Ch] [rbp-64h]
  __int64 v66; // [rsp+A0h] [rbp-60h]
  __int64 v67; // [rsp+A8h] [rbp-58h]
  const WCHAR *v68; // [rsp+B0h] [rbp-50h]
  int v69; // [rsp+B8h] [rbp-48h]
  int v70; // [rsp+BCh] [rbp-44h]
  __int64 v71; // [rsp+C0h] [rbp-40h]
  __int64 v72; // [rsp+C8h] [rbp-38h]
  const unsigned __int16 *v73; // [rsp+D0h] [rbp-30h]
  int v74; // [rsp+D8h] [rbp-28h]
  int v75; // [rsp+DCh] [rbp-24h]
  __int64 v76; // [rsp+E0h] [rbp-20h]
  __int64 v77; // [rsp+E8h] [rbp-18h]
  const unsigned __int16 *v78; // [rsp+F0h] [rbp-10h]
  int v79; // [rsp+F8h] [rbp-8h]
  int v80; // [rsp+FCh] [rbp-4h]
  const WCHAR *v81; // [rsp+100h] [rbp+0h]
  int v82; // [rsp+108h] [rbp+8h]
  int v83; // [rsp+10Ch] [rbp+Ch]
  __int64 v84; // [rsp+110h] [rbp+10h]
  __int64 v85; // [rsp+118h] [rbp+18h]
  const unsigned __int16 *v86; // [rsp+120h] [rbp+20h]
  int v87; // [rsp+128h] [rbp+28h]
  int v88; // [rsp+12Ch] [rbp+2Ch]
  const WCHAR *v89; // [rsp+130h] [rbp+30h]
  int v90; // [rsp+138h] [rbp+38h]
  int v91; // [rsp+13Ch] [rbp+3Ch]
  __int64 v92; // [rsp+140h] [rbp+40h]
  __int64 v93; // [rsp+148h] [rbp+48h]
  __int64 v94; // [rsp+150h] [rbp+50h]
  __int64 v95; // [rsp+158h] [rbp+58h]
  const unsigned __int16 *v96; // [rsp+160h] [rbp+60h]
  int v97; // [rsp+168h] [rbp+68h]
  int v98; // [rsp+16Ch] [rbp+6Ch]

  v24 = -1;
  v26 = 1;
  v27 = *a22;
  if ( *a22 )
  {
    v28 = -1;
    do
      ++v28;
    while ( *((_BYTE *)v27 + v28) );
    v29 = v28 + 1;
  }
  else
  {
    v27 = &word_18001582A;
    v29 = 1;
  }
  v97 = v29;
  v30 = 2;
  v94 = a21;
  v92 = a20;
  v96 = v27;
  v98 = 0;
  v95 = 4;
  v31 = *a19;
  v93 = 4;
  if ( v31 )
  {
    v32 = -1;
    do
      ++v32;
    while ( v31[v32] );
    v33 = 2 * v32 + 2;
  }
  else
  {
    v31 = &psz;
    v33 = 2;
  }
  v90 = v33;
  v89 = v31;
  v91 = 0;
  v34 = *a18;
  if ( *a18 )
  {
    v35 = -1;
    do
      ++v35;
    while ( *((_BYTE *)v34 + v35) );
    v36 = v35 + 1;
  }
  else
  {
    v34 = &word_18001582A;
    v36 = 1;
  }
  v87 = v36;
  v84 = a17;
  v86 = v34;
  v88 = 0;
  v85 = 4;
  v37 = *a16;
  if ( *a16 )
  {
    v38 = -1;
    do
      ++v38;
    while ( v37[v38] );
    v39 = 2 * v38 + 2;
  }
  else
  {
    v37 = &psz;
    v39 = 2;
  }
  v82 = v39;
  v81 = v37;
  v83 = 0;
  v40 = *a15;
  if ( *a15 )
  {
    v41 = -1;
    do
      ++v41;
    while ( *((_BYTE *)v40 + v41) );
    v42 = v41 + 1;
  }
  else
  {
    v40 = &word_18001582A;
    v42 = 1;
  }
  v79 = v42;
  v76 = a14;
  v78 = v40;
  v80 = 0;
  v77 = 4;
  v43 = *a13;
  if ( *a13 )
  {
    v44 = -1;
    do
      ++v44;
    while ( *((_BYTE *)v43 + v44) );
    v45 = v44 + 1;
  }
  else
  {
    v43 = &word_18001582A;
    v45 = 1;
  }
  v74 = v45;
  v71 = a12;
  v73 = v43;
  v75 = 0;
  v72 = 4;
  v46 = *a11;
  if ( *a11 )
  {
    v47 = -1;
    do
      ++v47;
    while ( v46[v47] );
    v30 = 2 * v47 + 2;
  }
  else
  {
    v46 = &psz;
  }
  v66 = a10;
  v68 = v46;
  v69 = v30;
  v70 = 0;
  v48 = *a9;
  v67 = 4;
  if ( v48 )
  {
    v49 = -1;
    do
      ++v49;
    while ( *((_BYTE *)v48 + v49) );
    v50 = v49 + 1;
  }
  else
  {
    v48 = &word_18001582A;
    v50 = 1;
  }
  v64 = v50;
  v61 = a8;
  v63 = v48;
  v65 = 0;
  v62 = 4;
  v51 = *a7;
  if ( *a7 )
  {
    do
      ++v24;
    while ( *((_BYTE *)v51 + v24) );
    v26 = v24 + 1;
  }
  else
  {
    v51 = &word_18001582A;
  }
  v56 = a6;
  v54 = a5;
  v58 = v51;
  v59 = v26;
  v60 = 0;
  v57 = 4;
  v55 = 8;
  return tlgWriteTransfer_EventWriteTransfer(a1, a2, a3, 0, 0x14u, &v53);
}

```

## disassembly

```asm
0x180001ae0  push    rbp
0x180001ae2  push    rbx
0x180001ae3  push    rsi
0x180001ae4  push    rdi
0x180001ae5  push    r15
0x180001ae7  lea     rbp, [rsp-80h]
0x180001aec  sub     rsp, 180h
0x180001af3  mov     rax, cs:__security_cookie
0x180001afa  xor     rax, rsp
0x180001afd  mov     [rbp+0A0h+var_30], rax
0x180001b01  mov     rax, [rbp+0A0h+arg_A8]
0x180001b08  lea     rsi, word_18001582A
0x180001b0f  mov     r11, rdx
0x180001b12  mov     r10, rcx
0x180001b15  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180001b19  xor     edi, edi
0x180001b1b  mov     rbx, r8
0x180001b1e  mov     r8d, 1
0x180001b24  mov     rcx, [rax]
0x180001b27  test    rcx, rcx
0x180001b2a  jz      short loc_180001B3C
0x180001b2c  mov     rax, rdx
0x180001b2f  inc     rax
0x180001b32  cmp     [rcx+rax], dil
0x180001b36  jnz     short loc_180001B2F
0x180001b38  inc     eax
0x180001b3a  jmp     short loc_180001B42
0x180001b3c  mov     rcx, rsi
0x180001b3f  mov     eax, r8d
0x180001b42  mov     [rbp+0A0h+var_38], eax
0x180001b45  mov     r9d, 2
0x180001b4b  mov     rax, [rbp+0A0h+arg_A0]
0x180001b52  mov     [rbp+0A0h+var_50], rax
0x180001b56  mov     rax, [rbp+0A0h+arg_98]
0x180001b5d  mov     [rbp+0A0h+var_60], rax
0x180001b61  mov     rax, [rbp+0A0h+arg_90]
0x180001b68  mov     [rbp+0A0h+var_40], rcx
0x180001b6c  mov     [rbp+0A0h+var_34], edi
0x180001b6f  mov     [rbp+0A0h+var_48], 4
0x180001b77  mov     rcx, [rax]
0x180001b7a  mov     [rbp+0A0h+var_58], 4
0x180001b82  test    rcx, rcx
0x180001b85  jz      short loc_180001B9C
0x180001b87  mov     rax, rdx
0x180001b8a  inc     rax
0x180001b8d  cmp     [rcx+rax*2], di
0x180001b91  jnz     short loc_180001B8A
0x180001b93  lea     eax, ds:2[rax*2]
0x180001b9a  jmp     short loc_180001BA6
0x180001b9c  lea     rcx, psz
0x180001ba3  mov     eax, r9d
0x180001ba6  mov     [rbp+0A0h+var_68], eax
0x180001ba9  mov     rax, [rbp+0A0h+arg_88]
0x180001bb0  mov     [rbp+0A0h+var_70], rcx
0x180001bb4  mov     [rbp+0A0h+var_64], edi
0x180001bb7  mov     rcx, [rax]
0x180001bba  test    rcx, rcx
0x180001bbd  jz      short loc_180001BCF
0x180001bbf  mov     rax, rdx
0x180001bc2  inc     rax
0x180001bc5  cmp     [rcx+rax], dil
0x180001bc9  jnz     short loc_180001BC2
0x180001bcb  inc     eax
0x180001bcd  jmp     short loc_180001BD5
0x180001bcf  mov     rcx, rsi
0x180001bd2  mov     eax, r8d
0x180001bd5  mov     [rbp+0A0h+var_78], eax
0x180001bd8  mov     rax, [rbp+0A0h+arg_80]
0x180001bdf  mov     [rbp+0A0h+var_90], rax
0x180001be3  mov     rax, [rbp+0A0h+arg_78]
0x180001bea  mov     [rbp+0A0h+var_80], rcx
0x180001bee  mov     [rbp+0A0h+var_74], edi
0x180001bf1  mov     [rbp+0A0h+var_88], 4
0x180001bf9  mov     rcx, [rax]
0x180001bfc  test    rcx, rcx
0x180001bff  jz      short loc_180001C16
0x180001c01  mov     rax, rdx
0x180001c04  inc     rax
0x180001c07  cmp     [rcx+rax*2], di
0x180001c0b  jnz     short loc_180001C04
0x180001c0d  lea     eax, ds:2[rax*2]
0x180001c14  jmp     short loc_180001C20
0x180001c16  lea     rcx, psz
0x180001c1d  mov     eax, r9d
0x180001c20  mov     [rbp+0A0h+var_98], eax
0x180001c23  mov     rax, [rbp+0A0h+arg_70]
0x180001c2a  mov     [rbp+0A0h+var_A0], rcx
0x180001c2e  mov     [rbp+0A0h+var_94], edi
0x180001c31  mov     rcx, [rax]
0x180001c34  test    rcx, rcx
0x180001c37  jz      short loc_180001C49
0x180001c39  mov     rax, rdx
0x180001c3c  inc     rax
0x180001c3f  cmp     [rcx+rax], dil
0x180001c43  jnz     short loc_180001C3C
0x180001c45  inc     eax
0x180001c47  jmp     short loc_180001C4F
0x180001c49  mov     rcx, rsi
0x180001c4c  mov     eax, r8d
0x180001c4f  mov     [rbp+0A0h+var_A8], eax
0x180001c52  mov     rax, [rbp+0A0h+arg_68]
0x180001c59  mov     [rbp+0A0h+var_C0], rax
0x180001c5d  mov     rax, [rbp+0A0h+arg_60]
0x180001c64  mov     [rbp+0A0h+var_B0], rcx
0x180001c68  mov     [rbp+0A0h+var_A4], edi
0x180001c6b  mov     [rbp+0A0h+var_B8], 4
0x180001c73  mov     rcx, [rax]
0x180001c76  test    rcx, rcx
0x180001c79  jz      short loc_180001C8B
0x180001c7b  mov     rax, rdx
0x180001c7e  inc     rax
0x180001c81  cmp     [rcx+rax], dil
0x180001c85  jnz     short loc_180001C7E
0x180001c87  inc     eax
0x180001c89  jmp     short loc_180001C91
0x180001c8b  mov     rcx, rsi
0x180001c8e  mov     eax, r8d
0x180001c91  mov     [rbp+0A0h+var_C8], eax
0x180001c94  mov     rax, [rbp+0A0h+arg_58]
0x180001c9b  mov     [rbp+0A0h+var_E0], rax
0x180001c9f  mov     rax, [rbp+0A0h+arg_50]
0x180001ca6  mov     [rbp+0A0h+var_D0], rcx
0x180001caa  mov     [rbp+0A0h+var_C4], edi
0x180001cad  mov     [rbp+0A0h+var_D8], 4
0x180001cb5  mov     rcx, [rax]
0x180001cb8  test    rcx, rcx
0x180001cbb  jz      short loc_180001CD3
0x180001cbd  mov     rax, rdx
0x180001cc0  inc     rax
0x180001cc3  cmp     [rcx+rax*2], di
0x180001cc7  jnz     short loc_180001CC0
0x180001cc9  lea     r9d, ds:2[rax*2]
0x180001cd1  jmp     short loc_180001CDA
0x180001cd3  lea     rcx, psz
0x180001cda  mov     rax, [rbp+0A0h+arg_48]
0x180001ce1  mov     [rbp+0A0h+var_100], rax
0x180001ce5  mov     rax, [rbp+0A0h+arg_40]
0x180001cec  mov     [rbp+0A0h+var_F0], rcx
0x180001cf0  mov     [rbp+0A0h+var_E8], r9d
0x180001cf4  mov     [rbp+0A0h+var_E4], edi
0x180001cf7  mov     rcx, [rax]
0x180001cfa  mov     [rbp+0A0h+var_F8], 4
0x180001d02  test    rcx, rcx
0x180001d05  jz      short loc_180001D17
0x180001d07  mov     rax, rdx
0x180001d0a  inc     rax
0x180001d0d  cmp     [rcx+rax], dil
0x180001d11  jnz     short loc_180001D0A
0x180001d13  inc     eax
0x180001d15  jmp     short loc_180001D1D
0x180001d17  mov     rcx, rsi
0x180001d1a  mov     eax, r8d
0x180001d1d  mov     [rbp+0A0h+var_108], eax
0x180001d20  mov     rax, [rbp+0A0h+arg_38]
0x180001d27  mov     [rbp+0A0h+var_120], rax
0x180001d2b  mov     rax, [rbp+0A0h+arg_30]
0x180001d32  mov     [rbp+0A0h+var_110], rcx
0x180001d36  mov     [rbp+0A0h+var_104], edi
0x180001d39  mov     [rbp+0A0h+var_118], 4
0x180001d41  mov     rcx, [rax]
0x180001d44  test    rcx, rcx
0x180001d47  jz      short loc_180001D58
0x180001d49  inc     rdx
0x180001d4c  cmp     [rcx+rdx], dil
0x180001d50  jnz     short loc_180001D49
0x180001d52  lea     r8d, [rdx+1]
0x180001d56  jmp     short loc_180001D5B
0x180001d58  mov     rcx, rsi
0x180001d5b  mov     rax, [rbp+0A0h+arg_28]
0x180001d62  xor     r9d, r9d; int
0x180001d65  mov     [rsp+1A0h+var_140], rax
0x180001d6a  mov     rdx, r11; int
0x180001d6d  mov     rax, [rbp+0A0h+arg_20]
0x180001d74  mov     [rsp+1A0h+var_150], rax
0x180001d79  lea     rax, [rsp+1A0h+var_170]
0x180001d7e  mov     [rsp+1A0h+var_130], rcx
0x180001d83  mov     rcx, r10; int
0x180001d86  mov     [rsp+1A0h+var_128], r8d
0x180001d8b  mov     r8, rbx; int
0x180001d8e  mov     [rsp+1A0h+var_178], rax; PEVENT_DATA_DESCRIPTOR
0x180001d93  mov     [rsp+1A0h+var_180], 14h; ULONG
0x180001d9b  mov     [rsp+1A0h+var_124], edi
0x180001d9f  mov     [rsp+1A0h+var_138], 4
0x180001da8  mov     [rsp+1A0h+var_148], 8
0x180001db1  call    _tlgWriteTransfer_EventWriteTransfer
0x180001db6  mov     rcx, [rbp+0A0h+var_30]
0x180001dba  xor     rcx, rsp; StackCookie
0x180001dbd  call    __security_check_cookie
0x180001dc2  add     rsp, 180h
0x180001dc9  pop     r15
0x180001dcb  pop     rdi
0x180001dcc  pop     rsi
0x180001dcd  pop     rbx
0x180001dce  pop     rbp
0x180001dcf  retn
```
