# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)

- ea: `0x140001010`
- end: `0x1400012b1`
- name: `??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456@Z`
- size: `673`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, __int64, __int64, const unsigned __int16 **, __int64, const unsigned __int16 **, __int64, const WCHAR **, __int64, const unsigned __int16 **, __int64, const unsigned __int16 **, const WCHAR **, __int64, const unsigned __int16 **, const WCHAR **)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x140010030`

## callees

- `0x140001010`
- `0x1400019e8`
- `0x1400029a0`

## pseudocode

```c
__int64 __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
        __int64 a1,
        __int64 a2,
        __int64 a3,
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
        const WCHAR **a19)
{
  __int64 v19; // r10
  const WCHAR *v20; // rax
  __int64 v21; // r9
  bool v22; // zf
  int v23; // r9d
  int v24; // r11d
  int v25; // ebx
  const unsigned __int16 *v26; // r9
  __int64 v27; // rax
  int v28; // eax
  const WCHAR *v29; // r9
  __int64 v30; // rax
  int v31; // eax
  const unsigned __int16 *v32; // r9
  __int64 v33; // rax
  int v34; // eax
  const unsigned __int16 *v35; // r9
  __int64 v36; // rax
  int v37; // eax
  const WCHAR *v38; // r9
  __int64 v39; // rax
  const unsigned __int16 *v40; // r9
  __int64 v41; // rax
  int v42; // eax
  const unsigned __int16 *v43; // r9
  _BYTE v45[32]; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v46; // [rsp+50h] [rbp-B0h]
  __int64 v47; // [rsp+58h] [rbp-A8h]
  __int64 v48; // [rsp+60h] [rbp-A0h]
  __int64 v49; // [rsp+68h] [rbp-98h]
  const unsigned __int16 *v50; // [rsp+70h] [rbp-90h]
  int v51; // [rsp+78h] [rbp-88h]
  int v52; // [rsp+7Ch] [rbp-84h]
  __int64 v53; // [rsp+80h] [rbp-80h]
  __int64 v54; // [rsp+88h] [rbp-78h]
  const unsigned __int16 *v55; // [rsp+90h] [rbp-70h]
  int v56; // [rsp+98h] [rbp-68h]
  int v57; // [rsp+9Ch] [rbp-64h]
  __int64 v58; // [rsp+A0h] [rbp-60h]
  __int64 v59; // [rsp+A8h] [rbp-58h]
  const WCHAR *v60; // [rsp+B0h] [rbp-50h]
  int v61; // [rsp+B8h] [rbp-48h]
  int v62; // [rsp+BCh] [rbp-44h]
  __int64 v63; // [rsp+C0h] [rbp-40h]
  __int64 v64; // [rsp+C8h] [rbp-38h]
  const unsigned __int16 *v65; // [rsp+D0h] [rbp-30h]
  int v66; // [rsp+D8h] [rbp-28h]
  int v67; // [rsp+DCh] [rbp-24h]
  __int64 v68; // [rsp+E0h] [rbp-20h]
  __int64 v69; // [rsp+E8h] [rbp-18h]
  const unsigned __int16 *v70; // [rsp+F0h] [rbp-10h]
  int v71; // [rsp+F8h] [rbp-8h]
  int v72; // [rsp+FCh] [rbp-4h]
  const WCHAR *v73; // [rsp+100h] [rbp+0h]
  int v74; // [rsp+108h] [rbp+8h]
  int v75; // [rsp+10Ch] [rbp+Ch]
  __int64 v76; // [rsp+110h] [rbp+10h]
  __int64 v77; // [rsp+118h] [rbp+18h]
  const unsigned __int16 *v78; // [rsp+120h] [rbp+20h]
  int v79; // [rsp+128h] [rbp+28h]
  int v80; // [rsp+12Ch] [rbp+2Ch]
  const WCHAR *v81; // [rsp+130h] [rbp+30h]
  int v82; // [rsp+138h] [rbp+38h]
  int v83; // [rsp+13Ch] [rbp+3Ch]

  v19 = -1;
  v20 = *a19;
  if ( *a19 )
  {
    v21 = -1;
    do
      v22 = v20[++v21] == 0;
    while ( !v22 );
    v23 = 2 * v21 + 2;
    v24 = 2;
  }
  else
  {
    v24 = 2;
    v20 = &String;
    v23 = 2;
  }
  v81 = v20;
  v25 = 1;
  v82 = v23;
  v83 = 0;
  v26 = *a18;
  if ( *a18 )
  {
    v27 = -1;
    do
      ++v27;
    while ( *((_BYTE *)v26 + v27) );
    v28 = v27 + 1;
  }
  else
  {
    v26 = &qword_14001A178;
    v28 = 1;
  }
  v79 = v28;
  v76 = a17;
  v78 = v26;
  v80 = 0;
  v77 = 4;
  v29 = *a16;
  if ( *a16 )
  {
    v30 = -1;
    do
      v22 = v29[++v30] == 0;
    while ( !v22 );
    v31 = 2 * v30 + 2;
  }
  else
  {
    v29 = &String;
    v31 = 2;
  }
  v74 = v31;
  v73 = v29;
  v75 = 0;
  v32 = *a15;
  if ( *a15 )
  {
    v33 = -1;
    do
      ++v33;
    while ( *((_BYTE *)v32 + v33) );
    v34 = v33 + 1;
  }
  else
  {
    v32 = &qword_14001A178;
    v34 = 1;
  }
  v71 = v34;
  v68 = a14;
  v70 = v32;
  v72 = 0;
  v69 = 4;
  v35 = *a13;
  if ( *a13 )
  {
    v36 = -1;
    do
      ++v36;
    while ( *((_BYTE *)v35 + v36) );
    v37 = v36 + 1;
  }
  else
  {
    v35 = &qword_14001A178;
    v37 = 1;
  }
  v66 = v37;
  v63 = a12;
  v65 = v35;
  v67 = 0;
  v64 = 4;
  v38 = *a11;
  if ( *a11 )
  {
    v39 = -1;
    do
      v22 = v38[++v39] == 0;
    while ( !v22 );
    v24 = 2 * v39 + 2;
  }
  else
  {
    v38 = &String;
  }
  v58 = a10;
  v60 = v38;
  v61 = v24;
  v62 = 0;
  v40 = *a9;
  v59 = 4;
  if ( v40 )
  {
    v41 = -1;
    do
      ++v41;
    while ( *((_BYTE *)v40 + v41) );
    v42 = v41 + 1;
  }
  else
  {
    v40 = &qword_14001A178;
    v42 = 1;
  }
  v56 = v42;
  v53 = a8;
  v55 = v40;
  v57 = 0;
  v54 = 4;
  v43 = *a7;
  if ( *a7 )
  {
    do
      v22 = *((_BYTE *)v43 + ++v19) == 0;
    while ( !v22 );
    v25 = v19 + 1;
  }
  else
  {
    v43 = &qword_14001A178;
  }
  v48 = a6;
  v46 = a5;
  v50 = v43;
  v51 = v25;
  v52 = 0;
  v49 = 4;
  v47 = 8;
  return tlgWriteTransfer_EventWriteTransfer(a1, a2, a3, 0, 17, v45);
}

```

## disassembly

```asm
0x140001010  push    rbp
0x140001012  push    rbx
0x140001013  push    rdi
0x140001014  lea     rbp, [rsp-50h]
0x140001019  sub     rsp, 150h
0x140001020  mov     rax, cs:__security_cookie
0x140001027  xor     rax, rsp
0x14000102a  mov     [rbp+60h+var_20], rax
0x14000102e  mov     rax, [rbp+60h+arg_90]
0x140001035  mov     r10, 0FFFFFFFFFFFFFFFFh
0x14000103c  mov     rax, [rax]
0x14000103f  test    rax, rax
0x140001042  jz      short loc_140001064
0x140001044  mov     r9, r10
0x140001047  cmp     word ptr [rax+r9*2+2], 0
0x14000104e  lea     r9, [r9+1]
0x140001052  jnz     short loc_140001047
0x140001054  lea     r9d, ds:2[r9*2]
0x14000105c  mov     r11d, 2
0x140001062  jmp     short loc_140001074
0x140001064  mov     r11d, 2
0x14000106a  lea     rax, String
0x140001071  mov     r9d, r11d
0x140001074  xor     edi, edi
0x140001076  mov     [rbp+60h+var_30], rax
0x14000107a  mov     rax, [rbp+60h+arg_88]
0x140001081  mov     ebx, 1
0x140001086  mov     [rbp+60h+var_28], r9d
0x14000108a  mov     [rbp+60h+var_24], edi
0x14000108d  mov     r9, [rax]
0x140001090  test    r9, r9
0x140001093  jz      short loc_1400010A5
0x140001095  mov     rax, r10
0x140001098  inc     rax
0x14000109b  cmp     [r9+rax], dil
0x14000109f  jnz     short loc_140001098
0x1400010a1  inc     eax
0x1400010a3  jmp     short loc_1400010AE
0x1400010a5  lea     r9, qword_14001A178
0x1400010ac  mov     eax, ebx
0x1400010ae  mov     [rbp+60h+var_38], eax
0x1400010b1  mov     rax, [rbp+60h+arg_80]
0x1400010b8  mov     [rbp+60h+var_50], rax
0x1400010bc  mov     rax, [rbp+60h+arg_78]
0x1400010c3  mov     [rbp+60h+var_40], r9
0x1400010c7  mov     [rbp+60h+var_34], edi
0x1400010ca  mov     [rbp+60h+var_48], 4
0x1400010d2  mov     r9, [rax]
0x1400010d5  test    r9, r9
0x1400010d8  jz      short loc_1400010F2
0x1400010da  mov     rax, r10
0x1400010dd  cmp     [r9+rax*2+2], di
0x1400010e3  lea     rax, [rax+1]
0x1400010e7  jnz     short loc_1400010DD
0x1400010e9  lea     eax, ds:2[rax*2]
0x1400010f0  jmp     short loc_1400010FC
0x1400010f2  lea     r9, String
0x1400010f9  mov     eax, r11d
0x1400010fc  mov     [rbp+60h+var_58], eax
0x1400010ff  mov     rax, [rbp+60h+arg_70]
0x140001106  mov     [rbp+60h+var_60], r9
0x14000110a  mov     [rbp+60h+var_54], edi
0x14000110d  mov     r9, [rax]
0x140001110  test    r9, r9
0x140001113  jz      short loc_140001125
0x140001115  mov     rax, r10
0x140001118  inc     rax
0x14000111b  cmp     [r9+rax], dil
0x14000111f  jnz     short loc_140001118
0x140001121  inc     eax
0x140001123  jmp     short loc_14000112E
0x140001125  lea     r9, qword_14001A178
0x14000112c  mov     eax, ebx
0x14000112e  mov     [rbp+60h+var_68], eax
0x140001131  mov     rax, [rbp+60h+arg_68]
0x140001138  mov     [rbp+60h+var_80], rax
0x14000113c  mov     rax, [rbp+60h+arg_60]
0x140001143  mov     [rbp+60h+var_70], r9
0x140001147  mov     [rbp+60h+var_64], edi
0x14000114a  mov     [rbp+60h+var_78], 4
0x140001152  mov     r9, [rax]
0x140001155  test    r9, r9
0x140001158  jz      short loc_14000116A
0x14000115a  mov     rax, r10
0x14000115d  inc     rax
0x140001160  cmp     [r9+rax], dil
0x140001164  jnz     short loc_14000115D
0x140001166  inc     eax
0x140001168  jmp     short loc_140001173
0x14000116a  lea     r9, qword_14001A178
0x140001171  mov     eax, ebx
0x140001173  mov     [rbp+60h+var_88], eax
0x140001176  mov     rax, [rbp+60h+arg_58]
0x14000117d  mov     [rbp+60h+var_A0], rax
0x140001181  mov     rax, [rbp+60h+arg_50]
0x140001188  mov     [rbp+60h+var_90], r9
0x14000118c  mov     [rbp+60h+var_84], edi
0x14000118f  mov     [rbp+60h+var_98], 4
0x140001197  mov     r9, [rax]
0x14000119a  test    r9, r9
0x14000119d  jz      short loc_1400011B8
0x14000119f  mov     rax, r10
0x1400011a2  cmp     [r9+rax*2+2], di
0x1400011a8  lea     rax, [rax+1]
0x1400011ac  jnz     short loc_1400011A2
0x1400011ae  lea     r11d, ds:2[rax*2]
0x1400011b6  jmp     short loc_1400011BF
0x1400011b8  lea     r9, String
0x1400011bf  mov     rax, [rbp+60h+arg_48]
0x1400011c6  mov     [rbp+60h+var_C0], rax
0x1400011ca  mov     rax, [rbp+60h+arg_40]
0x1400011d1  mov     [rbp+60h+var_B0], r9
0x1400011d5  mov     [rbp+60h+var_A8], r11d
0x1400011d9  mov     [rbp+60h+var_A4], edi
0x1400011dc  mov     r9, [rax]
0x1400011df  mov     [rbp+60h+var_B8], 4
0x1400011e7  test    r9, r9
0x1400011ea  jz      short loc_1400011FC
0x1400011ec  mov     rax, r10
0x1400011ef  inc     rax
0x1400011f2  cmp     [r9+rax], dil
0x1400011f6  jnz     short loc_1400011EF
0x1400011f8  inc     eax
0x1400011fa  jmp     short loc_140001205
0x1400011fc  lea     r9, qword_14001A178
0x140001203  mov     eax, ebx
0x140001205  mov     [rbp+60h+var_C8], eax
0x140001208  mov     rax, [rbp+60h+arg_38]
0x14000120f  mov     [rbp+60h+var_E0], rax
0x140001213  mov     rax, [rbp+60h+arg_30]
0x14000121a  mov     [rbp+60h+var_D0], r9
0x14000121e  mov     [rbp+60h+var_C4], edi
0x140001221  mov     [rbp+60h+var_D8], 4
0x140001229  mov     r9, [rax]
0x14000122c  test    r9, r9
0x14000122f  jz      short loc_140001242
0x140001231  cmp     [r9+r10+1], dil
0x140001236  lea     r10, [r10+1]
0x14000123a  jnz     short loc_140001231
0x14000123c  lea     ebx, [r10+1]
0x140001240  jmp     short loc_140001249
0x140001242  lea     r9, qword_14001A178
0x140001249  mov     rax, [rbp+60h+arg_28]
0x140001250  mov     [rsp+160h+var_100], rax
0x140001255  mov     rax, [rbp+60h+arg_20]
0x14000125c  mov     [rsp+160h+var_110], rax
0x140001261  lea     rax, [rsp+160h+var_130]
0x140001266  mov     [rsp+160h+var_F0], r9
0x14000126b  xor     r9d, r9d
0x14000126e  mov     [rsp+160h+var_138], rax
0x140001273  mov     [rsp+160h+var_140], 11h
0x14000127b  mov     [rsp+160h+var_E8], ebx
0x14000127f  mov     [rsp+160h+var_E4], edi
0x140001283  mov     [rsp+160h+var_F8], 4
0x14000128c  mov     [rsp+160h+var_108], 8
0x140001295  call    _tlgWriteTransfer_EventWriteTransfer
0x14000129a  mov     rcx, [rbp+60h+var_20]
0x14000129e  xor     rcx, rsp; StackCookie
0x1400012a1  call    __security_check_cookie
0x1400012a6  add     rsp, 150h
0x1400012ad  pop     rdi
0x1400012ae  pop     rbx
0x1400012af  pop     rbp
0x1400012b0  retn
```
