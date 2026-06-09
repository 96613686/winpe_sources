# CreateEventSystemKey(HKEY__ *,ulong,ushort const *)

- ea: `0x180007e6c`
- end: `0x1800084bf`
- name: `?CreateEventSystemKey@@YAJPEAUHKEY__@@KPEBG@Z`
- size: `1619`
- prototype: `__int64 __fastcall(HKEY hKey, unsigned int, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180016920`

## callees

- `0x180006194`
- `0x180007e6c`
- `0x1800084c8`
- `0x180008fbc`
- `0x180012654`
- `0x180043510`
- `0x1800435a0`
- `0x180046010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008392`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800083b0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800083e5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008392`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800083b0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800083e5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000812f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000812f`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180007f44`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18000806e`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180007f44`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18000806e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000811b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180008125`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000811b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180008125`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x180007f7d`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x1800080a2`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x180007f7d`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x1800080a2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180007efe`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180007efe`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180007eec`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180007eec`
- `api-ms-win-security-provider-l1-1-0!SetNamedSecurityInfoW` at `0x18000800d`
- `api-ms-win-security-provider-l1-1-0!SetNamedSecurityInfoW` at `0x1800082bd`
- `api-ms-win-security-provider-l1-1-0!SetNamedSecurityInfoW` at `0x18000800d`
- `api-ms-win-security-provider-l1-1-0!SetNamedSecurityInfoW` at `0x1800082bd`

## string_xrefs

- `0x180008302`: `com\complus\src\events\tier2\service.cpp`
- `0x18000849d`: `com\complus\src\events\tier2\service.cpp`

## pseudocode

```c
__int64 __fastcall CreateEventSystemKey(HKEY hKey, unsigned int a2, const unsigned __int16 *a3)
{
  signed int v6; // ebx
  LSTATUS v7; // eax
  __int64 v8; // rax
  unsigned int v9; // esi
  unsigned __int64 v10; // r14
  signed int v11; // eax
  LSTATUS v12; // eax
  __int64 v13; // rax
  unsigned int v14; // esi
  unsigned __int64 v15; // r14
  unsigned __int16 *p_dwDisposition; // rdi
  _DWORD *v18; // rax
  unsigned __int16 *p_StringSecurityDescriptor; // rdi
  unsigned __int64 v20; // rcx
  void *v21; // rsp
  void *v22; // rsp
  signed int v23; // eax
  int v24; // eax
  unsigned __int64 v25; // rcx
  unsigned __int64 v26; // rcx
  void *v27; // rsp
  void *v28; // rsp
  signed int LastError; // eax
  signed int v30; // eax
  signed int v31; // eax
  _DWORD *v32; // rax
  _BYTE v33[32]; // [rsp+0h] [rbp-50h] BYREF
  DWORD dwDisposition; // [rsp+50h] [rbp+0h] BYREF
  WINBOOL bDaclDefaulted; // [rsp+54h] [rbp+4h] BYREF
  LPCWSTR StringSecurityDescriptor; // [rsp+58h] [rbp+8h] BYREF
  PACL pDacl; // [rsp+60h] [rbp+10h] BYREF
  HKEY hKeya; // [rsp+68h] [rbp+18h] BYREF
  HKEY phkResult; // [rsp+70h] [rbp+20h] BYREF
  struct _SECURITY_ATTRIBUTES SecurityDescriptor; // [rsp+78h] [rbp+28h] BYREF
  unsigned __int16 v41[8]; // [rsp+A0h] [rbp+50h] BYREF
  __int128 v42; // [rsp+B0h] [rbp+60h]
  __int128 v43; // [rsp+C0h] [rbp+70h]
  __int128 v44; // [rsp+D0h] [rbp+80h]
  _OWORD v45[2]; // [rsp+E0h] [rbp+90h]

  hKeya = 0;
  dwDisposition = 0;
  StringSecurityDescriptor = 0;
  memset(&SecurityDescriptor, 0, sizeof(SecurityDescriptor));
  SecurityDescriptor.nLength = 24;
  v6 = InitializeStringSecurityDescriptorForEventSystemKey(a2, a3, (unsigned __int16 **)&StringSecurityDescriptor);
  if ( v6 >= 0 )
  {
    if ( !ConvertStringSecurityDescriptorToSecurityDescriptorW(
            StringSecurityDescriptor,
            1u,
            &SecurityDescriptor.lpSecurityDescriptor,
            0) )
    {
      LastError = GetLastError();
      v6 = LastError;
      if ( LastError > 0 )
        v6 = (unsigned __int16)LastError | 0x80070000;
    }
    CoTaskMemFree((LPVOID)StringSecurityDescriptor);
  }
  if ( v6 >= 0 )
  {
    v7 = RegCreateKeyExW(
           hKey,
           L"Software\\Microsoft\\EventSystem",
           0,
           0,
           0,
           0x20006u,
           &SecurityDescriptor,
           &hKeya,
           &dwDisposition);
    if ( v7 )
    {
      if ( v7 > 0 )
        v6 = (unsigned __int16)v7 | 0x80070000;
      else
        v6 = v7;
      goto LABEL_22;
    }
    if ( dwDisposition != 2 )
      goto LABEL_14;
    LODWORD(StringSecurityDescriptor) = 0;
    bDaclDefaulted = 0;
    pDacl = 0;
    if ( !GetSecurityDescriptorDacl(
            SecurityDescriptor.lpSecurityDescriptor,
            (LPBOOL)&StringSecurityDescriptor,
            &pDacl,
            &bDaclDefaulted) )
    {
      v30 = GetLastError();
      v6 = v30;
      if ( v30 > 0 )
        v6 = (unsigned __int16)v30 | 0x80070000;
LABEL_13:
      if ( v6 < 0 )
        goto LABEL_21;
LABEL_14:
      phkResult = 0;
      v12 = RegCreateKeyExW(
              hKeya,
              L"{26c409cc-ae86-11d1-b616-00805fc79216}",
              0,
              0,
              0,
              0x20006u,
              &SecurityDescriptor,
              &phkResult,
              &dwDisposition);
      if ( v12 )
      {
        if ( v12 > 0 )
          v6 = (unsigned __int16)v12 | 0x80070000;
        else
          v6 = v12;
        goto LABEL_21;
      }
      if ( dwDisposition != 2 )
        goto LABEL_20;
      bDaclDefaulted = 0;
      LODWORD(StringSecurityDescriptor) = 0;
      pDacl = 0;
      if ( !GetSecurityDescriptorDacl(
              SecurityDescriptor.lpSecurityDescriptor,
              &bDaclDefaulted,
              &pDacl,
              (LPBOOL)&StringSecurityDescriptor) )
      {
        v31 = GetLastError();
        v6 = v31;
        if ( v31 > 0 )
          v6 = (unsigned __int16)v31 | 0x80070000;
        goto LABEL_20;
      }
      v13 = a2 + 82;
      *(_OWORD *)v41 = *(_OWORD *)L"USERS\\%s\\Software\\Microsoft\\EventSystem\\%s";
      v42 = *(_OWORD *)L"\\Software\\Microsoft\\EventSystem\\%s";
      v43 = *(_OWORD *)L"e\\Microsoft\\EventSystem\\%s";
      v44 = *(_OWORD *)L"oft\\EventSystem\\%s";
      v45[0] = *(_OWORD *)L"tSystem\\%s";
      *(_QWORD *)((char *)v45 + 14) = *(_QWORD *)L"\\%s";
      if ( a2 >= 0xFFFFFFAE || (v14 = 2 * v13, v15 = (unsigned int)v13, (unsigned __int64)(2 * v13) > 0xFFFFFFFF) )
      {
        v6 = -2147024362;
LABEL_20:
        RegCloseKey(phkResult);
        goto LABEL_21;
      }
      p_dwDisposition = 0;
      if ( v14
        && v14 <= (unsigned __int64)g_ulMaxStackAllocSize
        && (unsigned __int64)v14 + g_ulAdditionalProbeSize + 8 >= v14
        && (unsigned int)VerifyStackAvailable() )
      {
        v25 = v14 + 23LL;
        if ( v25 <= (unsigned __int64)v14 + 8 )
          v25 = 0xFFFFFFFFFFFFFF0LL;
        v26 = v25 & 0xFFFFFFFFFFFFFFF0uLL;
        v27 = alloca(v26);
        v28 = alloca(v26);
        p_dwDisposition = (unsigned __int16 *)&dwDisposition;
        if ( v33 != (_BYTE *)-80LL )
        {
          dwDisposition = 1801679955;
          p_dwDisposition = (unsigned __int16 *)&StringSecurityDescriptor;
          if ( &StringSecurityDescriptor )
          {
LABEL_42:
            v6 = StringCchPrintfW(p_dwDisposition, v15, v41, a3, L"{26c409cc-ae86-11d1-b616-00805fc79216}");
            if ( v6 < 0 )
              goto LABEL_45;
            v23 = SetNamedSecurityInfoW(p_dwDisposition, SE_REGISTRY_KEY, 4u, 0, 0, pDacl, 0);
            if ( v23 )
            {
              if ( v23 > 0 )
                v6 = (unsigned __int16)v23 | 0x80070000;
              else
                v6 = v23;
            }
            if ( p_dwDisposition )
            {
LABEL_45:
              v24 = *((_DWORD *)p_dwDisposition - 2);
              if ( v24 == 1885431112 )
              {
                ((void (*)(void))g_pfnFree)();
              }
              else if ( v24 != 1801679955 )
              {
                InternalAssert(
                  L"com\\complus\\src\\events\\tier2\\service.cpp",
                  0x370u,
                  0x10u,
                  L"*(SAFEALLOCA_HEADER *) (Tag) == ((SAFEALLOCA_HEADER) 0x6b637453)");
              }
            }
            goto LABEL_20;
          }
        }
      }
      if ( (unsigned __int64)v14 + 8 >= v14 )
      {
        v18 = (_DWORD *)((__int64 (*)(void))g_pfnAllocate)();
        if ( !v18 )
          goto LABEL_29;
        *v18 = 1885431112;
        p_dwDisposition = (unsigned __int16 *)(v18 + 2);
      }
      if ( p_dwDisposition )
        goto LABEL_42;
LABEL_29:
      v6 = -2147024882;
      goto LABEL_20;
    }
    v8 = a2 + 40;
    *(_OWORD *)v41 = *(_OWORD *)L"USERS\\%s\\Software\\Microsoft\\EventSystem";
    v43 = *(_OWORD *)L"e\\Microsoft\\EventSystem";
    v42 = *(_OWORD *)L"\\Software\\Microsoft\\EventSystem";
    v45[0] = *(_OWORD *)L"tSystem";
    v44 = *(_OWORD *)L"oft\\EventSystem";
    if ( a2 >= 0xFFFFFFD8 || (v9 = 2 * v8, v10 = (unsigned int)v8, (unsigned __int64)(2 * v8) > 0xFFFFFFFF) )
    {
      v6 = -2147024362;
LABEL_21:
      RegCloseKey(hKeya);
LABEL_22:
      LocalFree(SecurityDescriptor.lpSecurityDescriptor);
      return (unsigned int)v6;
    }
    p_StringSecurityDescriptor = 0;
    if ( v9
      && v9 <= (unsigned __int64)g_ulMaxStackAllocSize
      && (unsigned __int64)v9 + g_ulAdditionalProbeSize + 8 >= v9
      && (unsigned int)VerifyStackAvailable() )
    {
      v20 = v9 + 23LL;
      if ( v20 <= (unsigned __int64)v9 + 8 )
        v20 = 0xFFFFFFFFFFFFFF0LL;
      v21 = alloca(v20 & 0xFFFFFFFFFFFFFFF0uLL);
      v22 = alloca(v20 & 0xFFFFFFFFFFFFFFF0uLL);
      p_StringSecurityDescriptor = (unsigned __int16 *)&dwDisposition;
      if ( v33 != (_BYTE *)-80LL )
      {
        dwDisposition = 1801679955;
        p_StringSecurityDescriptor = (unsigned __int16 *)&StringSecurityDescriptor;
        if ( &StringSecurityDescriptor )
        {
LABEL_38:
          v6 = StringCchPrintfW(p_StringSecurityDescriptor, v10, v41, a3);
          if ( v6 < 0 )
            goto LABEL_39;
          v11 = SetNamedSecurityInfoW(p_StringSecurityDescriptor, SE_REGISTRY_KEY, 4u, 0, 0, pDacl, 0);
          if ( v11 )
          {
            if ( v11 > 0 )
              v6 = (unsigned __int16)v11 | 0x80070000;
            else
              v6 = v11;
          }
          if ( p_StringSecurityDescriptor )
          {
LABEL_39:
            if ( *((_DWORD *)p_StringSecurityDescriptor - 2) == 1885431112 )
            {
              ((void (__fastcall *)(unsigned __int16 *))g_pfnFree)(p_StringSecurityDescriptor - 4);
            }
            else if ( *((_DWORD *)p_StringSecurityDescriptor - 2) != 1801679955 )
            {
              InternalAssert(
                L"com\\complus\\src\\events\\tier2\\service.cpp",
                0x341u,
                0x10u,
                L"*(SAFEALLOCA_HEADER *) (Tag) == ((SAFEALLOCA_HEADER) 0x6b637453)");
            }
          }
          goto LABEL_13;
        }
      }
    }
    if ( (unsigned __int64)v9 + 8 >= v9 )
    {
      v32 = (_DWORD *)((__int64 (*)(void))g_pfnAllocate)();
      if ( !v32 )
        goto LABEL_49;
      *v32 = 1885431112;
      p_StringSecurityDescriptor = (unsigned __int16 *)(v32 + 2);
    }
    if ( p_StringSecurityDescriptor )
      goto LABEL_38;
LABEL_49:
    v6 = -2147024882;
    goto LABEL_21;
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180007e6c  push    rbp
0x180007e6e  push    rsi
0x180007e6f  push    rdi
0x180007e70  push    r12
0x180007e72  push    r13
0x180007e74  push    r14
0x180007e76  push    r15
0x180007e78  sub     rsp, 110h
0x180007e7f  lea     rbp, [rsp+50h]
0x180007e84  mov     [rbp+0F0h+arg_18], rbx
0x180007e8b  mov     rax, cs:__security_cookie
0x180007e92  xor     rax, rbp
0x180007e95  mov     [rbp+0F0h+var_40], rax
0x180007e9c  mov     r12, r8
0x180007e9f  mov     r15d, edx
0x180007ea2  xor     r13d, r13d
0x180007ea5  lea     r8, [rbp+0F0h+StringSecurityDescriptor]; unsigned __int16 **
0x180007ea9  xorps   xmm0, xmm0
0x180007eac  mov     [rbp+0F0h+hKey], r13
0x180007eb0  mov     rdi, rcx
0x180007eb3  mov     [rbp+0F0h+dwDisposition], r13d
0x180007eb7  xor     eax, eax
0x180007eb9  mov     [rbp+0F0h+StringSecurityDescriptor], r13
0x180007ebd  movups  xmmword ptr [rbp+0F0h+SecurityDescriptor], xmm0
0x180007ec1  mov     rdx, r12; unsigned __int16 *
0x180007ec4  mov     dword ptr [rbp+0F0h+SecurityDescriptor], 18h
0x180007ecb  mov     ecx, r15d; unsigned int
0x180007ece  mov     [rbp+0F0h+var_B8], rax
0x180007ed2  call    ?InitializeStringSecurityDescriptorForEventSystemKey@@YAJKPEBGPEAPEAG@Z; InitializeStringSecurityDescriptorForEventSystemKey(ulong,ushort const *,ushort * *)
0x180007ed7  mov     ebx, eax
0x180007ed9  test    eax, eax
0x180007edb  js      short loc_180007F04
0x180007edd  mov     rcx, [rbp+0F0h+StringSecurityDescriptor]; StringSecurityDescriptor
0x180007ee1  lea     r8, [rbp+0F0h+SecurityDescriptor+8]; SecurityDescriptor
0x180007ee5  xor     r9d, r9d; SecurityDescriptorSize
0x180007ee8  lea     edx, [r13+1]; StringSDRevision
0x180007eec  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x180007ef2  test    eax, eax
0x180007ef4  jz      loc_180008392
0x180007efa  mov     rcx, [rbp+0F0h+StringSecurityDescriptor]; pv
0x180007efe  call    cs:__imp_CoTaskMemFree
0x180007f04  test    ebx, ebx
0x180007f06  js      loc_180008135
0x180007f0c  lea     rax, [rbp+0F0h+dwDisposition]
0x180007f10  xor     r9d, r9d; lpClass
0x180007f13  mov     [rsp+140h+lpdwDisposition], rax; lpdwDisposition
0x180007f18  lea     rdx, aSoftwareMicros_3; "Software\\Microsoft\\EventSystem"
0x180007f1f  lea     rax, [rbp+0F0h+hKey]
0x180007f23  xor     r8d, r8d; Reserved
0x180007f26  mov     [rsp+140h+phkResult], rax; phkResult
0x180007f2b  mov     rcx, rdi; hKey
0x180007f2e  lea     rax, [rbp+0F0h+SecurityDescriptor]
0x180007f32  mov     [rsp+140h+lpSecurityAttributes], rax; lpSecurityAttributes
0x180007f37  mov     [rsp+140h+samDesired], 20006h; samDesired
0x180007f3f  mov     [rsp+140h+dwOptions], r13d; dwOptions
0x180007f44  call    cs:__imp_RegCreateKeyExW
0x180007f4a  test    eax, eax
0x180007f4c  jnz     loc_180008431
0x180007f52  cmp     [rbp+0F0h+dwDisposition], 2
0x180007f56  mov     edi, 0FFFFFFFFh
0x180007f5b  jnz     loc_180008031
0x180007f61  mov     rcx, [rbp+0F0h+SecurityDescriptor+8]; pSecurityDescriptor
0x180007f65  lea     r9, [rbp+0F0h+bDaclDefaulted]; lpbDaclDefaulted
0x180007f69  lea     r8, [rbp+0F0h+pDacl]; pDacl
0x180007f6d  mov     dword ptr [rbp+0F0h+StringSecurityDescriptor], r13d
0x180007f71  lea     rdx, [rbp+0F0h+StringSecurityDescriptor]; lpbDaclPresent
0x180007f75  mov     [rbp+0F0h+bDaclDefaulted], r13d
0x180007f79  mov     [rbp+0F0h+pDacl], r13
0x180007f7d  call    cs:__imp_GetSecurityDescriptorDacl
0x180007f83  test    eax, eax
0x180007f85  jz      loc_1800083B0
0x180007f8b  movaps  xmm0, xmmword ptr cs:aUsersSSoftware_0; "USERS\\%s\\Software\\Microsoft\\EventSy"...
0x180007f92  lea     eax, [r15+28h]
0x180007f96  movaps  xmm1, xmmword ptr cs:aUsersSSoftware_0+10h; "\\Software\\Microsoft\\EventSystem"
0x180007f9d  movaps  xmmword ptr [rbp+0F0h+var_A0], xmm0
0x180007fa1  movaps  xmm0, xmmword ptr cs:aUsersSSoftware_0+20h; "e\\Microsoft\\EventSystem"
0x180007fa8  movaps  [rbp+0F0h+var_80], xmm0
0x180007fac  movaps  xmm0, xmmword ptr cs:aUsersSSoftware_0+40h; "tSystem"
0x180007fb3  movaps  [rbp+0F0h+var_90], xmm1
0x180007fb7  movaps  xmm1, xmmword ptr cs:aUsersSSoftware_0+30h; "oft\\EventSystem"
0x180007fbe  movaps  xmmword ptr [rbp+0F0h+var_60], xmm0
0x180007fc5  movaps  [rbp+0F0h+var_70], xmm1
0x180007fcc  cmp     eax, 28h ; '('
0x180007fcf  jb      short loc_180007FE1
0x180007fd1  lea     rsi, [rax+rax]
0x180007fd5  mov     r14d, eax
0x180007fd8  cmp     rsi, rdi
0x180007fdb  jbe     loc_1800081A7
0x180007fe1  mov     ebx, 80070216h
0x180007fe6  jmp     loc_180008121
0x180007feb  mov     rcx, [rbp+0F0h+pDacl]
0x180007fef  xor     r9d, r9d; psidOwner
0x180007ff2  mov     [rsp+140h+lpSecurityAttributes], r13; pSacl
0x180007ff7  mov     qword ptr [rsp+140h+samDesired], rcx; pDacl
0x180007ffc  mov     rcx, rdi; pObjectName
0x180007fff  mov     qword ptr [rsp+140h+dwOptions], r13; psidGroup
0x180008004  lea     esi, [r9+4]
0x180008008  mov     r8d, esi; SecurityInfo
0x18000800b  mov     edx, esi; ObjectType
0x18000800d  call    cs:__imp_SetNamedSecurityInfoW
0x180008013  test    eax, eax
0x180008015  jnz     loc_1800083CE
0x18000801b  test    rdi, rdi
0x18000801e  jnz     loc_180008245
0x180008024  mov     edi, 0FFFFFFFFh
0x180008029  test    ebx, ebx
0x18000802b  js      loc_180008121
0x180008031  mov     rcx, [rbp+0F0h+hKey]; hKey
0x180008035  lea     rax, [rbp+0F0h+dwDisposition]
0x180008039  mov     [rsp+140h+lpdwDisposition], rax; lpdwDisposition
0x18000803e  lea     rdx, a26c409ccAe8611; "{26c409cc-ae86-11d1-b616-00805fc79216}"
0x180008045  lea     rax, [rbp+0F0h+var_D0]
0x180008049  mov     [rbp+0F0h+var_D0], r13
0x18000804d  mov     [rsp+140h+phkResult], rax; phkResult
0x180008052  xor     r9d, r9d; lpClass
0x180008055  lea     rax, [rbp+0F0h+SecurityDescriptor]
0x180008059  xor     r8d, r8d; Reserved
0x18000805c  mov     [rsp+140h+lpSecurityAttributes], rax; lpSecurityAttributes
0x180008061  mov     [rsp+140h+samDesired], 20006h; samDesired
0x180008069  mov     [rsp+140h+dwOptions], r13d; dwOptions
0x18000806e  call    cs:__imp_RegCreateKeyExW
0x180008074  test    eax, eax
0x180008076  jnz     loc_18000841A
0x18000807c  cmp     [rbp+0F0h+dwDisposition], 2
0x180008080  jnz     loc_180008117
0x180008086  mov     rcx, [rbp+0F0h+SecurityDescriptor+8]; pSecurityDescriptor
0x18000808a  lea     r9, [rbp+0F0h+StringSecurityDescriptor]; lpbDaclDefaulted
0x18000808e  lea     r8, [rbp+0F0h+pDacl]; pDacl
0x180008092  mov     [rbp+0F0h+bDaclDefaulted], r13d
0x180008096  lea     rdx, [rbp+0F0h+bDaclDefaulted]; lpbDaclPresent
0x18000809a  mov     dword ptr [rbp+0F0h+StringSecurityDescriptor], r13d
0x18000809e  mov     [rbp+0F0h+pDacl], r13
0x1800080a2  call    cs:__imp_GetSecurityDescriptorDacl
0x1800080a8  test    eax, eax
0x1800080aa  jz      loc_1800083E5
0x1800080b0  movaps  xmm0, xmmword ptr cs:aUsersSSoftware; "USERS\\%s\\Software\\Microsoft\\EventSy"...
0x1800080b7  lea     eax, [r15+52h]
0x1800080bb  movaps  xmm1, xmmword ptr cs:aUsersSSoftware+10h; "\\Software\\Microsoft\\EventSystem\\%s"
0x1800080c2  movaps  xmmword ptr [rbp+0F0h+var_A0], xmm0
0x1800080c6  movaps  xmm0, xmmword ptr cs:aUsersSSoftware+20h; "e\\Microsoft\\EventSystem\\%s"
0x1800080cd  movaps  [rbp+0F0h+var_90], xmm1
0x1800080d1  movaps  xmm1, xmmword ptr cs:aUsersSSoftware+30h; "oft\\EventSystem\\%s"
0x1800080d8  movaps  [rbp+0F0h+var_80], xmm0
0x1800080dc  movaps  xmm0, xmmword ptr cs:aUsersSSoftware+40h; "tSystem\\%s"
0x1800080e3  movaps  [rbp+0F0h+var_70], xmm1
0x1800080ea  movsd   xmm1, qword ptr cs:aUsersSSoftware+4Eh; "\\%s"
0x1800080f2  movaps  xmmword ptr [rbp+0F0h+var_60], xmm0
0x1800080f9  movsd   qword ptr [rbp+0F0h+var_60+0Eh], xmm1
0x180008101  cmp     eax, 52h ; 'R'
0x180008104  jb      short loc_180008112
0x180008106  lea     rsi, [rax+rax]
0x18000810a  mov     r14d, eax
0x18000810d  cmp     rsi, rdi
0x180008110  jbe     short loc_180008160
0x180008112  mov     ebx, 80070216h
0x180008117  mov     rcx, [rbp+0F0h+var_D0]; hKey
0x18000811b  call    cs:__imp_RegCloseKey
0x180008121  mov     rcx, [rbp+0F0h+hKey]; hKey
0x180008125  call    cs:__imp_RegCloseKey
0x18000812b  mov     rcx, [rbp+0F0h+SecurityDescriptor+8]; hMem
0x18000812f  call    cs:__imp_LocalFree
0x180008135  mov     eax, ebx
0x180008137  mov     rcx, [rbp+0F0h+var_40]
0x18000813e  xor     rcx, rbp; StackCookie
0x180008141  call    __security_check_cookie
0x180008146  mov     rbx, [rbp+0F0h+arg_18]
0x18000814d  lea     rsp, [rbp+0C0h]
0x180008154  pop     r15
0x180008156  pop     r14
0x180008158  pop     r13
0x18000815a  pop     r12
0x18000815c  pop     rdi
0x18000815d  pop     rsi
0x18000815e  pop     rbp
0x18000815f  retn
0x180008160  mov     rdi, r13
0x180008163  test    esi, esi
0x180008165  jnz     loc_180008326
0x18000816b  mov     eax, esi
0x18000816d  lea     rcx, [rax+8]
0x180008171  cmp     rcx, rax
0x180008174  jb      short loc_180008194
0x180008176  mov     rax, cs:g_pfnAllocate
0x18000817d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008182  mov     rdi, rax
0x180008185  test    rax, rax
0x180008188  jz      short loc_18000819D
0x18000818a  mov     dword ptr [rax], 70616548h
0x180008190  add     rdi, 8
0x180008194  test    rdi, rdi
0x180008197  jnz     loc_180008277
0x18000819d  mov     ebx, 8007000Eh
0x1800081a2  jmp     loc_180008117
0x1800081a7  mov     rdi, r13
0x1800081aa  test    esi, esi
0x1800081ac  jz      loc_180008448
0x1800081b2  mov     ebx, esi
0x1800081b4  cmp     rbx, cs:g_ulMaxStackAllocSize
0x1800081bb  ja      loc_180008448
0x1800081c1  mov     rcx, cs:g_ulAdditionalProbeSize
0x1800081c8  add     rcx, 8
0x1800081cc  add     rcx, rbx
0x1800081cf  cmp     rcx, rbx
0x1800081d2  jb      loc_180008448
0x1800081d8  call    VerifyStackAvailable
0x1800081dd  test    eax, eax
0x1800081df  jz      loc_180008448
0x1800081e5  lea     rax, [rbx+8]
0x1800081e9  lea     rcx, [rax+0Fh]
0x1800081ed  cmp     rcx, rax
0x1800081f0  ja      short loc_1800081FC
0x1800081f2  mov     rcx, 0FFFFFFFFFFFFFF0h
0x1800081fc  and     rcx, 0FFFFFFFFFFFFFFF0h
0x180008200  mov     rax, rcx
0x180008203  call    _alloca_probe
0x180008208  sub     rsp, rcx
0x18000820b  lea     rdi, [rsp+140h+dwDisposition]
0x180008210  test    rdi, rdi
0x180008213  jz      loc_180008448
0x180008219  mov     dword ptr [rdi], 6B637453h
0x18000821f  add     rdi, 8
0x180008223  jz      loc_180008448
0x180008229  mov     r9, r12
0x18000822c  lea     r8, [rbp+0F0h+var_A0]; unsigned __int16 *
0x180008230  mov     rdx, r14; unsigned __int64
0x180008233  mov     rcx, rdi; unsigned __int16 *
0x180008236  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000823b  mov     ebx, eax
0x18000823d  test    eax, eax
0x18000823f  jns     loc_180007FEB
0x180008245  cmp     dword ptr [rdi-8], 70616548h
0x18000824c  jnz     loc_18000847E
0x180008252  mov     rax, cs:g_pfnFree
0x180008259  lea     rcx, [rdi-8]
0x18000825d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008262  jmp     loc_180008024
0x180008267  mov     dword ptr [rdi], 6B637453h
0x18000826d  add     rdi, 8
0x180008271  jz      loc_18000816B
0x180008277  lea     rax, a26c409ccAe8611; "{26c409cc-ae86-11d1-b616-00805fc79216}"
0x18000827e  mov     r9, r12
0x180008281  lea     r8, [rbp+0F0h+var_A0]; unsigned __int16 *
0x180008285  mov     qword ptr [rsp+140h+dwOptions], rax
0x18000828a  mov     rdx, r14; unsigned __int64
0x18000828d  mov     rcx, rdi; unsigned __int16 *
0x180008290  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180008295  mov     ebx, eax
0x180008297  test    eax, eax
0x180008299  js      short loc_1800082D4
0x18000829b  mov     rax, [rbp+0F0h+pDacl]
0x18000829f  xor     r9d, r9d; psidOwner
0x1800082a2  mov     [rsp+140h+lpSecurityAttributes], r13; pSacl
0x1800082a7  mov     rcx, rdi; pObjectName
0x1800082aa  mov     qword ptr [rsp+140h+samDesired], rax; pDacl
0x1800082af  mov     qword ptr [rsp+140h+dwOptions], r13; psidGroup
0x1800082b4  lea     eax, [r9+4]
0x1800082b8  mov     r8d, eax; SecurityInfo
0x1800082bb  mov     edx, eax; ObjectType
0x1800082bd  call    cs:__imp_SetNamedSecurityInfoW
0x1800082c3  test    eax, eax
0x1800082c5  jnz     loc_180008403
0x1800082cb  test    rdi, rdi
0x1800082ce  jz      loc_180008117
0x1800082d4  lea     rcx, [rdi-8]
0x1800082d8  mov     eax, [rcx]
0x1800082da  cmp     eax, 70616548h
0x1800082df  jz      loc_1800084AE
0x1800082e5  cmp     eax, 6B637453h
0x1800082ea  jz      loc_180008117
0x1800082f0  mov     r8d, 10h; unsigned __int16
0x1800082f6  lea     r9, aSafeallocaHead; "*(SAFEALLOCA_HEADER *) (Tag) == ((SAFEA"...
0x1800082fd  mov     edx, 370h; unsigned int
0x180008302  lea     rcx, aComComplusSrcE_8; "com\\complus\\src\\events\\tier2\\servi"...
0x180008309  call    ?InternalAssert@@YA_NPEBGKG0@Z; InternalAssert(ushort const *,ulong,ushort,ushort const *)
0x18000830e  jmp     loc_180008117
0x180008313  test    rdi, rdi
0x180008316  jnz     loc_180008229
0x18000831c  mov     ebx, 8007000Eh
0x180008321  jmp     loc_180008121
0x180008326  mov     ebx, esi
0x180008328  cmp     rbx, cs:g_ulMaxStackAllocSize
0x18000832f  ja      loc_18000816B
0x180008335  mov     rcx, cs:g_ulAdditionalProbeSize
0x18000833c  add     rcx, 8
0x180008340  add     rcx, rbx
0x180008343  cmp     rcx, rbx
0x180008346  jb      loc_18000816B
0x18000834c  call    VerifyStackAvailable
0x180008351  test    eax, eax
0x180008353  jz      loc_18000816B
0x180008359  lea     rax, [rbx+8]
0x18000835d  lea     rcx, [rax+0Fh]
0x180008361  cmp     rcx, rax
0x180008364  ja      short loc_180008370
0x180008366  mov     rcx, 0FFFFFFFFFFFFFF0h
0x180008370  and     rcx, 0FFFFFFFFFFFFFFF0h
0x180008374  mov     rax, rcx
0x180008377  call    _alloca_probe
0x18000837c  sub     rsp, rcx
0x18000837f  lea     rdi, [rsp+140h+dwDisposition]
  ... truncated ...
```
