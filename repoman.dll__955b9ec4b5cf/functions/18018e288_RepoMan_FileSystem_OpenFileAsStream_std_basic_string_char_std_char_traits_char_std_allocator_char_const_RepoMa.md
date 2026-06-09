# RepoMan::FileSystem::OpenFileAsStream(std::basic_string<char,std::char_traits<char>,std::allocator<char>> const &,RepoMan::FileSystem::OpenMode,RepoMan::ComPtr<IRepoProgress> const &,OpenFlags)

- ea: `0x18018e288`
- end: `0x18018e52c`
- name: `?OpenFileAsStream@FileSystem@RepoMan@@YA?AV?$ComPtr@UIStream@@@2@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@W4OpenMode@12@AEBV?$ComPtr@UIRepoProgress@@@2@W4OpenFlags@@@Z`
- size: `676`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD)`
- caller_count: `8`
- callee_count: `12`
- tags: `broker_com_uri`

## callers

- `0x18000f690`
- `0x18008e540`
- `0x1800a3d1c`
- `0x1800aa3c0`
- `0x1800ce570`
- `0x1800cefb0`
- `0x18018e8a4`
- `0x180194664`

## callees

- `0x180002010`
- `0x1800245b4`
- `0x18002f940`
- `0x180045350`
- `0x1800dfffc`
- `0x18018aed8`
- `0x18018b53c`
- `0x18018c304`
- `0x18018da80`
- `0x18018e288`
- `0x18019a840`
- `0x18019f7a0`

## import_xrefs

- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x18018e31a`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x18018e39f`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x18018e3e5`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x18018e31a`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x18018e39f`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x18018e3e5`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x18018e37e`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x18018e37e`
- `SHLWAPI!SHCreateStreamOnFileEx` at `0x18018e47b`
- `SHLWAPI!SHCreateStreamOnFileEx` at `0x18018e47b`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
IStream **__fastcall RepoMan::FileSystem::OpenFileAsStream(IStream **a1, const CHAR *a2, int a3, _QWORD *a4, char a5)
{
  unsigned __int64 v9; // rcx
  __int64 v10; // rsi
  __int64 v11; // rsi
  __int64 v12; // r15
  __int64 v13; // rdx
  void *v14; // rcx
  _QWORD *v15; // rcx
  RepoMan::FileStream *v16; // rax
  RepoMan::FileStream *v17; // rax
  DWORD v18; // edx
  BOOL v19; // r9d
  int v20; // ebx
  int v21; // ebx
  const WCHAR *v22; // rcx
  unsigned int v23; // eax
  const char *v24; // r9
  IStream *v25; // rcx
  IStream *ppstm; // [rsp+30h] [rbp-61h] BYREF
  int v28; // [rsp+38h] [rbp-59h]
  RepoMan::FileStream *v29; // [rsp+40h] [rbp-51h]
  char v30[8]; // [rsp+48h] [rbp-49h] BYREF
  __int64 v31; // [rsp+50h] [rbp-41h]
  unsigned __int64 v32; // [rsp+58h] [rbp-39h]
  __int64 v33; // [rsp+60h] [rbp-31h]
  __int64 v34; // [rsp+68h] [rbp-29h]
  int v35; // [rsp+70h] [rbp-21h]
  IStream **v36; // [rsp+78h] [rbp-19h]
  LPCWSTR pszFile[2]; // [rsp+80h] [rbp-11h] BYREF
  __m128i si128; // [rsp+90h] [rbp-1h]

  v36 = a1;
  v28 = 0;
  std::deque<std::function<void (void)>>::deque<std::function<void (void)>>(v30);
  v35 = 2;
  v9 = v32;
  if ( v32 <= v34 + 1 )
  {
    std::deque<std::function<void (void)>>::_Growmap(v30);
    v9 = v32;
  }
  v10 = v33 & (v9 - 1);
  v33 = v10;
  if ( !v10 )
    v10 = v9;
  v11 = v10 - 1;
  v12 = v11 & (v9 - 1);
  v13 = v31;
  if ( !*(_QWORD *)(v31 + 8 * v12) )
  {
    v14 = malloc(0x40u);
    if ( !v14 )
      std::_Xbad_alloc();
    *(_QWORD *)(v31 + 8 * v12) = v14;
    v9 = v32;
    v13 = v31;
  }
  v15 = *(_QWORD **)(v13 + 8 * (v11 & (v9 - 1)));
  *v15 = off_1801DB040;
  v15[1] = a2;
  v15[7] = v15;
  v33 = v11;
  if ( !++v34 )
    _invoke_watson(0, 0, 0, 0, 0);
  if ( *a4 )
  {
    *a1 = 0;
    v28 = 2;
    v16 = (RepoMan::FileStream *)malloc(0x50u);
    if ( !v16 )
      std::_Xbad_alloc();
    v29 = v16;
    *a1 = (IStream *)RepoMan::FileStream::FileStream(v16, a2);
    goto LABEL_31;
  }
  if ( (a5 & 1) != 0 )
  {
    *a1 = 0;
    v28 = 4;
    v17 = (RepoMan::FileStream *)malloc(0x68u);
    if ( !v17 )
      std::_Xbad_alloc();
    v29 = v17;
    *a1 = (IStream *)RepoMan::FileSystem::CFileStream::CFileStream((__int64)v17, a2, a3);
    goto LABEL_31;
  }
  RepoMan::utf8_to_wstring((LPWSTR)pszFile, a2);
  v18 = 0;
  v19 = 0;
  if ( !a3 )
  {
    v18 = 32;
    goto LABEL_23;
  }
  v20 = a3 - 1;
  if ( !v20 )
    goto LABEL_20;
  v21 = v20 - 1;
  if ( !v21 )
  {
    v18 = 18;
    goto LABEL_23;
  }
  if ( v21 == 1 )
  {
LABEL_20:
    v18 = 4114;
    v19 = 1;
  }
LABEL_23:
  ppstm = 0;
  v22 = (const WCHAR *)pszFile;
  if ( si128.m128i_i64[1] > 7uLL )
    v22 = pszFile[0];
  v23 = SHCreateStreamOnFileEx(v22, v18, 0x80u, v19, 0, &ppstm);
  RepoMan::RaiseExceptionIfFailed(
    (RepoMan *)v23,
    531,
    (int)"src\\repoman\\src\\reposhared\\pal\\filesystem\\win32\\filesystem.cpp",
    v24);
  *a1 = 0;
  if ( a1 == &ppstm )
  {
    v25 = ppstm;
  }
  else
  {
    *a1 = ppstm;
    v25 = 0;
    ppstm = 0;
  }
  if ( v25 )
  {
    ppstm = 0;
    ((void (__fastcall *)(IStream *))v25->lpVtbl->Release)(v25);
  }
  std::wstring::_Tidy_deallocate(pszFile);
  pszFile[0] = (LPCWSTR)19937;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
LABEL_31:
  RepoMan::Meta::ScopeGuard::~ScopeGuard((RepoMan::Meta::ScopeGuard *)v30);
  return a1;
}

```

## disassembly

```asm
0x18018e288  push    rbp
0x18018e28a  push    rbx
0x18018e28b  push    rsi
0x18018e28c  push    rdi
0x18018e28d  push    r12
0x18018e28f  push    r14
0x18018e291  push    r15
0x18018e293  lea     rbp, [rsp-1Fh]
0x18018e298  sub     rsp, 0B0h
0x18018e29f  mov     rax, cs:__security_cookie
0x18018e2a6  xor     rax, rsp
0x18018e2a9  mov     [rbp+4Fh+var_40], rax
0x18018e2ad  mov     r12, r9
0x18018e2b0  mov     ebx, r8d
0x18018e2b3  mov     r14, rdx
0x18018e2b6  mov     rdi, rcx
0x18018e2b9  mov     [rbp+4Fh+var_68], rcx
0x18018e2bd  mov     [rbp+4Fh+var_A8], 0
0x18018e2c4  lea     rcx, [rbp+4Fh+var_98]
0x18018e2c8  call    ??0?$deque@V?$function@$$A6AXXZ@std@@V?$allocator@V?$function@$$A6AXXZ@std@@@2@@std@@QEAA@XZ; std::deque<std::function<void (void)>>::deque<std::function<void (void)>>(void)
0x18018e2cd  mov     [rbp+4Fh+var_70], 2
0x18018e2d4  mov     rax, [rbp+4Fh+var_78]
0x18018e2d8  inc     rax
0x18018e2db  mov     rcx, [rbp+4Fh+var_88]
0x18018e2df  cmp     rcx, rax
0x18018e2e2  ja      short loc_18018E2F1
0x18018e2e4  lea     rcx, [rbp+4Fh+var_98]
0x18018e2e8  call    ?_Growmap@?$deque@V?$function@$$A6AXXZ@std@@V?$allocator@V?$function@$$A6AXXZ@std@@@2@@std@@AEAAX_K@Z; std::deque<std::function<void (void)>>::_Growmap(unsigned __int64)
0x18018e2ed  mov     rcx, [rbp+4Fh+var_88]
0x18018e2f1  lea     r15, [rcx-1]
0x18018e2f5  mov     rsi, r15
0x18018e2f8  and     rsi, [rbp+4Fh+var_80]
0x18018e2fc  mov     [rbp+4Fh+var_80], rsi
0x18018e300  cmovz   rsi, rcx
0x18018e304  dec     rsi
0x18018e307  and     r15, rsi
0x18018e30a  mov     rdx, [rbp+4Fh+var_90]
0x18018e30e  cmp     qword ptr [rdx+r15*8], 0
0x18018e313  jnz     short loc_18018E33C
0x18018e315  mov     ecx, 40h ; '@'; Size
0x18018e31a  call    cs:__imp_malloc
0x18018e320  mov     rcx, rax
0x18018e323  test    rax, rax
0x18018e326  jz      loc_18018E520
0x18018e32c  mov     rax, [rbp+4Fh+var_90]
0x18018e330  mov     [rax+r15*8], rcx
0x18018e334  mov     rcx, [rbp+4Fh+var_88]
0x18018e338  mov     rdx, [rbp+4Fh+var_90]
0x18018e33c  lea     rax, [rcx-1]
0x18018e340  and     rax, rsi
0x18018e343  mov     rcx, [rdx+rax*8]
0x18018e347  lea     rax, off_1801DB040
0x18018e34e  mov     [rcx], rax
0x18018e351  mov     [rcx+8], r14
0x18018e355  mov     [rcx+38h], rcx
0x18018e359  mov     [rbp+4Fh+var_80], rsi
0x18018e35d  mov     rax, [rbp+4Fh+var_78]
0x18018e361  add     rax, 1
0x18018e365  mov     [rbp+4Fh+var_78], rax
0x18018e369  jnz     short loc_18018E385
0x18018e36b  mov     [rsp+0E0h+Reserved], 0; Reserved
0x18018e374  xor     r9d, r9d; LineNo
0x18018e377  xor     r8d, r8d; FileName
0x18018e37a  xor     edx, edx; FunctionName
0x18018e37c  xor     ecx, ecx; Expression
0x18018e37e  call    cs:__imp__invoke_watson
0x18018e385  cmp     qword ptr [r12], 0
0x18018e38a  jz      short loc_18018E3CC
0x18018e38c  mov     qword ptr [rdi], 0
0x18018e393  mov     [rbp+4Fh+var_A8], 2
0x18018e39a  mov     ecx, 50h ; 'P'; Size
0x18018e39f  call    cs:__imp_malloc
0x18018e3a5  test    rax, rax
0x18018e3a8  jz      loc_18018E526
0x18018e3ae  mov     [rbp+4Fh+var_A0], rax
0x18018e3b2  mov     r9, r12
0x18018e3b5  mov     r8d, ebx
0x18018e3b8  mov     rdx, r14
0x18018e3bb  mov     rcx, rax
0x18018e3be  call    ??0FileStream@RepoMan@@QEAA@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@W4OpenMode@FileSystem@1@AEBV?$ComPtr@UIRepoProgress@@@1@@Z; RepoMan::FileStream::FileStream(std::string const &,RepoMan::FileSystem::OpenMode,RepoMan::ComPtr<IRepoProgress> const &)
0x18018e3c3  nop
0x18018e3c4  mov     [rdi], rax
0x18018e3c7  jmp     loc_18018E4F0
0x18018e3cc  test    [rbp+4Fh+arg_20], 1
0x18018e3d0  jz      short loc_18018E40F
0x18018e3d2  mov     qword ptr [rdi], 0
0x18018e3d9  mov     [rbp+4Fh+var_A8], 4
0x18018e3e0  mov     ecx, 68h ; 'h'; Size
0x18018e3e5  call    cs:__imp_malloc
0x18018e3eb  test    rax, rax
0x18018e3ee  jz      loc_18018E51A
0x18018e3f4  mov     [rbp+4Fh+var_A0], rax
0x18018e3f8  mov     r8d, ebx
0x18018e3fb  mov     rdx, r14
0x18018e3fe  mov     rcx, rax
0x18018e401  call    ??0CFileStream@FileSystem@RepoMan@@QEAA@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@W4OpenMode@12@@Z; RepoMan::FileSystem::CFileStream::CFileStream(std::string const &,RepoMan::FileSystem::OpenMode)
0x18018e406  nop
0x18018e407  mov     [rdi], rax
0x18018e40a  jmp     loc_18018E4F0
0x18018e40f  mov     rdx, r14; lpMultiByteStr
0x18018e412  lea     rcx, [rbp+4Fh+pszFile]; lpWideCharStr
0x18018e416  call    ?utf8_to_wstring@RepoMan@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@3@@Z; RepoMan::utf8_to_wstring(std::string const &)
0x18018e41b  nop
0x18018e41c  xor     edx, edx
0x18018e41e  xor     r9d, r9d; fCreate
0x18018e421  test    ebx, ebx
0x18018e423  jz      short loc_18018E448
0x18018e425  sub     ebx, 1
0x18018e428  jz      short loc_18018E434
0x18018e42a  sub     ebx, 1
0x18018e42d  jz      short loc_18018E441
0x18018e42f  cmp     ebx, 1
0x18018e432  jnz     short loc_18018E44D
0x18018e434  mov     edx, 1012h
0x18018e439  mov     r9d, 1
0x18018e43f  jmp     short loc_18018E44D
0x18018e441  mov     edx, 12h
0x18018e446  jmp     short loc_18018E44D
0x18018e448  mov     edx, 20h ; ' '; grfMode
0x18018e44d  mov     [rbp+4Fh+var_B0], 0
0x18018e455  lea     rcx, [rbp+4Fh+pszFile]
0x18018e459  cmp     [rbp+4Fh+var_48], 7
0x18018e45e  cmova   rcx, [rbp+4Fh+pszFile]; pszFile
0x18018e463  lea     rax, [rbp+4Fh+var_B0]
0x18018e467  mov     [rsp+0E0h+ppstm], rax; ppstm
0x18018e46c  mov     [rsp+0E0h+Reserved], 0; pstmTemplate
0x18018e475  mov     r8d, 80h; dwAttributes
0x18018e47b  call    cs:__imp_SHCreateStreamOnFileEx
0x18018e481  mov     ecx, eax; this
0x18018e483  lea     r8, aSrcRepomanSrcR_14; "src\\repoman\\src\\reposhared\\pal\\fil"...
0x18018e48a  mov     edx, 213h; int
0x18018e48f  call    ?RaiseExceptionIfFailed@RepoMan@@YAXJHQEBD@Z; RepoMan::RaiseExceptionIfFailed(long,int,char const * const)
0x18018e494  mov     qword ptr [rdi], 0
0x18018e49b  lea     rax, [rbp+4Fh+var_B0]
0x18018e49f  cmp     rdi, rax
0x18018e4a2  jz      short loc_18018E4B3
0x18018e4a4  mov     rax, [rbp+4Fh+var_B0]
0x18018e4a8  mov     [rdi], rax
0x18018e4ab  xor     ecx, ecx
0x18018e4ad  mov     [rbp+4Fh+var_B0], rcx
0x18018e4b1  jmp     short loc_18018E4B7
0x18018e4b3  mov     rcx, [rbp+4Fh+var_B0]
0x18018e4b7  test    rcx, rcx
0x18018e4ba  jz      short loc_18018E4D2
0x18018e4bc  mov     [rbp+4Fh+var_B0], 0
0x18018e4c4  mov     rax, [rcx]
0x18018e4c7  mov     rax, [rax+10h]
0x18018e4cb  call    cs:__guard_dispatch_icall_fptr
0x18018e4d1  nop
0x18018e4d2  lea     rcx, [rbp+4Fh+pszFile]
0x18018e4d6  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18018e4db  mov     [rbp+4Fh+pszFile], 4DE1h
0x18018e4e3  movdqa  xmm0, cs:__xmm@000000000000000f0000000000000000
0x18018e4eb  movdqu  xmmword ptr [rbp-1], xmm0
0x18018e4f0  lea     rcx, [rbp+4Fh+var_98]; this
0x18018e4f4  call    ??1ScopeGuard@Meta@RepoMan@@QEAA@XZ; RepoMan::Meta::ScopeGuard::~ScopeGuard(void)
0x18018e4f9  mov     rax, rdi
0x18018e4fc  mov     rcx, [rbp+4Fh+var_40]
0x18018e500  xor     rcx, rsp; StackCookie
0x18018e503  call    __security_check_cookie
0x18018e508  add     rsp, 0B0h
0x18018e50f  pop     r15
0x18018e511  pop     r14
0x18018e513  pop     r12
0x18018e515  pop     rdi
0x18018e516  pop     rsi
0x18018e517  pop     rbx
0x18018e518  pop     rbp
0x18018e519  retn
0x18018e51a  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
0x18018e520  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
0x18018e526  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
```
