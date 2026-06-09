# AicpCreateBindingHandle(ushort *,int,void * *)

- ea: `0x1800c6bdc`
- end: `0x1800c6d46`
- name: `?AicpCreateBindingHandle@@YAKPEAGHPEAPEAX@Z`
- size: `362`
- prototype: `unsigned int __fastcall(wchar_t *phLocalBinding, int pszUuid, void **bDynamicIdentityTracking)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x180039e7c`

## callees

- `0x1800475b8`
- `0x1800475e8`
- `0x180047e36`
- `0x1800c6bdc`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x1800c6ca3`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x1800c6ca3`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x1800c6c56`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x1800c6c56`
- `RPCRT4!RpcBindingFree` at `0x1800c6d27`
- `RPCRT4!RpcBindingFree` at `0x1800c6d27`
- `RPCRT4!RpcStringBindingComposeW` at `0x1800c6c38`
- `RPCRT4!RpcStringBindingComposeW` at `0x1800c6c38`
- `RPCRT4!RpcBindingSetAuthInfoExW` at `0x1800c6cf6`
- `RPCRT4!RpcBindingSetAuthInfoExW` at `0x1800c6cf6`
- `RPCRT4!RpcStringFreeW` at `0x1800c6c68`
- `RPCRT4!RpcStringFreeW` at `0x1800c6c68`

## pseudocode

```c
__int64 __fastcall AicpCreateBindingHandle(wchar_t *phLocalBinding, int pszUuid, void **bDynamicIdentityTracking)
{
  void *v4; // rdi
  DWORD LastError_0; // ebx
  HLOCAL v6; // rax
  void *v7; // rax
  _RPC_SECURITY_QOS_V3_W SecurityQOS; // [rsp+40h] [rbp-30h] BYREF
  void *hLocalBinding; // [rsp+90h] [rbp+20h] BYREF
  unsigned int cbSid; // [rsp+98h] [rbp+28h] BYREF
  wchar_t *pszBinding; // [rsp+A8h] [rbp+38h] BYREF

  pszBinding = 0;
  hLocalBinding = 0;
  cbSid = 0;
  v4 = 0;
  memset(&SecurityQOS, 0, sizeof(SecurityQOS));
  LastError_0 = RpcStringBindingComposeW(
                  (RPC_WSTR)L"5f54ce7d-5b79-4175-8584-cb65313a0e98",
                  (RPC_WSTR)L"ncalrpc",
                  0,
                  0,
                  0,
                  &pszBinding);
  if ( !LastError_0 )
  {
    LastError_0 = RpcBindingFromStringBindingW(pszBinding, &hLocalBinding);
    RpcStringFreeW(&pszBinding);
    if ( !LastError_0 )
    {
      cbSid = 68;
      v6 = LocalAlloc_0(0x40u, 0x44u);
      v4 = v6;
      if ( v6 )
      {
        if ( CreateWellKnownSid(WinLocalSystemSid, 0, v6, &cbSid) )
        {
          SecurityQOS.Sid = v4;
          SecurityQOS.Version = 3;
          SecurityQOS.ImpersonationType = 3;
          SecurityQOS.Capabilities = 1;
          SecurityQOS.IdentityTracking = 1;
          LastError_0 = RpcBindingSetAuthInfoExW(hLocalBinding, 0, 6u, 0xAu, 0, 0, (RPC_SECURITY_QOS *)&SecurityQOS);
          if ( !LastError_0 )
          {
            v7 = hLocalBinding;
            hLocalBinding = 0;
            *bDynamicIdentityTracking = v7;
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
  if ( hLocalBinding )
    RpcBindingFree(&hLocalBinding);
  return LastError_0;
}

```

## disassembly

```asm
0x1800c6bdc  mov     r11, rsp
0x1800c6bdf  mov     [r11+18h], rbx
0x1800c6be3  mov     [rsp-18h+cbSid], edx
0x1800c6be7  mov     [r11+8], rcx
0x1800c6beb  push    rbp
0x1800c6bec  push    rsi
0x1800c6bed  push    rdi
0x1800c6bee  mov     rbp, rsp
0x1800c6bf1  sub     rsp, 70h
0x1800c6bf5  and     [rbp+pszBinding], 0
0x1800c6bfa  lea     rdx, ProtSeq; "ncalrpc"
0x1800c6c01  and     [rbp+hLocalBinding], 0
0x1800c6c06  lea     rcx, ObjUuid; "5f54ce7d-5b79-4175-8584-cb65313a0e98"
0x1800c6c0d  xor     eax, eax
0x1800c6c0f  xorps   xmm0, xmm0
0x1800c6c12  and     [rbp+cbSid], eax
0x1800c6c15  mov     rsi, phLocalBinding
0x1800c6c18  mov     [rbp+SecurityQOS.Sid], rax
0x1800c6c1c  xor     edi, edi
0x1800c6c1e  lea     rax, [rbp+pszBinding]
0x1800c6c22  xor     r9d, r9d; Endpoint
0x1800c6c25  mov     [r11-60h], rax
0x1800c6c29  xor     r8d, r8d; NetworkAddr
0x1800c6c2c  and     [r11-68h], rdi
0x1800c6c30  movups  xmmword ptr [rbp+SecurityQOS.Version], xmm0
0x1800c6c34  movups  xmmword ptr [rbp+SecurityQOS.AdditionalSecurityInfoType], xmm0
0x1800c6c38  call    cs:__imp_RpcStringBindingComposeW
0x1800c6c3f  nop     dword ptr [rax+rax+00h]
0x1800c6c44  mov     ebx, eax
0x1800c6c46  test    eax, eax
0x1800c6c48  jnz     $CleanExit_1
0x1800c6c4e  mov     rcx, [rbp+pszBinding]; StringBinding
0x1800c6c52  lea     rdx, [rbp+hLocalBinding]; Binding
0x1800c6c56  call    cs:__imp_RpcBindingFromStringBindingW
0x1800c6c5d  nop     dword ptr [rax+rax+00h]
0x1800c6c62  lea     rcx, [rbp+pszBinding]; String
0x1800c6c66  mov     ebx, eax
0x1800c6c68  call    cs:__imp_RpcStringFreeW
0x1800c6c6f  nop     dword ptr [rax+rax+00h]
0x1800c6c74  test    ebx, ebx
0x1800c6c76  jnz     $CleanExit_1
0x1800c6c7c  lea     edx, [rdi+44h]; uBytes
0x1800c6c7f  lea     ecx, [rdi+40h]; uFlags
0x1800c6c82  mov     [rbp+cbSid], edx
0x1800c6c85  call    LocalAlloc_0
0x1800c6c8a  mov     rdi, rax
0x1800c6c8d  test    rax, rax
0x1800c6c90  jnz     short loc_1800C6C97
0x1800c6c92  lea     ebx, [rax+8]
0x1800c6c95  jmp     short $CleanExit_1
0x1800c6c97  xor     edx, edx; DomainSid
0x1800c6c99  lea     r9, [rbp+cbSid]; cbSid
0x1800c6c9d  mov     phLocalBinding, rdi; pSid
0x1800c6ca0  lea     ecx, [rdx+16h]; WellKnownSidType
0x1800c6ca3  call    cs:__imp_CreateWellKnownSid
0x1800c6caa  nop     dword ptr [rax+rax+00h]
0x1800c6caf  test    eax, eax
0x1800c6cb1  jnz     short loc_1800C6CBC
0x1800c6cb3  call    GetLastError_0
0x1800c6cb8  mov     ebx, eax
0x1800c6cba  jmp     short $CleanExit_1
0x1800c6cbc  mov     ecx, 3
0x1800c6cc1  mov     [rbp+SecurityQOS.Sid], rdi
0x1800c6cc5  mov     [rbp+SecurityQOS.Version], ecx
0x1800c6cc8  xor     edx, edx; ServerPrincName
0x1800c6cca  mov     [rbp+SecurityQOS.ImpersonationType], ecx
0x1800c6ccd  lea     eax, [rcx-2]
0x1800c6cd0  mov     [rbp+SecurityQOS.Capabilities], eax
0x1800c6cd3  lea     r9d, [rcx+7]; AuthnSvc
0x1800c6cd7  mov     [rbp+SecurityQOS.IdentityTracking], eax
0x1800c6cda  lea     r8d, [rcx+3]; AuthnLevel
0x1800c6cde  mov     rcx, [rbp+hLocalBinding]; Binding
0x1800c6ce2  lea     rax, [rbp+SecurityQOS]
0x1800c6ce6  mov     [rsp+70h+var_40], rax; SecurityQOS
0x1800c6ceb  and     [rsp+70h+var_48], 0
0x1800c6cf0  and     [rsp+70h+var_50], 0
0x1800c6cf6  call    cs:__imp_RpcBindingSetAuthInfoExW
0x1800c6cfd  nop     dword ptr [rax+rax+00h]
0x1800c6d02  mov     ebx, eax
0x1800c6d04  test    eax, eax
0x1800c6d06  jnz     short $CleanExit_1
0x1800c6d08  mov     rax, [rbp+hLocalBinding]
0x1800c6d0c  and     [rbp+hLocalBinding], 0
0x1800c6d11  mov     [rsi], rax
0x1800c6d14  mov     rcx, rdi; hMem
0x1800c6d17  call    LocalFree_0
0x1800c6d1c  cmp     [rbp+hLocalBinding], 0
0x1800c6d21  jz      short loc_1800C6D33
0x1800c6d23  lea     rcx, [rbp+hLocalBinding]; Binding
0x1800c6d27  call    cs:__imp_RpcBindingFree
0x1800c6d2e  nop     dword ptr [rax+rax+00h]
0x1800c6d33  mov     eax, ebx
0x1800c6d35  mov     rbx, [rsp+70h+arg_10]
0x1800c6d3d  add     rsp, 70h
0x1800c6d41  pop     rdi
0x1800c6d42  pop     rsi
0x1800c6d43  pop     rbp
0x1800c6d44  retn
```
