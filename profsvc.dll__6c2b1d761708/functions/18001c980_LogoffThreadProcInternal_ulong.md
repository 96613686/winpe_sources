# LogoffThreadProcInternal(ulong)

- ea: `0x18001c980`
- end: `0x18001cb71`
- name: `?LogoffThreadProcInternal@@YAJK@Z`
- size: `497`
- prototype: `__int64 __fastcall(unsigned int)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, installer_update`

## callers

- `0x18001cde0`

## callees

- `0x1800084bc`
- `0x180008fa0`
- `0x180011ea4`
- `0x18001a858`
- `0x18001c130`
- `0x18001c4a0`
- `0x18001c85c`
- `0x18001c980`
- `0x18001e010`
- `0x180030ad0`
- `0x18003d678`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18001c9a2`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18001c9a2`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18001ca2b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18001ca2b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001cb32`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001cb32`
- `ext-ms-win-profile-profsvc-l1-1-0!InitializeSuspendFolderPolicyAndUploadTaskConfig` at `0x18001cabe`
- `ext-ms-win-profile-profsvc-l1-1-0!InitializeSuspendFolderPolicyAndUploadTaskConfig` at `0x18001cabe`

## pseudocode

```c
__int64 __fastcall LogoffThreadProcInternal(unsigned int a1)
{
  PSRWLOCK v1; // rbx
  __int64 v3; // rdx
  unsigned __int64 i; // r8
  __int64 v5; // rax
  __int64 v6; // rcx
  _QWORD *Ptr; // rdx
  __int64 v8; // rcx
  _QWORD *v9; // rax
  void *v10; // rdi
  int v11; // eax
  unsigned int v12; // ebx
  int MyOwnToken; // eax
  CUserProfileManager *v14; // rcx
  void *UserToken; // rbx
  __int64 v16; // rcx
  int v17; // eax
  int v19[76]; // [rsp+20h] [rbp-138h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+158h] [rbp+0h]
  unsigned int v21; // [rsp+160h] [rbp+8h]
  HANDLE hObject; // [rsp+168h] [rbp+10h] BYREF

  v1 = g_pProfMgr;
  v21 = a1;
  AcquireSRWLockShared(g_pProfMgr);
  v3 = 0xCBF29CE484222325uLL;
  for ( i = 0; i < 4; ++i )
  {
    v5 = *((unsigned __int8 *)&v21 + i);
    v3 = 0x100000001B3LL * (v5 ^ v3);
  }
  v6 = v3 & (__int64)v1[12].Ptr;
  Ptr = v1[9].Ptr;
  v8 = 2 * v6;
  v9 = (_QWORD *)Ptr[v8 + 1];
  if ( v9 == v1[7].Ptr )
  {
LABEL_7:
    v9 = 0;
  }
  else
  {
    while ( a1 != *((_DWORD *)v9 + 4) )
    {
      if ( v9 == (_QWORD *)Ptr[v8] )
        goto LABEL_7;
      v9 = (_QWORD *)v9[1];
    }
  }
  if ( !v9 )
    v9 = v1[7].Ptr;
  if ( v9 == v1[7].Ptr )
    v10 = 0;
  else
    v10 = (void *)v9[4];
  if ( v1 )
    ReleaseSRWLockShared(v1);
  v11 = WaitForEventInternal(v10);
  v12 = v11;
  if ( v11 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x36B,
      (unsigned int)`DaclContainsPackageAndLpacCapabilitySid_'::`2'::AppPackageAuthority.SubAuthority,
      (const char *)(unsigned int)v11,
      v19[0]);
    return v12;
  }
  hObject = 0;
  MyOwnToken = GetMyOwnToken(&hObject);
  v12 = MyOwnToken;
  if ( MyOwnToken < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x36F,
      (unsigned int)`DaclContainsPackageAndLpacCapabilitySid_'::`2'::AppPackageAuthority.SubAuthority,
      (const char *)(unsigned int)MyOwnToken,
      v19[0]);
LABEL_25:
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hObject);
    return v12;
  }
  UserToken = CUserProfileManager::GetUserToken(v14, a1);
  if ( (unsigned __int8)IsWaitForNetworkForRoamingProfilePresent(v16) )
    InitializeSuspendFolderPolicyAndUploadTaskConfig(UserToken, 0);
  UpdateRunLogonScriptSyncCache(UserToken);
  CUserProfile::CUserProfile((CUserProfile *)v19);
  v17 = CUserProfile::Unload((CUserProfile *)v19, hObject, UserToken, a1);
  v12 = v17;
  if ( v17 >= 0 )
  {
    CUserProfile::~CUserProfile((CUserProfile *)v19);
    v12 = 0;
    goto LABEL_25;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x381,
    (unsigned int)`DaclContainsPackageAndLpacCapabilitySid_'::`2'::AppPackageAuthority.SubAuthority,
    (const char *)(unsigned int)v17,
    v19[0]);
  CUserProfile::~CUserProfile((CUserProfile *)v19);
  if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    CloseHandle(hObject);
  return v12;
}

```

## disassembly

```asm
0x18001c980  mov     rax, rsp
0x18001c983  mov     [rax+18h], rbx
0x18001c987  mov     [rax+20h], rsi
0x18001c98b  push    rdi
0x18001c98c  sub     rsp, 150h
0x18001c993  mov     rbx, cs:?g_pProfMgr@@3PEAVCUserProfileManager@@EA; CUserProfileManager * g_pProfMgr
0x18001c99a  mov     esi, ecx
0x18001c99c  mov     [rax+8], ecx
0x18001c99f  mov     rcx, rbx; SRWLock
0x18001c9a2  call    cs:__imp_AcquireSRWLockShared
0x18001c9a9  nop     dword ptr [rax+rax+00h]
0x18001c9ae  mov     rdx, 0CBF29CE484222325h
0x18001c9b8  xor     r8d, r8d
0x18001c9bb  movzx   eax, byte ptr [rsp+r8+158h+arg_0]
0x18001c9c4  mov     rcx, 100000001B3h
0x18001c9ce  xor     rdx, rax
0x18001c9d1  inc     r8
0x18001c9d4  imul    rdx, rcx
0x18001c9d8  cmp     r8, 4
0x18001c9dc  jb      short loc_18001C9BB
0x18001c9de  mov     rcx, [rbx+60h]
0x18001c9e2  and     rcx, rdx
0x18001c9e5  mov     rdx, [rbx+48h]
0x18001c9e9  add     rcx, rcx
0x18001c9ec  mov     rax, [rdx+rcx*8+8]
0x18001c9f1  cmp     rax, [rbx+38h]
0x18001c9f5  jz      short loc_18001CA0B
0x18001c9f7  mov     r8, [rdx+rcx*8]
0x18001c9fb  cmp     esi, [rax+10h]
0x18001c9fe  jz      short loc_18001CA0D
0x18001ca00  cmp     rax, r8
0x18001ca03  jz      short loc_18001CA0B
0x18001ca05  mov     rax, [rax+8]
0x18001ca09  jmp     short loc_18001C9FB
0x18001ca0b  xor     eax, eax
0x18001ca0d  test    rax, rax
0x18001ca10  cmovz   rax, [rbx+38h]
0x18001ca15  cmp     rax, [rbx+38h]
0x18001ca19  jnz     short loc_18001CA1F
0x18001ca1b  xor     edi, edi
0x18001ca1d  jmp     short loc_18001CA23
0x18001ca1f  mov     rdi, [rax+20h]
0x18001ca23  test    rbx, rbx
0x18001ca26  jz      short loc_18001CA37
0x18001ca28  mov     rcx, rbx; SRWLock
0x18001ca2b  call    cs:__imp_ReleaseSRWLockShared
0x18001ca32  nop     dword ptr [rax+rax+00h]
0x18001ca37  mov     rcx, rdi; void *
0x18001ca3a  call    ?WaitForEventInternal@@YAJPEAX@Z; WaitForEventInternal(void *)
0x18001ca3f  mov     ebx, eax
0x18001ca41  test    eax, eax
0x18001ca43  jns     short loc_18001CA66
0x18001ca45  mov     rcx, [rsp+158h]; this
0x18001ca4d  lea     r8, ?AppPackageAuthority@?1??DaclContainsPackageAndLpacCapabilitySid_@@YAHPEAX@Z@4U_SID_IDENTIFIER_AUTHORITY@@B.SubAuthority; unsigned int
0x18001ca54  mov     r9d, eax; char *
0x18001ca57  mov     edx, 36Bh; void *
0x18001ca5c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001ca61  jmp     loc_18001CB59
0x18001ca66  lea     rcx, [rsp+158h+hObject]; TokenHandle
0x18001ca6e  mov     [rsp+158h+hObject], 0
0x18001ca7a  call    ?GetMyOwnToken@@YAJPEAPEAX@Z; GetMyOwnToken(void * *)
0x18001ca7f  mov     ebx, eax
0x18001ca81  test    eax, eax
0x18001ca83  jns     short loc_18001CAA6
0x18001ca85  mov     rcx, [rsp+158h]; this
0x18001ca8d  lea     r8, ?AppPackageAuthority@?1??DaclContainsPackageAndLpacCapabilitySid_@@YAHPEAX@Z@4U_SID_IDENTIFIER_AUTHORITY@@B.SubAuthority; unsigned int
0x18001ca94  mov     r9d, eax; char *
0x18001ca97  mov     edx, 36Fh; void *
0x18001ca9c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001caa1  jmp     loc_18001CB4C
0x18001caa6  mov     edx, esi; unsigned int
0x18001caa8  call    ?GetUserToken@CUserProfileManager@@QEAAPEAXK@Z; CUserProfileManager::GetUserToken(ulong)
0x18001caad  mov     rbx, rax
0x18001cab0  call    IsWaitForNetworkForRoamingProfilePresent
0x18001cab5  test    al, al
0x18001cab7  jz      short loc_18001CACA
0x18001cab9  xor     edx, edx
0x18001cabb  mov     rcx, rbx
0x18001cabe  call    cs:__imp_InitializeSuspendFolderPolicyAndUploadTaskConfig
0x18001cac5  nop     dword ptr [rax+rax+00h]
0x18001caca  mov     rcx, rbx; TokenHandle
0x18001cacd  call    ?UpdateRunLogonScriptSyncCache@@YAXPEAX@Z; UpdateRunLogonScriptSyncCache(void *)
0x18001cad2  lea     rcx, [rsp+158h+var_138]; this
0x18001cad7  call    ??0CUserProfile@@QEAA@XZ; CUserProfile::CUserProfile(void)
0x18001cadc  mov     rdx, [rsp+158h+hObject]; hToken
0x18001cae4  lea     rcx, [rsp+158h+var_138]; this
0x18001cae9  mov     r9d, esi; unsigned int
0x18001caec  mov     r8, rbx; void *
0x18001caef  call    ?Unload@CUserProfile@@QEAAJPEAX0K@Z; CUserProfile::Unload(void *,void *,ulong)
0x18001caf4  mov     ebx, eax
0x18001caf6  test    eax, eax
0x18001caf8  jns     short loc_18001CB40
0x18001cafa  mov     rcx, [rsp+158h]; this
0x18001cb02  lea     r8, ?AppPackageAuthority@?1??DaclContainsPackageAndLpacCapabilitySid_@@YAHPEAX@Z@4U_SID_IDENTIFIER_AUTHORITY@@B.SubAuthority; unsigned int
0x18001cb09  mov     r9d, eax; char *
0x18001cb0c  mov     edx, 381h; void *
0x18001cb11  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001cb16  lea     rcx, [rsp+158h+var_138]; this
0x18001cb1b  call    ??1CUserProfile@@QEAA@XZ; CUserProfile::~CUserProfile(void)
0x18001cb20  mov     rcx, [rsp+158h+hObject]; hObject
0x18001cb28  lea     rdx, [rcx-1]
0x18001cb2c  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x18001cb30  ja      short loc_18001CB59
0x18001cb32  call    cs:__imp_CloseHandle
0x18001cb39  nop     dword ptr [rax+rax+00h]
0x18001cb3e  jmp     short loc_18001CB59
0x18001cb40  lea     rcx, [rsp+158h+var_138]; this
0x18001cb45  call    ??1CUserProfile@@QEAA@XZ; CUserProfile::~CUserProfile(void)
0x18001cb4a  xor     ebx, ebx
0x18001cb4c  lea     rcx, [rsp+158h+hObject]
0x18001cb54  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18001cb59  lea     r11, [rsp+158h+var_8]
0x18001cb61  mov     eax, ebx
0x18001cb63  mov     rbx, [r11+20h]
0x18001cb67  mov     rsi, [r11+28h]
0x18001cb6b  mov     rsp, r11
0x18001cb6e  pop     rdi
0x18001cb6f  retn
```
