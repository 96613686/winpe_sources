# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<char> const &,_tlgWrapperByRef<16> const &,_tlgWrapSz<char> const &,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)

- ea: `0x180002a98`
- end: `0x180002d3e`
- name: `??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByRef@$0BA@@@U1@U3@U?$_tlgWrapperByVal@$03@@U4@U4@U4@U4@U4@U4@U4@U4@U4@U4@U4@U4@U4@U4@U4@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByRef@$0BA@@@35AEBU?$_tlgWrapperByVal@$03@@6666666666666666@Z`
- size: `678`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18001d09c`

## callees

- `0x180001448`
- `0x180002a98`
- `0x1800036f0`

## pseudocode

```c
ULONG __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        __int64 a1,
        unsigned __int8 *a2,
        __int64 a3,
        __int64 a4,
        const unsigned __int16 **a5,
        __int64 a6,
        const unsigned __int16 **a7,
        __int64 *a8,
        const unsigned __int16 **a9,
        __int64 *a10,
        __int64 a11,
        __int64 a12,
        __int64 a13,
        __int64 a14,
        __int64 a15,
        __int64 a16,
        __int64 a17,
        __int64 a18,
        __int64 a19,
        __int64 a20,
        __int64 a21,
        __int64 a22,
        __int64 a23,
        __int64 a24,
        __int64 a25,
        __int64 a26,
        __int64 a27)
{
  __int64 v29; // rdx
  int v30; // r8d
  const unsigned __int16 *v31; // rcx
  __int64 v32; // rax
  int v33; // eax
  const unsigned __int16 *v34; // rcx
  __int64 v35; // rax
  int v36; // eax
  const unsigned __int16 *v37; // rcx
  struct _EVENT_DATA_DESCRIPTOR v39; // [rsp+30h] [rbp-D0h] BYREF
  const unsigned __int16 *v40; // [rsp+50h] [rbp-B0h]
  int v41; // [rsp+58h] [rbp-A8h]
  int v42; // [rsp+5Ch] [rbp-A4h]
  __int64 v43; // [rsp+60h] [rbp-A0h]
  __int64 v44; // [rsp+68h] [rbp-98h]
  const unsigned __int16 *v45; // [rsp+70h] [rbp-90h]
  int v46; // [rsp+78h] [rbp-88h]
  int v47; // [rsp+7Ch] [rbp-84h]
  __int64 v48; // [rsp+80h] [rbp-80h]
  __int64 v49; // [rsp+88h] [rbp-78h]
  const unsigned __int16 *v50; // [rsp+90h] [rbp-70h]
  int v51; // [rsp+98h] [rbp-68h]
  int v52; // [rsp+9Ch] [rbp-64h]
  __int64 v53; // [rsp+A0h] [rbp-60h]
  __int64 v54; // [rsp+A8h] [rbp-58h]
  __int64 v55; // [rsp+B0h] [rbp-50h]
  __int64 v56; // [rsp+B8h] [rbp-48h]
  __int64 v57; // [rsp+C0h] [rbp-40h]
  __int64 v58; // [rsp+C8h] [rbp-38h]
  __int64 v59; // [rsp+D0h] [rbp-30h]
  __int64 v60; // [rsp+D8h] [rbp-28h]
  __int64 v61; // [rsp+E0h] [rbp-20h]
  __int64 v62; // [rsp+E8h] [rbp-18h]
  __int64 v63; // [rsp+F0h] [rbp-10h]
  __int64 v64; // [rsp+F8h] [rbp-8h]
  __int64 v65; // [rsp+100h] [rbp+0h]
  __int64 v66; // [rsp+108h] [rbp+8h]
  __int64 v67; // [rsp+110h] [rbp+10h]
  __int64 v68; // [rsp+118h] [rbp+18h]
  __int64 v69; // [rsp+120h] [rbp+20h]
  __int64 v70; // [rsp+128h] [rbp+28h]
  __int64 v71; // [rsp+130h] [rbp+30h]
  __int64 v72; // [rsp+138h] [rbp+38h]
  __int64 v73; // [rsp+140h] [rbp+40h]
  __int64 v74; // [rsp+148h] [rbp+48h]
  __int64 v75; // [rsp+150h] [rbp+50h]
  __int64 v76; // [rsp+158h] [rbp+58h]
  __int64 v77; // [rsp+160h] [rbp+60h]
  __int64 v78; // [rsp+168h] [rbp+68h]
  __int64 v79; // [rsp+170h] [rbp+70h]
  __int64 v80; // [rsp+178h] [rbp+78h]
  __int64 v81; // [rsp+180h] [rbp+80h]
  __int64 v82; // [rsp+188h] [rbp+88h]
  __int64 v83; // [rsp+190h] [rbp+90h]
  __int64 v84; // [rsp+198h] [rbp+98h]
  __int64 v85; // [rsp+1A0h] [rbp+A0h]
  __int64 v86; // [rsp+1A8h] [rbp+A8h]
  __int64 v87; // [rsp+1B0h] [rbp+B0h]
  __int64 v88; // [rsp+1B8h] [rbp+B8h]

  v87 = a27;
  v85 = a26;
  v29 = -1;
  v83 = a25;
  v30 = 1;
  v81 = a24;
  v79 = a23;
  v77 = a22;
  v75 = a21;
  v73 = a20;
  v71 = a19;
  v69 = a18;
  v67 = a17;
  v65 = a16;
  v63 = a15;
  v61 = a14;
  v59 = a13;
  v57 = a12;
  v55 = a11;
  v88 = 4;
  v86 = 4;
  v84 = 4;
  v53 = *a10;
  v82 = 4;
  v80 = 4;
  v31 = *a9;
  v78 = 4;
  v76 = 4;
  v74 = 4;
  v72 = 4;
  v70 = 4;
  v68 = 4;
  v66 = 4;
  v64 = 4;
  v62 = 4;
  v60 = 4;
  v58 = 4;
  v56 = 4;
  v54 = 16;
  if ( v31 )
  {
    v32 = -1;
    do
      ++v32;
    while ( *((_BYTE *)v31 + v32) );
    v33 = v32 + 1;
  }
  else
  {
    v31 = &qword_18002D6C0;
    v33 = 1;
  }
  v51 = v33;
  v50 = v31;
  v52 = 0;
  v49 = 16;
  v48 = *a8;
  v34 = *a7;
  if ( *a7 )
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
  v46 = v36;
  v43 = a6;
  v45 = v34;
  v47 = 0;
  v44 = 8;
  v37 = *a5;
  if ( *a5 )
  {
    do
      ++v29;
    while ( *((_BYTE *)v37 + v29) );
    v30 = v29 + 1;
  }
  else
  {
    v37 = &qword_18002D6C0;
  }
  v40 = v37;
  v41 = v30;
  v42 = 0;
  return tlgWriteTransfer_EventWriteTransfer(a1, a2, 0, 0, 0x19u, &v39);
}

```

## disassembly

```asm
0x180002a98  push    rbp
0x180002a9a  lea     rbp, [rsp-0D0h]
0x180002aa2  sub     rsp, 1D0h
0x180002aa9  mov     rax, cs:__security_cookie
0x180002ab0  xor     rax, rsp
0x180002ab3  mov     [rbp+0D0h+var_10], rax
0x180002aba  mov     rax, [rbp+0D0h+arg_D0]
0x180002ac1  mov     r10, rcx
0x180002ac4  mov     [rbp+0D0h+var_20], rax
0x180002acb  xor     r9d, r9d
0x180002ace  mov     rax, [rbp+0D0h+arg_C8]
0x180002ad5  mov     r11, rdx
0x180002ad8  mov     [rbp+0D0h+var_30], rax
0x180002adf  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180002ae3  mov     rax, [rbp+0D0h+arg_C0]
0x180002aea  mov     [rbp+0D0h+var_40], rax
0x180002af1  lea     r8d, [r9+1]
0x180002af5  mov     rax, [rbp+0D0h+arg_B8]
0x180002afc  mov     [rbp+0D0h+var_50], rax
0x180002b03  mov     rax, [rbp+0D0h+arg_B0]
0x180002b0a  mov     [rbp+0D0h+var_60], rax
0x180002b0e  mov     rax, [rbp+0D0h+arg_A8]
0x180002b15  mov     [rbp+0D0h+var_70], rax
0x180002b19  mov     rax, [rbp+0D0h+arg_A0]
0x180002b20  mov     [rbp+0D0h+var_80], rax
0x180002b24  mov     rax, [rbp+0D0h+arg_98]
0x180002b2b  mov     [rbp+0D0h+var_90], rax
0x180002b2f  mov     rax, [rbp+0D0h+arg_90]
0x180002b36  mov     [rbp+0D0h+var_A0], rax
0x180002b3a  mov     rax, [rbp+0D0h+arg_88]
0x180002b41  mov     [rbp+0D0h+var_B0], rax
0x180002b45  mov     rax, [rbp+0D0h+arg_80]
0x180002b4c  mov     [rbp+0D0h+var_C0], rax
0x180002b50  mov     rax, [rbp+0D0h+arg_78]
0x180002b57  mov     [rbp+0D0h+var_D0], rax
0x180002b5b  mov     rax, [rbp+0D0h+arg_70]
0x180002b62  mov     [rbp+0D0h+var_E0], rax
0x180002b66  mov     rax, [rbp+0D0h+arg_68]
0x180002b6d  mov     [rbp+0D0h+var_F0], rax
0x180002b71  mov     rax, [rbp+0D0h+arg_60]
0x180002b78  mov     [rbp+0D0h+var_100], rax
0x180002b7c  mov     rax, [rbp+0D0h+arg_58]
0x180002b83  mov     [rbp+0D0h+var_110], rax
0x180002b87  mov     rax, [rbp+0D0h+arg_50]
0x180002b8e  mov     [rbp+0D0h+var_120], rax
0x180002b92  mov     rax, [rbp+0D0h+arg_48]
0x180002b99  mov     [rbp+0D0h+var_18], 4
0x180002ba4  mov     [rbp+0D0h+var_28], 4
0x180002baf  mov     [rbp+0D0h+var_38], 4
0x180002bba  mov     rcx, [rax]
0x180002bbd  mov     rax, [rbp+0D0h+arg_40]
0x180002bc4  mov     [rbp+0D0h+var_130], rcx
0x180002bc8  mov     [rbp+0D0h+var_48], 4
0x180002bd3  mov     [rbp+0D0h+var_58], 4
0x180002bdb  mov     rcx, [rax]
0x180002bde  mov     [rbp+0D0h+var_68], 4
0x180002be6  mov     [rbp+0D0h+var_78], 4
0x180002bee  mov     [rbp+0D0h+var_88], 4
0x180002bf6  mov     [rbp+0D0h+var_98], 4
0x180002bfe  mov     [rbp+0D0h+var_A8], 4
0x180002c06  mov     [rbp+0D0h+var_B8], 4
0x180002c0e  mov     [rbp+0D0h+var_C8], 4
0x180002c16  mov     [rbp+0D0h+var_D8], 4
0x180002c1e  mov     [rbp+0D0h+var_E8], 4
0x180002c26  mov     [rbp+0D0h+var_F8], 4
0x180002c2e  mov     [rbp+0D0h+var_108], 4
0x180002c36  mov     [rbp+0D0h+var_118], 4
0x180002c3e  mov     [rbp+0D0h+var_128], 10h
0x180002c46  test    rcx, rcx
0x180002c49  jz      short loc_180002C5B
0x180002c4b  mov     rax, rdx
0x180002c4e  inc     rax
0x180002c51  cmp     [rcx+rax], r9b
0x180002c55  jnz     short loc_180002C4E
0x180002c57  inc     eax
0x180002c59  jmp     short loc_180002C65
0x180002c5b  lea     rcx, qword_18002D6C0
0x180002c62  mov     eax, r8d
0x180002c65  mov     [rbp+0D0h+var_138], eax
0x180002c68  mov     rax, [rbp+0D0h+arg_38]
0x180002c6f  mov     [rbp+0D0h+var_140], rcx
0x180002c73  mov     [rbp+0D0h+var_134], r9d
0x180002c77  mov     [rbp+0D0h+var_148], 10h
0x180002c7f  mov     rcx, [rax]
0x180002c82  mov     rax, [rbp+0D0h+arg_30]
0x180002c89  mov     [rbp+0D0h+var_150], rcx
0x180002c8d  mov     rcx, [rax]
0x180002c90  test    rcx, rcx
0x180002c93  jz      short loc_180002CA5
0x180002c95  mov     rax, rdx
0x180002c98  inc     rax
0x180002c9b  cmp     [rcx+rax], r9b
0x180002c9f  jnz     short loc_180002C98
0x180002ca1  inc     eax
0x180002ca3  jmp     short loc_180002CAF
0x180002ca5  lea     rcx, qword_18002D6C0
0x180002cac  mov     eax, r8d
0x180002caf  mov     [rsp+1D0h+var_158], eax
0x180002cb3  mov     rax, [rbp+0D0h+arg_28]
0x180002cba  mov     [rsp+1D0h+var_170], rax
0x180002cbf  mov     rax, [rbp+0D0h+arg_20]
0x180002cc6  mov     [rsp+1D0h+var_160], rcx
0x180002ccb  mov     [rsp+1D0h+var_154], r9d
0x180002cd0  mov     [rsp+1D0h+var_168], 8
0x180002cd9  mov     rcx, [rax]
0x180002cdc  test    rcx, rcx
0x180002cdf  jz      short loc_180002CF0
0x180002ce1  inc     rdx
0x180002ce4  cmp     [rcx+rdx], r9b
0x180002ce8  jnz     short loc_180002CE1
0x180002cea  lea     r8d, [rdx+1]
0x180002cee  jmp     short loc_180002CF7
0x180002cf0  lea     rcx, qword_18002D6C0
0x180002cf7  lea     rax, [rsp+1D0h+var_1A0]
0x180002cfc  mov     [rsp+1D0h+var_180], rcx
0x180002d01  mov     [rsp+1D0h+var_178], r8d
0x180002d06  mov     rdx, r11
0x180002d09  mov     [rsp+1D0h+var_1A8], rax
0x180002d0e  xor     r8d, r8d
0x180002d11  mov     rcx, r10
0x180002d14  mov     [rsp+1D0h+var_1B0], 19h
0x180002d1c  mov     [rsp+1D0h+var_174], r9d
0x180002d21  call    _tlgWriteTransfer_EventWriteTransfer
0x180002d26  mov     rcx, [rbp+0D0h+var_10]
0x180002d2d  xor     rcx, rsp; StackCookie
0x180002d30  call    __security_check_cookie
0x180002d35  add     rsp, 1D0h
0x180002d3c  pop     rbp
0x180002d3d  retn
```
