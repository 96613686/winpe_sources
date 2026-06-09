# KipEnableRpcInterface

- ea: `0x180009674`
- end: `0x1800099d0`
- name: `KipEnableRpcInterface`
- size: `860`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x18000bee0`

## callees

- `0x180003cf0`
- `0x180009674`

## import_xrefs

- `RPCRT4!RpcServerInqBindings` at `0x18000972e`
- `RPCRT4!RpcServerInqBindings` at `0x18000972e`
- `RPCRT4!RpcBindingVectorFree` at `0x18000999b`
- `RPCRT4!RpcBindingVectorFree` at `0x18000999b`
- `RPCRT4!RpcEpRegisterW` at `0x180009841`
- `RPCRT4!RpcEpRegisterW` at `0x180009876`
- `RPCRT4!RpcEpRegisterW` at `0x1800098ab`
- `RPCRT4!RpcEpRegisterW` at `0x180009841`
- `RPCRT4!RpcEpRegisterW` at `0x180009876`
- `RPCRT4!RpcEpRegisterW` at `0x1800098ab`
- `RPCRT4!RpcEpUnregister` at `0x180009923`
- `RPCRT4!RpcEpUnregister` at `0x180009957`
- `RPCRT4!RpcEpUnregister` at `0x18000998a`
- `RPCRT4!RpcEpUnregister` at `0x180009923`
- `RPCRT4!RpcEpUnregister` at `0x180009957`
- `RPCRT4!RpcEpUnregister` at `0x18000998a`
- `RPCRT4!RpcServerUnregisterIfEx` at `0x180009907`
- `RPCRT4!RpcServerUnregisterIfEx` at `0x18000993b`
- `RPCRT4!RpcServerUnregisterIfEx` at `0x18000996f`
- `RPCRT4!RpcServerUnregisterIfEx` at `0x180009907`
- `RPCRT4!RpcServerUnregisterIfEx` at `0x18000993b`
- `RPCRT4!RpcServerUnregisterIfEx` at `0x18000996f`
- `RPCRT4!RpcServerRegisterIf3` at `0x180009774`
- `RPCRT4!RpcServerRegisterIf3` at `0x1800097c0`
- `RPCRT4!RpcServerRegisterIf3` at `0x18000980c`
- `RPCRT4!RpcServerRegisterIf3` at `0x180009774`
- `RPCRT4!RpcServerRegisterIf3` at `0x1800097c0`
- `RPCRT4!RpcServerRegisterIf3` at `0x18000980c`
- `RPCRT4!RpcServerUseProtseqW` at `0x180009710`
- `RPCRT4!RpcServerUseProtseqW` at `0x180009710`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800096cb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800096cb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800098e8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800098e8`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1800096c1`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1800096c1`
- `ntdll!RtlEnterCriticalSection` at `0x1800096aa`
- `ntdll!RtlEnterCriticalSection` at `0x1800096aa`
- `ntdll!RtlLeaveCriticalSection` at `0x1800099b0`
- `ntdll!RtlLeaveCriticalSection` at `0x1800099b0`

## string_xrefs

- `0x180009862`: `Ngc Pop Key Service`
- `0x180009897`: `Ngc Pop Key Service`
- `0x1800096e6`: `onecore\ds\security\cryptoapi\ncrypt\iso\service\keyiso.cxx`

## pseudocode

```c
__int64 KipEnableRpcInterface()
{
  int v0; // esi
  int v1; // r14d
  int v2; // r12d
  int v3; // r13d
  int v4; // r15d
  int v5; // edi
  signed int LastError; // eax
  unsigned int v7; // ebx
  __int64 v8; // r9
  RPC_STATUS v9; // ebx
  RPC_STATUS v10; // ebx
  int v11; // ebx
  int v12; // ebx
  int v13; // ebx
  RPC_STATUS v14; // ebx
  RPC_STATUS v15; // ebx
  RPC_STATUS v16; // ebx
  RPC_BINDING_VECTOR *BindingVector; // [rsp+80h] [rbp+40h] BYREF
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+88h] [rbp+48h] BYREF

  v0 = 0;
  BindingVector = 0;
  v1 = 0;
  SecurityDescriptor = 0;
  v2 = 0;
  v3 = 0;
  v4 = 0;
  v5 = 0;
  RtlEnterCriticalSection(&g_ResLock);
  if ( !ConvertStringSecurityDescriptorToSecurityDescriptorW(
          L"D:(A;;GRGWGX;;;WD)(A;;GRGWGX;;;RC)(A;;GA;;;BA)(A;;GA;;;OW)(A;;GR;;;AC)(A;;GR;;;S-1-15-3-1024-3203351429-212044"
           "3784-2872670797-1918958302-2829055647-4275794519-765664414-2751773334)",
          1u,
          &SecurityDescriptor,
          0) )
  {
    LastError = GetLastError();
    v7 = LastError;
    if ( LastError > 0 )
      v7 = (unsigned __int16)LastError | 0x80070000;
    v8 = 615;
    goto LABEL_5;
  }
  v9 = RpcServerUseProtseqW((RPC_WSTR)L"ncalrpc", 0xAu, SecurityDescriptor);
  if ( v9 )
  {
    v7 = v9 | 0x80010000;
    v8 = 631;
LABEL_5:
    DebugTraceError(v7, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\service\\keyiso.cxx", v8);
    goto LABEL_23;
  }
  v10 = RpcServerInqBindings(&BindingVector);
  if ( v10 )
  {
    v7 = v10 | 0x80010000;
    v8 = 644;
    goto LABEL_5;
  }
  v11 = RpcServerRegisterIf3(qword_18001A060, 0, 0, 41, 1234, 0, 0, SecurityDescriptor);
  if ( v11 )
  {
    v7 = v11 | 0x80010000;
    v8 = 671;
    goto LABEL_5;
  }
  v0 = 1;
  v12 = RpcServerRegisterIf3(qword_18001A000, 0, 0, 41, 1234, 0, 0, SecurityDescriptor);
  if ( v12 )
  {
    v7 = v12 | 0x80010000;
    v8 = 695;
    goto LABEL_5;
  }
  v2 = 1;
  v13 = RpcServerRegisterIf3(qword_18001A0C0, 0, 0, 41, 1234, 0, 0, SecurityDescriptor);
  if ( v13 )
  {
    v7 = v13 | 0x80010000;
    v8 = 719;
    goto LABEL_5;
  }
  v4 = 1;
  v14 = RpcEpRegisterW(qword_18001A060, BindingVector, 0, (RPC_WSTR)L"KeyIso");
  if ( v14 )
  {
    v7 = v14 | 0x80010000;
    v8 = 738;
    goto LABEL_5;
  }
  v1 = 1;
  v15 = RpcEpRegisterW(qword_18001A000, BindingVector, 0, (RPC_WSTR)L"Ngc Pop Key Service");
  if ( v15 )
  {
    v7 = v15 | 0x80010000;
    v8 = 752;
    goto LABEL_5;
  }
  v3 = 1;
  v16 = RpcEpRegisterW(qword_18001A0C0, BindingVector, 0, (RPC_WSTR)L"Ngc Pop Key Service");
  if ( v16 )
  {
    v7 = v16 | 0x80010000;
    v8 = 766;
    goto LABEL_5;
  }
  v5 = 1;
  ::BindingVector = BindingVector;
  v7 = 0;
  BindingVector = 0;
LABEL_23:
  if ( SecurityDescriptor )
    LocalFree(SecurityDescriptor);
  if ( v7 )
  {
    if ( v0 )
      RpcServerUnregisterIfEx(qword_18001A060, 0, 1);
    if ( v1 )
      RpcEpUnregister(qword_18001A060, ::BindingVector, 0);
    if ( v2 )
      RpcServerUnregisterIfEx(qword_18001A000, 0, 1);
    if ( v3 )
      RpcEpUnregister(qword_18001A000, ::BindingVector, 0);
    if ( v4 )
      RpcServerUnregisterIfEx(qword_18001A0C0, 0, 1);
    if ( v5 )
      RpcEpUnregister(qword_18001A0C0, ::BindingVector, 0);
    if ( BindingVector )
    {
      RpcBindingVectorFree(&BindingVector);
      BindingVector = 0;
    }
  }
  RtlLeaveCriticalSection(&g_ResLock);
  return v7;
}

```

## disassembly

```asm
0x180009674  mov     [rsp-38h+arg_10], rbx
0x180009679  push    rbp
0x18000967a  push    rsi
0x18000967b  push    rdi
0x18000967c  push    r12
0x18000967e  push    r13
0x180009680  push    r14
0x180009682  push    r15
0x180009684  mov     rbp, rsp
0x180009687  sub     rsp, 40h
0x18000968b  xor     esi, esi
0x18000968d  lea     rcx, g_ResLock; CriticalSection
0x180009694  mov     [rbp+BindingVector], rsi
0x180009698  xor     r14d, r14d
0x18000969b  mov     [rbp+SecurityDescriptor], rsi
0x18000969f  xor     r12d, r12d
0x1800096a2  xor     r13d, r13d
0x1800096a5  xor     r15d, r15d
0x1800096a8  xor     edi, edi
0x1800096aa  call    cs:__imp_RtlEnterCriticalSection
0x1800096b0  xor     r9d, r9d; SecurityDescriptorSize
0x1800096b3  lea     r8, [rbp+SecurityDescriptor]; SecurityDescriptor
0x1800096b7  lea     edx, [rsi+1]; StringSDRevision
0x1800096ba  lea     rcx, StringSecurityDescriptor; "D:(A;;GRGWGX;;;WD)(A;;GRGWGX;;;RC)(A;;G"...
0x1800096c1  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x1800096c7  test    eax, eax
0x1800096c9  jnz     short loc_180009700
0x1800096cb  call    cs:__imp_GetLastError
0x1800096d1  mov     ebx, eax
0x1800096d3  test    eax, eax
0x1800096d5  jle     short loc_1800096E0
0x1800096d7  movzx   ebx, ax
0x1800096da  or      ebx, 80070000h
0x1800096e0  mov     r9d, 267h
0x1800096e6  lea     r8, aOnecoreDsSecur_3; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800096ed  mov     ecx, ebx
0x1800096ef  lea     rdx, aStatus; "Status"
0x1800096f6  call    DebugTraceError
0x1800096fb  jmp     loc_1800098DF
0x180009700  mov     r8, [rbp+SecurityDescriptor]; SecurityDescriptor
0x180009704  lea     rcx, Protseq; "ncalrpc"
0x18000970b  mov     edx, 0Ah; MaxCalls
0x180009710  call    cs:__imp_RpcServerUseProtseqW
0x180009716  mov     ebx, eax
0x180009718  test    eax, eax
0x18000971a  jz      short loc_18000972A
0x18000971c  or      ebx, 80010000h
0x180009722  mov     r9d, 277h
0x180009728  jmp     short loc_1800096E6
0x18000972a  lea     rcx, [rbp+BindingVector]; BindingVector
0x18000972e  call    cs:__imp_RpcServerInqBindings
0x180009734  mov     ebx, eax
0x180009736  test    eax, eax
0x180009738  jz      short loc_180009748
0x18000973a  or      ebx, 80010000h
0x180009740  mov     r9d, 284h
0x180009746  jmp     short loc_1800096E6
0x180009748  mov     rax, [rbp+SecurityDescriptor]
0x18000974c  lea     rcx, qword_18001A060
0x180009753  mov     [rsp+40h+var_8], rax
0x180009758  mov     r9d, 29h ; ')'
0x18000975e  mov     [rsp+40h+var_10], rsi
0x180009763  xor     r8d, r8d
0x180009766  mov     [rsp+40h+var_18], esi
0x18000976a  xor     edx, edx
0x18000976c  mov     [rsp+40h+var_20], 4D2h
0x180009774  call    cs:__imp_RpcServerRegisterIf3
0x18000977a  mov     ebx, eax
0x18000977c  test    eax, eax
0x18000977e  jz      short loc_180009791
0x180009780  or      ebx, 80010000h
0x180009786  mov     r9d, 29Fh
0x18000978c  jmp     loc_1800096E6
0x180009791  mov     rax, [rbp+SecurityDescriptor]
0x180009795  lea     rcx, qword_18001A000
0x18000979c  mov     [rsp+40h+var_8], rax
0x1800097a1  mov     esi, 1
0x1800097a6  mov     [rsp+40h+var_10], rdi
0x1800097ab  xor     r8d, r8d
0x1800097ae  mov     [rsp+40h+var_18], edi
0x1800097b2  xor     edx, edx
0x1800097b4  mov     [rsp+40h+var_20], 4D2h
0x1800097bc  lea     r9d, [rsi+28h]
0x1800097c0  call    cs:__imp_RpcServerRegisterIf3
0x1800097c6  mov     ebx, eax
0x1800097c8  test    eax, eax
0x1800097ca  jz      short loc_1800097DD
0x1800097cc  or      ebx, 80010000h
0x1800097d2  mov     r9d, 2B7h
0x1800097d8  jmp     loc_1800096E6
0x1800097dd  mov     rax, [rbp+SecurityDescriptor]
0x1800097e1  lea     rcx, qword_18001A0C0
0x1800097e8  mov     [rsp+40h+var_8], rax
0x1800097ed  mov     r9d, 29h ; ')'
0x1800097f3  mov     [rsp+40h+var_10], rdi
0x1800097f8  xor     r8d, r8d
0x1800097fb  mov     [rsp+40h+var_18], edi
0x1800097ff  xor     edx, edx
0x180009801  mov     [rsp+40h+var_20], 4D2h
0x180009809  mov     r12d, esi
0x18000980c  call    cs:__imp_RpcServerRegisterIf3
0x180009812  mov     ebx, eax
0x180009814  test    eax, eax
0x180009816  jz      short loc_180009829
0x180009818  or      ebx, 80010000h
0x18000981e  mov     r9d, 2CFh
0x180009824  jmp     loc_1800096E6
0x180009829  mov     rdx, [rbp+BindingVector]; BindingVector
0x18000982d  lea     r9, ServiceName; "KeyIso"
0x180009834  xor     r8d, r8d; UuidVector
0x180009837  lea     rcx, qword_18001A060; IfSpec
0x18000983e  mov     r15d, esi
0x180009841  call    cs:__imp_RpcEpRegisterW
0x180009847  mov     ebx, eax
0x180009849  test    eax, eax
0x18000984b  jz      short loc_18000985E
0x18000984d  or      ebx, 80010000h
0x180009853  mov     r9d, 2E2h
0x180009859  jmp     loc_1800096E6
0x18000985e  mov     rdx, [rbp+BindingVector]; BindingVector
0x180009862  lea     r9, aNgcPopKeyServi; "Ngc Pop Key Service"
0x180009869  xor     r8d, r8d; UuidVector
0x18000986c  lea     rcx, qword_18001A000; IfSpec
0x180009873  mov     r14d, esi
0x180009876  call    cs:__imp_RpcEpRegisterW
0x18000987c  mov     ebx, eax
0x18000987e  test    eax, eax
0x180009880  jz      short loc_180009893
0x180009882  or      ebx, 80010000h
0x180009888  mov     r9d, 2F0h
0x18000988e  jmp     loc_1800096E6
0x180009893  mov     rdx, [rbp+BindingVector]; BindingVector
0x180009897  lea     r9, aNgcPopKeyServi; "Ngc Pop Key Service"
0x18000989e  xor     r8d, r8d; UuidVector
0x1800098a1  lea     rcx, qword_18001A0C0; IfSpec
0x1800098a8  mov     r13d, esi
0x1800098ab  call    cs:__imp_RpcEpRegisterW
0x1800098b1  mov     ebx, eax
0x1800098b3  test    eax, eax
0x1800098b5  jz      short loc_1800098C8
0x1800098b7  or      ebx, 80010000h
0x1800098bd  mov     r9d, 2FEh
0x1800098c3  jmp     loc_1800096E6
0x1800098c8  mov     rax, [rbp+BindingVector]
0x1800098cc  mov     edi, esi
0x1800098ce  mov     cs:BindingVector, rax
0x1800098d5  xor     ebx, ebx
0x1800098d7  mov     [rbp+BindingVector], 0
0x1800098df  mov     rcx, [rbp+SecurityDescriptor]; hMem
0x1800098e3  test    rcx, rcx
0x1800098e6  jz      short loc_1800098EE
0x1800098e8  call    cs:__imp_LocalFree
0x1800098ee  test    ebx, ebx
0x1800098f0  jz      loc_1800099A9
0x1800098f6  test    esi, esi
0x1800098f8  jz      short loc_18000990D
0x1800098fa  xor     edx, edx; MgrTypeUuid
0x1800098fc  lea     rcx, qword_18001A060; IfSpec
0x180009903  lea     r8d, [rdx+1]; RundownContextHandles
0x180009907  call    cs:__imp_RpcServerUnregisterIfEx
0x18000990d  test    r14d, r14d
0x180009910  jz      short loc_180009929
0x180009912  mov     rdx, cs:BindingVector; BindingVector
0x180009919  lea     rcx, qword_18001A060; IfSpec
0x180009920  xor     r8d, r8d; UuidVector
0x180009923  call    cs:__imp_RpcEpUnregister
0x180009929  test    r12d, r12d
0x18000992c  jz      short loc_180009941
0x18000992e  xor     edx, edx; MgrTypeUuid
0x180009930  lea     rcx, qword_18001A000; IfSpec
0x180009937  lea     r8d, [rdx+1]; RundownContextHandles
0x18000993b  call    cs:__imp_RpcServerUnregisterIfEx
0x180009941  test    r13d, r13d
0x180009944  jz      short loc_18000995D
0x180009946  mov     rdx, cs:BindingVector; BindingVector
0x18000994d  lea     rcx, qword_18001A000; IfSpec
0x180009954  xor     r8d, r8d; UuidVector
0x180009957  call    cs:__imp_RpcEpUnregister
0x18000995d  test    r15d, r15d
0x180009960  jz      short loc_180009975
0x180009962  xor     edx, edx; MgrTypeUuid
0x180009964  lea     rcx, qword_18001A0C0; IfSpec
0x18000996b  lea     r8d, [rdx+1]; RundownContextHandles
0x18000996f  call    cs:__imp_RpcServerUnregisterIfEx
0x180009975  test    edi, edi
0x180009977  jz      short loc_180009990
0x180009979  mov     rdx, cs:BindingVector; BindingVector
0x180009980  lea     rcx, qword_18001A0C0; IfSpec
0x180009987  xor     r8d, r8d; UuidVector
0x18000998a  call    cs:__imp_RpcEpUnregister
0x180009990  cmp     [rbp+BindingVector], 0
0x180009995  jz      short loc_1800099A9
0x180009997  lea     rcx, [rbp+BindingVector]; BindingVector
0x18000999b  call    cs:__imp_RpcBindingVectorFree
0x1800099a1  mov     [rbp+BindingVector], 0
0x1800099a9  lea     rcx, g_ResLock; CriticalSection
0x1800099b0  call    cs:__imp_RtlLeaveCriticalSection
0x1800099b6  mov     eax, ebx
0x1800099b8  mov     rbx, [rsp+40h+arg_10]
0x1800099c0  add     rsp, 40h
0x1800099c4  pop     r15
0x1800099c6  pop     r14
0x1800099c8  pop     r13
0x1800099ca  pop     r12
0x1800099cc  pop     rdi
0x1800099cd  pop     rsi
0x1800099ce  pop     rbp
0x1800099cf  retn
```
