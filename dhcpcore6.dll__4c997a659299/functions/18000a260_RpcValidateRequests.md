# RpcValidateRequests

- ea: `0x18000a260`
- end: `0x18000a427`
- name: `RpcValidateRequests`
- size: `455`
- prototype: `__int64 __fastcall(_WORD *, DWORD)`
- caller_count: `13`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180009520`
- `0x180009a70`
- `0x18000a170`
- `0x180026aa0`
- `0x180026b80`
- `0x180026d40`
- `0x180026e30`
- `0x180027120`
- `0x180027440`
- `0x180027540`
- `0x1800276b0`
- `0x180027900`
- `0x180027a08`

## callees

- `0x18000a260`
- `0x180019ad0`
- `0x18001a3ee`
- `0x1800338c0`
- `0x180033900`

## import_xrefs

- `RPCRT4!RpcImpersonateClient` at `0x18000a2d7`
- `RPCRT4!RpcImpersonateClient` at `0x18000a2d7`
- `RPCRT4!RpcRevertToSelf` at `0x18000a341`
- `RPCRT4!RpcRevertToSelf` at `0x18000a341`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a3aa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a3aa`
- `api-ms-win-security-base-l1-1-0!AccessCheck` at `0x18000a329`
- `api-ms-win-security-base-l1-1-0!AccessCheck` at `0x18000a329`

## pseudocode

```c
__int64 __fastcall RpcValidateRequests(_WORD *a1, DWORD a2)
{
  DWORD LastError; // ebx
  WINBOOL AccessStatus; // [rsp+40h] [rbp-228h] BYREF
  DWORD GrantedAccess; // [rsp+44h] [rbp-224h] BYREF
  DWORD PrivilegeSetLength; // [rsp+48h] [rbp-220h] BYREF
  struct _PRIVILEGE_SET PrivilegeSet; // [rsp+50h] [rbp-218h] BYREF

  if ( a1 && *a1 )
  {
    LastError = 50;
  }
  else
  {
    GrantedAccess = 0;
    AccessStatus = 0;
    memset_0(&PrivilegeSet, 0, 0x1F4u);
    PrivilegeSetLength = 500;
    if ( (xmmword_1800423E0 & 0x10) != 0 )
      WPP_SF_(1028, 14, WPP_b20fc9e0e0bb33b8827dda2f53003728_Traceguids);
    LastError = RpcImpersonateClient(0);
    if ( !LastError )
    {
      if ( AccessCheck(
             qword_180038290,
             (HANDLE)0xFFFFFFFFFFFFFFFBLL,
             a2,
             &GenericMapping,
             &PrivilegeSet,
             &PrivilegeSetLength,
             &GrantedAccess,
             &AccessStatus)
        && AccessStatus )
      {
        LastError = 0;
      }
      else
      {
        LastError = GetLastError();
        if ( !LastError )
          LastError = 1287;
      }
    }
    RpcRevertToSelf();
    if ( (xmmword_1800423E0 & 0x10) != 0 )
      WPP_SF_D(1028, 15, WPP_b20fc9e0e0bb33b8827dda2f53003728_Traceguids, LastError);
    if ( !LastError )
    {
      if ( !**(_DWORD **)&pDhcpv6GlobalIsShuttingDown )
        return LastError;
      LastError = 65;
      if ( (xmmword_1800423E0 & 2) == 0 )
        return LastError;
      WPP_SF_D(1025, 10, WPP_fabc15bf7f653c75a8730223311145c5_Traceguids, 65);
    }
  }
  if ( (xmmword_1800423E0 & 2) != 0 )
    WPP_SF_D(1025, 11, WPP_fabc15bf7f653c75a8730223311145c5_Traceguids, LastError);
  return LastError;
}

```

## disassembly

```asm
0x18000a260  mov     [rsp+arg_10], rbx
0x18000a265  push    rdi
0x18000a266  sub     rsp, 260h
0x18000a26d  mov     rax, cs:__security_cookie
0x18000a274  xor     rax, rsp
0x18000a277  mov     [rsp+268h+var_18], rax
0x18000a27f  mov     edi, edx
0x18000a281  test    rcx, rcx
0x18000a284  jnz     loc_18000A3C7
0x18000a28a  mov     [rsp+268h+arg_0], rsi
0x18000a292  lea     rcx, [rsp+268h+var_218]; void *
0x18000a297  xor     esi, esi
0x18000a299  xor     edx, edx; Val
0x18000a29b  mov     r8d, 1F4h; Size
0x18000a2a1  mov     [rsp+268h+var_224], esi
0x18000a2a5  mov     [rsp+268h+var_228], esi
0x18000a2a9  call    memset_0
0x18000a2ae  mov     [rsp+268h+var_220], 1F4h
0x18000a2b6  test    byte ptr cs:xmmword_1800423E0, 10h
0x18000a2bd  jz      short loc_18000A2D5
0x18000a2bf  mov     edx, 0Eh
0x18000a2c4  lea     r8, WPP_b20fc9e0e0bb33b8827dda2f53003728_Traceguids
0x18000a2cb  mov     ecx, 404h
0x18000a2d0  call    WPP_SF_
0x18000a2d5  xor     ecx, ecx; BindingHandle
0x18000a2d7  call    cs:__imp_RpcImpersonateClient
0x18000a2de  nop     dword ptr [rax+rax+00h]
0x18000a2e3  mov     ebx, eax
0x18000a2e5  test    eax, eax
0x18000a2e7  jnz     short loc_18000A341
0x18000a2e9  lea     rax, [rsp+268h+var_228]
0x18000a2ee  mov     r8d, edi; DesiredAccess
0x18000a2f1  mov     [rsp+268h+AccessStatus], rax; AccessStatus
0x18000a2f6  lea     r9, GenericMapping; GenericMapping
0x18000a2fd  lea     rax, [rsp+268h+var_224]
0x18000a302  mov     rdx, 0FFFFFFFFFFFFFFFBh; ClientToken
0x18000a309  mov     [rsp+268h+GrantedAccess], rax; GrantedAccess
0x18000a30e  lea     rcx, qword_180038290; pSecurityDescriptor
0x18000a315  lea     rax, [rsp+268h+var_220]
0x18000a31a  mov     [rsp+268h+PrivilegeSetLength], rax; PrivilegeSetLength
0x18000a31f  lea     rax, [rsp+268h+var_218]
0x18000a324  mov     [rsp+268h+PrivilegeSet], rax; PrivilegeSet
0x18000a329  call    cs:__imp_AccessCheck
0x18000a330  nop     dword ptr [rax+rax+00h]
0x18000a335  test    eax, eax
0x18000a337  jz      short loc_18000A3AA
0x18000a339  cmp     [rsp+268h+var_228], esi
0x18000a33d  jz      short loc_18000A3AA
0x18000a33f  mov     ebx, esi
0x18000a341  call    cs:__imp_RpcRevertToSelf
0x18000a348  nop     dword ptr [rax+rax+00h]
0x18000a34d  mov     rsi, [rsp+268h+arg_0]
0x18000a355  test    byte ptr cs:xmmword_1800423E0, 10h
0x18000a35c  jz      short loc_18000A377
0x18000a35e  mov     edx, 0Fh
0x18000a363  lea     r8, WPP_b20fc9e0e0bb33b8827dda2f53003728_Traceguids
0x18000a36a  mov     ecx, 404h
0x18000a36f  mov     r9d, ebx
0x18000a372  call    WPP_SF_D
0x18000a377  test    ebx, ebx
0x18000a379  jnz     short loc_18000A3D6
0x18000a37b  mov     rax, cs:pDhcpv6GlobalIsShuttingDown
0x18000a382  cmp     [rax], ebx
0x18000a384  jnz     short loc_18000A3FA
0x18000a386  mov     eax, ebx
0x18000a388  mov     rcx, [rsp+268h+var_18]
0x18000a390  xor     rcx, rsp; StackCookie
0x18000a393  call    __security_check_cookie
0x18000a398  mov     rbx, [rsp+268h+arg_10]
0x18000a3a0  add     rsp, 260h
0x18000a3a7  pop     rdi
0x18000a3a8  retn
0x18000a3aa  call    cs:__imp_GetLastError
0x18000a3b1  nop     dword ptr [rax+rax+00h]
0x18000a3b6  mov     ebx, eax
0x18000a3b8  mov     eax, 507h
0x18000a3bd  test    ebx, ebx
0x18000a3bf  cmovz   ebx, eax
0x18000a3c2  jmp     loc_18000A341
0x18000a3c7  cmp     word ptr [rcx], 0
0x18000a3cb  jz      loc_18000A28A
0x18000a3d1  mov     ebx, 32h ; '2'
0x18000a3d6  test    byte ptr cs:xmmword_1800423E0, 2
0x18000a3dd  jz      short loc_18000A386
0x18000a3df  mov     edx, 0Bh
0x18000a3e4  lea     r8, WPP_fabc15bf7f653c75a8730223311145c5_Traceguids
0x18000a3eb  mov     ecx, 401h
0x18000a3f0  mov     r9d, ebx
0x18000a3f3  call    WPP_SF_D
0x18000a3f8  jmp     short loc_18000A386
0x18000a3fa  mov     ebx, 41h ; 'A'
0x18000a3ff  test    byte ptr cs:xmmword_1800423E0, 2
0x18000a406  jz      loc_18000A386
0x18000a40c  mov     edx, 0Ah
0x18000a411  lea     r8, WPP_fabc15bf7f653c75a8730223311145c5_Traceguids
0x18000a418  mov     ecx, 401h
0x18000a41d  mov     r9d, ebx
0x18000a420  call    WPP_SF_D
0x18000a425  jmp     short loc_18000A3D6
```
