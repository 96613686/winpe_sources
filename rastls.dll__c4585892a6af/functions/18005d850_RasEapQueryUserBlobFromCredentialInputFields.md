# RasEapQueryUserBlobFromCredentialInputFields

- ea: `0x18005d850`
- end: `0x18005d9f9`
- name: `RasEapQueryUserBlobFromCredentialInputFields`
- size: `425`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x180005010`
- `0x18005388c`
- `0x180059210`
- `0x18005d850`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005d8f5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005d9b1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005d8f5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005d9b1`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18005d991`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18005d991`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18005d8e5`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18005d8e5`

## pseudocode

```c
__int64 __fastcall RasEapQueryUserBlobFromCredentialInputFields(
        void *a1,
        void *a2,
        unsigned int a3,
        unsigned __int8 *a4,
        unsigned int a5,
        struct _EAP_CONFIG_INPUT_FIELD_ARRAY *a6,
        unsigned __int8 **a7,
        unsigned int *a8)
{
  unsigned int v9; // eax
  int v11; // r15d
  __int64 v12; // r9
  int v13; // ebp
  DWORD LastError; // ebx
  struct _EAPTLS_CONTROL_BLOCK *v15; // rcx
  __int64 v16; // rdx
  __int64 v17; // r9
  unsigned int UserBlobFromCredentialInputFields; // eax
  DWORD v19; // eax

  v9 = a3;
  v11 = (int)a1;
  if ( a6 && a7 && a8 )
  {
    v12 = *a8;
    v13 = 0;
    if ( (_DWORD)v12 && *a7 )
    {
      if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 815, &WPP_eb8ccc023461353daee6fb3f53c7a16f_Traceguids, v12);
      *a8 = 0;
      *a7 = 0;
      if ( !ImpersonateLoggedOnUser(a2) )
      {
        LastError = GetLastError();
        v15 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
          return LastError;
        v16 = 816;
        v17 = LastError;
LABEL_21:
        WPP_SF_d(*((_QWORD *)v15 + 2), v16, &WPP_eb8ccc023461353daee6fb3f53c7a16f_Traceguids, v17);
        return LastError;
      }
      v9 = a3;
      v13 = 1;
    }
    if ( v11 == 13 )
    {
      UserBlobFromCredentialInputFields = EapTlsQueryUserBlobFromCredentialInputFields(a1, v9, a4, a5, a6, a7, a8);
    }
    else
    {
      LastError = 87;
      if ( v11 != 25 )
        goto LABEL_17;
      UserBlobFromCredentialInputFields = PeapQueryUserBlobFromCredentialInputFields(a2, v9, a4, a5, a6, a7, a8);
    }
    LastError = UserBlobFromCredentialInputFields;
LABEL_17:
    if ( !v13 || RevertToSelf() || WPP_GLOBAL_Control == (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
      return LastError;
    v19 = GetLastError();
    v15 = WPP_GLOBAL_Control;
    v16 = 817;
    LastError = v19;
    v17 = v19;
    goto LABEL_21;
  }
  return 87;
}

```

## disassembly

```asm
0x18005d850  mov     [rsp+arg_10], r8d
0x18005d855  push    rbx
0x18005d856  push    rbp
0x18005d857  push    rsi
0x18005d858  push    rdi
0x18005d859  push    r12
0x18005d85b  push    r13
0x18005d85d  push    r14
0x18005d85f  push    r15
0x18005d861  sub     rsp, 48h
0x18005d865  mov     r14, [rsp+88h+arg_28]
0x18005d86d  xor     ebx, ebx
0x18005d86f  mov     r13, r9
0x18005d872  mov     eax, r8d
0x18005d875  mov     r12, rdx
0x18005d878  mov     r15d, ecx
0x18005d87b  test    r14, r14
0x18005d87e  jz      loc_18005D9E2
0x18005d884  mov     rdi, [rsp+88h+arg_30]
0x18005d88c  test    rdi, rdi
0x18005d88f  jz      loc_18005D9E2
0x18005d895  mov     rsi, [rsp+88h+arg_38]
0x18005d89d  test    rsi, rsi
0x18005d8a0  jz      loc_18005D9E2
0x18005d8a6  mov     r9d, [rsi]
0x18005d8a9  lea     rdx, WPP_GLOBAL_Control
0x18005d8b0  mov     ebp, ebx
0x18005d8b2  test    r9d, r9d
0x18005d8b5  jz      short loc_18005D933
0x18005d8b7  cmp     [rdi], rbx
0x18005d8ba  jz      short loc_18005D933
0x18005d8bc  mov     rcx, cs:WPP_GLOBAL_Control
0x18005d8c3  cmp     rcx, rdx
0x18005d8c6  jz      short loc_18005D8DD
0x18005d8c8  mov     rcx, [rcx+10h]
0x18005d8cc  lea     r8, WPP_eb8ccc023461353daee6fb3f53c7a16f_Traceguids
0x18005d8d3  mov     edx, 32Fh
0x18005d8d8  call    WPP_SF_d
0x18005d8dd  mov     [rsi], ebx
0x18005d8df  mov     rcx, r12; hToken
0x18005d8e2  mov     [rdi], rbx
0x18005d8e5  call    cs:__imp_ImpersonateLoggedOnUser
0x18005d8ec  nop     dword ptr [rax+rax+00h]
0x18005d8f1  test    eax, eax
0x18005d8f3  jnz     short loc_18005D927
0x18005d8f5  call    cs:__imp_GetLastError
0x18005d8fc  nop     dword ptr [rax+rax+00h]
0x18005d901  mov     ebx, eax
0x18005d903  mov     rcx, cs:WPP_GLOBAL_Control
0x18005d90a  lea     rax, WPP_GLOBAL_Control
0x18005d911  cmp     rcx, rax
0x18005d914  jz      loc_18005D9DE
0x18005d91a  mov     edx, 330h
0x18005d91f  mov     r9d, ebx
0x18005d922  jmp     loc_18005D9CE
0x18005d927  mov     eax, [rsp+88h+arg_10]
0x18005d92e  mov     ebp, 1
0x18005d933  cmp     r15d, 0Dh
0x18005d937  jnz     short loc_18005D95C
0x18005d939  mov     r9d, [rsp+88h+arg_20]; unsigned int
0x18005d941  mov     r8, r13; unsigned __int8 *
0x18005d944  mov     [rsp+88h+var_58], rsi; unsigned int *
0x18005d949  mov     edx, eax; unsigned int
0x18005d94b  mov     [rsp+88h+var_60], rdi; unsigned __int8 **
0x18005d950  mov     [rsp+88h+var_68], r14; struct _EAP_CONFIG_INPUT_FIELD_ARRAY *
0x18005d955  call    ?EapTlsQueryUserBlobFromCredentialInputFields@@YAKPEAXKPEAEKPEBU_EAP_CONFIG_INPUT_FIELD_ARRAY@@PEAPEAEPEAK@Z; EapTlsQueryUserBlobFromCredentialInputFields(void *,ulong,uchar *,ulong,_EAP_CONFIG_INPUT_FIELD_ARRAY const *,uchar * *,ulong *)
0x18005d95a  jmp     short loc_18005D98B
0x18005d95c  mov     ebx, 57h ; 'W'
0x18005d961  cmp     r15d, 19h
0x18005d965  jnz     short loc_18005D98D
0x18005d967  mov     r9d, [rsp+88h+arg_20]; unsigned int
0x18005d96f  mov     r8, r13; unsigned __int8 *
0x18005d972  mov     [rsp+88h+var_58], rsi; unsigned int *
0x18005d977  mov     edx, eax; unsigned int
0x18005d979  mov     [rsp+88h+var_60], rdi; unsigned __int8 **
0x18005d97e  mov     rcx, r12; void *
0x18005d981  mov     [rsp+88h+var_68], r14; struct _EAP_CONFIG_INPUT_FIELD_ARRAY *
0x18005d986  call    ?PeapQueryUserBlobFromCredentialInputFields@@YAKPEAXKPEAEKPEBU_EAP_CONFIG_INPUT_FIELD_ARRAY@@PEAPEAEPEAK@Z; PeapQueryUserBlobFromCredentialInputFields(void *,ulong,uchar *,ulong,_EAP_CONFIG_INPUT_FIELD_ARRAY const *,uchar * *,ulong *)
0x18005d98b  mov     ebx, eax
0x18005d98d  test    ebp, ebp
0x18005d98f  jz      short loc_18005D9DE
0x18005d991  call    cs:__imp_RevertToSelf
0x18005d998  nop     dword ptr [rax+rax+00h]
0x18005d99d  test    eax, eax
0x18005d99f  jnz     short loc_18005D9DE
0x18005d9a1  lea     rax, WPP_GLOBAL_Control
0x18005d9a8  cmp     cs:WPP_GLOBAL_Control, rax
0x18005d9af  jz      short loc_18005D9DE
0x18005d9b1  call    cs:__imp_GetLastError
0x18005d9b8  nop     dword ptr [rax+rax+00h]
0x18005d9bd  mov     rcx, cs:WPP_GLOBAL_Control
0x18005d9c4  mov     edx, 331h
0x18005d9c9  mov     ebx, eax
0x18005d9cb  mov     r9d, eax
0x18005d9ce  mov     rcx, [rcx+10h]
0x18005d9d2  lea     r8, WPP_eb8ccc023461353daee6fb3f53c7a16f_Traceguids
0x18005d9d9  call    WPP_SF_d
0x18005d9de  mov     eax, ebx
0x18005d9e0  jmp     short loc_18005D9E7
0x18005d9e2  mov     eax, 57h ; 'W'
0x18005d9e7  add     rsp, 48h
0x18005d9eb  pop     r15
0x18005d9ed  pop     r14
0x18005d9ef  pop     r13
0x18005d9f1  pop     r12
0x18005d9f3  pop     rdi
0x18005d9f4  pop     rsi
0x18005d9f5  pop     rbp
0x18005d9f6  pop     rbx
0x18005d9f7  retn
```
