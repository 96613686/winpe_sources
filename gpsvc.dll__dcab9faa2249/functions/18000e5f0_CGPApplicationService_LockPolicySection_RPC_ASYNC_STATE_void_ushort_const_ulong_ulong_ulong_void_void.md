# CGPApplicationService::LockPolicySection(_RPC_ASYNC_STATE *,void *,ushort const *,ulong,ulong,ulong,void *,void * *)

- ea: `0x18000e5f0`
- end: `0x18000f9ea`
- name: `?LockPolicySection@CGPApplicationService@@UEAAKPEAU_RPC_ASYNC_STATE@@PEAXPEBGKKK1PEAPEAX@Z`
- size: `5114`
- prototype: `unsigned int __usercall@<eax>(CGPApplicationService *__hidden this@<rcx>, struct _RPC_ASYNC_STATE *@<rdx>, void *@<r8>, const unsigned __int16 *@<r9>, unsigned int, unsigned int, unsigned int, void *, void **)`
- caller_count: `0`
- callee_count: `23`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x180007c7c`
- `0x180008244`
- `0x18000a4b0`
- `0x18000b764`
- `0x18000cc30`
- `0x18000d2b0`
- `0x18000dec0`
- `0x18000e5f0`
- `0x180010520`
- `0x180010580`
- `0x1800105e0`
- `0x1800106c8`
- `0x180046c50`
- `0x180049e44`
- `0x18004a7f0`
- `0x18005ce24`
- `0x180075ec0`
- `0x18007d304`
- `0x18007d320`
- `0x18007d770`
- `0x180090284`
- `0x1800b4188`
- `0x1800bf010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__itow` at `0x18000f7be`
- `api-ms-win-crt-private-l1-1-0!_o__itow` at `0x18000f7be`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000e7c0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000ea0b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000ee6c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000e7c0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000ea0b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000ee6c`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000f4bf`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000f4bf`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18000e670`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18000e670`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000e7ee`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000e933`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000eb48`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000eda5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000eee8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000e7ee`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000e933`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000eb48`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000eda5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000eee8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f6f2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f7f9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f6f2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f7f9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000f52e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000f52e`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18000ec1b`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18000efd4`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18000ec1b`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18000efd4`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000ea9a`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000ea9a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000e760`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000e958`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000eba9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000ec41`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000eed3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000efec`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000e760`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000e958`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000eba9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000ec41`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000eed3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000efec`
- `api-ms-win-security-base-l1-1-0!AccessCheck` at `0x18000e8b9`
- `api-ms-win-security-base-l1-1-0!AccessCheck` at `0x18000e8b9`
- `ntdll!EtwEventWrite` at `0x18000f1c9`
- `ntdll!EtwEventWrite` at `0x18000f1c9`

## string_xrefs

- `0x18000f712`: `AccessCheckBasedOnSD:  AccessCheck failed with %d.`
- `0x18000f73a`: `AccessCheckBasedOnSD:  AccessCheck failed with %d.`
- `0x18000f771`: `AccessCheckBasedOnSD:  returning %d.`
- `0x18000f799`: `AccessCheckBasedOnSD:  returning %d.`
- `0x18000f5f3`: `Could not find user by sid, finding user by session id`
- `0x18000f61a`: `Could not find user by sid, finding user by session id`
- `0x18000ef8b`: `Session %d SID set to : %s`
- `0x18000f684`: `Session %d SID set to : %s`
- `0x18000f01c`: `AccessCheckForLock failed with 0x%x`
- `0x18000f823`: `AccessCheckForLock failed with 0x%x`
- `0x18000f20b`: `WaitForServiceInitialization: Event is null.`
- `0x18000f23b`: `WaitForServiceInitialization: Event is null.`
- `0x18000f32c`: `The reader was not present in the list.`
- `0x18000f35c`: `The reader was not present in the list.`
- `0x18000f867`: `Failed to allocate %d bytes for sid`
- `0x18000f897`: `Failed to allocate %d bytes for sid`
- `0x18000f8c3`: `SID = %ws`
- `0x18000f8fa`: `SID = %ws`
- `0x18000f478`: `Signalling first writer with ID [%d]`
- `0x18000f4a5`: `Signalling first writer with ID [%d]`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
__int64 __fastcall CGPApplicationService::LockPolicySection(
        CGPApplicationService *this,
        struct _RPC_ASYNC_STATE *a2,
        void *a3,
        const unsigned __int16 *a4,
        unsigned int a5,
        unsigned int a6,
        unsigned int a7,
        void *a8,
        void **a9)
{
  HANDLE v10; // r13
  CGPApplicationService *v12; // rdi
  void *v13; // rax
  PSECURITY_DESCRIPTOR *UserData; // r12
  void *v15; // rcx
  __int64 v16; // r14
  __int64 v17; // r15
  unsigned int v18; // ecx
  unsigned int v19; // ebx
  char *v20; // r13
  _QWORD *v21; // rbx
  _QWORD *v22; // rbx
  _QWORD *v23; // rax
  _QWORD *v24; // rax
  __int64 v25; // rdi
  __int64 v26; // rcx
  __int64 v27; // rax
  struct _RWLOCK_CONTEXT **v28; // rdi
  struct _RTL_CRITICAL_SECTION *v29; // rbx
  __int64 v30; // r8
  _QWORD *i; // rcx
  unsigned int v32; // ebx
  unsigned int LastError; // r13d
  struct _RWLOCK_CONTEXT **v34; // r9
  struct _RPC_ASYNC_STATE *v35; // r8
  struct _RWLOCK_CONTEXT **v36; // r13
  unsigned int v37; // ebx
  struct _RTL_CRITICAL_SECTION *v38; // rbx
  struct _RTL_CRITICAL_SECTION *v39; // rdi
  CGPApplicationService *v40; // r13
  __int64 ***v41; // rbx
  __int64 **v42; // rbx
  __int64 **v43; // rax
  struct _RWLOCK_CONTEXT *v44; // rax
  AccountPolicyCriticalSection *v45; // r12
  unsigned __int64 v46; // rbx
  WCHAR *v47; // rax
  unsigned int v48; // edx
  WCHAR *v49; // rcx
  unsigned int v50; // edx
  WCHAR v51; // ax
  const WCHAR *v52; // r8
  bool v53; // zf
  volatile signed __int32 *v54; // r12
  __int64 v55; // rax
  CPolicyCriticalSection *v56; // rcx
  unsigned int v57; // eax
  int v59; // eax
  int v60; // ecx
  struct _RWLOCK_CONTEXT *v61; // rax
  struct _RWLOCK_CONTEXT *v62; // rbx
  CRWLock *v63; // rcx
  struct _RWLOCK_CONTEXT *v64; // rax
  struct _RWLOCK_CONTEXT *v65; // rbx
  CRWLock *v66; // rcx
  const unsigned __int16 **v67; // rax
  const unsigned __int16 *v68; // rdx
  CPolicyCriticalSection *v69; // rcx
  CGPApplicationService *v70; // rbx
  struct _RTL_CRITICAL_SECTION *v71; // r13
  _QWORD *v72; // rax
  void *v73; // rcx
  AccountPolicyCriticalSection *v74; // rcx
  wchar_t v75; // ax
  wchar_t *v76; // r8
  wchar_t *v77; // r10
  __int64 v78; // rdx
  __int64 v79; // r9
  _WORD *v80; // rax
  __int64 v81; // rcx
  int v82; // ecx
  wchar_t *v83; // r9
  wchar_t v84; // ax
  __int64 v85; // rax
  int v86; // eax
  HANDLE *v87; // rax
  CRWLock *v88; // rcx
  struct CGroupPolicySession *UserDataBasedOnSessionId; // rax
  WINBOOL AccessStatus; // [rsp+40h] [rbp-C0h] BYREF
  BOOL v91; // [rsp+44h] [rbp-BCh] BYREF
  void *v92; // [rsp+48h] [rbp-B8h]
  CGPApplicationService *v93; // [rsp+50h] [rbp-B0h]
  HANDLE ClientToken; // [rsp+58h] [rbp-A8h] BYREF
  HLOCAL hMem; // [rsp+60h] [rbp-A0h] BYREF
  PSECURITY_DESCRIPTOR *v96; // [rsp+68h] [rbp-98h]
  HLOCAL v97; // [rsp+70h] [rbp-90h] BYREF
  DWORD GrantedAccess[2]; // [rsp+78h] [rbp-88h] BYREF
  void **v99; // [rsp+80h] [rbp-80h]
  struct _RPC_ASYNC_STATE *v100; // [rsp+88h] [rbp-78h]
  HLOCAL v101; // [rsp+90h] [rbp-70h] BYREF
  struct _RTL_CRITICAL_SECTION *v102; // [rsp+98h] [rbp-68h]
  struct _RWLOCK_CONTEXT *v103[2]; // [rsp+A0h] [rbp-60h] BYREF
  struct _PRIVILEGE_SET PrivilegeSet; // [rsp+B0h] [rbp-50h] BYREF
  _WORD *v105; // [rsp+C8h] [rbp-38h] BYREF
  int v106; // [rsp+D0h] [rbp-30h]
  int v107; // [rsp+D4h] [rbp-2Ch]
  HLOCAL *v108; // [rsp+D8h] [rbp-28h]
  __int64 v109; // [rsp+E0h] [rbp-20h]
  _WORD v110[13]; // [rsp+F8h] [rbp-8h] BYREF
  wchar_t Buffer[16]; // [rsp+118h] [rbp+18h] BYREF

  v10 = a3;
  ClientToken = a3;
  v100 = a2;
  v12 = this;
  v93 = this;
  v13 = a8;
  v92 = a8;
  v99 = a9;
  v101 = 0;
  UserData = 0;
  v96 = 0;
  v15 = (void *)*((_QWORD *)this + 44);
  if ( v15 )
  {
    WaitForSingleObject(v15, 0xFFFFFFFF);
LABEL_3:
    v13 = v92;
    goto LABEL_4;
  }
  if ( *(_DWORD *)&g_dwDebugLevel )
  {
    if ( g_lpDebugMsg )
    {
      g_lpDebugMsg(4u, L"WaitForServiceInitialization: Event is null.");
    }
    else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
    {
      RedirectDebugMsg(4u, L"WaitForServiceInitialization: Event is null.");
    }
    goto LABEL_3;
  }
LABEL_4:
  v16 = 2147483646;
  v17 = -1;
  v18 = a7;
  if ( (a7 & 0x10000000) != 0 )
  {
    v19 = a5;
    if ( !a5 && a4 )
    {
      a4 = 0;
      if ( *(_DWORD *)&g_dwDebugLevel )
      {
        if ( g_lpDebugMsg )
        {
          g_lpDebugMsg(4u, L"LockPolicySection[User] from session 0. Requesting console lock.");
        }
        else
        {
          if ( !g_lpDebugMsgContextInstance || !g_lpDebugMsgContext )
            goto LABEL_97;
          RedirectDebugMsg(4u, L"LockPolicySection[User] from session 0. Requesting console lock.");
        }
        v18 = a7;
      }
LABEL_97:
      v18 |= 0x20u;
      a7 = v18;
      goto LABEL_50;
    }
    v20 = (char *)v12 + 8;
    *(_QWORD *)GrantedAccess = (char *)v12 + 8;
    v97 = 0;
    if ( (unsigned int)CGPUserCollection::RWLock((char *)v12 + 8, a2, 0, &v97, v13) )
      goto LABEL_253;
    v96 = 0;
    v21 = (_QWORD *)**((_QWORD **)v12 + 7);
    if ( v21 )
    {
      v22 = (_QWORD *)*v21;
      while ( 1 )
      {
        v22 = (_QWORD *)*v22;
        v23 = (_QWORD *)**((_QWORD **)v20 + 6);
        v24 = v23 ? (_QWORD *)*v23 : 0LL;
        if ( v22 == v24 )
          break;
        v91 = 0;
        v25 = v22[2];
        v103[0] = (struct _RWLOCK_CONTEXT *)v25;
        if ( v25 )
          (**(void (__fastcall ***)(__int64))v25)(v25);
        hMem = 0;
        v91 = 0;
        v26 = v25 + 184;
        v27 = *(_QWORD *)(v25 + 184);
        if ( a4 )
        {
          if ( (*(unsigned int (__fastcall **)(__int64, HLOCAL *))(v27 + 64))(v26, &hMem) )
          {
            if ( hMem )
              hMem = LocalFree(hMem);
          }
          else
          {
            if ( a4 == hMem || (v59 = CompareStringW(0x7Fu, 1u, a4, -1, (PCNZWCH)hMem, -1), v59 == 2) )
            {
              v60 = 0;
            }
            else
            {
              v86 = v59 - 1;
              if ( v86 )
              {
                if ( v86 == 2 )
                  v60 = 1;
                else
                  v60 = -2;
              }
              else
              {
                v60 = -1;
              }
            }
            v91 = v60 == 0;
            if ( hMem )
              hMem = LocalFree(hMem);
          }
        }
        else
        {
          (*(void (__fastcall **)(__int64, BOOL *))(v27 + 16))(v26, &v91);
          if ( hMem )
            hMem = LocalFree(hMem);
        }
        if ( v25 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 8LL))(v25);
        if ( v91 )
        {
          UserData = (PSECURITY_DESCRIPTOR *)v22[2];
          v96 = UserData;
          break;
        }
      }
    }
    v28 = (struct _RWLOCK_CONTEXT **)v97;
    if ( *(_DWORD *)&g_dwDebugLevel )
    {
      if ( g_lpDebugMsg )
      {
        g_lpDebugMsg(4u, L"CGPUserCollection::RWUnlock called");
      }
      else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
      {
        RedirectDebugMsg(4u, L"CGPUserCollection::RWUnlock called");
      }
    }
    if ( !*((_DWORD *)v28 + 3) )
    {
      v29 = (struct _RTL_CRITICAL_SECTION *)*((_QWORD *)v20 + 5);
      if ( v29 )
      {
        EnterCriticalSection(*((LPCRITICAL_SECTION *)v20 + 5));
        v30 = *((_QWORD *)v93 + 18);
        if ( v30 )
        {
          for ( i = **(_QWORD ***)v30; ; i = (_QWORD *)*i )
          {
            if ( i == *(_QWORD **)v30 )
            {
              v20 = *(char **)GrantedAccess;
              goto LABEL_28;
            }
            v36 = (struct _RWLOCK_CONTEXT **)i[2];
            if ( v36 == v28 )
              break;
          }
          *(_QWORD *)i[1] = *i;
          *(_QWORD *)(*i + 8LL) = i[1];
          --*(_QWORD *)(v30 + 8);
          operator delete(i);
          LeaveCriticalSection(v29);
          v53 = v36 == 0;
          v20 = *(char **)GrantedAccess;
          if ( v53 )
            goto LABEL_43;
LABEL_124:
          v70 = v93;
          if ( *((_DWORD *)*v28 + 4) )
          {
            v37 = CRWLock::WriterUnLock((CGPApplicationService *)((char *)v93 + 64), v28);
LABEL_140:
            if ( v37 && *(_DWORD *)&g_dwDebugLevel )
            {
              if ( g_lpDebugMsg )
              {
                g_lpDebugMsg(2u, L"UnLock failed with 0x%x", v37);
              }
              else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
              {
                RedirectDebugMsg(2u, L"UnLock failed with 0x%x", v37);
              }
            }
            goto LABEL_44;
          }
          v71 = (struct _RTL_CRITICAL_SECTION *)*((_QWORD *)v93 + 17);
          v102 = v71;
          if ( v71 )
            EnterCriticalSection(v71);
          AccessStatus = 0;
          v53 = (*((_DWORD *)v70 + 16))-- == 1;
          if ( !v53 )
            goto LABEL_132;
          v72 = (_QWORD *)*((_QWORD *)v70 + 11);
          if ( !v72 || !v72[1] )
          {
            if ( *(_DWORD *)&g_dwDebugLevel )
            {
              if ( g_lpDebugMsg )
              {
                g_lpDebugMsg(4u, L"Setting lock state as notLocked");
              }
              else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
              {
                RedirectDebugMsg(4u, L"Setting lock state as notLocked");
              }
            }
            *((_DWORD *)v70 + 19) = 0;
            goto LABEL_132;
          }
          v97 = *(HLOCAL *)(*(_QWORD *)*v72 + 16LL);
          v103[0] = (struct _RWLOCK_CONTEXT *)v97;
          STLWrap_List<_NOTIFY_CALLER_INFO *>::pop_front((char *)v70 + 88);
          v87 = (HANDLE *)v97;
          if ( !v97 )
          {
            v37 = 1359;
            goto LABEL_133;
          }
          if ( *(_DWORD *)&g_dwDebugLevel )
          {
            if ( g_lpDebugMsg )
            {
              g_lpDebugMsg(4u, L"Signalling first writer with ID [%d]", *(unsigned int *)v97);
            }
            else
            {
              if ( !g_lpDebugMsgContextInstance || !g_lpDebugMsgContext )
                goto LABEL_238;
              RedirectDebugMsg(4u, L"Signalling first writer with ID [%d]", *(unsigned int *)v97);
            }
            v87 = (HANDLE *)v97;
          }
LABEL_238:
          SetEvent(v87[1]);
          CRWLock::FreeLockContext(v88, v103);
          *((_DWORD *)v70 + 19) = 2;
LABEL_132:
          v37 = AccessStatus;
LABEL_133:
          if ( *v28 )
          {
            v73 = (void *)*((_QWORD *)*v28 + 1);
            if ( v73 )
              CloseHandle(v73);
            *((_QWORD *)*v28 + 1) = 0;
            LocalFree(*v28);
            *v28 = 0;
          }
          if ( v71 )
            LeaveCriticalSection(v71);
          v20 = *(char **)GrantedAccess;
          goto LABEL_140;
        }
LABEL_28:
        LeaveCriticalSection(v29);
      }
LABEL_43:
      v37 = 0;
      if ( *(_DWORD *)&g_dwDebugLevel )
      {
        if ( g_lpDebugMsg )
        {
          g_lpDebugMsg(2u, L"The reader was not present in the list.");
        }
        else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
        {
          RedirectDebugMsg(2u, L"The reader was not present in the list.");
        }
      }
LABEL_44:
      LocalFree(v28);
      if ( *(_DWORD *)&g_dwDebugLevel )
      {
        if ( g_lpDebugMsg )
        {
          g_lpDebugMsg(4u, L"CGPUserCollection::RWUnlock exited with 0x%x", v37);
        }
        else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
        {
          RedirectDebugMsg(4u, L"CGPUserCollection::RWUnlock exited with 0x%x", v37);
        }
      }
      if ( UserData )
      {
        v38 = (struct _RTL_CRITICAL_SECTION *)UserData;
LABEL_47:
        v102 = v38;
        ((void (__fastcall *)(struct _RTL_CRITICAL_SECTION *))v38->DebugInfo->Type)(v38);
        LastError = (*((__int64 (__fastcall **)(HANDLE *, HLOCAL *))v38[4].LockSemaphore + 8))(
                      &v38[4].LockSemaphore,
                      &v101);
        ((void (__fastcall *)(struct _RTL_CRITICAL_SECTION *))v38->DebugInfo->CriticalSection)(v38);
        if ( LastError )
          goto LABEL_83;
        a4 = (const unsigned __int16 *)v101;
        if ( v101 && *(_DWORD *)&g_dwDebugLevel )
        {
          if ( g_lpDebugMsg )
          {
            g_lpDebugMsg(4u, L"Session %d SID set to : %s", a5, v101);
          }
          else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
          {
            RedirectDebugMsg(4u, L"Session %d SID set to : %s", a5, v101);
          }
        }
        LOBYTE(v18) = a7;
        v10 = ClientToken;
        v12 = v93;
        goto LABEL_50;
      }
      v19 = a5;
LABEL_253:
      if ( !a4 )
      {
        LastError = 1168;
        goto LABEL_83;
      }
      if ( *(_DWORD *)&g_dwDebugLevel )
      {
        if ( g_lpDebugMsg )
        {
          g_lpDebugMsg(4u, L"Could not find user by sid, finding user by session id");
        }
        else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
        {
          RedirectDebugMsg(4u, L"Could not find user by sid, finding user by session id");
        }
      }
      if ( !v19 )
      {
        if ( *(_DWORD *)&g_dwDebugLevel )
        {
          if ( g_lpDebugMsg )
          {
            g_lpDebugMsg(4u, L"Caller requesting for user notification/lock is from session 0");
          }
          else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
          {
            RedirectDebugMsg(4u, L"Caller requesting for user notification/lock is from session 0");
          }
        }
        LastError = 87;
        goto LABEL_83;
      }
      UserDataBasedOnSessionId = CGPUserCollection::GetUserDataBasedOnSessionId((CGPUserCollection *)v20, v19, v92);
      v38 = (struct _RTL_CRITICAL_SECTION *)UserDataBasedOnSessionId;
      if ( !UserDataBasedOnSessionId )
      {
        LastError = 5;
        goto LABEL_83;
      }
      UserData = (PSECURITY_DESCRIPTOR *)UserDataBasedOnSessionId;
      v96 = (PSECURITY_DESCRIPTOR *)UserDataBasedOnSessionId;
      goto LABEL_47;
    }
    if ( *((_DWORD *)v28 + 2) )
    {
      if ( *(_DWORD *)&g_dwDebugLevel )
      {
        if ( g_lpDebugMsg )
        {
          g_lpDebugMsg(4u, L"Cancelling lock in UnLock .");
        }
        else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
        {
          RedirectDebugMsg(4u, L"Cancelling lock in UnLock .");
        }
      }
      v37 = CRWLock::CancelLock((CGPApplicationService *)((char *)v93 + 64), v28);
      if ( v37 && *(_DWORD *)&g_dwDebugLevel )
      {
        if ( g_lpDebugMsg )
        {
          g_lpDebugMsg(2u, L"CancelLock failed with 0x%x", v37);
        }
        else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
        {
          RedirectDebugMsg(2u, L"CancelLock failed with 0x%x", v37);
        }
      }
      goto LABEL_44;
    }
    goto LABEL_124;
  }
  if ( a2 )
  {
    UserData = (PSECURITY_DESCRIPTOR *)CGPUserCollection::GetUserData(
                                         (CGPApplicationService *)((char *)v12 + 8),
                                         a4,
                                         v13);
    v96 = UserData;
    v32 = a7 & 0x20;
LABEL_31:
    if ( v32 )
    {
      LastError = CGPApplicationService::AccessCheckForConsoleSession(v12, v10, 4u);
    }
    else if ( UserData )
    {
      v102 = (struct _RTL_CRITICAL_SECTION *)UserData;
      (*(void (__fastcall **)(PSECURITY_DESCRIPTOR *))*UserData)(UserData);
      LastError = 0;
      *(_OWORD *)v103 = 0;
      GrantedAccess[0] = 0;
      AccessStatus = 0;
      v34 = v103;
      if ( UserData != (PSECURITY_DESCRIPTOR *)-424LL )
        v34 = (struct _RWLOCK_CONTEXT **)(UserData + 53);
      memset(&PrivilegeSet, 0, sizeof(PrivilegeSet));
      LODWORD(hMem) = 20;
      if ( !AccessCheck(
              UserData[52],
              ClientToken,
              4u,
              (PGENERIC_MAPPING)v34,
              &PrivilegeSet,
              (LPDWORD)&hMem,
              GrantedAccess,
              &AccessStatus) )
      {
        LastError = GetLastError();
        if ( *(_DWORD *)&g_dwDebugLevel )
        {
          if ( g_lpDebugMsg )
          {
            g_lpDebugMsg(2u, L"AccessCheckBasedOnSD:  AccessCheck failed with %d.", LastError);
          }
          else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
          {
            RedirectDebugMsg(2u, L"AccessCheckBasedOnSD:  AccessCheck failed with %d.", LastError);
          }
        }
        if ( LastError )
          goto LABEL_282;
      }
      if ( AccessStatus )
      {
        (*((void (__fastcall **)(PSECURITY_DESCRIPTOR *))*UserData + 1))(UserData);
      }
      else
      {
LABEL_282:
        LastError = 5;
        if ( *(_DWORD *)&g_dwDebugLevel )
        {
          if ( g_lpDebugMsg )
          {
            g_lpDebugMsg(2u, L"AccessCheckBasedOnSD:  returning %d.", 5);
          }
          else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
          {
            RedirectDebugMsg(2u, L"AccessCheckBasedOnSD:  returning %d.", 5);
          }
        }
        LODWORD(v97) = 5;
        _itow(4105, Buffer, 10);
        v78 = 2147483646;
        v76 = L"%%";
        v81 = 13;
        v79 = 13;
        v77 = v110;
        while ( v78 )
        {
          v75 = *v76;
          if ( !*v76 )
            break;
          ++v76;
          *v77++ = v75;
          --v78;
          if ( !--v79 )
          {
            *(v77 - 1) = 0;
            goto LABEL_188;
          }
        }
        *v77 = 0;
        v80 = v110;
        v78 = a7;
        while ( *v80 )
        {
          ++v80;
          --v81;
          UserData = v96;
          if ( !v81 )
          {
            LOWORD(v82) = 87;
            goto LABEL_174;
          }
        }
        v96 = UserData;
        v78 = 2147483646;
        v76 = Buffer;
        v83 = Buffer - v81 + 2;
        v91 = 0;
        while ( v78 )
        {
          v84 = *v76;
          if ( !*v76 )
            break;
          ++v76;
          *v83++ = v84;
          --v78;
          if ( !--v81 )
          {
            --v83;
            v82 = -2147024774;
            goto LABEL_182;
          }
        }
        v82 = v91;
LABEL_182:
        *v83 = 0;
        if ( v82 >= 0 )
          goto LABEL_183;
LABEL_174:
        if ( (_WORD)v82 )
          goto LABEL_187;
LABEL_183:
        v85 = -1;
        do
          ++v85;
        while ( v110[v85] );
        v105 = v110;
        v106 = 2 * v85 + 2;
        v107 = 0;
        v108 = &v97;
        v109 = 4;
        if ( (unsigned int)EtwEventWrite(
                             CGPServiceEventReporting::s_pEventProviderHandle,
                             OPERATIONAL_ERROR_MESSAGE,
                             2,
                             &v105) )
          GetLastError();
LABEL_187:
        UserData = v96;
LABEL_188:
        (*((void (__fastcall **)(PSECURITY_DESCRIPTOR *, __int64, wchar_t *))*UserData + 1))(UserData, v78, v76);
      }
      v12 = v93;
    }
    else
    {
      LastError = AccessCheckBasedOnSD(*((void **)v12 + 27), v10, 2u, 0);
    }
    if ( LastError )
    {
      if ( *(_DWORD *)&g_dwDebugLevel )
      {
        if ( g_lpDebugMsg )
        {
          g_lpDebugMsg(2u, L"AccessCheckForLock failed with 0x%x", LastError);
        }
        else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
        {
          RedirectDebugMsg(2u, L"AccessCheckForLock failed with 0x%x", LastError);
        }
      }
      goto LABEL_83;
    }
    v35 = v100;
    goto LABEL_51;
  }
LABEL_50:
  v32 = v18 & 0x20;
  v35 = v100;
  if ( v100 )
    goto LABEL_31;
LABEL_51:
  if ( !v32 )
  {
    v39 = (struct _RTL_CRITICAL_SECTION *)*((_QWORD *)v12 + 24);
    if ( !v39 )
    {
      LastError = 0;
      goto LABEL_83;
    }
    v102 = v39;
    EnterCriticalSection(v39);
    v40 = v93;
    v41 = (__int64 ***)*((_QWORD *)v93 + 25);
    if ( v41 )
    {
      v42 = *v41;
      while ( 1 )
      {
        while ( 1 )
        {
          v42 = (__int64 **)*v42;
          v43 = (__int64 **)*((_QWORD *)v40 + 25);
          if ( v43 )
            v43 = (__int64 **)*v43;
          if ( v42 == v43 )
            goto LABEL_58;
          v52 = (const WCHAR *)*v42[2];
          if ( a4 )
            break;
          v53 = v52 == 0;
LABEL_72:
          if ( v53 )
          {
            v54 = (volatile signed __int32 *)v42[2];
            if ( !v54 )
              goto LABEL_58;
            goto LABEL_74;
          }
        }
        if ( v52 )
        {
          v53 = CompareStringW(0x7Fu, 1u, v52, -1, a4, -1) == 2;
          goto LABEL_72;
        }
      }
    }
LABEL_58:
    v44 = (struct _RWLOCK_CONTEXT *)operator new(0xD0u, (const struct std::nothrow_t *)&std::nothrow);
    v103[0] = v44;
    if ( v44 )
      v45 = AccountPolicyCriticalSection::AccountPolicyCriticalSection(v44);
    else
      v45 = 0;
    ClientToken = v45;
    if ( !v45 )
      goto LABEL_114;
    if ( a4 )
    {
      do
        ++v17;
      while ( a4[v17] );
      v46 = v17 + 1;
      v47 = (WCHAR *)LocalAlloc(0x40u, 2 * (v17 + 1));
      v49 = v47;
      *(_QWORD *)v45 = v47;
      if ( !v47 )
      {
        if ( *(_DWORD *)&g_dwDebugLevel )
        {
          if ( g_lpDebugMsg )
          {
            g_lpDebugMsg(2u, L"Failed to allocate %d bytes for sid", v17 + 1);
          }
          else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
          {
            RedirectDebugMsg(2u, L"Failed to allocate %d bytes for sid", v17 + 1);
          }
        }
        goto LABEL_161;
      }
      v50 = 0;
      if ( v17 != -1 )
      {
        if ( v46 > 0x7FFFFFFF )
        {
          *v47 = 0;
        }
        else
        {
          while ( v16 )
          {
            v51 = *a4;
            if ( !*a4 )
              break;
            ++a4;
            *v49++ = v51;
            --v16;
            if ( !--v46 )
            {
              --v49;
              break;
            }
          }
          *v49 = 0;
        }
      }
      if ( *(_DWORD *)&g_dwDebugLevel )
      {
        if ( g_lpDebugMsg )
        {
          g_lpDebugMsg(4u, L"SID = %ws", *(_QWORD *)v45);
          v50 = 0;
        }
        else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
        {
          RedirectDebugMsg(4u, L"SID = %ws", *(_QWORD *)v45);
          v50 = 0;
        }
      }
    }
    else
    {
      v50 = 1;
    }
    if ( *(_DWORD *)&g_dwDebugLevel )
    {
      if ( g_lpDebugMsg )
      {
        g_lpDebugMsg(4u, L"bMachine = %d ", v50);
      }
      else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
      {
        RedirectDebugMsg(4u, L"bMachine = %d ", v50);
      }
    }
    v61 = (struct _RWLOCK_CONTEXT *)operator new(0x50u, (const struct std::nothrow_t *)&std::nothrow);
    v62 = v61;
    v103[0] = v61;
    if ( v61 )
    {
      *(_QWORD *)v61 = 0;
      *((_QWORD *)v61 + 1) = 0;
      STLWrap_List<CPolicyCriticalSection::CLockCallbackContext *>::STLWrap_List<CPolicyCriticalSection::CLockCallbackContext *>((char *)v61 + 16);
      STLWrap_List<CPolicyCriticalSection::CLockCallbackContext *>::STLWrap_List<CPolicyCriticalSection::CLockCallbackContext *>((char *)v62 + 24);
      XCritSec::XCritSec((struct _RWLOCK_CONTEXT *)((char *)v62 + 32));
    }
    else
    {
      v62 = 0;
    }
    v63 = (CRWLock *)*((_QWORD *)v45 + 2);
    if ( v63 )
      CRWLock::`scalar deleting destructor'(v63);
    *((_QWORD *)v45 + 2) = v62;
    if ( v62 )
    {
      v64 = (struct _RWLOCK_CONTEXT *)operator new(0x50u, (const struct std::nothrow_t *)&std::nothrow);
      v65 = v64;
      v103[0] = v64;
      if ( v64 )
      {
        *(_QWORD *)v64 = 0;
        *((_QWORD *)v64 + 1) = 0;
        STLWrap_List<CPolicyCriticalSection::CLockCallbackContext *>::STLWrap_List<CPolicyCriticalSection::CLockCallbackContext *>((char *)v64 + 16);
        STLWrap_List<CPolicyCriticalSection::CLockCallbackContext *>::STLWrap_List<CPolicyCriticalSection::CLockCallbackContext *>((char *)v65 + 24);
        XCritSec::XCritSec((struct _RWLOCK_CONTEXT *)((char *)v65 + 32));
      }
      else
      {
        v65 = 0;
      }
      v66 = (CRWLock *)*((_QWORD *)v45 + 14);
      if ( v66 )
        CRWLock::`scalar deleting destructor'(v66);
      *((_QWORD *)v45 + 14) = v65;
      if ( v65 )
      {
        if ( !(unsigned int)STLWrap_List<AccountPolicyCriticalSection *>::push_front((char *)v40 + 200, &ClientToken) )
        {
          v54 = (volatile signed __int32 *)ClientToken;
          goto LABEL_113;
        }
        v74 = (AccountPolicyCriticalSection *)ClientToken;
        if ( !ClientToken )
        {
LABEL_163:
          v54 = 0;
LABEL_113:
          if ( !v54 )
          {
LABEL_114:
            LastError = 6;
            LeaveCriticalSection(v39);
            goto LABEL_83;
          }
LABEL_74:
          v55 = 30;
          if ( (a7 & 2) == 0 )
            v55 = 6;
          _InterlockedIncrement(&v54[v55]);
          LeaveCriticalSection(v39);
          if ( (a7 & 2) != 0 )
          {
            if ( !v99 )
            {
              LastError = 87;
              goto LABEL_82;
            }
            v56 = (CPolicyCriticalSection *)(v54 + 28);
          }
          else
          {
            if ( !v99 )
            {
              LastError = 87;
              goto LABEL_82;
            }
            v56 = (CPolicyCriticalSection *)(v54 + 4);
          }
          if ( v100 )
            v57 = CPolicyCriticalSection::AsyncLock(
                    v56,
                    *(const unsigned __int16 **)v54,
                    v100,
                    (__int64)v99,
                    a7,
                    v92,
                    v99);
          else
            v57 = CPolicyCriticalSection::SyncLock(v56, *(const unsigned __int16 **)v54, a6, a7, v92, v99);
          LastError = v57;
LABEL_82:
          if ( LastError )
          {
            if ( (a7 & 2) != 0 )
              _InterlockedDecrement(v54 + 30);
            else
              _InterlockedDecrement(v54 + 6);
          }
          goto LABEL_83;
        }
LABEL_162:
        AccountPolicyCriticalSection::`scalar deleting destructor'(v74, v48);
        goto LABEL_163;
      }
    }
LABEL_161:
    v74 = v45;
    goto LABEL_162;
  }
  v67 = (const unsigned __int16 **)*((_QWORD *)v12 + 35);
  v68 = *v67;
  if ( (a7 & 2) != 0 )
  {
    if ( !v99 )
    {
      LastError = 87;
      goto LABEL_83;
    }
    v69 = (CPolicyCriticalSection *)(v67 + 14);
  }
  else
  {
    if ( !v99 )
    {
      LastError = 87;
      goto LABEL_83;
    }
    v69 = (CPolicyCriticalSection *)(v67 + 2);
  }
  if ( v35 )
    LastError = CPolicyCriticalSection::AsyncLock(v69, v68, v35, (__int64)v99, a7, v92, v99);
  else
    LastError = CPolicyCriticalSection::SyncLock(v69, v68, a6, a7, v92, v99);
LABEL_83:
  if ( v101 )
    LocalFree(v101);
  return LastError;
}

```

## disassembly

```asm
0x18000e5f0  mov     [rsp-8+arg_8], rbx
0x18000e5f5  push    rbp
0x18000e5f6  push    rsi
0x18000e5f7  push    rdi
0x18000e5f8  push    r12
0x18000e5fa  push    r13
0x18000e5fc  push    r14
0x18000e5fe  push    r15
0x18000e600  lea     rbp, [rsp-40h]
0x18000e605  sub     rsp, 140h
0x18000e60c  mov     rax, cs:__security_cookie
0x18000e613  xor     rax, rsp
0x18000e616  mov     [rbp+70h+var_38], rax
0x18000e61a  mov     rsi, r9
0x18000e61d  mov     r13, r8
0x18000e620  mov     [rsp+170h+ClientToken], r8
0x18000e625  mov     rbx, rdx
0x18000e628  mov     [rbp+70h+var_E8], rdx
0x18000e62c  mov     rdi, rcx
0x18000e62f  mov     [rsp+170h+var_120], rcx
0x18000e634  mov     rax, [rbp+70h+arg_38]
0x18000e63b  mov     [rsp+170h+var_128], rax
0x18000e640  mov     rcx, [rbp+70h+arg_40]
0x18000e647  mov     [rbp+70h+var_F0], rcx
0x18000e64b  mov     [rbp+70h+var_E0], 0
0x18000e653  xor     r12d, r12d
0x18000e656  mov     [rsp+170h+var_108], r12
0x18000e65b  mov     rcx, [rdi+160h]; hHandle
0x18000e662  test    rcx, rcx
0x18000e665  jz      loc_18000F1F2
0x18000e66b  mov     edx, 0FFFFFFFFh; dwMilliseconds
0x18000e670  call    cs:__imp_WaitForSingleObject
0x18000e676  mov     rax, [rsp+170h+var_128]
0x18000e67b  mov     r14d, 7FFFFFFEh
0x18000e681  mov     r15, 0FFFFFFFFFFFFFFFFh
0x18000e688  mov     ecx, [rbp+70h+arg_30]
0x18000e68e  bt      ecx, 1Ch
0x18000e692  jnb     loc_18000E7F9
0x18000e698  mov     ebx, [rbp+70h+arg_20]
0x18000e69e  test    ebx, ebx
0x18000e6a0  jz      loc_18000EC58
0x18000e6a6  lea     r13, [rdi+8]
0x18000e6aa  mov     qword ptr [rsp+170h+var_F8], r13
0x18000e6af  mov     [rsp+170h+var_100], r12
0x18000e6b4  mov     [rsp+170h+PrivilegeSet], rax
0x18000e6b9  lea     r9, [rsp+170h+var_100]
0x18000e6be  xor     r8d, r8d
0x18000e6c1  mov     rcx, r13
0x18000e6c4  call    ?RWLock@CGPUserCollection@@QEAAKKW4LockType@@PEAPEAXPEAX@Z; CGPUserCollection::RWLock(ulong,LockType,void * *,void *)
0x18000e6c9  test    eax, eax
0x18000e6cb  jnz     loc_18000F5CE
0x18000e6d1  xor     ecx, ecx
0x18000e6d3  mov     [rsp+170h+var_108], rcx
0x18000e6d8  mov     rax, [r13+30h]
0x18000e6dc  mov     rbx, [rax]
0x18000e6df  test    rbx, rbx
0x18000e6e2  jz      loc_18000E794
0x18000e6e8  mov     rbx, [rbx]
0x18000e6eb  mov     rbx, [rbx]
0x18000e6ee  mov     rax, [r13+30h]
0x18000e6f2  mov     rax, [rax]
0x18000e6f5  test    rax, rax
0x18000e6f8  jz      loc_18000EBD9
0x18000e6fe  mov     rax, [rax]
0x18000e701  cmp     rbx, rax
0x18000e704  jz      loc_18000E794
0x18000e70a  mov     [rsp+170h+var_12C], ecx
0x18000e70e  mov     rdi, [rbx+10h]
0x18000e712  mov     [rbp+70h+var_D0], rdi
0x18000e716  test    rdi, rdi
0x18000e719  jz      short loc_18000E72B
0x18000e71b  mov     rax, [rdi]
0x18000e71e  mov     rcx, rdi
0x18000e721  mov     rax, [rax]
0x18000e724  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e729  xor     ecx, ecx
0x18000e72b  mov     [rsp+170h+hMem], rcx
0x18000e730  mov     [rsp+170h+var_12C], ecx
0x18000e734  lea     rcx, [rdi+0B8h]
0x18000e73b  mov     rax, [rcx]
0x18000e73e  test    rsi, rsi
0x18000e741  jnz     loc_18000EBE1
0x18000e747  lea     rdx, [rsp+170h+var_12C]
0x18000e74c  mov     rax, [rax+10h]
0x18000e750  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e755  nop
0x18000e756  mov     rcx, [rsp+170h+hMem]; hMem
0x18000e75b  test    rcx, rcx
0x18000e75e  jz      short loc_18000E76B
0x18000e760  call    cs:__imp_LocalFree
0x18000e766  mov     [rsp+170h+hMem], rax
0x18000e76b  test    rdi, rdi
0x18000e76e  jz      short loc_18000E780
0x18000e770  mov     rax, [rdi]
0x18000e773  mov     rcx, rdi
0x18000e776  mov     rax, [rax+8]
0x18000e77a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e77f  nop
0x18000e780  cmp     [rsp+170h+var_12C], 0
0x18000e785  jz      loc_18000EC51
0x18000e78b  mov     r12, [rbx+10h]
0x18000e78f  mov     [rsp+170h+var_108], r12
0x18000e794  mov     rdi, [rsp+170h+var_100]
0x18000e799  cmp     cs:?g_dwDebugLevel@@3KA, 0; ulong g_dwDebugLevel
0x18000e7a0  jnz     loc_18000F2CC
0x18000e7a6  cmp     dword ptr [rdi+0Ch], 0
0x18000e7aa  jnz     loc_18000EE3D
0x18000e7b0  mov     rbx, [r13+28h]
0x18000e7b4  test    rbx, rbx
0x18000e7b7  jz      loc_18000E947
0x18000e7bd  mov     rcx, rbx; lpCriticalSection
0x18000e7c0  call    cs:__imp_EnterCriticalSection
0x18000e7c6  mov     rcx, [rsp+170h+var_120]
0x18000e7cb  mov     r8, [rcx+90h]
0x18000e7d2  test    r8, r8
0x18000e7d5  jz      short loc_18000E7EB
0x18000e7d7  mov     rax, [r8]
0x18000e7da  mov     rcx, [rax]; Block
0x18000e7dd  cmp     rcx, rax
0x18000e7e0  jnz     loc_18000E905
0x18000e7e6  mov     r13, qword ptr [rsp+170h+var_F8]
0x18000e7eb  mov     rcx, rbx; lpCriticalSection
0x18000e7ee  call    cs:__imp_LeaveCriticalSection
0x18000e7f4  jmp     loc_18000E947
0x18000e7f9  test    rbx, rbx
0x18000e7fc  jz      loc_18000E9DA
0x18000e802  lea     rcx, [rdi+8]; this
0x18000e806  mov     r8, rax; void *
0x18000e809  mov     rdx, rsi; unsigned __int16 *
0x18000e80c  call    ?GetUserData@CGPUserCollection@@QEAAPEAVCGroupPolicySession@@PEBGPEAX@Z; CGPUserCollection::GetUserData(ushort const *,void *)
0x18000e811  mov     r12, rax
0x18000e814  mov     [rsp+170h+var_108], rax
0x18000e819  mov     ebx, [rbp+70h+arg_30]
0x18000e81f  and     ebx, 20h
0x18000e822  test    ebx, ebx
0x18000e824  jnz     loc_18000F06A
0x18000e82a  test    r12, r12
0x18000e82d  jz      loc_18000F03A
0x18000e833  mov     [rbp+70h+var_D8], r12
0x18000e837  mov     rax, [r12]
0x18000e83b  mov     rcx, r12
0x18000e83e  mov     rax, [rax]
0x18000e841  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e846  nop
0x18000e847  lea     rax, [r12+1A8h]
0x18000e84f  xor     edi, edi
0x18000e851  mov     r13d, edi
0x18000e854  xorps   xmm0, xmm0
0x18000e857  movups  xmmword ptr [rbp+70h+var_D0], xmm0
0x18000e85b  mov     [rsp+170h+var_F8], edi
0x18000e85f  mov     [rsp+170h+var_130], edi
0x18000e863  lea     r9, [rbp+70h+var_D0]
0x18000e867  test    rax, rax
0x18000e86a  cmovnz  r9, rax; GenericMapping
0x18000e86e  xor     eax, eax
0x18000e870  movups  xmmword ptr [rbp+70h+var_C0.PrivilegeCount], xmm0
0x18000e874  mov     [rbp+70h+var_C0.Privilege.Attributes], eax
0x18000e877  mov     dword ptr [rsp+170h+hMem], 14h
0x18000e87f  lea     rax, [rsp+170h+var_130]
0x18000e884  mov     [rsp+170h+AccessStatus], rax; AccessStatus
0x18000e889  lea     rax, [rsp+170h+var_F8]
0x18000e88e  mov     [rsp+170h+GrantedAccess], rax; GrantedAccess
0x18000e893  lea     rax, [rsp+170h+hMem]
0x18000e898  mov     [rsp+170h+PrivilegeSetLength], rax; PrivilegeSetLength
0x18000e89d  lea     rax, [rbp+70h+var_C0]
0x18000e8a1  mov     [rsp+170h+PrivilegeSet], rax; PrivilegeSet
0x18000e8a6  mov     r8d, 4; DesiredAccess
0x18000e8ac  mov     rdx, [rsp+170h+ClientToken]; ClientToken
0x18000e8b1  mov     rcx, [r12+1A0h]; pSecurityDescriptor
0x18000e8b9  call    cs:__imp_AccessCheck
0x18000e8bf  test    eax, eax
0x18000e8c1  jz      loc_18000F6F2
0x18000e8c7  cmp     [rsp+170h+var_130], edi
0x18000e8cb  jz      loc_18000F754
0x18000e8d1  mov     edi, [rbp+70h+arg_30]
0x18000e8d7  mov     [rbp+70h+arg_30], edi
0x18000e8dd  mov     rax, [r12]
0x18000e8e1  mov     rcx, r12
0x18000e8e4  mov     rax, [rax+8]
0x18000e8e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e8ed  nop
0x18000e8ee  mov     rdi, [rsp+170h+var_120]
0x18000e8f3  test    r13d, r13d
0x18000e8f6  jnz     loc_18000EFFC
0x18000e8fc  mov     r8, [rbp+70h+var_E8]
0x18000e900  jmp     loc_18000E9EC
0x18000e905  mov     r13, [rcx+10h]
0x18000e909  mov     rdx, [rcx]
0x18000e90c  cmp     r13, rdi
0x18000e90f  jnz     loc_18000F083
0x18000e915  mov     rax, [rcx+8]
0x18000e919  mov     [rax], rdx
0x18000e91c  mov     rdx, [rcx]
0x18000e91f  mov     rax, [rcx+8]
0x18000e923  mov     [rdx+8], rax
0x18000e927  dec     qword ptr [r8+8]
0x18000e92b  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000e930  mov     rcx, rbx; lpCriticalSection
0x18000e933  call    cs:__imp_LeaveCriticalSection
0x18000e939  test    r13, r13
0x18000e93c  mov     r13, qword ptr [rsp+170h+var_F8]
0x18000e941  jnz     loc_18000EE47
0x18000e947  xor     ebx, ebx
0x18000e949  cmp     cs:?g_dwDebugLevel@@3KA, ebx; ulong g_dwDebugLevel
0x18000e94f  jnz     loc_18000F320
0x18000e955  mov     rcx, rdi; hMem
0x18000e958  call    cs:__imp_LocalFree
0x18000e95e  cmp     cs:?g_dwDebugLevel@@3KA, 0; ulong g_dwDebugLevel
0x18000e965  jnz     loc_18000F56E
0x18000e96b  test    r12, r12
0x18000e96e  jz      loc_18000F5C8
0x18000e974  mov     rbx, r12
0x18000e977  mov     [rbp+70h+var_D8], rbx
0x18000e97b  mov     rax, [rbx]
0x18000e97e  mov     rcx, rbx
0x18000e981  mov     rax, [rax]
0x18000e984  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e989  nop
0x18000e98a  lea     rcx, [rbx+0B8h]
0x18000e991  mov     rax, [rcx]
0x18000e994  lea     rdx, [rbp+70h+var_E0]
0x18000e998  mov     rax, [rax+40h]
0x18000e99c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e9a1  mov     r13d, eax
0x18000e9a4  mov     rax, [rbx]
0x18000e9a7  mov     rcx, rbx
0x18000e9aa  mov     rax, [rax+8]
0x18000e9ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e9b3  nop
0x18000e9b4  test    r13d, r13d
0x18000e9b7  jnz     loc_18000EBA0
0x18000e9bd  mov     rsi, [rbp+70h+var_E0]
0x18000e9c1  test    rsi, rsi
0x18000e9c4  jnz     loc_18000EF64
0x18000e9ca  mov     ecx, [rbp+70h+arg_30]
0x18000e9d0  mov     r13, [rsp+170h+ClientToken]
0x18000e9d5  mov     rdi, [rsp+170h+var_120]
0x18000e9da  mov     ebx, ecx
0x18000e9dc  and     ebx, 20h
0x18000e9df  mov     r8, [rbp+70h+var_E8]; struct _RPC_ASYNC_STATE *
0x18000e9e3  test    r8, r8
0x18000e9e6  jnz     loc_18000E822
0x18000e9ec  test    ebx, ebx
0x18000e9ee  jnz     loc_18000EDEA
0x18000e9f4  mov     rdi, [rdi+0C0h]
0x18000e9fb  test    rdi, rdi
0x18000e9fe  jz      loc_18000F9E1
0x18000ea04  mov     [rbp+70h+var_D8], rdi
0x18000ea08  mov     rcx, rdi; lpCriticalSection
0x18000ea0b  call    cs:__imp_EnterCriticalSection
0x18000ea11  nop
0x18000ea12  mov     r13, [rsp+170h+var_120]
0x18000ea17  mov     rbx, [r13+0C8h]
0x18000ea1e  test    rbx, rbx
0x18000ea21  jz      short loc_18000EA41
0x18000ea23  mov     rbx, [rbx]
0x18000ea26  mov     rbx, [rbx]
0x18000ea29  mov     rax, [r13+0C8h]
0x18000ea30  test    rax, rax
0x18000ea33  jz      short loc_18000EA38
0x18000ea35  mov     rax, [rax]
0x18000ea38  cmp     rbx, rax
0x18000ea3b  jnz     loc_18000EB02
0x18000ea41  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000ea48  mov     ecx, 0D0h; unsigned __int64
0x18000ea4d  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000ea52  mov     [rbp+70h+var_D0], rax
0x18000ea56  test    rax, rax
0x18000ea59  jz      loc_18000F032
0x18000ea5f  mov     rcx, rax; this
0x18000ea62  call    ??0AccountPolicyCriticalSection@@QEAA@XZ; AccountPolicyCriticalSection::AccountPolicyCriticalSection(void)
0x18000ea67  mov     r12, rax
0x18000ea6a  mov     [rsp+170h+ClientToken], r12
0x18000ea6f  test    r12, r12
0x18000ea72  jz      loc_18000ED9C
0x18000ea78  test    rsi, rsi
0x18000ea7b  jz      loc_18000F913
0x18000ea81  lea     r15, [r15+1]
0x18000ea85  cmp     word ptr [rsi+r15*2], 0
0x18000ea8b  jnz     short loc_18000EA81
0x18000ea8d  lea     rbx, [r15+1]
0x18000ea91  lea     rdx, [rbx+rbx]; uBytes
0x18000ea95  mov     ecx, 40h ; '@'; uFlags
0x18000ea9a  call    cs:__imp_LocalAlloc
0x18000eaa0  mov     rcx, rax
0x18000eaa3  mov     [r12], rax
0x18000eaa7  test    rax, rax
0x18000eaaa  jz      loc_18000F84F
0x18000eab0  xor     r15d, r15d
0x18000eab3  mov     edx, r15d
0x18000eab6  test    rbx, rbx
0x18000eab9  jz      loc_18000EC8A
0x18000eabf  cmp     rbx, 7FFFFFFFh
0x18000eac6  ja      loc_18000F8AA
0x18000eacc  nop     dword ptr [rax+00h]
0x18000ead0  test    r14, r14
0x18000ead3  jz      loc_18000EC86
0x18000ead9  movzx   eax, word ptr [rsi]
0x18000eadc  test    ax, ax
0x18000eadf  jz      loc_18000EC7D
  ... truncated ...
```
