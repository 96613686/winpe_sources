# LsarEfsGetSmartcardCredentials

- ea: `0x1800c8740`
- end: `0x1800c8b06`
- name: `LsarEfsGetSmartcardCredentials`
- size: `966`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x1800093b0`
- `0x180009410`
- `0x1800284d4`
- `0x18003a848`
- `0x1800ada18`
- `0x1800b86d0`
- `0x1800bd6e0`
- `0x1800c8740`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c886e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c886e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800c87e1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800c87e1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800c8898`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800c8898`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800c88ac`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800c88ac`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800c8a61`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800c8a8c`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800c8a61`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800c8a8c`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x1800c885e`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x1800c885e`
- `ntdll!NtPrivilegeCheck` at `0x1800c8943`
- `ntdll!NtPrivilegeCheck` at `0x1800c8943`
- `ntdll!RtlReleaseResource` at `0x1800c8aed`
- `ntdll!RtlReleaseResource` at `0x1800c8aed`
- `ntdll!RtlAcquireResourceShared` at `0x1800c89fa`
- `ntdll!RtlAcquireResourceShared` at `0x1800c89fa`
- `ntdll!NtOpenThreadToken` at `0x1800c8836`
- `ntdll!NtOpenThreadToken` at `0x1800c8836`
- `RPCRT4!RpcRevertToSelf` at `0x1800c8883`
- `RPCRT4!RpcRevertToSelf` at `0x1800c8997`
- `RPCRT4!RpcRevertToSelf` at `0x1800c8883`
- `RPCRT4!RpcRevertToSelf` at `0x1800c8997`
- `RPCRT4!I_RpcMapWin32Status` at `0x1800c880c`
- `RPCRT4!I_RpcMapWin32Status` at `0x1800c880c`
- `RPCRT4!RpcImpersonateClient` at `0x1800c87fe`
- `RPCRT4!RpcImpersonateClient` at `0x1800c87fe`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x1800c87cb`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x1800c87cb`

## pseudocode

```c
__int64 __fastcall LsarEfsGetSmartcardCredentials(
        __int64 a1,
        struct _LUID *a2,
        _QWORD *a3,
        _DWORD *a4,
        _QWORD *a5,
        unsigned int *a6)
{
  RPC_STATUS v8; // ebx
  HLOCAL v9; // r14
  RPC_STATUS v10; // eax
  DWORD LastError; // eax
  __int64 v12; // rdx
  __int64 v13; // r8
  __int64 v14; // r9
  struct _LSAP_LOGON_SESSION *LogonSession; // rax
  struct _LSAP_LOGON_SESSION *v17; // rdi
  unsigned int *v18; // rax
  int v19; // r15d
  unsigned int v20; // r12d
  HLOCAL v21; // rsi
  unsigned int *v22; // rax
  unsigned __int8 Result[4]; // [rsp+30h] [rbp-50h] BYREF
  unsigned int Pid; // [rsp+34h] [rbp-4Ch] BYREF
  WINBOOL IsMember; // [rsp+38h] [rbp-48h] BYREF
  void *TokenHandle; // [rsp+40h] [rbp-40h] BYREF
  _DWORD *v27; // [rsp+48h] [rbp-38h]
  unsigned int *v28; // [rsp+50h] [rbp-30h]
  _QWORD *v29; // [rsp+58h] [rbp-28h]
  struct _PRIVILEGE_SET RequiredPrivileges; // [rsp+60h] [rbp-20h] BYREF

  v27 = a4;
  v28 = a6;
  *a3 = 0;
  *a4 = 0;
  v29 = a5;
  *a5 = 0;
  *a6 = 0;
  Result[0] = 0;
  IsMember = 0;
  TokenHandle = 0;
  Pid = 0;
  memset(&RequiredPrivileges, 0, sizeof(RequiredPrivileges));
  if ( a1 )
    return (unsigned int)-1073741534;
  v9 = 0;
  v8 = I_RpcBindingInqLocalClientPID(0, &Pid);
  if ( v8 >= 0 )
  {
    if ( Pid == GetCurrentProcessId() )
    {
      v10 = RpcImpersonateClient(0);
      v8 = I_RpcMapWin32Status(v10);
      if ( v8 >= 0 )
      {
        v8 = NtOpenThreadToken((HANDLE)0xFFFFFFFFFFFFFFFELL, 8u, 1u, &TokenHandle);
        if ( v8 >= 0 )
        {
          if ( CheckTokenMembership(TokenHandle, *((PSID *)WellKnownSids + 90), &IsMember) )
          {
            if ( IsMember )
            {
              RequiredPrivileges.Privilege[0].Luid = LsapTcbPrivilege;
              RequiredPrivileges.PrivilegeCount = 1;
              RequiredPrivileges.Control = 1;
              RequiredPrivileges.Privilege[0].Attributes = 0;
              v8 = NtPrivilegeCheck(TokenHandle, &RequiredPrivileges, Result);
              if ( v8 >= 0 )
              {
                if ( Result[0] )
                {
                  RpcRevertToSelf();
                  LogonSession = LsapLocateLogonSession(a2);
                  v17 = LogonSession;
                  if ( LogonSession )
                  {
                    RtlAcquireResourceShared((PRTL_RESOURCE)((char *)LogonSession + 16), 1u);
                    v18 = (unsigned int *)*((_QWORD *)v17 + 67);
                    if ( v18 )
                    {
                      v19 = *v18;
                      v9 = LocalAlloc(0x40u, *v18);
                      if ( v9 && (v20 = *(_DWORD *)(*((_QWORD *)v17 + 67) + 16LL), (v21 = LocalAlloc(0x40u, v20)) != 0) )
                      {
                        memcpy_0(v9, *(const void **)(*((_QWORD *)v17 + 67) + 8LL), **((unsigned int **)v17 + 67));
                        memcpy_0(
                          v21,
                          *(const void **)(*((_QWORD *)v17 + 67) + 24LL),
                          *(unsigned int *)(*((_QWORD *)v17 + 67) + 16LL));
                        *v27 = v19;
                        v22 = v28;
                        *a3 = v9;
                        v9 = 0;
                        *v22 = v20;
                        *v29 = v21;
                      }
                      else
                      {
                        v8 = -1073741801;
                      }
                    }
                    else
                    {
                      if ( WPP_GLOBAL_Control != (LsaHandleCache *)&WPP_GLOBAL_Control
                        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
                      {
                        WPP_SF_Dd(
                          *((_QWORD *)WPP_GLOBAL_Control + 2),
                          16,
                          WPP_d35029fbee5832c18fc85881a7fe544c_Traceguids,
                          (unsigned int)a2->HighPart,
                          a2->LowPart);
                      }
                      v8 = -2147483614;
                    }
                    RtlReleaseResource((PRTL_RESOURCE)((char *)v17 + 16));
                    LsapReleaseLogonSession(v17);
                  }
                  else
                  {
                    if ( WPP_GLOBAL_Control != (LsaHandleCache *)&WPP_GLOBAL_Control
                      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
                    {
                      WPP_SF_Dd(
                        *((_QWORD *)WPP_GLOBAL_Control + 2),
                        15,
                        WPP_d35029fbee5832c18fc85881a7fe544c_Traceguids,
                        (unsigned int)a2->HighPart,
                        a2->LowPart);
                    }
                    v8 = -1073741729;
                  }
                  goto LABEL_11;
                }
                if ( WPP_GLOBAL_Control != (LsaHandleCache *)&WPP_GLOBAL_Control
                  && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
                {
                  WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_d35029fbee5832c18fc85881a7fe544c_Traceguids);
                }
                v8 = -1073741727;
              }
            }
            else
            {
              if ( WPP_GLOBAL_Control != (LsaHandleCache *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              {
                WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_d35029fbee5832c18fc85881a7fe544c_Traceguids);
              }
              v8 = -1073741790;
            }
          }
          else
          {
            LastError = GetLastError();
            v8 = NetpApiStatusToNtStatus(LastError, v12, v13, v14);
          }
        }
        RpcRevertToSelf();
      }
    }
    else
    {
      v8 = -1073741790;
    }
  }
LABEL_11:
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  if ( v9 )
    LocalFree(v9);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x1800c8740  mov     [rsp-38h+arg_0], rbx
0x1800c8745  push    rbp
0x1800c8746  push    rsi
0x1800c8747  push    rdi
0x1800c8748  push    r12
0x1800c874a  push    r13
0x1800c874c  push    r14
0x1800c874e  push    r15
0x1800c8750  mov     rbp, rsp
0x1800c8753  sub     rsp, 80h
0x1800c875a  mov     rax, cs:__security_cookie
0x1800c8761  xor     rax, rsp
0x1800c8764  mov     [rbp+var_8], rax
0x1800c8768  xor     r12d, r12d
0x1800c876b  mov     rax, r9
0x1800c876e  mov     r13, r8
0x1800c8771  mov     [rbp+var_38], rax
0x1800c8775  mov     r8, [rbp+arg_28]
0x1800c8779  xor     r9d, r9d
0x1800c877c  mov     [rbp+var_30], r8
0x1800c8780  mov     rsi, rdx
0x1800c8783  mov     rdx, [rbp+arg_20]
0x1800c8787  xorps   xmm0, xmm0
0x1800c878a  mov     [r13+0], r12
0x1800c878e  mov     [rax], r12d
0x1800c8791  mov     [rbp+var_28], rdx
0x1800c8795  mov     [rdx], r12
0x1800c8798  mov     [r8], r12d
0x1800c879b  mov     [rbp+RequiredPrivileges.Privilege.Attributes], r9d
0x1800c879f  mov     [rbp+Result], r12b
0x1800c87a3  mov     [rbp+IsMember], r12d
0x1800c87a7  mov     [rbp+TokenHandle], r12
0x1800c87ab  mov     [rbp+Pid], r12d
0x1800c87af  movups  xmmword ptr [rbp+RequiredPrivileges.PrivilegeCount], xmm0
0x1800c87b3  test    rcx, rcx
0x1800c87b6  jz      short loc_1800C87C2
0x1800c87b8  mov     ebx, 0C0000122h
0x1800c87bd  jmp     loc_1800C88B8
0x1800c87c2  lea     rdx, [rbp+Pid]; Pid
0x1800c87c6  xor     ecx, ecx; Binding
0x1800c87c8  mov     r14, r12
0x1800c87cb  call    cs:__imp_I_RpcBindingInqLocalClientPID
0x1800c87d2  nop     dword ptr [rax+rax+00h]
0x1800c87d7  mov     ebx, eax
0x1800c87d9  test    eax, eax
0x1800c87db  js      loc_1800C888F
0x1800c87e1  call    cs:__imp_GetCurrentProcessId
0x1800c87e8  nop     dword ptr [rax+rax+00h]
0x1800c87ed  cmp     [rbp+Pid], eax
0x1800c87f0  jz      short loc_1800C87FC
0x1800c87f2  mov     ebx, 0C0000022h
0x1800c87f7  jmp     loc_1800C888F
0x1800c87fc  xor     ecx, ecx; BindingHandle
0x1800c87fe  call    cs:__imp_RpcImpersonateClient
0x1800c8805  nop     dword ptr [rax+rax+00h]
0x1800c880a  mov     ecx, eax; Status
0x1800c880c  call    cs:__imp_I_RpcMapWin32Status
0x1800c8813  nop     dword ptr [rax+rax+00h]
0x1800c8818  mov     ebx, eax
0x1800c881a  test    eax, eax
0x1800c881c  js      short loc_1800C888F
0x1800c881e  mov     r15d, 1
0x1800c8824  lea     r9, [rbp+TokenHandle]; TokenHandle
0x1800c8828  mov     r8b, r15b; OpenAsSelf
0x1800c882b  mov     rcx, 0FFFFFFFFFFFFFFFEh; ThreadHandle
0x1800c8832  lea     edx, [r15+7]; DesiredAccess
0x1800c8836  call    cs:__imp_NtOpenThreadToken
0x1800c883d  nop     dword ptr [rax+rax+00h]
0x1800c8842  mov     ebx, eax
0x1800c8844  test    eax, eax
0x1800c8846  js      short loc_1800C8883
0x1800c8848  mov     rdx, cs:?WellKnownSids@@3PEAU_LSAP_WELL_KNOWN_SID_ENTRY@@EA; _LSAP_WELL_KNOWN_SID_ENTRY * WellKnownSids
0x1800c884f  lea     r8, [rbp+IsMember]; IsMember
0x1800c8853  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x1800c8857  mov     rdx, [rdx+2D0h]; SidToCheck
0x1800c885e  call    cs:__imp_CheckTokenMembership
0x1800c8865  nop     dword ptr [rax+rax+00h]
0x1800c886a  test    eax, eax
0x1800c886c  jnz     short loc_1800C88E2
0x1800c886e  call    cs:__imp_GetLastError
0x1800c8875  nop     dword ptr [rax+rax+00h]
0x1800c887a  mov     ecx, eax
0x1800c887c  call    NetpApiStatusToNtStatus
0x1800c8881  mov     ebx, eax
0x1800c8883  call    cs:__imp_RpcRevertToSelf
0x1800c888a  nop     dword ptr [rax+rax+00h]
0x1800c888f  mov     rcx, [rbp+TokenHandle]; hObject
0x1800c8893  test    rcx, rcx
0x1800c8896  jz      short loc_1800C88A4
0x1800c8898  call    cs:__imp_CloseHandle
0x1800c889f  nop     dword ptr [rax+rax+00h]
0x1800c88a4  test    r14, r14
0x1800c88a7  jz      short loc_1800C88B8
0x1800c88a9  mov     rcx, r14; hMem
0x1800c88ac  call    cs:__imp_LocalFree
0x1800c88b3  nop     dword ptr [rax+rax+00h]
0x1800c88b8  mov     eax, ebx
0x1800c88ba  mov     rcx, [rbp+var_8]
0x1800c88be  xor     rcx, rsp; StackCookie
0x1800c88c1  call    __security_check_cookie
0x1800c88c6  mov     rbx, [rsp+80h+arg_0]
0x1800c88ce  add     rsp, 80h
0x1800c88d5  pop     r15
0x1800c88d7  pop     r14
0x1800c88d9  pop     r13
0x1800c88db  pop     r12
0x1800c88dd  pop     rdi
0x1800c88de  pop     rsi
0x1800c88df  pop     rbp
0x1800c88e0  retn
0x1800c88e2  cmp     [rbp+IsMember], r12d
0x1800c88e6  jnz     short loc_1800C8920
0x1800c88e8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c88ef  lea     rax, WPP_GLOBAL_Control
0x1800c88f6  cmp     rcx, rax
0x1800c88f9  jz      short loc_1800C8916
0x1800c88fb  test    [rcx+1Ch], r15b
0x1800c88ff  jz      short loc_1800C8916
0x1800c8901  mov     rcx, [rcx+10h]
0x1800c8905  lea     r8, WPP_d35029fbee5832c18fc85881a7fe544c_Traceguids
0x1800c890c  mov     edx, 0Ch
0x1800c8911  call    WPP_SF_
0x1800c8916  mov     ebx, 0C0000022h
0x1800c891b  jmp     loc_1800C8883
0x1800c8920  mov     rax, cs:?LsapTcbPrivilege@@3U_LUID@@A; _LUID LsapTcbPrivilege
0x1800c8927  lea     r8, [rbp+Result]; Result
0x1800c892b  mov     rcx, [rbp+TokenHandle]; ClientToken
0x1800c892f  lea     rdx, [rbp+RequiredPrivileges]; RequiredPrivileges
0x1800c8933  mov     qword ptr [rbp+RequiredPrivileges.Privilege.Luid.LowPart], rax
0x1800c8937  mov     [rbp+RequiredPrivileges.PrivilegeCount], r15d
0x1800c893b  mov     [rbp+RequiredPrivileges.Control], r15d
0x1800c893f  mov     [rbp+RequiredPrivileges.Privilege.Attributes], r12d
0x1800c8943  call    cs:__imp_NtPrivilegeCheck
0x1800c894a  nop     dword ptr [rax+rax+00h]
0x1800c894f  mov     ebx, eax
0x1800c8951  test    eax, eax
0x1800c8953  js      loc_1800C8883
0x1800c8959  cmp     [rbp+Result], r12b
0x1800c895d  jnz     short loc_1800C8997
0x1800c895f  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c8966  lea     rax, WPP_GLOBAL_Control
0x1800c896d  cmp     rcx, rax
0x1800c8970  jz      short loc_1800C898D
0x1800c8972  test    [rcx+1Ch], r15b
0x1800c8976  jz      short loc_1800C898D
0x1800c8978  mov     rcx, [rcx+10h]
0x1800c897c  lea     r8, WPP_d35029fbee5832c18fc85881a7fe544c_Traceguids
0x1800c8983  mov     edx, 0Dh
0x1800c8988  call    WPP_SF_
0x1800c898d  mov     ebx, 0C0000061h
0x1800c8992  jmp     loc_1800C8883
0x1800c8997  call    cs:__imp_RpcRevertToSelf
0x1800c899e  nop     dword ptr [rax+rax+00h]
0x1800c89a3  mov     rcx, rsi; struct _LUID *
0x1800c89a6  call    ?LsapLocateLogonSession@@YAPEAU_LSAP_LOGON_SESSION@@PEAU_LUID@@@Z; LsapLocateLogonSession(_LUID *)
0x1800c89ab  mov     rdi, rax
0x1800c89ae  test    rax, rax
0x1800c89b1  jnz     short loc_1800C89F3
0x1800c89b3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c89ba  lea     rax, WPP_GLOBAL_Control
0x1800c89c1  cmp     rcx, rax
0x1800c89c4  jz      short loc_1800C89E9
0x1800c89c6  test    [rcx+1Ch], r15b
0x1800c89ca  jz      short loc_1800C89E9
0x1800c89cc  mov     eax, [rsi]
0x1800c89ce  lea     edx, [rdi+0Fh]
0x1800c89d1  mov     r9d, [rsi+4]
0x1800c89d5  lea     r8, WPP_d35029fbee5832c18fc85881a7fe544c_Traceguids
0x1800c89dc  mov     rcx, [rcx+10h]
0x1800c89e0  mov     [rsp+80h+var_60], eax
0x1800c89e4  call    WPP_SF_Dd
0x1800c89e9  mov     ebx, 0C000005Fh
0x1800c89ee  jmp     loc_1800C888F
0x1800c89f3  lea     rcx, [rax+10h]; Resource
0x1800c89f7  mov     dl, r15b; Wait
0x1800c89fa  call    cs:__imp_RtlAcquireResourceShared
0x1800c8a01  nop     dword ptr [rax+rax+00h]
0x1800c8a06  mov     rax, [rdi+218h]
0x1800c8a0d  test    rax, rax
0x1800c8a10  jnz     short loc_1800C8A54
0x1800c8a12  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c8a19  lea     rax, WPP_GLOBAL_Control
0x1800c8a20  cmp     rcx, rax
0x1800c8a23  jz      short loc_1800C8A4A
0x1800c8a25  test    [rcx+1Ch], r15b
0x1800c8a29  jz      short loc_1800C8A4A
0x1800c8a2b  mov     eax, [rsi]
0x1800c8a2d  lea     r8, WPP_d35029fbee5832c18fc85881a7fe544c_Traceguids
0x1800c8a34  mov     r9d, [rsi+4]
0x1800c8a38  mov     edx, 10h
0x1800c8a3d  mov     rcx, [rcx+10h]
0x1800c8a41  mov     [rsp+80h+var_60], eax
0x1800c8a45  call    WPP_SF_Dd
0x1800c8a4a  mov     ebx, 80000022h
0x1800c8a4f  jmp     loc_1800C8AE9
0x1800c8a54  mov     r15d, [rax]
0x1800c8a57  mov     esi, 40h ; '@'
0x1800c8a5c  mov     edx, r15d; uBytes
0x1800c8a5f  mov     ecx, esi; uFlags
0x1800c8a61  call    cs:__imp_LocalAlloc
0x1800c8a68  nop     dword ptr [rax+rax+00h]
0x1800c8a6d  mov     r14, rax
0x1800c8a70  test    rax, rax
0x1800c8a73  jnz     short loc_1800C8A7C
0x1800c8a75  mov     ebx, 0C0000017h
0x1800c8a7a  jmp     short loc_1800C8AE9
0x1800c8a7c  mov     rax, [rdi+218h]
0x1800c8a83  mov     ecx, esi; uFlags
0x1800c8a85  mov     r12d, [rax+10h]
0x1800c8a89  mov     edx, r12d; uBytes
0x1800c8a8c  call    cs:__imp_LocalAlloc
0x1800c8a93  nop     dword ptr [rax+rax+00h]
0x1800c8a98  mov     rsi, rax
0x1800c8a9b  test    rax, rax
0x1800c8a9e  jz      short loc_1800C8A75
0x1800c8aa0  mov     rdx, [rdi+218h]
0x1800c8aa7  mov     rcx, r14; void *
0x1800c8aaa  mov     r8d, [rdx]; Size
0x1800c8aad  mov     rdx, [rdx+8]; Src
0x1800c8ab1  call    memcpy_0
0x1800c8ab6  mov     rdx, [rdi+218h]
0x1800c8abd  mov     rcx, rsi; void *
0x1800c8ac0  mov     r8d, [rdx+10h]; Size
0x1800c8ac4  mov     rdx, [rdx+18h]; Src
0x1800c8ac8  call    memcpy_0
0x1800c8acd  mov     rax, [rbp+var_38]
0x1800c8ad1  mov     [rax], r15d
0x1800c8ad4  mov     rax, [rbp+var_30]
0x1800c8ad8  mov     [r13+0], r14
0x1800c8adc  xor     r14d, r14d
0x1800c8adf  mov     [rax], r12d
0x1800c8ae2  mov     rax, [rbp+var_28]
0x1800c8ae6  mov     [rax], rsi
0x1800c8ae9  lea     rcx, [rdi+10h]; Resource
0x1800c8aed  call    cs:__imp_RtlReleaseResource
0x1800c8af4  nop     dword ptr [rax+rax+00h]
0x1800c8af9  mov     rcx, rdi; struct _LSAP_LOGON_SESSION *
0x1800c8afc  call    ?LsapReleaseLogonSession@@YAXPEAU_LSAP_LOGON_SESSION@@@Z; LsapReleaseLogonSession(_LSAP_LOGON_SESSION *)
0x1800c8b01  jmp     loc_1800C888F
```
