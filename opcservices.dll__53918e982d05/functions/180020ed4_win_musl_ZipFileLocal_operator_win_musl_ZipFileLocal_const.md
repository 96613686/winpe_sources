# win_musl::ZipFileLocal::operator=(win_musl::ZipFileLocal const &)

- ea: `0x180020ed4`
- end: `0x18002129f`
- name: `??4ZipFileLocal@win_musl@@QEAAAEAV01@AEBV01@@Z`
- size: `971`
- prototype: ``
- caller_count: `2`
- callee_count: `12`
- tags: `file_ops`

## callers

- `0x18001f158`
- `0x180024cbc`

## callees

- `0x18001d3c0`
- `0x180020ed4`
- `0x180021d74`
- `0x1800761c0`
- `0x1800850a0`
- `0x1800856b8`
- `0x18008e69c`
- `0x18008e6dc`
- `0x180099e0c`
- `0x1800cd1c4`
- `0x1800cded0`
- `0x180111f20`

## import_xrefs

- `msvcrt!memmove_s` at `0x180021141`
- `msvcrt!memmove_s` at `0x18002118f`
- `msvcrt!memmove_s` at `0x180021141`
- `msvcrt!memmove_s` at `0x18002118f`
- `msvcrt!memcpy_s` at `0x180020f3f`
- `msvcrt!memcpy_s` at `0x180020f3f`

## pseudocode

```c
__int64 __fastcall win_musl::ZipFileLocal::operator=(__int64 a1, __int64 a2)
{
  __int64 v2; // r14
  rsize_t v4; // rdi
  __int64 v5; // rbx
  _QWORD *v7; // r8
  rsize_t v8; // rdx
  void **v9; // r14
  void *v10; // rcx
  __int64 v11; // r9
  unsigned __int64 v12; // rdx
  rsize_t v13; // rax
  __int64 v14; // r10
  __int64 v15; // rax
  _QWORD *v17; // rax
  void *v18; // rcx
  unsigned __int64 v19; // rax
  __int64 v20; // rcx
  unsigned __int64 v21; // rax
  __int64 v22; // rdx
  const void *v23; // r8
  __int64 v24; // r14
  rsize_t v25; // rdi
  __int64 v26; // rax
  const void *v27; // r14
  __int64 v28; // r15
  rsize_t v29; // rdi
  unsigned __int64 v30; // rax
  unsigned __int64 v31; // rdx
  __int64 v32; // r10
  unsigned __int64 v33; // rax
  unsigned __int64 v34; // rdx
  __int64 v35; // rax
  __int64 v36; // r10
  __int64 v37; // r8
  __int64 v38; // r9
  __int64 v39; // rcx
  void *v40; // rcx
  __int64 v41; // rax

  v2 = a2 + 8;
  v4 = *(_QWORD *)(a2 + 32);
  v5 = a1 + 8;
  if ( a1 + 8 == a2 + 8 )
  {
    std::string::erase(a1 + 8, v4, -1);
    std::string::erase(v5, 0, 0);
    goto LABEL_12;
  }
  if ( v4 == -1 )
    std::_String_base::_Xlen();
  if ( *(_QWORD *)(a1 + 40) < v4 )
  {
    std::string::_Copy(a1 + 8, v4, *(_QWORD *)(a1 + 32));
    if ( !v4 )
      goto LABEL_12;
    goto LABEL_5;
  }
  if ( v4 )
  {
LABEL_5:
    v7 = (_QWORD *)(v2 + 8);
    if ( *(_QWORD *)(v2 + 32) >= 0x10u )
      v7 = (_QWORD *)*v7;
    v8 = *(_QWORD *)(v5 + 32);
    v9 = (void **)(v5 + 8);
    if ( v8 < 0x10 )
      v10 = (void *)(v5 + 8);
    else
      v10 = *v9;
    memcpy_s(v10, v8, v7, v4);
    if ( *(_QWORD *)(v5 + 32) >= 0x10u )
      v9 = (void **)*v9;
    *(_QWORD *)(v5 + 24) = v4;
    *((_BYTE *)v9 + v4) = 0;
    goto LABEL_12;
  }
  v17 = (_QWORD *)(a1 + 16);
  if ( *(_QWORD *)(a1 + 40) >= 0x10u )
    v17 = (_QWORD *)*v17;
  *(_QWORD *)(a1 + 32) = 0;
  *(_BYTE *)v17 = 0;
LABEL_12:
  *(_BYTE *)(a1 + 48) = *(_BYTE *)(a2 + 48);
  if ( a1 + 56 == a2 + 56 )
    goto LABEL_19;
  v11 = *(_QWORD *)(a2 + 64);
  if ( !v11 || (v12 = *(_QWORD *)(a2 + 72) - v11) == 0 )
  {
    v13 = *(_QWORD *)(a1 + 64);
    if ( v13 == *(_QWORD *)(a1 + 72) )
      goto LABEL_19;
LABEL_18:
    *(_QWORD *)(a1 + 72) = v13;
    goto LABEL_19;
  }
  v18 = *(void **)(a1 + 64);
  if ( v18 )
    v19 = *(_QWORD *)(a1 + 72) - (_QWORD)v18;
  else
    v19 = 0;
  if ( v12 > v19 )
  {
    if ( v18 )
      v21 = *(_QWORD *)(a1 + 80) - (_QWORD)v18;
    else
      v21 = 0;
    if ( v12 <= v21 )
    {
      if ( v18 )
        v26 = *(_QWORD *)(a1 + 72) - (_QWORD)v18;
      else
        v26 = 0;
      v27 = (const void *)(v11 + v26);
      std::copy<unsigned char const *,unsigned char *>(*(void **)(a2 + 64));
      v28 = *(_QWORD *)(a1 + 72);
      v29 = *(_QWORD *)(a2 + 72) - (_QWORD)v27;
      if ( v29 )
        memmove_s(*(void *const *)(a1 + 72), v29, v27, v29);
      v13 = v29 + v28;
      goto LABEL_18;
    }
    if ( v18 )
      operator delete(v18);
    if ( *(_QWORD *)(a2 + 64) )
      v22 = *(_QWORD *)(a2 + 72) - *(_QWORD *)(a2 + 64);
    else
      v22 = 0;
    if ( (unsigned __int8)std::vector<unsigned char>::_Buy(a1 + 56, v22) )
    {
      v23 = *(const void **)(a2 + 64);
      v24 = *(_QWORD *)(a1 + 64);
      v25 = *(_QWORD *)(a2 + 72) - (_QWORD)v23;
      if ( v25 )
        memmove_s(*(void *const *)(a1 + 64), v25, v23, v25);
      v13 = v25 + v24;
      goto LABEL_18;
    }
  }
  else
  {
    std::copy<unsigned char const *,unsigned char *>(*(void **)(a2 + 64));
    if ( *(_QWORD *)(a2 + 64) )
      v20 = *(_QWORD *)(a2 + 72) - *(_QWORD *)(a2 + 64);
    else
      v20 = 0;
    *(_QWORD *)(a1 + 72) = *(_QWORD *)(a1 + 64) + v20;
  }
LABEL_19:
  if ( a1 + 88 == a2 + 88 )
    goto LABEL_24;
  v14 = *(_QWORD *)(a2 + 96);
  if ( v14 && 0xAAAAAAAAAAAAAAABuLL * ((*(_QWORD *)(a2 + 104) - v14) >> 3) )
  {
    std::vector<__MIDL___MIDL_itf_win72Ezip2Ebase_0000_0000_0001>::size(a1 + 88);
    v30 = std::vector<__MIDL___MIDL_itf_win72Ezip2Ebase_0000_0000_0001>::size(a2 + 88);
    if ( v30 <= v31 )
    {
      std::copy<__MIDL___MIDL_itf_win72Ezip2Ebase_0000_0000_0001 *,__MIDL___MIDL_itf_win72Ezip2Ebase_0000_0000_0001 *>(
        v32,
        *(_QWORD *)(a2 + 104),
        *(_QWORD *)(a1 + 96));
      *(_QWORD *)(a1 + 104) = *(_QWORD *)(a1 + 96)
                            + 24 * std::vector<__MIDL___MIDL_itf_win72Ezip2Ebase_0000_0000_0001>::size(a2 + 88);
      goto LABEL_24;
    }
    std::vector<__MIDL___MIDL_itf_win72Ezip2Ebase_0000_0000_0001>::capacity(a1 + 88, v31);
    v33 = std::vector<__MIDL___MIDL_itf_win72Ezip2Ebase_0000_0000_0001>::size(a2 + 88);
    if ( v33 > v34 )
    {
      v40 = *(void **)(a1 + 96);
      if ( v40 )
        operator delete(v40);
      v41 = std::vector<__MIDL___MIDL_itf_win72Ezip2Ebase_0000_0000_0001>::size(a2 + 88);
      if ( !(unsigned __int8)std::vector<__MIDL___MIDL_itf_win72Ezip2Ebase_0000_0000_0001>::_Buy(a1 + 88, v41) )
        goto LABEL_24;
      v37 = *(_QWORD *)(a1 + 96);
      v39 = *(_QWORD *)(a2 + 96);
    }
    else
    {
      v35 = std::vector<__MIDL___MIDL_itf_win72Ezip2Ebase_0000_0000_0001>::size(a1 + 88);
      std::copy<__MIDL___MIDL_itf_win72Ezip2Ebase_0000_0000_0001 *,__MIDL___MIDL_itf_win72Ezip2Ebase_0000_0000_0001 *>(
        v36,
        v36 + 24 * v35,
        *(_QWORD *)(a1 + 96));
      v37 = *(_QWORD *)(a1 + 104);
      v39 = v38;
    }
    v15 = std::_Uninit_copy<__MIDL___MIDL_itf_win72Ezip2Ebase_0000_0000_0001 *,__MIDL___MIDL_itf_win72Ezip2Ebase_0000_0000_0001 *,std::allocator<__MIDL___MIDL_itf_win72Ezip2Ebase_0000_0000_0001>>(
            v39,
            *(_QWORD *)(a2 + 104),
            v37);
    goto LABEL_23;
  }
  v15 = *(_QWORD *)(a1 + 96);
  if ( v15 != *(_QWORD *)(a1 + 104) )
LABEL_23:
    *(_QWORD *)(a1 + 104) = v15;
LABEL_24:
  *(_DWORD *)(a1 + 120) = *(_DWORD *)(a2 + 120);
  *(_OWORD *)(a1 + 128) = *(_OWORD *)(a2 + 128);
  *(_OWORD *)(a1 + 144) = *(_OWORD *)(a2 + 144);
  *(_OWORD *)(a1 + 160) = *(_OWORD *)(a2 + 160);
  *(_OWORD *)(a1 + 176) = *(_OWORD *)(a2 + 176);
  *(_QWORD *)(a1 + 192) = *(_QWORD *)(a2 + 192);
  *(_DWORD *)(a1 + 200) = *(_DWORD *)(a2 + 200);
  *(_BYTE *)(a1 + 204) = *(_BYTE *)(a2 + 204);
  *(_BYTE *)(a1 + 205) = *(_BYTE *)(a2 + 205);
  *(_BYTE *)(a1 + 206) = *(_BYTE *)(a2 + 206);
  return a1;
}

```

## disassembly

```asm
0x180020ed4  push    rbx
0x180020ed6  push    rbp
0x180020ed7  push    rsi
0x180020ed8  push    rdi
0x180020ed9  push    r14
0x180020edb  push    r15
0x180020edd  sub     rsp, 38h
0x180020ee1  lea     r14, [rdx+8]
0x180020ee5  mov     rbp, rdx
0x180020ee8  mov     rdi, [r14+18h]
0x180020eec  lea     rbx, [rcx+8]
0x180020ef0  mov     rsi, rcx
0x180020ef3  cmp     rbx, r14
0x180020ef6  jz      loc_1800211B0
0x180020efc  cmp     rdi, 0FFFFFFFFFFFFFFFEh
0x180020f00  ja      loc_1800211D1
0x180020f06  cmp     [rbx+20h], rdi
0x180020f0a  jb      loc_180021069
0x180020f10  test    rdi, rdi
0x180020f13  jz      loc_18002108E
0x180020f19  cmp     qword ptr [r14+20h], 10h
0x180020f1e  lea     r8, [r14+8]
0x180020f22  jb      short loc_180020F27
0x180020f24  mov     r8, [r8]; Source
0x180020f27  mov     rdx, [rbx+20h]; DestinationSize
0x180020f2b  lea     r14, [rbx+8]
0x180020f2f  cmp     rdx, 10h
0x180020f33  jb      loc_180021086
0x180020f39  mov     rcx, [r14]; Destination
0x180020f3c  mov     r9, rdi; SourceSize
0x180020f3f  call    cs:__imp_memcpy_s
0x180020f45  cmp     qword ptr [rbx+20h], 10h
0x180020f4a  jb      short loc_180020F4F
0x180020f4c  mov     r14, [r14]
0x180020f4f  mov     [rbx+18h], rdi
0x180020f53  mov     byte ptr [rdi+r14], 0
0x180020f58  mov     al, [rbp+30h]
0x180020f5b  lea     rdi, [rbp+38h]
0x180020f5f  lea     rbx, [rsi+38h]
0x180020f63  mov     [rsi+30h], al
0x180020f66  cmp     rbx, rdi
0x180020f69  jz      short loc_180020F95
0x180020f6b  mov     r9, [rdi+8]
0x180020f6f  test    r9, r9
0x180020f72  jz      short loc_180020F81
0x180020f74  mov     rdx, [rdi+10h]
0x180020f78  sub     rdx, r9
0x180020f7b  jnz     loc_1800210AC
0x180020f81  mov     rax, [rbx+8]
0x180020f85  cmp     rax, [rbx+10h]
0x180020f89  jnz     short loc_180020F91
0x180020f8b  jmp     short loc_180020F95
0x180020f8d  lea     rax, [rdi+r15]
0x180020f91  mov     [rbx+10h], rax
0x180020f95  lea     rdi, [rbp+58h]
0x180020f99  lea     rbx, [rsi+58h]
0x180020f9d  cmp     rbx, rdi
0x180020fa0  jz      short loc_180020FDB
0x180020fa2  mov     r10, [rdi+8]
0x180020fa6  test    r10, r10
0x180020fa9  jz      short loc_180020FCD
0x180020fab  mov     rax, [rdi+10h]
0x180020faf  mov     rcx, 0AAAAAAAAAAAAAAABh
0x180020fb9  sub     rax, r10
0x180020fbc  sar     rax, 3
0x180020fc0  imul    rax, rcx
0x180020fc4  test    rax, rax
0x180020fc7  jnz     loc_1800211DB
0x180020fcd  mov     rax, [rbx+8]
0x180020fd1  cmp     rax, [rbx+10h]
0x180020fd5  jz      short loc_180020FDB
0x180020fd7  mov     [rbx+10h], rax
0x180020fdb  mov     eax, [rbp+78h]
0x180020fde  mov     [rsi+78h], eax
0x180020fe1  movups  xmm0, xmmword ptr [rbp+80h]
0x180020fe8  movups  xmmword ptr [rsi+80h], xmm0
0x180020fef  movups  xmm1, xmmword ptr [rbp+90h]
0x180020ff6  movups  xmmword ptr [rsi+90h], xmm1
0x180020ffd  movups  xmm0, xmmword ptr [rbp+0A0h]
0x180021004  movups  xmmword ptr [rsi+0A0h], xmm0
0x18002100b  movups  xmm1, xmmword ptr [rbp+0B0h]
0x180021012  movups  xmmword ptr [rsi+0B0h], xmm1
0x180021019  movsd   xmm0, qword ptr [rbp+0C0h]
0x180021021  movsd   qword ptr [rsi+0C0h], xmm0
0x180021029  mov     eax, [rbp+0C8h]
0x18002102f  mov     [rsi+0C8h], eax
0x180021035  mov     al, [rbp+0CCh]
0x18002103b  mov     [rsi+0CCh], al
0x180021041  mov     al, [rbp+0CDh]
0x180021047  mov     [rsi+0CDh], al
0x18002104d  mov     al, [rbp+0CEh]
0x180021053  mov     [rsi+0CEh], al
0x180021059  mov     rax, rsi
0x18002105c  add     rsp, 38h
0x180021060  pop     r15
0x180021062  pop     r14
0x180021064  pop     rdi
0x180021065  pop     rsi
0x180021066  pop     rbp
0x180021067  pop     rbx
0x180021068  retn
0x180021069  mov     r8, [rbx+18h]
0x18002106d  mov     rdx, rdi
0x180021070  mov     rcx, rbx
0x180021073  call    ?_Copy@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@V_STL70@@@std@@IEAAX_K0@Z; std::string::_Copy(unsigned __int64,unsigned __int64)
0x180021078  test    rdi, rdi
0x18002107b  jz      loc_180020F58
0x180021081  jmp     loc_180020F19
0x180021086  mov     rcx, r14
0x180021089  jmp     loc_180020F3C
0x18002108e  cmp     qword ptr [rbx+20h], 10h
0x180021093  lea     rax, [rbx+8]
0x180021097  jb      short loc_18002109C
0x180021099  mov     rax, [rax]
0x18002109c  mov     qword ptr [rbx+18h], 0
0x1800210a4  mov     byte ptr [rax], 0
0x1800210a7  jmp     loc_180020F58
0x1800210ac  mov     rcx, [rbx+8]; Block
0x1800210b0  test    rcx, rcx
0x1800210b3  jnz     short loc_1800210E1
0x1800210b5  xor     eax, eax
0x1800210b7  cmp     rdx, rax
0x1800210ba  ja      short loc_1800210F4
0x1800210bc  mov     rdx, [rdi+10h]
0x1800210c0  mov     r8, rcx
0x1800210c3  mov     rcx, r9; Source
0x1800210c6  call    ??$copy@PEBEPEAE@std@@YAPEAEPEBE0PEAE@Z; std::copy<uchar const *,uchar *>(uchar const *,uchar const *,uchar *)
0x1800210cb  cmp     qword ptr [rdi+8], 0
0x1800210d0  jnz     short loc_1800210EA
0x1800210d2  xor     ecx, ecx
0x1800210d4  add     rcx, [rbx+8]
0x1800210d8  mov     [rbx+10h], rcx
0x1800210dc  jmp     loc_180020F95
0x1800210e1  mov     rax, [rbx+10h]
0x1800210e5  sub     rax, rcx
0x1800210e8  jmp     short loc_1800210B7
0x1800210ea  mov     rcx, [rdi+10h]
0x1800210ee  sub     rcx, [rdi+8]
0x1800210f2  jmp     short loc_1800210D4
0x1800210f4  test    rcx, rcx
0x1800210f7  jnz     short loc_180021150
0x1800210f9  xor     eax, eax
0x1800210fb  cmp     rdx, rax
0x1800210fe  jbe     short loc_180021159
0x180021100  test    rcx, rcx
0x180021103  jz      short loc_18002110A
0x180021105  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18002110a  cmp     qword ptr [rdi+8], 0
0x18002110f  jnz     loc_1800211A3
0x180021115  xor     edx, edx
0x180021117  mov     rcx, rbx
0x18002111a  call    ?_Buy@?$vector@EV?$allocator@E@std@@@std@@IEAA_N_K@Z; std::vector<uchar>::_Buy(unsigned __int64)
0x18002111f  test    al, al
0x180021121  jz      loc_180020F95
0x180021127  mov     r8, [rdi+8]; Source
0x18002112b  mov     rdi, [rdi+10h]
0x18002112f  mov     r14, [rbx+8]
0x180021133  sub     rdi, r8
0x180021136  jz      short loc_180021147
0x180021138  mov     r9, rdi; SourceSize
0x18002113b  mov     rdx, rdi; DestinationSize
0x18002113e  mov     rcx, r14; Destination
0x180021141  call    cs:__imp_memmove_s
0x180021147  lea     rax, [rdi+r14]
0x18002114b  jmp     loc_180020F91
0x180021150  mov     rax, [rbx+18h]
0x180021154  sub     rax, rcx
0x180021157  jmp     short loc_1800210FB
0x180021159  test    rcx, rcx
0x18002115c  jnz     short loc_18002119A
0x18002115e  xor     eax, eax
0x180021160  lea     r14, [r9+rax]
0x180021164  mov     r8, rcx
0x180021167  mov     rdx, r14
0x18002116a  mov     rcx, r9; Source
0x18002116d  call    ??$copy@PEBEPEAE@std@@YAPEAEPEBE0PEAE@Z; std::copy<uchar const *,uchar *>(uchar const *,uchar const *,uchar *)
0x180021172  mov     rdi, [rdi+10h]
0x180021176  mov     r15, [rbx+10h]
0x18002117a  sub     rdi, r14
0x18002117d  jz      loc_180020F8D
0x180021183  mov     r9, rdi; SourceSize
0x180021186  mov     r8, r14; Source
0x180021189  mov     rdx, rdi; DestinationSize
0x18002118c  mov     rcx, r15; Destination
0x18002118f  call    cs:__imp_memmove_s
0x180021195  jmp     loc_180020F8D
0x18002119a  mov     rax, [rbx+10h]
0x18002119e  sub     rax, rcx
0x1800211a1  jmp     short loc_180021160
0x1800211a3  mov     rdx, [rdi+10h]
0x1800211a7  sub     rdx, [rdi+8]
0x1800211ab  jmp     loc_180021117
0x1800211b0  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800211b4  mov     rdx, rdi
0x1800211b7  mov     rcx, rbx
0x1800211ba  call    ?erase@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@V_STL70@@@std@@QEAAAEAV12@_K0@Z; std::string::erase(unsigned __int64,unsigned __int64)
0x1800211bf  xor     r8d, r8d
0x1800211c2  xor     edx, edx
0x1800211c4  mov     rcx, rbx
0x1800211c7  call    ?erase@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@V_STL70@@@std@@QEAAAEAV12@_K0@Z; std::string::erase(unsigned __int64,unsigned __int64)
0x1800211cc  jmp     loc_180020F58
0x1800211d1  call    ?_Xlen@_String_base@std@@SAXXZ; std::_String_base::_Xlen(void)
0x1800211d6  jmp     loc_180020F06
0x1800211db  mov     rcx, rbx
0x1800211de  call    ?size@?$vector@U__MIDL___MIDL_itf_win72Ezip2Ebase_0000_0000_0001@@V?$allocator@U__MIDL___MIDL_itf_win72Ezip2Ebase_0000_0000_0001@@@std@@@std@@QEBA_KXZ; std::vector<__MIDL___MIDL_itf_win72Ezip2Ebase_0000_0000_0001>::size(void)
0x1800211e3  mov     rcx, rdi
0x1800211e6  mov     rdx, rax
0x1800211e9  call    ?size@?$vector@U__MIDL___MIDL_itf_win72Ezip2Ebase_0000_0000_0001@@V?$allocator@U__MIDL___MIDL_itf_win72Ezip2Ebase_0000_0000_0001@@@std@@@std@@QEBA_KXZ; std::vector<__MIDL___MIDL_itf_win72Ezip2Ebase_0000_0000_0001>::size(void)
0x1800211ee  cmp     rax, rdx
0x1800211f1  ja      short loc_180021220
0x1800211f3  mov     r8, [rbx+8]
0x1800211f7  mov     rcx, r10
0x1800211fa  mov     rdx, [rdi+10h]
0x1800211fe  call    ??$copy@PEAU__MIDL___MIDL_itf_win72Ezip2Ebase_0000_0000_0001@@PEAU1@@std@@YAPEAU__MIDL___MIDL_itf_win72Ezip2Ebase_0000_0000_0001@@PEAU1@00@Z; std::copy<__MIDL___MIDL_itf_win72Ezip2Ebase_0000_0000_0001 *,__MIDL___MIDL_itf_win72Ezip2Ebase_0000_0000_0001 *>(__MIDL___MIDL_itf_win72Ezip2Ebase_0000_0000_0001 *,__MIDL___MIDL_itf_win72Ezip2Ebase_0000_0000_0001 *,__MIDL___MIDL_itf_win72Ezip2Ebase_0000_0000_0001 *)
0x180021203  mov     rcx, rdi
0x180021206  call    ?size@?$vector@U__MIDL___MIDL_itf_win72Ezip2Ebase_0000_0000_0001@@V?$allocator@U__MIDL___MIDL_itf_win72Ezip2Ebase_0000_0000_0001@@@std@@@std@@QEBA_KXZ; std::vector<__MIDL___MIDL_itf_win72Ezip2Ebase_0000_0000_0001>::size(void)
0x18002120b  lea     rcx, [rax+rax*2]
0x18002120f  mov     rax, [rbx+8]
0x180021213  lea     rcx, [rax+rcx*8]
0x180021217  mov     [rbx+10h], rcx
0x18002121b  jmp     loc_180020FDB
0x180021220  mov     rcx, rbx
0x180021223  call    ?capacity@?$vector@U__MIDL___MIDL_itf_win72Ezip2Ebase_0000_0000_0001@@V?$allocator@U__MIDL___MIDL_itf_win72Ezip2Ebase_0000_0000_0001@@@std@@@std@@QEBA_KXZ; std::vector<__MIDL___MIDL_itf_win72Ezip2Ebase_0000_0000_0001>::capacity(void)
0x180021228  mov     rcx, rdi
0x18002122b  mov     rdx, rax
0x18002122e  call    ?size@?$vector@U__MIDL___MIDL_itf_win72Ezip2Ebase_0000_0000_0001@@V?$allocator@U__MIDL___MIDL_itf_win72Ezip2Ebase_0000_0000_0001@@@std@@@std@@QEBA_KXZ; std::vector<__MIDL___MIDL_itf_win72Ezip2Ebase_0000_0000_0001>::size(void)
0x180021233  cmp     rax, rdx
0x180021236  ja      short loc_180021260
0x180021238  mov     rcx, rbx
0x18002123b  call    ?size@?$vector@U__MIDL___MIDL_itf_win72Ezip2Ebase_0000_0000_0001@@V?$allocator@U__MIDL___MIDL_itf_win72Ezip2Ebase_0000_0000_0001@@@std@@@std@@QEBA_KXZ; std::vector<__MIDL___MIDL_itf_win72Ezip2Ebase_0000_0000_0001>::size(void)
0x180021240  mov     r8, [rbx+8]
0x180021244  lea     rcx, [rax+rax*2]
0x180021248  lea     r9, [r10+rcx*8]
0x18002124c  mov     rcx, r10
0x18002124f  mov     rdx, r9
0x180021252  call    ??$copy@PEAU__MIDL___MIDL_itf_win72Ezip2Ebase_0000_0000_0001@@PEAU1@@std@@YAPEAU__MIDL___MIDL_itf_win72Ezip2Ebase_0000_0000_0001@@PEAU1@00@Z; std::copy<__MIDL___MIDL_itf_win72Ezip2Ebase_0000_0000_0001 *,__MIDL___MIDL_itf_win72Ezip2Ebase_0000_0000_0001 *>(__MIDL___MIDL_itf_win72Ezip2Ebase_0000_0000_0001 *,__MIDL___MIDL_itf_win72Ezip2Ebase_0000_0000_0001 *,__MIDL___MIDL_itf_win72Ezip2Ebase_0000_0000_0001 *)
0x180021257  mov     r8, [rbx+10h]
0x18002125b  mov     rcx, r9
0x18002125e  jmp     short loc_180021291
0x180021260  mov     rcx, [rbx+8]; Block
0x180021264  test    rcx, rcx
0x180021267  jz      short loc_18002126E
0x180021269  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18002126e  mov     rcx, rdi
0x180021271  call    ?size@?$vector@U__MIDL___MIDL_itf_win72Ezip2Ebase_0000_0000_0001@@V?$allocator@U__MIDL___MIDL_itf_win72Ezip2Ebase_0000_0000_0001@@@std@@@std@@QEBA_KXZ; std::vector<__MIDL___MIDL_itf_win72Ezip2Ebase_0000_0000_0001>::size(void)
0x180021276  mov     rdx, rax
0x180021279  mov     rcx, rbx
0x18002127c  call    ?_Buy@?$vector@U__MIDL___MIDL_itf_win72Ezip2Ebase_0000_0000_0001@@V?$allocator@U__MIDL___MIDL_itf_win72Ezip2Ebase_0000_0000_0001@@@std@@@std@@IEAA_N_K@Z; std::vector<__MIDL___MIDL_itf_win72Ezip2Ebase_0000_0000_0001>::_Buy(unsigned __int64)
0x180021281  test    al, al
0x180021283  jz      loc_180020FDB
0x180021289  mov     r8, [rbx+8]
0x18002128d  mov     rcx, [rdi+8]
0x180021291  mov     rdx, [rdi+10h]
0x180021295  call    ??$_Uninit_copy@PEAU__MIDL___MIDL_itf_win72Ezip2Ebase_0000_0000_0001@@PEAU1@V?$allocator@U__MIDL___MIDL_itf_win72Ezip2Ebase_0000_0000_0001@@@std@@@std@@YAPEAU__MIDL___MIDL_itf_win72Ezip2Ebase_0000_0000_0001@@PEAU1@00AEAV?$allocator@U__MIDL___MIDL_itf_win72Ezip2Ebase_0000_0000_0001@@@0@U_Nonscalar_ptr_iterator_tag@0@U_Range_checked_iterator_tag@0@@Z; std::_Uninit_copy<__MIDL___MIDL_itf_win72Ezip2Ebase_0000_0000_0001 *,__MIDL___MIDL_itf_win72Ezip2Ebase_0000_0000_0001 *,std::allocator<__MIDL___MIDL_itf_win72Ezip2Ebase_0000_0000_0001>>(__MIDL___MIDL_itf_win72Ezip2Ebase_0000_0000_0001 *,__MIDL___MIDL_itf_win72Ezip2Ebase_0000_0000_0001 *,__MIDL___MIDL_itf_win72Ezip2Ebase_0000_0000_0001 *,std::allocator<__MIDL___MIDL_itf_win72Ezip2Ebase_0000_0000_0001> &,std::_Nonscalar_ptr_iterator_tag,std::_Range_checked_iterator_tag)
0x18002129a  jmp     loc_180020FD7
```
