# RegSetKeySecurityInfo

- ea: `0x18008e89c`
- end: `0x18008ebdd`
- name: `RegSetKeySecurityInfo`
- size: `833`
- prototype: `__int64 __fastcall(LPCSTR lpSubKey, __int64)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180089e30`

## callees

- `0x1800022a0`
- `0x180005e34`
- `0x18005cd78`
- `0x18005dec8`
- `0x18008e89c`
- `0x1800e7206`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetKeySecurity` at `0x18008eb3d`
- `api-ms-win-core-registry-l1-1-0!RegSetKeySecurity` at `0x18008eb3d`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExA` at `0x18008e906`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExA` at `0x18008e906`
- `api-ms-win-core-registry-l1-1-0!RegGetKeySecurity` at `0x18008e971`
- `api-ms-win-core-registry-l1-1-0!RegGetKeySecurity` at `0x18008e9a8`
- `api-ms-win-core-registry-l1-1-0!RegGetKeySecurity` at `0x18008e971`
- `api-ms-win-core-registry-l1-1-0!RegGetKeySecurity` at `0x18008e9a8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18008eb98`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18008eb98`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x18008e986`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x18008ea96`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x18008e986`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x18008ea96`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18008ea68`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18008ea76`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18008eb52`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18008eba6`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18008ebb9`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18008ea68`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18008ea76`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18008eb52`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18008eba6`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18008ebb9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18008eb49`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18008eb49`
- `api-ms-win-security-sddl-l1-1-0!ConvertSecurityDescriptorToStringSecurityDescriptorW` at `0x18008ea1a`
- `api-ms-win-security-sddl-l1-1-0!ConvertSecurityDescriptorToStringSecurityDescriptorW` at `0x18008ea1a`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18008eb26`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18008eb26`

## pseudocode

```c
__int64 __fastcall RegSetKeySecurityInfo(LPCSTR lpSubKey, __int64 a2)
{
  unsigned int v2; // eax
  unsigned int v3; // ebx
  void *v5; // rsi
  HGLOBAL v6; // rax
  unsigned int KeySecurity; // edi
  const WCHAR *v8; // rbx
  char *v9; // r14
  const char *v10; // rax
  int v11; // r15d
  char *v12; // rbx
  size_t v13; // r14
  wchar_t *v14; // rax
  wchar_t *v15; // rbx
  struct _LIST_ENTRY *v16; // rax
  __int64 v17; // rdx
  STRSAFE_LPWSTR *v18; // r9
  STRSAFE_LPWSTR *v19; // r9
  size_t *dwOptions; // [rsp+20h] [rbp-40h]
  size_t *dwOptionsa; // [rsp+20h] [rbp-40h]
  LPWSTR StringSecurityDescriptor; // [rsp+50h] [rbp-10h] BYREF
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+58h] [rbp-8h] BYREF
  DWORD cbSecurityDescriptor; // [rsp+90h] [rbp+30h] BYREF
  ULONG StringSecurityDescriptorLen; // [rsp+A0h] [rbp+40h] BYREF
  HKEY hKey; // [rsp+A8h] [rbp+48h] BYREF

  if ( !lpSubKey || a2 != -2147483645 )
    return 87;
  hKey = 0;
  v2 = RegCreateKeyExA(HKEY_USERS, lpSubKey, 0, 0, 0, 0xF023Fu, 0, &hKey, 0);
  v3 = v2;
  if ( !v2 )
  {
    v5 = 0;
    SecurityDescriptor = 0;
    cbSecurityDescriptor = 0;
    if ( RegGetKeySecurity(hKey, 4u, 0, &cbSecurityDescriptor) == 122
      && (v6 = GlobalAlloc(0x40u, cbSecurityDescriptor), (v5 = v6) != 0) )
    {
      KeySecurity = RegGetKeySecurity(hKey, 4u, v6, &cbSecurityDescriptor);
      if ( KeySecurity )
      {
        if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
          && SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0
          && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
        {
          WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 132, WPP_1a2c25c73f1633f64777688c8bb98551_Traceguids, KeySecurity);
        }
        return KeySecurity;
      }
      StringSecurityDescriptorLen = 0;
      StringSecurityDescriptor = 0;
      if ( !ConvertSecurityDescriptorToStringSecurityDescriptorW(
              v5,
              1u,
              4u,
              &StringSecurityDescriptor,
              &StringSecurityDescriptorLen) )
        goto LABEL_38;
      v8 = StringSecurityDescriptor;
      v9 = (char *)StrdupWtoA(
                     L"(A;CI;KA;;;S-1-15-3-1024-1068037383-729401668-2768096886-125909118-1680096985-174794564-3112554050-3241210738)");
      v10 = (const char *)StrdupWtoA(v8);
      v11 = 0;
      v12 = (char *)v10;
      if ( v9 )
      {
        if ( v10 )
          LOBYTE(v11) = strstr_0(v10, v9) != 0;
        GlobalFree(v9);
      }
      if ( v12 )
        GlobalFree(v12);
      if ( v11 )
        goto LABEL_38;
      v13 = StringSecurityDescriptorLen + 111;
      v14 = (wchar_t *)GlobalAlloc(0x40u, 2 * v13);
      v15 = v14;
      if ( v14 )
      {
        memset_0(v14, 0, v13);
        StringCchCatExW(v15, v13, StringSecurityDescriptor, v18, dwOptions, 0x100u);
        StringCchCatExW(
          v15,
          v13,
          L"(A;CI;KA;;;S-1-15-3-1024-1068037383-729401668-2768096886-125909118-1680096985-174794564-3112554050-3241210738)",
          v19,
          dwOptionsa,
          0x100u);
        if ( ConvertStringSecurityDescriptorToSecurityDescriptorW(v15, 1u, &SecurityDescriptor, 0) )
        {
          KeySecurity = RegSetKeySecurity(hKey, 4u, SecurityDescriptor);
          LocalFree(SecurityDescriptor);
        }
        GlobalFree(v15);
        goto LABEL_38;
      }
      KeySecurity = 8;
      v16 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        || SBYTE4(WPP_GLOBAL_Control[1].Blink) >= 0
        || BYTE1(WPP_GLOBAL_Control[1].Blink) < 2u )
      {
LABEL_38:
        RegCloseKey(hKey);
        if ( v5 )
          GlobalFree(v5);
        if ( StringSecurityDescriptor )
          GlobalFree(StringSecurityDescriptor);
        return KeySecurity;
      }
      v17 = 133;
    }
    else
    {
      v16 = WPP_GLOBAL_Control;
      KeySecurity = 8;
      if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        || SBYTE4(WPP_GLOBAL_Control[1].Blink) >= 0
        || BYTE1(WPP_GLOBAL_Control[1].Blink) < 2u )
      {
        goto LABEL_38;
      }
      v17 = 131;
    }
    WPP_SF_d(v16[1].Flink, v17, WPP_1a2c25c73f1633f64777688c8bb98551_Traceguids, 8);
    goto LABEL_38;
  }
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0
    && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 5u )
  {
    WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 130, WPP_1a2c25c73f1633f64777688c8bb98551_Traceguids, v2);
  }
  return v3;
}

```

## disassembly

```asm
0x18008e89c  mov     r11, rsp
0x18008e89f  mov     [r11+10h], rbx
0x18008e8a3  push    rbp
0x18008e8a4  push    rsi
0x18008e8a5  push    rdi
0x18008e8a6  push    r14
0x18008e8a8  push    r15
0x18008e8aa  mov     rbp, rsp
0x18008e8ad  sub     rsp, 60h
0x18008e8b1  test    rcx, rcx
0x18008e8b4  jz      loc_18008EBC4
0x18008e8ba  mov     r10, 0FFFFFFFF80000003h
0x18008e8c1  cmp     rdx, r10
0x18008e8c4  jnz     loc_18008EBC4
0x18008e8ca  mov     qword ptr [r11-48h], 0
0x18008e8d2  lea     rax, [rbp+hKey]
0x18008e8d6  mov     [r11-50h], rax
0x18008e8da  mov     rdx, rcx; lpSubKey
0x18008e8dd  mov     qword ptr [r11-58h], 0
0x18008e8e5  xor     r9d, r9d; lpClass
0x18008e8e8  mov     [rsp+60h+samDesired], 0F023Fh; samDesired
0x18008e8f0  xor     r8d, r8d; Reserved
0x18008e8f3  mov     rcx, r10; hKey
0x18008e8f6  mov     [rsp+60h+dwOptions], 0; dwOptions
0x18008e8fe  mov     [rbp+hKey], 0
0x18008e906  call    cs:__imp_RegCreateKeyExA
0x18008e90c  mov     ebx, eax
0x18008e90e  test    eax, eax
0x18008e910  jz      short loc_18008E952
0x18008e912  mov     r10, cs:WPP_GLOBAL_Control
0x18008e919  lea     rcx, WPP_GLOBAL_Control
0x18008e920  cmp     r10, rcx
0x18008e923  jz      short loc_18008E94B
0x18008e925  test    byte ptr [r10+1Ch], 80h
0x18008e92a  jz      short loc_18008E94B
0x18008e92c  cmp     byte ptr [r10+19h], 5
0x18008e931  jb      short loc_18008E94B
0x18008e933  mov     rcx, [r10+10h]
0x18008e937  lea     r8, WPP_1a2c25c73f1633f64777688c8bb98551_Traceguids
0x18008e93e  mov     edx, 82h
0x18008e943  mov     r9d, eax
0x18008e946  call    WPP_SF_d
0x18008e94b  mov     eax, ebx
0x18008e94d  jmp     loc_18008EBC9
0x18008e952  mov     rcx, [rbp+hKey]; hKey
0x18008e956  lea     r9, [rbp+cbSecurityDescriptor]; lpcbSecurityDescriptor
0x18008e95a  xor     esi, esi
0x18008e95c  mov     [rbp+SecurityDescriptor], 0
0x18008e964  xor     r8d, r8d; pSecurityDescriptor
0x18008e967  mov     [rbp+cbSecurityDescriptor], 0
0x18008e96e  lea     edx, [rsi+4]; SecurityInformation
0x18008e971  call    cs:__imp_RegGetKeySecurity
0x18008e977  cmp     eax, 7Ah ; 'z'
0x18008e97a  jnz     loc_18008EB5A
0x18008e980  mov     edx, [rbp+cbSecurityDescriptor]; dwBytes
0x18008e983  lea     ecx, [rsi+40h]; uFlags
0x18008e986  call    cs:__imp_GlobalAlloc
0x18008e98c  mov     rsi, rax
0x18008e98f  test    rax, rax
0x18008e992  jz      loc_18008EB5A
0x18008e998  mov     rcx, [rbp+hKey]; hKey
0x18008e99c  lea     r9, [rbp+cbSecurityDescriptor]; lpcbSecurityDescriptor
0x18008e9a0  mov     r8, rax; pSecurityDescriptor
0x18008e9a3  mov     edx, 4; SecurityInformation
0x18008e9a8  call    cs:__imp_RegGetKeySecurity
0x18008e9ae  mov     edi, eax
0x18008e9b0  test    eax, eax
0x18008e9b2  jz      short loc_18008E9F2
0x18008e9b4  mov     rax, cs:WPP_GLOBAL_Control
0x18008e9bb  lea     rcx, WPP_GLOBAL_Control
0x18008e9c2  cmp     rax, rcx
0x18008e9c5  jz      short loc_18008E9EB
0x18008e9c7  test    byte ptr [rax+1Ch], 80h
0x18008e9cb  jz      short loc_18008E9EB
0x18008e9cd  cmp     byte ptr [rax+19h], 2
0x18008e9d1  jb      short loc_18008E9EB
0x18008e9d3  mov     rcx, [rax+10h]
0x18008e9d7  lea     r8, WPP_1a2c25c73f1633f64777688c8bb98551_Traceguids
0x18008e9de  mov     edx, 84h
0x18008e9e3  mov     r9d, edi
0x18008e9e6  call    WPP_SF_d
0x18008e9eb  mov     eax, edi
0x18008e9ed  jmp     loc_18008EBC9
0x18008e9f2  mov     edx, 1; RequestedStringSDRevision
0x18008e9f7  mov     [rbp+StringSecurityDescriptorLen], 0
0x18008e9fe  lea     rax, [rbp+StringSecurityDescriptorLen]
0x18008ea02  mov     [rbp+StringSecurityDescriptor], 0
0x18008ea0a  lea     r9, [rbp+StringSecurityDescriptor]; StringSecurityDescriptor
0x18008ea0e  mov     qword ptr [rsp+60h+dwOptions], rax; pcchRemaining
0x18008ea13  mov     rcx, rsi; SecurityDescriptor
0x18008ea16  lea     r8d, [rdx+3]; SecurityInformation
0x18008ea1a  call    cs:__imp_ConvertSecurityDescriptorToStringSecurityDescriptorW
0x18008ea20  test    eax, eax
0x18008ea22  jz      loc_18008EB94
0x18008ea28  mov     rbx, [rbp+StringSecurityDescriptor]
0x18008ea2c  lea     rcx, aACiKaS11531024; "(A;CI;KA;;;S-1-15-3-1024-1068037383-729"...
0x18008ea33  call    _StrdupWtoA
0x18008ea38  mov     rcx, rbx; lpWideCharStr
0x18008ea3b  mov     r14, rax
0x18008ea3e  call    _StrdupWtoA
0x18008ea43  xor     r15d, r15d
0x18008ea46  mov     rbx, rax
0x18008ea49  test    r14, r14
0x18008ea4c  jz      short loc_18008EA6E
0x18008ea4e  test    rax, rax
0x18008ea51  jz      short loc_18008EA65
0x18008ea53  mov     rdx, r14; SubStr
0x18008ea56  mov     rcx, rax; Str
0x18008ea59  call    strstr_0
0x18008ea5e  test    rax, rax
0x18008ea61  setnz   r15b
0x18008ea65  mov     rcx, r14; hMem
0x18008ea68  call    cs:__imp_GlobalFree
0x18008ea6e  test    rbx, rbx
0x18008ea71  jz      short loc_18008EA7C
0x18008ea73  mov     rcx, rbx; hMem
0x18008ea76  call    cs:__imp_GlobalFree
0x18008ea7c  test    r15d, r15d
0x18008ea7f  jnz     loc_18008EB94
0x18008ea85  mov     eax, [rbp+StringSecurityDescriptorLen]
0x18008ea88  lea     ecx, [r15+40h]; uFlags
0x18008ea8c  add     eax, 6Fh ; 'o'
0x18008ea8f  mov     r14d, eax
0x18008ea92  lea     rdx, [rax+rax]; dwBytes
0x18008ea96  call    cs:__imp_GlobalAlloc
0x18008ea9c  mov     rbx, rax
0x18008ea9f  test    rax, rax
0x18008eaa2  jnz     short loc_18008EADA
0x18008eaa4  lea     edi, [rax+8]
0x18008eaa7  mov     rax, cs:WPP_GLOBAL_Control
0x18008eaae  lea     rcx, WPP_GLOBAL_Control
0x18008eab5  cmp     rax, rcx
0x18008eab8  jz      loc_18008EB94
0x18008eabe  test    byte ptr [rax+1Ch], 80h
0x18008eac2  jz      loc_18008EB94
0x18008eac8  cmp     byte ptr [rax+19h], 2
0x18008eacc  jb      loc_18008EB94
0x18008ead2  lea     edx, [rdi+7Dh]
0x18008ead5  jmp     loc_18008EB81
0x18008eada  mov     r8, r14; Size
0x18008eadd  xor     edx, edx; Val
0x18008eadf  mov     rcx, rbx; void *
0x18008eae2  call    memset_0
0x18008eae7  mov     r8, [rbp+StringSecurityDescriptor]; pszSrc
0x18008eaeb  mov     r15d, 100h
0x18008eaf1  mov     rdx, r14; cchDest
0x18008eaf4  mov     [rsp+60h+samDesired], r15d; dwFlags
0x18008eaf9  mov     rcx, rbx; pszDest
0x18008eafc  call    StringCchCatExW
0x18008eb01  lea     r8, aACiKaS11531024; "(A;CI;KA;;;S-1-15-3-1024-1068037383-729"...
0x18008eb08  mov     [rsp+60h+samDesired], r15d; dwFlags
0x18008eb0d  mov     rdx, r14; cchDest
0x18008eb10  mov     rcx, rbx; pszDest
0x18008eb13  call    StringCchCatExW
0x18008eb18  xor     r9d, r9d; SecurityDescriptorSize
0x18008eb1b  lea     r8, [rbp+SecurityDescriptor]; SecurityDescriptor
0x18008eb1f  mov     rcx, rbx; StringSecurityDescriptor
0x18008eb22  lea     edx, [r9+1]; StringSDRevision
0x18008eb26  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x18008eb2c  test    eax, eax
0x18008eb2e  jz      short loc_18008EB4F
0x18008eb30  mov     r8, [rbp+SecurityDescriptor]; pSecurityDescriptor
0x18008eb34  mov     edx, 4; SecurityInformation
0x18008eb39  mov     rcx, [rbp+hKey]; hKey
0x18008eb3d  call    cs:__imp_RegSetKeySecurity
0x18008eb43  mov     rcx, [rbp+SecurityDescriptor]; hMem
0x18008eb47  mov     edi, eax
0x18008eb49  call    cs:__imp_LocalFree
0x18008eb4f  mov     rcx, rbx; hMem
0x18008eb52  call    cs:__imp_GlobalFree
0x18008eb58  jmp     short loc_18008EB94
0x18008eb5a  mov     rax, cs:WPP_GLOBAL_Control
0x18008eb61  lea     rcx, WPP_GLOBAL_Control
0x18008eb68  mov     edi, 8
0x18008eb6d  cmp     rax, rcx
0x18008eb70  jz      short loc_18008EB94
0x18008eb72  test    byte ptr [rax+1Ch], 80h
0x18008eb76  jz      short loc_18008EB94
0x18008eb78  cmp     byte ptr [rax+19h], 2
0x18008eb7c  jb      short loc_18008EB94
0x18008eb7e  lea     edx, [rdi+7Bh]
0x18008eb81  mov     rcx, [rax+10h]
0x18008eb85  lea     r8, WPP_1a2c25c73f1633f64777688c8bb98551_Traceguids
0x18008eb8c  mov     r9d, edi
0x18008eb8f  call    WPP_SF_d
0x18008eb94  mov     rcx, [rbp+hKey]; hKey
0x18008eb98  call    cs:__imp_RegCloseKey
0x18008eb9e  test    rsi, rsi
0x18008eba1  jz      short loc_18008EBAC
0x18008eba3  mov     rcx, rsi; hMem
0x18008eba6  call    cs:__imp_GlobalFree
0x18008ebac  mov     rcx, [rbp+StringSecurityDescriptor]; hMem
0x18008ebb0  test    rcx, rcx
0x18008ebb3  jz      loc_18008E9EB
0x18008ebb9  call    cs:__imp_GlobalFree
0x18008ebbf  jmp     loc_18008E9EB
0x18008ebc4  mov     eax, 57h ; 'W'
0x18008ebc9  mov     rbx, [rsp+60h+arg_8]
0x18008ebd1  add     rsp, 60h
0x18008ebd5  pop     r15
0x18008ebd7  pop     r14
0x18008ebd9  pop     rdi
0x18008ebda  pop     rsi
0x18008ebdb  pop     rbp
0x18008ebdc  retn
```
