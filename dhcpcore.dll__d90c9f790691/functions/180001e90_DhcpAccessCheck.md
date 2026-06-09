# DhcpAccessCheck

- ea: `0x180001e90`
- end: `0x180001fbc`
- name: `DhcpAccessCheck`
- size: `300`
- prototype: `__int64 __fastcall(__int64, DWORD)`
- caller_count: `3`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180001c48`
- `0x180001cf0`
- `0x18002e538`

## callees

- `0x180001e90`
- `0x18001cef0`
- `0x18001d826`
- `0x18004d1a0`
- `0x18004d1e0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001f57`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001f57`
- `api-ms-win-security-base-l1-1-0!AccessCheck` at `0x180001f47`
- `api-ms-win-security-base-l1-1-0!AccessCheck` at `0x180001f47`
- `RPCRT4!RpcImpersonateClient` at `0x180001efb`
- `RPCRT4!RpcImpersonateClient` at `0x180001efb`
- `RPCRT4!RpcRevertToSelf` at `0x180001f69`
- `RPCRT4!RpcRevertToSelf` at `0x180001f69`

## pseudocode

```c
__int64 __fastcall DhcpAccessCheck(__int64 a1, DWORD a2)
{
  DWORD LastError; // ebx
  WINBOOL AccessStatus; // [rsp+40h] [rbp-228h] BYREF
  DWORD GrantedAccess; // [rsp+44h] [rbp-224h] BYREF
  DWORD PrivilegeSetLength; // [rsp+48h] [rbp-220h] BYREF
  struct _PRIVILEGE_SET PrivilegeSet; // [rsp+50h] [rbp-218h] BYREF

  GrantedAccess = 0;
  AccessStatus = 0;
  memset_0(&PrivilegeSet, 0, 0x1F4u);
  PrivilegeSetLength = 500;
  if ( (xmmword_1800616A0 & 0x10) != 0 )
    WPP_SF_(1028, 14, WPP_b20fc9e0e0bb33b8827dda2f53003728_Traceguids);
  LastError = RpcImpersonateClient(0);
  if ( !LastError )
  {
    if ( AccessCheck(
           qword_1800536A0,
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
  if ( (xmmword_1800616A0 & 0x10) != 0 )
    WPP_SF_D(1028, 15, WPP_b20fc9e0e0bb33b8827dda2f53003728_Traceguids, LastError);
  return LastError;
}

```

## disassembly

```asm
0x180001e90  mov     [rsp+arg_0], rbx
0x180001e95  mov     [rsp+arg_10], rsi
0x180001e9a  push    rdi
0x180001e9b  sub     rsp, 260h
0x180001ea2  mov     rax, cs:__security_cookie
0x180001ea9  xor     rax, rsp
0x180001eac  mov     [rsp+268h+var_18], rax
0x180001eb4  xor     esi, esi
0x180001eb6  lea     rcx, [rsp+268h+var_218]; void *
0x180001ebb  mov     edi, edx
0x180001ebd  mov     [rsp+268h+var_224], esi
0x180001ec1  xor     edx, edx; Val
0x180001ec3  mov     [rsp+268h+var_228], esi
0x180001ec7  mov     r8d, 1F4h; Size
0x180001ecd  call    memset_0
0x180001ed2  mov     [rsp+268h+var_220], 1F4h
0x180001eda  test    byte ptr cs:xmmword_1800616A0, 10h
0x180001ee1  jz      short loc_180001EF9
0x180001ee3  mov     edx, 0Eh
0x180001ee8  lea     r8, WPP_b20fc9e0e0bb33b8827dda2f53003728_Traceguids
0x180001eef  mov     ecx, 404h
0x180001ef4  call    WPP_SF_
0x180001ef9  xor     ecx, ecx; BindingHandle
0x180001efb  call    cs:__imp_RpcImpersonateClient
0x180001f01  mov     ebx, eax
0x180001f03  test    eax, eax
0x180001f05  jnz     short loc_180001F69
0x180001f07  lea     rax, [rsp+268h+var_228]
0x180001f0c  mov     r8d, edi; DesiredAccess
0x180001f0f  mov     [rsp+268h+AccessStatus], rax; AccessStatus
0x180001f14  lea     r9, GenericMapping; GenericMapping
0x180001f1b  lea     rax, [rsp+268h+var_224]
0x180001f20  mov     rdx, 0FFFFFFFFFFFFFFFBh; ClientToken
0x180001f27  mov     [rsp+268h+GrantedAccess], rax; GrantedAccess
0x180001f2c  lea     rcx, qword_1800536A0; pSecurityDescriptor
0x180001f33  lea     rax, [rsp+268h+var_220]
0x180001f38  mov     [rsp+268h+PrivilegeSetLength], rax; PrivilegeSetLength
0x180001f3d  lea     rax, [rsp+268h+var_218]
0x180001f42  mov     [rsp+268h+PrivilegeSet], rax; PrivilegeSet
0x180001f47  call    cs:__imp_AccessCheck
0x180001f4d  test    eax, eax
0x180001f4f  jz      short loc_180001F57
0x180001f51  cmp     [rsp+268h+var_228], esi
0x180001f55  jnz     short loc_180001FB8
0x180001f57  call    cs:__imp_GetLastError
0x180001f5d  mov     ebx, eax
0x180001f5f  mov     eax, 507h
0x180001f64  test    ebx, ebx
0x180001f66  cmovz   ebx, eax
0x180001f69  call    cs:__imp_RpcRevertToSelf
0x180001f6f  test    byte ptr cs:xmmword_1800616A0, 10h
0x180001f76  jz      short loc_180001F91
0x180001f78  mov     edx, 0Fh
0x180001f7d  lea     r8, WPP_b20fc9e0e0bb33b8827dda2f53003728_Traceguids
0x180001f84  mov     ecx, 404h
0x180001f89  mov     r9d, ebx
0x180001f8c  call    WPP_SF_D
0x180001f91  mov     eax, ebx
0x180001f93  mov     rcx, [rsp+268h+var_18]
0x180001f9b  xor     rcx, rsp; StackCookie
0x180001f9e  call    __security_check_cookie
0x180001fa3  lea     r11, [rsp+268h+var_8]
0x180001fab  mov     rbx, [r11+10h]
0x180001faf  mov     rsi, [r11+20h]
0x180001fb3  mov     rsp, r11
0x180001fb6  pop     rdi
0x180001fb7  retn
0x180001fb8  mov     ebx, esi
0x180001fba  jmp     short loc_180001F69
```
