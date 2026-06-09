# RegReadDefValue(HKEY__ *,ushort const *,ushort * *)

- ea: `0x18009b984`
- end: `0x18009ba80`
- name: `?RegReadDefValue@@YAJPEAUHKEY__@@PEBGPEAPEAG@Z`
- size: `252`
- prototype: `int __fastcall(HKEY__ *hKey, const wchar_t *pszKey, wchar_t **ppszValue)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18009ab88`

## callees

- `0x18009b984`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18009b9b4`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18009b9b4`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18009b9e6`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18009ba31`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18009b9e6`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18009ba31`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18009ba5e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18009ba5e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18009b9fc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18009b9fc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18009ba46`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18009ba46`

## pseudocode

```c
__int64 __fastcall RegReadDefValue(HKEY hKey, const wchar_t *pszKey, wchar_t **ppszValue)
{
  unsigned __int8 *v4; // rbx
  unsigned int v5; // edi
  unsigned int dw; // [rsp+50h] [rbp+18h] BYREF
  HKEY__ *hSubKey; // [rsp+58h] [rbp+20h] BYREF

  hSubKey = 0;
  dw = 0;
  v4 = 0;
  v5 = RegOpenKeyExW(hKey, pszKey, 0, 0x20019u, &hSubKey);
  if ( !v5 )
  {
    v5 = RegQueryValueExW(hSubKey, 0, 0, 0, 0, &dw);
    if ( !v5 )
    {
      v4 = (unsigned __int8 *)CoTaskMemAlloc(dw);
      if ( v4 )
      {
        v5 = RegQueryValueExW(hSubKey, 0, 0, 0, v4, &dw);
        if ( v5 )
        {
          CoTaskMemFree(v4);
          v4 = 0;
        }
      }
      else
      {
        v5 = 14;
      }
    }
  }
  if ( hSubKey )
    RegCloseKey(hSubKey);
  *ppszValue = (wchar_t *)v4;
  return v5;
}

```

## disassembly

```asm
0x18009b984  mov     rax, rsp
0x18009b987  mov     [rax+8], rbx
0x18009b98b  mov     [rax+10h], rsi
0x18009b98f  push    rdi
0x18009b990  sub     rsp, 30h
0x18009b994  and     qword ptr [rax+20h], 0
0x18009b999  mov     rsi, ppszValue
0x18009b99c  and     dword ptr [rax+18h], 0
0x18009b9a0  lea     rax, [rax+20h]
0x18009b9a4  mov     r9d, 20019h; samDesired
0x18009b9aa  mov     [rsp+38h+phkResult], rax; lpData
0x18009b9af  xor     r8d, r8d; ulOptions
0x18009b9b2  xor     ebx, ebx
0x18009b9b4  call    cs:__imp_RegOpenKeyExW
0x18009b9bb  nop     dword ptr [rax+rax+00h]
0x18009b9c0  mov     edi, eax
0x18009b9c2  test    eax, eax
0x18009b9c4  jnz     loc_18009BA54
0x18009b9ca  mov     hKey, [rsp+38h+hSubKey]; hKey
0x18009b9cf  lea     rax, [rsp+38h+dw]
0x18009b9d4  mov     [rsp+38h+lpcbData], rax; lpcbData
0x18009b9d9  xor     r9d, r9d; lpType
0x18009b9dc  and     [rsp+38h+phkResult], rbx
0x18009b9e1  xor     r8d, r8d; lpReserved
0x18009b9e4  xor     edx, edx; lpValueName
0x18009b9e6  call    cs:__imp_RegQueryValueExW
0x18009b9ed  nop     dword ptr [rax+rax+00h]
0x18009b9f2  mov     edi, eax
0x18009b9f4  test    eax, eax
0x18009b9f6  jnz     short loc_18009BA54
0x18009b9f8  mov     ecx, [rsp+38h+dw]; cb
0x18009b9fc  call    cs:__imp_CoTaskMemAlloc
0x18009ba03  nop     dword ptr [rax+rax+00h]
0x18009ba08  mov     rbx, rax
0x18009ba0b  test    rax, rax
0x18009ba0e  jnz     short loc_18009BA15
0x18009ba10  lea     edi, [rax+0Eh]
0x18009ba13  jmp     short loc_18009BA54
0x18009ba15  mov     hKey, [rsp+38h+hSubKey]; hKey
0x18009ba1a  lea     rax, [rsp+38h+dw]
0x18009ba1f  mov     [rsp+38h+lpcbData], rax; lpcbData
0x18009ba24  xor     r9d, r9d; lpType
0x18009ba27  xor     r8d, r8d; lpReserved
0x18009ba2a  mov     [rsp+38h+phkResult], rbx; lpData
0x18009ba2f  xor     edx, edx; lpValueName
0x18009ba31  call    cs:__imp_RegQueryValueExW
0x18009ba38  nop     dword ptr [rax+rax+00h]
0x18009ba3d  mov     edi, eax
0x18009ba3f  test    eax, eax
0x18009ba41  jz      short loc_18009BA54
0x18009ba43  mov     hKey, rbx; pv
0x18009ba46  call    cs:__imp_CoTaskMemFree
0x18009ba4d  nop     dword ptr [rax+rax+00h]
0x18009ba52  xor     ebx, ebx
0x18009ba54  mov     hKey, [rsp+38h+hSubKey]; hKey
0x18009ba59  test    hKey, hKey
0x18009ba5c  jz      short loc_18009BA6A
0x18009ba5e  call    cs:__imp_RegCloseKey
0x18009ba65  nop     dword ptr [rax+rax+00h]
0x18009ba6a  mov     [rsi], rbx
0x18009ba6d  mov     eax, edi
0x18009ba6f  mov     rbx, [rsp+38h+arg_0]
0x18009ba74  mov     rsi, [rsp+38h+arg_8]
0x18009ba79  add     rsp, 30h
0x18009ba7d  pop     rdi
0x18009ba7e  retn
```
