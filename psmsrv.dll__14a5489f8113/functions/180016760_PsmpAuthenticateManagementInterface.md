# PsmpAuthenticateManagementInterface

- ea: `0x180016760`
- end: `0x18001697d`
- name: `PsmpAuthenticateManagementInterface`
- size: `541`
- prototype: `ULONG __fastcall(__int64, void *)`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting`

## callees

- `0x180016760`
- `0x180017f60`
- `0x18001b7e0`
- `0x18001c10c`
- `0x18001ec88`

## import_xrefs

- `ntdll!NtClose` at `0x1800168a6`
- `ntdll!NtClose` at `0x1800168a6`
- `ntdll!RtlNtStatusToDosError` at `0x1800168dd`
- `ntdll!RtlNtStatusToDosError` at `0x1800168dd`
- `ntdll!NtOpenThreadToken` at `0x1800167e3`
- `ntdll!NtOpenThreadToken` at `0x1800167e3`
- `ntdll!NtQueryInformationToken` at `0x180016816`
- `ntdll!NtQueryInformationToken` at `0x180016816`
- `ntdll!NtAccessCheckByType` at `0x18001687d`
- `ntdll!NtAccessCheckByType` at `0x18001687d`
- `RPCRT4!RpcImpersonateClient` at `0x1800167c4`
- `RPCRT4!RpcImpersonateClient` at `0x1800167c4`
- `RPCRT4!RpcRevertToSelfEx` at `0x1800167ee`
- `RPCRT4!RpcRevertToSelfEx` at `0x1800167ee`
- `RPCRT4!I_RpcMapWin32Status` at `0x180016902`
- `RPCRT4!I_RpcMapWin32Status` at `0x180016902`

## pseudocode

```c
ULONG __fastcall PsmpAuthenticateManagementInterface(__int64 a1, void *a2)
{
  RPC_STATUS v3; // eax
  ULONG ObjectTypeLength; // edi
  int v5; // ebx
  __int64 v7; // rbx
  unsigned int v8; // eax
  ULONG PrivilegeSetLength; // [rsp+60h] [rbp-A0h] BYREF
  int AccessStatus; // [rsp+64h] [rbp-9Ch] BYREF
  DWORD GrantedAccess; // [rsp+68h] [rbp-98h] BYREF
  void *TokenHandle; // [rsp+70h] [rbp-90h] BYREF
  ULONG ReturnLength; // [rsp+78h] [rbp-88h] BYREF
  PSID TokenInformation[12]; // [rsp+80h] [rbp-80h] BYREF
  struct _PRIVILEGE_SET PrivilegeSet; // [rsp+E0h] [rbp-20h] BYREF
  struct _GENERIC_MAPPING GenericMapping; // [rsp+F8h] [rbp-8h] BYREF

  AccessStatus = 0;
  GrantedAccess = 0;
  PrivilegeSetLength = 0;
  ReturnLength = 0;
  TokenHandle = 0;
  GenericMapping = 0;
  memset(&PrivilegeSet, 0, sizeof(PrivilegeSet));
  memset_0(TokenInformation, 0, 0x58u);
  v3 = RpcImpersonateClient(a2);
  ObjectTypeLength = v3;
  if ( v3 )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v7 = *((_QWORD *)WPP_GLOBAL_Control + 2);
      v8 = I_RpcMapWin32Status(v3);
      WPP_SF_d(v7, 10, WPP_735869d416213cd339cc44f57f78ca1e_Traceguids, v8);
    }
    return ObjectTypeLength;
  }
  else
  {
    v5 = NtOpenThreadToken((HANDLE)0xFFFFFFFFFFFFFFFELL, 8u, 0, &TokenHandle);
    RpcRevertToSelfEx(a2);
    if ( v5 < 0 )
    {
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          11,
          WPP_735869d416213cd339cc44f57f78ca1e_Traceguids,
          (unsigned int)v5);
    }
    else
    {
      v5 = NtQueryInformationToken(
             TokenHandle,
             (TOKEN_INFORMATION_CLASS)(ObjectTypeLength + 1),
             TokenInformation,
             ObjectTypeLength + 88,
             &ReturnLength);
      if ( v5 >= 0 )
      {
        PrivilegeSetLength = 20;
        v5 = NtAccessCheckByType(
               PsmpManagementDescriptor,
               TokenInformation[0],
               TokenHandle,
               0x2000000u,
               0,
               ObjectTypeLength,
               &GenericMapping,
               &PrivilegeSet,
               &PrivilegeSetLength,
               &GrantedAccess,
               &AccessStatus);
        if ( v5 >= 0 )
        {
          if ( AccessStatus < 0 )
          {
            v5 = AccessStatus;
          }
          else if ( GrantedAccess == ObjectTypeLength )
          {
            v5 = -1073741790;
          }
        }
      }
      NtClose(TokenHandle);
      if ( v5 >= 0 )
        return 0;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        WPP_SF__sid_d(*((_QWORD *)WPP_GLOBAL_Control + 2), v5);
    }
    return RtlNtStatusToDosError(v5);
  }
}

```

## disassembly

```asm
0x180016760  push    rbp
0x180016762  push    rbx
0x180016763  push    rsi
0x180016764  push    rdi
0x180016765  lea     rbp, [rsp-18h]
0x18001676a  sub     rsp, 118h
0x180016771  mov     rax, cs:__security_cookie
0x180016778  xor     rax, rsp
0x18001677b  mov     [rbp+30h+var_28], rax
0x18001677f  xor     eax, eax
0x180016781  mov     [rsp+130h+var_CC], 0
0x180016789  mov     rsi, rdx
0x18001678c  mov     [rsp+130h+var_C8], 0
0x180016794  xorps   xmm0, xmm0
0x180016797  mov     [rbp+30h+var_50.Privilege.Attributes], eax
0x18001679a  xorps   xmm1, xmm1
0x18001679d  mov     [rsp+130h+var_D0], eax
0x1800167a1  lea     r8d, [rax+58h]; Size
0x1800167a5  mov     [rsp+130h+var_B8], eax
0x1800167a9  xor     edx, edx; Val
0x1800167ab  mov     [rsp+130h+TokenHandle], rax
0x1800167b0  lea     rcx, [rbp+30h+TokenInformation]; void *
0x1800167b4  movups  xmmword ptr [rbp+30h+var_38.GenericRead], xmm0
0x1800167b8  movups  xmmword ptr [rbp+30h+var_50.PrivilegeCount], xmm1
0x1800167bc  call    memset_0
0x1800167c1  mov     rcx, rsi; BindingHandle
0x1800167c4  call    cs:__imp_RpcImpersonateClient
0x1800167ca  mov     edi, eax
0x1800167cc  test    eax, eax
0x1800167ce  jnz     loc_1800168E5
0x1800167d4  xor     r8d, r8d; OpenAsSelf
0x1800167d7  lea     r9, [rsp+130h+TokenHandle]; TokenHandle
0x1800167dc  lea     edx, [rax+8]; DesiredAccess
0x1800167df  lea     rcx, [r8-2]; ThreadHandle
0x1800167e3  call    cs:__imp_NtOpenThreadToken
0x1800167e9  mov     rcx, rsi; BindingHandle
0x1800167ec  mov     ebx, eax
0x1800167ee  call    cs:__imp_RpcRevertToSelfEx
0x1800167f4  test    ebx, ebx
0x1800167f6  js      loc_1800168CE
0x1800167fc  mov     rcx, [rsp+130h+TokenHandle]; TokenHandle
0x180016801  lea     rax, [rsp+130h+var_B8]
0x180016806  lea     r9d, [rdi+58h]; TokenInformationLength
0x18001680a  mov     [rsp+130h+ReturnLength], rax; ReturnLength
0x18001680f  lea     r8, [rbp+30h+TokenInformation]; TokenInformation
0x180016813  lea     edx, [rdi+1]; TokenInformationClass
0x180016816  call    cs:__imp_NtQueryInformationToken
0x18001681c  mov     ebx, eax
0x18001681e  test    eax, eax
0x180016820  js      short loc_1800168A1
0x180016822  mov     r8, [rsp+130h+TokenHandle]; ClientToken
0x180016827  lea     rax, [rsp+130h+var_CC]
0x18001682c  mov     rdx, [rbp+30h+TokenInformation]; PrincipalSelfSid
0x180016830  lea     rcx, PsmpManagementDescriptor; SecurityDescriptor
0x180016837  mov     [rsp+130h+AccessStatus], rax; AccessStatus
0x18001683c  mov     r9d, 2000000h; DesiredAccess
0x180016842  lea     rax, [rsp+130h+var_C8]
0x180016847  mov     [rsp+130h+var_D0], 14h
0x18001684f  mov     [rsp+130h+GrantedAccess], rax; GrantedAccess
0x180016854  lea     rax, [rsp+130h+var_D0]
0x180016859  mov     [rsp+130h+PrivilegeSetLength], rax; PrivilegeSetLength
0x18001685e  lea     rax, [rbp+30h+var_50]
0x180016862  mov     [rsp+130h+PrivilegeSet], rax; PrivilegeSet
0x180016867  lea     rax, [rbp+30h+var_38]
0x18001686b  mov     [rsp+130h+GenericMapping], rax; GenericMapping
0x180016870  mov     [rsp+130h+ObjectTypeLength], edi; ObjectTypeLength
0x180016874  mov     [rsp+130h+ReturnLength], 0; ObjectTypeList
0x18001687d  call    cs:__imp_NtAccessCheckByType
0x180016883  mov     ebx, eax
0x180016885  test    eax, eax
0x180016887  js      short loc_1800168A1
0x180016889  mov     eax, [rsp+130h+var_CC]
0x18001688d  test    eax, eax
0x18001688f  js      loc_180016941
0x180016895  cmp     [rsp+130h+var_C8], edi
0x180016899  mov     eax, 0C0000022h
0x18001689e  cmovz   ebx, eax
0x1800168a1  mov     rcx, [rsp+130h+TokenHandle]; Handle
0x1800168a6  call    cs:__imp_NtClose
0x1800168ac  test    ebx, ebx
0x1800168ae  js      loc_180016948
0x1800168b4  xor     eax, eax
0x1800168b6  mov     rcx, [rbp+30h+var_28]
0x1800168ba  xor     rcx, rsp; StackCookie
0x1800168bd  call    __security_check_cookie
0x1800168c2  add     rsp, 118h
0x1800168c9  pop     rdi
0x1800168ca  pop     rsi
0x1800168cb  pop     rbx
0x1800168cc  pop     rbp
0x1800168cd  retn
0x1800168ce  mov     rcx, cs:WPP_GLOBAL_Control
0x1800168d5  test    byte ptr [rcx+1Ch], 2
0x1800168d9  jnz     short loc_180016921
0x1800168db  mov     ecx, ebx; Status
0x1800168dd  call    cs:__imp_RtlNtStatusToDosError
0x1800168e3  jmp     short loc_1800168B6
0x1800168e5  mov     rbx, cs:WPP_GLOBAL_Control
0x1800168ec  test    byte ptr [rbx+1Ch], 2
0x1800168f0  jnz     short loc_1800168F6
0x1800168f2  mov     eax, edi
0x1800168f4  jmp     short loc_1800168B6
0x1800168f6  cmp     byte ptr [rbx+19h], 2
0x1800168fa  jb      short loc_1800168F2
0x1800168fc  mov     rbx, [rbx+10h]
0x180016900  mov     ecx, edi; Status
0x180016902  call    cs:__imp_I_RpcMapWin32Status
0x180016908  mov     edx, 0Ah
0x18001690d  lea     r8, WPP_735869d416213cd339cc44f57f78ca1e_Traceguids
0x180016914  mov     r9d, eax
0x180016917  mov     rcx, rbx
0x18001691a  call    WPP_SF_d
0x18001691f  jmp     short loc_1800168F2
0x180016921  cmp     byte ptr [rcx+19h], 2
0x180016925  jb      short loc_1800168DB
0x180016927  mov     rcx, [rcx+10h]
0x18001692b  lea     r8, WPP_735869d416213cd339cc44f57f78ca1e_Traceguids
0x180016932  mov     edx, 0Bh
0x180016937  mov     r9d, ebx
0x18001693a  call    WPP_SF_d
0x18001693f  jmp     short loc_1800168DB
0x180016941  mov     ebx, eax
0x180016943  jmp     loc_1800168A1
0x180016948  mov     rcx, cs:WPP_GLOBAL_Control
0x18001694f  test    byte ptr [rcx+1Ch], 2
0x180016953  jz      short loc_1800168DB
0x180016955  cmp     byte ptr [rcx+19h], 2
0x180016959  jb      short loc_1800168DB
0x18001695b  mov     r9, [rbp+30h+TokenInformation]
0x18001695f  lea     r8, WPP_735869d416213cd339cc44f57f78ca1e_Traceguids
0x180016966  mov     rcx, [rcx+10h]; LoggerHandle
0x18001696a  mov     edx, 0Ch
0x18001696f  mov     dword ptr [rsp+130h+ReturnLength], ebx; char
0x180016973  call    WPP_SF__sid_d
0x180016978  jmp     loc_1800168DB
```
