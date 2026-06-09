# LsaRpcIfCallbackFn(void *,void *)

- ea: `0x1800737e0`
- end: `0x180073a67`
- name: `?LsaRpcIfCallbackFn@@YAJPEAX0@Z`
- size: `647`
- prototype: `int(void *, void *)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x1800737e0`
- `0x1800b86d0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800739e6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800739e6`
- `api-ms-win-security-base-l1-2-0!CheckTokenMembershipEx` at `0x18007393e`
- `api-ms-win-security-base-l1-2-0!CheckTokenMembershipEx` at `0x18007393e`
- `ntdll!NtClose` at `0x18007399e`
- `ntdll!NtClose` at `0x1800739ff`
- `ntdll!NtClose` at `0x18007399e`
- `ntdll!NtClose` at `0x1800739ff`
- `ntdll!NtQueryInformationToken` at `0x180073980`
- `ntdll!NtQueryInformationToken` at `0x180073980`
- `ntdll!NtOpenThreadToken` at `0x18007390e`
- `ntdll!NtOpenThreadToken` at `0x18007390e`
- `RPCRT4!RpcRevertToSelfEx` at `0x1800739ad`
- `RPCRT4!RpcRevertToSelfEx` at `0x180073a0e`
- `RPCRT4!RpcRevertToSelfEx` at `0x1800739ad`
- `RPCRT4!RpcRevertToSelfEx` at `0x180073a0e`
- `RPCRT4!RpcImpersonateClient` at `0x1800738d6`
- `RPCRT4!RpcImpersonateClient` at `0x1800738d6`
- `RPCRT4!RpcServerInqCallAttributesW` at `0x180073837`
- `RPCRT4!RpcServerInqCallAttributesW` at `0x180073837`

## pseudocode

```c
__int64 __fastcall LsaRpcIfCallbackFn(void *a1, void *a2)
{
  DWORD LastError; // ebx
  char v4; // dl
  struct _LSAP_RPC_FUNCTION_PROPERTIES near **v5; // rdi
  int v6; // eax
  void *v8; // rcx
  unsigned int v9; // eax
  ULONG ReturnLength; // [rsp+30h] [rbp-59h] BYREF
  void *TokenHandle; // [rsp+38h] [rbp-51h] BYREF
  int v12; // [rsp+40h] [rbp-49h] BYREF
  _DWORD TokenInformation[3]; // [rsp+44h] [rbp-45h] BYREF
  _DWORD RpcCallAttributes[2]; // [rsp+50h] [rbp-39h] BYREF
  __int128 v15; // [rsp+58h] [rbp-31h]
  __int128 v16; // [rsp+68h] [rbp-21h]
  __int128 v17; // [rsp+78h] [rbp-11h]
  __int128 v18; // [rsp+88h] [rbp-1h]
  __int128 v19; // [rsp+98h] [rbp+Fh]
  __int128 v20; // [rsp+A8h] [rbp+1Fh]
  __int64 v21; // [rsp+B8h] [rbp+2Fh]

  RpcCallAttributes[0] = 2;
  RpcCallAttributes[1] = 96;
  v21 = 0;
  v15 = 0;
  v16 = 0;
  v17 = 0;
  v18 = 0;
  v19 = 0;
  v20 = 0;
  LastError = RpcServerInqCallAttributesW(a2, RpcCallAttributes);
  if ( !LastError )
  {
    if ( (unsigned __int16)v20 >= 0x97u )
      return 1745;
    v4 = *((_BYTE *)&LsapRPCFunctionProperties + 8 * (unsigned __int16)v20 + 4);
    v5 = &LsapRPCFunctionProperties + (unsigned __int16)v20;
    if ( (v4 & 4) != 0 )
      return 1745;
    v6 = *(_DWORD *)v5;
    if ( !_bittest(&v6, v18) )
      return 1703;
    if ( (v4 & 1) != 0 && DWORD1(v18) != 1 || (unsigned int)(v17 - 2) <= 2 )
      return 5;
    if ( (v4 & 2) != 0 && (DWORD1(v17) != 68 || (unsigned int)v17 < 5) )
    {
      LastError = RpcImpersonateClient(a2);
      if ( !LastError )
      {
        v12 = 0;
        TokenHandle = 0;
        if ( NtOpenThreadToken((HANDLE)0xFFFFFFFFFFFFFFFELL, 8u, 0, &TokenHandle) < 0 )
          return 5;
        if ( (unsigned int)CheckTokenMembershipEx(TokenHandle, *((_QWORD *)WellKnownSids + 132), 2, &v12) )
        {
          v8 = TokenHandle;
          if ( v12 )
          {
            TokenInformation[0] = 0;
            ReturnLength = 0;
            if ( NtQueryInformationToken(TokenHandle, TokenIsAppContainer, TokenInformation, 4u, &ReturnLength) >= 0
              && (!TokenInformation[0] || (*((_BYTE *)v5 + 4) & 8) != 0) )
            {
LABEL_16:
              NtClose(TokenHandle);
              v9 = RpcRevertToSelfEx(a2);
              if ( !LastError && v9 )
                return v9;
              return LastError;
            }
            v8 = TokenHandle;
          }
          LastError = 5;
          NtClose(v8);
          RpcRevertToSelfEx(a2);
          return LastError;
        }
        LastError = GetLastError();
        goto LABEL_16;
      }
    }
  }
  return LastError;
}

```

## disassembly

```asm
0x1800737e0  push    rbp
0x1800737e2  push    rbx
0x1800737e3  push    rsi
0x1800737e4  lea     rbp, [rsp-47h]
0x1800737e9  sub     rsp, 0D0h
0x1800737f0  mov     rax, cs:__security_cookie
0x1800737f7  xor     rax, rsp
0x1800737fa  mov     [rbp+57h+var_20], rax
0x1800737fe  xorps   xmm0, xmm0
0x180073801  mov     [rbp+57h+RpcCallAttributes], 2
0x180073808  mov     rsi, rdx
0x18007380b  mov     [rbp+57h+var_8C], 60h ; '`'
0x180073812  xor     eax, eax
0x180073814  lea     rdx, [rbp+57h+RpcCallAttributes]; RpcCallAttributes
0x180073818  mov     rcx, rsi; ClientBinding
0x18007381b  mov     [rbp+57h+var_28], rax
0x18007381f  movups  [rbp+57h+var_88], xmm0
0x180073823  movups  [rbp+57h+var_78], xmm0
0x180073827  movups  [rbp+57h+var_68], xmm0
0x18007382b  movups  [rbp+57h+var_58], xmm0
0x18007382f  movups  [rbp+57h+var_48], xmm0
0x180073833  movups  [rbp+57h+var_38], xmm0
0x180073837  call    cs:__imp_RpcServerInqCallAttributesW
0x18007383e  nop     dword ptr [rax+rax+00h]
0x180073843  mov     ebx, eax
0x180073845  test    eax, eax
0x180073847  jnz     short loc_1800738AF
0x180073849  movzx   eax, word ptr [rbp+57h+var_38]
0x18007384d  mov     ecx, 97h
0x180073852  cmp     ax, cx
0x180073855  jnb     loc_180073A30
0x18007385b  lea     rcx, ?LsapRPCFunctionProperties@@3PAU_LSAP_RPC_FUNCTION_PROPERTIES@@A; _LSAP_RPC_FUNCTION_PROPERTIES near * LsapRPCFunctionProperties
0x180073862  mov     [rsp+0E0h+arg_0], rdi
0x18007386a  movzx   edx, byte ptr [rcx+rax*8+4]
0x18007386f  lea     rdi, [rcx+rax*8]
0x180073873  test    dl, 4
0x180073876  jnz     loc_1800739CA
0x18007387c  mov     ecx, dword ptr [rbp+57h+var_58]
0x18007387f  mov     eax, [rdi]
0x180073881  bt      eax, ecx
0x180073884  jnb     loc_180073A3A
0x18007388a  test    dl, 1
0x18007388d  jnz     loc_180073A1C
0x180073893  mov     ecx, dword ptr [rbp+57h+var_68]
0x180073896  lea     eax, [rcx-2]
0x180073899  cmp     eax, 2
0x18007389c  jbe     loc_180073A26
0x1800738a2  test    dl, 2
0x1800738a5  jnz     short loc_1800738C9
0x1800738a7  mov     rdi, [rsp+0E0h+arg_0]
0x1800738af  mov     eax, ebx
0x1800738b1  mov     rcx, [rbp+57h+var_20]
0x1800738b5  xor     rcx, rsp; StackCookie
0x1800738b8  call    __security_check_cookie
0x1800738bd  add     rsp, 0D0h
0x1800738c4  pop     rsi
0x1800738c5  pop     rbx
0x1800738c6  pop     rbp
0x1800738c7  retn
0x1800738c9  cmp     dword ptr [rbp+57h+var_68+4], 44h ; 'D'
0x1800738cd  jz      loc_180073A44
0x1800738d3  mov     rcx, rsi; BindingHandle
0x1800738d6  call    cs:__imp_RpcImpersonateClient
0x1800738dd  nop     dword ptr [rax+rax+00h]
0x1800738e2  mov     ebx, eax
0x1800738e4  test    eax, eax
0x1800738e6  jnz     short loc_1800738A7
0x1800738e8  mov     [rsp+0E0h+arg_10], r14
0x1800738f0  lea     r9, [rbp+57h+TokenHandle]; TokenHandle
0x1800738f4  xor     r14d, r14d
0x1800738f7  xor     r8d, r8d; OpenAsSelf
0x1800738fa  mov     edx, 8; DesiredAccess
0x1800738ff  mov     [rbp+57h+var_A0], r14d
0x180073903  mov     rcx, 0FFFFFFFFFFFFFFFEh; ThreadHandle
0x18007390a  mov     [rbp+57h+TokenHandle], r14
0x18007390e  call    cs:__imp_NtOpenThreadToken
0x180073915  nop     dword ptr [rax+rax+00h]
0x18007391a  test    eax, eax
0x18007391c  js      loc_180073A52
0x180073922  mov     rdx, cs:?WellKnownSids@@3PEAU_LSAP_WELL_KNOWN_SID_ENTRY@@EA; _LSAP_WELL_KNOWN_SID_ENTRY * WellKnownSids
0x180073929  lea     r9, [rbp+57h+var_A0]
0x18007392d  mov     rcx, [rbp+57h+TokenHandle]
0x180073931  mov     r8d, 2
0x180073937  mov     rdx, [rdx+420h]
0x18007393e  call    cs:__imp_CheckTokenMembershipEx
0x180073945  nop     dword ptr [rax+rax+00h]
0x18007394a  test    eax, eax
0x18007394c  jz      loc_1800739E6
0x180073952  mov     rcx, [rbp+57h+TokenHandle]; TokenHandle
0x180073956  cmp     [rbp+57h+var_A0], r14d
0x18007395a  jz      loc_1800739FA
0x180073960  lea     rax, [rbp+57h+var_B0]
0x180073964  mov     [rbp+57h+TokenInformation], r14d
0x180073968  mov     r9d, 4; TokenInformationLength
0x18007396e  mov     [rsp+0E0h+ReturnLength], rax; ReturnLength
0x180073973  lea     r8, [rbp+57h+TokenInformation]; TokenInformation
0x180073977  mov     [rbp+57h+var_B0], r14d
0x18007397b  mov     edx, 1Dh; TokenInformationClass
0x180073980  call    cs:__imp_NtQueryInformationToken
0x180073987  nop     dword ptr [rax+rax+00h]
0x18007398c  test    eax, eax
0x18007398e  js      short loc_1800739F6
0x180073990  cmp     [rbp+57h+TokenInformation], r14d
0x180073994  jnz     loc_180073A5C
0x18007399a  mov     rcx, [rbp+57h+TokenHandle]; Handle
0x18007399e  call    cs:__imp_NtClose
0x1800739a5  nop     dword ptr [rax+rax+00h]
0x1800739aa  mov     rcx, rsi; BindingHandle
0x1800739ad  call    cs:__imp_RpcRevertToSelfEx
0x1800739b4  nop     dword ptr [rax+rax+00h]
0x1800739b9  test    ebx, ebx
0x1800739bb  jz      short loc_1800739D4
0x1800739bd  mov     r14, [rsp+0E0h+arg_10]
0x1800739c5  jmp     loc_1800738A7
0x1800739ca  mov     ebx, 6D1h
0x1800739cf  jmp     loc_1800738A7
0x1800739d4  mov     r14, [rsp+0E0h+arg_10]
0x1800739dc  test    eax, eax
0x1800739de  cmovnz  ebx, eax
0x1800739e1  jmp     loc_1800738A7
0x1800739e6  call    cs:__imp_GetLastError
0x1800739ed  nop     dword ptr [rax+rax+00h]
0x1800739f2  mov     ebx, eax
0x1800739f4  jmp     short loc_18007399A
0x1800739f6  mov     rcx, [rbp+57h+TokenHandle]; Handle
0x1800739fa  mov     ebx, 5
0x1800739ff  call    cs:__imp_NtClose
0x180073a06  nop     dword ptr [rax+rax+00h]
0x180073a0b  mov     rcx, rsi; BindingHandle
0x180073a0e  call    cs:__imp_RpcRevertToSelfEx
0x180073a15  nop     dword ptr [rax+rax+00h]
0x180073a1a  jmp     short loc_1800739BD
0x180073a1c  cmp     dword ptr [rbp+57h+var_58+4], 1
0x180073a20  jz      loc_180073893
0x180073a26  mov     ebx, 5
0x180073a2b  jmp     loc_1800738A7
0x180073a30  mov     ebx, 6D1h
0x180073a35  jmp     loc_1800738AF
0x180073a3a  mov     ebx, 6A7h
0x180073a3f  jmp     loc_1800738A7
0x180073a44  cmp     ecx, 5
0x180073a47  jnb     loc_1800738A7
0x180073a4d  jmp     loc_1800738D3
0x180073a52  mov     ebx, 5
0x180073a57  jmp     loc_1800739BD
0x180073a5c  test    byte ptr [rdi+4], 8
0x180073a60  jz      short loc_1800739F6
0x180073a62  jmp     loc_18007399A
```
