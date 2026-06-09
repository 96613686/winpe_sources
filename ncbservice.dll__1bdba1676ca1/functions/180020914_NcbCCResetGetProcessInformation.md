# NcbCCResetGetProcessInformation

- ea: `0x180020914`
- end: `0x180020a89`
- name: `NcbCCResetGetProcessInformation`
- size: `373`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180020e80`
- `0x180021050`

## callees

- `0x180003ed0`
- `0x180004dc0`
- `0x18000a0a0`
- `0x18000e40c`
- `0x180020914`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002098c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800209d6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002098c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800209d6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800209b5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800209b5`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800209cc`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800209cc`
- `RPCRT4!I_RpcOpenClientProcess` at `0x180020953`
- `RPCRT4!I_RpcOpenClientProcess` at `0x180020953`
- `RPCRT4!RpcRevertToSelf` at `0x180020a66`
- `RPCRT4!RpcRevertToSelf` at `0x180020a66`
- `RPCRT4!RpcImpersonateClient` at `0x180020982`
- `RPCRT4!RpcImpersonateClient` at `0x180020982`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180020a60`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180020a71`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180020a60`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180020a71`

## string_xrefs

- `0x1800209a4`: `CCResetGetProcInfo: Failed to impersonate app`
- `0x1800209ea`: `CCResetGetProcInfo: Failed to open app's thread`
- `0x18002096f`: `CCResetGetProcInfo: Failed to open client handle %d \n`
- `0x180020a17`: `CCResetGetProcInfo: Failed to get user sid`

## pseudocode

```c
__int64 __fastcall NcbCCResetGetProcessInformation(void **a1, _QWORD *a2)
{
  unsigned int v4; // eax
  __int64 v5; // rdx
  __int64 v6; // rcx
  unsigned int v7; // ebx
  DWORD LastError; // eax
  __int64 v9; // rdx
  __int64 v10; // rcx
  HANDLE CurrentThread; // rax
  DWORD v12; // eax
  __int64 v13; // rdx
  __int64 v14; // rcx
  unsigned int ClientUserSid; // eax
  __int64 v16; // rdx
  __int64 v17; // rcx
  unsigned int PackageFullNameAndAppName; // eax
  __int64 v19; // rdx
  __int64 v20; // rcx
  void *TokenHandle; // [rsp+30h] [rbp+8h] BYREF
  HANDLE hObject; // [rsp+38h] [rbp+10h] BYREF

  *a1 = 0;
  *a2 = 0;
  hObject = 0;
  TokenHandle = 0;
  v4 = I_RpcOpenClientProcess(0, 0x400u, &hObject);
  v7 = v4;
  if ( v4 )
  {
    if ( (Microsoft_Windows_Network_Connection_BrokerEnableBits & 1) != 0 )
      McTemplateU0zq_EventWriteTransfer(v6, v5, L"CCResetGetProcInfo: Failed to open client handle %d \n", v4);
  }
  else
  {
    if ( RpcImpersonateClient(0) )
    {
      LastError = GetLastError();
      v7 = LastError;
      if ( (Microsoft_Windows_Network_Connection_BrokerEnableBits & 1) != 0 )
        McTemplateU0zq_EventWriteTransfer(v10, v9, L"CCResetGetProcInfo: Failed to impersonate app", LastError);
    }
    else
    {
      CurrentThread = GetCurrentThread();
      if ( OpenThreadToken(CurrentThread, 8u, 1, &TokenHandle) )
      {
        ClientUserSid = NcbUtilsGetClientUserSid(TokenHandle, a1);
        v7 = ClientUserSid;
        if ( ClientUserSid )
        {
          if ( (Microsoft_Windows_Network_Connection_BrokerEnableBits & 1) != 0 )
            McTemplateU0zq_EventWriteTransfer(v17, v16, L"CCResetGetProcInfo: Failed to get user sid", ClientUserSid);
        }
        else
        {
          PackageFullNameAndAppName = NcbUtilsGetPackageFullNameAndAppName(TokenHandle, a2, 0);
          v7 = PackageFullNameAndAppName;
          if ( PackageFullNameAndAppName )
          {
            if ( (Microsoft_Windows_Network_Connection_BrokerEnableBits & 1) != 0 )
              McTemplateU0zq_EventWriteTransfer(
                v20,
                v19,
                L"CCResetGetProcInfo: Failed to get package name",
                PackageFullNameAndAppName);
            VpnFree(*a1);
          }
        }
        CloseHandle(TokenHandle);
      }
      else
      {
        v12 = GetLastError();
        v7 = v12;
        if ( (Microsoft_Windows_Network_Connection_BrokerEnableBits & 1) != 0 )
          McTemplateU0zq_EventWriteTransfer(v14, v13, L"CCResetGetProcInfo: Failed to open app's thread", v12);
      }
      RpcRevertToSelf();
    }
    CloseHandle(hObject);
  }
  return v7;
}

```

## disassembly

```asm
0x180020914  mov     rax, rsp
0x180020917  mov     [rax+18h], rbx
0x18002091b  mov     [rax+20h], rsi
0x18002091f  push    rdi
0x180020920  sub     rsp, 20h
0x180020924  mov     qword ptr [rcx], 0
0x18002092b  lea     r8, [rax+10h]; ClientProcess
0x18002092f  mov     qword ptr [rdx], 0
0x180020936  mov     rsi, rdx
0x180020939  mov     rdi, rcx
0x18002093c  mov     qword ptr [rax+10h], 0
0x180020944  mov     edx, 400h; DesiredAccess
0x180020949  mov     qword ptr [rax+8], 0
0x180020951  xor     ecx, ecx; Binding
0x180020953  call    cs:__imp_I_RpcOpenClientProcess
0x180020959  mov     ebx, eax
0x18002095b  test    eax, eax
0x18002095d  jz      short loc_180020980
0x18002095f  test    byte ptr cs:Microsoft_Windows_Network_Connection_BrokerEnableBits, 1
0x180020966  jz      loc_180020A77
0x18002096c  mov     r9d, eax
0x18002096f  lea     r8, aCcresetgetproc_1; "CCResetGetProcInfo: Failed to open clie"...
0x180020976  call    McTemplateU0zq_EventWriteTransfer
0x18002097b  jmp     loc_180020A77
0x180020980  xor     ecx, ecx; BindingHandle
0x180020982  call    cs:__imp_RpcImpersonateClient
0x180020988  test    eax, eax
0x18002098a  jz      short loc_1800209B5
0x18002098c  call    cs:__imp_GetLastError
0x180020992  test    byte ptr cs:Microsoft_Windows_Network_Connection_BrokerEnableBits, 1
0x180020999  mov     ebx, eax
0x18002099b  jz      loc_180020A6C
0x1800209a1  mov     r9d, eax
0x1800209a4  lea     r8, aCcresetgetproc_0; "CCResetGetProcInfo: Failed to impersona"...
0x1800209ab  call    McTemplateU0zq_EventWriteTransfer
0x1800209b0  jmp     loc_180020A6C
0x1800209b5  call    cs:__imp_GetCurrentThread
0x1800209bb  mov     edx, 8; DesiredAccess
0x1800209c0  lea     r9, [rsp+28h+TokenHandle]; TokenHandle
0x1800209c5  mov     rcx, rax; ThreadHandle
0x1800209c8  lea     r8d, [rdx-7]; OpenAsSelf
0x1800209cc  call    cs:__imp_OpenThreadToken
0x1800209d2  test    eax, eax
0x1800209d4  jnz     short loc_1800209F8
0x1800209d6  call    cs:__imp_GetLastError
0x1800209dc  test    byte ptr cs:Microsoft_Windows_Network_Connection_BrokerEnableBits, 1
0x1800209e3  mov     ebx, eax
0x1800209e5  jz      short loc_180020A66
0x1800209e7  mov     r9d, eax
0x1800209ea  lea     r8, aCcresetgetproc; "CCResetGetProcInfo: Failed to open app'"...
0x1800209f1  call    McTemplateU0zq_EventWriteTransfer
0x1800209f6  jmp     short loc_180020A66
0x1800209f8  mov     rcx, [rsp+28h+TokenHandle]; TokenHandle
0x1800209fd  mov     rdx, rdi
0x180020a00  call    NcbUtilsGetClientUserSid
0x180020a05  mov     ebx, eax
0x180020a07  test    eax, eax
0x180020a09  jz      short loc_180020A25
0x180020a0b  test    byte ptr cs:Microsoft_Windows_Network_Connection_BrokerEnableBits, 1
0x180020a12  jz      short loc_180020A5B
0x180020a14  mov     r9d, eax
0x180020a17  lea     r8, aCcresetgetproc_2; "CCResetGetProcInfo: Failed to get user "...
0x180020a1e  call    McTemplateU0zq_EventWriteTransfer
0x180020a23  jmp     short loc_180020A5B
0x180020a25  mov     rcx, [rsp+28h+TokenHandle]
0x180020a2a  xor     r8d, r8d
0x180020a2d  mov     rdx, rsi
0x180020a30  call    NcbUtilsGetPackageFullNameAndAppName
0x180020a35  mov     ebx, eax
0x180020a37  test    eax, eax
0x180020a39  jz      short loc_180020A5B
0x180020a3b  test    byte ptr cs:Microsoft_Windows_Network_Connection_BrokerEnableBits, 1
0x180020a42  jz      short loc_180020A53
0x180020a44  mov     r9d, eax
0x180020a47  lea     r8, aCcresetgetproc_3; "CCResetGetProcInfo: Failed to get packa"...
0x180020a4e  call    McTemplateU0zq_EventWriteTransfer
0x180020a53  mov     rcx, [rdi]; lpMem
0x180020a56  call    VpnFree
0x180020a5b  mov     rcx, [rsp+28h+TokenHandle]; hObject
0x180020a60  call    cs:__imp_CloseHandle
0x180020a66  call    cs:__imp_RpcRevertToSelf
0x180020a6c  mov     rcx, [rsp+28h+hObject]; hObject
0x180020a71  call    cs:__imp_CloseHandle
0x180020a77  mov     rsi, [rsp+28h+arg_18]
0x180020a7c  mov     eax, ebx
0x180020a7e  mov     rbx, [rsp+28h+arg_10]
0x180020a83  add     rsp, 20h
0x180020a87  pop     rdi
0x180020a88  retn
```
