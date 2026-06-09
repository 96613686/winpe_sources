# TestUserAccessToProfile

- ea: `0x18000cbe0`
- end: `0x18000cc91`
- name: `TestUserAccessToProfile`
- size: `177`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config`

## callers

- `0x18000be24`

## callees

- `0x18000cbe0`
- `0x18000d478`
- `0x18000d5d8`
- `0x180011ba0`

## import_xrefs

- `KERNEL32!GetCurrentProcess` at `0x18000cc04`
- `KERNEL32!GetCurrentProcess` at `0x18000cc04`
- `ADVAPI32!RegCloseKey` at `0x18000cc6b`
- `ADVAPI32!RegCloseKey` at `0x18000cc6b`
- `ADVAPI32!RegOpenKeyExW` at `0x18000cc5a`
- `ADVAPI32!RegOpenKeyExW` at `0x18000cc5a`

## pseudocode

```c
_BOOL8 TestUserAccessToProfile()
{
  __int64 v0; // rcx
  DWORD ProcessSid; // ebx
  HKEY hKey; // [rsp+30h] [rbp-2B8h] BYREF
  _BYTE pSid[128]; // [rsp+40h] [rbp-2A8h] BYREF
  WCHAR SubKey[264]; // [rsp+C0h] [rbp-228h] BYREF

  hKey = 0;
  GetCurrentProcess();
  ProcessSid = DaGetProcessSid(v0, pSid);
  if ( !ProcessSid )
  {
    ProcessSid = DaConvertSidToString(pSid, SubKey, 0x104u);
    if ( !ProcessSid )
    {
      ProcessSid = RegOpenKeyExW(HKEY_USERS, SubKey, 0, 0x20019u, &hKey);
      if ( !ProcessSid )
        RegCloseKey(hKey);
    }
  }
  return ProcessSid == 0;
}

```

## disassembly

```asm
0x18000cbe0  push    rbx
0x18000cbe2  sub     rsp, 2E0h
0x18000cbe9  mov     rax, cs:__security_cookie
0x18000cbf0  xor     rax, rsp
0x18000cbf3  mov     [rsp+2E8h+var_18], rax
0x18000cbfb  mov     [rsp+2E8h+hKey], 0
0x18000cc04  call    cs:__imp_GetCurrentProcess
0x18000cc0a  lea     rdx, [rsp+2E8h+pSid]
0x18000cc0f  call    DaGetProcessSid
0x18000cc14  mov     ebx, eax
0x18000cc16  test    eax, eax
0x18000cc18  jnz     short loc_18000CC71
0x18000cc1a  mov     r8d, 104h; BufferCount
0x18000cc20  lea     rdx, [rsp+2E8h+SubKey]; Buffer
0x18000cc28  lea     rcx, [rsp+2E8h+pSid]; pSid
0x18000cc2d  call    DaConvertSidToString
0x18000cc32  mov     ebx, eax
0x18000cc34  test    eax, eax
0x18000cc36  jnz     short loc_18000CC71
0x18000cc38  lea     rax, [rsp+2E8h+hKey]
0x18000cc3d  mov     r9d, 20019h; samDesired
0x18000cc43  xor     r8d, r8d; ulOptions
0x18000cc46  mov     [rsp+2E8h+phkResult], rax; phkResult
0x18000cc4b  lea     rdx, [rsp+2E8h+SubKey]; lpSubKey
0x18000cc53  mov     rcx, 0FFFFFFFF80000003h; hKey
0x18000cc5a  call    cs:__imp_RegOpenKeyExW
0x18000cc60  mov     ebx, eax
0x18000cc62  test    eax, eax
0x18000cc64  jnz     short loc_18000CC71
0x18000cc66  mov     rcx, [rsp+2E8h+hKey]; hKey
0x18000cc6b  call    cs:__imp_RegCloseKey
0x18000cc71  xor     eax, eax
0x18000cc73  test    ebx, ebx
0x18000cc75  setz    al
0x18000cc78  mov     rcx, [rsp+2E8h+var_18]
0x18000cc80  xor     rcx, rsp; StackCookie
0x18000cc83  call    __security_check_cookie
0x18000cc88  add     rsp, 2E0h
0x18000cc8f  pop     rbx
0x18000cc90  retn
```
