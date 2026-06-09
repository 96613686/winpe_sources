# CRevocation::GetXML(uint *,ushort * *)

- ea: `0x1800111fc`
- end: `0x1800117f7`
- name: `?GetXML@CRevocation@@QEAAJPEAIPEAPEAG@Z`
- size: `1531`
- prototype: `__int64 __fastcall(CRevocation *__hidden this, unsigned int *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18000bc94`

## callees

- `0x180001284`
- `0x180001290`
- `0x1800111fc`
- `0x180012794`
- `0x180015438`
- `0x180017358`
- `0x18001ef6c`
- `0x180020080`
- `0x18005bd72`
- `0x18005bdc0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180011792`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180011792`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180011257`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180011257`

## pseudocode

```c
// Hidden C++ exception states: #wind=1 #try_helpers=1
__int64 __fastcall CRevocation::GetXML(CRevocation *this, unsigned int *a2, unsigned __int16 **a3)
{
  int v5; // edi
  unsigned __int16 *v6; // rax
  const wchar_t *v7; // rcx
  __int64 v8; // rdx
  __int64 v9; // r8
  unsigned __int16 *v10; // rcx
  const wchar_t *v11; // rax
  void *v12; // r14
  unsigned __int16 *v13; // r12
  unsigned __int16 *v14; // r13
  unsigned __int64 v15; // rax
  __int64 v16; // rdx
  __int64 v17; // rcx
  unsigned __int64 v18; // rax
  unsigned __int64 v19; // rdx
  __int64 v20; // rax
  unsigned __int64 v21; // rbx
  unsigned int v22; // eax
  CDRMCBase *v23; // rcx
  unsigned int v24; // r15d
  unsigned int v25; // eax
  CDRMCBase *v26; // rcx
  unsigned int v27; // ebx
  unsigned int v28; // eax
  CDRMCBase *v29; // rcx
  unsigned int v30; // r15d
  __int64 v31; // rcx
  unsigned int v32; // r15d
  CDRMCBase *v33; // rcx
  __int64 v34; // rax
  unsigned int v35; // eax
  unsigned __int64 v36; // rbx
  unsigned __int16 *v37; // rax
  unsigned int v38; // ebx
  unsigned __int16 *v39; // r8
  __int64 v40; // r15
  CDRMCBase *v41; // rcx
  __int64 v42; // rcx
  __int64 v43; // r15
  unsigned __int16 *v44; // rax
  unsigned __int16 **v45; // r15
  const unsigned __int16 *v46; // r11
  const unsigned __int16 *v47; // rax
  unsigned int v49; // [rsp+60h] [rbp-428h] BYREF
  unsigned __int16 **v50; // [rsp+68h] [rbp-420h]
  void *v51; // [rsp+70h] [rbp-418h]
  unsigned __int16 *v52; // [rsp+78h] [rbp-410h]
  unsigned __int16 *v53; // [rsp+80h] [rbp-408h]
  void *Block; // [rsp+88h] [rbp-400h] BYREF
  unsigned int *v55; // [rsp+90h] [rbp-3F8h]
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+98h] [rbp-3F0h]
  __int64 v57; // [rsp+A0h] [rbp-3E8h]
  char *v58; // [rsp+A8h] [rbp-3E0h]
  unsigned __int16 v59[8]; // [rsp+B0h] [rbp-3D8h] BYREF
  __int128 v60; // [rsp+C0h] [rbp-3C8h]
  unsigned __int16 v61[216]; // [rsp+D0h] [rbp-3B8h] BYREF
  unsigned __int16 v62[228]; // [rsp+280h] [rbp-208h] BYREF

  v57 = -2;
  v50 = a3;
  v55 = a2;
  lpCriticalSection = (LPCRITICAL_SECTION)((char *)this + 88);
  v58 = (char *)this + 88;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 88));
  v5 = 0;
  v6 = v61;
  v7 = L"<REFRESH><DISTRIBUTIONPOINT><OBJECT type=\"Revocation\"><ID type=\"%s\">%s</ID><ADDRESS type=\"URL\">%s</ADDRESS>"
        "%s</OBJECT>%s</DISTRIBUTIONPOINT><INTERVALTIME days=\"%d\" hours=\"%d\" minutes=\"%d\" seconds=\"%d\" /></REFRESH>";
  v8 = 3;
  v9 = 3;
  do
  {
    *(_OWORD *)v6 = *(_OWORD *)v7;
    *((_OWORD *)v6 + 1) = *((_OWORD *)v7 + 1);
    *((_OWORD *)v6 + 2) = *((_OWORD *)v7 + 2);
    *((_OWORD *)v6 + 3) = *((_OWORD *)v7 + 3);
    *((_OWORD *)v6 + 4) = *((_OWORD *)v7 + 4);
    *((_OWORD *)v6 + 5) = *((_OWORD *)v7 + 5);
    *((_OWORD *)v6 + 6) = *((_OWORD *)v7 + 6);
    *((_OWORD *)v6 + 7) = *((_OWORD *)v7 + 7);
    v6 += 64;
    v7 += 64;
    --v9;
  }
  while ( v9 );
  *(_OWORD *)v6 = *(_OWORD *)v7;
  *((_OWORD *)v6 + 1) = *((_OWORD *)v7 + 1);
  *(_OWORD *)(v6 + 14) = *(_OWORD *)(v7 + 14);
  *(_OWORD *)v59 = *(_OWORD *)L"<NAME>%s</NAME>";
  v60 = *(_OWORD *)L"</NAME>";
  v10 = v62;
  v11 = L"<PUBLICKEY><ALGORITHM>RSA</ALGORITHM><PARAMETER name=\"public-exponent\"><VALUE encoding=\"integer32\">65537</VA"
         "LUE></PARAMETER><PARAMETER name=\"modulus\"><VALUE encoding=\"base64\" size=\"%d\">%s</VALUE></PARAMETER></PUBLICKEY>";
  do
  {
    *(_OWORD *)v10 = *(_OWORD *)v11;
    *((_OWORD *)v10 + 1) = *((_OWORD *)v11 + 1);
    *((_OWORD *)v10 + 2) = *((_OWORD *)v11 + 2);
    *((_OWORD *)v10 + 3) = *((_OWORD *)v11 + 3);
    *((_OWORD *)v10 + 4) = *((_OWORD *)v11 + 4);
    *((_OWORD *)v10 + 5) = *((_OWORD *)v11 + 5);
    *((_OWORD *)v10 + 6) = *((_OWORD *)v11 + 6);
    *((_OWORD *)v10 + 7) = *((_OWORD *)v11 + 7);
    v10 += 64;
    v11 += 64;
    --v8;
  }
  while ( v8 );
  *(_OWORD *)v10 = *(_OWORD *)v11;
  *((_OWORD *)v10 + 1) = *((_OWORD *)v11 + 1);
  *((_OWORD *)v10 + 2) = *((_OWORD *)v11 + 2);
  *((_QWORD *)v10 + 6) = *((_QWORD *)v11 + 6);
  v12 = 0;
  v51 = 0;
  v13 = 0;
  v52 = 0;
  v14 = 0;
  v53 = 0;
  Block = 0;
  if ( !a2 )
  {
    v5 = -2147024809;
    goto LABEL_56;
  }
  *a2 = 0;
  if ( !(unsigned int)CRevocation::IsSet(this) )
    goto LABEL_56;
  v15 = -1;
  do
    ++v15;
  while ( *(_WORD *)(*((_QWORD *)this + 16) + 2 * v15) );
  if ( v15 > 0xFFFFFF2A )
    SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow(4294967082LL);
  v16 = (unsigned int)(v15 + 213);
  v17 = -1;
  do
    ++v17;
  while ( *(_WORD *)(*((_QWORD *)this + 17) + 2 * v17) );
  v18 = (unsigned int)v16;
  v19 = v17 + v16;
  if ( v19 < v18 || v19 > 0xFFFFFFFF )
    SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow(v17);
  v20 = -1;
  do
    ++v20;
  while ( *(_WORD *)(*((_QWORD *)this + 18) + 2 * v20) );
  v21 = (unsigned int)v19 + v20;
  if ( v21 < (unsigned int)v19 || v21 > 0xFFFFFFFF )
    SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow((unsigned int)v19);
  v22 = CDRMCBase::UINT2STRLength((CDRMCBase *)(unsigned int)v19, *((unsigned __int16 *)this + 87));
  v24 = v21 + v22;
  if ( (unsigned int)v21 + v22 < (unsigned int)v21 )
    SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow(v23);
  v25 = CDRMCBase::UINT2STRLength(v23, *((unsigned __int16 *)this + 88));
  v27 = v24 + v25;
  if ( v24 + v25 < v24 )
    SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow(v26);
  v28 = CDRMCBase::UINT2STRLength(v26, *((unsigned __int16 *)this + 89));
  v30 = v27 + v28;
  if ( v27 + v28 < v27 )
    SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow(v29);
  v31 = v30 + CDRMCBase::UINT2STRLength(v29, *((unsigned __int16 *)this + 90));
  if ( (unsigned int)v31 < v30 )
    SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow(v31);
  v32 = v31 + 16;
  if ( (int)v31 + 16 < (unsigned int)v31 )
    SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow(v31);
  v33 = (CDRMCBase *)*((_QWORD *)this + 19);
  if ( v33 )
  {
    v34 = -1;
    do
      ++v34;
    while ( *((_WORD *)v33 + v34) );
    v35 = v34 + 14;
    v49 = v35;
    if ( v50 )
    {
      v36 = v35;
      v37 = (unsigned __int16 *)operator new[](saturated_mul(v35, 2u));
      v13 = v37;
      v52 = v37;
      if ( !v37 )
      {
        v5 = -2147024882;
        goto LABEL_56;
      }
      memset_0(v37, 0, 2 * v36);
      v5 = StringCchPrintfW(v13, v36, v59, *((_QWORD *)this + 19));
      if ( v5 < 0 )
        goto LABEL_56;
      v35 = v49;
    }
    v38 = v35 + v32;
    if ( v35 + v32 < v32 )
      SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow(v33);
  }
  else
  {
    v38 = v32;
  }
  v39 = (unsigned __int16 *)*((_QWORD *)this + 20);
  if ( v39 )
  {
    v40 = -1;
    do
      ++v40;
    while ( v39[v40] );
    v49 = 0;
    v5 = CDRMCBase::Base64DecodeData(v33, v40, v39, &v49, (unsigned __int8 **)&Block);
    if ( v5 < 0 )
      goto LABEL_56;
    v49 *= 8;
    v43 = CDRMCBase::UINT2STRLength(v41, v49) + 220 + (unsigned int)v40;
    if ( v50 )
    {
      v44 = (unsigned __int16 *)operator new[](saturated_mul((unsigned int)v43, 2u));
      v14 = v44;
      v53 = v44;
      if ( !v44 )
      {
        v5 = -2147024882;
        goto LABEL_56;
      }
      memset_0(v44, 0, 2 * v43);
      v5 = StringCchPrintfW(v14, (unsigned int)v43, v62, v49, *((_QWORD *)this + 20));
      if ( v5 < 0 )
        goto LABEL_56;
    }
    if ( (unsigned int)v43 + v38 < v38 )
      SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow(v42);
    v38 += v43;
  }
  v45 = v50;
  if ( !v50 )
  {
LABEL_55:
    *v55 = v38;
    goto LABEL_56;
  }
  v12 = operator new[](saturated_mul(v38, 2u));
  v51 = v12;
  if ( !v12 )
  {
    v5 = -2147024882;
    goto LABEL_56;
  }
  if ( 2 * (unsigned __int64)v38 > 0xFFFFFFFF )
    SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow(0xFFFFFFFFLL);
  memset_0(v12, 0, 2 * v38);
  v46 = &Src;
  v47 = &Src;
  if ( v14 )
    v47 = v14;
  if ( v13 )
    v46 = v13;
  v5 = StringCchPrintfW(
         (unsigned __int16 *)v12,
         v38,
         v61,
         *((_QWORD *)this + 17),
         *((_QWORD *)this + 16),
         *((_QWORD *)this + 18),
         v46,
         v47,
         *((unsigned __int16 *)this + 87),
         *((unsigned __int16 *)this + 88),
         *((unsigned __int16 *)this + 89),
         *((unsigned __int16 *)this + 90));
  if ( v5 >= 0 )
  {
    *v45 = (unsigned __int16 *)v12;
    v12 = 0;
    v51 = 0;
    goto LABEL_55;
  }
LABEL_56:
  operator delete(v12);
  operator delete(v13);
  operator delete(v14);
  operator delete(Block);
  LeaveCriticalSection(lpCriticalSection);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x1800111fc  push    rbx
0x1800111fe  push    rsi
0x1800111ff  push    rdi
0x180011200  push    r12
0x180011202  push    r13
0x180011204  push    r14
0x180011206  push    r15
0x180011208  sub     rsp, 450h
0x18001120f  mov     [rsp+488h+var_3E8], 0FFFFFFFFFFFFFFFEh
0x18001121b  mov     rax, cs:__security_cookie
0x180011222  xor     rax, rsp
0x180011225  mov     [rsp+488h+var_40], rax
0x18001122d  mov     [rsp+488h+var_420], r8
0x180011232  mov     rbx, rdx
0x180011235  mov     [rsp+488h+var_3F8], rdx
0x18001123d  mov     rsi, rcx
0x180011240  lea     rax, [rcx+58h]
0x180011244  mov     [rsp+488h+lpCriticalSection], rax
0x18001124c  mov     [rsp+488h+var_3E0], rax
0x180011254  mov     rcx, rax; lpCriticalSection
0x180011257  call    cs:__imp_EnterCriticalSection
0x18001125d  nop
0x18001125e  xor     r15d, r15d
0x180011261  mov     edi, r15d
0x180011264  lea     rax, [rsp+488h+var_3B8]
0x18001126c  lea     rcx, aRefreshDistrib; "<REFRESH><DISTRIBUTIONPOINT><OBJECT typ"...
0x180011273  lea     edx, [r15+3]
0x180011277  mov     r8d, edx
0x18001127a  lea     r9d, [rdx+7Dh]
0x18001127e  movups  xmm0, xmmword ptr [rcx]
0x180011281  movups  xmmword ptr [rax], xmm0
0x180011284  movups  xmm1, xmmword ptr [rcx+10h]
0x180011288  movups  xmmword ptr [rax+10h], xmm1
0x18001128c  movups  xmm0, xmmword ptr [rcx+20h]
0x180011290  movups  xmmword ptr [rax+20h], xmm0
0x180011294  movups  xmm1, xmmword ptr [rcx+30h]
0x180011298  movups  xmmword ptr [rax+30h], xmm1
0x18001129c  movups  xmm0, xmmword ptr [rcx+40h]
0x1800112a0  movups  xmmword ptr [rax+40h], xmm0
0x1800112a4  movups  xmm1, xmmword ptr [rcx+50h]
0x1800112a8  movups  xmmword ptr [rax+50h], xmm1
0x1800112ac  movups  xmm0, xmmword ptr [rcx+60h]
0x1800112b0  movups  xmmword ptr [rax+60h], xmm0
0x1800112b4  movups  xmm1, xmmword ptr [rcx+70h]
0x1800112b8  movups  xmmword ptr [rax+70h], xmm1
0x1800112bc  add     rax, r9
0x1800112bf  add     rcx, r9
0x1800112c2  sub     r8, 1
0x1800112c6  jnz     short loc_18001127E
0x1800112c8  movups  xmm0, xmmword ptr [rcx]
0x1800112cb  movups  xmmword ptr [rax], xmm0
0x1800112ce  movups  xmm1, xmmword ptr [rcx+10h]
0x1800112d2  movups  xmmword ptr [rax+10h], xmm1
0x1800112d6  movups  xmm0, xmmword ptr [rcx+1Ch]
0x1800112da  movups  xmmword ptr [rax+1Ch], xmm0
0x1800112de  movups  xmm1, xmmword ptr cs:aNameSName; "<NAME>%s</NAME>"
0x1800112e5  movups  xmmword ptr [rsp+488h+var_3D8], xmm1
0x1800112ed  movups  xmm0, xmmword ptr cs:aNameSName+10h; "</NAME>"
0x1800112f4  movups  [rsp+488h+var_3C8], xmm0
0x1800112fc  lea     rcx, [rsp+488h+var_208]
0x180011304  lea     rax, aPublickeyAlgor; "<PUBLICKEY><ALGORITHM>RSA</ALGORITHM><P"...
0x18001130b  movups  xmm0, xmmword ptr [rax]
0x18001130e  movups  xmmword ptr [rcx], xmm0
0x180011311  movups  xmm1, xmmword ptr [rax+10h]
0x180011315  movups  xmmword ptr [rcx+10h], xmm1
0x180011319  movups  xmm0, xmmword ptr [rax+20h]
0x18001131d  movups  xmmword ptr [rcx+20h], xmm0
0x180011321  movups  xmm1, xmmword ptr [rax+30h]
0x180011325  movups  xmmword ptr [rcx+30h], xmm1
0x180011329  movups  xmm0, xmmword ptr [rax+40h]
0x18001132d  movups  xmmword ptr [rcx+40h], xmm0
0x180011331  movups  xmm1, xmmword ptr [rax+50h]
0x180011335  movups  xmmword ptr [rcx+50h], xmm1
0x180011339  movups  xmm0, xmmword ptr [rax+60h]
0x18001133d  movups  xmmword ptr [rcx+60h], xmm0
0x180011341  movups  xmm1, xmmword ptr [rax+70h]
0x180011345  movups  xmmword ptr [rcx+70h], xmm1
0x180011349  add     rcx, r9
0x18001134c  add     rax, r9
0x18001134f  sub     rdx, 1
0x180011353  jnz     short loc_18001130B
0x180011355  movups  xmm0, xmmword ptr [rax]
0x180011358  movups  xmmword ptr [rcx], xmm0
0x18001135b  movups  xmm1, xmmword ptr [rax+10h]
0x18001135f  movups  xmmword ptr [rcx+10h], xmm1
0x180011363  movups  xmm0, xmmword ptr [rax+20h]
0x180011367  movups  xmmword ptr [rcx+20h], xmm0
0x18001136b  mov     rax, [rax+30h]
0x18001136f  mov     [rcx+30h], rax
0x180011373  mov     r14, r15
0x180011376  mov     [rsp+488h+var_418], r15
0x18001137b  mov     r12, r15
0x18001137e  mov     [rsp+488h+var_410], r15
0x180011383  mov     r13, r15
0x180011386  mov     [rsp+488h+var_408], r15
0x18001138e  mov     [rsp+488h+Block], r15
0x180011396  test    rbx, rbx
0x180011399  jnz     short loc_1800113A5
0x18001139b  mov     edi, 80070057h
0x1800113a0  jmp     loc_180011764
0x1800113a5  mov     [rbx], r15d
0x1800113a8  mov     rcx, rsi; this
0x1800113ab  call    ?IsSet@CRevocation@@QEAAHXZ; CRevocation::IsSet(void)
0x1800113b0  test    eax, eax
0x1800113b2  jnz     short loc_1800113B9
0x1800113b4  jmp     loc_180011764
0x1800113b9  mov     rcx, [rsi+80h]
0x1800113c0  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800113c4  mov     rax, r8
0x1800113c7  inc     rax
0x1800113ca  cmp     [rcx+rax*2], r15w
0x1800113cf  jnz     short loc_1800113C7
0x1800113d1  mov     ecx, 0FFFFFF2Ah
0x1800113d6  cmp     rax, rcx
0x1800113d9  ja      loc_1800117F0
0x1800113df  lea     edx, [rax+0D5h]
0x1800113e5  mov     rax, [rsi+88h]
0x1800113ec  mov     rcx, r8
0x1800113ef  inc     rcx
0x1800113f2  cmp     [rax+rcx*2], r15w
0x1800113f7  jnz     short loc_1800113EF
0x1800113f9  mov     eax, edx
0x1800113fb  add     rdx, rcx
0x1800113fe  cmp     rdx, rax
0x180011401  jb      loc_1800117EB
0x180011407  mov     r9d, 0FFFFFFFFh
0x18001140d  cmp     rdx, r9
0x180011410  ja      loc_1800117EB
0x180011416  mov     ecx, edx; this
0x180011418  mov     rdx, [rsi+90h]
0x18001141f  mov     rax, r8
0x180011422  inc     rax
0x180011425  cmp     [rdx+rax*2], r15w
0x18001142a  jnz     short loc_180011422
0x18001142c  lea     rbx, [rcx+rax]
0x180011430  cmp     rbx, rcx
0x180011433  jb      loc_1800117E6
0x180011439  cmp     rbx, r9
0x18001143c  ja      loc_1800117E6
0x180011442  movzx   edx, word ptr [rsi+0AEh]; unsigned int
0x180011449  call    ?UINT2STRLength@CDRMCBase@@QEAAII@Z; CDRMCBase::UINT2STRLength(uint)
0x18001144e  lea     r15d, [rbx+rax]
0x180011452  cmp     r15d, ebx
0x180011455  jb      loc_1800117BD
0x18001145b  movzx   edx, word ptr [rsi+0B0h]; unsigned int
0x180011462  call    ?UINT2STRLength@CDRMCBase@@QEAAII@Z; CDRMCBase::UINT2STRLength(uint)
0x180011467  lea     ebx, [r15+rax]
0x18001146b  cmp     ebx, r15d
0x18001146e  jb      loc_1800117C3
0x180011474  movzx   edx, word ptr [rsi+0B2h]; unsigned int
0x18001147b  call    ?UINT2STRLength@CDRMCBase@@QEAAII@Z; CDRMCBase::UINT2STRLength(uint)
0x180011480  lea     r15d, [rbx+rax]
0x180011484  cmp     r15d, ebx
0x180011487  jb      loc_1800117C8
0x18001148d  movzx   edx, word ptr [rsi+0B4h]; unsigned int
0x180011494  call    ?UINT2STRLength@CDRMCBase@@QEAAII@Z; CDRMCBase::UINT2STRLength(uint)
0x180011499  lea     ecx, [r15+rax]
0x18001149d  cmp     ecx, r15d
0x1800114a0  jb      loc_1800117CD
0x1800114a6  lea     r15d, [rcx+10h]
0x1800114aa  cmp     r15d, ecx
0x1800114ad  jb      loc_1800117D2
0x1800114b3  mov     rcx, [rsi+98h]; this
0x1800114ba  xor     edx, edx
0x1800114bc  test    rcx, rcx
0x1800114bf  jz      loc_180011558
0x1800114c5  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800114c9  mov     rax, r8
0x1800114cc  inc     rax
0x1800114cf  cmp     [rcx+rax*2], dx
0x1800114d3  jnz     short loc_1800114CC
0x1800114d5  add     eax, 0Eh
0x1800114d8  mov     [rsp+488h+var_428], eax
0x1800114dc  cmp     [rsp+488h+var_420], rdx
0x1800114e1  jz      short loc_180011549
0x1800114e3  mov     ebx, eax
0x1800114e5  mov     eax, 2
0x1800114ea  mul     rbx
0x1800114ed  cmovb   rax, r8
0x1800114f1  mov     rcx, rax; unsigned __int64
0x1800114f4  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1800114f9  mov     r12, rax
0x1800114fc  mov     [rsp+488h+var_410], rax
0x180011501  test    rax, rax
0x180011504  jnz     short loc_180011510
0x180011506  mov     edi, 8007000Eh
0x18001150b  jmp     loc_180011764
0x180011510  lea     r8, [rbx+rbx]; Size
0x180011514  xor     edx, edx; Val
0x180011516  mov     rcx, r12; void *
0x180011519  call    memset_0
0x18001151e  mov     r9, [rsi+98h]
0x180011525  lea     r8, [rsp+488h+var_3D8]; unsigned __int16 *
0x18001152d  mov     rdx, rbx; unsigned __int64
0x180011530  mov     rcx, r12; unsigned __int16 *
0x180011533  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180011538  mov     edi, eax
0x18001153a  xor     edx, edx
0x18001153c  test    eax, eax
0x18001153e  jns     short loc_180011545
0x180011540  jmp     loc_180011764
0x180011545  mov     eax, [rsp+488h+var_428]
0x180011549  lea     ebx, [rax+r15]
0x18001154d  cmp     ebx, r15d
0x180011550  jb      loc_1800117D7
0x180011556  jmp     short loc_18001155B
0x180011558  mov     ebx, r15d
0x18001155b  mov     r8, [rsi+0A0h]; unsigned __int16 *
0x180011562  test    r8, r8
0x180011565  jz      loc_180011646
0x18001156b  or      r15, 0FFFFFFFFFFFFFFFFh
0x18001156f  inc     r15
0x180011572  cmp     [r8+r15*2], dx
0x180011577  jnz     short loc_18001156F
0x180011579  mov     [rsp+488h+var_428], edx
0x18001157d  lea     rax, [rsp+488h+Block]
0x180011585  mov     [rsp+488h+var_468], rax; unsigned __int8 **
0x18001158a  lea     r9, [rsp+488h+var_428]; unsigned int *
0x18001158f  mov     edx, r15d; unsigned int
0x180011592  call    ?Base64DecodeData@CDRMCBase@@QEAAJIPEAGPEAIPEAPEAE@Z; CDRMCBase::Base64DecodeData(uint,ushort *,uint *,uchar * *)
0x180011597  mov     edi, eax
0x180011599  test    eax, eax
0x18001159b  jns     short loc_1800115A2
0x18001159d  jmp     loc_180011764
0x1800115a2  mov     eax, [rsp+488h+var_428]
0x1800115a6  shl     eax, 3
0x1800115a9  mov     [rsp+488h+var_428], eax
0x1800115ad  mov     edx, eax; unsigned int
0x1800115af  call    ?UINT2STRLength@CDRMCBase@@QEAAII@Z; CDRMCBase::UINT2STRLength(uint)
0x1800115b4  add     eax, 0DCh
0x1800115b9  add     r15d, eax
0x1800115bc  xor     edx, edx
0x1800115be  cmp     [rsp+488h+var_420], rdx
0x1800115c3  jz      short loc_180011638
0x1800115c5  mov     edi, r15d
0x1800115c8  lea     eax, [rdx+2]
0x1800115cb  mul     rdi
0x1800115ce  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1800115d5  cmovb   rax, rcx
0x1800115d9  mov     rcx, rax; unsigned __int64
0x1800115dc  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1800115e1  mov     r13, rax
0x1800115e4  mov     [rsp+488h+var_408], rax
0x1800115ec  test    rax, rax
0x1800115ef  jnz     short loc_1800115FB
0x1800115f1  mov     edi, 8007000Eh
0x1800115f6  jmp     loc_180011764
0x1800115fb  lea     r8, [r15+r15]; Size
0x1800115ff  xor     edx, edx; Val
0x180011601  mov     rcx, r13; void *
0x180011604  call    memset_0
0x180011609  mov     rax, [rsi+0A0h]
0x180011610  mov     [rsp+488h+var_468], rax
0x180011615  mov     r9d, [rsp+488h+var_428]
0x18001161a  lea     r8, [rsp+488h+var_208]; unsigned __int16 *
0x180011622  mov     rdx, rdi; unsigned __int64
0x180011625  mov     rcx, r13; unsigned __int16 *
0x180011628  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18001162d  mov     edi, eax
0x18001162f  test    eax, eax
0x180011631  jns     short loc_180011638
0x180011633  jmp     loc_180011764
0x180011638  lea     eax, [r15+rbx]
0x18001163c  cmp     eax, ebx
0x18001163e  jb      loc_1800117DC
0x180011644  mov     ebx, eax
0x180011646  mov     r15, [rsp+488h+var_420]
0x18001164b  test    r15, r15
0x18001164e  jz      loc_180011742
0x180011654  mov     edi, ebx
0x180011656  mov     eax, 2
0x18001165b  mul     rdi
0x18001165e  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180011665  cmovb   rax, rcx
0x180011669  mov     rcx, rax; unsigned __int64
0x18001166c  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180011671  mov     r14, rax
0x180011674  mov     [rsp+488h+var_418], rax
0x180011679  test    rax, rax
0x18001167c  jnz     short loc_180011688
0x18001167e  mov     edi, 8007000Eh
0x180011683  jmp     loc_180011764
0x180011688  lea     rax, [rdi+rdi]
0x18001168c  mov     ecx, 0FFFFFFFFh
0x180011691  cmp     rax, rcx
0x180011694  ja      loc_1800117E1
0x18001169a  mov     r8d, eax; Size
0x18001169d  xor     edx, edx; Val
0x18001169f  mov     rcx, r14; void *
0x1800116a2  call    memset_0
0x1800116a7  movzx   ecx, word ptr [rsi+0B4h]
0x1800116ae  movzx   r8d, word ptr [rsi+0B2h]
0x1800116b6  movzx   r9d, word ptr [rsi+0B0h]
0x1800116be  movzx   r10d, word ptr [rsi+0AEh]
0x1800116c6  lea     r11, Src
0x1800116cd  mov     rax, r11
0x1800116d0  test    r13, r13
0x1800116d3  cmovnz  rax, r13
0x1800116d7  test    r12, r12
0x1800116da  cmovnz  r11, r12
  ... truncated ...
```
