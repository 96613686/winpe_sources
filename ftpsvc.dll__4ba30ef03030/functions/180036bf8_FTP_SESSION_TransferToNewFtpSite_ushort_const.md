# FTP_SESSION::TransferToNewFtpSite(ushort const *)

- ea: `0x180036bf8`
- end: `0x180036e88`
- name: `?TransferToNewFtpSite@FTP_SESSION@@QEAAJPEBG@Z`
- size: `656`
- prototype: `__int64 __fastcall(FTP_SESSION *__hidden this, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `7`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800392cc`
- `0x18003d220`

## callees

- `0x180001250`
- `0x180008f40`
- `0x180009090`
- `0x180009468`
- `0x18000a630`
- `0x180036bf8`
- `0x180049010`

## import_xrefs

- `iisutil!?ReadLock@CReaderWriterLock3@@QEAAXXZ` at `0x180036d8f`
- `iisutil!?ReadLock@CReaderWriterLock3@@QEAAXXZ` at `0x180036d8f`
- `iisutil!?Free@ALLOC_CACHE_HANDLER@@QEAAHPEAX@Z` at `0x180036e24`
- `iisutil!?Free@ALLOC_CACHE_HANDLER@@QEAAHPEAX@Z` at `0x180036e24`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180036e35`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180036e35`
- `iisutil!?ReadUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x180036dc3`
- `iisutil!?ReadUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x180036dc3`
- `iisutil!WriteRefTraceLog` at `0x180036db3`
- `iisutil!WriteRefTraceLog` at `0x180036e07`
- `iisutil!WriteRefTraceLog` at `0x180036db3`
- `iisutil!WriteRefTraceLog` at `0x180036e07`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall FTP_SESSION::TransferToNewFtpSite(FTP_SESSION *this, const unsigned __int16 *a2)
{
  int v4; // edi
  void *v5; // rcx
  unsigned __int32 v6; // edx
  unsigned __int32 v7; // r8d
  unsigned __int32 v8; // eax
  FTP_SITE_PERF_CTRS *i; // rdx
  unsigned __int32 v10; // eax
  volatile signed __int32 *v11; // rdi
  __int64 v12; // rdi
  CReaderWriterLock3 *v13; // rsi
  __int64 v14; // rdx
  __int64 v15; // rdi
  unsigned __int32 v16; // esi
  FTP_SITE *v17; // rbx
  void *Block; // [rsp+50h] [rbp+8h] BYREF

  Block = 0;
  v4 = (*(__int64 (__fastcall **)(FTP_SERVERP *, __int64, const unsigned __int16 *, void **))(*(_QWORD *)g_pFtpServer
                                                                                            + 8LL))(
         g_pFtpServer,
         *((_QWORD *)this + 135) + 320LL,
         a2,
         &Block);
  if ( v4 >= 0 )
  {
    if ( *((_DWORD *)Block + 1) )
    {
      _InterlockedDecrement((volatile signed __int32 *)(*((_QWORD *)this + 12) + 140LL));
      _InterlockedDecrement((volatile signed __int32 *)FTP_SITE_PERF_CTRS::sm_pPerfCtrsGlobal + 17);
      v5 = Block;
      v6 = _InterlockedIncrement((volatile signed __int32 *)Block + 35);
      v7 = _InterlockedIncrement((volatile signed __int32 *)FTP_SITE_PERF_CTRS::sm_pPerfCtrsGlobal + 17);
      while ( 1 )
      {
        v8 = *((_DWORD *)v5 + 36);
        if ( v8 >= v6 )
          break;
        _InterlockedCompareExchange((volatile signed __int32 *)v5 + 36, v6, v8);
      }
      for ( i = FTP_SITE_PERF_CTRS::sm_pPerfCtrsGlobal;
            ;
            _InterlockedCompareExchange((volatile signed __int32 *)i + 18, v7, v10) )
      {
        v10 = *((_DWORD *)i + 18);
        if ( v10 >= v7 )
          break;
      }
      _InterlockedAdd((volatile signed __int32 *)v5 + 37, 1u);
      FTP_SITE::RemoveFromSessionList(*((FTP_SITE **)this + 12), this);
      v4 = FTP_SITE::AddToSessionList((FTP_SITE *)Block, this);
      if ( v4 >= 0 )
      {
        v11 = (volatile signed __int32 *)*((_QWORD *)this + 12);
        if ( *((_QWORD *)this + 13) )
        {
          if ( _InterlockedExchangeAdd(v11 + 44, 0xFFFFFFFF) == 1 && v11 )
          {
            FTP_SITE::~FTP_SITE((FTP_SITE *)v11);
            operator delete((void *)v11);
          }
        }
        else
        {
          *((_QWORD *)this + 13) = v11;
        }
        *((_QWORD *)this + 12) = Block;
        Block = 0;
        (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 132) + 16LL))(*((_QWORD *)this + 132));
        v12 = *((_QWORD *)this + 12);
        v13 = (CReaderWriterLock3 *)(v12 + 208);
        CReaderWriterLock3::ReadLock((CReaderWriterLock3 *)(v12 + 208));
        v14 = (unsigned int)_InterlockedIncrement(*(volatile signed __int32 **)(v12 + 192));
        if ( FTP_SITE_CONFIG::sm_pRefTraceLog )
          WriteRefTraceLog(FTP_SITE_CONFIG::sm_pRefTraceLog, v14);
        v15 = *(_QWORD *)(v12 + 192);
        CReaderWriterLock3::ReadUnlock(v13);
        *((_DWORD *)this + 1196) = *(_DWORD *)(v15 + 912);
        *((_DWORD *)this + 1406) = *(_DWORD *)(v15 + 156);
        *((_DWORD *)this + 1407) = *(_DWORD *)(v15 + 140);
        v16 = _InterlockedDecrement((volatile signed __int32 *)v15);
        if ( FTP_SITE_CONFIG::sm_pRefTraceLog )
          WriteRefTraceLog(FTP_SITE_CONFIG::sm_pRefTraceLog, v16);
        if ( !v16 )
        {
          FTP_SITE_CONFIG::~FTP_SITE_CONFIG((FTP_SITE_CONFIG *)v15);
          ALLOC_CACHE_HANDLER::Free((ALLOC_CACHE_HANDLER *)FTP_SITE_CONFIG::sm_pAllocHandler, (void *)v15);
        }
        v4 = STRU::Copy((FTP_SESSION *)((char *)this + 872), a2);
        if ( v4 >= 0 )
          v4 = 0;
      }
      else
      {
        *((_DWORD *)this + 1405) = 0;
        (*(void (__fastcall **)(FTP_SESSION *, _QWORD, __int64, const unsigned __int16 *, int))(*(_QWORD *)this + 32LL))(
          this,
          (unsigned int)v4,
          21,
          L"Site is being stopped.",
          1);
      }
    }
    else
    {
      v4 = -2147013895;
    }
  }
  v17 = (FTP_SITE *)Block;
  if ( Block && _InterlockedExchangeAdd((volatile signed __int32 *)Block + 44, 0xFFFFFFFF) == 1 && v17 )
  {
    FTP_SITE::~FTP_SITE(v17);
    operator delete(v17);
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180036bf8  mov     r11, rsp
0x180036bfb  mov     [r11+10h], rbx
0x180036bff  mov     [r11+18h], rbp
0x180036c03  push    rsi
0x180036c04  push    rdi
0x180036c05  push    r12
0x180036c07  sub     rsp, 30h
0x180036c0b  mov     rbp, rdx
0x180036c0e  mov     rbx, rcx
0x180036c11  mov     qword ptr [r11+8], 0
0x180036c19  mov     rcx, cs:?g_pFtpServer@@3PEAVFTP_SERVER@@EA; FTP_SERVER * g_pFtpServer
0x180036c20  mov     rax, [rcx]
0x180036c23  mov     rdx, [rbx+438h]
0x180036c2a  add     rdx, 140h
0x180036c31  lea     r9, [r11+8]
0x180036c35  mov     r8, rbp
0x180036c38  mov     rax, [rax+8]
0x180036c3c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036c41  mov     edi, eax
0x180036c43  test    eax, eax
0x180036c45  js      loc_180036E44
0x180036c4b  mov     rax, [rsp+48h+Block]
0x180036c50  cmp     dword ptr [rax+4], 0
0x180036c54  jnz     short loc_180036C60
0x180036c56  mov     edi, 80072AF9h
0x180036c5b  jmp     loc_180036E44
0x180036c60  mov     rax, [rbx+60h]
0x180036c64  lock dec dword ptr [rax+8Ch]
0x180036c6b  mov     rax, cs:?sm_pPerfCtrsGlobal@FTP_SITE_PERF_CTRS@@0PEAV1@EA; FTP_SITE_PERF_CTRS * FTP_SITE_PERF_CTRS::sm_pPerfCtrsGlobal
0x180036c72  lock dec dword ptr [rax+44h]
0x180036c76  mov     rcx, [rsp+48h+Block]
0x180036c7b  mov     r12d, 1
0x180036c81  mov     edx, r12d
0x180036c84  lock xadd [rcx+8Ch], edx
0x180036c8c  add     edx, r12d
0x180036c8f  mov     rax, cs:?sm_pPerfCtrsGlobal@FTP_SITE_PERF_CTRS@@0PEAV1@EA; FTP_SITE_PERF_CTRS * FTP_SITE_PERF_CTRS::sm_pPerfCtrsGlobal
0x180036c96  mov     r8d, r12d
0x180036c99  lock xadd [rax+44h], r8d
0x180036c9f  add     r8d, r12d
0x180036ca2  jmp     short loc_180036CAC
0x180036ca4  lock cmpxchg [rcx+90h], edx
0x180036cac  mov     eax, [rcx+90h]
0x180036cb2  cmp     eax, edx
0x180036cb4  jb      short loc_180036CA4
0x180036cb6  mov     rdx, cs:?sm_pPerfCtrsGlobal@FTP_SITE_PERF_CTRS@@0PEAV1@EA; FTP_SITE_PERF_CTRS * FTP_SITE_PERF_CTRS::sm_pPerfCtrsGlobal
0x180036cbd  jmp     short loc_180036CC5
0x180036cbf  lock cmpxchg [rdx+48h], r8d
0x180036cc5  mov     eax, [rdx+48h]
0x180036cc8  cmp     eax, r8d
0x180036ccb  jb      short loc_180036CBF
0x180036ccd  lock add [rcx+94h], r12d
0x180036cd5  mov     rdx, rbx; struct FTP_SESSION_PUBLIC *
0x180036cd8  mov     rcx, [rbx+60h]; this
0x180036cdc  call    ?RemoveFromSessionList@FTP_SITE@@QEAAXPEAVFTP_SESSION_PUBLIC@@@Z; FTP_SITE::RemoveFromSessionList(FTP_SESSION_PUBLIC *)
0x180036ce1  mov     rdx, rbx; struct FTP_SESSION_PUBLIC *
0x180036ce4  mov     rcx, [rsp+48h+Block]; this
0x180036ce9  call    ?AddToSessionList@FTP_SITE@@QEAAJPEAVFTP_SESSION_PUBLIC@@@Z; FTP_SITE::AddToSessionList(FTP_SESSION_PUBLIC *)
0x180036cee  mov     edi, eax
0x180036cf0  test    eax, eax
0x180036cf2  jns     short loc_180036D26
0x180036cf4  mov     dword ptr [rbx+15F4h], 0
0x180036cfe  mov     rax, [rbx]
0x180036d01  mov     [rsp+48h+var_28], r12d
0x180036d06  lea     r9, aSiteIsBeingSto; "Site is being stopped."
0x180036d0d  mov     r8d, 15h
0x180036d13  mov     edx, edi
0x180036d15  mov     rcx, rbx
0x180036d18  mov     rax, [rax+20h]
0x180036d1c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036d21  jmp     loc_180036E44
0x180036d26  mov     rdi, [rbx+60h]
0x180036d2a  cmp     qword ptr [rbx+68h], 0
0x180036d2f  jnz     short loc_180036D37
0x180036d31  mov     [rbx+68h], rdi
0x180036d35  jmp     short loc_180036D5C
0x180036d37  or      eax, 0FFFFFFFFh
0x180036d3a  lock xadd [rdi+0B0h], eax
0x180036d42  cmp     eax, r12d
0x180036d45  jnz     short loc_180036D5C
0x180036d47  test    rdi, rdi
0x180036d4a  jz      short loc_180036D5C
0x180036d4c  mov     rcx, rdi; this
0x180036d4f  call    ??1FTP_SITE@@AEAA@XZ; FTP_SITE::~FTP_SITE(void)
0x180036d54  mov     rcx, rdi; Block
0x180036d57  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180036d5c  mov     rdx, [rsp+48h+Block]
0x180036d61  mov     [rbx+60h], rdx
0x180036d65  mov     [rsp+48h+Block], 0
0x180036d6e  mov     rcx, [rbx+420h]
0x180036d75  mov     rax, [rcx]
0x180036d78  mov     rax, [rax+10h]
0x180036d7c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036d81  mov     rdi, [rbx+60h]
0x180036d85  lea     rsi, [rdi+0D0h]
0x180036d8c  mov     rcx, rsi
0x180036d8f  call    cs:__imp_?ReadLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::ReadLock(void)
0x180036d95  mov     r8, [rdi+0C0h]
0x180036d9c  mov     edx, r12d
0x180036d9f  lock xadd [r8], edx
0x180036da4  add     edx, r12d
0x180036da7  mov     rcx, cs:?sm_pRefTraceLog@FTP_SITE_CONFIG@@0PEAU_TRACE_LOG@@EA; _TRACE_LOG * FTP_SITE_CONFIG::sm_pRefTraceLog
0x180036dae  test    rcx, rcx
0x180036db1  jz      short loc_180036DB9
0x180036db3  call    cs:__imp_WriteRefTraceLog
0x180036db9  mov     rdi, [rdi+0C0h]
0x180036dc0  mov     rcx, rsi
0x180036dc3  call    cs:__imp_?ReadUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::ReadUnlock(void)
0x180036dc9  mov     eax, [rdi+390h]
0x180036dcf  mov     [rbx+12B0h], eax
0x180036dd5  mov     eax, [rdi+9Ch]
0x180036ddb  mov     [rbx+15F8h], eax
0x180036de1  mov     eax, [rdi+8Ch]
0x180036de7  mov     [rbx+15FCh], eax
0x180036ded  or      esi, 0FFFFFFFFh
0x180036df0  lock xadd [rdi], esi
0x180036df4  dec     esi
0x180036df6  mov     rcx, cs:?sm_pRefTraceLog@FTP_SITE_CONFIG@@0PEAU_TRACE_LOG@@EA; _TRACE_LOG * FTP_SITE_CONFIG::sm_pRefTraceLog
0x180036dfd  test    rcx, rcx
0x180036e00  jz      short loc_180036E0D
0x180036e02  mov     r8, rdi
0x180036e05  mov     edx, esi
0x180036e07  call    cs:__imp_WriteRefTraceLog
0x180036e0d  test    esi, esi
0x180036e0f  jnz     short loc_180036E2B
0x180036e11  mov     rcx, rdi; this
0x180036e14  call    ??1FTP_SITE_CONFIG@@QEAA@XZ; FTP_SITE_CONFIG::~FTP_SITE_CONFIG(void)
0x180036e19  nop
0x180036e1a  mov     rdx, rdi
0x180036e1d  mov     rcx, cs:?sm_pAllocHandler@FTP_SITE_CONFIG@@0PEAVALLOC_CACHE_HANDLER@@EA; ALLOC_CACHE_HANDLER * FTP_SITE_CONFIG::sm_pAllocHandler
0x180036e24  call    cs:__imp_?Free@ALLOC_CACHE_HANDLER@@QEAAHPEAX@Z; ALLOC_CACHE_HANDLER::Free(void *)
0x180036e2a  nop
0x180036e2b  lea     rcx, [rbx+368h]
0x180036e32  mov     rdx, rbp
0x180036e35  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x180036e3b  mov     edi, eax
0x180036e3d  xor     eax, eax
0x180036e3f  test    edi, edi
0x180036e41  cmovns  edi, eax
0x180036e44  mov     rbx, [rsp+48h+Block]
0x180036e49  test    rbx, rbx
0x180036e4c  jz      short loc_180036E73
0x180036e4e  or      eax, 0FFFFFFFFh
0x180036e51  lock xadd [rbx+0B0h], eax
0x180036e59  cmp     eax, 1
0x180036e5c  jnz     short loc_180036E73
0x180036e5e  test    rbx, rbx
0x180036e61  jz      short loc_180036E73
0x180036e63  mov     rcx, rbx; this
0x180036e66  call    ??1FTP_SITE@@AEAA@XZ; FTP_SITE::~FTP_SITE(void)
0x180036e6b  mov     rcx, rbx; Block
0x180036e6e  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180036e73  mov     eax, edi
0x180036e75  mov     rbx, [rsp+48h+arg_8]
0x180036e7a  mov     rbp, [rsp+48h+arg_10]
0x180036e7f  add     rsp, 30h
0x180036e83  pop     r12
0x180036e85  pop     rdi
0x180036e86  pop     rsi
0x180036e87  retn
```
