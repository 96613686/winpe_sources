# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)

- ea: `0x140001590`
- end: `0x14000182b`
- name: `??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456@Z`
- size: `667`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, __int64, __int64, const unsigned __int16 **, __int64, const unsigned __int16 **, __int64, __int64 **, __int64, const unsigned __int16 **, __int64, const unsigned __int16 **, __int64 **, __int64, const unsigned __int16 **, __int64 **)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x14000a400`

## callees

- `0x140001590`
- `0x140001bac`
- `0x1400022a0`

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
        __int64 **a11,
        __int64 a12,
        const unsigned __int16 **a13,
        __int64 a14,
        const unsigned __int16 **a15,
        __int64 **a16,
        __int64 a17,
        const unsigned __int16 **a18,
        __int64 **a19)
{
  __int64 v21; // rdx
  int v23; // r9d
  __int64 *v24; // rcx
  __int64 v25; // rax
  int v26; // eax
  int v27; // r8d
  const unsigned __int16 *v28; // rcx
  __int64 v29; // rax
  int v30; // eax
  __int64 *v31; // rcx
  __int64 v32; // rax
  int v33; // eax
  const unsigned __int16 *v34; // rcx
  __int64 v35; // rax
  int v36; // eax
  const unsigned __int16 *v37; // rcx
  __int64 v38; // rax
  int v39; // eax
  __int64 *v40; // rcx
  __int64 v41; // rax
  const unsigned __int16 *v42; // rcx
  __int64 v43; // rax
  int v44; // eax
  const unsigned __int16 *v45; // rcx
  _BYTE v47[32]; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v48; // [rsp+50h] [rbp-B0h]
  __int64 v49; // [rsp+58h] [rbp-A8h]
  __int64 v50; // [rsp+60h] [rbp-A0h]
  __int64 v51; // [rsp+68h] [rbp-98h]
  const unsigned __int16 *v52; // [rsp+70h] [rbp-90h]
  int v53; // [rsp+78h] [rbp-88h]
  int v54; // [rsp+7Ch] [rbp-84h]
  __int64 v55; // [rsp+80h] [rbp-80h]
  __int64 v56; // [rsp+88h] [rbp-78h]
  const unsigned __int16 *v57; // [rsp+90h] [rbp-70h]
  int v58; // [rsp+98h] [rbp-68h]
  int v59; // [rsp+9Ch] [rbp-64h]
  __int64 v60; // [rsp+A0h] [rbp-60h]
  __int64 v61; // [rsp+A8h] [rbp-58h]
  __int64 *v62; // [rsp+B0h] [rbp-50h]
  int v63; // [rsp+B8h] [rbp-48h]
  int v64; // [rsp+BCh] [rbp-44h]
  __int64 v65; // [rsp+C0h] [rbp-40h]
  __int64 v66; // [rsp+C8h] [rbp-38h]
  const unsigned __int16 *v67; // [rsp+D0h] [rbp-30h]
  int v68; // [rsp+D8h] [rbp-28h]
  int v69; // [rsp+DCh] [rbp-24h]
  __int64 v70; // [rsp+E0h] [rbp-20h]
  __int64 v71; // [rsp+E8h] [rbp-18h]
  const unsigned __int16 *v72; // [rsp+F0h] [rbp-10h]
  int v73; // [rsp+F8h] [rbp-8h]
  int v74; // [rsp+FCh] [rbp-4h]
  __int64 *v75; // [rsp+100h] [rbp+0h]
  int v76; // [rsp+108h] [rbp+8h]
  int v77; // [rsp+10Ch] [rbp+Ch]
  __int64 v78; // [rsp+110h] [rbp+10h]
  __int64 v79; // [rsp+118h] [rbp+18h]
  const unsigned __int16 *v80; // [rsp+120h] [rbp+20h]
  int v81; // [rsp+128h] [rbp+28h]
  int v82; // [rsp+12Ch] [rbp+2Ch]
  __int64 *v83; // [rsp+130h] [rbp+30h]
  int v84; // [rsp+138h] [rbp+38h]
  int v85; // [rsp+13Ch] [rbp+3Ch]

  v21 = -1;
  v23 = 2;
  v24 = *a19;
  if ( *a19 )
  {
    v25 = -1;
    do
      ++v25;
    while ( *((_WORD *)v24 + v25) );
    v26 = 2 * v25 + 2;
  }
  else
  {
    v24 = &qword_140013B88;
    v26 = 2;
  }
  v84 = v26;
  v27 = 1;
  v83 = v24;
  v85 = 0;
  v28 = *a18;
  if ( *a18 )
  {
    v29 = -1;
    do
      ++v29;
    while ( *((_BYTE *)v28 + v29) );
    v30 = v29 + 1;
  }
  else
  {
    v28 = &dword_140013B84;
    v30 = 1;
  }
  v81 = v30;
  v78 = a17;
  v80 = v28;
  v82 = 0;
  v79 = 4;
  v31 = *a16;
  if ( *a16 )
  {
    v32 = -1;
    do
      ++v32;
    while ( *((_WORD *)v31 + v32) );
    v33 = 2 * v32 + 2;
  }
  else
  {
    v31 = &qword_140013B88;
    v33 = 2;
  }
  v76 = v33;
  v75 = v31;
  v77 = 0;
  v34 = *a15;
  if ( *a15 )
  {
    v35 = -1;
    do
      ++v35;
    while ( *((_BYTE *)v34 + v35) );
    v36 = v35 + 1;
  }
  else
  {
    v34 = &dword_140013B84;
    v36 = 1;
  }
  v73 = v36;
  v70 = a14;
  v72 = v34;
  v74 = 0;
  v71 = 4;
  v37 = *a13;
  if ( *a13 )
  {
    v38 = -1;
    do
      ++v38;
    while ( *((_BYTE *)v37 + v38) );
    v39 = v38 + 1;
  }
  else
  {
    v37 = &dword_140013B84;
    v39 = 1;
  }
  v68 = v39;
  v65 = a12;
  v67 = v37;
  v69 = 0;
  v66 = 4;
  v40 = *a11;
  if ( *a11 )
  {
    v41 = -1;
    do
      ++v41;
    while ( *((_WORD *)v40 + v41) );
    v23 = 2 * v41 + 2;
  }
  else
  {
    v40 = &qword_140013B88;
  }
  v60 = a10;
  v62 = v40;
  v63 = v23;
  v64 = 0;
  v42 = *a9;
  v61 = 4;
  if ( v42 )
  {
    v43 = -1;
    do
      ++v43;
    while ( *((_BYTE *)v42 + v43) );
    v44 = v43 + 1;
  }
  else
  {
    v42 = &dword_140013B84;
    v44 = 1;
  }
  v58 = v44;
  v55 = a8;
  v57 = v42;
  v59 = 0;
  v56 = 4;
  v45 = *a7;
  if ( *a7 )
  {
    do
      ++v21;
    while ( *((_BYTE *)v45 + v21) );
    v27 = v21 + 1;
  }
  else
  {
    v45 = &dword_140013B84;
  }
  v50 = a6;
  v48 = a5;
  v52 = v45;
  v53 = v27;
  v54 = 0;
  v51 = 4;
  v49 = 8;
  return tlgWriteTransfer_EventWriteTransfer(a1, a2, a3, 0, 17, v47);
}

```

## disassembly

```asm
0x140001590  push    rbp
0x140001592  push    rbx
0x140001593  push    rsi
0x140001594  push    rdi
0x140001595  push    r14
0x140001597  lea     rbp, [rsp-50h]
0x14000159c  sub     rsp, 150h
0x1400015a3  mov     rax, cs:__security_cookie
0x1400015aa  xor     rax, rsp
0x1400015ad  mov     [rbp+70h+var_30], rax
0x1400015b1  mov     rax, [rbp+70h+arg_90]
0x1400015b8  mov     r11, rdx
0x1400015bb  mov     r10, rcx
0x1400015be  or      rdx, 0FFFFFFFFFFFFFFFFh
0x1400015c2  xor     edi, edi
0x1400015c4  mov     rbx, r8
0x1400015c7  mov     r9d, 2
0x1400015cd  mov     rcx, [rax]
0x1400015d0  test    rcx, rcx
0x1400015d3  jz      short loc_1400015EA
0x1400015d5  mov     rax, rdx
0x1400015d8  inc     rax
0x1400015db  cmp     [rcx+rax*2], di
0x1400015df  jnz     short loc_1400015D8
0x1400015e1  lea     eax, ds:2[rax*2]
0x1400015e8  jmp     short loc_1400015F4
0x1400015ea  lea     rcx, qword_140013B88
0x1400015f1  mov     eax, r9d
0x1400015f4  mov     [rbp+70h+var_38], eax
0x1400015f7  lea     rsi, dword_140013B84
0x1400015fe  mov     rax, [rbp+70h+arg_88]
0x140001605  mov     r8d, 1
0x14000160b  mov     [rbp+70h+var_40], rcx
0x14000160f  mov     [rbp+70h+var_34], edi
0x140001612  mov     rcx, [rax]
0x140001615  test    rcx, rcx
0x140001618  jz      short loc_14000162A
0x14000161a  mov     rax, rdx
0x14000161d  inc     rax
0x140001620  cmp     [rcx+rax], dil
0x140001624  jnz     short loc_14000161D
0x140001626  inc     eax
0x140001628  jmp     short loc_140001630
0x14000162a  mov     rcx, rsi
0x14000162d  mov     eax, r8d
0x140001630  mov     [rbp+70h+var_48], eax
0x140001633  mov     rax, [rbp+70h+arg_80]
0x14000163a  mov     [rbp+70h+var_60], rax
0x14000163e  mov     rax, [rbp+70h+arg_78]
0x140001645  mov     [rbp+70h+var_50], rcx
0x140001649  mov     [rbp+70h+var_44], edi
0x14000164c  mov     [rbp+70h+var_58], 4
0x140001654  mov     rcx, [rax]
0x140001657  test    rcx, rcx
0x14000165a  jz      short loc_140001671
0x14000165c  mov     rax, rdx
0x14000165f  inc     rax
0x140001662  cmp     [rcx+rax*2], di
0x140001666  jnz     short loc_14000165F
0x140001668  lea     eax, ds:2[rax*2]
0x14000166f  jmp     short loc_14000167B
0x140001671  lea     rcx, qword_140013B88
0x140001678  mov     eax, r9d
0x14000167b  mov     [rbp+70h+var_68], eax
0x14000167e  mov     rax, [rbp+70h+arg_70]
0x140001685  mov     [rbp+70h+var_70], rcx
0x140001689  mov     [rbp+70h+var_64], edi
0x14000168c  mov     rcx, [rax]
0x14000168f  test    rcx, rcx
0x140001692  jz      short loc_1400016A4
0x140001694  mov     rax, rdx
0x140001697  inc     rax
0x14000169a  cmp     [rcx+rax], dil
0x14000169e  jnz     short loc_140001697
0x1400016a0  inc     eax
0x1400016a2  jmp     short loc_1400016AA
0x1400016a4  mov     rcx, rsi
0x1400016a7  mov     eax, r8d
0x1400016aa  mov     [rbp+70h+var_78], eax
0x1400016ad  mov     rax, [rbp+70h+arg_68]
0x1400016b4  mov     [rbp+70h+var_90], rax
0x1400016b8  mov     rax, [rbp+70h+arg_60]
0x1400016bf  mov     [rbp+70h+var_80], rcx
0x1400016c3  mov     [rbp+70h+var_74], edi
0x1400016c6  mov     [rbp+70h+var_88], 4
0x1400016ce  mov     rcx, [rax]
0x1400016d1  test    rcx, rcx
0x1400016d4  jz      short loc_1400016E6
0x1400016d6  mov     rax, rdx
0x1400016d9  inc     rax
0x1400016dc  cmp     [rcx+rax], dil
0x1400016e0  jnz     short loc_1400016D9
0x1400016e2  inc     eax
0x1400016e4  jmp     short loc_1400016EC
0x1400016e6  mov     rcx, rsi
0x1400016e9  mov     eax, r8d
0x1400016ec  mov     [rbp+70h+var_98], eax
0x1400016ef  mov     rax, [rbp+70h+arg_58]
0x1400016f6  mov     [rbp+70h+var_B0], rax
0x1400016fa  mov     rax, [rbp+70h+arg_50]
0x140001701  mov     [rbp+70h+var_A0], rcx
0x140001705  mov     [rbp+70h+var_94], edi
0x140001708  mov     [rbp+70h+var_A8], 4
0x140001710  mov     rcx, [rax]
0x140001713  test    rcx, rcx
0x140001716  jz      short loc_14000172E
0x140001718  mov     rax, rdx
0x14000171b  inc     rax
0x14000171e  cmp     [rcx+rax*2], di
0x140001722  jnz     short loc_14000171B
0x140001724  lea     r9d, ds:2[rax*2]
0x14000172c  jmp     short loc_140001735
0x14000172e  lea     rcx, qword_140013B88
0x140001735  mov     rax, [rbp+70h+arg_48]
0x14000173c  mov     [rbp+70h+var_D0], rax
0x140001740  mov     rax, [rbp+70h+arg_40]
0x140001747  mov     [rbp+70h+var_C0], rcx
0x14000174b  mov     [rbp+70h+var_B8], r9d
0x14000174f  mov     [rbp+70h+var_B4], edi
0x140001752  mov     rcx, [rax]
0x140001755  mov     [rbp+70h+var_C8], 4
0x14000175d  test    rcx, rcx
0x140001760  jz      short loc_140001772
0x140001762  mov     rax, rdx
0x140001765  inc     rax
0x140001768  cmp     [rcx+rax], dil
0x14000176c  jnz     short loc_140001765
0x14000176e  inc     eax
0x140001770  jmp     short loc_140001778
0x140001772  mov     rcx, rsi
0x140001775  mov     eax, r8d
0x140001778  mov     [rbp+70h+var_D8], eax
0x14000177b  mov     rax, [rbp+70h+arg_38]
0x140001782  mov     [rbp+70h+var_F0], rax
0x140001786  mov     rax, [rbp+70h+arg_30]
0x14000178d  mov     [rbp+70h+var_E0], rcx
0x140001791  mov     [rbp+70h+var_D4], edi
0x140001794  mov     [rbp+70h+var_E8], 4
0x14000179c  mov     rcx, [rax]
0x14000179f  test    rcx, rcx
0x1400017a2  jz      short loc_1400017B3
0x1400017a4  inc     rdx
0x1400017a7  cmp     [rcx+rdx], dil
0x1400017ab  jnz     short loc_1400017A4
0x1400017ad  lea     r8d, [rdx+1]
0x1400017b1  jmp     short loc_1400017B6
0x1400017b3  mov     rcx, rsi
0x1400017b6  mov     rax, [rbp+70h+arg_28]
0x1400017bd  xor     r9d, r9d
0x1400017c0  mov     [rsp+170h+var_110], rax
0x1400017c5  mov     rdx, r11
0x1400017c8  mov     rax, [rbp+70h+arg_20]
0x1400017cf  mov     [rsp+170h+var_120], rax
0x1400017d4  lea     rax, [rsp+170h+var_140]
0x1400017d9  mov     [rsp+170h+var_100], rcx
0x1400017de  mov     rcx, r10
0x1400017e1  mov     [rsp+170h+var_F8], r8d
0x1400017e6  mov     r8, rbx
0x1400017e9  mov     [rsp+170h+var_148], rax
0x1400017ee  mov     [rsp+170h+var_150], 11h
0x1400017f6  mov     [rsp+170h+var_F4], edi
0x1400017fa  mov     [rsp+170h+var_108], 4
0x140001803  mov     [rsp+170h+var_118], 8
0x14000180c  call    _tlgWriteTransfer_EventWriteTransfer
0x140001811  mov     rcx, [rbp+70h+var_30]
0x140001815  xor     rcx, rsp; StackCookie
0x140001818  call    __security_check_cookie
0x14000181d  add     rsp, 150h
0x140001824  pop     r14
0x140001826  pop     rdi
0x140001827  pop     rsi
0x140001828  pop     rbx
0x140001829  pop     rbp
0x14000182a  retn
```
