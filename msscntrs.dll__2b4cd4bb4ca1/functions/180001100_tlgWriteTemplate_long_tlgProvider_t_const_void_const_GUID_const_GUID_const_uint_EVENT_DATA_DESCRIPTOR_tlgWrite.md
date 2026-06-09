# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<wchar_t> const &)

- ea: `0x180001100`
- end: `0x1800013ab`
- name: `??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@_W@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@_W@@45456456@Z`
- size: `683`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, __int64, __int64, __int64, const wchar_t **, __int64, const wchar_t **, __int64, const WCHAR **, __int64, const wchar_t **, __int64, const wchar_t **, const WCHAR **, __int64, const wchar_t **, const WCHAR **)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18000f75c`

## callees

- `0x180001100`
- `0x1800017dc`
- `0x1800024a0`

## pseudocode

```c
__int64 __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>>(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        __int64 a7,
        const wchar_t **a8,
        __int64 a9,
        const wchar_t **a10,
        __int64 a11,
        const WCHAR **a12,
        __int64 a13,
        const wchar_t **a14,
        __int64 a15,
        const wchar_t **a16,
        const WCHAR **a17,
        __int64 a18,
        const wchar_t **a19,
        const WCHAR **a20)
{
  __int64 v22; // rcx
  int v23; // r9d
  const WCHAR *v24; // rdx
  __int64 v25; // rax
  int v26; // eax
  int v27; // r8d
  const wchar_t *v28; // rdx
  __int64 v29; // rax
  int v30; // eax
  const WCHAR *v31; // rdx
  __int64 v32; // rax
  int v33; // eax
  const wchar_t *v34; // rdx
  __int64 v35; // rax
  int v36; // eax
  const wchar_t *v37; // rdx
  __int64 v38; // rax
  int v39; // eax
  const WCHAR *v40; // rdx
  __int64 v41; // rax
  const wchar_t *v42; // rdx
  __int64 v43; // rax
  int v44; // eax
  const wchar_t *v45; // rdx
  _BYTE v47[32]; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v48; // [rsp+50h] [rbp-B0h]
  __int64 v49; // [rsp+58h] [rbp-A8h]
  __int64 v50; // [rsp+60h] [rbp-A0h]
  __int64 v51; // [rsp+68h] [rbp-98h]
  __int64 v52; // [rsp+70h] [rbp-90h]
  __int64 v53; // [rsp+78h] [rbp-88h]
  const wchar_t *v54; // [rsp+80h] [rbp-80h]
  int v55; // [rsp+88h] [rbp-78h]
  int v56; // [rsp+8Ch] [rbp-74h]
  __int64 v57; // [rsp+90h] [rbp-70h]
  __int64 v58; // [rsp+98h] [rbp-68h]
  const wchar_t *v59; // [rsp+A0h] [rbp-60h]
  int v60; // [rsp+A8h] [rbp-58h]
  int v61; // [rsp+ACh] [rbp-54h]
  __int64 v62; // [rsp+B0h] [rbp-50h]
  __int64 v63; // [rsp+B8h] [rbp-48h]
  const WCHAR *v64; // [rsp+C0h] [rbp-40h]
  int v65; // [rsp+C8h] [rbp-38h]
  int v66; // [rsp+CCh] [rbp-34h]
  __int64 v67; // [rsp+D0h] [rbp-30h]
  __int64 v68; // [rsp+D8h] [rbp-28h]
  const wchar_t *v69; // [rsp+E0h] [rbp-20h]
  int v70; // [rsp+E8h] [rbp-18h]
  int v71; // [rsp+ECh] [rbp-14h]
  __int64 v72; // [rsp+F0h] [rbp-10h]
  __int64 v73; // [rsp+F8h] [rbp-8h]
  const wchar_t *v74; // [rsp+100h] [rbp+0h]
  int v75; // [rsp+108h] [rbp+8h]
  int v76; // [rsp+10Ch] [rbp+Ch]
  const WCHAR *v77; // [rsp+110h] [rbp+10h]
  int v78; // [rsp+118h] [rbp+18h]
  int v79; // [rsp+11Ch] [rbp+1Ch]
  __int64 v80; // [rsp+120h] [rbp+20h]
  __int64 v81; // [rsp+128h] [rbp+28h]
  const wchar_t *v82; // [rsp+130h] [rbp+30h]
  int v83; // [rsp+138h] [rbp+38h]
  int v84; // [rsp+13Ch] [rbp+3Ch]
  const WCHAR *v85; // [rsp+140h] [rbp+40h]
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
    while ( v24[v25] );
    v26 = 2 * v25 + 2;
  }
  else
  {
    v24 = &Class;
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
    v28 = &dword_18001A14C;
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
    while ( v31[v32] );
    v33 = 2 * v32 + 2;
  }
  else
  {
    v31 = &Class;
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
    v34 = &dword_18001A14C;
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
    v37 = &dword_18001A14C;
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
    while ( v40[v41] );
    v23 = 2 * v41 + 2;
  }
  else
  {
    v40 = &Class;
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
    v42 = &dword_18001A14C;
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
    v45 = &dword_18001A14C;
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
0x180001100  mov     [rsp-8+arg_10], rbx
0x180001105  push    rbp
0x180001106  push    rsi
0x180001107  push    rdi
0x180001108  lea     rbp, [rsp-60h]
0x18000110d  sub     rsp, 160h
0x180001114  mov     rax, cs:__security_cookie
0x18000111b  xor     rax, rsp
0x18000111e  mov     [rbp+70h+var_20], rax
0x180001122  mov     rax, [rbp+70h+arg_98]
0x180001129  mov     r11, rdx
0x18000112c  mov     r10, rcx
0x18000112f  xor     ebx, ebx
0x180001131  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180001135  mov     r9d, 2
0x18000113b  mov     rdx, [rax]
0x18000113e  test    rdx, rdx
0x180001141  jz      short loc_180001158
0x180001143  mov     rax, rcx
0x180001146  inc     rax
0x180001149  cmp     [rdx+rax*2], bx
0x18000114d  jnz     short loc_180001146
0x18000114f  lea     eax, ds:2[rax*2]
0x180001156  jmp     short loc_180001162
0x180001158  lea     rdx, Class
0x18000115f  mov     eax, r9d
0x180001162  mov     [rbp+70h+var_28], eax
0x180001165  lea     rdi, dword_18001A14C
0x18000116c  mov     rax, [rbp+70h+arg_90]
0x180001173  mov     r8d, 1
0x180001179  mov     [rbp+70h+var_30], rdx
0x18000117d  mov     [rbp+70h+var_24], ebx
0x180001180  mov     rdx, [rax]
0x180001183  test    rdx, rdx
0x180001186  jz      short loc_180001197
0x180001188  mov     rax, rcx
0x18000118b  inc     rax
0x18000118e  cmp     [rdx+rax], bl
0x180001191  jnz     short loc_18000118B
0x180001193  inc     eax
0x180001195  jmp     short loc_18000119D
0x180001197  mov     rdx, rdi
0x18000119a  mov     eax, r8d
0x18000119d  mov     [rbp+70h+var_38], eax
0x1800011a0  mov     rax, [rbp+70h+arg_88]
0x1800011a7  mov     [rbp+70h+var_50], rax
0x1800011ab  mov     rax, [rbp+70h+arg_80]
0x1800011b2  mov     [rbp+70h+var_40], rdx
0x1800011b6  mov     [rbp+70h+var_34], ebx
0x1800011b9  mov     [rbp+70h+var_48], 4
0x1800011c1  mov     rdx, [rax]
0x1800011c4  test    rdx, rdx
0x1800011c7  jz      short loc_1800011DE
0x1800011c9  mov     rax, rcx
0x1800011cc  inc     rax
0x1800011cf  cmp     [rdx+rax*2], bx
0x1800011d3  jnz     short loc_1800011CC
0x1800011d5  lea     eax, ds:2[rax*2]
0x1800011dc  jmp     short loc_1800011E8
0x1800011de  lea     rdx, Class
0x1800011e5  mov     eax, r9d
0x1800011e8  mov     [rbp+70h+var_58], eax
0x1800011eb  mov     rax, [rbp+70h+arg_78]
0x1800011f2  mov     [rbp+70h+var_60], rdx
0x1800011f6  mov     [rbp+70h+var_54], ebx
0x1800011f9  mov     rdx, [rax]
0x1800011fc  test    rdx, rdx
0x1800011ff  jz      short loc_180001210
0x180001201  mov     rax, rcx
0x180001204  inc     rax
0x180001207  cmp     [rdx+rax], bl
0x18000120a  jnz     short loc_180001204
0x18000120c  inc     eax
0x18000120e  jmp     short loc_180001216
0x180001210  mov     rdx, rdi
0x180001213  mov     eax, r8d
0x180001216  mov     [rbp+70h+var_68], eax
0x180001219  mov     rax, [rbp+70h+arg_70]
0x180001220  mov     [rbp+70h+var_80], rax
0x180001224  mov     rax, [rbp+70h+arg_68]
0x18000122b  mov     [rbp+70h+var_70], rdx
0x18000122f  mov     [rbp+70h+var_64], ebx
0x180001232  mov     [rbp+70h+var_78], 4
0x18000123a  mov     rdx, [rax]
0x18000123d  test    rdx, rdx
0x180001240  jz      short loc_180001251
0x180001242  mov     rax, rcx
0x180001245  inc     rax
0x180001248  cmp     [rdx+rax], bl
0x18000124b  jnz     short loc_180001245
0x18000124d  inc     eax
0x18000124f  jmp     short loc_180001257
0x180001251  mov     rdx, rdi
0x180001254  mov     eax, r8d
0x180001257  mov     [rbp+70h+var_88], eax
0x18000125a  mov     rax, [rbp+70h+arg_60]
0x180001261  mov     [rbp+70h+var_A0], rax
0x180001265  mov     rax, [rbp+70h+arg_58]
0x18000126c  mov     [rbp+70h+var_90], rdx
0x180001270  mov     [rbp+70h+var_84], ebx
0x180001273  mov     [rbp+70h+var_98], 4
0x18000127b  mov     rdx, [rax]
0x18000127e  test    rdx, rdx
0x180001281  jz      short loc_180001299
0x180001283  mov     rax, rcx
0x180001286  inc     rax
0x180001289  cmp     [rdx+rax*2], bx
0x18000128d  jnz     short loc_180001286
0x18000128f  lea     r9d, ds:2[rax*2]
0x180001297  jmp     short loc_1800012A0
0x180001299  lea     rdx, Class
0x1800012a0  mov     rax, [rbp+70h+arg_50]
0x1800012a7  mov     [rbp+70h+var_C0], rax
0x1800012ab  mov     rax, [rbp+70h+arg_48]
0x1800012b2  mov     [rbp+70h+var_B0], rdx
0x1800012b6  mov     [rbp+70h+var_A8], r9d
0x1800012ba  mov     [rbp+70h+var_A4], ebx
0x1800012bd  mov     rdx, [rax]
0x1800012c0  mov     [rbp+70h+var_B8], 4
0x1800012c8  test    rdx, rdx
0x1800012cb  jz      short loc_1800012DC
0x1800012cd  mov     rax, rcx
0x1800012d0  inc     rax
0x1800012d3  cmp     [rdx+rax], bl
0x1800012d6  jnz     short loc_1800012D0
0x1800012d8  inc     eax
0x1800012da  jmp     short loc_1800012E2
0x1800012dc  mov     rdx, rdi
0x1800012df  mov     eax, r8d
0x1800012e2  mov     [rbp+70h+var_C8], eax
0x1800012e5  mov     rax, [rbp+70h+arg_40]
0x1800012ec  mov     [rbp+70h+var_E0], rax
0x1800012f0  mov     rax, [rbp+70h+arg_38]
0x1800012f7  mov     [rbp+70h+var_D0], rdx
0x1800012fb  mov     [rbp+70h+var_C4], ebx
0x1800012fe  mov     [rbp+70h+var_D8], 4
0x180001306  mov     rdx, [rax]
0x180001309  test    rdx, rdx
0x18000130c  jz      short loc_18000131C
0x18000130e  inc     rcx
0x180001311  cmp     [rdx+rcx], bl
0x180001314  jnz     short loc_18000130E
0x180001316  lea     r8d, [rcx+1]
0x18000131a  jmp     short loc_18000131F
0x18000131c  mov     rdx, rdi
0x18000131f  mov     rax, [rbp+70h+arg_30]
0x180001326  xor     r9d, r9d
0x180001329  mov     [rsp+170h+var_100], rax
0x18000132e  mov     rcx, r10
0x180001331  mov     rax, [rbp+70h+arg_28]
0x180001338  mov     [rsp+170h+var_110], rax
0x18000133d  mov     rax, [rbp+70h+arg_20]
0x180001344  mov     [rsp+170h+var_120], rax
0x180001349  lea     rax, [rsp+170h+var_140]
0x18000134e  mov     [rbp+70h+var_F0], rdx
0x180001352  mov     rdx, r11
0x180001355  mov     [rbp+70h+var_E8], r8d
0x180001359  xor     r8d, r8d
0x18000135c  mov     [rsp+170h+var_148], rax
0x180001361  mov     [rsp+170h+var_150], 12h
0x180001369  mov     [rbp+70h+var_E4], ebx
0x18000136c  mov     [rsp+170h+var_F8], 4
0x180001375  mov     [rsp+170h+var_108], 8
0x18000137e  mov     [rsp+170h+var_118], 8
0x180001387  call    _tlgWriteTransfer_EventWriteTransfer
0x18000138c  mov     rcx, [rbp+70h+var_20]
0x180001390  xor     rcx, rsp; StackCookie
0x180001393  call    __security_check_cookie
0x180001398  mov     rbx, [rsp+170h+arg_10]
0x1800013a0  add     rsp, 160h
0x1800013a7  pop     rdi
0x1800013a8  pop     rsi
0x1800013a9  pop     rbp
0x1800013aa  retn
```
