# EfsMdmPolicyUpdateHandler

- ea: `0x180041c20`
- end: `0x180041fc9`
- name: `EfsMdmPolicyUpdateHandler`
- size: `937`
- prototype: ``
- caller_count: `0`
- callee_count: `11`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x180005045`
- `0x18001f920`
- `0x1800254d4`
- `0x180025694`
- `0x180040484`
- `0x180040964`
- `0x180041c20`
- `0x180063698`
- `0x180063730`
- `0x1800637e8`
- `0x180084508`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180041d6c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180041d91`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180041f16`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180041d6c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180041d91`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180041f16`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180041cf6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180041f70`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180041cf6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180041f70`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180041cdd`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180041f61`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180041cdd`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180041f61`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180041d60`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180041d60`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrFreeSessionUsers` at `0x180041f87`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrFreeSessionUsers` at `0x180041f87`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrEnumerateSessionUsers` at `0x180041c7d`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrEnumerateSessionUsers` at `0x180041c7d`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserToken` at `0x180041d16`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserToken` at `0x180041d16`

## pseudocode

```c
void EfsMdmPolicyUpdateHandler()
{
  int v0; // ebx
  int v1; // ecx
  int v2; // eax
  BOOL v3; // edi
  int v4; // esi
  unsigned int i; // r14d
  int v6; // eax
  DWORD v7; // r8d
  DWORD v8; // eax
  unsigned __int8 UserInfo; // al
  int v10; // ecx
  int v11; // ebx
  int v12; // ecx
  int v13; // r8d
  int v14; // ebx
  int v15; // r8d
  int v16; // eax
  signed int LastError; // eax
  unsigned int v18; // r8d
  char v19; // [rsp+20h] [rbp-59h]
  _BYTE v20[24]; // [rsp+40h] [rbp-39h] BYREF
  unsigned __int16 *v21; // [rsp+58h] [rbp-21h]
  unsigned int v22; // [rsp+E8h] [rbp+6Fh] BYREF
  HANDLE hObject; // [rsp+F0h] [rbp+77h] BYREF
  __int64 v24; // [rsp+F8h] [rbp+7Fh] BYREF

  v0 = 0;
  v24 = 0;
  v22 = 0;
  hObject = 0;
  memset_0(v20, 0, 0x70u);
  fnEfsLogTrace1Strings(v1, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&sourceString, 32, 97);
  v2 = UMgrEnumerateSessionUsers(&v22, &v24);
  if ( (int)fnEfsLogTrace1String1Dword(
              g_hPublisher,
              (unsigned int)EFS_TRACE_COMPLETE_EVENT,
              (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
              (unsigned int)&sourceString,
              v2,
              32,
              97) < 0 )
    goto LABEL_45;
  v3 = 0;
  v4 = 0;
  for ( i = 0; i < v22; ++i )
  {
    if ( v4 )
    {
      EfsFreeUserInfo(v20);
      v4 = 0;
    }
    if ( v3 )
    {
      if ( !RevertToSelf() )
      {
        LastError = GetLastError();
        v0 = LastError;
        if ( LastError > 0 )
          v18 = (unsigned __int16)LastError | 0x80070000;
        else
          v18 = LastError;
        fnEfsLogTrace1(g_hPublisher, (unsigned int)EFS_TRACE_ERROR, v18, 32, 115);
        break;
      }
      v3 = 0;
    }
    if ( hObject )
    {
      CloseHandle(hObject);
      hObject = 0;
    }
    v6 = UMgrQueryUserToken(*(_QWORD *)(v24 + 16LL * i), &hObject);
    if ( v6 < 0 )
    {
      v0 = (unsigned __int16)v6;
      if ( (v6 & 0x1FFF0000) != 0x70000 )
        v0 = 1359;
      v19 = -124;
      v7 = v0;
      goto LABEL_15;
    }
    v3 = ImpersonateLoggedOnUser(hObject);
    if ( !v3 )
    {
      v8 = GetLastError();
      v19 = -107;
LABEL_18:
      v0 = v8;
      v7 = v8;
LABEL_15:
      fnEfsLogTrace1(g_hPublisher, (unsigned int)EFS_SERVICE_EDP_PROVISION_USER_ERROR, v7, 32, v19);
      continue;
    }
    UserInfo = EfsGetUserInfo((struct _EFS_USER_INFO *)v20);
    v4 = UserInfo;
    if ( !UserInfo )
    {
      v8 = GetLastError();
      v19 = -94;
      goto LABEL_18;
    }
    fnEfsLogTrace1Strings(v10, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&sourceString, 32, 175);
    v11 = EfspMdmProvisionEdp(v21);
    if ( (int)fnEfsLogTrace1String1Dword(
                g_hPublisher,
                (unsigned int)EFS_TRACE_COMPLETE_EVENT,
                (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
                (unsigned int)&sourceString,
                v11,
                32,
                175) < 0 )
    {
      if ( v11 < 0 )
      {
        v13 = (unsigned __int16)v11;
        if ( (v11 & 0x1FFF0000) != 0x70000 )
          v13 = 1359;
      }
      else
      {
        v13 = 0;
      }
      fnEfsLogTrace1(g_hPublisher, (unsigned int)EFS_SERVICE_EDP_PROVISION_USER_ERROR, v13, 32, 178);
    }
    fnEfsLogTrace1Strings(v12, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&sourceString, 32, 185);
    v14 = EfspMdmProvisionDpl(v21);
    if ( (int)fnEfsLogTrace1String1Dword(
                g_hPublisher,
                (unsigned int)EFS_TRACE_COMPLETE_EVENT,
                (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
                (unsigned int)&sourceString,
                v14,
                32,
                185) < 0 )
    {
      if ( v14 < 0 )
      {
        v15 = (unsigned __int16)v14;
        if ( (v14 & 0x1FFF0000) != 0x70000 )
          v15 = 1359;
      }
      else
      {
        v15 = 0;
      }
      fnEfsLogTrace1(g_hPublisher, (unsigned int)EFS_SERVICE_DPL_PROVISION_USER_ERROR, v15, 32, 188);
    }
    v16 = EfsProcessRecoveryPolicy();
    v0 = v16;
    if ( v16 )
      fnEfsLogTrace1(g_hPublisher, (unsigned int)EFS_SERVICE_INIT_PROCESSRECPOLICY_ERROR, v16, 32, 203);
    EdpCredSvcProcessRecoveryPolicy();
  }
  if ( v4 )
    EfsFreeUserInfo(v20);
  if ( v3 )
    RevertToSelf();
LABEL_45:
  if ( hObject )
  {
    CloseHandle(hObject);
    hObject = 0;
  }
  if ( v24 )
    UMgrFreeSessionUsers();
  if ( v0 )
    fnEfsLogTrace1(g_hPublisher, (unsigned int)EFS_SERVICE_MDM_POLICY_HANDLER_ERROR, v0, 32, 231);
}

```

## disassembly

```asm
0x180041c20  mov     [rsp-8+arg_0], rbx
0x180041c25  push    rbp
0x180041c26  push    rsi
0x180041c27  push    rdi
0x180041c28  push    r12
0x180041c2a  push    r14
0x180041c2c  lea     rbp, [rsp-37h]
0x180041c31  sub     rsp, 0B0h
0x180041c38  xor     ebx, ebx
0x180041c3a  lea     rcx, [rbp+57h+var_90]; void *
0x180041c3e  xor     edx, edx; Val
0x180041c40  mov     [rbp+57h+arg_18], rbx
0x180041c44  mov     [rbp+57h+arg_8], ebx
0x180041c47  mov     [rbp+57h+hObject], rbx
0x180041c4b  lea     r8d, [rbx+70h]; Size
0x180041c4f  call    memset_0
0x180041c54  lea     r12d, [rbx+20h]
0x180041c58  lea     edi, [rbx+61h]
0x180041c5b  mov     r9d, r12d
0x180041c5e  lea     r8, sourceString
0x180041c65  mov     dword ptr [rsp+0D0h+var_B0], edi
0x180041c69  lea     rdx, EFS_TRACE_START_EVENT
0x180041c70  call    fnEfsLogTrace1Strings
0x180041c75  lea     rdx, [rbp+57h+arg_18]
0x180041c79  lea     rcx, [rbp+57h+arg_8]
0x180041c7d  call    cs:__imp_UMgrEnumerateSessionUsers
0x180041c83  mov     rcx, cs:g_hPublisher
0x180041c8a  lea     r9, sourceString
0x180041c91  mov     [rsp+0D0h+var_A0], edi
0x180041c95  lea     r8, EFS_TRACE_COMPLETE_EVENT_ERROR
0x180041c9c  mov     [rsp+0D0h+var_A8], r12d
0x180041ca1  lea     rdx, EFS_TRACE_COMPLETE_EVENT
0x180041ca8  mov     dword ptr [rsp+0D0h+var_B0], eax
0x180041cac  call    fnEfsLogTrace1String1Dword
0x180041cb1  test    eax, eax
0x180041cb3  js      loc_180041F67
0x180041cb9  xor     edi, edi
0x180041cbb  xor     esi, esi
0x180041cbd  xor     r14d, r14d
0x180041cc0  cmp     r14d, [rbp+57h+arg_8]
0x180041cc4  jnb     loc_180041F50
0x180041cca  test    esi, esi
0x180041ccc  jz      short loc_180041CD9
0x180041cce  lea     rcx, [rbp+57h+var_90]
0x180041cd2  call    EfsFreeUserInfo
0x180041cd7  xor     esi, esi
0x180041cd9  test    edi, edi
0x180041cdb  jz      short loc_180041CED
0x180041cdd  call    cs:__imp_RevertToSelf
0x180041ce3  test    eax, eax
0x180041ce5  jz      loc_180041F16
0x180041ceb  xor     edi, edi
0x180041ced  mov     rcx, [rbp+57h+hObject]; hObject
0x180041cf1  test    rcx, rcx
0x180041cf4  jz      short loc_180041D04
0x180041cf6  call    cs:__imp_CloseHandle
0x180041cfc  mov     [rbp+57h+hObject], 0
0x180041d04  mov     rcx, [rbp+57h+arg_18]
0x180041d08  lea     rdx, [rbp+57h+hObject]
0x180041d0c  mov     eax, r14d
0x180041d0f  add     rax, rax
0x180041d12  mov     rcx, [rcx+rax*8]
0x180041d16  call    cs:__imp_UMgrQueryUserToken
0x180041d1c  mov     ecx, eax
0x180041d1e  test    eax, eax
0x180041d20  jns     short loc_180041D5C
0x180041d22  and     eax, 1FFF0000h
0x180041d27  movzx   ebx, cx
0x180041d2a  cmp     eax, 70000h
0x180041d2f  jz      short loc_180041D36
0x180041d31  mov     ebx, 54Fh
0x180041d36  mov     dword ptr [rsp+0D0h+var_B0], 84h
0x180041d3e  mov     r8d, ebx
0x180041d41  mov     rcx, cs:g_hPublisher
0x180041d48  lea     rdx, EFS_SERVICE_EDP_PROVISION_USER_ERROR
0x180041d4f  mov     r9d, r12d
0x180041d52  call    fnEfsLogTrace1
0x180041d57  jmp     loc_180041F0E
0x180041d5c  mov     rcx, [rbp+57h+hObject]; hToken
0x180041d60  call    cs:__imp_ImpersonateLoggedOnUser
0x180041d66  mov     edi, eax
0x180041d68  test    eax, eax
0x180041d6a  jnz     short loc_180041D81
0x180041d6c  call    cs:__imp_GetLastError
0x180041d72  mov     dword ptr [rsp+0D0h+var_B0], 95h
0x180041d7a  mov     ebx, eax
0x180041d7c  mov     r8d, eax
0x180041d7f  jmp     short loc_180041D41
0x180041d81  lea     rcx, [rbp+57h+var_90]
0x180041d85  call    EfsGetUserInfo
0x180041d8a  movzx   esi, al
0x180041d8d  test    al, al
0x180041d8f  jnz     short loc_180041DA1
0x180041d91  call    cs:__imp_GetLastError
0x180041d97  mov     dword ptr [rsp+0D0h+var_B0], 0A2h
0x180041d9f  jmp     short loc_180041D7A
0x180041da1  mov     r9d, r12d
0x180041da4  mov     dword ptr [rsp+0D0h+var_B0], 0AFh
0x180041dac  lea     r8, sourceString
0x180041db3  lea     rdx, EFS_TRACE_START_EVENT
0x180041dba  call    fnEfsLogTrace1Strings
0x180041dbf  mov     rcx, [rbp+57h+var_78]; unsigned __int16 *
0x180041dc3  call    ?EfspMdmProvisionEdp@@YAJPEBG@Z; EfspMdmProvisionEdp(ushort const *)
0x180041dc8  mov     rcx, cs:g_hPublisher
0x180041dcf  lea     r9, sourceString
0x180041dd6  mov     [rsp+0D0h+var_A0], 0AFh
0x180041dde  lea     r8, EFS_TRACE_COMPLETE_EVENT_ERROR
0x180041de5  mov     [rsp+0D0h+var_A8], r12d
0x180041dea  lea     rdx, EFS_TRACE_COMPLETE_EVENT
0x180041df1  mov     dword ptr [rsp+0D0h+var_B0], eax
0x180041df5  mov     ebx, eax
0x180041df7  call    fnEfsLogTrace1String1Dword
0x180041dfc  test    eax, eax
0x180041dfe  jns     short loc_180041E3F
0x180041e00  test    ebx, ebx
0x180041e02  js      short loc_180041E09
0x180041e04  xor     r8d, r8d
0x180041e07  jmp     short loc_180041E21
0x180041e09  mov     eax, ebx
0x180041e0b  movzx   r8d, bx
0x180041e0f  and     eax, 1FFF0000h
0x180041e14  cmp     eax, 70000h
0x180041e19  jz      short loc_180041E21
0x180041e1b  mov     r8d, 54Fh
0x180041e21  mov     rcx, cs:g_hPublisher
0x180041e28  lea     rdx, EFS_SERVICE_EDP_PROVISION_USER_ERROR
0x180041e2f  mov     r9d, r12d
0x180041e32  mov     dword ptr [rsp+0D0h+var_B0], 0B2h
0x180041e3a  call    fnEfsLogTrace1
0x180041e3f  mov     r9d, r12d
0x180041e42  mov     dword ptr [rsp+0D0h+var_B0], 0B9h
0x180041e4a  lea     r8, sourceString
0x180041e51  lea     rdx, EFS_TRACE_START_EVENT
0x180041e58  call    fnEfsLogTrace1Strings
0x180041e5d  mov     rcx, [rbp+57h+var_78]; unsigned __int16 *
0x180041e61  call    ?EfspMdmProvisionDpl@@YAJPEBG@Z; EfspMdmProvisionDpl(ushort const *)
0x180041e66  mov     rcx, cs:g_hPublisher
0x180041e6d  lea     r9, sourceString
0x180041e74  mov     [rsp+0D0h+var_A0], 0B9h
0x180041e7c  lea     r8, EFS_TRACE_COMPLETE_EVENT_ERROR
0x180041e83  mov     [rsp+0D0h+var_A8], r12d
0x180041e88  lea     rdx, EFS_TRACE_COMPLETE_EVENT
0x180041e8f  mov     dword ptr [rsp+0D0h+var_B0], eax
0x180041e93  mov     ebx, eax
0x180041e95  call    fnEfsLogTrace1String1Dword
0x180041e9a  test    eax, eax
0x180041e9c  jns     short loc_180041EDD
0x180041e9e  test    ebx, ebx
0x180041ea0  js      short loc_180041EA7
0x180041ea2  xor     r8d, r8d
0x180041ea5  jmp     short loc_180041EBF
0x180041ea7  mov     eax, ebx
0x180041ea9  movzx   r8d, bx
0x180041ead  and     eax, 1FFF0000h
0x180041eb2  cmp     eax, 70000h
0x180041eb7  jz      short loc_180041EBF
0x180041eb9  mov     r8d, 54Fh
0x180041ebf  mov     rcx, cs:g_hPublisher
0x180041ec6  lea     rdx, EFS_SERVICE_DPL_PROVISION_USER_ERROR
0x180041ecd  mov     r9d, r12d
0x180041ed0  mov     dword ptr [rsp+0D0h+var_B0], 0BCh
0x180041ed8  call    fnEfsLogTrace1
0x180041edd  call    EfsProcessRecoveryPolicy
0x180041ee2  mov     ebx, eax
0x180041ee4  test    eax, eax
0x180041ee6  jz      short loc_180041F09
0x180041ee8  mov     rcx, cs:g_hPublisher
0x180041eef  lea     rdx, EFS_SERVICE_INIT_PROCESSRECPOLICY_ERROR
0x180041ef6  mov     r9d, r12d
0x180041ef9  mov     dword ptr [rsp+0D0h+var_B0], 0CBh
0x180041f01  mov     r8d, eax
0x180041f04  call    fnEfsLogTrace1
0x180041f09  call    ?EdpCredSvcProcessRecoveryPolicy@@YAXXZ; EdpCredSvcProcessRecoveryPolicy(void)
0x180041f0e  inc     r14d
0x180041f11  jmp     loc_180041CC0
0x180041f16  call    cs:__imp_GetLastError
0x180041f1c  mov     ebx, eax
0x180041f1e  test    eax, eax
0x180041f20  jg      short loc_180041F27
0x180041f22  mov     r8d, eax
0x180041f25  jmp     short loc_180041F32
0x180041f27  movzx   r8d, ax
0x180041f2b  or      r8d, 80070000h
0x180041f32  mov     rcx, cs:g_hPublisher
0x180041f39  lea     rdx, EFS_TRACE_ERROR
0x180041f40  mov     r9d, r12d
0x180041f43  mov     dword ptr [rsp+0D0h+var_B0], 73h ; 's'
0x180041f4b  call    fnEfsLogTrace1
0x180041f50  test    esi, esi
0x180041f52  jz      short loc_180041F5D
0x180041f54  lea     rcx, [rbp+57h+var_90]
0x180041f58  call    EfsFreeUserInfo
0x180041f5d  test    edi, edi
0x180041f5f  jz      short loc_180041F67
0x180041f61  call    cs:__imp_RevertToSelf
0x180041f67  mov     rcx, [rbp+57h+hObject]; hObject
0x180041f6b  test    rcx, rcx
0x180041f6e  jz      short loc_180041F7E
0x180041f70  call    cs:__imp_CloseHandle
0x180041f76  mov     [rbp+57h+hObject], 0
0x180041f7e  mov     rcx, [rbp+57h+arg_18]
0x180041f82  test    rcx, rcx
0x180041f85  jz      short loc_180041F8D
0x180041f87  call    cs:__imp_UMgrFreeSessionUsers
0x180041f8d  test    ebx, ebx
0x180041f8f  jz      short loc_180041FB2
0x180041f91  mov     rcx, cs:g_hPublisher
0x180041f98  lea     rdx, EFS_SERVICE_MDM_POLICY_HANDLER_ERROR
0x180041f9f  mov     r9d, r12d
0x180041fa2  mov     dword ptr [rsp+0D0h+var_B0], 0E7h
0x180041faa  mov     r8d, ebx
0x180041fad  call    fnEfsLogTrace1
0x180041fb2  mov     rbx, [rsp+0D0h+arg_0]
0x180041fba  add     rsp, 0B0h
0x180041fc1  pop     r14
0x180041fc3  pop     r12
0x180041fc5  pop     rdi
0x180041fc6  pop     rsi
0x180041fc7  pop     rbp
0x180041fc8  retn
```
