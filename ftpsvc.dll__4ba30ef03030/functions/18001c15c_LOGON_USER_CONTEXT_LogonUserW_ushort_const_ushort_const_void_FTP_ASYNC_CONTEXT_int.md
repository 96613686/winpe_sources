# LOGON_USER_CONTEXT::LogonUserW(ushort const *,ushort const *,void *,FTP_ASYNC_CONTEXT *,int *)

- ea: `0x18001c15c`
- end: `0x18001c2f5`
- name: `?LogonUserW@LOGON_USER_CONTEXT@@QEAAJPEBG0PEAXPEAVFTP_ASYNC_CONTEXT@@PEAH@Z`
- size: `409`
- prototype: `__int64 __usercall@<rax>(LOGON_USER_CONTEXT *__hidden this@<rcx>, const unsigned __int16 *@<rdx>, const unsigned __int16 *@<r8>, void *@<r9>, struct FTP_ASYNC_CONTEXT *, int *)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180011ac0`

## callees

- `0x180009090`
- `0x18001c15c`
- `0x18001ccec`
- `0x180049010`

## import_xrefs

- `iisutil!?ReadLock@CReaderWriterLock3@@QEAAXXZ` at `0x18001c189`
- `iisutil!?ReadLock@CReaderWriterLock3@@QEAAXXZ` at `0x18001c189`
- `iisutil!?Free@ALLOC_CACHE_HANDLER@@QEAAHPEAX@Z` at `0x18001c2b8`
- `iisutil!?Free@ALLOC_CACHE_HANDLER@@QEAAHPEAX@Z` at `0x18001c2b8`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18001c1eb`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18001c1fc`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18001c1eb`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18001c1fc`
- `iisutil!?ReadUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x18001c1be`
- `iisutil!?ReadUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x18001c1be`
- `iisutil!WriteRefTraceLog` at `0x18001c1ae`
- `iisutil!WriteRefTraceLog` at `0x18001c29b`
- `iisutil!WriteRefTraceLog` at `0x18001c1ae`
- `iisutil!WriteRefTraceLog` at `0x18001c29b`

## string_xrefs

- `0x18001c2d6`: `An error occurred during the authentication process.`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall LOGON_USER_CONTEXT::LogonUserW(
        LOGON_USER_CONTEXT *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        void *a4,
        struct FTP_ASYNC_CONTEXT *a5,
        int *a6)
{
  __int64 v10; // rbp
  __int64 v11; // rdx
  __int64 v12; // rsi
  int v13; // ebp
  unsigned __int32 v14; // edi

  v10 = *(_QWORD *)(*((_QWORD *)this + 1) + 16LL);
  CReaderWriterLock3::ReadLock((CReaderWriterLock3 *)(v10 + 208));
  v11 = (unsigned int)_InterlockedIncrement(*(volatile signed __int32 **)(v10 + 192));
  if ( FTP_SITE_CONFIG::sm_pRefTraceLog )
    WriteRefTraceLog(FTP_SITE_CONFIG::sm_pRefTraceLog, v11);
  v12 = *(_QWORD *)(v10 + 192);
  CReaderWriterLock3::ReadUnlock((CReaderWriterLock3 *)(v10 + 208));
  (*(void (__fastcall **)(LOGON_USER_CONTEXT *))(*(_QWORD *)this + 8LL))(this);
  *((_DWORD *)this + 54) = 0;
  *((_QWORD *)this + 28) = a4;
  if ( (int)STRU::Copy((LOGON_USER_CONTEXT *)((char *)this + 24), a2) >= 0
    && (int)STRU::Copy((LOGON_USER_CONTEXT *)((char *)this + 80), a3) >= 0 )
  {
    *((_QWORD *)this + 25) = v12 + 264;
    *((_DWORD *)this + 48) = 0;
    *((_QWORD *)this + 26) = 0;
  }
  *((_QWORD *)this + 59) = a5;
  *((_DWORD *)this + 126) = 0;
  *((_QWORD *)this + 64) = &WideCharStr;
  if ( a6 )
    *a6 = 0;
  _InterlockedIncrement((volatile signed __int32 *)(v10 + 152));
  *(_DWORD *)(*((_QWORD *)this + 1) + 12LL) = *(_DWORD *)(v12 + 720);
  v13 = LOGON_USER_CONTEXT::ProcessUserLogon(this, a6);
  v14 = _InterlockedDecrement((volatile signed __int32 *)v12);
  if ( FTP_SITE_CONFIG::sm_pRefTraceLog )
    WriteRefTraceLog(FTP_SITE_CONFIG::sm_pRefTraceLog, v14);
  if ( !v14 )
  {
    FTP_SITE_CONFIG::~FTP_SITE_CONFIG((FTP_SITE_CONFIG *)v12);
    ALLOC_CACHE_HANDLER::Free((ALLOC_CACHE_HANDLER *)FTP_SITE_CONFIG::sm_pAllocHandler, (void *)v12);
  }
  if ( v13 < 0 && !*((_DWORD *)this + 126) )
  {
    *((_DWORD *)this + 126) = 41;
    *((_QWORD *)this + 64) = L"An error occurred during the authentication process.";
  }
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x18001c15c  push    rbx
0x18001c15e  push    rbp
0x18001c15f  push    rsi
0x18001c160  push    rdi
0x18001c161  push    r12
0x18001c163  push    r14
0x18001c165  push    r15
0x18001c167  sub     rsp, 20h
0x18001c16b  mov     r15, r9
0x18001c16e  mov     r14, r8
0x18001c171  mov     r12, rdx
0x18001c174  mov     rbx, rcx
0x18001c177  mov     rax, [rcx+8]
0x18001c17b  mov     rbp, [rax+10h]
0x18001c17f  lea     rdi, [rbp+0D0h]
0x18001c186  mov     rcx, rdi
0x18001c189  call    cs:__imp_?ReadLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::ReadLock(void)
0x18001c18f  mov     r8, [rbp+0C0h]
0x18001c196  mov     edx, 1
0x18001c19b  lock xadd [r8], edx
0x18001c1a0  inc     edx
0x18001c1a2  mov     rcx, cs:?sm_pRefTraceLog@FTP_SITE_CONFIG@@0PEAU_TRACE_LOG@@EA; _TRACE_LOG * FTP_SITE_CONFIG::sm_pRefTraceLog
0x18001c1a9  test    rcx, rcx
0x18001c1ac  jz      short loc_18001C1B4
0x18001c1ae  call    cs:__imp_WriteRefTraceLog
0x18001c1b4  mov     rsi, [rbp+0C0h]
0x18001c1bb  mov     rcx, rdi
0x18001c1be  call    cs:__imp_?ReadUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::ReadUnlock(void)
0x18001c1c4  mov     rax, [rbx]
0x18001c1c7  mov     rcx, rbx
0x18001c1ca  mov     rax, [rax+8]
0x18001c1ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c1d3  mov     dword ptr [rbx+0D8h], 0
0x18001c1dd  mov     [rbx+0E0h], r15
0x18001c1e4  mov     rdx, r12
0x18001c1e7  lea     rcx, [rbx+18h]
0x18001c1eb  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x18001c1f1  test    eax, eax
0x18001c1f3  js      short loc_18001C229
0x18001c1f5  lea     rcx, [rbx+50h]
0x18001c1f9  mov     rdx, r14
0x18001c1fc  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x18001c202  test    eax, eax
0x18001c204  js      short loc_18001C229
0x18001c206  lea     rax, [rsi+108h]
0x18001c20d  mov     [rbx+0C8h], rax
0x18001c214  mov     dword ptr [rbx+0C0h], 0
0x18001c21e  mov     qword ptr [rbx+0D0h], 0
0x18001c229  mov     rax, [rsp+58h+arg_20]
0x18001c231  mov     [rbx+1D8h], rax
0x18001c238  mov     dword ptr [rbx+1F8h], 0
0x18001c242  lea     rax, WideCharStr
0x18001c249  mov     [rbx+200h], rax
0x18001c250  mov     rdx, [rsp+58h+arg_28]; int *
0x18001c258  test    rdx, rdx
0x18001c25b  jz      short loc_18001C263
0x18001c25d  mov     dword ptr [rdx], 0
0x18001c263  lock inc dword ptr [rbp+98h]
0x18001c26a  mov     rcx, [rbx+8]
0x18001c26e  mov     eax, [rsi+2D0h]
0x18001c274  mov     [rcx+0Ch], eax
0x18001c277  mov     rcx, rbx; this
0x18001c27a  call    ?ProcessUserLogon@LOGON_USER_CONTEXT@@QEAAJPEAH@Z; LOGON_USER_CONTEXT::ProcessUserLogon(int *)
0x18001c27f  mov     ebp, eax
0x18001c281  or      edi, 0FFFFFFFFh
0x18001c284  lock xadd [rsi], edi
0x18001c288  dec     edi
0x18001c28a  mov     rcx, cs:?sm_pRefTraceLog@FTP_SITE_CONFIG@@0PEAU_TRACE_LOG@@EA; _TRACE_LOG * FTP_SITE_CONFIG::sm_pRefTraceLog
0x18001c291  test    rcx, rcx
0x18001c294  jz      short loc_18001C2A1
0x18001c296  mov     r8, rsi
0x18001c299  mov     edx, edi
0x18001c29b  call    cs:__imp_WriteRefTraceLog
0x18001c2a1  test    edi, edi
0x18001c2a3  jnz     short loc_18001C2BF
0x18001c2a5  mov     rcx, rsi; this
0x18001c2a8  call    ??1FTP_SITE_CONFIG@@QEAA@XZ; FTP_SITE_CONFIG::~FTP_SITE_CONFIG(void)
0x18001c2ad  nop
0x18001c2ae  mov     rdx, rsi
0x18001c2b1  mov     rcx, cs:?sm_pAllocHandler@FTP_SITE_CONFIG@@0PEAVALLOC_CACHE_HANDLER@@EA; ALLOC_CACHE_HANDLER * FTP_SITE_CONFIG::sm_pAllocHandler
0x18001c2b8  call    cs:__imp_?Free@ALLOC_CACHE_HANDLER@@QEAAHPEAX@Z; ALLOC_CACHE_HANDLER::Free(void *)
0x18001c2be  nop
0x18001c2bf  test    ebp, ebp
0x18001c2c1  jns     short loc_18001C2E4
0x18001c2c3  cmp     dword ptr [rbx+1F8h], 0
0x18001c2ca  jnz     short loc_18001C2E4
0x18001c2cc  mov     dword ptr [rbx+1F8h], 29h ; ')'
0x18001c2d6  lea     rax, aAnErrorOccurre; "An error occurred during the authentica"...
0x18001c2dd  mov     [rbx+200h], rax
0x18001c2e4  mov     eax, ebp
0x18001c2e6  add     rsp, 20h
0x18001c2ea  pop     r15
0x18001c2ec  pop     r14
0x18001c2ee  pop     r12
0x18001c2f0  pop     rdi
0x18001c2f1  pop     rsi
0x18001c2f2  pop     rbp
0x18001c2f3  pop     rbx
0x18001c2f4  retn
```
