# FTP_SITE_MANAGER::OnNewConnection(FTP_ENDPOINT_CONNECTION *,void *)

- ea: `0x18000c420`
- end: `0x18000c819`
- name: `?OnNewConnection@FTP_SITE_MANAGER@@SAXPEAVFTP_ENDPOINT_CONNECTION@@PEAX@Z`
- size: `1017`
- prototype: `void __fastcall(struct FTP_ENDPOINT_CONNECTION *, void *)`
- caller_count: `0`
- callee_count: `12`
- tags: `file_ops, loader_planting, broker_com_uri`

## callees

- `0x180001250`
- `0x180008f40`
- `0x18000bf2c`
- `0x18000c1f4`
- `0x18000c420`
- `0x180014288`
- `0x180022780`
- `0x1800235b0`
- `0x180032804`
- `0x18004700f`
- `0x180047050`
- `0x180049010`

## import_xrefs

- `iisutil!PuDbgPrint` at `0x18000c535`
- `iisutil!PuDbgPrint` at `0x18000c535`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18000c474`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18000c474`
- `iisutil!?Alloc@ALLOC_CACHE_HANDLER@@QEAAPEAXXZ` at `0x18000c6b5`
- `iisutil!?Alloc@ALLOC_CACHE_HANDLER@@QEAAPEAXXZ` at `0x18000c6b5`
- `iisutil!??0STRU@@QEAA@XZ` at `0x18000c496`
- `iisutil!??0STRU@@QEAA@XZ` at `0x18000c551`
- `iisutil!??0STRU@@QEAA@XZ` at `0x18000c496`
- `iisutil!??0STRU@@QEAA@XZ` at `0x18000c551`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000c5a3`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000c7b0`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000c7bb`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000c5a3`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000c7b0`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000c7bb`

## string_xrefs

- `0x18000c5bd`: `IP restriction rules denied the access.`
- `0x18000c637`: `Dynamic IP restriction rules denied the access(Log-only mode).`
- `0x18000c630`: `Dynamic IP restriction rules denied the access.`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall FTP_SITE_MANAGER::OnNewConnection(const struct sockaddr *a1, void *a2)
{
  int Metadata; // eax
  struct FTP_METADATA *v4; // rbx
  int v5; // r14d
  int v6; // ebx
  DYNAMIC_IP_RESTRICTION *v7; // rcx
  int v8; // eax
  const unsigned __int16 *v9; // rcx
  FTP_SITE_MANAGER *v10; // rax
  int v11; // eax
  volatile signed __int32 *v12; // rdi
  void *v13; // rax
  FTP_SESSION *v14; // rbx
  int v15; // eax
  __int64 v16; // r10
  struct FTP_METADATA *v17; // rcx
  int v18; // [rsp+40h] [rbp-C0h] BYREF
  struct FTP_METADATA *v19; // [rsp+48h] [rbp-B8h] BYREF
  int v20; // [rsp+50h] [rbp-B0h] BYREF
  int v21; // [rsp+54h] [rbp-ACh] BYREF
  unsigned int v22; // [rsp+58h] [rbp-A8h] BYREF
  void *Block; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int16 *v24; // [rsp+68h] [rbp-98h] BYREF
  _BYTE v25[56]; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v26[56]; // [rsp+A8h] [rbp-58h] BYREF
  _BYTE v27[64]; // [rsp+E0h] [rbp-20h] BYREF
  unsigned __int16 v28[64]; // [rsp+120h] [rbp+20h] BYREF

  memset_0(v28, 0, sizeof(v28));
  STRU::STRU((STRU *)v27, v28, 0x40u);
  Block = 0;
  v19 = 0;
  v22 = 0;
  v24 = 0;
  STRU::STRU(v26);
  v18 = 0;
  v21 = 0;
  Metadata = FTP_METADATA::GetMetadata(
               &WideCharStr,
               &WideCharStr,
               0,
               &v22,
               (const unsigned __int16 **)&v24,
               (struct STRU *)v26,
               &v19);
  if ( Metadata < 0 )
  {
    if ( (g_dwDebugFlags & 3) != 0 )
      PuDbgPrint(
        g_pDebug,
        "inetsrv\\iis\\iisrearc\\ftp\\server\\core\\ftp_site_manager.cxx",
        1069,
        "FTP_SITE_MANAGER::OnNewConnection",
        "GetMetadata(%S) failed. Error = 0x%x. Info = %S\n",
        L"/",
        Metadata,
        v24);
    goto LABEL_30;
  }
  v4 = v19;
  STRU::STRU(v25);
  v20 = 0;
  v5 = IP_RESTRICTION_LIST::Check((struct FTP_METADATA *)((char *)v4 + 640), a1 + 28, (struct STRU *)v25, &v20, &v21);
  v6 = 0;
  if ( v5 >= 0 )
  {
    if ( v20 )
    {
      v6 = 0;
    }
    else
    {
      v18 = 1;
      v6 = 1;
    }
  }
  STRU::~STRU(v25);
  if ( v5 >= 0 )
  {
    if ( v6 )
    {
      FTP_SITE_MANAGER::LogIpRestriction(
        (SOCKADDR *)&a1[28],
        (SOCKADDR *)&a1[20],
        -2147023660,
        4u,
        L"IP restriction rules denied the access.");
      goto LABEL_30;
    }
    if ( v21 )
      goto LABEL_18;
    v7 = (DYNAMIC_IP_RESTRICTION *)*((_QWORD *)v19 + 117);
    if ( !**((_DWORD **)v7 + 2) )
      goto LABEL_18;
    if ( (int)DYNAMIC_IP_RESTRICTION::CheckOnNewConnection(v7, a1 + 28, &v18) >= 0 )
    {
      if ( !v18 )
        goto LABEL_18;
      v8 = *(_DWORD *)(*((_QWORD *)v19 + 117) + 8LL);
      v9 = L"Dynamic IP restriction rules denied the access(Log-only mode).";
      if ( !v8 )
        v9 = L"Dynamic IP restriction rules denied the access.";
      FTP_SITE_MANAGER::LogIpRestriction((SOCKADDR *)&a1[28], (SOCKADDR *)&a1[20], -2147023660, (v8 != 0) + 56, v9);
      if ( *(_DWORD *)(*((_QWORD *)v19 + 117) + 8LL) )
      {
LABEL_18:
        v10 = (FTP_SITE_MANAGER *)(**(__int64 (__fastcall ***)(FTP_SERVERP *))g_pFtpServer)(g_pFtpServer);
        v11 = FTP_SITE_MANAGER::LookupSite(v10, (struct sockaddr *)&a1[20], 0, (struct FTP_SITE **)&Block);
        v12 = (volatile signed __int32 *)Block;
        if ( v11 >= 0 )
        {
          v13 = ALLOC_CACHE_HANDLER::Alloc((ALLOC_CACHE_HANDLER *)FTP_SESSION::sm_pAllocHandler);
          Block = v13;
          v14 = v13 ? FTP_SESSION::FTP_SESSION((FTP_SESSION *)v13) : 0LL;
          if ( v14 )
          {
            if ( (*(int (__fastcall **)(FTP_SESSION *, volatile signed __int32 *, const struct sockaddr *))(*(_QWORD *)v14 + 16LL))(
                   v14,
                   v12,
                   a1) >= 0 )
            {
              a1 = 0;
              v15 = (*(__int64 (__fastcall **)(FTP_SESSION *))(*(_QWORD *)v14 + 24LL))(v14);
              v16 = *(_QWORD *)v14;
              if ( v15 >= 0 )
              {
                (*(void (__fastcall **)(FTP_SESSION *))(v16 + 8))(v14);
                (*(void (__fastcall **)(FTP_SERVERP *, __int64, __int64))(*(_QWORD *)g_pFtpServer + 240LL))(
                  g_pFtpServer,
                  9001,
                  1);
                goto LABEL_27;
              }
              (*(void (__fastcall **)(FTP_SESSION *, _QWORD, _QWORD, const OLECHAR *, int))(v16 + 32))(
                v14,
                (unsigned int)v15,
                0,
                &WideCharStr,
                1);
            }
            (*(void (__fastcall **)(FTP_SESSION *))(*(_QWORD *)v14 + 8LL))(v14);
          }
        }
LABEL_27:
        if ( v12 && _InterlockedExchangeAdd(v12 + 44, 0xFFFFFFFF) == 1 )
        {
          FTP_SITE::~FTP_SITE((FTP_SITE *)v12);
          operator delete((void *)v12);
        }
      }
    }
  }
LABEL_30:
  v17 = v19;
  if ( v19 )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)v19 + 3, 0xFFFFFFFF) == 1 && v17 )
      (**(void (__fastcall ***)(struct FTP_METADATA *, __int64))v17)(v17, 1);
    v19 = 0;
  }
  if ( a1 )
    (**(void (__fastcall ***)(const struct sockaddr *, __int64))&a1->sa_family)(a1, 1);
  STRU::~STRU(v26);
  STRU::~STRU(v27);
}

```

## disassembly

```asm
0x18000c420  mov     [rsp-8+arg_8], rbx
0x18000c425  mov     [rsp-8+arg_10], rsi
0x18000c42a  push    rbp
0x18000c42b  push    rdi
0x18000c42c  push    r12
0x18000c42e  push    r14
0x18000c430  push    r15
0x18000c432  lea     rbp, [rsp-0B0h]
0x18000c43a  sub     rsp, 1B0h
0x18000c441  mov     rax, cs:__security_cookie
0x18000c448  xor     rax, rsp
0x18000c44b  mov     [rbp+0D0h+var_30], rax
0x18000c452  mov     rsi, rcx
0x18000c455  xor     edx, edx; Val
0x18000c457  mov     r8d, 80h; Size
0x18000c45d  lea     rcx, [rbp+0D0h+var_B0]; void *
0x18000c461  call    memset_0
0x18000c466  mov     r8d, 40h ; '@'
0x18000c46c  lea     rdx, [rbp+0D0h+var_B0]
0x18000c470  lea     rcx, [rbp+0D0h+var_F0]
0x18000c474  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x18000c47a  nop
0x18000c47b  xor     r15d, r15d
0x18000c47e  mov     [rsp+1D0h+Block], r15
0x18000c483  mov     [rsp+1D0h+var_188], r15
0x18000c488  mov     [rsp+1D0h+var_178], r15d
0x18000c48d  mov     [rsp+1D0h+var_168], r15
0x18000c492  lea     rcx, [rbp+0D0h+var_128]
0x18000c496  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x18000c49c  nop
0x18000c49d  mov     [rsp+1D0h+var_190], r15d
0x18000c4a2  mov     [rsp+1D0h+var_17C], r15d
0x18000c4a7  lea     rax, [rsp+1D0h+var_188]
0x18000c4ac  mov     [rsp+1D0h+var_1A0], rax; struct FTP_METADATA **
0x18000c4b1  lea     rax, [rbp+0D0h+var_128]
0x18000c4b5  mov     [rsp+1D0h+var_1A8], rax; struct STRU *
0x18000c4ba  lea     rax, [rsp+1D0h+var_168]
0x18000c4bf  mov     [rsp+1D0h+var_1B0], rax; unsigned __int16 **
0x18000c4c4  lea     r9, [rsp+1D0h+var_178]; unsigned int *
0x18000c4c9  xor     r8d, r8d; struct _GUID *
0x18000c4cc  lea     rdx, WideCharStr; unsigned __int16 *
0x18000c4d3  lea     rcx, WideCharStr; unsigned __int16 *
0x18000c4da  call    ?GetMetadata@FTP_METADATA@@SAJPEBG0PEBU_GUID@@PEAKPEAPEBGPEAVSTRU@@PEAPEAV1@@Z; FTP_METADATA::GetMetadata(ushort const *,ushort const *,_GUID const *,ulong *,ushort const * *,STRU *,FTP_METADATA * *)
0x18000c4df  lea     r12d, [r15+1]
0x18000c4e3  test    eax, eax
0x18000c4e5  jns     short loc_18000C540
0x18000c4e7  test    byte ptr cs:g_dwDebugFlags, 3
0x18000c4ee  jz      loc_18000C766
0x18000c4f4  mov     rcx, [rsp+1D0h+var_168]
0x18000c4f9  mov     [rsp+1D0h+var_198], rcx
0x18000c4fe  mov     dword ptr [rsp+1D0h+var_1A0], eax
0x18000c502  lea     rax, asc_18004BD14; "/"
0x18000c509  mov     [rsp+1D0h+var_1A8], rax
0x18000c50e  lea     rax, aGetmetadataSFa; "GetMetadata(%S) failed. Error = 0x%x. I"...
0x18000c515  mov     [rsp+1D0h+var_1B0], rax
0x18000c51a  lea     r9, aFtpSiteManager_1; "FTP_SITE_MANAGER::OnNewConnection"
0x18000c521  mov     r8d, 42Dh
0x18000c527  lea     rdx, aInetsrvIisIisr_18; "inetsrv\\iis\\iisrearc\\ftp\\server\\co"...
0x18000c52e  mov     rcx, cs:g_pDebug
0x18000c535  call    cs:__imp_PuDbgPrint
0x18000c53b  jmp     loc_18000C766
0x18000c540  mov     rbx, [rsp+1D0h+var_188]
0x18000c545  lea     rdi, [rsi+1C0h]
0x18000c54c  lea     rcx, [rsp+1D0h+var_160]
0x18000c551  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x18000c557  nop
0x18000c558  mov     [rsp+1D0h+var_180], r15d
0x18000c55d  lea     rax, [rsp+1D0h+var_17C]
0x18000c562  mov     [rsp+1D0h+var_1B0], rax; int *
0x18000c567  lea     r9, [rsp+1D0h+var_180]; int *
0x18000c56c  lea     r8, [rsp+1D0h+var_160]; struct STRU *
0x18000c571  mov     rdx, rdi; struct sockaddr *
0x18000c574  lea     rcx, [rbx+280h]; this
0x18000c57b  call    ?Check@IP_RESTRICTION_LIST@@QEAAJPEBUsockaddr@@PEAVSTRU@@PEAH2@Z; IP_RESTRICTION_LIST::Check(sockaddr const *,STRU *,int *,int *)
0x18000c580  mov     r14d, eax
0x18000c583  mov     ebx, r15d
0x18000c586  test    eax, eax
0x18000c588  js      short loc_18000C59E
0x18000c58a  cmp     [rsp+1D0h+var_180], r15d
0x18000c58f  jnz     short loc_18000C59B
0x18000c591  mov     [rsp+1D0h+var_190], r12d
0x18000c596  mov     ebx, r12d
0x18000c599  jmp     short loc_18000C59E
0x18000c59b  mov     ebx, r15d
0x18000c59e  lea     rcx, [rsp+1D0h+var_160]
0x18000c5a3  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x18000c5a9  test    r14d, r14d
0x18000c5ac  js      loc_18000C766
0x18000c5b2  lea     r14, [rsi+140h]
0x18000c5b9  test    ebx, ebx
0x18000c5bb  jz      short loc_18000C5E5
0x18000c5bd  lea     rax, aIpRestrictionR; "IP restriction rules denied the access."
0x18000c5c4  mov     [rsp+1D0h+var_1B0], rax; unsigned __int16 *
0x18000c5c9  mov     r9d, 4; unsigned int
0x18000c5cf  mov     r8d, 800704D4h; int
0x18000c5d5  mov     rdx, r14; SOCKADDR *
0x18000c5d8  mov     rcx, rdi; pSockaddr
0x18000c5db  call    ?LogIpRestriction@FTP_SITE_MANAGER@@SAJPEBUsockaddr@@0JKPEBG@Z; FTP_SITE_MANAGER::LogIpRestriction(sockaddr const *,sockaddr const *,long,ulong,ushort const *)
0x18000c5e0  jmp     loc_18000C766
0x18000c5e5  cmp     [rsp+1D0h+var_17C], r15d
0x18000c5ea  jnz     loc_18000C67C
0x18000c5f0  mov     rax, [rsp+1D0h+var_188]
0x18000c5f5  mov     rcx, [rax+3A8h]; this
0x18000c5fc  mov     rax, [rcx+10h]
0x18000c600  cmp     [rax], r15d
0x18000c603  jz      short loc_18000C67C
0x18000c605  lea     r8, [rsp+1D0h+var_190]; int *
0x18000c60a  mov     rdx, rdi; struct sockaddr *
0x18000c60d  call    ?CheckOnNewConnection@DYNAMIC_IP_RESTRICTION@@QEBAJPEBUsockaddr@@PEAH@Z; DYNAMIC_IP_RESTRICTION::CheckOnNewConnection(sockaddr const *,int *)
0x18000c612  test    eax, eax
0x18000c614  js      loc_18000C766
0x18000c61a  cmp     [rsp+1D0h+var_190], r15d
0x18000c61f  jz      short loc_18000C67C
0x18000c621  mov     rax, [rsp+1D0h+var_188]
0x18000c626  mov     rcx, [rax+3A8h]
0x18000c62d  mov     eax, [rcx+8]
0x18000c630  lea     rdx, aDynamicIpRestr; "Dynamic IP restriction rules denied the"...
0x18000c637  lea     rcx, aDynamicIpRestr_3; "Dynamic IP restriction rules denied the"...
0x18000c63e  test    eax, eax
0x18000c640  cmovz   rcx, rdx
0x18000c644  neg     eax
0x18000c646  sbb     r9d, r9d
0x18000c649  neg     r9d
0x18000c64c  add     r9d, 38h ; '8'; unsigned int
0x18000c650  mov     [rsp+1D0h+var_1B0], rcx; unsigned __int16 *
0x18000c655  mov     r8d, 800704D4h; int
0x18000c65b  mov     rdx, r14; SOCKADDR *
0x18000c65e  mov     rcx, rdi; pSockaddr
0x18000c661  call    ?LogIpRestriction@FTP_SITE_MANAGER@@SAJPEBUsockaddr@@0JKPEBG@Z; FTP_SITE_MANAGER::LogIpRestriction(sockaddr const *,sockaddr const *,long,ulong,ushort const *)
0x18000c666  mov     rax, [rsp+1D0h+var_188]
0x18000c66b  mov     rcx, [rax+3A8h]
0x18000c672  cmp     [rcx+8], r15d
0x18000c676  jz      loc_18000C766
0x18000c67c  mov     rcx, cs:?g_pFtpServer@@3PEAVFTP_SERVER@@EA; FTP_SERVER * g_pFtpServer
0x18000c683  mov     rax, [rcx]
0x18000c686  mov     rax, [rax]
0x18000c689  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c68e  lea     r9, [rsp+1D0h+Block]; struct FTP_SITE **
0x18000c693  xor     r8d, r8d; unsigned __int16 *
0x18000c696  mov     rdx, r14; struct sockaddr *
0x18000c699  mov     rcx, rax; this
0x18000c69c  call    ?LookupSite@FTP_SITE_MANAGER@@QEAAJPEBUsockaddr@@PEBGPEAPEAVFTP_SITE@@@Z; FTP_SITE_MANAGER::LookupSite(sockaddr const *,ushort const *,FTP_SITE * *)
0x18000c6a1  mov     rdi, [rsp+1D0h+Block]
0x18000c6a6  test    eax, eax
0x18000c6a8  js      loc_18000C73C
0x18000c6ae  mov     rcx, cs:?sm_pAllocHandler@FTP_SESSION@@0PEAVALLOC_CACHE_HANDLER@@EA; ALLOC_CACHE_HANDLER * FTP_SESSION::sm_pAllocHandler
0x18000c6b5  call    cs:__imp_?Alloc@ALLOC_CACHE_HANDLER@@QEAAPEAXXZ; ALLOC_CACHE_HANDLER::Alloc(void)
0x18000c6bb  mov     [rsp+1D0h+Block], rax
0x18000c6c0  test    rax, rax
0x18000c6c3  jz      short loc_18000C6D2
0x18000c6c5  mov     rcx, rax; this
0x18000c6c8  call    ??0FTP_SESSION@@QEAA@XZ; FTP_SESSION::FTP_SESSION(void)
0x18000c6cd  mov     rbx, rax
0x18000c6d0  jmp     short loc_18000C6D5
0x18000c6d2  mov     rbx, r15
0x18000c6d5  test    rbx, rbx
0x18000c6d8  jz      short loc_18000C73C
0x18000c6da  mov     rax, [rbx]
0x18000c6dd  mov     r8, rsi
0x18000c6e0  mov     rdx, rdi
0x18000c6e3  mov     rcx, rbx
0x18000c6e6  mov     rax, [rax+10h]
0x18000c6ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c6ef  test    eax, eax
0x18000c6f1  js      short loc_18000C72D
0x18000c6f3  mov     rsi, r15
0x18000c6f6  mov     rax, [rbx]
0x18000c6f9  mov     rcx, rbx
0x18000c6fc  mov     rax, [rax+18h]
0x18000c700  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c705  mov     r10, [rbx]
0x18000c708  mov     rcx, rbx
0x18000c70b  test    eax, eax
0x18000c70d  jns     loc_18000C7EC
0x18000c713  mov     dword ptr [rsp+1D0h+var_1B0], r12d
0x18000c718  lea     r9, WideCharStr
0x18000c71f  xor     r8d, r8d
0x18000c722  mov     edx, eax
0x18000c724  mov     rax, [r10+20h]
0x18000c728  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c72d  mov     rax, [rbx]
0x18000c730  mov     rcx, rbx
0x18000c733  mov     rax, [rax+8]
0x18000c737  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c73c  test    rdi, rdi
0x18000c73f  jz      short loc_18000C766
0x18000c741  or      eax, 0FFFFFFFFh
0x18000c744  lock xadd [rdi+0B0h], eax
0x18000c74c  cmp     eax, 1
0x18000c74f  jnz     short loc_18000C766
0x18000c751  test    rdi, rdi
0x18000c754  jz      short loc_18000C766
0x18000c756  mov     rcx, rdi; this
0x18000c759  call    ??1FTP_SITE@@AEAA@XZ; FTP_SITE::~FTP_SITE(void)
0x18000c75e  mov     rcx, rdi; Block
0x18000c761  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000c766  mov     rcx, [rsp+1D0h+var_188]
0x18000c76b  test    rcx, rcx
0x18000c76e  jz      short loc_18000C795
0x18000c770  or      eax, 0FFFFFFFFh
0x18000c773  lock xadd [rcx+0Ch], eax
0x18000c778  cmp     eax, 1
0x18000c77b  jnz     short loc_18000C790
0x18000c77d  test    rcx, rcx
0x18000c780  jz      short loc_18000C790
0x18000c782  mov     rax, [rcx]
0x18000c785  mov     edx, r12d
0x18000c788  mov     rax, [rax]
0x18000c78b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c790  mov     [rsp+1D0h+var_188], r15
0x18000c795  test    rsi, rsi
0x18000c798  jz      short loc_18000C7AC
0x18000c79a  mov     rax, [rsi]
0x18000c79d  mov     edx, r12d
0x18000c7a0  mov     rcx, rsi
0x18000c7a3  mov     rax, [rax]
0x18000c7a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c7ab  nop
0x18000c7ac  lea     rcx, [rbp+0D0h+var_128]
0x18000c7b0  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x18000c7b6  nop
0x18000c7b7  lea     rcx, [rbp+0D0h+var_F0]
0x18000c7bb  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x18000c7c1  mov     rcx, [rbp+0D0h+var_30]
0x18000c7c8  xor     rcx, rsp; StackCookie
0x18000c7cb  call    __security_check_cookie
0x18000c7d0  lea     r11, [rsp+1D0h+var_20]
0x18000c7d8  mov     rbx, [r11+38h]
0x18000c7dc  mov     rsi, [r11+40h]
0x18000c7e0  mov     rsp, r11
0x18000c7e3  pop     r15
0x18000c7e5  pop     r14
0x18000c7e7  pop     r12
0x18000c7e9  pop     rdi
0x18000c7ea  pop     rbp
0x18000c7eb  retn
0x18000c7ec  mov     rax, [r10+8]
0x18000c7f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c7f5  mov     rcx, cs:?g_pFtpServer@@3PEAVFTP_SERVER@@EA; FTP_SERVER * g_pFtpServer
0x18000c7fc  mov     rax, [rcx]
0x18000c7ff  mov     r8d, r12d
0x18000c802  mov     edx, 2329h
0x18000c807  mov     rax, [rax+0F0h]
0x18000c80e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c813  jmp     loc_18000C73C
```
