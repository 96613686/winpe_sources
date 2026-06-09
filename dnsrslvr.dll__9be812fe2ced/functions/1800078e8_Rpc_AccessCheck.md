# Rpc_AccessCheck

- ea: `0x1800078e8`
- end: `0x180007c72`
- name: `Rpc_AccessCheck`
- size: `906`
- prototype: ``
- caller_count: `4`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800084e0`
- `0x180017430`
- `0x180050130`
- `0x180050650`

## callees

- `0x180005e3c`
- `0x1800078e8`
- `0x180046ec0`
- `0x180086b1c`
- `0x180086b70`
- `0x180087e40`

## import_xrefs

- `RPCRT4!RpcRevertToSelf` at `0x180007a8e`
- `RPCRT4!RpcRevertToSelf` at `0x180007a8e`
- `RPCRT4!RpcImpersonateClient` at `0x180007974`
- `RPCRT4!RpcImpersonateClient` at `0x180007974`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007a13`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007ab7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007b0c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007a13`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007ab7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007b0c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007a76`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007a84`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007a76`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007a84`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800079a6`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800079a6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180007987`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180007987`
- `api-ms-win-security-base-l1-1-0!MapGenericMask` at `0x180007bea`
- `api-ms-win-security-base-l1-1-0!MapGenericMask` at `0x180007bea`
- `api-ms-win-security-base-l1-1-0!IsValidSecurityDescriptor` at `0x180007964`
- `api-ms-win-security-base-l1-1-0!IsValidSecurityDescriptor` at `0x180007964`
- `api-ms-win-security-base-l1-1-0!AccessCheck` at `0x180007a05`
- `api-ms-win-security-base-l1-1-0!AccessCheck` at `0x180007a05`

## pseudocode

```c
__int64 __fastcall Rpc_AccessCheck(DWORD a1)
{
  void *v2; // rdi
  int v3; // esi
  PSECURITY_DESCRIPTOR v4; // rcx
  unsigned int v5; // eax
  unsigned int inited; // ebx
  HANDLE CurrentThread; // rax
  DWORD v8; // r8d
  DWORD v9; // eax
  int v10; // edx
  int v11; // r8d
  DWORD v12; // ebx
  WINBOOL v13; // eax
  DWORD LastError; // eax
  __int64 v16; // rdx
  __int64 v17; // r9
  DWORD v18; // eax
  int PrivilegeSet; // [rsp+20h] [rbp-69h]
  int AccessStatus; // [rsp+38h] [rbp-51h]
  void *TokenHandle; // [rsp+60h] [rbp-29h] BYREF
  DWORD DesiredAccess; // [rsp+68h] [rbp-21h] BYREF
  WINBOOL v23; // [rsp+6Ch] [rbp-1Dh] BYREF
  DWORD PrivilegeSetLength; // [rsp+70h] [rbp-19h] BYREF
  DWORD GrantedAccess; // [rsp+74h] [rbp-15h] BYREF
  struct _PRIVILEGE_SET v26; // [rsp+78h] [rbp-11h] BYREF

  DesiredAccess = a1;
  v23 = 0;
  TokenHandle = 0;
  v2 = 0;
  GrantedAccess = 0;
  v3 = 0;
  PrivilegeSetLength = 0;
  memset(&v26, 0, sizeof(v26));
  if ( (xmmword_1800AB5A0 & 0x80u) != 0LL )
    WPP_SF_d(1031, 37, WPP_62b51b833ff23ae8bbd6c42f5e75c895_Traceguids, a1);
  v4 = g_pAccessSecurityDescriptor;
  if ( !g_pAccessSecurityDescriptor )
  {
    inited = Rpc_InitAccessChecking();
    if ( inited )
      goto LABEL_16;
    v4 = g_pAccessSecurityDescriptor;
  }
  if ( !IsValidSecurityDescriptor(v4) )
  {
    LastError = GetLastError();
    inited = LastError;
    if ( (xmmword_1800AB5A0 & 0x80u) != 0LL )
      WPP_SF_qD(1031, 38, WPP_62b51b833ff23ae8bbd6c42f5e75c895_Traceguids, g_pAccessSecurityDescriptor, LastError);
    goto LABEL_16;
  }
  v5 = RpcImpersonateClient(0);
  inited = v5;
  if ( v5 )
  {
    if ( (xmmword_1800AB5A0 & 0x80u) != 0LL )
      WPP_SF_d(1031, 39, WPP_62b51b833ff23ae8bbd6c42f5e75c895_Traceguids, v5);
    goto LABEL_16;
  }
  v3 = 1;
  CurrentThread = GetCurrentThread();
  v2 = CurrentThread;
  if ( !CurrentThread )
  {
LABEL_16:
    if ( SBYTE3(xmmword_1800AB5A0) < 0 )
      WPP_SF_d(1055, 47, WPP_62b51b833ff23ae8bbd6c42f5e75c895_Traceguids, inited);
    v13 = (DesiredAccess & 0x120) == 0;
    goto LABEL_19;
  }
  v23 = OpenThreadToken(CurrentThread, 8u, 1, &TokenHandle);
  if ( !v23 )
  {
    v18 = GetLastError();
    inited = v18;
    if ( (xmmword_1800AB5A0 & 0x80u) != 0LL )
      WPP_SF_d(1031, 40, WPP_62b51b833ff23ae8bbd6c42f5e75c895_Traceguids, v18);
    goto LABEL_16;
  }
  v8 = DesiredAccess;
  if ( (unsigned __int16)DesiredAccess != DesiredAccess )
  {
    if ( (xmmword_1800AB5A0 & 0x80u) != 0LL )
      WPP_SF_d(1031, 41, WPP_62b51b833ff23ae8bbd6c42f5e75c895_Traceguids, DesiredAccess);
    MapGenericMask(&DesiredAccess, &g_AccessGenericMapping);
    if ( (xmmword_1800AB5A0 & 0x80u) != 0LL )
      WPP_SF_d(1031, 42, WPP_62b51b833ff23ae8bbd6c42f5e75c895_Traceguids, DesiredAccess);
    v8 = DesiredAccess;
  }
  PrivilegeSetLength = 20;
  if ( !AccessCheck(
          g_pAccessSecurityDescriptor,
          TokenHandle,
          v8,
          &g_AccessGenericMapping,
          &v26,
          &PrivilegeSetLength,
          &GrantedAccess,
          &v23) )
  {
    v9 = GetLastError();
    v12 = v9;
    if ( (xmmword_1800AB5A0 & 0x80u) != 0LL )
      WPP_SF_DqqDqqqqq(
        DesiredAccess,
        v10,
        v11,
        v9,
        PrivilegeSet,
        (__int64)TokenHandle,
        DesiredAccess,
        AccessStatus,
        (__int64)&v26,
        (__int64)&PrivilegeSetLength,
        (__int64)&GrantedAccess,
        (__int64)&v23);
    if ( SBYTE3(xmmword_1800AB5A0) < 0 )
      WPP_SF_d(1055, 46, WPP_62b51b833ff23ae8bbd6c42f5e75c895_Traceguids, v12);
    v13 = ((DesiredAccess >> 8) & 1) == 0;
LABEL_19:
    v23 = v13;
    goto LABEL_20;
  }
  if ( v23 )
  {
    if ( (xmmword_1800AB5A0 & 0x80u) == 0LL )
      goto LABEL_20;
    v16 = 44;
    v17 = a1;
    goto LABEL_42;
  }
  if ( (xmmword_1800AB5A0 & 0x80u) != 0LL )
  {
    v17 = DesiredAccess;
    v16 = 45;
LABEL_42:
    WPP_SF_d(1031, v16, WPP_62b51b833ff23ae8bbd6c42f5e75c895_Traceguids, v17);
  }
LABEL_20:
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  if ( v2 )
    CloseHandle(v2);
  if ( v3 )
    RpcRevertToSelf();
  return (unsigned int)v23;
}

```

## disassembly

```asm
0x1800078e8  push    rbp
0x1800078ea  push    rbx
0x1800078eb  push    rsi
0x1800078ec  push    rdi
0x1800078ed  push    r12
0x1800078ef  push    r13
0x1800078f1  push    r14
0x1800078f3  push    r15
0x1800078f5  lea     rbp, [rsp-1Fh]
0x1800078fa  sub     rsp, 0A8h
0x180007901  mov     rax, cs:__security_cookie
0x180007908  xor     rax, rsp
0x18000790b  mov     [rbp+57h+var_50], rax
0x18000790f  xor     r15d, r15d
0x180007912  mov     [rbp+57h+DesiredAccess], ecx
0x180007915  xor     eax, eax
0x180007917  mov     [rbp+57h+var_74], r15d
0x18000791b  xorps   xmm0, xmm0
0x18000791e  mov     [rbp+57h+var_68.Privilege.Attributes], eax
0x180007921  mov     r14d, ecx
0x180007924  mov     [rbp+57h+TokenHandle], r15
0x180007928  mov     edi, r15d
0x18000792b  mov     [rbp+57h+var_6C], r15d
0x18000792f  mov     esi, r15d
0x180007932  mov     [rbp+57h+var_70], r15d
0x180007936  movups  xmmword ptr [rbp+57h+var_68.PrivilegeCount], xmm0
0x18000793a  cmp     byte ptr cs:xmmword_1800AB5A0, r15b
0x180007941  lea     r12, WPP_62b51b833ff23ae8bbd6c42f5e75c895_Traceguids
0x180007948  mov     r13d, 407h
0x18000794e  jl      loc_180007B39
0x180007954  mov     rcx, cs:g_pAccessSecurityDescriptor; pSecurityDescriptor
0x18000795b  test    rcx, rcx
0x18000795e  jz      loc_180007A41
0x180007964  call    cs:__imp_IsValidSecurityDescriptor
0x18000796a  test    eax, eax
0x18000796c  jz      loc_180007AB7
0x180007972  xor     ecx, ecx; BindingHandle
0x180007974  call    cs:__imp_RpcImpersonateClient
0x18000797a  mov     ebx, eax
0x18000797c  test    eax, eax
0x18000797e  jnz     loc_180007B9E
0x180007984  lea     esi, [rax+1]
0x180007987  call    cs:__imp_GetCurrentThread
0x18000798d  mov     rdi, rax
0x180007990  test    rax, rax
0x180007993  jz      loc_180007A50
0x180007999  lea     r9, [rbp+57h+TokenHandle]; TokenHandle
0x18000799d  mov     r8d, esi; OpenAsSelf
0x1800079a0  lea     edx, [rbx+8]; DesiredAccess
0x1800079a3  mov     rcx, rax; ThreadHandle
0x1800079a6  call    cs:__imp_OpenThreadToken
0x1800079ac  mov     [rbp+57h+var_74], eax
0x1800079af  test    eax, eax
0x1800079b1  jz      loc_180007B0C
0x1800079b7  mov     r8d, [rbp+57h+DesiredAccess]; DesiredAccess
0x1800079bb  movzx   eax, r8w
0x1800079bf  cmp     eax, r8d
0x1800079c2  jnz     loc_180007BC3
0x1800079c8  mov     rdx, [rbp+57h+TokenHandle]; ClientToken
0x1800079cc  lea     rax, [rbp+57h+var_74]
0x1800079d0  mov     rcx, cs:g_pAccessSecurityDescriptor; pSecurityDescriptor
0x1800079d7  lea     r9, g_AccessGenericMapping; GenericMapping
0x1800079de  mov     [rsp+0E0h+AccessStatus], rax; AccessStatus
0x1800079e3  lea     rax, [rbp+57h+var_6C]
0x1800079e7  mov     [rsp+0E0h+GrantedAccess], rax; GrantedAccess
0x1800079ec  lea     rax, [rbp+57h+var_70]
0x1800079f0  mov     [rsp+0E0h+PrivilegeSetLength], rax; PrivilegeSetLength
0x1800079f5  lea     rax, [rbp+57h+var_68]
0x1800079f9  mov     [rsp+0E0h+PrivilegeSet], rax; PrivilegeSet
0x1800079fe  mov     [rbp+57h+var_70], 14h
0x180007a05  call    cs:__imp_AccessCheck
0x180007a0b  test    eax, eax
0x180007a0d  jnz     loc_180007AE8
0x180007a13  call    cs:__imp_GetLastError
0x180007a19  mov     ebx, eax
0x180007a1b  cmp     byte ptr cs:xmmword_1800AB5A0, r15b
0x180007a22  jl      loc_180007B51
0x180007a28  cmp     byte ptr cs:xmmword_1800AB5A0+3, r15b
0x180007a2f  jl      loc_180007C16
0x180007a35  mov     eax, [rbp+57h+DesiredAccess]
0x180007a38  shr     eax, 8
0x180007a3b  not     eax
0x180007a3d  and     eax, esi
0x180007a3f  jmp     short loc_180007A6A
0x180007a41  call    Rpc_InitAccessChecking
0x180007a46  mov     ebx, eax
0x180007a48  test    eax, eax
0x180007a4a  jz      loc_180007B92
0x180007a50  cmp     byte ptr cs:xmmword_1800AB5A0+3, r15b
0x180007a57  jl      loc_180007C58
0x180007a5d  test    [rbp+57h+DesiredAccess], 120h
0x180007a64  mov     eax, r15d
0x180007a67  setz    al
0x180007a6a  mov     [rbp+57h+var_74], eax
0x180007a6d  mov     rcx, [rbp+57h+TokenHandle]; hObject
0x180007a71  test    rcx, rcx
0x180007a74  jz      short loc_180007A7C
0x180007a76  call    cs:__imp_CloseHandle
0x180007a7c  test    rdi, rdi
0x180007a7f  jz      short loc_180007A8A
0x180007a81  mov     rcx, rdi; hObject
0x180007a84  call    cs:__imp_CloseHandle
0x180007a8a  test    esi, esi
0x180007a8c  jz      short loc_180007A94
0x180007a8e  call    cs:__imp_RpcRevertToSelf
0x180007a94  mov     eax, [rbp+57h+var_74]
0x180007a97  mov     rcx, [rbp+57h+var_50]
0x180007a9b  xor     rcx, rsp; StackCookie
0x180007a9e  call    __security_check_cookie
0x180007aa3  add     rsp, 0A8h
0x180007aaa  pop     r15
0x180007aac  pop     r14
0x180007aae  pop     r13
0x180007ab0  pop     r12
0x180007ab2  pop     rdi
0x180007ab3  pop     rsi
0x180007ab4  pop     rbx
0x180007ab5  pop     rbp
0x180007ab6  retn
0x180007ab7  call    cs:__imp_GetLastError
0x180007abd  mov     ebx, eax
0x180007abf  cmp     byte ptr cs:xmmword_1800AB5A0, r15b
0x180007ac6  jge     short loc_180007A50
0x180007ac8  mov     r9, cs:g_pAccessSecurityDescriptor
0x180007acf  mov     edx, 26h ; '&'
0x180007ad4  mov     ecx, r13d
0x180007ad7  mov     dword ptr [rsp+0E0h+PrivilegeSet], eax
0x180007adb  mov     r8, r12
0x180007ade  call    WPP_SF_qD
0x180007ae3  jmp     loc_180007A50
0x180007ae8  cmp     [rbp+57h+var_74], r15d
0x180007aec  jz      loc_180007C49
0x180007af2  cmp     byte ptr cs:xmmword_1800AB5A0, r15b
0x180007af9  jge     loc_180007A6D
0x180007aff  mov     edx, 2Ch ; ','
0x180007b04  mov     r9d, r14d
0x180007b07  jmp     loc_180007C39
0x180007b0c  call    cs:__imp_GetLastError
0x180007b12  mov     ebx, eax
0x180007b14  cmp     byte ptr cs:xmmword_1800AB5A0, r15b
0x180007b1b  jge     loc_180007A50
0x180007b21  mov     edx, 28h ; '('
0x180007b26  mov     ecx, r13d
0x180007b29  mov     r9d, eax
0x180007b2c  mov     r8, r12
0x180007b2f  call    WPP_SF_d
0x180007b34  jmp     loc_180007A50
0x180007b39  mov     edx, 25h ; '%'
0x180007b3e  mov     ecx, r13d
0x180007b41  mov     r9d, r14d
0x180007b44  mov     r8, r12
0x180007b47  call    WPP_SF_d
0x180007b4c  jmp     loc_180007954
0x180007b51  mov     ecx, [rbp+57h+DesiredAccess]
0x180007b54  lea     rax, [rbp+57h+var_74]
0x180007b58  mov     [rsp+0E0h+var_88], rax
0x180007b5d  mov     r9d, ebx
0x180007b60  lea     rax, [rbp+57h+var_6C]
0x180007b64  mov     [rsp+0E0h+var_90], rax
0x180007b69  lea     rax, [rbp+57h+var_70]
0x180007b6d  mov     [rsp+0E0h+var_98], rax
0x180007b72  lea     rax, [rbp+57h+var_68]
0x180007b76  mov     [rsp+0E0h+var_A0], rax
0x180007b7b  mov     rax, [rbp+57h+TokenHandle]
0x180007b7f  mov     dword ptr [rsp+0E0h+GrantedAccess], ecx
0x180007b83  mov     [rsp+0E0h+PrivilegeSetLength], rax
0x180007b88  call    WPP_SF_DqqDqqqqq
0x180007b8d  jmp     loc_180007A28
0x180007b92  mov     rcx, cs:g_pAccessSecurityDescriptor
0x180007b99  jmp     loc_180007964
0x180007b9e  cmp     byte ptr cs:xmmword_1800AB5A0, r15b
0x180007ba5  jge     loc_180007A50
0x180007bab  mov     edx, 27h ; '''
0x180007bb0  mov     ecx, r13d
0x180007bb3  mov     r9d, eax
0x180007bb6  mov     r8, r12
0x180007bb9  call    WPP_SF_d
0x180007bbe  jmp     loc_180007A50
0x180007bc3  cmp     byte ptr cs:xmmword_1800AB5A0, r15b
0x180007bca  jge     short loc_180007BDF
0x180007bcc  mov     r9d, r8d
0x180007bcf  mov     edx, 29h ; ')'
0x180007bd4  mov     r8, r12
0x180007bd7  mov     ecx, r13d
0x180007bda  call    WPP_SF_d
0x180007bdf  lea     rdx, g_AccessGenericMapping; GenericMapping
0x180007be6  lea     rcx, [rbp+57h+DesiredAccess]; AccessMask
0x180007bea  call    cs:__imp_MapGenericMask
0x180007bf0  cmp     byte ptr cs:xmmword_1800AB5A0, r15b
0x180007bf7  jge     short loc_180007C0D
0x180007bf9  mov     r9d, [rbp+57h+DesiredAccess]
0x180007bfd  mov     edx, 2Ah ; '*'
0x180007c02  mov     ecx, r13d
0x180007c05  mov     r8, r12
0x180007c08  call    WPP_SF_d
0x180007c0d  mov     r8d, [rbp+57h+DesiredAccess]
0x180007c11  jmp     loc_1800079C8
0x180007c16  mov     edx, 2Eh ; '.'
0x180007c1b  mov     ecx, 41Fh
0x180007c20  mov     r9d, ebx
0x180007c23  mov     r8, r12
0x180007c26  call    WPP_SF_d
0x180007c2b  jmp     loc_180007A35
0x180007c30  mov     r9d, [rbp+57h+DesiredAccess]
0x180007c34  mov     edx, 2Dh ; '-'
0x180007c39  mov     ecx, r13d
0x180007c3c  mov     r8, r12
0x180007c3f  call    WPP_SF_d
0x180007c44  jmp     loc_180007A6D
0x180007c49  cmp     byte ptr cs:xmmword_1800AB5A0, r15b
0x180007c50  jge     loc_180007A6D
0x180007c56  jmp     short loc_180007C30
0x180007c58  mov     edx, 2Fh ; '/'
0x180007c5d  mov     ecx, 41Fh
0x180007c62  mov     r9d, ebx
0x180007c65  mov     r8, r12
0x180007c68  call    WPP_SF_d
0x180007c6d  jmp     loc_180007A5D
```
