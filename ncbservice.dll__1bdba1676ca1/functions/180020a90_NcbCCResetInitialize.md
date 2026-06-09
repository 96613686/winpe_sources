# NcbCCResetInitialize

- ea: `0x180020a90`
- end: `0x180020bc5`
- name: `NcbCCResetInitialize`
- size: `309`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x18002293c`

## callees

- `0x180009740`
- `0x18000a0a0`
- `0x180015fac`
- `0x180020874`
- `0x180020a90`
- `0x180026070`
- `0x1800260b4`

## import_xrefs

- `BrokerLib!BrCreateBrokerInstance2` at `0x180020adf`
- `BrokerLib!BrCreateBrokerInstance2` at `0x180020adf`
- `BrokerLib!BrDeleteBrokerInstance` at `0x180020b86`
- `BrokerLib!BrDeleteBrokerInstance` at `0x180020b86`
- `BrokerLib!BrInitializeBrokerInstance` at `0x180020b10`
- `BrokerLib!BrInitializeBrokerInstance` at `0x180020b10`

## string_xrefs

- `0x180020af8`: `Failed to create new broker`
- `0x180020b25`: `Failed to init broker`
- `0x180020bb1`: `NcbCCResetInitialize completed successfully`

## pseudocode

```c
__int64 NcbCCResetInitialize()
{
  __int64 v0; // rdx
  __int64 v1; // rcx
  unsigned int started; // ebx
  __int64 v3; // rdx
  __int64 v4; // rcx
  __int64 v5; // rdx
  __int64 v6; // rcx
  const wchar_t *v7; // r8
  __int64 v8; // rdx
  __int64 v9; // rcx
  unsigned int v11; // [rsp+40h] [rbp+8h] BYREF
  int v12; // [rsp+48h] [rbp+10h] BYREF
  __int64 v13; // [rsp+50h] [rbp+18h] BYREF

  v12 = 20;
  v11 = 0;
  v13 = 0;
  g_NcbCCResetBroker = 0;
  started = BrCreateBrokerInstance2(&g_NcbCCResetCallbackTable, g_NcbCCResetBrokerGuid, 1, &v12, &g_NcbCCResetBroker);
  if ( started )
  {
    if ( (Microsoft_Windows_Network_Connection_BrokerEnableBits & 1) == 0 )
      return started;
    McTemplateU0z_EventWriteTransfer(v1, v0, L"Failed to create new broker");
LABEL_14:
    if ( (Microsoft_Windows_Network_Connection_BrokerEnableBits & 1) != 0 )
      McTemplateU0zq_EventWriteTransfer(v4, v3, L"NcbCCResetInitialize: failed.", started);
    return started;
  }
  started = BrInitializeBrokerInstance(g_NcbCCResetBroker);
  if ( started )
  {
    if ( (Microsoft_Windows_Network_Connection_BrokerEnableBits & 1) == 0 )
    {
LABEL_13:
      BrDeleteBrokerInstance(g_NcbCCResetBroker);
      goto LABEL_14;
    }
    v7 = L"Failed to init broker";
LABEL_7:
    McTemplateU0z_EventWriteTransfer(v6, v5, v7);
    goto LABEL_13;
  }
  NcbCCResetGetCrashParameters(&v11, &v13);
  started = InitializeAppResurrectionManager(v11, v13);
  if ( started )
  {
    if ( (Microsoft_Windows_Network_Connection_BrokerEnableBits & 1) == 0 )
      goto LABEL_13;
    v7 = L"Failed to init app resurrection table";
    goto LABEL_7;
  }
  started = StartNcbCCResetRpcServer();
  if ( started )
  {
    CleanupAppResurrectionManager(&g_NcbCCResetAppResurrectionManager);
    goto LABEL_13;
  }
  if ( (Microsoft_Windows_Network_Connection_BrokerEnableBits & 1) != 0 )
    McTemplateU0z_EventWriteTransfer(v9, v8, L"NcbCCResetInitialize completed successfully");
  return 0;
}

```

## disassembly

```asm
0x180020a90  push    rbx
0x180020a92  sub     rsp, 30h
0x180020a96  lea     rax, g_NcbCCResetBroker
0x180020a9d  mov     [rsp+38h+arg_8], 14h
0x180020aa5  lea     r9, [rsp+38h+arg_8]
0x180020aaa  mov     [rsp+38h+var_18], rax
0x180020aaf  mov     r8d, 1
0x180020ab5  mov     [rsp+38h+arg_0], 0
0x180020abd  lea     rdx, g_NcbCCResetBrokerGuid
0x180020ac4  mov     [rsp+38h+arg_10], 0
0x180020acd  lea     rcx, g_NcbCCResetCallbackTable
0x180020ad4  mov     cs:g_NcbCCResetBroker, 0
0x180020adf  call    cs:__imp_BrCreateBrokerInstance2
0x180020ae5  mov     ebx, eax
0x180020ae7  test    eax, eax
0x180020ae9  jz      short loc_180020B09
0x180020aeb  test    byte ptr cs:Microsoft_Windows_Network_Connection_BrokerEnableBits, 1
0x180020af2  jz      loc_180020BA4
0x180020af8  lea     r8, aFailedToCreate; "Failed to create new broker"
0x180020aff  call    McTemplateU0z_EventWriteTransfer
0x180020b04  jmp     loc_180020B8C
0x180020b09  mov     rcx, cs:g_NcbCCResetBroker
0x180020b10  call    cs:__imp_BrInitializeBrokerInstance
0x180020b16  mov     ebx, eax
0x180020b18  test    eax, eax
0x180020b1a  jz      short loc_180020B33
0x180020b1c  test    byte ptr cs:Microsoft_Windows_Network_Connection_BrokerEnableBits, 1
0x180020b23  jz      short loc_180020B7F
0x180020b25  lea     r8, aFailedToInitBr; "Failed to init broker"
0x180020b2c  call    McTemplateU0z_EventWriteTransfer
0x180020b31  jmp     short loc_180020B7F
0x180020b33  lea     rdx, [rsp+38h+arg_10]
0x180020b38  lea     rcx, [rsp+38h+arg_0]
0x180020b3d  call    NcbCCResetGetCrashParameters
0x180020b42  mov     rdx, [rsp+38h+arg_10]
0x180020b47  mov     ecx, [rsp+38h+arg_0]
0x180020b4b  call    InitializeAppResurrectionManager
0x180020b50  mov     ebx, eax
0x180020b52  test    eax, eax
0x180020b54  jz      short loc_180020B68
0x180020b56  test    byte ptr cs:Microsoft_Windows_Network_Connection_BrokerEnableBits, 1
0x180020b5d  jz      short loc_180020B7F
0x180020b5f  lea     r8, aFailedToInitAp; "Failed to init app resurrection table"
0x180020b66  jmp     short loc_180020B2C
0x180020b68  call    StartNcbCCResetRpcServer
0x180020b6d  mov     ebx, eax
0x180020b6f  test    eax, eax
0x180020b71  jz      short loc_180020BA8
0x180020b73  lea     rcx, g_NcbCCResetAppResurrectionManager
0x180020b7a  call    CleanupAppResurrectionManager
0x180020b7f  mov     rcx, cs:g_NcbCCResetBroker
0x180020b86  call    cs:__imp_BrDeleteBrokerInstance
0x180020b8c  test    byte ptr cs:Microsoft_Windows_Network_Connection_BrokerEnableBits, 1
0x180020b93  jz      short loc_180020BA4
0x180020b95  mov     r9d, ebx
0x180020b98  lea     r8, aNcbccresetinit; "NcbCCResetInitialize: failed."
0x180020b9f  call    McTemplateU0zq_EventWriteTransfer
0x180020ba4  mov     eax, ebx
0x180020ba6  jmp     short loc_180020BBF
0x180020ba8  test    byte ptr cs:Microsoft_Windows_Network_Connection_BrokerEnableBits, 1
0x180020baf  jz      short loc_180020BBD
0x180020bb1  lea     r8, aNcbccresetinit_0; "NcbCCResetInitialize completed successf"...
0x180020bb8  call    McTemplateU0z_EventWriteTransfer
0x180020bbd  xor     eax, eax
0x180020bbf  add     rsp, 30h
0x180020bc3  pop     rbx
0x180020bc4  retn
```
