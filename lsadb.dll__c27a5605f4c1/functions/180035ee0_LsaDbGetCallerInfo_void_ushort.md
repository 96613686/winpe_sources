# LsaDbGetCallerInfo(void *,ushort * *)

- ea: `0x180035ee0`
- end: `0x180035fd3`
- name: `?LsaDbGetCallerInfo@@YAXPEAXPEAPEAG@Z`
- size: `243`
- prototype: `void __fastcall(void *, unsigned __int16 **)`
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000d000`
- `0x18000d210`
- `0x18000e9f0`

## callees

- `0x18002fe60`
- `0x180035ee0`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180035f92`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180035f92`
- `RPCRT4!RpcStringBindingParseW` at `0x180035f67`
- `RPCRT4!RpcStringBindingParseW` at `0x180035f67`
- `RPCRT4!RpcBindingToStringBindingW` at `0x180035f46`
- `RPCRT4!RpcBindingToStringBindingW` at `0x180035f46`
- `RPCRT4!RpcBindingServerFromClient` at `0x180035f34`
- `RPCRT4!RpcBindingServerFromClient` at `0x180035f34`
- `RPCRT4!RpcBindingFree` at `0x180035fc5`
- `RPCRT4!RpcBindingFree` at `0x180035fc5`
- `RPCRT4!RpcStringFreeW` at `0x180035fa3`
- `RPCRT4!RpcStringFreeW` at `0x180035fb4`
- `RPCRT4!RpcStringFreeW` at `0x180035fa3`
- `RPCRT4!RpcStringFreeW` at `0x180035fb4`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x180035f14`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x180035f14`
- `api-ms-win-core-processenvironment-l1-1-0!GetCommandLineW` at `0x180035f1e`
- `api-ms-win-core-processenvironment-l1-1-0!GetCommandLineW` at `0x180035f1e`

## pseudocode

```c
void __fastcall LsaDbGetCallerInfo(void *a1, unsigned __int16 **a2)
{
  unsigned __int16 *v2; // rbx
  LPWSTR CommandLineW; // rax
  unsigned __int16 *v5; // rcx
  RPC_BINDING_HANDLE ServerBinding[2]; // [rsp+30h] [rbp-10h] BYREF
  unsigned int Pid; // [rsp+60h] [rbp+20h] BYREF
  int v8; // [rsp+64h] [rbp+24h]
  unsigned __int16 *v9; // [rsp+68h] [rbp+28h] BYREF
  RPC_WSTR NetworkAddr; // [rsp+70h] [rbp+30h] BYREF
  RPC_WSTR StringBinding; // [rsp+78h] [rbp+38h] BYREF

  v8 = HIDWORD(a1);
  v2 = 0;
  Pid = 0;
  *a2 = 0;
  v9 = 0;
  ServerBinding[0] = 0;
  StringBinding = 0;
  NetworkAddr = 0;
  if ( !I_RpcBindingInqLocalClientPID(0, &Pid) )
  {
    CommandLineW = GetCommandLineW();
    if ( !CommandLineW )
      goto LABEL_11;
    v5 = CommandLineW;
    goto LABEL_8;
  }
  if ( !RpcBindingServerFromClient(0, ServerBinding)
    && !RpcBindingToStringBindingW(ServerBinding[0], &StringBinding)
    && !RpcStringBindingParseW(StringBinding, 0, 0, &NetworkAddr, 0, 0) )
  {
    v5 = NetworkAddr;
LABEL_8:
    if ( (int)LsaDbCopyString(v5, &v9) < 0 )
      v2 = v9;
    else
      *a2 = v9;
  }
LABEL_11:
  LocalFree(v2);
  if ( NetworkAddr )
    RpcStringFreeW(&NetworkAddr);
  if ( StringBinding )
    RpcStringFreeW(&StringBinding);
  if ( ServerBinding[0] )
    RpcBindingFree(ServerBinding);
}

```

## disassembly

```asm
0x180035ee0  mov     qword ptr [rsp-18h+Pid], rcx
0x180035ee5  push    rbp
0x180035ee6  push    rbx
0x180035ee7  push    rdi
0x180035ee8  mov     rbp, rsp
0x180035eeb  sub     rsp, 40h
0x180035eef  xor     ebx, ebx
0x180035ef1  mov     [rbp+Pid], 0
0x180035ef8  mov     [rdx], rbx
0x180035efb  mov     rdi, rdx
0x180035efe  lea     rdx, [rbp+Pid]; Pid
0x180035f02  mov     [rbp+arg_8], rbx
0x180035f06  xor     ecx, ecx; Binding
0x180035f08  mov     [rbp+ServerBinding], rbx
0x180035f0c  mov     [rbp+StringBinding], rbx
0x180035f10  mov     [rbp+NetworkAddr], rbx
0x180035f14  call    cs:__imp_I_RpcBindingInqLocalClientPID
0x180035f1a  test    eax, eax
0x180035f1c  jnz     short loc_180035F2E
0x180035f1e  call    cs:__imp_GetCommandLineW
0x180035f24  test    rax, rax
0x180035f27  jz      short loc_180035F8F
0x180035f29  mov     rcx, rax
0x180035f2c  jmp     short loc_180035F75
0x180035f2e  lea     rdx, [rbp+ServerBinding]; ServerBinding
0x180035f32  xor     ecx, ecx; ClientBinding
0x180035f34  call    cs:__imp_RpcBindingServerFromClient
0x180035f3a  test    eax, eax
0x180035f3c  jnz     short loc_180035F8F
0x180035f3e  mov     rcx, [rbp+ServerBinding]; Binding
0x180035f42  lea     rdx, [rbp+StringBinding]; StringBinding
0x180035f46  call    cs:__imp_RpcBindingToStringBindingW
0x180035f4c  test    eax, eax
0x180035f4e  jnz     short loc_180035F8F
0x180035f50  mov     rcx, [rbp+StringBinding]; StringBinding
0x180035f54  lea     r9, [rbp+NetworkAddr]; NetworkAddr
0x180035f58  mov     [rsp+40h+NetworkOptions], rbx; NetworkOptions
0x180035f5d  xor     r8d, r8d; Protseq
0x180035f60  xor     edx, edx; ObjUuid
0x180035f62  mov     [rsp+40h+Endpoint], rbx; Endpoint
0x180035f67  call    cs:__imp_RpcStringBindingParseW
0x180035f6d  test    eax, eax
0x180035f6f  jnz     short loc_180035F8F
0x180035f71  mov     rcx, [rbp+NetworkAddr]; unsigned __int16 *
0x180035f75  lea     rdx, [rbp+arg_8]; unsigned __int16 **
0x180035f79  call    ?LsaDbCopyString@@YAJPEAGPEAPEAG@Z; LsaDbCopyString(ushort *,ushort * *)
0x180035f7e  test    eax, eax
0x180035f80  js      short loc_180035F8B
0x180035f82  mov     rax, [rbp+arg_8]
0x180035f86  mov     [rdi], rax
0x180035f89  jmp     short loc_180035F8F
0x180035f8b  mov     rbx, [rbp+arg_8]
0x180035f8f  mov     rcx, rbx; hMem
0x180035f92  call    cs:__imp_LocalFree
0x180035f98  cmp     [rbp+NetworkAddr], 0
0x180035f9d  jz      short loc_180035FA9
0x180035f9f  lea     rcx, [rbp+NetworkAddr]; String
0x180035fa3  call    cs:__imp_RpcStringFreeW
0x180035fa9  cmp     [rbp+StringBinding], 0
0x180035fae  jz      short loc_180035FBA
0x180035fb0  lea     rcx, [rbp+StringBinding]; String
0x180035fb4  call    cs:__imp_RpcStringFreeW
0x180035fba  cmp     [rbp+ServerBinding], 0
0x180035fbf  jz      short loc_180035FCB
0x180035fc1  lea     rcx, [rbp+ServerBinding]; Binding
0x180035fc5  call    cs:__imp_RpcBindingFree
0x180035fcb  add     rsp, 40h
0x180035fcf  pop     rdi
0x180035fd0  pop     rbx
0x180035fd1  pop     rbp
0x180035fd2  retn
```
