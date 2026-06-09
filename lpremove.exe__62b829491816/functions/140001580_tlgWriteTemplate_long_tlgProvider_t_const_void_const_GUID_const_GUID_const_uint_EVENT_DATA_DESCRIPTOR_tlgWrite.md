# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)

- ea: `0x140001580`
- end: `0x14000181b`
- name: `??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456@Z`
- size: `667`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, __int64, __int64, const unsigned __int16 **, __int64, const unsigned __int16 **, __int64, int **, __int64, const unsigned __int16 **, __int64, const unsigned __int16 **, int **, __int64, const unsigned __int16 **, int **)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x140008b70`

## callees

- `0x140001580`
- `0x140001b9c`
- `0x140002190`

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
        int **a11,
        __int64 a12,
        const unsigned __int16 **a13,
        __int64 a14,
        const unsigned __int16 **a15,
        int **a16,
        __int64 a17,
        const unsigned __int16 **a18,
        int **a19)
{
  __int64 v21; // rdx
  int v23; // r9d
  int *v24; // rcx
  __int64 v25; // rax
  int v26; // eax
  int v27; // r8d
  const unsigned __int16 *v28; // rcx
  __int64 v29; // rax
  int v30; // eax
  int *v31; // rcx
  __int64 v32; // rax
  int v33; // eax
  const unsigned __int16 *v34; // rcx
  __int64 v35; // rax
  int v36; // eax
  const unsigned __int16 *v37; // rcx
  __int64 v38; // rax
  int v39; // eax
  int *v40; // rcx
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
  int *v62; // [rsp+B0h] [rbp-50h]
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
  int *v75; // [rsp+100h] [rbp+0h]
  int v76; // [rsp+108h] [rbp+8h]
  int v77; // [rsp+10Ch] [rbp+Ch]
  __int64 v78; // [rsp+110h] [rbp+10h]
  __int64 v79; // [rsp+118h] [rbp+18h]
  const unsigned __int16 *v80; // [rsp+120h] [rbp+20h]
  int v81; // [rsp+128h] [rbp+28h]
  int v82; // [rsp+12Ch] [rbp+2Ch]
  int *v83; // [rsp+130h] [rbp+30h]
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
    v24 = &dword_140013804;
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
    v28 = &byte_140013800;
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
    v31 = &dword_140013804;
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
    v34 = &byte_140013800;
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
    v37 = &byte_140013800;
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
    v40 = &dword_140013804;
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
    v42 = &byte_140013800;
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
    v45 = &byte_140013800;
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
0x140001580  push    rbp
0x140001582  push    rbx
0x140001583  push    rsi
0x140001584  push    rdi
0x140001585  push    r14
0x140001587  lea     rbp, [rsp-50h]
0x14000158c  sub     rsp, 150h
0x140001593  mov     rax, cs:__security_cookie
0x14000159a  xor     rax, rsp
0x14000159d  mov     [rbp+70h+var_30], rax
0x1400015a1  mov     rax, [rbp+70h+arg_90]
0x1400015a8  mov     r11, rdx
0x1400015ab  mov     r10, rcx
0x1400015ae  or      rdx, 0FFFFFFFFFFFFFFFFh
0x1400015b2  xor     edi, edi
0x1400015b4  mov     rbx, r8
0x1400015b7  mov     r9d, 2
0x1400015bd  mov     rcx, [rax]
0x1400015c0  test    rcx, rcx
0x1400015c3  jz      short loc_1400015DA
0x1400015c5  mov     rax, rdx
0x1400015c8  inc     rax
0x1400015cb  cmp     [rcx+rax*2], di
0x1400015cf  jnz     short loc_1400015C8
0x1400015d1  lea     eax, ds:2[rax*2]
0x1400015d8  jmp     short loc_1400015E4
0x1400015da  lea     rcx, dword_140013804
0x1400015e1  mov     eax, r9d
0x1400015e4  mov     [rbp+70h+var_38], eax
0x1400015e7  lea     rsi, byte_140013800
0x1400015ee  mov     rax, [rbp+70h+arg_88]
0x1400015f5  mov     r8d, 1
0x1400015fb  mov     [rbp+70h+var_40], rcx
0x1400015ff  mov     [rbp+70h+var_34], edi
0x140001602  mov     rcx, [rax]
0x140001605  test    rcx, rcx
0x140001608  jz      short loc_14000161A
0x14000160a  mov     rax, rdx
0x14000160d  inc     rax
0x140001610  cmp     [rcx+rax], dil
0x140001614  jnz     short loc_14000160D
0x140001616  inc     eax
0x140001618  jmp     short loc_140001620
0x14000161a  mov     rcx, rsi
0x14000161d  mov     eax, r8d
0x140001620  mov     [rbp+70h+var_48], eax
0x140001623  mov     rax, [rbp+70h+arg_80]
0x14000162a  mov     [rbp+70h+var_60], rax
0x14000162e  mov     rax, [rbp+70h+arg_78]
0x140001635  mov     [rbp+70h+var_50], rcx
0x140001639  mov     [rbp+70h+var_44], edi
0x14000163c  mov     [rbp+70h+var_58], 4
0x140001644  mov     rcx, [rax]
0x140001647  test    rcx, rcx
0x14000164a  jz      short loc_140001661
0x14000164c  mov     rax, rdx
0x14000164f  inc     rax
0x140001652  cmp     [rcx+rax*2], di
0x140001656  jnz     short loc_14000164F
0x140001658  lea     eax, ds:2[rax*2]
0x14000165f  jmp     short loc_14000166B
0x140001661  lea     rcx, dword_140013804
0x140001668  mov     eax, r9d
0x14000166b  mov     [rbp+70h+var_68], eax
0x14000166e  mov     rax, [rbp+70h+arg_70]
0x140001675  mov     [rbp+70h+var_70], rcx
0x140001679  mov     [rbp+70h+var_64], edi
0x14000167c  mov     rcx, [rax]
0x14000167f  test    rcx, rcx
0x140001682  jz      short loc_140001694
0x140001684  mov     rax, rdx
0x140001687  inc     rax
0x14000168a  cmp     [rcx+rax], dil
0x14000168e  jnz     short loc_140001687
0x140001690  inc     eax
0x140001692  jmp     short loc_14000169A
0x140001694  mov     rcx, rsi
0x140001697  mov     eax, r8d
0x14000169a  mov     [rbp+70h+var_78], eax
0x14000169d  mov     rax, [rbp+70h+arg_68]
0x1400016a4  mov     [rbp+70h+var_90], rax
0x1400016a8  mov     rax, [rbp+70h+arg_60]
0x1400016af  mov     [rbp+70h+var_80], rcx
0x1400016b3  mov     [rbp+70h+var_74], edi
0x1400016b6  mov     [rbp+70h+var_88], 4
0x1400016be  mov     rcx, [rax]
0x1400016c1  test    rcx, rcx
0x1400016c4  jz      short loc_1400016D6
0x1400016c6  mov     rax, rdx
0x1400016c9  inc     rax
0x1400016cc  cmp     [rcx+rax], dil
0x1400016d0  jnz     short loc_1400016C9
0x1400016d2  inc     eax
0x1400016d4  jmp     short loc_1400016DC
0x1400016d6  mov     rcx, rsi
0x1400016d9  mov     eax, r8d
0x1400016dc  mov     [rbp+70h+var_98], eax
0x1400016df  mov     rax, [rbp+70h+arg_58]
0x1400016e6  mov     [rbp+70h+var_B0], rax
0x1400016ea  mov     rax, [rbp+70h+arg_50]
0x1400016f1  mov     [rbp+70h+var_A0], rcx
0x1400016f5  mov     [rbp+70h+var_94], edi
0x1400016f8  mov     [rbp+70h+var_A8], 4
0x140001700  mov     rcx, [rax]
0x140001703  test    rcx, rcx
0x140001706  jz      short loc_14000171E
0x140001708  mov     rax, rdx
0x14000170b  inc     rax
0x14000170e  cmp     [rcx+rax*2], di
0x140001712  jnz     short loc_14000170B
0x140001714  lea     r9d, ds:2[rax*2]
0x14000171c  jmp     short loc_140001725
0x14000171e  lea     rcx, dword_140013804
0x140001725  mov     rax, [rbp+70h+arg_48]
0x14000172c  mov     [rbp+70h+var_D0], rax
0x140001730  mov     rax, [rbp+70h+arg_40]
0x140001737  mov     [rbp+70h+var_C0], rcx
0x14000173b  mov     [rbp+70h+var_B8], r9d
0x14000173f  mov     [rbp+70h+var_B4], edi
0x140001742  mov     rcx, [rax]
0x140001745  mov     [rbp+70h+var_C8], 4
0x14000174d  test    rcx, rcx
0x140001750  jz      short loc_140001762
0x140001752  mov     rax, rdx
0x140001755  inc     rax
0x140001758  cmp     [rcx+rax], dil
0x14000175c  jnz     short loc_140001755
0x14000175e  inc     eax
0x140001760  jmp     short loc_140001768
0x140001762  mov     rcx, rsi
0x140001765  mov     eax, r8d
0x140001768  mov     [rbp+70h+var_D8], eax
0x14000176b  mov     rax, [rbp+70h+arg_38]
0x140001772  mov     [rbp+70h+var_F0], rax
0x140001776  mov     rax, [rbp+70h+arg_30]
0x14000177d  mov     [rbp+70h+var_E0], rcx
0x140001781  mov     [rbp+70h+var_D4], edi
0x140001784  mov     [rbp+70h+var_E8], 4
0x14000178c  mov     rcx, [rax]
0x14000178f  test    rcx, rcx
0x140001792  jz      short loc_1400017A3
0x140001794  inc     rdx
0x140001797  cmp     [rcx+rdx], dil
0x14000179b  jnz     short loc_140001794
0x14000179d  lea     r8d, [rdx+1]
0x1400017a1  jmp     short loc_1400017A6
0x1400017a3  mov     rcx, rsi
0x1400017a6  mov     rax, [rbp+70h+arg_28]
0x1400017ad  xor     r9d, r9d
0x1400017b0  mov     [rsp+170h+var_110], rax
0x1400017b5  mov     rdx, r11
0x1400017b8  mov     rax, [rbp+70h+arg_20]
0x1400017bf  mov     [rsp+170h+var_120], rax
0x1400017c4  lea     rax, [rsp+170h+var_140]
0x1400017c9  mov     [rsp+170h+var_100], rcx
0x1400017ce  mov     rcx, r10
0x1400017d1  mov     [rsp+170h+var_F8], r8d
0x1400017d6  mov     r8, rbx
0x1400017d9  mov     [rsp+170h+var_148], rax
0x1400017de  mov     [rsp+170h+var_150], 11h
0x1400017e6  mov     [rsp+170h+var_F4], edi
0x1400017ea  mov     [rsp+170h+var_108], 4
0x1400017f3  mov     [rsp+170h+var_118], 8
0x1400017fc  call    _tlgWriteTransfer_EventWriteTransfer
0x140001801  mov     rcx, [rbp+70h+var_30]
0x140001805  xor     rcx, rsp; StackCookie
0x140001808  call    __security_check_cookie
0x14000180d  add     rsp, 150h
0x140001814  pop     r14
0x140001816  pop     rdi
0x140001817  pop     rsi
0x140001818  pop     rbx
0x140001819  pop     rbp
0x14000181a  retn
```
