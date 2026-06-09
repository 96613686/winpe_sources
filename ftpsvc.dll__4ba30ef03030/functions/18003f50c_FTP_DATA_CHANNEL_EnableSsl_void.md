# FTP_DATA_CHANNEL::EnableSsl(void)

- ea: `0x18003f50c`
- end: `0x18003f6a9`
- name: `?EnableSsl@FTP_DATA_CHANNEL@@QEAAJXZ`
- size: `413`
- prototype: `__int64 __fastcall(struct _SecHandle *this)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180033f90`
- `0x18003b12c`

## callees

- `0x180009090`
- `0x18002f78c`
- `0x18003f50c`

## import_xrefs

- `Secur32!DeleteSecurityContext` at `0x18003f60e`
- `Secur32!DeleteSecurityContext` at `0x18003f60e`
- `iisutil!?ReadLock@CReaderWriterLock3@@QEAAXXZ` at `0x18003f52a`
- `iisutil!?ReadLock@CReaderWriterLock3@@QEAAXXZ` at `0x18003f52a`
- `iisutil!?Free@ALLOC_CACHE_HANDLER@@QEAAHPEAX@Z` at `0x18003f697`
- `iisutil!?Free@ALLOC_CACHE_HANDLER@@QEAAHPEAX@Z` at `0x18003f697`
- `iisutil!?ReadUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x18003f561`
- `iisutil!?ReadUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x18003f561`
- `iisutil!WriteRefTraceLog` at `0x18003f551`
- `iisutil!WriteRefTraceLog` at `0x18003f675`
- `iisutil!WriteRefTraceLog` at `0x18003f551`
- `iisutil!WriteRefTraceLog` at `0x18003f675`
- `CRYPT32!CertFreeCertificateContext` at `0x18003f626`
- `CRYPT32!CertFreeCertificateContext` at `0x18003f626`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall FTP_DATA_CHANNEL::EnableSsl(struct _SecHandle *this)
{
  __int64 v2; // rdi
  CReaderWriterLock3 *v3; // rsi
  __int64 v4; // rdx
  __int64 v5; // rdi
  int v6; // ecx
  ULONG_PTR dwUpper; // rdx
  int v8; // esi
  const CERT_CONTEXT *dwLower; // rcx
  unsigned __int32 v10; // ebx
  _DWORD v12[2]; // [rsp+50h] [rbp-48h] BYREF
  __int64 v13; // [rsp+58h] [rbp-40h]
  int v14; // [rsp+60h] [rbp-38h]
  int v15; // [rsp+64h] [rbp-34h]

  v2 = *(_QWORD *)(this[4].dwUpper + 96);
  v3 = (CReaderWriterLock3 *)(v2 + 208);
  CReaderWriterLock3::ReadLock((CReaderWriterLock3 *)(v2 + 208));
  v4 = (unsigned int)_InterlockedIncrement(*(volatile signed __int32 **)(v2 + 192));
  if ( FTP_SITE_CONFIG::sm_pRefTraceLog )
    WriteRefTraceLog(FTP_SITE_CONFIG::sm_pRefTraceLog, v4);
  v5 = *(_QWORD *)(v2 + 192);
  CReaderWriterLock3::ReadUnlock(v3);
  if ( !HIDWORD(this[3].dwLower) )
  {
    v12[1] = 0;
    v15 = 0;
    v6 = *(_DWORD *)(v5 + 1064);
    v12[0] = v6 == 2;
    v14 = *(_DWORD *)(v5 + 120);
    dwUpper = this[4].dwUpper;
    v13 = *(_QWORD *)(dwUpper + 1168);
    v8 = ((__int64 (__fastcall *)(struct _SecHandle *, ULONG_PTR, _QWORD, _QWORD, bool, _DWORD, _DWORD, _DWORD, _DWORD, _DWORD *))SSL_STREAM_CONTEXT::Initialize)(
           &this[7],
           dwUpper + 368,
           *(_QWORD *)(v5 + 96),
           *(_QWORD *)(v5 + 104),
           v6 != 0,
           *(_DWORD *)(v5 + 1068),
           *(_DWORD *)(v5 + 1072),
           *(_DWORD *)(v5 + 1076),
           *(_DWORD *)(v5 + 1080),
           v12);
    if ( v8 < 0 )
      goto LABEL_11;
    if ( LODWORD(this[9].dwLower) )
    {
      DeleteSecurityContext(this + 8);
      LODWORD(this[9].dwLower) = 0;
    }
    dwLower = (const CERT_CONTEXT *)this[12].dwLower;
    if ( dwLower )
    {
      CertFreeCertificateContext(dwLower);
      this[12].dwLower = 0;
    }
    this[11].dwLower = 0;
    this[11].dwUpper = 0;
    this[10].dwLower = 0;
    this[10].dwUpper = 0;
    HIDWORD(this[7].dwUpper) = 0;
    HIDWORD(this[3].dwLower) = 1;
  }
  v8 = 0;
LABEL_11:
  v10 = _InterlockedDecrement((volatile signed __int32 *)v5);
  if ( FTP_SITE_CONFIG::sm_pRefTraceLog )
    WriteRefTraceLog(FTP_SITE_CONFIG::sm_pRefTraceLog, v10);
  if ( !v10 && v5 )
  {
    FTP_SITE_CONFIG::~FTP_SITE_CONFIG((FTP_SITE_CONFIG *)v5);
    ALLOC_CACHE_HANDLER::Free((ALLOC_CACHE_HANDLER *)FTP_SITE_CONFIG::sm_pAllocHandler, (void *)v5);
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18003f50c  push    rbx
0x18003f50e  push    rbp
0x18003f50f  push    rsi
0x18003f510  push    rdi
0x18003f511  sub     rsp, 78h
0x18003f515  mov     rbx, rcx
0x18003f518  mov     rax, [rcx+48h]
0x18003f51c  mov     rdi, [rax+60h]
0x18003f520  lea     rsi, [rdi+0D0h]
0x18003f527  mov     rcx, rsi
0x18003f52a  call    cs:__imp_?ReadLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::ReadLock(void)
0x18003f530  mov     r8, [rdi+0C0h]
0x18003f537  mov     edx, 1
0x18003f53c  lock xadd [r8], edx
0x18003f541  inc     edx
0x18003f543  mov     rcx, cs:?sm_pRefTraceLog@FTP_SITE_CONFIG@@0PEAU_TRACE_LOG@@EA; _TRACE_LOG * FTP_SITE_CONFIG::sm_pRefTraceLog
0x18003f54a  xor     ebp, ebp
0x18003f54c  test    rcx, rcx
0x18003f54f  jz      short loc_18003F557
0x18003f551  call    cs:__imp_WriteRefTraceLog
0x18003f557  mov     rdi, [rdi+0C0h]
0x18003f55e  mov     rcx, rsi
0x18003f561  call    cs:__imp_?ReadUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::ReadUnlock(void)
0x18003f567  cmp     [rbx+34h], ebp
0x18003f56a  jnz     loc_18003F659
0x18003f570  mov     [rsp+98h+var_44], ebp
0x18003f574  mov     [rsp+98h+var_34], ebp
0x18003f578  mov     ecx, [rdi+428h]
0x18003f57e  mov     eax, ebp
0x18003f580  cmp     ecx, 2
0x18003f583  setz    al
0x18003f586  mov     [rsp+98h+var_48], eax
0x18003f58a  mov     eax, [rdi+78h]
0x18003f58d  mov     [rsp+98h+var_38], eax
0x18003f591  mov     rdx, [rbx+48h]
0x18003f595  mov     rax, [rdx+490h]
0x18003f59c  mov     [rsp+98h+var_40], rax
0x18003f5a1  mov     r8d, ebp
0x18003f5a4  test    ecx, ecx
0x18003f5a6  setnz   r8b
0x18003f5aa  add     rdx, 170h
0x18003f5b1  lea     rcx, [rbx+70h]
0x18003f5b5  lea     rax, [rsp+98h+var_48]
0x18003f5ba  mov     [rsp+98h+var_50], rax
0x18003f5bf  mov     eax, [rdi+438h]
0x18003f5c5  mov     [rsp+98h+var_58], eax
0x18003f5c9  mov     eax, [rdi+434h]
0x18003f5cf  mov     [rsp+98h+var_60], eax
0x18003f5d3  mov     eax, [rdi+430h]
0x18003f5d9  mov     [rsp+98h+var_68], eax
0x18003f5dd  mov     eax, [rdi+42Ch]
0x18003f5e3  mov     [rsp+98h+var_70], eax
0x18003f5e7  mov     [rsp+98h+var_78], r8d
0x18003f5ec  mov     r9, [rdi+68h]
0x18003f5f0  mov     r8, [rdi+60h]
0x18003f5f4  call    ?Initialize@SSL_STREAM_CONTEXT@@QEAAJPEBU_GUID@@PEBG1HHW4SslClientCertificateValidationFlags@@KKPEAUSSL_FORCE_POLICY@@@Z; SSL_STREAM_CONTEXT::Initialize(_GUID const *,ushort const *,ushort const *,int,int,SslClientCertificateValidationFlags,ulong,ulong,SSL_FORCE_POLICY *)
0x18003f5f9  mov     esi, eax
0x18003f5fb  test    eax, eax
0x18003f5fd  js      short loc_18003F65B
0x18003f5ff  cmp     [rbx+90h], ebp
0x18003f605  jz      short loc_18003F61A
0x18003f607  lea     rcx, [rbx+80h]; phContext
0x18003f60e  call    cs:__imp_DeleteSecurityContext
0x18003f614  mov     [rbx+90h], ebp
0x18003f61a  mov     rcx, [rbx+0C0h]; pCertContext
0x18003f621  test    rcx, rcx
0x18003f624  jz      short loc_18003F633
0x18003f626  call    cs:__imp_CertFreeCertificateContext
0x18003f62c  mov     [rbx+0C0h], rbp
0x18003f633  mov     [rbx+0B0h], rbp
0x18003f63a  mov     [rbx+0B8h], rbp
0x18003f641  mov     [rbx+0A0h], rbp
0x18003f648  mov     [rbx+0A8h], rbp
0x18003f64f  mov     [rbx+7Ch], ebp
0x18003f652  mov     dword ptr [rbx+34h], 1
0x18003f659  mov     esi, ebp
0x18003f65b  or      ebx, 0FFFFFFFFh
0x18003f65e  lock xadd [rdi], ebx
0x18003f662  dec     ebx
0x18003f664  mov     rcx, cs:?sm_pRefTraceLog@FTP_SITE_CONFIG@@0PEAU_TRACE_LOG@@EA; _TRACE_LOG * FTP_SITE_CONFIG::sm_pRefTraceLog
0x18003f66b  test    rcx, rcx
0x18003f66e  jz      short loc_18003F67B
0x18003f670  mov     r8, rdi
0x18003f673  mov     edx, ebx
0x18003f675  call    cs:__imp_WriteRefTraceLog
0x18003f67b  test    ebx, ebx
0x18003f67d  jnz     short loc_18003F69E
0x18003f67f  test    rdi, rdi
0x18003f682  jz      short loc_18003F69E
0x18003f684  mov     rcx, rdi; this
0x18003f687  call    ??1FTP_SITE_CONFIG@@QEAA@XZ; FTP_SITE_CONFIG::~FTP_SITE_CONFIG(void)
0x18003f68c  nop
0x18003f68d  mov     rdx, rdi
0x18003f690  mov     rcx, cs:?sm_pAllocHandler@FTP_SITE_CONFIG@@0PEAVALLOC_CACHE_HANDLER@@EA; ALLOC_CACHE_HANDLER * FTP_SITE_CONFIG::sm_pAllocHandler
0x18003f697  call    cs:__imp_?Free@ALLOC_CACHE_HANDLER@@QEAAHPEAX@Z; ALLOC_CACHE_HANDLER::Free(void *)
0x18003f69d  nop
0x18003f69e  mov     eax, esi
0x18003f6a0  add     rsp, 78h
0x18003f6a4  pop     rdi
0x18003f6a5  pop     rsi
0x18003f6a6  pop     rbp
0x18003f6a7  pop     rbx
0x18003f6a8  retn
```
