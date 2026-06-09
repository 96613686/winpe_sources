# LOGON_USER_CONTEXT::LookupCredentialsCache(CREDENTIALS_CACHE_ENTRY * *)

- ea: `0x18001c2fc`
- end: `0x18001c44a`
- name: `?LookupCredentialsCache@LOGON_USER_CONTEXT@@AEAAJPEAPEAVCREDENTIALS_CACHE_ENTRY@@@Z`
- size: `334`
- prototype: `int(LOGON_USER_CONTEXT *__hidden this, struct CREDENTIALS_CACHE_ENTRY **)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callers

- `0x18001c998`

## callees

- `0x180009090`
- `0x18001c2fc`
- `0x18001e368`
- `0x180049010`

## import_xrefs

- `iisutil!?ReadLock@CReaderWriterLock3@@QEAAXXZ` at `0x18001c328`
- `iisutil!?ReadLock@CReaderWriterLock3@@QEAAXXZ` at `0x18001c328`
- `iisutil!?Free@ALLOC_CACHE_HANDLER@@QEAAHPEAX@Z` at `0x18001c432`
- `iisutil!?Free@ALLOC_CACHE_HANDLER@@QEAAHPEAX@Z` at `0x18001c432`
- `iisutil!?ReadUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x18001c35b`
- `iisutil!?ReadUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x18001c35b`
- `iisutil!WriteRefTraceLog` at `0x18001c34b`
- `iisutil!WriteRefTraceLog` at `0x18001c415`
- `iisutil!WriteRefTraceLog` at `0x18001c34b`
- `iisutil!WriteRefTraceLog` at `0x18001c415`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall LOGON_USER_CONTEXT::LookupCredentialsCache(
        LOGON_USER_CONTEXT *this,
        struct CREDENTIALS_CACHE_ENTRY **a2)
{
  int CachedCredentials; // edi
  __int64 v5; // rsi
  CReaderWriterLock3 *v6; // rbx
  __int64 v7; // rdx
  __int64 v8; // rsi
  unsigned int v9; // r14d
  unsigned int v10; // ebp
  __int64 v11; // rbx
  CREDENTIALS_CACHE *v12; // r10
  __int64 v13; // rcx
  unsigned __int16 *v14; // rdx
  unsigned __int32 v15; // ebx

  CachedCredentials = 0;
  *a2 = 0;
  v5 = *(_QWORD *)(*((_QWORD *)this + 1) + 16LL);
  v6 = (CReaderWriterLock3 *)(v5 + 208);
  CReaderWriterLock3::ReadLock((CReaderWriterLock3 *)(v5 + 208));
  v7 = (unsigned int)_InterlockedIncrement(*(volatile signed __int32 **)(v5 + 192));
  if ( FTP_SITE_CONFIG::sm_pRefTraceLog )
    WriteRefTraceLog(FTP_SITE_CONFIG::sm_pRefTraceLog, v7);
  v8 = *(_QWORD *)(v5 + 192);
  CReaderWriterLock3::ReadUnlock(v6);
  v9 = *(_DWORD *)(v8 + 272);
  v10 = 0;
  if ( v9 )
  {
    while ( v10 <= *(_DWORD *)(v8 + 272) )
    {
      v11 = *(_QWORD *)(v8 + 280);
      v12 = (CREDENTIALS_CACHE *)(*(__int64 (__fastcall **)(FTP_SERVERP *))(*(_QWORD *)g_pFtpServer + 192LL))(g_pFtpServer);
      v13 = *(_QWORD *)(*((_QWORD *)this + 1) + 16LL);
      v14 = (unsigned __int16 *)&dword_18004D454;
      if ( *(_QWORD *)(v13 + 8) )
        v14 = *(unsigned __int16 **)(v13 + 8);
      CachedCredentials = CREDENTIALS_CACHE::GetCachedCredentials(
                            v12,
                            *((const unsigned __int16 **)this + 7),
                            *((const BYTE **)this + 14),
                            *(const unsigned __int16 **)(600LL * v10 + v11 + 56),
                            v14,
                            a2);
      if ( CachedCredentials >= 0 && !*a2 && ++v10 < v9 )
        continue;
      goto LABEL_12;
    }
    CachedCredentials = -2147024809;
  }
LABEL_12:
  if ( v8 )
  {
    v15 = _InterlockedDecrement((volatile signed __int32 *)v8);
    if ( FTP_SITE_CONFIG::sm_pRefTraceLog )
      WriteRefTraceLog(FTP_SITE_CONFIG::sm_pRefTraceLog, v15);
    if ( !v15 )
    {
      FTP_SITE_CONFIG::~FTP_SITE_CONFIG((FTP_SITE_CONFIG *)v8);
      ALLOC_CACHE_HANDLER::Free((ALLOC_CACHE_HANDLER *)FTP_SITE_CONFIG::sm_pAllocHandler, (void *)v8);
    }
  }
  return (unsigned int)CachedCredentials;
}

```

## disassembly

```asm
0x18001c2fc  push    rbx
0x18001c2fe  push    rbp
0x18001c2ff  push    rsi
0x18001c300  push    rdi
0x18001c301  push    r13
0x18001c303  push    r14
0x18001c305  push    r15
0x18001c307  sub     rsp, 30h
0x18001c30b  mov     r15, rdx
0x18001c30e  mov     r13, rcx
0x18001c311  xor     edi, edi
0x18001c313  mov     [rdx], rdi
0x18001c316  mov     rax, [rcx+8]
0x18001c31a  mov     rsi, [rax+10h]
0x18001c31e  lea     rbx, [rsi+0D0h]
0x18001c325  mov     rcx, rbx
0x18001c328  call    cs:__imp_?ReadLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::ReadLock(void)
0x18001c32e  mov     r8, [rsi+0C0h]
0x18001c335  lea     edx, [rdi+1]
0x18001c338  lock xadd [r8], edx
0x18001c33d  inc     edx
0x18001c33f  mov     rcx, cs:?sm_pRefTraceLog@FTP_SITE_CONFIG@@0PEAU_TRACE_LOG@@EA; _TRACE_LOG * FTP_SITE_CONFIG::sm_pRefTraceLog
0x18001c346  test    rcx, rcx
0x18001c349  jz      short loc_18001C351
0x18001c34b  call    cs:__imp_WriteRefTraceLog
0x18001c351  mov     rsi, [rsi+0C0h]
0x18001c358  mov     rcx, rbx
0x18001c35b  call    cs:__imp_?ReadUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::ReadUnlock(void)
0x18001c361  mov     r14d, [rsi+110h]
0x18001c368  xor     ebp, ebp
0x18001c36a  test    r14d, r14d
0x18001c36d  jz      loc_18001C3F6
0x18001c373  cmp     ebp, [rsi+110h]
0x18001c379  ja      short loc_18001C3F1
0x18001c37b  mov     eax, ebp
0x18001c37d  imul    rdi, rax, 258h
0x18001c384  mov     rbx, [rsi+118h]
0x18001c38b  mov     rcx, cs:?g_pFtpServer@@3PEAVFTP_SERVER@@EA; FTP_SERVER * g_pFtpServer
0x18001c392  mov     rax, [rcx]
0x18001c395  mov     rax, [rax+0C0h]
0x18001c39c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c3a1  mov     r10, rax
0x18001c3a4  mov     rax, [r13+8]
0x18001c3a8  mov     rcx, [rax+10h]
0x18001c3ac  lea     rdx, dword_18004D454
0x18001c3b3  cmp     qword ptr [rcx+8], 0
0x18001c3b8  cmovnz  rdx, [rcx+8]
0x18001c3bd  mov     [rsp+68h+var_40], r15; struct CREDENTIALS_CACHE_ENTRY **
0x18001c3c2  mov     [rsp+68h+var_48], rdx; unsigned __int16 *
0x18001c3c7  mov     r9, [rdi+rbx+38h]; unsigned __int16 *
0x18001c3cc  mov     r8, [r13+70h]; unsigned __int16 *
0x18001c3d0  mov     rdx, [r13+38h]; unsigned __int16 *
0x18001c3d4  mov     rcx, r10; this
0x18001c3d7  call    ?GetCachedCredentials@CREDENTIALS_CACHE@@QEAAJPEBG000PEAPEAVCREDENTIALS_CACHE_ENTRY@@@Z; CREDENTIALS_CACHE::GetCachedCredentials(ushort const *,ushort const *,ushort const *,ushort const *,CREDENTIALS_CACHE_ENTRY * *)
0x18001c3dc  mov     edi, eax
0x18001c3de  test    eax, eax
0x18001c3e0  js      short loc_18001C3F6
0x18001c3e2  cmp     qword ptr [r15], 0
0x18001c3e6  jnz     short loc_18001C3F6
0x18001c3e8  inc     ebp
0x18001c3ea  cmp     ebp, r14d
0x18001c3ed  jb      short loc_18001C373
0x18001c3ef  jmp     short loc_18001C3F6
0x18001c3f1  mov     edi, 80070057h
0x18001c3f6  test    rsi, rsi
0x18001c3f9  jz      short loc_18001C439
0x18001c3fb  or      ebx, 0FFFFFFFFh
0x18001c3fe  lock xadd [rsi], ebx
0x18001c402  dec     ebx
0x18001c404  mov     rcx, cs:?sm_pRefTraceLog@FTP_SITE_CONFIG@@0PEAU_TRACE_LOG@@EA; _TRACE_LOG * FTP_SITE_CONFIG::sm_pRefTraceLog
0x18001c40b  test    rcx, rcx
0x18001c40e  jz      short loc_18001C41B
0x18001c410  mov     r8, rsi
0x18001c413  mov     edx, ebx
0x18001c415  call    cs:__imp_WriteRefTraceLog
0x18001c41b  test    ebx, ebx
0x18001c41d  jnz     short loc_18001C439
0x18001c41f  mov     rcx, rsi; this
0x18001c422  call    ??1FTP_SITE_CONFIG@@QEAA@XZ; FTP_SITE_CONFIG::~FTP_SITE_CONFIG(void)
0x18001c427  nop
0x18001c428  mov     rdx, rsi
0x18001c42b  mov     rcx, cs:?sm_pAllocHandler@FTP_SITE_CONFIG@@0PEAVALLOC_CACHE_HANDLER@@EA; ALLOC_CACHE_HANDLER * FTP_SITE_CONFIG::sm_pAllocHandler
0x18001c432  call    cs:__imp_?Free@ALLOC_CACHE_HANDLER@@QEAAHPEAX@Z; ALLOC_CACHE_HANDLER::Free(void *)
0x18001c438  nop
0x18001c439  mov     eax, edi
0x18001c43b  add     rsp, 30h
0x18001c43f  pop     r15
0x18001c441  pop     r14
0x18001c443  pop     r13
0x18001c445  pop     rdi
0x18001c446  pop     rsi
0x18001c447  pop     rbp
0x18001c448  pop     rbx
0x18001c449  retn
```
