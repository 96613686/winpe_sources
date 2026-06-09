# OpenPerformanceData

- ea: `0x18001a8d0`
- end: `0x18001a9dc`
- name: `OpenPerformanceData`
- size: `268`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation`

## callees

- `0x180007740`
- `0x180008042`
- `0x1800180b4`
- `0x18001a8d0`
- `0x18001ac84`
- `0x18001acf4`

## import_xrefs

- `RPCRT4!RpcRaiseException` at `0x18001a944`
- `RPCRT4!RpcRaiseException` at `0x18001a94c`
- `RPCRT4!RpcRaiseException` at `0x18001a960`
- `RPCRT4!RpcRaiseException` at `0x18001a944`
- `RPCRT4!RpcRaiseException` at `0x18001a94c`
- `RPCRT4!RpcRaiseException` at `0x18001a960`
- `RPCRT4!RpcImpersonateClient` at `0x18001a954`
- `RPCRT4!RpcImpersonateClient` at `0x18001a954`
- `RPCRT4!RpcRevertToSelf` at `0x18001a9a4`
- `RPCRT4!RpcRevertToSelf` at `0x18001e7cf`
- `RPCRT4!RpcRevertToSelf` at `0x18001a9a4`
- `RPCRT4!RpcRevertToSelf` at `0x18001e7cf`
- `RPCRT4!RpcServerInqCallAttributesW` at `0x18001a929`
- `RPCRT4!RpcServerInqCallAttributesW` at `0x18001a929`

## pseudocode

```c
__int64 __fastcall OpenPerformanceData(__int64 a1, __int64 a2, _QWORD *a3)
{
  RPC_STATUS v4; // eax
  RPC_STATUS v5; // eax
  unsigned int v6; // ebx
  _QWORD *v7; // rax
  _QWORD *v9; // [rsp+28h] [rbp-A0h] BYREF
  _DWORD RpcCallAttributes[32]; // [rsp+30h] [rbp-98h] BYREF

  v9 = 0;
  *a3 = 0;
  memset_0(RpcCallAttributes, 0, 0x78u);
  RpcCallAttributes[0] = 3;
  v4 = RpcServerInqCallAttributesW(0, RpcCallAttributes);
  if ( v4 != 1746 )
  {
    if ( v4 )
      RpcRaiseException(v4);
    if ( RpcCallAttributes[10] < 6u )
      RpcRaiseException(5);
  }
  v5 = RpcImpersonateClient(0);
  if ( v5 )
    RpcRaiseException(v5);
  if ( RegSecCheckRemotePerfAccess() )
  {
    v6 = RegSvcContextAllocate(&v9);
    if ( !v6 )
    {
      v7 = v9;
      *v9 = -2147483644;
      *a3 = v7;
      v9 = 0;
    }
  }
  else
  {
    v6 = 5;
  }
  RpcRevertToSelf();
  if ( v9 )
    RegSvcContextFree(v9);
  return v6;
}

```

## disassembly

```asm
0x18001a8d0  mov     [rsp+arg_0], rbx
0x18001a8d5  push    rdi
0x18001a8d6  sub     rsp, 0C0h
0x18001a8dd  mov     rax, cs:__security_cookie
0x18001a8e4  xor     rax, rsp
0x18001a8e7  mov     [rsp+0C8h+var_18], rax
0x18001a8ef  mov     rdi, r8
0x18001a8f2  mov     [rsp+0C8h+var_A0], 0
0x18001a8fb  mov     [rsp+0C8h+var_A8], 0
0x18001a903  mov     qword ptr [r8], 0
0x18001a90a  xor     edx, edx; Val
0x18001a90c  lea     r8d, [rdx+78h]; Size
0x18001a910  lea     rcx, [rsp+0C8h+RpcCallAttributes]; void *
0x18001a915  call    memset_0
0x18001a91a  mov     [rsp+0C8h+RpcCallAttributes], 3
0x18001a922  lea     rdx, [rsp+0C8h+RpcCallAttributes]; RpcCallAttributes
0x18001a927  xor     ecx, ecx; ClientBinding
0x18001a929  call    cs:__imp_RpcServerInqCallAttributesW
0x18001a92f  cmp     eax, 6D2h
0x18001a934  jz      short loc_18001A952
0x18001a936  test    eax, eax
0x18001a938  jnz     short loc_18001A94A
0x18001a93a  cmp     [rsp+0C8h+var_70], 6
0x18001a93f  jnb     short loc_18001A952
0x18001a941  lea     ecx, [rax+5]; exception
0x18001a944  call    cs:__imp_RpcRaiseException
0x18001a94a  mov     ecx, eax; exception
0x18001a94c  call    cs:__imp_RpcRaiseException
0x18001a952  xor     ecx, ecx; BindingHandle
0x18001a954  call    cs:__imp_RpcImpersonateClient
0x18001a95a  test    eax, eax
0x18001a95c  jz      short loc_18001A966
0x18001a95e  mov     ecx, eax; exception
0x18001a960  call    cs:__imp_RpcRaiseException
0x18001a966  mov     [rsp+0C8h+var_A8], 1
0x18001a96e  call    RegSecCheckRemotePerfAccess
0x18001a973  test    eax, eax
0x18001a975  jnz     short loc_18001A97C
0x18001a977  lea     ebx, [rax+5]
0x18001a97a  jmp     short loc_18001A9A4
0x18001a97c  lea     rcx, [rsp+0C8h+var_A0]
0x18001a981  call    RegSvcContextAllocate
0x18001a986  mov     ebx, eax
0x18001a988  test    eax, eax
0x18001a98a  jnz     short loc_18001A9A4
0x18001a98c  mov     rax, [rsp+0C8h+var_A0]
0x18001a991  mov     qword ptr [rax], 0FFFFFFFF80000004h
0x18001a998  mov     [rdi], rax
0x18001a99b  mov     [rsp+0C8h+var_A0], 0
0x18001a9a4  call    cs:__imp_RpcRevertToSelf
0x18001a9aa  mov     rcx, [rsp+0C8h+var_A0]
0x18001a9af  test    rcx, rcx
0x18001a9b2  jz      short loc_18001A9B9
0x18001a9b4  call    RegSvcContextFree
0x18001a9b9  mov     eax, ebx
0x18001a9bb  mov     rcx, [rsp+0C8h+var_18]
0x18001a9c3  xor     rcx, rsp; StackCookie
0x18001a9c6  call    __security_check_cookie
0x18001a9cb  mov     rbx, [rsp+0C8h+arg_0]
0x18001a9d3  add     rsp, 0C0h
0x18001a9da  pop     rdi
0x18001a9db  retn
0x18001e7c0  push    rbp
0x18001e7c2  sub     rsp, 20h
0x18001e7c6  mov     rbp, rdx
0x18001e7c9  cmp     dword ptr [rbp+20h], 0
0x18001e7cd  jz      short loc_18001E7D6
0x18001e7cf  call    cs:__imp_RpcRevertToSelf
0x18001e7d5  nop
0x18001e7d6  mov     rcx, [rbp+28h]
0x18001e7da  test    rcx, rcx
0x18001e7dd  jz      short loc_18001E7E5
0x18001e7df  call    RegSvcContextFree
0x18001e7e4  nop
0x18001e7e5  add     rsp, 20h
0x18001e7e9  pop     rbp
0x18001e7ea  retn
```
