# IsUpdateRelevantForState

- ea: `0x18002ab40`
- end: `0x18002ac32`
- name: `IsUpdateRelevantForState`
- size: `242`
- prototype: `__int64 __fastcall(int)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task, installer_update`

## callers

- `0x18002a910`

## callees

- `0x180007ea4`
- `0x18001b388`
- `0x18001b3a8`
- `0x18002ab40`
- `0x180033ed0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002abc8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002abe8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002abc8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002abe8`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002abb3`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002abb3`

## string_xrefs

- `0x18002ac0b`: `onecoreuap\admin\prov\lib\provagent.cpp`
- `0x18002ac20`: `onecoreuap\admin\prov\lib\provagent.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
char __fastcall IsUpdateRelevantForState(int a1)
{
  int v1; // eax
  unsigned int v2; // eax
  unsigned int phkResulta; // [rsp+20h] [rbp-248h]
  HKEY hKey; // [rsp+30h] [rbp-238h] BYREF
  WCHAR SubKey[264]; // [rsp+40h] [rbp-228h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+268h] [rbp+0h]

  v1 = StringCchPrintfW(SubKey, 0x104u, L"%s\\%s", gc_wszRegDUSettingsGroups);
  if ( v1 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x7B,
      (unsigned int)"onecoreuap\\admin\\prov\\lib\\provagent.cpp",
      (const char *)(unsigned int)v1,
      a1);
  hKey = 0;
  v2 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 1u, &hKey);
  if ( v2 == 2 )
  {
    if ( hKey )
      RegCloseKey(hKey);
    return 0;
  }
  else
  {
    if ( v2 )
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0x84,
        (unsigned int)"onecoreuap\\admin\\prov\\lib\\provagent.cpp",
        (const char *)v2,
        phkResulta);
    if ( hKey )
      RegCloseKey(hKey);
    return 1;
  }
}

```

## disassembly

```asm
0x18002ab40  sub     rsp, 268h
0x18002ab47  mov     rax, cs:__security_cookie
0x18002ab4e  xor     rax, rsp
0x18002ab51  mov     [rsp+268h+var_18], rax
0x18002ab59  mov     qword ptr [rsp+268h+phkResult], rcx; int
0x18002ab5e  mov     r9, cs:?gc_wszRegDUSettingsGroups@@3PEBGEB; ushort const * const gc_wszRegDUSettingsGroups
0x18002ab65  lea     r8, aSS; "%s\\%s"
0x18002ab6c  mov     edx, 104h; unsigned __int64
0x18002ab71  lea     rcx, [rsp+268h+SubKey]; unsigned __int16 *
0x18002ab76  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18002ab7b  mov     rcx, [rsp+268h]; this
0x18002ab83  test    eax, eax
0x18002ab85  js      loc_18002AC1D
0x18002ab8b  mov     [rsp+268h+hKey], 0
0x18002ab94  lea     rax, [rsp+268h+hKey]
0x18002ab99  mov     qword ptr [rsp+268h+phkResult], rax; unsigned int
0x18002ab9e  mov     r9d, 1; samDesired
0x18002aba4  xor     r8d, r8d; ulOptions
0x18002aba7  lea     rdx, [rsp+268h+SubKey]; lpSubKey
0x18002abac  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18002abb3  call    cs:__imp_RegOpenKeyExW
0x18002abb9  cmp     eax, 2
0x18002abbc  jnz     short loc_18002ABD2
0x18002abbe  mov     rcx, [rsp+268h+hKey]; hKey
0x18002abc3  test    rcx, rcx
0x18002abc6  jz      short loc_18002ABCE
0x18002abc8  call    cs:__imp_RegCloseKey
0x18002abce  xor     al, al
0x18002abd0  jmp     short loc_18002ABF0
0x18002abd2  mov     rcx, [rsp+268h]; this
0x18002abda  test    eax, eax
0x18002abdc  jnz     short loc_18002AC08
0x18002abde  mov     rcx, [rsp+268h+hKey]; hKey
0x18002abe3  test    rcx, rcx
0x18002abe6  jz      short loc_18002ABEE
0x18002abe8  call    cs:__imp_RegCloseKey
0x18002abee  mov     al, 1
0x18002abf0  mov     rcx, [rsp+268h+var_18]
0x18002abf8  xor     rcx, rsp; StackCookie
0x18002abfb  call    __security_check_cookie
0x18002ac00  add     rsp, 268h
0x18002ac07  retn
0x18002ac08  mov     r9d, eax; char *
0x18002ac0b  lea     r8, aOnecoreuapAdmi_6; "onecoreuap\\admin\\prov\\lib\\provagent"...
0x18002ac12  mov     edx, 84h; void *
0x18002ac17  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x18002ac1d  mov     r9d, eax; char *
0x18002ac20  lea     r8, aOnecoreuapAdmi_6; "onecoreuap\\admin\\prov\\lib\\provagent"...
0x18002ac27  mov     edx, 7Bh ; '{'; void *
0x18002ac2c  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
