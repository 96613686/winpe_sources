# IP_MODULE::DoEndOfRequest(IHttpContext *,STTABLE *,CONFIG_OBJECT *)

- ea: `0x180004630`
- end: `0x18000479c`
- name: `?DoEndOfRequest@IP_MODULE@@AEAAJPEAVIHttpContext@@PEAVSTTABLE@@PEAVCONFIG_OBJECT@@@Z`
- size: `364`
- prototype: `int(IP_MODULE *__hidden this, struct IHttpContext *, struct STTABLE *, struct CONFIG_OBJECT *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800061c0`

## callees

- `0x180004630`
- `0x180004f08`
- `0x180006074`
- `0x180007010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800046d9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180004744`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800046d9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180004744`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800046ca`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180004724`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800046ca`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180004724`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180004708`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180004708`
- `iisutil!PuDbgPrint` at `0x1800046b5`
- `iisutil!PuDbgPrint` at `0x18000477e`
- `iisutil!PuDbgPrint` at `0x1800046b5`
- `iisutil!PuDbgPrint` at `0x18000477e`

## string_xrefs

- `0x1800046ae`: `servercommon\inetsrv\iis\iisrearc\iis70\dynamiciprestriction\dipmodule.cpp`
- `0x180004777`: `servercommon\inetsrv\iis\iisrearc\iis70\dynamiciprestriction\dipmodule.cpp`

## pseudocode

```c
__int64 __fastcall IP_MODULE::DoEndOfRequest(
        IP_MODULE *this,
        struct IHttpContext *a2,
        struct STTABLE *a3,
        struct CONFIG_OBJECT *a4)
{
  int CachedRequestContext; // r14d
  struct IP_RECORD *v7; // rsi
  ULONGLONG TickCount64; // rbx
  int v9; // esi
  void (*v10)(struct STTABLE_ITEM *, unsigned __int64, int *); // rdx
  unsigned __int64 v11; // r8
  struct REQUEST_CONTEXT *v13; // [rsp+30h] [rbp-48h] BYREF
  struct IP_RECORD *v14; // [rsp+80h] [rbp+8h] BYREF

  v14 = 0;
  v13 = 0;
  CachedRequestContext = IP_MODULE::GetCachedRequestContext(a2, &v14, &v13);
  if ( CachedRequestContext >= 0 )
  {
    v7 = v14;
    if ( v14 )
    {
      EnterCriticalSection((LPCRITICAL_SECTION)((char *)v14 + 248));
      --*((_DWORD *)v7 + 56);
      LeaveCriticalSection((LPCRITICAL_SECTION)((char *)v7 + 248));
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)v7 + 6, 0xFFFFFFFF) == 1 )
        (**(void (__fastcall ***)(struct IP_RECORD *, __int64))v7)(v7, 1);
      if ( a4 )
      {
        TickCount64 = GetTickCount64();
        if ( TickCount64 - *((_QWORD *)a4 + 6) > *((_QWORD *)a4 + 5) )
        {
          v9 = 0;
          EnterCriticalSection((LPCRITICAL_SECTION)((char *)a4 + 56));
          if ( TickCount64 - *((_QWORD *)a4 + 6) > *((_QWORD *)a4 + 5) )
          {
            *((_QWORD *)a4 + 6) = TickCount64;
            v9 = 1;
          }
          LeaveCriticalSection((LPCRITICAL_SECTION)((char *)a4 + 56));
          if ( v9 )
          {
            if ( (g_dwDebugFlags & 3) != 0 )
              PuDbgPrint(
                g_pDebug,
                "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\dynamiciprestriction\\dipmodule.cpp",
                688,
                "IP_MODULE::DoEndOfRequest",
                "Iterating IP table to purge stale records.\n");
            STTABLE::Iterate(a3, v10, v11);
          }
        }
      }
    }
    else if ( (g_dwDebugFlags & 3) != 0 )
    {
      PuDbgPrint(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\dynamiciprestriction\\dipmodule.cpp",
        661,
        "IP_MODULE::DoEndOfRequest",
        "Failed to get client IP record in END_OF_REQUEST.\n");
    }
  }
  return (unsigned int)CachedRequestContext;
}

```

## disassembly

```asm
0x180004630  mov     rax, rsp
0x180004633  mov     [rax+8], rcx
0x180004637  push    rbx
0x180004638  push    rbp
0x180004639  push    rsi
0x18000463a  push    rdi
0x18000463b  push    r14
0x18000463d  push    r15
0x18000463f  sub     rsp, 48h
0x180004643  mov     r15, r8
0x180004646  mov     qword ptr [rax+8], 0
0x18000464e  mov     rcx, rdx; struct IHttpContext *
0x180004651  mov     qword ptr [rax-48h], 0
0x180004659  lea     r8, [rax-48h]; struct REQUEST_CONTEXT **
0x18000465d  mov     rdi, r9
0x180004660  lea     rdx, [rax+8]; struct IP_RECORD **
0x180004664  call    ?GetCachedRequestContext@IP_MODULE@@CAJPEAVIHttpContext@@PEAPEAVIP_RECORD@@PEAPEAVREQUEST_CONTEXT@@@Z; IP_MODULE::GetCachedRequestContext(IHttpContext *,IP_RECORD * *,REQUEST_CONTEXT * *)
0x180004669  mov     r14d, eax
0x18000466c  test    eax, eax
0x18000466e  js      loc_18000478C
0x180004674  mov     rsi, [rsp+78h+arg_0]
0x18000467c  test    rsi, rsi
0x18000467f  jnz     short loc_1800046C0
0x180004681  test    byte ptr cs:g_dwDebugFlags, 3
0x180004688  jz      loc_18000478C
0x18000468e  mov     rcx, cs:g_pDebug
0x180004695  lea     rax, aFailedToGetCli; "Failed to get client IP record in END_O"...
0x18000469c  lea     r9, aIpModuleDoendo; "IP_MODULE::DoEndOfRequest"
0x1800046a3  mov     [rsp+78h+var_58], rax
0x1800046a8  mov     r8d, 295h
0x1800046ae  lea     rdx, aServercommonIn; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x1800046b5  call    cs:__imp_PuDbgPrint
0x1800046bb  jmp     loc_18000478C
0x1800046c0  lea     rbx, [rsi+0F8h]
0x1800046c7  mov     rcx, rbx; lpCriticalSection
0x1800046ca  call    cs:__imp_EnterCriticalSection
0x1800046d0  dec     dword ptr [rsi+0E0h]
0x1800046d6  mov     rcx, rbx; lpCriticalSection
0x1800046d9  call    cs:__imp_LeaveCriticalSection
0x1800046df  or      eax, 0FFFFFFFFh
0x1800046e2  lock xadd [rsi+18h], eax
0x1800046e7  cmp     eax, 1
0x1800046ea  jnz     short loc_1800046FF
0x1800046ec  mov     rax, [rsi]
0x1800046ef  mov     edx, 1
0x1800046f4  mov     rcx, rsi
0x1800046f7  mov     rax, [rax]
0x1800046fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800046ff  test    rdi, rdi
0x180004702  jz      loc_18000478C
0x180004708  call    cs:__imp_GetTickCount64
0x18000470e  mov     rcx, rax
0x180004711  mov     rbx, rax
0x180004714  sub     rcx, [rdi+30h]
0x180004718  cmp     rcx, [rdi+28h]
0x18000471c  jbe     short loc_18000478C
0x18000471e  lea     rcx, [rdi+38h]; lpCriticalSection
0x180004722  xor     esi, esi
0x180004724  call    cs:__imp_EnterCriticalSection
0x18000472a  mov     rdx, rbx
0x18000472d  sub     rdx, [rdi+30h]
0x180004731  cmp     rdx, [rdi+28h]
0x180004735  jbe     short loc_180004740
0x180004737  mov     [rdi+30h], rbx
0x18000473b  mov     esi, 1
0x180004740  lea     rcx, [rdi+38h]; lpCriticalSection
0x180004744  call    cs:__imp_LeaveCriticalSection
0x18000474a  test    esi, esi
0x18000474c  jz      short loc_18000478C
0x18000474e  test    byte ptr cs:g_dwDebugFlags, 3
0x180004755  jz      short loc_180004784
0x180004757  mov     rcx, cs:g_pDebug
0x18000475e  lea     rax, aIteratingIpTab; "Iterating IP table to purge stale recor"...
0x180004765  lea     r9, aIpModuleDoendo; "IP_MODULE::DoEndOfRequest"
0x18000476c  mov     [rsp+78h+var_58], rax
0x180004771  mov     r8d, 2B0h
0x180004777  lea     rdx, aServercommonIn; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x18000477e  call    cs:__imp_PuDbgPrint
0x180004784  mov     rcx, r15; this
0x180004787  call    ?Iterate@STTABLE@@QEAAXP6AXPEAVSTTABLE_ITEM@@_KPEAH@Z1@Z; STTABLE::Iterate(void (*)(STTABLE_ITEM *,unsigned __int64,int *),unsigned __int64)
0x18000478c  mov     eax, r14d
0x18000478f  add     rsp, 48h
0x180004793  pop     r15
0x180004795  pop     r14
0x180004797  pop     rdi
0x180004798  pop     rsi
0x180004799  pop     rbp
0x18000479a  pop     rbx
0x18000479b  retn
```
