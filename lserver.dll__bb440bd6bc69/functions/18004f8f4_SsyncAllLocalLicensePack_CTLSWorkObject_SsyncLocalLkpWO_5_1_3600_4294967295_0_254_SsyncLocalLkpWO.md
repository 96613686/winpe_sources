# _SsyncAllLocalLicensePack(CTLSWorkObject<__SsyncLocalLkpWO,5,1,3600,4294967295,0,254> *,__SsyncLocalLkpWO *)

- ea: `0x18004f8f4`
- end: `0x18004fba0`
- name: `?_SsyncAllLocalLicensePack@@YAKPEAV?$CTLSWorkObject@U__SsyncLocalLkpWO@@$04$00$0OBA@$0PPPPPPPP@$0A@$0PO@@@PEAU__SsyncLocalLkpWO@@@Z`
- size: `684`
- prototype: ``
- caller_count: `1`
- callee_count: `17`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18004e610`

## callees

- `0x18000bb98`
- `0x18000cff0`
- `0x180024b70`
- `0x180036390`
- `0x1800364bc`
- `0x1800364d0`
- `0x18004ea48`
- `0x18004f324`
- `0x18004f73c`
- `0x18004f8f4`
- `0x18004fdc4`
- `0x1800662a0`
- `0x18007da44`
- `0x18007eea0`
- `0x1800a0fb0`
- `0x1800a1070`
- `0x1800a5010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18004fb45`
- `msvcrt!??3@YAXPEAX@Z` at `0x18004fb45`
- `KERNEL32!CompareFileTime` at `0x18004fa07`
- `KERNEL32!CompareFileTime` at `0x18004fa07`
- `KERNEL32!SetLastError` at `0x18004f97b`
- `KERNEL32!SetLastError` at `0x18004f97b`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall _SsyncAllLocalLicensePack(__int64 a1, __int64 a2)
{
  __int64 *v4; // rax
  struct IRdlsDBConnection *v5; // rbx
  unsigned int v6; // ebx
  __int64 v7; // rcx
  struct __LicensePack *v8; // r14
  struct __LicensePack *v9; // rdi
  __int64 v10; // rax
  struct __LicensePack *v11; // rbx
  unsigned int v13; // [rsp+30h] [rbp-D0h] BYREF
  struct __LicensePack *v14[2]; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v15; // [rsp+48h] [rbp-B8h]
  _BYTE v16[8]; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v17; // [rsp+58h] [rbp-A8h]
  __int64 v18; // [rsp+78h] [rbp-88h]
  int v19; // [rsp+80h] [rbp-80h]
  _BYTE v20[8]; // [rsp+EA0h] [rbp+DA0h] BYREF
  FILETIME FileTime1; // [rsp+EA8h] [rbp+DA8h] BYREF
  __int64 v22; // [rsp+EC8h] [rbp+DC8h]
  int v23; // [rsp+ED0h] [rbp+DD0h]
  unsigned __int16 v24[512]; // [rsp+ED4h] [rbp+DD4h] BYREF
  unsigned __int16 v25[1294]; // [rsp+12D4h] [rbp+11D4h] BYREF
  int v26[4]; // [rsp+1CF0h] [rbp+1BF0h] BYREF
  __int128 v27; // [rsp+1D00h] [rbp+1C00h]
  __int64 v28; // [rsp+1D10h] [rbp+1C10h]

  v17 = 0;
  v18 = 0;
  v19 = 0;
  FileTime1 = 0;
  v22 = 0;
  v23 = 0;
  *(_OWORD *)v14 = 0;
  v15 = 0;
  v4 = (__int64 *)CRdlsDBManager::AcquireRdlsDBConnection((CRdlsDBManager *)g_RdlsDBManager);
  v5 = (struct IRdlsDBConnection *)v4;
  if ( v4 )
  {
    if ( !(unsigned int)TLSDBKeyPackEnumBegin(v4, 0, 0, 0, 1) )
    {
      while ( !(unsigned int)TLSDBKeyPackEnumNext(v5, v20) )
      {
        v10 = (**(__int64 (__fastcall ***)(__int64))a1)(a1);
        if ( CompareFileTime(&FileTime1, (const FILETIME *)(v10 + 1428)) >= 0 )
        {
          if ( (unsigned int)CWorkObject::IsWorkManagerShuttingDown((CWorkObject *)(a1
                                                                                  + *(int *)(*(_QWORD *)(a1 + 8) + 4LL)
                                                                                  + 8LL)) == 1 )
            break;
          if ( (unsigned int)IsLicensePackRepl(v20) )
          {
            StringCchCopyW(v24, 0x100u, (const unsigned __int16 *)(a2 + 12));
            StringCchCopyW(v25, 0x100u, (const unsigned __int16 *)(a2 + 526));
            std::vector<__LicensePack>::push_back(v14, v20);
          }
        }
      }
      TLSDBKeyPackEnumEnd(v5);
    }
    CRdlsDBManager::ReleaseRdlsDBConnection((CRdlsDBManager *)g_RdlsDBManager, v5);
    v9 = v14[0];
    v11 = v14[0];
    v8 = v14[1];
    while ( v11 != v8
         && (unsigned int)CWorkObject::IsWorkManagerShuttingDown((CWorkObject *)(a1
                                                                               + *(int *)(*(_QWORD *)(a1 + 8) + 4LL)
                                                                               + 8LL)) != 1 )
    {
      *(_OWORD *)v26 = 0;
      v27 = 0;
      v28 = 0;
      v13 = *(_DWORD *)(a2 + 1044);
      _AnnounceLicensePackToServers(
        (struct CWorkObject *)(a1 + *(int *)(*(_QWORD *)(a1 + 8) + 4LL) + 8LL),
        v11,
        &v13,
        (unsigned __int16 (*const)[17])(a2 + 1048),
        v26);
      v11 = (struct __LicensePack *)((char *)v11 + 3664);
    }
    v6 = 0;
  }
  else
  {
    v6 = 7;
    SetLastError(7u);
    CrimsonHelper::RaiseEventInternal((CrimsonHelper *)CrimsonHelper::s_instance, &TLS_I_SSYNCLKP_SERVER_BUSY, 0, 0);
    v8 = v14[1];
    v9 = v14[0];
  }
  if ( v9 )
  {
    std::vector<__LicensePack>::_Destroy(v7, v9, v8);
    operator delete(v9);
    *(_OWORD *)v14 = 0;
    v15 = 0;
  }
  __LicensePack::~__LicensePack((__LicensePack *)v20);
  __LicensePack::~__LicensePack((__LicensePack *)v16);
  return v6;
}

```

## disassembly

```asm
0x18004f8f4  mov     [rsp-8+arg_10], rbx
0x18004f8f9  push    rbp
0x18004f8fa  push    rsi
0x18004f8fb  push    rdi
0x18004f8fc  push    r14
0x18004f8fe  push    r15
0x18004f900  lea     rbp, [rsp-1C20h]
0x18004f908  mov     eax, 1D20h
0x18004f90d  call    _alloca_probe
0x18004f912  sub     rsp, rax
0x18004f915  mov     rax, cs:__security_cookie
0x18004f91c  xor     rax, rsp
0x18004f91f  mov     [rbp+1C40h+var_28], rax
0x18004f926  mov     r15, rdx
0x18004f929  mov     rsi, rcx
0x18004f92c  and     [rsp+1D40h+var_1CE8], 0
0x18004f932  and     [rsp+1D40h+var_1CC8], 0
0x18004f938  and     [rbp+1C40h+var_1CC0], 0
0x18004f93c  and     qword ptr [rbp+1C40h+FileTime1.dwLowDateTime], 0
0x18004f944  and     [rbp+1C40h+var_E78], 0
0x18004f94c  and     [rbp+1C40h+var_E70], 0
0x18004f953  xorps   xmm0, xmm0
0x18004f956  movdqu  xmmword ptr [rsp+1D40h+var_1D08], xmm0
0x18004f95c  and     [rsp+1D40h+var_1CF8], 0
0x18004f962  mov     rcx, cs:?g_RdlsDBManager@@3PEAVCRdlsDBManager@@EA; this
0x18004f969  call    ?AcquireRdlsDBConnection@CRdlsDBManager@@QEAAPEAVIRdlsDBConnection@@XZ; CRdlsDBManager::AcquireRdlsDBConnection(void)
0x18004f96e  mov     rbx, rax
0x18004f971  test    rax, rax
0x18004f974  jnz     short loc_18004F9AF
0x18004f976  lea     ebx, [rax+7]
0x18004f979  mov     ecx, ebx; dwErrCode
0x18004f97b  call    cs:__imp_SetLastError
0x18004f982  nop     dword ptr [rax+rax+00h]
0x18004f987  xor     r9d, r9d; struct _EVENT_DATA_DESCRIPTOR *
0x18004f98a  xor     r8d, r8d; unsigned int
0x18004f98d  lea     rdx, TLS_I_SSYNCLKP_SERVER_BUSY; struct _EVENT_DESCRIPTOR *
0x18004f994  lea     rcx, ?s_instance@CrimsonHelper@@0V1@A; this
0x18004f99b  call    ?RaiseEventInternal@CrimsonHelper@@AEAAKAEBU_EVENT_DESCRIPTOR@@KQEAU_EVENT_DATA_DESCRIPTOR@@@Z; CrimsonHelper::RaiseEventInternal(_EVENT_DESCRIPTOR const &,ulong,_EVENT_DATA_DESCRIPTOR * const)
0x18004f9a0  mov     r14, [rsp+1D40h+var_1D08+8]
0x18004f9a5  mov     rdi, [rsp+1D40h+var_1D08]
0x18004f9aa  jmp     loc_18004FB32
0x18004f9af  mov     dword ptr [rsp+1D40h+var_1D20], 1
0x18004f9b7  xor     r9d, r9d
0x18004f9ba  xor     r8d, r8d
0x18004f9bd  xor     edx, edx
0x18004f9bf  mov     rcx, rbx
0x18004f9c2  call    TLSDBKeyPackEnumBegin
0x18004f9c7  test    eax, eax
0x18004f9c9  jnz     loc_18004FA99
0x18004f9cf  lea     rdx, [rbp+1C40h+var_EA0]
0x18004f9d6  mov     rcx, rbx
0x18004f9d9  call    TLSDBKeyPackEnumNext
0x18004f9de  test    eax, eax
0x18004f9e0  jnz     loc_18004FA91
0x18004f9e6  mov     edi, 100h
0x18004f9eb  mov     rax, [rsi]
0x18004f9ee  mov     rcx, rsi
0x18004f9f1  mov     rax, [rax]
0x18004f9f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f9f9  lea     rdx, [rax+594h]; lpFileTime2
0x18004fa00  lea     rcx, [rbp+1C40h+FileTime1]; lpFileTime1
0x18004fa07  call    cs:__imp_CompareFileTime
0x18004fa0e  nop     dword ptr [rax+rax+00h]
0x18004fa13  test    eax, eax
0x18004fa15  js      short loc_18004FA7A
0x18004fa17  mov     rax, [rsi+8]
0x18004fa1b  movsxd  rcx, dword ptr [rax+4]
0x18004fa1f  add     rcx, 8
0x18004fa23  add     rcx, rsi; this
0x18004fa26  call    ?IsWorkManagerShuttingDown@CWorkObject@@QEAAHXZ; CWorkObject::IsWorkManagerShuttingDown(void)
0x18004fa2b  cmp     eax, 1
0x18004fa2e  jz      short loc_18004FA91
0x18004fa30  lea     rcx, [rbp+1C40h+var_EA0]
0x18004fa37  call    IsLicensePackRepl
0x18004fa3c  test    eax, eax
0x18004fa3e  jz      short loc_18004FA7A
0x18004fa40  lea     r8, [r15+0Ch]; unsigned __int16 *
0x18004fa44  mov     rdx, rdi; unsigned __int64
0x18004fa47  lea     rcx, [rbp+1C40h+var_E6C]; unsigned __int16 *
0x18004fa4e  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18004fa53  lea     r8, [r15+20Eh]; unsigned __int16 *
0x18004fa5a  mov     rdx, rdi; unsigned __int64
0x18004fa5d  lea     rcx, [rbp+1C40h+var_A6C]; unsigned __int16 *
0x18004fa64  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18004fa69  lea     rdx, [rbp+1C40h+var_EA0]
0x18004fa70  lea     rcx, [rsp+1D40h+var_1D08]
0x18004fa75  call    ?push_back@?$vector@U__LicensePack@@V?$allocator@U__LicensePack@@@std@@@std@@QEAAXAEBU__LicensePack@@@Z; std::vector<__LicensePack>::push_back(__LicensePack const &)
0x18004fa7a  lea     rdx, [rbp+1C40h+var_EA0]
0x18004fa81  mov     rcx, rbx
0x18004fa84  call    TLSDBKeyPackEnumNext
0x18004fa89  test    eax, eax
0x18004fa8b  jz      loc_18004F9EB
0x18004fa91  mov     rcx, rbx
0x18004fa94  call    TLSDBKeyPackEnumEnd
0x18004fa99  mov     rdx, rbx; struct IRdlsDBConnection *
0x18004fa9c  mov     rcx, cs:?g_RdlsDBManager@@3PEAVCRdlsDBManager@@EA; this
0x18004faa3  call    ?ReleaseRdlsDBConnection@CRdlsDBManager@@QEAAKPEAVIRdlsDBConnection@@@Z; CRdlsDBManager::ReleaseRdlsDBConnection(IRdlsDBConnection *)
0x18004faa8  mov     rdi, [rsp+1D40h+var_1D08]
0x18004faad  mov     rbx, rdi
0x18004fab0  mov     r14, [rsp+1D40h+var_1D08+8]
0x18004fab5  cmp     rbx, r14
0x18004fab8  jz      short loc_18004FB30
0x18004faba  mov     rax, [rsi+8]
0x18004fabe  movsxd  rcx, dword ptr [rax+4]
0x18004fac2  add     rcx, 8
0x18004fac6  add     rcx, rsi; this
0x18004fac9  call    ?IsWorkManagerShuttingDown@CWorkObject@@QEAAHXZ; CWorkObject::IsWorkManagerShuttingDown(void)
0x18004face  cmp     eax, 1
0x18004fad1  jz      short loc_18004FB30
0x18004fad3  xorps   xmm0, xmm0
0x18004fad6  xor     eax, eax
0x18004fad8  movups  xmmword ptr [rbp+1C40h+var_50], xmm0
0x18004fadf  movups  [rbp+1C40h+var_40], xmm0
0x18004fae6  mov     [rbp+1C40h+var_30], rax
0x18004faed  mov     eax, [r15+414h]
0x18004faf4  mov     [rsp+1D40h+var_1D10], eax
0x18004faf8  lea     r9, [r15+418h]; unsigned __int16 (*)[17]
0x18004faff  mov     rax, [rsi+8]
0x18004fb03  movsxd  rcx, dword ptr [rax+4]
0x18004fb07  add     rcx, 8
0x18004fb0b  add     rcx, rsi; struct CWorkObject *
0x18004fb0e  lea     rax, [rbp+1C40h+var_50]
0x18004fb15  mov     [rsp+1D40h+var_1D20], rax; int *
0x18004fb1a  lea     r8, [rsp+1D40h+var_1D10]; unsigned int *
0x18004fb1f  mov     rdx, rbx; struct __LicensePack *
0x18004fb22  call    ?_AnnounceLicensePackToServers@@YAXPEAVCWorkObject@@PEAU__LicensePack@@PEAKQEAY0BB@GPEAH@Z; _AnnounceLicensePackToServers(CWorkObject *,__LicensePack *,ulong *,ushort (* const)[17],int *)
0x18004fb27  add     rbx, 0E50h
0x18004fb2e  jmp     short loc_18004FAB5
0x18004fb30  xor     ebx, ebx
0x18004fb32  test    rdi, rdi
0x18004fb35  jz      short loc_18004FB60
0x18004fb37  mov     r8, r14
0x18004fb3a  mov     rdx, rdi
0x18004fb3d  call    ?_Destroy@?$vector@U__LicensePack@@V?$allocator@U__LicensePack@@@std@@@std@@IEAAXPEAU__LicensePack@@0@Z; std::vector<__LicensePack>::_Destroy(__LicensePack *,__LicensePack *)
0x18004fb42  mov     rcx, rdi
0x18004fb45  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18004fb4c  nop     dword ptr [rax+rax+00h]
0x18004fb51  xorps   xmm0, xmm0
0x18004fb54  movdqu  xmmword ptr [rsp+1D40h+var_1D08], xmm0
0x18004fb5a  and     [rsp+1D40h+var_1CF8], 0
0x18004fb60  lea     rcx, [rbp+1C40h+var_EA0]; this
0x18004fb67  call    ??1__LicensePack@@QEAA@XZ; __LicensePack::~__LicensePack(void)
0x18004fb6c  nop
0x18004fb6d  lea     rcx, [rsp+1D40h+var_1CF0]; this
0x18004fb72  call    ??1__LicensePack@@QEAA@XZ; __LicensePack::~__LicensePack(void)
0x18004fb77  mov     eax, ebx
0x18004fb79  mov     rcx, [rbp+1C40h+var_28]
0x18004fb80  xor     rcx, rsp; StackCookie
0x18004fb83  call    __security_check_cookie
0x18004fb88  mov     rbx, [rsp+1D40h+arg_10]
0x18004fb90  add     rsp, 1D20h
0x18004fb97  pop     r15
0x18004fb99  pop     r14
0x18004fb9b  pop     rdi
0x18004fb9c  pop     rsi
0x18004fb9d  pop     rbp
0x18004fb9e  retn
```
