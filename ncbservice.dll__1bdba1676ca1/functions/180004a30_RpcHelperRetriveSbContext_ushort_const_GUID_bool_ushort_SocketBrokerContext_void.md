# RpcHelperRetriveSbContext(ushort const *,_GUID *,bool *,ushort * *,SocketBrokerContext * *,void * *)

- ea: `0x180004a30`
- end: `0x180004dae`
- name: `?RpcHelperRetriveSbContext@@YAKPEBGPEAU_GUID@@PEA_NPEAPEAGPEAPEAVSocketBrokerContext@@PEAPEAX@Z`
- size: `894`
- prototype: `unsigned int __fastcall(const unsigned __int16 *, struct _GUID *, bool *, unsigned __int16 **, struct SocketBrokerContext **, void **)`
- caller_count: `6`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180018a40`
- `0x180018bd0`
- `0x180018d40`
- `0x180019470`
- `0x180029d40`
- `0x180029f20`

## callees

- `0x180003b60`
- `0x180004a30`
- `0x1800050d0`
- `0x18000a0a0`
- `0x180017fc8`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004bad`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004bad`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004bbb`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004bbb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004cdc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004d0c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004d41`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004cdc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004d0c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004d41`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180004abd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180004abd`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180004ad6`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180004ad6`
- `RPCRT4!I_RpcOpenClientProcess` at `0x180004a99`
- `RPCRT4!I_RpcOpenClientProcess` at `0x180004a99`
- `RPCRT4!RpcImpersonateClient` at `0x180004aab`
- `RPCRT4!RpcImpersonateClient` at `0x180004aab`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004bcb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004bdb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004bcb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004bdb`

## string_xrefs

- `0x180004b1c`: `NcbUtilsAllocCopyString: Overflow in caluclating string length. ULongAdd failed`
- `0x180004da2`: `NcbUtilsAllocCopyString: Overflow in caluclating string length. ULongMult failed`
- `0x180004d59`: `NcbUtilsAllocCopyString: Failed to allocate memory`
- `0x180004d7d`: `NcbUtilsAllocCopyString: StringCchCopyW failed`
- `0x180004b51`: `RpcHelperRetriveSbContext: failed to open client handle`
- `0x180004d24`: `RpcHelperRetriveSbContext: Failed to impersonate app`
- `0x180004cf4`: `RpcHelperRetriveSbContext: Failed to open app's thread`
- `0x180004b37`: `RpcHelperRetriveSbContext: NcbUtilsAllocCopyString failed`
- `0x180004c99`: `RpcSrvSBTransferOwnership: finding Socket Broker Context failed`

## pseudocode

```c
__int64 __fastcall RpcHelperRetriveSbContext(
        const unsigned __int16 *a1,
        struct _GUID *a2,
        bool *a3,
        unsigned __int16 **a4,
        struct SocketBrokerContext **a5,
        void **a6)
{
  void **v6; // r15
  unsigned int v7; // ebp
  unsigned __int16 *v8; // rsi
  struct SocketBrokerContext **v12; // r12
  unsigned int v13; // eax
  __int64 v14; // rdx
  __int64 v15; // rcx
  unsigned int v16; // edi
  HANDLE CurrentThread; // rax
  __int64 v18; // rdx
  __int64 v19; // rax
  __int64 v20; // rcx
  struct _GUID *v21; // rdx
  __int64 v22; // rcx
  unsigned __int16 *v23; // rcx
  const unsigned __int16 *v24; // r8
  HANDLE ProcessHeap; // rax
  unsigned __int64 v27; // rdi
  unsigned __int16 *v28; // rax
  __int64 v29; // rcx
  unsigned int v30; // eax
  __int64 v31; // rdx
  __int64 v32; // rcx
  unsigned int ProcessImageFileName; // eax
  __int64 v34; // rcx
  DWORD v35; // eax
  __int64 v36; // rdx
  __int64 v37; // rcx
  DWORD LastError; // eax
  __int64 v39; // rdx
  __int64 v40; // rcx
  DWORD v41; // eax
  void *ClientProcess; // [rsp+68h] [rbp+10h] BYREF
  unsigned __int16 *v43; // [rsp+70h] [rbp+18h] BYREF
  void *TokenHandle; // [rsp+78h] [rbp+20h] BYREF

  v6 = a6;
  v7 = 0;
  ClientProcess = 0;
  v8 = 0;
  *a3 = 0;
  v43 = 0;
  TokenHandle = 0;
  *a4 = 0;
  if ( v6 )
    *v6 = 0;
  v12 = a5;
  if ( a5 )
    *a5 = 0;
  v13 = I_RpcOpenClientProcess(0, 0x440u, &ClientProcess);
  v16 = v13;
  if ( v13 )
  {
    if ( (Microsoft_Windows_Network_Connection_BrokerEnableBits & 1) != 0 )
      McTemplateU0zq_EventWriteTransfer(v15, v14, L"RpcHelperRetriveSbContext: failed to open client handle", v13);
  }
  else if ( RpcImpersonateClient(0) )
  {
    LastError = GetLastError();
    v16 = LastError;
    if ( (Microsoft_Windows_Network_Connection_BrokerEnableBits & 1) != 0 )
      McTemplateU0zq_EventWriteTransfer(v40, v39, L"RpcHelperRetriveSbContext: Failed to impersonate app", LastError);
  }
  else
  {
    *a3 = 1;
    CurrentThread = GetCurrentThread();
    if ( OpenThreadToken(CurrentThread, 8u, 1, &TokenHandle) )
    {
      if ( a1 )
      {
        v19 = -1;
        do
          ++v19;
        while ( a1[v19] );
        v20 = (unsigned int)(v19 + 1);
        if ( (unsigned int)v20 < (unsigned int)v19 )
        {
          v16 = 534;
          v7 = 534;
          if ( (Microsoft_Windows_Network_Connection_BrokerEnableBits & 1) == 0 )
            goto LABEL_26;
          McTemplateU0zq_EventWriteTransfer(
            v20,
            v18,
            L"NcbUtilsAllocCopyString: Overflow in caluclating string length. ULongAdd failed",
            534);
          goto LABEL_14;
        }
        v27 = (unsigned int)v20;
        if ( (unsigned __int64)(2 * v20) > 0xFFFFFFFF )
        {
          v16 = 534;
          v7 = 534;
          if ( (Microsoft_Windows_Network_Connection_BrokerEnableBits & 1) == 0 )
            goto LABEL_26;
          McTemplateU0zq_EventWriteTransfer(
            0xFFFFFFFFLL,
            v18,
            L"NcbUtilsAllocCopyString: Overflow in caluclating string length. ULongMult failed",
            534);
          goto LABEL_14;
        }
        v28 = (unsigned __int16 *)MALLOC((unsigned int)(2 * v20));
        v8 = v28;
        if ( v28 )
        {
          if ( v27 )
          {
            if ( v27 > 0x7FFFFFFF )
            {
              v22 = 2147942487LL;
              *v28 = 0;
            }
            else
            {
              v29 = 2147483646;
              do
              {
                if ( !v29 )
                  break;
                v21 = (struct _GUID *)*a1;
                if ( !(_WORD)v21 )
                  break;
                *v28 = (unsigned __int16)v21;
                ++a1;
                ++v28;
                --v29;
                --v27;
              }
              while ( v27 );
              v23 = v28 - 1;
              if ( v27 )
                v23 = v28;
              *v23 = 0;
              v22 = 2147942522LL;
              if ( v27 )
              {
                v22 = 0;
                goto LABEL_22;
              }
            }
          }
          else
          {
            v22 = 2147942487LL;
          }
          v7 = (unsigned __int16)v22;
          if ( (Microsoft_Windows_Network_Connection_BrokerEnableBits & 1) != 0 )
            McTemplateU0zq_EventWriteTransfer(
              v22,
              v21,
              L"NcbUtilsAllocCopyString: StringCchCopyW failed",
              (unsigned __int16)v22);
        }
        else
        {
          v41 = GetLastError();
          v7 = v41;
          if ( (Microsoft_Windows_Network_Connection_BrokerEnableBits & 1) != 0 )
            McTemplateU0zq_EventWriteTransfer(v22, v21, L"NcbUtilsAllocCopyString: Failed to allocate memory", v41);
        }
LABEL_22:
        v16 = v7;
        if ( v7 )
        {
LABEL_14:
          if ( (Microsoft_Windows_Network_Connection_BrokerEnableBits & 1) != 0 )
            McTemplateU0zq_EventWriteTransfer(
              v22,
              v21,
              L"RpcHelperRetriveSbContext: NcbUtilsAllocCopyString failed",
              v7);
          goto LABEL_26;
        }
        goto LABEL_23;
      }
      ProcessImageFileName = NcbUtilsGetProcessImageFileName(TokenHandle, ClientProcess, &v43);
      v16 = ProcessImageFileName;
      if ( !ProcessImageFileName )
      {
        v8 = v43;
LABEL_23:
        *a4 = v8;
        v24 = v8;
        v8 = 0;
        if ( v12 && (v30 = SocketBrokerTable::Find(g_SocketBrokerTable, v21, v24, v12), (v16 = v30) != 0) )
        {
          if ( (Microsoft_Windows_Network_Connection_BrokerEnableBits & 1) != 0 )
            McTemplateU0zq_EventWriteTransfer(
              v32,
              v31,
              L"RpcSrvSBTransferOwnership: finding Socket Broker Context failed",
              v30);
        }
        else if ( v6 )
        {
          *v6 = ClientProcess;
          ClientProcess = 0;
        }
        goto LABEL_26;
      }
      if ( (Microsoft_Windows_Network_Connection_BrokerEnableBits & 1) != 0 )
        McTemplateU0zq_EventWriteTransfer(
          v34,
          v21,
          L"RpcHelperRetriveSbContext: NcbUtilsGetProcessImageFileName failed",
          ProcessImageFileName);
      v8 = v43;
    }
    else
    {
      v35 = GetLastError();
      v16 = v35;
      if ( (Microsoft_Windows_Network_Connection_BrokerEnableBits & 1) != 0 )
        McTemplateU0zq_EventWriteTransfer(v37, v36, L"RpcHelperRetriveSbContext: Failed to open app's thread", v35);
    }
  }
LABEL_26:
  if ( v8 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v8);
  }
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  if ( ClientProcess )
    CloseHandle(ClientProcess);
  return v16;
}

```

## disassembly

```asm
0x180004a30  mov     [rsp+arg_0], rbx
0x180004a35  mov     [rsp+ClientProcess], rdx
0x180004a3a  push    rbp
0x180004a3b  push    rsi
0x180004a3c  push    rdi
0x180004a3d  push    r12
0x180004a3f  push    r13
0x180004a41  push    r14
0x180004a43  push    r15
0x180004a45  sub     rsp, 20h
0x180004a49  mov     r15, [rsp+58h+arg_28]
0x180004a51  xor     ebp, ebp
0x180004a53  mov     [rsp+58h+ClientProcess], rbp
0x180004a58  mov     esi, ebp
0x180004a5a  mov     [r8], sil
0x180004a5d  mov     r13, r9
0x180004a60  mov     [rsp+58h+arg_10], rbp
0x180004a65  mov     r14, r8
0x180004a68  mov     [rsp+58h+TokenHandle], rbp
0x180004a6d  mov     rbx, rcx
0x180004a70  mov     [r9], rbp
0x180004a73  test    r15, r15
0x180004a76  jnz     loc_180004BF8
0x180004a7c  mov     r12, [rsp+58h+arg_20]
0x180004a84  test    r12, r12
0x180004a87  jz      short loc_180004A8D
0x180004a89  mov     [r12], rbp
0x180004a8d  lea     r8, [rsp+58h+ClientProcess]; ClientProcess
0x180004a92  mov     edx, 440h; DesiredAccess
0x180004a97  xor     ecx, ecx; Binding
0x180004a99  call    cs:__imp_I_RpcOpenClientProcess
0x180004a9f  mov     edi, eax
0x180004aa1  test    eax, eax
0x180004aa3  jnz     loc_180004B45
0x180004aa9  xor     ecx, ecx; BindingHandle
0x180004aab  call    cs:__imp_RpcImpersonateClient
0x180004ab1  test    eax, eax
0x180004ab3  jnz     loc_180004D0C
0x180004ab9  mov     byte ptr [r14], 1
0x180004abd  call    cs:__imp_GetCurrentThread
0x180004ac3  lea     r9, [rsp+58h+TokenHandle]; TokenHandle
0x180004ac8  mov     edx, 8; DesiredAccess
0x180004acd  mov     rcx, rax; ThreadHandle
0x180004ad0  mov     r8d, 1; OpenAsSelf
0x180004ad6  call    cs:__imp_OpenThreadToken
0x180004adc  test    eax, eax
0x180004ade  jz      loc_180004CDC
0x180004ae4  test    rbx, rbx
0x180004ae7  jz      loc_180004CA5
0x180004aed  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180004af4  inc     rax
0x180004af7  cmp     [rbx+rax*2], si
0x180004afb  jnz     short loc_180004AF4
0x180004afd  lea     ecx, [rax+1]
0x180004b00  cmp     ecx, eax
0x180004b02  jnb     loc_180004C00
0x180004b08  test    byte ptr cs:Microsoft_Windows_Network_Connection_BrokerEnableBits, 1
0x180004b0f  mov     edi, 216h
0x180004b14  mov     ebp, edi
0x180004b16  jz      loc_180004BA8
0x180004b1c  lea     r8, aNcbutilsallocc_3; "NcbUtilsAllocCopyString: Overflow in ca"...
0x180004b23  mov     r9d, edi
0x180004b26  call    McTemplateU0zq_EventWriteTransfer
0x180004b2b  test    byte ptr cs:Microsoft_Windows_Network_Connection_BrokerEnableBits, 1
0x180004b32  jz      short loc_180004BA8
0x180004b34  mov     r9d, ebp
0x180004b37  lea     r8, aRpchelperretri_2; "RpcHelperRetriveSbContext: NcbUtilsAllo"...
0x180004b3e  call    McTemplateU0zq_EventWriteTransfer
0x180004b43  jmp     short loc_180004BA8
0x180004b45  test    byte ptr cs:Microsoft_Windows_Network_Connection_BrokerEnableBits, 1
0x180004b4c  jz      short loc_180004BA8
0x180004b4e  mov     r9d, eax
0x180004b51  lea     r8, aRpchelperretri_0; "RpcHelperRetriveSbContext: failed to op"...
0x180004b58  jmp     short loc_180004B3E
0x180004b5a  test    rdi, rdi
0x180004b5d  lea     rcx, [rax-2]
0x180004b61  cmovnz  rcx, rax
0x180004b65  xor     eax, eax
0x180004b67  test    rdi, rdi
0x180004b6a  mov     [rcx], ax
0x180004b6d  mov     ecx, 8007007Ah
0x180004b72  cmovnz  ecx, eax
0x180004b75  jz      loc_180004D6A
0x180004b7b  mov     edi, ebp
0x180004b7d  test    ebp, ebp
0x180004b7f  jnz     short loc_180004B2B
0x180004b81  xor     ebp, ebp
0x180004b83  mov     [r13+0], rsi
0x180004b87  mov     r8, rsi; unsigned __int16 *
0x180004b8a  mov     rsi, rbp
0x180004b8d  test    r12, r12
0x180004b90  jnz     loc_180004C70
0x180004b96  test    r15, r15
0x180004b99  jz      short loc_180004BA8
0x180004b9b  mov     rax, [rsp+58h+ClientProcess]
0x180004ba0  mov     [r15], rax
0x180004ba3  mov     [rsp+58h+ClientProcess], rbp
0x180004ba8  test    rsi, rsi
0x180004bab  jz      short loc_180004BC1
0x180004bad  call    cs:__imp_GetProcessHeap
0x180004bb3  mov     r8, rsi; lpMem
0x180004bb6  xor     edx, edx; dwFlags
0x180004bb8  mov     rcx, rax; hHeap
0x180004bbb  call    cs:__imp_HeapFree
0x180004bc1  mov     rcx, [rsp+58h+TokenHandle]; hObject
0x180004bc6  test    rcx, rcx
0x180004bc9  jz      short loc_180004BD1
0x180004bcb  call    cs:__imp_CloseHandle
0x180004bd1  mov     rcx, [rsp+58h+ClientProcess]; hObject
0x180004bd6  test    rcx, rcx
0x180004bd9  jz      short loc_180004BE1
0x180004bdb  call    cs:__imp_CloseHandle
0x180004be1  mov     rbx, [rsp+58h+arg_0]
0x180004be6  mov     eax, edi
0x180004be8  add     rsp, 20h
0x180004bec  pop     r15
0x180004bee  pop     r14
0x180004bf0  pop     r13
0x180004bf2  pop     r12
0x180004bf4  pop     rdi
0x180004bf5  pop     rsi
0x180004bf6  pop     rbp
0x180004bf7  retn
0x180004bf8  mov     [r15], rbp
0x180004bfb  jmp     loc_180004A7C
0x180004c00  lea     rax, [rcx+rcx]
0x180004c04  mov     edi, ecx
0x180004c06  mov     ecx, 0FFFFFFFFh
0x180004c0b  cmp     rax, rcx
0x180004c0e  ja      loc_180004D8E
0x180004c14  mov     ecx, eax; dwBytes
0x180004c16  call    MALLOC
0x180004c1b  mov     rsi, rax
0x180004c1e  test    rax, rax
0x180004c21  jz      loc_180004D41
0x180004c27  test    rdi, rdi
0x180004c2a  jz      loc_180004D00
0x180004c30  cmp     rdi, 7FFFFFFFh
0x180004c37  ja      loc_180004D62
0x180004c3d  mov     ecx, 7FFFFFFEh
0x180004c42  test    rcx, rcx
0x180004c45  jz      loc_180004B5A
0x180004c4b  movzx   edx, word ptr [rbx]
0x180004c4e  test    dx, dx
0x180004c51  jz      loc_180004B5A
0x180004c57  mov     [rax], dx
0x180004c5a  add     rbx, 2
0x180004c5e  add     rax, 2
0x180004c62  dec     rcx
0x180004c65  sub     rdi, 1
0x180004c69  jnz     short loc_180004C42
0x180004c6b  jmp     loc_180004B5A
0x180004c70  mov     rcx, cs:?g_SocketBrokerTable@@3PEAVSocketBrokerTable@@EA; lpCriticalSection
0x180004c77  mov     r9, r12; struct SocketBrokerContext **
0x180004c7a  call    ?Find@SocketBrokerTable@@QEAAKPEAU_GUID@@PEBGPEAPEAVSocketBrokerContext@@@Z; SocketBrokerTable::Find(_GUID *,ushort const *,SocketBrokerContext * *)
0x180004c7f  mov     edi, eax
0x180004c81  test    eax, eax
0x180004c83  jz      loc_180004B96
0x180004c89  test    byte ptr cs:Microsoft_Windows_Network_Connection_BrokerEnableBits, 1
0x180004c90  jz      loc_180004BA8
0x180004c96  mov     r9d, eax
0x180004c99  lea     r8, aRpcsrvsbtransf; "RpcSrvSBTransferOwnership: finding Sock"...
0x180004ca0  jmp     loc_180004B3E
0x180004ca5  mov     rdx, [rsp+58h+ClientProcess]
0x180004caa  lea     r8, [rsp+58h+arg_10]
0x180004caf  mov     rcx, [rsp+58h+TokenHandle]
0x180004cb4  call    NcbUtilsGetProcessImageFileName
0x180004cb9  mov     edi, eax
0x180004cbb  test    eax, eax
0x180004cbd  jz      short loc_180004CD2
0x180004cbf  test    byte ptr cs:Microsoft_Windows_Network_Connection_BrokerEnableBits, 1
0x180004cc6  jnz     short loc_180004D30
0x180004cc8  mov     rsi, [rsp+58h+arg_10]
0x180004ccd  jmp     loc_180004BA8
0x180004cd2  mov     rsi, [rsp+58h+arg_10]
0x180004cd7  jmp     loc_180004B83
0x180004cdc  call    cs:__imp_GetLastError
0x180004ce2  test    byte ptr cs:Microsoft_Windows_Network_Connection_BrokerEnableBits, 1
0x180004ce9  mov     edi, eax
0x180004ceb  jz      loc_180004BA8
0x180004cf1  mov     r9d, eax
0x180004cf4  lea     r8, aRpchelperretri_3; "RpcHelperRetriveSbContext: Failed to op"...
0x180004cfb  jmp     loc_180004B3E
0x180004d00  mov     ecx, 80070057h
0x180004d05  test    rdi, rdi
0x180004d08  jnz     short loc_180004D67
0x180004d0a  jmp     short loc_180004D6A
0x180004d0c  call    cs:__imp_GetLastError
0x180004d12  test    byte ptr cs:Microsoft_Windows_Network_Connection_BrokerEnableBits, 1
0x180004d19  mov     edi, eax
0x180004d1b  jz      loc_180004BA8
0x180004d21  mov     r9d, eax
0x180004d24  lea     r8, aRpchelperretri; "RpcHelperRetriveSbContext: Failed to im"...
0x180004d2b  jmp     loc_180004B3E
0x180004d30  mov     r9d, eax
0x180004d33  lea     r8, aRpchelperretri_1; "RpcHelperRetriveSbContext: NcbUtilsGetP"...
0x180004d3a  call    McTemplateU0zq_EventWriteTransfer
0x180004d3f  jmp     short loc_180004CC8
0x180004d41  call    cs:__imp_GetLastError
0x180004d47  test    byte ptr cs:Microsoft_Windows_Network_Connection_BrokerEnableBits, 1
0x180004d4e  mov     ebp, eax
0x180004d50  jz      loc_180004B7B
0x180004d56  mov     r9d, eax
0x180004d59  lea     r8, aNcbutilsallocc_0; "NcbUtilsAllocCopyString: Failed to allo"...
0x180004d60  jmp     short loc_180004D84
0x180004d62  mov     ecx, 80070057h
0x180004d67  mov     [rax], bp
0x180004d6a  test    byte ptr cs:Microsoft_Windows_Network_Connection_BrokerEnableBits, 1
0x180004d71  movzx   ebp, cx
0x180004d74  jz      loc_180004B7B
0x180004d7a  mov     r9d, ebp
0x180004d7d  lea     r8, aNcbutilsallocc_1; "NcbUtilsAllocCopyString: StringCchCopyW"...
0x180004d84  call    McTemplateU0zq_EventWriteTransfer
0x180004d89  jmp     loc_180004B7B
0x180004d8e  test    byte ptr cs:Microsoft_Windows_Network_Connection_BrokerEnableBits, 1
0x180004d95  mov     edi, 216h
0x180004d9a  mov     ebp, edi
0x180004d9c  jz      loc_180004BA8
0x180004da2  lea     r8, aNcbutilsallocc_2; "NcbUtilsAllocCopyString: Overflow in ca"...
0x180004da9  jmp     loc_180004B23
```
