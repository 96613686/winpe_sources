# OpenLocalMachine

- ea: `0x18001a710`
- end: `0x18001a8c5`
- name: `OpenLocalMachine`
- size: `437`
- prototype: `__int64 __fastcall(__int64, int, HANDLE **)`
- caller_count: `0`
- callee_count: `8`
- tags: `authz_impersonation, loader_planting`

## callees

- `0x180007740`
- `0x180008042`
- `0x180017f6c`
- `0x18001a710`
- `0x18001aad0`
- `0x18001ac84`
- `0x18001acc8`
- `0x18001d698`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x18001a81a`
- `ntdll!RtlNtStatusToDosError` at `0x18001a81a`
- `ntdll!NtClose` at `0x18001a858`
- `ntdll!NtClose` at `0x18001a89c`
- `ntdll!NtClose` at `0x18001a858`
- `ntdll!NtClose` at `0x18001a89c`
- `RPCRT4!RpcRaiseException` at `0x18001a79b`
- `RPCRT4!RpcRaiseException` at `0x18001a7a3`
- `RPCRT4!RpcRaiseException` at `0x18001a7b7`
- `RPCRT4!RpcRaiseException` at `0x18001a79b`
- `RPCRT4!RpcRaiseException` at `0x18001a7a3`
- `RPCRT4!RpcRaiseException` at `0x18001a7b7`
- `RPCRT4!RpcImpersonateClient` at `0x18001a7ab`
- `RPCRT4!RpcImpersonateClient` at `0x18001a7ab`
- `RPCRT4!RpcRevertToSelf` at `0x18001a87d`
- `RPCRT4!RpcRevertToSelf` at `0x18001a87d`
- `RPCRT4!RpcServerInqCallAttributesW` at `0x18001a77d`
- `RPCRT4!RpcServerInqCallAttributesW` at `0x18001a77d`

## pseudocode

```c
__int64 __fastcall OpenLocalMachine(__int64 a1, int a2, HANDLE **a3)
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
  const wchar_t *v15; // [rsp+58h] [rbp-C0h]
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
  v15 = L"\"\"";
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
        *v9 = RestrictedMachineHandle;
        *((_DWORD *)v9 + 2) = 1;
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
0x18001a710  mov     [rsp+arg_0], rbx
0x18001a715  push    rdi
0x18001a716  sub     rsp, 110h
0x18001a71d  mov     rax, cs:__security_cookie
0x18001a724  xor     rax, rsp
0x18001a727  mov     [rsp+118h+var_18], rax
0x18001a72f  mov     rdi, r8
0x18001a732  mov     ebx, edx
0x18001a734  mov     [rsp+118h+Handle], 0
0x18001a73d  mov     [rsp+118h+var_E8], 0
0x18001a745  mov     [rsp+118h+var_E0], 0
0x18001a74e  mov     qword ptr [r8], 0
0x18001a755  xor     edx, edx; Val
0x18001a757  lea     r8d, [rdx+78h]; Size
0x18001a75b  lea     rcx, [rsp+118h+RpcCallAttributes]; void *
0x18001a763  call    memset_0
0x18001a768  mov     [rsp+118h+RpcCallAttributes], 3
0x18001a773  lea     rdx, [rsp+118h+RpcCallAttributes]; RpcCallAttributes
0x18001a77b  xor     ecx, ecx; ClientBinding
0x18001a77d  call    cs:__imp_RpcServerInqCallAttributesW
0x18001a783  cmp     eax, 6D2h
0x18001a788  jz      short loc_18001A7A9
0x18001a78a  test    eax, eax
0x18001a78c  jnz     short loc_18001A7A1
0x18001a78e  cmp     [rsp+118h+var_70], 6
0x18001a796  jnb     short loc_18001A7A9
0x18001a798  lea     ecx, [rax+5]; exception
0x18001a79b  call    cs:__imp_RpcRaiseException
0x18001a7a1  mov     ecx, eax; exception
0x18001a7a3  call    cs:__imp_RpcRaiseException
0x18001a7a9  xor     ecx, ecx; BindingHandle
0x18001a7ab  call    cs:__imp_RpcImpersonateClient
0x18001a7b1  test    eax, eax
0x18001a7b3  jz      short loc_18001A7BD
0x18001a7b5  mov     ecx, eax; exception
0x18001a7b7  call    cs:__imp_RpcRaiseException
0x18001a7bd  mov     [rsp+118h+var_E8], 1
0x18001a7c5  xor     eax, eax
0x18001a7c7  mov     [rsp+118h+var_D0+4], eax
0x18001a7cb  xorps   xmm0, xmm0
0x18001a7ce  movups  xmmword ptr [rsp+118h+var_D0], xmm0
0x18001a7d3  movups  [rsp+118h+var_C0], xmm0
0x18001a7d8  movups  [rsp+118h+var_C0+0Ch], xmm0
0x18001a7dd  mov     [rsp+118h+var_D0], 30h ; '0'
0x18001a7e5  mov     qword ptr [rsp+118h+var_D0+8], rax
0x18001a7ea  mov     dword ptr [rsp+118h+var_C0+8], 40h ; '@'
0x18001a7f2  lea     rax, MachineStringKey; "\"\""
0x18001a7f9  mov     qword ptr [rsp+118h+var_C0], rax
0x18001a7fe  movdqu  [rsp+118h+var_B0], xmm0
0x18001a804  xor     r9d, r9d; int
0x18001a807  lea     r8, [rsp+118h+var_D0]; int
0x18001a80c  mov     edx, ebx; int
0x18001a80e  lea     rcx, [rsp+118h+Handle]; int
0x18001a813  call    Wow64NtOpenKey
0x18001a818  mov     ecx, eax; Status
0x18001a81a  call    cs:__imp_RtlNtStatusToDosError
0x18001a820  mov     ebx, eax
0x18001a822  test    eax, eax
0x18001a824  jnz     short loc_18001A87D
0x18001a826  lea     rcx, [rsp+118h+var_E0]
0x18001a82b  call    RegSvcContextAllocate
0x18001a830  mov     ebx, eax
0x18001a832  test    eax, eax
0x18001a834  jnz     short loc_18001A87D
0x18001a836  mov     rax, [rsp+118h+Handle]
0x18001a83b  mov     rbx, [rsp+118h+var_E0]
0x18001a840  mov     [rbx], rax
0x18001a843  mov     [rsp+118h+Handle], 0
0x18001a84c  call    RegSecCheckRemoteAccess
0x18001a851  test    eax, eax
0x18001a853  jnz     short loc_18001A86F
0x18001a855  mov     rcx, [rbx]; Handle
0x18001a858  call    cs:__imp_NtClose
0x18001a85e  mov     rax, cs:RestrictedMachineHandle
0x18001a865  mov     [rbx], rax
0x18001a868  mov     dword ptr [rbx+8], 1
0x18001a86f  mov     [rdi], rbx
0x18001a872  mov     [rsp+118h+var_E0], 0
0x18001a87b  xor     ebx, ebx
0x18001a87d  call    cs:__imp_RpcRevertToSelf
0x18001a883  mov     rcx, [rsp+118h+var_E0]
0x18001a888  test    rcx, rcx
0x18001a88b  jz      short loc_18001A892
0x18001a88d  call    RegSvcContextCleanup
0x18001a892  mov     rcx, [rsp+118h+Handle]; Handle
0x18001a897  test    rcx, rcx
0x18001a89a  jz      short loc_18001A8A2
0x18001a89c  call    cs:__imp_NtClose
0x18001a8a2  mov     eax, ebx
0x18001a8a4  mov     rcx, [rsp+118h+var_18]
0x18001a8ac  xor     rcx, rsp; StackCookie
0x18001a8af  call    __security_check_cookie
0x18001a8b4  mov     rbx, [rsp+118h+arg_0]
0x18001a8bc  add     rsp, 110h
0x18001a8c3  pop     rdi
0x18001a8c4  retn
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
