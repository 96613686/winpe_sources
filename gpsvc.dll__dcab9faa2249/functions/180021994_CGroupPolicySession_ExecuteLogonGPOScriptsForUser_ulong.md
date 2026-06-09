# CGroupPolicySession::ExecuteLogonGPOScriptsForUser(ulong)

- ea: `0x180021994`
- end: `0x180021e05`
- name: `?ExecuteLogonGPOScriptsForUser@CGroupPolicySession@@QEAAKK@Z`
- size: `1137`
- prototype: `unsigned int __fastcall(CGroupPolicySession *__hidden this, unsigned int)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180052dc0`

## callees

- `0x180021994`
- `0x180021e0c`
- `0x180021e54`
- `0x1800234e4`
- `0x1800239dc`
- `0x180023aac`
- `0x18004df78`
- `0x180075ec0`
- `0x1800bf010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180021c9c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180021c9c`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180021cf0`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180021cf0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180021dbd`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180021dbd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021d13`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021d43`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021d8e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021d13`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021d43`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021d8e`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180021d7f`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180021d7f`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180021abb`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180021abb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180021dd3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180021dd3`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CGroupPolicySession::ExecuteLogonGPOScriptsForUser(
        struct _RTL_CRITICAL_SECTION **this,
        unsigned int a2)
{
  unsigned int Setting; // r12d
  _DWORD *v5; // rax
  _DWORD *v6; // rbx
  unsigned int v7; // r14d
  void (*v8)(unsigned int, const unsigned __int16 *, ...); // rax
  const wchar_t *v9; // rdx
  struct _RTL_CRITICAL_SECTION *v10; // r15
  struct _RTL_CRITICAL_SECTION *v11; // rax
  _QWORD **DebugInfo; // rcx
  _QWORD *i; // rax
  __int64 v14; // r14
  HANDLE EventW; // rax
  void (*v16)(unsigned int, const unsigned __int16 *, ...); // r13
  DWORD LastError; // eax
  DWORD v18; // eax
  HANDLE Thread; // rax
  char v21[8]; // [rsp+40h] [rbp-20h] BYREF
  const WCHAR *v22; // [rsp+48h] [rbp-18h]
  const WCHAR *v23; // [rsp+50h] [rbp-10h]
  HKEY v24; // [rsp+A0h] [rbp+40h] BYREF
  unsigned int v25; // [rsp+B0h] [rbp+50h] BYREF
  CGroupPolicySession *v26; // [rsp+B8h] [rbp+58h]

  v26 = (CGroupPolicySession *)this;
  if ( this )
    ((void (__fastcall *)(struct _RTL_CRITICAL_SECTION **))(*this)->DebugInfo)(this);
  if ( !(unsigned int)CGroupPolicySession::GetPolicyApplicationMode(this) )
  {
    v24 = 0;
    if ( !CGroupPolicySession::GetRootRegistryForCurrentUser((CGroupPolicySession *)this, &v24) )
      *((_DWORD *)this + 111) = GPOScripts::IsScriptConfiguredSync(v24, 1);
  }
  if ( *((_DWORD *)this + 111) )
  {
    if ( *(_DWORD *)&g_dwDebugLevel )
    {
      if ( g_lpDebugMsg )
      {
        g_lpDebugMsg(4u, L"CGroupPolicySession::ExecuteLogonGPOScriptsForUser - Sync.");
      }
      else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
      {
        RedirectDebugMsg(4u, L"CGroupPolicySession::ExecuteLogonGPOScriptsForUser - Sync.");
      }
    }
    Setting = CGroupPolicySession::ExecuteGPOScriptsForThePrincipal((CGroupPolicySession *)this, 1, a2);
    goto LABEL_80;
  }
  if ( *(_DWORD *)&g_dwDebugLevel )
  {
    if ( g_lpDebugMsg )
    {
      g_lpDebugMsg(4u, L"CGroupPolicySession::ExecuteLogonGPOScriptsForUser - Async.");
    }
    else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
    {
      RedirectDebugMsg(4u, L"CGroupPolicySession::ExecuteLogonGPOScriptsForUser - Async.");
    }
  }
  v5 = LocalAlloc(0x40u, 0x18u);
  v6 = v5;
  if ( v5 )
  {
    *(_QWORD *)v5 = this;
    v5[2] = a2;
    v7 = 5;
    v5[3] = 5;
    v25 = 0;
    LODWORD(v24) = 5;
    v22 = L"Software\\Microsoft\\Windows NT\\CurrentVersion\\Winlogon";
    v23 = L"Software\\Policies\\Microsoft\\Windows\\System";
    Setting = CRegistryPolicy::GetSetting(
                (CRegistryPolicy *)v21,
                HKEY_LOCAL_MACHINE,
                L"EnableLogonScriptDelay",
                (BYTE *)&v25,
                0);
    if ( Setting )
    {
      if ( *(_DWORD *)&g_dwDebugLevel )
      {
        if ( g_lpDebugMsg )
        {
          g_lpDebugMsg(
            4u,
            L"CGroupPolicySession::ExecuteLogonGPOScriptsForUser - GetSetting EnableLogonScriptDelay failed.");
        }
        else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
        {
          RedirectDebugMsg(
            4u,
            L"CGroupPolicySession::ExecuteLogonGPOScriptsForUser - GetSetting EnableLogonScriptDelay failed.");
        }
      }
      LODWORD(v24) = 5;
LABEL_46:
      if ( *(_DWORD *)&g_dwDebugLevel )
      {
        if ( g_lpDebugMsg )
        {
          g_lpDebugMsg(
            4u,
            L"CGroupPolicySession::ExecuteLogonGPOScriptsForUser - GetSetting ASYNC_SCRIPT_DELAY value:%d minutes.",
            v7);
        }
        else
        {
          if ( !g_lpDebugMsgContextInstance || !g_lpDebugMsgContext )
            goto LABEL_53;
          RedirectDebugMsg(
            4u,
            L"CGroupPolicySession::ExecuteLogonGPOScriptsForUser - GetSetting ASYNC_SCRIPT_DELAY value:%d minutes.",
            v7);
        }
        v7 = (unsigned int)v24;
      }
LABEL_53:
      LODWORD(v24) = 60000 * v7;
      v6[3] = 60000 * v7;
      v10 = this[19];
      if ( v10 )
        EnterCriticalSection(v10);
      v11 = this[20];
      if ( v11 )
      {
        DebugInfo = (_QWORD **)v11->DebugInfo;
        for ( i = *(_QWORD **)&v11->DebugInfo->Type; i != DebugInfo; i = (_QWORD *)*i )
        {
          v14 = i[2];
          if ( a2 == *(_DWORD *)(v14 + 8) )
          {
            if ( !v14 )
              break;
            if ( (_DWORD)v24 )
            {
              v6[3] = (_DWORD)v24;
              EventW = CreateEventW(0, 1, 0, 0);
              *(_QWORD *)(v14 + 24) = EventW;
              if ( EventW )
              {
                *((_QWORD *)v6 + 2) = EventW;
              }
              else if ( *(_DWORD *)&g_dwDebugLevel )
              {
                v16 = g_lpDebugMsg;
                if ( g_lpDebugMsg )
                {
                  LastError = GetLastError();
                  v16(
                    4u,
                    L"CGroupPolicySession::ExecuteLogonGPOScriptsForUser - hLogonGPOScriptDelay failed with %d.",
                    LastError);
                }
                else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
                {
                  v18 = GetLastError();
                  RedirectDebugMsg(
                    4u,
                    L"CGroupPolicySession::ExecuteLogonGPOScriptsForUser - hLogonGPOScriptDelay failed with %d.",
                    v18);
                }
              }
            }
            Thread = CreateThread(0, 0, CGroupPolicySession::ExecuteLogonScriptsAsync, v6, 0, 0);
            *(_QWORD *)(v14 + 16) = Thread;
            if ( Thread )
            {
              v6 = 0;
            }
            else
            {
              Setting = GetLastError();
              if ( *(_QWORD *)(v14 + 24) )
                CGroupPolicySession::SafeCloseHandle((CGroupPolicySession *)this, (void **)(v14 + 24));
            }
            goto LABEL_75;
          }
        }
      }
      Setting = 13;
LABEL_75:
      if ( v10 )
        LeaveCriticalSection(v10);
      goto LABEL_78;
    }
    if ( v25 )
    {
      Setting = CRegistryPolicy::GetSetting(
                  (CRegistryPolicy *)v21,
                  HKEY_LOCAL_MACHINE,
                  L"AsyncScriptDelay",
                  (BYTE *)&v24,
                  5u);
      if ( !Setting )
      {
        v7 = (unsigned int)v24;
        goto LABEL_46;
      }
      if ( *(_DWORD *)&g_dwDebugLevel )
      {
        v8 = g_lpDebugMsg;
        if ( !g_lpDebugMsg )
        {
          if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
            RedirectDebugMsg(
              4u,
              L"CGroupPolicySession::ExecuteLogonGPOScriptsForUser - GetSetting ASYNC_SCRIPT_DELAY failed.");
          goto LABEL_37;
        }
        v9 = L"CGroupPolicySession::ExecuteLogonGPOScriptsForUser - GetSetting ASYNC_SCRIPT_DELAY failed.";
LABEL_33:
        v8(4u, v9);
      }
    }
    else if ( *(_DWORD *)&g_dwDebugLevel )
    {
      v8 = g_lpDebugMsg;
      if ( !g_lpDebugMsg )
      {
        if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
          RedirectDebugMsg(
            4u,
            L"CGroupPolicySession::ExecuteLogonGPOScriptsForUser - LogonScriptDelay policy disabled.");
        goto LABEL_37;
      }
      v9 = L"CGroupPolicySession::ExecuteLogonGPOScriptsForUser - LogonScriptDelay policy disabled.";
      goto LABEL_33;
    }
LABEL_37:
    v7 = 0;
    LODWORD(v24) = 0;
    goto LABEL_46;
  }
  Setting = 14;
LABEL_78:
  if ( v6 )
    LocalFree(v6);
LABEL_80:
  (*(void (__fastcall **)(struct _RTL_CRITICAL_SECTION **))&(*this)->LockCount)(this);
  return Setting;
}

```

## disassembly

```asm
0x180021994  mov     [rsp-38h+arg_8], rbx
0x180021999  push    rbp
0x18002199a  push    rsi
0x18002199b  push    rdi
0x18002199c  push    r12
0x18002199e  push    r13
0x1800219a0  push    r14
0x1800219a2  push    r15
0x1800219a4  mov     rbp, rsp
0x1800219a7  sub     rsp, 60h
0x1800219ab  mov     r13d, edx
0x1800219ae  mov     rdi, rcx
0x1800219b1  mov     [rbp+arg_18], rcx
0x1800219b5  xor     r15d, r15d
0x1800219b8  test    rcx, rcx
0x1800219bb  jz      short loc_1800219C9
0x1800219bd  mov     rax, [rcx]
0x1800219c0  mov     rax, [rax]
0x1800219c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800219c8  nop
0x1800219c9  mov     rcx, rdi
0x1800219cc  call    ?GetPolicyApplicationMode@CGroupPolicySession@@QEAA?AW4POLICY_PROCESSING_MODE@1@XZ; CGroupPolicySession::GetPolicyApplicationMode(void)
0x1800219d1  mov     ebx, 1
0x1800219d6  test    eax, eax
0x1800219d8  jnz     short loc_1800219FF
0x1800219da  mov     [rbp+arg_0], r15
0x1800219de  lea     rdx, [rbp+arg_0]; HKEY *
0x1800219e2  mov     rcx, rdi; this
0x1800219e5  call    ?GetRootRegistryForCurrentUser@CGroupPolicySession@@AEAAKPEAPEAUHKEY__@@@Z; CGroupPolicySession::GetRootRegistryForCurrentUser(HKEY__ * *)
0x1800219ea  test    eax, eax
0x1800219ec  jnz     short loc_1800219FF
0x1800219ee  mov     edx, ebx
0x1800219f0  mov     rcx, [rbp+arg_0]
0x1800219f4  call    ?IsScriptConfiguredSync@GPOScripts@@SAHPEAUHKEY__@@W4tagSCRIPTTYPE@@@Z; GPOScripts::IsScriptConfiguredSync(HKEY__ *,tagSCRIPTTYPE)
0x1800219f9  mov     [rdi+1BCh], eax
0x1800219ff  cmp     [rdi+1BCh], r15d
0x180021a06  jz      short loc_180021A68
0x180021a08  cmp     cs:?g_dwDebugLevel@@3KA, r15d; ulong g_dwDebugLevel
0x180021a0f  jz      short loc_180021A53
0x180021a11  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x180021a18  test    rax, rax
0x180021a1b  jz      short loc_180021A30
0x180021a1d  lea     rdx, aCgrouppolicyse_32; "CGroupPolicySession::ExecuteLogonGPOScr"...
0x180021a24  mov     ecx, 4
0x180021a29  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021a2e  jmp     short loc_180021A53
0x180021a30  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r15; void * g_lpDebugMsgContextInstance
0x180021a37  jz      short loc_180021A53
0x180021a39  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r15; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x180021a40  jz      short loc_180021A53
0x180021a42  lea     rdx, aCgrouppolicyse_32; "CGroupPolicySession::ExecuteLogonGPOScr"...
0x180021a49  mov     ecx, 4; unsigned int
0x180021a4e  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x180021a53  mov     r8d, r13d; unsigned int
0x180021a56  mov     edx, ebx; int
0x180021a58  mov     rcx, rdi; this
0x180021a5b  call    ?ExecuteGPOScriptsForThePrincipal@CGroupPolicySession@@QEAAKHK@Z; CGroupPolicySession::ExecuteGPOScriptsForThePrincipal(int,ulong)
0x180021a60  mov     r12d, eax
0x180021a63  jmp     loc_180021DDA
0x180021a68  mov     esi, 4
0x180021a6d  cmp     cs:?g_dwDebugLevel@@3KA, r15d; ulong g_dwDebugLevel
0x180021a74  jz      short loc_180021AB3
0x180021a76  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x180021a7d  test    rax, rax
0x180021a80  jz      short loc_180021A92
0x180021a82  lea     rdx, aCgrouppolicyse_26; "CGroupPolicySession::ExecuteLogonGPOScr"...
0x180021a89  mov     ecx, esi
0x180021a8b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021a90  jmp     short loc_180021AB3
0x180021a92  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r15; void * g_lpDebugMsgContextInstance
0x180021a99  jz      short loc_180021AB3
0x180021a9b  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r15; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x180021aa2  jz      short loc_180021AB3
0x180021aa4  lea     rdx, aCgrouppolicyse_26; "CGroupPolicySession::ExecuteLogonGPOScr"...
0x180021aab  mov     ecx, esi; unsigned int
0x180021aad  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x180021ab2  nop
0x180021ab3  mov     edx, 18h; uBytes
0x180021ab8  lea     ecx, [rdx+28h]; uFlags
0x180021abb  call    cs:__imp_LocalAlloc
0x180021ac1  mov     rbx, rax
0x180021ac4  mov     [rbp+var_30], rax
0x180021ac8  test    rax, rax
0x180021acb  jz      loc_180021DC5
0x180021ad1  mov     [rax], rdi
0x180021ad4  mov     [rax+8], r13d
0x180021ad8  mov     r14d, 5
0x180021ade  mov     [rax+0Ch], r14d
0x180021ae2  mov     [rbp+arg_10], r15d
0x180021ae6  mov     dword ptr [rbp+arg_0], r14d
0x180021aea  lea     rax, aSoftwareMicros_39; "Software\\Microsoft\\Windows NT\\Curren"...
0x180021af1  mov     [rbp+var_18], rax
0x180021af5  lea     rax, aSoftwarePolici; "Software\\Policies\\Microsoft\\Windows"...
0x180021afc  mov     [rbp+var_10], rax
0x180021b00  mov     [rsp+60h+dwCreationFlags], r15d; unsigned int
0x180021b05  lea     r9, [rbp+arg_10]; unsigned int *
0x180021b09  lea     r8, aEnablelogonscr; "EnableLogonScriptDelay"
0x180021b10  mov     rdx, 0FFFFFFFF80000002h; HKEY
0x180021b17  lea     rcx, [rbp+var_20]; this
0x180021b1b  call    ?GetSetting@CRegistryPolicy@@QEBAKPEAUHKEY__@@PEBGPEAKK@Z; CRegistryPolicy::GetSetting(HKEY__ *,ushort const *,ulong *,ulong)
0x180021b20  mov     r12d, eax
0x180021b23  test    eax, eax
0x180021b25  jz      short loc_180021B75
0x180021b27  cmp     cs:?g_dwDebugLevel@@3KA, r15d; ulong g_dwDebugLevel
0x180021b2e  jz      short loc_180021B6C
0x180021b30  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x180021b37  test    rax, rax
0x180021b3a  jz      short loc_180021B4C
0x180021b3c  lea     rdx, aCgrouppolicyse_79; "CGroupPolicySession::ExecuteLogonGPOScr"...
0x180021b43  mov     ecx, esi
0x180021b45  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021b4a  jmp     short loc_180021B6C
0x180021b4c  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r15; void * g_lpDebugMsgContextInstance
0x180021b53  jz      short loc_180021B6C
0x180021b55  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r15; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x180021b5c  jz      short loc_180021B6C
0x180021b5e  lea     rdx, aCgrouppolicyse_79; "CGroupPolicySession::ExecuteLogonGPOScr"...
0x180021b65  mov     ecx, esi; unsigned int
0x180021b67  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x180021b6c  mov     dword ptr [rbp+arg_0], r14d
0x180021b70  jmp     loc_180021C2D
0x180021b75  cmp     [rbp+arg_10], r15d
0x180021b79  jnz     short loc_180021BC9
0x180021b7b  cmp     cs:?g_dwDebugLevel@@3KA, r15d; ulong g_dwDebugLevel
0x180021b82  jz      short loc_180021BC0
0x180021b84  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x180021b8b  test    rax, rax
0x180021b8e  jz      short loc_180021BA0
0x180021b90  lea     rdx, aCgrouppolicyse_0; "CGroupPolicySession::ExecuteLogonGPOScr"...
0x180021b97  mov     ecx, esi
0x180021b99  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021b9e  jmp     short loc_180021BC0
0x180021ba0  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r15; void * g_lpDebugMsgContextInstance
0x180021ba7  jz      short loc_180021BC0
0x180021ba9  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r15; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x180021bb0  jz      short loc_180021BC0
0x180021bb2  lea     rdx, aCgrouppolicyse_0; "CGroupPolicySession::ExecuteLogonGPOScr"...
0x180021bb9  mov     ecx, esi; unsigned int
0x180021bbb  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x180021bc0  mov     r14d, r15d
0x180021bc3  mov     dword ptr [rbp+arg_0], r15d
0x180021bc7  jmp     short loc_180021C2D
0x180021bc9  mov     [rsp+60h+dwCreationFlags], r14d; unsigned int
0x180021bce  lea     r9, [rbp+arg_0]; unsigned int *
0x180021bd2  lea     r8, aAsyncscriptdel; "AsyncScriptDelay"
0x180021bd9  mov     rdx, 0FFFFFFFF80000002h; HKEY
0x180021be0  lea     rcx, [rbp+var_20]; this
0x180021be4  call    ?GetSetting@CRegistryPolicy@@QEBAKPEAUHKEY__@@PEBGPEAKK@Z; CRegistryPolicy::GetSetting(HKEY__ *,ushort const *,ulong *,ulong)
0x180021be9  mov     r12d, eax
0x180021bec  test    eax, eax
0x180021bee  jz      short loc_180021C29
0x180021bf0  cmp     cs:?g_dwDebugLevel@@3KA, r15d; ulong g_dwDebugLevel
0x180021bf7  jz      short loc_180021BC0
0x180021bf9  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x180021c00  test    rax, rax
0x180021c03  jz      short loc_180021C0E
0x180021c05  lea     rdx, aCgrouppolicyse_28; "CGroupPolicySession::ExecuteLogonGPOScr"...
0x180021c0c  jmp     short loc_180021B97
0x180021c0e  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r15; void * g_lpDebugMsgContextInstance
0x180021c15  jz      short loc_180021BC0
0x180021c17  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r15; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x180021c1e  jz      short loc_180021BC0
0x180021c20  lea     rdx, aCgrouppolicyse_28; "CGroupPolicySession::ExecuteLogonGPOScr"...
0x180021c27  jmp     short loc_180021BB9
0x180021c29  mov     r14d, dword ptr [rbp+arg_0]
0x180021c2d  cmp     cs:?g_dwDebugLevel@@3KA, r15d; ulong g_dwDebugLevel
0x180021c34  jz      short loc_180021C7C
0x180021c36  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x180021c3d  test    rax, rax
0x180021c40  jz      short loc_180021C55
0x180021c42  mov     r8d, r14d
0x180021c45  lea     rdx, aCgrouppolicyse_45; "CGroupPolicySession::ExecuteLogonGPOScr"...
0x180021c4c  mov     ecx, esi
0x180021c4e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021c53  jmp     short loc_180021C78
0x180021c55  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r15; void * g_lpDebugMsgContextInstance
0x180021c5c  jz      short loc_180021C7C
0x180021c5e  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r15; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x180021c65  jz      short loc_180021C7C
0x180021c67  mov     r8d, r14d
0x180021c6a  lea     rdx, aCgrouppolicyse_45; "CGroupPolicySession::ExecuteLogonGPOScr"...
0x180021c71  mov     ecx, esi; unsigned int
0x180021c73  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x180021c78  mov     r14d, dword ptr [rbp+arg_0]
0x180021c7c  imul    eax, r14d, 0EA60h
0x180021c83  mov     dword ptr [rbp+arg_0], eax
0x180021c86  mov     [rbx+0Ch], eax
0x180021c89  mov     r15, [rdi+98h]
0x180021c90  mov     [rbp+var_28], r15
0x180021c94  test    r15, r15
0x180021c97  jz      short loc_180021CA3
0x180021c99  mov     rcx, r15; lpCriticalSection
0x180021c9c  call    cs:__imp_EnterCriticalSection
0x180021ca2  nop
0x180021ca3  mov     rax, [rdi+0A0h]
0x180021caa  test    rax, rax
0x180021cad  jz      loc_180021DAF
0x180021cb3  mov     rcx, [rax]
0x180021cb6  mov     rax, [rcx]
0x180021cb9  cmp     rax, rcx
0x180021cbc  jz      loc_180021DAF
0x180021cc2  mov     r14, [rax+10h]
0x180021cc6  cmp     r13d, [r14+8]
0x180021cca  jz      short loc_180021CD1
0x180021ccc  mov     rax, [rax]
0x180021ccf  jmp     short loc_180021CB9
0x180021cd1  test    r14, r14
0x180021cd4  jz      loc_180021DAF
0x180021cda  mov     eax, dword ptr [rbp+arg_0]
0x180021cdd  test    eax, eax
0x180021cdf  jz      short loc_180021D60
0x180021ce1  mov     [rbx+0Ch], eax
0x180021ce4  xor     r9d, r9d; lpName
0x180021ce7  xor     r8d, r8d; bInitialState
0x180021cea  lea     edx, [r9+1]; bManualReset
0x180021cee  xor     ecx, ecx; lpEventAttributes
0x180021cf0  call    cs:__imp_CreateEventW
0x180021cf6  mov     [r14+18h], rax
0x180021cfa  test    rax, rax
0x180021cfd  jnz     short loc_180021D5C
0x180021cff  cmp     cs:?g_dwDebugLevel@@3KA, eax; ulong g_dwDebugLevel
0x180021d05  jz      short loc_180021D60
0x180021d07  mov     r13, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x180021d0e  test    r13, r13
0x180021d11  jz      short loc_180021D2F
0x180021d13  call    cs:__imp_GetLastError
0x180021d19  mov     r8d, eax
0x180021d1c  lea     rdx, aCgrouppolicyse_80; "CGroupPolicySession::ExecuteLogonGPOScr"...
0x180021d23  mov     ecx, esi
0x180021d25  mov     rax, r13
0x180021d28  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021d2d  jmp     short loc_180021D60
0x180021d2f  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, 0; void * g_lpDebugMsgContextInstance
0x180021d37  jz      short loc_180021D60
0x180021d39  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, 0; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x180021d41  jz      short loc_180021D60
0x180021d43  call    cs:__imp_GetLastError
0x180021d49  mov     r8d, eax
0x180021d4c  lea     rdx, aCgrouppolicyse_80; "CGroupPolicySession::ExecuteLogonGPOScr"...
0x180021d53  mov     ecx, esi; unsigned int
0x180021d55  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x180021d5a  jmp     short loc_180021D60
0x180021d5c  mov     [rbx+10h], rax
0x180021d60  mov     [rsp+60h+lpThreadId], 0; lpThreadId
0x180021d69  mov     [rsp+60h+dwCreationFlags], 0; dwCreationFlags
0x180021d71  mov     r9, rbx; lpParameter
0x180021d74  lea     r8, ?ExecuteLogonScriptsAsync@CGroupPolicySession@@CAKPEAX@Z; lpStartAddress
0x180021d7b  xor     edx, edx; dwStackSize
0x180021d7d  xor     ecx, ecx; lpThreadAttributes
0x180021d7f  call    cs:__imp_CreateThread
0x180021d85  mov     [r14+10h], rax
0x180021d89  test    rax, rax
0x180021d8c  jnz     short loc_180021DAB
0x180021d8e  call    cs:__imp_GetLastError
0x180021d94  mov     r12d, eax
0x180021d97  lea     rdx, [r14+18h]; void **
0x180021d9b  cmp     qword ptr [rdx], 0
0x180021d9f  jz      short loc_180021DB5
0x180021da1  mov     rcx, rdi; this
0x180021da4  call    ?SafeCloseHandle@CGroupPolicySession@@AEAAXAEAPEAX@Z; CGroupPolicySession::SafeCloseHandle(void * &)
0x180021da9  jmp     short loc_180021DB5
0x180021dab  xor     ebx, ebx
0x180021dad  jmp     short loc_180021DB5
0x180021daf  mov     r12d, 0Dh
0x180021db5  test    r15, r15
0x180021db8  jz      short loc_180021DCB
0x180021dba  mov     rcx, r15; lpCriticalSection
0x180021dbd  call    cs:__imp_LeaveCriticalSection
0x180021dc3  jmp     short loc_180021DCB
0x180021dc5  mov     r12d, 0Eh
0x180021dcb  test    rbx, rbx
0x180021dce  jz      short loc_180021DDA
0x180021dd0  mov     rcx, rbx; hMem
0x180021dd3  call    cs:__imp_LocalFree
0x180021dd9  nop
0x180021dda  mov     rax, [rdi]
0x180021ddd  mov     rcx, rdi
0x180021de0  mov     rax, [rax+8]
0x180021de4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021de9  nop
0x180021dea  mov     eax, r12d
0x180021ded  mov     rbx, [rsp+60h+arg_8]
0x180021df5  add     rsp, 60h
0x180021df9  pop     r15
0x180021dfb  pop     r14
0x180021dfd  pop     r13
0x180021dff  pop     r12
0x180021e01  pop     rdi
0x180021e02  pop     rsi
0x180021e03  pop     rbp
0x180021e04  retn
```
