# W3_REQUEST::SetHeader(_HTTP_HEADER_ID,char const *,ushort,int)

- ea: `0x1800286e4`
- end: `0x180028940`
- name: `?SetHeader@W3_REQUEST@@QEAAJW4_HTTP_HEADER_ID@@PEBDGH@Z`
- size: `604`
- prototype: `__int64 __fastcall(W3_REQUEST *this, enum _HTTP_HEADER_ID, const char *, unsigned __int16, int)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x1800226e0`

## callees

- `0x1800117f0`
- `0x1800162ec`
- `0x180016980`
- `0x1800286e4`
- `0x1800343f0`
- `0x180035010`

## import_xrefs

- `iisutil!??0STRA@@QEAA@PEADK@Z` at `0x180028730`
- `iisutil!??0STRA@@QEAA@PEADK@Z` at `0x180028745`
- `iisutil!??0STRA@@QEAA@PEADK@Z` at `0x180028730`
- `iisutil!??0STRA@@QEAA@PEADK@Z` at `0x180028745`
- `iisutil!??1STRA@@QEAA@XZ` at `0x1800288b5`
- `iisutil!??1STRA@@QEAA@XZ` at `0x1800288c0`
- `iisutil!??1STRA@@QEAA@XZ` at `0x1800288ed`
- `iisutil!??1STRA@@QEAA@XZ` at `0x1800288f8`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180028907`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180028912`
- `iisutil!??1STRA@@QEAA@XZ` at `0x1800288b5`
- `iisutil!??1STRA@@QEAA@XZ` at `0x1800288c0`
- `iisutil!??1STRA@@QEAA@XZ` at `0x1800288ed`
- `iisutil!??1STRA@@QEAA@XZ` at `0x1800288f8`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180028907`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180028912`
- `iisutil!?QueryStr@STRA@@QEAAPEADXZ` at `0x1800287a2`
- `iisutil!?QueryStr@STRA@@QEAAPEADXZ` at `0x18002885f`
- `iisutil!?QueryStr@STRA@@QEAAPEADXZ` at `0x180028871`
- `iisutil!?QueryStr@STRA@@QEAAPEADXZ` at `0x1800287a2`
- `iisutil!?QueryStr@STRA@@QEAAPEADXZ` at `0x18002885f`
- `iisutil!?QueryStr@STRA@@QEAAPEADXZ` at `0x180028871`
- `iisutil!?Copy@STRA@@QEAAJPEBDK@Z` at `0x18002877a`
- `iisutil!?Copy@STRA@@QEAAJPEBDK@Z` at `0x1800287f9`
- `iisutil!?Copy@STRA@@QEAAJPEBDK@Z` at `0x18002877a`
- `iisutil!?Copy@STRA@@QEAAJPEBDK@Z` at `0x1800287f9`
- `iisutil!?QueryCCH@STRA@@QEBAKXZ` at `0x180028846`
- `iisutil!?QueryCCH@STRA@@QEBAKXZ` at `0x18002887f`
- `iisutil!?QueryCCH@STRA@@QEBAKXZ` at `0x180028846`
- `iisutil!?QueryCCH@STRA@@QEBAKXZ` at `0x18002887f`
- `iisutil!?Append@STRA@@QEAAJPEBDK@Z` at `0x18002881b`
- `iisutil!?Append@STRA@@QEAAJPEBDK@Z` at `0x18002881b`
- `iisutil!?Append@STRA@@QEAAJAEBV1@@Z` at `0x180028835`
- `iisutil!?Append@STRA@@QEAAJAEBV1@@Z` at `0x180028835`

## pseudocode

```c
__int64 __fastcall W3_REQUEST::SetHeader(
        W3_REQUEST *this,
        enum _HTTP_HEADER_ID a2,
        const char *a3,
        unsigned __int16 a4,
        int a5)
{
  __int64 v6; // rsi
  unsigned int v8; // edi
  int v9; // ebx
  const char *String; // rax
  const char *v11; // r10
  __int64 v12; // r15
  __int64 v13; // rsi
  __int64 v14; // rdi
  const char *v15; // rdx
  char *Str; // rax
  STRA *v17; // rcx
  const char *v18; // rbx
  unsigned __int16 CCH; // ax
  __int64 v20; // rcx
  unsigned __int16 v21; // r13
  unsigned int v22; // r14d
  char *v23; // rax
  __int64 v25; // r10
  unsigned int v26; // [rsp+20h] [rbp-E0h] BYREF
  _BYTE v27[56]; // [rsp+28h] [rbp-D8h] BYREF
  _BYTE v28[64]; // [rsp+60h] [rbp-A0h] BYREF
  char v29[256]; // [rsp+A0h] [rbp-60h] BYREF
  char v30[256]; // [rsp+1A0h] [rbp+A0h] BYREF

  v6 = a2;
  v8 = a4;
  STRA::STRA((STRA *)v27, v29, 0x100u);
  STRA::STRA((STRA *)v28, v30, 0x100u);
  if ( (unsigned int)v6 > 0x28 )
  {
    STRA::~STRA((STRA *)v28);
    STRA::~STRA((STRA *)v27);
    return 2147943813LL;
  }
  else
  {
    if ( !a3 && (_WORD)v8 )
    {
      v9 = -2147024809;
LABEL_19:
      STRA::~STRA((STRA *)v28);
      STRA::~STRA((STRA *)v27);
      return (unsigned int)v9;
    }
    ++*((_DWORD *)this + 12);
    v9 = STRA::Copy((STRA *)v28, a3, v8);
    if ( v9 < 0 )
      goto LABEL_19;
    if ( *(_BYTE *)(*((_QWORD *)this + 14) + 9098LL) )
    {
      STRA::QueryStr((STRA *)v28);
      String = REQUEST_HEADER_HASH::GetString(v6, &v26);
      W3_REQUEST::TraceSetHeader(this, String, v11, a5);
    }
    v12 = *((_QWORD *)this + 5);
    v13 = 2 * v6;
    v14 = v12 + 8 * v13;
    if ( a5 || (v15 = *(const char **)(v14 + 160)) == 0 )
    {
      Str = STRA::QueryStr((STRA *)v28);
      v17 = (STRA *)v28;
    }
    else
    {
      v9 = STRA::Copy((STRA *)v27, v15, *(unsigned __int16 *)(v12 + 8 * v13 + 152));
      if ( v9 < 0 )
        goto LABEL_19;
      v9 = STRA::Append((STRA *)v27, ",", 1u);
      if ( v9 < 0 )
        goto LABEL_19;
      v9 = STRA::Append((STRA *)v27, (const struct STRA *)v28);
      if ( v9 < 0 )
        goto LABEL_19;
      if ( STRA::QueryCCH((STRA *)v27) > 0xFFFF )
      {
        v9 = -2147024883;
        goto LABEL_19;
      }
      Str = STRA::QueryStr((STRA *)v27);
      v17 = (STRA *)v27;
    }
    v18 = Str;
    CCH = STRA::QueryCCH(v17);
    v20 = *((_QWORD *)this + 14);
    v21 = CCH;
    v22 = CCH + 1;
    v23 = (char *)(*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v20 + 144LL))(v20, v22);
    if ( !v23 )
    {
      v9 = -2147024888;
      goto LABEL_19;
    }
    StringCchCopyA(v23, v22, v18);
    *(_QWORD *)(v14 + 160) = v25;
    *(_WORD *)(v12 + 8 * v13 + 152) = v21;
    STRA::~STRA((STRA *)v28);
    STRA::~STRA((STRA *)v27);
    return 0;
  }
}

```

## disassembly

```asm
0x1800286e4  push    rbp
0x1800286e6  push    rbx
0x1800286e7  push    rsi
0x1800286e8  push    rdi
0x1800286e9  push    r12
0x1800286eb  push    r13
0x1800286ed  push    r14
0x1800286ef  push    r15
0x1800286f1  lea     rbp, [rsp-1B8h]
0x1800286f9  sub     rsp, 2B8h
0x180028700  mov     rax, cs:__security_cookie
0x180028707  xor     rax, rsp
0x18002870a  mov     [rbp+1F0h+var_50], rax
0x180028711  mov     rbx, r8
0x180028714  movsxd  rsi, edx
0x180028717  mov     r14, rcx
0x18002871a  movzx   edi, r9w
0x18002871e  mov     r15d, 100h
0x180028724  lea     rdx, [rbp+1F0h+var_250]
0x180028728  mov     r8d, r15d
0x18002872b  lea     rcx, [rsp+2F0h+var_2C8]
0x180028730  call    cs:__imp_??0STRA@@QEAA@PEADK@Z; STRA::STRA(char *,ulong)
0x180028736  mov     r8d, r15d
0x180028739  lea     rdx, [rbp+1F0h+var_150]
0x180028740  lea     rcx, [rsp+2F0h+var_290]
0x180028745  call    cs:__imp_??0STRA@@QEAA@PEADK@Z; STRA::STRA(char *,ulong)
0x18002874b  cmp     esi, 28h ; '('
0x18002874e  ja      loc_180028902
0x180028754  xor     r12d, r12d
0x180028757  test    rbx, rbx
0x18002875a  jnz     short loc_18002876B
0x18002875c  test    di, di
0x18002875f  jz      short loc_18002876B
0x180028761  mov     ebx, 80070057h
0x180028766  jmp     loc_1800288B0
0x18002876b  inc     dword ptr [r14+30h]
0x18002876f  lea     rcx, [rsp+2F0h+var_290]
0x180028774  mov     r8d, edi
0x180028777  mov     rdx, rbx
0x18002877a  call    cs:__imp_?Copy@STRA@@QEAAJPEBDK@Z; STRA::Copy(char const *,ulong)
0x180028780  mov     ebx, eax
0x180028782  test    eax, eax
0x180028784  js      loc_1800288B0
0x18002878a  mov     rax, [r14+70h]
0x18002878e  mov     ebx, [rbp+1F0h+arg_20]
0x180028794  cmp     [rax+238Ah], r12b
0x18002879b  jz      short loc_1800287C8
0x18002879d  lea     rcx, [rsp+2F0h+var_290]
0x1800287a2  call    cs:__imp_?QueryStr@STRA@@QEAAPEADXZ; STRA::QueryStr(void)
0x1800287a8  lea     rdx, [rsp+2F0h+var_2D0]; unsigned int *
0x1800287ad  mov     ecx, esi; unsigned int
0x1800287af  mov     r10, rax
0x1800287b2  call    ?GetString@REQUEST_HEADER_HASH@@SAPEADKPEAK@Z; REQUEST_HEADER_HASH::GetString(ulong,ulong *)
0x1800287b7  mov     r8, r10; char *
0x1800287ba  mov     rdx, rax; char *
0x1800287bd  mov     rcx, r14; this
0x1800287c0  mov     r9d, ebx; int
0x1800287c3  call    ?TraceSetHeader@W3_REQUEST@@AEAAXPEBD0H@Z; W3_REQUEST::TraceSetHeader(char const *,char const *,int)
0x1800287c8  mov     r15, [r14+28h]
0x1800287cc  add     rsi, rsi
0x1800287cf  lea     rdi, [r15+rsi*8]
0x1800287d3  test    ebx, ebx
0x1800287d5  jnz     loc_18002886C
0x1800287db  mov     rdx, [rdi+0A0h]
0x1800287e2  test    rdx, rdx
0x1800287e5  jz      loc_18002886C
0x1800287eb  movzx   r8d, word ptr [r15+rsi*8+98h]
0x1800287f4  lea     rcx, [rsp+2F0h+var_2C8]
0x1800287f9  call    cs:__imp_?Copy@STRA@@QEAAJPEBDK@Z; STRA::Copy(char const *,ulong)
0x1800287ff  mov     ebx, eax
0x180028801  test    eax, eax
0x180028803  js      loc_1800288B0
0x180028809  mov     r8d, 1
0x18002880f  lea     rdx, asc_180039188; ","
0x180028816  lea     rcx, [rsp+2F0h+var_2C8]
0x18002881b  call    cs:__imp_?Append@STRA@@QEAAJPEBDK@Z; STRA::Append(char const *,ulong)
0x180028821  mov     ebx, eax
0x180028823  test    eax, eax
0x180028825  js      loc_1800288B0
0x18002882b  lea     rdx, [rsp+2F0h+var_290]
0x180028830  lea     rcx, [rsp+2F0h+var_2C8]
0x180028835  call    cs:__imp_?Append@STRA@@QEAAJAEBV1@@Z; STRA::Append(STRA const &)
0x18002883b  mov     ebx, eax
0x18002883d  test    eax, eax
0x18002883f  js      short loc_1800288B0
0x180028841  lea     rcx, [rsp+2F0h+var_2C8]
0x180028846  call    cs:__imp_?QueryCCH@STRA@@QEBAKXZ; STRA::QueryCCH(void)
0x18002884c  cmp     eax, 0FFFFh
0x180028851  jbe     short loc_18002885A
0x180028853  mov     ebx, 8007000Dh
0x180028858  jmp     short loc_1800288B0
0x18002885a  lea     rcx, [rsp+2F0h+var_2C8]
0x18002885f  call    cs:__imp_?QueryStr@STRA@@QEAAPEADXZ; STRA::QueryStr(void)
0x180028865  lea     rcx, [rsp+2F0h+var_2C8]
0x18002886a  jmp     short loc_18002887C
0x18002886c  lea     rcx, [rsp+2F0h+var_290]
0x180028871  call    cs:__imp_?QueryStr@STRA@@QEAAPEADXZ; STRA::QueryStr(void)
0x180028877  lea     rcx, [rsp+2F0h+var_290]
0x18002887c  mov     rbx, rax
0x18002887f  call    cs:__imp_?QueryCCH@STRA@@QEBAKXZ; STRA::QueryCCH(void)
0x180028885  mov     rcx, [r14+70h]
0x180028889  movzx   r13d, ax
0x18002888d  mov     rax, [rcx]
0x180028890  lea     r14d, [r13+1]
0x180028894  mov     edx, r14d
0x180028897  mov     rax, [rax+90h]
0x18002889e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800288a3  mov     r10, rax
0x1800288a6  test    rax, rax
0x1800288a9  jnz     short loc_1800288CA
0x1800288ab  mov     ebx, 80070008h
0x1800288b0  lea     rcx, [rsp+2F0h+var_290]
0x1800288b5  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x1800288bb  lea     rcx, [rsp+2F0h+var_2C8]
0x1800288c0  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x1800288c6  mov     eax, ebx
0x1800288c8  jmp     short loc_18002891D
0x1800288ca  mov     edx, r14d; unsigned __int64
0x1800288cd  mov     r8, rbx; char *
0x1800288d0  mov     rcx, r10; char *
0x1800288d3  call    ?StringCchCopyA@@YAJPEAD_KPEBD@Z; StringCchCopyA(char *,unsigned __int64,char const *)
0x1800288d8  lea     rcx, [rsp+2F0h+var_290]
0x1800288dd  mov     [rdi+0A0h], r10
0x1800288e4  mov     [r15+rsi*8+98h], r13w
0x1800288ed  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x1800288f3  lea     rcx, [rsp+2F0h+var_2C8]
0x1800288f8  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x1800288fe  xor     eax, eax
0x180028900  jmp     short loc_18002891D
0x180028902  lea     rcx, [rsp+2F0h+var_290]
0x180028907  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x18002890d  lea     rcx, [rsp+2F0h+var_2C8]
0x180028912  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x180028918  mov     eax, 80070585h
0x18002891d  mov     rcx, [rbp+1F0h+var_50]
0x180028924  xor     rcx, rsp; StackCookie
0x180028927  call    __security_check_cookie
0x18002892c  add     rsp, 2B8h
0x180028933  pop     r15
0x180028935  pop     r14
0x180028937  pop     r13
0x180028939  pop     r12
0x18002893b  pop     rdi
0x18002893c  pop     rsi
0x18002893d  pop     rbx
0x18002893e  pop     rbp
0x18002893f  retn
```
