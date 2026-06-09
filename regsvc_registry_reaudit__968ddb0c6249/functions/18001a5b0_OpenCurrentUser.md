# OpenCurrentUser

- ea: `0x18001a5b0`
- end: `0x18001a6ee`
- name: `OpenCurrentUser`
- size: `318`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting`

## callees

- `0x180007740`
- `0x180008042`
- `0x18001a5b0`
- `0x18001ac84`
- `0x18001acf4`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x18001a668`
- `ntdll!RtlNtStatusToDosError` at `0x18001a668`
- `ntdll!NtClose` at `0x18001a6c5`
- `ntdll!NtClose` at `0x18001e76a`
- `ntdll!NtClose` at `0x18001a6c5`
- `ntdll!NtClose` at `0x18001e76a`
- `ntdll!RtlOpenCurrentUser` at `0x18001a660`
- `ntdll!RtlOpenCurrentUser` at `0x18001a660`
- `RPCRT4!RpcRaiseException` at `0x18001a62f`
- `RPCRT4!RpcRaiseException` at `0x18001a637`
- `RPCRT4!RpcRaiseException` at `0x18001a64b`
- `RPCRT4!RpcRaiseException` at `0x18001a62f`
- `RPCRT4!RpcRaiseException` at `0x18001a637`
- `RPCRT4!RpcRaiseException` at `0x18001a64b`
- `RPCRT4!RpcImpersonateClient` at `0x18001a63f`
- `RPCRT4!RpcImpersonateClient` at `0x18001a63f`
- `RPCRT4!RpcRevertToSelf` at `0x18001a6a6`
- `RPCRT4!RpcRevertToSelf` at `0x18001e74b`
- `RPCRT4!RpcRevertToSelf` at `0x18001a6a6`
- `RPCRT4!RpcRevertToSelf` at `0x18001e74b`
- `RPCRT4!RpcServerInqCallAttributesW` at `0x18001a614`
- `RPCRT4!RpcServerInqCallAttributesW` at `0x18001a614`

## pseudocode

```c
__int64 __fastcall OpenCurrentUser(__int64 a1, ACCESS_MASK a2, void ***a3)
{
  RPC_STATUS v5; // eax
  RPC_STATUS v6; // eax
  NTSTATUS v7; // eax
  ULONG v8; // ebx
  void **v9; // rcx
  void **v11; // [rsp+28h] [rbp-B0h] BYREF
  void *KeyHandle; // [rsp+30h] [rbp-A8h] BYREF
  _DWORD RpcCallAttributes[32]; // [rsp+40h] [rbp-98h] BYREF

  KeyHandle = 0;
  v11 = 0;
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
  v7 = RtlOpenCurrentUser(a2, &KeyHandle);
  v8 = RtlNtStatusToDosError(v7);
  if ( !v8 )
  {
    v8 = RegSvcContextAllocate(&v11);
    if ( !v8 )
    {
      v9 = v11;
      *v11 = KeyHandle;
      KeyHandle = 0;
      *a3 = v9;
      v11 = 0;
    }
  }
  RpcRevertToSelf();
  if ( v11 )
    RegSvcContextFree(v11);
  if ( KeyHandle )
    NtClose(KeyHandle);
  return v8;
}

```

## disassembly

```asm
0x18001a5b0  mov     [rsp+arg_0], rbx
0x18001a5b5  push    rdi
0x18001a5b6  sub     rsp, 0D0h
0x18001a5bd  mov     rax, cs:__security_cookie
0x18001a5c4  xor     rax, rsp
0x18001a5c7  mov     [rsp+0D8h+var_18], rax
0x18001a5cf  mov     rdi, r8
0x18001a5d2  mov     ebx, edx
0x18001a5d4  mov     [rsp+0D8h+KeyHandle], 0
0x18001a5dd  mov     [rsp+0D8h+var_B0], 0
0x18001a5e6  mov     [rsp+0D8h+var_B8], 0
0x18001a5ee  mov     qword ptr [r8], 0
0x18001a5f5  xor     edx, edx; Val
0x18001a5f7  lea     r8d, [rdx+78h]; Size
0x18001a5fb  lea     rcx, [rsp+0D8h+RpcCallAttributes]; void *
0x18001a600  call    memset_0
0x18001a605  mov     [rsp+0D8h+RpcCallAttributes], 3
0x18001a60d  lea     rdx, [rsp+0D8h+RpcCallAttributes]; RpcCallAttributes
0x18001a612  xor     ecx, ecx; ClientBinding
0x18001a614  call    cs:__imp_RpcServerInqCallAttributesW
0x18001a61a  cmp     eax, 6D2h
0x18001a61f  jz      short loc_18001A63D
0x18001a621  test    eax, eax
0x18001a623  jnz     short loc_18001A635
0x18001a625  cmp     [rsp+0D8h+var_70], 6
0x18001a62a  jnb     short loc_18001A63D
0x18001a62c  lea     ecx, [rax+5]; exception
0x18001a62f  call    cs:__imp_RpcRaiseException
0x18001a635  mov     ecx, eax; exception
0x18001a637  call    cs:__imp_RpcRaiseException
0x18001a63d  xor     ecx, ecx; BindingHandle
0x18001a63f  call    cs:__imp_RpcImpersonateClient
0x18001a645  test    eax, eax
0x18001a647  jz      short loc_18001A651
0x18001a649  mov     ecx, eax; exception
0x18001a64b  call    cs:__imp_RpcRaiseException
0x18001a651  mov     [rsp+0D8h+var_B8], 1
0x18001a659  lea     rdx, [rsp+0D8h+KeyHandle]; KeyHandle
0x18001a65e  mov     ecx, ebx; DesiredAccess
0x18001a660  call    cs:__imp_RtlOpenCurrentUser
0x18001a666  mov     ecx, eax; Status
0x18001a668  call    cs:__imp_RtlNtStatusToDosError
0x18001a66e  mov     ebx, eax
0x18001a670  test    eax, eax
0x18001a672  jnz     short loc_18001A6A6
0x18001a674  lea     rcx, [rsp+0D8h+var_B0]
0x18001a679  call    RegSvcContextAllocate
0x18001a67e  mov     ebx, eax
0x18001a680  test    eax, eax
0x18001a682  jnz     short loc_18001A6A6
0x18001a684  mov     rax, [rsp+0D8h+KeyHandle]
0x18001a689  mov     rcx, [rsp+0D8h+var_B0]
0x18001a68e  mov     [rcx], rax
0x18001a691  mov     [rsp+0D8h+KeyHandle], 0
0x18001a69a  mov     [rdi], rcx
0x18001a69d  mov     [rsp+0D8h+var_B0], 0
0x18001a6a6  call    cs:__imp_RpcRevertToSelf
0x18001a6ac  mov     rcx, [rsp+0D8h+var_B0]
0x18001a6b1  test    rcx, rcx
0x18001a6b4  jz      short loc_18001A6BB
0x18001a6b6  call    RegSvcContextFree
0x18001a6bb  mov     rcx, [rsp+0D8h+KeyHandle]; Handle
0x18001a6c0  test    rcx, rcx
0x18001a6c3  jz      short loc_18001A6CB
0x18001a6c5  call    cs:__imp_NtClose
0x18001a6cb  mov     eax, ebx
0x18001a6cd  mov     rcx, [rsp+0D8h+var_18]
0x18001a6d5  xor     rcx, rsp; StackCookie
0x18001a6d8  call    __security_check_cookie
0x18001a6dd  mov     rbx, [rsp+0D8h+arg_0]
0x18001a6e5  add     rsp, 0D0h
0x18001a6ec  pop     rdi
0x18001a6ed  retn
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
