# W3_CGI_HANDLER::SetupChildEnv(BUFFER *)

- ea: `0x180005a54`
- end: `0x180005cf4`
- name: `?SetupChildEnv@W3_CGI_HANDLER@@AEAAJPEAVBUFFER@@@Z`
- size: `672`
- prototype: `__int64 __fastcall(W3_CGI_HANDLER *__hidden this, struct BUFFER *)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, installer_update`

## callers

- `0x18000337c`

## callees

- `0x180005a54`
- `0x180006e46`
- `0x180006e52`
- `0x180006e5e`
- `0x180006e90`
- `0x180008010`

## import_xrefs

- `msvcrt!wcschr` at `0x180005bb6`
- `msvcrt!wcschr` at `0x180005bcf`
- `msvcrt!wcschr` at `0x180005be1`
- `msvcrt!wcschr` at `0x180005bb6`
- `msvcrt!wcschr` at `0x180005bcf`
- `msvcrt!wcschr` at `0x180005be1`
- `iisutil!?CopyA@STRU@@QEAAJPEBDK@Z` at `0x180005c00`
- `iisutil!?CopyA@STRU@@QEAAJPEBDK@Z` at `0x180005c00`
- `iisutil!?Resize@BUFFER@@QEAA_NKK@Z` at `0x180005aa7`
- `iisutil!?Resize@BUFFER@@QEAA_NKK@Z` at `0x180005b66`
- `iisutil!?Resize@BUFFER@@QEAA_NKK@Z` at `0x180005aa7`
- `iisutil!?Resize@BUFFER@@QEAA_NKK@Z` at `0x180005b66`
- `iisutil!?Resize@BUFFER@@QEAA_NK@Z` at `0x180005c8c`
- `iisutil!?Resize@BUFFER@@QEAA_NK@Z` at `0x180005c8c`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180005ca4`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180005cb7`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180005cc5`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180005ca4`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180005cb7`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180005cc5`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180005b05`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180005b05`

## pseudocode

```c
__int64 __fastcall W3_CGI_HANDLER::SetupChildEnv(W3_CGI_HANDLER *this, struct BUFFER *a2)
{
  __int64 v2; // rsi
  void **v3; // r14
  W3_CGI_HANDLER *v4; // rdi
  __int64 v6; // r12
  const char *v7; // rbx
  int v8; // edi
  __int64 v9; // r15
  const wchar_t *v10; // r13
  wchar_t *v11; // rax
  wchar_t *v12; // rax
  int v13; // ebx
  int v14; // [rsp+30h] [rbp-89h] BYREF
  void *Src; // [rsp+38h] [rbp-81h] BYREF
  struct BUFFER *v16; // [rsp+40h] [rbp-79h]
  W3_CGI_HANDLER *v17; // [rsp+48h] [rbp-71h]
  _BYTE v18[32]; // [rsp+50h] [rbp-69h] BYREF
  void *v19; // [rsp+70h] [rbp-49h]
  unsigned __int16 v20[32]; // [rsp+90h] [rbp-29h] BYREF

  v2 = 0;
  v16 = a2;
  v3 = (void **)a2;
  v4 = this;
  v17 = this;
  if ( W3_CGI_HANDLER::sm_fForwardServerEnvironmentBlock )
  {
    if ( !BUFFER::Resize(a2, 2 * W3_CGI_HANDLER::sm_cchEnvLength, 0x200u) )
      return 2147942408LL;
    v2 = W3_CGI_HANDLER::sm_cchEnvLength;
    memcpy_0(v3[4], W3_CGI_HANDLER::sm_pEnvString, 2LL * W3_CGI_HANDLER::sm_cchEnvLength);
  }
  Src = 0;
  v14 = 0;
  memset_0(v20, 0, sizeof(v20));
  STRU::STRU((STRU *)v18, v20, 0x20u);
  LODWORD(v6) = 0;
  v7 = "ALL_HTTP";
  while ( 1 )
  {
    v8 = (*(__int64 (__fastcall **)(_QWORD, const char *, void **, int *))(**((_QWORD **)v4 + 6) + 128LL))(
           *((_QWORD *)v4 + 6),
           v7,
           &Src,
           &v14);
    if ( v8 < 0 )
      break;
    v9 = -1;
    do
      ++v9;
    while ( v7[v9] );
    if ( !BUFFER::Resize((BUFFER *)v3, 2 * (v2 + v9 + v14) + 4, 0x200u) )
      goto LABEL_20;
    v10 = (const wchar_t *)v3[4];
    if ( !strcmp_0(v7, "ALL_HTTP") )
    {
      memcpy_0((void *)&v10[v2], Src, 2LL * (unsigned int)(v14 + 1));
      v11 = wcschr(&v10[v2], 0x3Au);
      if ( v11 )
      {
        do
        {
          *v11 = 61;
          v12 = wcschr(v11 + 1, 0xAu);
          *v12 = 0;
          v11 = wcschr(v12 + 1, 0x3Au);
        }
        while ( v11 );
        v3 = (void **)v16;
      }
      v2 = (unsigned int)(v14 + v2);
    }
    else
    {
      v13 = STRU::CopyA((STRU *)v18, v7, v9);
      if ( v13 < 0 )
        goto LABEL_21;
      memcpy_0((void *)&v10[v2], v19, 2LL * (unsigned int)v9);
      v10[(unsigned int)v9 + v2] = 61;
      memcpy_0((void *)&v10[(unsigned int)v9 + 1 + v2], Src, 2LL * (unsigned int)(v14 + 1));
      v2 = (unsigned int)(v9 + v14 + v2 + 2);
    }
    v4 = v17;
    v6 = (unsigned int)(v6 + 1);
    v7 = (const char *)(&g_CGIServerVars)[v6];
    if ( !v7 )
    {
      if ( BUFFER::Resize((BUFFER *)v3, 2 * v2 + 2) )
      {
        *((_WORD *)v3[4] + v2) = 0;
        STRU::~STRU((STRU *)v18);
        return 0;
      }
LABEL_20:
      v13 = -2147024888;
LABEL_21:
      STRU::~STRU((STRU *)v18);
      return (unsigned int)v13;
    }
  }
  STRU::~STRU((STRU *)v18);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180005a54  mov     [rsp-8+arg_10], rbx
0x180005a59  push    rbp
0x180005a5a  push    rsi
0x180005a5b  push    rdi
0x180005a5c  push    r12
0x180005a5e  push    r13
0x180005a60  push    r14
0x180005a62  push    r15
0x180005a64  lea     rbp, [rsp-27h]
0x180005a69  sub     rsp, 0E0h
0x180005a70  mov     rax, cs:__security_cookie
0x180005a77  xor     rax, rsp
0x180005a7a  mov     [rbp+57h+var_40], rax
0x180005a7e  xor     esi, esi
0x180005a80  mov     [rbp+57h+var_D0], rdx
0x180005a84  cmp     cs:?sm_fForwardServerEnvironmentBlock@W3_CGI_HANDLER@@0HA, esi; int W3_CGI_HANDLER::sm_fForwardServerEnvironmentBlock
0x180005a8a  mov     r14, rdx
0x180005a8d  mov     rdi, rcx
0x180005a90  mov     [rbp+57h+var_C8], rcx
0x180005a94  jz      short loc_180005AD7
0x180005a96  mov     edx, cs:?sm_cchEnvLength@W3_CGI_HANDLER@@0KA; ulong W3_CGI_HANDLER::sm_cchEnvLength
0x180005a9c  mov     r8d, 200h
0x180005aa2  add     edx, edx
0x180005aa4  mov     rcx, r14
0x180005aa7  call    cs:__imp_?Resize@BUFFER@@QEAA_NKK@Z; BUFFER::Resize(ulong,ulong)
0x180005aad  test    al, al
0x180005aaf  jnz     short loc_180005ABB
0x180005ab1  mov     eax, 80070008h
0x180005ab6  jmp     loc_180005CCD
0x180005abb  mov     esi, cs:?sm_cchEnvLength@W3_CGI_HANDLER@@0KA; ulong W3_CGI_HANDLER::sm_cchEnvLength
0x180005ac1  mov     rdx, cs:?sm_pEnvString@W3_CGI_HANDLER@@0PEAGEA; Src
0x180005ac8  mov     r8d, esi
0x180005acb  mov     rcx, [r14+20h]; void *
0x180005acf  add     r8, r8; Size
0x180005ad2  call    memcpy_0
0x180005ad7  xor     edx, edx; Val
0x180005ad9  mov     [rsp+110h+Src], 0
0x180005ae2  lea     rcx, [rbp+57h+var_80]; void *
0x180005ae6  mov     [rsp+110h+var_E0], 0
0x180005aee  lea     r8d, [rdx+40h]; Size
0x180005af2  call    memset_0
0x180005af7  mov     r8d, 20h ; ' '
0x180005afd  lea     rdx, [rbp+57h+var_80]
0x180005b01  lea     rcx, [rbp+57h+var_C0]
0x180005b05  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x180005b0b  xor     r12d, r12d
0x180005b0e  lea     rbx, Str1; "ALL_HTTP"
0x180005b15  mov     rcx, [rdi+30h]
0x180005b19  lea     r9, [rsp+110h+var_E0]
0x180005b1e  lea     r8, [rsp+110h+Src]
0x180005b23  mov     rdx, rbx
0x180005b26  mov     rax, [rcx]
0x180005b29  mov     rax, [rax+80h]
0x180005b30  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005b35  mov     edi, eax
0x180005b37  test    eax, eax
0x180005b39  js      loc_180005CC1
0x180005b3f  or      r15, 0FFFFFFFFFFFFFFFFh
0x180005b43  inc     r15
0x180005b46  cmp     byte ptr [rbx+r15], 0
0x180005b4b  jnz     short loc_180005B43
0x180005b4d  mov     edx, [rsp+110h+var_E0]
0x180005b51  mov     r8d, 200h
0x180005b57  add     edx, r15d
0x180005b5a  mov     rcx, r14
0x180005b5d  add     edx, esi
0x180005b5f  lea     edx, ds:4[rdx*2]
0x180005b66  call    cs:__imp_?Resize@BUFFER@@QEAA_NKK@Z; BUFFER::Resize(ulong,ulong)
0x180005b6c  test    al, al
0x180005b6e  jz      loc_180005CAE
0x180005b74  mov     r13, [r14+20h]
0x180005b78  lea     rdx, Str1; "ALL_HTTP"
0x180005b7f  mov     rcx, rbx; Str1
0x180005b82  call    strcmp_0
0x180005b87  test    eax, eax
0x180005b89  jnz     short loc_180005BF6
0x180005b8b  mov     r8d, [rsp+110h+var_E0]
0x180005b90  lea     rbx, ds:0[rsi*2]
0x180005b98  mov     rdx, [rsp+110h+Src]; Src
0x180005b9d  add     rbx, r13
0x180005ba0  inc     r8d
0x180005ba3  mov     rcx, rbx; void *
0x180005ba6  add     r8, r8; Size
0x180005ba9  call    memcpy_0
0x180005bae  mov     edx, 3Ah ; ':'; Ch
0x180005bb3  mov     rcx, rbx; Str
0x180005bb6  call    cs:__imp_wcschr
0x180005bbc  test    rax, rax
0x180005bbf  jz      short loc_180005BF0
0x180005bc1  mov     edx, 0Ah; Ch
0x180005bc6  mov     word ptr [rax], 3Dh ; '='
0x180005bcb  lea     rcx, [rax+2]; Str
0x180005bcf  call    cs:__imp_wcschr
0x180005bd5  xor     ecx, ecx
0x180005bd7  mov     [rax], cx
0x180005bda  lea     edx, [rcx+3Ah]; Ch
0x180005bdd  lea     rcx, [rax+2]; Str
0x180005be1  call    cs:__imp_wcschr
0x180005be7  test    rax, rax
0x180005bea  jnz     short loc_180005BC1
0x180005bec  mov     r14, [rbp+57h+var_D0]
0x180005bf0  add     esi, [rsp+110h+var_E0]
0x180005bf4  jmp     short loc_180005C67
0x180005bf6  mov     r8d, r15d
0x180005bf9  lea     rcx, [rbp+57h+var_C0]
0x180005bfd  mov     rdx, rbx
0x180005c00  call    cs:__imp_?CopyA@STRU@@QEAAJPEBDK@Z; STRU::CopyA(char const *,ulong)
0x180005c06  mov     ebx, eax
0x180005c08  test    eax, eax
0x180005c0a  js      loc_180005CB3
0x180005c10  mov     rdx, [rbp+57h+var_A0]; Src
0x180005c14  lea     rcx, ds:0[rsi*2]
0x180005c1c  mov     ebx, r15d
0x180005c1f  add     rcx, r13; void *
0x180005c22  lea     r8, [rbx+rbx]; Size
0x180005c26  call    memcpy_0
0x180005c2b  lea     rcx, [rbx+rsi]
0x180005c2f  mov     word ptr [r13+rcx*2+0], 3Dh ; '='
0x180005c37  lea     rcx, [rcx+1]
0x180005c3b  mov     r8d, [rsp+110h+var_E0]
0x180005c40  lea     rcx, ds:0[rcx*2]
0x180005c48  mov     rdx, [rsp+110h+Src]; Src
0x180005c4d  inc     r8d
0x180005c50  add     r8, r8; Size
0x180005c53  add     rcx, r13; void *
0x180005c56  call    memcpy_0
0x180005c5b  mov     ecx, [rsp+110h+var_E0]
0x180005c5f  add     esi, 2
0x180005c62  add     ecx, r15d
0x180005c65  add     esi, ecx
0x180005c67  mov     rdi, [rbp+57h+var_C8]
0x180005c6b  lea     rbx, ?g_CGIServerVars@@3PAPEADA; char * near * g_CGIServerVars
0x180005c72  inc     r12d
0x180005c75  mov     rbx, [rbx+r12*8]
0x180005c79  test    rbx, rbx
0x180005c7c  jnz     loc_180005B15
0x180005c82  lea     edx, ds:2[rsi*2]
0x180005c89  mov     rcx, r14
0x180005c8c  call    cs:__imp_?Resize@BUFFER@@QEAA_NK@Z; BUFFER::Resize(ulong)
0x180005c92  test    al, al
0x180005c94  jz      short loc_180005CAE
0x180005c96  mov     rcx, [r14+20h]
0x180005c9a  xor     eax, eax
0x180005c9c  mov     [rcx+rsi*2], ax
0x180005ca0  lea     rcx, [rbp+57h+var_C0]
0x180005ca4  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180005caa  xor     eax, eax
0x180005cac  jmp     short loc_180005CCD
0x180005cae  mov     ebx, 80070008h
0x180005cb3  lea     rcx, [rbp+57h+var_C0]
0x180005cb7  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180005cbd  mov     eax, ebx
0x180005cbf  jmp     short loc_180005CCD
0x180005cc1  lea     rcx, [rbp+57h+var_C0]
0x180005cc5  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180005ccb  mov     eax, edi
0x180005ccd  mov     rcx, [rbp+57h+var_40]
0x180005cd1  xor     rcx, rsp; StackCookie
0x180005cd4  call    __security_check_cookie
0x180005cd9  mov     rbx, [rsp+110h+arg_10]
0x180005ce1  add     rsp, 0E0h
0x180005ce8  pop     r15
0x180005cea  pop     r14
0x180005cec  pop     r13
0x180005cee  pop     r12
0x180005cf0  pop     rdi
0x180005cf1  pop     rsi
0x180005cf2  pop     rbp
0x180005cf3  retn
```
