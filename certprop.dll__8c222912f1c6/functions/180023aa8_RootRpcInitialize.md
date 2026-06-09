# RootRpcInitialize

- ea: `0x180023aa8`
- end: `0x180023c09`
- name: `RootRpcInitialize`
- size: `353`
- prototype: `__int64 __fastcall(struct _SERVICE_THREAD_SECURITY_INFO **)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180017d90`

## callees

- `0x1800234b0`
- `0x180023a1c`
- `0x180023aa8`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180023ba0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180023ba0`
- `RPCRT4!RpcEpRegisterA` at `0x180023b69`
- `RPCRT4!RpcEpRegisterA` at `0x180023b69`
- `RPCRT4!RpcServerRegisterIf3` at `0x180023b33`
- `RPCRT4!RpcServerRegisterIf3` at `0x180023b33`
- `RPCRT4!RpcServerUnregisterIf` at `0x180023bd5`
- `RPCRT4!RpcServerUnregisterIf` at `0x180023bd5`
- `RPCRT4!RpcServerUseProtseqW` at `0x180023af1`
- `RPCRT4!RpcServerUseProtseqW` at `0x180023af1`
- `RPCRT4!RpcBindingVectorFree` at `0x180023bec`
- `RPCRT4!RpcBindingVectorFree` at `0x180023bec`
- `RPCRT4!RpcServerListen` at `0x180023b83`
- `RPCRT4!RpcServerListen` at `0x180023b83`
- `RPCRT4!RpcEpUnregister` at `0x180023bbf`
- `RPCRT4!RpcEpUnregister` at `0x180023bbf`
- `RPCRT4!RpcServerInqBindings` at `0x180023b49`
- `RPCRT4!RpcServerInqBindings` at `0x180023b49`

## pseudocode

```c
__int64 __fastcall RootRpcInitialize(struct _SERVICE_THREAD_SECURITY_INFO **a1)
{
  int v1; // esi
  int v2; // edi
  unsigned int v3; // ebx
  void *SecurityDescriptor; // [rsp+70h] [rbp+8h] BYREF

  v1 = 0;
  v2 = 0;
  SecurityDescriptor = 0;
  v3 = InitializeServiceThreadSecurityInfo(a1);
  if ( !v3 )
  {
    v3 = CalRpcCreateAppContainerRpcSD(&SecurityDescriptor);
    if ( !v3 )
    {
      v3 = RpcServerUseProtseqW((RPC_WSTR)L"ncalrpc", 0xAu, SecurityDescriptor);
      if ( !v3 )
      {
        v3 = RpcServerRegisterIf3(qword_180027200, 0, 0, 9, 1234, 0, RootRpcSecurityCallback, SecurityDescriptor);
        if ( !v3 )
        {
          v2 = 1;
          v3 = RpcServerInqBindings(&BindingVector);
          if ( !v3 )
          {
            v3 = RpcEpRegisterA(qword_180027200, BindingVector, 0, 0);
            if ( !v3 )
            {
              v1 = 1;
              v3 = RpcServerListen(1u, 0x4D2u, 1u);
              if ( v3 == 1713 )
                v3 = 0;
            }
          }
        }
      }
    }
  }
  if ( SecurityDescriptor )
    LocalFree(SecurityDescriptor);
  if ( v3 )
  {
    if ( v1 )
      RpcEpUnregister(qword_180027200, BindingVector, 0);
    if ( v2 )
      RpcServerUnregisterIf(qword_180027200, 0, 1u);
    if ( BindingVector )
    {
      RpcBindingVectorFree(&BindingVector);
      BindingVector = 0;
    }
  }
  return v3;
}

```

## disassembly

```asm
0x180023aa8  push    rbx
0x180023aaa  push    rsi
0x180023aab  push    rdi
0x180023aac  push    r15
0x180023aae  sub     rsp, 48h
0x180023ab2  xor     esi, esi
0x180023ab4  xor     edi, edi
0x180023ab6  mov     [rsp+68h+SecurityDescriptor], rsi
0x180023abb  call    ?InitializeServiceThreadSecurityInfo@@YAKPEAPEAU_SERVICE_THREAD_SECURITY_INFO@@@Z; InitializeServiceThreadSecurityInfo(_SERVICE_THREAD_SECURITY_INFO * *)
0x180023ac0  lea     r15d, [rdi+1]
0x180023ac4  mov     ebx, eax
0x180023ac6  test    eax, eax
0x180023ac8  jnz     loc_180023B96
0x180023ace  lea     rcx, [rsp+68h+SecurityDescriptor]; SecurityDescriptor
0x180023ad3  call    CalRpcCreateAppContainerRpcSD
0x180023ad8  mov     ebx, eax
0x180023ada  test    eax, eax
0x180023adc  jnz     loc_180023B96
0x180023ae2  mov     r8, [rsp+68h+SecurityDescriptor]; SecurityDescriptor
0x180023ae7  lea     edx, [rdi+0Ah]; MaxCalls
0x180023aea  lea     rcx, Protseq; "ncalrpc"
0x180023af1  call    cs:__imp_RpcServerUseProtseqW
0x180023af7  mov     ebx, eax
0x180023af9  test    eax, eax
0x180023afb  jnz     loc_180023B96
0x180023b01  mov     rax, [rsp+68h+SecurityDescriptor]
0x180023b06  lea     r9d, [rdi+9]
0x180023b0a  mov     [rsp+68h+var_30], rax
0x180023b0f  lea     rcx, qword_180027200
0x180023b16  lea     rax, ?RootRpcSecurityCallback@@YAJPEAX0@Z; RootRpcSecurityCallback(void *,void *)
0x180023b1d  xor     r8d, r8d
0x180023b20  mov     [rsp+68h+var_38], rax
0x180023b25  xor     edx, edx
0x180023b27  mov     [rsp+68h+var_40], esi
0x180023b2b  mov     [rsp+68h+var_48], 4D2h
0x180023b33  call    cs:__imp_RpcServerRegisterIf3
0x180023b39  mov     ebx, eax
0x180023b3b  test    eax, eax
0x180023b3d  jnz     short loc_180023B96
0x180023b3f  lea     rcx, BindingVector; BindingVector
0x180023b46  mov     edi, r15d
0x180023b49  call    cs:__imp_RpcServerInqBindings
0x180023b4f  mov     ebx, eax
0x180023b51  test    eax, eax
0x180023b53  jnz     short loc_180023B96
0x180023b55  mov     rdx, cs:BindingVector; BindingVector
0x180023b5c  lea     rcx, qword_180027200; IfSpec
0x180023b63  xor     r9d, r9d; Annotation
0x180023b66  xor     r8d, r8d; UuidVector
0x180023b69  call    cs:__imp_RpcEpRegisterA
0x180023b6f  mov     ebx, eax
0x180023b71  test    eax, eax
0x180023b73  jnz     short loc_180023B96
0x180023b75  mov     r8d, r15d; DontWait
0x180023b78  mov     edx, 4D2h; MaxCalls
0x180023b7d  mov     ecx, r15d; MinimumCallThreads
0x180023b80  mov     esi, r15d
0x180023b83  call    cs:__imp_RpcServerListen
0x180023b89  mov     ebx, eax
0x180023b8b  xor     eax, eax
0x180023b8d  cmp     ebx, 6B1h
0x180023b93  cmovz   ebx, eax
0x180023b96  mov     rcx, [rsp+68h+SecurityDescriptor]; hMem
0x180023b9b  test    rcx, rcx
0x180023b9e  jz      short loc_180023BA6
0x180023ba0  call    cs:__imp_LocalFree
0x180023ba6  test    ebx, ebx
0x180023ba8  jz      short loc_180023BFD
0x180023baa  test    esi, esi
0x180023bac  jz      short loc_180023BC5
0x180023bae  mov     rdx, cs:BindingVector; BindingVector
0x180023bb5  lea     rcx, qword_180027200; IfSpec
0x180023bbc  xor     r8d, r8d; UuidVector
0x180023bbf  call    cs:__imp_RpcEpUnregister
0x180023bc5  test    edi, edi
0x180023bc7  jz      short loc_180023BDB
0x180023bc9  mov     r8d, r15d; WaitForCallsToComplete
0x180023bcc  lea     rcx, qword_180027200; IfSpec
0x180023bd3  xor     edx, edx; MgrTypeUuid
0x180023bd5  call    cs:__imp_RpcServerUnregisterIf
0x180023bdb  cmp     cs:BindingVector, 0
0x180023be3  jz      short loc_180023BFD
0x180023be5  lea     rcx, BindingVector; BindingVector
0x180023bec  call    cs:__imp_RpcBindingVectorFree
0x180023bf2  mov     cs:BindingVector, 0
0x180023bfd  mov     eax, ebx
0x180023bff  add     rsp, 48h
0x180023c03  pop     r15
0x180023c05  pop     rdi
0x180023c06  pop     rsi
0x180023c07  pop     rbx
0x180023c08  retn
```
