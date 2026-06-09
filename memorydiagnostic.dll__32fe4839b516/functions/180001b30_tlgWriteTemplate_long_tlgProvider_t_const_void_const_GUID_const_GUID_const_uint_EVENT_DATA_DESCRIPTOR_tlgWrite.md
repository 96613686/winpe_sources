# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)

- ea: `0x180001b30`
- end: `0x180001e40`
- name: `??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456445@Z`
- size: `784`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18001e900`

## callees

- `0x180001a8c`
- `0x180001b30`
- `0x1800026b0`

## pseudocode

```c
ULONG __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
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
        void **a20,
        __int64 a21,
        __int64 a22,
        const unsigned __int16 **a23)
{
  __int64 v24; // rdx
  const unsigned __int16 *v25; // r8
  __int64 v26; // rax
  int v27; // eax
  int v28; // r9d
  _WORD *v29; // r8
  __int64 v30; // rax
  int v31; // eax
  const unsigned __int16 *v32; // r8
  __int64 v33; // rax
  int v34; // eax
  _WORD *v35; // r8
  __int64 v36; // rax
  int v37; // eax
  const unsigned __int16 *v38; // r8
  __int64 v39; // rax
  int v40; // eax
  const unsigned __int16 *v41; // r8
  __int64 v42; // rax
  int v43; // eax
  _WORD *v44; // r8
  __int64 v45; // rax
  const unsigned __int16 *v46; // r8
  __int64 v47; // rax
  int v48; // eax
  const unsigned __int16 *v49; // r8
  int v50; // edx
  struct _EVENT_DATA_DESCRIPTOR v52; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v53; // [rsp+50h] [rbp-B0h]
  __int64 v54; // [rsp+58h] [rbp-A8h]
  __int64 v55; // [rsp+60h] [rbp-A0h]
  __int64 v56; // [rsp+68h] [rbp-98h]
  __int64 v57; // [rsp+70h] [rbp-90h]
  __int64 v58; // [rsp+78h] [rbp-88h]
  const unsigned __int16 *v59; // [rsp+80h] [rbp-80h]
  int v60; // [rsp+88h] [rbp-78h]
  int v61; // [rsp+8Ch] [rbp-74h]
  __int64 v62; // [rsp+90h] [rbp-70h]
  __int64 v63; // [rsp+98h] [rbp-68h]
  const unsigned __int16 *v64; // [rsp+A0h] [rbp-60h]
  int v65; // [rsp+A8h] [rbp-58h]
  int v66; // [rsp+ACh] [rbp-54h]
  __int64 v67; // [rsp+B0h] [rbp-50h]
  __int64 v68; // [rsp+B8h] [rbp-48h]
  _WORD *v69; // [rsp+C0h] [rbp-40h]
  int v70; // [rsp+C8h] [rbp-38h]
  int v71; // [rsp+CCh] [rbp-34h]
  __int64 v72; // [rsp+D0h] [rbp-30h]
  __int64 v73; // [rsp+D8h] [rbp-28h]
  const unsigned __int16 *v74; // [rsp+E0h] [rbp-20h]
  int v75; // [rsp+E8h] [rbp-18h]
  int v76; // [rsp+ECh] [rbp-14h]
  __int64 v77; // [rsp+F0h] [rbp-10h]
  __int64 v78; // [rsp+F8h] [rbp-8h]
  const unsigned __int16 *v79; // [rsp+100h] [rbp+0h]
  int v80; // [rsp+108h] [rbp+8h]
  int v81; // [rsp+10Ch] [rbp+Ch]
  _WORD *v82; // [rsp+110h] [rbp+10h]
  int v83; // [rsp+118h] [rbp+18h]
  int v84; // [rsp+11Ch] [rbp+1Ch]
  __int64 v85; // [rsp+120h] [rbp+20h]
  __int64 v86; // [rsp+128h] [rbp+28h]
  const unsigned __int16 *v87; // [rsp+130h] [rbp+30h]
  int v88; // [rsp+138h] [rbp+38h]
  int v89; // [rsp+13Ch] [rbp+3Ch]
  _WORD *v90; // [rsp+140h] [rbp+40h]
  int v91; // [rsp+148h] [rbp+48h]
  int v92; // [rsp+14Ch] [rbp+4Ch]
  __int64 v93; // [rsp+150h] [rbp+50h]
  __int64 v94; // [rsp+158h] [rbp+58h]
  __int64 v95; // [rsp+160h] [rbp+60h]
  __int64 v96; // [rsp+168h] [rbp+68h]
  const unsigned __int16 *v97; // [rsp+170h] [rbp+70h]
  int v98; // [rsp+178h] [rbp+78h]
  int v99; // [rsp+17Ch] [rbp+7Ch]

  v24 = -1;
  v25 = *a23;
  if ( *a23 )
  {
    v26 = -1;
    do
      ++v26;
    while ( *((_BYTE *)v25 + v26) );
    v27 = v26 + 1;
  }
  else
  {
    v25 = &word_1800261C0;
    v27 = 1;
  }
  v98 = v27;
  v28 = 2;
  v95 = a22;
  v93 = a21;
  v97 = v25;
  v99 = 0;
  v96 = 4;
  v29 = *a20;
  v94 = 4;
  if ( v29 )
  {
    v30 = -1;
    do
      ++v30;
    while ( v29[v30] );
    v31 = 2 * v30 + 2;
  }
  else
  {
    v29 = &unk_1800261C4;
    v31 = 2;
  }
  v91 = v31;
  v90 = v29;
  v92 = 0;
  v32 = *a19;
  if ( *a19 )
  {
    v33 = -1;
    do
      ++v33;
    while ( *((_BYTE *)v32 + v33) );
    v34 = v33 + 1;
  }
  else
  {
    v32 = &word_1800261C0;
    v34 = 1;
  }
  v88 = v34;
  v85 = a18;
  v87 = v32;
  v89 = 0;
  v86 = 4;
  v35 = *a17;
  if ( *a17 )
  {
    v36 = -1;
    do
      ++v36;
    while ( v35[v36] );
    v37 = 2 * v36 + 2;
  }
  else
  {
    v35 = &unk_1800261C4;
    v37 = 2;
  }
  v83 = v37;
  v82 = v35;
  v84 = 0;
  v38 = *a16;
  if ( *a16 )
  {
    v39 = -1;
    do
      ++v39;
    while ( *((_BYTE *)v38 + v39) );
    v40 = v39 + 1;
  }
  else
  {
    v38 = &word_1800261C0;
    v40 = 1;
  }
  v80 = v40;
  v77 = a15;
  v79 = v38;
  v81 = 0;
  v78 = 4;
  v41 = *a14;
  if ( *a14 )
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
  v75 = v43;
  v72 = a13;
  v74 = v41;
  v76 = 0;
  v73 = 4;
  v44 = *a12;
  if ( *a12 )
  {
    v45 = -1;
    do
      ++v45;
    while ( v44[v45] );
    v28 = 2 * v45 + 2;
  }
  else
  {
    v44 = &unk_1800261C4;
  }
  v67 = a11;
  v69 = v44;
  v70 = v28;
  v71 = 0;
  v46 = *a10;
  v68 = 4;
  if ( v46 )
  {
    v47 = -1;
    do
      ++v47;
    while ( *((_BYTE *)v46 + v47) );
    v48 = v47 + 1;
  }
  else
  {
    v46 = &word_1800261C0;
    v48 = 1;
  }
  v65 = v48;
  v62 = a9;
  v64 = v46;
  v66 = 0;
  v63 = 4;
  v49 = *a8;
  if ( *a8 )
  {
    do
      ++v24;
    while ( *((_BYTE *)v49 + v24) );
    v50 = v24 + 1;
  }
  else
  {
    v49 = &word_1800261C0;
    v50 = 1;
  }
  v57 = a7;
  v55 = a6;
  v53 = a5;
  v59 = v49;
  v60 = v50;
  v61 = 0;
  v58 = 4;
  v56 = 8;
  v54 = 8;
  return tlgWriteTransfer_EventWriteTransfer(a1, a2, 0, 0, 0x15u, &v52);
}

```

## disassembly

```asm
0x180001b30  mov     [rsp-8+arg_10], rbx
0x180001b35  push    rbp
0x180001b36  push    rsi
0x180001b37  push    rdi
0x180001b38  lea     rbp, [rsp-90h]
0x180001b40  sub     rsp, 190h
0x180001b47  mov     rax, cs:__security_cookie
0x180001b4e  xor     rax, rsp
0x180001b51  mov     [rbp+0A0h+var_20], rax
0x180001b58  mov     rax, [rbp+0A0h+arg_B0]
0x180001b5f  lea     rdi, word_1800261C0
0x180001b66  mov     r11, rdx
0x180001b69  xor     ebx, ebx
0x180001b6b  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180001b6f  mov     r10, rcx
0x180001b72  mov     r8, [rax]
0x180001b75  test    r8, r8
0x180001b78  jz      short loc_180001B8F
0x180001b7a  mov     rax, rdx
0x180001b7d  inc     rax
0x180001b80  cmp     [r8+rax], bl
0x180001b84  jnz     short loc_180001B7D
0x180001b86  mov     ecx, 1
0x180001b8b  add     eax, ecx
0x180001b8d  jmp     short loc_180001B99
0x180001b8f  mov     ecx, 1
0x180001b94  mov     r8, rdi
0x180001b97  mov     eax, ecx
0x180001b99  mov     [rbp+0A0h+var_28], eax
0x180001b9c  mov     r9d, 2
0x180001ba2  mov     rax, [rbp+0A0h+arg_A8]
0x180001ba9  mov     [rbp+0A0h+var_40], rax
0x180001bad  mov     rax, [rbp+0A0h+arg_A0]
0x180001bb4  mov     [rbp+0A0h+var_50], rax
0x180001bb8  mov     rax, [rbp+0A0h+arg_98]
0x180001bbf  mov     [rbp+0A0h+var_30], r8
0x180001bc3  mov     [rbp+0A0h+var_24], ebx
0x180001bc6  mov     [rbp+0A0h+var_38], 4
0x180001bce  mov     r8, [rax]
0x180001bd1  mov     [rbp+0A0h+var_48], 4
0x180001bd9  test    r8, r8
0x180001bdc  jz      short loc_180001BF4
0x180001bde  mov     rax, rdx
0x180001be1  inc     rax
0x180001be4  cmp     [r8+rax*2], bx
0x180001be9  jnz     short loc_180001BE1
0x180001beb  lea     eax, ds:2[rax*2]
0x180001bf2  jmp     short loc_180001BFE
0x180001bf4  lea     r8, unk_1800261C4
0x180001bfb  mov     eax, r9d
0x180001bfe  mov     [rbp+0A0h+var_58], eax
0x180001c01  mov     rax, [rbp+0A0h+arg_90]
0x180001c08  mov     [rbp+0A0h+var_60], r8
0x180001c0c  mov     [rbp+0A0h+var_54], ebx
0x180001c0f  mov     r8, [rax]
0x180001c12  test    r8, r8
0x180001c15  jz      short loc_180001C27
0x180001c17  mov     rax, rdx
0x180001c1a  inc     rax
0x180001c1d  cmp     [r8+rax], bl
0x180001c21  jnz     short loc_180001C1A
0x180001c23  add     eax, ecx
0x180001c25  jmp     short loc_180001C2C
0x180001c27  mov     r8, rdi
0x180001c2a  mov     eax, ecx
0x180001c2c  mov     [rbp+0A0h+var_68], eax
0x180001c2f  mov     rax, [rbp+0A0h+arg_88]
0x180001c36  mov     [rbp+0A0h+var_80], rax
0x180001c3a  mov     rax, [rbp+0A0h+arg_80]
0x180001c41  mov     [rbp+0A0h+var_70], r8
0x180001c45  mov     [rbp+0A0h+var_64], ebx
0x180001c48  mov     [rbp+0A0h+var_78], 4
0x180001c50  mov     r8, [rax]
0x180001c53  test    r8, r8
0x180001c56  jz      short loc_180001C6E
0x180001c58  mov     rax, rdx
0x180001c5b  inc     rax
0x180001c5e  cmp     [r8+rax*2], bx
0x180001c63  jnz     short loc_180001C5B
0x180001c65  lea     eax, ds:2[rax*2]
0x180001c6c  jmp     short loc_180001C78
0x180001c6e  lea     r8, unk_1800261C4
0x180001c75  mov     eax, r9d
0x180001c78  mov     [rbp+0A0h+var_88], eax
0x180001c7b  mov     rax, [rbp+0A0h+arg_78]
0x180001c82  mov     [rbp+0A0h+var_90], r8
0x180001c86  mov     [rbp+0A0h+var_84], ebx
0x180001c89  mov     r8, [rax]
0x180001c8c  test    r8, r8
0x180001c8f  jz      short loc_180001CA1
0x180001c91  mov     rax, rdx
0x180001c94  inc     rax
0x180001c97  cmp     [r8+rax], bl
0x180001c9b  jnz     short loc_180001C94
0x180001c9d  add     eax, ecx
0x180001c9f  jmp     short loc_180001CA6
0x180001ca1  mov     r8, rdi
0x180001ca4  mov     eax, ecx
0x180001ca6  mov     [rbp+0A0h+var_98], eax
0x180001ca9  mov     rax, [rbp+0A0h+arg_70]
0x180001cb0  mov     [rbp+0A0h+var_B0], rax
0x180001cb4  mov     rax, [rbp+0A0h+arg_68]
0x180001cbb  mov     [rbp+0A0h+var_A0], r8
0x180001cbf  mov     [rbp+0A0h+var_94], ebx
0x180001cc2  mov     [rbp+0A0h+var_A8], 4
0x180001cca  mov     r8, [rax]
0x180001ccd  test    r8, r8
0x180001cd0  jz      short loc_180001CE2
0x180001cd2  mov     rax, rdx
0x180001cd5  inc     rax
0x180001cd8  cmp     [r8+rax], bl
0x180001cdc  jnz     short loc_180001CD5
0x180001cde  add     eax, ecx
0x180001ce0  jmp     short loc_180001CE7
0x180001ce2  mov     r8, rdi
0x180001ce5  mov     eax, ecx
0x180001ce7  mov     [rbp+0A0h+var_B8], eax
0x180001cea  mov     rax, [rbp+0A0h+arg_60]
0x180001cf1  mov     [rbp+0A0h+var_D0], rax
0x180001cf5  mov     rax, [rbp+0A0h+arg_58]
0x180001cfc  mov     [rbp+0A0h+var_C0], r8
0x180001d00  mov     [rbp+0A0h+var_B4], ebx
0x180001d03  mov     [rbp+0A0h+var_C8], 4
0x180001d0b  mov     r8, [rax]
0x180001d0e  test    r8, r8
0x180001d11  jz      short loc_180001D2A
0x180001d13  mov     rax, rdx
0x180001d16  inc     rax
0x180001d19  cmp     [r8+rax*2], bx
0x180001d1e  jnz     short loc_180001D16
0x180001d20  lea     r9d, ds:2[rax*2]
0x180001d28  jmp     short loc_180001D31
0x180001d2a  lea     r8, unk_1800261C4
0x180001d31  mov     rax, [rbp+0A0h+arg_50]
0x180001d38  mov     [rbp+0A0h+var_F0], rax
0x180001d3c  mov     rax, [rbp+0A0h+arg_48]
0x180001d43  mov     [rbp+0A0h+var_E0], r8
0x180001d47  mov     [rbp+0A0h+var_D8], r9d
0x180001d4b  mov     [rbp+0A0h+var_D4], ebx
0x180001d4e  mov     r8, [rax]
0x180001d51  mov     [rbp+0A0h+var_E8], 4
0x180001d59  test    r8, r8
0x180001d5c  jz      short loc_180001D6E
0x180001d5e  mov     rax, rdx
0x180001d61  inc     rax
0x180001d64  cmp     [r8+rax], bl
0x180001d68  jnz     short loc_180001D61
0x180001d6a  add     eax, ecx
0x180001d6c  jmp     short loc_180001D73
0x180001d6e  mov     r8, rdi
0x180001d71  mov     eax, ecx
0x180001d73  mov     [rbp+0A0h+var_F8], eax
0x180001d76  mov     rax, [rbp+0A0h+arg_40]
0x180001d7d  mov     [rbp+0A0h+var_110], rax
0x180001d81  mov     rax, [rbp+0A0h+arg_38]
0x180001d88  mov     [rbp+0A0h+var_100], r8
0x180001d8c  mov     [rbp+0A0h+var_F4], ebx
0x180001d8f  mov     [rbp+0A0h+var_108], 4
0x180001d97  mov     r8, [rax]
0x180001d9a  test    r8, r8
0x180001d9d  jz      short loc_180001DAC
0x180001d9f  inc     rdx
0x180001da2  cmp     [r8+rdx], bl
0x180001da6  jnz     short loc_180001D9F
0x180001da8  add     edx, ecx
0x180001daa  jmp     short loc_180001DB1
0x180001dac  mov     r8, rdi
0x180001daf  mov     edx, ecx
0x180001db1  mov     rax, [rbp+0A0h+arg_30]
0x180001db8  xor     r9d, r9d
0x180001dbb  mov     [rsp+1A0h+var_130], rax
0x180001dc0  mov     rcx, r10
0x180001dc3  mov     rax, [rbp+0A0h+arg_28]
0x180001dca  mov     [rsp+1A0h+var_140], rax
0x180001dcf  mov     rax, [rbp+0A0h+arg_20]
0x180001dd6  mov     [rsp+1A0h+var_150], rax
0x180001ddb  lea     rax, [rsp+1A0h+var_170]
0x180001de0  mov     [rbp+0A0h+var_120], r8
0x180001de4  xor     r8d, r8d
0x180001de7  mov     [rbp+0A0h+var_118], edx
0x180001dea  mov     rdx, r11
0x180001ded  mov     [rsp+1A0h+var_178], rax
0x180001df2  mov     [rsp+1A0h+var_180], 15h
0x180001dfa  mov     [rbp+0A0h+var_114], ebx
0x180001dfd  mov     [rsp+1A0h+var_128], 4
0x180001e06  mov     [rsp+1A0h+var_138], 8
0x180001e0f  mov     [rsp+1A0h+var_148], 8
0x180001e18  call    _tlgWriteTransfer_EventWriteTransfer
0x180001e1d  mov     rcx, [rbp+0A0h+var_20]
0x180001e24  xor     rcx, rsp; StackCookie
0x180001e27  call    __security_check_cookie
0x180001e2c  mov     rbx, [rsp+1A0h+arg_10]
0x180001e34  add     rsp, 190h
0x180001e3b  pop     rdi
0x180001e3c  pop     rsi
0x180001e3d  pop     rbp
0x180001e3e  retn
```
