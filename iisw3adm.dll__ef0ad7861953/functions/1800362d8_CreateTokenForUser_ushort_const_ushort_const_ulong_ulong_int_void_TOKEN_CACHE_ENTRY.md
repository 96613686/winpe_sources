# CreateTokenForUser(ushort const *,ushort const *,ulong,ulong,int,void *,TOKEN_CACHE_ENTRY * *)

- ea: `0x1800362d8`
- end: `0x180036583`
- name: `?CreateTokenForUser@@YAJPEBG0KKHPEAXPEAPEAVTOKEN_CACHE_ENTRY@@@Z`
- size: `683`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *, unsigned int, unsigned int, int, void *, struct TOKEN_CACHE_ENTRY **)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180037234`

## callees

- `0x180003e24`
- `0x1800050ac`
- `0x1800362d8`
- `0x18005e468`
- `0x18005f32c`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180036330`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800363c1`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180036330`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800363c1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180036386`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180036386`
- `iisutil!PuDbgPrintError` at `0x180036455`
- `iisutil!PuDbgPrintError` at `0x180036564`
- `iisutil!PuDbgPrintError` at `0x180036455`
- `iisutil!PuDbgPrintError` at `0x180036564`
- `iisutil!?Free@ALLOC_CACHE_HANDLER@@QEAAHPEAX@Z` at `0x180036370`
- `iisutil!?Free@ALLOC_CACHE_HANDLER@@QEAAHPEAX@Z` at `0x180036370`
- `iisutil!?GetLocalGroupSID@CSecurityDispenser@@QEAAKPEAPEAX@Z` at `0x18003640b`
- `iisutil!?GetLocalGroupSID@CSecurityDispenser@@QEAAKPEAPEAX@Z` at `0x18003640b`
- `iisutil!?AdjustTokenForAdministrators@CSecurityDispenser@@QEAAKPEAX@Z` at `0x180036517`
- `iisutil!?AdjustTokenForAdministrators@CSecurityDispenser@@QEAAKPEAX@Z` at `0x180036517`

## string_xrefs

- `0x18003644a`: `servercommon\inetsrv\iis\iisrearc\core\ap\was\dll\web_admin_service.cxx`
- `0x18003642a`: `could not resolve local group SID\n`
- `0x18003643c`: `WEB_ADMIN_SERVICE::GetLocalGroupSid`
- `0x18003655d`: `servercommon\inetsrv\iis\iisrearc\core\ap\was\dll\app_pool_config_store.cxx`
- `0x180036540`: `Could not adjust the users token to allow administrator rights\n`
- `0x18003654c`: `CreateTokenForUser`

## pseudocode

```c
__int64 __fastcall CreateTokenForUser(
        unsigned __int16 *a1,
        unsigned __int16 *a2,
        unsigned int a3,
        unsigned int a4,
        int a5,
        void *a6,
        struct TOKEN_CACHE_ENTRY **a7)
{
  _DWORD *v7; // rsi
  _QWORD *v12; // rax
  int CachedToken2; // edi
  TOKEN_CACHE_ENTRY *v14; // rbx
  _DWORD *v16; // rax
  WEB_ADMIN_SERVICE *v17; // rcx
  void *IisIusrsSid; // rax
  WEB_ADMIN_SERVICE *v19; // rcx
  signed int LocalGroupSID; // eax
  void *v21; // rax
  TOKEN_CACHE *v22; // rcx
  bool v23; // sf
  WEB_ADMIN_SERVICE *v24; // rbx
  void *PrimaryToken; // rax
  int v26; // eax
  unsigned int v27; // [rsp+60h] [rbp-21h] BYREF
  TOKEN_CACHE_ENTRY *v28; // [rsp+68h] [rbp-19h] BYREF
  void *v29; // [rsp+70h] [rbp-11h] BYREF

  v7 = 0;
  v27 = 0;
  v28 = 0;
  if ( !*((_DWORD *)g_pWebAdminService + 412) )
  {
    if ( a5 )
    {
      v12 = LocalAlloc(0x40u, 0x28u);
      v7 = v12;
      if ( !v12 )
      {
LABEL_4:
        CachedToken2 = -2147024888;
        goto LABEL_5;
      }
      *(_DWORD *)v12 = 1;
      v12[1] = a6;
      *((_DWORD *)v12 + 4) = 7;
    }
    else
    {
      v16 = LocalAlloc(0x40u, 0x48u);
      v7 = v16;
      if ( !v16 )
        goto LABEL_4;
      v17 = g_pWebAdminService;
      *v16 = 3;
      IisIusrsSid = WEB_ADMIN_SERVICE::GetIisIusrsSid(v17);
      v19 = g_pWebAdminService;
      *((_QWORD *)v7 + 1) = IisIusrsSid;
      v7[4] = 7;
      v29 = 0;
      LocalGroupSID = CSecurityDispenser::GetLocalGroupSID((WEB_ADMIN_SERVICE *)((char *)v19 + 1416), &v29);
      if ( LocalGroupSID )
      {
        if ( (g_dwDebugFlags & 0xF) != 0 )
        {
          if ( LocalGroupSID > 0 )
            LocalGroupSID = (unsigned __int16)LocalGroupSID | 0x80070000;
          PuDbgPrintError(
            g_pDebug,
            "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\web_admin_service.cxx",
            3109,
            "WEB_ADMIN_SERVICE::GetLocalGroupSid",
            LocalGroupSID,
            "could not resolve local group SID\n");
        }
        v21 = 0;
      }
      else
      {
        v21 = v29;
      }
      *((_QWORD *)v7 + 3) = v21;
      *((_QWORD *)v7 + 5) = a6;
      v7[8] = 7;
      v7[12] = 7;
    }
  }
  v22 = (WEB_ADMIN_SERVICE *)((char *)g_pWebAdminService + 1240);
  *a7 = 0;
  CachedToken2 = TOKEN_CACHE::GetCachedToken2(
                   v22,
                   a1,
                   (unsigned __int16 *)&SourceString,
                   a2,
                   a3,
                   a4,
                   0,
                   0,
                   &v28,
                   &v27,
                   (struct _TOKEN_GROUPS *)v7);
  if ( CachedToken2 >= 0 )
  {
    if ( v28 )
    {
      v24 = g_pWebAdminService;
      PrimaryToken = TOKEN_CACHE_ENTRY::QueryPrimaryToken(v28);
      v26 = CSecurityDispenser::AdjustTokenForAdministrators((WEB_ADMIN_SERVICE *)((char *)v24 + 1416), PrimaryToken);
      if ( !v26 )
      {
        *a7 = v28;
        goto LABEL_10;
      }
      if ( v26 > 0 )
        CachedToken2 = (unsigned __int16)v26 | 0x80070000;
      else
        CachedToken2 = v26;
      if ( (g_dwDebugFlags & 0xF) != 0 )
        PuDbgPrintError(
          g_pDebug,
          "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\app_pool_config_store.cxx",
          1781,
          "CreateTokenForUser",
          CachedToken2,
          "Could not adjust the users token to allow administrator rights\n");
    }
    else
    {
      CachedToken2 = v27;
      v23 = (v27 & 0x80000000) != 0;
      if ( (int)v27 <= 0 )
        goto LABEL_34;
      CachedToken2 = (unsigned __int16)v27 | 0x80070000;
    }
    v23 = CachedToken2 < 0;
LABEL_34:
    if ( !v23 )
      goto LABEL_10;
  }
LABEL_5:
  v14 = v28;
  if ( v28 )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)v28 + 5, 0xFFFFFFFF) == 1 && v14 )
    {
      TOKEN_CACHE_ENTRY::~TOKEN_CACHE_ENTRY(v14);
      ALLOC_CACHE_HANDLER::Free((ALLOC_CACHE_HANDLER *)TOKEN_CACHE_ENTRY::sm_pachTokenCacheEntry, v14);
    }
    v28 = 0;
  }
LABEL_10:
  if ( v7 )
    LocalFree(v7);
  return (unsigned int)CachedToken2;
}

```

## disassembly

```asm
0x1800362d8  push    rbp
0x1800362da  push    rbx
0x1800362db  push    rsi
0x1800362dc  push    rdi
0x1800362dd  push    r12
0x1800362df  push    r13
0x1800362e1  push    r14
0x1800362e3  push    r15
0x1800362e5  lea     rbp, [rsp-7]
0x1800362ea  sub     rsp, 88h
0x1800362f1  mov     rax, cs:?g_pWebAdminService@@3PEAVWEB_ADMIN_SERVICE@@EA; WEB_ADMIN_SERVICE * g_pWebAdminService
0x1800362f8  xor     esi, esi
0x1800362fa  mov     edi, r9d
0x1800362fd  mov     [rbp+3Fh+var_60], 0
0x180036304  mov     r15d, r8d
0x180036307  mov     [rbp+3Fh+var_58], 0
0x18003630f  mov     r12, rdx
0x180036312  mov     r13, rcx
0x180036315  cmp     [rax+670h], esi
0x18003631b  jnz     loc_180036475
0x180036321  lea     ecx, [rsi+40h]; uFlags
0x180036324  cmp     [rbp+3Fh+arg_20], esi
0x180036327  jz      loc_1800363BC
0x18003632d  lea     edx, [rsi+28h]; uBytes
0x180036330  call    cs:__imp_LocalAlloc
0x180036336  mov     rsi, rax
0x180036339  test    rax, rax
0x18003633c  jnz     short loc_1800363A2
0x18003633e  mov     edi, 80070008h
0x180036343  mov     rbx, [rbp+3Fh+var_58]
0x180036347  test    rbx, rbx
0x18003634a  jz      short loc_18003637E
0x18003634c  or      eax, 0FFFFFFFFh
0x18003634f  lock xadd [rbx+14h], eax
0x180036354  cmp     eax, 1
0x180036357  jnz     short loc_180036376
0x180036359  test    rbx, rbx
0x18003635c  jz      short loc_180036376
0x18003635e  mov     rcx, rbx; this
0x180036361  call    ??1TOKEN_CACHE_ENTRY@@AEAA@XZ; TOKEN_CACHE_ENTRY::~TOKEN_CACHE_ENTRY(void)
0x180036366  mov     rcx, cs:?sm_pachTokenCacheEntry@TOKEN_CACHE_ENTRY@@0PEAVALLOC_CACHE_HANDLER@@EA; ALLOC_CACHE_HANDLER * TOKEN_CACHE_ENTRY::sm_pachTokenCacheEntry
0x18003636d  mov     rdx, rbx
0x180036370  call    cs:__imp_?Free@ALLOC_CACHE_HANDLER@@QEAAHPEAX@Z; ALLOC_CACHE_HANDLER::Free(void *)
0x180036376  mov     [rbp+3Fh+var_58], 0
0x18003637e  test    rsi, rsi
0x180036381  jz      short loc_18003638C
0x180036383  mov     rcx, rsi; hMem
0x180036386  call    cs:__imp_LocalFree
0x18003638c  mov     eax, edi
0x18003638e  add     rsp, 88h
0x180036395  pop     r15
0x180036397  pop     r14
0x180036399  pop     r13
0x18003639b  pop     r12
0x18003639d  pop     rdi
0x18003639e  pop     rsi
0x18003639f  pop     rbx
0x1800363a0  pop     rbp
0x1800363a1  retn
0x1800363a2  mov     dword ptr [rax], 1
0x1800363a8  mov     rax, [rbp+3Fh+arg_28]
0x1800363ac  mov     [rsi+8], rax
0x1800363b0  mov     dword ptr [rsi+10h], 7
0x1800363b7  jmp     loc_180036475
0x1800363bc  mov     edx, 48h ; 'H'; uBytes
0x1800363c1  call    cs:__imp_LocalAlloc
0x1800363c7  mov     rsi, rax
0x1800363ca  test    rax, rax
0x1800363cd  jz      loc_18003633E
0x1800363d3  mov     rcx, cs:?g_pWebAdminService@@3PEAVWEB_ADMIN_SERVICE@@EA; this
0x1800363da  mov     dword ptr [rax], 3
0x1800363e0  call    ?GetIisIusrsSid@WEB_ADMIN_SERVICE@@QEAAPEAXXZ; WEB_ADMIN_SERVICE::GetIisIusrsSid(void)
0x1800363e5  mov     rcx, cs:?g_pWebAdminService@@3PEAVWEB_ADMIN_SERVICE@@EA; WEB_ADMIN_SERVICE * g_pWebAdminService
0x1800363ec  lea     rdx, [rbp+3Fh+var_50]
0x1800363f0  mov     ebx, 7
0x1800363f5  mov     [rsi+8], rax
0x1800363f9  add     rcx, 588h
0x180036400  mov     [rsi+10h], ebx
0x180036403  mov     [rbp+3Fh+var_50], 0
0x18003640b  call    cs:__imp_?GetLocalGroupSID@CSecurityDispenser@@QEAAKPEAPEAX@Z; CSecurityDispenser::GetLocalGroupSID(void * *)
0x180036411  test    eax, eax
0x180036413  jz      short loc_18003645F
0x180036415  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18003641c  jz      short loc_18003645B
0x18003641e  test    eax, eax
0x180036420  jle     short loc_18003642A
0x180036422  movzx   eax, ax
0x180036425  or      eax, 80070000h
0x18003642a  lea     rcx, aCouldNotResolv_0; "could not resolve local group SID\n"
0x180036431  mov     r8d, 0C25h
0x180036437  mov     qword ptr [rsp+0C0h+var_98], rcx
0x18003643c  lea     r9, aWebAdminServic_20; "WEB_ADMIN_SERVICE::GetLocalGroupSid"
0x180036443  mov     rcx, cs:g_pDebug
0x18003644a  lea     rdx, aServercommonIn_44; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x180036451  mov     [rsp+0C0h+var_A0], eax
0x180036455  call    cs:__imp_PuDbgPrintError
0x18003645b  xor     eax, eax
0x18003645d  jmp     short loc_180036463
0x18003645f  mov     rax, [rbp+3Fh+var_50]
0x180036463  mov     [rsi+18h], rax
0x180036467  mov     rax, [rbp+3Fh+arg_28]
0x18003646b  mov     [rsi+28h], rax
0x18003646f  mov     [rsi+20h], ebx
0x180036472  mov     [rsi+30h], ebx
0x180036475  mov     rcx, cs:?g_pWebAdminService@@3PEAVWEB_ADMIN_SERVICE@@EA; WEB_ADMIN_SERVICE * g_pWebAdminService
0x18003647c  lea     rax, [rbp+3Fh+var_60]
0x180036480  mov     r14, [rbp+3Fh+arg_30]
0x180036484  lea     r8, SourceString; unsigned __int16 *
0x18003648b  mov     [rsp+0C0h+var_68], 0; struct THREAD_POOL *
0x180036494  add     rcx, 4D8h; this
0x18003649b  mov     [rsp+0C0h+var_70], rsi; struct _TOKEN_GROUPS *
0x1800364a0  mov     r9, r12; unsigned __int16 *
0x1800364a3  mov     [rsp+0C0h+var_78], rax; unsigned int *
0x1800364a8  mov     rdx, r13; unsigned __int16 *
0x1800364ab  lea     rax, [rbp+3Fh+var_58]
0x1800364af  mov     qword ptr [r14], 0
0x1800364b6  mov     [rsp+0C0h+var_80], rax; struct TOKEN_CACHE_ENTRY **
0x1800364bb  mov     [rsp+0C0h+var_88], 0; struct sockaddr *
0x1800364c4  mov     [rsp+0C0h+var_90], 0; int
0x1800364cc  mov     [rsp+0C0h+var_98], edi; unsigned int
0x1800364d0  mov     [rsp+0C0h+var_A0], r15d; unsigned int
0x1800364d5  call    ?GetCachedToken2@TOKEN_CACHE@@QEAAJPEAG00KKHPEAUsockaddr@@PEAPEAVTOKEN_CACHE_ENTRY@@PEAKPEAU_TOKEN_GROUPS@@PEAVTHREAD_POOL@@@Z; TOKEN_CACHE::GetCachedToken2(ushort *,ushort *,ushort *,ulong,ulong,int,sockaddr *,TOKEN_CACHE_ENTRY * *,ulong *,_TOKEN_GROUPS *,THREAD_POOL *)
0x1800364da  mov     edi, eax
0x1800364dc  test    eax, eax
0x1800364de  js      loc_180036343
0x1800364e4  cmp     [rbp+3Fh+var_58], 0
0x1800364e9  jnz     short loc_1800364FD
0x1800364eb  mov     edi, [rbp+3Fh+var_60]
0x1800364ee  test    edi, edi
0x1800364f0  jle     short loc_18003656C
0x1800364f2  movzx   edi, di
0x1800364f5  or      edi, 80070000h
0x1800364fb  jmp     short loc_18003656A
0x1800364fd  mov     rcx, [rbp+3Fh+var_58]; this
0x180036501  mov     rbx, cs:?g_pWebAdminService@@3PEAVWEB_ADMIN_SERVICE@@EA; WEB_ADMIN_SERVICE * g_pWebAdminService
0x180036508  call    ?QueryPrimaryToken@TOKEN_CACHE_ENTRY@@QEAAPEAXXZ; TOKEN_CACHE_ENTRY::QueryPrimaryToken(void)
0x18003650d  mov     rdx, rax
0x180036510  lea     rcx, [rbx+588h]
0x180036517  call    cs:__imp_?AdjustTokenForAdministrators@CSecurityDispenser@@QEAAKPEAX@Z; CSecurityDispenser::AdjustTokenForAdministrators(void *)
0x18003651d  test    eax, eax
0x18003651f  jz      short loc_180036577
0x180036521  jg      short loc_180036527
0x180036523  mov     edi, eax
0x180036525  jmp     short loc_180036530
0x180036527  movzx   edi, ax
0x18003652a  or      edi, 80070000h
0x180036530  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180036537  jz      short loc_18003656A
0x180036539  mov     rcx, cs:g_pDebug
0x180036540  lea     rax, aCouldNotAdjust; "Could not adjust the users token to all"...
0x180036547  mov     qword ptr [rsp+0C0h+var_98], rax
0x18003654c  lea     r9, aCreatetokenfor; "CreateTokenForUser"
0x180036553  mov     r8d, 6F5h
0x180036559  mov     [rsp+0C0h+var_A0], edi
0x18003655d  lea     rdx, aServercommonIn_48; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x180036564  call    cs:__imp_PuDbgPrintError
0x18003656a  test    edi, edi
0x18003656c  jns     loc_18003637E
0x180036572  jmp     loc_180036343
0x180036577  mov     rax, [rbp+3Fh+var_58]
0x18003657b  mov     [r14], rax
0x18003657e  jmp     loc_18003637E
```
