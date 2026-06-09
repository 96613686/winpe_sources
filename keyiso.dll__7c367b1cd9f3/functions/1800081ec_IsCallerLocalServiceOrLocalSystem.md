# IsCallerLocalServiceOrLocalSystem

- ea: `0x1800081ec`
- end: `0x1800082a4`
- name: `IsCallerLocalServiceOrLocalSystem`
- size: `184`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callers

- `0x180008090`
- `0x18000d9e0`

## callees

- `0x1800081ec`
- `0x18000875c`
- `0x180008a70`

## import_xrefs

- `RPCRT4!RpcImpersonateClient` at `0x180008206`
- `RPCRT4!RpcImpersonateClient` at `0x180008206`
- `RPCRT4!RpcRevertToSelf` at `0x18000822d`
- `RPCRT4!RpcRevertToSelf` at `0x18000822d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180008281`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180008281`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000828f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000828f`
- `api-ms-win-security-base-l1-1-0!IsWellKnownSid` at `0x18000825a`
- `api-ms-win-security-base-l1-1-0!IsWellKnownSid` at `0x18000826a`
- `api-ms-win-security-base-l1-1-0!IsWellKnownSid` at `0x18000825a`
- `api-ms-win-security-base-l1-1-0!IsWellKnownSid` at `0x18000826a`

## pseudocode

```c
__int64 __fastcall IsCallerLocalServiceOrLocalSystem(void *a1)
{
  unsigned int v1; // esi
  void *v2; // rbx
  RPC_STATUS v3; // eax
  __int64 v4; // rcx
  RPC_STATUS v5; // edi
  int v6; // ebp
  int UserSid; // eax
  PSID *v8; // rdi
  void *v10; // [rsp+48h] [rbp+10h] BYREF
  HLOCAL hMem; // [rsp+50h] [rbp+18h]

  v1 = 0;
  v2 = 0;
  hMem = 0;
  v10 = 0;
  v3 = RpcImpersonateClient(a1);
  v5 = v3;
  if ( !v3 || v3 == 1725 )
  {
    v6 = OpenCallerToken(v4, &v10);
    if ( !v5 )
      RpcRevertToSelf();
    v2 = v10;
  }
  else
  {
    v6 = v3;
  }
  if ( v6 >= 0 )
  {
    UserSid = GetUserSid(v2);
    v8 = (PSID *)hMem;
    if ( UserSid >= 0 && (IsWellKnownSid(*(PSID *)hMem, WinLocalSystemSid) || IsWellKnownSid(*v8, WinLocalServiceSid)) )
      v1 = 1;
    if ( v8 )
      LocalFree(v8);
  }
  if ( v2 )
    CloseHandle(v2);
  return v1;
}

```

## disassembly

```asm
0x1800081ec  mov     [rsp+arg_0], rbx
0x1800081f1  push    rbp
0x1800081f2  push    rsi
0x1800081f3  push    rdi
0x1800081f4  sub     rsp, 20h
0x1800081f8  xor     esi, esi
0x1800081fa  xor     ebx, ebx
0x1800081fc  mov     [rsp+38h+hMem], rsi
0x180008201  mov     [rsp+38h+arg_8], rbx
0x180008206  call    cs:__imp_RpcImpersonateClient
0x18000820c  mov     edi, eax
0x18000820e  test    eax, eax
0x180008210  jz      short loc_18000821D
0x180008212  cmp     eax, 6BDh
0x180008217  jz      short loc_18000821D
0x180008219  mov     ebp, eax
0x18000821b  jmp     short loc_180008238
0x18000821d  lea     rdx, [rsp+38h+arg_8]
0x180008222  call    _OpenCallerToken
0x180008227  mov     ebp, eax
0x180008229  test    edi, edi
0x18000822b  jnz     short loc_180008233
0x18000822d  call    cs:__imp_RpcRevertToSelf
0x180008233  mov     rbx, [rsp+38h+arg_8]
0x180008238  test    ebp, ebp
0x18000823a  js      short loc_180008287
0x18000823c  lea     rdx, [rsp+38h+hMem]
0x180008241  mov     rcx, rbx; TokenHandle
0x180008244  call    GetUserSid
0x180008249  mov     rdi, [rsp+38h+hMem]
0x18000824e  test    eax, eax
0x180008250  js      short loc_180008279
0x180008252  mov     rcx, [rdi]; pSid
0x180008255  mov     edx, 16h; WellKnownSidType
0x18000825a  call    cs:__imp_IsWellKnownSid
0x180008260  test    eax, eax
0x180008262  jnz     short loc_180008274
0x180008264  mov     rcx, [rdi]; pSid
0x180008267  lea     edx, [rax+17h]; WellKnownSidType
0x18000826a  call    cs:__imp_IsWellKnownSid
0x180008270  test    eax, eax
0x180008272  jz      short loc_180008279
0x180008274  mov     esi, 1
0x180008279  test    rdi, rdi
0x18000827c  jz      short loc_180008287
0x18000827e  mov     rcx, rdi; hMem
0x180008281  call    cs:__imp_LocalFree
0x180008287  test    rbx, rbx
0x18000828a  jz      short loc_180008295
0x18000828c  mov     rcx, rbx; hObject
0x18000828f  call    cs:__imp_CloseHandle
0x180008295  mov     rbx, [rsp+38h+arg_0]
0x18000829a  mov     eax, esi
0x18000829c  add     rsp, 20h
0x1800082a0  pop     rdi
0x1800082a1  pop     rsi
0x1800082a2  pop     rbp
0x1800082a3  retn
```
