# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)

- ea: `0x180001ad0`
- end: `0x180001ddb`
- name: `??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456445@Z`
- size: `779`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, __int64, __int64, __int64, const unsigned __int16 **, __int64, const unsigned __int16 **, __int64, __int64 **, __int64, const unsigned __int16 **, __int64, const unsigned __int16 **, __int64 **, __int64, const unsigned __int16 **, __int64 **, __int64, __int64, const unsigned __int16 **)`
- caller_count: `8`
- callee_count: `3`
- tags: ``

## callers

- `0x1800092a0`
- `0x18000bf70`
- `0x180013e50`
- `0x180014090`
- `0x1800142d0`
- `0x180014510`
- `0x180014750`
- `0x180014990`

## callees

- `0x1800019e8`
- `0x180001ad0`
- `0x180002b10`

## pseudocode

```c
__int64 __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
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
        __int64 **a12,
        __int64 a13,
        const unsigned __int16 **a14,
        __int64 a15,
        const unsigned __int16 **a16,
        __int64 **a17,
        __int64 a18,
        const unsigned __int16 **a19,
        __int64 **a20,
        __int64 a21,
        __int64 a22,
        const unsigned __int16 **a23)
{
  __int64 v25; // rdx
  int v27; // r8d
  const unsigned __int16 *v28; // rcx
  __int64 v29; // rax
  int v30; // eax
  int v31; // r9d
  __int64 *v32; // rcx
  __int64 v33; // rax
  int v34; // eax
  const unsigned __int16 *v35; // rcx
  __int64 v36; // rax
  int v37; // eax
  __int64 *v38; // rcx
  __int64 v39; // rax
  int v40; // eax
  const unsigned __int16 *v41; // rcx
  __int64 v42; // rax
  int v43; // eax
  const unsigned __int16 *v44; // rcx
  __int64 v45; // rax
  int v46; // eax
  __int64 *v47; // rcx
  __int64 v48; // rax
  const unsigned __int16 *v49; // rcx
  __int64 v50; // rax
  int v51; // eax
  const unsigned __int16 *v52; // rcx
  _BYTE v54[32]; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v55; // [rsp+50h] [rbp-B0h]
  __int64 v56; // [rsp+58h] [rbp-A8h]
  __int64 v57; // [rsp+60h] [rbp-A0h]
  __int64 v58; // [rsp+68h] [rbp-98h]
  __int64 v59; // [rsp+70h] [rbp-90h]
  __int64 v60; // [rsp+78h] [rbp-88h]
  const unsigned __int16 *v61; // [rsp+80h] [rbp-80h]
  int v62; // [rsp+88h] [rbp-78h]
  int v63; // [rsp+8Ch] [rbp-74h]
  __int64 v64; // [rsp+90h] [rbp-70h]
  __int64 v65; // [rsp+98h] [rbp-68h]
  const unsigned __int16 *v66; // [rsp+A0h] [rbp-60h]
  int v67; // [rsp+A8h] [rbp-58h]
  int v68; // [rsp+ACh] [rbp-54h]
  __int64 v69; // [rsp+B0h] [rbp-50h]
  __int64 v70; // [rsp+B8h] [rbp-48h]
  __int64 *v71; // [rsp+C0h] [rbp-40h]
  int v72; // [rsp+C8h] [rbp-38h]
  int v73; // [rsp+CCh] [rbp-34h]
  __int64 v74; // [rsp+D0h] [rbp-30h]
  __int64 v75; // [rsp+D8h] [rbp-28h]
  const unsigned __int16 *v76; // [rsp+E0h] [rbp-20h]
  int v77; // [rsp+E8h] [rbp-18h]
  int v78; // [rsp+ECh] [rbp-14h]
  __int64 v79; // [rsp+F0h] [rbp-10h]
  __int64 v80; // [rsp+F8h] [rbp-8h]
  const unsigned __int16 *v81; // [rsp+100h] [rbp+0h]
  int v82; // [rsp+108h] [rbp+8h]
  int v83; // [rsp+10Ch] [rbp+Ch]
  __int64 *v84; // [rsp+110h] [rbp+10h]
  int v85; // [rsp+118h] [rbp+18h]
  int v86; // [rsp+11Ch] [rbp+1Ch]
  __int64 v87; // [rsp+120h] [rbp+20h]
  __int64 v88; // [rsp+128h] [rbp+28h]
  const unsigned __int16 *v89; // [rsp+130h] [rbp+30h]
  int v90; // [rsp+138h] [rbp+38h]
  int v91; // [rsp+13Ch] [rbp+3Ch]
  __int64 *v92; // [rsp+140h] [rbp+40h]
  int v93; // [rsp+148h] [rbp+48h]
  int v94; // [rsp+14Ch] [rbp+4Ch]
  __int64 v95; // [rsp+150h] [rbp+50h]
  __int64 v96; // [rsp+158h] [rbp+58h]
  __int64 v97; // [rsp+160h] [rbp+60h]
  __int64 v98; // [rsp+168h] [rbp+68h]
  const unsigned __int16 *v99; // [rsp+170h] [rbp+70h]
  int v100; // [rsp+178h] [rbp+78h]
  int v101; // [rsp+17Ch] [rbp+7Ch]

  v25 = -1;
  v27 = 1;
  v28 = *a23;
  if ( *a23 )
  {
    v29 = -1;
    do
      ++v29;
    while ( *((_BYTE *)v28 + v29) );
    v30 = v29 + 1;
  }
  else
  {
    v28 = &qword_18001DBF0;
    v30 = 1;
  }
  v100 = v30;
  v31 = 2;
  v97 = a22;
  v95 = a21;
  v99 = v28;
  v101 = 0;
  v98 = 4;
  v32 = *a20;
  v96 = 4;
  if ( v32 )
  {
    v33 = -1;
    do
      ++v33;
    while ( *((_WORD *)v32 + v33) );
    v34 = 2 * v33 + 2;
  }
  else
  {
    v32 = &qword_18001DFC8;
    v34 = 2;
  }
  v93 = v34;
  v92 = v32;
  v94 = 0;
  v35 = *a19;
  if ( *a19 )
  {
    v36 = -1;
    do
      ++v36;
    while ( *((_BYTE *)v35 + v36) );
    v37 = v36 + 1;
  }
  else
  {
    v35 = &qword_18001DBF0;
    v37 = 1;
  }
  v90 = v37;
  v87 = a18;
  v89 = v35;
  v91 = 0;
  v88 = 4;
  v38 = *a17;
  if ( *a17 )
  {
    v39 = -1;
    do
      ++v39;
    while ( *((_WORD *)v38 + v39) );
    v40 = 2 * v39 + 2;
  }
  else
  {
    v38 = &qword_18001DFC8;
    v40 = 2;
  }
  v85 = v40;
  v84 = v38;
  v86 = 0;
  v41 = *a16;
  if ( *a16 )
  {
    v42 = -1;
    do
      ++v42;
    while ( *((_BYTE *)v41 + v42) );
    v43 = v42 + 1;
  }
  else
  {
    v41 = &qword_18001DBF0;
    v43 = 1;
  }
  v82 = v43;
  v79 = a15;
  v81 = v41;
  v83 = 0;
  v80 = 4;
  v44 = *a14;
  if ( *a14 )
  {
    v45 = -1;
    do
      ++v45;
    while ( *((_BYTE *)v44 + v45) );
    v46 = v45 + 1;
  }
  else
  {
    v44 = &qword_18001DBF0;
    v46 = 1;
  }
  v77 = v46;
  v74 = a13;
  v76 = v44;
  v78 = 0;
  v75 = 4;
  v47 = *a12;
  if ( *a12 )
  {
    v48 = -1;
    do
      ++v48;
    while ( *((_WORD *)v47 + v48) );
    v31 = 2 * v48 + 2;
  }
  else
  {
    v47 = &qword_18001DFC8;
  }
  v69 = a11;
  v71 = v47;
  v72 = v31;
  v73 = 0;
  v49 = *a10;
  v70 = 4;
  if ( v49 )
  {
    v50 = -1;
    do
      ++v50;
    while ( *((_BYTE *)v49 + v50) );
    v51 = v50 + 1;
  }
  else
  {
    v49 = &qword_18001DBF0;
    v51 = 1;
  }
  v67 = v51;
  v64 = a9;
  v66 = v49;
  v68 = 0;
  v65 = 4;
  v52 = *a8;
  if ( *a8 )
  {
    do
      ++v25;
    while ( *((_BYTE *)v52 + v25) );
    v27 = v25 + 1;
  }
  else
  {
    v52 = &qword_18001DBF0;
  }
  v59 = a7;
  v57 = a6;
  v55 = a5;
  v61 = v52;
  v62 = v27;
  v63 = 0;
  v60 = 4;
  v58 = 8;
  v56 = 8;
  return tlgWriteTransfer_EventWriteTransfer(a1, a2, a3, 0, 21, v54);
}

```

## disassembly

```asm
0x180001ad0  push    rbp
0x180001ad2  push    rbx
0x180001ad3  push    rsi
0x180001ad4  push    rdi
0x180001ad5  push    r14
0x180001ad7  lea     rbp, [rsp-90h]
0x180001adf  sub     rsp, 190h
0x180001ae6  mov     rax, cs:__security_cookie
0x180001aed  xor     rax, rsp
0x180001af0  mov     [rbp+0B0h+var_30], rax
0x180001af7  mov     rax, [rbp+0B0h+arg_B0]
0x180001afe  lea     rsi, qword_18001DBF0
0x180001b05  mov     r11, rdx
0x180001b08  mov     r10, rcx
0x180001b0b  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180001b0f  xor     edi, edi
0x180001b11  mov     rbx, r8
0x180001b14  mov     r8d, 1
0x180001b1a  mov     rcx, [rax]
0x180001b1d  test    rcx, rcx
0x180001b20  jz      short loc_180001B32
0x180001b22  mov     rax, rdx
0x180001b25  inc     rax
0x180001b28  cmp     [rcx+rax], dil
0x180001b2c  jnz     short loc_180001B25
0x180001b2e  inc     eax
0x180001b30  jmp     short loc_180001B38
0x180001b32  mov     rcx, rsi
0x180001b35  mov     eax, r8d
0x180001b38  mov     [rbp+0B0h+var_38], eax
0x180001b3b  mov     r9d, 2
0x180001b41  mov     rax, [rbp+0B0h+arg_A8]
0x180001b48  mov     [rbp+0B0h+var_50], rax
0x180001b4c  mov     rax, [rbp+0B0h+arg_A0]
0x180001b53  mov     [rbp+0B0h+var_60], rax
0x180001b57  mov     rax, [rbp+0B0h+arg_98]
0x180001b5e  mov     [rbp+0B0h+var_40], rcx
0x180001b62  mov     [rbp+0B0h+var_34], edi
0x180001b65  mov     [rbp+0B0h+var_48], 4
0x180001b6d  mov     rcx, [rax]
0x180001b70  mov     [rbp+0B0h+var_58], 4
0x180001b78  test    rcx, rcx
0x180001b7b  jz      short loc_180001B92
0x180001b7d  mov     rax, rdx
0x180001b80  inc     rax
0x180001b83  cmp     [rcx+rax*2], di
0x180001b87  jnz     short loc_180001B80
0x180001b89  lea     eax, ds:2[rax*2]
0x180001b90  jmp     short loc_180001B9C
0x180001b92  lea     rcx, qword_18001DFC8
0x180001b99  mov     eax, r9d
0x180001b9c  mov     [rbp+0B0h+var_68], eax
0x180001b9f  mov     rax, [rbp+0B0h+arg_90]
0x180001ba6  mov     [rbp+0B0h+var_70], rcx
0x180001baa  mov     [rbp+0B0h+var_64], edi
0x180001bad  mov     rcx, [rax]
0x180001bb0  test    rcx, rcx
0x180001bb3  jz      short loc_180001BC5
0x180001bb5  mov     rax, rdx
0x180001bb8  inc     rax
0x180001bbb  cmp     [rcx+rax], dil
0x180001bbf  jnz     short loc_180001BB8
0x180001bc1  inc     eax
0x180001bc3  jmp     short loc_180001BCB
0x180001bc5  mov     rcx, rsi
0x180001bc8  mov     eax, r8d
0x180001bcb  mov     [rbp+0B0h+var_78], eax
0x180001bce  mov     rax, [rbp+0B0h+arg_88]
0x180001bd5  mov     [rbp+0B0h+var_90], rax
0x180001bd9  mov     rax, [rbp+0B0h+arg_80]
0x180001be0  mov     [rbp+0B0h+var_80], rcx
0x180001be4  mov     [rbp+0B0h+var_74], edi
0x180001be7  mov     [rbp+0B0h+var_88], 4
0x180001bef  mov     rcx, [rax]
0x180001bf2  test    rcx, rcx
0x180001bf5  jz      short loc_180001C0C
0x180001bf7  mov     rax, rdx
0x180001bfa  inc     rax
0x180001bfd  cmp     [rcx+rax*2], di
0x180001c01  jnz     short loc_180001BFA
0x180001c03  lea     eax, ds:2[rax*2]
0x180001c0a  jmp     short loc_180001C16
0x180001c0c  lea     rcx, qword_18001DFC8
0x180001c13  mov     eax, r9d
0x180001c16  mov     [rbp+0B0h+var_98], eax
0x180001c19  mov     rax, [rbp+0B0h+arg_78]
0x180001c20  mov     [rbp+0B0h+var_A0], rcx
0x180001c24  mov     [rbp+0B0h+var_94], edi
0x180001c27  mov     rcx, [rax]
0x180001c2a  test    rcx, rcx
0x180001c2d  jz      short loc_180001C3F
0x180001c2f  mov     rax, rdx
0x180001c32  inc     rax
0x180001c35  cmp     [rcx+rax], dil
0x180001c39  jnz     short loc_180001C32
0x180001c3b  inc     eax
0x180001c3d  jmp     short loc_180001C45
0x180001c3f  mov     rcx, rsi
0x180001c42  mov     eax, r8d
0x180001c45  mov     [rbp+0B0h+var_A8], eax
0x180001c48  mov     rax, [rbp+0B0h+arg_70]
0x180001c4f  mov     [rbp+0B0h+var_C0], rax
0x180001c53  mov     rax, [rbp+0B0h+arg_68]
0x180001c5a  mov     [rbp+0B0h+var_B0], rcx
0x180001c5e  mov     [rbp+0B0h+var_A4], edi
0x180001c61  mov     [rbp+0B0h+var_B8], 4
0x180001c69  mov     rcx, [rax]
0x180001c6c  test    rcx, rcx
0x180001c6f  jz      short loc_180001C81
0x180001c71  mov     rax, rdx
0x180001c74  inc     rax
0x180001c77  cmp     [rcx+rax], dil
0x180001c7b  jnz     short loc_180001C74
0x180001c7d  inc     eax
0x180001c7f  jmp     short loc_180001C87
0x180001c81  mov     rcx, rsi
0x180001c84  mov     eax, r8d
0x180001c87  mov     [rbp+0B0h+var_C8], eax
0x180001c8a  mov     rax, [rbp+0B0h+arg_60]
0x180001c91  mov     [rbp+0B0h+var_E0], rax
0x180001c95  mov     rax, [rbp+0B0h+arg_58]
0x180001c9c  mov     [rbp+0B0h+var_D0], rcx
0x180001ca0  mov     [rbp+0B0h+var_C4], edi
0x180001ca3  mov     [rbp+0B0h+var_D8], 4
0x180001cab  mov     rcx, [rax]
0x180001cae  test    rcx, rcx
0x180001cb1  jz      short loc_180001CC9
0x180001cb3  mov     rax, rdx
0x180001cb6  inc     rax
0x180001cb9  cmp     [rcx+rax*2], di
0x180001cbd  jnz     short loc_180001CB6
0x180001cbf  lea     r9d, ds:2[rax*2]
0x180001cc7  jmp     short loc_180001CD0
0x180001cc9  lea     rcx, qword_18001DFC8
0x180001cd0  mov     rax, [rbp+0B0h+arg_50]
0x180001cd7  mov     [rbp+0B0h+var_100], rax
0x180001cdb  mov     rax, [rbp+0B0h+arg_48]
0x180001ce2  mov     [rbp+0B0h+var_F0], rcx
0x180001ce6  mov     [rbp+0B0h+var_E8], r9d
0x180001cea  mov     [rbp+0B0h+var_E4], edi
0x180001ced  mov     rcx, [rax]
0x180001cf0  mov     [rbp+0B0h+var_F8], 4
0x180001cf8  test    rcx, rcx
0x180001cfb  jz      short loc_180001D0D
0x180001cfd  mov     rax, rdx
0x180001d00  inc     rax
0x180001d03  cmp     [rcx+rax], dil
0x180001d07  jnz     short loc_180001D00
0x180001d09  inc     eax
0x180001d0b  jmp     short loc_180001D13
0x180001d0d  mov     rcx, rsi
0x180001d10  mov     eax, r8d
0x180001d13  mov     [rbp+0B0h+var_108], eax
0x180001d16  mov     rax, [rbp+0B0h+arg_40]
0x180001d1d  mov     [rbp+0B0h+var_120], rax
0x180001d21  mov     rax, [rbp+0B0h+arg_38]
0x180001d28  mov     [rbp+0B0h+var_110], rcx
0x180001d2c  mov     [rbp+0B0h+var_104], edi
0x180001d2f  mov     [rbp+0B0h+var_118], 4
0x180001d37  mov     rcx, [rax]
0x180001d3a  test    rcx, rcx
0x180001d3d  jz      short loc_180001D4E
0x180001d3f  inc     rdx
0x180001d42  cmp     [rcx+rdx], dil
0x180001d46  jnz     short loc_180001D3F
0x180001d48  lea     r8d, [rdx+1]
0x180001d4c  jmp     short loc_180001D51
0x180001d4e  mov     rcx, rsi
0x180001d51  mov     rax, [rbp+0B0h+arg_30]
0x180001d58  xor     r9d, r9d
0x180001d5b  mov     [rsp+1B0h+var_140], rax
0x180001d60  mov     rdx, r11
0x180001d63  mov     rax, [rbp+0B0h+arg_28]
0x180001d6a  mov     [rsp+1B0h+var_150], rax
0x180001d6f  mov     rax, [rbp+0B0h+arg_20]
0x180001d76  mov     [rsp+1B0h+var_160], rax
0x180001d7b  lea     rax, [rsp+1B0h+var_180]
0x180001d80  mov     [rbp+0B0h+var_130], rcx
0x180001d84  mov     rcx, r10
0x180001d87  mov     [rbp+0B0h+var_128], r8d
0x180001d8b  mov     r8, rbx
0x180001d8e  mov     [rsp+1B0h+var_188], rax
0x180001d93  mov     [rsp+1B0h+var_190], 15h
0x180001d9b  mov     [rbp+0B0h+var_124], edi
0x180001d9e  mov     [rsp+1B0h+var_138], 4
0x180001da7  mov     [rsp+1B0h+var_148], 8
0x180001db0  mov     [rsp+1B0h+var_158], 8
0x180001db9  call    _tlgWriteTransfer_EventWriteTransfer
0x180001dbe  mov     rcx, [rbp+0B0h+var_30]
0x180001dc5  xor     rcx, rsp; StackCookie
0x180001dc8  call    __security_check_cookie
0x180001dcd  add     rsp, 190h
0x180001dd4  pop     r14
0x180001dd6  pop     rdi
0x180001dd7  pop     rsi
0x180001dd8  pop     rbx
0x180001dd9  pop     rbp
0x180001dda  retn
```
