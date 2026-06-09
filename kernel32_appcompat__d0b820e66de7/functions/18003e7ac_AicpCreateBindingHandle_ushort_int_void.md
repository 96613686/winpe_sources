# AicpCreateBindingHandle(ushort *,int,void * *)

- ea: `0x18003e7ac`
- end: `0x18003e936`
- name: `?AicpCreateBindingHandle@@YAKPEAGHPEAPEAX@Z`
- size: `394`
- prototype: `unsigned int __fastcall(unsigned __int16 *, int, void **)`
- caller_count: `3`
- callee_count: `1`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x18003e134`
- `0x18003e324`
- `0x18003e534`

## callees

- `0x18003e7ac`

## import_xrefs

- `KERNELBASE!LocalAlloc` at `0x18003e85b`
- `KERNELBASE!LocalAlloc` at `0x18003e85b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003e900`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003e900`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x18003e883`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x18003e883`
- `RPCRT4!RpcBindingFree` at `0x18003e917`
- `RPCRT4!RpcBindingFree` at `0x18003e917`
- `RPCRT4!RpcStringFreeW` at `0x18003e83e`
- `RPCRT4!RpcStringFreeW` at `0x18003e83e`
- `RPCRT4!RpcStringBindingComposeW` at `0x18003e80e`
- `RPCRT4!RpcStringBindingComposeW` at `0x18003e80e`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x18003e82c`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x18003e82c`
- `RPCRT4!RpcBindingSetAuthInfoExW` at `0x18003e8dc`
- `RPCRT4!RpcBindingSetAuthInfoExW` at `0x18003e8dc`

## pseudocode

```c
__int64 __fastcall AicpCreateBindingHandle(unsigned __int16 *a1, __int64 a2, void **a3)
{
  void *v4; // rdi
  ULONG LastErrorValue; // ebx
  HLOCAL v6; // rax
  RPC_SECURITY_QOS SecurityQOS; // [rsp+40h] [rbp-30h] BYREF
  __int128 v9; // [rsp+50h] [rbp-20h]
  void *v10; // [rsp+60h] [rbp-10h]
  RPC_BINDING_HANDLE Binding; // [rsp+90h] [rbp+20h] BYREF
  DWORD cbSid; // [rsp+98h] [rbp+28h] BYREF
  RPC_WSTR StringBinding; // [rsp+A8h] [rbp+38h] BYREF

  StringBinding = 0;
  v10 = 0;
  cbSid = 0;
  Binding = 0;
  v4 = 0;
  SecurityQOS = 0;
  v9 = 0;
  LastErrorValue = RpcStringBindingComposeW(
                     (RPC_WSTR)L"0497B57D-2E66-424F-A0C6-157CD5D41700",
                     (RPC_WSTR)L"ncalrpc",
                     0,
                     0,
                     0,
                     &StringBinding);
  if ( !LastErrorValue )
  {
    LastErrorValue = RpcBindingFromStringBindingW(StringBinding, &Binding);
    RpcStringFreeW(&StringBinding);
    if ( !LastErrorValue )
    {
      cbSid = 68;
      v6 = LocalAlloc(0x40u, 0x44u);
      v4 = v6;
      if ( v6 )
      {
        if ( CreateWellKnownSid(WinLocalSystemSid, 0, v6, &cbSid) )
        {
          SecurityQOS.Version = 3;
          SecurityQOS.ImpersonationType = 3;
          *(_QWORD *)&SecurityQOS.Capabilities = 1;
          v10 = v4;
          LastErrorValue = RpcBindingSetAuthInfoExW(Binding, 0, 6u, 0xAu, 0, 0, &SecurityQOS);
          if ( !LastErrorValue )
          {
            *a3 = Binding;
            Binding = 0;
          }
        }
        else
        {
          LastErrorValue = NtCurrentTeb()->LastErrorValue;
        }
      }
      else
      {
        LastErrorValue = 8;
      }
    }
  }
  LocalFree(v4);
  if ( Binding )
    RpcBindingFree(&Binding);
  return LastErrorValue;
}

```

## disassembly

```asm
0x18003e7ac  mov     r11, rsp
0x18003e7af  mov     [r11+18h], rbx
0x18003e7b3  mov     [rsp-18h+cbSid], edx
0x18003e7b7  mov     [r11+8], rcx
0x18003e7bb  push    rbp
0x18003e7bc  push    rsi
0x18003e7bd  push    rdi
0x18003e7be  mov     rbp, rsp
0x18003e7c1  sub     rsp, 70h
0x18003e7c5  xor     eax, eax
0x18003e7c7  mov     [rbp+StringBinding], 0
0x18003e7cf  xorps   xmm0, xmm0
0x18003e7d2  mov     [rbp+var_10], rax
0x18003e7d6  mov     [rbp+cbSid], eax
0x18003e7d9  lea     rdx, ProtSeq; "ncalrpc"
0x18003e7e0  lea     rax, [rbp+StringBinding]
0x18003e7e4  mov     [rbp+Binding], 0
0x18003e7ec  mov     rsi, r8
0x18003e7ef  mov     [r11-60h], rax
0x18003e7f3  xor     edi, edi
0x18003e7f5  lea     rcx, ObjUuid; "0497B57D-2E66-424F-A0C6-157CD5D41700"
0x18003e7fc  xor     r9d, r9d; Endpoint
0x18003e7ff  mov     [r11-68h], rdi
0x18003e803  xor     r8d, r8d; NetworkAddr
0x18003e806  movups  xmmword ptr [rbp+var_30.Version], xmm0
0x18003e80a  movups  [rbp+var_20], xmm0
0x18003e80e  call    cs:__imp_RpcStringBindingComposeW
0x18003e815  nop     dword ptr [rax+rax+00h]
0x18003e81a  mov     ebx, eax
0x18003e81c  test    eax, eax
0x18003e81e  jnz     loc_18003E8FD
0x18003e824  mov     rcx, [rbp+StringBinding]; StringBinding
0x18003e828  lea     rdx, [rbp+Binding]; Binding
0x18003e82c  call    cs:__imp_RpcBindingFromStringBindingW
0x18003e833  nop     dword ptr [rax+rax+00h]
0x18003e838  lea     rcx, [rbp+StringBinding]; String
0x18003e83c  mov     ebx, eax
0x18003e83e  call    cs:__imp_RpcStringFreeW
0x18003e845  nop     dword ptr [rax+rax+00h]
0x18003e84a  test    ebx, ebx
0x18003e84c  jnz     loc_18003E8FD
0x18003e852  lea     edx, [rdi+44h]; uBytes
0x18003e855  lea     ecx, [rdi+40h]; uFlags
0x18003e858  mov     [rbp+cbSid], edx
0x18003e85b  call    cs:__imp_LocalAlloc
0x18003e862  nop     dword ptr [rax+rax+00h]
0x18003e867  mov     rdi, rax
0x18003e86a  test    rax, rax
0x18003e86d  jnz     short loc_18003E877
0x18003e86f  lea     ebx, [rax+8]
0x18003e872  jmp     loc_18003E8FD
0x18003e877  xor     edx, edx; DomainSid
0x18003e879  lea     r9, [rbp+cbSid]; cbSid
0x18003e87d  mov     r8, rdi; pSid
0x18003e880  lea     ecx, [rdx+16h]; WellKnownSidType
0x18003e883  call    cs:__imp_CreateWellKnownSid
0x18003e88a  nop     dword ptr [rax+rax+00h]
0x18003e88f  test    eax, eax
0x18003e891  jnz     short loc_18003E89D
0x18003e893  mov     ebx, gs:68h
0x18003e89b  jmp     short loc_18003E8FD
0x18003e89d  mov     rcx, [rbp+Binding]; Binding
0x18003e8a1  mov     eax, 3
0x18003e8a6  xor     edx, edx; ServerPrincName
0x18003e8a8  mov     [rbp+var_30.Version], eax
0x18003e8ab  mov     [rbp+var_30.ImpersonationType], eax
0x18003e8ae  lea     rax, [rbp+var_30]
0x18003e8b2  mov     [rsp+70h+SecurityQOS], rax; SecurityQOS
0x18003e8b7  mov     [rsp+70h+AuthzSvc], 0; AuthzSvc
0x18003e8bf  lea     r9d, [rdx+0Ah]; AuthnSvc
0x18003e8c3  mov     [rsp+70h+AuthIdentity], 0; AuthIdentity
0x18003e8cc  lea     r8d, [rdx+6]; AuthnLevel
0x18003e8d0  mov     qword ptr [rbp+var_30.Capabilities], 1
0x18003e8d8  mov     [rbp+var_10], rdi
0x18003e8dc  call    cs:__imp_RpcBindingSetAuthInfoExW
0x18003e8e3  nop     dword ptr [rax+rax+00h]
0x18003e8e8  mov     ebx, eax
0x18003e8ea  test    eax, eax
0x18003e8ec  jnz     short loc_18003E8FD
0x18003e8ee  mov     rax, [rbp+Binding]
0x18003e8f2  mov     [rsi], rax
0x18003e8f5  mov     [rbp+Binding], 0
0x18003e8fd  mov     rcx, rdi; hMem
0x18003e900  call    cs:__imp_LocalFree
0x18003e907  nop     dword ptr [rax+rax+00h]
0x18003e90c  cmp     [rbp+Binding], 0
0x18003e911  jz      short loc_18003E923
0x18003e913  lea     rcx, [rbp+Binding]; Binding
0x18003e917  call    cs:__imp_RpcBindingFree
0x18003e91e  nop     dword ptr [rax+rax+00h]
0x18003e923  mov     eax, ebx
0x18003e925  mov     rbx, [rsp+70h+arg_10]
0x18003e92d  add     rsp, 70h
0x18003e931  pop     rdi
0x18003e932  pop     rsi
0x18003e933  pop     rbp
0x18003e934  retn
```
