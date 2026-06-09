# USER_SESSION::IsAnonymousUserAllowed(int *)

- ea: `0x1800119e0`
- end: `0x180011a93`
- name: `?IsAnonymousUserAllowed@USER_SESSION@@UEAAJPEAH@Z`
- size: `179`
- prototype: `__int64 __fastcall(USER_SESSION *__hidden this, int *)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callees

- `0x180009090`
- `0x1800119e0`

## import_xrefs

- `iisutil!?ReadLock@CReaderWriterLock3@@QEAAXXZ` at `0x180011a00`
- `iisutil!?ReadLock@CReaderWriterLock3@@QEAAXXZ` at `0x180011a00`
- `iisutil!?Free@ALLOC_CACHE_HANDLER@@QEAAHPEAX@Z` at `0x180011a7a`
- `iisutil!?Free@ALLOC_CACHE_HANDLER@@QEAAHPEAX@Z` at `0x180011a7a`
- `iisutil!?ReadUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x180011a35`
- `iisutil!?ReadUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x180011a35`
- `iisutil!WriteRefTraceLog` at `0x180011a25`
- `iisutil!WriteRefTraceLog` at `0x180011a5d`
- `iisutil!WriteRefTraceLog` at `0x180011a25`
- `iisutil!WriteRefTraceLog` at `0x180011a5d`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall USER_SESSION::IsAnonymousUserAllowed(USER_SESSION *this, int *a2)
{
  __int64 v3; // rbx
  CReaderWriterLock3 *v4; // rdi
  __int64 v5; // rdx
  __int64 v6; // rbx
  unsigned __int32 v7; // edi

  v3 = *((_QWORD *)this + 2);
  v4 = (CReaderWriterLock3 *)(v3 + 208);
  CReaderWriterLock3::ReadLock((CReaderWriterLock3 *)(v3 + 208));
  v5 = (unsigned int)_InterlockedIncrement(*(volatile signed __int32 **)(v3 + 192));
  if ( FTP_SITE_CONFIG::sm_pRefTraceLog )
    WriteRefTraceLog(FTP_SITE_CONFIG::sm_pRefTraceLog, v5);
  v6 = *(_QWORD *)(v3 + 192);
  CReaderWriterLock3::ReadUnlock(v4);
  *a2 = *(_DWORD *)(v6 + 184);
  v7 = _InterlockedDecrement((volatile signed __int32 *)v6);
  if ( FTP_SITE_CONFIG::sm_pRefTraceLog )
    WriteRefTraceLog(FTP_SITE_CONFIG::sm_pRefTraceLog, v7);
  if ( !v7 )
  {
    FTP_SITE_CONFIG::~FTP_SITE_CONFIG((FTP_SITE_CONFIG *)v6);
    ALLOC_CACHE_HANDLER::Free((ALLOC_CACHE_HANDLER *)FTP_SITE_CONFIG::sm_pAllocHandler, (void *)v6);
  }
  return 0;
}

```

## disassembly

```asm
0x1800119e0  mov     [rsp+arg_0], rbx
0x1800119e5  mov     [rsp+arg_8], rsi
0x1800119ea  push    rdi
0x1800119eb  sub     rsp, 20h
0x1800119ef  mov     rsi, rdx
0x1800119f2  mov     rbx, [rcx+10h]
0x1800119f6  lea     rdi, [rbx+0D0h]
0x1800119fd  mov     rcx, rdi
0x180011a00  call    cs:__imp_?ReadLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::ReadLock(void)
0x180011a06  mov     r8, [rbx+0C0h]
0x180011a0d  mov     edx, 1
0x180011a12  lock xadd [r8], edx
0x180011a17  inc     edx
0x180011a19  mov     rcx, cs:?sm_pRefTraceLog@FTP_SITE_CONFIG@@0PEAU_TRACE_LOG@@EA; _TRACE_LOG * FTP_SITE_CONFIG::sm_pRefTraceLog
0x180011a20  test    rcx, rcx
0x180011a23  jz      short loc_180011A2B
0x180011a25  call    cs:__imp_WriteRefTraceLog
0x180011a2b  mov     rbx, [rbx+0C0h]
0x180011a32  mov     rcx, rdi
0x180011a35  call    cs:__imp_?ReadUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::ReadUnlock(void)
0x180011a3b  mov     eax, [rbx+0B8h]
0x180011a41  mov     [rsi], eax
0x180011a43  or      edi, 0FFFFFFFFh
0x180011a46  lock xadd [rbx], edi
0x180011a4a  dec     edi
0x180011a4c  mov     rcx, cs:?sm_pRefTraceLog@FTP_SITE_CONFIG@@0PEAU_TRACE_LOG@@EA; _TRACE_LOG * FTP_SITE_CONFIG::sm_pRefTraceLog
0x180011a53  test    rcx, rcx
0x180011a56  jz      short loc_180011A63
0x180011a58  mov     r8, rbx
0x180011a5b  mov     edx, edi
0x180011a5d  call    cs:__imp_WriteRefTraceLog
0x180011a63  test    edi, edi
0x180011a65  jnz     short loc_180011A81
0x180011a67  mov     rcx, rbx; this
0x180011a6a  call    ??1FTP_SITE_CONFIG@@QEAA@XZ; FTP_SITE_CONFIG::~FTP_SITE_CONFIG(void)
0x180011a6f  nop
0x180011a70  mov     rdx, rbx
0x180011a73  mov     rcx, cs:?sm_pAllocHandler@FTP_SITE_CONFIG@@0PEAVALLOC_CACHE_HANDLER@@EA; ALLOC_CACHE_HANDLER * FTP_SITE_CONFIG::sm_pAllocHandler
0x180011a7a  call    cs:__imp_?Free@ALLOC_CACHE_HANDLER@@QEAAHPEAX@Z; ALLOC_CACHE_HANDLER::Free(void *)
0x180011a80  nop
0x180011a81  xor     eax, eax
0x180011a83  mov     rbx, [rsp+28h+arg_0]
0x180011a88  mov     rsi, [rsp+28h+arg_8]
0x180011a8d  add     rsp, 20h
0x180011a91  pop     rdi
0x180011a92  retn
```
