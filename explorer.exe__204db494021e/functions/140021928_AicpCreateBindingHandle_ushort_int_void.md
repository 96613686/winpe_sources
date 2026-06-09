# AicpCreateBindingHandle(ushort *,int,void * *)

- ea: `0x140021928`
- end: `0x140021aa3`
- name: `?AicpCreateBindingHandle@@YAKPEAGHPEAPEAX@Z`
- size: `379`
- prototype: `unsigned int __fastcall(unsigned __int16 *, int, void **)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x140021780`

## callees

- `0x140021928`
- `0x14010f88b`
- `0x14010f933`
- `0x14010f93f`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x1400219f8`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x1400219f8`
- `RPCRT4!RpcBindingFree` at `0x140021a84`
- `RPCRT4!RpcBindingFree` at `0x140021a84`
- `RPCRT4!RpcStringFreeW` at `0x1400219ba`
- `RPCRT4!RpcStringFreeW` at `0x1400219ba`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x1400219a8`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x1400219a8`
- `RPCRT4!RpcStringBindingComposeW` at `0x14002198a`
- `RPCRT4!RpcStringBindingComposeW` at `0x14002198a`
- `RPCRT4!RpcBindingSetAuthInfoExW` at `0x140021a50`
- `RPCRT4!RpcBindingSetAuthInfoExW` at `0x140021a50`

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
0x140021928  mov     r11, rsp
0x14002192b  mov     [r11+18h], rbx
0x14002192f  mov     [rsp-18h+cbSid], edx
0x140021933  mov     [r11+8], rcx
0x140021937  push    rbp
0x140021938  push    rsi
0x140021939  push    rdi
0x14002193a  mov     rbp, rsp
0x14002193d  sub     rsp, 70h
0x140021941  xor     eax, eax
0x140021943  mov     [rbp+StringBinding], 0
0x14002194b  xorps   xmm0, xmm0
0x14002194e  mov     [rbp+var_10], rax
0x140021952  mov     [rbp+cbSid], eax
0x140021955  lea     rdx, ProtSeq; "ncalrpc"
0x14002195c  lea     rax, [rbp+StringBinding]
0x140021960  mov     [rbp+Binding], 0
0x140021968  mov     rsi, r8
0x14002196b  mov     [r11-60h], rax
0x14002196f  xor     edi, edi
0x140021971  lea     rcx, ObjUuid; "201ef99a-7fa0-444c-9399-19ba84f12a1a"
0x140021978  xor     r9d, r9d; Endpoint
0x14002197b  mov     [r11-68h], rdi
0x14002197f  xor     r8d, r8d; NetworkAddr
0x140021982  movups  xmmword ptr [rbp+var_30.Version], xmm0
0x140021986  movups  [rbp+var_20], xmm0
0x14002198a  call    cs:__imp_RpcStringBindingComposeW
0x140021991  nop     dword ptr [rax+rax+00h]
0x140021996  mov     ebx, eax
0x140021998  test    eax, eax
0x14002199a  jnz     loc_140021A71
0x1400219a0  mov     rcx, [rbp+StringBinding]; StringBinding
0x1400219a4  lea     rdx, [rbp+Binding]; Binding
0x1400219a8  call    cs:__imp_RpcBindingFromStringBindingW
0x1400219af  nop     dword ptr [rax+rax+00h]
0x1400219b4  lea     rcx, [rbp+StringBinding]; String
0x1400219b8  mov     ebx, eax
0x1400219ba  call    cs:__imp_RpcStringFreeW
0x1400219c1  nop     dword ptr [rax+rax+00h]
0x1400219c6  test    ebx, ebx
0x1400219c8  jnz     loc_140021A71
0x1400219ce  lea     edx, [rdi+44h]; uBytes
0x1400219d1  lea     ecx, [rdi+40h]; uFlags
0x1400219d4  mov     [rbp+cbSid], edx
0x1400219d7  call    LocalAlloc_0
0x1400219dc  mov     rdi, rax
0x1400219df  test    rax, rax
0x1400219e2  jnz     short loc_1400219EC
0x1400219e4  lea     ebx, [rax+8]
0x1400219e7  jmp     loc_140021A71
0x1400219ec  xor     edx, edx; DomainSid
0x1400219ee  lea     r9, [rbp+cbSid]; cbSid
0x1400219f2  mov     r8, rdi; pSid
0x1400219f5  lea     ecx, [rdx+16h]; WellKnownSidType
0x1400219f8  call    cs:__imp_CreateWellKnownSid
0x1400219ff  nop     dword ptr [rax+rax+00h]
0x140021a04  test    eax, eax
0x140021a06  jnz     short loc_140021A11
0x140021a08  call    GetLastError_0
0x140021a0d  mov     ebx, eax
0x140021a0f  jmp     short loc_140021A71
0x140021a11  mov     rcx, [rbp+Binding]; Binding
0x140021a15  mov     eax, 3
0x140021a1a  xor     edx, edx; ServerPrincName
0x140021a1c  mov     [rbp+var_30.Version], eax
0x140021a1f  mov     [rbp+var_30.ImpersonationType], eax
0x140021a22  lea     rax, [rbp+var_30]
0x140021a26  mov     [rsp+70h+SecurityQOS], rax; SecurityQOS
0x140021a2b  mov     [rsp+70h+AuthzSvc], 0; AuthzSvc
0x140021a33  lea     r9d, [rdx+0Ah]; AuthnSvc
0x140021a37  mov     [rsp+70h+AuthIdentity], 0; AuthIdentity
0x140021a40  lea     r8d, [rdx+6]; AuthnLevel
0x140021a44  mov     qword ptr [rbp+var_30.Capabilities], 1
0x140021a4c  mov     [rbp+var_10], rdi
0x140021a50  call    cs:__imp_RpcBindingSetAuthInfoExW
0x140021a57  nop     dword ptr [rax+rax+00h]
0x140021a5c  mov     ebx, eax
0x140021a5e  test    eax, eax
0x140021a60  jnz     short loc_140021A71
0x140021a62  mov     rax, [rbp+Binding]
0x140021a66  mov     [rsi], rax
0x140021a69  mov     [rbp+Binding], 0
0x140021a71  mov     rcx, rdi; hMem
0x140021a74  call    LocalFree_0
0x140021a79  cmp     [rbp+Binding], 0
0x140021a7e  jz      short loc_140021A90
0x140021a80  lea     rcx, [rbp+Binding]; Binding
0x140021a84  call    cs:__imp_RpcBindingFree
0x140021a8b  nop     dword ptr [rax+rax+00h]
0x140021a90  mov     eax, ebx
0x140021a92  mov     rbx, [rsp+70h+arg_10]
0x140021a9a  add     rsp, 70h
0x140021a9e  pop     rdi
0x140021a9f  pop     rsi
0x140021aa0  pop     rbp
0x140021aa1  retn
```
