# AicpCreateBindingHandle(ushort *,int,void * *)

- ea: `0x1800af31c`
- end: `0x1800af4a0`
- name: `?AicpCreateBindingHandle@@YAKPEAGHPEAPEAX@Z`
- size: `388`
- prototype: `unsigned int __fastcall(unsigned __int16 *, int, void **)`
- caller_count: `4`
- callee_count: `1`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x1800af0b4`
- `0x1800af520`
- `0x1800af68c`
- `0x1800af80c`

## callees

- `0x1800af31c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800af3fd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800af3fd`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800af3c5`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800af3c5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800af46a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800af46a`
- `RPCRT4!RpcBindingSetAuthInfoExW` at `0x1800af449`
- `RPCRT4!RpcBindingSetAuthInfoExW` at `0x1800af449`
- `RPCRT4!RpcStringFreeW` at `0x1800af3a8`
- `RPCRT4!RpcStringFreeW` at `0x1800af3a8`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x1800af396`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x1800af396`
- `RPCRT4!RpcStringBindingComposeW` at `0x1800af378`
- `RPCRT4!RpcStringBindingComposeW` at `0x1800af378`
- `RPCRT4!RpcBindingFree` at `0x1800af481`
- `RPCRT4!RpcBindingFree` at `0x1800af481`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x1800af3ed`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x1800af3ed`

## pseudocode

```c
__int64 __fastcall AicpCreateBindingHandle(unsigned __int16 *a1, __int64 a2, void **a3)
{
  void *v4; // rdi
  DWORD LastError; // ebx
  HLOCAL v6; // rax
  RPC_BINDING_HANDLE v7; // rax
  RPC_SECURITY_QOS SecurityQOS; // [rsp+40h] [rbp-30h] BYREF
  __int128 v10; // [rsp+50h] [rbp-20h]
  void *v11; // [rsp+60h] [rbp-10h]
  RPC_BINDING_HANDLE Binding; // [rsp+90h] [rbp+20h] BYREF
  DWORD cbSid; // [rsp+98h] [rbp+28h] BYREF
  RPC_WSTR StringBinding; // [rsp+A8h] [rbp+38h] BYREF

  StringBinding = 0;
  Binding = 0;
  cbSid = 0;
  v11 = 0;
  v4 = 0;
  SecurityQOS = 0;
  v10 = 0;
  LastError = RpcStringBindingComposeW(
                (RPC_WSTR)L"0497B57D-2E66-424F-A0C6-157CD5D41700",
                (RPC_WSTR)L"ncalrpc",
                0,
                0,
                0,
                &StringBinding);
  if ( !LastError )
  {
    LastError = RpcBindingFromStringBindingW(StringBinding, &Binding);
    RpcStringFreeW(&StringBinding);
    if ( !LastError )
    {
      cbSid = 68;
      v6 = LocalAlloc(0x40u, 0x44u);
      v4 = v6;
      if ( v6 )
      {
        if ( CreateWellKnownSid(WinLocalSystemSid, 0, v6, &cbSid) )
        {
          SecurityQOS.IdentityTracking = 0;
          SecurityQOS.Version = 3;
          SecurityQOS.ImpersonationType = 3;
          SecurityQOS.Capabilities = 1;
          v11 = v4;
          LastError = RpcBindingSetAuthInfoExW(Binding, 0, 6u, 0xAu, 0, 0, &SecurityQOS);
          if ( !LastError )
          {
            v7 = Binding;
            Binding = 0;
            *a3 = v7;
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
0x1800af31c  mov     r11, rsp
0x1800af31f  mov     [r11+18h], rbx
0x1800af323  mov     [rsp-18h+cbSid], edx
0x1800af327  mov     [r11+8], rcx
0x1800af32b  push    rbp
0x1800af32c  push    rsi
0x1800af32d  push    rdi
0x1800af32e  mov     rbp, rsp
0x1800af331  sub     rsp, 70h
0x1800af335  and     [rbp+StringBinding], 0
0x1800af33a  lea     rdx, ProtSeq; "ncalrpc"
0x1800af341  and     [rbp+Binding], 0
0x1800af346  lea     rcx, ObjUuid; "0497B57D-2E66-424F-A0C6-157CD5D41700"
0x1800af34d  xor     eax, eax
0x1800af34f  xorps   xmm0, xmm0
0x1800af352  and     [rbp+cbSid], eax
0x1800af355  mov     rsi, r8
0x1800af358  mov     [rbp+var_10], rax
0x1800af35c  xor     edi, edi
0x1800af35e  lea     rax, [rbp+StringBinding]
0x1800af362  xor     r9d, r9d; Endpoint
0x1800af365  mov     [r11-60h], rax
0x1800af369  xor     r8d, r8d; NetworkAddr
0x1800af36c  and     [r11-68h], rdi
0x1800af370  movups  xmmword ptr [rbp+var_30.Version], xmm0
0x1800af374  movups  [rbp+var_20], xmm0
0x1800af378  call    cs:__imp_RpcStringBindingComposeW
0x1800af37f  nop     dword ptr [rax+rax+00h]
0x1800af384  mov     ebx, eax
0x1800af386  test    eax, eax
0x1800af388  jnz     loc_1800AF467
0x1800af38e  mov     rcx, [rbp+StringBinding]; StringBinding
0x1800af392  lea     rdx, [rbp+Binding]; Binding
0x1800af396  call    cs:__imp_RpcBindingFromStringBindingW
0x1800af39d  nop     dword ptr [rax+rax+00h]
0x1800af3a2  lea     rcx, [rbp+StringBinding]; String
0x1800af3a6  mov     ebx, eax
0x1800af3a8  call    cs:__imp_RpcStringFreeW
0x1800af3af  nop     dword ptr [rax+rax+00h]
0x1800af3b4  test    ebx, ebx
0x1800af3b6  jnz     loc_1800AF467
0x1800af3bc  lea     edx, [rdi+44h]; uBytes
0x1800af3bf  lea     ecx, [rdi+40h]; uFlags
0x1800af3c2  mov     [rbp+cbSid], edx
0x1800af3c5  call    cs:__imp_LocalAlloc
0x1800af3cc  nop     dword ptr [rax+rax+00h]
0x1800af3d1  mov     rdi, rax
0x1800af3d4  test    rax, rax
0x1800af3d7  jnz     short loc_1800AF3E1
0x1800af3d9  lea     ebx, [rax+8]
0x1800af3dc  jmp     loc_1800AF467
0x1800af3e1  xor     edx, edx; DomainSid
0x1800af3e3  lea     r9, [rbp+cbSid]; cbSid
0x1800af3e7  mov     r8, rdi; pSid
0x1800af3ea  lea     ecx, [rdx+16h]; WellKnownSidType
0x1800af3ed  call    cs:__imp_CreateWellKnownSid
0x1800af3f4  nop     dword ptr [rax+rax+00h]
0x1800af3f9  test    eax, eax
0x1800af3fb  jnz     short loc_1800AF40D
0x1800af3fd  call    cs:__imp_GetLastError
0x1800af404  nop     dword ptr [rax+rax+00h]
0x1800af409  mov     ebx, eax
0x1800af40b  jmp     short loc_1800AF467
0x1800af40d  mov     rcx, [rbp+Binding]; Binding
0x1800af411  mov     eax, 3
0x1800af416  and     [rbp+var_30.IdentityTracking], 0
0x1800af41a  xor     edx, edx; ServerPrincName
0x1800af41c  mov     [rbp+var_30.Version], eax
0x1800af41f  mov     [rbp+var_30.ImpersonationType], eax
0x1800af422  lea     rax, [rbp+var_30]
0x1800af426  mov     [rsp+70h+SecurityQOS], rax; SecurityQOS
0x1800af42b  and     [rsp+70h+var_48], 0
0x1800af430  lea     r9d, [rdx+0Ah]; AuthnSvc
0x1800af434  and     [rsp+70h+var_50], 0
0x1800af43a  lea     r8d, [rdx+6]; AuthnLevel
0x1800af43e  mov     [rbp+var_30.Capabilities], 1
0x1800af445  mov     [rbp+var_10], rdi
0x1800af449  call    cs:__imp_RpcBindingSetAuthInfoExW
0x1800af450  nop     dword ptr [rax+rax+00h]
0x1800af455  mov     ebx, eax
0x1800af457  test    eax, eax
0x1800af459  jnz     short loc_1800AF467
0x1800af45b  mov     rax, [rbp+Binding]
0x1800af45f  and     [rbp+Binding], 0
0x1800af464  mov     [rsi], rax
0x1800af467  mov     rcx, rdi; hMem
0x1800af46a  call    cs:__imp_LocalFree
0x1800af471  nop     dword ptr [rax+rax+00h]
0x1800af476  cmp     [rbp+Binding], 0
0x1800af47b  jz      short loc_1800AF48D
0x1800af47d  lea     rcx, [rbp+Binding]; Binding
0x1800af481  call    cs:__imp_RpcBindingFree
0x1800af488  nop     dword ptr [rax+rax+00h]
0x1800af48d  mov     eax, ebx
0x1800af48f  mov     rbx, [rsp+70h+arg_10]
0x1800af497  add     rsp, 70h
0x1800af49b  pop     rdi
0x1800af49c  pop     rsi
0x1800af49d  pop     rbp
0x1800af49e  retn
```
