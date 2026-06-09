# RassrvRegGetStr

- ea: `0x180033e0c`
- end: `0x180033efa`
- name: `RassrvRegGetStr`
- size: `238`
- prototype: `__int64 __usercall@<rax>(STRSAFE_LPWSTR pszDest@<rcx>, LPCWSTR lpValueName)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x1800367b4`
- `0x180036be0`

## callees

- `0x18001e944`
- `0x180033e0c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180033e56`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180033e56`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180033ee2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180033ee2`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180033e83`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180033e83`
- `rtutils!TracePrintfExA` at `0x180033ecf`
- `rtutils!TracePrintfExA` at `0x180033ecf`

## string_xrefs

- `0x180033ec5`: `RassrvRegGetStr: StringCchCopyExW failed. hr = 0x%x`

## pseudocode

```c
__int64 __fastcall RassrvRegGetStr(BYTE *pszDest, __int64 a2, const wchar_t *a3, const WCHAR *a4, LPCWSTR lpValueName)
{
  unsigned int v7; // ebx
  HRESULT v8; // eax
  unsigned __int16 v9; // di
  DWORD Type; // [rsp+30h] [rbp-18h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-10h] BYREF
  DWORD cbData; // [rsp+58h] [rbp+10h] BYREF

  Type = 1;
  cbData = 257;
  hKey = 0;
  v7 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, a4, 0, 0x20019u, &hKey);
  if ( !v7 )
  {
    v7 = RegQueryValueExW(hKey, lpValueName, 0, &Type, pszDest, &cbData);
    if ( v7 )
    {
      v7 = 0;
      v8 = StringCchCopyExW((STRSAFE_LPWSTR)pszDest, 0x101u, a3, 0, 0, 0x900u);
      v9 = v8;
      if ( v8 < 0 )
      {
        if ( g_dwTraceId != -1 )
          TracePrintfExA(g_dwTraceId, 0xCu, "RassrvRegGetStr: StringCchCopyExW failed. hr = 0x%x", v8);
        v7 = v9;
      }
    }
  }
  if ( hKey )
    RegCloseKey(hKey);
  return v7;
}

```

## disassembly

```asm
0x180033e0c  mov     rax, rsp
0x180033e0f  mov     [rax+8], rbx
0x180033e13  mov     [rax+18h], rsi
0x180033e17  mov     [rax+10h], edx
0x180033e1a  push    rdi
0x180033e1b  sub     rsp, 40h
0x180033e1f  mov     rdi, rcx
0x180033e22  mov     dword ptr [rax-18h], 1
0x180033e29  lea     rcx, [rax-10h]
0x180033e2d  mov     dword ptr [rax+10h], 101h
0x180033e34  mov     [rax-28h], rcx
0x180033e38  mov     rdx, r9; lpSubKey
0x180033e3b  mov     rsi, r8
0x180033e3e  mov     qword ptr [rax-10h], 0
0x180033e46  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180033e4d  mov     r9d, 20019h; samDesired
0x180033e53  xor     r8d, r8d; ulOptions
0x180033e56  call    cs:__imp_RegOpenKeyExW
0x180033e5c  mov     ebx, eax
0x180033e5e  test    eax, eax
0x180033e60  jnz     short loc_180033ED8
0x180033e62  mov     rdx, [rsp+48h+lpValueName]; lpValueName
0x180033e67  lea     rax, [rsp+48h+cbData]
0x180033e6c  mov     rcx, [rsp+48h+hKey]; hKey
0x180033e71  lea     r9, [rsp+48h+Type]; lpType
0x180033e76  mov     [rsp+48h+lpcbData], rax; lpcbData
0x180033e7b  xor     r8d, r8d; lpReserved
0x180033e7e  mov     [rsp+48h+lpData], rdi; lpData
0x180033e83  call    cs:__imp_RegQueryValueExW
0x180033e89  mov     ebx, eax
0x180033e8b  test    eax, eax
0x180033e8d  jz      short loc_180033ED8
0x180033e8f  xor     ebx, ebx
0x180033e91  mov     dword ptr [rsp+48h+lpcbData], 900h; dwFlags
0x180033e99  xor     r9d, r9d; ppszDestEnd
0x180033e9c  mov     [rsp+48h+lpData], rbx; pcchRemaining
0x180033ea1  mov     r8, rsi; pszSrc
0x180033ea4  mov     edx, 101h; cchDest
0x180033ea9  mov     rcx, rdi; pszDest
0x180033eac  call    StringCchCopyExW
0x180033eb1  mov     edi, eax
0x180033eb3  test    eax, eax
0x180033eb5  jns     short loc_180033ED8
0x180033eb7  mov     ecx, cs:g_dwTraceId; dwTraceID
0x180033ebd  cmp     ecx, 0FFFFFFFFh
0x180033ec0  jz      short loc_180033ED5
0x180033ec2  mov     r9d, eax
0x180033ec5  lea     r8, aRassrvreggetst; "RassrvRegGetStr: StringCchCopyExW faile"...
0x180033ecc  lea     edx, [rbx+0Ch]; dwFlags
0x180033ecf  call    cs:__imp_TracePrintfExA
0x180033ed5  movzx   ebx, di
0x180033ed8  mov     rcx, [rsp+48h+hKey]; hKey
0x180033edd  test    rcx, rcx
0x180033ee0  jz      short loc_180033EE8
0x180033ee2  call    cs:__imp_RegCloseKey
0x180033ee8  mov     rsi, [rsp+48h+arg_10]
0x180033eed  mov     eax, ebx
0x180033eef  mov     rbx, [rsp+48h+arg_0]
0x180033ef4  add     rsp, 40h
0x180033ef8  pop     rdi
0x180033ef9  retn
```
