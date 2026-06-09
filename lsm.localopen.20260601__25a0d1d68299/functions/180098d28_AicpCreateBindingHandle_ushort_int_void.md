# AicpCreateBindingHandle(ushort *,int,void * *)

- ea: `0x180098d28`
- end: `0x180098ea4`
- name: `?AicpCreateBindingHandle@@YAKPEAGHPEAPEAX@Z`
- size: `380`
- prototype: `unsigned int __fastcall(unsigned __int16 *, int, void **)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x180098a44`

## callees

- `0x18004f533`
- `0x18004f54b`
- `0x18004f557`
- `0x180098d28`

## import_xrefs

- `RPCRT4!RpcStringFreeW` at `0x180098dba`
- `RPCRT4!RpcStringFreeW` at `0x180098dba`
- `RPCRT4!RpcBindingFree` at `0x180098e85`
- `RPCRT4!RpcBindingFree` at `0x180098e85`
- `RPCRT4!RpcBindingSetAuthInfoExW` at `0x180098e51`
- `RPCRT4!RpcBindingSetAuthInfoExW` at `0x180098e51`
- `RPCRT4!RpcStringBindingComposeW` at `0x180098d8a`
- `RPCRT4!RpcStringBindingComposeW` at `0x180098d8a`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x180098da8`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x180098da8`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x180098df8`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x180098df8`

## pseudocode

```c
__int64 __fastcall AicpCreateBindingHandle(unsigned __int16 *a1, __int64 a2, void **a3)
{
  void *v4; // rdi
  DWORD LastError_0; // ebx
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
  LastError_0 = RpcStringBindingComposeW(
                  (RPC_WSTR)L"201ef99a-7fa0-444c-9399-19ba84f12a1a",
                  (RPC_WSTR)L"ncalrpc",
                  0,
                  0,
                  0,
                  &StringBinding);
  if ( !LastError_0 )
  {
    LastError_0 = RpcBindingFromStringBindingW(StringBinding, &Binding);
    RpcStringFreeW(&StringBinding);
    if ( !LastError_0 )
    {
      cbSid = 68;
      v6 = LocalAlloc_0(0x40u, 0x44u);
      v4 = v6;
      if ( v6 )
      {
        if ( CreateWellKnownSid(WinLocalSystemSid, 0, v6, &cbSid) )
        {
          v10 = v4;
          SecurityQOS.Version = 3;
          SecurityQOS.ImpersonationType = 3;
          SecurityQOS.Capabilities = 1;
          SecurityQOS.IdentityTracking = 1;
          LastError_0 = RpcBindingSetAuthInfoExW(Binding, 0, 6u, 0xAu, 0, 0, &SecurityQOS);
          if ( !LastError_0 )
          {
            *a3 = Binding;
            Binding = 0;
          }
        }
        else
        {
          LastError_0 = GetLastError_0();
        }
      }
      else
      {
        LastError_0 = 8;
      }
    }
  }
  LocalFree_0(v4);
  if ( Binding )
    RpcBindingFree(&Binding);
  return LastError_0;
}

```

## disassembly

```asm
0x180098d28  mov     r11, rsp
0x180098d2b  mov     [r11+18h], rbx
0x180098d2f  mov     [rsp-18h+cbSid], edx
0x180098d33  mov     [r11+8], rcx
0x180098d37  push    rbp
0x180098d38  push    rsi
0x180098d39  push    rdi
0x180098d3a  mov     rbp, rsp
0x180098d3d  sub     rsp, 70h
0x180098d41  xor     eax, eax
0x180098d43  mov     [rbp+StringBinding], 0
0x180098d4b  xorps   xmm0, xmm0
0x180098d4e  mov     [rbp+var_10], rax
0x180098d52  mov     [rbp+cbSid], eax
0x180098d55  lea     rdx, ProtSeq; "ncalrpc"
0x180098d5c  lea     rax, [rbp+StringBinding]
0x180098d60  mov     [rbp+Binding], 0
0x180098d68  mov     rsi, r8
0x180098d6b  mov     [r11-60h], rax
0x180098d6f  xor     edi, edi
0x180098d71  lea     rcx, ObjUuid; "201ef99a-7fa0-444c-9399-19ba84f12a1a"
0x180098d78  xor     r9d, r9d; Endpoint
0x180098d7b  mov     [r11-68h], rdi
0x180098d7f  xor     r8d, r8d; NetworkAddr
0x180098d82  movups  xmmword ptr [rbp+var_30.Version], xmm0
0x180098d86  movups  [rbp+var_20], xmm0
0x180098d8a  call    cs:__imp_RpcStringBindingComposeW
0x180098d91  nop     dword ptr [rax+rax+00h]
0x180098d96  mov     ebx, eax
0x180098d98  test    eax, eax
0x180098d9a  jnz     loc_180098E72
0x180098da0  mov     rcx, [rbp+StringBinding]; StringBinding
0x180098da4  lea     rdx, [rbp+Binding]; Binding
0x180098da8  call    cs:__imp_RpcBindingFromStringBindingW
0x180098daf  nop     dword ptr [rax+rax+00h]
0x180098db4  lea     rcx, [rbp+StringBinding]; String
0x180098db8  mov     ebx, eax
0x180098dba  call    cs:__imp_RpcStringFreeW
0x180098dc1  nop     dword ptr [rax+rax+00h]
0x180098dc6  test    ebx, ebx
0x180098dc8  jnz     loc_180098E72
0x180098dce  lea     edx, [rdi+44h]; uBytes
0x180098dd1  lea     ecx, [rdi+40h]; uFlags
0x180098dd4  mov     [rbp+cbSid], edx
0x180098dd7  call    LocalAlloc_0
0x180098ddc  mov     rdi, rax
0x180098ddf  test    rax, rax
0x180098de2  jnz     short loc_180098DEC
0x180098de4  lea     ebx, [rax+8]
0x180098de7  jmp     loc_180098E72
0x180098dec  xor     edx, edx; DomainSid
0x180098dee  lea     r9, [rbp+cbSid]; cbSid
0x180098df2  mov     r8, rdi; pSid
0x180098df5  lea     ecx, [rdx+16h]; WellKnownSidType
0x180098df8  call    cs:__imp_CreateWellKnownSid
0x180098dff  nop     dword ptr [rax+rax+00h]
0x180098e04  test    eax, eax
0x180098e06  jnz     short loc_180098E11
0x180098e08  call    GetLastError_0
0x180098e0d  mov     ebx, eax
0x180098e0f  jmp     short loc_180098E72
0x180098e11  mov     ecx, 3
0x180098e16  mov     [rbp+var_10], rdi
0x180098e1a  mov     [rbp+var_30.Version], ecx
0x180098e1d  xor     edx, edx; ServerPrincName
0x180098e1f  mov     [rbp+var_30.ImpersonationType], ecx
0x180098e22  lea     eax, [rcx-2]
0x180098e25  mov     [rbp+var_30.Capabilities], eax
0x180098e28  lea     r9d, [rcx+7]; AuthnSvc
0x180098e2c  mov     [rbp+var_30.IdentityTracking], eax
0x180098e2f  lea     r8d, [rcx+3]; AuthnLevel
0x180098e33  mov     rcx, [rbp+Binding]; Binding
0x180098e37  lea     rax, [rbp+var_30]
0x180098e3b  mov     [rsp+70h+SecurityQOS], rax; SecurityQOS
0x180098e40  mov     [rsp+70h+AuthzSvc], 0; AuthzSvc
0x180098e48  mov     [rsp+70h+AuthIdentity], 0; AuthIdentity
0x180098e51  call    cs:__imp_RpcBindingSetAuthInfoExW
0x180098e58  nop     dword ptr [rax+rax+00h]
0x180098e5d  mov     ebx, eax
0x180098e5f  test    eax, eax
0x180098e61  jnz     short loc_180098E72
0x180098e63  mov     rax, [rbp+Binding]
0x180098e67  mov     [rsi], rax
0x180098e6a  mov     [rbp+Binding], 0
0x180098e72  mov     rcx, rdi; hMem
0x180098e75  call    LocalFree_0
0x180098e7a  cmp     [rbp+Binding], 0
0x180098e7f  jz      short loc_180098E91
0x180098e81  lea     rcx, [rbp+Binding]; Binding
0x180098e85  call    cs:__imp_RpcBindingFree
0x180098e8c  nop     dword ptr [rax+rax+00h]
0x180098e91  mov     eax, ebx
0x180098e93  mov     rbx, [rsp+70h+arg_10]
0x180098e9b  add     rsp, 70h
0x180098e9f  pop     rdi
0x180098ea0  pop     rsi
0x180098ea1  pop     rbp
0x180098ea2  retn
```
