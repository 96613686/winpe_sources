# IsClientSameDomainDc

- ea: `0x14019ce58`
- end: `0x14019d1cc`
- name: `IsClientSameDomainDc`
- size: `884`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14019f8e0`

## callees

- `0x1400036a0`
- `0x14000cdc0`
- `0x14000e34c`
- `0x14004ab40`
- `0x14005c620`
- `0x14019ce58`
- `0x1401b9494`
- `0x1401c5e2c`
- `0x1401c7cd8`

## import_xrefs

- `KERNEL32!GetCurrentThread` at `0x14019cf4d`
- `KERNEL32!GetCurrentThread` at `0x14019cf4d`
- `KERNEL32!GetLastError` at `0x14019cf86`
- `KERNEL32!GetLastError` at `0x14019cffb`
- `KERNEL32!GetLastError` at `0x14019d076`
- `KERNEL32!GetLastError` at `0x14019cf86`
- `KERNEL32!GetLastError` at `0x14019cffb`
- `KERNEL32!GetLastError` at `0x14019d076`
- `KERNEL32!GetCurrentThreadId` at `0x14019cf0c`
- `KERNEL32!GetCurrentThreadId` at `0x14019cf78`
- `KERNEL32!GetCurrentThreadId` at `0x14019cfed`
- `KERNEL32!GetCurrentThreadId` at `0x14019d068`
- `KERNEL32!GetCurrentThreadId` at `0x14019d0bd`
- `KERNEL32!GetCurrentThreadId` at `0x14019cf0c`
- `KERNEL32!GetCurrentThreadId` at `0x14019cf78`
- `KERNEL32!GetCurrentThreadId` at `0x14019cfed`
- `KERNEL32!GetCurrentThreadId` at `0x14019d068`
- `KERNEL32!GetCurrentThreadId` at `0x14019d0bd`
- `ADVAPI32!CheckTokenMembership` at `0x14019cfdd`
- `ADVAPI32!CheckTokenMembership` at `0x14019d058`
- `ADVAPI32!CheckTokenMembership` at `0x14019cfdd`
- `ADVAPI32!CheckTokenMembership` at `0x14019d058`
- `ADVAPI32!OpenThreadToken` at `0x14019cf68`
- `ADVAPI32!OpenThreadToken` at `0x14019cf68`
- `RPCRT4!RpcRevertToSelf` at `0x14019d101`
- `RPCRT4!RpcRevertToSelf` at `0x14019d101`
- `RPCRT4!RpcImpersonateClient` at `0x14019cef6`
- `RPCRT4!RpcImpersonateClient` at `0x14019cef6`

## string_xrefs

- `0x14019d15e`: `Failed to check remote computer domain controller SID. Error:%?`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 IsClientSameDomainDc()
{
  unsigned int v0; // edi
  int v1; // r14d
  struct FrsStatus *LocalAccountDomainControllerSid; // rax
  struct FrsStatus *v3; // rbx
  unsigned int v4; // esi
  DWORD CurrentThreadId; // eax
  __int64 v6; // rcx
  HANDLE CurrentThread; // rax
  DWORD v8; // ebx
  DWORD LastError; // eax
  __int64 v10; // rcx
  DWORD v11; // ebx
  DWORD v12; // eax
  __int64 v13; // rcx
  DWORD v14; // ebx
  DWORD v15; // eax
  __int64 v16; // rcx
  DWORD v17; // eax
  __int64 v18; // rcx
  WINBOOL IsMember[2]; // [rsp+58h] [rbp-B0h] BYREF
  struct FrsStatus *v21; // [rsp+60h] [rbp-A8h] BYREF
  void *TokenHandle; // [rsp+68h] [rbp-A0h] BYREF
  _QWORD v23[3]; // [rsp+70h] [rbp-98h] BYREF
  _BYTE v24[8]; // [rsp+88h] [rbp-80h] BYREF
  _BYTE v25[120]; // [rsp+90h] [rbp-78h] BYREF
  _BYTE v26[8]; // [rsp+108h] [rbp+0h] BYREF
  _BYTE SidToCheck[120]; // [rsp+110h] [rbp+8h] BYREF

  Sid::Sid((Sid *)v26);
  Sid::Sid((Sid *)v24);
  v0 = 0;
  v1 = 0;
  TokenHandle = 0;
  LocalAccountDomainControllerSid = Sid::MakeLocalAccountDomainControllerSid((Sid *)v26, 0);
  v3 = LocalAccountDomainControllerSid;
  v21 = LocalAccountDomainControllerSid;
  if ( !LocalAccountDomainControllerSid )
  {
    LocalAccountDomainControllerSid = Sid::MakeLocalAccountDomainControllerSid((Sid *)v24, 1);
    v3 = LocalAccountDomainControllerSid;
    v21 = LocalAccountDomainControllerSid;
  }
  if ( !LocalAccountDomainControllerSid )
  {
    v4 = RpcImpersonateClient(0);
    if ( v4 )
    {
      CurrentThreadId = GetCurrentThreadId();
      v3 = (struct FrsStatus *)FrsStatusList::PushNewError(
                                 v6,
                                 v4,
                                 0,
                                 1,
                                 "base\\fs\\remotefs\\frs\\src\\transport\\servertransport.cpp",
                                 "IsClientSameDomainDc",
                                 339,
                                 CurrentThreadId,
                                 0);
      v21 = v3;
      if ( v3 )
        goto LABEL_8;
    }
    else
    {
      v1 = 1;
    }
    CurrentThread = GetCurrentThread();
    if ( !OpenThreadToken(CurrentThread, 8u, 0, &TokenHandle) )
    {
      v8 = GetCurrentThreadId();
      LastError = GetLastError();
      v3 = (struct FrsStatus *)FrsStatusList::PushNewError(
                                 v10,
                                 LastError,
                                 0,
                                 1,
                                 "base\\fs\\remotefs\\frs\\src\\transport\\servertransport.cpp",
                                 "IsClientSameDomainDc",
                                 351,
                                 v8,
                                 0);
      v21 = v3;
    }
  }
LABEL_8:
  if ( !v3 )
  {
    IsMember[0] = 0;
    if ( CheckTokenMembership(TokenHandle, SidToCheck, IsMember)
      || (v11 = GetCurrentThreadId(),
          v12 = GetLastError(),
          v3 = (struct FrsStatus *)FrsStatusList::PushNewError(
                                     v13,
                                     v12,
                                     0,
                                     1,
                                     "base\\fs\\remotefs\\frs\\src\\transport\\servertransport.cpp",
                                     "IsClientSameDomainDc",
                                     362,
                                     v11,
                                     0),
          (v21 = v3) == 0) )
    {
      if ( !IsMember[0] )
      {
        if ( CheckTokenMembership(TokenHandle, v25, IsMember)
          || (v14 = GetCurrentThreadId(),
              v15 = GetLastError(),
              v3 = (struct FrsStatus *)FrsStatusList::PushNewError(
                                         v16,
                                         v15,
                                         0,
                                         1,
                                         "base\\fs\\remotefs\\frs\\src\\transport\\servertransport.cpp",
                                         "IsClientSameDomainDc",
                                         371,
                                         v14,
                                         0),
              (v21 = v3) == 0) )
        {
          if ( !IsMember[0] )
          {
            v17 = GetCurrentThreadId();
            v3 = (struct FrsStatus *)FrsStatusList::PushNewError(
                                       v18,
                                       1168,
                                       0,
                                       1,
                                       "base\\fs\\remotefs\\frs\\src\\transport\\servertransport.cpp",
                                       "IsClientSameDomainDc",
                                       377,
                                       v17,
                                       0);
            v21 = v3;
          }
        }
      }
    }
  }
  if ( v1 )
    RpcRevertToSelf();
  CloseHandleEx(&TokenHandle);
  if ( v3 )
  {
    if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 2 )
    {
      v23[0] = L"IsClientSameDomainDc";
      v23[1] = 0x200000187LL;
      v23[2] = L"SRTR";
      dbgobj::DbgPrint<unsigned short,FrsStatus>(
        v23,
        L"Failed to check remote computer domain controller SID. Error:%?",
        v3);
    }
    CLEAR_ERROR(&v21);
  }
  else
  {
    v0 = 1;
  }
  Sid::~Sid((Sid *)v24);
  Sid::~Sid((Sid *)v26);
  return v0;
}

```

## disassembly

```asm
0x14019ce58  mov     rax, rsp
0x14019ce5b  mov     [rax+8], rbx
0x14019ce5f  mov     [rax+10h], rsi
0x14019ce63  mov     [rax+18h], rdi
0x14019ce67  push    rbp
0x14019ce68  push    r12
0x14019ce6a  push    r13
0x14019ce6c  push    r14
0x14019ce6e  push    r15
0x14019ce70  lea     rbp, [rax-0B8h]
0x14019ce77  sub     rsp, 190h
0x14019ce7e  mov     rax, cs:__security_cookie
0x14019ce85  xor     rax, rsp
0x14019ce88  mov     [rbp+0B0h+var_30], rax
0x14019ce8f  lea     rcx, [rbp+0B0h+var_B0]; this
0x14019ce93  call    ??0Sid@@QEAA@XZ; Sid::Sid(void)
0x14019ce98  nop
0x14019ce99  lea     rcx, [rbp+0B0h+var_130]; this
0x14019ce9d  call    ??0Sid@@QEAA@XZ; Sid::Sid(void)
0x14019cea2  nop
0x14019cea3  xor     edi, edi
0x14019cea5  mov     r14d, edi
0x14019cea8  mov     [rsp+1B0h+TokenHandle], rdi
0x14019cead  xor     edx, edx; int
0x14019ceaf  lea     rcx, [rbp+0B0h+var_B0]; this
0x14019ceb3  call    ?MakeLocalAccountDomainControllerSid@Sid@@QEAAPEAVFrsStatus@@H@Z; Sid::MakeLocalAccountDomainControllerSid(int)
0x14019ceb8  mov     rbx, rax
0x14019cebb  mov     [rsp+1B0h+var_158], rax
0x14019cec0  lea     r15d, [rdi+1]
0x14019cec4  test    rax, rax
0x14019cec7  jnz     short loc_14019CEDD
0x14019cec9  mov     edx, r15d; int
0x14019cecc  lea     rcx, [rbp+0B0h+var_130]; this
0x14019ced0  call    ?MakeLocalAccountDomainControllerSid@Sid@@QEAAPEAVFrsStatus@@H@Z; Sid::MakeLocalAccountDomainControllerSid(int)
0x14019ced5  mov     rbx, rax
0x14019ced8  mov     [rsp+1B0h+var_158], rax
0x14019cedd  lea     r12, aIsclientsamedo; "IsClientSameDomainDc"
0x14019cee4  lea     r13, aBaseFsRemotefs_11; "base\\fs\\remotefs\\frs\\src\\transport"...
0x14019ceeb  test    rax, rax
0x14019ceee  jnz     loc_14019CFC2
0x14019cef4  xor     ecx, ecx; BindingHandle
0x14019cef6  call    cs:__imp_RpcImpersonateClient
0x14019cefd  nop     dword ptr [rax+rax+00h]
0x14019cf02  mov     esi, eax
0x14019cf04  test    eax, eax
0x14019cf06  jz      loc_14019D17B
0x14019cf0c  call    cs:__imp_GetCurrentThreadId
0x14019cf13  nop     dword ptr [rax+rax+00h]
0x14019cf18  mov     [rsp+1B0h+var_170], rdi
0x14019cf1d  mov     dword ptr [rsp+1B0h+var_178], eax
0x14019cf21  mov     [rsp+1B0h+var_180], 153h
0x14019cf29  mov     qword ptr [rsp+1B0h+var_188], r12
0x14019cf2e  mov     [rsp+1B0h+var_190], r13
0x14019cf33  mov     r9d, r15d
0x14019cf36  xor     r8d, r8d
0x14019cf39  mov     edx, esi
0x14019cf3b  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x14019cf40  mov     rbx, rax
0x14019cf43  mov     [rsp+1B0h+var_158], rax
0x14019cf48  test    rax, rax
0x14019cf4b  jnz     short loc_14019CFC2
0x14019cf4d  call    cs:__imp_GetCurrentThread
0x14019cf54  nop     dword ptr [rax+rax+00h]
0x14019cf59  mov     rcx, rax; ThreadHandle
0x14019cf5c  lea     r9, [rsp+1B0h+TokenHandle]; TokenHandle
0x14019cf61  xor     r8d, r8d; OpenAsSelf
0x14019cf64  lea     edx, [r8+8]; DesiredAccess
0x14019cf68  call    cs:__imp_OpenThreadToken
0x14019cf6f  nop     dword ptr [rax+rax+00h]
0x14019cf74  test    eax, eax
0x14019cf76  jnz     short loc_14019CFC2
0x14019cf78  call    cs:__imp_GetCurrentThreadId
0x14019cf7f  nop     dword ptr [rax+rax+00h]
0x14019cf84  mov     ebx, eax
0x14019cf86  call    cs:__imp_GetLastError
0x14019cf8d  nop     dword ptr [rax+rax+00h]
0x14019cf92  mov     [rsp+1B0h+var_170], rdi
0x14019cf97  mov     dword ptr [rsp+1B0h+var_178], ebx
0x14019cf9b  mov     [rsp+1B0h+var_180], 15Fh
0x14019cfa3  mov     qword ptr [rsp+1B0h+var_188], r12
0x14019cfa8  mov     [rsp+1B0h+var_190], r13
0x14019cfad  mov     r9d, r15d
0x14019cfb0  xor     r8d, r8d
0x14019cfb3  mov     edx, eax
0x14019cfb5  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x14019cfba  mov     rbx, rax
0x14019cfbd  mov     [rsp+1B0h+var_158], rax
0x14019cfc2  test    rbx, rbx
0x14019cfc5  jnz     loc_14019D0FC
0x14019cfcb  mov     [rsp+1B0h+IsMember], edi
0x14019cfcf  lea     r8, [rsp+1B0h+IsMember]; IsMember
0x14019cfd4  lea     rdx, [rbp+0B0h+SidToCheck]; SidToCheck
0x14019cfd8  mov     rcx, [rsp+1B0h+TokenHandle]; TokenHandle
0x14019cfdd  call    cs:__imp_CheckTokenMembership
0x14019cfe4  nop     dword ptr [rax+rax+00h]
0x14019cfe9  test    eax, eax
0x14019cfeb  jnz     short loc_14019D040
0x14019cfed  call    cs:__imp_GetCurrentThreadId
0x14019cff4  nop     dword ptr [rax+rax+00h]
0x14019cff9  mov     ebx, eax
0x14019cffb  call    cs:__imp_GetLastError
0x14019d002  nop     dword ptr [rax+rax+00h]
0x14019d007  mov     [rsp+1B0h+var_170], rdi
0x14019d00c  mov     dword ptr [rsp+1B0h+var_178], ebx
0x14019d010  mov     [rsp+1B0h+var_180], 16Ah
0x14019d018  mov     qword ptr [rsp+1B0h+var_188], r12
0x14019d01d  mov     [rsp+1B0h+var_190], r13
0x14019d022  mov     r9d, r15d
0x14019d025  xor     r8d, r8d
0x14019d028  mov     edx, eax
0x14019d02a  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x14019d02f  mov     rbx, rax
0x14019d032  mov     [rsp+1B0h+var_158], rax
0x14019d037  test    rax, rax
0x14019d03a  jnz     loc_14019D0FC
0x14019d040  cmp     [rsp+1B0h+IsMember], edi
0x14019d044  jnz     loc_14019D0FC
0x14019d04a  lea     r8, [rsp+1B0h+IsMember]; IsMember
0x14019d04f  lea     rdx, [rbp+0B0h+var_128]; SidToCheck
0x14019d053  mov     rcx, [rsp+1B0h+TokenHandle]; TokenHandle
0x14019d058  call    cs:__imp_CheckTokenMembership
0x14019d05f  nop     dword ptr [rax+rax+00h]
0x14019d064  test    eax, eax
0x14019d066  jnz     short loc_14019D0B7
0x14019d068  call    cs:__imp_GetCurrentThreadId
0x14019d06f  nop     dword ptr [rax+rax+00h]
0x14019d074  mov     ebx, eax
0x14019d076  call    cs:__imp_GetLastError
0x14019d07d  nop     dword ptr [rax+rax+00h]
0x14019d082  mov     [rsp+1B0h+var_170], rdi
0x14019d087  mov     dword ptr [rsp+1B0h+var_178], ebx
0x14019d08b  mov     [rsp+1B0h+var_180], 173h
0x14019d093  mov     qword ptr [rsp+1B0h+var_188], r12
0x14019d098  mov     [rsp+1B0h+var_190], r13
0x14019d09d  mov     r9d, r15d
0x14019d0a0  xor     r8d, r8d
0x14019d0a3  mov     edx, eax
0x14019d0a5  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x14019d0aa  mov     rbx, rax
0x14019d0ad  mov     [rsp+1B0h+var_158], rax
0x14019d0b2  test    rax, rax
0x14019d0b5  jnz     short loc_14019D0FC
0x14019d0b7  cmp     [rsp+1B0h+IsMember], edi
0x14019d0bb  jnz     short loc_14019D0FC
0x14019d0bd  call    cs:__imp_GetCurrentThreadId
0x14019d0c4  nop     dword ptr [rax+rax+00h]
0x14019d0c9  mov     [rsp+1B0h+var_170], rdi
0x14019d0ce  mov     dword ptr [rsp+1B0h+var_178], eax
0x14019d0d2  mov     [rsp+1B0h+var_180], 179h
0x14019d0da  mov     qword ptr [rsp+1B0h+var_188], r12
0x14019d0df  mov     [rsp+1B0h+var_190], r13
0x14019d0e4  mov     r9d, r15d
0x14019d0e7  xor     r8d, r8d
0x14019d0ea  mov     edx, 490h
0x14019d0ef  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x14019d0f4  mov     rbx, rax
0x14019d0f7  mov     [rsp+1B0h+var_158], rax
0x14019d0fc  test    r14d, r14d
0x14019d0ff  jz      short loc_14019D10D
0x14019d101  call    cs:__imp_RpcRevertToSelf
0x14019d108  nop     dword ptr [rax+rax+00h]
0x14019d10d  lea     rcx, [rsp+1B0h+TokenHandle]; void **
0x14019d112  call    ?CloseHandleEx@@YAXAEAPEAX@Z; CloseHandleEx(void * &)
0x14019d117  test    rbx, rbx
0x14019d11a  jz      short loc_14019D183
0x14019d11c  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x14019d123  test    rax, rax
0x14019d126  jz      short loc_14019D16F
0x14019d128  cmp     [rax+40h], edi
0x14019d12b  jz      short loc_14019D16F
0x14019d12d  cmp     dword ptr [rax+38h], 2
0x14019d131  jl      short loc_14019D16F
0x14019d133  lea     rax, aIsclientsamedo_0; "IsClientSameDomainDc"
0x14019d13a  mov     qword ptr [rsp+1B0h+var_148], rax
0x14019d13f  mov     dword ptr [rsp+1B0h+var_140], 187h
0x14019d147  mov     dword ptr [rsp+1B0h+var_140+4], 2
0x14019d14f  lea     rax, aSrtr; "SRTR"
0x14019d156  mov     [rsp+1B0h+var_138], rax
0x14019d15b  mov     r8, rbx
0x14019d15e  lea     rdx, aFailedToCheckR; "Failed to check remote computer domain "...
0x14019d165  lea     rcx, [rsp+1B0h+var_148]
0x14019d16a  call    ??$DbgPrint@GVFrsStatus@@@dbgobj@@QEAA_KPEBGAEBVFrsStatus@@@Z; dbgobj::DbgPrint<ushort,FrsStatus>(ushort const *,FrsStatus const &)
0x14019d16f  lea     rcx, [rsp+1B0h+var_158]; struct FrsStatus **
0x14019d174  call    ?CLEAR_ERROR@@YAXAEAPEAVFrsStatus@@@Z; CLEAR_ERROR(FrsStatus * &)
0x14019d179  jmp     short loc_14019D186
0x14019d17b  mov     r14d, r15d
0x14019d17e  jmp     loc_14019CF4D
0x14019d183  mov     edi, r15d
0x14019d186  lea     rcx, [rbp+0B0h+var_130]; this
0x14019d18a  call    ??1Sid@@UEAA@XZ; Sid::~Sid(void)
0x14019d18f  nop
0x14019d190  lea     rcx, [rbp+0B0h+var_B0]; this
0x14019d194  call    ??1Sid@@UEAA@XZ; Sid::~Sid(void)
0x14019d199  mov     eax, edi
0x14019d19b  mov     rcx, [rbp+0B0h+var_30]
0x14019d1a2  xor     rcx, rsp; StackCookie
0x14019d1a5  call    __security_check_cookie
0x14019d1aa  lea     r11, [rsp+1B0h+var_20]
0x14019d1b2  mov     rbx, [r11+30h]
0x14019d1b6  mov     rsi, [r11+38h]
0x14019d1ba  mov     rdi, [r11+40h]
0x14019d1be  mov     rsp, r11
0x14019d1c1  pop     r15
0x14019d1c3  pop     r14
0x14019d1c5  pop     r13
0x14019d1c7  pop     r12
0x14019d1c9  pop     rbp
0x14019d1ca  retn
```
