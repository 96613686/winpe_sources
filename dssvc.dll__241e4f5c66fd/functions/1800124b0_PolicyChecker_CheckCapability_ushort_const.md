# PolicyChecker::CheckCapability(ushort const *)

- ea: `0x1800124b0`
- end: `0x1800125bc`
- name: `?CheckCapability@PolicyChecker@@SAHPEBG@Z`
- size: `268`
- prototype: `__int64 __fastcall(const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18000da68`

## callees

- `0x18000417c`
- `0x180006b84`
- `0x180006f78`
- `0x18000bf80`
- `0x18000dee8`
- `0x18000e674`
- `0x1800124b0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012519`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012519`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800124fa`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800124fa`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18001250f`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18001250f`
- `api-ms-win-security-capability-l1-1-0!CapabilityCheck` at `0x18001256b`
- `api-ms-win-security-capability-l1-1-0!CapabilityCheck` at `0x18001256b`

## string_xrefs

- `0x180012533`: `Unable to get client token! HR=0x%x`

## pseudocode

```c
__int64 __fastcall PolicyChecker::CheckCapability(const unsigned __int16 *a1)
{
  int v2; // ebx
  __int64 v3; // rdx
  __int64 v4; // rcx
  __int64 v5; // r8
  __int64 v6; // r9
  void **v7; // rbx
  HANDLE CurrentThread; // rax
  signed int LastError; // eax
  __int64 v10; // rdx
  __int64 v11; // rcx
  __int64 v12; // r8
  __int64 v13; // r9
  DSLogger *v14; // rax
  int v15; // eax
  DSLogger *v16; // rax
  unsigned int v17; // ebx
  int v19; // [rsp+20h] [rbp-10h]
  int v20; // [rsp+28h] [rbp-8h]
  unsigned __int8 v21; // [rsp+58h] [rbp+28h] BYREF
  int v22; // [rsp+60h] [rbp+30h] BYREF
  void *v23; // [rsp+68h] [rbp+38h] BYREF

  v23 = 0;
  v21 = 0;
  v22 = 0;
  v2 = AutoImpersonate<1>::ImpersonateClient(&v22);
  if ( v2 < 0 )
    goto LABEL_2;
  v7 = (void **)tlx::replace<void *,int (*)(void *),&int CloseHandle(void *),0>(&v23);
  CurrentThread = GetCurrentThread();
  if ( !OpenThreadToken(CurrentThread, 8u, 1, v7) )
  {
    LastError = GetLastError();
    v2 = LastError;
    if ( LastError > 0 )
      v2 = (unsigned __int16)LastError | 0x80070000;
    v14 = (DSLogger *)tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get(
                        v11,
                        v10,
                        v12,
                        v13);
    v19 = v2;
    DSLogger::LogError(v14, L"PolicyChecker::CheckCapability", 0x197u, L"Unable to get client token! HR=0x%x", v19);
    if ( v2 < 0 )
    {
LABEL_2:
      AutoImpersonate<1>::RevertToSelf(&v22);
LABEL_8:
      v16 = (DSLogger *)tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get(
                          v4,
                          v3,
                          v5,
                          v6);
      v20 = v2;
      DSLogger::LogError(
        v16,
        L"PolicyChecker::CheckCapability",
        0x1A3u,
        L"Capability check failed for %s. HR=0x%x",
        a1,
        v20);
      goto LABEL_9;
    }
  }
  AutoImpersonate<1>::RevertToSelf(&v22);
  v15 = CapabilityCheck(v23, a1, &v21);
  v2 = v15 | 0x10000000;
  if ( v15 < 0 )
    goto LABEL_8;
LABEL_9:
  v17 = v21;
  tlx::auto_xxx<void *,int (*)(void *),&int CloseHandle(void *),0>::_Delete(&v23);
  return v17;
}

```

## disassembly

```asm
0x1800124b0  push    rbp
0x1800124b2  push    rbx
0x1800124b3  push    rdi
0x1800124b4  mov     rbp, rsp
0x1800124b7  sub     rsp, 30h
0x1800124bb  mov     rdi, rcx
0x1800124be  mov     [rbp+arg_18], 0
0x1800124c6  lea     rcx, [rbp+arg_10]
0x1800124ca  mov     [rbp+arg_8], 0
0x1800124ce  mov     [rbp+arg_10], 0
0x1800124d5  call    ?ImpersonateClient@?$AutoImpersonate@$00@@QEAAJXZ; AutoImpersonate<1>::ImpersonateClient(void)
0x1800124da  mov     ebx, eax
0x1800124dc  test    eax, eax
0x1800124de  jns     short loc_1800124EE
0x1800124e0  lea     rcx, [rbp+arg_10]
0x1800124e4  call    ?RevertToSelf@?$AutoImpersonate@$00@@QEAAJXZ; AutoImpersonate<1>::RevertToSelf(void)
0x1800124e9  jmp     loc_18001257B
0x1800124ee  lea     rcx, [rbp+arg_18]
0x1800124f2  call    ??$replace@PEAXP6AHPEAX@Z$1?CloseHandle@@YAH0@Z$0A@@tlx@@YAPEAPEAXAEAV?$auto_xxx@PEAXP6AHPEAX@Z$1?CloseHandle@@YAH0@Z$0A@@0@@Z; tlx::replace<void *,int (*)(void *),&CloseHandle(void *),0>(tlx::auto_xxx<void *,int (*)(void *),&CloseHandle(void *),0> &)
0x1800124f7  mov     rbx, rax
0x1800124fa  call    cs:__imp_GetCurrentThread
0x180012500  mov     edx, 8; DesiredAccess
0x180012505  mov     r9, rbx; TokenHandle
0x180012508  mov     rcx, rax; ThreadHandle
0x18001250b  lea     r8d, [rdx-7]; OpenAsSelf
0x18001250f  call    cs:__imp_OpenThreadToken
0x180012515  test    eax, eax
0x180012517  jnz     short loc_180012557
0x180012519  call    cs:__imp_GetLastError
0x18001251f  mov     ebx, eax
0x180012521  test    eax, eax
0x180012523  jle     short loc_18001252E
0x180012525  movzx   ebx, ax
0x180012528  or      ebx, 80070000h
0x18001252e  call    ?get@?$_LazyImpl@VDSLogger@@V?$lazy_construct@VDSLogger@@@tlx@@V?$static_lazy@VDSLogger@@$0A@V?$lazy_construct@VDSLogger@@@tlx@@@3@@tlx@@QEAAAEAVDSLogger@@XZ; tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get(void)
0x180012533  lea     r9, aUnableToGetCli; "Unable to get client token! HR=0x%x"
0x18001253a  mov     dword ptr [rsp+30h+var_10], ebx
0x18001253e  mov     r8d, 197h; unsigned int
0x180012544  lea     rdx, aPolicycheckerC; "PolicyChecker::CheckCapability"
0x18001254b  mov     rcx, rax; this
0x18001254e  call    ?LogError@DSLogger@@QEAAXPEBGK0ZZ; DSLogger::LogError(ushort const *,ulong,ushort const *,...)
0x180012553  test    ebx, ebx
0x180012555  js      short loc_1800124E0
0x180012557  lea     rcx, [rbp+arg_10]
0x18001255b  call    ?RevertToSelf@?$AutoImpersonate@$00@@QEAAJXZ; AutoImpersonate<1>::RevertToSelf(void)
0x180012560  mov     rcx, [rbp+arg_18]
0x180012564  lea     r8, [rbp+arg_8]
0x180012568  mov     rdx, rdi
0x18001256b  call    cs:__imp_CapabilityCheck
0x180012571  mov     ebx, eax
0x180012573  or      ebx, 10000000h
0x180012579  jge     short loc_1800125A5
0x18001257b  call    ?get@?$_LazyImpl@VDSLogger@@V?$lazy_construct@VDSLogger@@@tlx@@V?$static_lazy@VDSLogger@@$0A@V?$lazy_construct@VDSLogger@@@tlx@@@3@@tlx@@QEAAAEAVDSLogger@@XZ; tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get(void)
0x180012580  lea     r9, aCapabilityChec; "Capability check failed for %s. HR=0x%x"
0x180012587  mov     [rsp+30h+var_8], ebx
0x18001258b  mov     r8d, 1A3h; unsigned int
0x180012591  mov     [rsp+30h+var_10], rdi
0x180012596  lea     rdx, aPolicycheckerC; "PolicyChecker::CheckCapability"
0x18001259d  mov     rcx, rax; this
0x1800125a0  call    ?LogError@DSLogger@@QEAAXPEBGK0ZZ; DSLogger::LogError(ushort const *,ulong,ushort const *,...)
0x1800125a5  movzx   ebx, [rbp+arg_8]
0x1800125a9  lea     rcx, [rbp+arg_18]
0x1800125ad  call    ?_Delete@?$auto_xxx@PEAXP6AHPEAX@Z$1?CloseHandle@@YAH0@Z$0A@@tlx@@AEAAXXZ; tlx::auto_xxx<void *,int (*)(void *),&CloseHandle(void *),0>::_Delete(void)
0x1800125b2  mov     eax, ebx
0x1800125b4  add     rsp, 30h
0x1800125b8  pop     rdi
0x1800125b9  pop     rbx
0x1800125ba  pop     rbp
0x1800125bb  retn
```
