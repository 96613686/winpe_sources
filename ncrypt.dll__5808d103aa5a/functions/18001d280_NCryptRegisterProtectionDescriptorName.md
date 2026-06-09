# NCryptRegisterProtectionDescriptorName

- ea: `0x18001d280`
- end: `0x18001d44d`
- name: `NCryptRegisterProtectionDescriptorName`
- size: `461`
- prototype: `__int64 __fastcall(LPCWSTR lpValueName, BYTE *lpData)`
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callees

- `0x18000e120`
- `0x1800198c4`
- `0x18001d280`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001d3bb`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001d3bb`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18001d36a`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18001d36a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001d430`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001d430`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18001d3e1`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18001d3e1`

## string_xrefs

- `0x18001d414`: `onecore\ds\security\cryptoapi\ncrypt\protect\ncryptprotect\reg.c`
- `0x18001d32d`: `Software\Microsoft\Cryptography\NProtect\NamedDescriptors`

## pseudocode

```c
__int64 __fastcall NCryptRegisterProtectionDescriptorName(LPCWSTR lpValueName, const wchar_t *lpData)
{
  int v2; // r14d
  size_t v5; // rdx
  int v6; // r11d
  __int64 v7; // r9
  unsigned int v8; // ebx
  __int64 v9; // rcx
  LSTATUS v10; // eax
  LSTATUS v11; // eax
  LSTATUS v12; // eax
  size_t pcchLength; // [rsp+50h] [rbp-10h] BYREF
  size_t v15; // [rsp+58h] [rbp-8h] BYREF
  DWORD dwDisposition; // [rsp+80h] [rbp+20h] BYREF
  HKEY hKey; // [rsp+98h] [rbp+38h] BYREF

  v2 = 0;
  hKey = 0;
  dwDisposition = 0;
  pcchLength = 0;
  v15 = 0;
  if ( !lpValueName || StringCchLengthW(lpValueName, (size_t)lpData, &pcchLength) < 0 || !pcchLength )
  {
    v7 = 495;
    goto LABEL_27;
  }
  if ( lpData )
  {
    if ( StringCchLengthW(lpData, v5, &v15) < 0 )
    {
      v7 = 503;
LABEL_27:
      v8 = -2146893785;
      v9 = 2148073511LL;
      goto LABEL_28;
    }
    v2 = v15;
  }
  if ( (v6 & 0xFFFFFFDF) == 0 )
  {
    v10 = RegCreateKeyExW(
            (HKEY)(((v6 & 0x20) != 0) - 0x7FFFFFFFLL),
            L"Software\\Microsoft\\Cryptography\\NProtect\\NamedDescriptors",
            0,
            0,
            0,
            0x20006u,
            0,
            &hKey,
            &dwDisposition);
    v8 = v10;
    if ( v10 )
    {
      if ( v10 > 0 )
        v8 = (unsigned __int16)v10 | 0x80070000;
      v7 = 538;
LABEL_14:
      v9 = v8;
      goto LABEL_28;
    }
    if ( lpData && *lpData )
    {
      v11 = RegSetValueExW(hKey, lpValueName, 0, 1u, (const BYTE *)lpData, 2 * v2 + 2);
      v8 = v11;
      if ( v11 )
      {
        if ( v11 > 0 )
          v8 = (unsigned __int16)v11 | 0x80070000;
        v7 = 568;
        goto LABEL_14;
      }
    }
    else
    {
      v12 = RegDeleteValueW(hKey, lpValueName);
      v8 = v12;
      if ( v12 )
      {
        if ( v12 > 0 )
          v8 = (unsigned __int16)v12 | 0x80070000;
        v7 = 551;
        goto LABEL_14;
      }
    }
    v8 = 0;
    goto LABEL_29;
  }
  v8 = -2146893815;
  v7 = 510;
  v9 = 2148073481LL;
LABEL_28:
  DebugTraceError(v9, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\protect\\ncryptprotect\\reg.c", v7);
LABEL_29:
  if ( hKey )
    RegCloseKey(hKey);
  return v8;
}

```

## disassembly

```asm
0x18001d280  mov     [rsp-18h+arg_8], rbx
0x18001d285  mov     [rsp-18h+arg_10], rsi
0x18001d28a  push    rbp
0x18001d28b  push    rdi
0x18001d28c  push    r14
0x18001d28e  mov     rbp, rsp
0x18001d291  sub     rsp, 60h
0x18001d295  xor     r14d, r14d
0x18001d298  mov     [rbp+hKey], 0
0x18001d2a0  mov     [rbp+dwDisposition], 0
0x18001d2a7  mov     r11d, r8d
0x18001d2aa  mov     [rbp+pcchLength], 0
0x18001d2b2  mov     rdi, rdx
0x18001d2b5  mov     [rbp+var_8], r14
0x18001d2b9  mov     rsi, rcx
0x18001d2bc  test    rcx, rcx
0x18001d2bf  jz      loc_18001D404
0x18001d2c5  lea     r8, [rbp+pcchLength]; pcchLength
0x18001d2c9  call    StringCchLengthW
0x18001d2ce  test    eax, eax
0x18001d2d0  js      loc_18001D404
0x18001d2d6  cmp     [rbp+pcchLength], r14
0x18001d2da  jz      loc_18001D404
0x18001d2e0  test    rdi, rdi
0x18001d2e3  jz      short loc_18001D304
0x18001d2e5  lea     r8, [rbp+var_8]; pcchLength
0x18001d2e9  mov     rcx, rdi; psz
0x18001d2ec  call    StringCchLengthW
0x18001d2f1  test    eax, eax
0x18001d2f3  jns     short loc_18001D300
0x18001d2f5  mov     r9d, 1F7h
0x18001d2fb  jmp     loc_18001D40A
0x18001d300  mov     r14, [rbp+var_8]
0x18001d304  test    r11d, 0FFFFFFDFh
0x18001d30b  jz      short loc_18001D322
0x18001d30d  mov     ebx, 80090009h
0x18001d312  mov     r9d, 1FEh
0x18001d318  mov     ecx, 80090009h
0x18001d31d  jmp     loc_18001D414
0x18001d322  xor     ecx, ecx
0x18001d324  lea     rax, [rbp+dwDisposition]
0x18001d328  mov     [rsp+60h+lpdwDisposition], rax; lpdwDisposition
0x18001d32d  lea     rdx, aSoftwareMicros; "Software\\Microsoft\\Cryptography\\NPro"...
0x18001d334  test    r11b, 20h
0x18001d338  lea     rax, [rbp+hKey]
0x18001d33c  mov     [rsp+60h+phkResult], rax; phkResult
0x18001d341  setnz   cl
0x18001d344  mov     [rsp+60h+lpSecurityAttributes], 0; lpSecurityAttributes
0x18001d34d  add     rcx, 0FFFFFFFF80000001h; hKey
0x18001d354  mov     [rsp+60h+samDesired], 20006h; samDesired
0x18001d35c  xor     r9d, r9d; lpClass
0x18001d35f  mov     [rsp+60h+dwOptions], 0; dwOptions
0x18001d367  xor     r8d, r8d; Reserved
0x18001d36a  call    cs:__imp_RegCreateKeyExW
0x18001d370  mov     ebx, eax
0x18001d372  test    eax, eax
0x18001d374  jz      short loc_18001D38E
0x18001d376  jle     short loc_18001D381
0x18001d378  movzx   ebx, ax
0x18001d37b  or      ebx, 80070000h
0x18001d381  mov     r9d, 21Ah
0x18001d387  mov     ecx, ebx
0x18001d389  jmp     loc_18001D414
0x18001d38e  test    rdi, rdi
0x18001d391  jz      short loc_18001D3DA
0x18001d393  xor     eax, eax
0x18001d395  cmp     ax, [rdi]
0x18001d398  jz      short loc_18001D3DA
0x18001d39a  mov     rcx, [rbp+hKey]; hKey
0x18001d39e  lea     eax, ds:2[r14*2]
0x18001d3a6  mov     [rsp+60h+samDesired], eax; cbData
0x18001d3aa  mov     r9d, 1; dwType
0x18001d3b0  xor     r8d, r8d; Reserved
0x18001d3b3  mov     qword ptr [rsp+60h+dwOptions], rdi; lpData
0x18001d3b8  mov     rdx, rsi; lpValueName
0x18001d3bb  call    cs:__imp_RegSetValueExW
0x18001d3c1  mov     ebx, eax
0x18001d3c3  test    eax, eax
0x18001d3c5  jz      short loc_18001D400
0x18001d3c7  jle     short loc_18001D3D2
0x18001d3c9  movzx   ebx, ax
0x18001d3cc  or      ebx, 80070000h
0x18001d3d2  mov     r9d, 238h
0x18001d3d8  jmp     short loc_18001D387
0x18001d3da  mov     rcx, [rbp+hKey]; hKey
0x18001d3de  mov     rdx, rsi; lpValueName
0x18001d3e1  call    cs:__imp_RegDeleteValueW
0x18001d3e7  mov     ebx, eax
0x18001d3e9  test    eax, eax
0x18001d3eb  jz      short loc_18001D400
0x18001d3ed  jle     short loc_18001D3F8
0x18001d3ef  movzx   ebx, ax
0x18001d3f2  or      ebx, 80070000h
0x18001d3f8  mov     r9d, 227h
0x18001d3fe  jmp     short loc_18001D387
0x18001d400  xor     ebx, ebx
0x18001d402  jmp     short loc_18001D427
0x18001d404  mov     r9d, 1EFh
0x18001d40a  mov     ebx, 80090027h
0x18001d40f  mov     ecx, 80090027h
0x18001d414  lea     r8, aOnecoreDsSecur_13; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18001d41b  lea     rdx, aStatus; "Status"
0x18001d422  call    DebugTraceError
0x18001d427  mov     rcx, [rbp+hKey]; hKey
0x18001d42b  test    rcx, rcx
0x18001d42e  jz      short loc_18001D436
0x18001d430  call    cs:__imp_RegCloseKey
0x18001d436  lea     r11, [rsp+60h+var_s0]
0x18001d43b  mov     eax, ebx
0x18001d43d  mov     rbx, [r11+28h]
0x18001d441  mov     rsi, [r11+30h]
0x18001d445  mov     rsp, r11
0x18001d448  pop     r14
0x18001d44a  pop     rdi
0x18001d44b  pop     rbp
0x18001d44c  retn
```
