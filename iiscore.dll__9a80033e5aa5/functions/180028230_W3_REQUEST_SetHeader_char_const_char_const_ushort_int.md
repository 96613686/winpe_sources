# W3_REQUEST::SetHeader(char const *,char const *,ushort,int)

- ea: `0x180028230`
- end: `0x1800286dc`
- name: `?SetHeader@W3_REQUEST@@QEAAJPEBD0GH@Z`
- size: `1196`
- prototype: `__int64 __fastcall(W3_REQUEST *this, const char *, const char *, unsigned __int16, int)`
- caller_count: `2`
- callee_count: `8`
- tags: `file_ops`

## callers

- `0x1800226d0`
- `0x180022a40`

## callees

- `0x180010420`
- `0x1800117f0`
- `0x1800159e0`
- `0x180016980`
- `0x180028230`
- `0x18003438e`
- `0x1800343f0`
- `0x180035010`

## import_xrefs

- `msvcrt!isspace` at `0x180028333`
- `msvcrt!isspace` at `0x180028333`
- `msvcrt!strcspn` at `0x1800282ba`
- `msvcrt!strcspn` at `0x180028310`
- `msvcrt!strcspn` at `0x1800282ba`
- `msvcrt!strcspn` at `0x180028310`
- `msvcrt!_stricmp` at `0x18002851c`
- `msvcrt!_stricmp` at `0x18002851c`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x1800285f9`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180028654`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180028678`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x1800285f9`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180028654`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180028678`
- `iisutil!??0STRA@@QEAA@PEADK@Z` at `0x18002827c`
- `iisutil!??0STRA@@QEAA@PEADK@Z` at `0x180028291`
- `iisutil!??0STRA@@QEAA@PEADK@Z` at `0x18002827c`
- `iisutil!??0STRA@@QEAA@PEADK@Z` at `0x180028291`
- `iisutil!??1STRA@@QEAA@XZ` at `0x1800282e2`
- `iisutil!??1STRA@@QEAA@XZ` at `0x1800282ed`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180028342`
- `iisutil!??1STRA@@QEAA@XZ` at `0x18002834d`
- `iisutil!??1STRA@@QEAA@XZ` at `0x1800286ba`
- `iisutil!??1STRA@@QEAA@XZ` at `0x1800286c5`
- `iisutil!??1STRA@@QEAA@XZ` at `0x1800282e2`
- `iisutil!??1STRA@@QEAA@XZ` at `0x1800282ed`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180028342`
- `iisutil!??1STRA@@QEAA@XZ` at `0x18002834d`
- `iisutil!??1STRA@@QEAA@XZ` at `0x1800286ba`
- `iisutil!??1STRA@@QEAA@XZ` at `0x1800286c5`
- `iisutil!?QueryStr@STRA@@QEAAPEADXZ` at `0x1800282f7`
- `iisutil!?QueryStr@STRA@@QEAAPEADXZ` at `0x180028384`
- `iisutil!?QueryStr@STRA@@QEAAPEADXZ` at `0x18002844c`
- `iisutil!?QueryStr@STRA@@QEAAPEADXZ` at `0x18002845e`
- `iisutil!?QueryStr@STRA@@QEAAPEADXZ` at `0x1800282f7`
- `iisutil!?QueryStr@STRA@@QEAAPEADXZ` at `0x180028384`
- `iisutil!?QueryStr@STRA@@QEAAPEADXZ` at `0x18002844c`
- `iisutil!?QueryStr@STRA@@QEAAPEADXZ` at `0x18002845e`
- `iisutil!?Copy@STRA@@QEAAJPEBDK@Z` at `0x1800282d1`
- `iisutil!?Copy@STRA@@QEAAJPEBDK@Z` at `0x1800283e7`
- `iisutil!?Copy@STRA@@QEAAJPEBDK@Z` at `0x1800282d1`
- `iisutil!?Copy@STRA@@QEAAJPEBDK@Z` at `0x1800283e7`
- `iisutil!?QueryCCH@STRA@@QEBAKXZ` at `0x180028433`
- `iisutil!?QueryCCH@STRA@@QEBAKXZ` at `0x18002846c`
- `iisutil!?QueryCCH@STRA@@QEBAKXZ` at `0x180028433`
- `iisutil!?QueryCCH@STRA@@QEBAKXZ` at `0x18002846c`
- `iisutil!?Resize@BUFFER@@QEAA_NKK@Z` at `0x180028629`
- `iisutil!?Resize@BUFFER@@QEAA_NKK@Z` at `0x180028629`
- `iisutil!?Append@STRA@@QEAAJPEBDK@Z` at `0x18002840c`
- `iisutil!?Append@STRA@@QEAAJPEBDK@Z` at `0x18002840c`
- `iisutil!?Append@STRA@@QEAAJAEBV1@@Z` at `0x180028422`
- `iisutil!?Append@STRA@@QEAAJAEBV1@@Z` at `0x180028422`

## pseudocode

```c
__int64 __fastcall W3_REQUEST::SetHeader(W3_REQUEST *this, const char *a2, const char *a3, unsigned __int16 a4, int a5)
{
  unsigned int v6; // r14d
  int v9; // ebx
  const char *Str; // rbx
  const char *v12; // rbx
  const char *v13; // rax
  signed int Index; // eax
  __int64 v15; // r14
  const char *Header; // rax
  char *v17; // rax
  STRA *v18; // rcx
  const char *v19; // rbx
  unsigned __int16 CCH; // ax
  __int64 v21; // rcx
  unsigned int v22; // r13d
  char *v23; // rax
  char *v24; // r12
  unsigned __int16 v25; // r13
  __int64 v26; // rcx
  unsigned __int16 v27; // r13
  int v28; // r14d
  __int64 v29; // rbx
  __int64 v30; // r15
  __int64 v31; // rax
  __int64 v32; // rcx
  __int64 v33; // r15
  char *v34; // rax
  char *v35; // r13
  BOOL v36; // ebx
  void *v37; // rdi
  unsigned int v38; // edi
  __int64 v39; // r14
  const void *v40; // rdi
  void *Ptr; // rax
  void *v42; // rax
  __int64 v43; // rdx
  __int64 v44; // rcx
  unsigned __int16 v45[4]; // [rsp+20h] [rbp-E0h] BYREF
  char *v46; // [rsp+28h] [rbp-D8h]
  _BYTE v47[56]; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v48[56]; // [rsp+68h] [rbp-98h] BYREF
  char v49[256]; // [rsp+A0h] [rbp-60h] BYREF
  char v50[256]; // [rsp+1A0h] [rbp+A0h] BYREF

  v6 = a4;
  STRA::STRA((STRA *)v48, v49, 0x100u);
  STRA::STRA((STRA *)v47, v50, 0x100u);
  v45[0] = 0;
  if ( a2 && a3 && !a2[strcspn(a2, "\r\n")] )
  {
    v9 = STRA::Copy((STRA *)v47, a3, v6);
    if ( v9 < 0 )
    {
LABEL_5:
      STRA::~STRA((STRA *)v47);
      STRA::~STRA((STRA *)v48);
      return (unsigned int)v9;
    }
    Str = STRA::QueryStr((STRA *)v47);
    while ( 1 )
    {
      v12 = &Str[strcspn(Str, "\r\n")];
      if ( !*v12 )
        break;
      for ( Str = v12 + 1; *Str == 13 || *Str == 10; ++Str )
        ;
      if ( !isspace(*Str) )
        goto LABEL_13;
    }
    ++*((_DWORD *)this + 12);
    v13 = STRA::QueryStr((STRA *)v47);
    W3_REQUEST::TraceSetHeader(this, a2, v13, a5);
    Index = REQUEST_HEADER_HASH::GetIndex(a2);
    v15 = Index;
    if ( a5 || Index == -1 || (Header = W3_REQUEST::QueryHeader(this, Index, v45)) == 0 )
    {
      v17 = STRA::QueryStr((STRA *)v47);
      v18 = (STRA *)v47;
    }
    else
    {
      v9 = STRA::Copy((STRA *)v48, Header, v45[0]);
      if ( v9 < 0 )
        goto LABEL_5;
      v9 = STRA::Append((STRA *)v48, ",", 1u);
      if ( v9 < 0 )
        goto LABEL_5;
      v9 = STRA::Append((STRA *)v48, (const struct STRA *)v47);
      if ( v9 < 0 )
        goto LABEL_5;
      if ( STRA::QueryCCH((STRA *)v48) > 0xFFFF )
      {
        v9 = -2147024883;
        goto LABEL_5;
      }
      v17 = STRA::QueryStr((STRA *)v48);
      v18 = (STRA *)v48;
    }
    v19 = v17;
    CCH = STRA::QueryCCH(v18);
    v21 = *((_QWORD *)this + 14);
    *(_DWORD *)v45 = CCH;
    v22 = CCH + 1;
    v23 = (char *)(*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v21 + 144LL))(v21, v22);
    v46 = v23;
    v24 = v23;
    if ( !v23 )
      goto LABEL_48;
    StringCchCopyA(v23, v22, v19);
    if ( (_DWORD)v15 != -1 )
    {
      v25 = v45[0];
      *(_QWORD *)(*((_QWORD *)this + 5) + 16 * (v15 + 10)) = v24;
      *(_WORD *)(*((_QWORD *)this + 5) + 16 * v15 + 152) = v25;
LABEL_28:
      v9 = 0;
      goto LABEL_5;
    }
    if ( a5 )
    {
      v26 = *((_QWORD *)this + 5);
      if ( *(_WORD *)(v26 + 120) )
      {
        v27 = v45[0];
        v28 = 0;
        v29 = 0;
        do
        {
          v30 = 3 * v29;
          if ( !_stricmp(a2, *(const char **)(*(_QWORD *)(v26 + 128) + 24 * v29 + 8)) )
          {
            v31 = *((_QWORD *)this + 5);
            v32 = *(_QWORD *)(v31 + 128);
            if ( v28 )
            {
              memmove_0(
                (void *)(v32 + 24 * v29),
                (const void *)(v32 + 24 * v29 + 24),
                24LL * (*(unsigned __int16 *)(v31 + 120) - (unsigned int)v29 - 1));
              --*(_WORD *)(*((_QWORD *)this + 5) + 120LL);
            }
            else
            {
              *(_QWORD *)(v32 + 24 * v29 + 16) = v24;
              v28 = 1;
              v29 = (unsigned int)(v29 + 1);
              *(_WORD *)(*(_QWORD *)(*((_QWORD *)this + 5) + 128LL) + 8 * v30 + 2) = v27;
            }
          }
          else
          {
            v29 = (unsigned int)(v29 + 1);
          }
          v26 = *((_QWORD *)this + 5);
        }
        while ( (unsigned int)v29 < *(unsigned __int16 *)(v26 + 120) );
        if ( v28 )
          goto LABEL_28;
      }
    }
    v33 = -1;
    do
      ++v33;
    while ( a2[v33] );
    v34 = (char *)(*(__int64 (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 14) + 144LL))(
                    *((_QWORD *)this + 14),
                    (unsigned int)(v33 + 1));
    v35 = v34;
    if ( !v34 )
      goto LABEL_48;
    v36 = 0;
    StringCchCopyA(v34, (unsigned int)(v33 + 1), a2);
    v37 = *(void **)(*((_QWORD *)this + 5) + 128LL);
    if ( v37 )
      v36 = BUFFER::QueryPtr((W3_REQUEST *)((char *)this + 168)) != v37;
    v38 = *(unsigned __int16 *)(*((_QWORD *)this + 5) + 120LL);
    if ( !BUFFER::Resize((W3_REQUEST *)((char *)this + 168), 24 * (v38 + 1), 0x200u) )
    {
LABEL_48:
      v9 = -2147024888;
      goto LABEL_5;
    }
    v39 = v38;
    if ( v36 )
    {
      v40 = *(const void **)(*((_QWORD *)this + 5) + 128LL);
      Ptr = BUFFER::QueryPtr((W3_REQUEST *)((char *)this + 168));
      memmove_0(Ptr, v40, 24 * v39);
    }
    ++*(_WORD *)(*((_QWORD *)this + 5) + 120LL);
    v42 = BUFFER::QueryPtr((W3_REQUEST *)((char *)this + 168));
    v43 = 3 * v39;
    *(_QWORD *)(*((_QWORD *)this + 5) + 128LL) = v42;
    v44 = *(_QWORD *)(*((_QWORD *)this + 5) + 128LL);
    *(_QWORD *)(v44 + 8 * v43 + 16) = v46;
    *(_WORD *)(v44 + 8 * v43 + 2) = v45[0];
    *(_QWORD *)(v44 + 8 * v43 + 8) = v35;
    *(_WORD *)(v44 + 8 * v43) = v33;
    STRA::~STRA((STRA *)v47);
    STRA::~STRA((STRA *)v48);
    return 0;
  }
  else
  {
LABEL_13:
    STRA::~STRA((STRA *)v47);
    STRA::~STRA((STRA *)v48);
    return 2147942487LL;
  }
}

```

## disassembly

```asm
0x180028230  push    rbp
0x180028232  push    rbx
0x180028233  push    rsi
0x180028234  push    rdi
0x180028235  push    r12
0x180028237  push    r13
0x180028239  push    r14
0x18002823b  push    r15
0x18002823d  lea     rbp, [rsp-1B8h]
0x180028245  sub     rsp, 2B8h
0x18002824c  mov     rax, cs:__security_cookie
0x180028253  xor     rax, rsp
0x180028256  mov     [rbp+1F0h+var_50], rax
0x18002825d  mov     rbx, r8
0x180028260  movzx   r14d, r9w
0x180028264  mov     rdi, rdx
0x180028267  mov     rsi, rcx
0x18002826a  mov     r15d, 100h
0x180028270  lea     rdx, [rbp+1F0h+var_250]
0x180028274  mov     r8d, r15d
0x180028277  lea     rcx, [rsp+2F0h+var_288]
0x18002827c  call    cs:__imp_??0STRA@@QEAA@PEADK@Z; STRA::STRA(char *,ulong)
0x180028282  mov     r8d, r15d
0x180028285  lea     rdx, [rbp+1F0h+var_150]
0x18002828c  lea     rcx, [rsp+2F0h+var_2C0]
0x180028291  call    cs:__imp_??0STRA@@QEAA@PEADK@Z; STRA::STRA(char *,ulong)
0x180028297  xor     eax, eax
0x180028299  mov     [rsp+2F0h+var_2D0], ax
0x18002829e  test    rdi, rdi
0x1800282a1  jz      loc_18002833D
0x1800282a7  test    rbx, rbx
0x1800282aa  jz      loc_18002833D
0x1800282b0  lea     rdx, Control; "\r\n"
0x1800282b7  mov     rcx, rdi; Str
0x1800282ba  call    cs:__imp_strcspn
0x1800282c0  cmp     byte ptr [rax+rdi], 0
0x1800282c4  jnz     short loc_18002833D
0x1800282c6  mov     r8d, r14d
0x1800282c9  lea     rcx, [rsp+2F0h+var_2C0]
0x1800282ce  mov     rdx, rbx
0x1800282d1  call    cs:__imp_?Copy@STRA@@QEAAJPEBDK@Z; STRA::Copy(char const *,ulong)
0x1800282d7  lea     rcx, [rsp+2F0h+var_2C0]
0x1800282dc  mov     ebx, eax
0x1800282de  test    eax, eax
0x1800282e0  jns     short loc_1800282F7
0x1800282e2  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x1800282e8  lea     rcx, [rsp+2F0h+var_288]
0x1800282ed  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x1800282f3  mov     eax, ebx
0x1800282f5  jmp     short loc_180028358
0x1800282f7  call    cs:__imp_?QueryStr@STRA@@QEAAPEADXZ; STRA::QueryStr(void)
0x1800282fd  mov     rbx, rax
0x180028300  mov     r12d, 1
0x180028306  lea     rdx, Control; "\r\n"
0x18002830d  mov     rcx, rbx; Str
0x180028310  call    cs:__imp_strcspn
0x180028316  add     rbx, rax
0x180028319  cmp     byte ptr [rbx], 0
0x18002831c  jz      short loc_18002837B
0x18002831e  inc     rbx
0x180028321  cmp     byte ptr [rbx], 0Dh
0x180028324  jz      short loc_18002832B
0x180028326  cmp     byte ptr [rbx], 0Ah
0x180028329  jnz     short loc_180028330
0x18002832b  add     rbx, r12
0x18002832e  jmp     short loc_180028321
0x180028330  movsx   ecx, byte ptr [rbx]; C
0x180028333  call    cs:__imp_isspace
0x180028339  test    eax, eax
0x18002833b  jnz     short loc_180028306
0x18002833d  lea     rcx, [rsp+2F0h+var_2C0]
0x180028342  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x180028348  lea     rcx, [rsp+2F0h+var_288]
0x18002834d  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x180028353  mov     eax, 80070057h
0x180028358  mov     rcx, [rbp+1F0h+var_50]
0x18002835f  xor     rcx, rsp; StackCookie
0x180028362  call    __security_check_cookie
0x180028367  add     rsp, 2B8h
0x18002836e  pop     r15
0x180028370  pop     r14
0x180028372  pop     r13
0x180028374  pop     r12
0x180028376  pop     rdi
0x180028377  pop     rsi
0x180028378  pop     rbx
0x180028379  pop     rbp
0x18002837a  retn
0x18002837b  add     [rsi+30h], r12d
0x18002837f  lea     rcx, [rsp+2F0h+var_2C0]
0x180028384  call    cs:__imp_?QueryStr@STRA@@QEAAPEADXZ; STRA::QueryStr(void)
0x18002838a  mov     r15d, [rbp+1F0h+arg_20]
0x180028391  mov     rdx, rdi; char *
0x180028394  mov     r8, rax; char *
0x180028397  mov     r9d, r15d; int
0x18002839a  mov     rcx, rsi; this
0x18002839d  call    ?TraceSetHeader@W3_REQUEST@@AEAAXPEBD0H@Z; W3_REQUEST::TraceSetHeader(char const *,char const *,int)
0x1800283a2  mov     rcx, rdi; char *
0x1800283a5  call    ?GetIndex@REQUEST_HEADER_HASH@@SAKPEBD@Z; REQUEST_HEADER_HASH::GetIndex(char const *)
0x1800283aa  movsxd  r14, eax
0x1800283ad  test    r15d, r15d
0x1800283b0  jnz     loc_180028459
0x1800283b6  cmp     r14d, 0FFFFFFFFh
0x1800283ba  jz      loc_180028459
0x1800283c0  lea     r8, [rsp+2F0h+var_2D0]; unsigned __int16 *
0x1800283c5  mov     edx, r14d; enum _HTTP_HEADER_ID
0x1800283c8  mov     rcx, rsi; this
0x1800283cb  call    ?QueryHeader@W3_REQUEST@@QEBAPEBDW4_HTTP_HEADER_ID@@PEAG@Z; W3_REQUEST::QueryHeader(_HTTP_HEADER_ID,ushort *)
0x1800283d0  test    rax, rax
0x1800283d3  jz      loc_180028459
0x1800283d9  movzx   r8d, [rsp+2F0h+var_2D0]
0x1800283df  lea     rcx, [rsp+2F0h+var_288]
0x1800283e4  mov     rdx, rax
0x1800283e7  call    cs:__imp_?Copy@STRA@@QEAAJPEBDK@Z; STRA::Copy(char const *,ulong)
0x1800283ed  mov     ebx, eax
0x1800283ef  test    eax, eax
0x1800283f1  jns     short loc_1800283FD
0x1800283f3  lea     rcx, [rsp+2F0h+var_2C0]
0x1800283f8  jmp     loc_1800282E2
0x1800283fd  mov     r8d, r12d
0x180028400  lea     rdx, asc_180039188; ","
0x180028407  lea     rcx, [rsp+2F0h+var_288]
0x18002840c  call    cs:__imp_?Append@STRA@@QEAAJPEBDK@Z; STRA::Append(char const *,ulong)
0x180028412  mov     ebx, eax
0x180028414  test    eax, eax
0x180028416  js      short loc_1800283F3
0x180028418  lea     rdx, [rsp+2F0h+var_2C0]
0x18002841d  lea     rcx, [rsp+2F0h+var_288]
0x180028422  call    cs:__imp_?Append@STRA@@QEAAJAEBV1@@Z; STRA::Append(STRA const &)
0x180028428  mov     ebx, eax
0x18002842a  test    eax, eax
0x18002842c  js      short loc_1800283F3
0x18002842e  lea     rcx, [rsp+2F0h+var_288]
0x180028433  call    cs:__imp_?QueryCCH@STRA@@QEBAKXZ; STRA::QueryCCH(void)
0x180028439  cmp     eax, 0FFFFh
0x18002843e  jbe     short loc_180028447
0x180028440  mov     ebx, 8007000Dh
0x180028445  jmp     short loc_1800283F3
0x180028447  lea     rcx, [rsp+2F0h+var_288]
0x18002844c  call    cs:__imp_?QueryStr@STRA@@QEAAPEADXZ; STRA::QueryStr(void)
0x180028452  lea     rcx, [rsp+2F0h+var_288]
0x180028457  jmp     short loc_180028469
0x180028459  lea     rcx, [rsp+2F0h+var_2C0]
0x18002845e  call    cs:__imp_?QueryStr@STRA@@QEAAPEADXZ; STRA::QueryStr(void)
0x180028464  lea     rcx, [rsp+2F0h+var_2C0]
0x180028469  mov     rbx, rax
0x18002846c  call    cs:__imp_?QueryCCH@STRA@@QEBAKXZ; STRA::QueryCCH(void)
0x180028472  mov     rcx, [rsi+70h]
0x180028476  movzx   eax, ax
0x180028479  mov     dword ptr [rsp+2F0h+var_2D0], eax
0x18002847d  lea     r13d, [rax+1]
0x180028481  mov     rax, [rcx]
0x180028484  mov     edx, r13d
0x180028487  mov     rax, [rax+90h]
0x18002848e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028493  mov     [rsp+2F0h+var_2C8], rax
0x180028498  mov     r12, rax
0x18002849b  test    rax, rax
0x18002849e  jz      loc_1800286D2
0x1800284a4  mov     edx, r13d; unsigned __int64
0x1800284a7  mov     r8, rbx; char *
0x1800284aa  mov     rcx, rax; char *
0x1800284ad  call    ?StringCchCopyA@@YAJPEAD_KPEBD@Z; StringCchCopyA(char *,unsigned __int64,char const *)
0x1800284b2  cmp     r14d, 0FFFFFFFFh
0x1800284b6  jz      short loc_1800284E6
0x1800284b8  mov     rax, [rsi+28h]
0x1800284bc  lea     rcx, [r14+0Ah]
0x1800284c0  mov     r13d, dword ptr [rsp+2F0h+var_2D0]
0x1800284c5  add     rcx, rcx
0x1800284c8  mov     rdx, r14
0x1800284cb  add     rdx, rdx
0x1800284ce  mov     [rax+rcx*8], r12
0x1800284d2  mov     rax, [rsi+28h]
0x1800284d6  mov     [rax+rdx*8+98h], r13w
0x1800284df  xor     ebx, ebx
0x1800284e1  jmp     loc_1800283F3
0x1800284e6  test    r15d, r15d
0x1800284e9  jz      loc_18002859E
0x1800284ef  mov     rcx, [rsi+28h]
0x1800284f3  xor     eax, eax
0x1800284f5  cmp     ax, [rcx+78h]
0x1800284f9  jnb     loc_18002859E
0x1800284ff  mov     r13d, dword ptr [rsp+2F0h+var_2D0]
0x180028504  xor     r14d, r14d
0x180028507  xor     ebx, ebx
0x180028509  mov     rdx, [rcx+80h]
0x180028510  lea     r15, [rbx+rbx*2]
0x180028514  mov     rcx, rdi; String1
0x180028517  mov     rdx, [rdx+r15*8+8]; String2
0x18002851c  call    cs:__imp__stricmp
0x180028522  test    eax, eax
0x180028524  jnz     short loc_180028583
0x180028526  mov     rax, [rsi+28h]
0x18002852a  mov     rcx, [rax+80h]
0x180028531  test    r14d, r14d
0x180028534  jnz     short loc_180028557
0x180028536  mov     [rcx+r15*8+10h], r12
0x18002853b  mov     rax, [rsi+28h]
0x18002853f  mov     rcx, [rax+80h]
0x180028546  lea     eax, [r14+1]
0x18002854a  mov     r14d, eax
0x18002854d  add     ebx, eax
0x18002854f  mov     [rcx+r15*8+2], r13w
0x180028555  jmp     short loc_180028585
0x180028557  movzx   eax, word ptr [rax+78h]
0x18002855b  lea     rcx, [rcx+r15*8]; void *
0x18002855f  sub     eax, ebx
0x180028561  lea     rdx, [rcx+18h]; Src
0x180028565  dec     eax
0x180028567  lea     r8, [rax+rax*2]
0x18002856b  shl     r8, 3; Size
0x18002856f  call    memmove_0
0x180028574  mov     rax, [rsi+28h]
0x180028578  mov     ecx, 0FFFFh
0x18002857d  add     [rax+78h], cx
0x180028581  jmp     short loc_180028585
0x180028583  inc     ebx
0x180028585  mov     rcx, [rsi+28h]
0x180028589  movzx   eax, word ptr [rcx+78h]
0x18002858d  cmp     ebx, eax
0x18002858f  jb      loc_180028509
0x180028595  test    r14d, r14d
0x180028598  jnz     loc_1800284DF
0x18002859e  or      r15, 0FFFFFFFFFFFFFFFFh
0x1800285a2  inc     r15
0x1800285a5  cmp     byte ptr [rdi+r15], 0
0x1800285aa  jnz     short loc_1800285A2
0x1800285ac  mov     rcx, [rsi+70h]
0x1800285b0  lea     r14d, [r15+1]
0x1800285b4  mov     edx, r14d
0x1800285b7  mov     rax, [rcx]
0x1800285ba  mov     rax, [rax+90h]
0x1800285c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800285c6  mov     r13, rax
0x1800285c9  test    rax, rax
0x1800285cc  jz      loc_1800286D2
0x1800285d2  mov     edx, r14d; unsigned __int64
0x1800285d5  mov     r8, rdi; char *
0x1800285d8  mov     rcx, rax; char *
0x1800285db  xor     ebx, ebx
0x1800285dd  call    ?StringCchCopyA@@YAJPEAD_KPEBD@Z; StringCchCopyA(char *,unsigned __int64,char const *)
0x1800285e2  mov     rcx, [rsi+28h]
0x1800285e6  mov     rdi, [rcx+80h]
0x1800285ed  test    rdi, rdi
0x1800285f0  jz      short loc_180028608
0x1800285f2  lea     rcx, [rsi+0A8h]
0x1800285f9  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x1800285ff  cmp     rax, rdi
0x180028602  lea     eax, [rbx+1]
0x180028605  cmovnz  ebx, eax
0x180028608  mov     rax, [rsi+28h]
0x18002860c  lea     r12, [rsi+0A8h]
0x180028613  mov     r8d, 200h
0x180028619  mov     rcx, r12
0x18002861c  movzx   edi, word ptr [rax+78h]
0x180028620  lea     eax, [rdi+1]
0x180028623  lea     edx, [rax+rax*2]
0x180028626  shl     edx, 3
0x180028629  call    cs:__imp_?Resize@BUFFER@@QEAA_NKK@Z; BUFFER::Resize(ulong,ulong)
0x18002862f  test    al, al
0x180028631  jz      loc_1800286D2
0x180028637  mov     r14d, edi
0x18002863a  test    ebx, ebx
0x18002863c  jz      short loc_180028668
0x18002863e  mov     rax, [rsi+28h]
0x180028642  lea     rbx, [r14+r14*2]
0x180028646  mov     rcx, r12
0x180028649  shl     rbx, 3
0x18002864d  mov     rdi, [rax+80h]
0x180028654  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x18002865a  mov     r8, rbx; Size
0x18002865d  mov     rdx, rdi; Src
0x180028660  mov     rcx, rax; void *
0x180028663  call    memmove_0
0x180028668  mov     rax, [rsi+28h]
0x18002866c  mov     ecx, 1
0x180028671  add     [rax+78h], cx
0x180028675  mov     rcx, r12
0x180028678  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x18002867e  mov     rcx, [rsi+28h]
0x180028682  lea     rdx, [r14+r14*2]
0x180028686  mov     [rcx+80h], rax
0x18002868d  mov     rax, [rsi+28h]
0x180028691  mov     rcx, [rax+80h]
0x180028698  mov     rax, [rsp+2F0h+var_2C8]
0x18002869d  mov     [rcx+rdx*8+10h], rax
0x1800286a2  mov     eax, dword ptr [rsp+2F0h+var_2D0]
0x1800286a6  mov     [rcx+rdx*8+2], ax
0x1800286ab  mov     [rcx+rdx*8+8], r13
0x1800286b0  mov     [rcx+rdx*8], r15w
0x1800286b5  lea     rcx, [rsp+2F0h+var_2C0]
0x1800286ba  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x1800286c0  lea     rcx, [rsp+2F0h+var_288]
0x1800286c5  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x1800286cb  xor     eax, eax
0x1800286cd  jmp     loc_180028358
0x1800286d2  mov     ebx, 80070008h
0x1800286d7  jmp     loc_1800283F3
```
