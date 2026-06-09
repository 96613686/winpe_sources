# NcbCCResetCapabilityCheck

- ea: `0x1800206e0`
- end: `0x18002081a`
- name: `NcbCCResetCapabilityCheck`
- size: `314`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x18000a0a0`
- `0x1800206e0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020781`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020781`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180020760`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180020760`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180020777`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180020777`
- `RPCRT4!I_RpcOpenClientProcess` at `0x180020704`
- `RPCRT4!I_RpcOpenClientProcess` at `0x180020704`
- `RPCRT4!RpcRevertToSelf` at `0x180020801`
- `RPCRT4!RpcRevertToSelf` at `0x180020801`
- `RPCRT4!RpcImpersonateClient` at `0x180020733`
- `RPCRT4!RpcImpersonateClient` at `0x180020733`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800207fb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002080c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800207fb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002080c`
- `BrokerLib!BrCheckCallerCapabilities` at `0x1800207d2`
- `BrokerLib!BrCheckCallerCapabilities` at `0x1800207d2`
- `BrokerLib!BrCheckCallerIsAppContainer` at `0x1800207a8`
- `BrokerLib!BrCheckCallerIsAppContainer` at `0x1800207a8`

## string_xrefs

- `0x180020720`: `CCResetCapabilityCheck: Failed to open client handle %d \n`
- `0x18002074f`: `CCResetGetProcInfo: Failed to impersonate app`
- `0x180020795`: `CCResetGetProcInfo: Failed to open app's thread`

## pseudocode

```c
__int64 NcbCCResetCapabilityCheck()
{
  unsigned int v0; // eax
  __int64 v1; // rdx
  __int64 v2; // rcx
  unsigned int v3; // ebx
  unsigned int v4; // eax
  __int64 v5; // rdx
  __int64 v6; // rcx
  HANDLE CurrentThread; // rax
  DWORD LastError; // eax
  __int64 v9; // rdx
  __int64 v10; // rcx
  unsigned int v11; // eax
  __int64 v12; // rdx
  __int64 v13; // rcx
  unsigned int v14; // eax
  __int64 v15; // rdx
  __int64 v16; // rcx
  void *TokenHandle; // [rsp+40h] [rbp+18h] BYREF
  void *ClientProcess; // [rsp+48h] [rbp+20h] BYREF

  ClientProcess = 0;
  TokenHandle = 0;
  v0 = I_RpcOpenClientProcess(0, 0x400u, &ClientProcess);
  v3 = v0;
  if ( v0 )
  {
    if ( (Microsoft_Windows_Network_Connection_BrokerEnableBits & 1) != 0 )
      McTemplateU0zq_EventWriteTransfer(v2, v1, L"CCResetCapabilityCheck: Failed to open client handle %d \n", v0);
  }
  else
  {
    v4 = RpcImpersonateClient(0);
    v3 = v4;
    if ( v4 )
    {
      if ( (Microsoft_Windows_Network_Connection_BrokerEnableBits & 1) != 0 )
        McTemplateU0zq_EventWriteTransfer(v6, v5, L"CCResetGetProcInfo: Failed to impersonate app", v4);
    }
    else
    {
      CurrentThread = GetCurrentThread();
      if ( OpenThreadToken(CurrentThread, 8u, 1, &TokenHandle) )
      {
        v11 = BrCheckCallerIsAppContainer(TokenHandle);
        v3 = v11;
        if ( v11 )
        {
          if ( (Microsoft_Windows_Network_Connection_BrokerEnableBits & 1) != 0 )
            McTemplateU0zq_EventWriteTransfer(v13, v12, L"CCResetCapabilityCheck: App is not app container", v11);
        }
        else
        {
          v14 = BrCheckCallerCapabilities(TokenHandle, 4);
          v3 = v14;
          if ( v14 && (Microsoft_Windows_Network_Connection_BrokerEnableBits & 1) != 0 )
            McTemplateU0zq_EventWriteTransfer(
              v16,
              v15,
              L"CCResetCapabilityCheck: App does not have BTC_SYSTEM_EVENT capability",
              v14);
        }
        CloseHandle(TokenHandle);
      }
      else
      {
        LastError = GetLastError();
        v3 = LastError;
        if ( (Microsoft_Windows_Network_Connection_BrokerEnableBits & 1) != 0 )
          McTemplateU0zq_EventWriteTransfer(v10, v9, L"CCResetGetProcInfo: Failed to open app's thread", LastError);
      }
      RpcRevertToSelf();
    }
    CloseHandle(ClientProcess);
  }
  return v3;
}

```

## disassembly

```asm
0x1800206e0  push    rbx
0x1800206e2  sub     rsp, 20h
0x1800206e6  lea     r8, [rsp+28h+ClientProcess]; ClientProcess
0x1800206eb  mov     [rsp+28h+ClientProcess], 0
0x1800206f4  mov     edx, 400h; DesiredAccess
0x1800206f9  mov     [rsp+28h+TokenHandle], 0
0x180020702  xor     ecx, ecx; Binding
0x180020704  call    cs:__imp_I_RpcOpenClientProcess
0x18002070a  mov     ebx, eax
0x18002070c  test    eax, eax
0x18002070e  jz      short loc_180020731
0x180020710  test    byte ptr cs:Microsoft_Windows_Network_Connection_BrokerEnableBits, 1
0x180020717  jz      loc_180020812
0x18002071d  mov     r9d, eax
0x180020720  lea     r8, aCcresetcapabil; "CCResetCapabilityCheck: Failed to open "...
0x180020727  call    McTemplateU0zq_EventWriteTransfer
0x18002072c  jmp     loc_180020812
0x180020731  xor     ecx, ecx; BindingHandle
0x180020733  call    cs:__imp_RpcImpersonateClient
0x180020739  mov     ebx, eax
0x18002073b  test    eax, eax
0x18002073d  jz      short loc_180020760
0x18002073f  test    byte ptr cs:Microsoft_Windows_Network_Connection_BrokerEnableBits, 1
0x180020746  jz      loc_180020807
0x18002074c  mov     r9d, eax
0x18002074f  lea     r8, aCcresetgetproc_0; "CCResetGetProcInfo: Failed to impersona"...
0x180020756  call    McTemplateU0zq_EventWriteTransfer
0x18002075b  jmp     loc_180020807
0x180020760  call    cs:__imp_GetCurrentThread
0x180020766  mov     edx, 8; DesiredAccess
0x18002076b  lea     r9, [rsp+28h+TokenHandle]; TokenHandle
0x180020770  mov     rcx, rax; ThreadHandle
0x180020773  lea     r8d, [rdx-7]; OpenAsSelf
0x180020777  call    cs:__imp_OpenThreadToken
0x18002077d  test    eax, eax
0x18002077f  jnz     short loc_1800207A3
0x180020781  call    cs:__imp_GetLastError
0x180020787  test    byte ptr cs:Microsoft_Windows_Network_Connection_BrokerEnableBits, 1
0x18002078e  mov     ebx, eax
0x180020790  jz      short loc_180020801
0x180020792  mov     r9d, eax
0x180020795  lea     r8, aCcresetgetproc; "CCResetGetProcInfo: Failed to open app'"...
0x18002079c  call    McTemplateU0zq_EventWriteTransfer
0x1800207a1  jmp     short loc_180020801
0x1800207a3  mov     rcx, [rsp+28h+TokenHandle]
0x1800207a8  call    cs:__imp_BrCheckCallerIsAppContainer
0x1800207ae  mov     ebx, eax
0x1800207b0  test    eax, eax
0x1800207b2  jz      short loc_1800207C6
0x1800207b4  test    byte ptr cs:Microsoft_Windows_Network_Connection_BrokerEnableBits, 1
0x1800207bb  jz      short loc_1800207F6
0x1800207bd  lea     r8, aCcresetcapabil_0; "CCResetCapabilityCheck: App is not app "...
0x1800207c4  jmp     short loc_1800207EE
0x1800207c6  mov     rcx, [rsp+28h+TokenHandle]
0x1800207cb  xor     r8d, r8d
0x1800207ce  lea     edx, [r8+4]
0x1800207d2  call    cs:__imp_BrCheckCallerCapabilities
0x1800207d8  mov     ebx, eax
0x1800207da  test    eax, eax
0x1800207dc  jz      short loc_1800207F6
0x1800207de  test    byte ptr cs:Microsoft_Windows_Network_Connection_BrokerEnableBits, 1
0x1800207e5  jz      short loc_1800207F6
0x1800207e7  lea     r8, aCcresetcapabil_1; "CCResetCapabilityCheck: App does not ha"...
0x1800207ee  mov     r9d, eax
0x1800207f1  call    McTemplateU0zq_EventWriteTransfer
0x1800207f6  mov     rcx, [rsp+28h+TokenHandle]; hObject
0x1800207fb  call    cs:__imp_CloseHandle
0x180020801  call    cs:__imp_RpcRevertToSelf
0x180020807  mov     rcx, [rsp+28h+ClientProcess]; hObject
0x18002080c  call    cs:__imp_CloseHandle
0x180020812  mov     eax, ebx
0x180020814  add     rsp, 20h
0x180020818  pop     rbx
0x180020819  retn
```
