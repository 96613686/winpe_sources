# VerifyDirectXDatabaseVersion(ushort const *)

- ea: `0x14000d384`
- end: `0x14000d482`
- name: `?VerifyDirectXDatabaseVersion@@YAJPEBG@Z`
- size: `254`
- prototype: `__int64 __fastcall(const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x140007ad8`

## callees

- `0x140002f40`
- `0x140003ab8`
- `0x140005680`
- `0x140006a10`
- `0x14000a4bc`
- `0x14000d384`
- `0x14000df28`

## import_xrefs

- `ext-ms-win-dx-dxdbhelper-l1-1-0!__imp_QueryDirectXDatabaseConfig` at `0x14000d3e3`
- `ext-ms-win-dx-dxdbhelper-l1-1-0!__imp_QueryDirectXDatabaseConfig` at `0x14000d3e3`

## string_xrefs

- `0x14000d3f6`: `onecore\windows\directx\database\updater\exe\main.cpp`
- `0x14000d433`: `onecore\windows\directx\database\updater\exe\main.cpp`

## pseudocode

```c
__int64 __fastcall VerifyDirectXDatabaseVersion(const unsigned __int16 *a1)
{
  int DirectXDatabaseConfig; // eax
  unsigned int v2; // ebx
  _BYTE v4[16]; // [rsp+38h] [rbp-61h] BYREF
  _BYTE v5[32]; // [rsp+48h] [rbp-51h] BYREF
  _BYTE v6[16]; // [rsp+68h] [rbp-31h] BYREF
  _BYTE v7[40]; // [rsp+78h] [rbp-21h] BYREF
  unsigned __int16 v8[32]; // [rsp+A0h] [rbp+7h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+F8h] [rbp+5Fh]

  VersionInfo::VersionInfo((VersionInfo *)v6, a1);
  memset_0(v8, 0, sizeof(v8));
  DirectXDatabaseConfig = QueryDirectXDatabaseConfig(0, 0, 0, 0);
  v2 = DirectXDatabaseConfig;
  if ( DirectXDatabaseConfig >= 0 )
  {
    VersionInfo::VersionInfo((VersionInfo *)v4, v8);
    if ( (unsigned int)VersionInfo::Compare((VersionInfo *)v4, (const struct VersionInfo *)v6) )
    {
      v2 = -2147418113;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x79,
        (unsigned int)"onecore\\windows\\directx\\database\\updater\\exe\\main.cpp",
        (const char *)0x8000FFFFLL,
        (int)v8);
      std::wstring::_Tidy_deallocate(v5);
    }
    else
    {
      std::wstring::_Tidy_deallocate(v5);
      v2 = 0;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x74,
      (unsigned int)"onecore\\windows\\directx\\database\\updater\\exe\\main.cpp",
      (const char *)(unsigned int)DirectXDatabaseConfig,
      (int)v8);
  }
  std::wstring::_Tidy_deallocate(v7);
  return v2;
}

```

## disassembly

```asm
0x14000d384  mov     [rsp-8+arg_8], rbx
0x14000d389  push    rbp
0x14000d38a  lea     rbp, [rsp-57h]
0x14000d38f  sub     rsp, 0F0h
0x14000d396  mov     rax, cs:__security_cookie
0x14000d39d  xor     rax, rsp
0x14000d3a0  mov     [rbp+57h+var_10], rax
0x14000d3a4  mov     rdx, rcx; unsigned __int16 *
0x14000d3a7  lea     rcx, [rbp+57h+var_88]; this
0x14000d3ab  call    ??0VersionInfo@@QEAA@PEBG@Z; VersionInfo::VersionInfo(ushort const *)
0x14000d3b0  nop
0x14000d3b1  mov     ebx, 40h ; '@'
0x14000d3b6  mov     r8d, ebx; Size
0x14000d3b9  xor     edx, edx; Val
0x14000d3bb  lea     rcx, [rbp+57h+var_50]; void *
0x14000d3bf  call    memset_0
0x14000d3c4  mov     [rbp+57h+var_C0], ebx
0x14000d3c7  lea     rax, [rbp+57h+var_C0]
0x14000d3cb  mov     [rsp+0F0h+var_C8], rax
0x14000d3d0  lea     rax, [rbp+57h+var_50]
0x14000d3d4  mov     qword ptr [rsp+0F0h+var_D0], rax; int
0x14000d3d9  xor     r9d, r9d
0x14000d3dc  xor     r8d, r8d
0x14000d3df  xor     edx, edx
0x14000d3e1  xor     ecx, ecx
0x14000d3e3  call    cs:__imp_QueryDirectXDatabaseConfig
0x14000d3e9  mov     ebx, eax
0x14000d3eb  test    eax, eax
0x14000d3ed  jns     short loc_14000D409
0x14000d3ef  mov     rcx, [rbp+5Fh]; this
0x14000d3f3  mov     r9d, eax; char *
0x14000d3f6  lea     r8, aOnecoreWindows_2; "onecore\\windows\\directx\\database\\up"...
0x14000d3fd  mov     edx, 74h ; 't'; void *
0x14000d402  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000d407  jmp     short loc_14000D45A
0x14000d409  lea     rdx, [rbp+57h+var_50]; unsigned __int16 *
0x14000d40d  lea     rcx, [rbp+57h+var_B8]; this
0x14000d411  call    ??0VersionInfo@@QEAA@PEBG@Z; VersionInfo::VersionInfo(ushort const *)
0x14000d416  lea     rdx, [rbp+57h+var_88]; struct VersionInfo *
0x14000d41a  lea     rcx, [rbp+57h+var_B8]; this
0x14000d41e  call    ?Compare@VersionInfo@@QEBAHAEBV1@@Z; VersionInfo::Compare(VersionInfo const &)
0x14000d423  test    eax, eax
0x14000d425  jz      short loc_14000D44F
0x14000d427  mov     rcx, [rbp+5Fh]; this
0x14000d42b  mov     ebx, 8000FFFFh
0x14000d430  mov     r9d, ebx; char *
0x14000d433  lea     r8, aOnecoreWindows_2; "onecore\\windows\\directx\\database\\up"...
0x14000d43a  mov     edx, 79h ; 'y'; void *
0x14000d43f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000d444  lea     rcx, [rbp+57h+var_A8]
0x14000d448  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x14000d44d  jmp     short loc_14000D45A
0x14000d44f  lea     rcx, [rbp+57h+var_A8]
0x14000d453  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x14000d458  xor     ebx, ebx
0x14000d45a  lea     rcx, [rbp+57h+var_78]
0x14000d45e  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x14000d463  mov     eax, ebx
0x14000d465  mov     rcx, [rbp+57h+var_10]
0x14000d469  xor     rcx, rsp; StackCookie
0x14000d46c  call    __security_check_cookie
0x14000d471  mov     rbx, [rsp+0F0h+arg_8]
0x14000d479  add     rsp, 0F0h
0x14000d480  pop     rbp
0x14000d481  retn
```
