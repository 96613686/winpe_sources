# WriteWPPTracingState

- ea: `0x1800bd534`
- end: `0x1800bd724`
- name: `WriteWPPTracingState`
- size: `496`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800bd2ac`

## callees

- `0x18007e3a8`
- `0x1800bb898`
- `0x1800bd26c`
- `0x1800bd534`
- `0x1800ded06`
- `0x1800ded50`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800bd640`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800bd66d`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800bd69a`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800bd640`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800bd66d`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800bd69a`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800bd607`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800bd607`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800bd6f8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800bd6f8`

## string_xrefs

- `0x1800bd5b8`: `SOFTWARE\Microsoft\Windows NT\CurrentVersion\Tracing\Microsoft\RemoteAccess\`

## pseudocode

```c
__int64 __fastcall WriteWPPTracingState(__int64 a1)
{
  unsigned int v2; // edi
  BYTE Data[8]; // [rsp+50h] [rbp-B0h] BYREF
  HKEY hKey; // [rsp+58h] [rbp-A8h] BYREF
  wchar_t pszDest[2]; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v7[524]; // [rsp+64h] [rbp-9Ch] BYREF
  int v8; // [rsp+270h] [rbp+170h] BYREF
  _BYTE v9[524]; // [rsp+274h] [rbp+174h] BYREF

  v2 = 0;
  hKey = 0;
  *(_DWORD *)pszDest = 0;
  memset_0(v7, 0, 0x206u);
  v8 = 0;
  memset_0(v9, 0, 0x206u);
  if ( a1 && *(_QWORD *)(a1 + 32) )
  {
    StringCchPrintfW(
      pszDest,
      0x105u,
      L"%s%s",
      L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\Tracing\\Microsoft\\RemoteAccess\\",
      a1 + 562);
    if ( !RegCreateKeyExW(HKEY_LOCAL_MACHINE, pszDest, 0, 0, 0, 0x20006u, 0, &hKey, 0) )
    {
      *(_DWORD *)Data = *(_DWORD *)a1;
      RegSetValueExW(hKey, L"Active", 0, 4u, Data, 4u);
      *(_DWORD *)Data = *(_DWORD *)(a1 + 4);
      RegSetValueExW(hKey, L"ControlFlags", 0, 4u, Data, 4u);
      *(_DWORD *)Data = *(_DWORD *)(a1 + 8);
      RegSetValueExW(hKey, L"ControlLevel", 0, 4u, Data, 4u);
      ConvertGuid2String(a1 + 12, 261, &v8);
      RegWriteString(hKey, L"Guid", &v8);
      RegWriteString(hKey, L"LogFileName", *(_QWORD *)(a1 + 32) + *(unsigned int *)(*(_QWORD *)(a1 + 32) + 112LL));
      v2 = 1;
    }
    if ( hKey )
      RegCloseKey(hKey);
  }
  return v2;
}

```

## disassembly

```asm
0x1800bd534  mov     [rsp-8+arg_8], rbx
0x1800bd539  mov     [rsp-8+arg_10], rdi
0x1800bd53e  push    rbp
0x1800bd53f  lea     rbp, [rsp-390h]
0x1800bd547  sub     rsp, 490h
0x1800bd54e  mov     rax, cs:__security_cookie
0x1800bd555  xor     rax, rsp
0x1800bd558  mov     [rbp+390h+var_10], rax
0x1800bd55f  mov     rbx, rcx
0x1800bd562  xor     edi, edi
0x1800bd564  lea     rcx, [rsp+490h+var_42C]; void *
0x1800bd569  mov     [rsp+490h+hKey], rdi
0x1800bd56e  xor     edx, edx; Val
0x1800bd570  mov     dword ptr [rsp+490h+pszDest], edi
0x1800bd574  mov     r8d, 206h; Size
0x1800bd57a  call    memset_0
0x1800bd57f  xor     edx, edx; Val
0x1800bd581  mov     [rbp+390h+var_220], edi
0x1800bd587  mov     r8d, 206h; Size
0x1800bd58d  lea     rcx, [rbp+390h+var_21C]; void *
0x1800bd594  call    memset_0
0x1800bd599  test    rbx, rbx
0x1800bd59c  jz      loc_1800BD6FE
0x1800bd5a2  cmp     [rbx+20h], rdi
0x1800bd5a6  jz      loc_1800BD6FE
0x1800bd5ac  lea     rax, [rbx+232h]
0x1800bd5b3  mov     edx, 105h; cchDest
0x1800bd5b8  lea     r9, aSoftwareMicros_8; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x1800bd5bf  mov     qword ptr [rsp+490h+dwOptions], rax
0x1800bd5c4  lea     r8, aSS_3; "%s%s"
0x1800bd5cb  lea     rcx, [rsp+490h+pszDest]; pszDest
0x1800bd5d0  call    StringCchPrintfW
0x1800bd5d5  mov     [rsp+490h+lpdwDisposition], rdi; lpdwDisposition
0x1800bd5da  lea     rax, [rsp+490h+hKey]
0x1800bd5df  mov     [rsp+490h+phkResult], rax; phkResult
0x1800bd5e4  lea     rdx, [rsp+490h+pszDest]; lpSubKey
0x1800bd5e9  mov     [rsp+490h+lpSecurityAttributes], rdi; lpSecurityAttributes
0x1800bd5ee  xor     r9d, r9d; lpClass
0x1800bd5f1  mov     [rsp+490h+samDesired], 20006h; samDesired
0x1800bd5f9  xor     r8d, r8d; Reserved
0x1800bd5fc  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800bd603  mov     [rsp+490h+dwOptions], edi; dwOptions
0x1800bd607  call    cs:__imp_RegCreateKeyExW
0x1800bd60d  test    eax, eax
0x1800bd60f  jnz     loc_1800BD6EE
0x1800bd615  mov     eax, [rbx]
0x1800bd617  lea     rdx, aActive; "Active"
0x1800bd61e  mov     rcx, [rsp+490h+hKey]; hKey
0x1800bd623  mov     edi, 4
0x1800bd628  mov     dword ptr [rsp+490h+Data], eax
0x1800bd62c  mov     r9d, edi; dwType
0x1800bd62f  lea     rax, [rsp+490h+Data]
0x1800bd634  mov     [rsp+490h+samDesired], edi; cbData
0x1800bd638  xor     r8d, r8d; Reserved
0x1800bd63b  mov     qword ptr [rsp+490h+dwOptions], rax; lpData
0x1800bd640  call    cs:__imp_RegSetValueExW
0x1800bd646  mov     eax, [rbx+4]
0x1800bd649  lea     rdx, aControlflags; "ControlFlags"
0x1800bd650  mov     rcx, [rsp+490h+hKey]; hKey
0x1800bd655  mov     r9d, edi; dwType
0x1800bd658  mov     dword ptr [rsp+490h+Data], eax
0x1800bd65c  xor     r8d, r8d; Reserved
0x1800bd65f  lea     rax, [rsp+490h+Data]
0x1800bd664  mov     [rsp+490h+samDesired], edi; cbData
0x1800bd668  mov     qword ptr [rsp+490h+dwOptions], rax; lpData
0x1800bd66d  call    cs:__imp_RegSetValueExW
0x1800bd673  mov     eax, [rbx+8]
0x1800bd676  lea     rdx, aControllevel; "ControlLevel"
0x1800bd67d  mov     rcx, [rsp+490h+hKey]; hKey
0x1800bd682  mov     r9d, edi; dwType
0x1800bd685  mov     dword ptr [rsp+490h+Data], eax
0x1800bd689  xor     r8d, r8d; Reserved
0x1800bd68c  lea     rax, [rsp+490h+Data]
0x1800bd691  mov     [rsp+490h+samDesired], edi; cbData
0x1800bd695  mov     qword ptr [rsp+490h+dwOptions], rax; lpData
0x1800bd69a  call    cs:__imp_RegSetValueExW
0x1800bd6a0  lea     rcx, [rbx+0Ch]
0x1800bd6a4  mov     edx, 105h
0x1800bd6a9  lea     r8, [rbp+390h+var_220]
0x1800bd6b0  call    ConvertGuid2String
0x1800bd6b5  mov     rcx, [rsp+490h+hKey]
0x1800bd6ba  lea     r8, [rbp+390h+var_220]
0x1800bd6c1  lea     rdx, aGuid_0; "Guid"
0x1800bd6c8  call    RegWriteString
0x1800bd6cd  mov     rax, [rbx+20h]
0x1800bd6d1  lea     rdx, aLogfilename; "LogFileName"
0x1800bd6d8  mov     rcx, [rsp+490h+hKey]
0x1800bd6dd  mov     r8d, [rax+70h]
0x1800bd6e1  add     r8, rax
0x1800bd6e4  call    RegWriteString
0x1800bd6e9  mov     edi, 1
0x1800bd6ee  mov     rcx, [rsp+490h+hKey]; hKey
0x1800bd6f3  test    rcx, rcx
0x1800bd6f6  jz      short loc_1800BD6FE
0x1800bd6f8  call    cs:__imp_RegCloseKey
0x1800bd6fe  mov     eax, edi
0x1800bd700  mov     rcx, [rbp+390h+var_10]
0x1800bd707  xor     rcx, rsp; StackCookie
0x1800bd70a  call    __security_check_cookie
0x1800bd70f  lea     r11, [rsp+490h+var_s0]
0x1800bd717  mov     rbx, [r11+18h]
0x1800bd71b  mov     rdi, [r11+20h]
0x1800bd71f  mov     rsp, r11
0x1800bd722  pop     rbp
0x1800bd723  retn
```
