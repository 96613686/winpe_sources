# AicpCreateBindingHandle(ushort *,int,void * *)

- ea: `0x180264b04`
- end: `0x180264c80`
- name: `?AicpCreateBindingHandle@@YAKPEAGHPEAPEAX@Z`
- size: `380`
- prototype: `unsigned int __fastcall(unsigned __int16 *, int, void **)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x1802645bc`

## callees

- `0x180176372`
- `0x180176396`
- `0x1801763ae`
- `0x180264b04`

## import_xrefs

- `RPCRT4!RpcBindingSetAuthInfoExW` at `0x180264c2d`
- `RPCRT4!RpcBindingSetAuthInfoExW` at `0x180264c2d`
- `RPCRT4!RpcStringFreeW` at `0x180264b96`
- `RPCRT4!RpcStringFreeW` at `0x180264b96`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x180264b84`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x180264b84`
- `RPCRT4!RpcBindingFree` at `0x180264c61`
- `RPCRT4!RpcBindingFree` at `0x180264c61`
- `RPCRT4!RpcStringBindingComposeW` at `0x180264b66`
- `RPCRT4!RpcStringBindingComposeW` at `0x180264b66`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x180264bd4`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x180264bd4`

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
                  (RPC_WSTR)L"fd7a0523-dc70-43dd-9b2e-9c5ed48225b1",
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
0x180264b04  mov     r11, rsp
0x180264b07  mov     [r11+18h], rbx
0x180264b0b  mov     [rsp-18h+cbSid], edx
0x180264b0f  mov     [r11+8], rcx
0x180264b13  push    rbp
0x180264b14  push    rsi
0x180264b15  push    rdi
0x180264b16  mov     rbp, rsp
0x180264b19  sub     rsp, 70h
0x180264b1d  xor     eax, eax
0x180264b1f  mov     [rbp+StringBinding], 0
0x180264b27  xorps   xmm0, xmm0
0x180264b2a  mov     [rbp+var_10], rax
0x180264b2e  mov     [rbp+cbSid], eax
0x180264b31  lea     rdx, ProtSeq; "ncalrpc"
0x180264b38  lea     rax, [rbp+StringBinding]
0x180264b3c  mov     [rbp+Binding], 0
0x180264b44  mov     rsi, r8
0x180264b47  mov     [r11-60h], rax
0x180264b4b  xor     edi, edi
0x180264b4d  lea     rcx, ObjUuid; "fd7a0523-dc70-43dd-9b2e-9c5ed48225b1"
0x180264b54  xor     r9d, r9d; Endpoint
0x180264b57  mov     [r11-68h], rdi
0x180264b5b  xor     r8d, r8d; NetworkAddr
0x180264b5e  movups  xmmword ptr [rbp+var_30.Version], xmm0
0x180264b62  movups  [rbp+var_20], xmm0
0x180264b66  call    cs:__imp_RpcStringBindingComposeW
0x180264b6d  nop     dword ptr [rax+rax+00h]
0x180264b72  mov     ebx, eax
0x180264b74  test    eax, eax
0x180264b76  jnz     loc_180264C4E
0x180264b7c  mov     rcx, [rbp+StringBinding]; StringBinding
0x180264b80  lea     rdx, [rbp+Binding]; Binding
0x180264b84  call    cs:__imp_RpcBindingFromStringBindingW
0x180264b8b  nop     dword ptr [rax+rax+00h]
0x180264b90  lea     rcx, [rbp+StringBinding]; String
0x180264b94  mov     ebx, eax
0x180264b96  call    cs:__imp_RpcStringFreeW
0x180264b9d  nop     dword ptr [rax+rax+00h]
0x180264ba2  test    ebx, ebx
0x180264ba4  jnz     loc_180264C4E
0x180264baa  lea     edx, [rdi+44h]; uBytes
0x180264bad  lea     ecx, [rdi+40h]; uFlags
0x180264bb0  mov     [rbp+cbSid], edx
0x180264bb3  call    LocalAlloc_0
0x180264bb8  mov     rdi, rax
0x180264bbb  test    rax, rax
0x180264bbe  jnz     short loc_180264BC8
0x180264bc0  lea     ebx, [rax+8]
0x180264bc3  jmp     loc_180264C4E
0x180264bc8  xor     edx, edx; DomainSid
0x180264bca  lea     r9, [rbp+cbSid]; cbSid
0x180264bce  mov     r8, rdi; pSid
0x180264bd1  lea     ecx, [rdx+16h]; WellKnownSidType
0x180264bd4  call    cs:__imp_CreateWellKnownSid
0x180264bdb  nop     dword ptr [rax+rax+00h]
0x180264be0  test    eax, eax
0x180264be2  jnz     short loc_180264BED
0x180264be4  call    GetLastError_0
0x180264be9  mov     ebx, eax
0x180264beb  jmp     short loc_180264C4E
0x180264bed  mov     ecx, 3
0x180264bf2  mov     [rbp+var_10], rdi
0x180264bf6  mov     [rbp+var_30.Version], ecx
0x180264bf9  xor     edx, edx; ServerPrincName
0x180264bfb  mov     [rbp+var_30.ImpersonationType], ecx
0x180264bfe  lea     eax, [rcx-2]
0x180264c01  mov     [rbp+var_30.Capabilities], eax
0x180264c04  lea     r9d, [rcx+7]; AuthnSvc
0x180264c08  mov     [rbp+var_30.IdentityTracking], eax
0x180264c0b  lea     r8d, [rcx+3]; AuthnLevel
0x180264c0f  mov     rcx, [rbp+Binding]; Binding
0x180264c13  lea     rax, [rbp+var_30]
0x180264c17  mov     [rsp+70h+SecurityQOS], rax; SecurityQOS
0x180264c1c  mov     [rsp+70h+AuthzSvc], 0; AuthzSvc
0x180264c24  mov     [rsp+70h+AuthIdentity], 0; AuthIdentity
0x180264c2d  call    cs:__imp_RpcBindingSetAuthInfoExW
0x180264c34  nop     dword ptr [rax+rax+00h]
0x180264c39  mov     ebx, eax
0x180264c3b  test    eax, eax
0x180264c3d  jnz     short loc_180264C4E
0x180264c3f  mov     rax, [rbp+Binding]
0x180264c43  mov     [rsi], rax
0x180264c46  mov     [rbp+Binding], 0
0x180264c4e  mov     rcx, rdi; hMem
0x180264c51  call    LocalFree_0
0x180264c56  cmp     [rbp+Binding], 0
0x180264c5b  jz      short loc_180264C6D
0x180264c5d  lea     rcx, [rbp+Binding]; Binding
0x180264c61  call    cs:__imp_RpcBindingFree
0x180264c68  nop     dword ptr [rax+rax+00h]
0x180264c6d  mov     eax, ebx
0x180264c6f  mov     rbx, [rsp+70h+arg_10]
0x180264c77  add     rsp, 70h
0x180264c7b  pop     rdi
0x180264c7c  pop     rsi
0x180264c7d  pop     rbp
0x180264c7e  retn
```
