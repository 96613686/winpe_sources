# AicpCreateBindingHandle(ushort *,int,void * *)

- ea: `0x1400122d0`
- end: `0x140012423`
- name: `?AicpCreateBindingHandle@@YAKPEAGHPEAPEAX@Z`
- size: `339`
- prototype: `unsigned int __fastcall(unsigned __int16 *, int, void **)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x140012138`

## callees

- `0x1400122d0`
- `0x14010582f`
- `0x1401058d7`
- `0x1401058e3`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x14001238b`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x14001238b`
- `RPCRT4!RpcBindingFree` at `0x14001240b`
- `RPCRT4!RpcBindingFree` at `0x14001240b`
- `RPCRT4!RpcStringFreeW` at `0x140012356`
- `RPCRT4!RpcStringFreeW` at `0x140012356`
- `RPCRT4!RpcBindingSetAuthInfoExW` at `0x1400123dd`
- `RPCRT4!RpcBindingSetAuthInfoExW` at `0x1400123dd`
- `RPCRT4!RpcStringBindingComposeW` at `0x140012332`
- `RPCRT4!RpcStringBindingComposeW` at `0x140012332`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x14001234a`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x14001234a`

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
0x1400122d0  mov     r11, rsp
0x1400122d3  mov     [r11+18h], rbx
0x1400122d7  mov     [rsp-18h+cbSid], edx
0x1400122db  mov     [r11+8], rcx
0x1400122df  push    rbp
0x1400122e0  push    rsi
0x1400122e1  push    rdi
0x1400122e2  mov     rbp, rsp
0x1400122e5  sub     rsp, 70h
0x1400122e9  xor     eax, eax
0x1400122eb  mov     [rbp+StringBinding], 0
0x1400122f3  xorps   xmm0, xmm0
0x1400122f6  mov     [rbp+var_10], rax
0x1400122fa  mov     [rbp+cbSid], eax
0x1400122fd  lea     rdx, ProtSeq; "ncalrpc"
0x140012304  lea     rax, [rbp+StringBinding]
0x140012308  mov     [rbp+Binding], 0
0x140012310  mov     rsi, r8
0x140012313  mov     [r11-60h], rax
0x140012317  xor     edi, edi
0x140012319  lea     rcx, ObjUuid; "201ef99a-7fa0-444c-9399-19ba84f12a1a"
0x140012320  xor     r9d, r9d; Endpoint
0x140012323  mov     [r11-68h], rdi
0x140012327  xor     r8d, r8d; NetworkAddr
0x14001232a  movups  xmmword ptr [rbp+var_30.Version], xmm0
0x14001232e  movups  [rbp+var_20], xmm0
0x140012332  call    cs:__imp_RpcStringBindingComposeW
0x140012338  mov     ebx, eax
0x14001233a  test    eax, eax
0x14001233c  jnz     loc_1400123F8
0x140012342  mov     rcx, [rbp+StringBinding]; StringBinding
0x140012346  lea     rdx, [rbp+Binding]; Binding
0x14001234a  call    cs:__imp_RpcBindingFromStringBindingW
0x140012350  lea     rcx, [rbp+StringBinding]; String
0x140012354  mov     ebx, eax
0x140012356  call    cs:__imp_RpcStringFreeW
0x14001235c  test    ebx, ebx
0x14001235e  jnz     loc_1400123F8
0x140012364  lea     edx, [rdi+44h]; uBytes
0x140012367  lea     ecx, [rdi+40h]; uFlags
0x14001236a  mov     [rbp+cbSid], edx
0x14001236d  call    LocalAlloc_0
0x140012372  mov     rdi, rax
0x140012375  test    rax, rax
0x140012378  jnz     short loc_14001237F
0x14001237a  lea     ebx, [rax+8]
0x14001237d  jmp     short loc_1400123F8
0x14001237f  xor     edx, edx; DomainSid
0x140012381  lea     r9, [rbp+cbSid]; cbSid
0x140012385  mov     r8, rdi; pSid
0x140012388  lea     ecx, [rdx+16h]; WellKnownSidType
0x14001238b  call    cs:__imp_CreateWellKnownSid
0x140012391  test    eax, eax
0x140012393  jnz     short loc_14001239E
0x140012395  call    GetLastError_0
0x14001239a  mov     ebx, eax
0x14001239c  jmp     short loc_1400123F8
0x14001239e  mov     rcx, [rbp+Binding]; Binding
0x1400123a2  mov     eax, 3
0x1400123a7  xor     edx, edx; ServerPrincName
0x1400123a9  mov     [rbp+var_30.Version], eax
0x1400123ac  mov     [rbp+var_30.ImpersonationType], eax
0x1400123af  lea     rax, [rbp+var_30]
0x1400123b3  mov     [rsp+70h+SecurityQOS], rax; SecurityQOS
0x1400123b8  mov     [rsp+70h+AuthzSvc], 0; AuthzSvc
0x1400123c0  lea     r9d, [rdx+0Ah]; AuthnSvc
0x1400123c4  mov     [rsp+70h+AuthIdentity], 0; AuthIdentity
0x1400123cd  lea     r8d, [rdx+6]; AuthnLevel
0x1400123d1  mov     qword ptr [rbp+var_30.Capabilities], 1
0x1400123d9  mov     [rbp+var_10], rdi
0x1400123dd  call    cs:__imp_RpcBindingSetAuthInfoExW
0x1400123e3  mov     ebx, eax
0x1400123e5  test    eax, eax
0x1400123e7  jnz     short loc_1400123F8
0x1400123e9  mov     rax, [rbp+Binding]
0x1400123ed  mov     [rsi], rax
0x1400123f0  mov     [rbp+Binding], 0
0x1400123f8  mov     rcx, rdi; hMem
0x1400123fb  call    LocalFree_0
0x140012400  cmp     [rbp+Binding], 0
0x140012405  jz      short loc_140012411
0x140012407  lea     rcx, [rbp+Binding]; Binding
0x14001240b  call    cs:__imp_RpcBindingFree
0x140012411  mov     eax, ebx
0x140012413  mov     rbx, [rsp+70h+arg_10]
0x14001241b  add     rsp, 70h
0x14001241f  pop     rdi
0x140012420  pop     rsi
0x140012421  pop     rbp
0x140012422  retn
```
