# NdrpRegisterInterface

- ea: `0x180085cbc`
- end: `0x180085ee5`
- name: `NdrpRegisterInterface`
- size: `553`
- prototype: `__int64 __usercall@<rax>(HKEY hKey@<rcx>, int)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180085eec`

## callees

- `0x18004d900`
- `0x180063204`
- `0x180085cbc`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__itoa_s` at `0x180085e60`
- `api-ms-win-crt-private-l1-1-0!_o__itoa_s` at `0x180085e60`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExA` at `0x180085dbb`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExA` at `0x180085e04`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExA` at `0x180085e97`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExA` at `0x180085dbb`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExA` at `0x180085e04`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExA` at `0x180085e97`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180085dc7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180085ea3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180085ead`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180085dc7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180085ea3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180085ead`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExA` at `0x180085d44`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExA` at `0x180085d85`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExA` at `0x180085e45`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExA` at `0x180085d44`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExA` at `0x180085d85`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExA` at `0x180085e45`

## string_xrefs

- `0x180085d61`: `ProxyStubClsid32`

## pseudocode

```c
__int64 __fastcall NdrpRegisterInterface(HKEY hKey, __int64 a2, const BYTE *a3, __int64 a4, unsigned int a5)
{
  const BYTE *v6; // rsi
  bool v7; // zf
  LSTATUS v8; // ebx
  __int64 v9; // rdi
  __int64 v10; // rax
  bool v11; // cc
  HKEY phkResult; // [rsp+50h] [rbp-21h] BYREF
  HKEY hKeya; // [rsp+58h] [rbp-19h] BYREF
  BYTE Data[8]; // [rsp+60h] [rbp-11h] BYREF
  CHAR SubKey[16]; // [rsp+68h] [rbp-9h] BYREF
  _BYTE v17[23]; // [rsp+78h] [rbp+7h] BYREF

  v6 = a3 + 1;
  v7 = *a3 == 95;
  memset(v17, 0, sizeof(v17));
  if ( !v7 )
    v6 = a3;
  phkResult = 0;
  *(_OWORD *)SubKey = 0;
  hKeya = 0;
  StringFromGUID2A(a2, SubKey);
  v8 = RegCreateKeyExA(hKey, SubKey, 0, 0, 0, 0x2000000u, 0, &hKeya, 0);
  if ( v8 )
  {
    v11 = v8 < 0;
  }
  else
  {
    v8 = RegCreateKeyExA(hKeya, "ProxyStubClsid32", 0, 0, 0, 0x2000000u, 0, &phkResult, 0);
    if ( !v8 )
    {
      v8 = RegSetValueExA(phkResult, g_szNull, 0, 1u, "{B196B286-BAB4-101A-B69C-00AA00341D07}", 0x27u);
      RegCloseKey(phkResult);
      if ( !v8 )
      {
        v9 = -1;
        v10 = -1;
        do
          ++v10;
        while ( v6[v10] );
        v8 = RegSetValueExA(hKeya, g_szNull, 0, 1u, v6, v10 + 1);
        if ( !v8 )
        {
          v8 = RegCreateKeyExA(hKeya, "NumMethods", 0, 0, 0, 0x2000000u, 0, &phkResult, 0);
          if ( !v8 )
          {
            _o__itoa_s(a5, Data, 6, 10);
            do
              ++v9;
            while ( Data[v9] );
            v8 = RegSetValueExA(phkResult, g_szNull, 0, 1u, Data, v9 + 1);
            RegCloseKey(phkResult);
          }
        }
      }
    }
    RegCloseKey(hKeya);
    v11 = v8 <= 0;
    if ( !v8 )
      return 0;
  }
  if ( !v11 )
    return (unsigned __int16)v8 | 0x80070000;
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180085cbc  push    rbp
0x180085cbe  push    rbx
0x180085cbf  push    rsi
0x180085cc0  push    rdi
0x180085cc1  push    r14
0x180085cc3  lea     rbp, [rsp-2Fh]
0x180085cc8  sub     rsp, 0A0h
0x180085ccf  mov     rax, cs:__security_cookie
0x180085cd6  xor     rax, rsp
0x180085cd9  mov     [rbp+4Fh+var_30], rax
0x180085cdd  mov     rbx, rcx
0x180085ce0  lea     rsi, [r8+1]
0x180085ce4  xor     ecx, ecx
0x180085ce6  xorps   xmm0, xmm0
0x180085ce9  xor     r14d, r14d
0x180085cec  mov     rax, rdx
0x180085cef  cmp     byte ptr [r8], 5Fh ; '_'
0x180085cf3  lea     rdx, [rbp+4Fh+SubKey]
0x180085cf7  movups  xmmword ptr [rbp+4Fh+var_48], xmm0
0x180085cfb  mov     qword ptr [rbp+4Fh+var_48+0Fh], rcx
0x180085cff  cmovnz  rsi, r8
0x180085d03  mov     rcx, rax
0x180085d06  mov     [rbp+4Fh+var_70], r14
0x180085d0a  movups  xmmword ptr [rbp+4Fh+SubKey], xmm0
0x180085d0e  mov     [rbp+4Fh+hKey], r14
0x180085d12  call    StringFromGUID2A
0x180085d17  mov     [rsp+0C0h+lpdwDisposition], r14; lpdwDisposition
0x180085d1c  lea     rax, [rbp+4Fh+hKey]
0x180085d20  mov     [rsp+0C0h+phkResult], rax; phkResult
0x180085d25  lea     rdx, [rbp+4Fh+SubKey]; lpSubKey
0x180085d29  mov     [rsp+0C0h+lpSecurityAttributes], r14; lpSecurityAttributes
0x180085d2e  xor     r9d, r9d; lpClass
0x180085d31  mov     [rsp+0C0h+samDesired], 2000000h; samDesired
0x180085d39  xor     r8d, r8d; Reserved
0x180085d3c  mov     rcx, rbx; hKey
0x180085d3f  mov     [rsp+0C0h+dwOptions], r14d; dwOptions
0x180085d44  call    cs:__imp_RegCreateKeyExA
0x180085d4a  mov     ebx, eax
0x180085d4c  test    eax, eax
0x180085d4e  jnz     loc_180085EBC
0x180085d54  mov     rcx, [rbp+4Fh+hKey]; hKey
0x180085d58  lea     rax, [rbp+4Fh+var_70]
0x180085d5c  mov     [rsp+0C0h+lpdwDisposition], r14; lpdwDisposition
0x180085d61  lea     rdx, g_szProxyStubClsid32; "ProxyStubClsid32"
0x180085d68  mov     [rsp+0C0h+phkResult], rax; phkResult
0x180085d6d  xor     r9d, r9d; lpClass
0x180085d70  mov     [rsp+0C0h+lpSecurityAttributes], r14; lpSecurityAttributes
0x180085d75  xor     r8d, r8d; Reserved
0x180085d78  mov     [rsp+0C0h+samDesired], 2000000h; samDesired
0x180085d80  mov     [rsp+0C0h+dwOptions], r14d; dwOptions
0x180085d85  call    cs:__imp_RegCreateKeyExA
0x180085d8b  mov     ebx, eax
0x180085d8d  test    eax, eax
0x180085d8f  jnz     loc_180085EA9
0x180085d95  mov     rcx, [rbp+4Fh+var_70]; hKey
0x180085d99  lea     rax, Data; "{B196B286-BAB4-101A-B69C-00AA00341D07}"
0x180085da0  mov     [rsp+0C0h+samDesired], 27h ; '''; cbData
0x180085da8  lea     r9d, [r14+1]; dwType
0x180085dac  xor     r8d, r8d; Reserved
0x180085daf  mov     qword ptr [rsp+0C0h+dwOptions], rax; lpData
0x180085db4  lea     rdx, g_szNull; lpValueName
0x180085dbb  call    cs:__imp_RegSetValueExA
0x180085dc1  mov     rcx, [rbp+4Fh+var_70]; hKey
0x180085dc5  mov     ebx, eax
0x180085dc7  call    cs:__imp_RegCloseKey
0x180085dcd  test    ebx, ebx
0x180085dcf  jnz     loc_180085EA9
0x180085dd5  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180085dd9  mov     rax, rdi
0x180085ddc  inc     rax
0x180085ddf  cmp     [rsi+rax], r14b
0x180085de3  jnz     short loc_180085DDC
0x180085de5  mov     rcx, [rbp+4Fh+hKey]; hKey
0x180085de9  lea     rdx, g_szNull; lpValueName
0x180085df0  inc     eax
0x180085df2  mov     r9d, 1; dwType
0x180085df8  mov     [rsp+0C0h+samDesired], eax; cbData
0x180085dfc  xor     r8d, r8d; Reserved
0x180085dff  mov     qword ptr [rsp+0C0h+dwOptions], rsi; lpData
0x180085e04  call    cs:__imp_RegSetValueExA
0x180085e0a  mov     ebx, eax
0x180085e0c  test    eax, eax
0x180085e0e  jnz     loc_180085EA9
0x180085e14  mov     rcx, [rbp+4Fh+hKey]; hKey
0x180085e18  lea     rax, [rbp+4Fh+var_70]
0x180085e1c  mov     [rsp+0C0h+lpdwDisposition], r14; lpdwDisposition
0x180085e21  lea     rdx, g_szNumMethods; "NumMethods"
0x180085e28  mov     [rsp+0C0h+phkResult], rax; phkResult
0x180085e2d  xor     r9d, r9d; lpClass
0x180085e30  mov     [rsp+0C0h+lpSecurityAttributes], r14; lpSecurityAttributes
0x180085e35  xor     r8d, r8d; Reserved
0x180085e38  mov     [rsp+0C0h+samDesired], 2000000h; samDesired
0x180085e40  mov     [rsp+0C0h+dwOptions], r14d; dwOptions
0x180085e45  call    cs:__imp_RegCreateKeyExA
0x180085e4b  mov     ebx, eax
0x180085e4d  test    eax, eax
0x180085e4f  jnz     short loc_180085EA9
0x180085e51  mov     ecx, [rbp+4Fh+arg_20]
0x180085e54  lea     r9d, [rax+0Ah]
0x180085e58  lea     r8d, [rax+6]
0x180085e5c  lea     rdx, [rbp+4Fh+Data]
0x180085e60  call    cs:__imp__o__itoa_s
0x180085e66  lea     rax, [rbp+4Fh+Data]
0x180085e6a  inc     rdi
0x180085e6d  cmp     [rax+rdi], r14b
0x180085e71  jnz     short loc_180085E6A
0x180085e73  mov     rcx, [rbp+4Fh+var_70]; hKey
0x180085e77  lea     eax, [rdi+1]
0x180085e7a  mov     [rsp+0C0h+samDesired], eax; cbData
0x180085e7e  lea     rdx, g_szNull; lpValueName
0x180085e85  lea     rax, [rbp+4Fh+Data]
0x180085e89  mov     r9d, 1; dwType
0x180085e8f  xor     r8d, r8d; Reserved
0x180085e92  mov     qword ptr [rsp+0C0h+dwOptions], rax; lpData
0x180085e97  call    cs:__imp_RegSetValueExA
0x180085e9d  mov     rcx, [rbp+4Fh+var_70]; hKey
0x180085ea1  mov     ebx, eax
0x180085ea3  call    cs:__imp_RegCloseKey
0x180085ea9  mov     rcx, [rbp+4Fh+hKey]; hKey
0x180085ead  call    cs:__imp_RegCloseKey
0x180085eb3  test    ebx, ebx
0x180085eb5  jnz     short loc_180085EBE
0x180085eb7  mov     ebx, r14d
0x180085eba  jmp     short loc_180085EC9
0x180085ebc  test    ebx, ebx
0x180085ebe  jle     short loc_180085EC9
0x180085ec0  movzx   ebx, bx
0x180085ec3  or      ebx, 80070000h
0x180085ec9  mov     eax, ebx
0x180085ecb  mov     rcx, [rbp+4Fh+var_30]
0x180085ecf  xor     rcx, rsp; StackCookie
0x180085ed2  call    __security_check_cookie
0x180085ed7  add     rsp, 0A0h
0x180085ede  pop     r14
0x180085ee0  pop     rdi
0x180085ee1  pop     rsi
0x180085ee2  pop     rbx
0x180085ee3  pop     rbp
0x180085ee4  retn
```
