# RegSetKeySecurityInfo

- ea: `0x1800dcbd4`
- end: `0x1800dcefd`
- name: `RegSetKeySecurityInfo`
- size: `809`
- prototype: `__int64 __fastcall(LPCSTR lpSubKey)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180040a68`

## callees

- `0x18000b0f4`
- `0x18000dde0`
- `0x180015f3c`
- `0x18004e580`
- `0x180063e9c`
- `0x1800dcbd4`
- `0x1800ded06`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetKeySecurity` at `0x1800dce6e`
- `api-ms-win-core-registry-l1-1-0!RegSetKeySecurity` at `0x1800dce6e`
- `api-ms-win-core-registry-l1-1-0!RegGetKeySecurity` at `0x1800dcca9`
- `api-ms-win-core-registry-l1-1-0!RegGetKeySecurity` at `0x1800dcce0`
- `api-ms-win-core-registry-l1-1-0!RegGetKeySecurity` at `0x1800dcca9`
- `api-ms-win-core-registry-l1-1-0!RegGetKeySecurity` at `0x1800dcce0`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExA` at `0x1800dcc3e`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExA` at `0x1800dcc3e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800dcec8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800dcec8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800dce7a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800dce7a`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x1800dccbe`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x1800dcdc7`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x1800dccbe`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x1800dcdc7`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1800dce57`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1800dce57`
- `api-ms-win-security-sddl-l1-1-0!ConvertSecurityDescriptorToStringSecurityDescriptorW` at `0x1800dcd52`
- `api-ms-win-security-sddl-l1-1-0!ConvertSecurityDescriptorToStringSecurityDescriptorW` at `0x1800dcd52`

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
  const char *v9; // r14
  const char *v10; // rax
  int v11; // r15d
  const char *v12; // rbx
  size_t v13; // r14
  wchar_t *v14; // rax
  wchar_t *v15; // rbx
  _QWORD *v16; // rax
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
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && *((char *)WPP_GLOBAL_Control + 28) < 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            132,
            WPP_1a2c25c73f1633f64777688c8bb98551_Traceguids,
            KeySecurity);
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
        goto LABEL_35;
      v8 = StringSecurityDescriptor;
      v9 = (const char *)StrdupWtoA(
                           L"(A;CI;KA;;;S-1-15-3-1024-1068037383-729401668-2768096886-125909118-1680096985-174794564-31125"
                            "54050-3241210738)");
      v10 = (const char *)StrdupWtoA(v8);
      v11 = 0;
      v12 = v10;
      if ( v9 && v10 )
        LOBYTE(v11) = strstr_0(v10, v9) != 0;
      Free0(v9);
      Free0(v12);
      if ( v11 )
        goto LABEL_35;
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
        Free0(v15);
        goto LABEL_35;
      }
      KeySecurity = 8;
      v16 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || *((char *)WPP_GLOBAL_Control + 28) >= 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
LABEL_35:
        RegCloseKey(hKey);
        Free0(v5);
        Free0(StringSecurityDescriptor);
        return KeySecurity;
      }
      v17 = 133;
    }
    else
    {
      v16 = WPP_GLOBAL_Control;
      KeySecurity = 8;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || *((char *)WPP_GLOBAL_Control + 28) >= 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_35;
      }
      v17 = 131;
    }
    WPP_SF_d(v16[2], v17, WPP_1a2c25c73f1633f64777688c8bb98551_Traceguids, 8);
    goto LABEL_35;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && *((char *)WPP_GLOBAL_Control + 28) < 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 130, WPP_1a2c25c73f1633f64777688c8bb98551_Traceguids, v2);
  }
  return v3;
}

```

## disassembly

```asm
0x1800dcbd4  mov     r11, rsp
0x1800dcbd7  mov     [r11+10h], rbx
0x1800dcbdb  push    rbp
0x1800dcbdc  push    rsi
0x1800dcbdd  push    rdi
0x1800dcbde  push    r14
0x1800dcbe0  push    r15
0x1800dcbe2  mov     rbp, rsp
0x1800dcbe5  sub     rsp, 60h
0x1800dcbe9  test    rcx, rcx
0x1800dcbec  jz      loc_1800DCEE4
0x1800dcbf2  mov     r10, 0FFFFFFFF80000003h
0x1800dcbf9  cmp     rdx, r10
0x1800dcbfc  jnz     loc_1800DCEE4
0x1800dcc02  mov     qword ptr [r11-48h], 0
0x1800dcc0a  lea     rax, [rbp+hKey]
0x1800dcc0e  mov     [r11-50h], rax
0x1800dcc12  mov     rdx, rcx; lpSubKey
0x1800dcc15  mov     qword ptr [r11-58h], 0
0x1800dcc1d  xor     r9d, r9d; lpClass
0x1800dcc20  mov     [rsp+60h+samDesired], 0F023Fh; samDesired
0x1800dcc28  xor     r8d, r8d; Reserved
0x1800dcc2b  mov     rcx, r10; hKey
0x1800dcc2e  mov     [rsp+60h+dwOptions], 0; dwOptions
0x1800dcc36  mov     [rbp+hKey], 0
0x1800dcc3e  call    cs:__imp_RegCreateKeyExA
0x1800dcc44  mov     ebx, eax
0x1800dcc46  test    eax, eax
0x1800dcc48  jz      short loc_1800DCC8A
0x1800dcc4a  mov     r10, cs:WPP_GLOBAL_Control
0x1800dcc51  lea     rcx, WPP_GLOBAL_Control
0x1800dcc58  cmp     r10, rcx
0x1800dcc5b  jz      short loc_1800DCC83
0x1800dcc5d  test    byte ptr [r10+1Ch], 80h
0x1800dcc62  jz      short loc_1800DCC83
0x1800dcc64  cmp     byte ptr [r10+19h], 5
0x1800dcc69  jb      short loc_1800DCC83
0x1800dcc6b  mov     rcx, [r10+10h]
0x1800dcc6f  lea     r8, WPP_1a2c25c73f1633f64777688c8bb98551_Traceguids
0x1800dcc76  mov     edx, 82h
0x1800dcc7b  mov     r9d, eax
0x1800dcc7e  call    WPP_SF_d
0x1800dcc83  mov     eax, ebx
0x1800dcc85  jmp     loc_1800DCEE9
0x1800dcc8a  mov     rcx, [rbp+hKey]; hKey
0x1800dcc8e  lea     r9, [rbp+cbSecurityDescriptor]; lpcbSecurityDescriptor
0x1800dcc92  xor     esi, esi
0x1800dcc94  mov     [rbp+SecurityDescriptor], 0
0x1800dcc9c  xor     r8d, r8d; pSecurityDescriptor
0x1800dcc9f  mov     [rbp+cbSecurityDescriptor], 0
0x1800dcca6  lea     edx, [rsi+4]; SecurityInformation
0x1800dcca9  call    cs:__imp_RegGetKeySecurity
0x1800dccaf  cmp     eax, 7Ah ; 'z'
0x1800dccb2  jnz     loc_1800DCE8A
0x1800dccb8  mov     edx, [rbp+cbSecurityDescriptor]; dwBytes
0x1800dccbb  lea     ecx, [rsi+40h]; uFlags
0x1800dccbe  call    cs:__imp_GlobalAlloc
0x1800dccc4  mov     rsi, rax
0x1800dccc7  test    rax, rax
0x1800dccca  jz      loc_1800DCE8A
0x1800dccd0  mov     rcx, [rbp+hKey]; hKey
0x1800dccd4  lea     r9, [rbp+cbSecurityDescriptor]; lpcbSecurityDescriptor
0x1800dccd8  mov     r8, rax; pSecurityDescriptor
0x1800dccdb  mov     edx, 4; SecurityInformation
0x1800dcce0  call    cs:__imp_RegGetKeySecurity
0x1800dcce6  mov     edi, eax
0x1800dcce8  test    eax, eax
0x1800dccea  jz      short loc_1800DCD2A
0x1800dccec  mov     rax, cs:WPP_GLOBAL_Control
0x1800dccf3  lea     rcx, WPP_GLOBAL_Control
0x1800dccfa  cmp     rax, rcx
0x1800dccfd  jz      short loc_1800DCD23
0x1800dccff  test    byte ptr [rax+1Ch], 80h
0x1800dcd03  jz      short loc_1800DCD23
0x1800dcd05  cmp     byte ptr [rax+19h], 2
0x1800dcd09  jb      short loc_1800DCD23
0x1800dcd0b  mov     rcx, [rax+10h]
0x1800dcd0f  lea     r8, WPP_1a2c25c73f1633f64777688c8bb98551_Traceguids
0x1800dcd16  mov     edx, 84h
0x1800dcd1b  mov     r9d, edi
0x1800dcd1e  call    WPP_SF_d
0x1800dcd23  mov     eax, edi
0x1800dcd25  jmp     loc_1800DCEE9
0x1800dcd2a  mov     edx, 1; RequestedStringSDRevision
0x1800dcd2f  mov     [rbp+StringSecurityDescriptorLen], 0
0x1800dcd36  lea     rax, [rbp+StringSecurityDescriptorLen]
0x1800dcd3a  mov     [rbp+StringSecurityDescriptor], 0
0x1800dcd42  lea     r9, [rbp+StringSecurityDescriptor]; StringSecurityDescriptor
0x1800dcd46  mov     qword ptr [rsp+60h+dwOptions], rax; pcchRemaining
0x1800dcd4b  mov     rcx, rsi; SecurityDescriptor
0x1800dcd4e  lea     r8d, [rdx+3]; SecurityInformation
0x1800dcd52  call    cs:__imp_ConvertSecurityDescriptorToStringSecurityDescriptorW
0x1800dcd58  test    eax, eax
0x1800dcd5a  jz      loc_1800DCEC4
0x1800dcd60  mov     rbx, [rbp+StringSecurityDescriptor]
0x1800dcd64  lea     rcx, aACiKaS11531024; "(A;CI;KA;;;S-1-15-3-1024-1068037383-729"...
0x1800dcd6b  call    _StrdupWtoA
0x1800dcd70  mov     rcx, rbx; lpWideCharStr
0x1800dcd73  mov     r14, rax
0x1800dcd76  call    _StrdupWtoA
0x1800dcd7b  xor     r15d, r15d
0x1800dcd7e  mov     rbx, rax
0x1800dcd81  test    r14, r14
0x1800dcd84  jz      short loc_1800DCD9D
0x1800dcd86  test    rax, rax
0x1800dcd89  jz      short loc_1800DCD9D
0x1800dcd8b  mov     rdx, r14; SubStr
0x1800dcd8e  mov     rcx, rax; Str
0x1800dcd91  call    strstr_0
0x1800dcd96  test    rax, rax
0x1800dcd99  setnz   r15b
0x1800dcd9d  mov     rcx, r14
0x1800dcda0  call    Free0
0x1800dcda5  mov     rcx, rbx
0x1800dcda8  call    Free0
0x1800dcdad  test    r15d, r15d
0x1800dcdb0  jnz     loc_1800DCEC4
0x1800dcdb6  mov     eax, [rbp+StringSecurityDescriptorLen]
0x1800dcdb9  lea     ecx, [r15+40h]; uFlags
0x1800dcdbd  add     eax, 6Fh ; 'o'
0x1800dcdc0  mov     r14d, eax
0x1800dcdc3  lea     rdx, [rax+rax]; dwBytes
0x1800dcdc7  call    cs:__imp_GlobalAlloc
0x1800dcdcd  mov     rbx, rax
0x1800dcdd0  test    rax, rax
0x1800dcdd3  jnz     short loc_1800DCE0B
0x1800dcdd5  lea     edi, [rax+8]
0x1800dcdd8  mov     rax, cs:WPP_GLOBAL_Control
0x1800dcddf  lea     rcx, WPP_GLOBAL_Control
0x1800dcde6  cmp     rax, rcx
0x1800dcde9  jz      loc_1800DCEC4
0x1800dcdef  test    byte ptr [rax+1Ch], 80h
0x1800dcdf3  jz      loc_1800DCEC4
0x1800dcdf9  cmp     byte ptr [rax+19h], 2
0x1800dcdfd  jb      loc_1800DCEC4
0x1800dce03  lea     edx, [rdi+7Dh]
0x1800dce06  jmp     loc_1800DCEB1
0x1800dce0b  mov     r8, r14; Size
0x1800dce0e  xor     edx, edx; Val
0x1800dce10  mov     rcx, rbx; void *
0x1800dce13  call    memset_0
0x1800dce18  mov     r8, [rbp+StringSecurityDescriptor]; pszSrc
0x1800dce1c  mov     r15d, 100h
0x1800dce22  mov     rdx, r14; cchDest
0x1800dce25  mov     [rsp+60h+samDesired], r15d; dwFlags
0x1800dce2a  mov     rcx, rbx; pszDest
0x1800dce2d  call    StringCchCatExW
0x1800dce32  lea     r8, aACiKaS11531024; "(A;CI;KA;;;S-1-15-3-1024-1068037383-729"...
0x1800dce39  mov     [rsp+60h+samDesired], r15d; dwFlags
0x1800dce3e  mov     rdx, r14; cchDest
0x1800dce41  mov     rcx, rbx; pszDest
0x1800dce44  call    StringCchCatExW
0x1800dce49  xor     r9d, r9d; SecurityDescriptorSize
0x1800dce4c  lea     r8, [rbp+SecurityDescriptor]; SecurityDescriptor
0x1800dce50  mov     rcx, rbx; StringSecurityDescriptor
0x1800dce53  lea     edx, [r9+1]; StringSDRevision
0x1800dce57  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x1800dce5d  test    eax, eax
0x1800dce5f  jz      short loc_1800DCE80
0x1800dce61  mov     r8, [rbp+SecurityDescriptor]; pSecurityDescriptor
0x1800dce65  mov     edx, 4; SecurityInformation
0x1800dce6a  mov     rcx, [rbp+hKey]; hKey
0x1800dce6e  call    cs:__imp_RegSetKeySecurity
0x1800dce74  mov     rcx, [rbp+SecurityDescriptor]; hMem
0x1800dce78  mov     edi, eax
0x1800dce7a  call    cs:__imp_LocalFree
0x1800dce80  mov     rcx, rbx
0x1800dce83  call    Free0
0x1800dce88  jmp     short loc_1800DCEC4
0x1800dce8a  mov     rax, cs:WPP_GLOBAL_Control
0x1800dce91  lea     rcx, WPP_GLOBAL_Control
0x1800dce98  mov     edi, 8
0x1800dce9d  cmp     rax, rcx
0x1800dcea0  jz      short loc_1800DCEC4
0x1800dcea2  test    byte ptr [rax+1Ch], 80h
0x1800dcea6  jz      short loc_1800DCEC4
0x1800dcea8  cmp     byte ptr [rax+19h], 2
0x1800dceac  jb      short loc_1800DCEC4
0x1800dceae  lea     edx, [rdi+7Bh]
0x1800dceb1  mov     rcx, [rax+10h]
0x1800dceb5  lea     r8, WPP_1a2c25c73f1633f64777688c8bb98551_Traceguids
0x1800dcebc  mov     r9d, edi
0x1800dcebf  call    WPP_SF_d
0x1800dcec4  mov     rcx, [rbp+hKey]; hKey
0x1800dcec8  call    cs:__imp_RegCloseKey
0x1800dcece  mov     rcx, rsi
0x1800dced1  call    Free0
0x1800dced6  mov     rcx, [rbp+StringSecurityDescriptor]
0x1800dceda  call    Free0
0x1800dcedf  jmp     loc_1800DCD23
0x1800dcee4  mov     eax, 57h ; 'W'
0x1800dcee9  mov     rbx, [rsp+60h+arg_8]
0x1800dcef1  add     rsp, 60h
0x1800dcef5  pop     r15
0x1800dcef7  pop     r14
0x1800dcef9  pop     rdi
0x1800dcefa  pop     rsi
0x1800dcefb  pop     rbp
0x1800dcefc  retn
```
