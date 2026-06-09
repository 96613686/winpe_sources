# W3_REQUEST::SetHeader(char const *,char const *,ushort,int)

- ea: `0x18002a430`
- end: `0x18002a97d`
- name: `?SetHeader@W3_REQUEST@@QEAAJPEBD0GH@Z`
- size: `1357`
- prototype: `__int64 __fastcall(W3_REQUEST *this, const char *, const char *, unsigned __int16, int)`
- caller_count: `2`
- callee_count: `8`
- tags: `file_ops`

## callers

- `0x180024360`
- `0x180024710`

## callees

- `0x1800111a0`
- `0x1800126f0`
- `0x180016b40`
- `0x180017d40`
- `0x18002a430`
- `0x18003772e`
- `0x180037790`
- `0x180038010`

## import_xrefs

- `msvcrt!isspace` at `0x18002a567`
- `msvcrt!isspace` at `0x18002a567`
- `msvcrt!strcspn` at `0x18002a4c6`
- `msvcrt!strcspn` at `0x18002a53e`
- `msvcrt!strcspn` at `0x18002a4c6`
- `msvcrt!strcspn` at `0x18002a53e`
- `msvcrt!_stricmp` at `0x18002a793`
- `msvcrt!_stricmp` at `0x18002a793`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18002a876`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18002a8dd`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18002a907`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18002a876`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18002a8dd`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18002a907`
- `iisutil!??0STRA@@QEAA@PEADK@Z` at `0x18002a47c`
- `iisutil!??0STRA@@QEAA@PEADK@Z` at `0x18002a497`
- `iisutil!??0STRA@@QEAA@PEADK@Z` at `0x18002a47c`
- `iisutil!??0STRA@@QEAA@PEADK@Z` at `0x18002a497`
- `iisutil!??1STRA@@QEAA@XZ` at `0x18002a4fe`
- `iisutil!??1STRA@@QEAA@XZ` at `0x18002a50f`
- `iisutil!??1STRA@@QEAA@XZ` at `0x18002a57c`
- `iisutil!??1STRA@@QEAA@XZ` at `0x18002a58d`
- `iisutil!??1STRA@@QEAA@XZ` at `0x18002a94f`
- `iisutil!??1STRA@@QEAA@XZ` at `0x18002a960`
- `iisutil!??1STRA@@QEAA@XZ` at `0x18002a4fe`
- `iisutil!??1STRA@@QEAA@XZ` at `0x18002a50f`
- `iisutil!??1STRA@@QEAA@XZ` at `0x18002a57c`
- `iisutil!??1STRA@@QEAA@XZ` at `0x18002a58d`
- `iisutil!??1STRA@@QEAA@XZ` at `0x18002a94f`
- `iisutil!??1STRA@@QEAA@XZ` at `0x18002a960`
- `iisutil!?QueryStr@STRA@@QEAAPEADXZ` at `0x18002a51f`
- `iisutil!?QueryStr@STRA@@QEAAPEADXZ` at `0x18002a5cb`
- `iisutil!?QueryStr@STRA@@QEAAPEADXZ` at `0x18002a6b1`
- `iisutil!?QueryStr@STRA@@QEAAPEADXZ` at `0x18002a6c9`
- `iisutil!?QueryStr@STRA@@QEAAPEADXZ` at `0x18002a51f`
- `iisutil!?QueryStr@STRA@@QEAAPEADXZ` at `0x18002a5cb`
- `iisutil!?QueryStr@STRA@@QEAAPEADXZ` at `0x18002a6b1`
- `iisutil!?QueryStr@STRA@@QEAAPEADXZ` at `0x18002a6c9`
- `iisutil!?Copy@STRA@@QEAAJPEBDK@Z` at `0x18002a4e7`
- `iisutil!?Copy@STRA@@QEAAJPEBDK@Z` at `0x18002a634`
- `iisutil!?Copy@STRA@@QEAAJPEBDK@Z` at `0x18002a4e7`
- `iisutil!?Copy@STRA@@QEAAJPEBDK@Z` at `0x18002a634`
- `iisutil!?QueryCCH@STRA@@QEBAKXZ` at `0x18002a692`
- `iisutil!?QueryCCH@STRA@@QEBAKXZ` at `0x18002a6dd`
- `iisutil!?QueryCCH@STRA@@QEBAKXZ` at `0x18002a692`
- `iisutil!?QueryCCH@STRA@@QEBAKXZ` at `0x18002a6dd`
- `iisutil!?Resize@BUFFER@@QEAA_NKK@Z` at `0x18002a8ac`
- `iisutil!?Resize@BUFFER@@QEAA_NKK@Z` at `0x18002a8ac`
- `iisutil!?Append@STRA@@QEAAJPEBDK@Z` at `0x18002a65f`
- `iisutil!?Append@STRA@@QEAAJPEBDK@Z` at `0x18002a65f`
- `iisutil!?Append@STRA@@QEAAJAEBV1@@Z` at `0x18002a67b`
- `iisutil!?Append@STRA@@QEAAJAEBV1@@Z` at `0x18002a67b`

## pseudocode

```c
__int64 __fastcall W3_REQUEST::SetHeader(W3_REQUEST *this, const char *a2, const char *a3, unsigned __int16 a4, int a5)
{
  unsigned int v6; // r14d
  int v9; // ebx
  const char *Str; // rbx
  const char *v12; // rbx
  const char *v13; // rax
  enum _HTTP_HEADER_ID Index; // eax
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
0x18002a430  push    rbp
0x18002a432  push    rbx
0x18002a433  push    rsi
0x18002a434  push    rdi
0x18002a435  push    r12
0x18002a437  push    r13
0x18002a439  push    r14
0x18002a43b  push    r15
0x18002a43d  lea     rbp, [rsp-1B8h]
0x18002a445  sub     rsp, 2B8h
0x18002a44c  mov     rax, cs:__security_cookie
0x18002a453  xor     rax, rsp
0x18002a456  mov     [rbp+1F0h+var_50], rax
0x18002a45d  mov     rbx, r8
0x18002a460  movzx   r14d, r9w
0x18002a464  mov     rdi, rdx
0x18002a467  mov     rsi, rcx
0x18002a46a  mov     r15d, 100h
0x18002a470  lea     rdx, [rbp+1F0h+var_250]
0x18002a474  mov     r8d, r15d
0x18002a477  lea     rcx, [rsp+2F0h+var_288]
0x18002a47c  call    cs:__imp_??0STRA@@QEAA@PEADK@Z; STRA::STRA(char *,ulong)
0x18002a483  nop     dword ptr [rax+rax+00h]
0x18002a488  mov     r8d, r15d
0x18002a48b  lea     rdx, [rbp+1F0h+var_150]
0x18002a492  lea     rcx, [rsp+2F0h+var_2C0]
0x18002a497  call    cs:__imp_??0STRA@@QEAA@PEADK@Z; STRA::STRA(char *,ulong)
0x18002a49e  nop     dword ptr [rax+rax+00h]
0x18002a4a3  xor     eax, eax
0x18002a4a5  mov     [rsp+2F0h+var_2D0], ax
0x18002a4aa  test    rdi, rdi
0x18002a4ad  jz      loc_18002A577
0x18002a4b3  test    rbx, rbx
0x18002a4b6  jz      loc_18002A577
0x18002a4bc  lea     rdx, Control; "\r\n"
0x18002a4c3  mov     rcx, rdi; Str
0x18002a4c6  call    cs:__imp_strcspn
0x18002a4cd  nop     dword ptr [rax+rax+00h]
0x18002a4d2  cmp     byte ptr [rax+rdi], 0
0x18002a4d6  jnz     loc_18002A577
0x18002a4dc  mov     r8d, r14d
0x18002a4df  lea     rcx, [rsp+2F0h+var_2C0]
0x18002a4e4  mov     rdx, rbx
0x18002a4e7  call    cs:__imp_?Copy@STRA@@QEAAJPEBDK@Z; STRA::Copy(char const *,ulong)
0x18002a4ee  nop     dword ptr [rax+rax+00h]
0x18002a4f3  lea     rcx, [rsp+2F0h+var_2C0]
0x18002a4f8  mov     ebx, eax
0x18002a4fa  test    eax, eax
0x18002a4fc  jns     short loc_18002A51F
0x18002a4fe  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x18002a505  nop     dword ptr [rax+rax+00h]
0x18002a50a  lea     rcx, [rsp+2F0h+var_288]
0x18002a50f  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x18002a516  nop     dword ptr [rax+rax+00h]
0x18002a51b  mov     eax, ebx
0x18002a51d  jmp     short loc_18002A59E
0x18002a51f  call    cs:__imp_?QueryStr@STRA@@QEAAPEADXZ; STRA::QueryStr(void)
0x18002a526  nop     dword ptr [rax+rax+00h]
0x18002a52b  mov     rbx, rax
0x18002a52e  mov     r12d, 1
0x18002a534  lea     rdx, Control; "\r\n"
0x18002a53b  mov     rcx, rbx; Str
0x18002a53e  call    cs:__imp_strcspn
0x18002a545  nop     dword ptr [rax+rax+00h]
0x18002a54a  add     rbx, rax
0x18002a54d  cmp     byte ptr [rbx], 0
0x18002a550  jz      short loc_18002A5C2
0x18002a552  inc     rbx
0x18002a555  cmp     byte ptr [rbx], 0Dh
0x18002a558  jz      short loc_18002A55F
0x18002a55a  cmp     byte ptr [rbx], 0Ah
0x18002a55d  jnz     short loc_18002A564
0x18002a55f  add     rbx, r12
0x18002a562  jmp     short loc_18002A555
0x18002a564  movsx   ecx, byte ptr [rbx]; C
0x18002a567  call    cs:__imp_isspace
0x18002a56e  nop     dword ptr [rax+rax+00h]
0x18002a573  test    eax, eax
0x18002a575  jnz     short loc_18002A534
0x18002a577  lea     rcx, [rsp+2F0h+var_2C0]
0x18002a57c  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x18002a583  nop     dword ptr [rax+rax+00h]
0x18002a588  lea     rcx, [rsp+2F0h+var_288]
0x18002a58d  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x18002a594  nop     dword ptr [rax+rax+00h]
0x18002a599  mov     eax, 80070057h
0x18002a59e  mov     rcx, [rbp+1F0h+var_50]
0x18002a5a5  xor     rcx, rsp; StackCookie
0x18002a5a8  call    __security_check_cookie
0x18002a5ad  add     rsp, 2B8h
0x18002a5b4  pop     r15
0x18002a5b6  pop     r14
0x18002a5b8  pop     r13
0x18002a5ba  pop     r12
0x18002a5bc  pop     rdi
0x18002a5bd  pop     rsi
0x18002a5be  pop     rbx
0x18002a5bf  pop     rbp
0x18002a5c0  retn
0x18002a5c2  add     [rsi+30h], r12d
0x18002a5c6  lea     rcx, [rsp+2F0h+var_2C0]
0x18002a5cb  call    cs:__imp_?QueryStr@STRA@@QEAAPEADXZ; STRA::QueryStr(void)
0x18002a5d2  nop     dword ptr [rax+rax+00h]
0x18002a5d7  mov     r15d, [rbp+1F0h+arg_20]
0x18002a5de  mov     rdx, rdi; char *
0x18002a5e1  mov     r8, rax; char *
0x18002a5e4  mov     r9d, r15d; int
0x18002a5e7  mov     rcx, rsi; this
0x18002a5ea  call    ?TraceSetHeader@W3_REQUEST@@AEAAXPEBD0H@Z; W3_REQUEST::TraceSetHeader(char const *,char const *,int)
0x18002a5ef  mov     rcx, rdi; char *
0x18002a5f2  call    ?GetIndex@REQUEST_HEADER_HASH@@SAKPEBD@Z; REQUEST_HEADER_HASH::GetIndex(char const *)
0x18002a5f7  movsxd  r14, eax
0x18002a5fa  test    r15d, r15d
0x18002a5fd  jnz     loc_18002A6C4
0x18002a603  cmp     r14d, 0FFFFFFFFh
0x18002a607  jz      loc_18002A6C4
0x18002a60d  lea     r8, [rsp+2F0h+var_2D0]; unsigned __int16 *
0x18002a612  mov     edx, r14d; enum _HTTP_HEADER_ID
0x18002a615  mov     rcx, rsi; this
0x18002a618  call    ?QueryHeader@W3_REQUEST@@QEBAPEBDW4_HTTP_HEADER_ID@@PEAG@Z; W3_REQUEST::QueryHeader(_HTTP_HEADER_ID,ushort *)
0x18002a61d  test    rax, rax
0x18002a620  jz      loc_18002A6C4
0x18002a626  movzx   r8d, [rsp+2F0h+var_2D0]
0x18002a62c  lea     rcx, [rsp+2F0h+var_288]
0x18002a631  mov     rdx, rax
0x18002a634  call    cs:__imp_?Copy@STRA@@QEAAJPEBDK@Z; STRA::Copy(char const *,ulong)
0x18002a63b  nop     dword ptr [rax+rax+00h]
0x18002a640  mov     ebx, eax
0x18002a642  test    eax, eax
0x18002a644  jns     short loc_18002A650
0x18002a646  lea     rcx, [rsp+2F0h+var_2C0]
0x18002a64b  jmp     loc_18002A4FE
0x18002a650  mov     r8d, r12d
0x18002a653  lea     rdx, asc_18003C188; ","
0x18002a65a  lea     rcx, [rsp+2F0h+var_288]
0x18002a65f  call    cs:__imp_?Append@STRA@@QEAAJPEBDK@Z; STRA::Append(char const *,ulong)
0x18002a666  nop     dword ptr [rax+rax+00h]
0x18002a66b  mov     ebx, eax
0x18002a66d  test    eax, eax
0x18002a66f  js      short loc_18002A646
0x18002a671  lea     rdx, [rsp+2F0h+var_2C0]
0x18002a676  lea     rcx, [rsp+2F0h+var_288]
0x18002a67b  call    cs:__imp_?Append@STRA@@QEAAJAEBV1@@Z; STRA::Append(STRA const &)
0x18002a682  nop     dword ptr [rax+rax+00h]
0x18002a687  mov     ebx, eax
0x18002a689  test    eax, eax
0x18002a68b  js      short loc_18002A646
0x18002a68d  lea     rcx, [rsp+2F0h+var_288]
0x18002a692  call    cs:__imp_?QueryCCH@STRA@@QEBAKXZ; STRA::QueryCCH(void)
0x18002a699  nop     dword ptr [rax+rax+00h]
0x18002a69e  cmp     eax, 0FFFFh
0x18002a6a3  jbe     short loc_18002A6AC
0x18002a6a5  mov     ebx, 8007000Dh
0x18002a6aa  jmp     short loc_18002A646
0x18002a6ac  lea     rcx, [rsp+2F0h+var_288]
0x18002a6b1  call    cs:__imp_?QueryStr@STRA@@QEAAPEADXZ; STRA::QueryStr(void)
0x18002a6b8  nop     dword ptr [rax+rax+00h]
0x18002a6bd  lea     rcx, [rsp+2F0h+var_288]
0x18002a6c2  jmp     short loc_18002A6DA
0x18002a6c4  lea     rcx, [rsp+2F0h+var_2C0]
0x18002a6c9  call    cs:__imp_?QueryStr@STRA@@QEAAPEADXZ; STRA::QueryStr(void)
0x18002a6d0  nop     dword ptr [rax+rax+00h]
0x18002a6d5  lea     rcx, [rsp+2F0h+var_2C0]
0x18002a6da  mov     rbx, rax
0x18002a6dd  call    cs:__imp_?QueryCCH@STRA@@QEBAKXZ; STRA::QueryCCH(void)
0x18002a6e4  nop     dword ptr [rax+rax+00h]
0x18002a6e9  mov     rcx, [rsi+70h]
0x18002a6ed  movzx   eax, ax
0x18002a6f0  mov     dword ptr [rsp+2F0h+var_2D0], eax
0x18002a6f4  lea     r13d, [rax+1]
0x18002a6f8  mov     rax, [rcx]
0x18002a6fb  mov     edx, r13d
0x18002a6fe  mov     rax, [rax+90h]
0x18002a705  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a70a  mov     [rsp+2F0h+var_2C8], rax
0x18002a70f  mov     r12, rax
0x18002a712  test    rax, rax
0x18002a715  jz      loc_18002A973
0x18002a71b  mov     edx, r13d; unsigned __int64
0x18002a71e  mov     r8, rbx; char *
0x18002a721  mov     rcx, rax; char *
0x18002a724  call    ?StringCchCopyA@@YAJPEAD_KPEBD@Z; StringCchCopyA(char *,unsigned __int64,char const *)
0x18002a729  cmp     r14d, 0FFFFFFFFh
0x18002a72d  jz      short loc_18002A75D
0x18002a72f  mov     rax, [rsi+28h]
0x18002a733  lea     rcx, [r14+0Ah]
0x18002a737  mov     r13d, dword ptr [rsp+2F0h+var_2D0]
0x18002a73c  add     rcx, rcx
0x18002a73f  mov     rdx, r14
0x18002a742  add     rdx, rdx
0x18002a745  mov     [rax+rcx*8], r12
0x18002a749  mov     rax, [rsi+28h]
0x18002a74d  mov     [rax+rdx*8+98h], r13w
0x18002a756  xor     ebx, ebx
0x18002a758  jmp     loc_18002A646
0x18002a75d  test    r15d, r15d
0x18002a760  jz      loc_18002A81B
0x18002a766  mov     rcx, [rsi+28h]
0x18002a76a  xor     eax, eax
0x18002a76c  cmp     ax, [rcx+78h]
0x18002a770  jnb     loc_18002A81B
0x18002a776  mov     r13d, dword ptr [rsp+2F0h+var_2D0]
0x18002a77b  xor     r14d, r14d
0x18002a77e  xor     ebx, ebx
0x18002a780  mov     rdx, [rcx+80h]
0x18002a787  lea     r15, [rbx+rbx*2]
0x18002a78b  mov     rcx, rdi; String1
0x18002a78e  mov     rdx, [rdx+r15*8+8]; String2
0x18002a793  call    cs:__imp__stricmp
0x18002a79a  nop     dword ptr [rax+rax+00h]
0x18002a79f  test    eax, eax
0x18002a7a1  jnz     short loc_18002A800
0x18002a7a3  mov     rax, [rsi+28h]
0x18002a7a7  mov     rcx, [rax+80h]
0x18002a7ae  test    r14d, r14d
0x18002a7b1  jnz     short loc_18002A7D4
0x18002a7b3  mov     [rcx+r15*8+10h], r12
0x18002a7b8  mov     rax, [rsi+28h]
0x18002a7bc  mov     rcx, [rax+80h]
0x18002a7c3  lea     eax, [r14+1]
0x18002a7c7  mov     r14d, eax
0x18002a7ca  add     ebx, eax
0x18002a7cc  mov     [rcx+r15*8+2], r13w
0x18002a7d2  jmp     short loc_18002A802
0x18002a7d4  movzx   eax, word ptr [rax+78h]
0x18002a7d8  lea     rcx, [rcx+r15*8]; void *
0x18002a7dc  sub     eax, ebx
0x18002a7de  lea     rdx, [rcx+18h]; Src
0x18002a7e2  dec     eax
0x18002a7e4  lea     r8, [rax+rax*2]
0x18002a7e8  shl     r8, 3; Size
0x18002a7ec  call    memmove_0
0x18002a7f1  mov     rax, [rsi+28h]
0x18002a7f5  mov     ecx, 0FFFFh
0x18002a7fa  add     [rax+78h], cx
0x18002a7fe  jmp     short loc_18002A802
0x18002a800  inc     ebx
0x18002a802  mov     rcx, [rsi+28h]
0x18002a806  movzx   eax, word ptr [rcx+78h]
0x18002a80a  cmp     ebx, eax
0x18002a80c  jb      loc_18002A780
0x18002a812  test    r14d, r14d
0x18002a815  jnz     loc_18002A756
0x18002a81b  or      r15, 0FFFFFFFFFFFFFFFFh
0x18002a81f  inc     r15
0x18002a822  cmp     byte ptr [rdi+r15], 0
0x18002a827  jnz     short loc_18002A81F
0x18002a829  mov     rcx, [rsi+70h]
0x18002a82d  lea     r14d, [r15+1]
0x18002a831  mov     edx, r14d
0x18002a834  mov     rax, [rcx]
0x18002a837  mov     rax, [rax+90h]
0x18002a83e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a843  mov     r13, rax
0x18002a846  test    rax, rax
0x18002a849  jz      loc_18002A973
0x18002a84f  mov     edx, r14d; unsigned __int64
0x18002a852  mov     r8, rdi; char *
0x18002a855  mov     rcx, rax; char *
0x18002a858  xor     ebx, ebx
0x18002a85a  call    ?StringCchCopyA@@YAJPEAD_KPEBD@Z; StringCchCopyA(char *,unsigned __int64,char const *)
0x18002a85f  mov     rcx, [rsi+28h]
0x18002a863  mov     rdi, [rcx+80h]
0x18002a86a  test    rdi, rdi
0x18002a86d  jz      short loc_18002A88B
0x18002a86f  lea     rcx, [rsi+0A8h]
0x18002a876  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x18002a87d  nop     dword ptr [rax+rax+00h]
0x18002a882  cmp     rax, rdi
0x18002a885  lea     eax, [rbx+1]
0x18002a888  cmovnz  ebx, eax
0x18002a88b  mov     rax, [rsi+28h]
0x18002a88f  lea     r12, [rsi+0A8h]
0x18002a896  mov     r8d, 200h
0x18002a89c  mov     rcx, r12
0x18002a89f  movzx   edi, word ptr [rax+78h]
0x18002a8a3  lea     eax, [rdi+1]
0x18002a8a6  lea     edx, [rax+rax*2]
0x18002a8a9  shl     edx, 3
0x18002a8ac  call    cs:__imp_?Resize@BUFFER@@QEAA_NKK@Z; BUFFER::Resize(ulong,ulong)
0x18002a8b3  nop     dword ptr [rax+rax+00h]
0x18002a8b8  test    al, al
0x18002a8ba  jz      loc_18002A973
0x18002a8c0  mov     r14d, edi
0x18002a8c3  test    ebx, ebx
0x18002a8c5  jz      short loc_18002A8F7
0x18002a8c7  mov     rax, [rsi+28h]
0x18002a8cb  lea     rbx, [r14+r14*2]
0x18002a8cf  mov     rcx, r12
0x18002a8d2  shl     rbx, 3
0x18002a8d6  mov     rdi, [rax+80h]
0x18002a8dd  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x18002a8e4  nop     dword ptr [rax+rax+00h]
0x18002a8e9  mov     r8, rbx; Size
0x18002a8ec  mov     rdx, rdi; Src
0x18002a8ef  mov     rcx, rax; void *
0x18002a8f2  call    memmove_0
0x18002a8f7  mov     rax, [rsi+28h]
0x18002a8fb  mov     ecx, 1
0x18002a900  add     [rax+78h], cx
  ... truncated ...
```
