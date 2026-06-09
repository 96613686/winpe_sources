# RasEapQueryUserBlobFromCredentialInputFields

- ea: `0x18005a4a0`
- end: `0x18005a630`
- name: `RasEapQueryUserBlobFromCredentialInputFields`
- size: `400`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x180004bd0`
- `0x180050b0c`
- `0x18005611c`
- `0x18005a4a0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005a53f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005a5ef`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005a53f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005a5ef`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18005a5d5`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18005a5d5`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18005a535`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18005a535`

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
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 815, &WPP_86dfd8e07fac39eb87041706834f74ed_Traceguids, v12);
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
        WPP_SF_d(*((_QWORD *)v15 + 2), v16, &WPP_86dfd8e07fac39eb87041706834f74ed_Traceguids, v17);
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
0x18005a4a0  mov     [rsp+arg_10], r8d
0x18005a4a5  push    rbx
0x18005a4a6  push    rbp
0x18005a4a7  push    rsi
0x18005a4a8  push    rdi
0x18005a4a9  push    r12
0x18005a4ab  push    r13
0x18005a4ad  push    r14
0x18005a4af  push    r15
0x18005a4b1  sub     rsp, 48h
0x18005a4b5  mov     r14, [rsp+88h+arg_28]
0x18005a4bd  xor     ebx, ebx
0x18005a4bf  mov     r13, r9
0x18005a4c2  mov     eax, r8d
0x18005a4c5  mov     r12, rdx
0x18005a4c8  mov     r15d, ecx
0x18005a4cb  test    r14, r14
0x18005a4ce  jz      loc_18005A61A
0x18005a4d4  mov     rdi, [rsp+88h+arg_30]
0x18005a4dc  test    rdi, rdi
0x18005a4df  jz      loc_18005A61A
0x18005a4e5  mov     rsi, [rsp+88h+arg_38]
0x18005a4ed  test    rsi, rsi
0x18005a4f0  jz      loc_18005A61A
0x18005a4f6  mov     r9d, [rsi]
0x18005a4f9  lea     rdx, WPP_GLOBAL_Control
0x18005a500  mov     ebp, ebx
0x18005a502  test    r9d, r9d
0x18005a505  jz      short loc_18005A577
0x18005a507  cmp     [rdi], rbx
0x18005a50a  jz      short loc_18005A577
0x18005a50c  mov     rcx, cs:WPP_GLOBAL_Control
0x18005a513  cmp     rcx, rdx
0x18005a516  jz      short loc_18005A52D
0x18005a518  mov     rcx, [rcx+10h]
0x18005a51c  lea     r8, WPP_86dfd8e07fac39eb87041706834f74ed_Traceguids
0x18005a523  mov     edx, 32Fh
0x18005a528  call    WPP_SF_d
0x18005a52d  mov     [rsi], ebx
0x18005a52f  mov     rcx, r12; hToken
0x18005a532  mov     [rdi], rbx
0x18005a535  call    cs:__imp_ImpersonateLoggedOnUser
0x18005a53b  test    eax, eax
0x18005a53d  jnz     short loc_18005A56B
0x18005a53f  call    cs:__imp_GetLastError
0x18005a545  mov     ebx, eax
0x18005a547  mov     rcx, cs:WPP_GLOBAL_Control
0x18005a54e  lea     rax, WPP_GLOBAL_Control
0x18005a555  cmp     rcx, rax
0x18005a558  jz      loc_18005A616
0x18005a55e  mov     edx, 330h
0x18005a563  mov     r9d, ebx
0x18005a566  jmp     loc_18005A606
0x18005a56b  mov     eax, [rsp+88h+arg_10]
0x18005a572  mov     ebp, 1
0x18005a577  cmp     r15d, 0Dh
0x18005a57b  jnz     short loc_18005A5A0
0x18005a57d  mov     r9d, [rsp+88h+arg_20]; unsigned int
0x18005a585  mov     r8, r13; unsigned __int8 *
0x18005a588  mov     [rsp+88h+var_58], rsi; unsigned int *
0x18005a58d  mov     edx, eax; unsigned int
0x18005a58f  mov     [rsp+88h+var_60], rdi; unsigned __int8 **
0x18005a594  mov     [rsp+88h+var_68], r14; struct _EAP_CONFIG_INPUT_FIELD_ARRAY *
0x18005a599  call    ?EapTlsQueryUserBlobFromCredentialInputFields@@YAKPEAXKPEAEKPEBU_EAP_CONFIG_INPUT_FIELD_ARRAY@@PEAPEAEPEAK@Z; EapTlsQueryUserBlobFromCredentialInputFields(void *,ulong,uchar *,ulong,_EAP_CONFIG_INPUT_FIELD_ARRAY const *,uchar * *,ulong *)
0x18005a59e  jmp     short loc_18005A5CF
0x18005a5a0  mov     ebx, 57h ; 'W'
0x18005a5a5  cmp     r15d, 19h
0x18005a5a9  jnz     short loc_18005A5D1
0x18005a5ab  mov     r9d, [rsp+88h+arg_20]; unsigned int
0x18005a5b3  mov     r8, r13; unsigned __int8 *
0x18005a5b6  mov     [rsp+88h+var_58], rsi; unsigned int *
0x18005a5bb  mov     edx, eax; unsigned int
0x18005a5bd  mov     [rsp+88h+var_60], rdi; unsigned __int8 **
0x18005a5c2  mov     rcx, r12; void *
0x18005a5c5  mov     [rsp+88h+var_68], r14; struct _EAP_CONFIG_INPUT_FIELD_ARRAY *
0x18005a5ca  call    ?PeapQueryUserBlobFromCredentialInputFields@@YAKPEAXKPEAEKPEBU_EAP_CONFIG_INPUT_FIELD_ARRAY@@PEAPEAEPEAK@Z; PeapQueryUserBlobFromCredentialInputFields(void *,ulong,uchar *,ulong,_EAP_CONFIG_INPUT_FIELD_ARRAY const *,uchar * *,ulong *)
0x18005a5cf  mov     ebx, eax
0x18005a5d1  test    ebp, ebp
0x18005a5d3  jz      short loc_18005A616
0x18005a5d5  call    cs:__imp_RevertToSelf
0x18005a5db  test    eax, eax
0x18005a5dd  jnz     short loc_18005A616
0x18005a5df  lea     rax, WPP_GLOBAL_Control
0x18005a5e6  cmp     cs:WPP_GLOBAL_Control, rax
0x18005a5ed  jz      short loc_18005A616
0x18005a5ef  call    cs:__imp_GetLastError
0x18005a5f5  mov     rcx, cs:WPP_GLOBAL_Control
0x18005a5fc  mov     edx, 331h
0x18005a601  mov     ebx, eax
0x18005a603  mov     r9d, eax
0x18005a606  mov     rcx, [rcx+10h]
0x18005a60a  lea     r8, WPP_86dfd8e07fac39eb87041706834f74ed_Traceguids
0x18005a611  call    WPP_SF_d
0x18005a616  mov     eax, ebx
0x18005a618  jmp     short loc_18005A61F
0x18005a61a  mov     eax, 57h ; 'W'
0x18005a61f  add     rsp, 48h
0x18005a623  pop     r15
0x18005a625  pop     r14
0x18005a627  pop     r13
0x18005a629  pop     r12
0x18005a62b  pop     rdi
0x18005a62c  pop     rsi
0x18005a62d  pop     rbp
0x18005a62e  pop     rbx
0x18005a62f  retn
```
