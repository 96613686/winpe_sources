# W3_RESPONSE::SetHeader(char const *,char const *,ushort,int)

- ea: `0x1800087a0`
- end: `0x180009022`
- name: `?SetHeader@W3_RESPONSE@@QEAAJPEBD0GH@Z`
- size: `2178`
- prototype: `__int64 __fastcall(W3_RESPONSE *this, const char *, const char *, unsigned __int16, int)`
- caller_count: `3`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x180008280`
- `0x180008790`
- `0x180026228`

## callees

- `0x1800087a0`
- `0x180009030`
- `0x180019418`
- `0x18003772e`
- `0x180037790`
- `0x180038010`

## import_xrefs

- `msvcrt!isspace` at `0x180008efc`
- `msvcrt!isspace` at `0x180008efc`
- `msvcrt!strcspn` at `0x18000882e`
- `msvcrt!strcspn` at `0x180008882`
- `msvcrt!strcspn` at `0x18000882e`
- `msvcrt!strcspn` at `0x180008882`
- `msvcrt!_stricmp` at `0x180008d2d`
- `msvcrt!_stricmp` at `0x180008de3`
- `msvcrt!_stricmp` at `0x180008e39`
- `msvcrt!_stricmp` at `0x180008d2d`
- `msvcrt!_stricmp` at `0x180008de3`
- `msvcrt!_stricmp` at `0x180008e39`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180008b60`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180008c08`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180008dbe`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180008b60`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180008c08`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180008dbe`
- `iisutil!??0STRA@@QEAA@PEADK@Z` at `0x1800087e9`
- `iisutil!??0STRA@@QEAA@PEADK@Z` at `0x180008806`
- `iisutil!??0STRA@@QEAA@PEADK@Z` at `0x1800087e9`
- `iisutil!??0STRA@@QEAA@PEADK@Z` at `0x180008806`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180008aed`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180008afe`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180008bdc`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180008bed`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180008ec0`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180008ed1`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180008f14`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180008f25`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180008f8b`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180008f9c`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180008fcb`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180008fdc`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180008aed`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180008afe`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180008bdc`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180008bed`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180008ec0`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180008ed1`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180008f14`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180008f25`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180008f8b`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180008f9c`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180008fcb`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180008fdc`
- `iisutil!?QueryStr@STRA@@QEAAPEADXZ` at `0x180008869`
- `iisutil!?QueryStr@STRA@@QEAAPEADXZ` at `0x180008987`
- `iisutil!?QueryStr@STRA@@QEAAPEADXZ` at `0x180008cdf`
- `iisutil!?QueryStr@STRA@@QEAAPEADXZ` at `0x180008869`
- `iisutil!?QueryStr@STRA@@QEAAPEADXZ` at `0x180008987`
- `iisutil!?QueryStr@STRA@@QEAAPEADXZ` at `0x180008cdf`
- `iisutil!?Copy@STRA@@QEAAJPEBDK@Z` at `0x18000884f`
- `iisutil!?Copy@STRA@@QEAAJPEBDK@Z` at `0x180008c61`
- `iisutil!?Copy@STRA@@QEAAJPEBDK@Z` at `0x18000884f`
- `iisutil!?Copy@STRA@@QEAAJPEBDK@Z` at `0x180008c61`
- `iisutil!?QueryCCH@STRA@@QEBAKXZ` at `0x18000899a`
- `iisutil!?QueryCCH@STRA@@QEBAKXZ` at `0x180008cc3`
- `iisutil!?QueryCCH@STRA@@QEBAKXZ` at `0x18000899a`
- `iisutil!?QueryCCH@STRA@@QEBAKXZ` at `0x180008cc3`
- `iisutil!?Resize@BUFFER@@QEAA_NKK@Z` at `0x180008ad9`
- `iisutil!?Resize@BUFFER@@QEAA_NKK@Z` at `0x180008ad9`
- `iisutil!?Append@STRA@@QEAAJPEBDK@Z` at `0x180008c89`
- `iisutil!?Append@STRA@@QEAAJPEBDK@Z` at `0x180008c89`
- `iisutil!?Append@STRA@@QEAAJAEBV1@@Z` at `0x180008ca8`
- `iisutil!?Append@STRA@@QEAAJAEBV1@@Z` at `0x180008ca8`

## pseudocode

```c
__int64 __fastcall W3_RESPONSE::SetHeader(
        W3_RESPONSE *this,
        const char *a2,
        const char *a3,
        unsigned __int16 a4,
        int a5)
{
  unsigned int v7; // edi
  int v9; // ebx
  const char *Str; // rbx
  const char *v11; // rbx
  unsigned int v12; // edx
  unsigned __int8 v13; // al
  const char *v14; // rbx
  _DWORD *v15; // rsi
  __int64 v16; // rbx
  __int64 i; // rdi
  __int64 v18; // rax
  unsigned int v19; // r15d
  char v20; // r12
  char *v21; // rax
  STRA *v22; // rcx
  char *v23; // rdi
  __int64 v24; // rax
  const char *v25; // r13
  __int64 v26; // rbx
  __int64 v27; // r8
  __int64 v28; // rcx
  _BYTE *v29; // rdx
  _BYTE *v30; // rax
  __int64 v31; // rsi
  _BYTE *v32; // rax
  _BYTE *v33; // r13
  int v34; // r15d
  __int64 v35; // r8
  const char *v36; // rdx
  _BYTE *v37; // rcx
  void *v38; // rbx
  __int64 v39; // rbx
  BUFFER *v40; // r15
  _WORD *v42; // rax
  __int64 v43; // rcx
  __int64 v44; // rax
  int (__fastcall ***v45)(_QWORD, GUID **); // rcx
  const struct _GUID *v46; // rdx
  const char *v47; // rdx
  int v48; // r15d
  unsigned int v49; // edi
  __int64 v50; // rsi
  __int64 v51; // rax
  __int64 v52; // rcx
  const struct _GUID *v53; // rdx
  __int64 v54; // rax
  struct IHttpTraceContext *v55; // rcx
  const void *v56; // rdi
  void *Ptr; // rax
  _QWORD *v58; // rcx
  __int64 v59; // rax
  __int64 v60; // rcx
  __int64 v61; // rax
  int v62; // eax
  int v63; // ecx
  __int64 v64; // rax
  struct IHttpTraceContext *v65; // rcx
  int CCH; // [rsp+38h] [rbp-C8h]
  int v68; // [rsp+3Ch] [rbp-C4h]
  char *v69; // [rsp+40h] [rbp-C0h]
  GUID *v70; // [rsp+48h] [rbp-B8h] BYREF
  __int128 v71; // [rsp+50h] [rbp-B0h]
  _BYTE v72[56]; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v73[56]; // [rsp+98h] [rbp-68h] BYREF
  char v74[256]; // [rsp+D0h] [rbp-30h] BYREF
  char v75[256]; // [rsp+1D0h] [rbp+D0h] BYREF

  v7 = a4;
  STRA::STRA((STRA *)v72, v74, 0x100u);
  STRA::STRA((STRA *)v73, v75, 0x100u);
  if ( !a2 || !a3 || a2[strcspn(a2, "\r\n")] )
  {
LABEL_90:
    STRA::~STRA((STRA *)v73);
    STRA::~STRA((STRA *)v72);
    return 2147942487LL;
  }
  v9 = STRA::Copy((STRA *)v73, a3, v7);
  if ( v9 < 0 )
  {
LABEL_85:
    STRA::~STRA((STRA *)v73);
    STRA::~STRA((STRA *)v72);
    return (unsigned int)v9;
  }
  Str = STRA::QueryStr((STRA *)v73);
  while ( 1 )
  {
    v11 = &Str[strcspn(Str, "\r\n")];
    if ( !*v11 )
      break;
    for ( Str = v11 + 1; ; ++Str )
    {
      v62 = *Str;
      if ( *Str != 13 && (_BYTE)v62 != 10 )
        break;
    }
    if ( !isspace(v62) )
      goto LABEL_90;
  }
  ++*((_DWORD *)this + 156);
  v12 = 0;
  v13 = *a2;
  v14 = a2;
  v15 = RESPONSE_HEADER_HASH::sm_pResponseHash;
  if ( *((_DWORD *)RESPONSE_HEADER_HASH::sm_pResponseHash + 158) )
  {
    if ( v13 )
    {
      do
      {
        ++v14;
        v63 = v13;
        v13 = *v14;
        v12 = v63 + 101 * v12;
      }
      while ( *v14 );
    }
  }
  else if ( v13 )
  {
    do
    {
      ++v14;
      v12 = (v13 & 0xDF) + 101 * v12;
      v13 = *v14;
    }
    while ( *v14 );
  }
  v16 = v14 - a2;
  for ( i = *((_QWORD *)RESPONSE_HEADER_HASH::sm_pResponseHash + v12 % 0x4F); ; i = *(_QWORD *)(i + 8) )
  {
    if ( !i )
    {
      v19 = -1;
      goto LABEL_19;
    }
    v18 = *(unsigned __int16 *)(i + 16);
    if ( !v15[158] )
      break;
    if ( v16 == v18 && !strcmp(a2, *(const char **)i) )
    {
      v19 = *(_DWORD *)(i + 24);
      goto LABEL_19;
    }
LABEL_14:
    ;
  }
  if ( v16 != v18 || _stricmp(a2, *(const char **)i) )
    goto LABEL_14;
  v19 = *(_DWORD *)(i + 24);
LABEL_19:
  v20 = a5;
  if ( a5 || v19 > 0x1D || (v47 = (const char *)*((_QWORD *)this + 2 * (int)v19 + 15)) == 0 )
  {
    v21 = STRA::QueryStr((STRA *)v73);
    v22 = (STRA *)v73;
    goto LABEL_21;
  }
  v9 = STRA::Copy((STRA *)v72, v47, *((unsigned __int16 *)this + 8 * (int)v19 + 56));
  if ( v9 < 0 )
    goto LABEL_85;
  v9 = STRA::Append((STRA *)v72, ",", 1u);
  if ( v9 < 0 )
    goto LABEL_85;
  v9 = STRA::Append((STRA *)v72, (const struct STRA *)v73);
  if ( v9 < 0 )
    goto LABEL_85;
  if ( STRA::QueryCCH((STRA *)v72) > 0xFFFF )
  {
    STRA::~STRA((STRA *)v73);
    STRA::~STRA((STRA *)v72);
    return 2147942413LL;
  }
  v21 = STRA::QueryStr((STRA *)v72);
  v22 = (STRA *)v72;
LABEL_21:
  v23 = v21;
  CCH = (unsigned __int16)STRA::QueryCCH(v22);
  v24 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 6) + 144LL))(
          *((_QWORD *)this + 6),
          (unsigned int)(CCH + 1));
  v69 = (char *)v24;
  v25 = (const char *)v24;
  if ( !v24 )
    goto LABEL_43;
  v26 = 2147483646;
  v27 = (unsigned int)(CCH + 1);
  v28 = 2147483646;
  v29 = (_BYTE *)v24;
  do
  {
    if ( !v28 )
      break;
    if ( !*v23 )
      break;
    *v29++ = *v23++;
    --v28;
    --v27;
  }
  while ( v27 );
  v30 = v29 - 1;
  if ( v27 )
    v30 = v29;
  *v30 = 0;
  if ( v19 != -1 )
  {
    if ( v19 == 1 && !_stricmp(v25, "close") )
      *(_BYTE *)(*(_QWORD *)(*((_QWORD *)this + 6) + 392LL) + 9347LL) = 1;
    *((_QWORD *)this + 2 * (int)v19 + 15) = v25;
    *((_WORD *)this + 8 * (int)v19 + 56) = CCH;
    v59 = *((_QWORD *)this + 6);
    v60 = v59 + 8;
    if ( !v59 )
      v60 = 0;
    if ( (unsigned int)WWWServerTraceProvider::CheckTracingEnabled(v60, 0, 4) )
    {
      v61 = *((_QWORD *)this + 6);
      v55 = (struct IHttpTraceContext *)(v61 + 8);
      if ( !v61 )
        v55 = 0;
LABEL_71:
      IISGeneralEvents::GENERAL_SET_RESPONSE_HEADER::RaiseEvent(v55, v53, a2, v25, v20);
    }
LABEL_50:
    STRA::~STRA((STRA *)v73);
    STRA::~STRA((STRA *)v72);
    return 0;
  }
  if ( !a5 )
    goto LABEL_30;
  v48 = 0;
  v49 = 0;
  if ( !*((_WORD *)this + 40) )
    goto LABEL_30;
  while ( 2 )
  {
    v50 = 24LL * v49;
    if ( !_stricmp(a2, *(const char **)(v50 + *((_QWORD *)this + 11) + 8)) )
    {
      v58 = (_QWORD *)(v50 + *((_QWORD *)this + 11));
      if ( !v48 )
      {
        v58[2] = v25;
        v48 = 1;
        *(_WORD *)(v50 + *((_QWORD *)this + 11) + 2) = CCH;
        goto LABEL_63;
      }
      memmove_0(v58, v58 + 3, 24LL * (*((unsigned __int16 *)this + 40) - v49 - 1));
      --*((_WORD *)this + 40);
    }
    else
    {
LABEL_63:
      ++v49;
    }
    if ( v49 < *((unsigned __int16 *)this + 40) )
      continue;
    break;
  }
  v20 = a5;
  v26 = 2147483646;
  if ( v48 )
  {
    v51 = *((_QWORD *)this + 6);
    v52 = v51 + 8;
    if ( !v51 )
      v52 = 0;
    if ( (unsigned int)WWWServerTraceProvider::CheckTracingEnabled(v52, 0, 4) )
    {
      v54 = *((_QWORD *)this + 6);
      v55 = (struct IHttpTraceContext *)(v54 + 8);
      if ( !v54 )
        v55 = 0;
      goto LABEL_71;
    }
    goto LABEL_50;
  }
LABEL_30:
  v31 = -1;
  do
    ++v31;
  while ( a2[v31] );
  v32 = (_BYTE *)(*(__int64 (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 6) + 144LL))(
                   *((_QWORD *)this + 6),
                   (unsigned int)(v31 + 1));
  v33 = v32;
  if ( v32 )
  {
    v34 = 0;
    v35 = (unsigned int)(v31 + 1);
    v68 = 0;
    if ( (unsigned int)v31 > 0x7FFFFFFE )
    {
      if ( (_DWORD)v31 != -1 )
        goto LABEL_40;
    }
    else
    {
      v36 = a2;
      v37 = v32;
      do
      {
        if ( !v26 )
          break;
        if ( !*v36 )
          break;
        *v37++ = *v36++;
        --v26;
        --v35;
      }
      while ( v35 );
      v32 = v37 - 1;
      if ( v35 )
        v32 = v37;
LABEL_40:
      *v32 = 0;
    }
    v38 = (void *)*((_QWORD *)this + 11);
    if ( v38 )
    {
      if ( BUFFER::QueryPtr((W3_RESPONSE *)((char *)this + 712)) != v38 )
        v34 = 1;
      v68 = v34;
    }
    v39 = *((unsigned __int16 *)this + 40);
    v40 = (W3_RESPONSE *)((char *)this + 712);
    if ( BUFFER::Resize((W3_RESPONSE *)((char *)this + 712), 24 * (v39 + 1), 0x200u) )
    {
      if ( v68 )
      {
        v56 = (const void *)*((_QWORD *)this + 11);
        Ptr = BUFFER::QueryPtr(v40);
        memmove_0(Ptr, v56, 24 * v39);
      }
      ++*((_WORD *)this + 40);
      v42 = BUFFER::QueryPtr(v40);
      v43 = 3 * v39;
      *((_QWORD *)this + 11) = v42;
      v42[4 * v43] = v31;
      v42[4 * v43 + 1] = CCH;
      *(_QWORD *)&v42[4 * v43 + 4] = v33;
      *(_QWORD *)&v42[4 * v43 + 8] = v69;
      v44 = *((_QWORD *)this + 6);
      v71 = 0;
      v45 = (int (__fastcall ***)(_QWORD, GUID **))(v44 + 8);
      if ( !v44 )
        v45 = 0;
      v70 = &`WWWServerTraceProvider::GetProviderGuid'::`2'::ProviderGuid;
      if ( (**v45)(v45, &v70) >= 0 && DWORD1(v71) >= 4 && DWORD2(v71) )
      {
        v64 = *((_QWORD *)this + 6);
        v65 = (struct IHttpTraceContext *)(v64 + 8);
        if ( !v64 )
          v65 = 0;
        IISGeneralEvents::GENERAL_SET_RESPONSE_HEADER::RaiseEvent(v65, v46, a2, v69, a5);
      }
      goto LABEL_50;
    }
  }
LABEL_43:
  STRA::~STRA((STRA *)v73);
  STRA::~STRA((STRA *)v72);
  return 2147942408LL;
}

```

## disassembly

```asm
0x1800087a0  push    rbp
0x1800087a2  push    rbx
0x1800087a3  push    rdi
0x1800087a4  push    r13
0x1800087a6  push    r14
0x1800087a8  lea     rbp, [rsp-200h]
0x1800087b0  sub     rsp, 300h
0x1800087b7  mov     rax, cs:__security_cookie
0x1800087be  xor     rax, rsp
0x1800087c1  mov     [rbp+220h+var_50], rax
0x1800087c8  mov     rbx, r8
0x1800087cb  mov     [rsp+320h+var_2F0], rcx
0x1800087d0  mov     r14, rdx
0x1800087d3  movzx   edi, r9w
0x1800087d7  mov     r13, rcx
0x1800087da  lea     rdx, [rbp+220h+var_250]
0x1800087de  mov     r8d, 100h
0x1800087e4  lea     rcx, [rsp+320h+var_2C0]
0x1800087e9  call    cs:__imp_??0STRA@@QEAA@PEADK@Z; STRA::STRA(char *,ulong)
0x1800087f0  nop     dword ptr [rax+rax+00h]
0x1800087f5  mov     r8d, 100h
0x1800087fb  lea     rdx, [rbp+220h+var_150]
0x180008802  lea     rcx, [rbp+220h+var_288]
0x180008806  call    cs:__imp_??0STRA@@QEAA@PEADK@Z; STRA::STRA(char *,ulong)
0x18000880d  nop     dword ptr [rax+rax+00h]
0x180008812  test    r14, r14
0x180008815  jz      loc_180008F10
0x18000881b  test    rbx, rbx
0x18000881e  jz      loc_180008F10
0x180008824  lea     rdx, Control; "\r\n"
0x18000882b  mov     rcx, r14; Str
0x18000882e  call    cs:__imp_strcspn
0x180008835  nop     dword ptr [rax+rax+00h]
0x18000883a  cmp     byte ptr [rax+r14], 0
0x18000883f  jnz     loc_180008F10
0x180008845  mov     r8d, edi
0x180008848  lea     rcx, [rbp+220h+var_288]
0x18000884c  mov     rdx, rbx
0x18000884f  call    cs:__imp_?Copy@STRA@@QEAAJPEBDK@Z; STRA::Copy(char const *,ulong)
0x180008856  nop     dword ptr [rax+rax+00h]
0x18000885b  lea     rcx, [rbp+220h+var_288]
0x18000885f  mov     ebx, eax
0x180008861  test    eax, eax
0x180008863  js      loc_180008EC0
0x180008869  call    cs:__imp_?QueryStr@STRA@@QEAAPEADXZ; STRA::QueryStr(void)
0x180008870  nop     dword ptr [rax+rax+00h]
0x180008875  mov     rbx, rax
0x180008878  lea     rdx, Control; "\r\n"
0x18000887f  mov     rcx, rbx; Str
0x180008882  call    cs:__imp_strcspn
0x180008889  nop     dword ptr [rax+rax+00h]
0x18000888e  add     rbx, rax
0x180008891  cmp     byte ptr [rbx], 0
0x180008894  jnz     loc_180008EE4
0x18000889a  inc     dword ptr [r13+270h]
0x1800088a1  xor     edx, edx
0x1800088a3  movzx   eax, byte ptr [r14]
0x1800088a7  mov     rbx, r14
0x1800088aa  mov     [rsp+320h+var_28], rsi
0x1800088b2  mov     rsi, cs:?sm_pResponseHash@RESPONSE_HEADER_HASH@@0PEAV1@EA; RESPONSE_HEADER_HASH * RESPONSE_HEADER_HASH::sm_pResponseHash
0x1800088b9  mov     [rsp+320h+var_30], r12
0x1800088c1  cmp     [rsi+278h], edx
0x1800088c7  jnz     loc_180008F62
0x1800088cd  test    al, al
0x1800088cf  jz      short loc_1800088F4
0x1800088d1  nop     dword ptr [rax+00h]
0x1800088d5  nop     word ptr [rax+rax+00000000h]
0x1800088e0  and     eax, 0DFh
0x1800088e5  imul    edx, 65h ; 'e'
0x1800088e8  inc     rbx
0x1800088eb  add     edx, eax
0x1800088ed  movzx   eax, byte ptr [rbx]
0x1800088f0  test    al, al
0x1800088f2  jnz     short loc_1800088E0
0x1800088f4  mov     ecx, edx
0x1800088f6  mov     rax, 67B23A5440CF6475h
0x180008900  mul     rcx
0x180008903  sub     rbx, r14
0x180008906  mov     [rsp+320h+var_38], r15
0x18000890e  shr     rdx, 5
0x180008912  imul    rax, rdx, 4Fh ; 'O'
0x180008916  sub     rcx, rax
0x180008919  mov     eax, ecx
0x18000891b  mov     rdi, [rsi+rax*8]
0x18000891f  nop
0x180008920  test    rdi, rdi
0x180008923  jz      short loc_18000896D
0x180008925  cmp     dword ptr [rsi+278h], 0
0x18000892c  movzx   eax, word ptr [rdi+10h]
0x180008930  jnz     short loc_180008941
0x180008932  cmp     rbx, rax
0x180008935  jz      loc_180008DDD
0x18000893b  mov     rdi, [rdi+8]
0x18000893f  jmp     short loc_180008920
0x180008941  cmp     rbx, rax
0x180008944  jnz     short loc_18000893B
0x180008946  mov     r8, [rdi]
0x180008949  mov     rax, r14
0x18000894c  sub     r8, r14
0x18000894f  nop
0x180008950  movzx   edx, byte ptr [rax]
0x180008953  movzx   ecx, byte ptr [rax+r8]
0x180008958  sub     edx, ecx
0x18000895a  jnz     short loc_180008963
0x18000895c  inc     rax
0x18000895f  test    ecx, ecx
0x180008961  jnz     short loc_180008950
0x180008963  test    edx, edx
0x180008965  jnz     short loc_18000893B
0x180008967  mov     r15d, [rdi+18h]
0x18000896b  jmp     short loc_180008973
0x18000896d  mov     r15d, 0FFFFFFFFh
0x180008973  mov     r12d, dword ptr [rbp+220h+arg_20]
0x18000897a  test    r12d, r12d
0x18000897d  jz      loc_180008C2A
0x180008983  lea     rcx, [rbp+220h+var_288]
0x180008987  call    cs:__imp_?QueryStr@STRA@@QEAAPEADXZ; STRA::QueryStr(void)
0x18000898e  nop     dword ptr [rax+rax+00h]
0x180008993  lea     rcx, [rbp+220h+var_288]
0x180008997  mov     rdi, rax
0x18000899a  call    cs:__imp_?QueryCCH@STRA@@QEBAKXZ; STRA::QueryCCH(void)
0x1800089a1  nop     dword ptr [rax+rax+00h]
0x1800089a6  mov     rcx, [r13+30h]
0x1800089aa  movzx   eax, ax
0x1800089ad  mov     [rsp+320h+var_2E8], eax
0x1800089b1  lea     esi, [rax+1]
0x1800089b4  mov     rax, [rcx]
0x1800089b7  mov     edx, esi
0x1800089b9  mov     rax, [rax+90h]
0x1800089c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800089c5  mov     [rsp+320h+var_2E0], rax
0x1800089ca  mov     r13, rax
0x1800089cd  test    rax, rax
0x1800089d0  jz      loc_180008AE9
0x1800089d6  mov     ebx, 7FFFFFFEh
0x1800089db  mov     r8d, esi
0x1800089de  mov     ecx, ebx
0x1800089e0  mov     rdx, rax
0x1800089e3  test    rcx, rcx
0x1800089e6  jz      short loc_180008A00
0x1800089e8  movzx   eax, byte ptr [rdi]
0x1800089eb  test    al, al
0x1800089ed  jz      short loc_180008A00
0x1800089ef  mov     [rdx], al
0x1800089f1  inc     rdi
0x1800089f4  inc     rdx
0x1800089f7  dec     rcx
0x1800089fa  sub     r8, 1
0x1800089fe  jnz     short loc_1800089E3
0x180008a00  test    r8, r8
0x180008a03  lea     rax, [rdx-1]
0x180008a07  cmovnz  rax, rdx
0x180008a0b  mov     byte ptr [rax], 0
0x180008a0e  cmp     r15d, 0FFFFFFFFh
0x180008a12  jnz     loc_180008E29
0x180008a18  test    r12d, r12d
0x180008a1b  jnz     loc_180008CF5
0x180008a21  mov     rsi, 0FFFFFFFFFFFFFFFFh
0x180008a28  nop     dword ptr [rax+rax+00000000h]
0x180008a30  inc     rsi
0x180008a33  cmp     byte ptr [r14+rsi], 0
0x180008a38  jnz     short loc_180008A30
0x180008a3a  mov     r12, [rsp+320h+var_2F0]
0x180008a3f  lea     edi, [rsi+1]
0x180008a42  mov     edx, edi
0x180008a44  mov     rcx, [r12+30h]
0x180008a49  mov     rax, [rcx]
0x180008a4c  mov     rax, [rax+90h]
0x180008a53  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008a58  mov     r13, rax
0x180008a5b  test    rax, rax
0x180008a5e  jz      loc_180008AE9
0x180008a64  xor     r15d, r15d
0x180008a67  mov     r8d, edi
0x180008a6a  lea     ecx, [rdi-1]
0x180008a6d  mov     [rsp+320h+var_2E4], r15d
0x180008a72  cmp     ecx, ebx
0x180008a74  ja      loc_180008FB2
0x180008a7a  mov     rdx, r14
0x180008a7d  mov     rcx, rax
0x180008a80  test    rbx, rbx
0x180008a83  jz      short loc_180008A9D
0x180008a85  movzx   eax, byte ptr [rdx]
0x180008a88  test    al, al
0x180008a8a  jz      short loc_180008A9D
0x180008a8c  mov     [rcx], al
0x180008a8e  inc     rdx
0x180008a91  inc     rcx
0x180008a94  dec     rbx
0x180008a97  sub     r8, 1
0x180008a9b  jnz     short loc_180008A80
0x180008a9d  test    r8, r8
0x180008aa0  lea     rax, [rcx-1]
0x180008aa4  cmovnz  rax, rcx
0x180008aa8  mov     [rax], r15b
0x180008aab  mov     rbx, [r12+58h]
0x180008ab0  test    rbx, rbx
0x180008ab3  jnz     loc_180008C00
0x180008ab9  movzx   ebx, word ptr [r12+50h]
0x180008abf  lea     r15, [r12+2C8h]
0x180008ac7  mov     r8d, 200h
0x180008acd  mov     rcx, r15
0x180008ad0  lea     eax, [rbx+1]
0x180008ad3  lea     edx, [rax+rax*2]
0x180008ad6  shl     edx, 3
0x180008ad9  call    cs:__imp_?Resize@BUFFER@@QEAA_NKK@Z; BUFFER::Resize(ulong,ulong)
0x180008ae0  nop     dword ptr [rax+rax+00h]
0x180008ae5  test    al, al
0x180008ae7  jnz     short loc_180008B46
0x180008ae9  lea     rcx, [rbp+220h+var_288]
0x180008aed  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x180008af4  nop     dword ptr [rax+rax+00h]
0x180008af9  lea     rcx, [rsp+320h+var_2C0]
0x180008afe  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x180008b05  nop     dword ptr [rax+rax+00h]
0x180008b0a  mov     eax, 80070008h
0x180008b0f  mov     r15, [rsp+320h+var_38]
0x180008b17  mov     rsi, [rsp+320h+var_28]
0x180008b1f  mov     r12, [rsp+320h+var_30]
0x180008b27  mov     rcx, [rbp+220h+var_50]
0x180008b2e  xor     rcx, rsp; StackCookie
0x180008b31  call    __security_check_cookie
0x180008b36  add     rsp, 300h
0x180008b3d  pop     r14
0x180008b3f  pop     r13
0x180008b41  pop     rdi
0x180008b42  pop     rbx
0x180008b43  pop     rbp
0x180008b44  retn
0x180008b46  cmp     [rsp+320h+var_2E4], 0
0x180008b4b  mov     r12, rbx
0x180008b4e  jnz     loc_180008DAA
0x180008b54  mov     rdi, [rsp+320h+var_2F0]
0x180008b59  mov     rcx, r15
0x180008b5c  inc     word ptr [rdi+50h]
0x180008b60  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x180008b67  nop     dword ptr [rax+rax+00h]
0x180008b6c  mov     edx, [rsp+320h+var_2E8]
0x180008b70  lea     rcx, [r12+r12*2]
0x180008b74  mov     rbx, [rsp+320h+var_2E0]
0x180008b79  xorps   xmm0, xmm0
0x180008b7c  mov     [rdi+58h], rax
0x180008b80  mov     [rax+rcx*8], si
0x180008b84  mov     esi, 0
0x180008b89  mov     [rax+rcx*8+2], dx
0x180008b8e  lea     rdx, [rsp+320h+var_2D8]
0x180008b93  mov     [rax+rcx*8+8], r13
0x180008b98  mov     [rax+rcx*8+10h], rbx
0x180008b9d  mov     rax, [rdi+30h]
0x180008ba1  test    rax, rax
0x180008ba4  movdqu  [rsp+320h+var_2D0], xmm0
0x180008baa  lea     rcx, [rax+8]
0x180008bae  cmovz   rcx, rsi
0x180008bb2  lea     rax, ?ProviderGuid@?1??GetProviderGuid@WWWServerTraceProvider@@SAPEBU_GUID@@XZ@4U3@B; _GUID const `WWWServerTraceProvider::GetProviderGuid(void)'::`2'::ProviderGuid
0x180008bb9  mov     [rsp+320h+var_2D8], rax
0x180008bbe  mov     rax, [rcx]
0x180008bc1  mov     rax, [rax]
0x180008bc4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008bc9  test    eax, eax
0x180008bcb  js      short loc_180008BD8
0x180008bcd  cmp     dword ptr [rsp+320h+var_2D0+4], 4
0x180008bd2  jnb     loc_180008FEF
0x180008bd8  lea     rcx, [rbp+220h+var_288]
0x180008bdc  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x180008be3  nop     dword ptr [rax+rax+00h]
0x180008be8  lea     rcx, [rsp+320h+var_2C0]
0x180008bed  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x180008bf4  nop     dword ptr [rax+rax+00h]
0x180008bf9  xor     eax, eax
0x180008bfb  jmp     loc_180008B0F
0x180008c00  lea     rcx, [r12+2C8h]
0x180008c08  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x180008c0f  nop     dword ptr [rax+rax+00h]
0x180008c14  cmp     rax, rbx
0x180008c17  mov     eax, 1
0x180008c1c  cmovnz  r15d, eax
0x180008c20  mov     [rsp+320h+var_2E4], r15d
0x180008c25  jmp     loc_180008AB9
0x180008c2a  cmp     r15d, 1Dh
0x180008c2e  ja      loc_180008983
0x180008c34  cmp     r15d, 0FFFFFFFFh
0x180008c38  jz      loc_180008983
0x180008c3e  movsxd  rax, r15d
0x180008c41  add     rax, 7
0x180008c45  add     rax, rax
0x180008c48  mov     rdx, [r13+rax*8+8]
0x180008c4d  test    rdx, rdx
0x180008c50  jz      loc_180008983
0x180008c56  movzx   r8d, word ptr [r13+rax*8+0]
0x180008c5c  lea     rcx, [rsp+320h+var_2C0]
0x180008c61  call    cs:__imp_?Copy@STRA@@QEAAJPEBDK@Z; STRA::Copy(char const *,ulong)
0x180008c68  nop     dword ptr [rax+rax+00h]
0x180008c6d  mov     ebx, eax
0x180008c6f  test    eax, eax
0x180008c71  js      loc_180008FC7
0x180008c77  mov     r8d, 1
0x180008c7d  lea     rdx, asc_18003C188; ","
0x180008c84  lea     rcx, [rsp+320h+var_2C0]
0x180008c89  call    cs:__imp_?Append@STRA@@QEAAJPEBDK@Z; STRA::Append(char const *,ulong)
0x180008c90  nop     dword ptr [rax+rax+00h]
  ... truncated ...
```
