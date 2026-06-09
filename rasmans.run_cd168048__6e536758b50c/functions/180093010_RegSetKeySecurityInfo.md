# RegSetKeySecurityInfo

- ea: `0x180093010`
- end: `0x1800933ac`
- name: `RegSetKeySecurityInfo`
- size: `924`
- prototype: `__int64 __fastcall(LPCSTR lpSubKey)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18008e3fc`

## callees

- `0x180001fd0`
- `0x180005bfc`
- `0x18005fe20`
- `0x180061064`
- `0x180093010`
- `0x1800e8e96`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetKeySecurity` at `0x1800930eb`
- `api-ms-win-core-registry-l1-1-0!RegGetKeySecurity` at `0x18009312e`
- `api-ms-win-core-registry-l1-1-0!RegGetKeySecurity` at `0x1800930eb`
- `api-ms-win-core-registry-l1-1-0!RegGetKeySecurity` at `0x18009312e`
- `api-ms-win-core-registry-l1-1-0!RegSetKeySecurity` at `0x1800932e7`
- `api-ms-win-core-registry-l1-1-0!RegSetKeySecurity` at `0x1800932e7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180093354`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180093354`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExA` at `0x18009307a`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExA` at `0x18009307a`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x1800931fa`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18009320e`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180093308`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180093368`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180093381`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x1800931fa`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18009320e`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180093308`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180093368`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180093381`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x180093106`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x180093234`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x180093106`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x180093234`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800932f9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800932f9`
- `api-ms-win-security-sddl-l1-1-0!ConvertSecurityDescriptorToStringSecurityDescriptorW` at `0x1800931a6`
- `api-ms-win-security-sddl-l1-1-0!ConvertSecurityDescriptorToStringSecurityDescriptorW` at `0x1800931a6`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1800932ca`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1800932ca`

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
0x180093010  mov     r11, rsp
0x180093013  mov     [r11+10h], rbx
0x180093017  push    rbp
0x180093018  push    rsi
0x180093019  push    rdi
0x18009301a  push    r14
0x18009301c  push    r15
0x18009301e  mov     rbp, rsp
0x180093021  sub     rsp, 60h
0x180093025  test    rcx, rcx
0x180093028  jz      loc_180093392
0x18009302e  mov     r10, 0FFFFFFFF80000003h
0x180093035  cmp     rdx, r10
0x180093038  jnz     loc_180093392
0x18009303e  mov     qword ptr [r11-48h], 0
0x180093046  lea     rax, [rbp+hKey]
0x18009304a  mov     [r11-50h], rax
0x18009304e  mov     rdx, rcx; lpSubKey
0x180093051  mov     qword ptr [r11-58h], 0
0x180093059  xor     r9d, r9d; lpClass
0x18009305c  mov     [rsp+60h+samDesired], 0F023Fh; samDesired
0x180093064  xor     r8d, r8d; Reserved
0x180093067  mov     rcx, r10; hKey
0x18009306a  mov     [rsp+60h+dwOptions], 0; dwOptions
0x180093072  mov     [rbp+hKey], 0
0x18009307a  call    cs:__imp_RegCreateKeyExA
0x180093081  nop     dword ptr [rax+rax+00h]
0x180093086  mov     ebx, eax
0x180093088  test    eax, eax
0x18009308a  jz      short loc_1800930CC
0x18009308c  mov     r10, cs:WPP_GLOBAL_Control
0x180093093  lea     rcx, WPP_GLOBAL_Control
0x18009309a  cmp     r10, rcx
0x18009309d  jz      short loc_1800930C5
0x18009309f  test    byte ptr [r10+1Ch], 80h
0x1800930a4  jz      short loc_1800930C5
0x1800930a6  cmp     byte ptr [r10+19h], 5
0x1800930ab  jb      short loc_1800930C5
0x1800930ad  mov     rcx, [r10+10h]
0x1800930b1  lea     r8, WPP_1a2c25c73f1633f64777688c8bb98551_Traceguids
0x1800930b8  mov     edx, 82h
0x1800930bd  mov     r9d, eax
0x1800930c0  call    WPP_SF_d
0x1800930c5  mov     eax, ebx
0x1800930c7  jmp     loc_180093397
0x1800930cc  mov     rcx, [rbp+hKey]; hKey
0x1800930d0  lea     r9, [rbp+cbSecurityDescriptor]; lpcbSecurityDescriptor
0x1800930d4  xor     esi, esi
0x1800930d6  mov     [rbp+SecurityDescriptor], 0
0x1800930de  xor     r8d, r8d; pSecurityDescriptor
0x1800930e1  mov     [rbp+cbSecurityDescriptor], 0
0x1800930e8  lea     edx, [rsi+4]; SecurityInformation
0x1800930eb  call    cs:__imp_RegGetKeySecurity
0x1800930f2  nop     dword ptr [rax+rax+00h]
0x1800930f7  cmp     eax, 7Ah ; 'z'
0x1800930fa  jnz     loc_180093316
0x180093100  mov     edx, [rbp+cbSecurityDescriptor]; dwBytes
0x180093103  lea     ecx, [rsi+40h]; uFlags
0x180093106  call    cs:__imp_GlobalAlloc
0x18009310d  nop     dword ptr [rax+rax+00h]
0x180093112  mov     rsi, rax
0x180093115  test    rax, rax
0x180093118  jz      loc_180093316
0x18009311e  mov     rcx, [rbp+hKey]; hKey
0x180093122  lea     r9, [rbp+cbSecurityDescriptor]; lpcbSecurityDescriptor
0x180093126  mov     r8, rax; pSecurityDescriptor
0x180093129  mov     edx, 4; SecurityInformation
0x18009312e  call    cs:__imp_RegGetKeySecurity
0x180093135  nop     dword ptr [rax+rax+00h]
0x18009313a  mov     edi, eax
0x18009313c  test    eax, eax
0x18009313e  jz      short loc_18009317E
0x180093140  mov     rax, cs:WPP_GLOBAL_Control
0x180093147  lea     rcx, WPP_GLOBAL_Control
0x18009314e  cmp     rax, rcx
0x180093151  jz      short loc_180093177
0x180093153  test    byte ptr [rax+1Ch], 80h
0x180093157  jz      short loc_180093177
0x180093159  cmp     byte ptr [rax+19h], 2
0x18009315d  jb      short loc_180093177
0x18009315f  mov     rcx, [rax+10h]
0x180093163  lea     r8, WPP_1a2c25c73f1633f64777688c8bb98551_Traceguids
0x18009316a  mov     edx, 84h
0x18009316f  mov     r9d, edi
0x180093172  call    WPP_SF_d
0x180093177  mov     eax, edi
0x180093179  jmp     loc_180093397
0x18009317e  mov     edx, 1; RequestedStringSDRevision
0x180093183  mov     [rbp+StringSecurityDescriptorLen], 0
0x18009318a  lea     rax, [rbp+StringSecurityDescriptorLen]
0x18009318e  mov     [rbp+StringSecurityDescriptor], 0
0x180093196  lea     r9, [rbp+StringSecurityDescriptor]; StringSecurityDescriptor
0x18009319a  mov     qword ptr [rsp+60h+dwOptions], rax; pcchRemaining
0x18009319f  mov     rcx, rsi; SecurityDescriptor
0x1800931a2  lea     r8d, [rdx+3]; SecurityInformation
0x1800931a6  call    cs:__imp_ConvertSecurityDescriptorToStringSecurityDescriptorW
0x1800931ad  nop     dword ptr [rax+rax+00h]
0x1800931b2  test    eax, eax
0x1800931b4  jz      loc_180093350
0x1800931ba  mov     rbx, [rbp+StringSecurityDescriptor]
0x1800931be  lea     rcx, aACiKaS11531024; "(A;CI;KA;;;S-1-15-3-1024-1068037383-729"...
0x1800931c5  call    _StrdupWtoA
0x1800931ca  mov     rcx, rbx; lpWideCharStr
0x1800931cd  mov     r14, rax
0x1800931d0  call    _StrdupWtoA
0x1800931d5  xor     r15d, r15d
0x1800931d8  mov     rbx, rax
0x1800931db  test    r14, r14
0x1800931de  jz      short loc_180093206
0x1800931e0  test    rax, rax
0x1800931e3  jz      short loc_1800931F7
0x1800931e5  mov     rdx, r14; SubStr
0x1800931e8  mov     rcx, rax; Str
0x1800931eb  call    strstr_0
0x1800931f0  test    rax, rax
0x1800931f3  setnz   r15b
0x1800931f7  mov     rcx, r14; hMem
0x1800931fa  call    cs:__imp_GlobalFree
0x180093201  nop     dword ptr [rax+rax+00h]
0x180093206  test    rbx, rbx
0x180093209  jz      short loc_18009321A
0x18009320b  mov     rcx, rbx; hMem
0x18009320e  call    cs:__imp_GlobalFree
0x180093215  nop     dword ptr [rax+rax+00h]
0x18009321a  test    r15d, r15d
0x18009321d  jnz     loc_180093350
0x180093223  mov     eax, [rbp+StringSecurityDescriptorLen]
0x180093226  lea     ecx, [r15+40h]; uFlags
0x18009322a  add     eax, 6Fh ; 'o'
0x18009322d  mov     r14d, eax
0x180093230  lea     rdx, [rax+rax]; dwBytes
0x180093234  call    cs:__imp_GlobalAlloc
0x18009323b  nop     dword ptr [rax+rax+00h]
0x180093240  mov     rbx, rax
0x180093243  test    rax, rax
0x180093246  jnz     short loc_18009327E
0x180093248  lea     edi, [rax+8]
0x18009324b  mov     rax, cs:WPP_GLOBAL_Control
0x180093252  lea     rcx, WPP_GLOBAL_Control
0x180093259  cmp     rax, rcx
0x18009325c  jz      loc_180093350
0x180093262  test    byte ptr [rax+1Ch], 80h
0x180093266  jz      loc_180093350
0x18009326c  cmp     byte ptr [rax+19h], 2
0x180093270  jb      loc_180093350
0x180093276  lea     edx, [rdi+7Dh]
0x180093279  jmp     loc_18009333D
0x18009327e  mov     r8, r14; Size
0x180093281  xor     edx, edx; Val
0x180093283  mov     rcx, rbx; void *
0x180093286  call    memset_0
0x18009328b  mov     r8, [rbp+StringSecurityDescriptor]; pszSrc
0x18009328f  mov     r15d, 100h
0x180093295  mov     rdx, r14; cchDest
0x180093298  mov     [rsp+60h+samDesired], r15d; dwFlags
0x18009329d  mov     rcx, rbx; pszDest
0x1800932a0  call    StringCchCatExW
0x1800932a5  lea     r8, aACiKaS11531024; "(A;CI;KA;;;S-1-15-3-1024-1068037383-729"...
0x1800932ac  mov     [rsp+60h+samDesired], r15d; dwFlags
0x1800932b1  mov     rdx, r14; cchDest
0x1800932b4  mov     rcx, rbx; pszDest
0x1800932b7  call    StringCchCatExW
0x1800932bc  xor     r9d, r9d; SecurityDescriptorSize
0x1800932bf  lea     r8, [rbp+SecurityDescriptor]; SecurityDescriptor
0x1800932c3  mov     rcx, rbx; StringSecurityDescriptor
0x1800932c6  lea     edx, [r9+1]; StringSDRevision
0x1800932ca  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x1800932d1  nop     dword ptr [rax+rax+00h]
0x1800932d6  test    eax, eax
0x1800932d8  jz      short loc_180093305
0x1800932da  mov     r8, [rbp+SecurityDescriptor]; pSecurityDescriptor
0x1800932de  mov     edx, 4; SecurityInformation
0x1800932e3  mov     rcx, [rbp+hKey]; hKey
0x1800932e7  call    cs:__imp_RegSetKeySecurity
0x1800932ee  nop     dword ptr [rax+rax+00h]
0x1800932f3  mov     rcx, [rbp+SecurityDescriptor]; hMem
0x1800932f7  mov     edi, eax
0x1800932f9  call    cs:__imp_LocalFree
0x180093300  nop     dword ptr [rax+rax+00h]
0x180093305  mov     rcx, rbx; hMem
0x180093308  call    cs:__imp_GlobalFree
0x18009330f  nop     dword ptr [rax+rax+00h]
0x180093314  jmp     short loc_180093350
0x180093316  mov     rax, cs:WPP_GLOBAL_Control
0x18009331d  lea     rcx, WPP_GLOBAL_Control
0x180093324  mov     edi, 8
0x180093329  cmp     rax, rcx
0x18009332c  jz      short loc_180093350
0x18009332e  test    byte ptr [rax+1Ch], 80h
0x180093332  jz      short loc_180093350
0x180093334  cmp     byte ptr [rax+19h], 2
0x180093338  jb      short loc_180093350
0x18009333a  lea     edx, [rdi+7Bh]
0x18009333d  mov     rcx, [rax+10h]
0x180093341  lea     r8, WPP_1a2c25c73f1633f64777688c8bb98551_Traceguids
0x180093348  mov     r9d, edi
0x18009334b  call    WPP_SF_d
0x180093350  mov     rcx, [rbp+hKey]; hKey
0x180093354  call    cs:__imp_RegCloseKey
0x18009335b  nop     dword ptr [rax+rax+00h]
0x180093360  test    rsi, rsi
0x180093363  jz      short loc_180093374
0x180093365  mov     rcx, rsi; hMem
0x180093368  call    cs:__imp_GlobalFree
0x18009336f  nop     dword ptr [rax+rax+00h]
0x180093374  mov     rcx, [rbp+StringSecurityDescriptor]; hMem
0x180093378  test    rcx, rcx
0x18009337b  jz      loc_180093177
0x180093381  call    cs:__imp_GlobalFree
0x180093388  nop     dword ptr [rax+rax+00h]
0x18009338d  jmp     loc_180093177
0x180093392  mov     eax, 57h ; 'W'
0x180093397  mov     rbx, [rsp+60h+arg_8]
0x18009339f  add     rsp, 60h
0x1800933a3  pop     r15
0x1800933a5  pop     r14
0x1800933a7  pop     rdi
0x1800933a8  pop     rsi
0x1800933a9  pop     rbp
0x1800933aa  retn
```
