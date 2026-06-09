# DisableAutoWPPTracingForSubComponent

- ea: `0x1800a4874`
- end: `0x1800a49e6`
- name: `DisableAutoWPPTracingForSubComponent`
- size: `370`
- prototype: `LSTATUS __fastcall(int)`
- caller_count: `3`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18002040c`
- `0x1800d4f20`
- `0x1800df9c0`

## callees

- `0x18000e564`
- `0x1800a4874`
- `0x1800a5b38`
- `0x1800e7206`
- `0x1800e7260`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800a4963`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800a4963`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800a4927`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800a4927`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800a49ba`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800a49ba`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800a49ad`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800a49ad`

## string_xrefs

- `0x1800a48db`: `SOFTWARE\Microsoft\Windows NT\CurrentVersion\Tracing\Microsoft\RemoteAccess\`

## pseudocode

```c
LSTATUS __fastcall DisableAutoWPPTracingForSubComponent(int a1)
{
  __int64 v1; // rdi
  LSTATUS result; // eax
  LSTATUS v3; // eax
  LSTATUS v4; // ebx
  BYTE Data[4]; // [rsp+30h] [rbp-D0h] BYREF
  DWORD cbData; // [rsp+34h] [rbp-CCh] BYREF
  HKEY hKey; // [rsp+38h] [rbp-C8h] BYREF
  WCHAR SubKey[2]; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v9[524]; // [rsp+44h] [rbp-BCh] BYREF

  v1 = a1;
  hKey = 0;
  *(_DWORD *)SubKey = 0;
  memset_0(v9, 0, 0x206u);
  *(_DWORD *)Data = 0;
  cbData = 4;
  StringCchPrintfW(
    SubKey,
    0x105u,
    L"%s%s",
    L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\Tracing\\Microsoft\\RemoteAccess\\",
    &WPP_COMPONENT_INFO[274 * v1]);
  result = RegOpenKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 0x2011Fu, &hKey);
  if ( !result )
  {
    cbData = 4;
    v3 = RegQueryValueExW(hKey, L"AutoActive", 0, 0, Data, &cbData);
    v4 = v3;
    if ( v3 != 2 )
    {
      if ( v3 )
      {
LABEL_7:
        RegCloseKey(hKey);
        return v4;
      }
      if ( *(_DWORD *)Data == 1 )
      {
        TraceEnableDisableWPPComponent(0, v1);
        *(_DWORD *)Data = v4;
        RegSetValueExW(hKey, L"AutoActive", 0, v4 + 4, Data, 4u);
      }
    }
    v4 = 0;
    goto LABEL_7;
  }
  return result;
}

```

## disassembly

```asm
0x1800a4874  mov     [rsp-8+arg_8], rbx
0x1800a4879  mov     [rsp-8+arg_10], rdi
0x1800a487e  push    rbp
0x1800a487f  lea     rbp, [rsp-160h]
0x1800a4887  sub     rsp, 260h
0x1800a488e  mov     rax, cs:__security_cookie
0x1800a4895  xor     rax, rsp
0x1800a4898  mov     [rbp+160h+var_10], rax
0x1800a489f  movsxd  rdi, ecx
0x1800a48a2  xor     edx, edx; Val
0x1800a48a4  lea     rcx, [rsp+260h+var_21C]; void *
0x1800a48a9  mov     [rsp+260h+hKey], 0
0x1800a48b2  mov     r8d, 206h; Size
0x1800a48b8  mov     dword ptr [rsp+260h+SubKey], 0
0x1800a48c0  call    memset_0
0x1800a48c5  lea     rax, WPP_COMPONENT_INFO; "RASMAN"
0x1800a48cc  mov     dword ptr [rsp+260h+Data], 0
0x1800a48d4  imul    rcx, rdi, 224h
0x1800a48db  lea     r9, aSoftwareMicros_6; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x1800a48e2  mov     [rsp+260h+cbData], 4
0x1800a48ea  add     rcx, rax
0x1800a48ed  lea     r8, aSS_0; "%s%s"
0x1800a48f4  mov     [rsp+260h+phkResult], rcx
0x1800a48f9  mov     edx, 105h; unsigned __int64
0x1800a48fe  lea     rcx, [rsp+260h+SubKey]; unsigned __int16 *
0x1800a4903  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800a4908  lea     rax, [rsp+260h+hKey]
0x1800a490d  mov     r9d, 2011Fh; samDesired
0x1800a4913  xor     r8d, r8d; ulOptions
0x1800a4916  mov     [rsp+260h+phkResult], rax; phkResult
0x1800a491b  lea     rdx, [rsp+260h+SubKey]; lpSubKey
0x1800a4920  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800a4927  call    cs:__imp_RegOpenKeyExW
0x1800a492d  test    eax, eax
0x1800a492f  jnz     loc_1800A49C2
0x1800a4935  mov     rcx, [rsp+260h+hKey]; hKey
0x1800a493a  lea     rax, [rsp+260h+cbData]
0x1800a493f  mov     [rsp+260h+lpcbData], rax; lpcbData
0x1800a4944  lea     rdx, aAutoactive; "AutoActive"
0x1800a494b  lea     rax, [rsp+260h+Data]
0x1800a4950  mov     [rsp+260h+cbData], 4
0x1800a4958  xor     r9d, r9d; lpType
0x1800a495b  mov     [rsp+260h+phkResult], rax; lpData
0x1800a4960  xor     r8d, r8d; lpReserved
0x1800a4963  call    cs:__imp_RegQueryValueExW
0x1800a4969  mov     ebx, eax
0x1800a496b  cmp     eax, 2
0x1800a496e  jz      short loc_1800A49B3
0x1800a4970  test    eax, eax
0x1800a4972  jnz     short loc_1800A49B5
0x1800a4974  cmp     dword ptr [rsp+260h+Data], 1
0x1800a4979  jnz     short loc_1800A49B3
0x1800a497b  mov     edx, edi
0x1800a497d  xor     ecx, ecx
0x1800a497f  call    TraceEnableDisableWPPComponent
0x1800a4984  mov     rcx, [rsp+260h+hKey]; hKey
0x1800a4989  lea     rax, [rsp+260h+Data]
0x1800a498e  mov     dword ptr [rsp+260h+lpcbData], 4; cbData
0x1800a4996  lea     r9d, [rbx+4]; dwType
0x1800a499a  xor     r8d, r8d; Reserved
0x1800a499d  mov     [rsp+260h+phkResult], rax; lpData
0x1800a49a2  lea     rdx, aAutoactive; "AutoActive"
0x1800a49a9  mov     dword ptr [rsp+260h+Data], ebx
0x1800a49ad  call    cs:__imp_RegSetValueExW
0x1800a49b3  xor     ebx, ebx
0x1800a49b5  mov     rcx, [rsp+260h+hKey]; hKey
0x1800a49ba  call    cs:__imp_RegCloseKey
0x1800a49c0  mov     eax, ebx
0x1800a49c2  mov     rcx, [rbp+160h+var_10]
0x1800a49c9  xor     rcx, rsp; StackCookie
0x1800a49cc  call    __security_check_cookie
0x1800a49d1  lea     r11, [rsp+260h+var_s0]
0x1800a49d9  mov     rbx, [r11+18h]
0x1800a49dd  mov     rdi, [r11+20h]
0x1800a49e1  mov     rsp, r11
0x1800a49e4  pop     rbp
0x1800a49e5  retn
```
