# FTP_DATA_CHANNEL::AcceptPasiveConnectionOnBackground(void)

- ea: `0x18003ed9c`
- end: `0x18003ef56`
- name: `?AcceptPasiveConnectionOnBackground@FTP_DATA_CHANNEL@@QEAAJXZ`
- size: `442`
- prototype: `__int64 __fastcall(FTP_DATA_CHANNEL *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, loader_planting`

## callers

- `0x18003a8f8`

## callees

- `0x180006e78`
- `0x180007578`
- `0x180009090`
- `0x18000e004`
- `0x18003ed9c`
- `0x1800412e0`
- `0x180049010`

## import_xrefs

- `iisutil!?ReadLock@CReaderWriterLock3@@QEAAXXZ` at `0x18003edf8`
- `iisutil!?ReadLock@CReaderWriterLock3@@QEAAXXZ` at `0x18003edf8`
- `iisutil!?Free@ALLOC_CACHE_HANDLER@@QEAAHPEAX@Z` at `0x18003ee75`
- `iisutil!?Free@ALLOC_CACHE_HANDLER@@QEAAHPEAX@Z` at `0x18003ee75`
- `iisutil!?WriteLock@CSpinLock@@QEAAXXZ` at `0x18003eebd`
- `iisutil!?WriteLock@CSpinLock@@QEAAXXZ` at `0x18003eebd`
- `iisutil!?ReadUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x18003ee2d`
- `iisutil!?ReadUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x18003ee2d`
- `iisutil!WriteRefTraceLog` at `0x18003ee1d`
- `iisutil!WriteRefTraceLog` at `0x18003ee58`
- `iisutil!WriteRefTraceLog` at `0x18003ee1d`
- `iisutil!WriteRefTraceLog` at `0x18003ee58`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall FTP_DATA_CHANNEL::AcceptPasiveConnectionOnBackground(FTP_DATA_CHANNEL *this)
{
  struct FTP_ASYNC_CONTEXT *v2; // rbp
  struct _OVERLAPPED *v3; // r14
  int v4; // edi
  __int64 v5; // rdi
  CReaderWriterLock3 *v6; // rsi
  __int64 v7; // rdx
  __int64 v8; // rdi
  unsigned __int64 v9; // r15
  unsigned __int32 v10; // esi
  FTP_TIMEOUT_MONITOR *v11; // rax

  v2 = (FTP_DATA_CHANNEL *)((char *)this + 288);
  *((_DWORD *)this + 88) = 2;
  v3 = (struct _OVERLAPPED *)((char *)this + 544);
  v4 = FTP_ASYNC_SOCKET::Initialize(
         (FTP_DATA_CHANNEL *)((char *)this + 544),
         *(_DWORD *)(*(_QWORD *)(*((_QWORD *)this + 9) + 1080LL) + 12LL));
  if ( v4 < 0 )
  {
LABEL_13:
    if ( *((_WORD *)this + 1198) )
    {
      (*(void (__fastcall **)(FTP_SERVERP *))(*(_QWORD *)g_pFtpServer + 144LL))(g_pFtpServer);
      *((_WORD *)this + 1198) = 0;
    }
    return (unsigned int)v4;
  }
  v5 = *(_QWORD *)(*((_QWORD *)this + 9) + 96LL);
  v6 = (CReaderWriterLock3 *)(v5 + 208);
  CReaderWriterLock3::ReadLock((CReaderWriterLock3 *)(v5 + 208));
  v7 = (unsigned int)_InterlockedIncrement(*(volatile signed __int32 **)(v5 + 192));
  if ( FTP_SITE_CONFIG::sm_pRefTraceLog )
    WriteRefTraceLog(FTP_SITE_CONFIG::sm_pRefTraceLog, v7);
  v8 = *(_QWORD *)(v5 + 192);
  CReaderWriterLock3::ReadUnlock(v6);
  v9 = (unsigned int)(1000 * *(_DWORD *)(v8 + 152));
  v10 = _InterlockedDecrement((volatile signed __int32 *)v8);
  if ( FTP_SITE_CONFIG::sm_pRefTraceLog )
    WriteRefTraceLog(FTP_SITE_CONFIG::sm_pRefTraceLog, v10);
  if ( !v10 )
  {
    FTP_SITE_CONFIG::~FTP_SITE_CONFIG((FTP_SITE_CONFIG *)v8);
    ALLOC_CACHE_HANDLER::Free((ALLOC_CACHE_HANDLER *)FTP_SITE_CONFIG::sm_pAllocHandler, (void *)v8);
  }
  *((_DWORD *)this + 554) = 1;
  v11 = (FTP_TIMEOUT_MONITOR *)(*(__int64 (__fastcall **)(FTP_SERVERP *))(*(_QWORD *)g_pFtpServer + 88LL))(g_pFtpServer);
  FTP_TIMEOUT_MONITOR::AddEntryToMonitorList(v11, this, v9);
  (***((void (__fastcall ****)(_QWORD))this + 9))(*((_QWORD *)this + 9));
  CSpinLock::WriteLock((FTP_DATA_CHANNEL *)((char *)this + 2144));
  if ( *((_DWORD *)this + 538) )
    v4 = -2147023673;
  else
    v4 = FTP_ASYNC_SOCKET::AcceptNewConnection(v3, (FTP_DATA_CHANNEL *)((char *)this + 1344), v2);
  _InterlockedExchange(
    (volatile __int32 *)this + 536,
    ((*((_BYTE *)this + 2144) - 1) & 3) != 0 ? *((_DWORD *)this + 536) - 1 : 0);
  if ( v4 < 0 )
  {
    FTP_DATA_CHANNEL::StopConnectionIdleMonitor(this);
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 9) + 8LL))(*((_QWORD *)this + 9));
    goto LABEL_13;
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18003ed9c  push    rbx
0x18003ed9e  push    rbp
0x18003ed9f  push    rsi
0x18003eda0  push    rdi
0x18003eda1  push    r12
0x18003eda3  push    r14
0x18003eda5  push    r15
0x18003eda7  sub     rsp, 20h
0x18003edab  mov     rbx, rcx
0x18003edae  lea     rbp, [rcx+120h]
0x18003edb5  mov     dword ptr [rbp+40h], 2
0x18003edbc  lea     r14, [rcx+220h]
0x18003edc3  mov     rax, [rcx+48h]
0x18003edc7  mov     rdx, [rax+438h]
0x18003edce  mov     edx, [rdx+0Ch]; af
0x18003edd1  mov     rcx, r14; this
0x18003edd4  call    ?Initialize@FTP_ASYNC_SOCKET@@QEAAJK@Z; FTP_ASYNC_SOCKET::Initialize(ulong)
0x18003edd9  mov     edi, eax
0x18003eddb  xor     r12d, r12d
0x18003edde  test    eax, eax
0x18003ede0  js      loc_18003EF1B
0x18003ede6  mov     rax, [rbx+48h]
0x18003edea  mov     rdi, [rax+60h]
0x18003edee  lea     rsi, [rdi+0D0h]
0x18003edf5  mov     rcx, rsi
0x18003edf8  call    cs:__imp_?ReadLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::ReadLock(void)
0x18003edfe  mov     r8, [rdi+0C0h]
0x18003ee05  lea     edx, [r12+1]
0x18003ee0a  lock xadd [r8], edx
0x18003ee0f  inc     edx
0x18003ee11  mov     rcx, cs:?sm_pRefTraceLog@FTP_SITE_CONFIG@@0PEAU_TRACE_LOG@@EA; _TRACE_LOG * FTP_SITE_CONFIG::sm_pRefTraceLog
0x18003ee18  test    rcx, rcx
0x18003ee1b  jz      short loc_18003EE23
0x18003ee1d  call    cs:__imp_WriteRefTraceLog
0x18003ee23  mov     rdi, [rdi+0C0h]
0x18003ee2a  mov     rcx, rsi
0x18003ee2d  call    cs:__imp_?ReadUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::ReadUnlock(void)
0x18003ee33  imul    r15d, [rdi+98h], 3E8h
0x18003ee3e  or      esi, 0FFFFFFFFh
0x18003ee41  lock xadd [rdi], esi
0x18003ee45  dec     esi
0x18003ee47  mov     rcx, cs:?sm_pRefTraceLog@FTP_SITE_CONFIG@@0PEAU_TRACE_LOG@@EA; _TRACE_LOG * FTP_SITE_CONFIG::sm_pRefTraceLog
0x18003ee4e  test    rcx, rcx
0x18003ee51  jz      short loc_18003EE5E
0x18003ee53  mov     r8, rdi
0x18003ee56  mov     edx, esi
0x18003ee58  call    cs:__imp_WriteRefTraceLog
0x18003ee5e  test    esi, esi
0x18003ee60  jnz     short loc_18003EE7C
0x18003ee62  mov     rcx, rdi; this
0x18003ee65  call    ??1FTP_SITE_CONFIG@@QEAA@XZ; FTP_SITE_CONFIG::~FTP_SITE_CONFIG(void)
0x18003ee6a  nop
0x18003ee6b  mov     rdx, rdi
0x18003ee6e  mov     rcx, cs:?sm_pAllocHandler@FTP_SITE_CONFIG@@0PEAVALLOC_CACHE_HANDLER@@EA; ALLOC_CACHE_HANDLER * FTP_SITE_CONFIG::sm_pAllocHandler
0x18003ee75  call    cs:__imp_?Free@ALLOC_CACHE_HANDLER@@QEAAHPEAX@Z; ALLOC_CACHE_HANDLER::Free(void *)
0x18003ee7b  nop
0x18003ee7c  mov     dword ptr [rbx+8A8h], 1
0x18003ee86  mov     rcx, cs:?g_pFtpServer@@3PEAVFTP_SERVER@@EA; FTP_SERVER * g_pFtpServer
0x18003ee8d  mov     rax, [rcx]
0x18003ee90  mov     rax, [rax+58h]
0x18003ee94  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ee99  mov     r8, r15; unsigned __int64
0x18003ee9c  mov     rdx, rbx; struct FTP_TIMEOUT_MONITOR_ENTRY *
0x18003ee9f  mov     rcx, rax; this
0x18003eea2  call    ?AddEntryToMonitorList@FTP_TIMEOUT_MONITOR@@QEAAXPEAVFTP_TIMEOUT_MONITOR_ENTRY@@_K@Z; FTP_TIMEOUT_MONITOR::AddEntryToMonitorList(FTP_TIMEOUT_MONITOR_ENTRY *,unsigned __int64)
0x18003eea7  mov     rcx, [rbx+48h]
0x18003eeab  mov     rax, [rcx]
0x18003eeae  mov     rax, [rax]
0x18003eeb1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003eeb6  lea     rcx, [rbx+860h]
0x18003eebd  call    cs:__imp_?WriteLock@CSpinLock@@QEAAXXZ; CSpinLock::WriteLock(void)
0x18003eec3  cmp     [rbx+868h], r12d
0x18003eeca  jz      short loc_18003EED3
0x18003eecc  mov     edi, 800704C7h
0x18003eed1  jmp     short loc_18003EEE7
0x18003eed3  lea     rdx, [rbx+540h]; struct FTP_ASYNC_SOCKET *
0x18003eeda  mov     r8, rbp; struct FTP_ASYNC_CONTEXT *
0x18003eedd  mov     rcx, r14; this
0x18003eee0  call    ?AcceptNewConnection@FTP_ASYNC_SOCKET@@QEAAJPEAV1@PEAVFTP_ASYNC_CONTEXT@@@Z; FTP_ASYNC_SOCKET::AcceptNewConnection(FTP_ASYNC_SOCKET *,FTP_ASYNC_CONTEXT *)
0x18003eee5  mov     edi, eax
0x18003eee7  mov     edx, [rbx+860h]
0x18003eeed  dec     edx
0x18003eeef  mov     eax, edx
0x18003eef1  and     al, 3
0x18003eef3  neg     al
0x18003eef5  sbb     ecx, ecx
0x18003eef7  and     ecx, edx
0x18003eef9  xchg    ecx, [rbx+860h]
0x18003eeff  test    edi, edi
0x18003ef01  jns     short loc_18003EF45
0x18003ef03  mov     rcx, rbx; this
0x18003ef06  call    ?StopConnectionIdleMonitor@FTP_DATA_CHANNEL@@AEAAXXZ; FTP_DATA_CHANNEL::StopConnectionIdleMonitor(void)
0x18003ef0b  mov     rcx, [rbx+48h]
0x18003ef0f  mov     rax, [rcx]
0x18003ef12  mov     rax, [rax+8]
0x18003ef16  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ef1b  movzx   edx, word ptr [rbx+95Ch]
0x18003ef22  test    dx, dx
0x18003ef25  jz      short loc_18003EF45
0x18003ef27  mov     rcx, cs:?g_pFtpServer@@3PEAVFTP_SERVER@@EA; FTP_SERVER * g_pFtpServer
0x18003ef2e  mov     rax, [rcx]
0x18003ef31  mov     rax, [rax+90h]
0x18003ef38  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ef3d  mov     [rbx+95Ch], r12w
0x18003ef45  mov     eax, edi
0x18003ef47  add     rsp, 20h
0x18003ef4b  pop     r15
0x18003ef4d  pop     r14
0x18003ef4f  pop     r12
0x18003ef51  pop     rdi
0x18003ef52  pop     rsi
0x18003ef53  pop     rbp
0x18003ef54  pop     rbx
0x18003ef55  retn
```
