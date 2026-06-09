# Trust::IsCallerLocalService(void)

- ea: `0x18003f328`
- end: `0x18003f4a3`
- name: `?IsCallerLocalService@Trust@@YA_NXZ`
- size: `379`
- prototype: `bool __fastcall()`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180022540`

## callees

- `0x180002790`
- `0x180012770`
- `0x180012bc8`
- `0x180029ff8`
- `0x18003f328`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003f3a8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003f416`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003f3a8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003f416`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x18003f385`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x18003f385`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18003f3dc`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x18003f3f3`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x18003f3f3`

## pseudocode

```c
bool __fastcall Trust::IsCallerLocalService()
{
  bool v0; // bl
  DWORD v1; // eax
  unsigned __int16 v2; // dx
  DWORD LastError; // eax
  ScopeGuardImpl1<void (__cdecl*)(void *),WWAN_INTERFACE_OBJECT *> j; // [rsp+60h] [rbp+17h] BYREF
  void *sid; // [rsp+78h] [rbp+2Fh] BYREF
  _SID_IDENTIFIER_AUTHORITY NtAuthority; // [rsp+80h] [rbp+37h] BYREF
  int isMember; // [rsp+88h] [rbp+3Fh] BYREF

  v0 = 0;
  *(_WORD *)&NtAuthority.Value[4] = 1280;
  *(_DWORD *)NtAuthority.Value = 0;
  sid = 0;
  if ( AllocateAndInitializeSid(&NtAuthority, 1u, 0x13u, 0, 0, 0, 0, 0, 0, 0, &sid) )
  {
    j.fun_ = (void (__fastcall *)(void *))FreeSid;
    j.p1_ = (WWAN_INTERFACE_OBJECT *const)sid;
    j.dismissed_ = 0;
    isMember = 0;
    if ( CheckTokenMembership(0, sid, &isMember) )
    {
      if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
        && (WPP_GLOBAL_Control->ReserveSpace[28] & 0x10) != 0 )
      {
        WPP_SF_d(
          WPP_GLOBAL_Control->Control.Logger,
          0xCu,
          WPP_9a7550d4dd9638825a8f1b31a61a0fd5_Traceguids,
          isMember != 0);
      }
      v0 = isMember != 0;
    }
    else if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
           && (WPP_GLOBAL_Control->ReserveSpace[28] & 2) != 0 )
    {
      LastError = GetLastError();
      WPP_SF_d(WPP_GLOBAL_Control->Control.Logger, 0xBu, WPP_9a7550d4dd9638825a8f1b31a61a0fd5_Traceguids, LastError);
    }
    ScopeGuardImplBase::SafeExecute<ScopeGuardImpl1<void (*)(void *),WWAN_INTERFACE_OBJECT *>>(&j);
    return v0;
  }
  else
  {
    if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
      && (WPP_GLOBAL_Control->ReserveSpace[28] & 2) != 0 )
    {
      v1 = GetLastError();
      WPP_SF_dD(WPP_GLOBAL_Control->Control.Logger, v2, WPP_9a7550d4dd9638825a8f1b31a61a0fd5_Traceguids, 19, v1);
    }
    return 0;
  }
}

```

## disassembly

```asm
0x18003f328  mov     [rsp-8+arg_0], rbx
0x18003f32d  push    rbp
0x18003f32e  lea     rbp, [rsp-57h]
0x18003f333  sub     rsp, 0A0h
0x18003f33a  mov     rax, cs:__security_cookie
0x18003f341  xor     rax, rsp
0x18003f344  mov     [rbp+57h+var_10], rax
0x18003f348  xor     ebx, ebx
0x18003f34a  mov     word ptr [rbp+57h+NtAuthority.Value+4], 500h
0x18003f350  lea     rax, [rbp+57h+sid]
0x18003f354  mov     dword ptr [rbp+57h+NtAuthority.Value], ebx
0x18003f357  mov     [rsp+0A0h+pSid], rax; pSid
0x18003f35c  lea     rcx, [rbp+57h+NtAuthority]; pIdentifierAuthority
0x18003f360  mov     [rsp+0A0h+nSubAuthority7], ebx; nSubAuthority7
0x18003f364  xor     r9d, r9d; nSubAuthority1
0x18003f367  mov     [rsp+0A0h+nSubAuthority6], ebx; nSubAuthority6
0x18003f36b  lea     r8d, [rbx+13h]; nSubAuthority0
0x18003f36f  mov     [rsp+0A0h+nSubAuthority5], ebx; nSubAuthority5
0x18003f373  mov     dl, 1; nSubAuthorityCount
0x18003f375  mov     [rsp+0A0h+nSubAuthority4], ebx; nSubAuthority4
0x18003f379  mov     [rsp+0A0h+nSubAuthority3], ebx; nSubAuthority3
0x18003f37d  mov     [rsp+0A0h+nSubAuthority2], ebx; nSubAuthority2
0x18003f381  mov     [rbp+57h+sid], rbx
0x18003f385  call    cs:__imp_AllocateAndInitializeSid
0x18003f38b  test    eax, eax
0x18003f38d  jnz     short loc_18003F3D4
0x18003f38f  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x18003f396  lea     rax, WPP_GLOBAL_Control
0x18003f39d  cmp     rcx, rax
0x18003f3a0  jz      short loc_18003F3CD
0x18003f3a2  test    byte ptr [rcx+1Ch], 2
0x18003f3a6  jz      short loc_18003F3CD
0x18003f3a8  call    cs:__imp_GetLastError
0x18003f3ae  mov     rcx, cs:WPP_GLOBAL_Control
0x18003f3b5  lea     r9d, [rbx+13h]; _a2
0x18003f3b9  lea     r8, WPP_9a7550d4dd9638825a8f1b31a61a0fd5_Traceguids; _a1
0x18003f3c0  mov     [rsp+0A0h+nSubAuthority2], eax; Logger
0x18003f3c4  mov     rcx, [rcx+10h]; Logger
0x18003f3c8  call    WPP_SF_dD
0x18003f3cd  xor     al, al
0x18003f3cf  jmp     loc_18003F486
0x18003f3d4  mov     rdx, [rbp+57h+sid]; SidToCheck
0x18003f3d8  lea     r8, [rbp+57h+isMember]; IsMember
0x18003f3dc  mov     rax, cs:__imp_FreeSid
0x18003f3e3  xor     ecx, ecx; TokenHandle
0x18003f3e5  mov     [rbp+57h+j.fun_], rax
0x18003f3e9  mov     [rbp+57h+j.p1_], rdx
0x18003f3ed  mov     [rbp+57h+j.dismissed_], bl
0x18003f3f0  mov     [rbp+57h+isMember], ebx
0x18003f3f3  call    cs:__imp_CheckTokenMembership
0x18003f3f9  test    eax, eax
0x18003f3fb  jnz     short loc_18003F43D
0x18003f3fd  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x18003f404  lea     rax, WPP_GLOBAL_Control
0x18003f40b  cmp     rcx, rax
0x18003f40e  jz      short loc_18003F47B
0x18003f410  test    byte ptr [rcx+1Ch], 2
0x18003f414  jz      short loc_18003F47B
0x18003f416  call    cs:__imp_GetLastError
0x18003f41c  mov     rcx, cs:WPP_GLOBAL_Control
0x18003f423  lea     r8, WPP_9a7550d4dd9638825a8f1b31a61a0fd5_Traceguids; TraceGuid
0x18003f42a  mov     edx, 0Bh; id
0x18003f42f  mov     r9d, eax; _a1
0x18003f432  mov     rcx, [rcx+10h]; Logger
0x18003f436  call    WPP_SF_d
0x18003f43b  jmp     short loc_18003F47B
0x18003f43d  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x18003f444  lea     rax, WPP_GLOBAL_Control
0x18003f44b  cmp     rcx, rax
0x18003f44e  jz      short loc_18003F475
0x18003f450  test    byte ptr [rcx+1Ch], 10h
0x18003f454  jz      short loc_18003F475
0x18003f456  cmp     [rbp+57h+isMember], ebx
0x18003f459  lea     r8, WPP_9a7550d4dd9638825a8f1b31a61a0fd5_Traceguids; TraceGuid
0x18003f460  mov     rcx, [rcx+10h]; Logger
0x18003f464  mov     r9d, ebx
0x18003f467  setnz   r9b; _a1
0x18003f46b  mov     edx, 0Ch; id
0x18003f470  call    WPP_SF_d
0x18003f475  cmp     [rbp+57h+isMember], ebx
0x18003f478  setnz   bl
0x18003f47b  lea     rcx, [rbp+57h+j]; j
0x18003f47f  call    ??$SafeExecute@V?$ScopeGuardImpl1@P6AXPEAX@ZPEAUWWAN_INTERFACE_OBJECT@@@@@ScopeGuardImplBase@@KAXAEAV?$ScopeGuardImpl1@P6AXPEAX@ZPEAUWWAN_INTERFACE_OBJECT@@@@@Z; ScopeGuardImplBase::SafeExecute<ScopeGuardImpl1<void (*)(void *),WWAN_INTERFACE_OBJECT *>>(ScopeGuardImpl1<void (*)(void *),WWAN_INTERFACE_OBJECT *> &)
0x18003f484  mov     al, bl
0x18003f486  mov     rcx, [rbp+57h+var_10]
0x18003f48a  xor     rcx, rsp; StackCookie
0x18003f48d  call    __security_check_cookie
0x18003f492  mov     rbx, [rsp+0A0h+arg_0]
0x18003f49a  add     rsp, 0A0h
0x18003f4a1  pop     rbp
0x18003f4a2  retn
```
