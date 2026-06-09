# UnregisterUnknownObject(_GUID const &)

- ea: `0x18006c2e4`
- end: `0x18006c37c`
- name: `?UnregisterUnknownObject@@YAHAEBU_GUID@@@Z`
- size: `152`
- prototype: `__int64 __fastcall(const struct _GUID *)`
- caller_count: `3`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180041290`
- `0x18006ba44`
- `0x18006c168`

## callees

- `0x180066874`
- `0x18006bf3c`
- `0x18006c2e4`
- `0x180075c90`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x18006c357`
- `ADVAPI32!RegCloseKey` at `0x18006c357`
- `ADVAPI32!RegOpenKeyExA` at `0x18006c337`
- `ADVAPI32!RegOpenKeyExA` at `0x18006c337`

## string_xrefs

- `0x18006c329`: `CLSID`

## pseudocode

```c
_BOOL8 __fastcall UnregisterUnknownObject(const struct _GUID *a1)
{
  BOOL v1; // ebx
  HKEY hKey; // [rsp+30h] [rbp-138h] BYREF
  char v4[272]; // [rsp+40h] [rbp-128h] BYREF

  hKey = 0;
  if ( !StringFromGuidA(a1, v4) || RegOpenKeyExA(HKEY_CLASSES_ROOT, "CLSID", 0, 0xF003Fu, &hKey) )
    return 0;
  v1 = DeleteKeyAndSubKeys(hKey, v4);
  RegCloseKey(hKey);
  return v1;
}

```

## disassembly

```asm
0x18006c2e4  push    rbx
0x18006c2e6  sub     rsp, 160h
0x18006c2ed  mov     rax, cs:__security_cookie
0x18006c2f4  xor     rax, rsp
0x18006c2f7  mov     [rsp+168h+var_18], rax
0x18006c2ff  lea     rdx, [rsp+168h+var_128]; char *
0x18006c304  mov     [rsp+168h+hKey], 0
0x18006c30d  call    ?StringFromGuidA@@YAHAEBU_GUID@@PEAD@Z; StringFromGuidA(_GUID const &,char *)
0x18006c312  test    eax, eax
0x18006c314  jz      short loc_18006C361
0x18006c316  lea     rax, [rsp+168h+hKey]
0x18006c31b  mov     r9d, 0F003Fh; samDesired
0x18006c321  xor     r8d, r8d; ulOptions
0x18006c324  mov     [rsp+168h+phkResult], rax; phkResult
0x18006c329  lea     rdx, aClsid; "CLSID"
0x18006c330  mov     rcx, 0FFFFFFFF80000000h; hKey
0x18006c337  call    cs:__imp_RegOpenKeyExA
0x18006c33d  test    eax, eax
0x18006c33f  jnz     short loc_18006C361
0x18006c341  mov     rcx, [rsp+168h+hKey]; HKEY
0x18006c346  lea     rdx, [rsp+168h+var_128]; char *
0x18006c34b  call    ?DeleteKeyAndSubKeys@@YAHPEAUHKEY__@@PEBD@Z; DeleteKeyAndSubKeys(HKEY__ *,char const *)
0x18006c350  mov     rcx, [rsp+168h+hKey]; hKey
0x18006c355  mov     ebx, eax
0x18006c357  call    cs:__imp_RegCloseKey
0x18006c35d  mov     eax, ebx
0x18006c35f  jmp     short loc_18006C363
0x18006c361  xor     eax, eax
0x18006c363  mov     rcx, [rsp+168h+var_18]
0x18006c36b  xor     rcx, rsp; StackCookie
0x18006c36e  call    __security_check_cookie
0x18006c373  add     rsp, 160h
0x18006c37a  pop     rbx
0x18006c37b  retn
```
