# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)

- ea: `0x180001008`
- end: `0x18000130c`
- name: `??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@U2@U1@U2@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4434AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456@Z`
- size: `772`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1800107c0`

## callees

- `0x180001008`
- `0x180008988`
- `0x18000b410`

## pseudocode

```c
ULONG __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
        __int64 a1,
        unsigned __int8 *a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        __int64 a7,
        __int64 a8,
        __int64 a9,
        __int64 a10,
        const unsigned __int16 **a11,
        __int64 a12,
        const unsigned __int16 **a13,
        __int64 a14,
        __int64 **a15,
        __int64 a16,
        const unsigned __int16 **a17,
        __int64 a18,
        const unsigned __int16 **a19,
        __int64 **a20,
        __int64 a21,
        const unsigned __int16 **a22,
        __int64 **a23)
{
  __int64 v24; // rcx
  int v25; // r9d
  __int64 *v26; // rdx
  __int64 v27; // rax
  int v28; // eax
  int v29; // r8d
  const unsigned __int16 *v30; // rdx
  __int64 v31; // rax
  int v32; // eax
  __int64 *v33; // rdx
  __int64 v34; // rax
  int v35; // eax
  const unsigned __int16 *v36; // rdx
  __int64 v37; // rax
  int v38; // eax
  const unsigned __int16 *v39; // rdx
  __int64 v40; // rax
  int v41; // eax
  __int64 *v42; // rdx
  __int64 v43; // rax
  const unsigned __int16 *v44; // rdx
  __int64 v45; // rax
  int v46; // eax
  const unsigned __int16 *v47; // rdx
  struct _EVENT_DATA_DESCRIPTOR v49; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v50; // [rsp+50h] [rbp-B0h]
  __int64 v51; // [rsp+58h] [rbp-A8h]
  __int64 v52; // [rsp+60h] [rbp-A0h]
  __int64 v53; // [rsp+68h] [rbp-98h]
  __int64 v54; // [rsp+70h] [rbp-90h]
  __int64 v55; // [rsp+78h] [rbp-88h]
  __int64 v56; // [rsp+80h] [rbp-80h]
  __int64 v57; // [rsp+88h] [rbp-78h]
  __int64 v58; // [rsp+90h] [rbp-70h]
  __int64 v59; // [rsp+98h] [rbp-68h]
  __int64 v60; // [rsp+A0h] [rbp-60h]
  __int64 v61; // [rsp+A8h] [rbp-58h]
  const unsigned __int16 *v62; // [rsp+B0h] [rbp-50h]
  int v63; // [rsp+B8h] [rbp-48h]
  int v64; // [rsp+BCh] [rbp-44h]
  __int64 v65; // [rsp+C0h] [rbp-40h]
  __int64 v66; // [rsp+C8h] [rbp-38h]
  const unsigned __int16 *v67; // [rsp+D0h] [rbp-30h]
  int v68; // [rsp+D8h] [rbp-28h]
  int v69; // [rsp+DCh] [rbp-24h]
  __int64 v70; // [rsp+E0h] [rbp-20h]
  __int64 v71; // [rsp+E8h] [rbp-18h]
  __int64 *v72; // [rsp+F0h] [rbp-10h]
  int v73; // [rsp+F8h] [rbp-8h]
  int v74; // [rsp+FCh] [rbp-4h]
  __int64 v75; // [rsp+100h] [rbp+0h]
  __int64 v76; // [rsp+108h] [rbp+8h]
  const unsigned __int16 *v77; // [rsp+110h] [rbp+10h]
  int v78; // [rsp+118h] [rbp+18h]
  int v79; // [rsp+11Ch] [rbp+1Ch]
  __int64 v80; // [rsp+120h] [rbp+20h]
  __int64 v81; // [rsp+128h] [rbp+28h]
  const unsigned __int16 *v82; // [rsp+130h] [rbp+30h]
  int v83; // [rsp+138h] [rbp+38h]
  int v84; // [rsp+13Ch] [rbp+3Ch]
  __int64 *v85; // [rsp+140h] [rbp+40h]
  int v86; // [rsp+148h] [rbp+48h]
  int v87; // [rsp+14Ch] [rbp+4Ch]
  __int64 v88; // [rsp+150h] [rbp+50h]
  __int64 v89; // [rsp+158h] [rbp+58h]
  const unsigned __int16 *v90; // [rsp+160h] [rbp+60h]
  int v91; // [rsp+168h] [rbp+68h]
  int v92; // [rsp+16Ch] [rbp+6Ch]
  __int64 *v93; // [rsp+170h] [rbp+70h]
  int v94; // [rsp+178h] [rbp+78h]
  int v95; // [rsp+17Ch] [rbp+7Ch]

  v24 = -1;
  v25 = 2;
  v26 = *a23;
  if ( *a23 )
  {
    v27 = -1;
    do
      ++v27;
    while ( *((_WORD *)v26 + v27) );
    v28 = 2 * v27 + 2;
  }
  else
  {
    v26 = &qword_180017AB8;
    v28 = 2;
  }
  v94 = v28;
  v29 = 1;
  v93 = v26;
  v95 = 0;
  v30 = *a22;
  if ( *a22 )
  {
    v31 = -1;
    do
      ++v31;
    while ( *((_BYTE *)v30 + v31) );
    v32 = v31 + 1;
  }
  else
  {
    v30 = &qword_180017450;
    v32 = 1;
  }
  v91 = v32;
  v88 = a21;
  v90 = v30;
  v92 = 0;
  v89 = 4;
  v33 = *a20;
  if ( *a20 )
  {
    v34 = -1;
    do
      ++v34;
    while ( *((_WORD *)v33 + v34) );
    v35 = 2 * v34 + 2;
  }
  else
  {
    v33 = &qword_180017AB8;
    v35 = 2;
  }
  v86 = v35;
  v85 = v33;
  v87 = 0;
  v36 = *a19;
  if ( *a19 )
  {
    v37 = -1;
    do
      ++v37;
    while ( *((_BYTE *)v36 + v37) );
    v38 = v37 + 1;
  }
  else
  {
    v36 = &qword_180017450;
    v38 = 1;
  }
  v83 = v38;
  v80 = a18;
  v82 = v36;
  v84 = 0;
  v81 = 4;
  v39 = *a17;
  if ( *a17 )
  {
    v40 = -1;
    do
      ++v40;
    while ( *((_BYTE *)v39 + v40) );
    v41 = v40 + 1;
  }
  else
  {
    v39 = &qword_180017450;
    v41 = 1;
  }
  v78 = v41;
  v75 = a16;
  v77 = v39;
  v79 = 0;
  v76 = 4;
  v42 = *a15;
  if ( *a15 )
  {
    v43 = -1;
    do
      ++v43;
    while ( *((_WORD *)v42 + v43) );
    v25 = 2 * v43 + 2;
  }
  else
  {
    v42 = &qword_180017AB8;
  }
  v70 = a14;
  v72 = v42;
  v73 = v25;
  v74 = 0;
  v44 = *a13;
  v71 = 4;
  if ( v44 )
  {
    v45 = -1;
    do
      ++v45;
    while ( *((_BYTE *)v44 + v45) );
    v46 = v45 + 1;
  }
  else
  {
    v44 = &qword_180017450;
    v46 = 1;
  }
  v68 = v46;
  v65 = a12;
  v67 = v44;
  v69 = 0;
  v66 = 4;
  v47 = *a11;
  if ( *a11 )
  {
    do
      ++v24;
    while ( *((_BYTE *)v47 + v24) );
    v29 = v24 + 1;
  }
  else
  {
    v47 = &qword_180017450;
  }
  v60 = a10;
  v58 = a9;
  v56 = a8;
  v54 = a7;
  v52 = a6;
  v50 = a5;
  v62 = v47;
  v63 = v29;
  v64 = 0;
  v61 = 4;
  v59 = 8;
  v57 = 4;
  v55 = 4;
  v53 = 4;
  v51 = 8;
  return tlgWriteTransfer_EventWriteTransfer((__int64)&dword_18001C068, a2, 0, 0, 0x15u, &v49);
}

```

## disassembly

```asm
0x180001008  mov     [rsp-8+arg_0], rbx
0x18000100d  mov     [rsp-8+arg_10], rdi
0x180001012  push    rbp
0x180001013  lea     rbp, [rsp-90h]
0x18000101b  sub     rsp, 190h
0x180001022  mov     rax, cs:__security_cookie
0x180001029  xor     rax, rsp
0x18000102c  mov     [rbp+90h+var_10], rax
0x180001033  mov     rax, [rbp+90h+arg_B0]
0x18000103a  mov     r10, rdx
0x18000103d  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180001041  xor     r11d, r11d
0x180001044  mov     r9d, 2
0x18000104a  mov     rdx, [rax]
0x18000104d  test    rdx, rdx
0x180001050  jz      short loc_180001068
0x180001052  mov     rax, rcx
0x180001055  inc     rax
0x180001058  cmp     [rdx+rax*2], r11w
0x18000105d  jnz     short loc_180001055
0x18000105f  lea     eax, ds:2[rax*2]
0x180001066  jmp     short loc_180001072
0x180001068  lea     rdx, qword_180017AB8
0x18000106f  mov     eax, r9d
0x180001072  mov     [rbp+90h+var_18], eax
0x180001075  lea     rdi, qword_180017450
0x18000107c  mov     rax, [rbp+90h+arg_A8]
0x180001083  mov     r8d, 1
0x180001089  mov     [rbp+90h+var_20], rdx
0x18000108d  mov     [rbp+90h+var_14], r11d
0x180001091  mov     rdx, [rax]
0x180001094  test    rdx, rdx
0x180001097  jz      short loc_1800010A9
0x180001099  mov     rax, rcx
0x18000109c  inc     rax
0x18000109f  cmp     [rdx+rax], r11b
0x1800010a3  jnz     short loc_18000109C
0x1800010a5  inc     eax
0x1800010a7  jmp     short loc_1800010AF
0x1800010a9  mov     rdx, rdi
0x1800010ac  mov     eax, r8d
0x1800010af  mov     [rbp+90h+var_28], eax
0x1800010b2  mov     rax, [rbp+90h+arg_A0]
0x1800010b9  mov     [rbp+90h+var_40], rax
0x1800010bd  mov     rax, [rbp+90h+arg_98]
0x1800010c4  mov     [rbp+90h+var_30], rdx
0x1800010c8  mov     [rbp+90h+var_24], r11d
0x1800010cc  mov     [rbp+90h+var_38], 4
0x1800010d4  mov     rdx, [rax]
0x1800010d7  test    rdx, rdx
0x1800010da  jz      short loc_1800010F2
0x1800010dc  mov     rax, rcx
0x1800010df  inc     rax
0x1800010e2  cmp     [rdx+rax*2], r11w
0x1800010e7  jnz     short loc_1800010DF
0x1800010e9  lea     eax, ds:2[rax*2]
0x1800010f0  jmp     short loc_1800010FC
0x1800010f2  lea     rdx, qword_180017AB8
0x1800010f9  mov     eax, r9d
0x1800010fc  mov     [rbp+90h+var_48], eax
0x1800010ff  mov     rax, [rbp+90h+arg_90]
0x180001106  mov     [rbp+90h+var_50], rdx
0x18000110a  mov     [rbp+90h+var_44], r11d
0x18000110e  mov     rdx, [rax]
0x180001111  test    rdx, rdx
0x180001114  jz      short loc_180001126
0x180001116  mov     rax, rcx
0x180001119  inc     rax
0x18000111c  cmp     [rdx+rax], r11b
0x180001120  jnz     short loc_180001119
0x180001122  inc     eax
0x180001124  jmp     short loc_18000112C
0x180001126  mov     rdx, rdi
0x180001129  mov     eax, r8d
0x18000112c  mov     [rbp+90h+var_58], eax
0x18000112f  mov     rax, [rbp+90h+arg_88]
0x180001136  mov     [rbp+90h+var_70], rax
0x18000113a  mov     rax, [rbp+90h+arg_80]
0x180001141  mov     [rbp+90h+var_60], rdx
0x180001145  mov     [rbp+90h+var_54], r11d
0x180001149  mov     [rbp+90h+var_68], 4
0x180001151  mov     rdx, [rax]
0x180001154  test    rdx, rdx
0x180001157  jz      short loc_180001169
0x180001159  mov     rax, rcx
0x18000115c  inc     rax
0x18000115f  cmp     [rdx+rax], r11b
0x180001163  jnz     short loc_18000115C
0x180001165  inc     eax
0x180001167  jmp     short loc_18000116F
0x180001169  mov     rdx, rdi
0x18000116c  mov     eax, r8d
0x18000116f  mov     [rbp+90h+var_78], eax
0x180001172  mov     rax, [rbp+90h+arg_78]
0x180001179  mov     [rbp+90h+var_90], rax
0x18000117d  mov     rax, [rbp+90h+arg_70]
0x180001184  mov     [rbp+90h+var_80], rdx
0x180001188  mov     [rbp+90h+var_74], r11d
0x18000118c  mov     [rbp+90h+var_88], 4
0x180001194  mov     rdx, [rax]
0x180001197  test    rdx, rdx
0x18000119a  jz      short loc_1800011B3
0x18000119c  mov     rax, rcx
0x18000119f  inc     rax
0x1800011a2  cmp     [rdx+rax*2], r11w
0x1800011a7  jnz     short loc_18000119F
0x1800011a9  lea     r9d, ds:2[rax*2]
0x1800011b1  jmp     short loc_1800011BA
0x1800011b3  lea     rdx, qword_180017AB8
0x1800011ba  mov     rax, [rbp+90h+arg_68]
0x1800011c1  mov     [rbp+90h+var_B0], rax
0x1800011c5  mov     rax, [rbp+90h+arg_60]
0x1800011cc  mov     [rbp+90h+var_A0], rdx
0x1800011d0  mov     [rbp+90h+var_98], r9d
0x1800011d4  mov     [rbp+90h+var_94], r11d
0x1800011d8  mov     rdx, [rax]
0x1800011db  mov     [rbp+90h+var_A8], 4
0x1800011e3  test    rdx, rdx
0x1800011e6  jz      short loc_1800011F8
0x1800011e8  mov     rax, rcx
0x1800011eb  inc     rax
0x1800011ee  cmp     [rdx+rax], r11b
0x1800011f2  jnz     short loc_1800011EB
0x1800011f4  inc     eax
0x1800011f6  jmp     short loc_1800011FE
0x1800011f8  mov     rdx, rdi
0x1800011fb  mov     eax, r8d
0x1800011fe  mov     [rbp+90h+var_B8], eax
0x180001201  mov     rax, [rbp+90h+arg_58]
0x180001208  mov     [rbp+90h+var_D0], rax
0x18000120c  mov     rax, [rbp+90h+arg_50]
0x180001213  mov     [rbp+90h+var_C0], rdx
0x180001217  mov     [rbp+90h+var_B4], r11d
0x18000121b  mov     [rbp+90h+var_C8], 4
0x180001223  mov     rdx, [rax]
0x180001226  test    rdx, rdx
0x180001229  jz      short loc_18000123A
0x18000122b  inc     rcx
0x18000122e  cmp     [rdx+rcx], r11b
0x180001232  jnz     short loc_18000122B
0x180001234  lea     r8d, [rcx+1]
0x180001238  jmp     short loc_18000123D
0x18000123a  mov     rdx, rdi
0x18000123d  mov     rax, [rbp+90h+arg_48]
0x180001244  lea     rcx, dword_18001C068
0x18000124b  mov     [rbp+90h+var_F0], rax
0x18000124f  xor     r9d, r9d
0x180001252  mov     rax, [rbp+90h+arg_40]
0x180001259  mov     [rbp+90h+var_100], rax
0x18000125d  mov     rax, [rbp+90h+arg_38]
0x180001264  mov     [rbp+90h+var_110], rax
0x180001268  mov     rax, [rbp+90h+arg_30]
0x18000126f  mov     [rsp+190h+var_120], rax
0x180001274  mov     rax, [rbp+90h+arg_28]
0x18000127b  mov     [rsp+190h+var_130], rax
0x180001280  mov     rax, [rbp+90h+arg_20]
0x180001287  mov     [rsp+190h+var_140], rax
0x18000128c  lea     rax, [rsp+190h+var_160]
0x180001291  mov     [rbp+90h+var_E0], rdx
0x180001295  mov     rdx, r10
0x180001298  mov     [rbp+90h+var_D8], r8d
0x18000129c  xor     r8d, r8d
0x18000129f  mov     [rsp+190h+var_168], rax
0x1800012a4  mov     [rsp+190h+var_170], 15h
0x1800012ac  mov     [rbp+90h+var_D4], r11d
0x1800012b0  mov     [rbp+90h+var_E8], 4
0x1800012b8  mov     [rbp+90h+var_F8], 8
0x1800012c0  mov     [rbp+90h+var_108], 4
0x1800012c8  mov     [rsp+190h+var_118], 4
0x1800012d1  mov     [rsp+190h+var_128], 4
0x1800012da  mov     [rsp+190h+var_138], 8
0x1800012e3  call    _tlgWriteTransfer_EventWriteTransfer
0x1800012e8  mov     rcx, [rbp+90h+var_10]
0x1800012ef  xor     rcx, rsp; StackCookie
0x1800012f2  call    __security_check_cookie
0x1800012f7  lea     r11, [rsp+190h+var_s0]
0x1800012ff  mov     rbx, [r11+10h]
0x180001303  mov     rdi, [r11+20h]
0x180001307  mov     rsp, r11
0x18000130a  pop     rbp
0x18000130b  retn
```
