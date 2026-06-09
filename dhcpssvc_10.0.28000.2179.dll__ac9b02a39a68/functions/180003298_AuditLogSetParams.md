# AuditLogSetParams

- ea: `0x180003298`
- end: `0x180003533`
- name: `AuditLogSetParams`
- size: `667`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, service_task`

## callers

- `0x18002f230`

## callees

- `0x18000282c`
- `0x180003298`
- `0x180005834`
- `0x180062128`
- `0x18009c43c`

## import_xrefs

- `ADVAPI32!RegSetValueExW` at `0x1800033c4`
- `ADVAPI32!RegSetValueExW` at `0x180003435`
- `ADVAPI32!RegSetValueExW` at `0x180003487`
- `ADVAPI32!RegSetValueExW` at `0x1800034e6`
- `ADVAPI32!RegSetValueExW` at `0x1800033c4`
- `ADVAPI32!RegSetValueExW` at `0x180003435`
- `ADVAPI32!RegSetValueExW` at `0x180003487`
- `ADVAPI32!RegSetValueExW` at `0x1800034e6`
- `RPCRT4!RpcImpersonateClient` at `0x1800032b3`
- `RPCRT4!RpcImpersonateClient` at `0x1800032b3`
- `RPCRT4!RpcRevertToSelf` at `0x180003307`
- `RPCRT4!RpcRevertToSelf` at `0x180003332`
- `RPCRT4!RpcRevertToSelf` at `0x180003307`
- `RPCRT4!RpcRevertToSelf` at `0x180003332`
- `KERNEL32!GetLastError` at `0x180003313`
- `KERNEL32!GetLastError` at `0x180003313`

## string_xrefs

- `0x1800033ab`: `DhcpLogFilePath`

## pseudocode

```c
RPC_STATUS AuditLogSetParams(__int64 a1, WCHAR *a2, int a3, int a4, ...)
{
  RPC_STATUS v5; // esi
  RPC_STATUS result; // eax
  int v7; // edi
  DWORD cbData; // eax
  __int64 v9; // rax
  unsigned int v10; // ebx
  _QWORD *v11; // rcx
  __int64 v12; // rdx
  int Data; // [rsp+60h] [rbp+18h] BYREF
  int v14; // [rsp+68h] [rbp+20h] BYREF
  va_list va; // [rsp+70h] [rbp+28h] BYREF

  va_start(va, a4);
  v14 = a4;
  Data = a3;
  v5 = RpcImpersonateClient(0);
  if ( !(unsigned int)CreateDirectoryPathW(a2) )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      WPP_SF_LS(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        25,
        (unsigned int)&WPP_3f918084cf8d369c2c20a8a49a789173_Traceguids,
        0,
        (__int64)a2);
    if ( !v5 )
      RpcRevertToSelf();
    return GetLastError();
  }
  v7 = DhcpAddServiceAceToDir(a2);
  if ( !v5 )
  {
    result = RpcRevertToSelf();
    if ( result )
      return result;
  }
  if ( !v7 )
  {
    if ( a2 )
    {
      v9 = -1;
      do
        ++v9;
      while ( a2[v9] );
      cbData = 2 * v9 + 2;
    }
    else
    {
      cbData = 0;
    }
    v10 = RegSetValueExW(DhcpGlobalRegParam, L"DhcpLogFilePath", 0, 1u, (const BYTE *)a2, cbData);
    if ( v10 )
    {
      v11 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
        return v10;
      v12 = 27;
    }
    else
    {
      v10 = RegSetValueExW(DhcpGlobalRegParam, L"DhcpLogDiskSpaceCheckInterval", 0, 4u, (const BYTE *)&Data, 4u);
      if ( v10 )
      {
        v11 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
          return v10;
        v12 = 28;
      }
      else
      {
        v10 = RegSetValueExW(DhcpGlobalRegParam, L"DhcpLogFilesMaxSize", 0, 4u, (const BYTE *)&v14, 4u);
        if ( v10 )
        {
          v11 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
          {
            return v10;
          }
          v12 = 29;
        }
        else
        {
          v10 = RegSetValueExW(DhcpGlobalRegParam, L"DhcpLogMinSpaceOnDisk", 0, 4u, (const BYTE *)va, 4u);
          if ( !v10 )
            return 0;
          v11 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
          {
            return v10;
          }
          v12 = 30;
        }
      }
    }
    WPP_SF_D(v11[2], v12, &WPP_3f918084cf8d369c2c20a8a49a789173_Traceguids, v10);
    return v10;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    WPP_SF_LS(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      26,
      (unsigned int)&WPP_3f918084cf8d369c2c20a8a49a789173_Traceguids,
      v7,
      (__int64)a2);
  return v7;
}

```

## disassembly

```asm
0x180003298  mov     [rsp+arg_0], rbx
0x18000329d  mov     [rsp+arg_18], r9d
0x1800032a2  mov     [rsp+Data], r8d
0x1800032a7  push    rbp
0x1800032a8  push    rsi
0x1800032a9  push    rdi
0x1800032aa  sub     rsp, 30h
0x1800032ae  xor     ecx, ecx; BindingHandle
0x1800032b0  mov     rbx, rdx
0x1800032b3  call    cs:__imp_RpcImpersonateClient
0x1800032ba  nop     dword ptr [rax+rax+00h]
0x1800032bf  mov     rcx, rbx; lpPathName
0x1800032c2  mov     esi, eax
0x1800032c4  call    CreateDirectoryPathW
0x1800032c9  xor     ebp, ebp
0x1800032cb  test    eax, eax
0x1800032cd  jnz     short loc_180003324
0x1800032cf  mov     rcx, cs:WPP_GLOBAL_Control
0x1800032d6  lea     r8, WPP_GLOBAL_Control
0x1800032dd  cmp     rcx, r8
0x1800032e0  jz      short loc_180003303
0x1800032e2  test    byte ptr [rcx+1Ch], 10h
0x1800032e6  jz      short loc_180003303
0x1800032e8  mov     rcx, [rcx+10h]
0x1800032ec  lea     edx, [rbp+19h]
0x1800032ef  xor     r9d, r9d
0x1800032f2  mov     [rsp+48h+lpData], rbx
0x1800032f7  lea     r8, WPP_3f918084cf8d369c2c20a8a49a789173_Traceguids
0x1800032fe  call    WPP_SF_LS
0x180003303  test    esi, esi
0x180003305  jnz     short loc_180003313
0x180003307  call    cs:__imp_RpcRevertToSelf
0x18000330e  nop     dword ptr [rax+rax+00h]
0x180003313  call    cs:__imp_GetLastError
0x18000331a  nop     dword ptr [rax+rax+00h]
0x18000331f  jmp     loc_180003525
0x180003324  mov     rcx, rbx; pObjectName
0x180003327  call    DhcpAddServiceAceToDir
0x18000332c  mov     edi, eax
0x18000332e  test    esi, esi
0x180003330  jnz     short loc_180003346
0x180003332  call    cs:__imp_RpcRevertToSelf
0x180003339  nop     dword ptr [rax+rax+00h]
0x18000333e  test    eax, eax
0x180003340  jnz     loc_180003525
0x180003346  test    edi, edi
0x180003348  jz      short loc_180003387
0x18000334a  mov     rcx, cs:WPP_GLOBAL_Control
0x180003351  lea     r8, WPP_GLOBAL_Control
0x180003358  cmp     rcx, r8
0x18000335b  jz      short loc_180003380
0x18000335d  test    byte ptr [rcx+1Ch], 10h
0x180003361  jz      short loc_180003380
0x180003363  mov     rcx, [rcx+10h]
0x180003367  lea     r8, WPP_3f918084cf8d369c2c20a8a49a789173_Traceguids
0x18000336e  mov     edx, 1Ah
0x180003373  mov     [rsp+48h+lpData], rbx
0x180003378  mov     r9d, edi
0x18000337b  call    WPP_SF_LS
0x180003380  mov     eax, edi
0x180003382  jmp     loc_180003525
0x180003387  test    rbx, rbx
0x18000338a  jnz     short loc_180003390
0x18000338c  mov     eax, ebp
0x18000338e  jmp     short loc_1800033A4
0x180003390  or      rax, 0FFFFFFFFFFFFFFFFh
0x180003394  inc     rax
0x180003397  cmp     [rbx+rax*2], bp
0x18000339b  jnz     short loc_180003394
0x18000339d  lea     eax, ds:2[rax*2]
0x1800033a4  mov     rcx, cs:DhcpGlobalRegParam; hKey
0x1800033ab  lea     rdx, ValueName; "DhcpLogFilePath"
0x1800033b2  mov     [rsp+48h+cbData], eax; cbData
0x1800033b6  mov     r9d, 1; dwType
0x1800033bc  xor     r8d, r8d; Reserved
0x1800033bf  mov     [rsp+48h+lpData], rbx; lpData
0x1800033c4  call    cs:__imp_RegSetValueExW
0x1800033cb  nop     dword ptr [rax+rax+00h]
0x1800033d0  mov     ebx, eax
0x1800033d2  test    eax, eax
0x1800033d4  jz      short loc_18000340E
0x1800033d6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800033dd  lea     r8, WPP_GLOBAL_Control
0x1800033e4  cmp     rcx, r8
0x1800033e7  jz      short loc_180003407
0x1800033e9  test    byte ptr [rcx+1Ch], 10h
0x1800033ed  jz      short loc_180003407
0x1800033ef  mov     edx, 1Bh
0x1800033f4  mov     rcx, [rcx+10h]
0x1800033f8  lea     r8, WPP_3f918084cf8d369c2c20a8a49a789173_Traceguids
0x1800033ff  mov     r9d, ebx
0x180003402  call    WPP_SF_D
0x180003407  mov     eax, ebx
0x180003409  jmp     loc_180003525
0x18000340e  mov     rcx, cs:DhcpGlobalRegParam; hKey
0x180003415  lea     rax, [rsp+48h+Data]
0x18000341a  mov     edi, 4
0x18000341f  lea     rdx, aDhcplogdiskspa; "DhcpLogDiskSpaceCheckInterval"
0x180003426  mov     [rsp+48h+cbData], edi; cbData
0x18000342a  mov     r9d, edi; dwType
0x18000342d  xor     r8d, r8d; Reserved
0x180003430  mov     [rsp+48h+lpData], rax; lpData
0x180003435  call    cs:__imp_RegSetValueExW
0x18000343c  nop     dword ptr [rax+rax+00h]
0x180003441  mov     ebx, eax
0x180003443  test    eax, eax
0x180003445  jz      short loc_180003465
0x180003447  mov     rcx, cs:WPP_GLOBAL_Control
0x18000344e  lea     r8, WPP_GLOBAL_Control
0x180003455  cmp     rcx, r8
0x180003458  jz      short loc_180003407
0x18000345a  test    byte ptr [rcx+1Ch], 10h
0x18000345e  jz      short loc_180003407
0x180003460  lea     edx, [rdi+18h]
0x180003463  jmp     short loc_1800033F4
0x180003465  mov     rcx, cs:DhcpGlobalRegParam; hKey
0x18000346c  lea     rax, [rsp+48h+arg_18]
0x180003471  mov     [rsp+48h+cbData], edi; cbData
0x180003475  lea     rdx, aDhcplogfilesma; "DhcpLogFilesMaxSize"
0x18000347c  mov     r9d, edi; dwType
0x18000347f  mov     [rsp+48h+lpData], rax; lpData
0x180003484  xor     r8d, r8d; Reserved
0x180003487  call    cs:__imp_RegSetValueExW
0x18000348e  nop     dword ptr [rax+rax+00h]
0x180003493  mov     ebx, eax
0x180003495  test    eax, eax
0x180003497  jz      short loc_1800034C4
0x180003499  mov     rcx, cs:WPP_GLOBAL_Control
0x1800034a0  lea     r8, WPP_GLOBAL_Control
0x1800034a7  cmp     rcx, r8
0x1800034aa  jz      loc_180003407
0x1800034b0  test    byte ptr [rcx+1Ch], 10h
0x1800034b4  jz      loc_180003407
0x1800034ba  mov     edx, 1Dh
0x1800034bf  jmp     loc_1800033F4
0x1800034c4  mov     rcx, cs:DhcpGlobalRegParam; hKey
0x1800034cb  lea     rax, [rsp+48h+arg_20]
0x1800034d0  mov     [rsp+48h+cbData], edi; cbData
0x1800034d4  lea     rdx, aDhcplogminspac; "DhcpLogMinSpaceOnDisk"
0x1800034db  mov     r9d, edi; dwType
0x1800034de  mov     [rsp+48h+lpData], rax; lpData
0x1800034e3  xor     r8d, r8d; Reserved
0x1800034e6  call    cs:__imp_RegSetValueExW
0x1800034ed  nop     dword ptr [rax+rax+00h]
0x1800034f2  mov     ebx, eax
0x1800034f4  test    eax, eax
0x1800034f6  jz      short loc_180003523
0x1800034f8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800034ff  lea     r8, WPP_GLOBAL_Control
0x180003506  cmp     rcx, r8
0x180003509  jz      loc_180003407
0x18000350f  test    byte ptr [rcx+1Ch], 10h
0x180003513  jz      loc_180003407
0x180003519  mov     edx, 1Eh
0x18000351e  jmp     loc_1800033F4
0x180003523  xor     eax, eax
0x180003525  mov     rbx, [rsp+48h+arg_0]
0x18000352a  add     rsp, 30h
0x18000352e  pop     rdi
0x18000352f  pop     rsi
0x180003530  pop     rbp
0x180003531  retn
```
