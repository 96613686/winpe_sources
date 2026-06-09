# OpenUsers

- ea: `0x18001aad0`
- end: `0x18001ac7e`
- name: `OpenUsers`
- size: `430`
- prototype: `__int64 __fastcall(__int64, int, HANDLE **)`
- caller_count: `0`
- callee_count: `7`
- tags: `authz_impersonation, loader_planting`

## callees

- `0x180007740`
- `0x180008042`
- `0x180017f6c`
- `0x18001aad0`
- `0x18001ac84`
- `0x18001acc8`
- `0x18001d698`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x18001abda`
- `ntdll!RtlNtStatusToDosError` at `0x18001abda`
- `ntdll!NtClose` at `0x18001ac18`
- `ntdll!NtClose` at `0x18001ac55`
- `ntdll!NtClose` at `0x18001e7ac`
- `ntdll!NtClose` at `0x18001ac18`
- `ntdll!NtClose` at `0x18001ac55`
- `ntdll!NtClose` at `0x18001e7ac`
- `RPCRT4!RpcRaiseException` at `0x18001ab5b`
- `RPCRT4!RpcRaiseException` at `0x18001ab63`
- `RPCRT4!RpcRaiseException` at `0x18001ab77`
- `RPCRT4!RpcRaiseException` at `0x18001ab5b`
- `RPCRT4!RpcRaiseException` at `0x18001ab63`
- `RPCRT4!RpcRaiseException` at `0x18001ab77`
- `RPCRT4!RpcImpersonateClient` at `0x18001ab6b`
- `RPCRT4!RpcImpersonateClient` at `0x18001ab6b`
- `RPCRT4!RpcRevertToSelf` at `0x18001ac36`
- `RPCRT4!RpcRevertToSelf` at `0x18001e78d`
- `RPCRT4!RpcRevertToSelf` at `0x18001ac36`
- `RPCRT4!RpcRevertToSelf` at `0x18001e78d`
- `RPCRT4!RpcServerInqCallAttributesW` at `0x18001ab3d`
- `RPCRT4!RpcServerInqCallAttributesW` at `0x18001ab3d`

## pseudocode

```c
__int64 __fastcall OpenUsers(__int64 a1, int a2, HANDLE **a3)
{
  RPC_STATUS v5; // eax
  RPC_STATUS v6; // eax
  NTSTATUS v7; // eax
  ULONG v8; // ebx
  HANDLE *v9; // rbx
  int v11; // [rsp+20h] [rbp-F8h]
  HANDLE *v12; // [rsp+38h] [rbp-E0h] BYREF
  HANDLE Handle; // [rsp+40h] [rbp-D8h] BYREF
  int v14[4]; // [rsp+48h] [rbp-D0h] BYREF
  __int64 *v15; // [rsp+58h] [rbp-C0h]
  __int64 v16; // [rsp+60h] [rbp-B8h]
  __int128 v17; // [rsp+68h] [rbp-B0h]
  _DWORD RpcCallAttributes[32]; // [rsp+80h] [rbp-98h] BYREF

  Handle = 0;
  v12 = 0;
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
  v15 = &UserStringKey;
  v17 = 0;
  v7 = Wow64NtOpenKey((int)&Handle, a2, (int)v14, 0, v11);
  v8 = RtlNtStatusToDosError(v7);
  if ( !v8 )
  {
    v8 = RegSvcContextAllocate(&v12);
    if ( !v8 )
    {
      v9 = v12;
      *v12 = Handle;
      Handle = 0;
      if ( !(unsigned int)RegSecCheckRemoteAccess() )
      {
        NtClose(*v9);
        *v9 = RestrictedUserHandle;
      }
      *a3 = v9;
      v12 = 0;
      v8 = 0;
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
0x18001aad0  mov     [rsp+arg_0], rbx
0x18001aad5  push    rdi
0x18001aad6  sub     rsp, 110h
0x18001aadd  mov     rax, cs:__security_cookie
0x18001aae4  xor     rax, rsp
0x18001aae7  mov     [rsp+118h+var_18], rax
0x18001aaef  mov     rdi, r8
0x18001aaf2  mov     ebx, edx
0x18001aaf4  mov     [rsp+118h+Handle], 0
0x18001aafd  mov     [rsp+118h+var_E0], 0
0x18001ab06  mov     [rsp+118h+var_E8], 0
0x18001ab0e  mov     qword ptr [r8], 0
0x18001ab15  xor     edx, edx; Val
0x18001ab17  lea     r8d, [rdx+78h]; Size
0x18001ab1b  lea     rcx, [rsp+118h+RpcCallAttributes]; void *
0x18001ab23  call    memset_0
0x18001ab28  mov     [rsp+118h+RpcCallAttributes], 3
0x18001ab33  lea     rdx, [rsp+118h+RpcCallAttributes]; RpcCallAttributes
0x18001ab3b  xor     ecx, ecx; ClientBinding
0x18001ab3d  call    cs:__imp_RpcServerInqCallAttributesW
0x18001ab43  cmp     eax, 6D2h
0x18001ab48  jz      short loc_18001AB69
0x18001ab4a  test    eax, eax
0x18001ab4c  jnz     short loc_18001AB61
0x18001ab4e  cmp     [rsp+118h+var_70], 6
0x18001ab56  jnb     short loc_18001AB69
0x18001ab58  lea     ecx, [rax+5]; exception
0x18001ab5b  call    cs:__imp_RpcRaiseException
0x18001ab61  mov     ecx, eax; exception
0x18001ab63  call    cs:__imp_RpcRaiseException
0x18001ab69  xor     ecx, ecx; BindingHandle
0x18001ab6b  call    cs:__imp_RpcImpersonateClient
0x18001ab71  test    eax, eax
0x18001ab73  jz      short loc_18001AB7D
0x18001ab75  mov     ecx, eax; exception
0x18001ab77  call    cs:__imp_RpcRaiseException
0x18001ab7d  mov     [rsp+118h+var_E8], 1
0x18001ab85  xor     eax, eax
0x18001ab87  mov     [rsp+118h+var_D0+4], eax
0x18001ab8b  xorps   xmm0, xmm0
0x18001ab8e  movups  xmmword ptr [rsp+118h+var_D0], xmm0
0x18001ab93  movups  [rsp+118h+var_C0], xmm0
0x18001ab98  movups  [rsp+118h+var_C0+0Ch], xmm0
0x18001ab9d  mov     [rsp+118h+var_D0], 30h ; '0'
0x18001aba5  mov     qword ptr [rsp+118h+var_D0+8], rax
0x18001abaa  mov     dword ptr [rsp+118h+var_C0+8], 40h ; '@'
0x18001abb2  lea     rax, UserStringKey
0x18001abb9  mov     qword ptr [rsp+118h+var_C0], rax
0x18001abbe  movdqu  [rsp+118h+var_B0], xmm0
0x18001abc4  xor     r9d, r9d; int
0x18001abc7  lea     r8, [rsp+118h+var_D0]; int
0x18001abcc  mov     edx, ebx; int
0x18001abce  lea     rcx, [rsp+118h+Handle]; int
0x18001abd3  call    Wow64NtOpenKey
0x18001abd8  mov     ecx, eax; Status
0x18001abda  call    cs:__imp_RtlNtStatusToDosError
0x18001abe0  mov     ebx, eax
0x18001abe2  test    eax, eax
0x18001abe4  jnz     short loc_18001AC36
0x18001abe6  lea     rcx, [rsp+118h+var_E0]
0x18001abeb  call    RegSvcContextAllocate
0x18001abf0  mov     ebx, eax
0x18001abf2  test    eax, eax
0x18001abf4  jnz     short loc_18001AC36
0x18001abf6  mov     rax, [rsp+118h+Handle]
0x18001abfb  mov     rbx, [rsp+118h+var_E0]
0x18001ac00  mov     [rbx], rax
0x18001ac03  mov     [rsp+118h+Handle], 0
0x18001ac0c  call    RegSecCheckRemoteAccess
0x18001ac11  test    eax, eax
0x18001ac13  jnz     short loc_18001AC28
0x18001ac15  mov     rcx, [rbx]; Handle
0x18001ac18  call    cs:__imp_NtClose
0x18001ac1e  mov     rax, cs:RestrictedUserHandle
0x18001ac25  mov     [rbx], rax
0x18001ac28  mov     [rdi], rbx
0x18001ac2b  mov     [rsp+118h+var_E0], 0
0x18001ac34  xor     ebx, ebx
0x18001ac36  call    cs:__imp_RpcRevertToSelf
0x18001ac3c  mov     rcx, [rsp+118h+var_E0]
0x18001ac41  test    rcx, rcx
0x18001ac44  jz      short loc_18001AC4B
0x18001ac46  call    RegSvcContextCleanup
0x18001ac4b  mov     rcx, [rsp+118h+Handle]; Handle
0x18001ac50  test    rcx, rcx
0x18001ac53  jz      short loc_18001AC5B
0x18001ac55  call    cs:__imp_NtClose
0x18001ac5b  mov     eax, ebx
0x18001ac5d  mov     rcx, [rsp+118h+var_18]
0x18001ac65  xor     rcx, rsp; StackCookie
0x18001ac68  call    __security_check_cookie
0x18001ac6d  mov     rbx, [rsp+118h+arg_0]
0x18001ac75  add     rsp, 110h
0x18001ac7c  pop     rdi
0x18001ac7d  retn
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
