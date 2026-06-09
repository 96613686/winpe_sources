# FTP_CONTROL_CHANNEL::EnableSslSession(int)

- ea: `0x180041544`
- end: `0x1800416c4`
- name: `?EnableSslSession@FTP_CONTROL_CHANNEL@@QEAAJH@Z`
- size: `384`
- prototype: `__int64 __fastcall(FTP_CONTROL_CHANNEL *__hidden this, int)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180033f90`
- `0x180038b28`

## callees

- `0x180009090`
- `0x18002f78c`
- `0x180041544`

## import_xrefs

- `Secur32!DeleteSecurityContext` at `0x18004162d`
- `Secur32!DeleteSecurityContext` at `0x18004162d`
- `iisutil!?ReadLock@CReaderWriterLock3@@QEAAXXZ` at `0x180041566`
- `iisutil!?ReadLock@CReaderWriterLock3@@QEAAXXZ` at `0x180041566`
- `iisutil!?Free@ALLOC_CACHE_HANDLER@@QEAAHPEAX@Z` at `0x1800416b0`
- `iisutil!?Free@ALLOC_CACHE_HANDLER@@QEAAHPEAX@Z` at `0x1800416b0`
- `iisutil!?WriteLock@CSpinLock@@QEAAXXZ` at `0x1800415ab`
- `iisutil!?WriteLock@CSpinLock@@QEAAXXZ` at `0x1800415ab`
- `iisutil!?ReadUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x18004159e`
- `iisutil!?ReadUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x18004159e`
- `iisutil!WriteRefTraceLog` at `0x18004158e`
- `iisutil!WriteRefTraceLog` at `0x180041693`
- `iisutil!WriteRefTraceLog` at `0x18004158e`
- `iisutil!WriteRefTraceLog` at `0x180041693`
- `CRYPT32!CertFreeCertificateContext` at `0x180041640`
- `CRYPT32!CertFreeCertificateContext` at `0x180041640`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall FTP_CONTROL_CHANNEL::EnableSslSession(FTP_CONTROL_CHANNEL *this, int a2)
{
  __int64 v4; // rdi
  CReaderWriterLock3 *v5; // rsi
  __int64 v6; // rdx
  __int64 v7; // rdi
  int v8; // esi
  const CERT_CONTEXT *v9; // rcx
  unsigned __int32 v10; // ebx

  v4 = *(_QWORD *)(*((_QWORD *)this + 1) + 96LL);
  v5 = (CReaderWriterLock3 *)(v4 + 208);
  CReaderWriterLock3::ReadLock((CReaderWriterLock3 *)(v4 + 208));
  v6 = (unsigned int)_InterlockedIncrement(*(volatile signed __int32 **)(v4 + 192));
  if ( FTP_SITE_CONFIG::sm_pRefTraceLog )
    WriteRefTraceLog(FTP_SITE_CONFIG::sm_pRefTraceLog, v6);
  v7 = *(_QWORD *)(v4 + 192);
  CReaderWriterLock3::ReadUnlock(v5);
  CSpinLock::WriteLock((FTP_CONTROL_CHANNEL *)((char *)this + 804));
  v8 = SSL_STREAM_CONTEXT::Initialize(
         (char *)this + 24,
         *((_QWORD *)this + 1) + 368LL,
         *(_QWORD *)(v7 + 96),
         *(_QWORD *)(v7 + 104),
         *(_DWORD *)(v7 + 1064) != 0,
         *(_DWORD *)(v7 + 1068),
         *(_DWORD *)(v7 + 1072),
         *(_DWORD *)(v7 + 1076),
         *(_DWORD *)(v7 + 1080),
         0);
  if ( v8 >= 0 )
  {
    if ( a2 )
    {
      *((_DWORD *)this + 50) = 1;
    }
    else
    {
      if ( *((_DWORD *)this + 14) )
      {
        DeleteSecurityContext((PCtxtHandle)((char *)this + 40));
        *((_DWORD *)this + 14) = 0;
      }
      v9 = (const CERT_CONTEXT *)*((_QWORD *)this + 13);
      if ( v9 )
      {
        CertFreeCertificateContext(v9);
        *((_QWORD *)this + 13) = 0;
      }
      *((_QWORD *)this + 11) = 0;
      *((_QWORD *)this + 12) = 0;
      *((_QWORD *)this + 9) = 0;
      *((_QWORD *)this + 10) = 0;
      *((_DWORD *)this + 9) = 0;
    }
    v8 = 0;
  }
  _InterlockedExchange(
    (volatile __int32 *)this + 201,
    ((*((_BYTE *)this + 804) - 1) & 3) != 0 ? *((_DWORD *)this + 201) - 1 : 0);
  v10 = _InterlockedDecrement((volatile signed __int32 *)v7);
  if ( FTP_SITE_CONFIG::sm_pRefTraceLog )
    WriteRefTraceLog(FTP_SITE_CONFIG::sm_pRefTraceLog, v10);
  if ( !v10 )
  {
    FTP_SITE_CONFIG::~FTP_SITE_CONFIG((FTP_SITE_CONFIG *)v7);
    ALLOC_CACHE_HANDLER::Free((ALLOC_CACHE_HANDLER *)FTP_SITE_CONFIG::sm_pAllocHandler, (void *)v7);
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180041544  push    rbx
0x180041546  push    rbp
0x180041547  push    rsi
0x180041548  push    rdi
0x180041549  push    r14
0x18004154b  sub     rsp, 50h
0x18004154f  mov     ebp, edx
0x180041551  mov     rbx, rcx
0x180041554  mov     rax, [rcx+8]
0x180041558  mov     rdi, [rax+60h]
0x18004155c  lea     rsi, [rdi+0D0h]
0x180041563  mov     rcx, rsi
0x180041566  call    cs:__imp_?ReadLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::ReadLock(void)
0x18004156c  mov     r8, [rdi+0C0h]
0x180041573  mov     edx, 1
0x180041578  lock xadd [r8], edx
0x18004157d  inc     edx
0x18004157f  mov     rcx, cs:?sm_pRefTraceLog@FTP_SITE_CONFIG@@0PEAU_TRACE_LOG@@EA; _TRACE_LOG * FTP_SITE_CONFIG::sm_pRefTraceLog
0x180041586  xor     r14d, r14d
0x180041589  test    rcx, rcx
0x18004158c  jz      short loc_180041594
0x18004158e  call    cs:__imp_WriteRefTraceLog
0x180041594  mov     rdi, [rdi+0C0h]
0x18004159b  mov     rcx, rsi
0x18004159e  call    cs:__imp_?ReadUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::ReadUnlock(void)
0x1800415a4  lea     rcx, [rbx+324h]
0x1800415ab  call    cs:__imp_?WriteLock@CSpinLock@@QEAAXXZ; CSpinLock::WriteLock(void)
0x1800415b1  mov     r8d, r14d
0x1800415b4  cmp     [rdi+428h], r14d
0x1800415bb  setnz   r8b
0x1800415bf  mov     rdx, [rbx+8]
0x1800415c3  add     rdx, 170h
0x1800415ca  lea     rcx, [rbx+18h]
0x1800415ce  mov     [rsp+78h+var_30], r14
0x1800415d3  mov     eax, [rdi+438h]
0x1800415d9  mov     [rsp+78h+var_38], eax
0x1800415dd  mov     eax, [rdi+434h]
0x1800415e3  mov     [rsp+78h+var_40], eax
0x1800415e7  mov     eax, [rdi+430h]
0x1800415ed  mov     [rsp+78h+var_48], eax
0x1800415f1  mov     eax, [rdi+42Ch]
0x1800415f7  mov     [rsp+78h+var_50], eax
0x1800415fb  mov     [rsp+78h+var_58], r8d
0x180041600  mov     r9, [rdi+68h]
0x180041604  mov     r8, [rdi+60h]
0x180041608  call    ?Initialize@SSL_STREAM_CONTEXT@@QEAAJPEBU_GUID@@PEBG1HHW4SslClientCertificateValidationFlags@@KKPEAUSSL_FORCE_POLICY@@@Z; SSL_STREAM_CONTEXT::Initialize(_GUID const *,ushort const *,ushort const *,int,int,SslClientCertificateValidationFlags,ulong,ulong,SSL_FORCE_POLICY *)
0x18004160d  mov     esi, eax
0x18004160f  test    eax, eax
0x180041611  js      short loc_180041661
0x180041613  test    ebp, ebp
0x180041615  jz      short loc_180041623
0x180041617  mov     dword ptr [rbx+0C8h], 1
0x180041621  jmp     short loc_18004165E
0x180041623  cmp     [rbx+38h], r14d
0x180041627  jz      short loc_180041637
0x180041629  lea     rcx, [rbx+28h]; phContext
0x18004162d  call    cs:__imp_DeleteSecurityContext
0x180041633  mov     [rbx+38h], r14d
0x180041637  mov     rcx, [rbx+68h]; pCertContext
0x18004163b  test    rcx, rcx
0x18004163e  jz      short loc_18004164A
0x180041640  call    cs:__imp_CertFreeCertificateContext
0x180041646  mov     [rbx+68h], r14
0x18004164a  mov     [rbx+58h], r14
0x18004164e  mov     [rbx+60h], r14
0x180041652  mov     [rbx+48h], r14
0x180041656  mov     [rbx+50h], r14
0x18004165a  mov     [rbx+24h], r14d
0x18004165e  mov     esi, r14d
0x180041661  mov     edx, [rbx+324h]
0x180041667  dec     edx
0x180041669  mov     eax, edx
0x18004166b  and     al, 3
0x18004166d  neg     al
0x18004166f  sbb     ecx, ecx
0x180041671  and     ecx, edx
0x180041673  xchg    ecx, [rbx+324h]
0x180041679  or      ebx, 0FFFFFFFFh
0x18004167c  lock xadd [rdi], ebx
0x180041680  dec     ebx
0x180041682  mov     rcx, cs:?sm_pRefTraceLog@FTP_SITE_CONFIG@@0PEAU_TRACE_LOG@@EA; _TRACE_LOG * FTP_SITE_CONFIG::sm_pRefTraceLog
0x180041689  test    rcx, rcx
0x18004168c  jz      short loc_180041699
0x18004168e  mov     r8, rdi
0x180041691  mov     edx, ebx
0x180041693  call    cs:__imp_WriteRefTraceLog
0x180041699  test    ebx, ebx
0x18004169b  jnz     short loc_1800416B7
0x18004169d  mov     rcx, rdi; this
0x1800416a0  call    ??1FTP_SITE_CONFIG@@QEAA@XZ; FTP_SITE_CONFIG::~FTP_SITE_CONFIG(void)
0x1800416a5  nop
0x1800416a6  mov     rdx, rdi
0x1800416a9  mov     rcx, cs:?sm_pAllocHandler@FTP_SITE_CONFIG@@0PEAVALLOC_CACHE_HANDLER@@EA; ALLOC_CACHE_HANDLER * FTP_SITE_CONFIG::sm_pAllocHandler
0x1800416b0  call    cs:__imp_?Free@ALLOC_CACHE_HANDLER@@QEAAHPEAX@Z; ALLOC_CACHE_HANDLER::Free(void *)
0x1800416b6  nop
0x1800416b7  mov     eax, esi
0x1800416b9  add     rsp, 50h
0x1800416bd  pop     r14
0x1800416bf  pop     rdi
0x1800416c0  pop     rsi
0x1800416c1  pop     rbp
0x1800416c2  pop     rbx
0x1800416c3  retn
```
