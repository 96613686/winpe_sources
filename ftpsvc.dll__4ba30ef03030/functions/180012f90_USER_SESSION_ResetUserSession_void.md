# USER_SESSION::ResetUserSession(void)

- ea: `0x180012f90`
- end: `0x180013133`
- name: `?ResetUserSession@USER_SESSION@@UEAAXXZ`
- size: `419`
- prototype: `void __fastcall(USER_SESSION *__hidden this)`
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops, registry_config, loader_planting`

## callers

- `0x18000e230`
- `0x18000e3f4`

## callees

- `0x180001250`
- `0x180009090`
- `0x180012f90`
- `0x180017d44`
- `0x180049010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x1800130c2`
- `msvcrt!_wcsicmp` at `0x1800130c2`
- `KERNEL32!FindClose` at `0x180012fd7`
- `KERNEL32!FindClose` at `0x180012fd7`
- `KERNEL32!CloseHandle` at `0x180013086`
- `KERNEL32!CloseHandle` at `0x180013086`
- `iisutil!?Free@ALLOC_CACHE_HANDLER@@QEAAHPEAX@Z` at `0x180013052`
- `iisutil!?Free@ALLOC_CACHE_HANDLER@@QEAAHPEAX@Z` at `0x180013052`
- `iisutil!WriteRefTraceLog` at `0x180013035`
- `iisutil!WriteRefTraceLog` at `0x180013035`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall USER_SESSION::ResetUserSession(USER_SESSION *this)
{
  void *v2; // rcx
  __int64 v3; // rcx
  volatile signed __int32 *v4; // rdi
  unsigned __int32 v5; // esi
  void *v6; // rcx
  char *v7; // rdi
  const wchar_t *v8; // rax
  int v9; // eax
  __int64 v10; // rcx
  void *v11; // rsi

  *((_DWORD *)this + 278) = 0;
  *((_QWORD *)this + 138) = &WideCharStr;
  *((_DWORD *)this + 3) = 4;
  *((_QWORD *)this + 141) = 0;
  v2 = (void *)*((_QWORD *)this + 60);
  if ( v2 != (void *)-1LL )
  {
    FindClose(v2);
    *((_QWORD *)this + 60) = -1;
  }
  v3 = *((_QWORD *)this + 118);
  if ( v3 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 8LL))(v3);
  **((_WORD **)this + 67) = 0;
  *((_DWORD *)this + 138) = 0;
  v4 = (volatile signed __int32 *)*((_QWORD *)this + 117);
  if ( v4 )
  {
    v5 = _InterlockedDecrement(v4);
    if ( FTP_SITE_CONFIG::sm_pRefTraceLog )
      WriteRefTraceLog(FTP_SITE_CONFIG::sm_pRefTraceLog, v5);
    if ( !v5 )
    {
      FTP_SITE_CONFIG::~FTP_SITE_CONFIG((FTP_SITE_CONFIG *)v4);
      ALLOC_CACHE_HANDLER::Free((ALLOC_CACHE_HANDLER *)FTP_SITE_CONFIG::sm_pAllocHandler, (void *)v4);
    }
    *((_QWORD *)this + 117) = 0;
  }
  *((_QWORD *)this + 62) = 0;
  *((_QWORD *)this + 61) = 0;
  v6 = (void *)*((_QWORD *)this + 130);
  if ( v6 != (void *)-1LL )
  {
    CloseHandle(v6);
    *((_QWORD *)this + 130) = -1;
  }
  v7 = (char *)this + 24;
  if ( (*(unsigned int (__fastcall **)(char *))(*((_QWORD *)this + 3) + 48LL))((char *)this + 24) )
  {
    v8 = (const wchar_t *)(**(__int64 (__fastcall ***)(char *))v7)((char *)this + 24);
    v9 = _wcsicmp(v8, L"AnonymousAuth");
    v10 = *((_QWORD *)this + 2);
    if ( v9 )
    {
      _InterlockedAdd((volatile signed __int32 *)(v10 + 120), 0xFFFFFFFF);
      _InterlockedAdd((volatile signed __int32 *)FTP_SITE_PERF_CTRS::sm_pPerfCtrsGlobal + 12, 0xFFFFFFFF);
    }
    else
    {
      _InterlockedAdd((volatile signed __int32 *)(v10 + 116), 0xFFFFFFFF);
      _InterlockedAdd((volatile signed __int32 *)FTP_SITE_PERF_CTRS::sm_pPerfCtrsGlobal + 11, 0xFFFFFFFF);
    }
  }
  v11 = (void *)*((_QWORD *)this + 43);
  if ( v11 )
  {
    FTP_VDIR_PARENT_TABLE::~FTP_VDIR_PARENT_TABLE(*((FTP_VDIR_PARENT_TABLE **)this + 43));
    operator delete(v11);
    *((_QWORD *)this + 43) = 0;
  }
  (*(void (__fastcall **)(char *))(*(_QWORD *)v7 + 40LL))((char *)this + 24);
}

```

## disassembly

```asm
0x180012f90  push    rbx
0x180012f92  push    rsi
0x180012f93  push    rdi
0x180012f94  push    r14
0x180012f96  sub     rsp, 28h
0x180012f9a  mov     rbx, rcx
0x180012f9d  mov     dword ptr [rcx+458h], 0
0x180012fa7  lea     rax, WideCharStr
0x180012fae  mov     [rcx+450h], rax
0x180012fb5  mov     dword ptr [rcx+0Ch], 4
0x180012fbc  mov     qword ptr [rcx+468h], 0
0x180012fc7  mov     rcx, [rcx+1E0h]; hFindFile
0x180012fce  or      r14, 0FFFFFFFFFFFFFFFFh
0x180012fd2  cmp     rcx, r14
0x180012fd5  jz      short loc_180012FE4
0x180012fd7  call    cs:__imp_FindClose
0x180012fdd  mov     [rbx+1E0h], r14
0x180012fe4  mov     rcx, [rbx+3B0h]
0x180012feb  test    rcx, rcx
0x180012fee  jz      short loc_180012FFC
0x180012ff0  mov     rax, [rcx]
0x180012ff3  mov     rax, [rax+8]
0x180012ff7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012ffc  mov     rcx, [rbx+218h]
0x180013003  xor     eax, eax
0x180013005  mov     [rcx], ax
0x180013008  mov     [rbx+228h], eax
0x18001300e  mov     rdi, [rbx+3A8h]
0x180013015  test    rdi, rdi
0x180013018  jz      short loc_180013064
0x18001301a  mov     esi, r14d
0x18001301d  lock xadd [rdi], esi
0x180013021  add     esi, r14d
0x180013024  mov     rcx, cs:?sm_pRefTraceLog@FTP_SITE_CONFIG@@0PEAU_TRACE_LOG@@EA; _TRACE_LOG * FTP_SITE_CONFIG::sm_pRefTraceLog
0x18001302b  test    rcx, rcx
0x18001302e  jz      short loc_18001303B
0x180013030  mov     r8, rdi
0x180013033  mov     edx, esi
0x180013035  call    cs:__imp_WriteRefTraceLog
0x18001303b  test    esi, esi
0x18001303d  jnz     short loc_180013059
0x18001303f  mov     rcx, rdi; this
0x180013042  call    ??1FTP_SITE_CONFIG@@QEAA@XZ; FTP_SITE_CONFIG::~FTP_SITE_CONFIG(void)
0x180013047  nop
0x180013048  mov     rdx, rdi
0x18001304b  mov     rcx, cs:?sm_pAllocHandler@FTP_SITE_CONFIG@@0PEAVALLOC_CACHE_HANDLER@@EA; ALLOC_CACHE_HANDLER * FTP_SITE_CONFIG::sm_pAllocHandler
0x180013052  call    cs:__imp_?Free@ALLOC_CACHE_HANDLER@@QEAAHPEAX@Z; ALLOC_CACHE_HANDLER::Free(void *)
0x180013058  nop
0x180013059  mov     qword ptr [rbx+3A8h], 0
0x180013064  mov     qword ptr [rbx+1F0h], 0
0x18001306f  mov     qword ptr [rbx+1E8h], 0
0x18001307a  mov     rcx, [rbx+410h]; hObject
0x180013081  cmp     rcx, r14
0x180013084  jz      short loc_180013093
0x180013086  call    cs:__imp_CloseHandle
0x18001308c  mov     [rbx+410h], r14
0x180013093  lea     rdi, [rbx+18h]
0x180013097  mov     rax, [rdi]
0x18001309a  mov     rcx, rdi
0x18001309d  mov     rax, [rax+30h]
0x1800130a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800130a6  test    eax, eax
0x1800130a8  jz      short loc_1800130F4
0x1800130aa  mov     rax, [rdi]
0x1800130ad  mov     rcx, rdi
0x1800130b0  mov     rax, [rax]
0x1800130b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800130b8  mov     rcx, rax; String1
0x1800130bb  lea     rdx, aAnonymousauth; "AnonymousAuth"
0x1800130c2  call    cs:__imp__wcsicmp
0x1800130c8  mov     rcx, [rbx+10h]
0x1800130cc  test    eax, eax
0x1800130ce  jnz     short loc_1800130E3
0x1800130d0  lock add [rcx+74h], r14d
0x1800130d5  mov     rax, cs:?sm_pPerfCtrsGlobal@FTP_SITE_PERF_CTRS@@0PEAV1@EA; FTP_SITE_PERF_CTRS * FTP_SITE_PERF_CTRS::sm_pPerfCtrsGlobal
0x1800130dc  lock add [rax+2Ch], r14d
0x1800130e1  jmp     short loc_1800130F4
0x1800130e3  lock add [rcx+78h], r14d
0x1800130e8  mov     rax, cs:?sm_pPerfCtrsGlobal@FTP_SITE_PERF_CTRS@@0PEAV1@EA; FTP_SITE_PERF_CTRS * FTP_SITE_PERF_CTRS::sm_pPerfCtrsGlobal
0x1800130ef  lock add [rax+30h], r14d
0x1800130f4  mov     rsi, [rbx+158h]
0x1800130fb  test    rsi, rsi
0x1800130fe  jz      short loc_18001311B
0x180013100  mov     rcx, rsi; this
0x180013103  call    ??1FTP_VDIR_PARENT_TABLE@@QEAA@XZ; FTP_VDIR_PARENT_TABLE::~FTP_VDIR_PARENT_TABLE(void)
0x180013108  mov     rcx, rsi; Block
0x18001310b  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180013110  mov     qword ptr [rbx+158h], 0
0x18001311b  mov     rax, [rdi]
0x18001311e  mov     rcx, rdi
0x180013121  mov     rax, [rax+28h]
0x180013125  add     rsp, 28h
0x180013129  pop     r14
0x18001312b  pop     rdi
0x18001312c  pop     rsi
0x18001312d  pop     rbx
0x18001312e  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
