# areg_SetAdapterFlag

- ea: `0x180034574`
- end: `0x180034667`
- name: `areg_SetAdapterFlag`
- size: `243`
- prototype: `__int64 __fastcall(LPCWSTR lpSubKey, LPCWSTR lpValueName)`
- caller_count: `3`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x1800344dc`
- `0x180034528`
- `0x180036530`

## callees

- `0x180034574`
- `0x180046ec0`
- `0x180085e68`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180034649`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180034649`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18003463e`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18003463e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800345e8`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800345e8`

## pseudocode

```c
LSTATUS __fastcall areg_SetAdapterFlag(LPCWSTR lpSubKey, LPCWSTR lpValueName, int a3)
{
  LSTATUS result; // eax
  HKEY hKey; // [rsp+30h] [rbp-28h] BYREF
  BYTE Data[8]; // [rsp+38h] [rbp-20h] BYREF

  *(_DWORD *)Data = a3;
  hKey = 0;
  if ( SBYTE2(xmmword_1800AB5A0) < 0 )
    WPP_SF_SSd(
      1047,
      90,
      (unsigned int)WPP_7d480ea9e959396e1e8188612fd17a9a_Traceguids,
      (_DWORD)lpSubKey,
      (__int64)lpValueName,
      a3);
  result = RegOpenKeyExW(g_hAregRegKey, lpSubKey, 0, 0x2001Fu, &hKey);
  if ( !result )
  {
    if ( SBYTE2(xmmword_1800AB5A0) < 0 )
      WPP_SF_SSd(
        1047,
        91,
        (unsigned int)WPP_7d480ea9e959396e1e8188612fd17a9a_Traceguids,
        (_DWORD)lpSubKey,
        (__int64)lpValueName,
        Data[0]);
    RegSetValueExW(hKey, lpValueName, 0, 4u, Data, 4u);
    return RegCloseKey(hKey);
  }
  return result;
}

```

## disassembly

```asm
0x180034574  mov     r11, rsp
0x180034577  mov     [r11+20h], rbx
0x18003457b  push    rdi
0x18003457c  sub     rsp, 50h
0x180034580  mov     rax, cs:__security_cookie
0x180034587  xor     rax, rsp
0x18003458a  mov     [rsp+58h+var_18], rax
0x18003458f  mov     [r11-20h], r8d
0x180034593  mov     rbx, rdx
0x180034596  mov     qword ptr [r11-28h], 0
0x18003459e  mov     rdi, rcx
0x1800345a1  cmp     byte ptr cs:xmmword_1800AB5A0+2, 0
0x1800345a8  jge     short loc_1800345CB
0x1800345aa  mov     [r11-30h], r8d
0x1800345ae  mov     edx, 5Ah ; 'Z'
0x1800345b3  lea     r8, WPP_7d480ea9e959396e1e8188612fd17a9a_Traceguids
0x1800345ba  mov     [r11-38h], rbx
0x1800345be  mov     ecx, 417h
0x1800345c3  mov     r9, rdi
0x1800345c6  call    WPP_SF_SSd
0x1800345cb  mov     rcx, cs:g_hAregRegKey; hKey
0x1800345d2  lea     rax, [rsp+58h+hKey]
0x1800345d7  mov     r9d, 2001Fh; samDesired
0x1800345dd  mov     [rsp+58h+phkResult], rax; phkResult
0x1800345e2  xor     r8d, r8d; ulOptions
0x1800345e5  mov     rdx, rdi; lpSubKey
0x1800345e8  call    cs:__imp_RegOpenKeyExW
0x1800345ee  test    eax, eax
0x1800345f0  jnz     short loc_18003464F
0x1800345f2  cmp     byte ptr cs:xmmword_1800AB5A0+2, al
0x1800345f8  jge     short loc_18003461E
0x1800345fa  lea     edx, [rax+5Bh]
0x1800345fd  mov     ecx, 417h
0x180034602  mov     eax, dword ptr [rsp+58h+Data]
0x180034606  lea     r8, WPP_7d480ea9e959396e1e8188612fd17a9a_Traceguids
0x18003460d  mov     [rsp+58h+cbData], eax
0x180034611  mov     r9, rdi
0x180034614  mov     [rsp+58h+phkResult], rbx
0x180034619  call    WPP_SF_SSd
0x18003461e  mov     rcx, [rsp+58h+hKey]; hKey
0x180034623  lea     rax, [rsp+58h+Data]
0x180034628  mov     r9d, 4; dwType
0x18003462e  xor     r8d, r8d; Reserved
0x180034631  mov     [rsp+58h+cbData], r9d; cbData
0x180034636  mov     rdx, rbx; lpValueName
0x180034639  mov     [rsp+58h+phkResult], rax; lpData
0x18003463e  call    cs:__imp_RegSetValueExW
0x180034644  mov     rcx, [rsp+58h+hKey]; hKey
0x180034649  call    cs:__imp_RegCloseKey
0x18003464f  mov     rcx, [rsp+58h+var_18]
0x180034654  xor     rcx, rsp; StackCookie
0x180034657  call    __security_check_cookie
0x18003465c  mov     rbx, [rsp+58h+arg_18]
0x180034661  add     rsp, 50h
0x180034665  pop     rdi
0x180034666  retn
```
