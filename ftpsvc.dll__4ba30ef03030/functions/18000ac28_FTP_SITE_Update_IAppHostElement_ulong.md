# FTP_SITE::Update(IAppHostElement *,ulong)

- ea: `0x18000ac28`
- end: `0x18000af59`
- name: `?Update@FTP_SITE@@QEAAJPEAUIAppHostElement@@K@Z`
- size: `817`
- prototype: `__int64 __fastcall(FTP_SITE *__hidden this, struct IAppHostElement *, unsigned int)`
- caller_count: `2`
- callee_count: `11`
- tags: `registry_config, loader_planting, installer_update`

## callers

- `0x18000cb74`
- `0x18000cfe0`

## callees

- `0x180001210`
- `0x180008bb0`
- `0x180009090`
- `0x180009f78`
- `0x18000a6cc`
- `0x18000ac28`
- `0x180026df8`
- `0x180026fdc`
- `0x180027010`
- `0x180045dac`
- `0x180049010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18000ad30`
- `msvcrt!_wcsicmp` at `0x18000add2`
- `msvcrt!_wcsicmp` at `0x18000ad30`
- `msvcrt!_wcsicmp` at `0x18000add2`
- `iisutil!?ReadLock@CReaderWriterLock3@@QEAAXXZ` at `0x18000ae28`
- `iisutil!?ReadLock@CReaderWriterLock3@@QEAAXXZ` at `0x18000ae28`
- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x18000ac62`
- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x18000ae6f`
- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x18000ae9b`
- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x18000ac62`
- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x18000ae6f`
- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x18000ae9b`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x18000ae8b`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x18000aef5`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x18000af39`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x18000ae8b`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x18000aef5`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x18000af39`
- `iisutil!?Free@ALLOC_CACHE_HANDLER@@QEAAHPEAX@Z` at `0x18000aee4`
- `iisutil!?Free@ALLOC_CACHE_HANDLER@@QEAAHPEAX@Z` at `0x18000af2b`
- `iisutil!?Free@ALLOC_CACHE_HANDLER@@QEAAHPEAX@Z` at `0x18000aee4`
- `iisutil!?Free@ALLOC_CACHE_HANDLER@@QEAAHPEAX@Z` at `0x18000af2b`
- `iisutil!?ReadUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x18000ae39`
- `iisutil!?ReadUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x18000ae39`
- `iisutil!?Alloc@ALLOC_CACHE_HANDLER@@QEAAPEAXXZ` at `0x18000ac76`
- `iisutil!?Alloc@ALLOC_CACHE_HANDLER@@QEAAPEAXXZ` at `0x18000ac76`
- `iisutil!WriteRefTraceLog` at `0x18000aec2`
- `iisutil!WriteRefTraceLog` at `0x18000aec2`

## string_xrefs

- `0x18000ad4d`: `Session closed because of configuration change.`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall FTP_SITE::Update(FTP_SITE *this, struct IAppHostElement *a2, unsigned int a3)
{
  __int64 v6; // r13
  FTP_SITE_CONFIG *v7; // rax
  FTP_SITE_CONFIG *v8; // rbp
  int updated; // ebx
  __int64 v10; // rbx
  int v11; // eax
  int v12; // esi
  unsigned int v13; // edi
  __int64 v14; // rdx
  FTP_LOGGING *v15; // rax
  FTP_LOGGING *v16; // r15
  unsigned int v17; // esi
  int v18; // edi
  volatile signed __int32 *v19; // rbx
  unsigned __int32 v20; // edi

  v6 = *(_QWORD *)((**(__int64 (__fastcall ***)(FTP_SERVERP *))g_pFtpServer)(g_pFtpServer) + 184);
  CReaderWriterLock3::WriteLock((FTP_SITE *)((char *)this + 200));
  *((_DWORD *)this + 76) = a3;
  v7 = (FTP_SITE_CONFIG *)ALLOC_CACHE_HANDLER::Alloc((ALLOC_CACHE_HANDLER *)FTP_SITE_CONFIG::sm_pAllocHandler);
  if ( v7 )
    v8 = FTP_SITE_CONFIG::FTP_SITE_CONFIG(v7);
  else
    v8 = 0;
  if ( !v8 )
  {
    updated = -2147024888;
    goto LABEL_43;
  }
  updated = FTP_SITE_CONFIG::Initialize(v8, a2);
  if ( updated < 0 )
  {
LABEL_42:
    FTP_SITE_CONFIG::~FTP_SITE_CONFIG(v8);
    ALLOC_CACHE_HANDLER::Free((ALLOC_CACHE_HANDLER *)FTP_SITE_CONFIG::sm_pAllocHandler, v8);
    goto LABEL_43;
  }
  v10 = *((_QWORD *)this + 24);
  if ( *((_DWORD *)v8 + 46) != *(_DWORD *)(v10 + 184) )
    goto LABEL_17;
  if ( *((_DWORD *)v8 + 56) != *(_DWORD *)(v10 + 224) )
    goto LABEL_17;
  v11 = *((_DWORD *)v8 + 68);
  if ( v11 != *(_DWORD *)(v10 + 272) )
    goto LABEL_17;
  if ( v11 )
  {
    v12 = 0;
    v13 = 0;
    do
    {
      if ( v13 > *(_DWORD *)(v10 + 272) )
      {
        updated = -2147024809;
        goto LABEL_42;
      }
      if ( _wcsicmp(
             *(const wchar_t **)(*((_QWORD *)v8 + 35) + 600LL * v13 + 56),
             *(const wchar_t **)(*(_QWORD *)(v10 + 280) + 600LL * v13 + 56)) )
      {
        v12 = 1;
      }
      ++v13;
    }
    while ( v13 < *((_DWORD *)v8 + 68) );
    if ( !v12 )
      goto LABEL_18;
LABEL_17:
    FTP_SITE::ShutdownAllSessions(this, 0x36u, L"Session closed because of configuration change.");
  }
LABEL_18:
  if ( (*(_BYTE *)(v6 + 32) & 1) != 0
    || (v14 = *((_QWORD *)this + 24), *((_DWORD *)v8 + 297) != *(_DWORD *)(v14 + 1188))
    || *((_DWORD *)v8 + 293) != *(_DWORD *)(v14 + 1172)
    || *((_DWORD *)v8 + 296) != *(_DWORD *)(v14 + 1184)
    || *((_DWORD *)v8 + 288) != *(_DWORD *)(v14 + 1152)
    || *((_DWORD *)v8 + 292) != *(_DWORD *)(v14 + 1168)
    || *((_QWORD *)v8 + 147) != *(_QWORD *)(v14 + 1176)
    || _wcsicmp(*((const wchar_t **)v8 + 145), *(const wchar_t **)(v14 + 1160)) )
  {
    v15 = (FTP_LOGGING *)operator new(0x68u);
    if ( v15 )
      v16 = FTP_LOGGING::FTP_LOGGING(v15);
    else
      v16 = 0;
    if ( !v16 )
    {
      updated = -2147024888;
      goto LABEL_42;
    }
    v17 = *((_DWORD *)this + 1);
    CReaderWriterLock3::ReadLock((CReaderWriterLock3 *)(v6 + 48));
    v18 = *(_DWORD *)(*(_QWORD *)(v6 + 16) + 12LL);
    CReaderWriterLock3::ReadUnlock((CReaderWriterLock3 *)(v6 + 48));
    updated = FTP_LOGGING::Initialize(v16, (FTP_SITE_CONFIG *)((char *)v8 + 1152), v18, 1, v17);
    if ( updated < 0 )
    {
      FTP_LOGGING::DereferenceFtpLogging(v16);
      goto LABEL_42;
    }
    CReaderWriterLock3::WriteLock((FTP_SITE *)((char *)this + 216));
    FTP_LOGGING::DereferenceFtpLogging(*((FTP_LOGGING **)this + 23));
    *((_QWORD *)this + 23) = v16;
    CReaderWriterLock3::WriteUnlock((FTP_SITE *)((char *)this + 216));
  }
  CReaderWriterLock3::WriteLock((FTP_SITE *)((char *)this + 208));
  v19 = (volatile signed __int32 *)*((_QWORD *)this + 24);
  v20 = _InterlockedDecrement(v19);
  if ( FTP_SITE_CONFIG::sm_pRefTraceLog )
    WriteRefTraceLog(FTP_SITE_CONFIG::sm_pRefTraceLog, v20);
  if ( !v20 && v19 )
  {
    FTP_SITE_CONFIG::~FTP_SITE_CONFIG((FTP_SITE_CONFIG *)v19);
    ALLOC_CACHE_HANDLER::Free((ALLOC_CACHE_HANDLER *)FTP_SITE_CONFIG::sm_pAllocHandler, (void *)v19);
  }
  *((_QWORD *)this + 24) = v8;
  CReaderWriterLock3::WriteUnlock((FTP_SITE *)((char *)this + 208));
  updated = FTP_SITE::InitializeOrUpdateEndpoints(this, a3);
  if ( updated >= 0 )
    updated = 0;
LABEL_43:
  CReaderWriterLock3::WriteUnlock((FTP_SITE *)((char *)this + 200));
  *((_DWORD *)this + 77) = updated;
  return (unsigned int)updated;
}

```

## disassembly

```asm
0x18000ac28  push    rbx
0x18000ac2a  push    rbp
0x18000ac2b  push    rsi
0x18000ac2c  push    rdi
0x18000ac2d  push    r12
0x18000ac2f  push    r13
0x18000ac31  push    r14
0x18000ac33  push    r15
0x18000ac35  sub     rsp, 38h
0x18000ac39  mov     r12d, r8d
0x18000ac3c  mov     rbx, rdx
0x18000ac3f  mov     r14, rcx
0x18000ac42  mov     rcx, cs:?g_pFtpServer@@3PEAVFTP_SERVER@@EA; FTP_SERVER * g_pFtpServer
0x18000ac49  mov     rax, [rcx]
0x18000ac4c  mov     rax, [rax]
0x18000ac4f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ac54  mov     r13, [rax+0B8h]
0x18000ac5b  lea     rcx, [r14+0C8h]
0x18000ac62  call    cs:__imp_?WriteLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteLock(void)
0x18000ac68  mov     [r14+130h], r12d
0x18000ac6f  mov     rcx, cs:?sm_pAllocHandler@FTP_SITE_CONFIG@@0PEAVALLOC_CACHE_HANDLER@@EA; ALLOC_CACHE_HANDLER * FTP_SITE_CONFIG::sm_pAllocHandler
0x18000ac76  call    cs:__imp_?Alloc@ALLOC_CACHE_HANDLER@@QEAAPEAXXZ; ALLOC_CACHE_HANDLER::Alloc(void)
0x18000ac7c  mov     [rsp+78h+arg_0], rax
0x18000ac84  test    rax, rax
0x18000ac87  jz      short loc_18000AC96
0x18000ac89  mov     rcx, rax; this
0x18000ac8c  call    ??0FTP_SITE_CONFIG@@QEAA@XZ; FTP_SITE_CONFIG::FTP_SITE_CONFIG(void)
0x18000ac91  mov     rbp, rax
0x18000ac94  jmp     short loc_18000AC98
0x18000ac96  xor     ebp, ebp
0x18000ac98  test    rbp, rbp
0x18000ac9b  jnz     short loc_18000ACA7
0x18000ac9d  mov     ebx, 80070008h
0x18000aca2  jmp     loc_18000AF32
0x18000aca7  mov     rdx, rbx; struct IAppHostElement *
0x18000acaa  mov     rcx, rbp; this
0x18000acad  call    ?Initialize@FTP_SITE_CONFIG@@QEAAJPEAUIAppHostElement@@@Z; FTP_SITE_CONFIG::Initialize(IAppHostElement *)
0x18000acb2  mov     ebx, eax
0x18000acb4  test    eax, eax
0x18000acb6  js      loc_18000AF18
0x18000acbc  mov     rbx, [r14+0C0h]
0x18000acc3  mov     eax, [rbx+0B8h]
0x18000acc9  mov     r15d, 1
0x18000accf  cmp     [rbp+0B8h], eax
0x18000acd5  jnz     short loc_18000AD4D
0x18000acd7  mov     eax, [rbx+0E0h]
0x18000acdd  cmp     [rbp+0E0h], eax
0x18000ace3  jnz     short loc_18000AD4D
0x18000ace5  mov     eax, [rbp+110h]
0x18000aceb  cmp     eax, [rbx+110h]
0x18000acf1  jnz     short loc_18000AD4D
0x18000acf3  test    eax, eax
0x18000acf5  jz      short loc_18000AD61
0x18000acf7  xor     esi, esi
0x18000acf9  xor     edi, edi
0x18000acfb  cmp     edi, eax
0x18000acfd  ja      loc_18000AE04
0x18000ad03  cmp     edi, [rbx+110h]
0x18000ad09  ja      loc_18000AE04
0x18000ad0f  mov     eax, edi
0x18000ad11  imul    r8, rax, 258h
0x18000ad18  mov     rdx, [rbx+118h]
0x18000ad1f  mov     rcx, [rbp+118h]
0x18000ad26  mov     rdx, [rdx+r8+38h]; String2
0x18000ad2b  mov     rcx, [rcx+r8+38h]; String1
0x18000ad30  call    cs:__imp__wcsicmp
0x18000ad36  test    eax, eax
0x18000ad38  cmovnz  esi, r15d
0x18000ad3c  add     edi, r15d
0x18000ad3f  mov     eax, [rbp+110h]
0x18000ad45  cmp     edi, eax
0x18000ad47  jb      short loc_18000AD03
0x18000ad49  test    esi, esi
0x18000ad4b  jz      short loc_18000AD61
0x18000ad4d  lea     r8, aSessionClosedB; "Session closed because of configuration"...
0x18000ad54  mov     edx, 36h ; '6'; unsigned int
0x18000ad59  mov     rcx, r14; this
0x18000ad5c  call    ?ShutdownAllSessions@FTP_SITE@@QEAAXKPEBG@Z; FTP_SITE::ShutdownAllSessions(ulong,ushort const *)
0x18000ad61  test    [r13+20h], r15b
0x18000ad65  jnz     short loc_18000ADE0
0x18000ad67  mov     rdx, [r14+0C0h]
0x18000ad6e  mov     eax, [rdx+4A4h]
0x18000ad74  cmp     [rbp+4A4h], eax
0x18000ad7a  jnz     short loc_18000ADE0
0x18000ad7c  mov     eax, [rdx+494h]
0x18000ad82  cmp     [rbp+494h], eax
0x18000ad88  jnz     short loc_18000ADE0
0x18000ad8a  mov     eax, [rdx+4A0h]
0x18000ad90  cmp     [rbp+4A0h], eax
0x18000ad96  jnz     short loc_18000ADE0
0x18000ad98  mov     eax, [rdx+480h]
0x18000ad9e  cmp     [rbp+480h], eax
0x18000ada4  jnz     short loc_18000ADE0
0x18000ada6  mov     eax, [rdx+490h]
0x18000adac  cmp     [rbp+490h], eax
0x18000adb2  jnz     short loc_18000ADE0
0x18000adb4  mov     rax, [rdx+498h]
0x18000adbb  cmp     [rbp+498h], rax
0x18000adc2  jnz     short loc_18000ADE0
0x18000adc4  mov     rdx, [rdx+488h]; String2
0x18000adcb  mov     rcx, [rbp+488h]; String1
0x18000add2  call    cs:__imp__wcsicmp
0x18000add8  test    eax, eax
0x18000adda  jz      loc_18000AE91
0x18000ade0  mov     ecx, 68h ; 'h'; Size
0x18000ade5  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000adea  mov     [rsp+78h+arg_0], rax
0x18000adf2  test    rax, rax
0x18000adf5  jz      short loc_18000AE0E
0x18000adf7  mov     rcx, rax; this
0x18000adfa  call    ??0FTP_LOGGING@@QEAA@XZ; FTP_LOGGING::FTP_LOGGING(void)
0x18000adff  mov     r15, rax
0x18000ae02  jmp     short loc_18000AE11
0x18000ae04  mov     ebx, 80070057h
0x18000ae09  jmp     loc_18000AF18
0x18000ae0e  xor     r15d, r15d
0x18000ae11  test    r15, r15
0x18000ae14  jnz     short loc_18000AE20
0x18000ae16  mov     ebx, 80070008h
0x18000ae1b  jmp     loc_18000AF18
0x18000ae20  mov     esi, [r14+4]
0x18000ae24  lea     rcx, [r13+30h]
0x18000ae28  call    cs:__imp_?ReadLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::ReadLock(void)
0x18000ae2e  mov     rax, [r13+10h]
0x18000ae32  mov     edi, [rax+0Ch]
0x18000ae35  lea     rcx, [r13+30h]
0x18000ae39  call    cs:__imp_?ReadUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::ReadUnlock(void)
0x18000ae3f  lea     rdx, [rbp+480h]; struct FTP_LOG_FILE_CONFIG_ELEMENT *
0x18000ae46  mov     [rsp+78h+var_58], esi; unsigned int
0x18000ae4a  mov     r9d, 1; int
0x18000ae50  mov     r8d, edi; int
0x18000ae53  mov     rcx, r15; this
0x18000ae56  call    ?Initialize@FTP_LOGGING@@QEAAJPEAVFTP_LOG_FILE_CONFIG_ELEMENT@@HHK@Z; FTP_LOGGING::Initialize(FTP_LOG_FILE_CONFIG_ELEMENT *,int,int,ulong)
0x18000ae5b  mov     ebx, eax
0x18000ae5d  test    eax, eax
0x18000ae5f  js      loc_18000AF10
0x18000ae65  lea     rbx, [r14+0D8h]
0x18000ae6c  mov     rcx, rbx
0x18000ae6f  call    cs:__imp_?WriteLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteLock(void)
0x18000ae75  mov     rcx, [r14+0B8h]; this
0x18000ae7c  call    ?DereferenceFtpLogging@FTP_LOGGING@@QEAAXXZ; FTP_LOGGING::DereferenceFtpLogging(void)
0x18000ae81  mov     [r14+0B8h], r15
0x18000ae88  mov     rcx, rbx
0x18000ae8b  call    cs:__imp_?WriteUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteUnlock(void)
0x18000ae91  lea     rsi, [r14+0D0h]
0x18000ae98  mov     rcx, rsi
0x18000ae9b  call    cs:__imp_?WriteLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteLock(void)
0x18000aea1  mov     rbx, [r14+0C0h]
0x18000aea8  or      edi, 0FFFFFFFFh
0x18000aeab  lock xadd [rbx], edi
0x18000aeaf  dec     edi
0x18000aeb1  mov     rcx, cs:?sm_pRefTraceLog@FTP_SITE_CONFIG@@0PEAU_TRACE_LOG@@EA; _TRACE_LOG * FTP_SITE_CONFIG::sm_pRefTraceLog
0x18000aeb8  test    rcx, rcx
0x18000aebb  jz      short loc_18000AEC8
0x18000aebd  mov     r8, rbx
0x18000aec0  mov     edx, edi
0x18000aec2  call    cs:__imp_WriteRefTraceLog
0x18000aec8  test    edi, edi
0x18000aeca  jnz     short loc_18000AEEB
0x18000aecc  test    rbx, rbx
0x18000aecf  jz      short loc_18000AEEB
0x18000aed1  mov     rcx, rbx; this
0x18000aed4  call    ??1FTP_SITE_CONFIG@@QEAA@XZ; FTP_SITE_CONFIG::~FTP_SITE_CONFIG(void)
0x18000aed9  nop
0x18000aeda  mov     rdx, rbx
0x18000aedd  mov     rcx, cs:?sm_pAllocHandler@FTP_SITE_CONFIG@@0PEAVALLOC_CACHE_HANDLER@@EA; ALLOC_CACHE_HANDLER * FTP_SITE_CONFIG::sm_pAllocHandler
0x18000aee4  call    cs:__imp_?Free@ALLOC_CACHE_HANDLER@@QEAAHPEAX@Z; ALLOC_CACHE_HANDLER::Free(void *)
0x18000aeea  nop
0x18000aeeb  mov     [r14+0C0h], rbp
0x18000aef2  mov     rcx, rsi
0x18000aef5  call    cs:__imp_?WriteUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteUnlock(void)
0x18000aefb  mov     edx, r12d; unsigned int
0x18000aefe  mov     rcx, r14; this
0x18000af01  call    ?InitializeOrUpdateEndpoints@FTP_SITE@@AEAAJK@Z; FTP_SITE::InitializeOrUpdateEndpoints(ulong)
0x18000af06  mov     ebx, eax
0x18000af08  test    eax, eax
0x18000af0a  js      short loc_18000AF32
0x18000af0c  xor     ebx, ebx
0x18000af0e  jmp     short loc_18000AF32
0x18000af10  mov     rcx, r15; this
0x18000af13  call    ?DereferenceFtpLogging@FTP_LOGGING@@QEAAXXZ; FTP_LOGGING::DereferenceFtpLogging(void)
0x18000af18  mov     rcx, rbp; this
0x18000af1b  call    ??1FTP_SITE_CONFIG@@QEAA@XZ; FTP_SITE_CONFIG::~FTP_SITE_CONFIG(void)
0x18000af20  nop
0x18000af21  mov     rdx, rbp
0x18000af24  mov     rcx, cs:?sm_pAllocHandler@FTP_SITE_CONFIG@@0PEAVALLOC_CACHE_HANDLER@@EA; ALLOC_CACHE_HANDLER * FTP_SITE_CONFIG::sm_pAllocHandler
0x18000af2b  call    cs:__imp_?Free@ALLOC_CACHE_HANDLER@@QEAAHPEAX@Z; ALLOC_CACHE_HANDLER::Free(void *)
0x18000af31  nop
0x18000af32  lea     rcx, [r14+0C8h]
0x18000af39  call    cs:__imp_?WriteUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteUnlock(void)
0x18000af3f  mov     [r14+134h], ebx
0x18000af46  mov     eax, ebx
0x18000af48  add     rsp, 38h
0x18000af4c  pop     r15
0x18000af4e  pop     r14
0x18000af50  pop     r13
0x18000af52  pop     r12
0x18000af54  pop     rdi
0x18000af55  pop     rsi
0x18000af56  pop     rbp
0x18000af57  pop     rbx
0x18000af58  retn
```
