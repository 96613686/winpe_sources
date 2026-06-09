# DiscpCheckCallerIsAdmin

- ea: `0x180004e84`
- end: `0x180004ee1`
- name: `DiscpCheckCallerIsAdmin`
- size: `93`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `24`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800034a0`
- `0x1800037d0`
- `0x180003840`
- `0x1800039d0`
- `0x180003a70`
- `0x180003b00`
- `0x180003bc0`
- `0x180003c30`
- `0x180003c70`
- `0x180003cd0`
- `0x180003da0`
- `0x180003e50`
- `0x180003f80`
- `0x180004120`
- `0x180004170`
- `0x180004190`
- `0x1800041d0`
- `0x180004310`
- `0x180004380`
- `0x1800045d0`
- `0x180004690`
- `0x180004740`
- `0x180004850`
- `0x180004980`

## callees

- `0x180004e84`

## import_xrefs

- `RPCRT4!RpcImpersonateClient` at `0x180004e98`
- `RPCRT4!RpcImpersonateClient` at `0x180004e98`
- `RPCRT4!RpcRevertToSelf` at `0x180004ed3`
- `RPCRT4!RpcRevertToSelf` at `0x180004ed3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004ecb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004ecb`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x180004eb2`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x180004eb2`

## pseudocode

```c
__int64 __fastcall DiscpCheckCallerIsAdmin(__int64 a1)
{
  unsigned int LastError; // ebx
  WINBOOL IsMember; // [rsp+30h] [rbp+8h] BYREF
  int v4; // [rsp+34h] [rbp+Ch]

  v4 = HIDWORD(a1);
  IsMember = 0;
  LastError = RpcImpersonateClient(0);
  if ( !LastError )
  {
    if ( CheckTokenMembership(0, DiscpAdministratorsGroup, &IsMember) )
      LastError = IsMember == 0 ? 5 : 0;
    else
      LastError = GetLastError();
    RpcRevertToSelf();
  }
  return LastError;
}

```

## disassembly

```asm
0x180004e84  mov     qword ptr [rsp+IsMember], rcx
0x180004e89  push    rbx
0x180004e8a  sub     rsp, 20h
0x180004e8e  xor     ecx, ecx; BindingHandle
0x180004e90  mov     [rsp+28h+IsMember], 0
0x180004e98  call    cs:__imp_RpcImpersonateClient
0x180004e9e  mov     ebx, eax
0x180004ea0  test    eax, eax
0x180004ea2  jnz     short loc_180004ED9
0x180004ea4  mov     rdx, cs:DiscpAdministratorsGroup; SidToCheck
0x180004eab  lea     r8, [rsp+28h+IsMember]; IsMember
0x180004eb0  xor     ecx, ecx; TokenHandle
0x180004eb2  call    cs:__imp_CheckTokenMembership
0x180004eb8  test    eax, eax
0x180004eba  jz      short loc_180004ECB
0x180004ebc  mov     eax, [rsp+28h+IsMember]
0x180004ec0  neg     eax
0x180004ec2  sbb     ebx, ebx
0x180004ec4  not     ebx
0x180004ec6  and     ebx, 5
0x180004ec9  jmp     short loc_180004ED3
0x180004ecb  call    cs:__imp_GetLastError
0x180004ed1  mov     ebx, eax
0x180004ed3  call    cs:__imp_RpcRevertToSelf
0x180004ed9  mov     eax, ebx
0x180004edb  add     rsp, 20h
0x180004edf  pop     rbx
0x180004ee0  retn
```
