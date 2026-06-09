# CDRMSoapRequest::PutResponse(ushort const *,bool)

- ea: `0x18004b2c4`
- end: `0x18004ba4f`
- name: `?PutResponse@CDRMSoapRequest@@QEAAJPEBG_N@Z`
- size: `1931`
- prototype: `__int64 __fastcall(CDRMSoapRequest *__hidden this, const unsigned __int16 *, bool)`
- caller_count: `1`
- callee_count: `15`
- tags: `file_ops, registry_config`

## callers

- `0x180049250`

## callees

- `0x180001244`
- `0x180001284`
- `0x180001290`
- `0x18000420c`
- `0x1800046c8`
- `0x18003b45c`
- `0x180040940`
- `0x180041048`
- `0x1800410a0`
- `0x180041678`
- `0x1800419d8`
- `0x180041afc`
- `0x180048958`
- `0x180049508`
- `0x18004b2c4`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18004b6fe`
- `msvcrt!_wcsicmp` at `0x18004b718`
- `msvcrt!_wcsicmp` at `0x18004b6fe`
- `msvcrt!_wcsicmp` at `0x18004b718`

## string_xrefs

- `0x18004b72d`: `xmlns`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CDRMSoapRequest::PutResponse(
        CDRMSoapRequest *this,
        const unsigned __int16 *a2,
        __int64 a3,
        __int64 a4)
{
  char v4; // r12
  unsigned __int16 *v7; // rdi
  int Child; // ebx
  int XML; // eax
  unsigned __int16 *v10; // rax
  int v11; // r8d
  int v12; // edx
  unsigned __int16 *v13; // rax
  int v14; // r8d
  int v15; // edx
  unsigned __int16 *v16; // rax
  int v17; // edx
  int v18; // r8d
  unsigned __int16 *v19; // rax
  int v20; // ecx
  int v21; // edx
  int v22; // esi
  _DWORD *v23; // r15
  unsigned __int64 v24; // rcx
  _QWORD *v25; // r12
  __int64 v26; // r8
  _DWORD *v27; // rbx
  _QWORD *v28; // rax
  _QWORD *v29; // rsi
  __int64 v30; // rax
  __int64 v31; // rcx
  unsigned __int16 *v32; // rax
  int v33; // ecx
  int v34; // edx
  unsigned __int16 *v35; // rax
  int v36; // ecx
  int v37; // edx
  char v38; // si
  const wchar_t **v39; // r15
  int v40; // r12d
  unsigned int *v41; // r15
  unsigned int v42; // edx
  _QWORD *v43; // rsi
  unsigned int v44; // r8d
  _DWORD *v45; // rbx
  _QWORD *v46; // rax
  _QWORD *v47; // rsi
  unsigned __int16 *v48; // rax
  int v49; // r8d
  int v50; // edx
  unsigned __int16 *v51; // rax
  int v52; // r8d
  int v53; // ecx
  void *Block[2]; // [rsp+20h] [rbp-30h] BYREF
  __int64 v56; // [rsp+30h] [rbp-20h] BYREF
  int v57; // [rsp+38h] [rbp-18h]
  __int64 v58; // [rsp+40h] [rbp-10h]
  __int64 v59; // [rsp+48h] [rbp-8h]
  char v60; // [rsp+90h] [rbp+40h]
  _QWORD *v61; // [rsp+98h] [rbp+48h] BYREF

  v60 = a3;
  Block[1] = (void *)-2LL;
  v4 = a3;
  v56 = 0;
  v57 = 0;
  v58 = 0;
  LOBYTE(v61) = 0;
  v7 = 0;
  Block[0] = 0;
  if ( !(unsigned __int8)DRMIsValidStringT<unsigned short>(a2, 0, a3, a4) )
  {
    Child = -2147024809;
    goto LABEL_109;
  }
  CDRMSoapRequest::CleanRequest(this);
  XML = CDRMXML::LoadXML((CDRMXML *)&v56, a2);
  Child = XML;
  if ( XML == -2147024809 )
  {
    _RTLTRACE("[msdrm]:Response from the server - %S", a2);
LABEL_108:
    Child = -2147168304;
    goto LABEL_109;
  }
  if ( XML < 0 )
    goto LABEL_105;
  v59 = v58;
  if ( !v58 )
    goto LABEL_108;
  if ( !*(_DWORD *)(v58 + 4) )
  {
    Child = CDRMXML::FirstChild((CDRMXML *)&v56, (bool *)&v61);
    if ( Child < 0 )
      goto LABEL_105;
    if ( !(_BYTE)v61 )
      goto LABEL_108;
  }
  Child = CDRMXML::GetNodeValue((CDRMXML *)&v56, (unsigned __int16 **)Block);
  if ( Child < 0 )
    goto LABEL_104;
  v7 = (unsigned __int16 *)Block[0];
  if ( !Block[0] )
    goto LABEL_108;
  v10 = (unsigned __int16 *)Block[0];
  do
  {
    v11 = *(unsigned __int16 *)((char *)v10 + (char *)L"Envelope" - (char *)Block[0]);
    v12 = *v10 - v11;
    if ( v12 )
      break;
    ++v10;
  }
  while ( v11 );
  if ( v12 )
  {
    v13 = (unsigned __int16 *)Block[0];
    do
    {
      v14 = *(unsigned __int16 *)((char *)v13 + (char *)L"soap:Envelope" - (char *)Block[0]);
      v15 = *v13 - v14;
      if ( v15 )
        break;
      ++v13;
    }
    while ( v14 );
    if ( v15 )
      goto LABEL_108;
  }
  Child = CDRMXML::FirstChild((CDRMXML *)&v56, (bool *)&v61);
  if ( Child < 0 )
    goto LABEL_105;
  if ( !(_BYTE)v61 )
    goto LABEL_108;
  operator delete(v7);
  Block[0] = 0;
  Child = CDRMXML::GetNodeValue((CDRMXML *)&v56, (unsigned __int16 **)Block);
  if ( Child < 0 )
    goto LABEL_104;
  v7 = (unsigned __int16 *)Block[0];
  if ( !Block[0] )
    goto LABEL_108;
  v16 = (unsigned __int16 *)Block[0];
  do
  {
    v17 = *(unsigned __int16 *)((char *)v16 + (char *)L"Header" - (char *)Block[0]);
    v18 = *v16 - v17;
    if ( v18 )
      break;
    ++v16;
  }
  while ( v17 );
  if ( !v18 )
    goto LABEL_32;
  v19 = (unsigned __int16 *)Block[0];
  do
  {
    v20 = *(unsigned __int16 *)((char *)v19 + (char *)L"soap:Header" - (char *)Block[0]);
    v21 = *v19 - v20;
    if ( v21 )
      break;
    ++v19;
  }
  while ( v20 );
  if ( !v21 )
  {
LABEL_32:
    v22 = *(_DWORD *)(v59 + 64);
    v23 = (_DWORD *)((char *)this + 232);
    v24 = (unsigned int)(v22 + *((_DWORD *)this + 58));
    if ( *((_DWORD *)this + 59) <= (unsigned int)v24 )
    {
      v25 = operator new[](saturated_mul(v24, 8u));
      if ( !v25 )
      {
LABEL_34:
        Child = -2147024882;
        goto LABEL_109;
      }
      v26 = 0;
      if ( *v23 )
      {
        do
        {
          v25[v26] = *(_QWORD *)(*((_QWORD *)this + 28) + 8 * v26);
          v26 = (unsigned int)(v26 + 1);
        }
        while ( (unsigned int)v26 < *v23 );
        v27 = (_DWORD *)((char *)this + 232);
      }
      else
      {
        v27 = (_DWORD *)((char *)this + 232);
      }
      operator delete(*((void **)this + 30));
      *((_QWORD *)this + 30) = 0;
      *((_QWORD *)this + 28) = v25;
      *((_DWORD *)this + 59) = v22 + *v27;
      v4 = v60;
    }
    Child = CDRMXML::FirstChild((CDRMXML *)&v56, (bool *)&v61);
    if ( Child < 0 )
      goto LABEL_105;
    if ( (_BYTE)v61 )
    {
      while ( 1 )
      {
        v28 = operator new(0x38u);
        v29 = v28;
        v61 = v28;
        if ( !v28 )
          goto LABEL_34;
        v28[1] = 0;
        v28[2] = 0;
        v28[3] = 0;
        v28[4] = 0;
        v28[5] = 0;
        v28[6] = 0;
        Child = CDRMSoapRequest::ExtractParameter(this, (struct CDRMXML *)&v56, (unsigned __int16 **)v28);
        if ( Child < 0 )
          goto LABEL_105;
        *(_QWORD *)(*((_QWORD *)this + 28) + 8LL * *((unsigned int *)this + 58)) = v29;
        ++*v23;
        v30 = v59;
        if ( !v59 || !*(_QWORD *)(v59 + 40) )
          goto LABEL_48;
        v59 = *(_QWORD *)(v59 + 40);
        LOBYTE(v61) = 1;
      }
    }
    v30 = v59;
LABEL_48:
    if ( !v30 )
      goto LABEL_108;
    v31 = *(_QWORD *)(v30 + 32);
    if ( !v31 )
      goto LABEL_108;
    v59 = *(_QWORD *)(v30 + 32);
    if ( !*(_QWORD *)(v31 + 40) )
      goto LABEL_108;
    v59 = *(_QWORD *)(v31 + 40);
    LOBYTE(v61) = 1;
    operator delete(v7);
    Block[0] = 0;
    Child = CDRMXML::GetNodeValue((CDRMXML *)&v56, (unsigned __int16 **)Block);
    if ( Child >= 0 )
    {
      v7 = (unsigned __int16 *)Block[0];
      goto LABEL_53;
    }
LABEL_104:
    v7 = (unsigned __int16 *)Block[0];
    goto LABEL_105;
  }
LABEL_53:
  if ( !v7 )
    goto LABEL_108;
  v32 = v7;
  do
  {
    v33 = *(unsigned __int16 *)((char *)v32 + (char *)L"Body" - (char *)v7);
    v34 = *v32 - v33;
    if ( v34 )
      break;
    ++v32;
  }
  while ( v33 );
  if ( v34 )
  {
    v35 = v7;
    do
    {
      v36 = *(unsigned __int16 *)((char *)v35 + (char *)L"soap:Body" - (char *)v7);
      v37 = *v35 - v36;
      if ( v37 )
        break;
      ++v35;
    }
    while ( v36 );
    if ( v37 )
      goto LABEL_108;
  }
  Child = CDRMXML::FirstChild((CDRMXML *)&v56, (bool *)&v61);
  if ( Child < 0 )
    goto LABEL_105;
  v38 = (char)v61;
  if ( !(_BYTE)v61 )
    goto LABEL_108;
  v39 = (const wchar_t **)((char *)this + 176);
  Child = CDRMXML::GetNodeValue((CDRMXML *)&v56, (unsigned __int16 **)this + 22);
  if ( Child < 0 )
    goto LABEL_105;
  Child = 0;
  if ( !_wcsicmp(*v39, L"Fault") || !_wcsicmp(*v39, L"soap:Fault") )
  {
    Child = CDRMXML::FirstChild((CDRMXML *)&v56, (bool *)&v61);
    if ( Child < 0 )
      goto LABEL_105;
    if ( !(_BYTE)v61 )
      goto LABEL_108;
    operator delete(v7);
    Block[0] = 0;
    Child = CDRMXML::GetNodeValue((CDRMXML *)&v56, (unsigned __int16 **)Block);
    if ( Child >= 0 )
    {
      v7 = (unsigned __int16 *)Block[0];
      v48 = (unsigned __int16 *)Block[0];
      do
      {
        v49 = *(unsigned __int16 *)((char *)v48 + (char *)L"faultcode" - (char *)Block[0]);
        v50 = *v48 - v49;
        if ( v50 )
          break;
        ++v48;
      }
      while ( v49 );
      if ( v50 )
        goto LABEL_108;
      Child = CDRMXML::GetXMLFragment((CDRMXML *)&v56, 0, (unsigned __int16 **)this + 26);
      if ( Child < 0 )
        goto LABEL_105;
      Child = UnescapeXML(*((unsigned __int16 **)this + 26));
      if ( Child < 0 )
        goto LABEL_105;
      if ( !v59 || !*(_QWORD *)(v59 + 40) )
        goto LABEL_108;
      v59 = *(_QWORD *)(v59 + 40);
      operator delete(v7);
      Block[0] = 0;
      Child = CDRMXML::GetNodeValue((CDRMXML *)&v56, (unsigned __int16 **)Block);
      if ( Child >= 0 )
      {
        v7 = (unsigned __int16 *)Block[0];
        v51 = (unsigned __int16 *)Block[0];
        do
        {
          v52 = *(unsigned __int16 *)((char *)v51 + (char *)L"faultstring" - (char *)Block[0]);
          v53 = *v51 - v52;
          if ( v53 )
            break;
          ++v51;
        }
        while ( v52 );
        if ( v53 )
          goto LABEL_108;
        Child = CDRMXML::GetXMLFragment((CDRMXML *)&v56, 0, (unsigned __int16 **)this + 27);
        if ( Child >= 0 )
        {
          Child = UnescapeXML(*((unsigned __int16 **)this + 27));
          if ( Child >= 0 )
          {
            Child = -2147168300;
            goto LABEL_109;
          }
        }
        goto LABEL_105;
      }
    }
    goto LABEL_104;
  }
  CDRMXML::GetAttribute((CDRMXML *)&v56, L"xmlns", (unsigned __int16 **)this + 23);
  if ( v4 )
  {
    Child = CDRMXML::FirstChild((CDRMXML *)&v56, (bool *)&v61);
    if ( Child < 0 )
      goto LABEL_105;
    v38 = (char)v61;
    Child = 0;
  }
  if ( !v38 )
    goto LABEL_109;
  v40 = *(_DWORD *)(v59 + 64);
  v41 = (unsigned int *)((char *)this + 248);
  v42 = v40 + *((_DWORD *)this + 62);
  if ( *((_DWORD *)this + 63) <= v42 )
  {
    v43 = operator new[](saturated_mul(v42, 8u));
    if ( !v43 )
      goto LABEL_34;
    v44 = 0;
    if ( *v41 )
    {
      do
      {
        v43[v44] = *(_QWORD *)(*((_QWORD *)this + 30) + 8LL * v44);
        ++v44;
      }
      while ( v44 < *v41 );
      v45 = (_DWORD *)((char *)this + 248);
    }
    else
    {
      v45 = (_DWORD *)((char *)this + 248);
    }
    operator delete(*((void **)this + 30));
    *((_QWORD *)this + 30) = 0;
    *((_QWORD *)this + 30) = v43;
    *((_DWORD *)this + 63) = v40 + *v45;
  }
  Child = CDRMXML::FirstChild((CDRMXML *)&v56, (bool *)&v61);
  if ( Child >= 0 )
  {
    Child = 0;
    if ( !(_BYTE)v61 )
      goto LABEL_109;
    while ( 1 )
    {
      v46 = operator new(0x38u);
      v47 = v46;
      v61 = v46;
      if ( !v46 )
        goto LABEL_34;
      v46[1] = 0;
      v46[2] = 0;
      v46[3] = 0;
      v46[4] = 0;
      v46[5] = 0;
      v46[6] = 0;
      Child = CDRMSoapRequest::ExtractParameter(this, (struct CDRMXML *)&v56, (unsigned __int16 **)v46);
      if ( Child < 0 )
        break;
      *(_QWORD *)(*((_QWORD *)this + 30) + 8LL * *((unsigned int *)this + 62)) = v47;
      ++*v41;
      Child = 0;
      if ( !v59 || !*(_QWORD *)(v59 + 40) )
        goto LABEL_109;
      v59 = *(_QWORD *)(v59 + 40);
    }
  }
LABEL_105:
  if ( Child != -2147168300 && Child != -2147024882 && Child != -2147024809 )
    goto LABEL_108;
LABEL_109:
  operator delete(v7);
  CDRMXML::~CDRMXML((CDRMXML *)&v56);
  return (unsigned int)Child;
}

```

## disassembly

```asm
0x18004b2c4  mov     rax, rsp
0x18004b2c7  mov     [rax+18h], r8b
0x18004b2cb  push    rbp
0x18004b2cc  push    rdi
0x18004b2cd  push    r12
0x18004b2cf  push    r14
0x18004b2d1  push    r15
0x18004b2d3  mov     rbp, rsp
0x18004b2d6  sub     rsp, 50h
0x18004b2da  mov     [rbp+var_28], 0FFFFFFFFFFFFFFFEh
0x18004b2e2  mov     [rax+8], rbx
0x18004b2e6  mov     [rax+10h], rsi
0x18004b2ea  mov     r12b, r8b
0x18004b2ed  mov     rsi, rdx
0x18004b2f0  mov     r14, rcx
0x18004b2f3  xor     r15d, r15d
0x18004b2f6  mov     [rbp+var_20], r15
0x18004b2fa  mov     [rbp+var_18], r15d
0x18004b2fe  mov     [rbp+var_10], r15
0x18004b302  mov     byte ptr [rbp+arg_18], r15b
0x18004b306  mov     edi, r15d
0x18004b309  mov     [rbp+Block], r15
0x18004b30d  xor     edx, edx
0x18004b30f  mov     rcx, rsi
0x18004b312  call    ??$DRMIsValidStringT@G@@YA_NPEBGPEA_K@Z; DRMIsValidStringT<ushort>(ushort const *,unsigned __int64 *)
0x18004b317  test    al, al
0x18004b319  jnz     short loc_18004B325
0x18004b31b  mov     ebx, 80070057h
0x18004b320  jmp     loc_18004BA22
0x18004b325  mov     rcx, r14; this
0x18004b328  call    ?CleanRequest@CDRMSoapRequest@@QEAAXXZ; CDRMSoapRequest::CleanRequest(void)
0x18004b32d  mov     rdx, rsi; unsigned __int16 *
0x18004b330  lea     rcx, [rbp+var_20]; this
0x18004b334  call    ?LoadXML@CDRMXML@@QEAAJPEBG@Z; CDRMXML::LoadXML(ushort const *)
0x18004b339  mov     ebx, eax
0x18004b33b  cmp     eax, 80070057h
0x18004b340  jnz     short loc_18004B356
0x18004b342  mov     rdx, rsi
0x18004b345  lea     rcx, aMsdrmResponseF; "[msdrm]:Response from the server - %S"
0x18004b34c  call    ?_RTLTRACE@@YAXPEBDZZ; _RTLTRACE(char const *,...)
0x18004b351  jmp     loc_18004BA1D
0x18004b356  test    eax, eax
0x18004b358  js      loc_18004BA05
0x18004b35e  mov     rax, [rbp+var_10]
0x18004b362  mov     [rbp+var_8], rax
0x18004b366  test    rax, rax
0x18004b369  jz      loc_18004BA1D
0x18004b36f  cmp     [rax+4], r15d
0x18004b373  jnz     short loc_18004B396
0x18004b375  lea     rdx, [rbp+arg_18]; bool *
0x18004b379  lea     rcx, [rbp+var_20]; this
0x18004b37d  call    ?FirstChild@CDRMXML@@QEAAJPEA_N@Z; CDRMXML::FirstChild(bool *)
0x18004b382  mov     ebx, eax
0x18004b384  test    eax, eax
0x18004b386  js      loc_18004BA05
0x18004b38c  cmp     byte ptr [rbp+arg_18], r15b
0x18004b390  jz      loc_18004BA1D
0x18004b396  lea     rdx, [rbp+Block]; unsigned __int16 **
0x18004b39a  lea     rcx, [rbp+var_20]; this
0x18004b39e  call    ?GetNodeValue@CDRMXML@@QEAAJPEAPEAG@Z; CDRMXML::GetNodeValue(ushort * *)
0x18004b3a3  mov     ebx, eax
0x18004b3a5  test    eax, eax
0x18004b3a7  js      loc_18004BA01
0x18004b3ad  mov     rdi, [rbp+Block]
0x18004b3b1  test    rdi, rdi
0x18004b3b4  jz      loc_18004BA1D
0x18004b3ba  mov     rax, rdi
0x18004b3bd  lea     rcx, ?g_wszSOAP_ENVELOPE_NODE@@3QBGB; "Envelope"
0x18004b3c4  sub     rcx, rdi
0x18004b3c7  movzx   edx, word ptr [rax]
0x18004b3ca  movzx   r8d, word ptr [rax+rcx]
0x18004b3cf  sub     edx, r8d
0x18004b3d2  jnz     short loc_18004B3DD
0x18004b3d4  add     rax, 2
0x18004b3d8  test    r8d, r8d
0x18004b3db  jnz     short loc_18004B3C7
0x18004b3dd  test    edx, edx
0x18004b3df  jz      short loc_18004B40C
0x18004b3e1  mov     rax, rdi
0x18004b3e4  lea     rcx, ?g_wszSOAP_SOAPENVELOPE_NODE@@3QBGB; "soap:Envelope"
0x18004b3eb  sub     rcx, rdi
0x18004b3ee  movzx   edx, word ptr [rax]
0x18004b3f1  movzx   r8d, word ptr [rax+rcx]
0x18004b3f6  sub     edx, r8d
0x18004b3f9  jnz     short loc_18004B404
0x18004b3fb  add     rax, 2
0x18004b3ff  test    r8d, r8d
0x18004b402  jnz     short loc_18004B3EE
0x18004b404  test    edx, edx
0x18004b406  jnz     loc_18004BA1D
0x18004b40c  lea     rdx, [rbp+arg_18]; bool *
0x18004b410  lea     rcx, [rbp+var_20]; this
0x18004b414  call    ?FirstChild@CDRMXML@@QEAAJPEA_N@Z; CDRMXML::FirstChild(bool *)
0x18004b419  mov     ebx, eax
0x18004b41b  test    eax, eax
0x18004b41d  js      loc_18004BA05
0x18004b423  cmp     byte ptr [rbp+arg_18], r15b
0x18004b427  jz      loc_18004BA1D
0x18004b42d  mov     rcx, rdi; Block
0x18004b430  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18004b435  mov     [rbp+Block], r15
0x18004b439  lea     rdx, [rbp+Block]; unsigned __int16 **
0x18004b43d  lea     rcx, [rbp+var_20]; this
0x18004b441  call    ?GetNodeValue@CDRMXML@@QEAAJPEAPEAG@Z; CDRMXML::GetNodeValue(ushort * *)
0x18004b446  mov     ebx, eax
0x18004b448  test    eax, eax
0x18004b44a  js      loc_18004BA01
0x18004b450  mov     rdi, [rbp+Block]
0x18004b454  test    rdi, rdi
0x18004b457  jz      loc_18004BA1D
0x18004b45d  mov     rax, rdi
0x18004b460  lea     rcx, ?g_wszSOAP_HEADER_NODE@@3QBGB; "Header"
0x18004b467  sub     rcx, rdi
0x18004b46a  movzx   r8d, word ptr [rax]
0x18004b46e  movzx   edx, word ptr [rax+rcx]
0x18004b472  sub     r8d, edx
0x18004b475  jnz     short loc_18004B47F
0x18004b477  add     rax, 2
0x18004b47b  test    edx, edx
0x18004b47d  jnz     short loc_18004B46A
0x18004b47f  or      r9, 0FFFFFFFFFFFFFFFFh
0x18004b483  test    r8d, r8d
0x18004b486  jz      short loc_18004B4B1
0x18004b488  mov     rax, rdi
0x18004b48b  lea     r8, ?g_wszSOAP_SOAPHEADER_NODE@@3QBGB; "soap:Header"
0x18004b492  sub     r8, rdi
0x18004b495  movzx   edx, word ptr [rax]
0x18004b498  movzx   ecx, word ptr [rax+r8]
0x18004b49d  sub     edx, ecx
0x18004b49f  jnz     short loc_18004B4A9
0x18004b4a1  add     rax, 2
0x18004b4a5  test    ecx, ecx
0x18004b4a7  jnz     short loc_18004B495
0x18004b4a9  test    edx, edx
0x18004b4ab  jnz     loc_18004B65C
0x18004b4b1  mov     rax, [rbp+var_8]
0x18004b4b5  mov     esi, [rax+40h]
0x18004b4b8  lea     r15, [r14+0E8h]
0x18004b4bf  mov     ecx, [r15]
0x18004b4c2  add     ecx, esi
0x18004b4c4  cmp     [r14+0ECh], ecx
0x18004b4cb  ja      short loc_18004B54B
0x18004b4cd  mov     eax, 8
0x18004b4d2  mul     rcx
0x18004b4d5  cmovb   rax, r9
0x18004b4d9  mov     rcx, rax; unsigned __int64
0x18004b4dc  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18004b4e1  mov     r12, rax
0x18004b4e4  test    rax, rax
0x18004b4e7  jnz     short loc_18004B4F3
0x18004b4e9  mov     ebx, 8007000Eh
0x18004b4ee  jmp     loc_18004BA22
0x18004b4f3  xor     r8d, r8d
0x18004b4f6  cmp     [r15], r8d
0x18004b4f9  jbe     short loc_18004B51B
0x18004b4fb  mov     rax, [r14+0E0h]
0x18004b502  mov     rcx, [rax+r8*8]
0x18004b506  mov     [r12+r8*8], rcx
0x18004b50a  inc     r8d
0x18004b50d  cmp     r8d, [r15]
0x18004b510  jb      short loc_18004B4FB
0x18004b512  lea     rbx, [r14+0E8h]
0x18004b519  jmp     short loc_18004B51E
0x18004b51b  mov     rbx, r15
0x18004b51e  mov     rcx, [r14+0F0h]; Block
0x18004b525  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18004b52a  mov     qword ptr [r14+0F0h], 0
0x18004b535  mov     [r14+0E0h], r12
0x18004b53c  mov     ecx, [rbx]
0x18004b53e  add     ecx, esi
0x18004b540  mov     [r14+0ECh], ecx
0x18004b547  mov     r12b, [rbp+arg_10]
0x18004b54b  lea     rdx, [rbp+arg_18]; bool *
0x18004b54f  lea     rcx, [rbp+var_20]; this
0x18004b553  call    ?FirstChild@CDRMXML@@QEAAJPEA_N@Z; CDRMXML::FirstChild(bool *)
0x18004b558  mov     ebx, eax
0x18004b55a  test    eax, eax
0x18004b55c  js      loc_18004BA05
0x18004b562  xor     ebx, ebx
0x18004b564  cmp     byte ptr [rbp+arg_18], bl
0x18004b567  jz      loc_18004B5FF
0x18004b56d  mov     ecx, 38h ; '8'; Size
0x18004b572  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18004b577  mov     rsi, rax
0x18004b57a  mov     [rbp+arg_18], rax
0x18004b57e  test    rax, rax
0x18004b581  jz      loc_18004B4E9
0x18004b587  mov     [rax+8], rbx
0x18004b58b  mov     [rax+10h], rbx
0x18004b58f  mov     [rax+18h], rbx
0x18004b593  mov     qword ptr [rax+20h], 0
0x18004b59b  mov     [rax+28h], rbx
0x18004b59f  mov     qword ptr [rax+30h], 0
0x18004b5a7  test    rax, rax
0x18004b5aa  jz      loc_18004B4E9
0x18004b5b0  mov     r8, rax; struct CDRMSoapRequestParameter *
0x18004b5b3  lea     rdx, [rbp+var_20]; struct CDRMXML *
0x18004b5b7  mov     rcx, r14; this
0x18004b5ba  call    ?ExtractParameter@CDRMSoapRequest@@IEAAJPEAVCDRMXML@@PEAVCDRMSoapRequestParameter@@@Z; CDRMSoapRequest::ExtractParameter(CDRMXML *,CDRMSoapRequestParameter *)
0x18004b5bf  mov     ebx, eax
0x18004b5c1  test    eax, eax
0x18004b5c3  js      loc_18004BA05
0x18004b5c9  mov     ecx, [r14+0E8h]
0x18004b5d0  mov     rax, [r14+0E0h]
0x18004b5d7  mov     [rax+rcx*8], rsi
0x18004b5db  inc     dword ptr [r15]
0x18004b5de  mov     rax, [rbp+var_8]
0x18004b5e2  xor     ebx, ebx
0x18004b5e4  test    rax, rax
0x18004b5e7  jz      short loc_18004B603
0x18004b5e9  mov     rcx, [rax+28h]
0x18004b5ed  test    rcx, rcx
0x18004b5f0  jz      short loc_18004B603
0x18004b5f2  mov     [rbp+var_8], rcx
0x18004b5f6  mov     byte ptr [rbp+arg_18], 1
0x18004b5fa  jmp     loc_18004B56D
0x18004b5ff  mov     rax, [rbp+var_8]
0x18004b603  xor     r15d, r15d
0x18004b606  test    rax, rax
0x18004b609  jz      loc_18004BA1D
0x18004b60f  mov     rcx, [rax+20h]
0x18004b613  test    rcx, rcx
0x18004b616  jz      loc_18004BA1D
0x18004b61c  mov     [rbp+var_8], rcx
0x18004b620  mov     rax, [rcx+28h]
0x18004b624  test    rax, rax
0x18004b627  jz      loc_18004BA1D
0x18004b62d  mov     [rbp+var_8], rax
0x18004b631  mov     byte ptr [rbp+arg_18], 1
0x18004b635  mov     rcx, rdi; Block
0x18004b638  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18004b63d  mov     [rbp+Block], r15
0x18004b641  lea     rdx, [rbp+Block]; unsigned __int16 **
0x18004b645  lea     rcx, [rbp+var_20]; this
0x18004b649  call    ?GetNodeValue@CDRMXML@@QEAAJPEAPEAG@Z; CDRMXML::GetNodeValue(ushort * *)
0x18004b64e  mov     ebx, eax
0x18004b650  test    eax, eax
0x18004b652  js      loc_18004BA01
0x18004b658  mov     rdi, [rbp+Block]
0x18004b65c  test    rdi, rdi
0x18004b65f  jz      loc_18004BA1D
0x18004b665  mov     rax, rdi
0x18004b668  lea     r8, ?g_wszSOAP_BODY_NODE@@3QBGB; "Body"
0x18004b66f  sub     r8, rdi
0x18004b672  movzx   edx, word ptr [rax]
0x18004b675  movzx   ecx, word ptr [rax+r8]
0x18004b67a  sub     edx, ecx
0x18004b67c  jnz     short loc_18004B686
0x18004b67e  add     rax, 2
0x18004b682  test    ecx, ecx
0x18004b684  jnz     short loc_18004B672
0x18004b686  test    edx, edx
0x18004b688  jz      short loc_18004B6B3
0x18004b68a  mov     rax, rdi
0x18004b68d  lea     r8, ?g_wszSOAP_SOAPBODY_NODE@@3QBGB; "soap:Body"
0x18004b694  sub     r8, rdi
0x18004b697  movzx   edx, word ptr [rax]
0x18004b69a  movzx   ecx, word ptr [rax+r8]
0x18004b69f  sub     edx, ecx
0x18004b6a1  jnz     short loc_18004B6AB
0x18004b6a3  add     rax, 2
0x18004b6a7  test    ecx, ecx
0x18004b6a9  jnz     short loc_18004B697
0x18004b6ab  test    edx, edx
0x18004b6ad  jnz     loc_18004BA1D
0x18004b6b3  lea     rdx, [rbp+arg_18]; bool *
0x18004b6b7  lea     rcx, [rbp+var_20]; this
0x18004b6bb  call    ?FirstChild@CDRMXML@@QEAAJPEA_N@Z; CDRMXML::FirstChild(bool *)
0x18004b6c0  mov     ebx, eax
0x18004b6c2  test    eax, eax
0x18004b6c4  js      loc_18004BA05
0x18004b6ca  mov     sil, byte ptr [rbp+arg_18]
0x18004b6ce  test    sil, sil
0x18004b6d1  jz      loc_18004BA1D
0x18004b6d7  lea     r15, [r14+0B0h]
0x18004b6de  mov     rdx, r15; unsigned __int16 **
0x18004b6e1  lea     rcx, [rbp+var_20]; this
0x18004b6e5  call    ?GetNodeValue@CDRMXML@@QEAAJPEAPEAG@Z; CDRMXML::GetNodeValue(ushort * *)
0x18004b6ea  mov     ebx, eax
0x18004b6ec  test    eax, eax
0x18004b6ee  js      loc_18004BA05
0x18004b6f4  lea     rdx, ?g_wszSOAP_FAULT_NODE@@3QBGB; "Fault"
0x18004b6fb  mov     rcx, [r15]; String1
0x18004b6fe  call    cs:__imp__wcsicmp
0x18004b704  xor     ebx, ebx
0x18004b706  test    eax, eax
0x18004b708  jz      loc_18004B8C3
0x18004b70e  lea     rdx, ?g_wszSOAP_SOAPFAULT_NODE@@3QBGB; "soap:Fault"
0x18004b715  mov     rcx, [r15]; String1
0x18004b718  call    cs:__imp__wcsicmp
0x18004b71e  test    eax, eax
0x18004b720  jz      loc_18004B8C3
0x18004b726  lea     r8, [r14+0B8h]; unsigned __int16 **
0x18004b72d  lea     rdx, ?g_wszSOAP_NAMESPACE_TAG@@3QBGB; "xmlns"
0x18004b734  lea     rcx, [rbp+var_20]; this
0x18004b738  call    ?GetAttribute@CDRMXML@@QEAAJPEBGPEAPEAG@Z; CDRMXML::GetAttribute(ushort const *,ushort * *)
0x18004b73d  test    r12b, r12b
0x18004b740  jz      short loc_18004B75F
0x18004b742  lea     rdx, [rbp+arg_18]; bool *
0x18004b746  lea     rcx, [rbp+var_20]; this
  ... truncated ...
```
