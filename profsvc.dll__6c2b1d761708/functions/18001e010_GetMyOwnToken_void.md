# GetMyOwnToken(void * *)

- ea: `0x18001e010`
- end: `0x18001e178`
- name: `?GetMyOwnToken@@YAJPEAPEAX@Z`
- size: `360`
- prototype: `__int64 __fastcall(PHANDLE TokenHandle)`
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18001c980`
- `0x18001ce78`

## callees

- `0x18001e010`
- `0x1800281ec`
- `0x18002df48`
- `0x180030ad0`
- `0x1800364c8`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18001e125`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18001e125`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18001e108`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18001e108`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18001e0be`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18001e15b`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18001e0be`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18001e15b`
- `api-ms-win-security-base-l1-1-0!ImpersonateSelf` at `0x18001e02a`
- `api-ms-win-security-base-l1-1-0!ImpersonateSelf` at `0x18001e02a`
- `ntdll!RtlAdjustPrivilege` at `0x18001e093`
- `ntdll!RtlAdjustPrivilege` at `0x18001e0e1`
- `ntdll!RtlAdjustPrivilege` at `0x18001e093`
- `ntdll!RtlAdjustPrivilege` at `0x18001e0e1`

## pseudocode

```c
__int64 __fastcall GetMyOwnToken(PHANDLE TokenHandle)
{
  const char *v2; // r9
  int LastError; // eax
  char v4; // bl
  unsigned int v5; // edi
  NTSTATUS v7; // eax
  NTSTATUS v8; // eax
  int v9; // eax
  HANDLE CurrentThread; // rax
  const char *v11; // r9
  unsigned int v12; // ebx
  int v13; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  char v15; // [rsp+48h] [rbp+10h] BYREF
  unsigned __int8 OldValue; // [rsp+50h] [rbp+18h] BYREF
  unsigned __int8 v17; // [rsp+58h] [rbp+20h] BYREF

  v15 = 0;
  if ( ImpersonateSelf(SecurityImpersonation) )
  {
    v15 = 1;
    v4 = 1;
  }
  else
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x3D5,
                  (unsigned int)`DaclContainsPackageAndLpacCapabilitySid_'::`2'::AppPackageAuthority.SubAuthority,
                  v2);
    v4 = 0;
    v5 = LastError;
    if ( LastError < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x404,
        (unsigned int)`DaclContainsPackageAndLpacCapabilitySid_'::`2'::AppPackageAuthority.SubAuthority,
        (const char *)(unsigned int)LastError,
        v13);
      return v5;
    }
  }
  OldValue = 0;
  v7 = RtlAdjustPrivilege(0x12u, 1u, 1u, &OldValue);
  if ( v7 < 0 )
  {
    v5 = wil::details::in1diag3::Return_NtStatus(
           retaddr,
           (void *)0x407,
           (unsigned int)`DaclContainsPackageAndLpacCapabilitySid_'::`2'::AppPackageAuthority.SubAuthority,
           (const char *)(unsigned int)v7,
           v13);
    if ( v4 )
      RevertToSelf();
    return v5;
  }
  v17 = 0;
  v8 = RtlAdjustPrivilege(0x11u, 1u, 1u, &v17);
  if ( v8 < 0 )
  {
    v9 = wil::details::in1diag3::Return_NtStatus(
           retaddr,
           (void *)0x40A,
           (unsigned int)`DaclContainsPackageAndLpacCapabilitySid_'::`2'::AppPackageAuthority.SubAuthority,
           (const char *)(unsigned int)v8,
           v13);
LABEL_13:
    v12 = v9;
    CAutoImpersonateSelf::ResetImpersonation((CAutoImpersonateSelf *)&v15);
    return v12;
  }
  CurrentThread = GetCurrentThread();
  if ( !OpenThreadToken(CurrentThread, 0x2000Cu, 1, TokenHandle) )
  {
    v9 = wil::details::in1diag3::Return_GetLastError(
           retaddr,
           (void *)0x40C,
           (unsigned int)`DaclContainsPackageAndLpacCapabilitySid_'::`2'::AppPackageAuthority.SubAuthority,
           v11);
    goto LABEL_13;
  }
  if ( v4 )
    RevertToSelf();
  return 0;
}

```

## disassembly

```asm
0x18001e010  mov     [rsp+arg_0], rbx
0x18001e015  push    rsi
0x18001e016  push    rdi
0x18001e017  push    r14; int
0x18001e019  sub     rsp, 20h
0x18001e01d  mov     rsi, rcx
0x18001e020  mov     [rsp+38h+arg_8], 0
0x18001e025  mov     ecx, 2; ImpersonationLevel
0x18001e02a  call    cs:__imp_ImpersonateSelf
0x18001e031  nop     dword ptr [rax+rax+00h]
0x18001e036  lea     r14, ?AppPackageAuthority@?1??DaclContainsPackageAndLpacCapabilitySid_@@YAHPEAX@Z@4U_SID_IDENTIFIER_AUTHORITY@@B.SubAuthority; _SID_IDENTIFIER_AUTHORITY const `DaclContainsPackageAndLpacCapabilitySid_(void *)'::`2'::AppPackageAuthority ...
0x18001e03d  test    eax, eax
0x18001e03f  jnz     short loc_18001E077
0x18001e041  mov     rcx, [rsp+38h]; this
0x18001e046  mov     r8, r14; unsigned int
0x18001e049  mov     edx, 3D5h; void *
0x18001e04e  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18001e053  xor     bl, bl
0x18001e055  mov     edi, eax
0x18001e057  test    eax, eax
0x18001e059  jns     short loc_18001E07E
0x18001e05b  mov     rcx, [rsp+38h]; this
0x18001e060  mov     r9d, eax; char *
0x18001e063  mov     r8, r14; unsigned int
0x18001e066  mov     edx, 404h; void *
0x18001e06b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001e070  mov     eax, edi
0x18001e072  jmp     loc_18001E169
0x18001e077  mov     [rsp+38h+arg_8], 1
0x18001e07c  mov     bl, 1
0x18001e07e  mov     r8b, 1; ForThread
0x18001e081  mov     [rsp+38h+OldValue], 0
0x18001e086  mov     dl, r8b; NewValue
0x18001e089  lea     r9, [rsp+38h+OldValue]; OldValue
0x18001e08e  mov     ecx, 12h; Privilege
0x18001e093  call    cs:__imp_RtlAdjustPrivilege
0x18001e09a  nop     dword ptr [rax+rax+00h]
0x18001e09f  test    eax, eax
0x18001e0a1  jns     short loc_18001E0CC
0x18001e0a3  mov     rcx, [rsp+38h]; this
0x18001e0a8  mov     r9d, eax; char *
0x18001e0ab  mov     r8, r14; unsigned int
0x18001e0ae  mov     edx, 407h; void *
0x18001e0b3  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x18001e0b8  mov     edi, eax
0x18001e0ba  test    bl, bl
0x18001e0bc  jz      short loc_18001E070
0x18001e0be  call    cs:__imp_RevertToSelf
0x18001e0c5  nop     dword ptr [rax+rax+00h]
0x18001e0ca  jmp     short loc_18001E070
0x18001e0cc  mov     r8b, 1; ForThread
0x18001e0cf  mov     [rsp+38h+arg_18], 0
0x18001e0d4  mov     dl, r8b; NewValue
0x18001e0d7  lea     r9, [rsp+38h+arg_18]; OldValue
0x18001e0dc  mov     ecx, 11h; Privilege
0x18001e0e1  call    cs:__imp_RtlAdjustPrivilege
0x18001e0e8  nop     dword ptr [rax+rax+00h]
0x18001e0ed  test    eax, eax
0x18001e0ef  jns     short loc_18001E108
0x18001e0f1  mov     rcx, [rsp+38h]; this
0x18001e0f6  mov     r9d, eax; char *
0x18001e0f9  mov     r8, r14; unsigned int
0x18001e0fc  mov     edx, 40Ah; void *
0x18001e101  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x18001e106  jmp     short loc_18001E147
0x18001e108  call    cs:__imp_GetCurrentThread
0x18001e10f  nop     dword ptr [rax+rax+00h]
0x18001e114  mov     r9, rsi; TokenHandle
0x18001e117  mov     edx, 2000Ch; DesiredAccess
0x18001e11c  mov     rcx, rax; ThreadHandle
0x18001e11f  mov     r8d, 1; OpenAsSelf
0x18001e125  call    cs:__imp_OpenThreadToken
0x18001e12c  nop     dword ptr [rax+rax+00h]
0x18001e131  test    eax, eax
0x18001e133  jnz     short loc_18001E157
0x18001e135  mov     rcx, [rsp+38h]; this
0x18001e13a  mov     r8, r14; unsigned int
0x18001e13d  mov     edx, 40Ch; void *
0x18001e142  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18001e147  lea     rcx, [rsp+38h+arg_8]; this
0x18001e14c  mov     ebx, eax
0x18001e14e  call    ?ResetImpersonation@CAutoImpersonateSelf@@AEAAXXZ; CAutoImpersonateSelf::ResetImpersonation(void)
0x18001e153  mov     eax, ebx
0x18001e155  jmp     short loc_18001E169
0x18001e157  test    bl, bl
0x18001e159  jz      short loc_18001E167
0x18001e15b  call    cs:__imp_RevertToSelf
0x18001e162  nop     dword ptr [rax+rax+00h]
0x18001e167  xor     eax, eax
0x18001e169  mov     rbx, [rsp+38h+arg_0]
0x18001e16e  add     rsp, 20h
0x18001e172  pop     r14
0x18001e174  pop     rdi
0x18001e175  pop     rsi
0x18001e176  retn
```
