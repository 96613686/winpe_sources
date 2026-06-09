# SaveScpGUIDToRegistry

- ea: `0x18007bc7c`
- end: `0x18007bf35`
- name: `SaveScpGUIDToRegistry`
- size: `697`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x18007c0e0`

## callees

- `0x180005665`
- `0x18001aea4`
- `0x18007aaf8`
- `0x18007bc7c`
- `0x1800a0fb0`
- `0x1800a1070`
- `0x1800a5010`

## import_xrefs

- `msvcrt!wcsncpy_s` at `0x18007bd35`
- `msvcrt!wcsncpy_s` at `0x18007bd35`
- `msvcrt!wcsncat_s` at `0x18007bd6a`
- `msvcrt!wcsncat_s` at `0x18007bd9d`
- `msvcrt!wcsncat_s` at `0x18007bd6a`
- `msvcrt!wcsncat_s` at `0x18007bd9d`
- `ADVAPI32!RegSetValueExW` at `0x18007be8e`
- `ADVAPI32!RegSetValueExW` at `0x18007be8e`
- `ADVAPI32!RegCreateKeyExW` at `0x18007be0b`
- `ADVAPI32!RegCreateKeyExW` at `0x18007be0b`
- `ADVAPI32!RegCloseKey` at `0x18007beec`
- `ADVAPI32!RegCloseKey` at `0x18007beec`
- `ADVAPI32!RegDeleteKeyW` at `0x18007bdc9`
- `ADVAPI32!RegDeleteKeyW` at `0x18007bdc9`
- `OLEAUT32!__imp_SysFreeString` at `0x18007befe`
- `OLEAUT32!__imp_SysFreeString` at `0x18007befe`

## string_xrefs

- `0x18007be51`: `"RegCreateKeyEx"`
- `0x18007bec7`: `"RegSetValueEx"`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall SaveScpGUIDToRegistry(__int64 a1, __int64 a2)
{
  signed int v3; // ebx
  _QWORD *v4; // rcx
  int v5; // edx
  const wchar_t *v6; // r9
  __int64 v7; // rdi
  __int64 v8; // rax
  __int64 v9; // rax
  LSTATUS v10; // eax
  LSTATUS v11; // eax
  DWORD dwDisposition; // [rsp+50h] [rbp-B0h] BYREF
  HKEY hKey; // [rsp+58h] [rbp-A8h] BYREF
  wchar_t *Source; // [rsp+60h] [rbp-A0h] BYREF
  wchar_t Destination[1024]; // [rsp+70h] [rbp-90h] BYREF
  WCHAR SubKey[1024]; // [rsp+870h] [rbp+770h] BYREF

  Source = 0;
  hKey = 0;
  dwDisposition = 0;
  v3 = (*(__int64 (__fastcall **)(__int64, wchar_t **))(*(_QWORD *)a1 + 72LL))(a1, &Source);
  if ( v3 >= 0 )
  {
    memset_0(Destination, 0, sizeof(Destination));
    wcsncpy_s(Destination, 0x400u, L"LDAP://<GUID=", 0x400u);
    v7 = -1;
    v8 = -1;
    do
      ++v8;
    while ( Destination[v8] );
    wcsncat_s(Destination, 0x400u, Source, 1024 - v8);
    v9 = -1;
    do
      ++v9;
    while ( Destination[v9] );
    wcsncat_s(Destination, 0x400u, L">", 1024 - v9);
    GetScpGUIDRegistryKeyPath(a2, SubKey);
    RegDeleteKeyW(HKEY_LOCAL_MACHINE, SubKey);
    v10 = RegCreateKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 0, 0, 0xF003Fu, 0, &hKey, &dwDisposition);
    v3 = v10;
    if ( v10 > 0 )
      v3 = (unsigned __int16)v10 | 0x80070000;
    if ( v3 >= 0 )
    {
      do
        ++v7;
      while ( Destination[v7] );
      v11 = RegSetValueExW(hKey, L"GUIDBindingString", 0, 1u, (const BYTE *)Destination, 2 * v7);
      v3 = v11;
      if ( v11 > 0 )
        v3 = (unsigned __int16)v11 | 0x80070000;
      if ( v3 < 0 )
      {
        v4 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v5 = 83;
          v6 = L"\"RegSetValueEx\"";
          goto LABEL_22;
        }
      }
    }
    else
    {
      v4 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v5 = 82;
        v6 = L"\"RegCreateKeyEx\"";
        goto LABEL_22;
      }
    }
  }
  else
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v5 = 81;
      v6 = L"\"pIADsSCP->get_GUID\"";
LABEL_22:
      WPP_SF_SD(v4[2], v5, (unsigned int)WPP_4a9851e82e14323852e4e238f8b1a374_Traceguids, (_DWORD)v6, v3);
    }
  }
  if ( hKey )
    RegCloseKey(hKey);
  SysFreeString(Source);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x18007bc7c  mov     [rsp-8+arg_10], rbx
0x18007bc81  mov     [rsp-8+arg_18], rsi
0x18007bc86  push    rbp
0x18007bc87  push    rdi
0x18007bc88  push    r14
0x18007bc8a  lea     rbp, [rsp-0F80h]
0x18007bc92  mov     eax, 1080h
0x18007bc97  call    _alloca_probe
0x18007bc9c  sub     rsp, rax
0x18007bc9f  mov     rax, cs:__security_cookie
0x18007bca6  xor     rax, rsp
0x18007bca9  mov     [rbp+0F90h+var_20], rax
0x18007bcb0  mov     rsi, rdx
0x18007bcb3  xor     r14d, r14d
0x18007bcb6  mov     [rsp+1090h+Source], r14
0x18007bcbb  mov     [rsp+1090h+hKey], r14
0x18007bcc0  mov     [rsp+1090h+dwDisposition], r14d
0x18007bcc5  mov     rax, [rcx]
0x18007bcc8  lea     rdx, [rsp+1090h+Source]
0x18007bccd  mov     rax, [rax+48h]
0x18007bcd1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007bcd6  mov     ebx, eax
0x18007bcd8  test    eax, eax
0x18007bcda  jns     short loc_18007BD0D
0x18007bcdc  lea     rax, WPP_GLOBAL_Control
0x18007bce3  mov     rcx, cs:WPP_GLOBAL_Control
0x18007bcea  cmp     rcx, rax
0x18007bced  jz      loc_18007BEE2
0x18007bcf3  cmp     byte ptr [rcx+19h], 2
0x18007bcf7  jb      loc_18007BEE2
0x18007bcfd  lea     edx, [r14+51h]
0x18007bd01  lea     r9, aPiadsscpGetGui; "\"pIADsSCP->get_GUID\""
0x18007bd08  jmp     loc_18007BECE
0x18007bd0d  xor     edx, edx; Val
0x18007bd0f  mov     r8d, 800h; Size
0x18007bd15  lea     rcx, [rsp+1090h+Destination]; void *
0x18007bd1a  call    memset_0
0x18007bd1f  mov     ebx, 400h
0x18007bd24  mov     r9d, ebx; MaxCount
0x18007bd27  lea     r8, aLdapGuid; "LDAP://<GUID="
0x18007bd2e  mov     edx, ebx; SizeInWords
0x18007bd30  lea     rcx, [rsp+1090h+Destination]; Destination
0x18007bd35  call    cs:__imp_wcsncpy_s
0x18007bd3c  nop     dword ptr [rax+rax+00h]
0x18007bd41  lea     rcx, [rsp+1090h+Destination]
0x18007bd46  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18007bd4a  mov     rax, rdi
0x18007bd4d  inc     rax
0x18007bd50  cmp     [rcx+rax*2], r14w
0x18007bd55  jnz     short loc_18007BD4D
0x18007bd57  mov     r9, rbx
0x18007bd5a  sub     r9, rax; MaxCount
0x18007bd5d  mov     r8, [rsp+1090h+Source]; Source
0x18007bd62  mov     rdx, rbx; SizeInWords
0x18007bd65  lea     rcx, [rsp+1090h+Destination]; Destination
0x18007bd6a  call    cs:__imp_wcsncat_s
0x18007bd71  nop     dword ptr [rax+rax+00h]
0x18007bd76  lea     rcx, [rsp+1090h+Destination]
0x18007bd7b  mov     rax, rdi
0x18007bd7e  inc     rax
0x18007bd81  cmp     [rcx+rax*2], r14w
0x18007bd86  jnz     short loc_18007BD7E
0x18007bd88  mov     r9, rbx
0x18007bd8b  sub     r9, rax; MaxCount
0x18007bd8e  lea     r8, asc_1800BFB20; ">"
0x18007bd95  mov     rdx, rbx; SizeInWords
0x18007bd98  lea     rcx, [rsp+1090h+Destination]; Destination
0x18007bd9d  call    cs:__imp_wcsncat_s
0x18007bda4  nop     dword ptr [rax+rax+00h]
0x18007bda9  lea     rdx, [rbp+0F90h+SubKey]
0x18007bdb0  mov     rcx, rsi
0x18007bdb3  call    GetScpGUIDRegistryKeyPath
0x18007bdb8  lea     rdx, [rbp+0F90h+SubKey]; lpSubKey
0x18007bdbf  mov     rbx, 0FFFFFFFF80000002h
0x18007bdc6  mov     rcx, rbx; hKey
0x18007bdc9  call    cs:__imp_RegDeleteKeyW
0x18007bdd0  nop     dword ptr [rax+rax+00h]
0x18007bdd5  lea     rax, [rsp+1090h+dwDisposition]
0x18007bdda  mov     [rsp+1090h+lpdwDisposition], rax; lpdwDisposition
0x18007bddf  lea     rax, [rsp+1090h+hKey]
0x18007bde4  mov     [rsp+1090h+phkResult], rax; phkResult
0x18007bde9  mov     [rsp+1090h+lpSecurityAttributes], r14; lpSecurityAttributes
0x18007bdee  mov     [rsp+1090h+samDesired], 0F003Fh; samDesired
0x18007bdf6  mov     [rsp+1090h+dwOptions], r14d; dwOptions
0x18007bdfb  xor     r9d, r9d; lpClass
0x18007bdfe  xor     r8d, r8d; Reserved
0x18007be01  lea     rdx, [rbp+0F90h+SubKey]; lpSubKey
0x18007be08  mov     rcx, rbx; hKey
0x18007be0b  call    cs:__imp_RegCreateKeyExW
0x18007be12  nop     dword ptr [rax+rax+00h]
0x18007be17  mov     ebx, eax
0x18007be19  mov     esi, 80070000h
0x18007be1e  test    eax, eax
0x18007be20  jle     short loc_18007BE27
0x18007be22  movzx   ebx, ax
0x18007be25  or      ebx, esi
0x18007be27  test    ebx, ebx
0x18007be29  jns     short loc_18007BE5A
0x18007be2b  lea     rax, WPP_GLOBAL_Control
0x18007be32  mov     rcx, cs:WPP_GLOBAL_Control
0x18007be39  cmp     rcx, rax
0x18007be3c  jz      loc_18007BEE2
0x18007be42  cmp     byte ptr [rcx+19h], 2
0x18007be46  jb      loc_18007BEE2
0x18007be4c  mov     edx, 52h ; 'R'
0x18007be51  lea     r9, aRegcreatekeyex; "\"RegCreateKeyEx\""
0x18007be58  jmp     short loc_18007BECE
0x18007be5a  lea     rax, [rsp+1090h+Destination]
0x18007be5f  inc     rdi
0x18007be62  cmp     [rax+rdi*2], r14w
0x18007be67  jnz     short loc_18007BE5F
0x18007be69  add     edi, edi
0x18007be6b  mov     [rsp+1090h+samDesired], edi; cbData
0x18007be6f  lea     rax, [rsp+1090h+Destination]
0x18007be74  mov     qword ptr [rsp+1090h+dwOptions], rax; lpData
0x18007be79  mov     r9d, 1; dwType
0x18007be7f  xor     r8d, r8d; Reserved
0x18007be82  lea     rdx, aGuidbindingstr; "GUIDBindingString"
0x18007be89  mov     rcx, [rsp+1090h+hKey]; hKey
0x18007be8e  call    cs:__imp_RegSetValueExW
0x18007be95  nop     dword ptr [rax+rax+00h]
0x18007be9a  mov     ebx, eax
0x18007be9c  test    eax, eax
0x18007be9e  jle     short loc_18007BEA5
0x18007bea0  movzx   ebx, ax
0x18007bea3  or      ebx, esi
0x18007bea5  test    ebx, ebx
0x18007bea7  jns     short loc_18007BEE2
0x18007bea9  lea     rax, WPP_GLOBAL_Control
0x18007beb0  mov     rcx, cs:WPP_GLOBAL_Control
0x18007beb7  cmp     rcx, rax
0x18007beba  jz      short loc_18007BEE2
0x18007bebc  cmp     byte ptr [rcx+19h], 2
0x18007bec0  jb      short loc_18007BEE2
0x18007bec2  mov     edx, 53h ; 'S'
0x18007bec7  lea     r9, aRegsetvalueex; "\"RegSetValueEx\""
0x18007bece  mov     [rsp+1090h+dwOptions], ebx
0x18007bed2  lea     r8, WPP_4a9851e82e14323852e4e238f8b1a374_Traceguids
0x18007bed9  mov     rcx, [rcx+10h]
0x18007bedd  call    WPP_SF_SD
0x18007bee2  mov     rcx, [rsp+1090h+hKey]; hKey
0x18007bee7  test    rcx, rcx
0x18007beea  jz      short loc_18007BEF9
0x18007beec  call    cs:__imp_RegCloseKey
0x18007bef3  nop     dword ptr [rax+rax+00h]
0x18007bef8  nop
0x18007bef9  mov     rcx, [rsp+1090h+Source]; bstrString
0x18007befe  call    cs:__imp_SysFreeString
0x18007bf05  nop     dword ptr [rax+rax+00h]
0x18007bf0a  nop
0x18007bf0b  mov     eax, ebx
0x18007bf0d  mov     rcx, [rbp+0F90h+var_20]
0x18007bf14  xor     rcx, rsp; StackCookie
0x18007bf17  call    __security_check_cookie
0x18007bf1c  lea     r11, [rsp+1090h+var_10]
0x18007bf24  mov     rbx, [r11+30h]
0x18007bf28  mov     rsi, [r11+38h]
0x18007bf2c  mov     rsp, r11
0x18007bf2f  pop     r14
0x18007bf31  pop     rdi
0x18007bf32  pop     rbp
0x18007bf33  retn
```
