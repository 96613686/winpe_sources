# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)

- ea: `0x140001824`
- end: `0x140001b14`
- name: `??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456445@Z`
- size: `752`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, __int64, __int64, const unsigned __int16 **, __int64, const unsigned __int16 **, __int64, int **, __int64, const unsigned __int16 **, __int64, const unsigned __int16 **, int **, __int64, const unsigned __int16 **, int **, __int64, __int64, const unsigned __int16 **)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x140008b70`
- `0x14000a5f8`

## callees

- `0x140001824`
- `0x140001b9c`
- `0x140002190`

## pseudocode

```c
__int64 __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
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
        int **a11,
        __int64 a12,
        const unsigned __int16 **a13,
        __int64 a14,
        const unsigned __int16 **a15,
        int **a16,
        __int64 a17,
        const unsigned __int16 **a18,
        int **a19,
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
  int *v31; // rcx
  __int64 v32; // rax
  int v33; // eax
  const unsigned __int16 *v34; // rcx
  __int64 v35; // rax
  int v36; // eax
  int *v37; // rcx
  __int64 v38; // rax
  int v39; // eax
  const unsigned __int16 *v40; // rcx
  __int64 v41; // rax
  int v42; // eax
  const unsigned __int16 *v43; // rcx
  __int64 v44; // rax
  int v45; // eax
  int *v46; // rcx
  __int64 v47; // rax
  const unsigned __int16 *v48; // rcx
  __int64 v49; // rax
  int v50; // eax
  const unsigned __int16 *v51; // rcx
  _BYTE v53[32]; // [rsp+30h] [rbp-D0h] BYREF
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
  int *v68; // [rsp+B0h] [rbp-50h]
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
  int *v81; // [rsp+100h] [rbp+0h]
  int v82; // [rsp+108h] [rbp+8h]
  int v83; // [rsp+10Ch] [rbp+Ch]
  __int64 v84; // [rsp+110h] [rbp+10h]
  __int64 v85; // [rsp+118h] [rbp+18h]
  const unsigned __int16 *v86; // [rsp+120h] [rbp+20h]
  int v87; // [rsp+128h] [rbp+28h]
  int v88; // [rsp+12Ch] [rbp+2Ch]
  int *v89; // [rsp+130h] [rbp+30h]
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
    v27 = &byte_140013800;
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
    while ( *((_WORD *)v31 + v32) );
    v33 = 2 * v32 + 2;
  }
  else
  {
    v31 = &dword_140013804;
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
    v34 = &byte_140013800;
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
    while ( *((_WORD *)v37 + v38) );
    v39 = 2 * v38 + 2;
  }
  else
  {
    v37 = &dword_140013804;
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
    v40 = &byte_140013800;
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
    v43 = &byte_140013800;
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
    while ( *((_WORD *)v46 + v47) );
    v30 = 2 * v47 + 2;
  }
  else
  {
    v46 = &dword_140013804;
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
    v48 = &byte_140013800;
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
    v51 = &byte_140013800;
  }
  v56 = a6;
  v54 = a5;
  v58 = v51;
  v59 = v26;
  v60 = 0;
  v57 = 4;
  v55 = 8;
  return tlgWriteTransfer_EventWriteTransfer(a1, a2, a3, 0, 20, v53);
}

```

## disassembly

```asm
0x140001824  push    rbp
0x140001826  push    rbx
0x140001827  push    rsi
0x140001828  push    rdi
0x140001829  push    r15
0x14000182b  lea     rbp, [rsp-80h]
0x140001830  sub     rsp, 180h
0x140001837  mov     rax, cs:__security_cookie
0x14000183e  xor     rax, rsp
0x140001841  mov     [rbp+0A0h+var_30], rax
0x140001845  mov     rax, [rbp+0A0h+arg_A8]
0x14000184c  lea     rsi, byte_140013800
0x140001853  mov     r11, rdx
0x140001856  mov     r10, rcx
0x140001859  or      rdx, 0FFFFFFFFFFFFFFFFh
0x14000185d  xor     edi, edi
0x14000185f  mov     rbx, r8
0x140001862  mov     r8d, 1
0x140001868  mov     rcx, [rax]
0x14000186b  test    rcx, rcx
0x14000186e  jz      short loc_140001880
0x140001870  mov     rax, rdx
0x140001873  inc     rax
0x140001876  cmp     [rcx+rax], dil
0x14000187a  jnz     short loc_140001873
0x14000187c  inc     eax
0x14000187e  jmp     short loc_140001886
0x140001880  mov     rcx, rsi
0x140001883  mov     eax, r8d
0x140001886  mov     [rbp+0A0h+var_38], eax
0x140001889  mov     r9d, 2
0x14000188f  mov     rax, [rbp+0A0h+arg_A0]
0x140001896  mov     [rbp+0A0h+var_50], rax
0x14000189a  mov     rax, [rbp+0A0h+arg_98]
0x1400018a1  mov     [rbp+0A0h+var_60], rax
0x1400018a5  mov     rax, [rbp+0A0h+arg_90]
0x1400018ac  mov     [rbp+0A0h+var_40], rcx
0x1400018b0  mov     [rbp+0A0h+var_34], edi
0x1400018b3  mov     [rbp+0A0h+var_48], 4
0x1400018bb  mov     rcx, [rax]
0x1400018be  mov     [rbp+0A0h+var_58], 4
0x1400018c6  test    rcx, rcx
0x1400018c9  jz      short loc_1400018E0
0x1400018cb  mov     rax, rdx
0x1400018ce  inc     rax
0x1400018d1  cmp     [rcx+rax*2], di
0x1400018d5  jnz     short loc_1400018CE
0x1400018d7  lea     eax, ds:2[rax*2]
0x1400018de  jmp     short loc_1400018EA
0x1400018e0  lea     rcx, dword_140013804
0x1400018e7  mov     eax, r9d
0x1400018ea  mov     [rbp+0A0h+var_68], eax
0x1400018ed  mov     rax, [rbp+0A0h+arg_88]
0x1400018f4  mov     [rbp+0A0h+var_70], rcx
0x1400018f8  mov     [rbp+0A0h+var_64], edi
0x1400018fb  mov     rcx, [rax]
0x1400018fe  test    rcx, rcx
0x140001901  jz      short loc_140001913
0x140001903  mov     rax, rdx
0x140001906  inc     rax
0x140001909  cmp     [rcx+rax], dil
0x14000190d  jnz     short loc_140001906
0x14000190f  inc     eax
0x140001911  jmp     short loc_140001919
0x140001913  mov     rcx, rsi
0x140001916  mov     eax, r8d
0x140001919  mov     [rbp+0A0h+var_78], eax
0x14000191c  mov     rax, [rbp+0A0h+arg_80]
0x140001923  mov     [rbp+0A0h+var_90], rax
0x140001927  mov     rax, [rbp+0A0h+arg_78]
0x14000192e  mov     [rbp+0A0h+var_80], rcx
0x140001932  mov     [rbp+0A0h+var_74], edi
0x140001935  mov     [rbp+0A0h+var_88], 4
0x14000193d  mov     rcx, [rax]
0x140001940  test    rcx, rcx
0x140001943  jz      short loc_14000195A
0x140001945  mov     rax, rdx
0x140001948  inc     rax
0x14000194b  cmp     [rcx+rax*2], di
0x14000194f  jnz     short loc_140001948
0x140001951  lea     eax, ds:2[rax*2]
0x140001958  jmp     short loc_140001964
0x14000195a  lea     rcx, dword_140013804
0x140001961  mov     eax, r9d
0x140001964  mov     [rbp+0A0h+var_98], eax
0x140001967  mov     rax, [rbp+0A0h+arg_70]
0x14000196e  mov     [rbp+0A0h+var_A0], rcx
0x140001972  mov     [rbp+0A0h+var_94], edi
0x140001975  mov     rcx, [rax]
0x140001978  test    rcx, rcx
0x14000197b  jz      short loc_14000198D
0x14000197d  mov     rax, rdx
0x140001980  inc     rax
0x140001983  cmp     [rcx+rax], dil
0x140001987  jnz     short loc_140001980
0x140001989  inc     eax
0x14000198b  jmp     short loc_140001993
0x14000198d  mov     rcx, rsi
0x140001990  mov     eax, r8d
0x140001993  mov     [rbp+0A0h+var_A8], eax
0x140001996  mov     rax, [rbp+0A0h+arg_68]
0x14000199d  mov     [rbp+0A0h+var_C0], rax
0x1400019a1  mov     rax, [rbp+0A0h+arg_60]
0x1400019a8  mov     [rbp+0A0h+var_B0], rcx
0x1400019ac  mov     [rbp+0A0h+var_A4], edi
0x1400019af  mov     [rbp+0A0h+var_B8], 4
0x1400019b7  mov     rcx, [rax]
0x1400019ba  test    rcx, rcx
0x1400019bd  jz      short loc_1400019CF
0x1400019bf  mov     rax, rdx
0x1400019c2  inc     rax
0x1400019c5  cmp     [rcx+rax], dil
0x1400019c9  jnz     short loc_1400019C2
0x1400019cb  inc     eax
0x1400019cd  jmp     short loc_1400019D5
0x1400019cf  mov     rcx, rsi
0x1400019d2  mov     eax, r8d
0x1400019d5  mov     [rbp+0A0h+var_C8], eax
0x1400019d8  mov     rax, [rbp+0A0h+arg_58]
0x1400019df  mov     [rbp+0A0h+var_E0], rax
0x1400019e3  mov     rax, [rbp+0A0h+arg_50]
0x1400019ea  mov     [rbp+0A0h+var_D0], rcx
0x1400019ee  mov     [rbp+0A0h+var_C4], edi
0x1400019f1  mov     [rbp+0A0h+var_D8], 4
0x1400019f9  mov     rcx, [rax]
0x1400019fc  test    rcx, rcx
0x1400019ff  jz      short loc_140001A17
0x140001a01  mov     rax, rdx
0x140001a04  inc     rax
0x140001a07  cmp     [rcx+rax*2], di
0x140001a0b  jnz     short loc_140001A04
0x140001a0d  lea     r9d, ds:2[rax*2]
0x140001a15  jmp     short loc_140001A1E
0x140001a17  lea     rcx, dword_140013804
0x140001a1e  mov     rax, [rbp+0A0h+arg_48]
0x140001a25  mov     [rbp+0A0h+var_100], rax
0x140001a29  mov     rax, [rbp+0A0h+arg_40]
0x140001a30  mov     [rbp+0A0h+var_F0], rcx
0x140001a34  mov     [rbp+0A0h+var_E8], r9d
0x140001a38  mov     [rbp+0A0h+var_E4], edi
0x140001a3b  mov     rcx, [rax]
0x140001a3e  mov     [rbp+0A0h+var_F8], 4
0x140001a46  test    rcx, rcx
0x140001a49  jz      short loc_140001A5B
0x140001a4b  mov     rax, rdx
0x140001a4e  inc     rax
0x140001a51  cmp     [rcx+rax], dil
0x140001a55  jnz     short loc_140001A4E
0x140001a57  inc     eax
0x140001a59  jmp     short loc_140001A61
0x140001a5b  mov     rcx, rsi
0x140001a5e  mov     eax, r8d
0x140001a61  mov     [rbp+0A0h+var_108], eax
0x140001a64  mov     rax, [rbp+0A0h+arg_38]
0x140001a6b  mov     [rbp+0A0h+var_120], rax
0x140001a6f  mov     rax, [rbp+0A0h+arg_30]
0x140001a76  mov     [rbp+0A0h+var_110], rcx
0x140001a7a  mov     [rbp+0A0h+var_104], edi
0x140001a7d  mov     [rbp+0A0h+var_118], 4
0x140001a85  mov     rcx, [rax]
0x140001a88  test    rcx, rcx
0x140001a8b  jz      short loc_140001A9C
0x140001a8d  inc     rdx
0x140001a90  cmp     [rcx+rdx], dil
0x140001a94  jnz     short loc_140001A8D
0x140001a96  lea     r8d, [rdx+1]
0x140001a9a  jmp     short loc_140001A9F
0x140001a9c  mov     rcx, rsi
0x140001a9f  mov     rax, [rbp+0A0h+arg_28]
0x140001aa6  xor     r9d, r9d
0x140001aa9  mov     [rsp+1A0h+var_140], rax
0x140001aae  mov     rdx, r11
0x140001ab1  mov     rax, [rbp+0A0h+arg_20]
0x140001ab8  mov     [rsp+1A0h+var_150], rax
0x140001abd  lea     rax, [rsp+1A0h+var_170]
0x140001ac2  mov     [rsp+1A0h+var_130], rcx
0x140001ac7  mov     rcx, r10
0x140001aca  mov     [rsp+1A0h+var_128], r8d
0x140001acf  mov     r8, rbx
0x140001ad2  mov     [rsp+1A0h+var_178], rax
0x140001ad7  mov     [rsp+1A0h+var_180], 14h
0x140001adf  mov     [rsp+1A0h+var_124], edi
0x140001ae3  mov     [rsp+1A0h+var_138], 4
0x140001aec  mov     [rsp+1A0h+var_148], 8
0x140001af5  call    _tlgWriteTransfer_EventWriteTransfer
0x140001afa  mov     rcx, [rbp+0A0h+var_30]
0x140001afe  xor     rcx, rsp; StackCookie
0x140001b01  call    __security_check_cookie
0x140001b06  add     rsp, 180h
0x140001b0d  pop     r15
0x140001b0f  pop     rdi
0x140001b10  pop     rsi
0x140001b11  pop     rbx
0x140001b12  pop     rbp
0x140001b13  retn
```
