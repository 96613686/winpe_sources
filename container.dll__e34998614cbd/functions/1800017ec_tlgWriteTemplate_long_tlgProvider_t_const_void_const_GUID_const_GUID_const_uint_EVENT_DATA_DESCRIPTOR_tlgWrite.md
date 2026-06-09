# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)

- ea: `0x1800017ec`
- end: `0x180001a88`
- name: `??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456@Z`
- size: `668`
- prototype: ``
- caller_count: `4`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180008350`
- `0x18000eb50`
- `0x18000eea0`
- `0x18000f2cc`

## callees

- `0x1800017ec`
- `0x180001e10`
- `0x180002ad0`

## pseudocode

```c
ULONG __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
        __int64 a1,
        unsigned __int8 *a2,
        const GUID *a3,
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
  __int64 v21; // rdx
  int v23; // r9d
  const WCHAR *v24; // rcx
  __int64 v25; // rax
  int v26; // eax
  int v27; // r8d
  const unsigned __int16 *v28; // rcx
  __int64 v29; // rax
  int v30; // eax
  const WCHAR *v31; // rcx
  __int64 v32; // rax
  int v33; // eax
  const unsigned __int16 *v34; // rcx
  __int64 v35; // rax
  int v36; // eax
  const unsigned __int16 *v37; // rcx
  __int64 v38; // rax
  int v39; // eax
  const WCHAR *v40; // rcx
  __int64 v41; // rax
  const unsigned __int16 *v42; // rcx
  __int64 v43; // rax
  int v44; // eax
  const unsigned __int16 *v45; // rcx
  struct _EVENT_DATA_DESCRIPTOR v47; // [rsp+30h] [rbp-D0h] BYREF
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
  const WCHAR *v62; // [rsp+B0h] [rbp-50h]
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
  const WCHAR *v75; // [rsp+100h] [rbp+0h]
  int v76; // [rsp+108h] [rbp+8h]
  int v77; // [rsp+10Ch] [rbp+Ch]
  __int64 v78; // [rsp+110h] [rbp+10h]
  __int64 v79; // [rsp+118h] [rbp+18h]
  const unsigned __int16 *v80; // [rsp+120h] [rbp+20h]
  int v81; // [rsp+128h] [rbp+28h]
  int v82; // [rsp+12Ch] [rbp+2Ch]
  const WCHAR *v83; // [rsp+130h] [rbp+30h]
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
    while ( v24[v25] );
    v26 = 2 * v25 + 2;
  }
  else
  {
    v24 = &pwszBaseUri;
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
    v28 = &byte_180037E05;
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
    while ( v31[v32] );
    v33 = 2 * v32 + 2;
  }
  else
  {
    v31 = &pwszBaseUri;
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
    v34 = &byte_180037E05;
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
    v37 = &byte_180037E05;
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
    while ( v40[v41] );
    v23 = 2 * v41 + 2;
  }
  else
  {
    v40 = &pwszBaseUri;
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
    v42 = &byte_180037E05;
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
    v45 = &byte_180037E05;
  }
  v50 = a6;
  v48 = a5;
  v52 = v45;
  v53 = v27;
  v54 = 0;
  v51 = 4;
  v49 = 8;
  return tlgWriteTransfer_EventWriteTransfer(a1, a2, a3, 0, 0x11u, &v47);
}

```

## disassembly

```asm
0x1800017ec  push    rbp
0x1800017ee  push    rbx
0x1800017ef  push    rsi
0x1800017f0  push    rdi
0x1800017f1  push    r14
0x1800017f3  lea     rbp, [rsp-50h]
0x1800017f8  sub     rsp, 150h
0x1800017ff  mov     rax, cs:__security_cookie
0x180001806  xor     rax, rsp
0x180001809  mov     [rbp+70h+var_30], rax
0x18000180d  mov     rax, [rbp+70h+arg_90]
0x180001814  mov     r11, rdx
0x180001817  mov     r10, rcx
0x18000181a  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18000181e  xor     edi, edi
0x180001820  mov     rbx, r8
0x180001823  mov     r9d, 2
0x180001829  mov     rcx, [rax]
0x18000182c  test    rcx, rcx
0x18000182f  jz      short loc_180001846
0x180001831  mov     rax, rdx
0x180001834  inc     rax
0x180001837  cmp     [rcx+rax*2], di
0x18000183b  jnz     short loc_180001834
0x18000183d  lea     eax, ds:2[rax*2]
0x180001844  jmp     short loc_180001850
0x180001846  lea     rcx, pwszBaseUri
0x18000184d  mov     eax, r9d
0x180001850  mov     [rbp+70h+var_38], eax
0x180001853  lea     rsi, byte_180037E05
0x18000185a  mov     rax, [rbp+70h+arg_88]
0x180001861  mov     r8d, 1
0x180001867  mov     [rbp+70h+var_40], rcx
0x18000186b  mov     [rbp+70h+var_34], edi
0x18000186e  mov     rcx, [rax]
0x180001871  test    rcx, rcx
0x180001874  jz      short loc_180001886
0x180001876  mov     rax, rdx
0x180001879  inc     rax
0x18000187c  cmp     [rcx+rax], dil
0x180001880  jnz     short loc_180001879
0x180001882  inc     eax
0x180001884  jmp     short loc_18000188C
0x180001886  mov     rcx, rsi
0x180001889  mov     eax, r8d
0x18000188c  mov     [rbp+70h+var_48], eax
0x18000188f  mov     rax, [rbp+70h+arg_80]
0x180001896  mov     [rbp+70h+var_60], rax
0x18000189a  mov     rax, [rbp+70h+arg_78]
0x1800018a1  mov     [rbp+70h+var_50], rcx
0x1800018a5  mov     [rbp+70h+var_44], edi
0x1800018a8  mov     [rbp+70h+var_58], 4
0x1800018b0  mov     rcx, [rax]
0x1800018b3  test    rcx, rcx
0x1800018b6  jz      short loc_1800018CD
0x1800018b8  mov     rax, rdx
0x1800018bb  inc     rax
0x1800018be  cmp     [rcx+rax*2], di
0x1800018c2  jnz     short loc_1800018BB
0x1800018c4  lea     eax, ds:2[rax*2]
0x1800018cb  jmp     short loc_1800018D7
0x1800018cd  lea     rcx, pwszBaseUri
0x1800018d4  mov     eax, r9d
0x1800018d7  mov     [rbp+70h+var_68], eax
0x1800018da  mov     rax, [rbp+70h+arg_70]
0x1800018e1  mov     [rbp+70h+var_70], rcx
0x1800018e5  mov     [rbp+70h+var_64], edi
0x1800018e8  mov     rcx, [rax]
0x1800018eb  test    rcx, rcx
0x1800018ee  jz      short loc_180001900
0x1800018f0  mov     rax, rdx
0x1800018f3  inc     rax
0x1800018f6  cmp     [rcx+rax], dil
0x1800018fa  jnz     short loc_1800018F3
0x1800018fc  inc     eax
0x1800018fe  jmp     short loc_180001906
0x180001900  mov     rcx, rsi
0x180001903  mov     eax, r8d
0x180001906  mov     [rbp+70h+var_78], eax
0x180001909  mov     rax, [rbp+70h+arg_68]
0x180001910  mov     [rbp+70h+var_90], rax
0x180001914  mov     rax, [rbp+70h+arg_60]
0x18000191b  mov     [rbp+70h+var_80], rcx
0x18000191f  mov     [rbp+70h+var_74], edi
0x180001922  mov     [rbp+70h+var_88], 4
0x18000192a  mov     rcx, [rax]
0x18000192d  test    rcx, rcx
0x180001930  jz      short loc_180001942
0x180001932  mov     rax, rdx
0x180001935  inc     rax
0x180001938  cmp     [rcx+rax], dil
0x18000193c  jnz     short loc_180001935
0x18000193e  inc     eax
0x180001940  jmp     short loc_180001948
0x180001942  mov     rcx, rsi
0x180001945  mov     eax, r8d
0x180001948  mov     [rbp+70h+var_98], eax
0x18000194b  mov     rax, [rbp+70h+arg_58]
0x180001952  mov     [rbp+70h+var_B0], rax
0x180001956  mov     rax, [rbp+70h+arg_50]
0x18000195d  mov     [rbp+70h+var_A0], rcx
0x180001961  mov     [rbp+70h+var_94], edi
0x180001964  mov     [rbp+70h+var_A8], 4
0x18000196c  mov     rcx, [rax]
0x18000196f  test    rcx, rcx
0x180001972  jz      short loc_18000198A
0x180001974  mov     rax, rdx
0x180001977  inc     rax
0x18000197a  cmp     [rcx+rax*2], di
0x18000197e  jnz     short loc_180001977
0x180001980  lea     r9d, ds:2[rax*2]
0x180001988  jmp     short loc_180001991
0x18000198a  lea     rcx, pwszBaseUri
0x180001991  mov     rax, [rbp+70h+arg_48]
0x180001998  mov     [rbp+70h+var_D0], rax
0x18000199c  mov     rax, [rbp+70h+arg_40]
0x1800019a3  mov     [rbp+70h+var_C0], rcx
0x1800019a7  mov     [rbp+70h+var_B8], r9d
0x1800019ab  mov     [rbp+70h+var_B4], edi
0x1800019ae  mov     rcx, [rax]
0x1800019b1  mov     [rbp+70h+var_C8], 4
0x1800019b9  test    rcx, rcx
0x1800019bc  jz      short loc_1800019CE
0x1800019be  mov     rax, rdx
0x1800019c1  inc     rax
0x1800019c4  cmp     [rcx+rax], dil
0x1800019c8  jnz     short loc_1800019C1
0x1800019ca  inc     eax
0x1800019cc  jmp     short loc_1800019D4
0x1800019ce  mov     rcx, rsi
0x1800019d1  mov     eax, r8d
0x1800019d4  mov     [rbp+70h+var_D8], eax
0x1800019d7  mov     rax, [rbp+70h+arg_38]
0x1800019de  mov     [rbp+70h+var_F0], rax
0x1800019e2  mov     rax, [rbp+70h+arg_30]
0x1800019e9  mov     [rbp+70h+var_E0], rcx
0x1800019ed  mov     [rbp+70h+var_D4], edi
0x1800019f0  mov     [rbp+70h+var_E8], 4
0x1800019f8  mov     rcx, [rax]
0x1800019fb  test    rcx, rcx
0x1800019fe  jz      short loc_180001A0F
0x180001a00  inc     rdx
0x180001a03  cmp     [rcx+rdx], dil
0x180001a07  jnz     short loc_180001A00
0x180001a09  lea     r8d, [rdx+1]
0x180001a0d  jmp     short loc_180001A12
0x180001a0f  mov     rcx, rsi
0x180001a12  mov     rax, [rbp+70h+arg_28]
0x180001a19  xor     r9d, r9d
0x180001a1c  mov     [rsp+170h+var_110], rax
0x180001a21  mov     rdx, r11
0x180001a24  mov     rax, [rbp+70h+arg_20]
0x180001a2b  mov     [rsp+170h+var_120], rax
0x180001a30  lea     rax, [rsp+170h+var_140]
0x180001a35  mov     [rsp+170h+var_100], rcx
0x180001a3a  mov     rcx, r10
0x180001a3d  mov     [rsp+170h+var_F8], r8d
0x180001a42  mov     r8, rbx
0x180001a45  mov     [rsp+170h+var_148], rax
0x180001a4a  mov     [rsp+170h+var_150], 11h
0x180001a52  mov     [rsp+170h+var_F4], edi
0x180001a56  mov     [rsp+170h+var_108], 4
0x180001a5f  mov     [rsp+170h+var_118], 8
0x180001a68  call    _tlgWriteTransfer_EventWriteTransfer
0x180001a6d  mov     rcx, [rbp+70h+var_30]
0x180001a71  xor     rcx, rsp; StackCookie
0x180001a74  call    __security_check_cookie
0x180001a79  add     rsp, 150h
0x180001a80  pop     r14
0x180001a82  pop     rdi
0x180001a83  pop     rsi
0x180001a84  pop     rbx
0x180001a85  pop     rbp
0x180001a86  retn
```
