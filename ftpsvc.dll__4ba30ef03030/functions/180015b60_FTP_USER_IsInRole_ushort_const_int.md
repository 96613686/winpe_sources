# FTP_USER::IsInRole(ushort const *,int *)

- ea: `0x180015b60`
- end: `0x180015f16`
- name: `?IsInRole@FTP_USER@@UEAAJPEBGPEAH@Z`
- size: `950`
- prototype: `__int64 __fastcall(FTP_USER *__hidden this, const unsigned __int16 *, int *)`
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x180009090`
- `0x180015b60`
- `0x1800199d4`
- `0x180019b48`
- `0x18002c12c`
- `0x18004700f`
- `0x180047050`
- `0x180049010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x180015bfe`
- `msvcrt!_wcsicmp` at `0x180015bfe`
- `iisutil!?ReadLock@CReaderWriterLock3@@QEAAXXZ` at `0x180015bac`
- `iisutil!?ReadLock@CReaderWriterLock3@@QEAAXXZ` at `0x180015bac`
- `iisutil!?Free@ALLOC_CACHE_HANDLER@@QEAAHPEAX@Z` at `0x180015ee6`
- `iisutil!?Free@ALLOC_CACHE_HANDLER@@QEAAHPEAX@Z` at `0x180015ee6`
- `iisutil!PuDbgPrint` at `0x180015e1a`
- `iisutil!PuDbgPrint` at `0x180015e1a`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180015d24`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180015d24`
- `iisutil!?ReadUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x180015be1`
- `iisutil!?ReadUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x180015be1`
- `iisutil!WriteRefTraceLog` at `0x180015bd1`
- `iisutil!WriteRefTraceLog` at `0x180015ec4`
- `iisutil!WriteRefTraceLog` at `0x180015bd1`
- `iisutil!WriteRefTraceLog` at `0x180015ec4`
- `iisutil!PuDbgPrintError` at `0x180015d73`
- `iisutil!PuDbgPrintError` at `0x180015e77`
- `iisutil!PuDbgPrintError` at `0x180015d73`
- `iisutil!PuDbgPrintError` at `0x180015e77`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180015dc5`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180015e3b`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180015dc5`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180015e3b`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall FTP_USER::IsInRole(const wchar_t **this, const unsigned __int16 *a2, int *a3)
{
  __int64 v5; // rdi
  CReaderWriterLock3 *v6; // rbx
  __int64 v7; // rdx
  __int64 v8; // rdi
  unsigned int v9; // r12d
  unsigned int v10; // esi
  struct IUnknown *v11; // rcx
  CUSTOM_PROVIDER_ENTRY *v12; // r14
  int v13; // r15d
  int ReferencedProvider; // ebx
  __int64 v15; // rdx
  __int64 v16; // r8
  int *v17; // r10
  unsigned __int32 v18; // esi
  struct IUnknown *v20; // [rsp+40h] [rbp-C0h] BYREF
  FTP_USER *v21; // [rsp+48h] [rbp-B8h]
  const unsigned __int16 *v22; // [rsp+50h] [rbp-B0h]
  _BYTE v23[32]; // [rsp+58h] [rbp-A8h] BYREF
  const wchar_t *v24; // [rsp+78h] [rbp-88h]
  unsigned __int16 v25[64]; // [rsp+90h] [rbp-70h] BYREF

  v22 = a2;
  v21 = (FTP_USER *)this;
  v5 = *((_QWORD *)this[1] + 2);
  v6 = (CReaderWriterLock3 *)(v5 + 208);
  CReaderWriterLock3::ReadLock((CReaderWriterLock3 *)(v5 + 208));
  v7 = (unsigned int)_InterlockedIncrement(*(volatile signed __int32 **)(v5 + 192));
  if ( FTP_SITE_CONFIG::sm_pRefTraceLog )
    WriteRefTraceLog(FTP_SITE_CONFIG::sm_pRefTraceLog, v7);
  v8 = *(_QWORD *)(v5 + 192);
  CReaderWriterLock3::ReadUnlock(v6);
  v20 = 0;
  if ( _wcsicmp(this[17], L"CustomAuth") )
  {
    ReferencedProvider = -2147467263;
  }
  else
  {
    v9 = *(_DWORD *)(v8 + 272);
    v10 = 0;
    if ( v9 )
    {
      while ( 2 )
      {
        v11 = v20;
        if ( v20 )
        {
          ((void (__fastcall *)(struct IUnknown *))v20->lpVtbl->Release)(v20);
          v11 = 0;
          v20 = 0;
        }
        if ( v10 > *(_DWORD *)(v8 + 272) )
        {
          ReferencedProvider = -2147024809;
          goto LABEL_33;
        }
        v12 = (CUSTOM_PROVIDER_ENTRY *)(*(_QWORD *)(v8 + 280) + 600LL * v10);
        v13 = 0;
        while ( 1 )
        {
          ReferencedProvider = CUSTOM_PROVIDER_ENTRY::GetReferencedProvider(
                                 v12,
                                 &GUID_909c850d_8ca0_4674_96b8_cc2941535725,
                                 &v20);
          if ( ReferencedProvider < 0 )
            break;
          (*(void (__fastcall **)(FTP_SERVERP *, __int64))(*(_QWORD *)g_pFtpServer + 176LL))(g_pFtpServer, 1);
          v15 = *((_QWORD *)v21 + 1);
          v16 = *(_QWORD *)(v15 + 16);
          v17 = &dword_18004D454;
          if ( *(_QWORD *)(v16 + 8) )
            v17 = *(int **)(v16 + 8);
          ReferencedProvider = ((__int64 (__fastcall *)(struct IUnknown *, _QWORD, int *, _QWORD, const unsigned __int16 *, int *))v20->lpVtbl[1].QueryInterface)(
                                 v20,
                                 *(_QWORD *)(v15 + 1168),
                                 v17,
                                 *((_QWORD *)v21 + 7),
                                 v22,
                                 a3);
          (*(void (__fastcall **)(FTP_SERVERP *, __int64))(*(_QWORD *)g_pFtpServer + 184LL))(g_pFtpServer, 1);
          if ( ReferencedProvider < 0 )
          {
            memset_0(v25, 0, sizeof(v25));
            STRU::STRU((STRU *)v23, v25, 0x40u);
            GetLastComExceptionErrorInfo((struct STRU *)v23);
            if ( (g_dwDebugFlags & 0xF) != 0 )
              PuDbgPrintError(
                g_pDebug,
                "inetsrv\\iis\\iisrearc\\ftp\\server\\core\\ftp_user.cxx",
                414,
                "FTP_USER::IsInRole",
                ReferencedProvider,
                "Failed to call pFtpRoleProvider->IsUserInRole(). Exception details: %S\n",
                v24);
            if ( ReferencedProvider != -2147417848
              && ReferencedProvider != -2147023170
              && ReferencedProvider != -2146234348
              && ReferencedProvider != -2147023174 )
            {
              STRU::~STRU(v23);
              goto LABEL_32;
            }
            ((void (__fastcall *)(struct IUnknown *))v20->lpVtbl->Release)(v20);
            v20 = 0;
            CUSTOM_PROVIDER_ENTRY::Invalidate(v12);
            STRU::~STRU(v23);
            if ( (unsigned int)++v13 < 2 )
              continue;
          }
          goto LABEL_24;
        }
        if ( ReferencedProvider != -2147467262 )
        {
          if ( (g_dwDebugFlags & 0xF) != 0 )
            PuDbgPrintError(
              g_pDebug,
              "inetsrv\\iis\\iisrearc\\ftp\\server\\core\\ftp_user.cxx",
              381,
              "FTP_USER::IsInRole",
              ReferencedProvider,
              "Failed to retrieve IFtpRoleProvider interface.");
          goto LABEL_32;
        }
        *a3 = 0;
        if ( (g_dwDebugFlags & 3) != 0 )
        {
          PuDbgPrint(
            g_pDebug,
            "inetsrv\\iis\\iisrearc\\ftp\\server\\core\\ftp_user.cxx",
            374,
            "FTP_USER::IsInRole",
            "IFtpRoleProvider is not implemented by the object. Set InRole = FALSE\n");
LABEL_24:
          if ( *a3 )
            break;
        }
        if ( ++v10 < v9 )
          continue;
        break;
      }
    }
    ReferencedProvider = 0;
  }
LABEL_32:
  v11 = v20;
LABEL_33:
  if ( v11 )
  {
    ((void (__fastcall *)(struct IUnknown *))v11->lpVtbl->Release)(v11);
    v20 = 0;
  }
  v18 = _InterlockedDecrement((volatile signed __int32 *)v8);
  if ( FTP_SITE_CONFIG::sm_pRefTraceLog )
    WriteRefTraceLog(FTP_SITE_CONFIG::sm_pRefTraceLog, v18);
  if ( !v18 && v8 )
  {
    FTP_SITE_CONFIG::~FTP_SITE_CONFIG((FTP_SITE_CONFIG *)v8);
    ALLOC_CACHE_HANDLER::Free((ALLOC_CACHE_HANDLER *)FTP_SITE_CONFIG::sm_pAllocHandler, (void *)v8);
  }
  return (unsigned int)ReferencedProvider;
}

```

## disassembly

```asm
0x180015b60  mov     [rsp-8+arg_18], rbx
0x180015b65  push    rbp
0x180015b66  push    rsi
0x180015b67  push    rdi
0x180015b68  push    r12
0x180015b6a  push    r13
0x180015b6c  push    r14
0x180015b6e  push    r15
0x180015b70  lea     rbp, [rsp-20h]
0x180015b75  sub     rsp, 120h
0x180015b7c  mov     rax, cs:__security_cookie
0x180015b83  xor     rax, rsp
0x180015b86  mov     [rbp+50h+var_40], rax
0x180015b8a  mov     r13, r8
0x180015b8d  mov     [rsp+150h+var_100], rdx
0x180015b92  mov     rsi, rcx
0x180015b95  mov     [rsp+150h+var_108], rcx
0x180015b9a  mov     rax, [rcx+8]
0x180015b9e  mov     rdi, [rax+10h]
0x180015ba2  lea     rbx, [rdi+0D0h]
0x180015ba9  mov     rcx, rbx
0x180015bac  call    cs:__imp_?ReadLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::ReadLock(void)
0x180015bb2  mov     r8, [rdi+0C0h]
0x180015bb9  mov     edx, 1
0x180015bbe  lock xadd [r8], edx
0x180015bc3  inc     edx
0x180015bc5  mov     rcx, cs:?sm_pRefTraceLog@FTP_SITE_CONFIG@@0PEAU_TRACE_LOG@@EA; _TRACE_LOG * FTP_SITE_CONFIG::sm_pRefTraceLog
0x180015bcc  test    rcx, rcx
0x180015bcf  jz      short loc_180015BD7
0x180015bd1  call    cs:__imp_WriteRefTraceLog
0x180015bd7  mov     rdi, [rdi+0C0h]
0x180015bde  mov     rcx, rbx
0x180015be1  call    cs:__imp_?ReadUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::ReadUnlock(void)
0x180015be7  mov     [rsp+150h+var_110], 0
0x180015bf0  lea     rdx, aCustomauth; "CustomAuth"
0x180015bf7  mov     rcx, [rsi+88h]; String1
0x180015bfe  call    cs:__imp__wcsicmp
0x180015c04  test    eax, eax
0x180015c06  jnz     loc_180015E86
0x180015c0c  mov     r12d, [rdi+110h]
0x180015c13  xor     esi, esi
0x180015c15  test    r12d, r12d
0x180015c18  jz      loc_180015E32
0x180015c1e  mov     rcx, [rsp+150h+var_110]
0x180015c23  test    rcx, rcx
0x180015c26  jz      short loc_180015C3B
0x180015c28  mov     rax, [rcx]
0x180015c2b  mov     rax, [rax+10h]
0x180015c2f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015c34  xor     ecx, ecx
0x180015c36  mov     [rsp+150h+var_110], rcx
0x180015c3b  cmp     esi, [rdi+110h]
0x180015c41  ja      loc_180015E7F
0x180015c47  mov     eax, esi
0x180015c49  imul    r14, rax, 258h
0x180015c50  add     r14, [rdi+118h]
0x180015c57  xor     r15d, r15d
0x180015c5a  lea     r8, [rsp+150h+var_110]; struct IUnknown **
0x180015c5f  lea     rdx, _GUID_909c850d_8ca0_4674_96b8_cc2941535725; struct _GUID *
0x180015c66  mov     rcx, r14; this
0x180015c69  call    ?GetReferencedProvider@CUSTOM_PROVIDER_ENTRY@@QEAAJAEBU_GUID@@PEAPEAUIUnknown@@@Z; CUSTOM_PROVIDER_ENTRY::GetReferencedProvider(_GUID const &,IUnknown * *)
0x180015c6e  mov     ebx, eax
0x180015c70  test    eax, eax
0x180015c72  js      loc_180015DDA
0x180015c78  mov     rcx, cs:?g_pFtpServer@@3PEAVFTP_SERVER@@EA; FTP_SERVER * g_pFtpServer
0x180015c7f  mov     rax, [rcx]
0x180015c82  mov     edx, 1
0x180015c87  mov     rax, [rax+0B0h]
0x180015c8e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015c93  mov     rcx, [rsp+150h+var_110]
0x180015c98  mov     rax, [rcx]
0x180015c9b  mov     r9, [rsp+150h+var_108]
0x180015ca0  mov     rdx, [r9+8]
0x180015ca4  mov     r8, [rdx+10h]
0x180015ca8  lea     r10, dword_18004D454
0x180015caf  cmp     qword ptr [r8+8], 0
0x180015cb4  cmovnz  r10, [r8+8]
0x180015cb9  mov     [rsp+150h+var_128], r13
0x180015cbe  mov     r8, [rsp+150h+var_100]
0x180015cc3  mov     [rsp+150h+var_130], r8
0x180015cc8  mov     r9, [r9+38h]
0x180015ccc  mov     r8, r10
0x180015ccf  mov     rdx, [rdx+490h]
0x180015cd6  mov     rax, [rax+18h]
0x180015cda  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015cdf  mov     ebx, eax
0x180015ce1  mov     rcx, cs:?g_pFtpServer@@3PEAVFTP_SERVER@@EA; FTP_SERVER * g_pFtpServer
0x180015ce8  mov     rax, [rcx]
0x180015ceb  mov     edx, 1
0x180015cf0  mov     rax, [rax+0B8h]
0x180015cf7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015cfc  test    ebx, ebx
0x180015cfe  jns     loc_180015E20
0x180015d04  xor     edx, edx; Val
0x180015d06  mov     r8d, 80h; Size
0x180015d0c  lea     rcx, [rbp+50h+var_C0]; void *
0x180015d10  call    memset_0
0x180015d15  mov     r8d, 40h ; '@'
0x180015d1b  lea     rdx, [rbp+50h+var_C0]
0x180015d1f  lea     rcx, [rsp+150h+var_F8]
0x180015d24  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x180015d2a  nop
0x180015d2b  lea     rcx, [rsp+150h+var_F8]; struct STRU *
0x180015d30  call    ?GetLastComExceptionErrorInfo@@YAJPEAVSTRU@@H@Z; GetLastComExceptionErrorInfo(STRU *,int)
0x180015d35  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180015d3c  jz      short loc_180015D79
0x180015d3e  mov     rax, [rsp+150h+var_D8]
0x180015d43  mov     [rsp+150h+var_120], rax
0x180015d48  lea     rax, aFailedToCallPf; "Failed to call pFtpRoleProvider->IsUser"...
0x180015d4f  mov     [rsp+150h+var_128], rax
0x180015d54  mov     dword ptr [rsp+150h+var_130], ebx
0x180015d58  lea     r9, aFtpUserIsinrol; "FTP_USER::IsInRole"
0x180015d5f  mov     r8d, 19Eh
0x180015d65  lea     rdx, aInetsrvIisIisr_24; "inetsrv\\iis\\iisrearc\\ftp\\server\\co"...
0x180015d6c  mov     rcx, cs:g_pDebug
0x180015d73  call    cs:__imp_PuDbgPrintError
0x180015d79  cmp     ebx, 80010108h
0x180015d7f  jz      short loc_180015D9D
0x180015d81  cmp     ebx, 800706BEh
0x180015d87  jz      short loc_180015D9D
0x180015d89  cmp     ebx, 80131014h
0x180015d8f  jz      short loc_180015D9D
0x180015d91  cmp     ebx, 800706BAh
0x180015d97  jnz     loc_180015E36
0x180015d9d  mov     rcx, [rsp+150h+var_110]
0x180015da2  mov     rax, [rcx]
0x180015da5  mov     rax, [rax+10h]
0x180015da9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015dae  mov     [rsp+150h+var_110], 0
0x180015db7  mov     rcx, r14; this
0x180015dba  call    ?Invalidate@CUSTOM_PROVIDER_ENTRY@@QEAAXXZ; CUSTOM_PROVIDER_ENTRY::Invalidate(void)
0x180015dbf  nop
0x180015dc0  lea     rcx, [rsp+150h+var_F8]
0x180015dc5  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180015dcb  inc     r15d
0x180015dce  cmp     r15d, 2
0x180015dd2  jb      loc_180015C5A
0x180015dd8  jmp     short loc_180015E20
0x180015dda  cmp     ebx, 80004002h
0x180015de0  jnz     short loc_180015E43
0x180015de2  mov     dword ptr [r13+0], 0
0x180015dea  test    byte ptr cs:g_dwDebugFlags, 3
0x180015df1  jz      short loc_180015E27
0x180015df3  lea     rax, aIftproleprovid; "IFtpRoleProvider is not implemented by "...
0x180015dfa  mov     [rsp+150h+var_130], rax
0x180015dff  lea     r9, aFtpUserIsinrol; "FTP_USER::IsInRole"
0x180015e06  mov     r8d, 176h
0x180015e0c  lea     rdx, aInetsrvIisIisr_24; "inetsrv\\iis\\iisrearc\\ftp\\server\\co"...
0x180015e13  mov     rcx, cs:g_pDebug
0x180015e1a  call    cs:__imp_PuDbgPrint
0x180015e20  cmp     dword ptr [r13+0], 0
0x180015e25  jnz     short loc_180015E32
0x180015e27  inc     esi
0x180015e29  cmp     esi, r12d
0x180015e2c  jb      loc_180015C1E
0x180015e32  xor     ebx, ebx
0x180015e34  jmp     short loc_180015E8B
0x180015e36  lea     rcx, [rsp+150h+var_F8]
0x180015e3b  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180015e41  jmp     short loc_180015E8B
0x180015e43  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180015e4a  jz      short loc_180015E8B
0x180015e4c  lea     rax, aFailedToRetrie_3; "Failed to retrieve IFtpRoleProvider int"...
0x180015e53  mov     [rsp+150h+var_128], rax
0x180015e58  mov     dword ptr [rsp+150h+var_130], ebx
0x180015e5c  lea     r9, aFtpUserIsinrol; "FTP_USER::IsInRole"
0x180015e63  mov     r8d, 17Dh
0x180015e69  lea     rdx, aInetsrvIisIisr_24; "inetsrv\\iis\\iisrearc\\ftp\\server\\co"...
0x180015e70  mov     rcx, cs:g_pDebug
0x180015e77  call    cs:__imp_PuDbgPrintError
0x180015e7d  jmp     short loc_180015E8B
0x180015e7f  mov     ebx, 80070057h
0x180015e84  jmp     short loc_180015E90
0x180015e86  mov     ebx, 80004001h
0x180015e8b  mov     rcx, [rsp+150h+var_110]
0x180015e90  test    rcx, rcx
0x180015e93  jz      short loc_180015EAA
0x180015e95  mov     rax, [rcx]
0x180015e98  mov     rax, [rax+10h]
0x180015e9c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015ea1  mov     [rsp+150h+var_110], 0
0x180015eaa  or      esi, 0FFFFFFFFh
0x180015ead  lock xadd [rdi], esi
0x180015eb1  dec     esi
0x180015eb3  mov     rcx, cs:?sm_pRefTraceLog@FTP_SITE_CONFIG@@0PEAU_TRACE_LOG@@EA; _TRACE_LOG * FTP_SITE_CONFIG::sm_pRefTraceLog
0x180015eba  test    rcx, rcx
0x180015ebd  jz      short loc_180015ECA
0x180015ebf  mov     r8, rdi
0x180015ec2  mov     edx, esi
0x180015ec4  call    cs:__imp_WriteRefTraceLog
0x180015eca  test    esi, esi
0x180015ecc  jnz     short loc_180015EED
0x180015ece  test    rdi, rdi
0x180015ed1  jz      short loc_180015EED
0x180015ed3  mov     rcx, rdi; this
0x180015ed6  call    ??1FTP_SITE_CONFIG@@QEAA@XZ; FTP_SITE_CONFIG::~FTP_SITE_CONFIG(void)
0x180015edb  nop
0x180015edc  mov     rdx, rdi
0x180015edf  mov     rcx, cs:?sm_pAllocHandler@FTP_SITE_CONFIG@@0PEAVALLOC_CACHE_HANDLER@@EA; ALLOC_CACHE_HANDLER * FTP_SITE_CONFIG::sm_pAllocHandler
0x180015ee6  call    cs:__imp_?Free@ALLOC_CACHE_HANDLER@@QEAAHPEAX@Z; ALLOC_CACHE_HANDLER::Free(void *)
0x180015eec  nop
0x180015eed  mov     eax, ebx
0x180015eef  mov     rcx, [rbp+50h+var_40]
0x180015ef3  xor     rcx, rsp; StackCookie
0x180015ef6  call    __security_check_cookie
0x180015efb  mov     rbx, [rsp+150h+arg_18]
0x180015f03  add     rsp, 120h
0x180015f0a  pop     r15
0x180015f0c  pop     r14
0x180015f0e  pop     r13
0x180015f10  pop     r12
0x180015f12  pop     rdi
0x180015f13  pop     rsi
0x180015f14  pop     rbp
0x180015f15  retn
```
