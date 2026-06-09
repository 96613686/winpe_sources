# QuerySetFlags

- ea: `0x14000aa4c`
- end: `0x14000ae51`
- name: `QuerySetFlags`
- size: `1029`
- prototype: `__int64 __fastcall(HKEY, _WORD *, __int64)`
- caller_count: `2`
- callee_count: `13`
- tags: `registry_config, loader_planting`

## callers

- `0x14000a4e4`
- `0x14000aa4c`

## callees

- `0x140001340`
- `0x140001bb2`
- `0x140001cc6`
- `0x140002ce4`
- `0x14000aa4c`
- `0x14000ce50`
- `0x14000d2d0`
- `0x14000d694`
- `0x14000e600`
- `0x14000e864`
- `0x14000ec2c`
- `0x14000ef5c`
- `0x14000f0c0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14000adba`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14000adba`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x14000ad45`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x14000ad45`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14000ade4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14000ade4`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x14000ac6b`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x14000ac6b`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x14000acc5`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x14000acc5`
- `ntdll!NtQueryKey` at `0x14000ab3e`
- `ntdll!NtQueryKey` at `0x14000ab3e`
- `ntdll!NtSetInformationKey` at `0x14000aae8`
- `ntdll!NtSetInformationKey` at `0x14000aae8`

## pseudocode

```c
__int64 __fastcall QuerySetFlags(HKEY a1, _WORD *a2, __int64 a3)
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
  _WORD *v23; // r15
  int v24; // r9d
  REGSAM v25; // r9d
  DWORD cbMaxSubKeyLen; // [rsp+60h] [rbp-29h] BYREF
  DWORD cSubKeys; // [rsp+64h] [rbp-25h] BYREF
  int KeySetInformation; // [rsp+68h] [rbp-21h] BYREF
  DWORD cchName; // [rsp+6Ch] [rbp-1Dh] BYREF
  HKEY hKey; // [rsp+70h] [rbp-19h] BYREF
  ULONG ResultLength; // [rsp+78h] [rbp-11h] BYREF
  LPVOID Memory; // [rsp+80h] [rbp-9h] BYREF
  _WORD *v33; // [rsp+88h] [rbp-1h]
  _WORD *v34; // [rsp+90h] [rbp+7h] BYREF
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
    v20 = Memory;
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
0x14000aa4c  mov     [rsp-8+arg_18], rbx
0x14000aa51  push    rbp
0x14000aa52  push    rsi
0x14000aa53  push    rdi
0x14000aa54  push    r12
0x14000aa56  push    r13
0x14000aa58  push    r14
0x14000aa5a  push    r15
0x14000aa5c  lea     rbp, [rsp-27h]
0x14000aa61  sub     rsp, 0B0h
0x14000aa68  mov     rax, cs:__security_cookie
0x14000aa6f  xor     rax, rsp
0x14000aa72  mov     [rbp+57h+var_38], rax
0x14000aa76  xor     r12d, r12d
0x14000aa79  mov     [rbp+57h+var_58], rdx
0x14000aa7d  xor     eax, eax
0x14000aa7f  mov     [rbp+57h+hKey], r12
0x14000aa83  mov     [rbp+57h+KeyInformation], rax
0x14000aa87  mov     rsi, r8
0x14000aa8a  mov     [rbp+57h+var_40], eax
0x14000aa8d  mov     r15, rdx
0x14000aa90  mov     [rbp+57h+KeySetInformation], r12d
0x14000aa94  mov     r14, rcx
0x14000aa97  mov     [rbp+57h+var_68], r12d
0x14000aa9b  mov     [rbp+57h+cchName], r12d
0x14000aa9f  mov     [rbp+57h+cbMaxSubKeyLen], r12d
0x14000aaa3  mov     [rbp+57h+cSubKeys], r12d
0x14000aaa7  test    rcx, rcx
0x14000aaaa  jz      loc_14000AE1B
0x14000aab0  test    rdx, rdx
0x14000aab3  jz      loc_14000AE1B
0x14000aab9  test    r8, r8
0x14000aabc  jz      loc_14000AE1B
0x14000aac2  lea     r13d, [r12+1]
0x14000aac7  cmp     [r8+88h], r13d
0x14000aace  jnz     short loc_14000AB27
0x14000aad0  mov     eax, [r8+90h]
0x14000aad7  lea     r9d, [r12+4]; KeySetInformationLength
0x14000aadc  lea     r8, [rbp+57h+KeySetInformation]; KeySetInformation
0x14000aae0  mov     [rbp+57h+KeySetInformation], eax
0x14000aae3  lea     edx, [r12+2]; KeySetInformationClass
0x14000aae8  call    cs:__imp_NtSetInformationKey
0x14000aaef  nop     dword ptr [rax+rax+00h]
0x14000aaf4  mov     ecx, 0C0000000h
0x14000aaf9  and     eax, ecx
0x14000aafb  cmp     eax, ecx
0x14000aafd  jnz     loc_14000AC23
0x14000ab03  xor     r8d, r8d
0x14000ab06  mov     edx, 0A1h
0x14000ab0b  call    GetResString2FromModule
0x14000ab10  mov     r8, [rsi+58h]
0x14000ab14  mov     rdx, rax
0x14000ab17  mov     ecx, r13d
0x14000ab1a  call    SetReason2
0x14000ab1f  mov     eax, r13d
0x14000ab22  jmp     loc_14000AE29
0x14000ab27  mov     r9d, 0Ch; Length
0x14000ab2d  lea     rax, [rbp+57h+var_68]
0x14000ab31  lea     r8, [rbp+57h+KeyInformation]; KeyInformation
0x14000ab35  mov     [rsp+0E0h+ResultLength], rax; ResultLength
0x14000ab3a  lea     edx, [r9-7]; KeyInformationClass
0x14000ab3e  call    cs:__imp_NtQueryKey
0x14000ab45  nop     dword ptr [rax+rax+00h]
0x14000ab4a  mov     ecx, 0C0000000h
0x14000ab4f  and     eax, ecx
0x14000ab51  cmp     eax, ecx
0x14000ab53  jz      short loc_14000AB03
0x14000ab55  mov     ecx, r13d; Ix
0x14000ab58  call    _o___acrt_iob_func_0
0x14000ab5d  mov     rcx, rax; Stream
0x14000ab60  lea     rdx, asc_140011950; "\n"
0x14000ab67  call    ShowMessage
0x14000ab6c  mov     ecx, r13d; Ix
0x14000ab6f  call    _o___acrt_iob_func_0
0x14000ab74  mov     rcx, rax
0x14000ab77  mov     [rsp+0E0h+ResultLength], r15
0x14000ab7c  lea     r9, aS_5; "%s\n"
0x14000ab83  mov     r8d, r13d
0x14000ab86  mov     edx, r13d
0x14000ab89  call    ShowMessageEx
0x14000ab8e  test    byte ptr [rbp+57h+var_40], 2
0x14000ab92  lea     rdi, aSet; "SET"
0x14000ab99  mov     rbx, rdi
0x14000ab9c  lea     r12, aClear; "CLEAR"
0x14000aba3  mov     ecx, r13d; Ix
0x14000aba6  cmovz   rbx, r12
0x14000abaa  call    _o___acrt_iob_func_0
0x14000abaf  mov     rcx, rax
0x14000abb2  mov     [rsp+0E0h+ResultLength], rbx
0x14000abb7  lea     r9, aRegKeyDontVirt; "\tREG_KEY_DONT_VIRTUALIZE: %s\n"
0x14000abbe  mov     r8d, r13d
0x14000abc1  mov     edx, r13d
0x14000abc4  call    ShowMessageEx
0x14000abc9  test    byte ptr [rbp+57h+var_40], 4
0x14000abcd  mov     rbx, rdi
0x14000abd0  mov     ecx, r13d; Ix
0x14000abd3  cmovz   rbx, r12
0x14000abd7  call    _o___acrt_iob_func_0
0x14000abdc  mov     rcx, rax
0x14000abdf  mov     [rsp+0E0h+ResultLength], rbx
0x14000abe4  lea     r9, aRegKeyDontSile; "\tREG_KEY_DONT_SILENT_FAIL: %s\n"
0x14000abeb  mov     r8d, r13d
0x14000abee  mov     edx, r13d
0x14000abf1  call    ShowMessageEx
0x14000abf6  test    byte ptr [rbp+57h+var_40], 8
0x14000abfa  mov     ecx, r13d; Ix
0x14000abfd  cmovz   rdi, r12
0x14000ac01  call    _o___acrt_iob_func_0
0x14000ac06  mov     rcx, rax
0x14000ac09  mov     [rsp+0E0h+ResultLength], rdi
0x14000ac0e  lea     r9, aRegKeyRecurseF; "\tREG_KEY_RECURSE_FLAG: %s\n\n"
0x14000ac15  mov     r8d, r13d
0x14000ac18  mov     edx, r13d
0x14000ac1b  call    ShowMessageEx
0x14000ac20  xor     r12d, r12d
0x14000ac23  mov     edi, r12d
0x14000ac26  cmp     [rsi+20h], r13d
0x14000ac2a  jnz     loc_14000AE17
0x14000ac30  mov     [rsp+0E0h+lpftLastWriteTime], r12; lpftLastWriteTime
0x14000ac35  lea     rax, [rbp+57h+cbMaxSubKeyLen]
0x14000ac39  mov     [rsp+0E0h+lpcbSecurityDescriptor], r12; lpcbSecurityDescriptor
0x14000ac3e  xor     r9d, r9d; lpReserved
0x14000ac41  mov     [rsp+0E0h+lpcbMaxValueLen], r12; lpcbMaxValueLen
0x14000ac46  xor     r8d, r8d; lpcchClass
0x14000ac49  mov     [rsp+0E0h+lpcbMaxValueNameLen], r12; lpcbMaxValueNameLen
0x14000ac4e  xor     edx, edx; lpClass
0x14000ac50  mov     [rsp+0E0h+lpcValues], r12; lpcValues
0x14000ac55  mov     rcx, r14; hKey
0x14000ac58  mov     [rsp+0E0h+lpcbMaxClassLen], r12; lpcbMaxClassLen
0x14000ac5d  mov     [rsp+0E0h+lpcbMaxSubKeyLen], rax; lpcbMaxSubKeyLen
0x14000ac62  lea     rax, [rbp+57h+cSubKeys]
0x14000ac66  mov     [rsp+0E0h+ResultLength], rax; lpcSubKeys
0x14000ac6b  call    cs:__imp_RegQueryInfoKeyW
0x14000ac72  nop     dword ptr [rax+rax+00h]
0x14000ac77  mov     ebx, eax
0x14000ac79  test    eax, eax
0x14000ac7b  jnz     loc_14000AE20
0x14000ac81  mov     ecx, [rbp+57h+cbMaxSubKeyLen]
0x14000ac84  cmp     [rbp+57h+cSubKeys], r12d
0x14000ac88  jz      short loc_14000AC95
0x14000ac8a  test    ecx, ecx
0x14000ac8c  jnz     short loc_14000AC95
0x14000ac8e  mov     ecx, 100h
0x14000ac93  jmp     short loc_14000AC9F
0x14000ac95  cmp     ecx, 100h
0x14000ac9b  jnb     short loc_14000AC9F
0x14000ac9d  add     ecx, ecx
0x14000ac9f  add     ecx, r13d
0x14000aca2  mov     [rbp+57h+cbMaxSubKeyLen], ecx
0x14000aca5  add     ecx, ecx; dwBytes
0x14000aca7  call    AllocateMemory
0x14000acac  mov     [rbp+57h+var_60], rax
0x14000acb0  mov     rbx, rax
0x14000acb3  test    rax, rax
0x14000acb6  jnz     short loc_14000ACC2
0x14000acb8  mov     ebx, 0Eh
0x14000acbd  jmp     loc_14000AE20
0x14000acc2  mov     rcx, r15; lpString
0x14000acc5  call    cs:__imp_lstrlenW
0x14000accc  nop     dword ptr [rax+rax+00h]
0x14000acd1  mov     r13d, [rbp+57h+cbMaxSubKeyLen]
0x14000acd5  inc     r13d
0x14000acd8  add     r13d, eax
0x14000acdb  lea     ecx, ds:0[r13*2]; dwBytes
0x14000ace3  call    AllocateMemory
0x14000ace8  mov     [rbp+57h+var_50], rax
0x14000acec  mov     r15, rax
0x14000acef  test    rax, rax
0x14000acf2  jnz     short loc_14000ACFF
0x14000acf4  lea     rcx, [rbp+57h+var_60]
0x14000acf8  call    FreeMemory
0x14000acfd  jmp     short loc_14000ACB8
0x14000acff  cmp     [rbp+57h+cSubKeys], 0
0x14000ad03  mov     edi, r12d
0x14000ad06  jbe     loc_14000AE05
0x14000ad0c  mov     eax, [rbp+57h+cbMaxSubKeyLen]
0x14000ad0f  xor     edx, edx; Val
0x14000ad11  mov     r8d, eax
0x14000ad14  mov     [rbp+57h+cchName], eax
0x14000ad17  add     r8, r8; Size
0x14000ad1a  mov     rcx, rbx; void *
0x14000ad1d  call    memset_0
0x14000ad22  xor     edi, edi
0x14000ad24  lea     r9, [rbp+57h+cchName]; lpcchName
0x14000ad28  mov     [rsp+0E0h+lpcValues], rdi; lpftLastWriteTime
0x14000ad2d  mov     r8, rbx; lpName
0x14000ad30  mov     [rsp+0E0h+lpcbMaxClassLen], rdi; lpcchClass
0x14000ad35  mov     edx, r12d; dwIndex
0x14000ad38  mov     [rsp+0E0h+lpcbMaxSubKeyLen], rdi; lpClass
0x14000ad3d  mov     rcx, r14; hKey
0x14000ad40  mov     [rsp+0E0h+ResultLength], rdi; lpReserved
0x14000ad45  call    cs:__imp_RegEnumKeyExW
0x14000ad4c  nop     dword ptr [rax+rax+00h]
0x14000ad51  test    eax, eax
0x14000ad53  jnz     loc_14000ADF8
0x14000ad59  mov     rdx, [rbp+57h+var_58]
0x14000ad5d  mov     r8d, r13d
0x14000ad60  mov     rcx, r15
0x14000ad63  call    StringCopyW
0x14000ad68  mov     r8d, r13d
0x14000ad6b  lea     rdx, asc_14001181C; "\\"
0x14000ad72  mov     rcx, r15
0x14000ad75  call    StringConcatW
0x14000ad7a  mov     r8d, r13d
0x14000ad7d  mov     rdx, rbx
0x14000ad80  mov     rcx, r15
0x14000ad83  call    StringConcatW
0x14000ad88  mov     r9d, [rsi+8Ch]
0x14000ad8f  lea     rax, [rbp+57h+hKey]
0x14000ad93  xor     r8d, r8d; ulOptions
0x14000ad96  mov     [rsp+0E0h+ResultLength], rax; phkResult
0x14000ad9b  cmp     dword ptr [rsi+88h], 1
0x14000ada2  mov     rdx, rbx; lpSubKey
0x14000ada5  mov     rcx, r14; hKey
0x14000ada8  jnz     short loc_14000ADB3
0x14000adaa  or      r9d, 0F003Fh
0x14000adb1  jmp     short loc_14000ADBA
0x14000adb3  or      r9d, 20019h; samDesired
0x14000adba  call    cs:__imp_RegOpenKeyExW
0x14000adc1  nop     dword ptr [rax+rax+00h]
0x14000adc6  test    eax, eax
0x14000adc8  jnz     short loc_14000ADF8
0x14000adca  mov     rcx, [rbp+57h+hKey]
0x14000adce  mov     r8, rsi
0x14000add1  mov     rdx, r15
0x14000add4  call    QuerySetFlags
0x14000add9  mov     rcx, [rbp+57h+hKey]; hKey
0x14000addd  mov     edi, eax
0x14000addf  test    rcx, rcx
0x14000ade2  jz      short loc_14000ADF8
0x14000ade4  call    cs:__imp_RegCloseKey
0x14000adeb  nop     dword ptr [rax+rax+00h]
0x14000adf0  mov     [rbp+57h+hKey], 0
0x14000adf8  inc     r12d
0x14000adfb  cmp     r12d, [rbp+57h+cSubKeys]
0x14000adff  jb      loc_14000AD0C
0x14000ae05  lea     rcx, [rbp+57h+var_60]
0x14000ae09  call    FreeMemory
0x14000ae0e  lea     rcx, [rbp+57h+var_50]
0x14000ae12  call    FreeMemory
0x14000ae17  mov     eax, edi
0x14000ae19  jmp     short loc_14000AE29
0x14000ae1b  mov     ebx, 57h ; 'W'
0x14000ae20  mov     ecx, ebx
0x14000ae22  call    SaveErrorMessage
0x14000ae27  mov     eax, ebx
0x14000ae29  mov     rcx, [rbp+57h+var_38]
0x14000ae2d  xor     rcx, rsp; StackCookie
0x14000ae30  call    __security_check_cookie
0x14000ae35  mov     rbx, [rsp+0E0h+arg_18]
0x14000ae3d  add     rsp, 0B0h
0x14000ae44  pop     r15
0x14000ae46  pop     r14
0x14000ae48  pop     r13
0x14000ae4a  pop     r12
0x14000ae4c  pop     rdi
0x14000ae4d  pop     rsi
0x14000ae4e  pop     rbp
0x14000ae4f  retn
```
