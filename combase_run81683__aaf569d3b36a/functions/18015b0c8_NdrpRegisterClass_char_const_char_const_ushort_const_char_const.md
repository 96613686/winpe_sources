# NdrpRegisterClass(char const *,char const *,ushort const *,char const *)

- ea: `0x18015b0c8`
- end: `0x18015b2be`
- name: `?NdrpRegisterClass@@YAJPEBD0PEBG0@Z`
- size: `502`
- prototype: `__int64 __fastcall(const char *pszClassID, const char *pszDllFileName, const BYTE *, const char *pszClassName)`
- caller_count: `2`
- callee_count: `1`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18015abf0`
- `0x1801f6ae0`

## callees

- `0x18015b0c8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExA` at `0x18015b137`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExA` at `0x18015b17c`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExA` at `0x18015b1c5`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExA` at `0x18015b137`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExA` at `0x18015b17c`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExA` at `0x18015b1c5`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExA` at `0x18015b23a`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExA` at `0x18015b275`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExA` at `0x18015b23a`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExA` at `0x18015b275`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18015b246`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18015b281`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18015b28b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18015b246`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18015b281`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18015b28b`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18015b209`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18015b209`

## string_xrefs

- `0x18015b104`: `CLSID`
- `0x18015b228`: `ThreadingModel`

## pseudocode

```c
__int64 __fastcall NdrpRegisterClass(
        const char *pszClassID,
        const char *pszDllFileName,
        const BYTE *a3,
        const char *pszClassName)
{
  LSTATUS v6; // ebx
  __int64 v7; // rax
  bool v8; // cc
  HKEY__ *hKeyClassID; // [rsp+50h] [rbp-10h] BYREF
  HKEY__ *hKeyCLSID; // [rsp+58h] [rbp-8h] BYREF
  HKEY__ *hKey; // [rsp+88h] [rbp+28h] BYREF
  unsigned int dwDisposition; // [rsp+98h] [rbp+38h] BYREF
  int v14; // [rsp+9Ch] [rbp+3Ch]

  v14 = HIDWORD(pszClassName);
  hKeyCLSID = 0;
  hKeyClassID = 0;
  hKey = 0;
  dwDisposition = 0;
  v6 = RegCreateKeyExA(HKEY_CLASSES_ROOT, "CLSID", 0, (LPSTR)"REG_SZ", 0, 0x20006u, 0, &hKeyCLSID, &dwDisposition);
  if ( v6 )
  {
    v8 = v6 < 0;
  }
  else
  {
    v6 = RegCreateKeyExA(hKeyCLSID, pszClassID, 0, (LPSTR)"REG_SZ", 0, 0x20006u, 0, &hKeyClassID, &dwDisposition);
    if ( !v6 )
    {
      v6 = RegCreateKeyExA(hKeyClassID, "InProcServer32", 0, (LPSTR)"REG_SZ", 0, 0x20006u, 0, &hKey, &dwDisposition);
      if ( !v6 )
      {
        v7 = -1;
        do
          ++v7;
        while ( *(_WORD *)&a3[2 * v7] );
        v6 = RegSetValueExW(hKey, &pszValueToSet, 0, 1u, a3, 2 * v7 + 2);
        if ( !v6 )
          v6 = RegSetValueExA(hKey, "ThreadingModel", 0, 1u, "Both", 5u);
        RegCloseKey(hKey);
        if ( !v6 )
          v6 = RegSetValueExA(hKeyClassID, Description4, 0, 1u, "PSFactoryBuffer", 0x10u);
      }
      RegCloseKey(hKeyClassID);
    }
    RegCloseKey(hKeyCLSID);
    v8 = v6 <= 0;
    if ( !v6 )
      return 0;
  }
  if ( !v8 )
    return (unsigned __int16)v6 | 0x80070000;
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18015b0c8  mov     r11, rsp
0x18015b0cb  mov     [r11+8], rbx
0x18015b0cf  mov     [r11+18h], rsi
0x18015b0d3  mov     [r11+20h], r9
0x18015b0d7  mov     [r11+10h], rdx
0x18015b0db  push    rbp
0x18015b0dc  push    rdi
0x18015b0dd  push    r14
0x18015b0df  mov     rbp, rsp
0x18015b0e2  sub     rsp, 60h
0x18015b0e6  xor     r14d, r14d
0x18015b0e9  lea     rax, [rbp+dwDisposition]
0x18015b0ed  mov     [r11-38h], rax
0x18015b0f1  lea     r9, Class; "REG_SZ"
0x18015b0f8  lea     rax, [rbp+hKeyCLSID]
0x18015b0fc  mov     [rbp+hKeyCLSID], r14
0x18015b100  mov     [r11-40h], rax
0x18015b104  lea     rdx, aClsid_0; "CLSID"
0x18015b10b  mov     [r11-48h], r14
0x18015b10f  mov     rdi, pszDllFileName
0x18015b112  mov     rsi, pszClassID
0x18015b115  mov     [rsp+60h+samDesired], 20006h; samDesired
0x18015b11d  xor     r8d, r8d; Reserved
0x18015b120  mov     [r11-58h], r14d
0x18015b124  mov     pszClassID, 0FFFFFFFF80000000h; hKey
0x18015b12b  mov     [rbp+hKeyClassID], r14
0x18015b12f  mov     [rbp+hKey], r14
0x18015b133  mov     [rbp+dwDisposition], r14d
0x18015b137  call    cs:__imp_RegCreateKeyExA
0x18015b13d  mov     ebx, eax
0x18015b13f  test    eax, eax
0x18015b141  jnz     loc_18015B29A
0x18015b147  mov     pszClassID, [rbp+hKeyCLSID]; hKey
0x18015b14b  lea     rax, [rbp+dwDisposition]
0x18015b14f  mov     [rsp+60h+lpdwDisposition], rax; lpdwDisposition
0x18015b154  lea     r9, Class; "REG_SZ"
0x18015b15b  lea     rax, [rbp+hKeyClassID]
0x18015b15f  xor     r8d, r8d; Reserved
0x18015b162  mov     [rsp+60h+phkResult], rax; phkResult
0x18015b167  mov     rdx, rsi; lpSubKey
0x18015b16a  mov     [rsp+60h+lpSecurityAttributes], r14; lpSecurityAttributes
0x18015b16f  mov     [rsp+60h+samDesired], 20006h; samDesired
0x18015b177  mov     [rsp+60h+dwOptions], r14d; dwOptions
0x18015b17c  call    cs:__imp_RegCreateKeyExA
0x18015b182  mov     ebx, eax
0x18015b184  test    eax, eax
0x18015b186  jnz     loc_18015B287
0x18015b18c  mov     pszClassID, [rbp+hKeyClassID]; hKey
0x18015b190  lea     rax, [rbp+dwDisposition]
0x18015b194  mov     [rsp+60h+lpdwDisposition], rax; lpdwDisposition
0x18015b199  lea     r9, Class; "REG_SZ"
0x18015b1a0  lea     rax, [rbp+hKey]
0x18015b1a4  xor     r8d, r8d; Reserved
0x18015b1a7  mov     [rsp+60h+phkResult], rax; phkResult
0x18015b1ac  lea     rdx, aInprocserver32; "InProcServer32"
0x18015b1b3  mov     [rsp+60h+lpSecurityAttributes], r14; lpSecurityAttributes
0x18015b1b8  mov     [rsp+60h+samDesired], 20006h; samDesired
0x18015b1c0  mov     [rsp+60h+dwOptions], r14d; dwOptions
0x18015b1c5  call    cs:__imp_RegCreateKeyExA
0x18015b1cb  mov     ebx, eax
0x18015b1cd  test    eax, eax
0x18015b1cf  jnz     loc_18015B27D
0x18015b1d5  or      rax, 0FFFFFFFFFFFFFFFFh
0x18015b1d9  inc     rax
0x18015b1dc  cmp     [rdi+rax*2], r14w
0x18015b1e1  jnz     short loc_18015B1D9
0x18015b1e3  mov     pszClassID, [rbp+hKey]; hKey
0x18015b1e7  lea     eax, ds:2[rax*2]
0x18015b1ee  mov     [rsp+60h+samDesired], eax; cbData
0x18015b1f2  lea     rdx, pszValueToSet; lpValueName
0x18015b1f9  mov     qword ptr [rsp+60h+dwOptions], rdi; lpData
0x18015b1fe  xor     r8d, r8d; Reserved
0x18015b201  mov     edi, 1
0x18015b206  mov     r9d, edi; dwType
0x18015b209  call    cs:__imp_RegSetValueExW
0x18015b20f  mov     ebx, eax
0x18015b211  test    eax, eax
0x18015b213  jnz     short loc_18015B242
0x18015b215  mov     pszClassID, [rbp+hKey]; hKey
0x18015b219  lea     rax, Data; "Both"
0x18015b220  mov     [rsp+60h+samDesired], 5; cbData
0x18015b228  lea     rdx, aThreadingmodel; "ThreadingModel"
0x18015b22f  mov     r9d, edi; dwType
0x18015b232  mov     qword ptr [rsp+60h+dwOptions], rax; lpData
0x18015b237  xor     r8d, r8d; Reserved
0x18015b23a  call    cs:__imp_RegSetValueExA
0x18015b240  mov     ebx, eax
0x18015b242  mov     pszClassID, [rbp+hKey]; hKey
0x18015b246  call    cs:__imp_RegCloseKey
0x18015b24c  test    ebx, ebx
0x18015b24e  jnz     short loc_18015B27D
0x18015b250  mov     pszClassID, [rbp+hKeyClassID]; hKey
0x18015b254  lea     rax, aPsfactorybuffe; "PSFactoryBuffer"
0x18015b25b  mov     [rsp+60h+samDesired], 10h; cbData
0x18015b263  lea     rdx, Description4; lpValueName
0x18015b26a  mov     r9d, edi; dwType
0x18015b26d  mov     qword ptr [rsp+60h+dwOptions], rax; lpData
0x18015b272  xor     r8d, r8d; Reserved
0x18015b275  call    cs:__imp_RegSetValueExA
0x18015b27b  mov     ebx, eax
0x18015b27d  mov     pszClassID, [rbp+hKeyClassID]; hKey
0x18015b281  call    cs:__imp_RegCloseKey
0x18015b287  mov     pszClassID, [rbp+hKeyCLSID]; hKey
0x18015b28b  call    cs:__imp_RegCloseKey
0x18015b291  test    ebx, ebx
0x18015b293  jnz     short loc_18015B29C
0x18015b295  mov     ebx, r14d
0x18015b298  jmp     short loc_18015B2A7
0x18015b29a  test    ebx, ebx
0x18015b29c  jle     short loc_18015B2A7
0x18015b29e  movzx   ebx, bx
0x18015b2a1  or      ebx, 80070000h
0x18015b2a7  lea     r11, [rsp+60h+var_s0]
0x18015b2ac  mov     eax, ebx
0x18015b2ae  mov     rbx, [r11+20h]
0x18015b2b2  mov     rsi, [r11+30h]
0x18015b2b6  mov     rsp, r11
0x18015b2b9  pop     r14
0x18015b2bb  pop     rdi
0x18015b2bc  pop     rbp
0x18015b2bd  retn
```
