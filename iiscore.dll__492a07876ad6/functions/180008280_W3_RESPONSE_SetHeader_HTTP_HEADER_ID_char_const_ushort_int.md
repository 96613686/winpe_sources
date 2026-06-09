# W3_RESPONSE::SetHeader(_HTTP_HEADER_ID,char const *,ushort,int)

- ea: `0x180008280`
- end: `0x180008786`
- name: `?SetHeader@W3_RESPONSE@@QEAAJW4_HTTP_HEADER_ID@@PEBDGH@Z`
- size: `1286`
- prototype: `__int64 __fastcall(const struct _GUID **this, unsigned int, const char *, unsigned __int16, int)`
- caller_count: `4`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x180008270`
- `0x180024b80`
- `0x180026228`
- `0x1800265f8`

## callees

- `0x180008280`
- `0x1800087a0`
- `0x180019418`
- `0x180037790`
- `0x180038010`

## import_xrefs

- `msvcrt!isspace` at `0x180008634`
- `msvcrt!isspace` at `0x180008634`
- `msvcrt!strcspn` at `0x180008359`
- `msvcrt!strcspn` at `0x180008359`
- `msvcrt!_stricmp` at `0x1800086a8`
- `msvcrt!_stricmp` at `0x1800086a8`
- `iisutil!??0STRA@@QEAA@PEADK@Z` at `0x1800082c1`
- `iisutil!??0STRA@@QEAA@PEADK@Z` at `0x1800082df`
- `iisutil!??0STRA@@QEAA@PEADK@Z` at `0x1800082c1`
- `iisutil!??0STRA@@QEAA@PEADK@Z` at `0x1800082df`
- `iisutil!??1STRA@@QEAA@XZ` at `0x18000849e`
- `iisutil!??1STRA@@QEAA@XZ` at `0x1800084ae`
- `iisutil!??1STRA@@QEAA@XZ` at `0x1800085ac`
- `iisutil!??1STRA@@QEAA@XZ` at `0x1800085bc`
- `iisutil!??1STRA@@QEAA@XZ` at `0x1800085f9`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180008609`
- `iisutil!??1STRA@@QEAA@XZ` at `0x18000864d`
- `iisutil!??1STRA@@QEAA@XZ` at `0x18000865d`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180008678`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180008688`
- `iisutil!??1STRA@@QEAA@XZ` at `0x1800086f0`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180008700`
- `iisutil!??1STRA@@QEAA@XZ` at `0x18000871b`
- `iisutil!??1STRA@@QEAA@XZ` at `0x18000872b`
- `iisutil!??1STRA@@QEAA@XZ` at `0x18000849e`
- `iisutil!??1STRA@@QEAA@XZ` at `0x1800084ae`
- `iisutil!??1STRA@@QEAA@XZ` at `0x1800085ac`
- `iisutil!??1STRA@@QEAA@XZ` at `0x1800085bc`
- `iisutil!??1STRA@@QEAA@XZ` at `0x1800085f9`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180008609`
- `iisutil!??1STRA@@QEAA@XZ` at `0x18000864d`
- `iisutil!??1STRA@@QEAA@XZ` at `0x18000865d`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180008678`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180008688`
- `iisutil!??1STRA@@QEAA@XZ` at `0x1800086f0`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180008700`
- `iisutil!??1STRA@@QEAA@XZ` at `0x18000871b`
- `iisutil!??1STRA@@QEAA@XZ` at `0x18000872b`
- `iisutil!?QueryStr@STRA@@QEAAPEADXZ` at `0x180008340`
- `iisutil!?QueryStr@STRA@@QEAAPEADXZ` at `0x1800083ab`
- `iisutil!?QueryStr@STRA@@QEAAPEADXZ` at `0x18000854a`
- `iisutil!?QueryStr@STRA@@QEAAPEADXZ` at `0x180008592`
- `iisutil!?QueryStr@STRA@@QEAAPEADXZ` at `0x180008340`
- `iisutil!?QueryStr@STRA@@QEAAPEADXZ` at `0x1800083ab`
- `iisutil!?QueryStr@STRA@@QEAAPEADXZ` at `0x18000854a`
- `iisutil!?QueryStr@STRA@@QEAAPEADXZ` at `0x180008592`
- `iisutil!?Copy@STRA@@QEAAJPEBDK@Z` at `0x180008325`
- `iisutil!?Copy@STRA@@QEAAJPEBDK@Z` at `0x180008508`
- `iisutil!?Copy@STRA@@QEAAJPEBDK@Z` at `0x180008325`
- `iisutil!?Copy@STRA@@QEAAJPEBDK@Z` at `0x180008508`
- `iisutil!?QueryCCH@STRA@@QEBAKXZ` at `0x1800083bf`
- `iisutil!?QueryCCH@STRA@@QEBAKXZ` at `0x180008577`
- `iisutil!?QueryCCH@STRA@@QEBAKXZ` at `0x1800083bf`
- `iisutil!?QueryCCH@STRA@@QEBAKXZ` at `0x180008577`
- `iisutil!?Append@STRA@@QEAAJPEBD@Z` at `0x18000855d`
- `iisutil!?Append@STRA@@QEAAJPEBD@Z` at `0x18000855d`
- `iisutil!?Append@STRA@@QEAAJPEBDK@Z` at `0x18000852f`
- `iisutil!?Append@STRA@@QEAAJPEBDK@Z` at `0x18000852f`

## pseudocode

```c
__int64 __fastcall W3_RESPONSE::SetHeader(
        const struct _GUID **this,
        unsigned int a2,
        const char *a3,
        unsigned __int16 a4,
        int a5)
{
  __int64 v6; // rsi
  unsigned int v8; // edi
  int v9; // ebx
  const char *Str; // rbx
  const char *v11; // rbx
  unsigned __int16 *v12; // r13
  char *v13; // rax
  STRA *v14; // rcx
  char *v15; // rbx
  const char *v16; // r15
  __int64 v17; // rax
  __int64 v18; // r8
  char *v19; // rdx
  char *v20; // rax
  const struct _GUID *v21; // rcx
  unsigned __int8 *Data4; // r8
  const char *v24; // rdx
  const char *v25; // rax
  const char *v26; // rdx
  int v27; // eax
  const struct _GUID *v28; // rdx
  struct IHttpTraceContext *v29; // rcx
  int CCH; // [rsp+30h] [rbp-D0h]
  GUID *v31; // [rsp+38h] [rbp-C8h] BYREF
  __int128 v32; // [rsp+40h] [rbp-C0h]
  _BYTE v33[56]; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v34[56]; // [rsp+88h] [rbp-78h] BYREF
  char v35[256]; // [rsp+C0h] [rbp-40h] BYREF
  char v36[256]; // [rsp+1C0h] [rbp+C0h] BYREF

  v6 = a2;
  v8 = a4;
  STRA::STRA((STRA *)v34, v35, 0x100u);
  STRA::STRA((STRA *)v33, v36, 0x100u);
  if ( (unsigned int)v6 > 0x1D )
  {
    STRA::~STRA((STRA *)v33);
    STRA::~STRA((STRA *)v34);
    return 2147943813LL;
  }
  if ( !a3 )
  {
LABEL_38:
    STRA::~STRA((STRA *)v33);
    STRA::~STRA((STRA *)v34);
    return 2147942487LL;
  }
  switch ( (_DWORD)v6 )
  {
    case 0x1A:
      v26 = "Server";
      goto LABEL_32;
    case 0x1B:
      v26 = "Set-Cookie";
      goto LABEL_32;
    case 0x1D:
      v26 = "WWW-Authenticate";
LABEL_32:
      v9 = W3_RESPONSE::SetHeader((W3_RESPONSE *)this, v26, a3, v8, a5);
      goto LABEL_33;
  }
  v9 = STRA::Copy((STRA *)v33, a3, v8);
  if ( v9 < 0 )
    goto LABEL_33;
  Str = STRA::QueryStr((STRA *)v33);
  while ( 1 )
  {
    v11 = &Str[strcspn(Str, "\r\n")];
    if ( !*v11 )
      break;
    for ( Str = v11 + 1; ; ++Str )
    {
      v27 = *Str;
      if ( *Str != 13 && (_BYTE)v27 != 10 )
        break;
    }
    if ( !isspace(v27) )
      goto LABEL_38;
  }
  ++*((_DWORD *)this + 156);
  v12 = (unsigned __int16 *)&this[2 * (int)v6 + 14];
  if ( !a5 )
  {
    v24 = (const char *)*((_QWORD *)v12 + 1);
    if ( v24 )
    {
      v9 = STRA::Copy((STRA *)v34, v24, *v12);
      if ( v9 >= 0 )
      {
        v9 = STRA::Append((STRA *)v34, ",", 1u);
        if ( v9 >= 0 )
        {
          v25 = STRA::QueryStr((STRA *)v33);
          v9 = STRA::Append((STRA *)v34, v25);
          if ( v9 >= 0 )
          {
            if ( STRA::QueryCCH((STRA *)v34) > 0xFFFF )
            {
              STRA::~STRA((STRA *)v33);
              STRA::~STRA((STRA *)v34);
              return 2147942413LL;
            }
            v13 = STRA::QueryStr((STRA *)v34);
            v14 = (STRA *)v34;
            goto LABEL_11;
          }
        }
      }
LABEL_33:
      STRA::~STRA((STRA *)v33);
      STRA::~STRA((STRA *)v34);
      return (unsigned int)v9;
    }
  }
  v13 = STRA::QueryStr((STRA *)v33);
  v14 = (STRA *)v33;
LABEL_11:
  v15 = v13;
  CCH = (unsigned __int16)STRA::QueryCCH(v14);
  v16 = (const char *)(*(__int64 (__fastcall **)(const struct _GUID *, _QWORD))(*(_QWORD *)&this[6]->Data1 + 144LL))(
                        this[6],
                        (unsigned int)(CCH + 1));
  if ( v16 )
  {
    v17 = 2147483646;
    v18 = (unsigned int)(CCH + 1);
    v19 = (char *)v16;
    do
    {
      if ( !v17 )
        break;
      if ( !*v15 )
        break;
      *v19++ = *v15++;
      --v17;
      --v18;
    }
    while ( v18 );
    v20 = v19 - 1;
    if ( v18 )
      v20 = v19;
    *v20 = 0;
    if ( (_DWORD)v6 == 1 && !_stricmp(v16, "close") )
      *(_BYTE *)(*(_QWORD *)this[6][24].Data4 + 9347LL) = 1;
    *v12 = CCH;
    *((_QWORD *)v12 + 1) = v16;
    v21 = this[6];
    v32 = 0;
    Data4 = v21->Data4;
    if ( !v21 )
      Data4 = 0;
    v31 = &`WWWServerTraceProvider::GetProviderGuid'::`2'::ProviderGuid;
    if ( (**(int (__fastcall ***)(unsigned __int8 *, GUID **))Data4)(Data4, &v31) >= 0
      && DWORD1(v32) >= 4
      && DWORD2(v32) )
    {
      v28 = this[6];
      v29 = (struct IHttpTraceContext *)v28->Data4;
      if ( !v28 )
        v29 = 0;
      IISGeneralEvents::GENERAL_SET_RESPONSE_HEADER::RaiseEvent(
        v29,
        v28,
        (const char *)*(&RESPONSE_HEADER_HASH::sm_rgHeaders + 4 * v6),
        v16,
        a5);
    }
    STRA::~STRA((STRA *)v33);
    STRA::~STRA((STRA *)v34);
    return 0;
  }
  else
  {
    STRA::~STRA((STRA *)v33);
    STRA::~STRA((STRA *)v34);
    return 2147942408LL;
  }
}

```

## disassembly

```asm
0x180008280  push    rbp
0x180008282  push    rbx
0x180008283  push    rsi
0x180008284  push    rdi
0x180008285  push    r14
0x180008287  lea     rbp, [rsp-1F0h]
0x18000828f  sub     rsp, 2F0h
0x180008296  mov     rax, cs:__security_cookie
0x18000829d  xor     rax, rsp
0x1800082a0  mov     [rbp+210h+var_50], rax
0x1800082a7  mov     rbx, r8
0x1800082aa  mov     esi, edx
0x1800082ac  mov     r14, rcx
0x1800082af  movzx   edi, r9w
0x1800082b3  mov     r8d, 100h
0x1800082b9  lea     rdx, [rbp+210h+var_250]
0x1800082bd  lea     rcx, [rbp+210h+var_288]
0x1800082c1  call    cs:__imp_??0STRA@@QEAA@PEADK@Z; STRA::STRA(char *,ulong)
0x1800082c8  nop     dword ptr [rax+rax+00h]
0x1800082cd  mov     r8d, 100h
0x1800082d3  lea     rdx, [rbp+210h+var_150]
0x1800082da  lea     rcx, [rsp+310h+var_2C0]
0x1800082df  call    cs:__imp_??0STRA@@QEAA@PEADK@Z; STRA::STRA(char *,ulong)
0x1800082e6  nop     dword ptr [rax+rax+00h]
0x1800082eb  cmp     esi, 1Dh
0x1800082ee  ja      loc_1800086EB
0x1800082f4  test    rbx, rbx
0x1800082f7  jz      loc_180008648
0x1800082fd  mov     ecx, esi
0x1800082ff  sub     ecx, 1Ah
0x180008302  jz      loc_1800086DF
0x180008308  sub     ecx, 1
0x18000830b  jz      loc_1800086D3
0x180008311  cmp     ecx, 2
0x180008314  jz      loc_1800085D2
0x18000831a  mov     r8d, edi
0x18000831d  lea     rcx, [rsp+310h+var_2C0]
0x180008322  mov     rdx, rbx
0x180008325  call    cs:__imp_?Copy@STRA@@QEAAJPEBDK@Z; STRA::Copy(char const *,ulong)
0x18000832c  nop     dword ptr [rax+rax+00h]
0x180008331  lea     rcx, [rsp+310h+var_2C0]
0x180008336  mov     ebx, eax
0x180008338  test    eax, eax
0x18000833a  js      loc_1800085F9
0x180008340  call    cs:__imp_?QueryStr@STRA@@QEAAPEADXZ; STRA::QueryStr(void)
0x180008347  nop     dword ptr [rax+rax+00h]
0x18000834c  mov     rbx, rax
0x18000834f  lea     rdx, Control; "\r\n"
0x180008356  mov     rcx, rbx; Str
0x180008359  call    cs:__imp_strcspn
0x180008360  nop     dword ptr [rax+rax+00h]
0x180008365  add     rbx, rax
0x180008368  cmp     byte ptr [rbx], 0
0x18000836b  jnz     loc_18000861C
0x180008371  inc     dword ptr [r14+270h]
0x180008378  mov     [rsp+310h+var_28], r12
0x180008380  mov     r12d, dword ptr [rbp+210h+arg_20]
0x180008387  mov     [rsp+310h+var_30], r13
0x18000838f  movsxd  r13, esi
0x180008392  add     r13, 7
0x180008396  shl     r13, 4
0x18000839a  add     r13, r14
0x18000839d  test    r12d, r12d
0x1800083a0  jz      loc_1800084F2
0x1800083a6  lea     rcx, [rsp+310h+var_2C0]
0x1800083ab  call    cs:__imp_?QueryStr@STRA@@QEAAPEADXZ; STRA::QueryStr(void)
0x1800083b2  nop     dword ptr [rax+rax+00h]
0x1800083b7  lea     rcx, [rsp+310h+var_2C0]
0x1800083bc  mov     rbx, rax
0x1800083bf  call    cs:__imp_?QueryCCH@STRA@@QEBAKXZ; STRA::QueryCCH(void)
0x1800083c6  nop     dword ptr [rax+rax+00h]
0x1800083cb  mov     rcx, [r14+30h]
0x1800083cf  movzx   eax, ax
0x1800083d2  mov     [rsp+310h+var_2E0], eax
0x1800083d6  mov     [rsp+310h+var_38], r15
0x1800083de  lea     edi, [rax+1]
0x1800083e1  mov     rax, [rcx]
0x1800083e4  mov     edx, edi
0x1800083e6  mov     rax, [rax+90h]
0x1800083ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800083f2  mov     r15, rax
0x1800083f5  test    rax, rax
0x1800083f8  jz      loc_1800085A7
0x1800083fe  mov     eax, 7FFFFFFEh
0x180008403  mov     r8d, edi
0x180008406  mov     rdx, r15
0x180008409  nop     dword ptr [rax+00000000h]
0x180008410  test    rax, rax
0x180008413  jz      short loc_18000842D
0x180008415  movzx   ecx, byte ptr [rbx]
0x180008418  test    cl, cl
0x18000841a  jz      short loc_18000842D
0x18000841c  mov     [rdx], cl
0x18000841e  inc     rbx
0x180008421  inc     rdx
0x180008424  dec     rax
0x180008427  sub     r8, 1
0x18000842b  jnz     short loc_180008410
0x18000842d  test    r8, r8
0x180008430  lea     rax, [rdx-1]
0x180008434  cmovnz  rax, rdx
0x180008438  mov     byte ptr [rax], 0
0x18000843b  cmp     esi, 1
0x18000843e  jz      loc_18000869E
0x180008444  mov     eax, [rsp+310h+var_2E0]
0x180008448  lea     rdx, [rsp+310h+var_2D8]
0x18000844d  mov     [r13+0], ax
0x180008452  xorps   xmm0, xmm0
0x180008455  xor     eax, eax
0x180008457  mov     [r13+8], r15
0x18000845b  mov     rcx, [r14+30h]
0x18000845f  test    rcx, rcx
0x180008462  movdqu  [rsp+310h+var_2D0], xmm0
0x180008468  lea     r8, [rcx+8]
0x18000846c  cmovz   r8, rax
0x180008470  lea     rax, ?ProviderGuid@?1??GetProviderGuid@WWWServerTraceProvider@@SAPEBU_GUID@@XZ@4U3@B; _GUID const `WWWServerTraceProvider::GetProviderGuid(void)'::`2'::ProviderGuid
0x180008477  mov     [rsp+310h+var_2D8], rax
0x18000847c  mov     rcx, r8
0x18000847f  mov     rax, [r8]
0x180008482  mov     rax, [rax]
0x180008485  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000848a  test    eax, eax
0x18000848c  js      short loc_180008499
0x18000848e  cmp     dword ptr [rsp+310h+var_2D0+4], 4
0x180008493  jnb     loc_180008746
0x180008499  lea     rcx, [rsp+310h+var_2C0]
0x18000849e  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x1800084a5  nop     dword ptr [rax+rax+00h]
0x1800084aa  lea     rcx, [rbp+210h+var_288]
0x1800084ae  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x1800084b5  nop     dword ptr [rax+rax+00h]
0x1800084ba  xor     eax, eax
0x1800084bc  mov     r15, [rsp+310h+var_38]
0x1800084c4  mov     r12, [rsp+310h+var_28]
0x1800084cc  mov     r13, [rsp+310h+var_30]
0x1800084d4  mov     rcx, [rbp+210h+var_50]
0x1800084db  xor     rcx, rsp; StackCookie
0x1800084de  call    __security_check_cookie
0x1800084e3  add     rsp, 2F0h
0x1800084ea  pop     r14
0x1800084ec  pop     rdi
0x1800084ed  pop     rsi
0x1800084ee  pop     rbx
0x1800084ef  pop     rbp
0x1800084f0  retn
0x1800084f2  mov     rdx, [r13+8]
0x1800084f6  test    rdx, rdx
0x1800084f9  jz      loc_1800083A6
0x1800084ff  movzx   r8d, word ptr [r13+0]
0x180008504  lea     rcx, [rbp+210h+var_288]
0x180008508  call    cs:__imp_?Copy@STRA@@QEAAJPEBDK@Z; STRA::Copy(char const *,ulong)
0x18000850f  nop     dword ptr [rax+rax+00h]
0x180008514  mov     ebx, eax
0x180008516  test    eax, eax
0x180008518  js      loc_180008716
0x18000851e  mov     r8d, 1
0x180008524  lea     rdx, asc_18003C188; ","
0x18000852b  lea     rcx, [rbp+210h+var_288]
0x18000852f  call    cs:__imp_?Append@STRA@@QEAAJPEBDK@Z; STRA::Append(char const *,ulong)
0x180008536  nop     dword ptr [rax+rax+00h]
0x18000853b  lea     rcx, [rsp+310h+var_2C0]
0x180008540  mov     ebx, eax
0x180008542  test    eax, eax
0x180008544  js      loc_18000871B
0x18000854a  call    cs:__imp_?QueryStr@STRA@@QEAAPEADXZ; STRA::QueryStr(void)
0x180008551  nop     dword ptr [rax+rax+00h]
0x180008556  mov     rdx, rax
0x180008559  lea     rcx, [rbp+210h+var_288]
0x18000855d  call    cs:__imp_?Append@STRA@@QEAAJPEBD@Z; STRA::Append(char const *)
0x180008564  nop     dword ptr [rax+rax+00h]
0x180008569  mov     ebx, eax
0x18000856b  test    eax, eax
0x18000856d  js      loc_180008716
0x180008573  lea     rcx, [rbp+210h+var_288]
0x180008577  call    cs:__imp_?QueryCCH@STRA@@QEBAKXZ; STRA::QueryCCH(void)
0x18000857e  nop     dword ptr [rax+rax+00h]
0x180008583  cmp     eax, 0FFFFh
0x180008588  ja      loc_180008673
0x18000858e  lea     rcx, [rbp+210h+var_288]
0x180008592  call    cs:__imp_?QueryStr@STRA@@QEAAPEADXZ; STRA::QueryStr(void)
0x180008599  nop     dword ptr [rax+rax+00h]
0x18000859e  lea     rcx, [rbp+210h+var_288]
0x1800085a2  jmp     loc_1800083BC
0x1800085a7  lea     rcx, [rsp+310h+var_2C0]
0x1800085ac  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x1800085b3  nop     dword ptr [rax+rax+00h]
0x1800085b8  lea     rcx, [rbp+210h+var_288]
0x1800085bc  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x1800085c3  nop     dword ptr [rax+rax+00h]
0x1800085c8  mov     eax, 80070008h
0x1800085cd  jmp     loc_1800084BC
0x1800085d2  lea     rdx, aWwwAuthenticat; "WWW-Authenticate"
0x1800085d9  mov     eax, dword ptr [rbp+210h+arg_20]
0x1800085df  movzx   r9d, di; unsigned __int16
0x1800085e3  mov     r8, rbx; char *
0x1800085e6  mov     dword ptr [rsp+310h+var_2F0], eax; int
0x1800085ea  mov     rcx, r14; this
0x1800085ed  call    ?SetHeader@W3_RESPONSE@@QEAAJPEBD0GH@Z; W3_RESPONSE::SetHeader(char const *,char const *,ushort,int)
0x1800085f2  mov     ebx, eax
0x1800085f4  lea     rcx, [rsp+310h+var_2C0]
0x1800085f9  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x180008600  nop     dword ptr [rax+rax+00h]
0x180008605  lea     rcx, [rbp+210h+var_288]
0x180008609  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x180008610  nop     dword ptr [rax+rax+00h]
0x180008615  mov     eax, ebx
0x180008617  jmp     loc_1800084D4
0x18000861c  inc     rbx
0x18000861f  movsx   eax, byte ptr [rbx]
0x180008622  cmp     al, 0Dh
0x180008624  jz      loc_18000873E
0x18000862a  cmp     al, 0Ah
0x18000862c  jz      loc_18000873E
0x180008632  mov     ecx, eax; C
0x180008634  call    cs:__imp_isspace
0x18000863b  nop     dword ptr [rax+rax+00h]
0x180008640  test    eax, eax
0x180008642  jnz     loc_18000834F
0x180008648  lea     rcx, [rsp+310h+var_2C0]
0x18000864d  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x180008654  nop     dword ptr [rax+rax+00h]
0x180008659  lea     rcx, [rbp+210h+var_288]
0x18000865d  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x180008664  nop     dword ptr [rax+rax+00h]
0x180008669  mov     eax, 80070057h
0x18000866e  jmp     loc_1800084D4
0x180008673  lea     rcx, [rsp+310h+var_2C0]
0x180008678  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x18000867f  nop     dword ptr [rax+rax+00h]
0x180008684  lea     rcx, [rbp+210h+var_288]
0x180008688  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x18000868f  nop     dword ptr [rax+rax+00h]
0x180008694  mov     eax, 8007000Dh
0x180008699  jmp     loc_1800084C4
0x18000869e  lea     rdx, aClose; "close"
0x1800086a5  mov     rcx, r15; String1
0x1800086a8  call    cs:__imp__stricmp
0x1800086af  nop     dword ptr [rax+rax+00h]
0x1800086b4  test    eax, eax
0x1800086b6  jnz     loc_180008444
0x1800086bc  mov     rax, [r14+30h]
0x1800086c0  mov     rcx, [rax+188h]
0x1800086c7  mov     byte ptr [rcx+2483h], 1
0x1800086ce  jmp     loc_180008444
0x1800086d3  lea     rdx, aSetCookie; "Set-Cookie"
0x1800086da  jmp     loc_1800085D9
0x1800086df  lea     rdx, aServer_0; "Server"
0x1800086e6  jmp     loc_1800085D9
0x1800086eb  lea     rcx, [rsp+310h+var_2C0]
0x1800086f0  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x1800086f7  nop     dword ptr [rax+rax+00h]
0x1800086fc  lea     rcx, [rbp+210h+var_288]
0x180008700  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x180008707  nop     dword ptr [rax+rax+00h]
0x18000870c  mov     eax, 80070585h
0x180008711  jmp     loc_1800084D4
0x180008716  lea     rcx, [rsp+310h+var_2C0]
0x18000871b  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x180008722  nop     dword ptr [rax+rax+00h]
0x180008727  lea     rcx, [rbp+210h+var_288]
0x18000872b  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x180008732  nop     dword ptr [rax+rax+00h]
0x180008737  mov     eax, ebx
0x180008739  jmp     loc_1800084C4
0x18000873e  inc     rbx
0x180008741  jmp     loc_18000861F
0x180008746  cmp     dword ptr [rsp+310h+var_2D0+8], 0
0x18000874b  jz      loc_180008499
0x180008751  mov     rdx, [r14+30h]; struct _GUID *
0x180008755  lea     r10, ?sm_rgHeaders@RESPONSE_HEADER_HASH@@0PAUHEADER_RECORD@@A; HEADER_RECORD near * RESPONSE_HEADER_HASH::sm_rgHeaders
0x18000875c  xor     eax, eax
0x18000875e  mov     dword ptr [rsp+310h+var_2F0], r12d; char
0x180008763  mov     r8, rsi
0x180008766  mov     r9, r15; char *
0x180008769  shl     r8, 5
0x18000876d  test    rdx, rdx
0x180008770  lea     rcx, [rdx+8]
0x180008774  cmovz   rcx, rax; struct IHttpTraceContext *
0x180008778  mov     r8, [r8+r10]; char *
0x18000877c  call    ?RaiseEvent@GENERAL_SET_RESPONSE_HEADER@IISGeneralEvents@@SAJPEAVIHttpTraceContext@@PEBU_GUID@@PEBD2H@Z; IISGeneralEvents::GENERAL_SET_RESPONSE_HEADER::RaiseEvent(IHttpTraceContext *,_GUID const *,char const *,char const *,int)
0x180008781  jmp     loc_180008499
```
