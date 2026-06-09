# DisableAutoWPPTracingForSubComponent

- ea: `0x1800aa594`
- end: `0x1800aa71f`
- name: `DisableAutoWPPTracingForSubComponent`
- size: `395`
- prototype: ``
- caller_count: `3`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800210e0`
- `0x1800d9a60`
- `0x1800e1f2c`

## callees

- `0x18000eb54`
- `0x1800aa594`
- `0x1800aba58`
- `0x1800e8e96`
- `0x1800e8ef0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800aa647`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800aa647`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800aa6d9`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800aa6d9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800aa6ec`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800aa6ec`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800aa689`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800aa689`

## string_xrefs

- `0x1800aa5fb`: `SOFTWARE\Microsoft\Windows NT\CurrentVersion\Tracing\Microsoft\RemoteAccess\`

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
        TraceEnableDisableWPPComponent(0, (unsigned int)v1);
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
0x1800aa594  mov     [rsp-8+arg_8], rbx
0x1800aa599  mov     [rsp-8+arg_10], rdi
0x1800aa59e  push    rbp
0x1800aa59f  lea     rbp, [rsp-160h]
0x1800aa5a7  sub     rsp, 260h
0x1800aa5ae  mov     rax, cs:__security_cookie
0x1800aa5b5  xor     rax, rsp
0x1800aa5b8  mov     [rbp+160h+var_10], rax
0x1800aa5bf  movsxd  rdi, ecx
0x1800aa5c2  xor     edx, edx; Val
0x1800aa5c4  lea     rcx, [rsp+260h+var_21C]; void *
0x1800aa5c9  mov     [rsp+260h+hKey], 0
0x1800aa5d2  mov     r8d, 206h; Size
0x1800aa5d8  mov     dword ptr [rsp+260h+SubKey], 0
0x1800aa5e0  call    memset_0
0x1800aa5e5  lea     rax, WPP_COMPONENT_INFO; "RASMAN"
0x1800aa5ec  mov     dword ptr [rsp+260h+Data], 0
0x1800aa5f4  imul    rcx, rdi, 224h
0x1800aa5fb  lea     r9, aSoftwareMicros_6; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x1800aa602  mov     [rsp+260h+cbData], 4
0x1800aa60a  add     rcx, rax
0x1800aa60d  lea     r8, aSS_3; "%s%s"
0x1800aa614  mov     [rsp+260h+phkResult], rcx
0x1800aa619  mov     edx, 105h; unsigned __int64
0x1800aa61e  lea     rcx, [rsp+260h+SubKey]; unsigned __int16 *
0x1800aa623  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800aa628  lea     rax, [rsp+260h+hKey]
0x1800aa62d  mov     r9d, 2011Fh; samDesired
0x1800aa633  xor     r8d, r8d; ulOptions
0x1800aa636  mov     [rsp+260h+phkResult], rax; phkResult
0x1800aa63b  lea     rdx, [rsp+260h+SubKey]; lpSubKey
0x1800aa640  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800aa647  call    cs:__imp_RegOpenKeyExW
0x1800aa64e  nop     dword ptr [rax+rax+00h]
0x1800aa653  test    eax, eax
0x1800aa655  jnz     loc_1800AA6FA
0x1800aa65b  mov     rcx, [rsp+260h+hKey]; hKey
0x1800aa660  lea     rax, [rsp+260h+cbData]
0x1800aa665  mov     [rsp+260h+lpcbData], rax; lpcbData
0x1800aa66a  lea     rdx, aAutoactive; "AutoActive"
0x1800aa671  lea     rax, [rsp+260h+Data]
0x1800aa676  mov     [rsp+260h+cbData], 4
0x1800aa67e  xor     r9d, r9d; lpType
0x1800aa681  mov     [rsp+260h+phkResult], rax; lpData
0x1800aa686  xor     r8d, r8d; lpReserved
0x1800aa689  call    cs:__imp_RegQueryValueExW
0x1800aa690  nop     dword ptr [rax+rax+00h]
0x1800aa695  mov     ebx, eax
0x1800aa697  cmp     eax, 2
0x1800aa69a  jz      short loc_1800AA6E5
0x1800aa69c  test    eax, eax
0x1800aa69e  jnz     short loc_1800AA6E7
0x1800aa6a0  cmp     dword ptr [rsp+260h+Data], 1
0x1800aa6a5  jnz     short loc_1800AA6E5
0x1800aa6a7  mov     edx, edi
0x1800aa6a9  xor     ecx, ecx
0x1800aa6ab  call    TraceEnableDisableWPPComponent
0x1800aa6b0  mov     rcx, [rsp+260h+hKey]; hKey
0x1800aa6b5  lea     rax, [rsp+260h+Data]
0x1800aa6ba  mov     dword ptr [rsp+260h+lpcbData], 4; cbData
0x1800aa6c2  lea     r9d, [rbx+4]; dwType
0x1800aa6c6  xor     r8d, r8d; Reserved
0x1800aa6c9  mov     [rsp+260h+phkResult], rax; lpData
0x1800aa6ce  lea     rdx, aAutoactive; "AutoActive"
0x1800aa6d5  mov     dword ptr [rsp+260h+Data], ebx
0x1800aa6d9  call    cs:__imp_RegSetValueExW
0x1800aa6e0  nop     dword ptr [rax+rax+00h]
0x1800aa6e5  xor     ebx, ebx
0x1800aa6e7  mov     rcx, [rsp+260h+hKey]; hKey
0x1800aa6ec  call    cs:__imp_RegCloseKey
0x1800aa6f3  nop     dword ptr [rax+rax+00h]
0x1800aa6f8  mov     eax, ebx
0x1800aa6fa  mov     rcx, [rbp+160h+var_10]
0x1800aa701  xor     rcx, rsp; StackCookie
0x1800aa704  call    __security_check_cookie
0x1800aa709  lea     r11, [rsp+260h+var_s0]
0x1800aa711  mov     rbx, [r11+18h]
0x1800aa715  mov     rdi, [r11+20h]
0x1800aa719  mov     rsp, r11
0x1800aa71c  pop     rbp
0x1800aa71d  retn
```
