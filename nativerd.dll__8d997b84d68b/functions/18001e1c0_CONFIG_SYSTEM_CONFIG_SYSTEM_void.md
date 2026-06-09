# CONFIG_SYSTEM::CONFIG_SYSTEM(void)

- ea: `0x18001e1c0`
- end: `0x18001e2cc`
- name: `??0CONFIG_SYSTEM@@QEAA@XZ`
- size: `268`
- prototype: `CONFIG_SYSTEM *__fastcall(CONFIG_SYSTEM *__hidden this)`
- caller_count: `3`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18001f190`
- `0x18003a280`
- `0x18004b640`

## callees

- `0x18001e1c0`
- `0x18004cdfc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x18001e237`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x18001e237`
- `iisutil!??0BUFFER@@QEAA@XZ` at `0x18001e21e`
- `iisutil!??0BUFFER@@QEAA@XZ` at `0x18001e21e`
- `iisutil!??0CReaderWriterLock3@@QEAA@XZ` at `0x18001e294`
- `iisutil!??0CReaderWriterLock3@@QEAA@XZ` at `0x18001e294`
- `iisutil!?TraceCreate@BIG_REF_TRACE@@QEAAJPEAX@Z` at `0x18001e2b3`
- `iisutil!?TraceCreate@BIG_REF_TRACE@@QEAAJPEAX@Z` at `0x18001e2b3`

## pseudocode

```c
CONFIG_SYSTEM *__fastcall CONFIG_SYSTEM::CONFIG_SYSTEM(CONFIG_SYSTEM *this)
{
  BIG_REF_TRACE *v2; // rcx

  *((_QWORD *)this + 1) = &INativeConfigurationSystem::`vftable';
  _InterlockedIncrement(&g_cModuleRefs);
  *((_QWORD *)this + 2) = 0;
  *(_QWORD *)this = &CONFIG_SYSTEM::`vftable'{for `IAppHostWritableAdminManager'};
  *((_QWORD *)this + 1) = &CONFIG_SYSTEM::`vftable'{for `INativeConfigurationSystem'};
  *((_QWORD *)this + 3) = 1;
  *((_QWORD *)this + 4) = 0;
  CONFIG_CACHE::CONFIG_CACHE((CONFIG_SYSTEM *)((char *)this + 40));
  BUFFER::BUFFER((CONFIG_SYSTEM *)((char *)this + 880));
  *((_WORD *)this + 464) = 0;
  *((_QWORD *)this + 118) = 0;
  *((_QWORD *)this + 128) = 0;
  InitializeSRWLock((PSRWLOCK)this + 117);
  *((_QWORD *)this + 130) = 0;
  *((_QWORD *)this + 131) = &PARSE_ERROR_INFO::`vftable';
  *((_QWORD *)this + 132) = 1;
  *((_DWORD *)this + 266) = 0;
  *((_QWORD *)this + 134) = 0;
  *((_QWORD *)this + 135) = 0;
  *((_QWORD *)this + 136) = 0;
  *((_QWORD *)this + 137) = 0;
  *((_QWORD *)this + 138) = 0;
  *((_QWORD *)this + 139) = 0;
  CReaderWriterLock3::CReaderWriterLock3((CONFIG_SYSTEM *)((char *)this + 1120));
  v2 = (BIG_REF_TRACE *)g_pBigRefTrace;
  *((_DWORD *)this + 258) = 268435498;
  if ( v2 )
    BIG_REF_TRACE::TraceCreate(v2, this);
  return this;
}

```

## disassembly

```asm
0x18001e1c0  mov     [rsp+arg_0], rbx
0x18001e1c5  mov     [rsp+arg_8], rbp
0x18001e1ca  push    rdi
0x18001e1cb  sub     rsp, 20h
0x18001e1cf  lea     rax, ??_7INativeConfigurationSystem@@6B@; const INativeConfigurationSystem::`vftable'
0x18001e1d6  mov     rdi, rcx
0x18001e1d9  mov     [rcx+8], rax
0x18001e1dd  lock inc cs:?g_cModuleRefs@@3JC; long volatile g_cModuleRefs
0x18001e1e4  xor     ebp, ebp
0x18001e1e6  lea     rax, ??_7CONFIG_SYSTEM@@6BIAppHostWritableAdminManager@@@; const CONFIG_SYSTEM::`vftable'{for `IAppHostWritableAdminManager'}
0x18001e1ed  mov     [rcx+10h], rbp
0x18001e1f1  mov     [rcx], rax
0x18001e1f4  lea     rax, ??_7CONFIG_SYSTEM@@6BINativeConfigurationSystem@@@; const CONFIG_SYSTEM::`vftable'{for `INativeConfigurationSystem'}
0x18001e1fb  mov     [rcx+8], rax
0x18001e1ff  mov     qword ptr [rcx+18h], 1
0x18001e207  mov     [rcx+20h], rbp
0x18001e20b  add     rcx, 28h ; '('; this
0x18001e20f  call    ??0CONFIG_CACHE@@QEAA@XZ; CONFIG_CACHE::CONFIG_CACHE(void)
0x18001e214  lea     rbx, [rdi+370h]
0x18001e21b  mov     rcx, rbx
0x18001e21e  call    cs:__imp_??0BUFFER@@QEAA@XZ; BUFFER::BUFFER(void)
0x18001e224  lea     rcx, [rbx+38h]; SRWLock
0x18001e228  mov     [rbx+30h], bp
0x18001e22c  mov     [rbx+40h], rbp
0x18001e230  mov     [rbx+90h], rbp
0x18001e237  call    cs:__imp_InitializeSRWLock
0x18001e23d  mov     [rdi+410h], rbp
0x18001e244  lea     rax, ??_7PARSE_ERROR_INFO@@6B@; const PARSE_ERROR_INFO::`vftable'
0x18001e24b  mov     [rdi+418h], rax
0x18001e252  lea     rcx, [rdi+460h]
0x18001e259  mov     qword ptr [rdi+420h], 1
0x18001e264  mov     [rdi+428h], ebp
0x18001e26a  mov     [rdi+430h], rbp
0x18001e271  mov     [rdi+438h], rbp
0x18001e278  mov     [rdi+440h], rbp
0x18001e27f  mov     [rdi+448h], rbp
0x18001e286  mov     [rdi+450h], rbp
0x18001e28d  mov     [rdi+458h], rbp
0x18001e294  call    cs:__imp_??0CReaderWriterLock3@@QEAA@XZ; CReaderWriterLock3::CReaderWriterLock3(void)
0x18001e29a  mov     rcx, cs:?g_pBigRefTrace@@3PEAVBIG_REF_TRACE@@EA; BIG_REF_TRACE * g_pBigRefTrace
0x18001e2a1  mov     dword ptr [rdi+408h], 1000002Ah
0x18001e2ab  test    rcx, rcx
0x18001e2ae  jz      short loc_18001E2B9
0x18001e2b0  mov     rdx, rdi
0x18001e2b3  call    cs:__imp_?TraceCreate@BIG_REF_TRACE@@QEAAJPEAX@Z; BIG_REF_TRACE::TraceCreate(void *)
0x18001e2b9  mov     rbx, [rsp+28h+arg_0]
0x18001e2be  mov     rax, rdi
0x18001e2c1  mov     rbp, [rsp+28h+arg_8]
0x18001e2c6  add     rsp, 20h
0x18001e2ca  pop     rdi
0x18001e2cb  retn
```
