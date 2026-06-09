# CoInternetQueryFeatureDWORDDeprecated

- ea: `0x180023a00`
- end: `0x180023cc5`
- name: `CoInternetQueryFeatureDWORDDeprecated`
- size: `709`
- prototype: `__int64 __fastcall(struct _GUID *, LPCWSTR lpValueName, LPBYTE lpData)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1800230f4`
- `0x180023a00`
- `0x1800246e8`
- `0x180083c10`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180023aba`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180023ae0`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180023b02`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180023b24`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180023c43`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180023c72`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180023aba`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180023ae0`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180023b02`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180023b24`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180023c43`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180023c72`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180023bc2`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180023c98`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180023bc2`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180023c98`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180023bd4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180023ca9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180023cb3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180023bd4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180023ca9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180023cb3`

## pseudocode

```c
__int64 __fastcall CoInternetQueryFeatureDWORDDeprecated(struct _GUID *a1, LPCWSTR lpValueName, LPBYTE lpData)
{
  int v6; // edi
  __int64 v7; // rax
  BOOL v8; // ebx
  unsigned int v9; // esi
  const WCHAR *v10; // r13
  HKEY v12; // rcx
  __int64 v13; // rax
  __int64 v14; // rax
  DWORD cbData; // [rsp+30h] [rbp-50h] BYREF
  DWORD Type; // [rsp+34h] [rbp-4Ch] BYREF
  HKEY v17; // [rsp+38h] [rbp-48h] BYREF
  HKEY v18; // [rsp+40h] [rbp-40h] BYREF
  _DWORD v19[4]; // [rsp+48h] [rbp-38h]
  HKEY hKey[2]; // [rsp+58h] [rbp-28h] BYREF
  HKEY phkResult[2]; // [rsp+68h] [rbp-18h] BYREF

  v6 = -2147467259;
  if ( a1 )
  {
    v7 = *(_QWORD *)&a1->Data1 - *(_QWORD *)&GUID_fda14e96_13e0_4fb0_baf5_5870c1b099e4.Data1;
    if ( *(_QWORD *)&a1->Data1 == *(_QWORD *)&GUID_fda14e96_13e0_4fb0_baf5_5870c1b099e4.Data1 )
      v7 = *(_QWORD *)a1->Data4 - *(_QWORD *)GUID_fda14e96_13e0_4fb0_baf5_5870c1b099e4.Data4;
    if ( !v7 )
      goto LABEL_31;
    v13 = *(_QWORD *)&a1->Data1 - *(_QWORD *)&GUID_428bf17b_00eb_4359_ac87_844188177b35.Data1;
    if ( *(_QWORD *)&a1->Data1 == *(_QWORD *)&GUID_428bf17b_00eb_4359_ac87_844188177b35.Data1 )
      v13 = *(_QWORD *)a1->Data4 - *(_QWORD *)GUID_428bf17b_00eb_4359_ac87_844188177b35.Data4;
    if ( !v13 )
      goto LABEL_31;
    v14 = *(_QWORD *)&a1->Data1 - *(_QWORD *)&GUID_e833c51f_d8fd_4cf4_871b_1b5bcb0ec309.Data1;
    if ( *(_QWORD *)&a1->Data1 == *(_QWORD *)&GUID_e833c51f_d8fd_4cf4_871b_1b5bcb0ec309.Data1 )
      v14 = *(_QWORD *)a1->Data4 - *(_QWORD *)GUID_e833c51f_d8fd_4cf4_871b_1b5bcb0ec309.Data4;
    if ( v14 )
    {
      return (unsigned int)-2147418113;
    }
    else
    {
LABEL_31:
      if ( !IEIsWebPlatformProcess() )
      {
        cbData = 0;
        v6 = GuidToFeatureIndex(a1, &cbData);
        if ( v6 >= 0 )
        {
          *(_OWORD *)hKey = 0;
          *(_OWORD *)phkResult = 0;
          v19[0] = RegOpenKeyExW(
                     HKEY_LOCAL_MACHINE,
                     L"Software\\Policies\\Microsoft\\Internet Explorer\\Main\\FeatureControl",
                     0,
                     0x20019u,
                     hKey);
          v19[1] = RegOpenKeyExW(
                     HKEY_CURRENT_USER,
                     L"Software\\Policies\\Microsoft\\Internet Explorer\\Main\\FeatureControl",
                     0,
                     0x20019u,
                     &hKey[1]);
          v19[2] = RegOpenKeyExW(
                     HKEY_CURRENT_USER,
                     L"Software\\Microsoft\\Internet Explorer\\Main\\FeatureControl",
                     0,
                     0x20019u,
                     phkResult);
          v19[3] = RegOpenKeyExW(
                     HKEY_LOCAL_MACHINE,
                     L"Software\\Microsoft\\Internet Explorer\\Main\\FeatureControl",
                     0,
                     0x20019u,
                     &phkResult[1]);
          v8 = 1;
          v9 = 0;
          v10 = (&off_1800DB008)[4 * cbData];
          do
          {
            if ( !v19[v9] )
            {
              v12 = hKey[v9];
              if ( v12 )
              {
                if ( v8 )
                {
                  Type = 4;
                  cbData = 4;
                  if ( lpValueName )
                  {
                    v18 = 0;
                    if ( !RegOpenKeyExW(v12, v10, 0, 0x20019u, &v18) )
                    {
                      v17 = 0;
                      if ( !RegOpenKeyExW(v18, L"Settings", 0, 0x20019u, &v17) )
                      {
                        v8 = RegQueryValueExW(v17, lpValueName, 0, &Type, lpData, &cbData) != 0;
                        RegCloseKey(v17);
                      }
                      RegCloseKey(v18);
                    }
                  }
                  else
                  {
                    v8 = RegQueryValueExW(v12, v10, 0, &Type, lpData, &cbData) != 0;
                  }
                }
                RegCloseKey(hKey[v9]);
              }
            }
            ++v9;
          }
          while ( v9 < 4 );
          if ( !v8 )
            return 0;
        }
      }
    }
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180023a00  mov     [rsp-38h+arg_18], rbx
0x180023a05  push    rbp
0x180023a06  push    rsi
0x180023a07  push    rdi
0x180023a08  push    r12
0x180023a0a  push    r13
0x180023a0c  push    r14
0x180023a0e  push    r15
0x180023a10  mov     rbp, rsp
0x180023a13  sub     rsp, 80h
0x180023a1a  mov     rax, cs:__security_cookie
0x180023a21  xor     rax, rsp
0x180023a24  mov     [rbp+var_8], rax
0x180023a28  mov     r12, r8
0x180023a2b  mov     r15, rdx
0x180023a2e  mov     rbx, rcx
0x180023a31  mov     edi, 80004005h
0x180023a36  test    rcx, rcx
0x180023a39  jz      loc_180023B60
0x180023a3f  mov     rax, [rcx]
0x180023a42  sub     rax, qword ptr cs:_GUID_fda14e96_13e0_4fb0_baf5_5870c1b099e4.Data1
0x180023a49  jnz     short loc_180023A56
0x180023a4b  mov     rax, [rcx+8]
0x180023a4f  sub     rax, qword ptr cs:_GUID_fda14e96_13e0_4fb0_baf5_5870c1b099e4.Data4
0x180023a56  test    rax, rax
0x180023a59  jnz     loc_180023BDF
0x180023a5f  call    ?IEIsWebPlatformProcess@@YA_NXZ; IEIsWebPlatformProcess(void)
0x180023a64  test    al, al
0x180023a66  jnz     loc_180023B60
0x180023a6c  lea     rdx, [rbp+cbData]; unsigned int *
0x180023a70  mov     [rbp+cbData], 0
0x180023a77  mov     rcx, rbx; struct _GUID *
0x180023a7a  call    ?GuidToFeatureIndex@@YAJPEBU_GUID@@PEAK@Z; GuidToFeatureIndex(_GUID const *,ulong *)
0x180023a7f  mov     edi, eax
0x180023a81  test    eax, eax
0x180023a83  js      loc_180023B60
0x180023a89  xorps   xmm0, xmm0
0x180023a8c  lea     rax, [rbp+hKey]
0x180023a90  mov     r14d, 20019h
0x180023a96  mov     [rsp+80h+phkResult], rax; phkResult
0x180023a9b  mov     rsi, 0FFFFFFFF80000002h
0x180023aa2  lea     rdx, SubKey; "Software\\Policies\\Microsoft\\Internet"...
0x180023aa9  mov     r9d, r14d; samDesired
0x180023aac  mov     rcx, rsi; hKey
0x180023aaf  xor     r8d, r8d; ulOptions
0x180023ab2  movups  xmmword ptr [rbp+hKey], xmm0
0x180023ab6  movups  xmmword ptr [rbp+var_18], xmm0
0x180023aba  call    cs:__imp_RegOpenKeyExW
0x180023ac0  mov     [rbp+var_38], eax
0x180023ac3  lea     rbx, [rsi-1]
0x180023ac7  lea     rax, [rbp+hKey+8]
0x180023acb  mov     r9d, r14d; samDesired
0x180023ace  xor     r8d, r8d; ulOptions
0x180023ad1  mov     [rsp+80h+phkResult], rax; phkResult
0x180023ad6  lea     rdx, SubKey; "Software\\Policies\\Microsoft\\Internet"...
0x180023add  mov     rcx, rbx; hKey
0x180023ae0  call    cs:__imp_RegOpenKeyExW
0x180023ae6  mov     [rbp+var_34], eax
0x180023ae9  mov     r9d, r14d; samDesired
0x180023aec  xor     r8d, r8d; ulOptions
0x180023aef  lea     rdx, aSoftwareMicros_34; "Software\\Microsoft\\Internet Explorer"...
0x180023af6  lea     rax, [rbp+var_18]
0x180023afa  mov     rcx, rbx; hKey
0x180023afd  mov     [rsp+80h+phkResult], rax; phkResult
0x180023b02  call    cs:__imp_RegOpenKeyExW
0x180023b08  mov     [rbp+var_30], eax
0x180023b0b  mov     r9d, r14d; samDesired
0x180023b0e  xor     r8d, r8d; ulOptions
0x180023b11  lea     rdx, aSoftwareMicros_34; "Software\\Microsoft\\Internet Explorer"...
0x180023b18  lea     rax, [rbp+var_18+8]
0x180023b1c  mov     rcx, rsi; hKey
0x180023b1f  mov     [rsp+80h+phkResult], rax; phkResult
0x180023b24  call    cs:__imp_RegOpenKeyExW
0x180023b2a  mov     [rbp+var_2C], eax
0x180023b2d  lea     r13, off_1800DB008; "FEATURE_WINDOW_RESTRICTIONS"
0x180023b34  mov     eax, [rbp+cbData]
0x180023b37  mov     ebx, 1
0x180023b3c  shl     rax, 5
0x180023b40  xor     esi, esi
0x180023b42  mov     r13, [rax+r13]
0x180023b46  movsxd  r14, esi
0x180023b49  cmp     [rbp+r14*4+var_38], 0
0x180023b4f  jz      short loc_180023B89
0x180023b51  inc     esi
0x180023b53  cmp     esi, 4
0x180023b56  jb      short loc_180023B46
0x180023b58  test    ebx, ebx
0x180023b5a  jz      loc_180023CBE
0x180023b60  mov     eax, edi
0x180023b62  mov     rcx, [rbp+var_8]
0x180023b66  xor     rcx, rsp; StackCookie
0x180023b69  call    __security_check_cookie
0x180023b6e  mov     rbx, [rsp+80h+arg_18]
0x180023b76  add     rsp, 80h
0x180023b7d  pop     r15
0x180023b7f  pop     r14
0x180023b81  pop     r13
0x180023b83  pop     r12
0x180023b85  pop     rdi
0x180023b86  pop     rsi
0x180023b87  pop     rbp
0x180023b88  retn
0x180023b89  mov     rcx, [rbp+r14*8+hKey]; hKey
0x180023b8e  test    rcx, rcx
0x180023b91  jz      short loc_180023B51
0x180023b93  test    ebx, ebx
0x180023b95  jz      short loc_180023BCF
0x180023b97  mov     [rbp+Type], 4
0x180023b9e  mov     rdx, r13; lpSubKey
0x180023ba1  mov     [rbp+cbData], 4
0x180023ba8  test    r15, r15
0x180023bab  jnz     short loc_180023C29
0x180023bad  lea     rax, [rbp+cbData]
0x180023bb1  xor     r8d, r8d; lpReserved
0x180023bb4  mov     [rsp+80h+lpcbData], rax; lpcbData
0x180023bb9  lea     r9, [rbp+Type]; lpType
0x180023bbd  mov     [rsp+80h+phkResult], r12; lpData
0x180023bc2  call    cs:__imp_RegQueryValueExW
0x180023bc8  xor     ebx, ebx
0x180023bca  test    eax, eax
0x180023bcc  setnz   bl
0x180023bcf  mov     rcx, [rbp+r14*8+hKey]; hKey
0x180023bd4  call    cs:__imp_RegCloseKey
0x180023bda  jmp     loc_180023B51
0x180023bdf  mov     rax, [rcx]
0x180023be2  sub     rax, qword ptr cs:_GUID_428bf17b_00eb_4359_ac87_844188177b35.Data1
0x180023be9  jnz     short loc_180023BF6
0x180023beb  mov     rax, [rcx+8]
0x180023bef  sub     rax, qword ptr cs:_GUID_428bf17b_00eb_4359_ac87_844188177b35.Data4
0x180023bf6  test    rax, rax
0x180023bf9  jz      loc_180023A5F
0x180023bff  mov     rax, [rcx]
0x180023c02  sub     rax, qword ptr cs:_GUID_e833c51f_d8fd_4cf4_871b_1b5bcb0ec309.Data1
0x180023c09  jnz     short loc_180023C16
0x180023c0b  mov     rax, [rcx+8]
0x180023c0f  sub     rax, qword ptr cs:_GUID_e833c51f_d8fd_4cf4_871b_1b5bcb0ec309.Data4
0x180023c16  test    rax, rax
0x180023c19  jz      loc_180023A5F
0x180023c1f  mov     edi, 8000FFFFh
0x180023c24  jmp     loc_180023B60
0x180023c29  lea     rax, [rbp+var_40]
0x180023c2d  mov     [rbp+var_40], 0
0x180023c35  mov     r9d, 20019h; samDesired
0x180023c3b  mov     [rsp+80h+phkResult], rax; phkResult
0x180023c40  xor     r8d, r8d; ulOptions
0x180023c43  call    cs:__imp_RegOpenKeyExW
0x180023c49  test    eax, eax
0x180023c4b  jnz     short loc_180023BCF
0x180023c4d  mov     rcx, [rbp+var_40]; hKey
0x180023c51  lea     rax, [rbp+var_48]
0x180023c55  mov     r9d, 20019h; samDesired
0x180023c5b  mov     [rsp+80h+phkResult], rax; phkResult
0x180023c60  xor     r8d, r8d; ulOptions
0x180023c63  mov     [rbp+var_48], 0
0x180023c6b  lea     rdx, aSettings; "Settings"
0x180023c72  call    cs:__imp_RegOpenKeyExW
0x180023c78  test    eax, eax
0x180023c7a  jnz     short loc_180023CAF
0x180023c7c  mov     rcx, [rbp+var_48]; hKey
0x180023c80  lea     rax, [rbp+cbData]
0x180023c84  mov     [rsp+80h+lpcbData], rax; lpcbData
0x180023c89  lea     r9, [rbp+Type]; lpType
0x180023c8d  xor     r8d, r8d; lpReserved
0x180023c90  mov     [rsp+80h+phkResult], r12; lpData
0x180023c95  mov     rdx, r15; lpValueName
0x180023c98  call    cs:__imp_RegQueryValueExW
0x180023c9e  mov     rcx, [rbp+var_48]; hKey
0x180023ca2  xor     ebx, ebx
0x180023ca4  test    eax, eax
0x180023ca6  setnz   bl
0x180023ca9  call    cs:__imp_RegCloseKey
0x180023caf  mov     rcx, [rbp+var_40]; hKey
0x180023cb3  call    cs:__imp_RegCloseKey
0x180023cb9  jmp     loc_180023BCF
0x180023cbe  xor     edi, edi
0x180023cc0  jmp     loc_180023B60
```
