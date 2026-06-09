# AicpCreateBindingHandle(ushort *,int,void * *)

- ea: `0x14004a2ec`
- end: `0x14004a46e`
- name: `?AicpCreateBindingHandle@@YAKPEAGHPEAPEAX@Z`
- size: `386`
- prototype: `unsigned int __fastcall(unsigned __int16 *, int, void **)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x14004a218`

## callees

- `0x140001402`
- `0x14000140e`
- `0x14004a2ec`

## import_xrefs

- `RPCRT4!RpcBindingSetAuthInfoExW` at `0x14004a41b`
- `RPCRT4!RpcBindingSetAuthInfoExW` at `0x14004a41b`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x14004a36c`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x14004a36c`
- `RPCRT4!RpcStringBindingComposeW` at `0x14004a34e`
- `RPCRT4!RpcStringBindingComposeW` at `0x14004a34e`
- `RPCRT4!RpcBindingFree` at `0x14004a44f`
- `RPCRT4!RpcBindingFree` at `0x14004a44f`
- `RPCRT4!RpcStringFreeW` at `0x14004a37e`
- `RPCRT4!RpcStringFreeW` at `0x14004a37e`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x14004a39b`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x14004a39b`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x14004a3c3`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x14004a3c3`

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
0x14004a2ec  mov     r11, rsp
0x14004a2ef  mov     [r11+18h], rbx
0x14004a2f3  mov     [rsp-18h+cbSid], edx
0x14004a2f7  mov     [r11+8], rcx
0x14004a2fb  push    rbp
0x14004a2fc  push    rsi
0x14004a2fd  push    rdi
0x14004a2fe  mov     rbp, rsp
0x14004a301  sub     rsp, 70h
0x14004a305  xor     eax, eax
0x14004a307  mov     [rbp+StringBinding], 0
0x14004a30f  xorps   xmm0, xmm0
0x14004a312  mov     [rbp+var_10], rax
0x14004a316  mov     [rbp+cbSid], eax
0x14004a319  lea     rdx, ProtSeq; "ncalrpc"
0x14004a320  lea     rax, [rbp+StringBinding]
0x14004a324  mov     [rbp+Binding], 0
0x14004a32c  mov     rsi, r8
0x14004a32f  mov     [r11-60h], rax
0x14004a333  xor     edi, edi
0x14004a335  lea     rcx, ObjUuid; "201ef99a-7fa0-444c-9399-19ba84f12a1a"
0x14004a33c  xor     r9d, r9d; Endpoint
0x14004a33f  mov     [r11-68h], rdi
0x14004a343  xor     r8d, r8d; NetworkAddr
0x14004a346  movups  xmmword ptr [rbp+var_30.Version], xmm0
0x14004a34a  movups  [rbp+var_20], xmm0
0x14004a34e  call    cs:__imp_RpcStringBindingComposeW
0x14004a355  nop     dword ptr [rax+rax+00h]
0x14004a35a  mov     ebx, eax
0x14004a35c  test    eax, eax
0x14004a35e  jnz     loc_14004A43C
0x14004a364  mov     rcx, [rbp+StringBinding]; StringBinding
0x14004a368  lea     rdx, [rbp+Binding]; Binding
0x14004a36c  call    cs:__imp_RpcBindingFromStringBindingW
0x14004a373  nop     dword ptr [rax+rax+00h]
0x14004a378  lea     rcx, [rbp+StringBinding]; String
0x14004a37c  mov     ebx, eax
0x14004a37e  call    cs:__imp_RpcStringFreeW
0x14004a385  nop     dword ptr [rax+rax+00h]
0x14004a38a  test    ebx, ebx
0x14004a38c  jnz     loc_14004A43C
0x14004a392  lea     edx, [rdi+44h]; uBytes
0x14004a395  lea     ecx, [rdi+40h]; uFlags
0x14004a398  mov     [rbp+cbSid], edx
0x14004a39b  call    cs:__imp_LocalAlloc
0x14004a3a2  nop     dword ptr [rax+rax+00h]
0x14004a3a7  mov     rdi, rax
0x14004a3aa  test    rax, rax
0x14004a3ad  jnz     short loc_14004A3B7
0x14004a3af  lea     ebx, [rax+8]
0x14004a3b2  jmp     loc_14004A43C
0x14004a3b7  xor     edx, edx; DomainSid
0x14004a3b9  lea     r9, [rbp+cbSid]; cbSid
0x14004a3bd  mov     r8, rdi; pSid
0x14004a3c0  lea     ecx, [rdx+16h]; WellKnownSidType
0x14004a3c3  call    cs:__imp_CreateWellKnownSid
0x14004a3ca  nop     dword ptr [rax+rax+00h]
0x14004a3cf  test    eax, eax
0x14004a3d1  jnz     short loc_14004A3DC
0x14004a3d3  call    GetLastError_0
0x14004a3d8  mov     ebx, eax
0x14004a3da  jmp     short loc_14004A43C
0x14004a3dc  mov     rcx, [rbp+Binding]; Binding
0x14004a3e0  mov     eax, 3
0x14004a3e5  xor     edx, edx; ServerPrincName
0x14004a3e7  mov     [rbp+var_30.Version], eax
0x14004a3ea  mov     [rbp+var_30.ImpersonationType], eax
0x14004a3ed  lea     rax, [rbp+var_30]
0x14004a3f1  mov     [rsp+70h+SecurityQOS], rax; SecurityQOS
0x14004a3f6  mov     [rsp+70h+AuthzSvc], 0; AuthzSvc
0x14004a3fe  lea     r9d, [rdx+0Ah]; AuthnSvc
0x14004a402  mov     [rsp+70h+AuthIdentity], 0; AuthIdentity
0x14004a40b  lea     r8d, [rdx+6]; AuthnLevel
0x14004a40f  mov     qword ptr [rbp+var_30.Capabilities], 1
0x14004a417  mov     [rbp+var_10], rdi
0x14004a41b  call    cs:__imp_RpcBindingSetAuthInfoExW
0x14004a422  nop     dword ptr [rax+rax+00h]
0x14004a427  mov     ebx, eax
0x14004a429  test    eax, eax
0x14004a42b  jnz     short loc_14004A43C
0x14004a42d  mov     rax, [rbp+Binding]
0x14004a431  mov     [rsi], rax
0x14004a434  mov     [rbp+Binding], 0
0x14004a43c  mov     rcx, rdi; hMem
0x14004a43f  call    LocalFree_0
0x14004a444  cmp     [rbp+Binding], 0
0x14004a449  jz      short loc_14004A45B
0x14004a44b  lea     rcx, [rbp+Binding]; Binding
0x14004a44f  call    cs:__imp_RpcBindingFree
0x14004a456  nop     dword ptr [rax+rax+00h]
0x14004a45b  mov     eax, ebx
0x14004a45d  mov     rbx, [rsp+70h+arg_10]
0x14004a465  add     rsp, 70h
0x14004a469  pop     rdi
0x14004a46a  pop     rsi
0x14004a46b  pop     rbp
0x14004a46c  retn
```
