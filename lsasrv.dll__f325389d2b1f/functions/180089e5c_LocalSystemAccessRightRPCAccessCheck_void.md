# LocalSystemAccessRightRPCAccessCheck(void *)

- ea: `0x180089e5c`
- end: `0x180089fc8`
- name: `?LocalSystemAccessRightRPCAccessCheck@@YAJPEAX@Z`
- size: `364`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `4`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180117010`
- `0x1801170c0`
- `0x180117210`
- `0x1801172d0`

## callees

- `0x180011278`
- `0x180089e5c`
- `0x1800ada18`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180089ee3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180089f59`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180089ee3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180089f59`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180089eb6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180089eb6`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180089ed3`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180089ed3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180089fb3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180089fb3`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x180089f49`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x180089f49`
- `RPCRT4!RpcRevertToSelf` at `0x180089f14`
- `RPCRT4!RpcRevertToSelf` at `0x180089f25`
- `RPCRT4!RpcRevertToSelf` at `0x180089f14`
- `RPCRT4!RpcRevertToSelf` at `0x180089f25`
- `RPCRT4!RpcImpersonateClient` at `0x180089e78`
- `RPCRT4!RpcImpersonateClient` at `0x180089e78`

## pseudocode

```c
__int64 __fastcall LocalSystemAccessRightRPCAccessCheck(void *a1)
{
  unsigned int v1; // ebx
  DWORD LastError; // eax
  LsaHandleCache *v3; // rcx
  __int64 v4; // rdx
  HANDLE CurrentThread; // rax
  DWORD v6; // eax
  WINBOOL IsMember; // [rsp+38h] [rbp+10h] BYREF
  void *TokenHandle; // [rsp+40h] [rbp+18h] BYREF

  IsMember = 0;
  v1 = -1073741790;
  TokenHandle = 0;
  LastError = RpcImpersonateClient(a1);
  if ( LastError )
  {
    v3 = WPP_GLOBAL_Control;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) == 0 )
      goto LABEL_16;
    v4 = 31;
    goto LABEL_4;
  }
  CurrentThread = GetCurrentThread();
  if ( OpenThreadToken(CurrentThread, 8u, 1, &TokenHandle) )
  {
    RpcRevertToSelf();
    if ( CheckTokenMembership(TokenHandle, *((PSID *)WellKnownSids + 96), &IsMember) )
    {
      if ( IsMember )
      {
        v1 = 0;
      }
      else if ( (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 34, &WPP_4f6ab1b6c995309645dc077809c6c64b_Traceguids);
      }
    }
    else
    {
      LastError = GetLastError();
      v3 = WPP_GLOBAL_Control;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
      {
        v4 = 33;
LABEL_4:
        WPP_SF_d(*((_QWORD *)v3 + 12), v4, &WPP_4f6ab1b6c995309645dc077809c6c64b_Traceguids, LastError);
      }
    }
  }
  else
  {
    v6 = GetLastError();
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 12), 32, &WPP_4f6ab1b6c995309645dc077809c6c64b_Traceguids, v6);
    RpcRevertToSelf();
  }
LABEL_16:
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  return v1;
}

```

## disassembly

```asm
0x180089e5c  push    rbx
0x180089e5e  sub     rsp, 20h
0x180089e62  mov     [rsp+28h+IsMember], 0
0x180089e6a  mov     ebx, 0C0000022h
0x180089e6f  mov     [rsp+28h+TokenHandle], 0
0x180089e78  call    cs:__imp_RpcImpersonateClient
0x180089e7f  nop     dword ptr [rax+rax+00h]
0x180089e84  test    eax, eax
0x180089e86  jz      short loc_180089EB6
0x180089e88  mov     rcx, cs:WPP_GLOBAL_Control
0x180089e8f  test    byte ptr [rcx+6Ch], 1
0x180089e93  jz      loc_180089FA9
0x180089e99  mov     edx, 1Fh
0x180089e9e  mov     rcx, [rcx+60h]
0x180089ea2  lea     r8, WPP_4f6ab1b6c995309645dc077809c6c64b_Traceguids
0x180089ea9  mov     r9d, eax
0x180089eac  call    WPP_SF_d
0x180089eb1  jmp     loc_180089FA9
0x180089eb6  call    cs:__imp_GetCurrentThread
0x180089ebd  nop     dword ptr [rax+rax+00h]
0x180089ec2  mov     edx, 8; DesiredAccess
0x180089ec7  lea     r9, [rsp+28h+TokenHandle]; TokenHandle
0x180089ecc  mov     rcx, rax; ThreadHandle
0x180089ecf  lea     r8d, [rdx-7]; OpenAsSelf
0x180089ed3  call    cs:__imp_OpenThreadToken
0x180089eda  nop     dword ptr [rax+rax+00h]
0x180089edf  test    eax, eax
0x180089ee1  jnz     short loc_180089F25
0x180089ee3  call    cs:__imp_GetLastError
0x180089eea  nop     dword ptr [rax+rax+00h]
0x180089eef  mov     rcx, cs:WPP_GLOBAL_Control
0x180089ef6  test    byte ptr [rcx+6Ch], 1
0x180089efa  jz      short loc_180089F14
0x180089efc  mov     rcx, [rcx+60h]
0x180089f00  lea     r8, WPP_4f6ab1b6c995309645dc077809c6c64b_Traceguids
0x180089f07  mov     edx, 20h ; ' '
0x180089f0c  mov     r9d, eax
0x180089f0f  call    WPP_SF_d
0x180089f14  call    cs:__imp_RpcRevertToSelf
0x180089f1b  nop     dword ptr [rax+rax+00h]
0x180089f20  jmp     loc_180089FA9
0x180089f25  call    cs:__imp_RpcRevertToSelf
0x180089f2c  nop     dword ptr [rax+rax+00h]
0x180089f31  mov     rdx, cs:?WellKnownSids@@3PEAU_LSAP_WELL_KNOWN_SID_ENTRY@@EA; _LSAP_WELL_KNOWN_SID_ENTRY * WellKnownSids
0x180089f38  lea     r8, [rsp+28h+IsMember]; IsMember
0x180089f3d  mov     rcx, [rsp+28h+TokenHandle]; TokenHandle
0x180089f42  mov     rdx, [rdx+300h]; SidToCheck
0x180089f49  call    cs:__imp_CheckTokenMembership
0x180089f50  nop     dword ptr [rax+rax+00h]
0x180089f55  test    eax, eax
0x180089f57  jnz     short loc_180089F7C
0x180089f59  call    cs:__imp_GetLastError
0x180089f60  nop     dword ptr [rax+rax+00h]
0x180089f65  mov     rcx, cs:WPP_GLOBAL_Control
0x180089f6c  test    byte ptr [rcx+6Ch], 1
0x180089f70  jz      short loc_180089FA9
0x180089f72  mov     edx, 21h ; '!'
0x180089f77  jmp     loc_180089E9E
0x180089f7c  cmp     [rsp+28h+IsMember], 0
0x180089f81  jnz     short loc_180089FA7
0x180089f83  mov     rcx, cs:WPP_GLOBAL_Control
0x180089f8a  test    byte ptr [rcx+6Ch], 1
0x180089f8e  jz      short loc_180089FA9
0x180089f90  mov     rcx, [rcx+60h]
0x180089f94  lea     r8, WPP_4f6ab1b6c995309645dc077809c6c64b_Traceguids
0x180089f9b  mov     edx, 22h ; '"'
0x180089fa0  call    WPP_SF_
0x180089fa5  jmp     short loc_180089FA9
0x180089fa7  xor     ebx, ebx
0x180089fa9  mov     rcx, [rsp+28h+TokenHandle]; hObject
0x180089fae  test    rcx, rcx
0x180089fb1  jz      short loc_180089FBF
0x180089fb3  call    cs:__imp_CloseHandle
0x180089fba  nop     dword ptr [rax+rax+00h]
0x180089fbf  mov     eax, ebx
0x180089fc1  add     rsp, 20h
0x180089fc5  pop     rbx
0x180089fc6  retn
```
