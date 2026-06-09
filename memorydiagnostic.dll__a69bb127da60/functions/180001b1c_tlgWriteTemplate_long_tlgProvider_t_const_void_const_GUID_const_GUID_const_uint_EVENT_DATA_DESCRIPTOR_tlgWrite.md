# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)

- ea: `0x180001b1c`
- end: `0x180001e24`
- name: `??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456445@Z`
- size: `776`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, __int64, __int64, __int64, const unsigned __int16 **, __int64, const unsigned __int16 **, __int64, int **, __int64, const unsigned __int16 **, __int64, const unsigned __int16 **, int **, __int64, const unsigned __int16 **, int **, __int64, __int64, const unsigned __int16 **)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18001d5d0`

## callees

- `0x180001a7c`
- `0x180001b1c`
- `0x180002e50`

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
        int **a12,
        __int64 a13,
        const unsigned __int16 **a14,
        __int64 a15,
        const unsigned __int16 **a16,
        int **a17,
        __int64 a18,
        const unsigned __int16 **a19,
        int **a20,
        __int64 a21,
        __int64 a22,
        const unsigned __int16 **a23)
{
  __int64 v25; // rcx
  int v26; // r8d
  const unsigned __int16 *v27; // rdx
  __int64 v28; // rax
  int v29; // eax
  int v30; // r9d
  int *v31; // rdx
  __int64 v32; // rax
  int v33; // eax
  const unsigned __int16 *v34; // rdx
  __int64 v35; // rax
  int v36; // eax
  int *v37; // rdx
  __int64 v38; // rax
  int v39; // eax
  const unsigned __int16 *v40; // rdx
  __int64 v41; // rax
  int v42; // eax
  const unsigned __int16 *v43; // rdx
  __int64 v44; // rax
  int v45; // eax
  int *v46; // rdx
  __int64 v47; // rax
  const unsigned __int16 *v48; // rdx
  __int64 v49; // rax
  int v50; // eax
  const unsigned __int16 *v51; // rdx
  _BYTE v53[32]; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v54; // [rsp+50h] [rbp-B0h]
  __int64 v55; // [rsp+58h] [rbp-A8h]
  __int64 v56; // [rsp+60h] [rbp-A0h]
  __int64 v57; // [rsp+68h] [rbp-98h]
  __int64 v58; // [rsp+70h] [rbp-90h]
  __int64 v59; // [rsp+78h] [rbp-88h]
  const unsigned __int16 *v60; // [rsp+80h] [rbp-80h]
  int v61; // [rsp+88h] [rbp-78h]
  int v62; // [rsp+8Ch] [rbp-74h]
  __int64 v63; // [rsp+90h] [rbp-70h]
  __int64 v64; // [rsp+98h] [rbp-68h]
  const unsigned __int16 *v65; // [rsp+A0h] [rbp-60h]
  int v66; // [rsp+A8h] [rbp-58h]
  int v67; // [rsp+ACh] [rbp-54h]
  __int64 v68; // [rsp+B0h] [rbp-50h]
  __int64 v69; // [rsp+B8h] [rbp-48h]
  int *v70; // [rsp+C0h] [rbp-40h]
  int v71; // [rsp+C8h] [rbp-38h]
  int v72; // [rsp+CCh] [rbp-34h]
  __int64 v73; // [rsp+D0h] [rbp-30h]
  __int64 v74; // [rsp+D8h] [rbp-28h]
  const unsigned __int16 *v75; // [rsp+E0h] [rbp-20h]
  int v76; // [rsp+E8h] [rbp-18h]
  int v77; // [rsp+ECh] [rbp-14h]
  __int64 v78; // [rsp+F0h] [rbp-10h]
  __int64 v79; // [rsp+F8h] [rbp-8h]
  const unsigned __int16 *v80; // [rsp+100h] [rbp+0h]
  int v81; // [rsp+108h] [rbp+8h]
  int v82; // [rsp+10Ch] [rbp+Ch]
  int *v83; // [rsp+110h] [rbp+10h]
  int v84; // [rsp+118h] [rbp+18h]
  int v85; // [rsp+11Ch] [rbp+1Ch]
  __int64 v86; // [rsp+120h] [rbp+20h]
  __int64 v87; // [rsp+128h] [rbp+28h]
  const unsigned __int16 *v88; // [rsp+130h] [rbp+30h]
  int v89; // [rsp+138h] [rbp+38h]
  int v90; // [rsp+13Ch] [rbp+3Ch]
  int *v91; // [rsp+140h] [rbp+40h]
  int v92; // [rsp+148h] [rbp+48h]
  int v93; // [rsp+14Ch] [rbp+4Ch]
  __int64 v94; // [rsp+150h] [rbp+50h]
  __int64 v95; // [rsp+158h] [rbp+58h]
  __int64 v96; // [rsp+160h] [rbp+60h]
  __int64 v97; // [rsp+168h] [rbp+68h]
  const unsigned __int16 *v98; // [rsp+170h] [rbp+70h]
  int v99; // [rsp+178h] [rbp+78h]
  int v100; // [rsp+17Ch] [rbp+7Ch]

  v25 = -1;
  v26 = 1;
  v27 = *a23;
  if ( *a23 )
  {
    v28 = -1;
    do
      ++v28;
    while ( *((_BYTE *)v27 + v28) );
    v29 = v28 + 1;
  }
  else
  {
    v27 = &byte_180025210;
    v29 = 1;
  }
  v99 = v29;
  v30 = 2;
  v96 = a22;
  v94 = a21;
  v98 = v27;
  v100 = 0;
  v97 = 4;
  v31 = *a20;
  v95 = 4;
  if ( v31 )
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
  v92 = v33;
  v91 = v31;
  v93 = 0;
  v34 = *a19;
  if ( *a19 )
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
  v89 = v36;
  v86 = a18;
  v88 = v34;
  v90 = 0;
  v87 = 4;
  v37 = *a17;
  if ( *a17 )
  {
    v38 = -1;
    do
      ++v38;
    while ( *((_WORD *)v37 + v38) );
    v39 = 2 * v38 + 2;
  }
  else
  {
    v37 = &dword_180025214;
    v39 = 2;
  }
  v84 = v39;
  v83 = v37;
  v85 = 0;
  v40 = *a16;
  if ( *a16 )
  {
    v41 = -1;
    do
      ++v41;
    while ( *((_BYTE *)v40 + v41) );
    v42 = v41 + 1;
  }
  else
  {
    v40 = &byte_180025210;
    v42 = 1;
  }
  v81 = v42;
  v78 = a15;
  v80 = v40;
  v82 = 0;
  v79 = 4;
  v43 = *a14;
  if ( *a14 )
  {
    v44 = -1;
    do
      ++v44;
    while ( *((_BYTE *)v43 + v44) );
    v45 = v44 + 1;
  }
  else
  {
    v43 = &byte_180025210;
    v45 = 1;
  }
  v76 = v45;
  v73 = a13;
  v75 = v43;
  v77 = 0;
  v74 = 4;
  v46 = *a12;
  if ( *a12 )
  {
    v47 = -1;
    do
      ++v47;
    while ( *((_WORD *)v46 + v47) );
    v30 = 2 * v47 + 2;
  }
  else
  {
    v46 = &dword_180025214;
  }
  v68 = a11;
  v70 = v46;
  v71 = v30;
  v72 = 0;
  v48 = *a10;
  v69 = 4;
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
    v48 = &byte_180025210;
    v50 = 1;
  }
  v66 = v50;
  v63 = a9;
  v65 = v48;
  v67 = 0;
  v64 = 4;
  v51 = *a8;
  if ( *a8 )
  {
    do
      ++v25;
    while ( *((_BYTE *)v51 + v25) );
    v26 = v25 + 1;
  }
  else
  {
    v51 = &byte_180025210;
  }
  v58 = a7;
  v56 = a6;
  v54 = a5;
  v60 = v51;
  v61 = v26;
  v62 = 0;
  v59 = 4;
  v57 = 8;
  v55 = 8;
  return ((__int64 (__fastcall *)(__int64, __int64, _QWORD, _QWORD, int, _BYTE *))tlgWriteTransfer_EventWriteTransfer)(
           a1,
           a2,
           0,
           0,
           21,
           v53);
}

```

## disassembly

```asm
0x180001b1c  mov     [rsp-8+arg_10], rbx
0x180001b21  push    rbp
0x180001b22  push    rsi
0x180001b23  push    rdi
0x180001b24  lea     rbp, [rsp-90h]
0x180001b2c  sub     rsp, 190h
0x180001b33  mov     rax, cs:__security_cookie
0x180001b3a  xor     rax, rsp
0x180001b3d  mov     [rbp+0A0h+var_20], rax
0x180001b44  mov     rax, [rbp+0A0h+arg_B0]
0x180001b4b  lea     rdi, byte_180025210
0x180001b52  mov     r11, rdx
0x180001b55  mov     r10, rcx
0x180001b58  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180001b5c  xor     ebx, ebx
0x180001b5e  mov     r8d, 1
0x180001b64  mov     rdx, [rax]
0x180001b67  test    rdx, rdx
0x180001b6a  jz      short loc_180001B7B
0x180001b6c  mov     rax, rcx
0x180001b6f  inc     rax
0x180001b72  cmp     [rdx+rax], bl
0x180001b75  jnz     short loc_180001B6F
0x180001b77  inc     eax
0x180001b79  jmp     short loc_180001B81
0x180001b7b  mov     rdx, rdi
0x180001b7e  mov     eax, r8d
0x180001b81  mov     [rbp+0A0h+var_28], eax
0x180001b84  mov     r9d, 2
0x180001b8a  mov     rax, [rbp+0A0h+arg_A8]
0x180001b91  mov     [rbp+0A0h+var_40], rax
0x180001b95  mov     rax, [rbp+0A0h+arg_A0]
0x180001b9c  mov     [rbp+0A0h+var_50], rax
0x180001ba0  mov     rax, [rbp+0A0h+arg_98]
0x180001ba7  mov     [rbp+0A0h+var_30], rdx
0x180001bab  mov     [rbp+0A0h+var_24], ebx
0x180001bae  mov     [rbp+0A0h+var_38], 4
0x180001bb6  mov     rdx, [rax]
0x180001bb9  mov     [rbp+0A0h+var_48], 4
0x180001bc1  test    rdx, rdx
0x180001bc4  jz      short loc_180001BDB
0x180001bc6  mov     rax, rcx
0x180001bc9  inc     rax
0x180001bcc  cmp     [rdx+rax*2], bx
0x180001bd0  jnz     short loc_180001BC9
0x180001bd2  lea     eax, ds:2[rax*2]
0x180001bd9  jmp     short loc_180001BE5
0x180001bdb  lea     rdx, dword_180025214
0x180001be2  mov     eax, r9d
0x180001be5  mov     [rbp+0A0h+var_58], eax
0x180001be8  mov     rax, [rbp+0A0h+arg_90]
0x180001bef  mov     [rbp+0A0h+var_60], rdx
0x180001bf3  mov     [rbp+0A0h+var_54], ebx
0x180001bf6  mov     rdx, [rax]
0x180001bf9  test    rdx, rdx
0x180001bfc  jz      short loc_180001C0D
0x180001bfe  mov     rax, rcx
0x180001c01  inc     rax
0x180001c04  cmp     [rdx+rax], bl
0x180001c07  jnz     short loc_180001C01
0x180001c09  inc     eax
0x180001c0b  jmp     short loc_180001C13
0x180001c0d  mov     rdx, rdi
0x180001c10  mov     eax, r8d
0x180001c13  mov     [rbp+0A0h+var_68], eax
0x180001c16  mov     rax, [rbp+0A0h+arg_88]
0x180001c1d  mov     [rbp+0A0h+var_80], rax
0x180001c21  mov     rax, [rbp+0A0h+arg_80]
0x180001c28  mov     [rbp+0A0h+var_70], rdx
0x180001c2c  mov     [rbp+0A0h+var_64], ebx
0x180001c2f  mov     [rbp+0A0h+var_78], 4
0x180001c37  mov     rdx, [rax]
0x180001c3a  test    rdx, rdx
0x180001c3d  jz      short loc_180001C54
0x180001c3f  mov     rax, rcx
0x180001c42  inc     rax
0x180001c45  cmp     [rdx+rax*2], bx
0x180001c49  jnz     short loc_180001C42
0x180001c4b  lea     eax, ds:2[rax*2]
0x180001c52  jmp     short loc_180001C5E
0x180001c54  lea     rdx, dword_180025214
0x180001c5b  mov     eax, r9d
0x180001c5e  mov     [rbp+0A0h+var_88], eax
0x180001c61  mov     rax, [rbp+0A0h+arg_78]
0x180001c68  mov     [rbp+0A0h+var_90], rdx
0x180001c6c  mov     [rbp+0A0h+var_84], ebx
0x180001c6f  mov     rdx, [rax]
0x180001c72  test    rdx, rdx
0x180001c75  jz      short loc_180001C86
0x180001c77  mov     rax, rcx
0x180001c7a  inc     rax
0x180001c7d  cmp     [rdx+rax], bl
0x180001c80  jnz     short loc_180001C7A
0x180001c82  inc     eax
0x180001c84  jmp     short loc_180001C8C
0x180001c86  mov     rdx, rdi
0x180001c89  mov     eax, r8d
0x180001c8c  mov     [rbp+0A0h+var_98], eax
0x180001c8f  mov     rax, [rbp+0A0h+arg_70]
0x180001c96  mov     [rbp+0A0h+var_B0], rax
0x180001c9a  mov     rax, [rbp+0A0h+arg_68]
0x180001ca1  mov     [rbp+0A0h+var_A0], rdx
0x180001ca5  mov     [rbp+0A0h+var_94], ebx
0x180001ca8  mov     [rbp+0A0h+var_A8], 4
0x180001cb0  mov     rdx, [rax]
0x180001cb3  test    rdx, rdx
0x180001cb6  jz      short loc_180001CC7
0x180001cb8  mov     rax, rcx
0x180001cbb  inc     rax
0x180001cbe  cmp     [rdx+rax], bl
0x180001cc1  jnz     short loc_180001CBB
0x180001cc3  inc     eax
0x180001cc5  jmp     short loc_180001CCD
0x180001cc7  mov     rdx, rdi
0x180001cca  mov     eax, r8d
0x180001ccd  mov     [rbp+0A0h+var_B8], eax
0x180001cd0  mov     rax, [rbp+0A0h+arg_60]
0x180001cd7  mov     [rbp+0A0h+var_D0], rax
0x180001cdb  mov     rax, [rbp+0A0h+arg_58]
0x180001ce2  mov     [rbp+0A0h+var_C0], rdx
0x180001ce6  mov     [rbp+0A0h+var_B4], ebx
0x180001ce9  mov     [rbp+0A0h+var_C8], 4
0x180001cf1  mov     rdx, [rax]
0x180001cf4  test    rdx, rdx
0x180001cf7  jz      short loc_180001D0F
0x180001cf9  mov     rax, rcx
0x180001cfc  inc     rax
0x180001cff  cmp     [rdx+rax*2], bx
0x180001d03  jnz     short loc_180001CFC
0x180001d05  lea     r9d, ds:2[rax*2]
0x180001d0d  jmp     short loc_180001D16
0x180001d0f  lea     rdx, dword_180025214
0x180001d16  mov     rax, [rbp+0A0h+arg_50]
0x180001d1d  mov     [rbp+0A0h+var_F0], rax
0x180001d21  mov     rax, [rbp+0A0h+arg_48]
0x180001d28  mov     [rbp+0A0h+var_E0], rdx
0x180001d2c  mov     [rbp+0A0h+var_D8], r9d
0x180001d30  mov     [rbp+0A0h+var_D4], ebx
0x180001d33  mov     rdx, [rax]
0x180001d36  mov     [rbp+0A0h+var_E8], 4
0x180001d3e  test    rdx, rdx
0x180001d41  jz      short loc_180001D52
0x180001d43  mov     rax, rcx
0x180001d46  inc     rax
0x180001d49  cmp     [rdx+rax], bl
0x180001d4c  jnz     short loc_180001D46
0x180001d4e  inc     eax
0x180001d50  jmp     short loc_180001D58
0x180001d52  mov     rdx, rdi
0x180001d55  mov     eax, r8d
0x180001d58  mov     [rbp+0A0h+var_F8], eax
0x180001d5b  mov     rax, [rbp+0A0h+arg_40]
0x180001d62  mov     [rbp+0A0h+var_110], rax
0x180001d66  mov     rax, [rbp+0A0h+arg_38]
0x180001d6d  mov     [rbp+0A0h+var_100], rdx
0x180001d71  mov     [rbp+0A0h+var_F4], ebx
0x180001d74  mov     [rbp+0A0h+var_108], 4
0x180001d7c  mov     rdx, [rax]
0x180001d7f  test    rdx, rdx
0x180001d82  jz      short loc_180001D92
0x180001d84  inc     rcx
0x180001d87  cmp     [rdx+rcx], bl
0x180001d8a  jnz     short loc_180001D84
0x180001d8c  lea     r8d, [rcx+1]
0x180001d90  jmp     short loc_180001D95
0x180001d92  mov     rdx, rdi
0x180001d95  mov     rax, [rbp+0A0h+arg_30]
0x180001d9c  xor     r9d, r9d
0x180001d9f  mov     [rsp+1A0h+var_130], rax
0x180001da4  mov     rcx, r10
0x180001da7  mov     rax, [rbp+0A0h+arg_28]
0x180001dae  mov     [rsp+1A0h+var_140], rax
0x180001db3  mov     rax, [rbp+0A0h+arg_20]
0x180001dba  mov     [rsp+1A0h+var_150], rax
0x180001dbf  lea     rax, [rsp+1A0h+var_170]
0x180001dc4  mov     [rbp+0A0h+var_120], rdx
0x180001dc8  mov     rdx, r11
0x180001dcb  mov     [rbp+0A0h+var_118], r8d
0x180001dcf  xor     r8d, r8d
0x180001dd2  mov     [rsp+1A0h+var_178], rax
0x180001dd7  mov     [rsp+1A0h+var_180], 15h
0x180001ddf  mov     [rbp+0A0h+var_114], ebx
0x180001de2  mov     [rsp+1A0h+var_128], 4
0x180001deb  mov     [rsp+1A0h+var_138], 8
0x180001df4  mov     [rsp+1A0h+var_148], 8
0x180001dfd  call    _tlgWriteTransfer_EventWriteTransfer
0x180001e02  mov     rcx, [rbp+0A0h+var_20]
0x180001e09  xor     rcx, rsp; StackCookie
0x180001e0c  call    __security_check_cookie
0x180001e11  mov     rbx, [rsp+1A0h+arg_10]
0x180001e19  add     rsp, 190h
0x180001e20  pop     rdi
0x180001e21  pop     rsi
0x180001e22  pop     rbp
0x180001e23  retn
```
