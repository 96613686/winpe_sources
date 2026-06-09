# CheckRpcCallerTokenMembership(void *,void *,int *)

- ea: `0x180006d38`
- end: `0x180006e86`
- name: `?CheckRpcCallerTokenMembership@@YAJPEAX0PEAH@Z`
- size: `334`
- prototype: `__int64 __fastcall(RPC_BINDING_HANDLE BindingHandle, PSID SidToCheck, int *)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x18000a50c`
- `0x18000f8b8`

## callees

- `0x180006d38`
- `0x18000a2b4`
- `0x18001aea4`

## import_xrefs

- `ADVAPI32!CheckTokenMembership` at `0x180006dcc`
- `ADVAPI32!CheckTokenMembership` at `0x180006dcc`
- `RPCRT4!RpcImpersonateClient` at `0x180006d5f`
- `RPCRT4!RpcImpersonateClient` at `0x180006d5f`
- `RPCRT4!RpcRevertToSelfEx` at `0x180006e1b`
- `RPCRT4!RpcRevertToSelfEx` at `0x180006e1b`

## string_xrefs

- `0x180006d99`: `CheckRpcCallerTokenMembership`
- `0x180006dfc`: `CheckRpcCallerTokenMembership`
- `0x180006e44`: `CheckRpcCallerTokenMembership`

## pseudocode

```c
__int64 __fastcall CheckRpcCallerTokenMembership(RPC_BINDING_HANDLE BindingHandle, PSID SidToCheck, int *a3)
{
  signed int v6; // ebx
  RPC_STATUS v7; // eax
  signed int Error; // eax
  RPC_STATUS v9; // eax
  WINBOOL IsMember; // [rsp+60h] [rbp+18h] BYREF

  *a3 = 0;
  v6 = 0;
  v7 = RpcImpersonateClient(BindingHandle);
  if ( v7 )
  {
    v6 = v7 | 0x80010000;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0 )
      WPP_SF_SD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        22,
        (unsigned int)&WPP_14f402b3e7783efa9cd4a35c63de2b16_Traceguids,
        (unsigned int)L"CheckRpcCallerTokenMembership",
        v7);
  }
  IsMember = 0;
  if ( v6 >= 0 )
  {
    if ( !CheckTokenMembership(0, SidToCheck, &IsMember) )
    {
      Error = HResultFromLastError();
      v6 = Error;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0 )
        WPP_SF_SD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          23,
          (unsigned int)&WPP_14f402b3e7783efa9cd4a35c63de2b16_Traceguids,
          (unsigned int)L"CheckRpcCallerTokenMembership",
          Error);
    }
    v9 = RpcRevertToSelfEx(BindingHandle);
    if ( v9 && WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0 )
      WPP_SF_SD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        24,
        (unsigned int)&WPP_14f402b3e7783efa9cd4a35c63de2b16_Traceguids,
        (unsigned int)L"CheckRpcCallerTokenMembership",
        v9);
    if ( v6 >= 0 )
      *a3 = IsMember;
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180006d38  mov     [rsp+arg_0], rbx
0x180006d3d  mov     [rsp+arg_8], rbp
0x180006d42  mov     [rsp+arg_18], rsi
0x180006d47  push    rdi
0x180006d48  push    r12
0x180006d4a  push    r14
0x180006d4c  sub     rsp, 30h
0x180006d50  and     dword ptr [r8], 0
0x180006d54  mov     rsi, r8
0x180006d57  mov     r14, rdx
0x180006d5a  mov     rbp, rcx
0x180006d5d  xor     ebx, ebx
0x180006d5f  call    cs:__imp_RpcImpersonateClient
0x180006d66  nop     dword ptr [rax+rax+00h]
0x180006d6b  lea     r12, WPP_GLOBAL_Control
0x180006d72  test    eax, eax
0x180006d74  jz      short loc_180006DB5
0x180006d76  mov     edi, eax
0x180006d78  or      edi, 80010000h
0x180006d7e  mov     rcx, cs:WPP_GLOBAL_Control
0x180006d85  mov     ebx, edi
0x180006d87  cmp     rcx, r12
0x180006d8a  jz      short loc_180006DB5
0x180006d8c  test    dword ptr [rcx+1Ch], 1000h
0x180006d93  jz      short loc_180006DB5
0x180006d95  mov     rcx, [rcx+10h]
0x180006d99  lea     r9, aCheckrpccaller; "CheckRpcCallerTokenMembership"
0x180006da0  mov     edx, 16h
0x180006da5  mov     [rsp+48h+var_28], eax
0x180006da9  lea     r8, WPP_14f402b3e7783efa9cd4a35c63de2b16_Traceguids
0x180006db0  call    WPP_SF_SD
0x180006db5  and     [rsp+48h+IsMember], 0
0x180006dba  test    ebx, ebx
0x180006dbc  js      loc_180006E6A
0x180006dc2  lea     r8, [rsp+48h+IsMember]; IsMember
0x180006dc7  mov     rdx, r14; SidToCheck
0x180006dca  xor     ecx, ecx; TokenHandle
0x180006dcc  call    cs:__imp_CheckTokenMembership
0x180006dd3  nop     dword ptr [rax+rax+00h]
0x180006dd8  test    eax, eax
0x180006dda  jnz     short loc_180006E18
0x180006ddc  call    ?HResultFromLastError@@YAJXZ; HResultFromLastError(void)
0x180006de1  mov     ebx, eax
0x180006de3  mov     rcx, cs:WPP_GLOBAL_Control
0x180006dea  cmp     rcx, r12
0x180006ded  jz      short loc_180006E18
0x180006def  test    dword ptr [rcx+1Ch], 1000h
0x180006df6  jz      short loc_180006E18
0x180006df8  mov     rcx, [rcx+10h]
0x180006dfc  lea     r9, aCheckrpccaller; "CheckRpcCallerTokenMembership"
0x180006e03  mov     edx, 17h
0x180006e08  mov     [rsp+48h+var_28], eax
0x180006e0c  lea     r8, WPP_14f402b3e7783efa9cd4a35c63de2b16_Traceguids
0x180006e13  call    WPP_SF_SD
0x180006e18  mov     rcx, rbp; BindingHandle
0x180006e1b  call    cs:__imp_RpcRevertToSelfEx
0x180006e22  nop     dword ptr [rax+rax+00h]
0x180006e27  test    eax, eax
0x180006e29  jz      short loc_180006E60
0x180006e2b  mov     rcx, cs:WPP_GLOBAL_Control
0x180006e32  cmp     rcx, r12
0x180006e35  jz      short loc_180006E60
0x180006e37  test    dword ptr [rcx+1Ch], 1000h
0x180006e3e  jz      short loc_180006E60
0x180006e40  mov     rcx, [rcx+10h]
0x180006e44  lea     r9, aCheckrpccaller; "CheckRpcCallerTokenMembership"
0x180006e4b  mov     edx, 18h
0x180006e50  mov     [rsp+48h+var_28], eax
0x180006e54  lea     r8, WPP_14f402b3e7783efa9cd4a35c63de2b16_Traceguids
0x180006e5b  call    WPP_SF_SD
0x180006e60  test    ebx, ebx
0x180006e62  js      short loc_180006E6A
0x180006e64  mov     eax, [rsp+48h+IsMember]
0x180006e68  mov     [rsi], eax
0x180006e6a  mov     rbp, [rsp+48h+arg_8]
0x180006e6f  mov     eax, ebx
0x180006e71  mov     rbx, [rsp+48h+arg_0]
0x180006e76  mov     rsi, [rsp+48h+arg_18]
0x180006e7b  add     rsp, 30h
0x180006e7f  pop     r14
0x180006e81  pop     r12
0x180006e83  pop     rdi
0x180006e84  retn
```
