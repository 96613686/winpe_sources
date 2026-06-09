# FTP_DATA_CHANNEL::EstablishActiveConnectionOnBackground(sockaddr const *)

- ea: `0x18003f6b0`
- end: `0x18003f9ad`
- name: `?EstablishActiveConnectionOnBackground@FTP_DATA_CHANNEL@@QEAAJPEBUsockaddr@@@Z`
- size: `765`
- prototype: `__int64 __fastcall(FTP_DATA_CHANNEL *__hidden this, const struct sockaddr *)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, loader_planting`

## callers

- `0x18003add4`

## callees

- `0x180006fc0`
- `0x180007154`
- `0x180007578`
- `0x180009090`
- `0x18000e004`
- `0x18003f6b0`
- `0x1800412e0`
- `0x180046ff7`
- `0x18004700f`
- `0x180047050`
- `0x180049010`

## import_xrefs

- `WS2_32!__imp_htons` at `0x18003f822`
- `WS2_32!__imp_htons` at `0x18003f822`
- `WS2_32!__imp_ntohs` at `0x18003f815`
- `WS2_32!__imp_ntohs` at `0x18003f815`
- `WS2_32!__imp_setsockopt` at `0x18003f7ac`
- `WS2_32!__imp_setsockopt` at `0x18003f7ac`
- `WS2_32!__imp_WSAGetLastError` at `0x18003f7b7`
- `WS2_32!__imp_WSAGetLastError` at `0x18003f7b7`
- `iisutil!?ReadLock@CReaderWriterLock3@@QEAAXXZ` at `0x18003f77a`
- `iisutil!?ReadLock@CReaderWriterLock3@@QEAAXXZ` at `0x18003f856`
- `iisutil!?ReadLock@CReaderWriterLock3@@QEAAXXZ` at `0x18003f77a`
- `iisutil!?ReadLock@CReaderWriterLock3@@QEAAXXZ` at `0x18003f856`
- `iisutil!?Free@ALLOC_CACHE_HANDLER@@QEAAHPEAX@Z` at `0x18003f8d2`
- `iisutil!?Free@ALLOC_CACHE_HANDLER@@QEAAHPEAX@Z` at `0x18003f8d2`
- `iisutil!?WriteLock@CSpinLock@@QEAAXXZ` at `0x18003f90c`
- `iisutil!?WriteLock@CSpinLock@@QEAAXXZ` at `0x18003f90c`
- `iisutil!?ReadUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x18003f7cf`
- `iisutil!?ReadUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x18003f88a`
- `iisutil!?ReadUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x18003f7cf`
- `iisutil!?ReadUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x18003f88a`
- `iisutil!WriteRefTraceLog` at `0x18003f87a`
- `iisutil!WriteRefTraceLog` at `0x18003f8b5`
- `iisutil!WriteRefTraceLog` at `0x18003f87a`
- `iisutil!WriteRefTraceLog` at `0x18003f8b5`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall FTP_DATA_CHANNEL::EstablishActiveConnectionOnBackground(
        FTP_DATA_CHANNEL *this,
        const struct sockaddr *a2)
{
  int v4; // ebx
  SOCKET v5; // rcx
  int Error; // eax
  __int64 v7; // rbx
  size_t v8; // r8
  u_short v9; // ax
  __int64 v10; // rbx
  CReaderWriterLock3 *v11; // rsi
  __int64 v12; // rdx
  __int64 v13; // rbx
  unsigned __int64 v14; // r12
  unsigned __int32 v15; // esi
  FTP_TIMEOUT_MONITOR *v16; // rax
  char optval[16]; // [rsp+30h] [rbp-D8h] BYREF
  struct sockaddr v19; // [rsp+40h] [rbp-C8h] BYREF

  *(_DWORD *)optval = 1;
  memset_0(&v19, 0, 0x80u);
  *((_DWORD *)this + 88) = 1;
  *((_QWORD *)this + 300) = 0;
  **((_WORD **)this + 305) = 0;
  *((_DWORD *)this + 614) = 0;
  *((_DWORD *)this + 537) = 0;
  if ( *((_WORD *)this + 1198) )
  {
    (*(void (__fastcall **)(FTP_SERVERP *))(*(_QWORD *)g_pFtpServer + 144LL))(g_pFtpServer);
    *((_WORD *)this + 1198) = 0;
  }
  v4 = FTP_ASYNC_SOCKET::Initialize((FTP_DATA_CHANNEL *)((char *)this + 544), a2->sa_family);
  if ( v4 >= 0 )
  {
    CReaderWriterLock3::ReadLock((FTP_DATA_CHANNEL *)((char *)this + 1120));
    v5 = *((_QWORD *)this + 70);
    if ( v5 == -1 )
    {
      v4 = -2147023660;
    }
    else
    {
      v4 = 0;
      if ( setsockopt(v5, 0xFFFF, 4, optval, 4) == -1 )
      {
        Error = WSAGetLastError();
        v4 = Error;
        if ( Error > 0 )
          v4 = (unsigned __int16)Error | 0x80070000;
      }
    }
    CReaderWriterLock3::ReadUnlock((FTP_DATA_CHANNEL *)((char *)this + 1120));
    if ( v4 >= 0 )
    {
      v7 = *(_QWORD *)(*((_QWORD *)this + 9) + 1080LL);
      v8 = 16;
      if ( *(_WORD *)(v7 + 320) != 2 )
        v8 = 28;
      memcpy_0(&v19, (const void *)(v7 + 320), v8);
      v9 = ntohs(*(_WORD *)(v7 + 322));
      *(_WORD *)v19.sa_data = htons(v9 - 1);
      v4 = FTP_ASYNC_SOCKET::Bind((FTP_DATA_CHANNEL *)((char *)this + 544), &v19);
      if ( v4 >= 0 )
      {
        v10 = *(_QWORD *)(*((_QWORD *)this + 9) + 96LL);
        v11 = (CReaderWriterLock3 *)(v10 + 208);
        CReaderWriterLock3::ReadLock((CReaderWriterLock3 *)(v10 + 208));
        v12 = (unsigned int)_InterlockedIncrement(*(volatile signed __int32 **)(v10 + 192));
        if ( FTP_SITE_CONFIG::sm_pRefTraceLog )
          WriteRefTraceLog(FTP_SITE_CONFIG::sm_pRefTraceLog, v12);
        v13 = *(_QWORD *)(v10 + 192);
        CReaderWriterLock3::ReadUnlock(v11);
        v14 = (unsigned int)(1000 * *(_DWORD *)(v13 + 152));
        v15 = _InterlockedDecrement((volatile signed __int32 *)v13);
        if ( FTP_SITE_CONFIG::sm_pRefTraceLog )
          WriteRefTraceLog(FTP_SITE_CONFIG::sm_pRefTraceLog, v15);
        if ( !v15 )
        {
          FTP_SITE_CONFIG::~FTP_SITE_CONFIG((FTP_SITE_CONFIG *)v13);
          ALLOC_CACHE_HANDLER::Free((ALLOC_CACHE_HANDLER *)FTP_SITE_CONFIG::sm_pAllocHandler, (void *)v13);
        }
        *((_DWORD *)this + 554) = 1;
        v16 = (FTP_TIMEOUT_MONITOR *)(*(__int64 (__fastcall **)(FTP_SERVERP *))(*(_QWORD *)g_pFtpServer + 88LL))(g_pFtpServer);
        FTP_TIMEOUT_MONITOR::AddEntryToMonitorList(v16, this, v14);
        CSpinLock::WriteLock((FTP_DATA_CHANNEL *)((char *)this + 2144));
        (***((void (__fastcall ****)(_QWORD))this + 9))(*((_QWORD *)this + 9));
        *((_DWORD *)this + 15) = 1;
        if ( *((_DWORD *)this + 538) )
        {
          v4 = -2147023673;
        }
        else
        {
          v4 = FTP_ASYNC_SOCKET::Connect(
                 (FTP_DATA_CHANNEL *)((char *)this + 544),
                 a2,
                 (FTP_DATA_CHANNEL *)((char *)this + 288));
          if ( v4 >= 0 )
            goto LABEL_23;
        }
        *((_DWORD *)this + 15) = 0;
LABEL_23:
        _InterlockedExchange(
          (volatile __int32 *)this + 536,
          ((*((_BYTE *)this + 2144) - 1) & 3) != 0 ? *((_DWORD *)this + 536) - 1 : 0);
        if ( v4 < 0 )
        {
          FTP_DATA_CHANNEL::StopConnectionIdleMonitor(this);
          (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 9) + 8LL))(*((_QWORD *)this + 9));
        }
      }
    }
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18003f6b0  mov     [rsp+arg_10], rbx
0x18003f6b5  push    rbp
0x18003f6b6  push    rsi
0x18003f6b7  push    rdi
0x18003f6b8  push    r12
0x18003f6ba  push    r13
0x18003f6bc  push    r14
0x18003f6be  push    r15
0x18003f6c0  sub     rsp, 0D0h
0x18003f6c7  mov     rax, cs:__security_cookie
0x18003f6ce  xor     rax, rsp
0x18003f6d1  mov     [rsp+108h+var_48], rax
0x18003f6d9  mov     r14, rdx
0x18003f6dc  mov     rdi, rcx
0x18003f6df  mov     r12d, 1
0x18003f6e5  mov     dword ptr [rsp+108h+optval], r12d
0x18003f6ea  xor     edx, edx; Val
0x18003f6ec  lea     r8d, [r12+7Fh]; Size
0x18003f6f1  lea     rcx, [rsp+108h+var_C8]; void *
0x18003f6f6  call    memset_0
0x18003f6fb  lea     r15, [rdi+120h]
0x18003f702  mov     [r15+40h], r12d
0x18003f706  xor     r13d, r13d
0x18003f709  mov     [rdi+960h], r13
0x18003f710  mov     rcx, [rdi+988h]
0x18003f717  mov     [rcx], r13w
0x18003f71b  mov     [rdi+998h], r13d
0x18003f722  mov     [rdi+864h], r13d
0x18003f729  movzx   edx, word ptr [rdi+95Ch]
0x18003f730  test    dx, dx
0x18003f733  jz      short loc_18003F753
0x18003f735  mov     rcx, cs:?g_pFtpServer@@3PEAVFTP_SERVER@@EA; FTP_SERVER * g_pFtpServer
0x18003f73c  mov     rax, [rcx]
0x18003f73f  mov     rax, [rax+90h]
0x18003f746  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f74b  mov     [rdi+95Ch], r13w
0x18003f753  lea     rbp, [rdi+220h]
0x18003f75a  movzx   edx, word ptr [r14]; af
0x18003f75e  mov     rcx, rbp; this
0x18003f761  call    ?Initialize@FTP_ASYNC_SOCKET@@QEAAJK@Z; FTP_ASYNC_SOCKET::Initialize(ulong)
0x18003f766  mov     ebx, eax
0x18003f768  test    eax, eax
0x18003f76a  js      loc_18003F980
0x18003f770  lea     rsi, [rdi+460h]
0x18003f777  mov     rcx, rsi
0x18003f77a  call    cs:__imp_?ReadLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::ReadLock(void)
0x18003f780  mov     rcx, [rdi+230h]; s
0x18003f787  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18003f78b  jnz     short loc_18003F794
0x18003f78d  mov     ebx, 800704D4h
0x18003f792  jmp     short loc_18003F7CC
0x18003f794  mov     ebx, r13d
0x18003f797  mov     r8d, 4; optname
0x18003f79d  mov     [rsp+108h+optlen], r8d; optlen
0x18003f7a2  lea     r9, [rsp+108h+optval]; optval
0x18003f7a7  mov     edx, 0FFFFh; level
0x18003f7ac  call    cs:__imp_setsockopt
0x18003f7b2  cmp     eax, 0FFFFFFFFh
0x18003f7b5  jnz     short loc_18003F7CC
0x18003f7b7  call    cs:__imp_WSAGetLastError
0x18003f7bd  mov     ebx, eax
0x18003f7bf  test    eax, eax
0x18003f7c1  jle     short loc_18003F7CC
0x18003f7c3  movzx   ebx, ax
0x18003f7c6  or      ebx, 80070000h
0x18003f7cc  mov     rcx, rsi
0x18003f7cf  call    cs:__imp_?ReadUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::ReadUnlock(void)
0x18003f7d5  test    ebx, ebx
0x18003f7d7  js      loc_18003F980
0x18003f7dd  mov     rax, [rdi+48h]
0x18003f7e1  mov     rbx, [rax+438h]
0x18003f7e8  mov     eax, 1Ch
0x18003f7ed  lea     r8d, [rax-0Ch]
0x18003f7f1  cmp     word ptr [rbx+140h], 2
0x18003f7f9  cmovnz  r8d, eax; Size
0x18003f7fd  lea     rdx, [rbx+140h]; Src
0x18003f804  lea     rcx, [rsp+108h+var_C8]; void *
0x18003f809  call    memcpy_0
0x18003f80e  movzx   ecx, word ptr [rbx+142h]; netshort
0x18003f815  call    cs:__imp_ntohs
0x18003f81b  sub     ax, r12w
0x18003f81f  movzx   ecx, ax; hostshort
0x18003f822  call    cs:__imp_htons
0x18003f828  mov     word ptr [rsp+108h+var_C8.sa_data], ax
0x18003f82d  lea     rdx, [rsp+108h+var_C8]; struct sockaddr *
0x18003f832  mov     rcx, rbp; this
0x18003f835  call    ?Bind@FTP_ASYNC_SOCKET@@QEAAJPEAUsockaddr@@@Z; FTP_ASYNC_SOCKET::Bind(sockaddr *)
0x18003f83a  mov     ebx, eax
0x18003f83c  test    eax, eax
0x18003f83e  js      loc_18003F980
0x18003f844  mov     rax, [rdi+48h]
0x18003f848  mov     rbx, [rax+60h]
0x18003f84c  lea     rsi, [rbx+0D0h]
0x18003f853  mov     rcx, rsi
0x18003f856  call    cs:__imp_?ReadLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::ReadLock(void)
0x18003f85c  mov     r8, [rbx+0C0h]
0x18003f863  mov     edx, r12d
0x18003f866  lock xadd [r8], edx
0x18003f86b  add     edx, r12d
0x18003f86e  mov     rcx, cs:?sm_pRefTraceLog@FTP_SITE_CONFIG@@0PEAU_TRACE_LOG@@EA; _TRACE_LOG * FTP_SITE_CONFIG::sm_pRefTraceLog
0x18003f875  test    rcx, rcx
0x18003f878  jz      short loc_18003F880
0x18003f87a  call    cs:__imp_WriteRefTraceLog
0x18003f880  mov     rbx, [rbx+0C0h]
0x18003f887  mov     rcx, rsi
0x18003f88a  call    cs:__imp_?ReadUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::ReadUnlock(void)
0x18003f890  imul    r12d, [rbx+98h], 3E8h
0x18003f89b  or      esi, 0FFFFFFFFh
0x18003f89e  lock xadd [rbx], esi
0x18003f8a2  dec     esi
0x18003f8a4  mov     rcx, cs:?sm_pRefTraceLog@FTP_SITE_CONFIG@@0PEAU_TRACE_LOG@@EA; _TRACE_LOG * FTP_SITE_CONFIG::sm_pRefTraceLog
0x18003f8ab  test    rcx, rcx
0x18003f8ae  jz      short loc_18003F8BB
0x18003f8b0  mov     r8, rbx
0x18003f8b3  mov     edx, esi
0x18003f8b5  call    cs:__imp_WriteRefTraceLog
0x18003f8bb  test    esi, esi
0x18003f8bd  jnz     short loc_18003F8D9
0x18003f8bf  mov     rcx, rbx; this
0x18003f8c2  call    ??1FTP_SITE_CONFIG@@QEAA@XZ; FTP_SITE_CONFIG::~FTP_SITE_CONFIG(void)
0x18003f8c7  nop
0x18003f8c8  mov     rdx, rbx
0x18003f8cb  mov     rcx, cs:?sm_pAllocHandler@FTP_SITE_CONFIG@@0PEAVALLOC_CACHE_HANDLER@@EA; ALLOC_CACHE_HANDLER * FTP_SITE_CONFIG::sm_pAllocHandler
0x18003f8d2  call    cs:__imp_?Free@ALLOC_CACHE_HANDLER@@QEAAHPEAX@Z; ALLOC_CACHE_HANDLER::Free(void *)
0x18003f8d8  nop
0x18003f8d9  mov     ebx, 1
0x18003f8de  mov     [rdi+8A8h], ebx
0x18003f8e4  mov     rcx, cs:?g_pFtpServer@@3PEAVFTP_SERVER@@EA; FTP_SERVER * g_pFtpServer
0x18003f8eb  mov     rax, [rcx]
0x18003f8ee  mov     rax, [rax+58h]
0x18003f8f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f8f7  mov     r8, r12; unsigned __int64
0x18003f8fa  mov     rdx, rdi; struct FTP_TIMEOUT_MONITOR_ENTRY *
0x18003f8fd  mov     rcx, rax; this
0x18003f900  call    ?AddEntryToMonitorList@FTP_TIMEOUT_MONITOR@@QEAAXPEAVFTP_TIMEOUT_MONITOR_ENTRY@@_K@Z; FTP_TIMEOUT_MONITOR::AddEntryToMonitorList(FTP_TIMEOUT_MONITOR_ENTRY *,unsigned __int64)
0x18003f905  lea     rcx, [rdi+860h]
0x18003f90c  call    cs:__imp_?WriteLock@CSpinLock@@QEAAXXZ; CSpinLock::WriteLock(void)
0x18003f912  mov     rcx, [rdi+48h]
0x18003f916  mov     rax, [rcx]
0x18003f919  mov     rax, [rax]
0x18003f91c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f921  mov     [rdi+3Ch], ebx
0x18003f924  cmp     [rdi+868h], r13d
0x18003f92b  jz      short loc_18003F934
0x18003f92d  mov     ebx, 800704C7h
0x18003f932  jmp     short loc_18003F948
0x18003f934  mov     r8, r15; struct FTP_ASYNC_CONTEXT *
0x18003f937  mov     rdx, r14; struct sockaddr *
0x18003f93a  mov     rcx, rbp; this
0x18003f93d  call    ?Connect@FTP_ASYNC_SOCKET@@QEAAJPEBUsockaddr@@PEAVFTP_ASYNC_CONTEXT@@@Z; FTP_ASYNC_SOCKET::Connect(sockaddr const *,FTP_ASYNC_CONTEXT *)
0x18003f942  mov     ebx, eax
0x18003f944  test    eax, eax
0x18003f946  jns     short loc_18003F94C
0x18003f948  mov     [rdi+3Ch], r13d
0x18003f94c  mov     edx, [rdi+860h]
0x18003f952  dec     edx
0x18003f954  mov     eax, edx
0x18003f956  and     al, 3
0x18003f958  neg     al
0x18003f95a  sbb     ecx, ecx
0x18003f95c  and     ecx, edx
0x18003f95e  xchg    ecx, [rdi+860h]
0x18003f964  test    ebx, ebx
0x18003f966  jns     short loc_18003F980
0x18003f968  mov     rcx, rdi; this
0x18003f96b  call    ?StopConnectionIdleMonitor@FTP_DATA_CHANNEL@@AEAAXXZ; FTP_DATA_CHANNEL::StopConnectionIdleMonitor(void)
0x18003f970  mov     rcx, [rdi+48h]
0x18003f974  mov     rax, [rcx]
0x18003f977  mov     rax, [rax+8]
0x18003f97b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f980  mov     eax, ebx
0x18003f982  mov     rcx, [rsp+108h+var_48]
0x18003f98a  xor     rcx, rsp; StackCookie
0x18003f98d  call    __security_check_cookie
0x18003f992  mov     rbx, [rsp+108h+arg_10]
0x18003f99a  add     rsp, 0D0h
0x18003f9a1  pop     r15
0x18003f9a3  pop     r14
0x18003f9a5  pop     r13
0x18003f9a7  pop     r12
0x18003f9a9  pop     rdi
0x18003f9aa  pop     rsi
0x18003f9ab  pop     rbp
0x18003f9ac  retn
```
