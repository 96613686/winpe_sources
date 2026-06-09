# AicpCreateBindingHandle(ushort *,int,void * *)

- ea: `0x18009387c`
- end: `0x1800939d0`
- name: `?AicpCreateBindingHandle@@YAKPEAGHPEAPEAX@Z`
- size: `340`
- prototype: `unsigned int __fastcall(unsigned __int16 *, int, void **)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x1800935b8`

## callees

- `0x18004c123`
- `0x18004c13b`
- `0x18004c147`
- `0x18009387c`

## import_xrefs

- `RPCRT4!RpcStringFreeW` at `0x180093902`
- `RPCRT4!RpcStringFreeW` at `0x180093902`
- `RPCRT4!RpcBindingFree` at `0x1800939b8`
- `RPCRT4!RpcBindingFree` at `0x1800939b8`
- `RPCRT4!RpcBindingSetAuthInfoExW` at `0x18009398a`
- `RPCRT4!RpcBindingSetAuthInfoExW` at `0x18009398a`
- `RPCRT4!RpcStringBindingComposeW` at `0x1800938de`
- `RPCRT4!RpcStringBindingComposeW` at `0x1800938de`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x1800938f6`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x1800938f6`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x180093937`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x180093937`

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
0x18009387c  mov     r11, rsp
0x18009387f  mov     [r11+18h], rbx
0x180093883  mov     [rsp-18h+cbSid], edx
0x180093887  mov     [r11+8], rcx
0x18009388b  push    rbp
0x18009388c  push    rsi
0x18009388d  push    rdi
0x18009388e  mov     rbp, rsp
0x180093891  sub     rsp, 70h
0x180093895  xor     eax, eax
0x180093897  mov     [rbp+StringBinding], 0
0x18009389f  xorps   xmm0, xmm0
0x1800938a2  mov     [rbp+var_10], rax
0x1800938a6  mov     [rbp+cbSid], eax
0x1800938a9  lea     rdx, ProtSeq; "ncalrpc"
0x1800938b0  lea     rax, [rbp+StringBinding]
0x1800938b4  mov     [rbp+Binding], 0
0x1800938bc  mov     rsi, r8
0x1800938bf  mov     [r11-60h], rax
0x1800938c3  xor     edi, edi
0x1800938c5  lea     rcx, ObjUuid; "201ef99a-7fa0-444c-9399-19ba84f12a1a"
0x1800938cc  xor     r9d, r9d; Endpoint
0x1800938cf  mov     [r11-68h], rdi
0x1800938d3  xor     r8d, r8d; NetworkAddr
0x1800938d6  movups  xmmword ptr [rbp+var_30.Version], xmm0
0x1800938da  movups  [rbp+var_20], xmm0
0x1800938de  call    cs:__imp_RpcStringBindingComposeW
0x1800938e4  mov     ebx, eax
0x1800938e6  test    eax, eax
0x1800938e8  jnz     loc_1800939A5
0x1800938ee  mov     rcx, [rbp+StringBinding]; StringBinding
0x1800938f2  lea     rdx, [rbp+Binding]; Binding
0x1800938f6  call    cs:__imp_RpcBindingFromStringBindingW
0x1800938fc  lea     rcx, [rbp+StringBinding]; String
0x180093900  mov     ebx, eax
0x180093902  call    cs:__imp_RpcStringFreeW
0x180093908  test    ebx, ebx
0x18009390a  jnz     loc_1800939A5
0x180093910  lea     edx, [rdi+44h]; uBytes
0x180093913  lea     ecx, [rdi+40h]; uFlags
0x180093916  mov     [rbp+cbSid], edx
0x180093919  call    LocalAlloc_0
0x18009391e  mov     rdi, rax
0x180093921  test    rax, rax
0x180093924  jnz     short loc_18009392B
0x180093926  lea     ebx, [rax+8]
0x180093929  jmp     short loc_1800939A5
0x18009392b  xor     edx, edx; DomainSid
0x18009392d  lea     r9, [rbp+cbSid]; cbSid
0x180093931  mov     r8, rdi; pSid
0x180093934  lea     ecx, [rdx+16h]; WellKnownSidType
0x180093937  call    cs:__imp_CreateWellKnownSid
0x18009393d  test    eax, eax
0x18009393f  jnz     short loc_18009394A
0x180093941  call    GetLastError_0
0x180093946  mov     ebx, eax
0x180093948  jmp     short loc_1800939A5
0x18009394a  mov     ecx, 3
0x18009394f  mov     [rbp+var_10], rdi
0x180093953  mov     [rbp+var_30.Version], ecx
0x180093956  xor     edx, edx; ServerPrincName
0x180093958  mov     [rbp+var_30.ImpersonationType], ecx
0x18009395b  lea     eax, [rcx-2]
0x18009395e  mov     [rbp+var_30.Capabilities], eax
0x180093961  lea     r9d, [rcx+7]; AuthnSvc
0x180093965  mov     [rbp+var_30.IdentityTracking], eax
0x180093968  lea     r8d, [rcx+3]; AuthnLevel
0x18009396c  mov     rcx, [rbp+Binding]; Binding
0x180093970  lea     rax, [rbp+var_30]
0x180093974  mov     [rsp+70h+SecurityQOS], rax; SecurityQOS
0x180093979  mov     [rsp+70h+AuthzSvc], 0; AuthzSvc
0x180093981  mov     [rsp+70h+AuthIdentity], 0; AuthIdentity
0x18009398a  call    cs:__imp_RpcBindingSetAuthInfoExW
0x180093990  mov     ebx, eax
0x180093992  test    eax, eax
0x180093994  jnz     short loc_1800939A5
0x180093996  mov     rax, [rbp+Binding]
0x18009399a  mov     [rsi], rax
0x18009399d  mov     [rbp+Binding], 0
0x1800939a5  mov     rcx, rdi; hMem
0x1800939a8  call    LocalFree_0
0x1800939ad  cmp     [rbp+Binding], 0
0x1800939b2  jz      short loc_1800939BE
0x1800939b4  lea     rcx, [rbp+Binding]; Binding
0x1800939b8  call    cs:__imp_RpcBindingFree
0x1800939be  mov     eax, ebx
0x1800939c0  mov     rbx, [rsp+70h+arg_10]
0x1800939c8  add     rsp, 70h
0x1800939cc  pop     rdi
0x1800939cd  pop     rsi
0x1800939ce  pop     rbp
0x1800939cf  retn
```
