# OpenCurrentConfig

- ea: `0x18001a410`
- end: `0x18001a5a0`
- name: `OpenCurrentConfig`
- size: `400`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, loader_planting`

## callees

- `0x180007740`
- `0x180008042`
- `0x18001a410`
- `0x18001aad0`
- `0x18001ac84`
- `0x18001acc8`
- `0x18001d698`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x18001a51a`
- `ntdll!RtlNtStatusToDosError` at `0x18001a51a`
- `ntdll!NtClose` at `0x18001a577`
- `ntdll!NtClose` at `0x18001a577`
- `RPCRT4!RpcRaiseException` at `0x18001a49b`
- `RPCRT4!RpcRaiseException` at `0x18001a4a3`
- `RPCRT4!RpcRaiseException` at `0x18001a4b7`
- `RPCRT4!RpcRaiseException` at `0x18001a49b`
- `RPCRT4!RpcRaiseException` at `0x18001a4a3`
- `RPCRT4!RpcRaiseException` at `0x18001a4b7`
- `RPCRT4!RpcImpersonateClient` at `0x18001a4ab`
- `RPCRT4!RpcImpersonateClient` at `0x18001a4ab`
- `RPCRT4!RpcRevertToSelf` at `0x18001a558`
- `RPCRT4!RpcRevertToSelf` at `0x18001a558`
- `RPCRT4!RpcServerInqCallAttributesW` at `0x18001a47d`
- `RPCRT4!RpcServerInqCallAttributesW` at `0x18001a47d`

## pseudocode

```c
__int64 __fastcall OpenCurrentConfig(__int64 a1, unsigned int a2, HANDLE **a3)
{
  RPC_STATUS v5; // eax
  RPC_STATUS v6; // eax
  NTSTATUS v7; // eax
  ULONG v8; // ebx
  HANDLE *v9; // rcx
  int v11; // [rsp+20h] [rbp-F8h]
  HANDLE *v12; // [rsp+38h] [rbp-E0h] BYREF
  HANDLE Handle; // [rsp+40h] [rbp-D8h] BYREF
  int v14[4]; // [rsp+48h] [rbp-D0h] BYREF
  __int64 *v15; // [rsp+58h] [rbp-C0h]
  __int64 v16; // [rsp+60h] [rbp-B8h]
  __int128 v17; // [rsp+68h] [rbp-B0h]
  _DWORD RpcCallAttributes[32]; // [rsp+80h] [rbp-98h] BYREF

  v12 = 0;
  Handle = 0;
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
  v14[1] = 0;
  v14[0] = 48;
  *(_QWORD *)&v14[2] = 0;
  v16 = 64;
  v15 = &CurrentConfigStringKey;
  v17 = 0;
  v7 = Wow64NtOpenKey(&Handle, a2, (__int128 *)v14, 0, v11);
  v8 = RtlNtStatusToDosError(v7);
  if ( !v8 )
  {
    v8 = RegSvcContextAllocate(&v12);
    if ( !v8 )
    {
      v9 = v12;
      *v12 = Handle;
      Handle = 0;
      *a3 = v9;
      v12 = 0;
    }
  }
  RpcRevertToSelf();
  if ( v12 )
    RegSvcContextCleanup();
  if ( Handle )
    NtClose(Handle);
  return v8;
}

```

## disassembly

```asm
0x18001a410  mov     [rsp+arg_0], rbx
0x18001a415  push    rdi
0x18001a416  sub     rsp, 110h
0x18001a41d  mov     rax, cs:__security_cookie
0x18001a424  xor     rax, rsp
0x18001a427  mov     [rsp+118h+var_18], rax
0x18001a42f  mov     rdi, r8
0x18001a432  mov     ebx, edx
0x18001a434  mov     [rsp+118h+var_E0], 0
0x18001a43d  mov     [rsp+118h+var_E8], 0
0x18001a445  mov     [rsp+118h+Handle], 0
0x18001a44e  mov     qword ptr [r8], 0
0x18001a455  xor     edx, edx; Val
0x18001a457  lea     r8d, [rdx+78h]; Size
0x18001a45b  lea     rcx, [rsp+118h+RpcCallAttributes]; void *
0x18001a463  call    memset_0
0x18001a468  mov     [rsp+118h+RpcCallAttributes], 3
0x18001a473  lea     rdx, [rsp+118h+RpcCallAttributes]; RpcCallAttributes
0x18001a47b  xor     ecx, ecx; ClientBinding
0x18001a47d  call    cs:__imp_RpcServerInqCallAttributesW
0x18001a483  cmp     eax, 6D2h
0x18001a488  jz      short loc_18001A4A9
0x18001a48a  test    eax, eax
0x18001a48c  jnz     short loc_18001A4A1
0x18001a48e  cmp     [rsp+118h+var_70], 6
0x18001a496  jnb     short loc_18001A4A9
0x18001a498  lea     ecx, [rax+5]; exception
0x18001a49b  call    cs:__imp_RpcRaiseException
0x18001a4a1  mov     ecx, eax; exception
0x18001a4a3  call    cs:__imp_RpcRaiseException
0x18001a4a9  xor     ecx, ecx; BindingHandle
0x18001a4ab  call    cs:__imp_RpcImpersonateClient
0x18001a4b1  test    eax, eax
0x18001a4b3  jz      short loc_18001A4BD
0x18001a4b5  mov     ecx, eax; exception
0x18001a4b7  call    cs:__imp_RpcRaiseException
0x18001a4bd  mov     [rsp+118h+var_E8], 1
0x18001a4c5  xor     eax, eax
0x18001a4c7  mov     [rsp+118h+var_D0+4], eax
0x18001a4cb  xorps   xmm0, xmm0
0x18001a4ce  movups  xmmword ptr [rsp+118h+var_D0], xmm0
0x18001a4d3  movups  [rsp+118h+var_C0], xmm0
0x18001a4d8  movups  [rsp+118h+var_C0+0Ch], xmm0
0x18001a4dd  mov     [rsp+118h+var_D0], 30h ; '0'
0x18001a4e5  mov     qword ptr [rsp+118h+var_D0+8], rax
0x18001a4ea  mov     dword ptr [rsp+118h+var_C0+8], 40h ; '@'
0x18001a4f2  lea     rax, CurrentConfigStringKey
0x18001a4f9  mov     qword ptr [rsp+118h+var_C0], rax
0x18001a4fe  movdqu  [rsp+118h+var_B0], xmm0
0x18001a504  xor     r9d, r9d; int
0x18001a507  lea     r8, [rsp+118h+var_D0]; int
0x18001a50c  mov     edx, ebx; int
0x18001a50e  lea     rcx, [rsp+118h+Handle]; int
0x18001a513  call    Wow64NtOpenKey
0x18001a518  mov     ecx, eax; Status
0x18001a51a  call    cs:__imp_RtlNtStatusToDosError
0x18001a520  mov     ebx, eax
0x18001a522  test    eax, eax
0x18001a524  jnz     short loc_18001A558
0x18001a526  lea     rcx, [rsp+118h+var_E0]
0x18001a52b  call    RegSvcContextAllocate
0x18001a530  mov     ebx, eax
0x18001a532  test    eax, eax
0x18001a534  jnz     short loc_18001A558
0x18001a536  mov     rax, [rsp+118h+Handle]
0x18001a53b  mov     rcx, [rsp+118h+var_E0]
0x18001a540  mov     [rcx], rax
0x18001a543  mov     [rsp+118h+Handle], 0
0x18001a54c  mov     [rdi], rcx
0x18001a54f  mov     [rsp+118h+var_E0], 0
0x18001a558  call    cs:__imp_RpcRevertToSelf
0x18001a55e  mov     rcx, [rsp+118h+var_E0]
0x18001a563  test    rcx, rcx
0x18001a566  jz      short loc_18001A56D
0x18001a568  call    RegSvcContextCleanup
0x18001a56d  mov     rcx, [rsp+118h+Handle]; Handle
0x18001a572  test    rcx, rcx
0x18001a575  jz      short loc_18001A57D
0x18001a577  call    cs:__imp_NtClose
0x18001a57d  mov     eax, ebx
0x18001a57f  mov     rcx, [rsp+118h+var_18]
0x18001a587  xor     rcx, rsp; StackCookie
0x18001a58a  call    __security_check_cookie
0x18001a58f  mov     rbx, [rsp+118h+arg_0]
0x18001a597  add     rsp, 110h
0x18001a59e  pop     rdi
0x18001a59f  retn
0x18001e77e  push    rbp
0x18001e780  sub     rsp, 30h
0x18001e784  mov     rbp, rdx
0x18001e787  cmp     dword ptr [rbp+30h], 0
0x18001e78b  jz      short loc_18001E794
0x18001e78d  call    cs:__imp_RpcRevertToSelf
0x18001e793  nop
0x18001e794  mov     rcx, [rbp+38h]
0x18001e798  test    rcx, rcx
0x18001e79b  jz      short loc_18001E7A3
0x18001e79d  call    RegSvcContextCleanup
0x18001e7a2  nop
0x18001e7a3  mov     rcx, [rbp+40h]; Handle
0x18001e7a7  test    rcx, rcx
0x18001e7aa  jz      short loc_18001E7B3
0x18001e7ac  call    cs:__imp_NtClose
0x18001e7b2  nop
0x18001e7b3  add     rsp, 30h
0x18001e7b7  pop     rbp
0x18001e7b8  retn
```
