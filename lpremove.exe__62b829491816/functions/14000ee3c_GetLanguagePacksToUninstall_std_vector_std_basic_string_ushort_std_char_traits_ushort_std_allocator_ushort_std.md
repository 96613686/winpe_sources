# GetLanguagePacksToUninstall(std::vector<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>> &,std::vector<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>> &)

- ea: `0x14000ee3c`
- end: `0x14000eeaf`
- name: `?GetLanguagePacksToUninstall@@YAJAEAV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@0@Z`
- size: `115`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `installer_update`

## callers

- `0x14000c36c`

## callees

- `0x140002dcc`
- `0x14000a914`
- `0x14000ee3c`

## import_xrefs

- `ext-ms-win-resources-languageoverlay-l1-1-4!EnumerateInstalledSystemLanguagePacks` at `0x14000ee72`
- `ext-ms-win-resources-languageoverlay-l1-1-4!EnumerateInstalledSystemLanguagePacks` at `0x14000ee72`

## pseudocode

```c
__int64 __fastcall GetLanguagePacksToUninstall(__int64 a1, __int64 a2)
{
  int v5; // eax
  unsigned int v6; // ebx
  int v7[2]; // [rsp+20h] [rbp-18h] BYREF
  __int64 v8; // [rsp+28h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  if ( !(unsigned __int8)IsEnumerateInstalledSystemLanguagePacksPresent() )
    return 2147500033LL;
  *(_QWORD *)v7 = a1;
  v8 = a2;
  v5 = EnumerateInstalledSystemLanguagePacks(lambda_4029cdf8fd3d553b1057432be738174f_::_lambda_invoker_cdecl_, v7);
  v6 = v5;
  if ( v5 >= 0 )
    return 0;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0xB0,
    (unsigned int)"shell\\osshell\\cpls\\lpksetup\\utils\\languagepackcleanuputils.cpp",
    (const char *)(unsigned int)v5,
    v7[0]);
  return v6;
}

```

## disassembly

```asm
0x14000ee3c  mov     [rsp+arg_0], rbx
0x14000ee41  push    rdi
0x14000ee42  sub     rsp, 30h
0x14000ee46  mov     rbx, rdx
0x14000ee49  mov     rdi, rcx
0x14000ee4c  call    IsEnumerateInstalledSystemLanguagePacksPresent
0x14000ee51  test    al, al
0x14000ee53  jnz     short loc_14000EE5C
0x14000ee55  mov     eax, 80004001h
0x14000ee5a  jmp     short loc_14000EEA3
0x14000ee5c  mov     qword ptr [rsp+38h+var_18], rdi; int
0x14000ee61  mov     [rsp+38h+var_10], rbx
0x14000ee66  lea     rdx, [rsp+38h+var_18]
0x14000ee6b  lea     rcx, _lambda_4029cdf8fd3d553b1057432be738174f____lambda_invoker_cdecl_
0x14000ee72  call    cs:__imp_EnumerateInstalledSystemLanguagePacks
0x14000ee78  mov     ebx, eax
0x14000ee7a  test    eax, eax
0x14000ee7c  jns     short loc_14000EE9B
0x14000ee7e  mov     rcx, [rsp+38h]; this
0x14000ee83  mov     r9d, eax; char *
0x14000ee86  lea     r8, aShellOsshellCp; "shell\\osshell\\cpls\\lpksetup\\utils\\"...
0x14000ee8d  mov     edx, 0B0h; void *
0x14000ee92  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000ee97  mov     eax, ebx
0x14000ee99  jmp     short loc_14000EEA3
0x14000ee9b  xor     eax, eax
0x14000ee9d  jmp     short loc_14000EEA3
0x14000ee9f  mov     eax, [rsp+38h+arg_10]
0x14000eea3  mov     rbx, [rsp+38h+arg_0]
0x14000eea8  add     rsp, 30h
0x14000eeac  pop     rdi
0x14000eead  retn
```
