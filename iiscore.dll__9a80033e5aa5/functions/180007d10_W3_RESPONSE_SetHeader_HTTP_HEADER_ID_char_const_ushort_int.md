# W3_RESPONSE::SetHeader(_HTTP_HEADER_ID,char const *,ushort,int)

- ea: `0x180007d10`
- end: `0x180008161`
- name: `?SetHeader@W3_RESPONSE@@QEAAJW4_HTTP_HEADER_ID@@PEBDGH@Z`
- size: `1105`
- prototype: `__int64 __fastcall(const struct _GUID **this, unsigned int, const char *, unsigned __int16, int)`
- caller_count: `4`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x180007d00`
- `0x180022e70`
- `0x180024388`
- `0x180024724`

## callees

- `0x180007d10`
- `0x180008180`
- `0x180017f98`
- `0x1800343f0`
- `0x180035010`

## import_xrefs

- `msvcrt!isspace` at `0x18000804b`
- `msvcrt!isspace` at `0x18000804b`
- `msvcrt!strcspn` at `0x180007dd1`
- `msvcrt!strcspn` at `0x180007dd1`
- `msvcrt!_stricmp` at `0x1800080a1`
- `msvcrt!_stricmp` at `0x1800080a1`
- `iisutil!??0STRA@@QEAA@PEADK@Z` at `0x180007d51`
- `iisutil!??0STRA@@QEAA@PEADK@Z` at `0x180007d69`
- `iisutil!??0STRA@@QEAA@PEADK@Z` at `0x180007d51`
- `iisutil!??0STRA@@QEAA@PEADK@Z` at `0x180007d69`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180007efe`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180007f08`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180007fdb`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180007fe5`
- `iisutil!??1STRA@@QEAA@XZ` at `0x18000801c`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180008026`
- `iisutil!??1STRA@@QEAA@XZ` at `0x18000805e`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180008068`
- `iisutil!??1STRA@@QEAA@XZ` at `0x18000807d`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180008087`
- `iisutil!??1STRA@@QEAA@XZ` at `0x1800080e3`
- `iisutil!??1STRA@@QEAA@XZ` at `0x1800080ed`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180008102`
- `iisutil!??1STRA@@QEAA@XZ` at `0x18000810c`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180007efe`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180007f08`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180007fdb`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180007fe5`
- `iisutil!??1STRA@@QEAA@XZ` at `0x18000801c`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180008026`
- `iisutil!??1STRA@@QEAA@XZ` at `0x18000805e`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180008068`
- `iisutil!??1STRA@@QEAA@XZ` at `0x18000807d`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180008087`
- `iisutil!??1STRA@@QEAA@XZ` at `0x1800080e3`
- `iisutil!??1STRA@@QEAA@XZ` at `0x1800080ed`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180008102`
- `iisutil!??1STRA@@QEAA@XZ` at `0x18000810c`
- `iisutil!?QueryStr@STRA@@QEAAPEADXZ` at `0x180007dbe`
- `iisutil!?QueryStr@STRA@@QEAAPEADXZ` at `0x180007e1d`
- `iisutil!?QueryStr@STRA@@QEAAPEADXZ` at `0x180007f91`
- `iisutil!?QueryStr@STRA@@QEAAPEADXZ` at `0x180007fc7`
- `iisutil!?QueryStr@STRA@@QEAAPEADXZ` at `0x180007dbe`
- `iisutil!?QueryStr@STRA@@QEAAPEADXZ` at `0x180007e1d`
- `iisutil!?QueryStr@STRA@@QEAAPEADXZ` at `0x180007f91`
- `iisutil!?QueryStr@STRA@@QEAAPEADXZ` at `0x180007fc7`
- `iisutil!?Copy@STRA@@QEAAJPEBDK@Z` at `0x180007da9`
- `iisutil!?Copy@STRA@@QEAAJPEBDK@Z` at `0x180007f5b`
- `iisutil!?Copy@STRA@@QEAAJPEBDK@Z` at `0x180007da9`
- `iisutil!?Copy@STRA@@QEAAJPEBDK@Z` at `0x180007f5b`
- `iisutil!?QueryCCH@STRA@@QEBAKXZ` at `0x180007e2b`
- `iisutil!?QueryCCH@STRA@@QEBAKXZ` at `0x180007fb2`
- `iisutil!?QueryCCH@STRA@@QEBAKXZ` at `0x180007e2b`
- `iisutil!?QueryCCH@STRA@@QEBAKXZ` at `0x180007fb2`
- `iisutil!?Append@STRA@@QEAAJPEBD@Z` at `0x180007f9e`
- `iisutil!?Append@STRA@@QEAAJPEBD@Z` at `0x180007f9e`
- `iisutil!?Append@STRA@@QEAAJPEBDK@Z` at `0x180007f7c`
- `iisutil!?Append@STRA@@QEAAJPEBDK@Z` at `0x180007f7c`

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
0x180007d10  push    rbp
0x180007d12  push    rbx
0x180007d13  push    rsi
0x180007d14  push    rdi
0x180007d15  push    r14
0x180007d17  lea     rbp, [rsp-1F0h]
0x180007d1f  sub     rsp, 2F0h
0x180007d26  mov     rax, cs:__security_cookie
0x180007d2d  xor     rax, rsp
0x180007d30  mov     [rbp+210h+var_50], rax
0x180007d37  mov     rbx, r8
0x180007d3a  mov     esi, edx
0x180007d3c  mov     r14, rcx
0x180007d3f  movzx   edi, r9w
0x180007d43  mov     r8d, 100h
0x180007d49  lea     rdx, [rbp+210h+var_250]
0x180007d4d  lea     rcx, [rbp+210h+var_288]
0x180007d51  call    cs:__imp_??0STRA@@QEAA@PEADK@Z; STRA::STRA(char *,ulong)
0x180007d57  mov     r8d, 100h
0x180007d5d  lea     rdx, [rbp+210h+var_150]
0x180007d64  lea     rcx, [rsp+310h+var_2C0]
0x180007d69  call    cs:__imp_??0STRA@@QEAA@PEADK@Z; STRA::STRA(char *,ulong)
0x180007d6f  cmp     esi, 1Dh
0x180007d72  ja      loc_1800080DE
0x180007d78  test    rbx, rbx
0x180007d7b  jz      loc_180008059
0x180007d81  mov     ecx, esi
0x180007d83  sub     ecx, 1Ah
0x180007d86  jz      loc_1800080D2
0x180007d8c  sub     ecx, 1
0x180007d8f  jz      loc_1800080C6
0x180007d95  cmp     ecx, 2
0x180007d98  jz      loc_180007FF5
0x180007d9e  mov     r8d, edi
0x180007da1  lea     rcx, [rsp+310h+var_2C0]
0x180007da6  mov     rdx, rbx
0x180007da9  call    cs:__imp_?Copy@STRA@@QEAAJPEBDK@Z; STRA::Copy(char const *,ulong)
0x180007daf  lea     rcx, [rsp+310h+var_2C0]
0x180007db4  mov     ebx, eax
0x180007db6  test    eax, eax
0x180007db8  js      loc_18000801C
0x180007dbe  call    cs:__imp_?QueryStr@STRA@@QEAAPEADXZ; STRA::QueryStr(void)
0x180007dc4  mov     rbx, rax
0x180007dc7  lea     rdx, Control; "\r\n"
0x180007dce  mov     rcx, rbx; Str
0x180007dd1  call    cs:__imp_strcspn
0x180007dd7  add     rbx, rax
0x180007dda  cmp     byte ptr [rbx], 0
0x180007ddd  jnz     loc_180008033
0x180007de3  inc     dword ptr [r14+270h]
0x180007dea  mov     [rsp+310h+var_28], r12
0x180007df2  mov     r12d, dword ptr [rbp+210h+arg_20]
0x180007df9  mov     [rsp+310h+var_30], r13
0x180007e01  movsxd  r13, esi
0x180007e04  add     r13, 7
0x180007e08  shl     r13, 4
0x180007e0c  add     r13, r14
0x180007e0f  test    r12d, r12d
0x180007e12  jz      loc_180007F45
0x180007e18  lea     rcx, [rsp+310h+var_2C0]
0x180007e1d  call    cs:__imp_?QueryStr@STRA@@QEAAPEADXZ; STRA::QueryStr(void)
0x180007e23  lea     rcx, [rsp+310h+var_2C0]
0x180007e28  mov     rbx, rax
0x180007e2b  call    cs:__imp_?QueryCCH@STRA@@QEBAKXZ; STRA::QueryCCH(void)
0x180007e31  mov     rcx, [r14+30h]
0x180007e35  movzx   eax, ax
0x180007e38  mov     [rsp+310h+var_2E0], eax
0x180007e3c  mov     [rsp+310h+var_38], r15
0x180007e44  lea     edi, [rax+1]
0x180007e47  mov     rax, [rcx]
0x180007e4a  mov     edx, edi
0x180007e4c  mov     rax, [rax+90h]
0x180007e53  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007e58  mov     r15, rax
0x180007e5b  test    rax, rax
0x180007e5e  jz      loc_180007FD6
0x180007e64  mov     eax, 7FFFFFFEh
0x180007e69  mov     r8d, edi
0x180007e6c  mov     rdx, r15
0x180007e6f  nop
0x180007e70  test    rax, rax
0x180007e73  jz      short loc_180007E8D
0x180007e75  movzx   ecx, byte ptr [rbx]
0x180007e78  test    cl, cl
0x180007e7a  jz      short loc_180007E8D
0x180007e7c  mov     [rdx], cl
0x180007e7e  inc     rbx
0x180007e81  inc     rdx
0x180007e84  dec     rax
0x180007e87  sub     r8, 1
0x180007e8b  jnz     short loc_180007E70
0x180007e8d  test    r8, r8
0x180007e90  lea     rax, [rdx-1]
0x180007e94  cmovnz  rax, rdx
0x180007e98  mov     byte ptr [rax], 0
0x180007e9b  cmp     esi, 1
0x180007e9e  jz      loc_180008097
0x180007ea4  mov     eax, [rsp+310h+var_2E0]
0x180007ea8  lea     rdx, [rsp+310h+var_2D8]
0x180007ead  mov     [r13+0], ax
0x180007eb2  xorps   xmm0, xmm0
0x180007eb5  xor     eax, eax
0x180007eb7  mov     [r13+8], r15
0x180007ebb  mov     rcx, [r14+30h]
0x180007ebf  test    rcx, rcx
0x180007ec2  movdqu  [rsp+310h+var_2D0], xmm0
0x180007ec8  lea     r8, [rcx+8]
0x180007ecc  cmovz   r8, rax
0x180007ed0  lea     rax, ?ProviderGuid@?1??GetProviderGuid@WWWServerTraceProvider@@SAPEBU_GUID@@XZ@4U3@B; _GUID const `WWWServerTraceProvider::GetProviderGuid(void)'::`2'::ProviderGuid
0x180007ed7  mov     [rsp+310h+var_2D8], rax
0x180007edc  mov     rcx, r8
0x180007edf  mov     rax, [r8]
0x180007ee2  mov     rax, [rax]
0x180007ee5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007eea  test    eax, eax
0x180007eec  js      short loc_180007EF9
0x180007eee  cmp     dword ptr [rsp+310h+var_2D0+4], 4
0x180007ef3  jnb     loc_180008121
0x180007ef9  lea     rcx, [rsp+310h+var_2C0]
0x180007efe  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x180007f04  lea     rcx, [rbp+210h+var_288]
0x180007f08  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x180007f0e  xor     eax, eax
0x180007f10  mov     r15, [rsp+310h+var_38]
0x180007f18  mov     r12, [rsp+310h+var_28]
0x180007f20  mov     r13, [rsp+310h+var_30]
0x180007f28  mov     rcx, [rbp+210h+var_50]
0x180007f2f  xor     rcx, rsp; StackCookie
0x180007f32  call    __security_check_cookie
0x180007f37  add     rsp, 2F0h
0x180007f3e  pop     r14
0x180007f40  pop     rdi
0x180007f41  pop     rsi
0x180007f42  pop     rbx
0x180007f43  pop     rbp
0x180007f44  retn
0x180007f45  mov     rdx, [r13+8]
0x180007f49  test    rdx, rdx
0x180007f4c  jz      loc_180007E18
0x180007f52  movzx   r8d, word ptr [r13+0]
0x180007f57  lea     rcx, [rbp+210h+var_288]
0x180007f5b  call    cs:__imp_?Copy@STRA@@QEAAJPEBDK@Z; STRA::Copy(char const *,ulong)
0x180007f61  mov     ebx, eax
0x180007f63  test    eax, eax
0x180007f65  js      loc_1800080FD
0x180007f6b  mov     r8d, 1
0x180007f71  lea     rdx, asc_180039188; ","
0x180007f78  lea     rcx, [rbp+210h+var_288]
0x180007f7c  call    cs:__imp_?Append@STRA@@QEAAJPEBDK@Z; STRA::Append(char const *,ulong)
0x180007f82  lea     rcx, [rsp+310h+var_2C0]
0x180007f87  mov     ebx, eax
0x180007f89  test    eax, eax
0x180007f8b  js      loc_180008102
0x180007f91  call    cs:__imp_?QueryStr@STRA@@QEAAPEADXZ; STRA::QueryStr(void)
0x180007f97  mov     rdx, rax
0x180007f9a  lea     rcx, [rbp+210h+var_288]
0x180007f9e  call    cs:__imp_?Append@STRA@@QEAAJPEBD@Z; STRA::Append(char const *)
0x180007fa4  mov     ebx, eax
0x180007fa6  test    eax, eax
0x180007fa8  js      loc_1800080FD
0x180007fae  lea     rcx, [rbp+210h+var_288]
0x180007fb2  call    cs:__imp_?QueryCCH@STRA@@QEBAKXZ; STRA::QueryCCH(void)
0x180007fb8  cmp     eax, 0FFFFh
0x180007fbd  ja      loc_180008078
0x180007fc3  lea     rcx, [rbp+210h+var_288]
0x180007fc7  call    cs:__imp_?QueryStr@STRA@@QEAAPEADXZ; STRA::QueryStr(void)
0x180007fcd  lea     rcx, [rbp+210h+var_288]
0x180007fd1  jmp     loc_180007E28
0x180007fd6  lea     rcx, [rsp+310h+var_2C0]
0x180007fdb  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x180007fe1  lea     rcx, [rbp+210h+var_288]
0x180007fe5  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x180007feb  mov     eax, 80070008h
0x180007ff0  jmp     loc_180007F10
0x180007ff5  lea     rdx, aWwwAuthenticat; "WWW-Authenticate"
0x180007ffc  mov     eax, dword ptr [rbp+210h+arg_20]
0x180008002  movzx   r9d, di; unsigned __int16
0x180008006  mov     r8, rbx; char *
0x180008009  mov     dword ptr [rsp+310h+var_2F0], eax; int
0x18000800d  mov     rcx, r14; this
0x180008010  call    ?SetHeader@W3_RESPONSE@@QEAAJPEBD0GH@Z; W3_RESPONSE::SetHeader(char const *,char const *,ushort,int)
0x180008015  mov     ebx, eax
0x180008017  lea     rcx, [rsp+310h+var_2C0]
0x18000801c  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x180008022  lea     rcx, [rbp+210h+var_288]
0x180008026  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x18000802c  mov     eax, ebx
0x18000802e  jmp     loc_180007F28
0x180008033  inc     rbx
0x180008036  movsx   eax, byte ptr [rbx]
0x180008039  cmp     al, 0Dh
0x18000803b  jz      loc_180008119
0x180008041  cmp     al, 0Ah
0x180008043  jz      loc_180008119
0x180008049  mov     ecx, eax; C
0x18000804b  call    cs:__imp_isspace
0x180008051  test    eax, eax
0x180008053  jnz     loc_180007DC7
0x180008059  lea     rcx, [rsp+310h+var_2C0]
0x18000805e  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x180008064  lea     rcx, [rbp+210h+var_288]
0x180008068  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x18000806e  mov     eax, 80070057h
0x180008073  jmp     loc_180007F28
0x180008078  lea     rcx, [rsp+310h+var_2C0]
0x18000807d  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x180008083  lea     rcx, [rbp+210h+var_288]
0x180008087  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x18000808d  mov     eax, 8007000Dh
0x180008092  jmp     loc_180007F18
0x180008097  lea     rdx, aClose; "close"
0x18000809e  mov     rcx, r15; String1
0x1800080a1  call    cs:__imp__stricmp
0x1800080a7  test    eax, eax
0x1800080a9  jnz     loc_180007EA4
0x1800080af  mov     rax, [r14+30h]
0x1800080b3  mov     rcx, [rax+188h]
0x1800080ba  mov     byte ptr [rcx+2483h], 1
0x1800080c1  jmp     loc_180007EA4
0x1800080c6  lea     rdx, aSetCookie; "Set-Cookie"
0x1800080cd  jmp     loc_180007FFC
0x1800080d2  lea     rdx, aServer_0; "Server"
0x1800080d9  jmp     loc_180007FFC
0x1800080de  lea     rcx, [rsp+310h+var_2C0]
0x1800080e3  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x1800080e9  lea     rcx, [rbp+210h+var_288]
0x1800080ed  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x1800080f3  mov     eax, 80070585h
0x1800080f8  jmp     loc_180007F28
0x1800080fd  lea     rcx, [rsp+310h+var_2C0]
0x180008102  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x180008108  lea     rcx, [rbp+210h+var_288]
0x18000810c  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x180008112  mov     eax, ebx
0x180008114  jmp     loc_180007F18
0x180008119  inc     rbx
0x18000811c  jmp     loc_180008036
0x180008121  cmp     dword ptr [rsp+310h+var_2D0+8], 0
0x180008126  jz      loc_180007EF9
0x18000812c  mov     rdx, [r14+30h]; struct _GUID *
0x180008130  lea     r10, ?sm_rgHeaders@RESPONSE_HEADER_HASH@@0PAUHEADER_RECORD@@A; HEADER_RECORD near * RESPONSE_HEADER_HASH::sm_rgHeaders
0x180008137  xor     eax, eax
0x180008139  mov     dword ptr [rsp+310h+var_2F0], r12d; char
0x18000813e  mov     r8, rsi
0x180008141  mov     r9, r15; char *
0x180008144  shl     r8, 5
0x180008148  test    rdx, rdx
0x18000814b  lea     rcx, [rdx+8]
0x18000814f  cmovz   rcx, rax; struct IHttpTraceContext *
0x180008153  mov     r8, [r8+r10]; char *
0x180008157  call    ?RaiseEvent@GENERAL_SET_RESPONSE_HEADER@IISGeneralEvents@@SAJPEAVIHttpTraceContext@@PEBU_GUID@@PEBD2H@Z; IISGeneralEvents::GENERAL_SET_RESPONSE_HEADER::RaiseEvent(IHttpTraceContext *,_GUID const *,char const *,char const *,int)
0x18000815c  jmp     loc_180007EF9
```
