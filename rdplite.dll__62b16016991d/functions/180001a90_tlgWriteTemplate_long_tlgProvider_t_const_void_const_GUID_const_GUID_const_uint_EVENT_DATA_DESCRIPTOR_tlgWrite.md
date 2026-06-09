# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)

- ea: `0x180001a90`
- end: `0x180001d7f`
- name: `??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456445@Z`
- size: `751`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18000bd88`

## callees

- `0x180001448`
- `0x180001a90`
- `0x1800036f0`

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
        __int64 **a11,
        __int64 a12,
        const unsigned __int16 **a13,
        __int64 a14,
        const unsigned __int16 **a15,
        __int64 **a16,
        __int64 a17,
        const unsigned __int16 **a18,
        __int64 **a19,
        __int64 a20,
        __int64 a21,
        const unsigned __int16 **a22)
{
  __int64 v24; // rdx
  int v25; // r8d
  const unsigned __int16 *v26; // rcx
  __int64 v27; // rax
  int v28; // eax
  int v29; // r9d
  __int64 *v30; // rcx
  __int64 v31; // rax
  int v32; // eax
  const unsigned __int16 *v33; // rcx
  __int64 v34; // rax
  int v35; // eax
  __int64 *v36; // rcx
  __int64 v37; // rax
  int v38; // eax
  const unsigned __int16 *v39; // rcx
  __int64 v40; // rax
  int v41; // eax
  const unsigned __int16 *v42; // rcx
  __int64 v43; // rax
  int v44; // eax
  __int64 *v45; // rcx
  __int64 v46; // rax
  const unsigned __int16 *v47; // rcx
  __int64 v48; // rax
  int v49; // eax
  const unsigned __int16 *v50; // rcx
  struct _EVENT_DATA_DESCRIPTOR v52; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v53; // [rsp+50h] [rbp-B0h]
  __int64 v54; // [rsp+58h] [rbp-A8h]
  __int64 v55; // [rsp+60h] [rbp-A0h]
  __int64 v56; // [rsp+68h] [rbp-98h]
  const unsigned __int16 *v57; // [rsp+70h] [rbp-90h]
  int v58; // [rsp+78h] [rbp-88h]
  int v59; // [rsp+7Ch] [rbp-84h]
  __int64 v60; // [rsp+80h] [rbp-80h]
  __int64 v61; // [rsp+88h] [rbp-78h]
  const unsigned __int16 *v62; // [rsp+90h] [rbp-70h]
  int v63; // [rsp+98h] [rbp-68h]
  int v64; // [rsp+9Ch] [rbp-64h]
  __int64 v65; // [rsp+A0h] [rbp-60h]
  __int64 v66; // [rsp+A8h] [rbp-58h]
  __int64 *v67; // [rsp+B0h] [rbp-50h]
  int v68; // [rsp+B8h] [rbp-48h]
  int v69; // [rsp+BCh] [rbp-44h]
  __int64 v70; // [rsp+C0h] [rbp-40h]
  __int64 v71; // [rsp+C8h] [rbp-38h]
  const unsigned __int16 *v72; // [rsp+D0h] [rbp-30h]
  int v73; // [rsp+D8h] [rbp-28h]
  int v74; // [rsp+DCh] [rbp-24h]
  __int64 v75; // [rsp+E0h] [rbp-20h]
  __int64 v76; // [rsp+E8h] [rbp-18h]
  const unsigned __int16 *v77; // [rsp+F0h] [rbp-10h]
  int v78; // [rsp+F8h] [rbp-8h]
  int v79; // [rsp+FCh] [rbp-4h]
  __int64 *v80; // [rsp+100h] [rbp+0h]
  int v81; // [rsp+108h] [rbp+8h]
  int v82; // [rsp+10Ch] [rbp+Ch]
  __int64 v83; // [rsp+110h] [rbp+10h]
  __int64 v84; // [rsp+118h] [rbp+18h]
  const unsigned __int16 *v85; // [rsp+120h] [rbp+20h]
  int v86; // [rsp+128h] [rbp+28h]
  int v87; // [rsp+12Ch] [rbp+2Ch]
  __int64 *v88; // [rsp+130h] [rbp+30h]
  int v89; // [rsp+138h] [rbp+38h]
  int v90; // [rsp+13Ch] [rbp+3Ch]
  __int64 v91; // [rsp+140h] [rbp+40h]
  __int64 v92; // [rsp+148h] [rbp+48h]
  __int64 v93; // [rsp+150h] [rbp+50h]
  __int64 v94; // [rsp+158h] [rbp+58h]
  const unsigned __int16 *v95; // [rsp+160h] [rbp+60h]
  int v96; // [rsp+168h] [rbp+68h]
  int v97; // [rsp+16Ch] [rbp+6Ch]

  v24 = -1;
  v25 = 1;
  v26 = *a22;
  if ( *a22 )
  {
    v27 = -1;
    do
      ++v27;
    while ( *((_BYTE *)v26 + v27) );
    v28 = v27 + 1;
  }
  else
  {
    v26 = &qword_18002D6C0;
    v28 = 1;
  }
  v96 = v28;
  v29 = 2;
  v93 = a21;
  v91 = a20;
  v95 = v26;
  v97 = 0;
  v94 = 4;
  v30 = *a19;
  v92 = 4;
  if ( v30 )
  {
    v31 = -1;
    do
      ++v31;
    while ( *((_WORD *)v30 + v31) );
    v32 = 2 * v31 + 2;
  }
  else
  {
    v30 = &qword_18002E230;
    v32 = 2;
  }
  v89 = v32;
  v88 = v30;
  v90 = 0;
  v33 = *a18;
  if ( *a18 )
  {
    v34 = -1;
    do
      ++v34;
    while ( *((_BYTE *)v33 + v34) );
    v35 = v34 + 1;
  }
  else
  {
    v33 = &qword_18002D6C0;
    v35 = 1;
  }
  v86 = v35;
  v83 = a17;
  v85 = v33;
  v87 = 0;
  v84 = 4;
  v36 = *a16;
  if ( *a16 )
  {
    v37 = -1;
    do
      ++v37;
    while ( *((_WORD *)v36 + v37) );
    v38 = 2 * v37 + 2;
  }
  else
  {
    v36 = &qword_18002E230;
    v38 = 2;
  }
  v81 = v38;
  v80 = v36;
  v82 = 0;
  v39 = *a15;
  if ( *a15 )
  {
    v40 = -1;
    do
      ++v40;
    while ( *((_BYTE *)v39 + v40) );
    v41 = v40 + 1;
  }
  else
  {
    v39 = &qword_18002D6C0;
    v41 = 1;
  }
  v78 = v41;
  v75 = a14;
  v77 = v39;
  v79 = 0;
  v76 = 4;
  v42 = *a13;
  if ( *a13 )
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
  v73 = v44;
  v70 = a12;
  v72 = v42;
  v74 = 0;
  v71 = 4;
  v45 = *a11;
  if ( *a11 )
  {
    v46 = -1;
    do
      ++v46;
    while ( *((_WORD *)v45 + v46) );
    v29 = 2 * v46 + 2;
  }
  else
  {
    v45 = &qword_18002E230;
  }
  v65 = a10;
  v67 = v45;
  v68 = v29;
  v69 = 0;
  v47 = *a9;
  v66 = 4;
  if ( v47 )
  {
    v48 = -1;
    do
      ++v48;
    while ( *((_BYTE *)v47 + v48) );
    v49 = v48 + 1;
  }
  else
  {
    v47 = &qword_18002D6C0;
    v49 = 1;
  }
  v63 = v49;
  v60 = a8;
  v62 = v47;
  v64 = 0;
  v61 = 4;
  v50 = *a7;
  if ( *a7 )
  {
    do
      ++v24;
    while ( *((_BYTE *)v50 + v24) );
    v25 = v24 + 1;
  }
  else
  {
    v50 = &qword_18002D6C0;
  }
  v55 = a6;
  v53 = a5;
  v57 = v50;
  v58 = v25;
  v59 = 0;
  v56 = 4;
  v54 = 8;
  return tlgWriteTransfer_EventWriteTransfer(a1, a2, 0, 0, 0x14u, &v52);
}

```

## disassembly

```asm
0x180001a90  mov     [rsp-8+arg_10], rbx
0x180001a95  push    rbp
0x180001a96  push    rdi
0x180001a97  push    r14
0x180001a99  lea     rbp, [rsp-80h]
0x180001a9e  sub     rsp, 180h
0x180001aa5  mov     rax, cs:__security_cookie
0x180001aac  xor     rax, rsp
0x180001aaf  mov     [rbp+90h+var_20], rax
0x180001ab3  mov     rax, [rbp+90h+arg_A8]
0x180001aba  lea     rdi, qword_18002D6C0
0x180001ac1  mov     r11, rdx
0x180001ac4  mov     r10, rcx
0x180001ac7  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180001acb  xor     ebx, ebx
0x180001acd  mov     r8d, 1
0x180001ad3  mov     rcx, [rax]
0x180001ad6  test    rcx, rcx
0x180001ad9  jz      short loc_180001AEA
0x180001adb  mov     rax, rdx
0x180001ade  inc     rax
0x180001ae1  cmp     [rcx+rax], bl
0x180001ae4  jnz     short loc_180001ADE
0x180001ae6  inc     eax
0x180001ae8  jmp     short loc_180001AF0
0x180001aea  mov     rcx, rdi
0x180001aed  mov     eax, r8d
0x180001af0  mov     [rbp+90h+var_28], eax
0x180001af3  mov     r9d, 2
0x180001af9  mov     rax, [rbp+90h+arg_A0]
0x180001b00  mov     [rbp+90h+var_40], rax
0x180001b04  mov     rax, [rbp+90h+arg_98]
0x180001b0b  mov     [rbp+90h+var_50], rax
0x180001b0f  mov     rax, [rbp+90h+arg_90]
0x180001b16  mov     [rbp+90h+var_30], rcx
0x180001b1a  mov     [rbp+90h+var_24], ebx
0x180001b1d  mov     [rbp+90h+var_38], 4
0x180001b25  mov     rcx, [rax]
0x180001b28  mov     [rbp+90h+var_48], 4
0x180001b30  test    rcx, rcx
0x180001b33  jz      short loc_180001B4A
0x180001b35  mov     rax, rdx
0x180001b38  inc     rax
0x180001b3b  cmp     [rcx+rax*2], bx
0x180001b3f  jnz     short loc_180001B38
0x180001b41  lea     eax, ds:2[rax*2]
0x180001b48  jmp     short loc_180001B54
0x180001b4a  lea     rcx, qword_18002E230
0x180001b51  mov     eax, r9d
0x180001b54  mov     [rbp+90h+var_58], eax
0x180001b57  mov     rax, [rbp+90h+arg_88]
0x180001b5e  mov     [rbp+90h+var_60], rcx
0x180001b62  mov     [rbp+90h+var_54], ebx
0x180001b65  mov     rcx, [rax]
0x180001b68  test    rcx, rcx
0x180001b6b  jz      short loc_180001B7C
0x180001b6d  mov     rax, rdx
0x180001b70  inc     rax
0x180001b73  cmp     [rcx+rax], bl
0x180001b76  jnz     short loc_180001B70
0x180001b78  inc     eax
0x180001b7a  jmp     short loc_180001B82
0x180001b7c  mov     rcx, rdi
0x180001b7f  mov     eax, r8d
0x180001b82  mov     [rbp+90h+var_68], eax
0x180001b85  mov     rax, [rbp+90h+arg_80]
0x180001b8c  mov     [rbp+90h+var_80], rax
0x180001b90  mov     rax, [rbp+90h+arg_78]
0x180001b97  mov     [rbp+90h+var_70], rcx
0x180001b9b  mov     [rbp+90h+var_64], ebx
0x180001b9e  mov     [rbp+90h+var_78], 4
0x180001ba6  mov     rcx, [rax]
0x180001ba9  test    rcx, rcx
0x180001bac  jz      short loc_180001BC3
0x180001bae  mov     rax, rdx
0x180001bb1  inc     rax
0x180001bb4  cmp     [rcx+rax*2], bx
0x180001bb8  jnz     short loc_180001BB1
0x180001bba  lea     eax, ds:2[rax*2]
0x180001bc1  jmp     short loc_180001BCD
0x180001bc3  lea     rcx, qword_18002E230
0x180001bca  mov     eax, r9d
0x180001bcd  mov     [rbp+90h+var_88], eax
0x180001bd0  mov     rax, [rbp+90h+arg_70]
0x180001bd7  mov     [rbp+90h+var_90], rcx
0x180001bdb  mov     [rbp+90h+var_84], ebx
0x180001bde  mov     rcx, [rax]
0x180001be1  test    rcx, rcx
0x180001be4  jz      short loc_180001BF5
0x180001be6  mov     rax, rdx
0x180001be9  inc     rax
0x180001bec  cmp     [rcx+rax], bl
0x180001bef  jnz     short loc_180001BE9
0x180001bf1  inc     eax
0x180001bf3  jmp     short loc_180001BFB
0x180001bf5  mov     rcx, rdi
0x180001bf8  mov     eax, r8d
0x180001bfb  mov     [rbp+90h+var_98], eax
0x180001bfe  mov     rax, [rbp+90h+arg_68]
0x180001c05  mov     [rbp+90h+var_B0], rax
0x180001c09  mov     rax, [rbp+90h+arg_60]
0x180001c10  mov     [rbp+90h+var_A0], rcx
0x180001c14  mov     [rbp+90h+var_94], ebx
0x180001c17  mov     [rbp+90h+var_A8], 4
0x180001c1f  mov     rcx, [rax]
0x180001c22  test    rcx, rcx
0x180001c25  jz      short loc_180001C36
0x180001c27  mov     rax, rdx
0x180001c2a  inc     rax
0x180001c2d  cmp     [rcx+rax], bl
0x180001c30  jnz     short loc_180001C2A
0x180001c32  inc     eax
0x180001c34  jmp     short loc_180001C3C
0x180001c36  mov     rcx, rdi
0x180001c39  mov     eax, r8d
0x180001c3c  mov     [rbp+90h+var_B8], eax
0x180001c3f  mov     rax, [rbp+90h+arg_58]
0x180001c46  mov     [rbp+90h+var_D0], rax
0x180001c4a  mov     rax, [rbp+90h+arg_50]
0x180001c51  mov     [rbp+90h+var_C0], rcx
0x180001c55  mov     [rbp+90h+var_B4], ebx
0x180001c58  mov     [rbp+90h+var_C8], 4
0x180001c60  mov     rcx, [rax]
0x180001c63  test    rcx, rcx
0x180001c66  jz      short loc_180001C7E
0x180001c68  mov     rax, rdx
0x180001c6b  inc     rax
0x180001c6e  cmp     [rcx+rax*2], bx
0x180001c72  jnz     short loc_180001C6B
0x180001c74  lea     r9d, ds:2[rax*2]
0x180001c7c  jmp     short loc_180001C85
0x180001c7e  lea     rcx, qword_18002E230
0x180001c85  mov     rax, [rbp+90h+arg_48]
0x180001c8c  mov     [rbp+90h+var_F0], rax
0x180001c90  mov     rax, [rbp+90h+arg_40]
0x180001c97  mov     [rbp+90h+var_E0], rcx
0x180001c9b  mov     [rbp+90h+var_D8], r9d
0x180001c9f  mov     [rbp+90h+var_D4], ebx
0x180001ca2  mov     rcx, [rax]
0x180001ca5  mov     [rbp+90h+var_E8], 4
0x180001cad  test    rcx, rcx
0x180001cb0  jz      short loc_180001CC1
0x180001cb2  mov     rax, rdx
0x180001cb5  inc     rax
0x180001cb8  cmp     [rcx+rax], bl
0x180001cbb  jnz     short loc_180001CB5
0x180001cbd  inc     eax
0x180001cbf  jmp     short loc_180001CC7
0x180001cc1  mov     rcx, rdi
0x180001cc4  mov     eax, r8d
0x180001cc7  mov     [rbp+90h+var_F8], eax
0x180001cca  mov     rax, [rbp+90h+arg_38]
0x180001cd1  mov     [rbp+90h+var_110], rax
0x180001cd5  mov     rax, [rbp+90h+arg_30]
0x180001cdc  mov     [rbp+90h+var_100], rcx
0x180001ce0  mov     [rbp+90h+var_F4], ebx
0x180001ce3  mov     [rbp+90h+var_108], 4
0x180001ceb  mov     rcx, [rax]
0x180001cee  test    rcx, rcx
0x180001cf1  jz      short loc_180001D01
0x180001cf3  inc     rdx
0x180001cf6  cmp     [rcx+rdx], bl
0x180001cf9  jnz     short loc_180001CF3
0x180001cfb  lea     r8d, [rdx+1]
0x180001cff  jmp     short loc_180001D04
0x180001d01  mov     rcx, rdi
0x180001d04  mov     rax, [rbp+90h+arg_28]
0x180001d0b  xor     r9d, r9d
0x180001d0e  mov     [rsp+190h+var_130], rax
0x180001d13  mov     rdx, r11
0x180001d16  mov     rax, [rbp+90h+arg_20]
0x180001d1d  mov     [rsp+190h+var_140], rax
0x180001d22  lea     rax, [rsp+190h+var_160]
0x180001d27  mov     [rsp+190h+var_120], rcx
0x180001d2c  mov     rcx, r10
0x180001d2f  mov     [rsp+190h+var_118], r8d
0x180001d34  xor     r8d, r8d
0x180001d37  mov     [rsp+190h+var_168], rax
0x180001d3c  mov     [rsp+190h+var_170], 14h
0x180001d44  mov     [rsp+190h+var_114], ebx
0x180001d48  mov     [rsp+190h+var_128], 4
0x180001d51  mov     [rsp+190h+var_138], 8
0x180001d5a  call    _tlgWriteTransfer_EventWriteTransfer
0x180001d5f  mov     rcx, [rbp+90h+var_20]
0x180001d63  xor     rcx, rsp; StackCookie
0x180001d66  call    __security_check_cookie
0x180001d6b  mov     rbx, [rsp+190h+arg_10]
0x180001d73  add     rsp, 180h
0x180001d7a  pop     r14
0x180001d7c  pop     rdi
0x180001d7d  pop     rbp
0x180001d7e  retn
```
