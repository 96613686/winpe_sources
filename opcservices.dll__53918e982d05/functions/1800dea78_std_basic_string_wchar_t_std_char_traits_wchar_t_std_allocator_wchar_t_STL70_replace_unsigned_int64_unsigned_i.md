# std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>,_STL70>::replace(unsigned __int64,unsigned __int64,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>,_STL70> const &,unsigned __int64,unsigned __int64)

- ea: `0x1800dea78`
- end: `0x1800dedb8`
- name: `?replace@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@QEAAAEAV12@_K0AEBV12@00@Z`
- size: `832`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18008414c`

## callees

- `0x180018fc0`
- `0x1800cded0`
- `0x1800cdf2c`
- `0x1800dea78`

## import_xrefs

- `msvcrt!memmove_s` at `0x1800deb66`
- `msvcrt!memmove_s` at `0x1800debd4`
- `msvcrt!memmove_s` at `0x1800dec4f`
- `msvcrt!memmove_s` at `0x1800decbb`
- `msvcrt!memmove_s` at `0x1800ded07`
- `msvcrt!memmove_s` at `0x1800ded45`
- `msvcrt!memmove_s` at `0x1800ded82`
- `msvcrt!memmove_s` at `0x1800deb66`
- `msvcrt!memmove_s` at `0x1800debd4`
- `msvcrt!memmove_s` at `0x1800dec4f`
- `msvcrt!memmove_s` at `0x1800decbb`
- `msvcrt!memmove_s` at `0x1800ded07`
- `msvcrt!memmove_s` at `0x1800ded45`
- `msvcrt!memmove_s` at `0x1800ded82`
- `msvcrt!memcpy_s` at `0x1800deb9e`
- `msvcrt!memcpy_s` at `0x1800deb9e`

## pseudocode

```c
_QWORD *__fastcall std::wstring::replace(
        _QWORD *a1,
        unsigned __int64 a2,
        unsigned __int64 a3,
        _QWORD *a4,
        unsigned __int64 a5,
        unsigned __int64 a6)
{
  unsigned __int64 v7; // r15
  unsigned __int64 v8; // r12
  unsigned __int64 v11; // rdx
  unsigned __int64 v12; // r14
  unsigned __int64 v13; // rdx
  unsigned __int64 v14; // rax
  unsigned __int64 v15; // rbp
  unsigned __int64 v16; // rdx
  _QWORD *v17; // rbx
  _QWORD *v18; // rcx
  _QWORD *v19; // r8
  _QWORD *v20; // rax
  unsigned __int64 v21; // rdx
  _QWORD *v22; // rcx
  _QWORD *v23; // rax
  _QWORD *v24; // rcx
  unsigned __int64 v25; // rdx
  _QWORD *v26; // rcx
  _QWORD *v27; // r8
  char *v28; // r8
  unsigned __int64 v29; // rdx
  char *v30; // rcx
  rsize_t v31; // r9
  _QWORD *v32; // rcx
  _QWORD *v33; // r8
  unsigned __int64 v34; // rdx
  _QWORD *v35; // rax
  _QWORD *v36; // rcx
  unsigned __int64 v37; // r13
  _QWORD *v38; // rcx
  _QWORD *v39; // rax
  _QWORD *v40; // rax
  _QWORD *v41; // rcx
  unsigned __int64 v42; // rdx
  __int64 v43; // r13
  _QWORD *v44; // rax
  _QWORD *v45; // rcx
  unsigned __int64 v46; // rdx
  _QWORD *v47; // rcx
  _QWORD *v48; // r8
  unsigned __int64 v50; // [rsp+98h] [rbp+30h]

  v7 = a5;
  v8 = a3;
  if ( a1[3] < a2 || (v11 = a4[3], v11 < a5) )
    std::_String_base::_Xran();
  v12 = a6;
  if ( a1[3] - a2 < a3 )
    v8 = a1[3] - a2;
  v13 = v11 - a5;
  if ( v13 < a6 )
    v12 = v13;
  if ( ~v12 <= a1[3] - v8 )
    std::_String_base::_Xlen();
  v14 = a1[3];
  v15 = v14 - a2 - v8;
  v50 = v14 + v12 - v8;
  if ( v14 < v50 )
    std::wstring::_Grow(a1, v14 + v12 - v8, 0);
  v16 = a1[4];
  v17 = a1 + 1;
  if ( a1 == a4 )
  {
    if ( v12 > v8 )
    {
      if ( a5 > a2 )
      {
        v37 = a2 + v8;
        if ( a2 + v8 > a5 )
        {
          if ( v16 < 8 )
          {
            v40 = a1 + 1;
            v41 = a1 + 1;
          }
          else
          {
            v40 = (_QWORD *)*v17;
            v41 = (_QWORD *)*v17;
          }
          memmove_s((char *)v40 + 2 * a2, 2 * (v16 - a2), (char *)v41 + 2 * a5, 2 * v8);
          v42 = a1[4];
          v43 = 2 * v37;
          if ( v42 < 8 )
          {
            v45 = a1 + 1;
            v44 = a1 + 1;
          }
          else
          {
            v44 = (_QWORD *)*v17;
            v45 = (_QWORD *)*v17;
          }
          memmove_s((char *)v45 + 2 * a2 + 2 * v12, 2 * (v42 - a2 - v12), (char *)v44 + v43, 2 * v15);
          v46 = a1[4];
          if ( v46 < 8 )
          {
            v47 = a1 + 1;
            v48 = a1 + 1;
          }
          else
          {
            v47 = (_QWORD *)*v17;
            v48 = (_QWORD *)*v17;
          }
          v28 = (char *)v48 + 2 * a5 + 2 * v12;
          v31 = 2 * (v12 - v8);
          v29 = v46 - a2 - v8;
          v30 = (char *)v47 + v43;
          goto LABEL_56;
        }
        if ( v16 < 8 )
        {
          v38 = a1 + 1;
          v39 = a1 + 1;
        }
        else
        {
          v38 = (_QWORD *)*v17;
          v39 = (_QWORD *)*v17;
        }
        memmove_s((char *)v38 + 2 * a2 + 2 * v12, 2 * (v16 - a2 - v12), (char *)v39 + 2 * v37, 2 * v15);
        v34 = a1[4];
        if ( v34 < 8 )
        {
          v35 = a1 + 1;
          v36 = a1 + 1;
        }
        else
        {
          v35 = (_QWORD *)*v17;
          v36 = (_QWORD *)*v17;
        }
        v7 = v12 + a5 - v8;
      }
      else
      {
        if ( v16 < 8 )
        {
          v32 = a1 + 1;
          v33 = a1 + 1;
        }
        else
        {
          v32 = (_QWORD *)*v17;
          v33 = (_QWORD *)*v17;
        }
        memmove_s((char *)v32 + 2 * a2 + 2 * v12, 2 * (v16 - a2 - v12), (char *)v33 + 2 * a2 + 2 * v8, 2 * v15);
        v34 = a1[4];
        if ( v34 < 8 )
        {
          v35 = a1 + 1;
          v36 = a1 + 1;
        }
        else
        {
          v35 = (_QWORD *)*v17;
          v36 = (_QWORD *)*v17;
        }
      }
      v28 = (char *)v36 + 2 * v7;
      v29 = v34 - a2;
      v30 = (char *)v35 + 2 * a2;
      v31 = 2 * v12;
    }
    else
    {
      if ( v16 < 8 )
      {
        v23 = a1 + 1;
        v24 = a1 + 1;
      }
      else
      {
        v23 = (_QWORD *)*v17;
        v24 = (_QWORD *)*v17;
      }
      memmove_s((char *)v23 + 2 * a2, 2 * (v16 - a2), (char *)v24 + 2 * a5, 2 * v12);
      v25 = a1[4];
      if ( v25 < 8 )
      {
        v26 = a1 + 1;
        v27 = a1 + 1;
      }
      else
      {
        v26 = (_QWORD *)*v17;
        v27 = (_QWORD *)*v17;
      }
      v28 = (char *)v27 + 2 * a2 + 2 * v8;
      v29 = v25 - a2 - v12;
      v30 = (char *)v26 + 2 * a2 + 2 * v12;
      v31 = 2 * v15;
    }
LABEL_56:
    memmove_s(v30, 2 * v29, v28, v31);
    goto LABEL_57;
  }
  if ( v16 < 8 )
  {
    v18 = a1 + 1;
    v19 = a1 + 1;
  }
  else
  {
    v18 = (_QWORD *)*v17;
    v19 = (_QWORD *)*v17;
  }
  memmove_s((char *)v18 + 2 * a2 + 2 * v12, 2 * (v16 - a2 - v12), (char *)v19 + 2 * a2 + 2 * v8, 2 * v15);
  v20 = a4 + 1;
  if ( a4[4] >= 8u )
    v20 = (_QWORD *)*v20;
  v21 = a1[4];
  if ( v21 < 8 )
    v22 = a1 + 1;
  else
    v22 = (_QWORD *)*v17;
  memcpy_s((char *)v22 + 2 * a2, 2 * (v21 - a2), (char *)v20 + 2 * a5, 2 * v12);
LABEL_57:
  if ( a1[4] >= 8u )
    v17 = (_QWORD *)*v17;
  a1[3] = v50;
  *((_WORD *)v17 + v50) = 0;
  return a1;
}

```

## disassembly

```asm
0x1800dea78  push    rbx
0x1800dea7a  push    rbp
0x1800dea7b  push    rsi
0x1800dea7c  push    rdi
0x1800dea7d  push    r12
0x1800dea7f  push    r13
0x1800dea81  push    r14
0x1800dea83  push    r15
0x1800dea85  sub     rsp, 28h
0x1800dea89  mov     r13, r9
0x1800dea8c  mov     r15, [rsp+68h+arg_20]
0x1800dea94  mov     r12, r8
0x1800dea97  mov     rdi, rdx
0x1800dea9a  mov     rsi, rcx
0x1800dea9d  cmp     [rcx+18h], rdx
0x1800deaa1  jb      short loc_1800DEAAC
0x1800deaa3  mov     rdx, [r9+18h]
0x1800deaa7  cmp     rdx, r15
0x1800deaaa  jnb     short loc_1800DEAB5
0x1800deaac  call    ?_Xran@_String_base@std@@SAXXZ; std::_String_base::_Xran(void)
0x1800deab1  mov     rdx, [r13+18h]
0x1800deab5  mov     rcx, [rsi+18h]
0x1800deab9  mov     r14, [rsp+68h+arg_28]
0x1800deac1  mov     rax, rcx
0x1800deac4  sub     rax, rdi
0x1800deac7  cmp     rax, r12
0x1800deaca  cmovb   r12, rax
0x1800deace  sub     rdx, r15
0x1800dead1  cmp     rdx, r14
0x1800dead4  cmovb   r14, rdx
0x1800dead8  sub     rcx, r12
0x1800deadb  mov     rax, r14
0x1800deade  not     rax
0x1800deae1  cmp     rax, rcx
0x1800deae4  ja      short loc_1800DEAEB
0x1800deae6  call    ?_Xlen@_String_base@std@@SAXXZ; std::_String_base::_Xlen(void)
0x1800deaeb  mov     rax, [rsi+18h]
0x1800deaef  mov     rcx, r14
0x1800deaf2  sub     rcx, r12
0x1800deaf5  mov     rbp, rax
0x1800deaf8  sub     rbp, rdi
0x1800deafb  mov     [rsp+68h+arg_20], rcx
0x1800deb03  add     rcx, rax
0x1800deb06  sub     rbp, r12
0x1800deb09  mov     [rsp+68h+arg_28], rcx
0x1800deb11  cmp     rax, rcx
0x1800deb14  jnb     short loc_1800DEB24
0x1800deb16  mov     rdx, rcx
0x1800deb19  xor     r8d, r8d
0x1800deb1c  mov     rcx, rsi
0x1800deb1f  call    ?_Grow@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@IEAA_N_K_N@Z; std::wstring::_Grow(unsigned __int64,bool)
0x1800deb24  mov     rdx, [rsi+20h]
0x1800deb28  lea     rbx, [rsi+8]
0x1800deb2c  cmp     rsi, r13
0x1800deb2f  jz      short loc_1800DEBA9
0x1800deb31  cmp     rdx, 8
0x1800deb35  jb      short loc_1800DEB3F
0x1800deb37  mov     rcx, [rbx]
0x1800deb3a  mov     r8, rcx
0x1800deb3d  jmp     short loc_1800DEB45
0x1800deb3f  mov     rcx, rbx
0x1800deb42  mov     r8, rbx
0x1800deb45  sub     rdx, rdi
0x1800deb48  lea     rax, [rdi+r12]
0x1800deb4c  lea     r8, [r8+rax*2]; Source
0x1800deb50  sub     rdx, r14
0x1800deb53  lea     rax, [rdi+r14]
0x1800deb57  add     rdx, rdx; DestinationSize
0x1800deb5a  lea     rcx, [rcx+rax*2]; Destination
0x1800deb5e  lea     r9, ds:0[rbp*2]; SourceSize
0x1800deb66  call    cs:__imp_memmove_s
0x1800deb6c  cmp     qword ptr [r13+20h], 8
0x1800deb71  lea     rax, [r13+8]
0x1800deb75  jb      short loc_1800DEB7A
0x1800deb77  mov     rax, [rax]
0x1800deb7a  mov     rdx, [rsi+20h]
0x1800deb7e  cmp     rdx, 8
0x1800deb82  jb      short loc_1800DEB89
0x1800deb84  mov     rcx, [rbx]
0x1800deb87  jmp     short loc_1800DEB8C
0x1800deb89  mov     rcx, rbx
0x1800deb8c  sub     rdx, rdi
0x1800deb8f  lea     r9, [r14+r14]; SourceSize
0x1800deb93  add     rdx, rdx; DestinationSize
0x1800deb96  lea     r8, [rax+r15*2]; Source
0x1800deb9a  lea     rcx, [rcx+rdi*2]; Destination
0x1800deb9e  call    cs:__imp_memcpy_s
0x1800deba4  jmp     loc_1800DED88
0x1800deba9  cmp     r14, r12
0x1800debac  ja      short loc_1800DEC15
0x1800debae  cmp     rdx, 8
0x1800debb2  jb      short loc_1800DEBBC
0x1800debb4  mov     rax, [rbx]
0x1800debb7  mov     rcx, rax
0x1800debba  jmp     short loc_1800DEBC2
0x1800debbc  mov     rax, rbx
0x1800debbf  mov     rcx, rbx
0x1800debc2  sub     rdx, rdi
0x1800debc5  lea     r8, [rcx+r15*2]; Source
0x1800debc9  add     rdx, rdx; DestinationSize
0x1800debcc  lea     r9, [r14+r14]; SourceSize
0x1800debd0  lea     rcx, [rax+rdi*2]; Destination
0x1800debd4  call    cs:__imp_memmove_s
0x1800debda  mov     rdx, [rsi+20h]
0x1800debde  cmp     rdx, 8
0x1800debe2  jb      short loc_1800DEBEC
0x1800debe4  mov     rcx, [rbx]
0x1800debe7  mov     r8, rcx
0x1800debea  jmp     short loc_1800DEBF2
0x1800debec  mov     rcx, rbx
0x1800debef  mov     r8, rbx
0x1800debf2  lea     rax, [rdi+r12]
0x1800debf6  sub     rdx, rdi
0x1800debf9  lea     r8, [r8+rax*2]
0x1800debfd  sub     rdx, r14
0x1800dec00  lea     rax, [rdi+r14]
0x1800dec04  lea     rcx, [rcx+rax*2]
0x1800dec08  lea     r9, ds:0[rbp*2]
0x1800dec10  jmp     loc_1800DED7F
0x1800dec15  cmp     r15, rdi
0x1800dec18  ja      short loc_1800DEC81
0x1800dec1a  cmp     rdx, 8
0x1800dec1e  jb      short loc_1800DEC28
0x1800dec20  mov     rcx, [rbx]
0x1800dec23  mov     r8, rcx
0x1800dec26  jmp     short loc_1800DEC2E
0x1800dec28  mov     rcx, rbx
0x1800dec2b  mov     r8, rbx
0x1800dec2e  sub     rdx, rdi
0x1800dec31  lea     rax, [rdi+r12]
0x1800dec35  lea     r8, [r8+rax*2]; Source
0x1800dec39  sub     rdx, r14
0x1800dec3c  lea     rax, [rdi+r14]
0x1800dec40  add     rdx, rdx; DestinationSize
0x1800dec43  lea     rcx, [rcx+rax*2]; Destination
0x1800dec47  lea     r9, ds:0[rbp*2]; SourceSize
0x1800dec4f  call    cs:__imp_memmove_s
0x1800dec55  mov     rdx, [rsi+20h]
0x1800dec59  cmp     rdx, 8
0x1800dec5d  jb      short loc_1800DEC67
0x1800dec5f  mov     rax, [rbx]
0x1800dec62  mov     rcx, rax
0x1800dec65  jmp     short loc_1800DEC6D
0x1800dec67  mov     rax, rbx
0x1800dec6a  mov     rcx, rbx
0x1800dec6d  lea     r8, [rcx+r15*2]
0x1800dec71  sub     rdx, rdi
0x1800dec74  lea     rcx, [rax+rdi*2]
0x1800dec78  lea     r9, [r14+r14]
0x1800dec7c  jmp     loc_1800DED7F
0x1800dec81  lea     r13, [rdi+r12]
0x1800dec85  cmp     r13, r15
0x1800dec88  ja      short loc_1800DECE1
0x1800dec8a  cmp     rdx, 8
0x1800dec8e  jb      short loc_1800DEC98
0x1800dec90  mov     rcx, [rbx]
0x1800dec93  mov     rax, rcx
0x1800dec96  jmp     short loc_1800DEC9E
0x1800dec98  mov     rcx, rbx
0x1800dec9b  mov     rax, rbx
0x1800dec9e  sub     rdx, rdi
0x1800deca1  lea     r8, [rax+r13*2]; Source
0x1800deca5  sub     rdx, r14
0x1800deca8  lea     rax, [rdi+r14]
0x1800decac  add     rdx, rdx; DestinationSize
0x1800decaf  lea     r9, ds:0[rbp*2]; SourceSize
0x1800decb7  lea     rcx, [rcx+rax*2]; Destination
0x1800decbb  call    cs:__imp_memmove_s
0x1800decc1  mov     rdx, [rsi+20h]
0x1800decc5  cmp     rdx, 8
0x1800decc9  jb      short loc_1800DECD3
0x1800deccb  mov     rax, [rbx]
0x1800decce  mov     rcx, rax
0x1800decd1  jmp     short loc_1800DECD9
0x1800decd3  mov     rax, rbx
0x1800decd6  mov     rcx, rbx
0x1800decd9  sub     r15, r12
0x1800decdc  add     r15, r14
0x1800decdf  jmp     short loc_1800DEC6D
0x1800dece1  cmp     rdx, 8
0x1800dece5  jb      short loc_1800DECEF
0x1800dece7  mov     rax, [rbx]
0x1800decea  mov     rcx, rax
0x1800deced  jmp     short loc_1800DECF5
0x1800decef  mov     rax, rbx
0x1800decf2  mov     rcx, rbx
0x1800decf5  sub     rdx, rdi
0x1800decf8  lea     r8, [rcx+r15*2]; Source
0x1800decfc  add     rdx, rdx; DestinationSize
0x1800decff  lea     r9, [r12+r12]; SourceSize
0x1800ded03  lea     rcx, [rax+rdi*2]; Destination
0x1800ded07  call    cs:__imp_memmove_s
0x1800ded0d  mov     rdx, [rsi+20h]
0x1800ded11  add     r13, r13
0x1800ded14  cmp     rdx, 8
0x1800ded18  jb      short loc_1800DED22
0x1800ded1a  mov     rax, [rbx]
0x1800ded1d  mov     rcx, rax
0x1800ded20  jmp     short loc_1800DED28
0x1800ded22  mov     rcx, rbx
0x1800ded25  mov     rax, rbx
0x1800ded28  sub     rdx, rdi
0x1800ded2b  lea     r8, [rax+r13]; Source
0x1800ded2f  sub     rdx, r14
0x1800ded32  lea     rax, [rdi+r14]
0x1800ded36  add     rdx, rdx; DestinationSize
0x1800ded39  lea     r9, ds:0[rbp*2]; SourceSize
0x1800ded41  lea     rcx, [rcx+rax*2]; Destination
0x1800ded45  call    cs:__imp_memmove_s
0x1800ded4b  mov     rdx, [rsi+20h]
0x1800ded4f  cmp     rdx, 8
0x1800ded53  jb      short loc_1800DED5D
0x1800ded55  mov     rcx, [rbx]
0x1800ded58  mov     r8, rcx
0x1800ded5b  jmp     short loc_1800DED63
0x1800ded5d  mov     rcx, rbx
0x1800ded60  mov     r8, rbx
0x1800ded63  mov     r9, [rsp+68h+arg_20]
0x1800ded6b  lea     rax, [r15+r14]
0x1800ded6f  sub     rdx, rdi
0x1800ded72  lea     r8, [r8+rax*2]; Source
0x1800ded76  add     r9, r9; SourceSize
0x1800ded79  sub     rdx, r12
0x1800ded7c  add     rcx, r13; Destination
0x1800ded7f  add     rdx, rdx; DestinationSize
0x1800ded82  call    cs:__imp_memmove_s
0x1800ded88  cmp     qword ptr [rsi+20h], 8
0x1800ded8d  jb      short loc_1800DED92
0x1800ded8f  mov     rbx, [rbx]
0x1800ded92  mov     rax, [rsp+68h+arg_28]
0x1800ded9a  xor     ecx, ecx
0x1800ded9c  mov     [rsi+18h], rax
0x1800deda0  mov     [rbx+rax*2], cx
0x1800deda4  mov     rax, rsi
0x1800deda7  add     rsp, 28h
0x1800dedab  pop     r15
0x1800dedad  pop     r14
0x1800dedaf  pop     r13
0x1800dedb1  pop     r12
0x1800dedb3  pop     rdi
0x1800dedb4  pop     rsi
0x1800dedb5  pop     rbp
0x1800dedb6  pop     rbx
0x1800dedb7  retn
```
