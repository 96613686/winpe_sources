# IIS_MODULE::CreateParams(IHttpContext *)

- ea: `0x18000b564`
- end: `0x18000ba33`
- name: `?CreateParams@IIS_MODULE@@AEAAJPEAVIHttpContext@@@Z`
- size: `1231`
- prototype: `__int64 __fastcall(IIS_MODULE *__hidden this, struct IHttpContext *)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, installer_update`

## callers

- `0x18000cb30`

## callees

- `0x180001008`
- `0x180001048`
- `0x18000b564`
- `0x18000e330`
- `0x18000edc6`
- `0x18000ee10`
- `0x180010010`

## import_xrefs

- `msvcrt!strchr` at `0x18000b660`
- `msvcrt!strchr` at `0x18000b673`
- `msvcrt!strchr` at `0x18000b6c3`
- `msvcrt!strchr` at `0x18000b6d6`
- `msvcrt!strchr` at `0x18000b660`
- `msvcrt!strchr` at `0x18000b673`
- `msvcrt!strchr` at `0x18000b6c3`
- `msvcrt!strchr` at `0x18000b6d6`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18000b906`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18000b9b3`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18000b906`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18000b9b3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b913`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b9c0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b913`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b9c0`
- `iisutil!?CopyW@STRA@@QEAAJPEBG@Z` at `0x18000b775`
- `iisutil!?CopyW@STRA@@QEAAJPEBG@Z` at `0x18000b775`
- `iisutil!?Append@MULTISZA@@QEAAHAEAVSTRA@@@Z` at `0x18000b790`
- `iisutil!?Append@MULTISZA@@QEAAHAEAVSTRA@@@Z` at `0x18000b790`
- `iisutil!??0STRA@@QEAA@PEADK@Z` at `0x18000b5c2`
- `iisutil!??0STRA@@QEAA@PEADK@Z` at `0x18000b5c2`
- `iisutil!??1STRA@@QEAA@XZ` at `0x18000b5fd`
- `iisutil!??1STRA@@QEAA@XZ` at `0x18000b5fd`

## pseudocode

```c
__int64 __fastcall IIS_MODULE::CreateParams(IIS_MODULE *this, struct IHttpContext *a2)
{
  struct _FCGI_PARAM *v3; // rdi
  signed int v4; // ebx
  unsigned int v6; // r14d
  char *v7; // rbx
  char *v8; // rsi
  __int64 v9; // rdx
  IIS_MODULE *v10; // rcx
  int v11; // eax
  unsigned int v12; // eax
  unsigned int v13; // esi
  __int64 v14; // rsi
  unsigned int v15; // r12d
  __int64 v16; // r8
  IIS_MODULE *v17; // rcx
  __int64 v18; // rax
  __int64 v19; // rax
  __int64 v20; // rax
  __int64 v21; // rcx
  unsigned int v22; // edx
  unsigned int v23; // r12d
  __int64 v24; // rsi
  __int64 v25; // rdx
  __int64 v26; // r12
  unsigned int v27; // eax
  int cbMultiByte; // r13d
  signed int LastError; // eax
  __int64 v30; // rax
  CHAR *lpMultiByteStr; // rax
  CHAR *v32; // r12
  unsigned int v33; // [rsp+50h] [rbp-B0h] BYREF
  struct _FCGI_PARAM *v34; // [rsp+58h] [rbp-A8h] BYREF
  unsigned int v35; // [rsp+60h] [rbp-A0h] BYREF
  char *Str; // [rsp+68h] [rbp-98h] BYREF
  int v37; // [rsp+70h] [rbp-90h]
  int v38; // [rsp+74h] [rbp-8Ch] BYREF
  int v39; // [rsp+78h] [rbp-88h] BYREF
  int v40; // [rsp+7Ch] [rbp-84h] BYREF
  __int64 v41; // [rsp+80h] [rbp-80h] BYREF
  LPCWCH lpWideCharStr; // [rsp+88h] [rbp-78h] BYREF
  __int64 v43; // [rsp+90h] [rbp-70h] BYREF
  __int64 v44; // [rsp+98h] [rbp-68h] BYREF
  _BYTE v45[64]; // [rsp+A0h] [rbp-60h] BYREF
  char v46[64]; // [rsp+E0h] [rbp-20h] BYREF

  Str = 0;
  v38 = 0;
  v40 = 0;
  v35 = 0;
  v41 = 0;
  v43 = 0;
  v39 = 0;
  v44 = 0;
  STRA::STRA((STRA *)v45, v46, 0x40u);
  v33 = 59;
  v34 = (struct _FCGI_PARAM *)operator new(0x760u);
  v3 = v34;
  if ( v34 )
  {
    v4 = (*(__int64 (__fastcall **)(_QWORD, const char *, char **, int *))(**((_QWORD **)this + 21) + 120LL))(
           *((_QWORD *)this + 21),
           "ALL_HTTP",
           &Str,
           &v38);
    if ( v4 < 0 )
      goto LABEL_3;
    v6 = 0;
    v7 = strchr(Str, 58);
    v8 = strchr(Str, 10);
    while ( v7 && v8 )
    {
      v9 = 32LL * v6;
      *(_QWORD *)((char *)v3 + v9) = Str;
      *(_DWORD *)((char *)v3 + v9 + 8) = (_DWORD)v7 - (_DWORD)Str;
      *(_QWORD *)((char *)v3 + v9 + 16) = v7 + 1;
      *(_DWORD *)((char *)v3 + v9 + 24) = (_DWORD)v8 - (_DWORD)v7 - 1;
      Str = v8 + 1;
      v7 = strchr(v8 + 1, 58);
      ++v6;
      v8 = strchr(Str, 10);
      v11 = IIS_MODULE::ResizeParamsIfNeeded(v10, &v34, &v33, v6 + 42);
      v3 = v34;
      if ( !v11 )
        goto LABEL_2;
    }
    v4 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, int *, unsigned int *, __int64 *, __int64 *, int *, __int64 *))(**((_QWORD **)this + 21) + 280LL))(
           *((_QWORD *)this + 21),
           0,
           &v40,
           &v35,
           &v41,
           &v43,
           &v39,
           &v44);
    if ( v4 < 0 )
      goto LABEL_3;
    v12 = v35;
    v13 = 0;
    if ( v35 )
    {
      do
      {
        v4 = STRA::CopyW((STRA *)v45, *(const unsigned __int16 **)(v43 + 8LL * v13));
        if ( v4 < 0 )
          goto LABEL_3;
        if ( !MULTISZA::Append((IIS_MODULE *)((char *)this + 176), (struct STRA *)v45) )
          goto LABEL_2;
        v12 = v35;
      }
      while ( ++v13 < v35 );
    }
    v14 = *((_QWORD *)this + 26);
    v15 = 0;
    if ( v12 )
    {
      while ( 1 )
      {
        v16 = 32LL * v6;
        *(_QWORD *)((char *)v3 + v16) = *(_QWORD *)(v41 + 8LL * v15);
        v17 = *(IIS_MODULE **)(v41 + 8LL * v15);
        v18 = -1;
        do
          ++v18;
        while ( *((_BYTE *)v17 + v18) );
        *(_DWORD *)((char *)v3 + v16 + 8) = v18;
        v19 = -1;
        *(_QWORD *)((char *)v3 + v16 + 16) = v14;
        do
          ++v19;
        while ( *(_BYTE *)(v14 + v19) );
        *(_DWORD *)((char *)v3 + v16 + 24) = v19;
        if ( !(unsigned int)IIS_MODULE::ResizeParamsIfNeeded(v17, &v34, &v33, ++v6 + 42) )
          break;
        v20 = -1;
        do
          ++v20;
        while ( *(_BYTE *)(v14 + v20) );
        v3 = v34;
        v21 = v20 + v14 + 1;
        ++v15;
        v14 = v21 & -(__int64)(*(_BYTE *)v21 != 0);
        if ( !v14 )
          v14 = v21;
        if ( v15 >= v35 )
          goto LABEL_27;
      }
      v3 = v34;
      v4 = -2147024882;
      goto LABEL_3;
    }
LABEL_27:
    memcpy_0((char *)v3 + 32 * v6, &IIS_MODULE::sm_rgParams, 0x560u);
    v22 = v6 + 43;
    v37 = 0;
    LODWORD(v34) = v6 + 43;
    v23 = 0;
    if ( v6 >= v6 + 43 )
    {
LABEL_45:
      *((_QWORD *)this + 15) = v3;
      *((_DWORD *)this + 32) = v22;
      goto LABEL_5;
    }
    while ( 1 )
    {
      v24 = 32LL * v6;
      v25 = *(_QWORD *)((char *)v3 + v24);
      if ( *((_DWORD *)IIS_MODULE::sm_pfSendUtf8 + v23) == 1 )
        break;
      v4 = (*(__int64 (__fastcall **)(_QWORD, __int64, __int64, __int64))(**((_QWORD **)this + 21) + 120LL))(
             *((_QWORD *)this + 21),
             v25,
             (__int64)v3 + v24 + 16,
             (__int64)v3 + v24 + 24);
      if ( v4 < 0 )
        goto LABEL_3;
LABEL_42:
      v22 = (unsigned int)v34;
      if ( ++v6 >= (unsigned int)v34 )
        goto LABEL_45;
      v37 = ++v23;
    }
    v26 = *((_QWORD *)this + 21);
    lpWideCharStr = 0;
    v33 = 0;
    v4 = (*(__int64 (__fastcall **)(__int64, __int64, LPCWCH *, unsigned int *))(*(_QWORD *)v26 + 128LL))(
           v26,
           v25,
           &lpWideCharStr,
           &v33);
    if ( v4 >= 0 )
    {
      v27 = WideCharToMultiByte(0xFDE9u, 0, lpWideCharStr, v33 + 1, 0, 0, 0, 0);
      cbMultiByte = v27;
      if ( v27 )
      {
        lpMultiByteStr = (CHAR *)(*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v26 + 144LL))(v26, v27);
        v32 = lpMultiByteStr;
        if ( !lpMultiByteStr )
        {
          v4 = -2147024888;
          goto LABEL_3;
        }
        if ( WideCharToMultiByte(0xFDE9u, 0, lpWideCharStr, v33 + 1, lpMultiByteStr, cbMultiByte, 0, 0) )
        {
          *(_QWORD *)((char *)v3 + v24 + 16) = v32;
LABEL_34:
          v30 = -1;
          do
            ++v30;
          while ( *(_BYTE *)(*(_QWORD *)((char *)v3 + v24 + 16) + v30) );
          v23 = v37;
          *(_DWORD *)((char *)v3 + v24 + 24) = v30;
          goto LABEL_42;
        }
      }
      LastError = GetLastError();
      v4 = LastError;
      if ( LastError > 0 )
        v4 = (unsigned __int16)LastError | 0x80070000;
    }
    if ( v4 < 0 )
      goto LABEL_3;
    goto LABEL_34;
  }
LABEL_2:
  v4 = -2147024882;
LABEL_3:
  if ( v3 )
    operator delete(v3);
LABEL_5:
  STRA::~STRA((STRA *)v45);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18000b564  push    rbp
0x18000b566  push    rbx
0x18000b567  push    rsi
0x18000b568  push    rdi
0x18000b569  push    r12
0x18000b56b  push    r13
0x18000b56d  push    r14
0x18000b56f  push    r15
0x18000b571  lea     rbp, [rsp-38h]
0x18000b576  sub     rsp, 138h
0x18000b57d  mov     rax, cs:__security_cookie
0x18000b584  xor     rax, rsp
0x18000b587  mov     [rbp+70h+var_50], rax
0x18000b58b  xor     r13d, r13d
0x18000b58e  lea     rdx, [rbp+70h+var_90]
0x18000b592  mov     r15, rcx
0x18000b595  mov     [rsp+170h+Str], r13
0x18000b59a  lea     rcx, [rbp+70h+var_D0]
0x18000b59e  mov     [rsp+170h+var_FC], r13d
0x18000b5a3  mov     [rsp+170h+var_F4], r13d
0x18000b5a8  lea     r8d, [r13+40h]
0x18000b5ac  mov     [rsp+170h+var_110], r13d
0x18000b5b1  mov     [rbp+70h+var_F0], r13
0x18000b5b5  mov     [rbp+70h+var_E0], r13
0x18000b5b9  mov     [rsp+170h+var_F8], r13d
0x18000b5be  mov     [rbp+70h+var_D8], r13
0x18000b5c2  call    cs:__imp_??0STRA@@QEAA@PEADK@Z; STRA::STRA(char *,ulong)
0x18000b5c8  mov     ecx, 760h; Size
0x18000b5cd  mov     [rsp+170h+var_120], 3Bh ; ';'
0x18000b5d5  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000b5da  mov     [rsp+170h+var_118], rax
0x18000b5df  mov     rdi, rax
0x18000b5e2  test    rax, rax
0x18000b5e5  jnz     short loc_18000B625
0x18000b5e7  mov     ebx, 8007000Eh
0x18000b5ec  test    rdi, rdi
0x18000b5ef  jz      short loc_18000B5F9
0x18000b5f1  mov     rcx, rdi; Block
0x18000b5f4  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000b5f9  lea     rcx, [rbp+70h+var_D0]
0x18000b5fd  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x18000b603  mov     eax, ebx
0x18000b605  mov     rcx, [rbp+70h+var_50]
0x18000b609  xor     rcx, rsp; StackCookie
0x18000b60c  call    __security_check_cookie
0x18000b611  add     rsp, 138h
0x18000b618  pop     r15
0x18000b61a  pop     r14
0x18000b61c  pop     r13
0x18000b61e  pop     r12
0x18000b620  pop     rdi
0x18000b621  pop     rsi
0x18000b622  pop     rbx
0x18000b623  pop     rbp
0x18000b624  retn
0x18000b625  mov     rcx, [r15+0A8h]
0x18000b62c  lea     r9, [rsp+170h+var_FC]
0x18000b631  lea     r8, [rsp+170h+Str]
0x18000b636  lea     rdx, aAllHttp; "ALL_HTTP"
0x18000b63d  mov     rax, [rcx]
0x18000b640  mov     rax, [rax+78h]
0x18000b644  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b649  mov     ebx, eax
0x18000b64b  test    eax, eax
0x18000b64d  js      short loc_18000B5EC
0x18000b64f  mov     rcx, [rsp+170h+Str]; Str
0x18000b654  mov     r12d, 3Ah ; ':'
0x18000b65a  mov     edx, r12d; Val
0x18000b65d  mov     r14d, r13d
0x18000b660  call    cs:__imp_strchr
0x18000b666  mov     rcx, [rsp+170h+Str]; Str
0x18000b66b  lea     edx, [r12-30h]; Val
0x18000b670  mov     rbx, rax
0x18000b673  call    cs:__imp_strchr
0x18000b679  mov     rsi, rax
0x18000b67c  jmp     loc_18000B702
0x18000b681  test    rsi, rsi
0x18000b684  jz      loc_18000B70B
0x18000b68a  mov     rcx, [rsp+170h+Str]
0x18000b68f  mov     eax, ebx
0x18000b691  mov     edx, r14d
0x18000b694  shl     rdx, 5
0x18000b698  mov     [rdx+rdi], rcx
0x18000b69c  lea     rcx, [rsi+1]; Str
0x18000b6a0  sub     eax, dword ptr [rsp+170h+Str]
0x18000b6a4  mov     [rdx+rdi+8], eax
0x18000b6a8  lea     rax, [rbx+1]
0x18000b6ac  mov     [rdx+rdi+10h], rax
0x18000b6b1  mov     eax, esi
0x18000b6b3  sub     eax, ebx
0x18000b6b5  dec     eax
0x18000b6b7  mov     [rdx+rdi+18h], eax
0x18000b6bb  mov     edx, r12d; Val
0x18000b6be  mov     [rsp+170h+Str], rcx
0x18000b6c3  call    cs:__imp_strchr
0x18000b6c9  mov     rcx, [rsp+170h+Str]; Str
0x18000b6ce  mov     edx, 0Ah; Val
0x18000b6d3  mov     rbx, rax
0x18000b6d6  call    cs:__imp_strchr
0x18000b6dc  inc     r14d
0x18000b6df  lea     r8, [rsp+170h+var_120]; unsigned int *
0x18000b6e4  lea     rdx, [rsp+170h+var_118]; struct _FCGI_PARAM **
0x18000b6e9  mov     rsi, rax
0x18000b6ec  lea     r9d, [r14+2Ah]; unsigned int
0x18000b6f0  call    ?ResizeParamsIfNeeded@IIS_MODULE@@AEAAHPEAPEAU_FCGI_PARAM@@PEAKK@Z; IIS_MODULE::ResizeParamsIfNeeded(_FCGI_PARAM * *,ulong *,ulong)
0x18000b6f5  mov     rdi, [rsp+170h+var_118]
0x18000b6fa  test    eax, eax
0x18000b6fc  jz      loc_18000B5E7
0x18000b702  test    rbx, rbx
0x18000b705  jnz     loc_18000B681
0x18000b70b  mov     rcx, [r15+0A8h]
0x18000b712  lea     rdx, [rbp+70h+var_D8]
0x18000b716  mov     [rsp+170h+lpUsedDefaultChar], rdx
0x18000b71b  lea     r9, [rsp+170h+var_110]
0x18000b720  lea     rdx, [rsp+170h+var_F8]
0x18000b725  mov     [rsp+170h+lpDefaultChar], rdx
0x18000b72a  lea     r8, [rsp+170h+var_F4]
0x18000b72f  mov     rax, [rcx]
0x18000b732  lea     rdx, [rbp+70h+var_E0]
0x18000b736  mov     qword ptr [rsp+170h+cbMultiByte], rdx
0x18000b73b  lea     rdx, [rbp+70h+var_F0]
0x18000b73f  mov     [rsp+170h+lpMultiByteStr], rdx
0x18000b744  xor     edx, edx
0x18000b746  mov     rax, [rax+118h]
0x18000b74d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b752  mov     ebx, eax
0x18000b754  test    eax, eax
0x18000b756  js      loc_18000B5EC
0x18000b75c  mov     eax, [rsp+170h+var_110]
0x18000b760  mov     esi, r13d
0x18000b763  test    eax, eax
0x18000b765  jz      short loc_18000B7A8
0x18000b767  mov     rdx, [rbp+70h+var_E0]
0x18000b76b  lea     rcx, [rbp+70h+var_D0]
0x18000b76f  mov     eax, esi
0x18000b771  mov     rdx, [rdx+rax*8]
0x18000b775  call    cs:__imp_?CopyW@STRA@@QEAAJPEBG@Z; STRA::CopyW(ushort const *)
0x18000b77b  mov     ebx, eax
0x18000b77d  test    eax, eax
0x18000b77f  js      loc_18000B5EC
0x18000b785  lea     rcx, [r15+0B0h]
0x18000b78c  lea     rdx, [rbp+70h+var_D0]
0x18000b790  call    cs:__imp_?Append@MULTISZA@@QEAAHAEAVSTRA@@@Z; MULTISZA::Append(STRA &)
0x18000b796  test    eax, eax
0x18000b798  jz      loc_18000B5E7
0x18000b79e  mov     eax, [rsp+170h+var_110]
0x18000b7a2  inc     esi
0x18000b7a4  cmp     esi, eax
0x18000b7a6  jb      short loc_18000B767
0x18000b7a8  mov     rsi, [r15+0D0h]
0x18000b7af  or      r9, 0FFFFFFFFFFFFFFFFh
0x18000b7b3  mov     r12d, r13d
0x18000b7b6  test    eax, eax
0x18000b7b8  jz      loc_18000B859
0x18000b7be  mov     rax, [rbp+70h+var_F0]
0x18000b7c2  mov     edx, r12d
0x18000b7c5  mov     r8d, r14d
0x18000b7c8  shl     r8, 5
0x18000b7cc  mov     rcx, [rax+rdx*8]
0x18000b7d0  mov     [r8+rdi], rcx
0x18000b7d4  mov     rax, [rbp+70h+var_F0]
0x18000b7d8  mov     rcx, [rax+rdx*8]; this
0x18000b7dc  mov     rax, r9
0x18000b7df  inc     rax
0x18000b7e2  cmp     [rcx+rax], r13b
0x18000b7e6  jnz     short loc_18000B7DF
0x18000b7e8  mov     [r8+rdi+8], eax
0x18000b7ed  mov     rax, r9
0x18000b7f0  mov     [r8+rdi+10h], rsi
0x18000b7f5  inc     rax
0x18000b7f8  cmp     [rsi+rax], r13b
0x18000b7fc  jnz     short loc_18000B7F5
0x18000b7fe  mov     [r8+rdi+18h], eax
0x18000b803  lea     rdx, [rsp+170h+var_118]; struct _FCGI_PARAM **
0x18000b808  inc     r14d
0x18000b80b  lea     r8, [rsp+170h+var_120]; unsigned int *
0x18000b810  lea     r9d, [r14+2Ah]; unsigned int
0x18000b814  call    ?ResizeParamsIfNeeded@IIS_MODULE@@AEAAHPEAPEAU_FCGI_PARAM@@PEAKK@Z; IIS_MODULE::ResizeParamsIfNeeded(_FCGI_PARAM * *,ulong *,ulong)
0x18000b819  test    eax, eax
0x18000b81b  jz      loc_18000B953
0x18000b821  or      r9, 0FFFFFFFFFFFFFFFFh
0x18000b825  mov     rax, r9
0x18000b828  inc     rax
0x18000b82b  cmp     [rsi+rax], r13b
0x18000b82f  jnz     short loc_18000B828
0x18000b831  mov     rdi, [rsp+170h+var_118]
0x18000b836  lea     rcx, [rsi+1]
0x18000b83a  add     rcx, rax
0x18000b83d  mov     al, [rcx]
0x18000b83f  neg     al
0x18000b841  sbb     rsi, rsi
0x18000b844  inc     r12d
0x18000b847  and     rsi, rcx
0x18000b84a  cmovz   rsi, rcx
0x18000b84e  cmp     r12d, [rsp+170h+var_110]
0x18000b853  jb      loc_18000B7BE
0x18000b859  mov     ecx, r14d
0x18000b85c  lea     rdx, ?sm_rgParams@IIS_MODULE@@0PAU_FCGI_PARAM@@A; Src
0x18000b863  shl     rcx, 5
0x18000b867  mov     r8d, 560h; Size
0x18000b86d  add     rcx, rdi; void *
0x18000b870  call    memcpy_0
0x18000b875  lea     edx, [r14+2Bh]
0x18000b879  mov     [rsp+170h+var_100], r13d
0x18000b87e  mov     dword ptr [rsp+170h+var_118], edx
0x18000b882  mov     r12d, r13d
0x18000b885  cmp     r14d, edx
0x18000b888  jnb     loc_18000BA23
0x18000b88e  mov     rax, cs:?sm_pfSendUtf8@IIS_MODULE@@0PEAHEA; int * IIS_MODULE::sm_pfSendUtf8
0x18000b895  mov     esi, r14d
0x18000b898  shl     rsi, 5
0x18000b89c  mov     ecx, r12d
0x18000b89f  mov     rdx, [rsi+rdi]
0x18000b8a3  cmp     dword ptr [rax+rcx*4], 1
0x18000b8a7  jnz     loc_18000B9D5
0x18000b8ad  mov     r12, [r15+0A8h]
0x18000b8b4  lea     r9, [rsp+170h+var_120]
0x18000b8b9  lea     r8, [rbp+70h+lpWideCharStr]
0x18000b8bd  mov     [rbp+70h+lpWideCharStr], r13
0x18000b8c1  mov     rcx, r12
0x18000b8c4  mov     [rsp+170h+var_120], r13d
0x18000b8c9  mov     rax, [r12]
0x18000b8cd  mov     rax, [rax+80h]
0x18000b8d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b8d9  mov     ebx, eax
0x18000b8db  test    eax, eax
0x18000b8dd  js      short loc_18000B92B
0x18000b8df  mov     r9d, [rsp+170h+var_120]
0x18000b8e4  xor     edx, edx; dwFlags
0x18000b8e6  mov     r8, [rbp+70h+lpWideCharStr]; lpWideCharStr
0x18000b8ea  inc     r9d; cchWideChar
0x18000b8ed  mov     [rsp+170h+lpUsedDefaultChar], r13; lpUsedDefaultChar
0x18000b8f2  mov     ecx, 0FDE9h; CodePage
0x18000b8f7  mov     [rsp+170h+lpDefaultChar], r13; lpDefaultChar
0x18000b8fc  mov     [rsp+170h+cbMultiByte], r13d; cbMultiByte
0x18000b901  mov     [rsp+170h+lpMultiByteStr], r13; lpMultiByteStr
0x18000b906  call    cs:__imp_WideCharToMultiByte
0x18000b90c  mov     r13d, eax
0x18000b90f  test    eax, eax
0x18000b911  jnz     short loc_18000B962
0x18000b913  call    cs:__imp_GetLastError
0x18000b919  xor     r13d, r13d
0x18000b91c  mov     ebx, eax
0x18000b91e  test    eax, eax
0x18000b920  jle     short loc_18000B92B
0x18000b922  movzx   ebx, ax
0x18000b925  or      ebx, 80070000h
0x18000b92b  test    ebx, ebx
0x18000b92d  js      loc_18000B5EC
0x18000b933  mov     rcx, [rsi+rdi+10h]
0x18000b938  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000b93c  inc     rax
0x18000b93f  cmp     [rcx+rax], r13b
0x18000b943  jnz     short loc_18000B93C
0x18000b945  mov     r12d, [rsp+170h+var_100]
0x18000b94a  mov     [rsi+rdi+18h], eax
0x18000b94e  jmp     loc_18000BA00
0x18000b953  mov     rdi, [rsp+170h+var_118]
0x18000b958  mov     ebx, 8007000Eh
0x18000b95d  jmp     loc_18000B5EC
0x18000b962  mov     rax, [r12]
0x18000b966  mov     edx, r13d
0x18000b969  mov     rcx, r12
0x18000b96c  mov     rax, [rax+90h]
0x18000b973  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b978  mov     r12, rax
0x18000b97b  test    rax, rax
0x18000b97e  jz      loc_18000BA19
0x18000b984  mov     r9d, [rsp+170h+var_120]
0x18000b989  xor     edx, edx; dwFlags
0x18000b98b  mov     r8, [rbp+70h+lpWideCharStr]; lpWideCharStr
0x18000b98f  inc     r9d; cchWideChar
0x18000b992  mov     [rsp+170h+lpUsedDefaultChar], 0; lpUsedDefaultChar
0x18000b99b  mov     ecx, 0FDE9h; CodePage
0x18000b9a0  mov     [rsp+170h+lpDefaultChar], 0; lpDefaultChar
0x18000b9a9  mov     [rsp+170h+cbMultiByte], r13d; cbMultiByte
0x18000b9ae  mov     [rsp+170h+lpMultiByteStr], rax; lpMultiByteStr
0x18000b9b3  call    cs:__imp_WideCharToMultiByte
0x18000b9b9  xor     r13d, r13d
0x18000b9bc  test    eax, eax
0x18000b9be  jnz     short loc_18000B9CB
0x18000b9c0  call    cs:__imp_GetLastError
0x18000b9c6  jmp     loc_18000B91C
0x18000b9cb  mov     [rsi+rdi+10h], r12
0x18000b9d0  jmp     loc_18000B933
0x18000b9d5  mov     rcx, [r15+0A8h]
0x18000b9dc  lea     r9, [rdi+18h]
0x18000b9e0  lea     r8, [rdi+10h]
0x18000b9e4  add     r9, rsi
0x18000b9e7  add     r8, rsi
0x18000b9ea  mov     rax, [rcx]
0x18000b9ed  mov     rax, [rax+78h]
0x18000b9f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b9f6  mov     ebx, eax
0x18000b9f8  test    eax, eax
0x18000b9fa  js      loc_18000B5EC
0x18000ba00  mov     edx, dword ptr [rsp+170h+var_118]
0x18000ba04  inc     r14d
0x18000ba07  cmp     r14d, edx
0x18000ba0a  jnb     short loc_18000BA23
  ... truncated ...
```
