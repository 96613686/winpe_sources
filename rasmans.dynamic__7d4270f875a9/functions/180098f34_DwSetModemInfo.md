# DwSetModemInfo

- ea: `0x180098f34`
- end: `0x1800990d5`
- name: `DwSetModemInfo`
- size: `417`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18002c940`

## callees

- `0x180098070`
- `0x180098f34`
- `0x1800e8e96`
- `0x1800e8ef0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180098fab`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180098fab`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180099008`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180099008`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18009903e`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180099074`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18009903e`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180099074`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18009908f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800990a5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18009908f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800990a5`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180098f9b`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180098f9b`

## pseudocode

```c
__int64 __fastcall DwSetModemInfo(__int64 a1)
{
  unsigned int *v2; // r8
  DWORD LastError; // ebx
  HKEY hKey; // [rsp+30h] [rbp-138h] BYREF
  HKEY phkResult; // [rsp+38h] [rbp-130h] BYREF
  WCHAR WideCharStr[136]; // [rsp+40h] [rbp-128h] BYREF

  hKey = 0;
  memset_0(WideCharStr, 0, 0x102u);
  phkResult = 0;
  if ( !MultiByteToWideChar(0, 0, (LPCCH)(a1 + 133), -1, WideCharStr, 129) )
  {
    LastError = GetLastError();
    goto LABEL_10;
  }
  LastError = lrGetRegKeyFromGuid((unsigned __int8 *)WideCharStr, &hKey, v2, 1);
  if ( !LastError )
  {
    if ( !hKey )
      goto LABEL_10;
    LastError = RegOpenKeyExW(hKey, L"Clients\\Ras", 0, 0xF003Fu, &phkResult);
    if ( !LastError )
    {
      LastError = RegSetValueExW(phkResult, L"EnableForRas", 0, 4u, (const BYTE *)(a1 + 56), 4u);
      if ( !LastError )
        LastError = RegSetValueExW(phkResult, L"EnableforRouting", 0, 4u, (const BYTE *)(a1 + 60), 4u);
    }
  }
  if ( hKey )
    RegCloseKey(hKey);
LABEL_10:
  if ( phkResult )
    RegCloseKey(phkResult);
  return LastError;
}

```

## disassembly

```asm
0x180098f34  mov     [rsp+arg_8], rbx
0x180098f39  push    rsi
0x180098f3a  sub     rsp, 160h
0x180098f41  mov     rax, cs:__security_cookie
0x180098f48  xor     rax, rsp
0x180098f4b  mov     [rsp+168h+var_18], rax
0x180098f53  mov     rsi, rcx
0x180098f56  mov     [rsp+168h+hKey], 0
0x180098f5f  lea     rcx, [rsp+168h+WideCharStr]; void *
0x180098f64  xor     edx, edx; Val
0x180098f66  mov     r8d, 102h; Size
0x180098f6c  call    memset_0
0x180098f71  lea     rax, [rsp+168h+WideCharStr]
0x180098f76  mov     [rsp+168h+cchWideChar], 81h; cchWideChar
0x180098f7e  lea     r8, [rsi+85h]; lpMultiByteStr
0x180098f85  mov     [rsp+168h+lpWideCharStr], rax; lpWideCharStr
0x180098f8a  or      r9d, 0FFFFFFFFh; cbMultiByte
0x180098f8e  mov     [rsp+168h+phkResult], 0
0x180098f97  xor     edx, edx; dwFlags
0x180098f99  xor     ecx, ecx; CodePage
0x180098f9b  call    cs:__imp_MultiByteToWideChar
0x180098fa2  nop     dword ptr [rax+rax+00h]
0x180098fa7  test    eax, eax
0x180098fa9  jnz     short loc_180098FBE
0x180098fab  call    cs:__imp_GetLastError
0x180098fb2  nop     dword ptr [rax+rax+00h]
0x180098fb7  mov     ebx, eax
0x180098fb9  jmp     loc_18009909B
0x180098fbe  mov     r9d, 1; int
0x180098fc4  lea     rdx, [rsp+168h+hKey]; HKEY *
0x180098fc9  lea     rcx, [rsp+168h+WideCharStr]; unsigned __int8 *
0x180098fce  call    ?lrGetRegKeyFromGuid@@YAJPEAEPEAPEAUHKEY__@@PEAKH@Z; lrGetRegKeyFromGuid(uchar *,HKEY__ * *,ulong *,int)
0x180098fd3  mov     ebx, eax
0x180098fd5  test    eax, eax
0x180098fd7  jnz     loc_180099082
0x180098fdd  cmp     [rsp+168h+hKey], 0
0x180098fe3  jz      loc_18009909B
0x180098fe9  mov     rcx, [rsp+168h+hKey]; hKey
0x180098fee  lea     rax, [rsp+168h+phkResult]
0x180098ff3  mov     r9d, 0F003Fh; samDesired
0x180098ff9  mov     [rsp+168h+lpWideCharStr], rax; phkResult
0x180098ffe  xor     r8d, r8d; ulOptions
0x180099001  lea     rdx, aClientsRas; "Clients\\Ras"
0x180099008  call    cs:__imp_RegOpenKeyExW
0x18009900f  nop     dword ptr [rax+rax+00h]
0x180099014  mov     ebx, eax
0x180099016  test    eax, eax
0x180099018  jnz     short loc_180099082
0x18009901a  mov     rcx, [rsp+168h+phkResult]; hKey
0x18009901f  lea     rax, [rsi+38h]
0x180099023  mov     [rsp+168h+cchWideChar], 4; cbData
0x18009902b  lea     r9d, [rbx+4]; dwType
0x18009902f  xor     r8d, r8d; Reserved
0x180099032  mov     [rsp+168h+lpWideCharStr], rax; lpData
0x180099037  lea     rdx, aEnableforras; "EnableForRas"
0x18009903e  call    cs:__imp_RegSetValueExW
0x180099045  nop     dword ptr [rax+rax+00h]
0x18009904a  mov     ebx, eax
0x18009904c  test    eax, eax
0x18009904e  jnz     short loc_180099082
0x180099050  mov     rcx, [rsp+168h+phkResult]; hKey
0x180099055  lea     rax, [rsi+3Ch]
0x180099059  mov     [rsp+168h+cchWideChar], 4; cbData
0x180099061  lea     r9d, [rbx+4]; dwType
0x180099065  xor     r8d, r8d; Reserved
0x180099068  mov     [rsp+168h+lpWideCharStr], rax; lpData
0x18009906d  lea     rdx, aEnableforrouti_0; "EnableforRouting"
0x180099074  call    cs:__imp_RegSetValueExW
0x18009907b  nop     dword ptr [rax+rax+00h]
0x180099080  mov     ebx, eax
0x180099082  cmp     [rsp+168h+hKey], 0
0x180099088  jz      short loc_18009909B
0x18009908a  mov     rcx, [rsp+168h+hKey]; hKey
0x18009908f  call    cs:__imp_RegCloseKey
0x180099096  nop     dword ptr [rax+rax+00h]
0x18009909b  mov     rcx, [rsp+168h+phkResult]; hKey
0x1800990a0  test    rcx, rcx
0x1800990a3  jz      short loc_1800990B1
0x1800990a5  call    cs:__imp_RegCloseKey
0x1800990ac  nop     dword ptr [rax+rax+00h]
0x1800990b1  mov     eax, ebx
0x1800990b3  mov     rcx, [rsp+168h+var_18]
0x1800990bb  xor     rcx, rsp; StackCookie
0x1800990be  call    __security_check_cookie
0x1800990c3  mov     rbx, [rsp+168h+arg_8]
0x1800990cb  add     rsp, 160h
0x1800990d2  pop     rsi
0x1800990d3  retn
```
