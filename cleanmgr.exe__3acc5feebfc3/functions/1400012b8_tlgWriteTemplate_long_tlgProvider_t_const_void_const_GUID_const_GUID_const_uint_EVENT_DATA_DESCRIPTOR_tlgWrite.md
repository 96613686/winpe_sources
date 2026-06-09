# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)

- ea: `0x1400012b8`
- end: `0x140001565`
- name: `??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456@Z`
- size: `685`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, __int64, __int64, __int64, const unsigned __int16 **, __int64, const unsigned __int16 **, __int64, const WCHAR **, __int64, const unsigned __int16 **, __int64, const unsigned __int16 **, const WCHAR **, __int64, const unsigned __int16 **, const WCHAR **)`
- caller_count: `8`
- callee_count: `3`
- tags: ``

## callers

- `0x14000e17c`
- `0x140010e00`
- `0x140011030`
- `0x140011260`
- `0x140011490`
- `0x1400116c0`
- `0x1400118f0`
- `0x140011b20`

## callees

- `0x1400012b8`
- `0x1400019e8`
- `0x1400029a0`

## pseudocode

```c
__int64 __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
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
        const WCHAR **a12,
        __int64 a13,
        const unsigned __int16 **a14,
        __int64 a15,
        const unsigned __int16 **a16,
        const WCHAR **a17,
        __int64 a18,
        const unsigned __int16 **a19,
        const WCHAR **a20)
{
  __int64 v22; // rdx
  int v24; // r9d
  const WCHAR *v25; // rcx
  __int64 v26; // rax
  int v27; // eax
  int v28; // r8d
  const unsigned __int16 *v29; // rcx
  __int64 v30; // rax
  int v31; // eax
  const WCHAR *v32; // rcx
  __int64 v33; // rax
  int v34; // eax
  const unsigned __int16 *v35; // rcx
  __int64 v36; // rax
  int v37; // eax
  const unsigned __int16 *v38; // rcx
  __int64 v39; // rax
  int v40; // eax
  const WCHAR *v41; // rcx
  __int64 v42; // rax
  const unsigned __int16 *v43; // rcx
  __int64 v44; // rax
  int v45; // eax
  const unsigned __int16 *v46; // rcx
  _BYTE v48[32]; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v49; // [rsp+50h] [rbp-B0h]
  __int64 v50; // [rsp+58h] [rbp-A8h]
  __int64 v51; // [rsp+60h] [rbp-A0h]
  __int64 v52; // [rsp+68h] [rbp-98h]
  __int64 v53; // [rsp+70h] [rbp-90h]
  __int64 v54; // [rsp+78h] [rbp-88h]
  const unsigned __int16 *v55; // [rsp+80h] [rbp-80h]
  int v56; // [rsp+88h] [rbp-78h]
  int v57; // [rsp+8Ch] [rbp-74h]
  __int64 v58; // [rsp+90h] [rbp-70h]
  __int64 v59; // [rsp+98h] [rbp-68h]
  const unsigned __int16 *v60; // [rsp+A0h] [rbp-60h]
  int v61; // [rsp+A8h] [rbp-58h]
  int v62; // [rsp+ACh] [rbp-54h]
  __int64 v63; // [rsp+B0h] [rbp-50h]
  __int64 v64; // [rsp+B8h] [rbp-48h]
  const WCHAR *v65; // [rsp+C0h] [rbp-40h]
  int v66; // [rsp+C8h] [rbp-38h]
  int v67; // [rsp+CCh] [rbp-34h]
  __int64 v68; // [rsp+D0h] [rbp-30h]
  __int64 v69; // [rsp+D8h] [rbp-28h]
  const unsigned __int16 *v70; // [rsp+E0h] [rbp-20h]
  int v71; // [rsp+E8h] [rbp-18h]
  int v72; // [rsp+ECh] [rbp-14h]
  __int64 v73; // [rsp+F0h] [rbp-10h]
  __int64 v74; // [rsp+F8h] [rbp-8h]
  const unsigned __int16 *v75; // [rsp+100h] [rbp+0h]
  int v76; // [rsp+108h] [rbp+8h]
  int v77; // [rsp+10Ch] [rbp+Ch]
  const WCHAR *v78; // [rsp+110h] [rbp+10h]
  int v79; // [rsp+118h] [rbp+18h]
  int v80; // [rsp+11Ch] [rbp+1Ch]
  __int64 v81; // [rsp+120h] [rbp+20h]
  __int64 v82; // [rsp+128h] [rbp+28h]
  const unsigned __int16 *v83; // [rsp+130h] [rbp+30h]
  int v84; // [rsp+138h] [rbp+38h]
  int v85; // [rsp+13Ch] [rbp+3Ch]
  const WCHAR *v86; // [rsp+140h] [rbp+40h]
  int v87; // [rsp+148h] [rbp+48h]
  int v88; // [rsp+14Ch] [rbp+4Ch]

  v22 = -1;
  v24 = 2;
  v25 = *a20;
  if ( *a20 )
  {
    v26 = -1;
    do
      ++v26;
    while ( v25[v26] );
    v27 = 2 * v26 + 2;
  }
  else
  {
    v25 = &String;
    v27 = 2;
  }
  v87 = v27;
  v28 = 1;
  v86 = v25;
  v88 = 0;
  v29 = *a19;
  if ( *a19 )
  {
    v30 = -1;
    do
      ++v30;
    while ( *((_BYTE *)v29 + v30) );
    v31 = v30 + 1;
  }
  else
  {
    v29 = &qword_14001A178;
    v31 = 1;
  }
  v84 = v31;
  v81 = a18;
  v83 = v29;
  v85 = 0;
  v82 = 4;
  v32 = *a17;
  if ( *a17 )
  {
    v33 = -1;
    do
      ++v33;
    while ( v32[v33] );
    v34 = 2 * v33 + 2;
  }
  else
  {
    v32 = &String;
    v34 = 2;
  }
  v79 = v34;
  v78 = v32;
  v80 = 0;
  v35 = *a16;
  if ( *a16 )
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
  v76 = v37;
  v73 = a15;
  v75 = v35;
  v77 = 0;
  v74 = 4;
  v38 = *a14;
  if ( *a14 )
  {
    v39 = -1;
    do
      ++v39;
    while ( *((_BYTE *)v38 + v39) );
    v40 = v39 + 1;
  }
  else
  {
    v38 = &qword_14001A178;
    v40 = 1;
  }
  v71 = v40;
  v68 = a13;
  v70 = v38;
  v72 = 0;
  v69 = 4;
  v41 = *a12;
  if ( *a12 )
  {
    v42 = -1;
    do
      ++v42;
    while ( v41[v42] );
    v24 = 2 * v42 + 2;
  }
  else
  {
    v41 = &String;
  }
  v63 = a11;
  v65 = v41;
  v66 = v24;
  v67 = 0;
  v43 = *a10;
  v64 = 4;
  if ( v43 )
  {
    v44 = -1;
    do
      ++v44;
    while ( *((_BYTE *)v43 + v44) );
    v45 = v44 + 1;
  }
  else
  {
    v43 = &qword_14001A178;
    v45 = 1;
  }
  v61 = v45;
  v58 = a9;
  v60 = v43;
  v62 = 0;
  v59 = 4;
  v46 = *a8;
  if ( *a8 )
  {
    do
      ++v22;
    while ( *((_BYTE *)v46 + v22) );
    v28 = v22 + 1;
  }
  else
  {
    v46 = &qword_14001A178;
  }
  v53 = a7;
  v51 = a6;
  v49 = a5;
  v55 = v46;
  v56 = v28;
  v57 = 0;
  v54 = 4;
  v52 = 8;
  v50 = 8;
  return tlgWriteTransfer_EventWriteTransfer(a1, a2, a3, 0, 18, v48);
}

```

## disassembly

```asm
0x1400012b8  push    rbp
0x1400012ba  push    rbx
0x1400012bb  push    rsi
0x1400012bc  push    rdi
0x1400012bd  push    r14
0x1400012bf  lea     rbp, [rsp-60h]
0x1400012c4  sub     rsp, 160h
0x1400012cb  mov     rax, cs:__security_cookie
0x1400012d2  xor     rax, rsp
0x1400012d5  mov     [rbp+80h+var_30], rax
0x1400012d9  mov     rax, [rbp+80h+arg_98]
0x1400012e0  mov     r11, rdx
0x1400012e3  mov     r10, rcx
0x1400012e6  or      rdx, 0FFFFFFFFFFFFFFFFh
0x1400012ea  xor     edi, edi
0x1400012ec  mov     rbx, r8
0x1400012ef  mov     r9d, 2
0x1400012f5  mov     rcx, [rax]
0x1400012f8  test    rcx, rcx
0x1400012fb  jz      short loc_140001312
0x1400012fd  mov     rax, rdx
0x140001300  inc     rax
0x140001303  cmp     [rcx+rax*2], di
0x140001307  jnz     short loc_140001300
0x140001309  lea     eax, ds:2[rax*2]
0x140001310  jmp     short loc_14000131C
0x140001312  lea     rcx, String
0x140001319  mov     eax, r9d
0x14000131c  mov     [rbp+80h+var_38], eax
0x14000131f  lea     rsi, qword_14001A178
0x140001326  mov     rax, [rbp+80h+arg_90]
0x14000132d  mov     r8d, 1
0x140001333  mov     [rbp+80h+var_40], rcx
0x140001337  mov     [rbp+80h+var_34], edi
0x14000133a  mov     rcx, [rax]
0x14000133d  test    rcx, rcx
0x140001340  jz      short loc_140001352
0x140001342  mov     rax, rdx
0x140001345  inc     rax
0x140001348  cmp     [rcx+rax], dil
0x14000134c  jnz     short loc_140001345
0x14000134e  inc     eax
0x140001350  jmp     short loc_140001358
0x140001352  mov     rcx, rsi
0x140001355  mov     eax, r8d
0x140001358  mov     [rbp+80h+var_48], eax
0x14000135b  mov     rax, [rbp+80h+arg_88]
0x140001362  mov     [rbp+80h+var_60], rax
0x140001366  mov     rax, [rbp+80h+arg_80]
0x14000136d  mov     [rbp+80h+var_50], rcx
0x140001371  mov     [rbp+80h+var_44], edi
0x140001374  mov     [rbp+80h+var_58], 4
0x14000137c  mov     rcx, [rax]
0x14000137f  test    rcx, rcx
0x140001382  jz      short loc_140001399
0x140001384  mov     rax, rdx
0x140001387  inc     rax
0x14000138a  cmp     [rcx+rax*2], di
0x14000138e  jnz     short loc_140001387
0x140001390  lea     eax, ds:2[rax*2]
0x140001397  jmp     short loc_1400013A3
0x140001399  lea     rcx, String
0x1400013a0  mov     eax, r9d
0x1400013a3  mov     [rbp+80h+var_68], eax
0x1400013a6  mov     rax, [rbp+80h+arg_78]
0x1400013ad  mov     [rbp+80h+var_70], rcx
0x1400013b1  mov     [rbp+80h+var_64], edi
0x1400013b4  mov     rcx, [rax]
0x1400013b7  test    rcx, rcx
0x1400013ba  jz      short loc_1400013CC
0x1400013bc  mov     rax, rdx
0x1400013bf  inc     rax
0x1400013c2  cmp     [rcx+rax], dil
0x1400013c6  jnz     short loc_1400013BF
0x1400013c8  inc     eax
0x1400013ca  jmp     short loc_1400013D2
0x1400013cc  mov     rcx, rsi
0x1400013cf  mov     eax, r8d
0x1400013d2  mov     [rbp+80h+var_78], eax
0x1400013d5  mov     rax, [rbp+80h+arg_70]
0x1400013dc  mov     [rbp+80h+var_90], rax
0x1400013e0  mov     rax, [rbp+80h+arg_68]
0x1400013e7  mov     [rbp+80h+var_80], rcx
0x1400013eb  mov     [rbp+80h+var_74], edi
0x1400013ee  mov     [rbp+80h+var_88], 4
0x1400013f6  mov     rcx, [rax]
0x1400013f9  test    rcx, rcx
0x1400013fc  jz      short loc_14000140E
0x1400013fe  mov     rax, rdx
0x140001401  inc     rax
0x140001404  cmp     [rcx+rax], dil
0x140001408  jnz     short loc_140001401
0x14000140a  inc     eax
0x14000140c  jmp     short loc_140001414
0x14000140e  mov     rcx, rsi
0x140001411  mov     eax, r8d
0x140001414  mov     [rbp+80h+var_98], eax
0x140001417  mov     rax, [rbp+80h+arg_60]
0x14000141e  mov     [rbp+80h+var_B0], rax
0x140001422  mov     rax, [rbp+80h+arg_58]
0x140001429  mov     [rbp+80h+var_A0], rcx
0x14000142d  mov     [rbp+80h+var_94], edi
0x140001430  mov     [rbp+80h+var_A8], 4
0x140001438  mov     rcx, [rax]
0x14000143b  test    rcx, rcx
0x14000143e  jz      short loc_140001456
0x140001440  mov     rax, rdx
0x140001443  inc     rax
0x140001446  cmp     [rcx+rax*2], di
0x14000144a  jnz     short loc_140001443
0x14000144c  lea     r9d, ds:2[rax*2]
0x140001454  jmp     short loc_14000145D
0x140001456  lea     rcx, String
0x14000145d  mov     rax, [rbp+80h+arg_50]
0x140001464  mov     [rbp+80h+var_D0], rax
0x140001468  mov     rax, [rbp+80h+arg_48]
0x14000146f  mov     [rbp+80h+var_C0], rcx
0x140001473  mov     [rbp+80h+var_B8], r9d
0x140001477  mov     [rbp+80h+var_B4], edi
0x14000147a  mov     rcx, [rax]
0x14000147d  mov     [rbp+80h+var_C8], 4
0x140001485  test    rcx, rcx
0x140001488  jz      short loc_14000149A
0x14000148a  mov     rax, rdx
0x14000148d  inc     rax
0x140001490  cmp     [rcx+rax], dil
0x140001494  jnz     short loc_14000148D
0x140001496  inc     eax
0x140001498  jmp     short loc_1400014A0
0x14000149a  mov     rcx, rsi
0x14000149d  mov     eax, r8d
0x1400014a0  mov     [rbp+80h+var_D8], eax
0x1400014a3  mov     rax, [rbp+80h+arg_40]
0x1400014aa  mov     [rbp+80h+var_F0], rax
0x1400014ae  mov     rax, [rbp+80h+arg_38]
0x1400014b5  mov     [rbp+80h+var_E0], rcx
0x1400014b9  mov     [rbp+80h+var_D4], edi
0x1400014bc  mov     [rbp+80h+var_E8], 4
0x1400014c4  mov     rcx, [rax]
0x1400014c7  test    rcx, rcx
0x1400014ca  jz      short loc_1400014DB
0x1400014cc  inc     rdx
0x1400014cf  cmp     [rcx+rdx], dil
0x1400014d3  jnz     short loc_1400014CC
0x1400014d5  lea     r8d, [rdx+1]
0x1400014d9  jmp     short loc_1400014DE
0x1400014db  mov     rcx, rsi
0x1400014de  mov     rax, [rbp+80h+arg_30]
0x1400014e5  xor     r9d, r9d
0x1400014e8  mov     [rsp+180h+var_110], rax
0x1400014ed  mov     rdx, r11
0x1400014f0  mov     rax, [rbp+80h+arg_28]
0x1400014f7  mov     [rsp+180h+var_120], rax
0x1400014fc  mov     rax, [rbp+80h+arg_20]
0x140001503  mov     [rsp+180h+var_130], rax
0x140001508  lea     rax, [rsp+180h+var_150]
0x14000150d  mov     [rbp+80h+var_100], rcx
0x140001511  mov     rcx, r10
0x140001514  mov     [rbp+80h+var_F8], r8d
0x140001518  mov     r8, rbx
0x14000151b  mov     [rsp+180h+var_158], rax
0x140001520  mov     [rsp+180h+var_160], 12h
0x140001528  mov     [rbp+80h+var_F4], edi
0x14000152b  mov     [rsp+180h+var_108], 4
0x140001534  mov     [rsp+180h+var_118], 8
0x14000153d  mov     [rsp+180h+var_128], 8
0x140001546  call    _tlgWriteTransfer_EventWriteTransfer
0x14000154b  mov     rcx, [rbp+80h+var_30]
0x14000154f  xor     rcx, rsp; StackCookie
0x140001552  call    __security_check_cookie
0x140001557  add     rsp, 160h
0x14000155e  pop     r14
0x140001560  pop     rdi
0x140001561  pop     rsi
0x140001562  pop     rbx
0x140001563  pop     rbp
0x140001564  retn
```
