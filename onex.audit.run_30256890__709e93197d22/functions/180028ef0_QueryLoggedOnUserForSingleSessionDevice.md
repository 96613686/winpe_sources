# QueryLoggedOnUserForSingleSessionDevice

- ea: `0x180028ef0`
- end: `0x180028f8d`
- name: `QueryLoggedOnUserForSingleSessionDevice`
- size: `157`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x180002a30`
- `0x18001abb4`

## callees

- `0x180020de4`
- `0x180020f74`
- `0x180028ef0`

## import_xrefs

- `ext-ms-win-session-usertoken-l1-1-0!QueryUserToken` at `0x180028f77`
- `ext-ms-win-session-usertoken-l1-1-0!QueryUserToken` at `0x180028f77`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrEnumerateSessionUsers` at `0x180028f37`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrEnumerateSessionUsers` at `0x180028f37`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserToken` at `0x180028f65`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserToken` at `0x180028f65`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrFreeSessionUsers` at `0x180028f54`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrFreeSessionUsers` at `0x180028f54`

## pseudocode

```c
__int64 __fastcall QueryLoggedOnUserForSingleSessionDevice(unsigned int a1, __int64 a2)
{
  __int64 v5; // rbx
  __int64 v6; // rdx
  int v7; // [rsp+40h] [rbp+18h] BYREF
  __int64 *v8; // [rsp+48h] [rbp+20h] BYREF

  if ( !(unsigned __int8)IsQueryUserTokenPresent() )
    return 0;
  if ( (unsigned __int8)IsUMgrEnumerateSessionUsersPresent() )
  {
    v7 = 0;
    v8 = 0;
    v5 = 0;
    if ( (int)UMgrEnumerateSessionUsers(&v7, &v8) >= 0 && v7 )
      v5 = *v8;
    if ( v8 )
      UMgrFreeSessionUsers(v8);
    v6 = a2;
    if ( v5 )
      return (int)UMgrQueryUserToken(v5, a2) >= 0;
  }
  else
  {
    v6 = a2;
  }
  return QueryUserToken(a1, v6);
}

```

## disassembly

```asm
0x180028ef0  mov     [rsp+arg_0], rbx
0x180028ef5  mov     [rsp+arg_8], rsi
0x180028efa  push    rdi
0x180028efb  sub     rsp, 20h
0x180028eff  mov     rdi, rdx
0x180028f02  mov     esi, ecx
0x180028f04  call    IsQueryUserTokenPresent
0x180028f09  test    al, al
0x180028f0b  jnz     short loc_180028F11
0x180028f0d  xor     eax, eax
0x180028f0f  jmp     short loc_180028F7D
0x180028f11  call    IsUMgrEnumerateSessionUsersPresent
0x180028f16  test    al, al
0x180028f18  jz      short loc_180028F72
0x180028f1a  lea     rdx, [rsp+28h+arg_18]
0x180028f1f  mov     [rsp+28h+arg_10], 0
0x180028f27  lea     rcx, [rsp+28h+arg_10]
0x180028f2c  mov     [rsp+28h+arg_18], 0
0x180028f35  xor     ebx, ebx
0x180028f37  call    cs:__imp_UMgrEnumerateSessionUsers
0x180028f3d  mov     rcx, [rsp+28h+arg_18]
0x180028f42  test    eax, eax
0x180028f44  js      short loc_180028F4F
0x180028f46  cmp     [rsp+28h+arg_10], ebx
0x180028f4a  jbe     short loc_180028F4F
0x180028f4c  mov     rbx, [rcx]
0x180028f4f  test    rcx, rcx
0x180028f52  jz      short loc_180028F5A
0x180028f54  call    cs:__imp_UMgrFreeSessionUsers
0x180028f5a  mov     rdx, rdi
0x180028f5d  test    rbx, rbx
0x180028f60  jz      short loc_180028F75
0x180028f62  mov     rcx, rbx
0x180028f65  call    cs:__imp_UMgrQueryUserToken
0x180028f6b  not     eax
0x180028f6d  shr     eax, 1Fh
0x180028f70  jmp     short loc_180028F7D
0x180028f72  mov     rdx, rdi
0x180028f75  mov     ecx, esi
0x180028f77  call    cs:__imp_QueryUserToken
0x180028f7d  mov     rbx, [rsp+28h+arg_0]
0x180028f82  mov     rsi, [rsp+28h+arg_8]
0x180028f87  add     rsp, 20h
0x180028f8b  pop     rdi
0x180028f8c  retn
```
