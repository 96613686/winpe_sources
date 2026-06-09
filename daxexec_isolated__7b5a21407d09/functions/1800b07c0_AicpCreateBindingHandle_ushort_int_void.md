# AicpCreateBindingHandle(ushort *,int,void * *)

- ea: `0x1800b07c0`
- end: `0x1800b0945`
- name: `?AicpCreateBindingHandle@@YAKPEAGHPEAPEAX@Z`
- size: `389`
- prototype: `unsigned int __fastcall(unsigned __int16 *, int, void **)`
- caller_count: `5`
- callee_count: `1`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x1800b0548`
- `0x1800b1074`
- `0x1800b11e0`
- `0x1800b137c`
- `0x1800b19e4`

## callees

- `0x1800b07c0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b089c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b089c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800b090f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800b090f`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800b0864`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800b0864`
- `RPCRT4!RpcStringFreeW` at `0x1800b0847`
- `RPCRT4!RpcStringFreeW` at `0x1800b0847`
- `RPCRT4!RpcBindingSetAuthInfoExW` at `0x1800b08eb`
- `RPCRT4!RpcBindingSetAuthInfoExW` at `0x1800b08eb`
- `RPCRT4!RpcStringBindingComposeW` at `0x1800b0817`
- `RPCRT4!RpcStringBindingComposeW` at `0x1800b0817`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x1800b0835`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x1800b0835`
- `RPCRT4!RpcBindingFree` at `0x1800b0926`
- `RPCRT4!RpcBindingFree` at `0x1800b0926`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x1800b088c`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x1800b088c`

## pseudocode

```c
__int64 __fastcall AicpCreateBindingHandle(unsigned __int16 *a1, __int64 a2, void **a3)
{
  void *v4; // rdi
  DWORD LastError; // ebx
  HLOCAL v6; // rax
  RPC_WSTR String; // [rsp+40h] [rbp-30h] BYREF
  RPC_SECURITY_QOS SecurityQOS; // [rsp+48h] [rbp-28h] BYREF
  __int128 v10; // [rsp+58h] [rbp-18h]
  void *v11; // [rsp+68h] [rbp-8h]
  DWORD cbSid; // [rsp+98h] [rbp+28h] BYREF
  RPC_BINDING_HANDLE Binding; // [rsp+A8h] [rbp+38h] BYREF

  String = 0;
  v11 = 0;
  cbSid = 0;
  Binding = 0;
  v4 = 0;
  SecurityQOS = 0;
  v10 = 0;
  LastError = RpcStringBindingComposeW(a1, (RPC_WSTR)L"ncalrpc", 0, 0, 0, &String);
  if ( !LastError )
  {
    LastError = RpcBindingFromStringBindingW(String, &Binding);
    RpcStringFreeW(&String);
    if ( !LastError )
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
          v11 = v4;
          LastError = RpcBindingSetAuthInfoExW(Binding, 0, 6u, 0xAu, 0, 0, &SecurityQOS);
          if ( !LastError )
          {
            *a3 = Binding;
            Binding = 0;
          }
        }
        else
        {
          LastError = GetLastError();
        }
      }
      else
      {
        LastError = 8;
      }
    }
  }
  LocalFree(v4);
  if ( Binding )
    RpcBindingFree(&Binding);
  return LastError;
}

```

## disassembly

```asm
0x1800b07c0  mov     [rsp-18h+arg_0], rbx
0x1800b07c5  mov     [rsp-18h+cbSid], edx
0x1800b07c9  push    rbp
0x1800b07ca  push    rsi
0x1800b07cb  push    rdi
0x1800b07cc  mov     rbp, rsp
0x1800b07cf  sub     rsp, 70h
0x1800b07d3  xor     eax, eax
0x1800b07d5  mov     [rbp+String], 0
0x1800b07dd  xorps   xmm0, xmm0
0x1800b07e0  mov     [rbp+var_8], rax
0x1800b07e4  mov     [rbp+cbSid], eax
0x1800b07e7  lea     rdx, ProtSeq; "ncalrpc"
0x1800b07ee  lea     rax, [rbp+String]
0x1800b07f2  mov     [rbp+Binding], 0
0x1800b07fa  mov     rsi, r8
0x1800b07fd  mov     [rsp+70h+StringBinding], rax; StringBinding
0x1800b0802  xor     edi, edi
0x1800b0804  xor     r9d, r9d; Endpoint
0x1800b0807  xor     r8d, r8d; NetworkAddr
0x1800b080a  mov     [rsp+70h+Options], rdi; Options
0x1800b080f  movups  xmmword ptr [rbp+var_28.Version], xmm0
0x1800b0813  movups  [rbp+var_18], xmm0
0x1800b0817  call    cs:__imp_RpcStringBindingComposeW
0x1800b081e  nop     dword ptr [rax+rax+00h]
0x1800b0823  mov     ebx, eax
0x1800b0825  test    eax, eax
0x1800b0827  jnz     loc_1800B090C
0x1800b082d  mov     rcx, [rbp+String]; StringBinding
0x1800b0831  lea     rdx, [rbp+Binding]; Binding
0x1800b0835  call    cs:__imp_RpcBindingFromStringBindingW
0x1800b083c  nop     dword ptr [rax+rax+00h]
0x1800b0841  lea     rcx, [rbp+String]; String
0x1800b0845  mov     ebx, eax
0x1800b0847  call    cs:__imp_RpcStringFreeW
0x1800b084e  nop     dword ptr [rax+rax+00h]
0x1800b0853  test    ebx, ebx
0x1800b0855  jnz     loc_1800B090C
0x1800b085b  lea     edx, [rdi+44h]; uBytes
0x1800b085e  lea     ecx, [rdi+40h]; uFlags
0x1800b0861  mov     [rbp+cbSid], edx
0x1800b0864  call    cs:__imp_LocalAlloc
0x1800b086b  nop     dword ptr [rax+rax+00h]
0x1800b0870  mov     rdi, rax
0x1800b0873  test    rax, rax
0x1800b0876  jnz     short loc_1800B0880
0x1800b0878  lea     ebx, [rax+8]
0x1800b087b  jmp     loc_1800B090C
0x1800b0880  xor     edx, edx; DomainSid
0x1800b0882  lea     r9, [rbp+cbSid]; cbSid
0x1800b0886  mov     r8, rdi; pSid
0x1800b0889  lea     ecx, [rdx+16h]; WellKnownSidType
0x1800b088c  call    cs:__imp_CreateWellKnownSid
0x1800b0893  nop     dword ptr [rax+rax+00h]
0x1800b0898  test    eax, eax
0x1800b089a  jnz     short loc_1800B08AC
0x1800b089c  call    cs:__imp_GetLastError
0x1800b08a3  nop     dword ptr [rax+rax+00h]
0x1800b08a8  mov     ebx, eax
0x1800b08aa  jmp     short loc_1800B090C
0x1800b08ac  mov     rcx, [rbp+Binding]; Binding
0x1800b08b0  mov     eax, 3
0x1800b08b5  xor     edx, edx; ServerPrincName
0x1800b08b7  mov     [rbp+var_28.Version], eax
0x1800b08ba  mov     [rbp+var_28.ImpersonationType], eax
0x1800b08bd  lea     rax, [rbp+var_28]
0x1800b08c1  mov     [rsp+70h+SecurityQOS], rax; SecurityQOS
0x1800b08c6  mov     dword ptr [rsp+70h+StringBinding], 0; AuthzSvc
0x1800b08ce  lea     r9d, [rdx+0Ah]; AuthnSvc
0x1800b08d2  mov     [rsp+70h+Options], 0; AuthIdentity
0x1800b08db  lea     r8d, [rdx+6]; AuthnLevel
0x1800b08df  mov     qword ptr [rbp+var_28.Capabilities], 1
0x1800b08e7  mov     [rbp+var_8], rdi
0x1800b08eb  call    cs:__imp_RpcBindingSetAuthInfoExW
0x1800b08f2  nop     dword ptr [rax+rax+00h]
0x1800b08f7  mov     ebx, eax
0x1800b08f9  test    eax, eax
0x1800b08fb  jnz     short loc_1800B090C
0x1800b08fd  mov     rax, [rbp+Binding]
0x1800b0901  mov     [rsi], rax
0x1800b0904  mov     [rbp+Binding], 0
0x1800b090c  mov     rcx, rdi; hMem
0x1800b090f  call    cs:__imp_LocalFree
0x1800b0916  nop     dword ptr [rax+rax+00h]
0x1800b091b  cmp     [rbp+Binding], 0
0x1800b0920  jz      short loc_1800B0932
0x1800b0922  lea     rcx, [rbp+Binding]; Binding
0x1800b0926  call    cs:__imp_RpcBindingFree
0x1800b092d  nop     dword ptr [rax+rax+00h]
0x1800b0932  mov     eax, ebx
0x1800b0934  mov     rbx, [rsp+70h+arg_0]
0x1800b093c  add     rsp, 70h
0x1800b0940  pop     rdi
0x1800b0941  pop     rsi
0x1800b0942  pop     rbp
0x1800b0943  retn
```
