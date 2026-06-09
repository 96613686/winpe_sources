# QueryLoggedOnUserForSingleSessionDevice(ulong,void * *)

- ea: `0x18006ae64`
- end: `0x18006aef9`
- name: `?QueryLoggedOnUserForSingleSessionDevice@@YAHKPEAPEAX@Z`
- size: `149`
- prototype: `__int64 __fastcall(int, void **)`
- caller_count: `4`
- callee_count: `3`
- tags: ``

## callers

- `0x1800679b0`
- `0x180070fb0`
- `0x1800b00e0`
- `0x1800b0370`

## callees

- `0x180064ca0`
- `0x180064cf4`
- `0x18006ae64`

## import_xrefs

- `ext-ms-win-session-usermgr-l1-1-0!UMgrEnumerateSessionUsers` at `0x18006aea8`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrEnumerateSessionUsers` at `0x18006aea8`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrFreeSessionUsers` at `0x18006aec5`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrFreeSessionUsers` at `0x18006aec5`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserToken` at `0x18006aed6`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserToken` at `0x18006aed6`
- `ext-ms-win-session-usertoken-l1-1-0!QueryUserToken` at `0x18006aee8`
- `ext-ms-win-session-usertoken-l1-1-0!QueryUserToken` at `0x18006aee8`

## pseudocode

```c
__int64 __fastcall QueryLoggedOnUserForSingleSessionDevice(int a1, void **a2)
{
  __int64 v4; // rbx
  void **v5; // rdx
  int v6; // [rsp+30h] [rbp+8h] BYREF
  __int64 *v7; // [rsp+40h] [rbp+18h] BYREF

  v6 = a1;
  if ( !(unsigned __int8)IsQueryUserTokenPresent() )
    return 0;
  if ( (unsigned __int8)IsUMgrEnumerateSessionUsersPresent() )
  {
    v6 = 0;
    v7 = 0;
    v4 = 0;
    if ( (int)UMgrEnumerateSessionUsers(&v6, &v7) >= 0 && v6 )
      v4 = *v7;
    if ( v7 )
      UMgrFreeSessionUsers(v7);
    v5 = a2;
    if ( v4 )
      return (int)UMgrQueryUserToken(v4, a2) >= 0;
  }
  else
  {
    v5 = a2;
  }
  return QueryUserToken(0, v5);
}

```

## disassembly

```asm
0x18006ae64  mov     [rsp+arg_8], rbx
0x18006ae69  mov     [rsp+arg_0], ecx
0x18006ae6d  push    rdi
0x18006ae6e  sub     rsp, 20h
0x18006ae72  mov     rdi, rdx
0x18006ae75  call    IsQueryUserTokenPresent
0x18006ae7a  test    al, al
0x18006ae7c  jnz     short loc_18006AE82
0x18006ae7e  xor     eax, eax
0x18006ae80  jmp     short loc_18006AEEE
0x18006ae82  call    IsUMgrEnumerateSessionUsersPresent
0x18006ae87  test    al, al
0x18006ae89  jz      short loc_18006AEE3
0x18006ae8b  lea     rdx, [rsp+28h+arg_10]
0x18006ae90  mov     [rsp+28h+arg_0], 0
0x18006ae98  lea     rcx, [rsp+28h+arg_0]
0x18006ae9d  mov     [rsp+28h+arg_10], 0
0x18006aea6  xor     ebx, ebx
0x18006aea8  call    cs:__imp_UMgrEnumerateSessionUsers
0x18006aeae  mov     rcx, [rsp+28h+arg_10]
0x18006aeb3  test    eax, eax
0x18006aeb5  js      short loc_18006AEC0
0x18006aeb7  cmp     [rsp+28h+arg_0], ebx
0x18006aebb  jbe     short loc_18006AEC0
0x18006aebd  mov     rbx, [rcx]
0x18006aec0  test    rcx, rcx
0x18006aec3  jz      short loc_18006AECB
0x18006aec5  call    cs:__imp_UMgrFreeSessionUsers
0x18006aecb  mov     rdx, rdi
0x18006aece  test    rbx, rbx
0x18006aed1  jz      short loc_18006AEE6
0x18006aed3  mov     rcx, rbx
0x18006aed6  call    cs:__imp_UMgrQueryUserToken
0x18006aedc  not     eax
0x18006aede  shr     eax, 1Fh
0x18006aee1  jmp     short loc_18006AEEE
0x18006aee3  mov     rdx, rdi
0x18006aee6  xor     ecx, ecx
0x18006aee8  call    cs:__imp_QueryUserToken
0x18006aeee  mov     rbx, [rsp+28h+arg_8]
0x18006aef3  add     rsp, 20h
0x18006aef7  pop     rdi
0x18006aef8  retn
```
