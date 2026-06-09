# AicpCreateBindingHandle(ushort *,int,void * *)

- ea: `0x18003b550`
- end: `0x18003b6a6`
- name: `?AicpCreateBindingHandle@@YAKPEAGHPEAPEAX@Z`
- size: `342`
- prototype: `__int64 __fastcall(unsigned __int16 *, __int64, void **)`
- caller_count: `3`
- callee_count: `1`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x18003af40`
- `0x18003b114`
- `0x18003b300`

## callees

- `0x18003b550`

## import_xrefs

- `KERNELBASE!LocalAlloc` at `0x18003b5ed`
- `KERNELBASE!LocalAlloc` at `0x18003b5ed`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003b67d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003b67d`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x18003b60c`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x18003b60c`
- `RPCRT4!RpcBindingFree` at `0x18003b68e`
- `RPCRT4!RpcBindingFree` at `0x18003b68e`
- `RPCRT4!RpcStringFreeW` at `0x18003b5d6`
- `RPCRT4!RpcStringFreeW` at `0x18003b5d6`
- `RPCRT4!RpcStringBindingComposeW` at `0x18003b5b2`
- `RPCRT4!RpcStringBindingComposeW` at `0x18003b5b2`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x18003b5ca`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x18003b5ca`
- `RPCRT4!RpcBindingSetAuthInfoExW` at `0x18003b65f`
- `RPCRT4!RpcBindingSetAuthInfoExW` at `0x18003b65f`

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
0x18003b550  mov     r11, rsp
0x18003b553  mov     [r11+18h], rbx
0x18003b557  mov     [rsp-18h+cbSid], edx
0x18003b55b  mov     [r11+8], rcx
0x18003b55f  push    rbp
0x18003b560  push    rsi
0x18003b561  push    rdi
0x18003b562  mov     rbp, rsp
0x18003b565  sub     rsp, 70h
0x18003b569  xor     eax, eax
0x18003b56b  mov     [rbp+StringBinding], 0
0x18003b573  xorps   xmm0, xmm0
0x18003b576  mov     [rbp+var_10], rax
0x18003b57a  mov     [rbp+cbSid], eax
0x18003b57d  lea     rdx, ProtSeq; "ncalrpc"
0x18003b584  lea     rax, [rbp+StringBinding]
0x18003b588  mov     [rbp+Binding], 0
0x18003b590  mov     rsi, r8
0x18003b593  mov     [r11-60h], rax
0x18003b597  xor     edi, edi
0x18003b599  lea     rcx, ObjUuid; "0497B57D-2E66-424F-A0C6-157CD5D41700"
0x18003b5a0  xor     r9d, r9d; Endpoint
0x18003b5a3  mov     [r11-68h], rdi
0x18003b5a7  xor     r8d, r8d; NetworkAddr
0x18003b5aa  movups  xmmword ptr [rbp+var_30.Version], xmm0
0x18003b5ae  movups  [rbp+var_20], xmm0
0x18003b5b2  call    cs:__imp_RpcStringBindingComposeW
0x18003b5b8  mov     ebx, eax
0x18003b5ba  test    eax, eax
0x18003b5bc  jnz     loc_18003B67A
0x18003b5c2  mov     rcx, [rbp+StringBinding]; StringBinding
0x18003b5c6  lea     rdx, [rbp+Binding]; Binding
0x18003b5ca  call    cs:__imp_RpcBindingFromStringBindingW
0x18003b5d0  lea     rcx, [rbp+StringBinding]; String
0x18003b5d4  mov     ebx, eax
0x18003b5d6  call    cs:__imp_RpcStringFreeW
0x18003b5dc  test    ebx, ebx
0x18003b5de  jnz     loc_18003B67A
0x18003b5e4  lea     edx, [rdi+44h]; uBytes
0x18003b5e7  lea     ecx, [rdi+40h]; uFlags
0x18003b5ea  mov     [rbp+cbSid], edx
0x18003b5ed  call    cs:__imp_LocalAlloc
0x18003b5f3  mov     rdi, rax
0x18003b5f6  test    rax, rax
0x18003b5f9  jnz     short loc_18003B600
0x18003b5fb  lea     ebx, [rax+8]
0x18003b5fe  jmp     short loc_18003B67A
0x18003b600  xor     edx, edx; DomainSid
0x18003b602  lea     r9, [rbp+cbSid]; cbSid
0x18003b606  mov     r8, rdi; pSid
0x18003b609  lea     ecx, [rdx+16h]; WellKnownSidType
0x18003b60c  call    cs:__imp_CreateWellKnownSid
0x18003b612  test    eax, eax
0x18003b614  jnz     short loc_18003B620
0x18003b616  mov     ebx, gs:68h
0x18003b61e  jmp     short loc_18003B67A
0x18003b620  mov     rcx, [rbp+Binding]; Binding
0x18003b624  mov     eax, 3
0x18003b629  xor     edx, edx; ServerPrincName
0x18003b62b  mov     [rbp+var_30.Version], eax
0x18003b62e  mov     [rbp+var_30.ImpersonationType], eax
0x18003b631  lea     rax, [rbp+var_30]
0x18003b635  mov     [rsp+70h+SecurityQOS], rax; SecurityQOS
0x18003b63a  mov     [rsp+70h+AuthzSvc], 0; AuthzSvc
0x18003b642  lea     r9d, [rdx+0Ah]; AuthnSvc
0x18003b646  mov     [rsp+70h+AuthIdentity], 0; AuthIdentity
0x18003b64f  lea     r8d, [rdx+6]; AuthnLevel
0x18003b653  mov     qword ptr [rbp+var_30.Capabilities], 1
0x18003b65b  mov     [rbp+var_10], rdi
0x18003b65f  call    cs:__imp_RpcBindingSetAuthInfoExW
0x18003b665  mov     ebx, eax
0x18003b667  test    eax, eax
0x18003b669  jnz     short loc_18003B67A
0x18003b66b  mov     rax, [rbp+Binding]
0x18003b66f  mov     [rsi], rax
0x18003b672  mov     [rbp+Binding], 0
0x18003b67a  mov     rcx, rdi; hMem
0x18003b67d  call    cs:__imp_LocalFree
0x18003b683  cmp     [rbp+Binding], 0
0x18003b688  jz      short loc_18003B694
0x18003b68a  lea     rcx, [rbp+Binding]; Binding
0x18003b68e  call    cs:__imp_RpcBindingFree
0x18003b694  mov     eax, ebx
0x18003b696  mov     rbx, [rsp+70h+arg_10]
0x18003b69e  add     rsp, 70h
0x18003b6a2  pop     rdi
0x18003b6a3  pop     rsi
0x18003b6a4  pop     rbp
0x18003b6a5  retn
```
