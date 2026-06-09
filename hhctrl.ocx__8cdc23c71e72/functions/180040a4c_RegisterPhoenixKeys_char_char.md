# RegisterPhoenixKeys(char *,char *)

- ea: `0x180040a4c`
- end: `0x180040bb4`
- name: `?RegisterPhoenixKeys@@YA_NPEAD0@Z`
- size: `360`
- prototype: `bool(char *, char *)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180041e20`

## callees

- `0x1800029b8`
- `0x1800095c8`
- `0x180040a4c`
- `0x180075c90`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x180040b8f`
- `ADVAPI32!RegCloseKey` at `0x180040b8f`
- `ADVAPI32!RegCreateKeyExA` at `0x180040b12`
- `ADVAPI32!RegCreateKeyExA` at `0x180040b12`
- `ADVAPI32!RegSetValueExA` at `0x180040b50`
- `ADVAPI32!RegSetValueExA` at `0x180040b7e`
- `ADVAPI32!RegSetValueExA` at `0x180040b50`
- `ADVAPI32!RegSetValueExA` at `0x180040b7e`

## string_xrefs

- `0x180040b77`: `Compatibility Flags`
- `0x180040b35`: `AlternateCLSID`
- `0x180040a97`: `Software\Microsoft\Internet Explorer\ActiveX Compatibility\`

## pseudocode

```c
char __fastcall RegisterPhoenixKeys(char *a1, const BYTE *a2)
{
  const char *v3; // r10
  unsigned int v4; // r11d
  __int64 v5; // rax
  char v6; // bl
  const BYTE *dwOptions; // [rsp+20h] [rbp-168h]
  HKEY hKey; // [rsp+50h] [rbp-138h] BYREF
  CHAR SubKey[272]; // [rsp+60h] [rbp-128h] BYREF

  if ( !a1 )
    return 0;
  if ( !*a1 )
    return 0;
  if ( !a2 )
    return 0;
  if ( !*a2 )
    return 0;
  if ( StringCchCopyA(SubKey, 0x104u, "Software\\Microsoft\\Internet Explorer\\ActiveX Compatibility\\") < 0 )
    return 0;
  if ( (int)StringCchCatA(SubKey, v4, v3) < 0 )
    return 0;
  hKey = 0;
  if ( RegCreateKeyExA(HKEY_LOCAL_MACHINE, SubKey, 0, 0, 0, 0xF003Fu, 0, &hKey, 0) || !hKey )
    return 0;
  v5 = -1;
  do
    ++v5;
  while ( a2[v5] );
  dwOptions = a2;
  v6 = 1;
  if ( RegSetValueExA(hKey, "AlternateCLSID", 0, 1u, dwOptions, v5 + 1)
    || RegSetValueExA(hKey, "Compatibility Flags", 0, 4u, &Data, 4u) )
  {
    v6 = 0;
  }
  RegCloseKey(hKey);
  return v6;
}

```

## disassembly

```asm
0x180040a4c  push    rbx
0x180040a4e  sub     rsp, 180h
0x180040a55  mov     rax, cs:__security_cookie
0x180040a5c  xor     rax, rsp
0x180040a5f  mov     [rsp+188h+var_18], rax
0x180040a67  mov     rbx, rdx
0x180040a6a  mov     r10, rcx
0x180040a6d  test    rcx, rcx
0x180040a70  jz      loc_180040B99
0x180040a76  cmp     byte ptr [rcx], 0
0x180040a79  jz      loc_180040B99
0x180040a7f  test    rdx, rdx
0x180040a82  jz      loc_180040B99
0x180040a88  cmp     byte ptr [rdx], 0
0x180040a8b  jz      loc_180040B99
0x180040a91  mov     r11d, 104h
0x180040a97  lea     r8, aSoftwareMicros_5; "Software\\Microsoft\\Internet Explorer"...
0x180040a9e  mov     edx, r11d; unsigned __int64
0x180040aa1  lea     rcx, [rsp+188h+SubKey]; char *
0x180040aa6  call    ?StringCchCopyA@@YAJPEAD_KPEBD@Z; StringCchCopyA(char *,unsigned __int64,char const *)
0x180040aab  test    eax, eax
0x180040aad  js      loc_180040B99
0x180040ab3  mov     r8, r10; char *
0x180040ab6  lea     rcx, [rsp+188h+SubKey]; char *
0x180040abb  mov     edx, r11d; unsigned __int64
0x180040abe  call    ?StringCchCatA@@YAJPEAD_KPEBD@Z; StringCchCatA(char *,unsigned __int64,char const *)
0x180040ac3  test    eax, eax
0x180040ac5  js      loc_180040B99
0x180040acb  mov     [rsp+188h+lpdwDisposition], 0; lpdwDisposition
0x180040ad4  lea     rax, [rsp+188h+hKey]
0x180040ad9  mov     [rsp+188h+phkResult], rax; phkResult
0x180040ade  lea     rdx, [rsp+188h+SubKey]; lpSubKey
0x180040ae3  mov     [rsp+188h+lpSecurityAttributes], 0; lpSecurityAttributes
0x180040aec  xor     r9d, r9d; lpClass
0x180040aef  mov     [rsp+188h+samDesired], 0F003Fh; samDesired
0x180040af7  xor     r8d, r8d; Reserved
0x180040afa  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180040b01  mov     [rsp+188h+dwOptions], 0; dwOptions
0x180040b09  mov     [rsp+188h+hKey], 0
0x180040b12  call    cs:__imp_RegCreateKeyExA
0x180040b18  test    eax, eax
0x180040b1a  jnz     short loc_180040B99
0x180040b1c  mov     rcx, [rsp+188h+hKey]; hKey
0x180040b21  test    rcx, rcx
0x180040b24  jz      short loc_180040B99
0x180040b26  or      rax, 0FFFFFFFFFFFFFFFFh
0x180040b2a  inc     rax
0x180040b2d  cmp     byte ptr [rbx+rax], 0
0x180040b31  jnz     short loc_180040B2A
0x180040b33  inc     eax
0x180040b35  lea     rdx, aAlternateclsid; "AlternateCLSID"
0x180040b3c  mov     [rsp+188h+samDesired], eax; cbData
0x180040b40  xor     r8d, r8d; Reserved
0x180040b43  mov     qword ptr [rsp+188h+dwOptions], rbx; lpData
0x180040b48  mov     ebx, 1
0x180040b4d  mov     r9d, ebx; dwType
0x180040b50  call    cs:__imp_RegSetValueExA
0x180040b56  test    eax, eax
0x180040b58  jnz     short loc_180040B88
0x180040b5a  mov     rcx, [rsp+188h+hKey]; hKey
0x180040b5f  lea     r9d, [rbx+3]; dwType
0x180040b63  lea     rax, Data
0x180040b6a  mov     [rsp+188h+samDesired], r9d; cbData
0x180040b6f  xor     r8d, r8d; Reserved
0x180040b72  mov     qword ptr [rsp+188h+dwOptions], rax; lpData
0x180040b77  lea     rdx, aCompatibilityF; "Compatibility Flags"
0x180040b7e  call    cs:__imp_RegSetValueExA
0x180040b84  test    eax, eax
0x180040b86  jz      short loc_180040B8A
0x180040b88  xor     bl, bl
0x180040b8a  mov     rcx, [rsp+188h+hKey]; hKey
0x180040b8f  call    cs:__imp_RegCloseKey
0x180040b95  mov     al, bl
0x180040b97  jmp     short loc_180040B9B
0x180040b99  xor     al, al
0x180040b9b  mov     rcx, [rsp+188h+var_18]
0x180040ba3  xor     rcx, rsp; StackCookie
0x180040ba6  call    __security_check_cookie
0x180040bab  add     rsp, 180h
0x180040bb2  pop     rbx
0x180040bb3  retn
```
