# AuditLogSetParams

- ea: `0x1800032a4`
- end: `0x18000353f`
- name: `AuditLogSetParams`
- size: `667`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, service_task`

## callers

- `0x18002fc50`

## callees

- `0x180002854`
- `0x1800032a4`
- `0x180005844`
- `0x1800623a4`
- `0x18009b7a0`

## import_xrefs

- `ADVAPI32!RegSetValueExW` at `0x1800033d0`
- `ADVAPI32!RegSetValueExW` at `0x180003441`
- `ADVAPI32!RegSetValueExW` at `0x180003493`
- `ADVAPI32!RegSetValueExW` at `0x1800034f2`
- `ADVAPI32!RegSetValueExW` at `0x1800033d0`
- `ADVAPI32!RegSetValueExW` at `0x180003441`
- `ADVAPI32!RegSetValueExW` at `0x180003493`
- `ADVAPI32!RegSetValueExW` at `0x1800034f2`
- `RPCRT4!RpcImpersonateClient` at `0x1800032bf`
- `RPCRT4!RpcImpersonateClient` at `0x1800032bf`
- `RPCRT4!RpcRevertToSelf` at `0x180003313`
- `RPCRT4!RpcRevertToSelf` at `0x18000333e`
- `RPCRT4!RpcRevertToSelf` at `0x180003313`
- `RPCRT4!RpcRevertToSelf` at `0x18000333e`
- `KERNEL32!GetLastError` at `0x18000331f`
- `KERNEL32!GetLastError` at `0x18000331f`

## string_xrefs

- `0x1800033b7`: `DhcpLogFilePath`

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
0x1800032a4  mov     [rsp+arg_0], rbx
0x1800032a9  mov     [rsp+arg_18], r9d
0x1800032ae  mov     [rsp+Data], r8d
0x1800032b3  push    rbp
0x1800032b4  push    rsi
0x1800032b5  push    rdi
0x1800032b6  sub     rsp, 30h
0x1800032ba  xor     ecx, ecx; BindingHandle
0x1800032bc  mov     rbx, rdx
0x1800032bf  call    cs:__imp_RpcImpersonateClient
0x1800032c6  nop     dword ptr [rax+rax+00h]
0x1800032cb  mov     rcx, rbx; lpPathName
0x1800032ce  mov     esi, eax
0x1800032d0  call    CreateDirectoryPathW
0x1800032d5  xor     ebp, ebp
0x1800032d7  test    eax, eax
0x1800032d9  jnz     short loc_180003330
0x1800032db  mov     rcx, cs:WPP_GLOBAL_Control
0x1800032e2  lea     r8, WPP_GLOBAL_Control
0x1800032e9  cmp     rcx, r8
0x1800032ec  jz      short loc_18000330F
0x1800032ee  test    byte ptr [rcx+1Ch], 10h
0x1800032f2  jz      short loc_18000330F
0x1800032f4  mov     rcx, [rcx+10h]
0x1800032f8  lea     edx, [rbp+19h]
0x1800032fb  xor     r9d, r9d
0x1800032fe  mov     [rsp+48h+lpData], rbx
0x180003303  lea     r8, WPP_3f918084cf8d369c2c20a8a49a789173_Traceguids
0x18000330a  call    WPP_SF_LS
0x18000330f  test    esi, esi
0x180003311  jnz     short loc_18000331F
0x180003313  call    cs:__imp_RpcRevertToSelf
0x18000331a  nop     dword ptr [rax+rax+00h]
0x18000331f  call    cs:__imp_GetLastError
0x180003326  nop     dword ptr [rax+rax+00h]
0x18000332b  jmp     loc_180003531
0x180003330  mov     rcx, rbx; pObjectName
0x180003333  call    DhcpAddServiceAceToDir
0x180003338  mov     edi, eax
0x18000333a  test    esi, esi
0x18000333c  jnz     short loc_180003352
0x18000333e  call    cs:__imp_RpcRevertToSelf
0x180003345  nop     dword ptr [rax+rax+00h]
0x18000334a  test    eax, eax
0x18000334c  jnz     loc_180003531
0x180003352  test    edi, edi
0x180003354  jz      short loc_180003393
0x180003356  mov     rcx, cs:WPP_GLOBAL_Control
0x18000335d  lea     r8, WPP_GLOBAL_Control
0x180003364  cmp     rcx, r8
0x180003367  jz      short loc_18000338C
0x180003369  test    byte ptr [rcx+1Ch], 10h
0x18000336d  jz      short loc_18000338C
0x18000336f  mov     rcx, [rcx+10h]
0x180003373  lea     r8, WPP_3f918084cf8d369c2c20a8a49a789173_Traceguids
0x18000337a  mov     edx, 1Ah
0x18000337f  mov     [rsp+48h+lpData], rbx
0x180003384  mov     r9d, edi
0x180003387  call    WPP_SF_LS
0x18000338c  mov     eax, edi
0x18000338e  jmp     loc_180003531
0x180003393  test    rbx, rbx
0x180003396  jnz     short loc_18000339C
0x180003398  mov     eax, ebp
0x18000339a  jmp     short loc_1800033B0
0x18000339c  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800033a0  inc     rax
0x1800033a3  cmp     [rbx+rax*2], bp
0x1800033a7  jnz     short loc_1800033A0
0x1800033a9  lea     eax, ds:2[rax*2]
0x1800033b0  mov     rcx, cs:DhcpGlobalRegParam; hKey
0x1800033b7  lea     rdx, ValueName; "DhcpLogFilePath"
0x1800033be  mov     [rsp+48h+cbData], eax; cbData
0x1800033c2  mov     r9d, 1; dwType
0x1800033c8  xor     r8d, r8d; Reserved
0x1800033cb  mov     [rsp+48h+lpData], rbx; lpData
0x1800033d0  call    cs:__imp_RegSetValueExW
0x1800033d7  nop     dword ptr [rax+rax+00h]
0x1800033dc  mov     ebx, eax
0x1800033de  test    eax, eax
0x1800033e0  jz      short loc_18000341A
0x1800033e2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800033e9  lea     r8, WPP_GLOBAL_Control
0x1800033f0  cmp     rcx, r8
0x1800033f3  jz      short loc_180003413
0x1800033f5  test    byte ptr [rcx+1Ch], 10h
0x1800033f9  jz      short loc_180003413
0x1800033fb  mov     edx, 1Bh
0x180003400  mov     rcx, [rcx+10h]
0x180003404  lea     r8, WPP_3f918084cf8d369c2c20a8a49a789173_Traceguids
0x18000340b  mov     r9d, ebx
0x18000340e  call    WPP_SF_D
0x180003413  mov     eax, ebx
0x180003415  jmp     loc_180003531
0x18000341a  mov     rcx, cs:DhcpGlobalRegParam; hKey
0x180003421  lea     rax, [rsp+48h+Data]
0x180003426  mov     edi, 4
0x18000342b  lea     rdx, aDhcplogdiskspa; "DhcpLogDiskSpaceCheckInterval"
0x180003432  mov     [rsp+48h+cbData], edi; cbData
0x180003436  mov     r9d, edi; dwType
0x180003439  xor     r8d, r8d; Reserved
0x18000343c  mov     [rsp+48h+lpData], rax; lpData
0x180003441  call    cs:__imp_RegSetValueExW
0x180003448  nop     dword ptr [rax+rax+00h]
0x18000344d  mov     ebx, eax
0x18000344f  test    eax, eax
0x180003451  jz      short loc_180003471
0x180003453  mov     rcx, cs:WPP_GLOBAL_Control
0x18000345a  lea     r8, WPP_GLOBAL_Control
0x180003461  cmp     rcx, r8
0x180003464  jz      short loc_180003413
0x180003466  test    byte ptr [rcx+1Ch], 10h
0x18000346a  jz      short loc_180003413
0x18000346c  lea     edx, [rdi+18h]
0x18000346f  jmp     short loc_180003400
0x180003471  mov     rcx, cs:DhcpGlobalRegParam; hKey
0x180003478  lea     rax, [rsp+48h+arg_18]
0x18000347d  mov     [rsp+48h+cbData], edi; cbData
0x180003481  lea     rdx, aDhcplogfilesma; "DhcpLogFilesMaxSize"
0x180003488  mov     r9d, edi; dwType
0x18000348b  mov     [rsp+48h+lpData], rax; lpData
0x180003490  xor     r8d, r8d; Reserved
0x180003493  call    cs:__imp_RegSetValueExW
0x18000349a  nop     dword ptr [rax+rax+00h]
0x18000349f  mov     ebx, eax
0x1800034a1  test    eax, eax
0x1800034a3  jz      short loc_1800034D0
0x1800034a5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800034ac  lea     r8, WPP_GLOBAL_Control
0x1800034b3  cmp     rcx, r8
0x1800034b6  jz      loc_180003413
0x1800034bc  test    byte ptr [rcx+1Ch], 10h
0x1800034c0  jz      loc_180003413
0x1800034c6  mov     edx, 1Dh
0x1800034cb  jmp     loc_180003400
0x1800034d0  mov     rcx, cs:DhcpGlobalRegParam; hKey
0x1800034d7  lea     rax, [rsp+48h+arg_20]
0x1800034dc  mov     [rsp+48h+cbData], edi; cbData
0x1800034e0  lea     rdx, aDhcplogminspac; "DhcpLogMinSpaceOnDisk"
0x1800034e7  mov     r9d, edi; dwType
0x1800034ea  mov     [rsp+48h+lpData], rax; lpData
0x1800034ef  xor     r8d, r8d; Reserved
0x1800034f2  call    cs:__imp_RegSetValueExW
0x1800034f9  nop     dword ptr [rax+rax+00h]
0x1800034fe  mov     ebx, eax
0x180003500  test    eax, eax
0x180003502  jz      short loc_18000352F
0x180003504  mov     rcx, cs:WPP_GLOBAL_Control
0x18000350b  lea     r8, WPP_GLOBAL_Control
0x180003512  cmp     rcx, r8
0x180003515  jz      loc_180003413
0x18000351b  test    byte ptr [rcx+1Ch], 10h
0x18000351f  jz      loc_180003413
0x180003525  mov     edx, 1Eh
0x18000352a  jmp     loc_180003400
0x18000352f  xor     eax, eax
0x180003531  mov     rbx, [rsp+48h+arg_0]
0x180003536  add     rsp, 30h
0x18000353a  pop     rdi
0x18000353b  pop     rsi
0x18000353c  pop     rbp
0x18000353d  retn
```
