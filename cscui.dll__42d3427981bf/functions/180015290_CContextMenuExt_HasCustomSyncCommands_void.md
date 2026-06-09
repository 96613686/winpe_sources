# CContextMenuExt::_HasCustomSyncCommands(void)

- ea: `0x180015290`
- end: `0x1800153dd`
- name: `?_HasCustomSyncCommands@CContextMenuExt@@AEAAHXZ`
- size: `333`
- prototype: `__int64 __fastcall(CContextMenuExt *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800051f0`

## callees

- `0x180015290`
- `0x18004c670`
- `0x18004d010`

## import_xrefs

- `SHELL32!__imp_SHCoCreateInstance` at `0x180015352`
- `SHELL32!__imp_SHCoCreateInstance` at `0x180015352`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800152dc`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180015328`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800152dc`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180015328`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800153aa`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800153b4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800153aa`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800153b4`
- `ADVAPI32!RegEnumKeyW` at `0x1800152f8`
- `ADVAPI32!RegEnumKeyW` at `0x1800152f8`

## string_xrefs

- `0x1800152ca`: `SyncCommands\shell`
- `0x18001531a`: `SyncCommands`

## pseudocode

```c
_BOOL8 __fastcall CContextMenuExt::_HasCustomSyncCommands(CContextMenuExt *this)
{
  BOOL v1; // ebx
  void *ppv; // [rsp+30h] [rbp-79h] BYREF
  HKEY phkResult; // [rsp+38h] [rbp-71h] BYREF
  HKEY hKey; // [rsp+40h] [rbp-69h] BYREF
  WCHAR Name[80]; // [rsp+50h] [rbp-59h] BYREF

  v1 = 0;
  hKey = 0;
  if ( !RegOpenKeyExW(HKEY_CLASSES_ROOT, L"SyncCommands\\shell", 0, 8u, &hKey) )
  {
    if ( !RegEnumKeyW(hKey, 0, Name, 0x50u) )
    {
      phkResult = 0;
      if ( !RegOpenKeyExW(HKEY_CLASSES_ROOT, L"SyncCommands", 0, 9u, &phkResult) )
      {
        ppv = 0;
        if ( SHCoCreateInstance(
               0,
               &CLSID_ExplorerCommandEnumerator,
               0,
               &GUID_d960050c_f4e1_4294_ac4b_598913605923,
               &ppv) >= 0 )
        {
          if ( (*(int (__fastcall **)(void *, HKEY))(*(_QWORD *)ppv + 24LL))(ppv, phkResult) >= 0 )
            v1 = (**(int (__fastcall ***)(void *, GUID *, char *))ppv)(
                   ppv,
                   &GUID_a88826f8_186f_4987_aade_ea0cef8fbfe8,
                   (char *)this + 48) >= 0;
          (*(void (__fastcall **)(void *))(*(_QWORD *)ppv + 16LL))(ppv);
        }
        RegCloseKey(phkResult);
      }
    }
    RegCloseKey(hKey);
  }
  return v1;
}

```

## disassembly

```asm
0x180015290  mov     [rsp-8+arg_8], rbx
0x180015295  mov     [rsp-8+arg_10], rdi
0x18001529a  push    rbp
0x18001529b  lea     rbp, [rsp-57h]
0x1800152a0  sub     rsp, 100h
0x1800152a7  mov     rax, cs:__security_cookie
0x1800152ae  xor     rax, rsp
0x1800152b1  mov     [rbp+57h+var_10], rax
0x1800152b5  xor     ebx, ebx
0x1800152b7  lea     rax, [rbp+57h+hKey]
0x1800152bb  mov     rdi, rcx
0x1800152be  mov     [rbp+57h+hKey], rbx
0x1800152c2  xor     r8d, r8d; ulOptions
0x1800152c5  mov     [rsp+100h+phkResult], rax; phkResult
0x1800152ca  lea     rdx, aSynccommandsSh; "SyncCommands\\shell"
0x1800152d1  mov     rcx, 0FFFFFFFF80000000h; hKey
0x1800152d8  lea     r9d, [rbx+8]; samDesired
0x1800152dc  call    cs:__imp_RegOpenKeyExW
0x1800152e2  test    eax, eax
0x1800152e4  jnz     loc_1800153BA
0x1800152ea  mov     rcx, [rbp+57h+hKey]; hKey
0x1800152ee  lea     r9d, [rbx+50h]; cchName
0x1800152f2  lea     r8, [rbp+57h+Name]; lpName
0x1800152f6  xor     edx, edx; dwIndex
0x1800152f8  call    cs:__imp_RegEnumKeyW
0x1800152fe  test    eax, eax
0x180015300  jnz     loc_1800153B0
0x180015306  lea     rax, [rbp+57h+var_C8]
0x18001530a  mov     [rbp+57h+var_C8], rbx
0x18001530e  lea     r9d, [rbx+9]; samDesired
0x180015312  mov     [rsp+100h+phkResult], rax; phkResult
0x180015317  xor     r8d, r8d; ulOptions
0x18001531a  lea     rdx, aSynccommands; "SyncCommands"
0x180015321  mov     rcx, 0FFFFFFFF80000000h; hKey
0x180015328  call    cs:__imp_RegOpenKeyExW
0x18001532e  test    eax, eax
0x180015330  jnz     short loc_1800153B0
0x180015332  lea     rax, [rbp+57h+ppv]
0x180015336  mov     [rbp+57h+ppv], rbx
0x18001533a  lea     r9, _GUID_d960050c_f4e1_4294_ac4b_598913605923; riid
0x180015341  mov     [rsp+100h+phkResult], rax; ppv
0x180015346  xor     r8d, r8d; pUnkOuter
0x180015349  lea     rdx, CLSID_ExplorerCommandEnumerator; pclsid
0x180015350  xor     ecx, ecx; pszCLSID
0x180015352  call    cs:__imp_SHCoCreateInstance
0x180015358  test    eax, eax
0x18001535a  js      short loc_1800153A6
0x18001535c  mov     rcx, [rbp+57h+ppv]
0x180015360  mov     rdx, [rbp+57h+var_C8]
0x180015364  mov     rax, [rcx]
0x180015367  mov     rax, [rax+18h]
0x18001536b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015370  test    eax, eax
0x180015372  js      short loc_180015396
0x180015374  mov     rcx, [rbp+57h+ppv]
0x180015378  lea     r8, [rdi+30h]
0x18001537c  lea     rdx, _GUID_a88826f8_186f_4987_aade_ea0cef8fbfe8
0x180015383  mov     rax, [rcx]
0x180015386  mov     rax, [rax]
0x180015389  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001538e  test    eax, eax
0x180015390  lea     ecx, [rbx+1]
0x180015393  cmovns  ebx, ecx
0x180015396  mov     rcx, [rbp+57h+ppv]
0x18001539a  mov     rax, [rcx]
0x18001539d  mov     rax, [rax+10h]
0x1800153a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800153a6  mov     rcx, [rbp+57h+var_C8]; hKey
0x1800153aa  call    cs:__imp_RegCloseKey
0x1800153b0  mov     rcx, [rbp+57h+hKey]; hKey
0x1800153b4  call    cs:__imp_RegCloseKey
0x1800153ba  mov     eax, ebx
0x1800153bc  mov     rcx, [rbp+57h+var_10]
0x1800153c0  xor     rcx, rsp; StackCookie
0x1800153c3  call    __security_check_cookie
0x1800153c8  lea     r11, [rsp+100h+var_s0]
0x1800153d0  mov     rbx, [r11+18h]
0x1800153d4  mov     rdi, [r11+20h]
0x1800153d8  mov     rsp, r11
0x1800153db  pop     rbp
0x1800153dc  retn
```
