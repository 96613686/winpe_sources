# CreateRpcBinding

- ea: `0x180013520`
- end: `0x1800136aa`
- name: `CreateRpcBinding`
- size: `394`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18001403c`

## callees

- `0x180013250`
- `0x180013274`
- `0x180013298`
- `0x1800132b8`
- `0x1800132e4`
- `0x180013520`

## import_xrefs

- `RPCRT4!RpcBindingSetAuthInfoExW` at `0x180013657`
- `RPCRT4!RpcBindingSetAuthInfoExW` at `0x180013657`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x1800135e2`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x1800135e2`
- `RPCRT4!RpcStringBindingComposeW` at `0x1800135a7`
- `RPCRT4!RpcStringBindingComposeW` at `0x1800135a7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013560`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013560`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180013556`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180013556`

## pseudocode

```c
__int64 __fastcall CreateRpcBinding(RPC_BINDING_HANDLE *a1)
{
  __int64 v2; // rcx
  DWORD LastError; // ebx
  __int64 v4; // rcx
  RPC_BINDING_HANDLE v5; // rcx
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+40h] [rbp-9h] BYREF
  RPC_BINDING_HANDLE v8; // [rsp+48h] [rbp-1h] BYREF
  RPC_SECURITY_QOS SecurityQOS; // [rsp+50h] [rbp+7h] BYREF
  __int128 v10; // [rsp+60h] [rbp+17h]
  __int64 *v11; // [rsp+70h] [rbp+27h]
  __int64 v12; // [rsp+78h] [rbp+2Fh]
  PSECURITY_DESCRIPTOR v13; // [rsp+80h] [rbp+37h]
  ULONG SecurityDescriptorSize; // [rsp+B8h] [rbp+6Fh] BYREF
  RPC_BINDING_HANDLE Binding; // [rsp+C0h] [rbp+77h] BYREF
  RPC_WSTR StringBinding; // [rsp+C8h] [rbp+7Fh] BYREF

  SecurityDescriptorSize = 0;
  SecurityDescriptor = 0;
  if ( ConvertStringSecurityDescriptorToSecurityDescriptorW(
         L"D:(A;;GR;;;S-1-5-80-3596911058-2952229928-1888671852-1743692427-614402820)",
         1u,
         &SecurityDescriptor,
         &SecurityDescriptorSize) )
  {
    v8 = 0;
    StringBinding = 0;
    tlx::handle_traits<unsigned short *,long (unsigned short *),&long MyRpcStringFree(unsigned short *),0>::operator()(
      v2,
      &v8);
    LastError = RpcStringBindingComposeW(0, (RPC_WSTR)L"ncalrpc", 0, 0, 0, &StringBinding);
    if ( !LastError )
    {
      v8 = 0;
      Binding = 0;
      tlx::handle_traits<void *,long (void *),&long MyRpcBindingFree(void *),0>::operator()(v4, &v8);
      LastError = RpcBindingFromStringBindingW(StringBinding, &Binding);
      if ( !LastError )
      {
        v11 = qword_1800242C8;
        v13 = SecurityDescriptor;
        v12 = 0;
        v10 = 0;
        SecurityQOS.Version = 5;
        *(_QWORD *)&SecurityQOS.Capabilities = 17;
        SecurityQOS.ImpersonationType = 3;
        LastError = RpcBindingSetAuthInfoExW(Binding, 0, 6u, 0xFFFFFFFF, 0, 0xFFFFFFFF, &SecurityQOS);
        if ( !LastError )
        {
          v5 = Binding;
          v8 = *a1;
          *a1 = Binding;
          Binding = 0;
          tlx::handle_traits<void *,long (void *),&long MyRpcBindingFree(void *),0>::operator()(v5, &v8);
          tlx::unique_any<tlx::handle_traits<void *,long (void *),&long MyRpcBindingFree(void *),0>>::~unique_any<tlx::handle_traits<void *,long (void *),&long MyRpcBindingFree(void *),0>>(&Binding);
          tlx::unique_any<tlx::handle_traits<unsigned short *,long (unsigned short *),&long MyRpcStringFree(unsigned short *),0>>::~unique_any<tlx::handle_traits<unsigned short *,long (unsigned short *),&long MyRpcStringFree(unsigned short *),0>>(&StringBinding);
          goto LABEL_9;
        }
      }
      tlx::unique_any<tlx::handle_traits<void *,long (void *),&long MyRpcBindingFree(void *),0>>::~unique_any<tlx::handle_traits<void *,long (void *),&long MyRpcBindingFree(void *),0>>(&Binding);
    }
    tlx::unique_any<tlx::handle_traits<unsigned short *,long (unsigned short *),&long MyRpcStringFree(unsigned short *),0>>::~unique_any<tlx::handle_traits<unsigned short *,long (unsigned short *),&long MyRpcStringFree(unsigned short *),0>>(&StringBinding);
  }
  else
  {
    LastError = GetLastError();
  }
LABEL_9:
  tlx::unique_any<tlx::handle_traits<void *,void * (void *),&void * LocalFree(void *),0>>::~unique_any<tlx::handle_traits<void *,void * (void *),&void * LocalFree(void *),0>>(&SecurityDescriptor);
  return LastError;
}

```

## disassembly

```asm
0x180013520  push    rbp
0x180013522  push    rbx
0x180013523  push    rdi
0x180013524  lea     rbp, [rsp-47h]
0x180013529  sub     rsp, 90h
0x180013530  mov     rdi, rcx
0x180013533  mov     [rbp+57h+SecurityDescriptorSize], 0
0x18001353a  lea     rcx, aDAGrS158035969; "D:(A;;GR;;;S-1-5-80-3596911058-29522299"...
0x180013541  mov     [rbp+57h+SecurityDescriptor], 0
0x180013549  lea     r9, [rbp+57h+SecurityDescriptorSize]; SecurityDescriptorSize
0x18001354d  mov     edx, 1; StringSDRevision
0x180013552  lea     r8, [rbp+57h+SecurityDescriptor]; SecurityDescriptor
0x180013556  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x18001355c  test    eax, eax
0x18001355e  jnz     short loc_18001356D
0x180013560  call    cs:__imp_GetLastError
0x180013566  mov     ebx, eax
0x180013568  jmp     loc_180013694
0x18001356d  lea     rdx, [rbp+57h+var_58]
0x180013571  mov     [rbp+57h+var_58], 0
0x180013579  mov     [rbp+57h+arg_18], 0
0x180013581  call    ??R?$handle_traits@PEAG$$A6AJPEAG@Z$1?MyRpcStringFree@@YAJ0@Z$0A@@tlx@@QEBAXAEBQEAG@Z; tlx::handle_traits<ushort *,long (ushort *),&MyRpcStringFree(ushort *),0>::operator()(ushort * const &)
0x180013586  lea     rax, [rbp+57h+arg_18]
0x18001358a  xor     r9d, r9d; Endpoint
0x18001358d  mov     [rsp+0A0h+StringBinding], rax; StringBinding
0x180013592  lea     rdx, ProtSeq; "ncalrpc"
0x180013599  xor     r8d, r8d; NetworkAddr
0x18001359c  mov     [rsp+0A0h+Options], 0; Options
0x1800135a5  xor     ecx, ecx; ObjUuid
0x1800135a7  call    cs:__imp_RpcStringBindingComposeW
0x1800135ad  mov     ebx, eax
0x1800135af  test    eax, eax
0x1800135b1  jz      short loc_1800135C1
0x1800135b3  lea     rcx, [rbp+57h+arg_18]
0x1800135b7  call    ??1?$unique_any@U?$handle_traits@PEAG$$A6AJPEAG@Z$1?MyRpcStringFree@@YAJ0@Z$0A@@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::handle_traits<ushort *,long (ushort *),&MyRpcStringFree(ushort *),0>>::~unique_any<tlx::handle_traits<ushort *,long (ushort *),&MyRpcStringFree(ushort *),0>>(void)
0x1800135bc  jmp     loc_180013694
0x1800135c1  lea     rdx, [rbp+57h+var_58]
0x1800135c5  mov     [rbp+57h+var_58], 0
0x1800135cd  mov     [rbp+57h+Binding], 0
0x1800135d5  call    ??R?$handle_traits@PEAX$$A6AJPEAX@Z$1?MyRpcBindingFree@@YAJ0@Z$0A@@tlx@@QEBAXAEBQEAX@Z; tlx::handle_traits<void *,long (void *),&MyRpcBindingFree(void *),0>::operator()(void * const &)
0x1800135da  mov     rcx, [rbp+57h+arg_18]; StringBinding
0x1800135de  lea     rdx, [rbp+57h+Binding]; Binding
0x1800135e2  call    cs:__imp_RpcBindingFromStringBindingW
0x1800135e8  mov     ebx, eax
0x1800135ea  test    eax, eax
0x1800135ec  jz      short loc_1800135F9
0x1800135ee  lea     rcx, [rbp+57h+Binding]
0x1800135f2  call    ??1?$unique_any@U?$handle_traits@PEAX$$A6AJPEAX@Z$1?MyRpcBindingFree@@YAJ0@Z$0A@@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::handle_traits<void *,long (void *),&MyRpcBindingFree(void *),0>>::~unique_any<tlx::handle_traits<void *,long (void *),&MyRpcBindingFree(void *),0>>(void)
0x1800135f7  jmp     short loc_1800135B3
0x1800135f9  mov     rcx, [rbp+57h+Binding]; Binding
0x1800135fd  lea     rax, qword_1800242C8
0x180013604  mov     [rbp+57h+var_30], rax
0x180013608  xor     edx, edx; ServerPrincName
0x18001360a  mov     rax, [rbp+57h+SecurityDescriptor]
0x18001360e  or      r9d, 0FFFFFFFFh; AuthnSvc
0x180013612  mov     [rbp+57h+var_20], rax
0x180013616  xorps   xmm0, xmm0
0x180013619  lea     rax, [rbp+57h+var_50]
0x18001361d  mov     [rbp+57h+var_28], 0
0x180013625  mov     [rsp+0A0h+SecurityQOS], rax; SecurityQOS
0x18001362a  lea     r8d, [rdx+6]; AuthnLevel
0x18001362e  mov     dword ptr [rsp+0A0h+StringBinding], r9d; AuthzSvc
0x180013633  mov     [rsp+0A0h+Options], 0; AuthIdentity
0x18001363c  movdqu  [rbp+57h+var_40], xmm0
0x180013641  mov     [rbp+57h+var_50.Version], 5
0x180013648  mov     qword ptr [rbp+57h+var_50.Capabilities], 11h
0x180013650  mov     [rbp+57h+var_50.ImpersonationType], 3
0x180013657  call    cs:__imp_RpcBindingSetAuthInfoExW
0x18001365d  mov     ebx, eax
0x18001365f  test    eax, eax
0x180013661  jnz     short loc_1800135EE
0x180013663  mov     rcx, [rbp+57h+Binding]
0x180013667  lea     rdx, [rbp+57h+var_58]
0x18001366b  mov     rax, [rdi]
0x18001366e  mov     [rbp+57h+var_58], rax
0x180013672  mov     [rdi], rcx
0x180013675  mov     [rbp+57h+Binding], 0
0x18001367d  call    ??R?$handle_traits@PEAX$$A6AJPEAX@Z$1?MyRpcBindingFree@@YAJ0@Z$0A@@tlx@@QEBAXAEBQEAX@Z; tlx::handle_traits<void *,long (void *),&MyRpcBindingFree(void *),0>::operator()(void * const &)
0x180013682  lea     rcx, [rbp+57h+Binding]
0x180013686  call    ??1?$unique_any@U?$handle_traits@PEAX$$A6AJPEAX@Z$1?MyRpcBindingFree@@YAJ0@Z$0A@@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::handle_traits<void *,long (void *),&MyRpcBindingFree(void *),0>>::~unique_any<tlx::handle_traits<void *,long (void *),&MyRpcBindingFree(void *),0>>(void)
0x18001368b  lea     rcx, [rbp+57h+arg_18]
0x18001368f  call    ??1?$unique_any@U?$handle_traits@PEAG$$A6AJPEAG@Z$1?MyRpcStringFree@@YAJ0@Z$0A@@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::handle_traits<ushort *,long (ushort *),&MyRpcStringFree(ushort *),0>>::~unique_any<tlx::handle_traits<ushort *,long (ushort *),&MyRpcStringFree(ushort *),0>>(void)
0x180013694  lea     rcx, [rbp+57h+SecurityDescriptor]
0x180013698  call    ??1?$unique_any@U?$handle_traits@PEAX$$A6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z$0A@@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::handle_traits<void *,void * (void *),&LocalFree(void *),0>>::~unique_any<tlx::handle_traits<void *,void * (void *),&LocalFree(void *),0>>(void)
0x18001369d  mov     eax, ebx
0x18001369f  add     rsp, 90h
0x1800136a6  pop     rdi
0x1800136a7  pop     rbx
0x1800136a8  pop     rbp
0x1800136a9  retn
```
