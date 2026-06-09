# LOGON_USER_CONTEXT::RequestCustomProviderUpdate(ulong)

- ea: `0x18001d704`
- end: `0x18001d813`
- name: `?RequestCustomProviderUpdate@LOGON_USER_CONTEXT@@AEAAJK@Z`
- size: `271`
- prototype: `__int64 __fastcall(LOGON_USER_CONTEXT *__hidden this, unsigned int)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, loader_planting, installer_update`

## callers

- `0x18001bd7c`
- `0x18001d8a0`

## callees

- `0x180009090`
- `0x1800199d4`
- `0x180019b48`
- `0x18001d704`
- `0x180049010`

## import_xrefs

- `iisutil!?ReadLock@CReaderWriterLock3@@QEAAXXZ` at `0x18001d727`
- `iisutil!?ReadLock@CReaderWriterLock3@@QEAAXXZ` at `0x18001d727`
- `iisutil!?Free@ALLOC_CACHE_HANDLER@@QEAAHPEAX@Z` at `0x18001d7fa`
- `iisutil!?Free@ALLOC_CACHE_HANDLER@@QEAAHPEAX@Z` at `0x18001d7fa`
- `iisutil!?ReadUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x18001d75c`
- `iisutil!?ReadUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x18001d75c`
- `iisutil!WriteRefTraceLog` at `0x18001d74c`
- `iisutil!WriteRefTraceLog` at `0x18001d7dd`
- `iisutil!WriteRefTraceLog` at `0x18001d74c`
- `iisutil!WriteRefTraceLog` at `0x18001d7dd`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall LOGON_USER_CONTEXT::RequestCustomProviderUpdate(LOGON_USER_CONTEXT *this, unsigned int a2)
{
  __int64 v2; // rbx
  __int64 v3; // rdi
  CReaderWriterLock3 *v4; // rsi
  __int64 v5; // rdx
  __int64 v6; // rdi
  struct IUnknown *v7; // rcx
  CUSTOM_PROVIDER_ENTRY *v8; // rbx
  unsigned int ReferencedProvider; // esi
  unsigned __int32 v10; // ebx
  struct IUnknown *v12; // [rsp+30h] [rbp+8h] BYREF

  v2 = a2;
  v3 = *(_QWORD *)(*((_QWORD *)this + 1) + 16LL);
  v4 = (CReaderWriterLock3 *)(v3 + 208);
  CReaderWriterLock3::ReadLock((CReaderWriterLock3 *)(v3 + 208));
  v5 = (unsigned int)_InterlockedIncrement(*(volatile signed __int32 **)(v3 + 192));
  if ( FTP_SITE_CONFIG::sm_pRefTraceLog )
    WriteRefTraceLog(FTP_SITE_CONFIG::sm_pRefTraceLog, v5);
  v6 = *(_QWORD *)(v3 + 192);
  CReaderWriterLock3::ReadUnlock(v4);
  v7 = 0;
  v12 = 0;
  if ( (unsigned int)v2 > *(_DWORD *)(v6 + 272) )
  {
    ReferencedProvider = -2147024809;
  }
  else
  {
    v8 = (CUSTOM_PROVIDER_ENTRY *)(*(_QWORD *)(v6 + 280) + 600 * v2);
    CUSTOM_PROVIDER_ENTRY::Invalidate(v8);
    ReferencedProvider = CUSTOM_PROVIDER_ENTRY::GetReferencedProvider(
                           v8,
                           &GUID_00000000_0000_0000_c000_000000000046,
                           &v12);
    v7 = v12;
  }
  if ( v7 )
  {
    ((void (__fastcall *)(struct IUnknown *))v7->lpVtbl->Release)(v7);
    v12 = 0;
  }
  v10 = _InterlockedDecrement((volatile signed __int32 *)v6);
  if ( FTP_SITE_CONFIG::sm_pRefTraceLog )
    WriteRefTraceLog(FTP_SITE_CONFIG::sm_pRefTraceLog, v10);
  if ( !v10 )
  {
    FTP_SITE_CONFIG::~FTP_SITE_CONFIG((FTP_SITE_CONFIG *)v6);
    ALLOC_CACHE_HANDLER::Free((ALLOC_CACHE_HANDLER *)FTP_SITE_CONFIG::sm_pAllocHandler, (void *)v6);
  }
  return ReferencedProvider;
}

```

## disassembly

```asm
0x18001d704  mov     [rsp+arg_8], rbx
0x18001d709  mov     [rsp+arg_10], rsi
0x18001d70e  push    rdi
0x18001d70f  sub     rsp, 20h
0x18001d713  mov     ebx, edx
0x18001d715  mov     rax, [rcx+8]
0x18001d719  mov     rdi, [rax+10h]
0x18001d71d  lea     rsi, [rdi+0D0h]
0x18001d724  mov     rcx, rsi
0x18001d727  call    cs:__imp_?ReadLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::ReadLock(void)
0x18001d72d  mov     r8, [rdi+0C0h]
0x18001d734  mov     edx, 1
0x18001d739  lock xadd [r8], edx
0x18001d73e  inc     edx
0x18001d740  mov     rcx, cs:?sm_pRefTraceLog@FTP_SITE_CONFIG@@0PEAU_TRACE_LOG@@EA; _TRACE_LOG * FTP_SITE_CONFIG::sm_pRefTraceLog
0x18001d747  test    rcx, rcx
0x18001d74a  jz      short loc_18001D752
0x18001d74c  call    cs:__imp_WriteRefTraceLog
0x18001d752  mov     rdi, [rdi+0C0h]
0x18001d759  mov     rcx, rsi
0x18001d75c  call    cs:__imp_?ReadUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::ReadUnlock(void)
0x18001d762  xor     ecx, ecx
0x18001d764  mov     [rsp+28h+arg_0], rcx
0x18001d769  cmp     ebx, [rdi+110h]
0x18001d76f  ja      short loc_18001D7A4
0x18001d771  imul    rbx, 258h
0x18001d778  add     rbx, [rdi+118h]
0x18001d77f  mov     rcx, rbx; this
0x18001d782  call    ?Invalidate@CUSTOM_PROVIDER_ENTRY@@QEAAXXZ; CUSTOM_PROVIDER_ENTRY::Invalidate(void)
0x18001d787  lea     r8, [rsp+28h+arg_0]; struct IUnknown **
0x18001d78c  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046; struct _GUID *
0x18001d793  mov     rcx, rbx; this
0x18001d796  call    ?GetReferencedProvider@CUSTOM_PROVIDER_ENTRY@@QEAAJAEBU_GUID@@PEAPEAUIUnknown@@@Z; CUSTOM_PROVIDER_ENTRY::GetReferencedProvider(_GUID const &,IUnknown * *)
0x18001d79b  mov     esi, eax
0x18001d79d  mov     rcx, [rsp+28h+arg_0]
0x18001d7a2  jmp     short loc_18001D7A9
0x18001d7a4  mov     esi, 80070057h
0x18001d7a9  test    rcx, rcx
0x18001d7ac  jz      short loc_18001D7C3
0x18001d7ae  mov     rax, [rcx]
0x18001d7b1  mov     rax, [rax+10h]
0x18001d7b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d7ba  mov     [rsp+28h+arg_0], 0
0x18001d7c3  or      ebx, 0FFFFFFFFh
0x18001d7c6  lock xadd [rdi], ebx
0x18001d7ca  dec     ebx
0x18001d7cc  mov     rcx, cs:?sm_pRefTraceLog@FTP_SITE_CONFIG@@0PEAU_TRACE_LOG@@EA; _TRACE_LOG * FTP_SITE_CONFIG::sm_pRefTraceLog
0x18001d7d3  test    rcx, rcx
0x18001d7d6  jz      short loc_18001D7E3
0x18001d7d8  mov     r8, rdi
0x18001d7db  mov     edx, ebx
0x18001d7dd  call    cs:__imp_WriteRefTraceLog
0x18001d7e3  test    ebx, ebx
0x18001d7e5  jnz     short loc_18001D801
0x18001d7e7  mov     rcx, rdi; this
0x18001d7ea  call    ??1FTP_SITE_CONFIG@@QEAA@XZ; FTP_SITE_CONFIG::~FTP_SITE_CONFIG(void)
0x18001d7ef  nop
0x18001d7f0  mov     rdx, rdi
0x18001d7f3  mov     rcx, cs:?sm_pAllocHandler@FTP_SITE_CONFIG@@0PEAVALLOC_CACHE_HANDLER@@EA; ALLOC_CACHE_HANDLER * FTP_SITE_CONFIG::sm_pAllocHandler
0x18001d7fa  call    cs:__imp_?Free@ALLOC_CACHE_HANDLER@@QEAAHPEAX@Z; ALLOC_CACHE_HANDLER::Free(void *)
0x18001d800  nop
0x18001d801  mov     eax, esi
0x18001d803  mov     rbx, [rsp+28h+arg_8]
0x18001d808  mov     rsi, [rsp+28h+arg_10]
0x18001d80d  add     rsp, 20h
0x18001d811  pop     rdi
0x18001d812  retn
```
