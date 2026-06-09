# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)

- ea: `0x18000b13c`
- end: `0x18000b3e7`
- name: `??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456@Z`
- size: `683`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, __int64, __int64, __int64, const unsigned __int16 **, __int64, const unsigned __int16 **, __int64, int **, __int64, const unsigned __int16 **, __int64, const unsigned __int16 **, int **, __int64, const unsigned __int16 **, int **)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18000b71c`

## callees

- `0x18000b13c`
- `0x18000b468`
- `0x18000fa10`

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
        int **a12,
        __int64 a13,
        const unsigned __int16 **a14,
        __int64 a15,
        const unsigned __int16 **a16,
        int **a17,
        __int64 a18,
        const unsigned __int16 **a19,
        int **a20)
{
  __int64 v22; // rcx
  int v23; // r9d
  int *v24; // rdx
  __int64 v25; // rax
  int v26; // eax
  int v27; // r8d
  const unsigned __int16 *v28; // rdx
  __int64 v29; // rax
  int v30; // eax
  int *v31; // rdx
  __int64 v32; // rax
  int v33; // eax
  const unsigned __int16 *v34; // rdx
  __int64 v35; // rax
  int v36; // eax
  const unsigned __int16 *v37; // rdx
  __int64 v38; // rax
  int v39; // eax
  int *v40; // rdx
  __int64 v41; // rax
  const unsigned __int16 *v42; // rdx
  __int64 v43; // rax
  int v44; // eax
  const unsigned __int16 *v45; // rdx
  _BYTE v47[32]; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v48; // [rsp+50h] [rbp-B0h]
  __int64 v49; // [rsp+58h] [rbp-A8h]
  __int64 v50; // [rsp+60h] [rbp-A0h]
  __int64 v51; // [rsp+68h] [rbp-98h]
  __int64 v52; // [rsp+70h] [rbp-90h]
  __int64 v53; // [rsp+78h] [rbp-88h]
  const unsigned __int16 *v54; // [rsp+80h] [rbp-80h]
  int v55; // [rsp+88h] [rbp-78h]
  int v56; // [rsp+8Ch] [rbp-74h]
  __int64 v57; // [rsp+90h] [rbp-70h]
  __int64 v58; // [rsp+98h] [rbp-68h]
  const unsigned __int16 *v59; // [rsp+A0h] [rbp-60h]
  int v60; // [rsp+A8h] [rbp-58h]
  int v61; // [rsp+ACh] [rbp-54h]
  __int64 v62; // [rsp+B0h] [rbp-50h]
  __int64 v63; // [rsp+B8h] [rbp-48h]
  int *v64; // [rsp+C0h] [rbp-40h]
  int v65; // [rsp+C8h] [rbp-38h]
  int v66; // [rsp+CCh] [rbp-34h]
  __int64 v67; // [rsp+D0h] [rbp-30h]
  __int64 v68; // [rsp+D8h] [rbp-28h]
  const unsigned __int16 *v69; // [rsp+E0h] [rbp-20h]
  int v70; // [rsp+E8h] [rbp-18h]
  int v71; // [rsp+ECh] [rbp-14h]
  __int64 v72; // [rsp+F0h] [rbp-10h]
  __int64 v73; // [rsp+F8h] [rbp-8h]
  const unsigned __int16 *v74; // [rsp+100h] [rbp+0h]
  int v75; // [rsp+108h] [rbp+8h]
  int v76; // [rsp+10Ch] [rbp+Ch]
  int *v77; // [rsp+110h] [rbp+10h]
  int v78; // [rsp+118h] [rbp+18h]
  int v79; // [rsp+11Ch] [rbp+1Ch]
  __int64 v80; // [rsp+120h] [rbp+20h]
  __int64 v81; // [rsp+128h] [rbp+28h]
  const unsigned __int16 *v82; // [rsp+130h] [rbp+30h]
  int v83; // [rsp+138h] [rbp+38h]
  int v84; // [rsp+13Ch] [rbp+3Ch]
  int *v85; // [rsp+140h] [rbp+40h]
  int v86; // [rsp+148h] [rbp+48h]
  int v87; // [rsp+14Ch] [rbp+4Ch]

  v22 = -1;
  v23 = 2;
  v24 = *a20;
  if ( *a20 )
  {
    v25 = -1;
    do
      ++v25;
    while ( *((_WORD *)v24 + v25) );
    v26 = 2 * v25 + 2;
  }
  else
  {
    v24 = &dword_18001A40C;
    v26 = 2;
  }
  v86 = v26;
  v27 = 1;
  v85 = v24;
  v87 = 0;
  v28 = *a19;
  if ( *a19 )
  {
    v29 = -1;
    do
      ++v29;
    while ( *((_BYTE *)v28 + v29) );
    v30 = v29 + 1;
  }
  else
  {
    v28 = &word_18001A40A;
    v30 = 1;
  }
  v83 = v30;
  v80 = a18;
  v82 = v28;
  v84 = 0;
  v81 = 4;
  v31 = *a17;
  if ( *a17 )
  {
    v32 = -1;
    do
      ++v32;
    while ( *((_WORD *)v31 + v32) );
    v33 = 2 * v32 + 2;
  }
  else
  {
    v31 = &dword_18001A40C;
    v33 = 2;
  }
  v78 = v33;
  v77 = v31;
  v79 = 0;
  v34 = *a16;
  if ( *a16 )
  {
    v35 = -1;
    do
      ++v35;
    while ( *((_BYTE *)v34 + v35) );
    v36 = v35 + 1;
  }
  else
  {
    v34 = &word_18001A40A;
    v36 = 1;
  }
  v75 = v36;
  v72 = a15;
  v74 = v34;
  v76 = 0;
  v73 = 4;
  v37 = *a14;
  if ( *a14 )
  {
    v38 = -1;
    do
      ++v38;
    while ( *((_BYTE *)v37 + v38) );
    v39 = v38 + 1;
  }
  else
  {
    v37 = &word_18001A40A;
    v39 = 1;
  }
  v70 = v39;
  v67 = a13;
  v69 = v37;
  v71 = 0;
  v68 = 4;
  v40 = *a12;
  if ( *a12 )
  {
    v41 = -1;
    do
      ++v41;
    while ( *((_WORD *)v40 + v41) );
    v23 = 2 * v41 + 2;
  }
  else
  {
    v40 = &dword_18001A40C;
  }
  v62 = a11;
  v64 = v40;
  v65 = v23;
  v66 = 0;
  v42 = *a10;
  v63 = 4;
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
    v42 = &word_18001A40A;
    v44 = 1;
  }
  v60 = v44;
  v57 = a9;
  v59 = v42;
  v61 = 0;
  v58 = 4;
  v45 = *a8;
  if ( *a8 )
  {
    do
      ++v22;
    while ( *((_BYTE *)v45 + v22) );
    v27 = v22 + 1;
  }
  else
  {
    v45 = &word_18001A40A;
  }
  v52 = a7;
  v50 = a6;
  v48 = a5;
  v54 = v45;
  v55 = v27;
  v56 = 0;
  v53 = 4;
  v51 = 8;
  v49 = 8;
  return tlgWriteTransfer_EventWriteTransfer(a1, a2, 0, 0, 18, v47);
}

```

## disassembly

```asm
0x18000b13c  mov     [rsp-8+arg_10], rbx
0x18000b141  push    rbp
0x18000b142  push    rsi
0x18000b143  push    rdi
0x18000b144  lea     rbp, [rsp-60h]
0x18000b149  sub     rsp, 160h
0x18000b150  mov     rax, cs:__security_cookie
0x18000b157  xor     rax, rsp
0x18000b15a  mov     [rbp+70h+var_20], rax
0x18000b15e  mov     rax, [rbp+70h+arg_98]
0x18000b165  mov     r11, rdx
0x18000b168  mov     r10, rcx
0x18000b16b  xor     ebx, ebx
0x18000b16d  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18000b171  mov     r9d, 2
0x18000b177  mov     rdx, [rax]
0x18000b17a  test    rdx, rdx
0x18000b17d  jz      short loc_18000B194
0x18000b17f  mov     rax, rcx
0x18000b182  inc     rax
0x18000b185  cmp     [rdx+rax*2], bx
0x18000b189  jnz     short loc_18000B182
0x18000b18b  lea     eax, ds:2[rax*2]
0x18000b192  jmp     short loc_18000B19E
0x18000b194  lea     rdx, dword_18001A40C
0x18000b19b  mov     eax, r9d
0x18000b19e  mov     [rbp+70h+var_28], eax
0x18000b1a1  lea     rdi, word_18001A40A
0x18000b1a8  mov     rax, [rbp+70h+arg_90]
0x18000b1af  mov     r8d, 1
0x18000b1b5  mov     [rbp+70h+var_30], rdx
0x18000b1b9  mov     [rbp+70h+var_24], ebx
0x18000b1bc  mov     rdx, [rax]
0x18000b1bf  test    rdx, rdx
0x18000b1c2  jz      short loc_18000B1D3
0x18000b1c4  mov     rax, rcx
0x18000b1c7  inc     rax
0x18000b1ca  cmp     [rdx+rax], bl
0x18000b1cd  jnz     short loc_18000B1C7
0x18000b1cf  inc     eax
0x18000b1d1  jmp     short loc_18000B1D9
0x18000b1d3  mov     rdx, rdi
0x18000b1d6  mov     eax, r8d
0x18000b1d9  mov     [rbp+70h+var_38], eax
0x18000b1dc  mov     rax, [rbp+70h+arg_88]
0x18000b1e3  mov     [rbp+70h+var_50], rax
0x18000b1e7  mov     rax, [rbp+70h+arg_80]
0x18000b1ee  mov     [rbp+70h+var_40], rdx
0x18000b1f2  mov     [rbp+70h+var_34], ebx
0x18000b1f5  mov     [rbp+70h+var_48], 4
0x18000b1fd  mov     rdx, [rax]
0x18000b200  test    rdx, rdx
0x18000b203  jz      short loc_18000B21A
0x18000b205  mov     rax, rcx
0x18000b208  inc     rax
0x18000b20b  cmp     [rdx+rax*2], bx
0x18000b20f  jnz     short loc_18000B208
0x18000b211  lea     eax, ds:2[rax*2]
0x18000b218  jmp     short loc_18000B224
0x18000b21a  lea     rdx, dword_18001A40C
0x18000b221  mov     eax, r9d
0x18000b224  mov     [rbp+70h+var_58], eax
0x18000b227  mov     rax, [rbp+70h+arg_78]
0x18000b22e  mov     [rbp+70h+var_60], rdx
0x18000b232  mov     [rbp+70h+var_54], ebx
0x18000b235  mov     rdx, [rax]
0x18000b238  test    rdx, rdx
0x18000b23b  jz      short loc_18000B24C
0x18000b23d  mov     rax, rcx
0x18000b240  inc     rax
0x18000b243  cmp     [rdx+rax], bl
0x18000b246  jnz     short loc_18000B240
0x18000b248  inc     eax
0x18000b24a  jmp     short loc_18000B252
0x18000b24c  mov     rdx, rdi
0x18000b24f  mov     eax, r8d
0x18000b252  mov     [rbp+70h+var_68], eax
0x18000b255  mov     rax, [rbp+70h+arg_70]
0x18000b25c  mov     [rbp+70h+var_80], rax
0x18000b260  mov     rax, [rbp+70h+arg_68]
0x18000b267  mov     [rbp+70h+var_70], rdx
0x18000b26b  mov     [rbp+70h+var_64], ebx
0x18000b26e  mov     [rbp+70h+var_78], 4
0x18000b276  mov     rdx, [rax]
0x18000b279  test    rdx, rdx
0x18000b27c  jz      short loc_18000B28D
0x18000b27e  mov     rax, rcx
0x18000b281  inc     rax
0x18000b284  cmp     [rdx+rax], bl
0x18000b287  jnz     short loc_18000B281
0x18000b289  inc     eax
0x18000b28b  jmp     short loc_18000B293
0x18000b28d  mov     rdx, rdi
0x18000b290  mov     eax, r8d
0x18000b293  mov     [rbp+70h+var_88], eax
0x18000b296  mov     rax, [rbp+70h+arg_60]
0x18000b29d  mov     [rbp+70h+var_A0], rax
0x18000b2a1  mov     rax, [rbp+70h+arg_58]
0x18000b2a8  mov     [rbp+70h+var_90], rdx
0x18000b2ac  mov     [rbp+70h+var_84], ebx
0x18000b2af  mov     [rbp+70h+var_98], 4
0x18000b2b7  mov     rdx, [rax]
0x18000b2ba  test    rdx, rdx
0x18000b2bd  jz      short loc_18000B2D5
0x18000b2bf  mov     rax, rcx
0x18000b2c2  inc     rax
0x18000b2c5  cmp     [rdx+rax*2], bx
0x18000b2c9  jnz     short loc_18000B2C2
0x18000b2cb  lea     r9d, ds:2[rax*2]
0x18000b2d3  jmp     short loc_18000B2DC
0x18000b2d5  lea     rdx, dword_18001A40C
0x18000b2dc  mov     rax, [rbp+70h+arg_50]
0x18000b2e3  mov     [rbp+70h+var_C0], rax
0x18000b2e7  mov     rax, [rbp+70h+arg_48]
0x18000b2ee  mov     [rbp+70h+var_B0], rdx
0x18000b2f2  mov     [rbp+70h+var_A8], r9d
0x18000b2f6  mov     [rbp+70h+var_A4], ebx
0x18000b2f9  mov     rdx, [rax]
0x18000b2fc  mov     [rbp+70h+var_B8], 4
0x18000b304  test    rdx, rdx
0x18000b307  jz      short loc_18000B318
0x18000b309  mov     rax, rcx
0x18000b30c  inc     rax
0x18000b30f  cmp     [rdx+rax], bl
0x18000b312  jnz     short loc_18000B30C
0x18000b314  inc     eax
0x18000b316  jmp     short loc_18000B31E
0x18000b318  mov     rdx, rdi
0x18000b31b  mov     eax, r8d
0x18000b31e  mov     [rbp+70h+var_C8], eax
0x18000b321  mov     rax, [rbp+70h+arg_40]
0x18000b328  mov     [rbp+70h+var_E0], rax
0x18000b32c  mov     rax, [rbp+70h+arg_38]
0x18000b333  mov     [rbp+70h+var_D0], rdx
0x18000b337  mov     [rbp+70h+var_C4], ebx
0x18000b33a  mov     [rbp+70h+var_D8], 4
0x18000b342  mov     rdx, [rax]
0x18000b345  test    rdx, rdx
0x18000b348  jz      short loc_18000B358
0x18000b34a  inc     rcx
0x18000b34d  cmp     [rdx+rcx], bl
0x18000b350  jnz     short loc_18000B34A
0x18000b352  lea     r8d, [rcx+1]
0x18000b356  jmp     short loc_18000B35B
0x18000b358  mov     rdx, rdi
0x18000b35b  mov     rax, [rbp+70h+arg_30]
0x18000b362  xor     r9d, r9d
0x18000b365  mov     [rsp+170h+var_100], rax
0x18000b36a  mov     rcx, r10
0x18000b36d  mov     rax, [rbp+70h+arg_28]
0x18000b374  mov     [rsp+170h+var_110], rax
0x18000b379  mov     rax, [rbp+70h+arg_20]
0x18000b380  mov     [rsp+170h+var_120], rax
0x18000b385  lea     rax, [rsp+170h+var_140]
0x18000b38a  mov     [rbp+70h+var_F0], rdx
0x18000b38e  mov     rdx, r11
0x18000b391  mov     [rbp+70h+var_E8], r8d
0x18000b395  xor     r8d, r8d
0x18000b398  mov     [rsp+170h+var_148], rax
0x18000b39d  mov     [rsp+170h+var_150], 12h
0x18000b3a5  mov     [rbp+70h+var_E4], ebx
0x18000b3a8  mov     [rsp+170h+var_F8], 4
0x18000b3b1  mov     [rsp+170h+var_108], 8
0x18000b3ba  mov     [rsp+170h+var_118], 8
0x18000b3c3  call    _tlgWriteTransfer_EventWriteTransfer
0x18000b3c8  mov     rcx, [rbp+70h+var_20]
0x18000b3cc  xor     rcx, rsp; StackCookie
0x18000b3cf  call    __security_check_cookie
0x18000b3d4  mov     rbx, [rsp+170h+arg_10]
0x18000b3dc  add     rsp, 160h
0x18000b3e3  pop     rdi
0x18000b3e4  pop     rsi
0x18000b3e5  pop     rbp
0x18000b3e6  retn
```
