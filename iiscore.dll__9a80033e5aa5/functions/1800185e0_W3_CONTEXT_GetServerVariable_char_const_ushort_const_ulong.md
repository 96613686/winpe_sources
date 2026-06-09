# W3_CONTEXT::GetServerVariable(char const *,ushort const * *,ulong *)

- ea: `0x1800185e0`
- end: `0x1800189fd`
- name: `?GetServerVariable@W3_CONTEXT@@UEAAJPEBDPEAPEBGPEAK@Z`
- size: `1053`
- prototype: `int(W3_CONTEXT *__hidden this, const char *, const unsigned __int16 **, unsigned int *)`
- caller_count: `0`
- callee_count: `5`
- tags: `file_ops`

## callees

- `0x180010240`
- `0x1800185e0`
- `0x1800343b2`
- `0x1800343f0`
- `0x180035010`

## import_xrefs

- `msvcrt!_stricmp` at `0x1800187c2`
- `msvcrt!_stricmp` at `0x1800187c2`
- `msvcrt!strchr` at `0x180018895`
- `msvcrt!strchr` at `0x1800188ac`
- `msvcrt!strchr` at `0x180018895`
- `msvcrt!strchr` at `0x1800188ac`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018971`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800189a6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018971`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800189a6`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180018967`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18001899c`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180018967`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18001899c`
- `iisutil!??0STRA@@QEAA@PEADK@Z` at `0x18001883e`
- `iisutil!??0STRA@@QEAA@PEADK@Z` at `0x18001883e`
- `iisutil!??1STRA@@QEAA@XZ` at `0x18001887e`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180018909`
- `iisutil!??1STRA@@QEAA@XZ` at `0x1800189e3`
- `iisutil!??1STRA@@QEAA@XZ` at `0x18001887e`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180018909`
- `iisutil!??1STRA@@QEAA@XZ` at `0x1800189e3`
- `iisutil!?Copy@STRA@@QEAAJPEBD@Z` at `0x18001886d`
- `iisutil!?Copy@STRA@@QEAAJPEBD@Z` at `0x18001886d`

## pseudocode

```c
int __fastcall W3_CONTEXT::GetServerVariable(
        W3_CONTEXT *this,
        const char *a2,
        const unsigned __int16 **a3,
        unsigned int *a4)
{
  unsigned int v8; // r11d
  __int64 v9; // r9
  __int64 v10; // rbx
  const char *v11; // rax
  const char *v12; // r8
  int v13; // ecx
  int v14; // edx
  unsigned __int8 v15; // cl
  unsigned int v16; // edx
  const char *v17; // rdi
  _DWORD *v18; // r14
  int v19; // eax
  __int64 v20; // rax
  const unsigned __int16 *v21; // rdx
  int result; // eax
  __int64 v23; // rdi
  __int64 i; // rbx
  __int64 v25; // rax
  bool v26; // zf
  __int64 (__fastcall *v27)(W3_CONTEXT *, const unsigned __int16 **, unsigned int *); // rax
  __int64 (__fastcall *v28)(W3_CONTEXT *, LPCCH *, int *); // rax
  int v29; // ebx
  char *j; // rax
  char *v31; // rdx
  WCHAR *lpWideCharStr; // rax
  unsigned __int16 *v33; // rbx
  int v34; // eax
  unsigned __int16 v35[2]; // [rsp+30h] [rbp-A8h] BYREF
  int v36; // [rsp+34h] [rbp-A4h] BYREF
  LPCCH lpMultiByteStr; // [rsp+38h] [rbp-A0h] BYREF
  _BYTE v38[32]; // [rsp+40h] [rbp-98h] BYREF
  char *Str; // [rsp+60h] [rbp-78h]
  char v40[32]; // [rsp+78h] [rbp-60h] BYREF

  lpMultiByteStr = 0;
  v36 = 0;
  if ( !a2 || !a3 || !a4 )
    return -2147024809;
  v8 = *((_DWORD *)this + 2268);
  if ( v8 )
  {
    v9 = 0;
    v10 = *(_QWORD *)(*((_QWORD *)this + 1132) + 32LL);
    while ( 1 )
    {
      v11 = *(const char **)(v10 + 8 * v9);
      v12 = (const char *)(a2 - v11);
      do
      {
        v13 = (unsigned __int8)v12[(_QWORD)v11];
        v14 = *(unsigned __int8 *)v11 - v13;
        if ( v14 )
          break;
        ++v11;
      }
      while ( v13 );
      if ( !v14 )
        break;
      v9 = (unsigned int)(v9 + 1);
      if ( (unsigned int)v9 >= v8 )
        goto LABEL_11;
    }
    v20 = -1;
    v21 = *(const unsigned __int16 **)(8 * v9 + *(_QWORD *)(*((_QWORD *)this + 1133) + 32LL));
    *a3 = v21;
    do
      ++v20;
    while ( v21[v20] );
    goto LABEL_17;
  }
LABEL_11:
  v15 = *a2;
  v16 = 0;
  v17 = a2;
  v18 = SERVERVAR_HASH::sm_pServerVarHash;
  if ( *((_DWORD *)SERVERVAR_HASH::sm_pServerVarHash + 214) )
  {
    if ( v15 )
    {
      do
      {
        ++v17;
        v19 = v15;
        v15 = *v17;
        v16 = v19 + 101 * v16;
      }
      while ( *v17 );
    }
  }
  else if ( v15 )
  {
    do
    {
      ++v17;
      v16 = (v15 & 0xDF) + 101 * v16;
      v15 = *v17;
    }
    while ( *v17 );
  }
  v23 = v17 - a2;
  for ( i = *((_QWORD *)SERVERVAR_HASH::sm_pServerVarHash + v16 % 0x6B); i; i = *(_QWORD *)(i + 8) )
  {
    v25 = *(unsigned __int16 *)(i + 16);
    if ( v18[214] )
    {
      if ( v23 == v25 )
      {
        v26 = strcmp(a2, *(const char **)i) == 0;
        goto LABEL_27;
      }
    }
    else if ( v23 == v25 )
    {
      v26 = _stricmp(a2, *(const char **)i) == 0;
LABEL_27:
      if ( v26 )
        break;
    }
  }
  if ( !i )
    goto LABEL_35;
  v27 = *(__int64 (__fastcall **)(W3_CONTEXT *, const unsigned __int16 **, unsigned int *))(i + 24);
  if ( v27 )
    return v27(this, a3, a4);
  v28 = *(__int64 (__fastcall **)(W3_CONTEXT *, LPCCH *, int *))(i + 32);
  if ( !v28 )
  {
LABEL_35:
    STRA::STRA((STRA *)v38, v40, 0x20u);
    v35[0] = 0;
    if ( !strncmp_0(a2, "HTTP_", 5u) )
    {
      v29 = STRA::Copy((STRA *)v38, a2 + 5);
      if ( v29 < 0 )
      {
        STRA::~STRA((STRA *)v38);
        return v29;
      }
      for ( j = strchr(Str, 95); j; j = strchr(j + 1, 95) )
        *j = 45;
      v31 = Str;
    }
    else
    {
      if ( strncmp_0(a2, "HEADER_", 7u) )
        goto LABEL_55;
      v31 = (char *)(a2 + 7);
    }
    lpMultiByteStr = W3_REQUEST::GetHeader(*((W3_REQUEST **)this + 6), v31, v35);
    if ( lpMultiByteStr )
    {
      v36 = v35[0];
      STRA::~STRA((STRA *)v38);
      goto LABEL_45;
    }
LABEL_55:
    STRA::~STRA((STRA *)v38);
    return -2147023483;
  }
  result = v28(this, &lpMultiByteStr, &v36);
  if ( result < 0 )
    return result;
LABEL_45:
  if ( !v36 )
  {
    LODWORD(v20) = 0;
    *a3 = &dword_180039134;
    goto LABEL_17;
  }
  lpWideCharStr = (WCHAR *)(*(__int64 (__fastcall **)(W3_CONTEXT *, _QWORD))(*(_QWORD *)this + 144LL))(
                             this,
                             (unsigned int)(2 * v36 + 2));
  v33 = lpWideCharStr;
  if ( !lpWideCharStr )
    return -2147024888;
  v34 = MultiByteToWideChar(0xFDE9u, 8u, lpMultiByteStr, v36 + 1, lpWideCharStr, v36 + 1);
  if ( v34 || GetLastError() == 1113 && (v34 = MultiByteToWideChar(0, 9u, lpMultiByteStr, v36 + 1, v33, v36 + 1)) != 0 )
  {
    LODWORD(v20) = v34 - 1;
    *a3 = v33;
LABEL_17:
    *a4 = v20;
    return 0;
  }
  result = GetLastError();
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x1800185e0  push    rbp
0x1800185e2  push    rsi
0x1800185e3  push    r12
0x1800185e5  push    r15
0x1800185e7  sub     rsp, 0B8h
0x1800185ee  mov     rax, cs:__security_cookie
0x1800185f5  xor     rax, rsp
0x1800185f8  mov     [rsp+0D8h+var_40], rax
0x180018600  mov     [rsp+0D8h+lpMultiByteStr], 0
0x180018609  mov     rbp, r9
0x18001860c  mov     [rsp+0D8h+var_A4], 0
0x180018614  mov     r12, r8
0x180018617  mov     rsi, rdx
0x18001861a  mov     r15, rcx
0x18001861d  test    rdx, rdx
0x180018620  jz      loc_1800189F3
0x180018626  test    r8, r8
0x180018629  jz      loc_1800189F3
0x18001862f  test    r9, r9
0x180018632  jz      loc_1800189F3
0x180018638  mov     r11d, [rcx+2370h]
0x18001863f  mov     [rsp+0D8h+var_28], rbx
0x180018647  test    r11d, r11d
0x18001864a  jz      short loc_180018691
0x18001864c  mov     rax, [rcx+2360h]
0x180018653  xor     r9d, r9d
0x180018656  mov     rbx, [rax+20h]
0x18001865a  nop     word ptr [rax+rax+00h]
0x180018660  mov     rax, [rbx+r9*8]
0x180018664  lea     r10, ds:0[r9*8]
0x18001866c  mov     r8, rsi
0x18001866f  sub     r8, rax
0x180018672  movzx   edx, byte ptr [rax]
0x180018675  movzx   ecx, byte ptr [rax+r8]
0x18001867a  sub     edx, ecx
0x18001867c  jnz     short loc_180018685
0x18001867e  inc     rax
0x180018681  test    ecx, ecx
0x180018683  jnz     short loc_180018672
0x180018685  test    edx, edx
0x180018687  jz      short loc_1800186D5
0x180018689  inc     r9d
0x18001868c  cmp     r9d, r11d
0x18001868f  jb      short loc_180018660
0x180018691  movzx   ecx, byte ptr [rsi]
0x180018694  xor     edx, edx
0x180018696  mov     [rsp+0D8h+var_30], rdi
0x18001869e  mov     rdi, rsi
0x1800186a1  mov     [rsp+0D8h+var_38], r14
0x1800186a9  mov     r14, cs:?sm_pServerVarHash@SERVERVAR_HASH@@0PEAV1@EA; SERVERVAR_HASH * SERVERVAR_HASH::sm_pServerVarHash
0x1800186b0  cmp     [r14+358h], edx
0x1800186b7  jz      short loc_180018725
0x1800186b9  test    cl, cl
0x1800186bb  jz      loc_180018745
0x1800186c1  imul    edx, 65h ; 'e'
0x1800186c4  inc     rdi
0x1800186c7  movzx   eax, cl
0x1800186ca  movzx   ecx, byte ptr [rdi]
0x1800186cd  add     edx, eax
0x1800186cf  test    cl, cl
0x1800186d1  jnz     short loc_1800186C1
0x1800186d3  jmp     short loc_180018745
0x1800186d5  mov     rax, [r15+2368h]
0x1800186dc  mov     rcx, [rax+20h]
0x1800186e0  mov     rax, 0FFFFFFFFFFFFFFFFh
0x1800186e7  mov     rdx, [r10+rcx]
0x1800186eb  mov     [r12], rdx
0x1800186ef  nop
0x1800186f0  inc     rax
0x1800186f3  cmp     word ptr [rdx+rax*2], 0
0x1800186f8  jnz     short loc_1800186F0
0x1800186fa  mov     [rbp+0], eax
0x1800186fd  xor     eax, eax
0x1800186ff  mov     rbx, [rsp+0D8h+var_28]
0x180018707  mov     rcx, [rsp+0D8h+var_40]
0x18001870f  xor     rcx, rsp; StackCookie
0x180018712  call    __security_check_cookie
0x180018717  add     rsp, 0B8h
0x18001871e  pop     r15
0x180018720  pop     r12
0x180018722  pop     rsi
0x180018723  pop     rbp
0x180018724  retn
0x180018725  test    cl, cl
0x180018727  jz      short loc_180018745
0x180018729  nop     dword ptr [rax+00000000h]
0x180018730  and     ecx, 0DFh
0x180018736  imul    edx, 65h ; 'e'
0x180018739  inc     rdi
0x18001873c  add     edx, ecx
0x18001873e  movzx   ecx, byte ptr [rdi]
0x180018741  test    cl, cl
0x180018743  jnz     short loc_180018730
0x180018745  mov     ecx, edx
0x180018747  mov     rax, 323E34A2B10BF66Fh
0x180018751  mul     rcx
0x180018754  mov     eax, ecx
0x180018756  sub     rdi, rsi
0x180018759  sub     rax, rdx
0x18001875c  shr     rax, 1
0x18001875f  add     rax, rdx
0x180018762  shr     rax, 6
0x180018766  imul    rax, 6Bh ; 'k'
0x18001876a  sub     rcx, rax
0x18001876d  mov     eax, ecx
0x18001876f  mov     rbx, [r14+rax*8]
0x180018773  test    rbx, rbx
0x180018776  jz      short loc_1800187D5
0x180018778  nop     dword ptr [rax+rax+00000000h]
0x180018780  cmp     dword ptr [r14+358h], 0
0x180018788  movzx   eax, word ptr [rbx+10h]
0x18001878c  jz      short loc_1800187B7
0x18001878e  cmp     rdi, rax
0x180018791  jnz     short loc_1800187CC
0x180018793  mov     r8, [rbx]
0x180018796  mov     rax, rsi
0x180018799  sub     r8, rsi
0x18001879c  nop     dword ptr [rax+00h]
0x1800187a0  movzx   edx, byte ptr [rax]
0x1800187a3  movzx   ecx, byte ptr [rax+r8]
0x1800187a8  sub     edx, ecx
0x1800187aa  jnz     short loc_1800187B3
0x1800187ac  inc     rax
0x1800187af  test    ecx, ecx
0x1800187b1  jnz     short loc_1800187A0
0x1800187b3  test    edx, edx
0x1800187b5  jmp     short loc_1800187CA
0x1800187b7  cmp     rdi, rax
0x1800187ba  jnz     short loc_1800187CC
0x1800187bc  mov     rdx, [rbx]; String2
0x1800187bf  mov     rcx, rsi; String1
0x1800187c2  call    cs:__imp__stricmp
0x1800187c8  test    eax, eax
0x1800187ca  jz      short loc_1800187D5
0x1800187cc  mov     rbx, [rbx+8]
0x1800187d0  test    rbx, rbx
0x1800187d3  jnz     short loc_180018780
0x1800187d5  mov     r14, [rsp+0D8h+var_38]
0x1800187dd  mov     rdi, [rsp+0D8h+var_30]
0x1800187e5  test    rbx, rbx
0x1800187e8  jz      short loc_18001882E
0x1800187ea  mov     rax, [rbx+18h]
0x1800187ee  test    rax, rax
0x1800187f1  jz      short loc_180018806
0x1800187f3  mov     r8, rbp
0x1800187f6  mov     rdx, r12
0x1800187f9  mov     rcx, r15
0x1800187fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018801  jmp     loc_1800186FF
0x180018806  mov     rax, [rbx+20h]
0x18001880a  test    rax, rax
0x18001880d  jz      short loc_18001882E
0x18001880f  lea     r8, [rsp+0D8h+var_A4]
0x180018814  mov     rcx, r15
0x180018817  lea     rdx, [rsp+0D8h+lpMultiByteStr]
0x18001881c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018821  test    eax, eax
0x180018823  jns     loc_18001890F
0x180018829  jmp     loc_1800186FF
0x18001882e  mov     r8d, 20h ; ' '
0x180018834  lea     rdx, [rsp+0D8h+var_60]
0x180018839  lea     rcx, [rsp+0D8h+var_98]
0x18001883e  call    cs:__imp_??0STRA@@QEAA@PEADK@Z; STRA::STRA(char *,ulong)
0x180018844  xor     eax, eax
0x180018846  lea     rdx, aHttp; "HTTP_"
0x18001884d  mov     r8d, 5; MaxCount
0x180018853  mov     [rsp+0D8h+var_A8], ax
0x180018858  mov     rcx, rsi; Str1
0x18001885b  call    strncmp_0
0x180018860  test    eax, eax
0x180018862  jnz     short loc_1800188BE
0x180018864  lea     rdx, [rsi+5]
0x180018868  lea     rcx, [rsp+0D8h+var_98]
0x18001886d  call    cs:__imp_?Copy@STRA@@QEAAJPEBD@Z; STRA::Copy(char const *)
0x180018873  mov     ebx, eax
0x180018875  test    eax, eax
0x180018877  jns     short loc_18001888B
0x180018879  lea     rcx, [rsp+0D8h+var_98]
0x18001887e  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x180018884  mov     eax, ebx
0x180018886  jmp     loc_1800186FF
0x18001888b  mov     rcx, [rsp+0D8h+Str]; Str
0x180018890  mov     edx, 5Fh ; '_'; Val
0x180018895  call    cs:__imp_strchr
0x18001889b  test    rax, rax
0x18001889e  jz      short loc_1800188B7
0x1800188a0  lea     rcx, [rax+1]; Str
0x1800188a4  mov     byte ptr [rax], 2Dh ; '-'
0x1800188a7  mov     edx, 5Fh ; '_'; Val
0x1800188ac  call    cs:__imp_strchr
0x1800188b2  test    rax, rax
0x1800188b5  jnz     short loc_1800188A0
0x1800188b7  mov     rdx, [rsp+0D8h+Str]
0x1800188bc  jmp     short loc_1800188DF
0x1800188be  mov     r8d, 7; MaxCount
0x1800188c4  lea     rdx, aHeader; "HEADER_"
0x1800188cb  mov     rcx, rsi; Str1
0x1800188ce  call    strncmp_0
0x1800188d3  test    eax, eax
0x1800188d5  jnz     loc_1800189DE
0x1800188db  lea     rdx, [rsi+7]; char *
0x1800188df  mov     rcx, [r15+30h]; this
0x1800188e3  lea     r8, [rsp+0D8h+var_A8]; unsigned __int16 *
0x1800188e8  call    ?GetHeader@W3_REQUEST@@QEBAPEBDPEBDPEAG@Z; W3_REQUEST::GetHeader(char const *,ushort *)
0x1800188ed  mov     [rsp+0D8h+lpMultiByteStr], rax
0x1800188f2  test    rax, rax
0x1800188f5  jz      loc_1800189DE
0x1800188fb  movzx   eax, [rsp+0D8h+var_A8]
0x180018900  lea     rcx, [rsp+0D8h+var_98]
0x180018905  mov     [rsp+0D8h+var_A4], eax
0x180018909  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x18001890f  mov     edx, [rsp+0D8h+var_A4]
0x180018913  test    edx, edx
0x180018915  jz      loc_1800189CC
0x18001891b  mov     rax, [r15]
0x18001891e  lea     edx, ds:2[rdx*2]
0x180018925  mov     rcx, r15
0x180018928  mov     rax, [rax+90h]
0x18001892f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018934  mov     rbx, rax
0x180018937  test    rax, rax
0x18001893a  jnz     short loc_180018946
0x18001893c  mov     eax, 80070008h
0x180018941  jmp     loc_1800186FF
0x180018946  mov     r9d, [rsp+0D8h+var_A4]
0x18001894b  mov     edx, 8; dwFlags
0x180018950  mov     r8, [rsp+0D8h+lpMultiByteStr]; lpMultiByteStr
0x180018955  inc     r9d; cbMultiByte
0x180018958  mov     [rsp+0D8h+cchWideChar], r9d; cchWideChar
0x18001895d  mov     ecx, 0FDE9h; CodePage
0x180018962  mov     [rsp+0D8h+lpWideCharStr], rbx; lpWideCharStr
0x180018967  call    cs:__imp_MultiByteToWideChar
0x18001896d  test    eax, eax
0x18001896f  jnz     short loc_1800189C1
0x180018971  call    cs:__imp_GetLastError
0x180018977  cmp     eax, 459h
0x18001897c  jnz     short loc_1800189A6
0x18001897e  mov     r9d, [rsp+0D8h+var_A4]
0x180018983  mov     edx, 9; dwFlags
0x180018988  mov     r8, [rsp+0D8h+lpMultiByteStr]; lpMultiByteStr
0x18001898d  inc     r9d; cbMultiByte
0x180018990  mov     [rsp+0D8h+cchWideChar], r9d; cchWideChar
0x180018995  xor     ecx, ecx; CodePage
0x180018997  mov     [rsp+0D8h+lpWideCharStr], rbx; lpWideCharStr
0x18001899c  call    cs:__imp_MultiByteToWideChar
0x1800189a2  test    eax, eax
0x1800189a4  jnz     short loc_1800189C1
0x1800189a6  call    cs:__imp_GetLastError
0x1800189ac  test    eax, eax
0x1800189ae  jle     loc_1800186FF
0x1800189b4  movzx   eax, ax
0x1800189b7  or      eax, 80070000h
0x1800189bc  jmp     loc_1800186FF
0x1800189c1  dec     eax
0x1800189c3  mov     [r12], rbx
0x1800189c7  jmp     loc_1800186FA
0x1800189cc  lea     rbx, dword_180039134
0x1800189d3  xor     eax, eax
0x1800189d5  mov     [r12], rbx
0x1800189d9  jmp     loc_1800186FA
0x1800189de  lea     rcx, [rsp+0D8h+var_98]
0x1800189e3  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x1800189e9  mov     eax, 80070585h
0x1800189ee  jmp     loc_1800186FF
0x1800189f3  mov     eax, 80070057h
0x1800189f8  jmp     loc_180018707
```
