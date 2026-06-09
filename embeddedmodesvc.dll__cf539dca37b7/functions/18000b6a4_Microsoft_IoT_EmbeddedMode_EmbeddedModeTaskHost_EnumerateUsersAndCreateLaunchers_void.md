# Microsoft::IoT::EmbeddedMode::EmbeddedModeTaskHost::EnumerateUsersAndCreateLaunchers(void)

- ea: `0x18000b6a4`
- end: `0x18000b745`
- name: `?EnumerateUsersAndCreateLaunchers@EmbeddedModeTaskHost@EmbeddedMode@IoT@Microsoft@@QEAAJXZ`
- size: `161`
- prototype: `__int64 __fastcall(Microsoft::IoT::EmbeddedMode::EmbeddedModeTaskHost *this)`
- caller_count: `2`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x180008018`
- `0x18000af90`

## callees

- `0x180008378`
- `0x18000b6a4`
- `0x18000ba9c`

## import_xrefs

- `ext-ms-win-session-usermgr-l1-1-0!UMgrFreeSessionUsers` at `0x18000b72d`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrFreeSessionUsers` at `0x18000b72d`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrEnumerateSessionUsers` at `0x18000b6ce`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrEnumerateSessionUsers` at `0x18000b6ce`

## string_xrefs

- `0x18000b70c`: `onecoreuap\shell\embedded\shell\embeddedmode\svc\embeddedmodetaskhost.cpp`

## pseudocode

```c
__int64 __fastcall Microsoft::IoT::EmbeddedMode::EmbeddedModeTaskHost::EnumerateUsersAndCreateLaunchers(
        Microsoft::IoT::EmbeddedMode::EmbeddedModeTaskHost *this)
{
  int v2; // edi
  __int64 v3; // rcx
  unsigned int i; // ebx
  int v5; // eax
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  unsigned int v8; // [rsp+38h] [rbp+10h] BYREF
  __int64 v9; // [rsp+40h] [rbp+18h] BYREF

  v8 = 0;
  v9 = 0;
  v2 = UMgrEnumerateSessionUsers(&v8, &v9);
  if ( v2 >= 0 )
  {
    if ( v8 )
    {
      v3 = v9;
      if ( v9 )
      {
        for ( i = 0; i < v8; ++i )
        {
          v5 = Microsoft::IoT::EmbeddedMode::EmbeddedModeTaskHost::LaunchBackgroundTasks(
                 this,
                 *(unsigned int *)(v3 + 16LL * i + 8));
          if ( v5 < 0 )
            wil::details::in1diag3::_Log_Hr(
              retaddr,
              (void *)0x99,
              (int)"onecoreuap\\shell\\embedded\\shell\\embeddedmode\\svc\\embeddedmodetaskhost.cpp",
              (const char *)(unsigned int)v5);
          v3 = v9;
        }
        UMgrFreeSessionUsers();
      }
    }
  }
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x18000b6a4  mov     rax, rsp
0x18000b6a7  mov     [rax+8], rbx
0x18000b6ab  mov     [rax+20h], rsi
0x18000b6af  push    rdi; int
0x18000b6b0  sub     rsp, 20h
0x18000b6b4  mov     rsi, rcx
0x18000b6b7  mov     dword ptr [rax+10h], 0
0x18000b6be  lea     rcx, [rax+10h]
0x18000b6c2  mov     qword ptr [rax+18h], 0
0x18000b6ca  lea     rdx, [rax+18h]
0x18000b6ce  call    cs:__imp_UMgrEnumerateSessionUsers
0x18000b6d4  mov     edi, eax
0x18000b6d6  test    eax, eax
0x18000b6d8  js      short loc_18000B733
0x18000b6da  mov     edx, [rsp+28h+arg_8]
0x18000b6de  test    edx, edx
0x18000b6e0  jz      short loc_18000B733
0x18000b6e2  mov     rcx, [rsp+28h+arg_10]
0x18000b6e7  test    rcx, rcx
0x18000b6ea  jz      short loc_18000B733
0x18000b6ec  xor     ebx, ebx
0x18000b6ee  test    edx, edx
0x18000b6f0  jz      short loc_18000B72D
0x18000b6f2  mov     edx, ebx
0x18000b6f4  add     rdx, rdx
0x18000b6f7  mov     edx, [rcx+rdx*8+8]; unsigned int
0x18000b6fb  mov     rcx, rsi; this
0x18000b6fe  call    ?LaunchBackgroundTasks@EmbeddedModeTaskHost@EmbeddedMode@IoT@Microsoft@@QEAAJK@Z; Microsoft::IoT::EmbeddedMode::EmbeddedModeTaskHost::LaunchBackgroundTasks(ulong)
0x18000b703  test    eax, eax
0x18000b705  jns     short loc_18000B720
0x18000b707  mov     rcx, [rsp+28h]; this
0x18000b70c  lea     r8, aOnecoreuapShel_3; "onecoreuap\\shell\\embedded\\shell\\emb"...
0x18000b713  mov     r9d, eax; char *
0x18000b716  mov     edx, 99h; void *
0x18000b71b  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18000b720  mov     rcx, [rsp+28h+arg_10]
0x18000b725  inc     ebx
0x18000b727  cmp     ebx, [rsp+28h+arg_8]
0x18000b72b  jb      short loc_18000B6F2
0x18000b72d  call    cs:__imp_UMgrFreeSessionUsers
0x18000b733  mov     rbx, [rsp+28h+arg_0]
0x18000b738  mov     eax, edi
0x18000b73a  mov     rsi, [rsp+28h+arg_18]
0x18000b73f  add     rsp, 20h
0x18000b743  pop     rdi
0x18000b744  retn
```
