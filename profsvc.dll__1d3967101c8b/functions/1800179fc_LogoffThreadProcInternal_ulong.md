# LogoffThreadProcInternal(ulong)

- ea: `0x1800179fc`
- end: `0x180017bd4`
- name: `?LogoffThreadProcInternal@@YAJK@Z`
- size: `472`
- prototype: `__int64 __fastcall(unsigned int)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x1800172d0`

## callees

- `0x180004d94`
- `0x18000a9b8`
- `0x18000b540`
- `0x180016f5c`
- `0x1800170c8`
- `0x1800179fc`
- `0x180019460`
- `0x180019630`
- `0x1800199b4`
- `0x18002d2d8`
- `0x18003c118`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180017a1e`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180017a1e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180017aa1`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180017aa1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180017b9c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180017b9c`
- `ext-ms-win-profile-profsvc-l1-1-0!InitializeSuspendFolderPolicyAndUploadTaskConfig` at `0x180017b2e`
- `ext-ms-win-profile-profsvc-l1-1-0!InitializeSuspendFolderPolicyAndUploadTaskConfig` at `0x180017b2e`

## string_xrefs

- `0x180017abd`: `onecore\ds\security\gina\profile\profsvc\winlogon.cpp`
- `0x180017afd`: `onecore\ds\security\gina\profile\profsvc\winlogon.cpp`
- `0x180017b6c`: `onecore\ds\security\gina\profile\profsvc\winlogon.cpp`

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
  int v16; // eax
  int v18[76]; // [rsp+20h] [rbp-138h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+158h] [rbp+0h]
  unsigned int v20; // [rsp+160h] [rbp+8h]
  HANDLE hObject; // [rsp+168h] [rbp+10h] BYREF

  v1 = g_pProfMgr;
  v20 = a1;
  AcquireSRWLockShared(g_pProfMgr);
  v3 = 0xCBF29CE484222325uLL;
  for ( i = 0; i < 4; ++i )
  {
    v5 = *((unsigned __int8 *)&v20 + i);
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
      (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\winlogon.cpp",
      (const char *)(unsigned int)v11,
      v18[0]);
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
      (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\winlogon.cpp",
      (const char *)(unsigned int)MyOwnToken,
      v18[0]);
LABEL_25:
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hObject);
    return v12;
  }
  UserToken = CUserProfileManager::GetUserToken(v14, a1);
  if ( (unsigned __int8)IsWaitForNetworkForRoamingProfilePresent() )
    InitializeSuspendFolderPolicyAndUploadTaskConfig(UserToken, 0);
  UpdateRunLogonScriptSyncCache(UserToken);
  CUserProfile::CUserProfile((CUserProfile *)v18);
  v16 = CUserProfile::Unload((CUserProfile *)v18, hObject, UserToken, a1);
  v12 = v16;
  if ( v16 >= 0 )
  {
    CUserProfile::~CUserProfile((CUserProfile *)v18);
    v12 = 0;
    goto LABEL_25;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x381,
    (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\winlogon.cpp",
    (const char *)(unsigned int)v16,
    v18[0]);
  CUserProfile::~CUserProfile((CUserProfile *)v18);
  if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    CloseHandle(hObject);
  return v12;
}

```

## disassembly

```asm
0x1800179fc  mov     rax, rsp
0x1800179ff  mov     [rax+18h], rbx
0x180017a03  mov     [rax+20h], rsi
0x180017a07  push    rdi
0x180017a08  sub     rsp, 150h
0x180017a0f  mov     rbx, cs:?g_pProfMgr@@3PEAVCUserProfileManager@@EA; CUserProfileManager * g_pProfMgr
0x180017a16  mov     esi, ecx
0x180017a18  mov     [rax+8], ecx
0x180017a1b  mov     rcx, rbx; SRWLock
0x180017a1e  call    cs:__imp_AcquireSRWLockShared
0x180017a24  mov     rdx, 0CBF29CE484222325h
0x180017a2e  xor     r8d, r8d
0x180017a31  movzx   eax, byte ptr [rsp+r8+158h+arg_0]
0x180017a3a  mov     rcx, 100000001B3h
0x180017a44  xor     rdx, rax
0x180017a47  inc     r8
0x180017a4a  imul    rdx, rcx
0x180017a4e  cmp     r8, 4
0x180017a52  jb      short loc_180017A31
0x180017a54  mov     rcx, [rbx+60h]
0x180017a58  and     rcx, rdx
0x180017a5b  mov     rdx, [rbx+48h]
0x180017a5f  add     rcx, rcx
0x180017a62  mov     rax, [rdx+rcx*8+8]
0x180017a67  cmp     rax, [rbx+38h]
0x180017a6b  jz      short loc_180017A81
0x180017a6d  mov     r8, [rdx+rcx*8]
0x180017a71  cmp     esi, [rax+10h]
0x180017a74  jz      short loc_180017A83
0x180017a76  cmp     rax, r8
0x180017a79  jz      short loc_180017A81
0x180017a7b  mov     rax, [rax+8]
0x180017a7f  jmp     short loc_180017A71
0x180017a81  xor     eax, eax
0x180017a83  test    rax, rax
0x180017a86  cmovz   rax, [rbx+38h]
0x180017a8b  cmp     rax, [rbx+38h]
0x180017a8f  jnz     short loc_180017A95
0x180017a91  xor     edi, edi
0x180017a93  jmp     short loc_180017A99
0x180017a95  mov     rdi, [rax+20h]
0x180017a99  test    rbx, rbx
0x180017a9c  jz      short loc_180017AA7
0x180017a9e  mov     rcx, rbx; SRWLock
0x180017aa1  call    cs:__imp_ReleaseSRWLockShared
0x180017aa7  mov     rcx, rdi; void *
0x180017aaa  call    ?WaitForEventInternal@@YAJPEAX@Z; WaitForEventInternal(void *)
0x180017aaf  mov     ebx, eax
0x180017ab1  test    eax, eax
0x180017ab3  jns     short loc_180017AD6
0x180017ab5  mov     rcx, [rsp+158h]; this
0x180017abd  lea     r8, aOnecoreDsSecur_12; "onecore\\ds\\security\\gina\\profile\\p"...
0x180017ac4  mov     r9d, eax; char *
0x180017ac7  mov     edx, 36Bh; void *
0x180017acc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180017ad1  jmp     loc_180017BBD
0x180017ad6  lea     rcx, [rsp+158h+hObject]; TokenHandle
0x180017ade  mov     [rsp+158h+hObject], 0
0x180017aea  call    ?GetMyOwnToken@@YAJPEAPEAX@Z; GetMyOwnToken(void * *)
0x180017aef  mov     ebx, eax
0x180017af1  test    eax, eax
0x180017af3  jns     short loc_180017B16
0x180017af5  mov     rcx, [rsp+158h]; this
0x180017afd  lea     r8, aOnecoreDsSecur_12; "onecore\\ds\\security\\gina\\profile\\p"...
0x180017b04  mov     r9d, eax; char *
0x180017b07  mov     edx, 36Fh; void *
0x180017b0c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180017b11  jmp     loc_180017BB0
0x180017b16  mov     edx, esi; unsigned int
0x180017b18  call    ?GetUserToken@CUserProfileManager@@QEAAPEAXK@Z; CUserProfileManager::GetUserToken(ulong)
0x180017b1d  mov     rbx, rax
0x180017b20  call    IsWaitForNetworkForRoamingProfilePresent
0x180017b25  test    al, al
0x180017b27  jz      short loc_180017B34
0x180017b29  xor     edx, edx
0x180017b2b  mov     rcx, rbx
0x180017b2e  call    cs:__imp_InitializeSuspendFolderPolicyAndUploadTaskConfig
0x180017b34  mov     rcx, rbx; TokenHandle
0x180017b37  call    ?UpdateRunLogonScriptSyncCache@@YAXPEAX@Z; UpdateRunLogonScriptSyncCache(void *)
0x180017b3c  lea     rcx, [rsp+158h+var_138]; this
0x180017b41  call    ??0CUserProfile@@QEAA@XZ; CUserProfile::CUserProfile(void)
0x180017b46  mov     rdx, [rsp+158h+hObject]; hToken
0x180017b4e  lea     rcx, [rsp+158h+var_138]; this
0x180017b53  mov     r9d, esi; unsigned int
0x180017b56  mov     r8, rbx; void *
0x180017b59  call    ?Unload@CUserProfile@@QEAAJPEAX0K@Z; CUserProfile::Unload(void *,void *,ulong)
0x180017b5e  mov     ebx, eax
0x180017b60  test    eax, eax
0x180017b62  jns     short loc_180017BA4
0x180017b64  mov     rcx, [rsp+158h]; this
0x180017b6c  lea     r8, aOnecoreDsSecur_12; "onecore\\ds\\security\\gina\\profile\\p"...
0x180017b73  mov     r9d, eax; char *
0x180017b76  mov     edx, 381h; void *
0x180017b7b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180017b80  lea     rcx, [rsp+158h+var_138]; this
0x180017b85  call    ??1CUserProfile@@QEAA@XZ; CUserProfile::~CUserProfile(void)
0x180017b8a  mov     rcx, [rsp+158h+hObject]; hObject
0x180017b92  lea     rdx, [rcx-1]
0x180017b96  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x180017b9a  ja      short loc_180017BBD
0x180017b9c  call    cs:__imp_CloseHandle
0x180017ba2  jmp     short loc_180017BBD
0x180017ba4  lea     rcx, [rsp+158h+var_138]; this
0x180017ba9  call    ??1CUserProfile@@QEAA@XZ; CUserProfile::~CUserProfile(void)
0x180017bae  xor     ebx, ebx
0x180017bb0  lea     rcx, [rsp+158h+hObject]
0x180017bb8  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180017bbd  lea     r11, [rsp+158h+var_8]
0x180017bc5  mov     eax, ebx
0x180017bc7  mov     rbx, [r11+20h]
0x180017bcb  mov     rsi, [r11+28h]
0x180017bcf  mov     rsp, r11
0x180017bd2  pop     rdi
0x180017bd3  retn
```
