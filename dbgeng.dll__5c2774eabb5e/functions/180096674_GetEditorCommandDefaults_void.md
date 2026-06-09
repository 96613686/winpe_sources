# GetEditorCommandDefaults(void)

- ea: `0x180096674`
- end: `0x1800967f2`
- name: `?GetEditorCommandDefaults@@YAXXZ`
- size: `382`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x1801ae2b4`

## callees

- `0x18007daa4`
- `0x1800866c0`
- `0x18009543c`
- `0x180096674`

## import_xrefs

- `api-ms-win-crt-environment-l1-1-0!_wgetenv` at `0x180096769`
- `api-ms-win-crt-environment-l1-1-0!_wgetenv` at `0x1800967b5`
- `api-ms-win-crt-environment-l1-1-0!_wgetenv` at `0x180096769`
- `api-ms-win-crt-environment-l1-1-0!_wgetenv` at `0x1800967b5`
- `api-ms-win-core-localregistry-l1-1-0!RegOpenKeyExW` at `0x1800966a9`
- `api-ms-win-core-localregistry-l1-1-0!RegOpenKeyExW` at `0x1800966a9`
- `api-ms-win-core-localregistry-l1-1-0!RegCloseKey` at `0x180096756`
- `api-ms-win-core-localregistry-l1-1-0!RegCloseKey` at `0x180096756`
- `api-ms-win-core-localregistry-l1-1-0!RegQueryValueExW` at `0x1800966e7`
- `api-ms-win-core-localregistry-l1-1-0!RegQueryValueExW` at `0x18009673e`
- `api-ms-win-core-localregistry-l1-1-0!RegQueryValueExW` at `0x1800966e7`
- `api-ms-win-core-localregistry-l1-1-0!RegQueryValueExW` at `0x18009673e`

## string_xrefs

- `0x1800967ae`: `WINDBG_UPDATE_EDITOR`

## pseudocode

```c
void GetEditorCommandDefaults(void)
{
  bool v0; // bl
  wchar_t *v1; // rax
  wchar_t *v2; // rax
  DWORD cbData; // [rsp+50h] [rbp+20h] BYREF
  DWORD Type; // [rsp+58h] [rbp+28h] BYREF
  HKEY hKey; // [rsp+60h] [rbp+30h] BYREF

  hKey = 0;
  v0 = 0;
  if ( !RegOpenKeyExW(HKEY_CURRENT_USER, L"Software\\Microsoft\\Windiff", 0, 0x20019u, &hKey) )
  {
    Type = 0;
    cbData = 0;
    if ( !RegQueryValueExW(hKey, L"Editor", 0, &Type, 0, &cbData)
      && Type == 1
      && DbsDynamicString<unsigned short>::GetStr(&g_EditorInvokeCommand, (cbData >> 1) + 1) )
    {
      v0 = RegQueryValueExW(hKey, L"Editor", 0, &Type, g_EditorInvokeCommand, &cbData) == 0;
    }
    RegCloseKey(hKey);
  }
  v1 = _wgetenv(L"WINDBG_INVOKE_EDITOR");
  if ( (!v1 || !DbsDynamicString<unsigned short>::CopyStr(&g_EditorInvokeCommand, v1, 0xFFFFFFFFLL)) && !v0 )
    DbsDynamicString<unsigned short>::CopyStr(&g_EditorInvokeCommand, L"notepad %f", 0xFFFFFFFFLL);
  v2 = _wgetenv(L"WINDBG_UPDATE_EDITOR");
  if ( v2 )
  {
    if ( !DbsDynamicString<unsigned short>::CopyStr(&g_EditorUpdateCommand, v2, 0xFFFFFFFFLL) )
      DbsDynamicString<unsigned short>::EmptyStr(&g_EditorUpdateCommand);
  }
}

```

## disassembly

```asm
0x180096674  push    rbp
0x180096676  push    rbx
0x180096677  push    rsi
0x180096678  mov     rbp, rsp
0x18009667b  sub     rsp, 30h
0x18009667f  lea     rax, [rbp+hKey]
0x180096683  mov     [rbp+hKey], 0
0x18009668b  mov     r9d, 20019h; samDesired
0x180096691  mov     [rsp+30h+phkResult], rax; phkResult
0x180096696  xor     r8d, r8d; ulOptions
0x180096699  lea     rdx, SubKey; "Software\\Microsoft\\Windiff"
0x1800966a0  mov     rcx, 0FFFFFFFF80000001h; hKey
0x1800966a7  xor     bl, bl
0x1800966a9  call    cs:__imp_RegOpenKeyExW
0x1800966b0  nop     dword ptr [rax+rax+00h]
0x1800966b5  test    eax, eax
0x1800966b7  jnz     loc_180096762
0x1800966bd  mov     rcx, [rbp+hKey]; hKey
0x1800966c1  lea     r9, [rbp+Type]; lpType
0x1800966c5  mov     [rbp+Type], eax
0x1800966c8  lea     rdx, ValueName; "Editor"
0x1800966cf  mov     [rbp+cbData], eax
0x1800966d2  xor     r8d, r8d; lpReserved
0x1800966d5  lea     rax, [rbp+cbData]
0x1800966d9  mov     [rsp+30h+lpcbData], rax; lpcbData
0x1800966de  mov     [rsp+30h+phkResult], 0; lpData
0x1800966e7  call    cs:__imp_RegQueryValueExW
0x1800966ee  nop     dword ptr [rax+rax+00h]
0x1800966f3  test    eax, eax
0x1800966f5  jnz     short loc_180096752
0x1800966f7  lea     esi, [rax+1]
0x1800966fa  cmp     [rbp+Type], esi
0x1800966fd  jnz     short loc_180096752
0x1800966ff  mov     edx, [rbp+cbData]
0x180096702  lea     rcx, ?g_EditorInvokeCommand@@3V?$DbsDeclDynamicString@G$0GE@$00@@A; DbsDeclDynamicString<ushort,100,1> g_EditorInvokeCommand
0x180096709  shr     edx, 1
0x18009670b  add     edx, esi
0x18009670d  call    ?GetStr@?$DbsDynamicString@G@@QEAAPEAGK@Z; DbsDynamicString<ushort>::GetStr(ulong)
0x180096712  test    rax, rax
0x180096715  jz      short loc_180096752
0x180096717  mov     rax, cs:?g_EditorInvokeCommand@@3V?$DbsDeclDynamicString@G$0GE@$00@@A; DbsDeclDynamicString<ushort,100,1> g_EditorInvokeCommand
0x18009671e  lea     rcx, [rbp+cbData]
0x180096722  mov     [rsp+30h+lpcbData], rcx; lpcbData
0x180096727  lea     r9, [rbp+Type]; lpType
0x18009672b  mov     rcx, [rbp+hKey]; hKey
0x18009672f  lea     rdx, ValueName; "Editor"
0x180096736  xor     r8d, r8d; lpReserved
0x180096739  mov     [rsp+30h+phkResult], rax; lpData
0x18009673e  call    cs:__imp_RegQueryValueExW
0x180096745  nop     dword ptr [rax+rax+00h]
0x18009674a  test    eax, eax
0x18009674c  movzx   ebx, bl
0x18009674f  cmovz   ebx, esi
0x180096752  mov     rcx, [rbp+hKey]; hKey
0x180096756  call    cs:__imp_RegCloseKey
0x18009675d  nop     dword ptr [rax+rax+00h]
0x180096762  lea     rcx, aWindbgInvokeEd; "WINDBG_INVOKE_EDITOR"
0x180096769  call    cs:__imp__wgetenv
0x180096770  nop     dword ptr [rax+rax+00h]
0x180096775  or      esi, 0FFFFFFFFh
0x180096778  test    rax, rax
0x18009677b  jz      short loc_180096794
0x18009677d  mov     r8d, esi
0x180096780  lea     rcx, ?g_EditorInvokeCommand@@3V?$DbsDeclDynamicString@G$0GE@$00@@A; DbsDeclDynamicString<ushort,100,1> g_EditorInvokeCommand
0x180096787  mov     rdx, rax
0x18009678a  call    ?CopyStr@?$DbsDynamicString@G@@QEAAPEAGPEBGK@Z; DbsDynamicString<ushort>::CopyStr(ushort const *,ulong)
0x18009678f  test    rax, rax
0x180096792  jnz     short loc_1800967AE
0x180096794  test    bl, bl
0x180096796  jnz     short loc_1800967AE
0x180096798  mov     r8d, esi
0x18009679b  lea     rdx, aNotepadF; "notepad %f"
0x1800967a2  lea     rcx, ?g_EditorInvokeCommand@@3V?$DbsDeclDynamicString@G$0GE@$00@@A; DbsDeclDynamicString<ushort,100,1> g_EditorInvokeCommand
0x1800967a9  call    ?CopyStr@?$DbsDynamicString@G@@QEAAPEAGPEBGK@Z; DbsDynamicString<ushort>::CopyStr(ushort const *,ulong)
0x1800967ae  lea     rcx, aWindbgUpdateEd; "WINDBG_UPDATE_EDITOR"
0x1800967b5  call    cs:__imp__wgetenv
0x1800967bc  nop     dword ptr [rax+rax+00h]
0x1800967c1  test    rax, rax
0x1800967c4  jz      short loc_1800967E9
0x1800967c6  mov     r8d, esi
0x1800967c9  lea     rcx, ?g_EditorUpdateCommand@@3V?$DbsDeclDynamicString@G$0GE@$00@@A; DbsDeclDynamicString<ushort,100,1> g_EditorUpdateCommand
0x1800967d0  mov     rdx, rax
0x1800967d3  call    ?CopyStr@?$DbsDynamicString@G@@QEAAPEAGPEBGK@Z; DbsDynamicString<ushort>::CopyStr(ushort const *,ulong)
0x1800967d8  test    rax, rax
0x1800967db  jnz     short loc_1800967E9
0x1800967dd  lea     rcx, ?g_EditorUpdateCommand@@3V?$DbsDeclDynamicString@G$0GE@$00@@A; DbsDeclDynamicString<ushort,100,1> g_EditorUpdateCommand
0x1800967e4  call    ?EmptyStr@?$DbsDynamicString@G@@QEAAXXZ; DbsDynamicString<ushort>::EmptyStr(void)
0x1800967e9  add     rsp, 30h
0x1800967ed  pop     rsi
0x1800967ee  pop     rbx
0x1800967ef  pop     rbp
0x1800967f0  retn
```
