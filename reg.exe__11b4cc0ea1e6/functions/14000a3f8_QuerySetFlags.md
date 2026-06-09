# QuerySetFlags

- ea: `0x14000a3f8`
- end: `0x14000a7d2`
- name: `QuerySetFlags`
- size: `986`
- prototype: `__int64 __fastcall(HKEY, const WCHAR *, __int64)`
- caller_count: `2`
- callee_count: `13`
- tags: `registry_config, loader_planting`

## callers

- `0x140009ec0`
- `0x14000a3f8`

## callees

- `0x140001340`
- `0x140001bb2`
- `0x140001cc6`
- `0x140002b70`
- `0x14000a3f8`
- `0x14000c62c`
- `0x14000c9c0`
- `0x14000cd48`
- `0x14000daa4`
- `0x14000dce0`
- `0x14000e020`
- `0x14000e2f8`
- `0x14000e450`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14000a748`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14000a748`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x14000a6d9`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x14000a6d9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14000a76c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14000a76c`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x14000a60b`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x14000a60b`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x14000a65f`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x14000a65f`
- `ntdll!NtQueryKey` at `0x14000a4e4`
- `ntdll!NtQueryKey` at `0x14000a4e4`
- `ntdll!NtSetInformationKey` at `0x14000a494`
- `ntdll!NtSetInformationKey` at `0x14000a494`

## pseudocode

```c
__int64 __fastcall QuerySetFlags(HKEY a1, const WCHAR *a2, __int64 a3)
{
  DWORD v3; // r12d
  __int64 ResString2FromModule; // rax
  FILE *v9; // rax
  FILE *v10; // rax
  const wchar_t *v11; // rdi
  const wchar_t *v12; // rbx
  FILE *v13; // rax
  const wchar_t *v14; // rbx
  FILE *v15; // rax
  FILE *v16; // rax
  unsigned int SetFlags; // edi
  unsigned int v18; // ebx
  DWORD v19; // ecx
  void *v20; // rbx
  int v21; // eax
  DWORD v22; // r13d
  __int64 v23; // r15
  int v24; // r9d
  REGSAM v25; // r9d
  DWORD cbMaxSubKeyLen; // [rsp+60h] [rbp-29h] BYREF
  DWORD cSubKeys; // [rsp+64h] [rbp-25h] BYREF
  int KeySetInformation; // [rsp+68h] [rbp-21h] BYREF
  DWORD cchName; // [rsp+6Ch] [rbp-1Dh] BYREF
  HKEY hKey; // [rsp+70h] [rbp-19h] BYREF
  ULONG ResultLength; // [rsp+78h] [rbp-11h] BYREF
  __int64 Memory; // [rsp+80h] [rbp-9h] BYREF
  const WCHAR *v33; // [rsp+88h] [rbp-1h]
  __int64 v34; // [rsp+90h] [rbp+7h] BYREF
  __int64 KeyInformation; // [rsp+98h] [rbp+Fh] BYREF
  int v36; // [rsp+A0h] [rbp+17h]

  v3 = 0;
  v33 = a2;
  hKey = 0;
  KeyInformation = 0;
  v36 = 0;
  KeySetInformation = 0;
  ResultLength = 0;
  cchName = 0;
  cbMaxSubKeyLen = 0;
  cSubKeys = 0;
  if ( !a1 || !a2 || !a3 )
  {
    v18 = 87;
    goto LABEL_38;
  }
  if ( *(_DWORD *)(a3 + 136) == 1 )
  {
    KeySetInformation = *(_DWORD *)(a3 + 144);
    if ( (NtSetInformationKey(a1, KeyControlFlagsInformation, &KeySetInformation, 4u) & 0xC0000000) == 0xC0000000 )
    {
LABEL_6:
      ResString2FromModule = GetResString2FromModule(3221225472LL, 161, 0);
      SetReason2(1, ResString2FromModule, *(_QWORD *)(a3 + 88));
      return 1;
    }
  }
  else
  {
    if ( (NtQueryKey(a1, KeyFlagsInformation, &KeyInformation, 0xCu, &ResultLength) & 0xC0000000) == 0xC0000000 )
      goto LABEL_6;
    v9 = o___acrt_iob_func_0(1u);
    ShowMessage(v9, L"\n");
    v10 = o___acrt_iob_func_0(1u);
    ShowMessageEx(v10, 1, 1, L"%s\n", a2);
    v11 = L"SET";
    v12 = L"SET";
    if ( (v36 & 2) == 0 )
      v12 = L"CLEAR";
    v13 = o___acrt_iob_func_0(1u);
    ShowMessageEx(v13, 1, 1, L"\tREG_KEY_DONT_VIRTUALIZE: %s\n", v12);
    v14 = L"SET";
    if ( (v36 & 4) == 0 )
      v14 = L"CLEAR";
    v15 = o___acrt_iob_func_0(1u);
    ShowMessageEx(v15, 1, 1, L"\tREG_KEY_DONT_SILENT_FAIL: %s\n", v14);
    if ( (v36 & 8) == 0 )
      v11 = L"CLEAR";
    v16 = o___acrt_iob_func_0(1u);
    ShowMessageEx(v16, 1, 1, L"\tREG_KEY_RECURSE_FLAG: %s\n\n", v11);
    v3 = 0;
  }
  SetFlags = 0;
  if ( *(_DWORD *)(a3 + 32) != 1 )
    return SetFlags;
  v18 = RegQueryInfoKeyW(a1, 0, 0, 0, &cSubKeys, &cbMaxSubKeyLen, 0, 0, 0, 0, 0, 0);
  if ( !v18 )
  {
    v19 = cbMaxSubKeyLen;
    if ( !cSubKeys || cbMaxSubKeyLen )
    {
      if ( cbMaxSubKeyLen < 0x100 )
        v19 = 2 * cbMaxSubKeyLen;
    }
    else
    {
      v19 = 256;
    }
    cbMaxSubKeyLen = v19 + 1;
    Memory = AllocateMemory(2 * (v19 + 1));
    v20 = (void *)Memory;
    if ( !Memory )
      goto LABEL_23;
    v21 = lstrlenW(a2);
    v22 = v21 + cbMaxSubKeyLen + 1;
    v34 = AllocateMemory(2 * v22);
    v23 = v34;
    if ( !v34 )
    {
      FreeMemory(&Memory);
LABEL_23:
      v18 = 14;
      goto LABEL_38;
    }
    SetFlags = 0;
    if ( cSubKeys )
    {
      do
      {
        cchName = cbMaxSubKeyLen;
        memset_0(v20, 0, 2LL * cbMaxSubKeyLen);
        SetFlags = 0;
        if ( !RegEnumKeyExW(a1, v3, (LPWSTR)v20, &cchName, 0, 0, 0, 0) )
        {
          StringCopyW(v23, v33, v22);
          StringConcatW(v23, L"\\", v22);
          StringConcatW(v23, v20, v22);
          v24 = *(_DWORD *)(a3 + 140);
          if ( *(_DWORD *)(a3 + 136) == 1 )
            v25 = v24 | 0xF003F;
          else
            v25 = v24 | 0x20019;
          if ( !RegOpenKeyExW(a1, (LPCWSTR)v20, 0, v25, &hKey) )
          {
            SetFlags = QuerySetFlags(hKey, v23, a3);
            if ( hKey )
            {
              RegCloseKey(hKey);
              hKey = 0;
            }
          }
        }
        ++v3;
      }
      while ( v3 < cSubKeys );
    }
    FreeMemory(&Memory);
    FreeMemory(&v34);
    return SetFlags;
  }
LABEL_38:
  SaveErrorMessage(v18);
  return v18;
}

```

## disassembly

```asm
0x14000a3f8  mov     [rsp-8+arg_18], rbx
0x14000a3fd  push    rbp
0x14000a3fe  push    rsi
0x14000a3ff  push    rdi
0x14000a400  push    r12
0x14000a402  push    r13
0x14000a404  push    r14
0x14000a406  push    r15
0x14000a408  lea     rbp, [rsp-27h]
0x14000a40d  sub     rsp, 0B0h
0x14000a414  mov     rax, cs:__security_cookie
0x14000a41b  xor     rax, rsp
0x14000a41e  mov     [rbp+57h+var_38], rax
0x14000a422  xor     r12d, r12d
0x14000a425  mov     [rbp+57h+var_58], rdx
0x14000a429  xor     eax, eax
0x14000a42b  mov     [rbp+57h+hKey], r12
0x14000a42f  mov     [rbp+57h+KeyInformation], rax
0x14000a433  mov     rsi, r8
0x14000a436  mov     [rbp+57h+var_40], eax
0x14000a439  mov     r15, rdx
0x14000a43c  mov     [rbp+57h+KeySetInformation], r12d
0x14000a440  mov     r14, rcx
0x14000a443  mov     [rbp+57h+var_68], r12d
0x14000a447  mov     [rbp+57h+cchName], r12d
0x14000a44b  mov     [rbp+57h+cbMaxSubKeyLen], r12d
0x14000a44f  mov     [rbp+57h+cSubKeys], r12d
0x14000a453  test    rcx, rcx
0x14000a456  jz      loc_14000A79D
0x14000a45c  test    rdx, rdx
0x14000a45f  jz      loc_14000A79D
0x14000a465  test    r8, r8
0x14000a468  jz      loc_14000A79D
0x14000a46e  lea     r13d, [r12+1]
0x14000a473  cmp     [r8+88h], r13d
0x14000a47a  jnz     short loc_14000A4CD
0x14000a47c  mov     eax, [r8+90h]
0x14000a483  lea     r9d, [r12+4]; KeySetInformationLength
0x14000a488  lea     r8, [rbp+57h+KeySetInformation]; KeySetInformation
0x14000a48c  mov     [rbp+57h+KeySetInformation], eax
0x14000a48f  lea     edx, [r12+2]; KeySetInformationClass
0x14000a494  call    cs:__imp_NtSetInformationKey
0x14000a49a  mov     ecx, 0C0000000h
0x14000a49f  and     eax, ecx
0x14000a4a1  cmp     eax, ecx
0x14000a4a3  jnz     loc_14000A5C3
0x14000a4a9  xor     r8d, r8d
0x14000a4ac  mov     edx, 0A1h
0x14000a4b1  call    GetResString2FromModule
0x14000a4b6  mov     r8, [rsi+58h]
0x14000a4ba  mov     rdx, rax
0x14000a4bd  mov     ecx, r13d
0x14000a4c0  call    SetReason2
0x14000a4c5  mov     eax, r13d
0x14000a4c8  jmp     loc_14000A7AB
0x14000a4cd  mov     r9d, 0Ch; Length
0x14000a4d3  lea     rax, [rbp+57h+var_68]
0x14000a4d7  lea     r8, [rbp+57h+KeyInformation]; KeyInformation
0x14000a4db  mov     [rsp+0E0h+ResultLength], rax; ResultLength
0x14000a4e0  lea     edx, [r9-7]; KeyInformationClass
0x14000a4e4  call    cs:__imp_NtQueryKey
0x14000a4ea  mov     ecx, 0C0000000h
0x14000a4ef  and     eax, ecx
0x14000a4f1  cmp     eax, ecx
0x14000a4f3  jz      short loc_14000A4A9
0x14000a4f5  mov     ecx, r13d; Ix
0x14000a4f8  call    _o___acrt_iob_func_0
0x14000a4fd  mov     rcx, rax; Stream
0x14000a500  lea     rdx, asc_140010950; "\n"
0x14000a507  call    ShowMessage
0x14000a50c  mov     ecx, r13d; Ix
0x14000a50f  call    _o___acrt_iob_func_0
0x14000a514  mov     rcx, rax
0x14000a517  mov     [rsp+0E0h+ResultLength], r15
0x14000a51c  lea     r9, aS_5; "%s\n"
0x14000a523  mov     r8d, r13d
0x14000a526  mov     edx, r13d
0x14000a529  call    ShowMessageEx
0x14000a52e  test    byte ptr [rbp+57h+var_40], 2
0x14000a532  lea     rdi, aSet; "SET"
0x14000a539  mov     rbx, rdi
0x14000a53c  lea     r12, aClear; "CLEAR"
0x14000a543  mov     ecx, r13d; Ix
0x14000a546  cmovz   rbx, r12
0x14000a54a  call    _o___acrt_iob_func_0
0x14000a54f  mov     rcx, rax
0x14000a552  mov     [rsp+0E0h+ResultLength], rbx
0x14000a557  lea     r9, aRegKeyDontVirt; "\tREG_KEY_DONT_VIRTUALIZE: %s\n"
0x14000a55e  mov     r8d, r13d
0x14000a561  mov     edx, r13d
0x14000a564  call    ShowMessageEx
0x14000a569  test    byte ptr [rbp+57h+var_40], 4
0x14000a56d  mov     rbx, rdi
0x14000a570  mov     ecx, r13d; Ix
0x14000a573  cmovz   rbx, r12
0x14000a577  call    _o___acrt_iob_func_0
0x14000a57c  mov     rcx, rax
0x14000a57f  mov     [rsp+0E0h+ResultLength], rbx
0x14000a584  lea     r9, aRegKeyDontSile; "\tREG_KEY_DONT_SILENT_FAIL: %s\n"
0x14000a58b  mov     r8d, r13d
0x14000a58e  mov     edx, r13d
0x14000a591  call    ShowMessageEx
0x14000a596  test    byte ptr [rbp+57h+var_40], 8
0x14000a59a  mov     ecx, r13d; Ix
0x14000a59d  cmovz   rdi, r12
0x14000a5a1  call    _o___acrt_iob_func_0
0x14000a5a6  mov     rcx, rax
0x14000a5a9  mov     [rsp+0E0h+ResultLength], rdi
0x14000a5ae  lea     r9, aRegKeyRecurseF; "\tREG_KEY_RECURSE_FLAG: %s\n\n"
0x14000a5b5  mov     r8d, r13d
0x14000a5b8  mov     edx, r13d
0x14000a5bb  call    ShowMessageEx
0x14000a5c0  xor     r12d, r12d
0x14000a5c3  mov     edi, r12d
0x14000a5c6  cmp     [rsi+20h], r13d
0x14000a5ca  jnz     loc_14000A799
0x14000a5d0  mov     [rsp+0E0h+lpftLastWriteTime], r12; lpftLastWriteTime
0x14000a5d5  lea     rax, [rbp+57h+cbMaxSubKeyLen]
0x14000a5d9  mov     [rsp+0E0h+lpcbSecurityDescriptor], r12; lpcbSecurityDescriptor
0x14000a5de  xor     r9d, r9d; lpReserved
0x14000a5e1  mov     [rsp+0E0h+lpcbMaxValueLen], r12; lpcbMaxValueLen
0x14000a5e6  xor     r8d, r8d; lpcchClass
0x14000a5e9  mov     [rsp+0E0h+lpcbMaxValueNameLen], r12; lpcbMaxValueNameLen
0x14000a5ee  xor     edx, edx; lpClass
0x14000a5f0  mov     [rsp+0E0h+lpcValues], r12; lpcValues
0x14000a5f5  mov     rcx, r14; hKey
0x14000a5f8  mov     [rsp+0E0h+lpcbMaxClassLen], r12; lpcbMaxClassLen
0x14000a5fd  mov     [rsp+0E0h+lpcbMaxSubKeyLen], rax; lpcbMaxSubKeyLen
0x14000a602  lea     rax, [rbp+57h+cSubKeys]
0x14000a606  mov     [rsp+0E0h+ResultLength], rax; lpcSubKeys
0x14000a60b  call    cs:__imp_RegQueryInfoKeyW
0x14000a611  mov     ebx, eax
0x14000a613  test    eax, eax
0x14000a615  jnz     loc_14000A7A2
0x14000a61b  mov     ecx, [rbp+57h+cbMaxSubKeyLen]
0x14000a61e  cmp     [rbp+57h+cSubKeys], r12d
0x14000a622  jz      short loc_14000A62F
0x14000a624  test    ecx, ecx
0x14000a626  jnz     short loc_14000A62F
0x14000a628  mov     ecx, 100h
0x14000a62d  jmp     short loc_14000A639
0x14000a62f  cmp     ecx, 100h
0x14000a635  jnb     short loc_14000A639
0x14000a637  add     ecx, ecx
0x14000a639  add     ecx, r13d
0x14000a63c  mov     [rbp+57h+cbMaxSubKeyLen], ecx
0x14000a63f  add     ecx, ecx; dwBytes
0x14000a641  call    AllocateMemory
0x14000a646  mov     [rbp+57h+var_60], rax
0x14000a64a  mov     rbx, rax
0x14000a64d  test    rax, rax
0x14000a650  jnz     short loc_14000A65C
0x14000a652  mov     ebx, 0Eh
0x14000a657  jmp     loc_14000A7A2
0x14000a65c  mov     rcx, r15; lpString
0x14000a65f  call    cs:__imp_lstrlenW
0x14000a665  mov     r13d, [rbp+57h+cbMaxSubKeyLen]
0x14000a669  inc     r13d
0x14000a66c  add     r13d, eax
0x14000a66f  lea     ecx, ds:0[r13*2]; dwBytes
0x14000a677  call    AllocateMemory
0x14000a67c  mov     [rbp+57h+var_50], rax
0x14000a680  mov     r15, rax
0x14000a683  test    rax, rax
0x14000a686  jnz     short loc_14000A693
0x14000a688  lea     rcx, [rbp+57h+var_60]
0x14000a68c  call    FreeMemory
0x14000a691  jmp     short loc_14000A652
0x14000a693  cmp     [rbp+57h+cSubKeys], 0
0x14000a697  mov     edi, r12d
0x14000a69a  jbe     loc_14000A787
0x14000a6a0  mov     eax, [rbp+57h+cbMaxSubKeyLen]
0x14000a6a3  xor     edx, edx; Val
0x14000a6a5  mov     r8d, eax
0x14000a6a8  mov     [rbp+57h+cchName], eax
0x14000a6ab  add     r8, r8; Size
0x14000a6ae  mov     rcx, rbx; void *
0x14000a6b1  call    memset_0
0x14000a6b6  xor     edi, edi
0x14000a6b8  lea     r9, [rbp+57h+cchName]; lpcchName
0x14000a6bc  mov     [rsp+0E0h+lpcValues], rdi; lpftLastWriteTime
0x14000a6c1  mov     r8, rbx; lpName
0x14000a6c4  mov     [rsp+0E0h+lpcbMaxClassLen], rdi; lpcchClass
0x14000a6c9  mov     edx, r12d; dwIndex
0x14000a6cc  mov     [rsp+0E0h+lpcbMaxSubKeyLen], rdi; lpClass
0x14000a6d1  mov     rcx, r14; hKey
0x14000a6d4  mov     [rsp+0E0h+ResultLength], rdi; lpReserved
0x14000a6d9  call    cs:__imp_RegEnumKeyExW
0x14000a6df  test    eax, eax
0x14000a6e1  jnz     loc_14000A77A
0x14000a6e7  mov     rdx, [rbp+57h+var_58]
0x14000a6eb  mov     r8d, r13d
0x14000a6ee  mov     rcx, r15
0x14000a6f1  call    StringCopyW
0x14000a6f6  mov     r8d, r13d
0x14000a6f9  lea     rdx, asc_14001081C; "\\"
0x14000a700  mov     rcx, r15
0x14000a703  call    StringConcatW
0x14000a708  mov     r8d, r13d
0x14000a70b  mov     rdx, rbx
0x14000a70e  mov     rcx, r15
0x14000a711  call    StringConcatW
0x14000a716  mov     r9d, [rsi+8Ch]
0x14000a71d  lea     rax, [rbp+57h+hKey]
0x14000a721  xor     r8d, r8d; ulOptions
0x14000a724  mov     [rsp+0E0h+ResultLength], rax; phkResult
0x14000a729  cmp     dword ptr [rsi+88h], 1
0x14000a730  mov     rdx, rbx; lpSubKey
0x14000a733  mov     rcx, r14; hKey
0x14000a736  jnz     short loc_14000A741
0x14000a738  or      r9d, 0F003Fh
0x14000a73f  jmp     short loc_14000A748
0x14000a741  or      r9d, 20019h; samDesired
0x14000a748  call    cs:__imp_RegOpenKeyExW
0x14000a74e  test    eax, eax
0x14000a750  jnz     short loc_14000A77A
0x14000a752  mov     rcx, [rbp+57h+hKey]
0x14000a756  mov     r8, rsi
0x14000a759  mov     rdx, r15
0x14000a75c  call    QuerySetFlags
0x14000a761  mov     rcx, [rbp+57h+hKey]; hKey
0x14000a765  mov     edi, eax
0x14000a767  test    rcx, rcx
0x14000a76a  jz      short loc_14000A77A
0x14000a76c  call    cs:__imp_RegCloseKey
0x14000a772  mov     [rbp+57h+hKey], 0
0x14000a77a  inc     r12d
0x14000a77d  cmp     r12d, [rbp+57h+cSubKeys]
0x14000a781  jb      loc_14000A6A0
0x14000a787  lea     rcx, [rbp+57h+var_60]
0x14000a78b  call    FreeMemory
0x14000a790  lea     rcx, [rbp+57h+var_50]
0x14000a794  call    FreeMemory
0x14000a799  mov     eax, edi
0x14000a79b  jmp     short loc_14000A7AB
0x14000a79d  mov     ebx, 57h ; 'W'
0x14000a7a2  mov     ecx, ebx
0x14000a7a4  call    SaveErrorMessage
0x14000a7a9  mov     eax, ebx
0x14000a7ab  mov     rcx, [rbp+57h+var_38]
0x14000a7af  xor     rcx, rsp; StackCookie
0x14000a7b2  call    __security_check_cookie
0x14000a7b7  mov     rbx, [rsp+0E0h+arg_18]
0x14000a7bf  add     rsp, 0B0h
0x14000a7c6  pop     r15
0x14000a7c8  pop     r14
0x14000a7ca  pop     r13
0x14000a7cc  pop     r12
0x14000a7ce  pop     rdi
0x14000a7cf  pop     rsi
0x14000a7d0  pop     rbp
0x14000a7d1  retn
```
