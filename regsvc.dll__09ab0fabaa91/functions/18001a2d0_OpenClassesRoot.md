# OpenClassesRoot

- ea: `0x18001a2d0`
- end: `0x18001a405`
- name: `OpenClassesRoot`
- size: `309`
- prototype: `__int64 __fastcall(__int64, unsigned int, HANDLE **)`
- caller_count: `0`
- callee_count: `7`
- tags: `authz_impersonation, loader_planting`

## callees

- `0x180007740`
- `0x180008042`
- `0x1800175ac`
- `0x18001a2d0`
- `0x18001a5b0`
- `0x18001ac84`
- `0x18001acf4`

## import_xrefs

- `ntdll!NtClose` at `0x18001a3dc`
- `ntdll!NtClose` at `0x18001a3dc`
- `RPCRT4!RpcRaiseException` at `0x18001a34f`
- `RPCRT4!RpcRaiseException` at `0x18001a357`
- `RPCRT4!RpcRaiseException` at `0x18001a36b`
- `RPCRT4!RpcRaiseException` at `0x18001a34f`
- `RPCRT4!RpcRaiseException` at `0x18001a357`
- `RPCRT4!RpcRaiseException` at `0x18001a36b`
- `RPCRT4!RpcImpersonateClient` at `0x18001a35f`
- `RPCRT4!RpcImpersonateClient` at `0x18001a35f`
- `RPCRT4!RpcRevertToSelf` at `0x18001a3bd`
- `RPCRT4!RpcRevertToSelf` at `0x18001a3bd`
- `RPCRT4!RpcServerInqCallAttributesW` at `0x18001a334`
- `RPCRT4!RpcServerInqCallAttributesW` at `0x18001a334`

## pseudocode

```c
__int64 __fastcall OpenClassesRoot(__int64 a1, unsigned int a2, HANDLE **a3)
{
  RPC_STATUS v5; // eax
  RPC_STATUS v6; // eax
  __int64 v7; // rcx
  ULONG v8; // ebx
  HANDLE *v9; // rcx
  HANDLE *v11; // [rsp+28h] [rbp-B0h] BYREF
  HANDLE Handle[2]; // [rsp+30h] [rbp-A8h] BYREF
  _DWORD RpcCallAttributes[32]; // [rsp+40h] [rbp-98h] BYREF

  v11 = 0;
  Handle[0] = 0;
  *a3 = 0;
  memset_0(RpcCallAttributes, 0, 0x78u);
  RpcCallAttributes[0] = 3;
  v5 = RpcServerInqCallAttributesW(0, RpcCallAttributes);
  if ( v5 != 1746 )
  {
    if ( v5 )
      RpcRaiseException(v5);
    if ( RpcCallAttributes[10] < 6u )
      RpcRaiseException(5);
  }
  v6 = RpcImpersonateClient(0);
  if ( v6 )
    RpcRaiseException(v6);
  v8 = OpenClassesRootInternal(v7, a2, (__int64)Handle);
  if ( !v8 )
  {
    v8 = RegSvcContextAllocate(&v11);
    if ( !v8 )
    {
      v9 = v11;
      *v11 = Handle[0];
      Handle[0] = 0;
      *a3 = v9;
      v11 = 0;
    }
  }
  RpcRevertToSelf();
  if ( v11 )
    RegSvcContextFree(v11);
  if ( Handle[0] )
    NtClose(Handle[0]);
  return v8;
}

```

## disassembly

```asm
0x18001a2d0  mov     [rsp+arg_0], rbx
0x18001a2d5  push    rdi
0x18001a2d6  sub     rsp, 0D0h
0x18001a2dd  mov     rax, cs:__security_cookie
0x18001a2e4  xor     rax, rsp
0x18001a2e7  mov     [rsp+0D8h+var_18], rax
0x18001a2ef  mov     rdi, r8
0x18001a2f2  mov     ebx, edx
0x18001a2f4  mov     [rsp+0D8h+var_B0], 0
0x18001a2fd  mov     [rsp+0D8h+var_B8], 0
0x18001a305  mov     [rsp+0D8h+Handle], 0
0x18001a30e  mov     qword ptr [r8], 0
0x18001a315  xor     edx, edx; Val
0x18001a317  lea     r8d, [rdx+78h]; Size
0x18001a31b  lea     rcx, [rsp+0D8h+RpcCallAttributes]; void *
0x18001a320  call    memset_0
0x18001a325  mov     [rsp+0D8h+RpcCallAttributes], 3
0x18001a32d  lea     rdx, [rsp+0D8h+RpcCallAttributes]; RpcCallAttributes
0x18001a332  xor     ecx, ecx; ClientBinding
0x18001a334  call    cs:__imp_RpcServerInqCallAttributesW
0x18001a33a  cmp     eax, 6D2h
0x18001a33f  jz      short loc_18001A35D
0x18001a341  test    eax, eax
0x18001a343  jnz     short loc_18001A355
0x18001a345  cmp     [rsp+0D8h+var_70], 6
0x18001a34a  jnb     short loc_18001A35D
0x18001a34c  lea     ecx, [rax+5]; exception
0x18001a34f  call    cs:__imp_RpcRaiseException
0x18001a355  mov     ecx, eax; exception
0x18001a357  call    cs:__imp_RpcRaiseException
0x18001a35d  xor     ecx, ecx; BindingHandle
0x18001a35f  call    cs:__imp_RpcImpersonateClient
0x18001a365  test    eax, eax
0x18001a367  jz      short loc_18001A371
0x18001a369  mov     ecx, eax; exception
0x18001a36b  call    cs:__imp_RpcRaiseException
0x18001a371  mov     [rsp+0D8h+var_B8], 1
0x18001a379  lea     r8, [rsp+0D8h+Handle]
0x18001a37e  mov     edx, ebx
0x18001a380  call    OpenClassesRootInternal
0x18001a385  mov     ebx, eax
0x18001a387  test    eax, eax
0x18001a389  jnz     short loc_18001A3BD
0x18001a38b  lea     rcx, [rsp+0D8h+var_B0]
0x18001a390  call    RegSvcContextAllocate
0x18001a395  mov     ebx, eax
0x18001a397  test    eax, eax
0x18001a399  jnz     short loc_18001A3BD
0x18001a39b  mov     rax, [rsp+0D8h+Handle]
0x18001a3a0  mov     rcx, [rsp+0D8h+var_B0]
0x18001a3a5  mov     [rcx], rax
0x18001a3a8  mov     [rsp+0D8h+Handle], 0
0x18001a3b1  mov     [rdi], rcx
0x18001a3b4  mov     [rsp+0D8h+var_B0], 0
0x18001a3bd  call    cs:__imp_RpcRevertToSelf
0x18001a3c3  mov     rcx, [rsp+0D8h+var_B0]
0x18001a3c8  test    rcx, rcx
0x18001a3cb  jz      short loc_18001A3D2
0x18001a3cd  call    RegSvcContextFree
0x18001a3d2  mov     rcx, [rsp+0D8h+Handle]; Handle
0x18001a3d7  test    rcx, rcx
0x18001a3da  jz      short loc_18001A3E2
0x18001a3dc  call    cs:__imp_NtClose
0x18001a3e2  mov     eax, ebx
0x18001a3e4  mov     rcx, [rsp+0D8h+var_18]
0x18001a3ec  xor     rcx, rsp; StackCookie
0x18001a3ef  call    __security_check_cookie
0x18001a3f4  mov     rbx, [rsp+0D8h+arg_0]
0x18001a3fc  add     rsp, 0D0h
0x18001a403  pop     rdi
0x18001a404  retn
0x18001e73c  push    rbp
0x18001e73e  sub     rsp, 20h
0x18001e742  mov     rbp, rdx
0x18001e745  cmp     dword ptr [rbp+20h], 0
0x18001e749  jz      short loc_18001E752
0x18001e74b  call    cs:__imp_RpcRevertToSelf
0x18001e751  nop
0x18001e752  mov     rcx, [rbp+28h]
0x18001e756  test    rcx, rcx
0x18001e759  jz      short loc_18001E761
0x18001e75b  call    RegSvcContextFree
0x18001e760  nop
0x18001e761  mov     rcx, [rbp+30h]; Handle
0x18001e765  test    rcx, rcx
0x18001e768  jz      short loc_18001E771
0x18001e76a  call    cs:__imp_NtClose
0x18001e770  nop
0x18001e771  add     rsp, 20h
0x18001e775  pop     rbp
0x18001e776  retn
```
