# CDSoundDevice::InitClass(int,_GUID const *)

- ea: `0x1800f4be0`
- end: `0x1800f4c94`
- name: `?InitClass@CDSoundDevice@@SAXHPEBU_GUID@@@Z`
- size: `180`
- prototype: `void __fastcall(int, const struct _GUID *)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callees

- `0x1800388a0`
- `0x1800595dc`
- `0x1800f4be0`

## import_xrefs

- `ADVAPI32!RegOpenKeyW` at `0x1800f4c17`
- `ADVAPI32!RegOpenKeyW` at `0x1800f4c56`
- `ADVAPI32!RegOpenKeyW` at `0x1800f4c17`
- `ADVAPI32!RegOpenKeyW` at `0x1800f4c56`
- `ADVAPI32!RegCloseKey` at `0x1800f4c2c`
- `ADVAPI32!RegCloseKey` at `0x1800f4c6b`
- `ADVAPI32!RegCloseKey` at `0x1800f4c2c`
- `ADVAPI32!RegCloseKey` at `0x1800f4c6b`

## string_xrefs

- `0x1800f4c48`: `CLSID\{e436ebb3-524f-11ce-9f53-0020af0ba770}`
- `0x1800f4c09`: `CLSID\{79376820-07D0-11CF-A24D-0020AFD79767}`

## pseudocode

```c
void __fastcall CDSoundDevice::InitClass(int a1, const struct _GUID *a2)
{
  HKEY phkResult; // [rsp+20h] [rbp-28h] BYREF
  HKEY hKey; // [rsp+28h] [rbp-20h] BYREF

  if ( a1 )
  {
    phkResult = 0;
    if ( RegOpenKeyW(HKEY_CLASSES_ROOT, L"CLSID\\{79376820-07D0-11CF-A24D-0020AFD79767}", &phkResult) )
    {
      hKey = 0;
      if ( !RegOpenKeyW(HKEY_CLASSES_ROOT, L"CLSID\\{e436ebb3-524f-11ce-9f53-0020af0ba770}", &hKey) )
      {
        RegCloseKey(hKey);
        AMovieDllRegisterServer2(1);
      }
    }
    else
    {
      RegCloseKey(phkResult);
    }
  }
}

```

## disassembly

```asm
0x1800f4be0  test    ecx, ecx
0x1800f4be2  jz      locret_1800F4C92
0x1800f4be8  sub     rsp, 48h
0x1800f4bec  mov     rax, cs:__security_cookie
0x1800f4bf3  xor     rax, rsp
0x1800f4bf6  mov     [rsp+48h+var_18], rax
0x1800f4bfb  lea     r8, [rsp+48h+phkResult]; phkResult
0x1800f4c00  mov     [rsp+48h+phkResult], 0
0x1800f4c09  lea     rdx, aClsid793768200; "CLSID\\{79376820-07D0-11CF-A24D-0020AFD"...
0x1800f4c10  mov     rcx, 0FFFFFFFF80000000h; hKey
0x1800f4c17  call    cs:__imp_RegOpenKeyW
0x1800f4c1e  nop     dword ptr [rax+rax+00h]
0x1800f4c23  test    eax, eax
0x1800f4c25  jnz     short loc_1800F4C3A
0x1800f4c27  mov     rcx, [rsp+48h+phkResult]; hKey
0x1800f4c2c  call    cs:__imp_RegCloseKey
0x1800f4c33  nop     dword ptr [rax+rax+00h]
0x1800f4c38  jmp     short loc_1800F4C81
0x1800f4c3a  lea     r8, [rsp+48h+hKey]; phkResult
0x1800f4c3f  mov     [rsp+48h+hKey], 0
0x1800f4c48  lea     rdx, aClsidE436ebb35; "CLSID\\{e436ebb3-524f-11ce-9f53-0020af0"...
0x1800f4c4f  mov     rcx, 0FFFFFFFF80000000h; hKey
0x1800f4c56  call    cs:__imp_RegOpenKeyW
0x1800f4c5d  nop     dword ptr [rax+rax+00h]
0x1800f4c62  test    eax, eax
0x1800f4c64  jnz     short loc_1800F4C81
0x1800f4c66  mov     rcx, [rsp+48h+hKey]; hKey
0x1800f4c6b  call    cs:__imp_RegCloseKey
0x1800f4c72  nop     dword ptr [rax+rax+00h]
0x1800f4c77  mov     ecx, 1
0x1800f4c7c  call    AMovieDllRegisterServer2
0x1800f4c81  mov     rcx, [rsp+48h+var_18]
0x1800f4c86  xor     rcx, rsp; StackCookie
0x1800f4c89  call    __security_check_cookie
0x1800f4c8e  add     rsp, 48h
0x1800f4c92  retn
```
