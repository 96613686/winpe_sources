# TSLSRPCAccessCheck(void)

- ea: `0x18000dab8`
- end: `0x18000dec0`
- name: `?TSLSRPCAccessCheck@@YAHXZ`
- size: `1032`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x18000c960`

## callees

- `0x180005665`
- `0x18000acf4`
- `0x18000d028`
- `0x18000d060`
- `0x18000dab8`
- `0x18001ad48`
- `0x18001ad74`
- `0x18001ae3c`
- `0x1800385d8`
- `0x180078280`
- `0x1800a0fb0`

## import_xrefs

- `ADVAPI32!AccessCheck` at `0x18000dde7`
- `ADVAPI32!AccessCheck` at `0x18000dde7`
- `ADVAPI32!OpenThreadToken` at `0x18000dc11`
- `ADVAPI32!OpenThreadToken` at `0x18000dc11`
- `NETAPI32!NetGetJoinInformation` at `0x18000dcab`
- `NETAPI32!NetGetJoinInformation` at `0x18000dcab`
- `NETAPI32!NetApiBufferFree` at `0x18000de5a`
- `NETAPI32!NetApiBufferFree` at `0x18000de5a`
- `RPCRT4!RpcImpersonateClient` at `0x18000dbc2`
- `RPCRT4!RpcImpersonateClient` at `0x18000dbc2`
- `RPCRT4!RpcRevertToSelf` at `0x18000dc53`
- `RPCRT4!RpcRevertToSelf` at `0x18000dc64`
- `RPCRT4!RpcRevertToSelf` at `0x18000dc53`
- `RPCRT4!RpcRevertToSelf` at `0x18000dc64`
- `KERNEL32!GetComputerNameW` at `0x18000dc8b`
- `KERNEL32!GetComputerNameW` at `0x18000dc8b`
- `KERNEL32!GetCurrentThread` at `0x18000dbf6`
- `KERNEL32!GetCurrentThread` at `0x18000dbf6`
- `KERNEL32!GetLastError` at `0x18000dc21`
- `KERNEL32!GetLastError` at `0x18000dd71`
- `KERNEL32!GetLastError` at `0x18000ddf7`
- `KERNEL32!GetLastError` at `0x18000dc21`
- `KERNEL32!GetLastError` at `0x18000dd71`
- `KERNEL32!GetLastError` at `0x18000ddf7`
- `KERNEL32!CloseHandle` at `0x18000de3a`
- `KERNEL32!CloseHandle` at `0x18000de3a`

## string_xrefs

- `0x18000db8f`: `TSLSRPCAccessCheck`
- `0x18000de7f`: `TSLSRPCAccessCheck`

## pseudocode

```c
__int64 TSLSRPCAccessCheck(void)
{
  PVOID *v1; // rcx
  __int64 v2; // rdx
  HANDLE CurrentThread; // rax
  DWORD LastError; // eax
  DWORD JoinInformation; // eax
  __int64 v6; // rdx
  WINBOOL AccessStatus[2]; // [rsp+48h] [rbp-C0h] BYREF
  void *TokenHandle; // [rsp+50h] [rbp-B8h] BYREF
  LPWSTR NameBuffer; // [rsp+58h] [rbp-B0h] BYREF
  DWORD nSize; // [rsp+60h] [rbp-A8h] BYREF
  _NETSETUP_JOIN_STATUS BufferType; // [rsp+64h] [rbp-A4h] BYREF
  DWORD PrivilegeSetLength[2]; // [rsp+68h] [rbp-A0h] BYREF
  unsigned __int64 v13; // [rsp+70h] [rbp-98h] BYREF
  _GENERIC_MAPPING GenericMapping; // [rsp+78h] [rbp-90h] BYREF
  WCHAR Buffer; // [rsp+88h] [rbp-80h] BYREF
  __int128 v16; // [rsp+8Ah] [rbp-7Eh]
  __int64 v17; // [rsp+9Ah] [rbp-6Eh]
  int v18; // [rsp+A2h] [rbp-66h]
  __int16 v19; // [rsp+A6h] [rbp-62h]
  struct _PRIVILEGE_SET PrivilegeSet; // [rsp+A8h] [rbp-60h] BYREF
  unsigned __int16 v21; // [rsp+E8h] [rbp-20h] BYREF
  _BYTE v22[1022]; // [rsp+EAh] [rbp-1Eh] BYREF

  GenericMapping.GenericRead = 0x20000;
  TokenHandle = 0;
  PrivilegeSetLength[0] = 0;
  AccessStatus[0] = 0;
  Buffer = 0;
  v17 = 0;
  v16 = 0;
  v18 = 0;
  v19 = 0;
  v21 = 0;
  GenericMapping.GenericWrite = 0x20000;
  GenericMapping.GenericExecute = 0x20000;
  GenericMapping.GenericAll = 2031616;
  PrivilegeSetLength[1] = 56;
  memset_0(v22, 0, sizeof(v22));
  nSize = 16;
  NameBuffer = 0;
  v13 = 0;
  BufferType = NetSetupDomainName;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0 )
    WPP_SF_S(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      57,
      &WPP_14f402b3e7783efa9cd4a35c63de2b16_Traceguids,
      L"TSLSRPCAccessCheck");
  if ( !g_pSecDes && (!(unsigned int)TSLSLoadLocalGroupSecDes() || !g_pSecDes) )
    return 0;
  if ( RpcImpersonateClient(0) )
  {
    v1 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) == 0 )
      goto LABEL_39;
    v2 = 58;
    goto LABEL_37;
  }
  CurrentThread = GetCurrentThread();
  if ( !OpenThreadToken(CurrentThread, 8u, 0, &TokenHandle) )
  {
    LastError = GetLastError();
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 59, &WPP_14f402b3e7783efa9cd4a35c63de2b16_Traceguids, LastError);
    RpcRevertToSelf();
    goto LABEL_38;
  }
  RpcRevertToSelf();
  if ( (unsigned int)IsRequestFromLocalMachine(TokenHandle) )
  {
    if ( GetComputerNameW(&Buffer, &nSize) )
    {
      JoinInformation = NetGetJoinInformation(0, &NameBuffer, &BufferType);
      if ( JoinInformation )
      {
        v1 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) == 0 )
          goto LABEL_39;
        v6 = 60;
      }
      else
      {
        StringCchLengthW(NameBuffer, 0x7FFFFFFFu, &v13);
        if ( v13 + 18 >= 0x200 )
          goto LABEL_38;
        StringCchPrintfW(&v21, 0x200u, L"%s\\%s$", NameBuffer, &Buffer);
        JoinInformation = IsMachineNameInTSCGrp(&v21, AccessStatus);
        if ( !JoinInformation )
          goto LABEL_38;
        v1 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) == 0 )
          goto LABEL_39;
        v6 = 61;
      }
    }
    else
    {
      JoinInformation = GetLastError();
      if ( !JoinInformation )
        goto LABEL_38;
      v1 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) == 0 )
        goto LABEL_39;
      v6 = 62;
    }
    WPP_SF_D(v1[2], v6, &WPP_14f402b3e7783efa9cd4a35c63de2b16_Traceguids, JoinInformation);
  }
  else if ( !AccessCheck(
               g_pSecDes,
               TokenHandle,
               0x20000u,
               &GenericMapping,
               &PrivilegeSet,
               &PrivilegeSetLength[1],
               PrivilegeSetLength,
               AccessStatus) )
  {
    GetLastError();
    v1 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) == 0 )
      goto LABEL_39;
    v2 = 63;
LABEL_37:
    WPP_SF_(v1[2], v2, &WPP_14f402b3e7783efa9cd4a35c63de2b16_Traceguids);
  }
LABEL_38:
  v1 = (PVOID *)WPP_GLOBAL_Control;
LABEL_39:
  if ( TokenHandle )
  {
    CloseHandle(TokenHandle);
    v1 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( NameBuffer )
  {
    NetApiBufferFree(NameBuffer);
    v1 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v1 != &WPP_GLOBAL_Control && (*((_DWORD *)v1 + 7) & 0x1000) != 0 )
    WPP_SF_S(v1[2], 64, &WPP_14f402b3e7783efa9cd4a35c63de2b16_Traceguids, L"TSLSRPCAccessCheck");
  return (unsigned int)AccessStatus[0];
}

```

## disassembly

```asm
0x18000dab8  mov     rax, rsp
0x18000dabb  mov     [rax+8], rbx
0x18000dabf  mov     [rax+10h], rsi
0x18000dac3  mov     [rax+18h], rdi
0x18000dac7  push    rbp
0x18000dac8  lea     rbp, [rax-3F8h]
0x18000dacf  sub     rsp, 4F0h
0x18000dad6  mov     rax, cs:__security_cookie
0x18000dadd  xor     rax, rsp
0x18000dae0  mov     [rbp+3F0h+var_10], rax
0x18000dae7  xor     ebx, ebx
0x18000dae9  mov     [rsp+4F0h+GenericMapping.GenericRead], 20000h
0x18000daf1  xor     eax, eax
0x18000daf3  mov     [rsp+4F0h+TokenHandle], rbx
0x18000daf8  xorps   xmm0, xmm0
0x18000dafb  mov     [rsp+4F0h+var_490], ebx
0x18000daff  xor     edx, edx; Val
0x18000db01  mov     [rsp+4F0h+var_4B0], ebx
0x18000db05  mov     r8d, 3FEh; Size
0x18000db0b  mov     [rbp+3F0h+Buffer], bx
0x18000db0f  lea     rcx, [rbp+3F0h+var_40E]; void *
0x18000db13  mov     [rbp+3F0h+var_45E], rax
0x18000db17  movups  [rbp+3F0h+var_46E], xmm0
0x18000db1b  mov     [rbp+3F0h+var_456], eax
0x18000db1e  mov     [rbp+3F0h+var_452], ax
0x18000db22  mov     [rbp+3F0h+var_410], bx
0x18000db26  mov     [rsp+4F0h+GenericMapping.GenericWrite], 20000h
0x18000db2e  mov     [rsp+4F0h+GenericMapping.GenericExecute], 20000h
0x18000db36  mov     [rsp+4F0h+GenericMapping.GenericAll], 1F0000h
0x18000db3e  mov     [rsp+4F0h+var_490+4], 38h ; '8'
0x18000db46  call    memset_0
0x18000db4b  mov     [rsp+4F0h+nSize], 10h
0x18000db53  mov     [rsp+4F0h+NameBuffer], rbx
0x18000db58  mov     [rsp+4F0h+var_488], rbx
0x18000db5d  mov     [rsp+4F0h+BufferType], 3
0x18000db65  mov     rcx, cs:WPP_GLOBAL_Control
0x18000db6c  lea     rdi, WPP_GLOBAL_Control
0x18000db73  lea     rsi, WPP_14f402b3e7783efa9cd4a35c63de2b16_Traceguids
0x18000db7a  cmp     rcx, rdi
0x18000db7d  jz      short loc_18000DB9E
0x18000db7f  test    dword ptr [rcx+1Ch], 1000h
0x18000db86  jz      short loc_18000DB9E
0x18000db88  mov     rcx, [rcx+10h]
0x18000db8c  lea     edx, [rbx+39h]
0x18000db8f  lea     r9, aTslsrpcaccessc; "TSLSRPCAccessCheck"
0x18000db96  mov     r8, rsi
0x18000db99  call    WPP_SF_S
0x18000db9e  cmp     cs:?g_pSecDes@@3PEAXEA, rbx; void * g_pSecDes
0x18000dba5  jnz     short loc_18000DBC0
0x18000dba7  call    ?TSLSLoadLocalGroupSecDes@@YAHXZ; TSLSLoadLocalGroupSecDes(void)
0x18000dbac  test    eax, eax
0x18000dbae  jz      short loc_18000DBB9
0x18000dbb0  cmp     cs:?g_pSecDes@@3PEAXEA, rbx; void * g_pSecDes
0x18000dbb7  jnz     short loc_18000DBC0
0x18000dbb9  xor     eax, eax
0x18000dbbb  jmp     loc_18000DE97
0x18000dbc0  xor     ecx, ecx; BindingHandle
0x18000dbc2  call    cs:__imp_RpcImpersonateClient
0x18000dbc9  nop     dword ptr [rax+rax+00h]
0x18000dbce  test    eax, eax
0x18000dbd0  jz      short loc_18000DBF6
0x18000dbd2  mov     rcx, cs:WPP_GLOBAL_Control
0x18000dbd9  cmp     rcx, rdi
0x18000dbdc  jz      loc_18000DE2D
0x18000dbe2  test    byte ptr [rcx+1Ch], 20h
0x18000dbe6  jz      loc_18000DE2D
0x18000dbec  mov     edx, 3Ah ; ':'
0x18000dbf1  jmp     loc_18000DE1A
0x18000dbf6  call    cs:__imp_GetCurrentThread
0x18000dbfd  nop     dword ptr [rax+rax+00h]
0x18000dc02  xor     r8d, r8d; OpenAsSelf
0x18000dc05  lea     r9, [rsp+4F0h+TokenHandle]; TokenHandle
0x18000dc0a  mov     rcx, rax; ThreadHandle
0x18000dc0d  lea     edx, [r8+8]; DesiredAccess
0x18000dc11  call    cs:__imp_OpenThreadToken
0x18000dc18  nop     dword ptr [rax+rax+00h]
0x18000dc1d  test    eax, eax
0x18000dc1f  jnz     short loc_18000DC64
0x18000dc21  call    cs:__imp_GetLastError
0x18000dc28  nop     dword ptr [rax+rax+00h]
0x18000dc2d  mov     rcx, cs:WPP_GLOBAL_Control
0x18000dc34  cmp     rcx, rdi
0x18000dc37  jz      short loc_18000DC53
0x18000dc39  test    byte ptr [rcx+1Ch], 20h
0x18000dc3d  jz      short loc_18000DC53
0x18000dc3f  mov     rcx, [rcx+10h]
0x18000dc43  mov     edx, 3Bh ; ';'
0x18000dc48  mov     r9d, eax
0x18000dc4b  mov     r8, rsi
0x18000dc4e  call    WPP_SF_D
0x18000dc53  call    cs:__imp_RpcRevertToSelf
0x18000dc5a  nop     dword ptr [rax+rax+00h]
0x18000dc5f  jmp     loc_18000DE26
0x18000dc64  call    cs:__imp_RpcRevertToSelf
0x18000dc6b  nop     dword ptr [rax+rax+00h]
0x18000dc70  mov     rcx, [rsp+4F0h+TokenHandle]; TokenHandle
0x18000dc75  call    ?IsRequestFromLocalMachine@@YAHPEAX@Z; IsRequestFromLocalMachine(void *)
0x18000dc7a  test    eax, eax
0x18000dc7c  jz      loc_18000DDA9
0x18000dc82  lea     rdx, [rsp+4F0h+nSize]; nSize
0x18000dc87  lea     rcx, [rbp+3F0h+Buffer]; lpBuffer
0x18000dc8b  call    cs:__imp_GetComputerNameW
0x18000dc92  nop     dword ptr [rax+rax+00h]
0x18000dc97  test    eax, eax
0x18000dc99  jz      loc_18000DD71
0x18000dc9f  lea     r8, [rsp+4F0h+BufferType]; BufferType
0x18000dca4  xor     ecx, ecx; lpServer
0x18000dca6  lea     rdx, [rsp+4F0h+NameBuffer]; lpNameBuffer
0x18000dcab  call    cs:__imp_NetGetJoinInformation
0x18000dcb2  nop     dword ptr [rax+rax+00h]
0x18000dcb7  test    eax, eax
0x18000dcb9  jz      short loc_18000DCEE
0x18000dcbb  mov     rcx, cs:WPP_GLOBAL_Control
0x18000dcc2  cmp     rcx, rdi
0x18000dcc5  jz      loc_18000DE2D
0x18000dccb  test    byte ptr [rcx+1Ch], 20h
0x18000dccf  jz      loc_18000DE2D
0x18000dcd5  mov     edx, 3Ch ; '<'
0x18000dcda  mov     rcx, [rcx+10h]
0x18000dcde  mov     r9d, eax
0x18000dce1  mov     r8, rsi
0x18000dce4  call    WPP_SF_D
0x18000dce9  jmp     loc_18000DE26
0x18000dcee  mov     rcx, [rsp+4F0h+NameBuffer]; unsigned __int16 *
0x18000dcf3  lea     r8, [rsp+4F0h+var_488]; unsigned __int64 *
0x18000dcf8  mov     edx, 7FFFFFFFh; unsigned __int64
0x18000dcfd  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x18000dd02  mov     r8, [rsp+4F0h+var_488]
0x18000dd07  mov     edx, 200h; unsigned __int64
0x18000dd0c  add     r8, 12h
0x18000dd10  cmp     r8, rdx
0x18000dd13  jnb     loc_18000DE26
0x18000dd19  mov     r9, [rsp+4F0h+NameBuffer]
0x18000dd1e  lea     rax, [rbp+3F0h+Buffer]
0x18000dd22  lea     r8, aSS; "%s\\%s$"
0x18000dd29  mov     [rsp+4F0h+PrivilegeSet], rax
0x18000dd2e  lea     rcx, [rbp+3F0h+var_410]; unsigned __int16 *
0x18000dd32  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000dd37  lea     rdx, [rsp+4F0h+var_4B0]; int *
0x18000dd3c  lea     rcx, [rbp+3F0h+var_410]; unsigned __int16 *
0x18000dd40  call    ?IsMachineNameInTSCGrp@@YAKPEAGPEAH@Z; IsMachineNameInTSCGrp(ushort *,int *)
0x18000dd45  test    eax, eax
0x18000dd47  jz      loc_18000DE26
0x18000dd4d  mov     rcx, cs:WPP_GLOBAL_Control
0x18000dd54  cmp     rcx, rdi
0x18000dd57  jz      loc_18000DE2D
0x18000dd5d  test    byte ptr [rcx+1Ch], 20h
0x18000dd61  jz      loc_18000DE2D
0x18000dd67  mov     edx, 3Dh ; '='
0x18000dd6c  jmp     loc_18000DCDA
0x18000dd71  call    cs:__imp_GetLastError
0x18000dd78  nop     dword ptr [rax+rax+00h]
0x18000dd7d  test    eax, eax
0x18000dd7f  jz      loc_18000DE26
0x18000dd85  mov     rcx, cs:WPP_GLOBAL_Control
0x18000dd8c  cmp     rcx, rdi
0x18000dd8f  jz      loc_18000DE2D
0x18000dd95  test    byte ptr [rcx+1Ch], 20h
0x18000dd99  jz      loc_18000DE2D
0x18000dd9f  mov     edx, 3Eh ; '>'
0x18000dda4  jmp     loc_18000DCDA
0x18000dda9  mov     rdx, [rsp+4F0h+TokenHandle]; ClientToken
0x18000ddae  lea     rax, [rsp+4F0h+var_4B0]
0x18000ddb3  mov     rcx, cs:?g_pSecDes@@3PEAXEA; pSecurityDescriptor
0x18000ddba  lea     r9, [rsp+4F0h+GenericMapping]; GenericMapping
0x18000ddbf  mov     [rsp+4F0h+AccessStatus], rax; AccessStatus
0x18000ddc4  mov     r8d, 20000h; DesiredAccess
0x18000ddca  lea     rax, [rsp+4F0h+var_490]
0x18000ddcf  mov     [rsp+4F0h+GrantedAccess], rax; GrantedAccess
0x18000ddd4  lea     rax, [rsp+4F0h+var_490+4]
0x18000ddd9  mov     [rsp+4F0h+PrivilegeSetLength], rax; PrivilegeSetLength
0x18000ddde  lea     rax, [rbp+3F0h+var_450]
0x18000dde2  mov     [rsp+4F0h+PrivilegeSet], rax; PrivilegeSet
0x18000dde7  call    cs:__imp_AccessCheck
0x18000ddee  nop     dword ptr [rax+rax+00h]
0x18000ddf3  test    eax, eax
0x18000ddf5  jnz     short loc_18000DE26
0x18000ddf7  call    cs:__imp_GetLastError
0x18000ddfe  nop     dword ptr [rax+rax+00h]
0x18000de03  mov     rcx, cs:WPP_GLOBAL_Control
0x18000de0a  cmp     rcx, rdi
0x18000de0d  jz      short loc_18000DE2D
0x18000de0f  test    byte ptr [rcx+1Ch], 20h
0x18000de13  jz      short loc_18000DE2D
0x18000de15  mov     edx, 3Fh ; '?'
0x18000de1a  mov     rcx, [rcx+10h]
0x18000de1e  mov     r8, rsi
0x18000de21  call    WPP_SF_
0x18000de26  mov     rcx, cs:WPP_GLOBAL_Control
0x18000de2d  mov     rax, [rsp+4F0h+TokenHandle]
0x18000de32  test    rax, rax
0x18000de35  jz      short loc_18000DE4D
0x18000de37  mov     rcx, rax; hObject
0x18000de3a  call    cs:__imp_CloseHandle
0x18000de41  nop     dword ptr [rax+rax+00h]
0x18000de46  mov     rcx, cs:WPP_GLOBAL_Control
0x18000de4d  mov     rax, [rsp+4F0h+NameBuffer]
0x18000de52  test    rax, rax
0x18000de55  jz      short loc_18000DE6D
0x18000de57  mov     rcx, rax; Buffer
0x18000de5a  call    cs:__imp_NetApiBufferFree
0x18000de61  nop     dword ptr [rax+rax+00h]
0x18000de66  mov     rcx, cs:WPP_GLOBAL_Control
0x18000de6d  cmp     rcx, rdi
0x18000de70  jz      short loc_18000DE93
0x18000de72  test    dword ptr [rcx+1Ch], 1000h
0x18000de79  jz      short loc_18000DE93
0x18000de7b  mov     rcx, [rcx+10h]
0x18000de7f  lea     r9, aTslsrpcaccessc; "TSLSRPCAccessCheck"
0x18000de86  mov     edx, 40h ; '@'
0x18000de8b  mov     r8, rsi
0x18000de8e  call    WPP_SF_S
0x18000de93  mov     eax, [rsp+4F0h+var_4B0]
0x18000de97  mov     rcx, [rbp+3F0h+var_10]
0x18000de9e  xor     rcx, rsp; StackCookie
0x18000dea1  call    __security_check_cookie
0x18000dea6  lea     r11, [rsp+4F0h+var_s0]
0x18000deae  mov     rbx, [r11+10h]
0x18000deb2  mov     rsi, [r11+18h]
0x18000deb6  mov     rdi, [r11+20h]
0x18000deba  mov     rsp, r11
0x18000debd  pop     rbp
0x18000debe  retn
```
