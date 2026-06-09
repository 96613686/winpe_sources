# AutoImpersonate<2>::ImpersonateCallingUserWithEnterpriseContext(void)

- ea: `0x18000ddb8`
- end: `0x18000dee0`
- name: `?ImpersonateCallingUserWithEnterpriseContext@?$AutoImpersonate@$01@@QEAAJXZ`
- size: `296`
- prototype: `__int64 __fastcall(_DWORD *)`
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18000ca4c`
- `0x18000d3e4`

## callees

- `0x18000417c`
- `0x180006b84`
- `0x18000ddb8`
- `0x18000dee8`
- `0x18000e674`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18000ddfa`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18000ddfa`
- `ntdll!NtOpenThreadToken` at `0x18000de0e`
- `ntdll!NtOpenThreadToken` at `0x18000de0e`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18000de79`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18000de79`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserContext` at `0x18000de4d`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserContext` at `0x18000de4d`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserToken` at `0x18000de69`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserToken` at `0x18000de69`
- `srpapi!SrpInheritEnterpriseContext` at `0x18000deaa`
- `srpapi!SrpInheritEnterpriseContext` at `0x18000deaa`

## pseudocode

```c
__int64 __fastcall AutoImpersonate<2>::ImpersonateCallingUserWithEnterpriseContext(_DWORD *a1)
{
  int UserToken; // ebx
  void **v3; // rbx
  HANDLE CurrentThread; // rax
  NTSTATUS v5; // eax
  __int64 v6; // rax
  __int64 v7; // rax
  __int64 v9; // [rsp+20h] [rbp-10h] BYREF
  int v10; // [rsp+50h] [rbp+20h] BYREF
  __int64 v11; // [rsp+58h] [rbp+28h] BYREF
  HANDLE hToken; // [rsp+60h] [rbp+30h] BYREF
  __int64 v13; // [rsp+68h] [rbp+38h] BYREF

  UserToken = 0;
  if ( !*a1 )
  {
    v10 = 0;
    UserToken = AutoImpersonate<1>::ImpersonateClient(&v10);
    if ( UserToken >= 0 )
    {
      v11 = 0;
      v3 = (void **)tlx::replace<void *,int (*)(void *),&int CloseHandle(void *),0>(&v11);
      CurrentThread = GetCurrentThread();
      v5 = NtOpenThreadToken(CurrentThread, 0xF01FFu, 0, v3);
      UserToken = v5 | 0x10000000;
      if ( v5 >= 0 )
      {
        UserToken = AutoImpersonate<1>::RevertToSelf(&v10);
        if ( UserToken >= 0 )
        {
          hToken = 0;
          v9 = 0;
          UserToken = UMgrQueryUserContext(v11, &v9);
          if ( UserToken >= 0 )
          {
            v6 = tlx::replace<void *,int (*)(void *),&int CloseHandle(void *),0>(&hToken);
            UserToken = UMgrQueryUserToken(v9, v6);
            if ( UserToken >= 0 )
            {
              if ( ImpersonateLoggedOnUser(hToken) )
              {
                *a1 = 1;
                v13 = 0;
                v7 = tlx::replace<void *,int (*)(void *),&int CloseHandle(void *),0>(&v13);
                UserToken = SrpInheritEnterpriseContext(v11, 0, v7);
                tlx::auto_xxx<void *,int (*)(void *),&int CloseHandle(void *),0>::_Delete(&v13);
              }
              else
              {
                UserToken = -2147024891;
              }
            }
          }
          tlx::auto_xxx<void *,int (*)(void *),&int CloseHandle(void *),0>::_Delete(&hToken);
        }
      }
      tlx::auto_xxx<void *,int (*)(void *),&int CloseHandle(void *),0>::_Delete(&v11);
    }
    AutoImpersonate<1>::RevertToSelf(&v10);
  }
  return (unsigned int)UserToken;
}

```

## disassembly

```asm
0x18000ddb8  push    rbp
0x18000ddba  push    rbx
0x18000ddbb  push    rdi
0x18000ddbc  mov     rbp, rsp
0x18000ddbf  sub     rsp, 30h
0x18000ddc3  xor     ebx, ebx
0x18000ddc5  mov     rdi, rcx
0x18000ddc8  cmp     [rcx], ebx
0x18000ddca  jnz     loc_18000DED6
0x18000ddd0  lea     rcx, [rbp+arg_0]
0x18000ddd4  mov     [rbp+arg_0], ebx
0x18000ddd7  call    ?ImpersonateClient@?$AutoImpersonate@$00@@QEAAJXZ; AutoImpersonate<1>::ImpersonateClient(void)
0x18000dddc  mov     ebx, eax
0x18000ddde  test    eax, eax
0x18000dde0  js      loc_18000DECD
0x18000dde6  lea     rcx, [rbp+arg_8]
0x18000ddea  mov     [rbp+arg_8], 0
0x18000ddf2  call    ??$replace@PEAXP6AHPEAX@Z$1?CloseHandle@@YAH0@Z$0A@@tlx@@YAPEAPEAXAEAV?$auto_xxx@PEAXP6AHPEAX@Z$1?CloseHandle@@YAH0@Z$0A@@0@@Z; tlx::replace<void *,int (*)(void *),&CloseHandle(void *),0>(tlx::auto_xxx<void *,int (*)(void *),&CloseHandle(void *),0> &)
0x18000ddf7  mov     rbx, rax
0x18000ddfa  call    cs:__imp_GetCurrentThread
0x18000de00  mov     r9, rbx; TokenHandle
0x18000de03  xor     r8d, r8d; OpenAsSelf
0x18000de06  mov     rcx, rax; ThreadHandle
0x18000de09  mov     edx, 0F01FFh; DesiredAccess
0x18000de0e  call    cs:__imp_NtOpenThreadToken
0x18000de14  mov     ebx, eax
0x18000de16  or      ebx, 10000000h
0x18000de1c  jl      loc_18000DEC4
0x18000de22  lea     rcx, [rbp+arg_0]
0x18000de26  call    ?RevertToSelf@?$AutoImpersonate@$00@@QEAAJXZ; AutoImpersonate<1>::RevertToSelf(void)
0x18000de2b  mov     ebx, eax
0x18000de2d  test    eax, eax
0x18000de2f  js      loc_18000DEC4
0x18000de35  mov     rcx, [rbp+arg_8]
0x18000de39  lea     rdx, [rbp+var_10]
0x18000de3d  mov     [rbp+hToken], 0
0x18000de45  mov     [rbp+var_10], 0
0x18000de4d  call    cs:__imp_UMgrQueryUserContext
0x18000de53  lea     rcx, [rbp+hToken]
0x18000de57  mov     ebx, eax
0x18000de59  test    eax, eax
0x18000de5b  js      short loc_18000DEBF
0x18000de5d  call    ??$replace@PEAXP6AHPEAX@Z$1?CloseHandle@@YAH0@Z$0A@@tlx@@YAPEAPEAXAEAV?$auto_xxx@PEAXP6AHPEAX@Z$1?CloseHandle@@YAH0@Z$0A@@0@@Z; tlx::replace<void *,int (*)(void *),&CloseHandle(void *),0>(tlx::auto_xxx<void *,int (*)(void *),&CloseHandle(void *),0> &)
0x18000de62  mov     rcx, [rbp+var_10]
0x18000de66  mov     rdx, rax
0x18000de69  call    cs:__imp_UMgrQueryUserToken
0x18000de6f  mov     ebx, eax
0x18000de71  test    eax, eax
0x18000de73  js      short loc_18000DEBB
0x18000de75  mov     rcx, [rbp+hToken]; hToken
0x18000de79  call    cs:__imp_ImpersonateLoggedOnUser
0x18000de7f  test    eax, eax
0x18000de81  jnz     short loc_18000DE8A
0x18000de83  mov     ebx, 80070005h
0x18000de88  jmp     short loc_18000DEBB
0x18000de8a  lea     rcx, [rbp+arg_18]
0x18000de8e  mov     dword ptr [rdi], 1
0x18000de94  mov     [rbp+arg_18], 0
0x18000de9c  call    ??$replace@PEAXP6AHPEAX@Z$1?CloseHandle@@YAH0@Z$0A@@tlx@@YAPEAPEAXAEAV?$auto_xxx@PEAXP6AHPEAX@Z$1?CloseHandle@@YAH0@Z$0A@@0@@Z; tlx::replace<void *,int (*)(void *),&CloseHandle(void *),0>(tlx::auto_xxx<void *,int (*)(void *),&CloseHandle(void *),0> &)
0x18000dea1  mov     rcx, [rbp+arg_8]
0x18000dea5  mov     r8, rax
0x18000dea8  xor     edx, edx
0x18000deaa  call    cs:__imp_SrpInheritEnterpriseContext
0x18000deb0  lea     rcx, [rbp+arg_18]
0x18000deb4  mov     ebx, eax
0x18000deb6  call    ?_Delete@?$auto_xxx@PEAXP6AHPEAX@Z$1?CloseHandle@@YAH0@Z$0A@@tlx@@AEAAXXZ; tlx::auto_xxx<void *,int (*)(void *),&CloseHandle(void *),0>::_Delete(void)
0x18000debb  lea     rcx, [rbp+hToken]
0x18000debf  call    ?_Delete@?$auto_xxx@PEAXP6AHPEAX@Z$1?CloseHandle@@YAH0@Z$0A@@tlx@@AEAAXXZ; tlx::auto_xxx<void *,int (*)(void *),&CloseHandle(void *),0>::_Delete(void)
0x18000dec4  lea     rcx, [rbp+arg_8]
0x18000dec8  call    ?_Delete@?$auto_xxx@PEAXP6AHPEAX@Z$1?CloseHandle@@YAH0@Z$0A@@tlx@@AEAAXXZ; tlx::auto_xxx<void *,int (*)(void *),&CloseHandle(void *),0>::_Delete(void)
0x18000decd  lea     rcx, [rbp+arg_0]
0x18000ded1  call    ?RevertToSelf@?$AutoImpersonate@$00@@QEAAJXZ; AutoImpersonate<1>::RevertToSelf(void)
0x18000ded6  mov     eax, ebx
0x18000ded8  add     rsp, 30h
0x18000dedc  pop     rdi
0x18000dedd  pop     rbx
0x18000dede  pop     rbp
0x18000dedf  retn
```
