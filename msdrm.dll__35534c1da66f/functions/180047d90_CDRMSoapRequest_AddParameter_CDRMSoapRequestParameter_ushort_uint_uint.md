# CDRMSoapRequest::AddParameter(CDRMSoapRequestParameter *,ushort * *,uint,uint *)

- ea: `0x180047d90`
- end: `0x18004862e`
- name: `?AddParameter@CDRMSoapRequest@@IEAAJPEAVCDRMSoapRequestParameter@@PEAPEAGIPEAI@Z`
- size: `2206`
- prototype: `__int64 __fastcall(CDRMSoapRequest *__hidden this, struct CDRMSoapRequestParameter *, unsigned __int16 **, unsigned int, unsigned int *)`
- caller_count: `3`
- callee_count: `9`
- tags: `file_ops, registry_config`

## callers

- `0x180047d90`
- `0x18004a118`
- `0x18004a62c`

## callees

- `0x180001284`
- `0x180001290`
- `0x180017358`
- `0x18003b280`
- `0x180047d90`
- `0x180048834`
- `0x18005bd72`
- `0x18005bd96`
- `0x18005bdc0`

## import_xrefs

- `msvcrt!wcschr` at `0x1800483a8`
- `msvcrt!wcschr` at `0x1800483a8`

## string_xrefs

- `0x180048392`: `<?xml`

## pseudocode

```c
__int64 __fastcall CDRMSoapRequest::AddParameter(
        CDRMSoapRequest *this,
        struct CDRMSoapRequestParameter *a2,
        unsigned __int16 **a3,
        unsigned int a4,
        unsigned int *a5)
{
  unsigned __int16 *v5; // r13
  unsigned __int16 *v7; // r12
  __int64 v9; // r14
  CDRMSoapRequest *v10; // r10
  CDRMSoapRequest *v11; // rcx
  __int64 v12; // rbp
  __int64 v13; // rax
  CDRMSoapRequest *v14; // rcx
  CDRMSoapRequest *v15; // rcx
  unsigned __int64 v16; // rbx
  unsigned __int16 *v17; // rax
  size_t v18; // r8
  unsigned __int16 *v19; // rbx
  int v20; // eax
  __int64 v21; // rax
  CDRMSoapRequest *v22; // rcx
  bool v23; // cc
  const unsigned __int16 *v24; // r9
  unsigned __int64 v25; // r8
  CDRMSoapRequest *v26; // rcx
  __int64 v27; // rbp
  __int64 v28; // rax
  __int64 v29; // rbx
  CDRMSoapRequest *v30; // rcx
  char *v31; // r9
  unsigned __int16 *v32; // rax
  int v33; // ecx
  int v34; // edx
  CDRMSoapRequest *v35; // rcx
  const unsigned __int16 *v36; // r9
  __int64 v37; // rax
  unsigned int v38; // eax
  __int64 v39; // rax
  CDRMSoapRequest *v40; // rcx
  CDRMSoapRequest *v41; // rcx
  CDRMSoapRequest *v42; // rcx
  __int64 v43; // r8
  __int64 v44; // rax
  CDRMSoapRequest *v45; // rcx
  CDRMSoapRequest *v46; // rcx
  unsigned int v47; // ebx
  CDRMSoapRequest *v48; // rcx
  __int64 v49; // rbp
  __int64 v50; // rax
  CDRMSoapRequest *v51; // rcx
  __int64 v52; // rbx
  CDRMSoapRequest *v53; // rcx
  CDRMSoapRequest *v54; // rcx
  __int64 v55; // rbp
  __int64 v56; // rax
  CDRMSoapRequest *v57; // rcx
  const wchar_t *v58; // r13
  CDRMSoapRequest *v59; // rcx
  wchar_t *v60; // rax
  __int64 v62; // rax
  CDRMSoapRequest *v63; // rcx
  CDRMSoapRequest *v64; // rcx
  CDRMSoapRequest *v65; // rcx
  __int64 v66; // rax
  CDRMSoapRequest *v67; // rcx
  unsigned int v68; // edx
  __int64 v69; // rax
  unsigned int v70; // eax
  CDRMSoapRequest *v71; // rcx
  CDRMSoapRequest *v72; // rcx
  int v73; // [rsp+38h] [rbp-70h]
  unsigned int v74; // [rsp+3Ch] [rbp-6Ch] BYREF
  CDRMSoapRequest *v75; // [rsp+40h] [rbp-68h]
  unsigned __int16 v76[8]; // [rsp+48h] [rbp-60h] BYREF

  v5 = 0;
  v7 = *a3;
  v9 = a4;
  v10 = this;
  v75 = this;
  v73 = 0;
  v74 = 0;
  if ( !*(_DWORD *)a2 || *(_DWORD *)a2 == 3 )
  {
    v65 = (CDRMSoapRequest *)*((_QWORD *)a2 + 1);
    v12 = -1;
    v66 = -1;
    do
      ++v66;
    while ( *((_WORD *)v65 + v66) );
    *a5 += v66 + 1;
    if ( a4 > *a5 )
    {
      CDRMSoapRequest::CatRequest(v65, a3, a4, L"<");
      CDRMSoapRequest::CatRequest(v67, a3, v9 - (*a3 - v7), *((const unsigned __int16 **)a2 + 1));
    }
    v15 = (CDRMSoapRequest *)*((_QWORD *)a2 + 2);
    v68 = *a5;
    if ( v15 )
    {
      v69 = -1;
      do
        ++v69;
      while ( *((_WORD *)v15 + v69) );
      v70 = v68 + v69 + 1;
      *a5 = v70;
      if ( (unsigned int)v9 > v70 )
      {
        CDRMSoapRequest::CatRequest(v15, a3, v9 - (*a3 - v7), ">");
        CDRMSoapRequest::CatRequest(v71, a3, v9 - (*a3 - v7), *((const unsigned __int16 **)a2 + 2));
      }
      do
        ++v12;
      while ( *(_WORD *)(*((_QWORD *)a2 + 1) + 2 * v12) );
      goto LABEL_103;
    }
    *a5 = v68 + 14;
    v23 = (unsigned int)v9 <= v68 + 14;
LABEL_21:
    if ( v23 )
      goto LABEL_80;
    v24 = L" xsi:nil=\"1\"/>";
    v25 = v9 - (*a3 - v7);
LABEL_106:
    CDRMSoapRequest::CatRequest(v15, a3, v25, v24);
    goto LABEL_80;
  }
  if ( *(_DWORD *)a2 != 1 )
  {
    if ( *(_DWORD *)a2 != 4 )
    {
      if ( *(_DWORD *)a2 == 5 )
      {
        v15 = (CDRMSoapRequest *)*((_QWORD *)a2 + 1);
        v12 = -1;
        v44 = -1;
        do
          ++v44;
        while ( *((_WORD *)v15 + v44) );
        *a5 += v44 + 2;
        if ( a4 > *a5 )
        {
          CDRMSoapRequest::CatRequest(v15, a3, a4 - (*a3 - v7), L"<");
          CDRMSoapRequest::CatRequest(v45, a3, v9 - (*a3 - v7), *((const unsigned __int16 **)a2 + 1));
          CDRMSoapRequest::CatRequest(v46, a3, v9 - (*a3 - v7), ">");
          v10 = v75;
        }
        v47 = 0;
        if ( !*((_DWORD *)a2 + 9) )
        {
          do
LABEL_60:
            ++v12;
          while ( *(_WORD *)(*((_QWORD *)a2 + 1) + 2 * v12) );
          goto LABEL_103;
        }
        while ( 1 )
        {
          v73 = CDRMSoapRequest::AddParameter(
                  v10,
                  *(struct CDRMSoapRequestParameter **)(*((_QWORD *)a2 + 3) + 8LL * v47),
                  a3,
                  v9,
                  a5);
          if ( v73 < 0 )
            goto LABEL_80;
          v10 = v75;
          if ( ++v47 >= *((_DWORD *)a2 + 9) )
            goto LABEL_60;
        }
      }
      if ( *(_DWORD *)a2 == 6 )
      {
        v48 = (CDRMSoapRequest *)*((_QWORD *)a2 + 1);
        v49 = -1;
        v50 = -1;
        do
          ++v50;
        while ( *((_WORD *)v48 + v50) );
        *a5 += v50 + 1;
        if ( a4 > *a5 )
        {
          CDRMSoapRequest::CatRequest(v48, a3, a4 - (*a3 - v7), L"<");
          CDRMSoapRequest::CatRequest(v51, a3, v9 - (*a3 - v7), *((const unsigned __int16 **)a2 + 1));
        }
        do
          ++v49;
        while ( *(_WORD *)(*((_QWORD *)a2 + 2) + 2 * v49) );
        *a5 += v49 + 10;
        if ( (unsigned int)v9 > *a5 )
        {
          v52 = v9;
          CDRMSoapRequest::CatRequest(v48, a3, v9 - (*a3 - v7), L" href=\"");
          CDRMSoapRequest::CatRequest(v53, a3, v9 - (*a3 - v7), *((const unsigned __int16 **)a2 + 2));
          v24 = L"\"/>";
LABEL_105:
          v25 = v52 - (*a3 - v7);
          goto LABEL_106;
        }
        goto LABEL_80;
      }
      if ( *(_DWORD *)a2 != 2 )
        goto LABEL_80;
      v54 = (CDRMSoapRequest *)*((_QWORD *)a2 + 1);
      v55 = -1;
      v56 = -1;
      do
        ++v56;
      while ( *((_WORD *)v54 + v56) );
      *a5 += v56 + 1;
      if ( a4 > *a5 )
      {
        CDRMSoapRequest::CatRequest(v54, a3, a4 - (*a3 - v7), L"<");
        CDRMSoapRequest::CatRequest(v57, a3, v9 - (*a3 - v7), *((const unsigned __int16 **)a2 + 1));
      }
      v58 = (const wchar_t *)*((_QWORD *)a2 + 2);
      v19 = 0;
      if ( !v58 )
      {
        *a5 += 14;
        if ( (unsigned int)v9 > *a5 )
          CDRMSoapRequest::CatRequest(v54, a3, v9 - (*a3 - v7), L" xsi:nil=\"1\"/>");
        goto LABEL_79;
      }
      if ( !wcsncmp_0(*((const wchar_t **)a2 + 2), L"<?xml", 5u) )
      {
        v60 = wcschr(v58, 0x3Eu);
        if ( !v60 )
        {
          v73 = -2147024809;
          goto LABEL_79;
        }
        v58 = v60 + 1;
      }
      v62 = -1;
      do
        ++v62;
      while ( v58[v62] );
      *a5 += v62 + 1;
      if ( (unsigned int)v9 > *a5 )
      {
        CDRMSoapRequest::CatRequest(v59, a3, v9 - (*a3 - v7), ">");
        CDRMSoapRequest::CatRequest(v63, a3, v9 - (*a3 - v7), v58);
      }
      do
        ++v55;
      while ( *(_WORD *)(*((_QWORD *)a2 + 1) + 2 * v55) );
      *a5 += v55 + 3;
      if ( (unsigned int)v9 > *a5 )
      {
        v29 = v9;
        CDRMSoapRequest::CatRequest(v59, a3, v9 - (*a3 - v7), L"</");
        v43 = v9;
        goto LABEL_89;
      }
LABEL_90:
      v5 = 0;
      goto LABEL_80;
    }
    v73 = StringCchPrintfW(v76, 6u, L"%d", *((unsigned int *)a2 + 8));
    if ( v73 < 0 )
      goto LABEL_80;
    v26 = (CDRMSoapRequest *)*((_QWORD *)a2 + 1);
    v27 = -1;
    v28 = -1;
    do
      ++v28;
    while ( *((_WORD *)v26 + v28) );
    v29 = v9;
    *a5 += v28 + 1;
    if ( (unsigned int)v9 > *a5 )
    {
      CDRMSoapRequest::CatRequest(v26, a3, v9 - (*a3 - v7), L"<");
      CDRMSoapRequest::CatRequest(v30, a3, v9 - (*a3 - v7), *((const unsigned __int16 **)a2 + 1));
    }
    *a5 += 20;
    if ( (unsigned int)v9 > *a5 )
      CDRMSoapRequest::CatRequest(v26, a3, v9 - (*a3 - v7), L" soapenc:arrayType=\"");
    v31 = (char *)*((_QWORD *)a2 + 2);
    v32 = (unsigned __int16 *)v31;
    do
    {
      v33 = *(unsigned __int16 *)((char *)v32 + (char *)L"string" - v31);
      v34 = *v32 - v33;
      if ( v34 )
        break;
      ++v32;
    }
    while ( v33 );
    v35 = (CDRMSoapRequest *)*a5;
    if ( v34 )
    {
      v37 = -1;
      do
        ++v37;
      while ( *(_WORD *)&v31[2 * v37] );
      v38 = (_DWORD)v35 + v37;
      *a5 = v38;
      if ( (unsigned int)v9 > v38 )
      {
        v36 = (const unsigned __int16 *)*((_QWORD *)a2 + 2);
        goto LABEL_41;
      }
    }
    else
    {
      *a5 = (_DWORD)v35 + 10;
      if ( (unsigned int)v9 > (int)v35 + 10 )
      {
        v36 = L"xsd:string";
LABEL_41:
        CDRMSoapRequest::CatRequest(v35, a3, v9 - (*a3 - v7), v36);
      }
    }
    v39 = -1;
    do
      ++v39;
    while ( v76[v39] );
    *a5 += v39 + 4;
    if ( (unsigned int)v9 > *a5 )
    {
      CDRMSoapRequest::CatRequest((CDRMSoapRequest *)v76, a3, v9 - (*a3 - v7), L"[");
      CDRMSoapRequest::CatRequest(v40, a3, v9 - (*a3 - v7), v76);
      CDRMSoapRequest::CatRequest(v41, a3, v9 - (*a3 - v7), L"]\">");
    }
    if ( *((_DWORD *)a2 + 8) )
    {
      while ( 1 )
      {
        v73 = CDRMSoapRequest::AddParameter(
                v75,
                *(struct CDRMSoapRequestParameter **)(*((_QWORD *)a2 + 3) + 8LL * (unsigned int)v5),
                a3,
                v9,
                a5);
        if ( v73 < 0 )
          break;
        LODWORD(v5) = (_DWORD)v5 + 1;
        if ( (unsigned int)v5 >= *((_DWORD *)a2 + 8) )
          goto LABEL_49;
      }
      v5 = 0;
      goto LABEL_80;
    }
    do
LABEL_49:
      ++v27;
    while ( *(_WORD *)(*((_QWORD *)a2 + 1) + 2 * v27) );
    *a5 += v27 + 3;
    if ( (unsigned int)v9 > *a5 )
    {
      CDRMSoapRequest::CatRequest(0, a3, v9 - (*a3 - v7), L"</");
      v43 = v9;
LABEL_89:
      CDRMSoapRequest::CatRequest(v42, a3, v43 - (*a3 - v7), *((const unsigned __int16 **)a2 + 1));
      CDRMSoapRequest::CatRequest(v64, a3, v29 - (*a3 - v7), ">");
      goto LABEL_90;
    }
    goto LABEL_90;
  }
  v11 = (CDRMSoapRequest *)*((_QWORD *)a2 + 1);
  v12 = -1;
  v13 = -1;
  do
    ++v13;
  while ( *((_WORD *)v11 + v13) );
  *a5 += v13 + 1;
  if ( a4 > *a5 )
  {
    CDRMSoapRequest::CatRequest(v11, a3, a4 - (*a3 - v7), L"<");
    CDRMSoapRequest::CatRequest(v14, a3, v9 - (*a3 - v7), *((const unsigned __int16 **)a2 + 1));
  }
  v15 = (CDRMSoapRequest *)*((_QWORD *)a2 + 2);
  if ( !v15 )
  {
    *a5 += 14;
    v23 = (unsigned int)v9 <= *a5;
    goto LABEL_21;
  }
  v73 = EscapeXML((unsigned __int16 *)v15, 0, &v74);
  if ( v73 >= 0 )
  {
    v16 = v74 + 1;
    v17 = (unsigned __int16 *)operator new[](saturated_mul(v16, 2u));
    v5 = v17;
    if ( !v17 )
    {
      v73 = -2147024882;
      goto LABEL_80;
    }
    v18 = 2 * v16;
    v19 = v17;
    memset_0(v17, 0, v18);
    v20 = EscapeXML(*((unsigned __int16 **)a2 + 2), v19, &v74);
    v15 = 0;
    v73 = v20;
    if ( v20 >= 0 )
    {
      v21 = -1;
      do
        ++v21;
      while ( v19[v21] );
      *a5 += v21 + 1;
      if ( (unsigned int)v9 <= *a5 )
      {
        v5 = v19;
      }
      else
      {
        CDRMSoapRequest::CatRequest(0, a3, v9 - (*a3 - v7), ">");
        CDRMSoapRequest::CatRequest(v22, a3, v9 - (*a3 - v7), v5);
        v15 = 0;
      }
      do
        ++v12;
      while ( *(_WORD *)(*((_QWORD *)a2 + 1) + 2 * v12) );
LABEL_103:
      *a5 += v12 + 3;
      if ( (unsigned int)v9 <= *a5 )
        goto LABEL_80;
      v52 = v9;
      CDRMSoapRequest::CatRequest(v15, a3, v9 - (*a3 - v7), L"</");
      CDRMSoapRequest::CatRequest(v72, a3, v9 - (*a3 - v7), *((const unsigned __int16 **)a2 + 1));
      v24 = ">";
      goto LABEL_105;
    }
LABEL_79:
    v5 = v19;
  }
LABEL_80:
  operator delete(v5);
  return (unsigned int)v73;
}

```

## disassembly

```asm
0x180047d90  push    rbx
0x180047d92  push    rbp
0x180047d93  push    rsi
0x180047d94  push    rdi
0x180047d95  push    r12
0x180047d97  push    r13
0x180047d99  push    r14
0x180047d9b  push    r15
0x180047d9d  sub     rsp, 68h
0x180047da1  mov     rax, cs:__security_cookie
0x180047da8  xor     rax, rsp
0x180047dab  mov     [rsp+0A8h+var_50], rax
0x180047db0  mov     rdi, [rsp+0A8h+arg_20]
0x180047db8  xor     r13d, r13d
0x180047dbb  mov     rsi, r8
0x180047dbe  mov     r12, [r8]
0x180047dc1  mov     r15, rdx
0x180047dc4  mov     r14d, r9d
0x180047dc7  mov     r10, rcx
0x180047dca  mov     [rsp+0A8h+var_68], rcx
0x180047dcf  mov     [rsp+0A8h+var_70], r13d
0x180047dd4  mov     [rsp+0A8h+var_78], r13
0x180047dd9  mov     [rsp+0A8h+var_6C], r13d
0x180047dde  cmp     [rdx], r13d
0x180047de1  jz      loc_1800484ED
0x180047de7  cmp     dword ptr [rdx], 3
0x180047dea  jz      loc_1800484ED
0x180047df0  cmp     dword ptr [rdx], 1
0x180047df3  jnz     loc_180047F67
0x180047df9  mov     rcx, [rdx+8]; this
0x180047dfd  or      rbp, 0FFFFFFFFFFFFFFFFh
0x180047e01  mov     rax, rbp
0x180047e04  inc     rax
0x180047e07  cmp     [rcx+rax*2], r13w
0x180047e0c  jnz     short loc_180047E04
0x180047e0e  inc     eax
0x180047e10  add     [rdi], eax
0x180047e12  cmp     r14d, [rdi]
0x180047e15  jbe     short loc_180047E53
0x180047e17  mov     rax, [r8]
0x180047e1a  lea     r9, ?g_wszSOAP_OPEN_TAG@@3QBGB; "<"
0x180047e21  sub     rax, r12
0x180047e24  mov     r8, r14
0x180047e27  sar     rax, 1
0x180047e2a  mov     rdx, rsi; unsigned __int16 **
0x180047e2d  sub     r8, rax; unsigned __int64
0x180047e30  mov     rbx, r14
0x180047e33  call    ?CatRequest@CDRMSoapRequest@@IEAAXPEAPEAG_KPEBG@Z; CDRMSoapRequest::CatRequest(ushort * *,unsigned __int64,ushort const *)
0x180047e38  mov     rax, [rsi]
0x180047e3b  mov     rdx, rsi; unsigned __int16 **
0x180047e3e  mov     r9, [r15+8]; unsigned __int16 *
0x180047e42  sub     rax, r12
0x180047e45  sar     rax, 1
0x180047e48  sub     rbx, rax
0x180047e4b  mov     r8, rbx; unsigned __int64
0x180047e4e  call    ?CatRequest@CDRMSoapRequest@@IEAAXPEAPEAG_KPEBG@Z; CDRMSoapRequest::CatRequest(ushort * *,unsigned __int64,ushort const *)
0x180047e53  mov     rcx, [r15+10h]; unsigned __int16 *
0x180047e57  test    rcx, rcx
0x180047e5a  jz      loc_180047F40
0x180047e60  lea     r8, [rsp+0A8h+var_6C]; unsigned int *
0x180047e65  xor     edx, edx; unsigned __int16 *
0x180047e67  call    ?EscapeXML@@YAJPEAG0PEAI@Z; EscapeXML(ushort *,ushort *,uint *)
0x180047e6c  mov     [rsp+0A8h+var_70], eax
0x180047e70  test    eax, eax
0x180047e72  js      loc_1800483C1
0x180047e78  mov     ebx, [rsp+0A8h+var_6C]
0x180047e7c  mov     eax, 2
0x180047e81  inc     ebx
0x180047e83  mul     rbx
0x180047e86  cmovb   rax, rbp
0x180047e8a  mov     rcx, rax; unsigned __int64
0x180047e8d  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180047e92  mov     r13, rax
0x180047e95  test    rax, rax
0x180047e98  jnz     short loc_180047EA7
0x180047e9a  mov     [rsp+0A8h+var_70], 8007000Eh
0x180047ea2  jmp     loc_1800483C1
0x180047ea7  lea     r8, [rbx+rbx]; Size
0x180047eab  xor     edx, edx; Val
0x180047ead  mov     rcx, rax; void *
0x180047eb0  mov     rbx, rax
0x180047eb3  call    memset_0
0x180047eb8  mov     rcx, [r15+10h]; unsigned __int16 *
0x180047ebc  lea     r8, [rsp+0A8h+var_6C]; unsigned int *
0x180047ec1  mov     rdx, rbx; unsigned __int16 *
0x180047ec4  call    ?EscapeXML@@YAJPEAG0PEAI@Z; EscapeXML(ushort *,ushort *,uint *)
0x180047ec9  xor     ecx, ecx; this
0x180047ecb  mov     [rsp+0A8h+var_70], eax
0x180047ecf  test    eax, eax
0x180047ed1  js      loc_1800483BE
0x180047ed7  mov     rax, rbp
0x180047eda  inc     rax
0x180047edd  cmp     [rbx+rax*2], cx
0x180047ee1  jnz     short loc_180047EDA
0x180047ee3  inc     eax
0x180047ee5  add     [rdi], eax
0x180047ee7  cmp     r14d, [rdi]
0x180047eea  jbe     short loc_180047F2B
0x180047eec  mov     rax, [rsi]
0x180047eef  lea     r9, ?g_wszSOAP_CLOSE_TAG@@3QBGB; ">"
0x180047ef6  sub     rax, r12
0x180047ef9  mov     r8, r14
0x180047efc  sar     rax, 1
0x180047eff  mov     rdx, rsi; unsigned __int16 **
0x180047f02  sub     r8, rax; unsigned __int64
0x180047f05  mov     rbx, r14
0x180047f08  call    ?CatRequest@CDRMSoapRequest@@IEAAXPEAPEAG_KPEBG@Z; CDRMSoapRequest::CatRequest(ushort * *,unsigned __int64,ushort const *)
0x180047f0d  mov     rax, [rsi]
0x180047f10  mov     r9, r13; unsigned __int16 *
0x180047f13  sub     rax, r12
0x180047f16  mov     rdx, rsi; unsigned __int16 **
0x180047f19  sar     rax, 1
0x180047f1c  sub     rbx, rax
0x180047f1f  mov     r8, rbx; unsigned __int64
0x180047f22  call    ?CatRequest@CDRMSoapRequest@@IEAAXPEAPEAG_KPEBG@Z; CDRMSoapRequest::CatRequest(ushort * *,unsigned __int64,ushort const *)
0x180047f27  xor     ecx, ecx
0x180047f29  jmp     short loc_180047F2E
0x180047f2b  mov     r13, rbx
0x180047f2e  mov     rax, [r15+8]
0x180047f32  inc     rbp
0x180047f35  cmp     [rax+rbp*2], cx
0x180047f39  jnz     short loc_180047F32
0x180047f3b  jmp     loc_1800485AC
0x180047f40  add     dword ptr [rdi], 0Eh
0x180047f43  cmp     r14d, [rdi]
0x180047f46  jbe     loc_1800483C1
0x180047f4c  mov     rax, [rsi]
0x180047f4f  lea     r9, ?g_wszSOAP_NILPARAM@@3QBGB; " xsi:nil=\"1\"/>"
0x180047f56  sub     rax, r12
0x180047f59  mov     r8, r14
0x180047f5c  sar     rax, 1
0x180047f5f  sub     r8, rax
0x180047f62  jmp     loc_18004860C
0x180047f67  cmp     dword ptr [rdx], 4
0x180047f6a  jnz     loc_180048179
0x180047f70  mov     r9d, [rdx+20h]
0x180047f74  lea     r8, aD; "%d"
0x180047f7b  mov     edx, 6; unsigned __int64
0x180047f80  lea     rcx, [rsp+0A8h+var_60]; unsigned __int16 *
0x180047f85  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180047f8a  mov     [rsp+0A8h+var_70], eax
0x180047f8e  test    eax, eax
0x180047f90  js      loc_1800483C1
0x180047f96  mov     rcx, [r15+8]; this
0x180047f9a  or      rbp, 0FFFFFFFFFFFFFFFFh
0x180047f9e  mov     rax, rbp
0x180047fa1  inc     rax
0x180047fa4  cmp     [rcx+rax*2], r13w
0x180047fa9  jnz     short loc_180047FA1
0x180047fab  inc     eax
0x180047fad  mov     rbx, r14
0x180047fb0  add     [rdi], eax
0x180047fb2  cmp     r14d, [rdi]
0x180047fb5  jbe     short loc_180047FF0
0x180047fb7  mov     rax, [rsi]
0x180047fba  lea     r9, ?g_wszSOAP_OPEN_TAG@@3QBGB; "<"
0x180047fc1  sub     rax, r12
0x180047fc4  mov     r8, r14
0x180047fc7  sar     rax, 1
0x180047fca  mov     rdx, rsi; unsigned __int16 **
0x180047fcd  sub     r8, rax; unsigned __int64
0x180047fd0  call    ?CatRequest@CDRMSoapRequest@@IEAAXPEAPEAG_KPEBG@Z; CDRMSoapRequest::CatRequest(ushort * *,unsigned __int64,ushort const *)
0x180047fd5  mov     rax, [rsi]
0x180047fd8  mov     r8, r14
0x180047fdb  mov     r9, [r15+8]; unsigned __int16 *
0x180047fdf  sub     rax, r12
0x180047fe2  sar     rax, 1
0x180047fe5  mov     rdx, rsi; unsigned __int16 **
0x180047fe8  sub     r8, rax; unsigned __int64
0x180047feb  call    ?CatRequest@CDRMSoapRequest@@IEAAXPEAPEAG_KPEBG@Z; CDRMSoapRequest::CatRequest(ushort * *,unsigned __int64,ushort const *)
0x180047ff0  add     dword ptr [rdi], 14h
0x180047ff3  cmp     r14d, [rdi]
0x180047ff6  jbe     short loc_180048016
0x180047ff8  mov     rax, [rsi]
0x180047ffb  lea     r9, ?g_wszSOAP_ARRAY_TYPE@@3QBGB; " soapenc:arrayType=\""
0x180048002  sub     rax, r12
0x180048005  mov     r8, rbx
0x180048008  sar     rax, 1
0x18004800b  mov     rdx, rsi; unsigned __int16 **
0x18004800e  sub     r8, rax; unsigned __int64
0x180048011  call    ?CatRequest@CDRMSoapRequest@@IEAAXPEAPEAG_KPEBG@Z; CDRMSoapRequest::CatRequest(ushort * *,unsigned __int64,ushort const *)
0x180048016  mov     r9, [r15+10h]
0x18004801a  lea     r8, ?g_wszSOAP_STRING_TAG@@3QBGB; "string"
0x180048021  mov     rax, r9
0x180048024  sub     r8, r9
0x180048027  movzx   edx, word ptr [rax]
0x18004802a  movzx   ecx, word ptr [rax+r8]
0x18004802f  sub     edx, ecx
0x180048031  jnz     short loc_18004803B
0x180048033  add     rax, 2
0x180048037  test    ecx, ecx
0x180048039  jnz     short loc_180048027
0x18004803b  mov     ecx, [rdi]; this
0x18004803d  test    edx, edx
0x18004803f  jnz     short loc_180048054
0x180048041  lea     eax, [rcx+0Ah]
0x180048044  mov     [rdi], eax
0x180048046  cmp     r14d, eax
0x180048049  jbe     short loc_180048085
0x18004804b  lea     r9, ?g_wszSOAP_STRING_TYPE@@3QBGB; "xsd:string"
0x180048052  jmp     short loc_18004806E
0x180048054  mov     rax, rbp
0x180048057  inc     rax
0x18004805a  cmp     [r9+rax*2], r13w
0x18004805f  jnz     short loc_180048057
0x180048061  add     eax, ecx
0x180048063  mov     [rdi], eax
0x180048065  cmp     r14d, eax
0x180048068  jbe     short loc_180048085
0x18004806a  mov     r9, [r15+10h]; unsigned __int16 *
0x18004806e  mov     rax, [rsi]
0x180048071  mov     r8, rbx
0x180048074  sub     rax, r12
0x180048077  mov     rdx, rsi; unsigned __int16 **
0x18004807a  sar     rax, 1
0x18004807d  sub     r8, rax; unsigned __int64
0x180048080  call    ?CatRequest@CDRMSoapRequest@@IEAAXPEAPEAG_KPEBG@Z; CDRMSoapRequest::CatRequest(ushort * *,unsigned __int64,ushort const *)
0x180048085  lea     rcx, [rsp+0A8h+var_60]; this
0x18004808a  mov     rax, rbp
0x18004808d  inc     rax
0x180048090  cmp     [rcx+rax*2], r13w
0x180048095  jnz     short loc_18004808D
0x180048097  add     eax, 4
0x18004809a  add     [rdi], eax
0x18004809c  cmp     r14d, [rdi]
0x18004809f  jbe     short loc_1800480F9
0x1800480a1  mov     rax, [rsi]
0x1800480a4  lea     r9, ?g_wszSOAP_OPEN_ARRAYSIZE@@3QBGB; "["
0x1800480ab  sub     rax, r12
0x1800480ae  mov     r8, rbx
0x1800480b1  sar     rax, 1
0x1800480b4  mov     rdx, rsi; unsigned __int16 **
0x1800480b7  sub     r8, rax; unsigned __int64
0x1800480ba  call    ?CatRequest@CDRMSoapRequest@@IEAAXPEAPEAG_KPEBG@Z; CDRMSoapRequest::CatRequest(ushort * *,unsigned __int64,ushort const *)
0x1800480bf  mov     rax, [rsi]
0x1800480c2  lea     r9, [rsp+0A8h+var_60]; unsigned __int16 *
0x1800480c7  sub     rax, r12
0x1800480ca  mov     r8, rbx
0x1800480cd  sar     rax, 1
0x1800480d0  mov     rdx, rsi; unsigned __int16 **
0x1800480d3  sub     r8, rax; unsigned __int64
0x1800480d6  call    ?CatRequest@CDRMSoapRequest@@IEAAXPEAPEAG_KPEBG@Z; CDRMSoapRequest::CatRequest(ushort * *,unsigned __int64,ushort const *)
0x1800480db  mov     rax, [rsi]
0x1800480de  lea     r9, ?g_wszSOAP_CLOSE_ARRAYSIZE@@3QBGB; "]\">"
0x1800480e5  sub     rax, r12
0x1800480e8  mov     r8, rbx
0x1800480eb  sar     rax, 1
0x1800480ee  mov     rdx, rsi; unsigned __int16 **
0x1800480f1  sub     r8, rax; unsigned __int64
0x1800480f4  call    ?CatRequest@CDRMSoapRequest@@IEAAXPEAPEAG_KPEBG@Z; CDRMSoapRequest::CatRequest(ushort * *,unsigned __int64,ushort const *)
0x1800480f9  xor     ecx, ecx
0x1800480fb  cmp     [r15+20h], ecx
0x1800480ff  jbe     short loc_180048138
0x180048101  mov     rdx, [r15+18h]
0x180048105  mov     r9d, r14d; unsigned int
0x180048108  mov     rcx, [rsp+0A8h+var_68]; this
0x18004810d  mov     r8, rsi; unsigned __int16 **
0x180048110  mov     eax, r13d
0x180048113  mov     [rsp+0A8h+var_88], rdi; unsigned int *
0x180048118  mov     rdx, [rdx+rax*8]; struct CDRMSoapRequestParameter *
0x18004811c  call    ?AddParameter@CDRMSoapRequest@@IEAAJPEAVCDRMSoapRequestParameter@@PEAPEAGIPEAI@Z; CDRMSoapRequest::AddParameter(CDRMSoapRequestParameter *,ushort * *,uint,uint *)
0x180048121  xor     ecx, ecx; this
0x180048123  mov     [rsp+0A8h+var_70], eax
0x180048127  test    eax, eax
0x180048129  js      loc_180048626
0x18004812f  inc     r13d
0x180048132  cmp     r13d, [r15+20h]
0x180048136  jb      short loc_180048101
0x180048138  mov     rax, [r15+8]
0x18004813c  inc     rbp
0x18004813f  cmp     [rax+rbp*2], cx
0x180048143  jnz     short loc_18004813C
0x180048145  lea     eax, [rbp+3]
0x180048148  add     [rdi], eax
0x18004814a  cmp     r14d, [rdi]
0x18004814d  jbe     loc_1800484B4
0x180048153  mov     rax, [rsi]
0x180048156  lea     r9, ?g_wszSOAP_OPEN_END_TAG@@3QBGB; "</"
0x18004815d  sub     rax, r12
0x180048160  mov     r8, rbx
0x180048163  sar     rax, 1
0x180048166  mov     rdx, rsi; unsigned __int16 **
0x180048169  sub     r8, rax; unsigned __int64
0x18004816c  call    ?CatRequest@CDRMSoapRequest@@IEAAXPEAPEAG_KPEBG@Z; CDRMSoapRequest::CatRequest(ushort * *,unsigned __int64,ushort const *)
0x180048171  mov     r8, rbx
0x180048174  jmp     loc_18004847E
0x180048179  cmp     dword ptr [rdx], 5
0x18004817c  jnz     loc_180048252
0x180048182  mov     rcx, [rdx+8]; this
0x180048186  or      rbp, 0FFFFFFFFFFFFFFFFh
0x18004818a  mov     rax, rbp
0x18004818d  inc     rax
0x180048190  cmp     [rcx+rax*2], r13w
0x180048195  jnz     short loc_18004818D
0x180048197  add     eax, 2
0x18004819a  add     [rdi], eax
0x18004819c  cmp     r14d, [rdi]
0x18004819f  jbe     short loc_180048200
0x1800481a1  mov     rax, [r8]
0x1800481a4  lea     r9, ?g_wszSOAP_OPEN_TAG@@3QBGB; "<"
  ... truncated ...
```
