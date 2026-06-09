# CFveApi::StoreEncryptedRegKeyData(_GUID const *,_CRYPTOAPI_BLOB *,_CRYPTOAPI_BLOB *)

- ea: `0x1800d0520`
- end: `0x1800d0745`
- name: `?StoreEncryptedRegKeyData@CFveApi@@QEAAJPEBU_GUID@@PEAU_CRYPTOAPI_BLOB@@1@Z`
- size: `549`
- prototype: `int(CFveApi *__hidden this, const struct _GUID *, struct _CRYPTOAPI_BLOB *, struct _CRYPTOAPI_BLOB *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800cf31c`

## callees

- `0x180008d70`
- `0x1800090c0`
- `0x1800d0520`
- `0x18011f010`

## import_xrefs

- `ntdll!RtlFreeUnicodeString` at `0x1800d06f0`
- `ntdll!RtlFreeUnicodeString` at `0x1801284d8`
- `ntdll!RtlFreeUnicodeString` at `0x1800d06f0`
- `ntdll!RtlFreeUnicodeString` at `0x1801284d8`
- `ntdll!RtlStringFromGUID` at `0x1800d0590`
- `ntdll!RtlStringFromGUID` at `0x1800d0590`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800d05ec`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800d0638`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800d05ec`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800d0638`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800d066f`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800d06a0`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800d066f`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800d06a0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800d06c9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800d06df`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1801284b1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1801284c7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800d06c9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800d06df`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1801284b1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1801284c7`

## pseudocode

```c
__int64 __fastcall CFveApi::StoreEncryptedRegKeyData(
        CFveApi *this,
        const struct _GUID *a2,
        struct _CRYPTOAPI_BLOB *a3,
        struct _CRYPTOAPI_BLOB *a4)
{
  unsigned int v7; // ebx
  NTSTATUS v8; // eax
  LSTATUS v9; // eax
  bool v10; // cc
  HKEY phkResult; // [rsp+50h] [rbp-58h] BYREF
  HKEY hKey; // [rsp+58h] [rbp-50h] BYREF
  struct _UNICODE_STRING GuidString; // [rsp+60h] [rbp-48h] BYREF

  GuidString = 0;
  v7 = 0;
  hKey = 0;
  phkResult = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, WPP_82fbf6316f983a090a97009b222379cf_Traceguids);
  v8 = RtlStringFromGUID(a2, &GuidString);
  if ( v8 >= 0 )
  {
    v9 = RegCreateKeyExW(
           HKEY_CURRENT_USER,
           L"Software\\Microsoft\\Windows\\CurrentVersion\\FveAutoUnlock",
           0,
           0,
           0,
           0x2000000u,
           0,
           &hKey,
           0);
    v10 = v9 <= 0;
    if ( v9
      || (v9 = RegCreateKeyExW(hKey, GuidString.Buffer, 0, 0, 0, 0x2000000u, 0, &phkResult, 0), v10 = v9 <= 0, v9)
      || (v9 = RegSetValueExW(phkResult, L"element", 0, 3u, a3->pbData, a3->cbData), v10 = v9 <= 0, v9)
      || (v9 = RegSetValueExW(phkResult, L"info", 0, 3u, a4->pbData, a4->cbData), v10 = v9 <= 0, v9) )
    {
      if ( v10 )
        v7 = v9;
      else
        v7 = (unsigned __int16)v9 | 0x80070000;
    }
  }
  else
  {
    v7 = v8 | 0x10000000;
  }
  if ( phkResult )
    RegCloseKey(phkResult);
  if ( hKey )
    RegCloseKey(hKey);
  RtlFreeUnicodeString(&GuidString);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, WPP_82fbf6316f983a090a97009b222379cf_Traceguids, v7);
  return v7;
}

```

## disassembly

```asm
0x1800d0520  push    rbx
0x1800d0522  push    rsi
0x1800d0523  push    rdi
0x1800d0524  push    r12
0x1800d0526  push    r14
0x1800d0528  sub     rsp, 80h
0x1800d052f  mov     rax, cs:__security_cookie
0x1800d0536  xor     rax, rsp
0x1800d0539  mov     [rsp+0A8h+var_38], rax
0x1800d053e  mov     rsi, r9
0x1800d0541  mov     r14, r8
0x1800d0544  mov     rdi, rdx
0x1800d0547  xorps   xmm0, xmm0
0x1800d054a  movups  xmmword ptr [rsp+0A8h+GuidString.Length], xmm0
0x1800d054f  xor     ebx, ebx
0x1800d0551  mov     [rsp+0A8h+hKey], rbx
0x1800d0556  mov     [rsp+0A8h+var_58], rbx
0x1800d055b  lea     r12, WPP_GLOBAL_Control
0x1800d0562  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d0569  cmp     rcx, r12
0x1800d056c  jz      short loc_1800D0588
0x1800d056e  test    byte ptr [rcx+1Ch], 20h
0x1800d0572  jz      short loc_1800D0588
0x1800d0574  lea     edx, [rbx+12h]
0x1800d0577  lea     r8, WPP_82fbf6316f983a090a97009b222379cf_Traceguids
0x1800d057e  mov     rcx, [rcx+10h]
0x1800d0582  call    WPP_SF_
0x1800d0587  nop
0x1800d0588  lea     rdx, [rsp+0A8h+GuidString]; GuidString
0x1800d058d  mov     rcx, rdi; Guid
0x1800d0590  call    cs:__imp_RtlStringFromGUID
0x1800d0597  nop     dword ptr [rax+rax+00h]
0x1800d059c  test    eax, eax
0x1800d059e  jns     short loc_1800D05AB
0x1800d05a0  mov     ebx, eax
0x1800d05a2  bts     ebx, 1Ch
0x1800d05a6  jmp     loc_1800D06BF
0x1800d05ab  mov     [rsp+0A8h+lpdwDisposition], 0; lpdwDisposition
0x1800d05b4  lea     rax, [rsp+0A8h+hKey]
0x1800d05b9  mov     [rsp+0A8h+phkResult], rax; phkResult
0x1800d05be  mov     [rsp+0A8h+lpSecurityAttributes], 0; lpSecurityAttributes
0x1800d05c7  mov     edi, 2000000h
0x1800d05cc  mov     [rsp+0A8h+samDesired], edi; samDesired
0x1800d05d0  mov     [rsp+0A8h+dwOptions], 0; dwOptions
0x1800d05d8  xor     r9d, r9d; lpClass
0x1800d05db  xor     r8d, r8d; Reserved
0x1800d05de  lea     rdx, aSoftwareMicros_2; "Software\\Microsoft\\Windows\\CurrentVe"...
0x1800d05e5  mov     rcx, 0FFFFFFFF80000001h; hKey
0x1800d05ec  call    cs:__imp_RegCreateKeyExW
0x1800d05f3  nop     dword ptr [rax+rax+00h]
0x1800d05f8  test    eax, eax
0x1800d05fa  jnz     loc_1800D06B0
0x1800d0600  mov     [rsp+0A8h+lpdwDisposition], 0; lpdwDisposition
0x1800d0609  lea     rax, [rsp+0A8h+var_58]
0x1800d060e  mov     [rsp+0A8h+phkResult], rax; phkResult
0x1800d0613  mov     [rsp+0A8h+lpSecurityAttributes], 0; lpSecurityAttributes
0x1800d061c  mov     [rsp+0A8h+samDesired], edi; samDesired
0x1800d0620  mov     [rsp+0A8h+dwOptions], 0; dwOptions
0x1800d0628  xor     r9d, r9d; lpClass
0x1800d062b  xor     r8d, r8d; Reserved
0x1800d062e  mov     rdx, [rsp+0A8h+GuidString.Buffer]; lpSubKey
0x1800d0633  mov     rcx, [rsp+0A8h+hKey]; hKey
0x1800d0638  call    cs:__imp_RegCreateKeyExW
0x1800d063f  nop     dword ptr [rax+rax+00h]
0x1800d0644  test    eax, eax
0x1800d0646  jnz     short loc_1800D06B0
0x1800d0648  mov     eax, [r14]
0x1800d064b  mov     [rsp+0A8h+samDesired], eax; cbData
0x1800d064f  mov     rax, [r14+8]
0x1800d0653  mov     qword ptr [rsp+0A8h+dwOptions], rax; lpData
0x1800d0658  mov     edi, 3
0x1800d065d  mov     r9d, edi; dwType
0x1800d0660  xor     r8d, r8d; Reserved
0x1800d0663  lea     rdx, aElement; "element"
0x1800d066a  mov     rcx, [rsp+0A8h+var_58]; hKey
0x1800d066f  call    cs:__imp_RegSetValueExW
0x1800d0676  nop     dword ptr [rax+rax+00h]
0x1800d067b  test    eax, eax
0x1800d067d  jnz     short loc_1800D06B0
0x1800d067f  mov     eax, [rsi]
0x1800d0681  mov     [rsp+0A8h+samDesired], eax; cbData
0x1800d0685  mov     rax, [rsi+8]
0x1800d0689  mov     qword ptr [rsp+0A8h+dwOptions], rax; lpData
0x1800d068e  mov     r9d, edi; dwType
0x1800d0691  xor     r8d, r8d; Reserved
0x1800d0694  lea     rdx, aInfo; "info"
0x1800d069b  mov     rcx, [rsp+0A8h+var_58]; hKey
0x1800d06a0  call    cs:__imp_RegSetValueExW
0x1800d06a7  nop     dword ptr [rax+rax+00h]
0x1800d06ac  test    eax, eax
0x1800d06ae  jz      short loc_1800D06BF
0x1800d06b0  jg      short loc_1800D06B6
0x1800d06b2  mov     ebx, eax
0x1800d06b4  jmp     short loc_1800D06BF
0x1800d06b6  movzx   ebx, ax
0x1800d06b9  or      ebx, 80070000h
0x1800d06bf  mov     rcx, [rsp+0A8h+var_58]; hKey
0x1800d06c4  test    rcx, rcx
0x1800d06c7  jz      short loc_1800D06D5
0x1800d06c9  call    cs:__imp_RegCloseKey
0x1800d06d0  nop     dword ptr [rax+rax+00h]
0x1800d06d5  mov     rcx, [rsp+0A8h+hKey]; hKey
0x1800d06da  test    rcx, rcx
0x1800d06dd  jz      short loc_1800D06EB
0x1800d06df  call    cs:__imp_RegCloseKey
0x1800d06e6  nop     dword ptr [rax+rax+00h]
0x1800d06eb  lea     rcx, [rsp+0A8h+GuidString]; UnicodeString
0x1800d06f0  call    cs:__imp_RtlFreeUnicodeString
0x1800d06f7  nop     dword ptr [rax+rax+00h]
0x1800d06fc  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d0703  cmp     rcx, r12
0x1800d0706  jz      short loc_1800D0726
0x1800d0708  test    byte ptr [rcx+1Ch], 20h
0x1800d070c  jz      short loc_1800D0726
0x1800d070e  mov     edx, 13h
0x1800d0713  mov     r9d, ebx
0x1800d0716  lea     r8, WPP_82fbf6316f983a090a97009b222379cf_Traceguids
0x1800d071d  mov     rcx, [rcx+10h]
0x1800d0721  call    WPP_SF_d
0x1800d0726  mov     eax, ebx
0x1800d0728  mov     rcx, [rsp+0A8h+var_38]
0x1800d072d  xor     rcx, rsp; StackCookie
0x1800d0730  call    __security_check_cookie
0x1800d0735  add     rsp, 80h
0x1800d073c  pop     r14
0x1800d073e  pop     r12
0x1800d0740  pop     rdi
0x1800d0741  pop     rsi
0x1800d0742  pop     rbx
0x1800d0743  retn
0x18012849f  push    rbp
0x1801284a1  sub     rsp, 50h
0x1801284a5  mov     rbp, rdx
0x1801284a8  mov     rcx, [rbp+50h]; hKey
0x1801284ac  test    rcx, rcx
0x1801284af  jz      short loc_1801284BE
0x1801284b1  call    cs:__imp_RegCloseKey
0x1801284b8  nop     dword ptr [rax+rax+00h]
0x1801284bd  nop
0x1801284be  mov     rcx, [rbp+58h]; hKey
0x1801284c2  test    rcx, rcx
0x1801284c5  jz      short loc_1801284D4
0x1801284c7  call    cs:__imp_RegCloseKey
0x1801284ce  nop     dword ptr [rax+rax+00h]
0x1801284d3  nop
0x1801284d4  lea     rcx, [rbp+60h]; UnicodeString
0x1801284d8  call    cs:__imp_RtlFreeUnicodeString
0x1801284df  nop     dword ptr [rax+rax+00h]
0x1801284e4  nop
0x1801284e5  add     rsp, 50h
0x1801284e9  pop     rbp
0x1801284ea  retn
```
