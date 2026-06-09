# CW32System::SkipObjectData(void)

- ea: `0x180090900`
- end: `0x180090c06`
- name: `?SkipObjectData@CW32System@@SAHXZ`
- size: `774`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800026c0`

## callees

- `0x1800233dc`
- `0x180037760`
- `0x18004180c`
- `0x18004c348`
- `0x180090900`
- `0x180091140`

## import_xrefs

- `ADVAPI32!RegEnumKeyExA` at `0x180090a5b`
- `ADVAPI32!RegEnumKeyExA` at `0x180090a5b`
- `ADVAPI32!RegOpenKeyExW` at `0x1800909d2`
- `ADVAPI32!RegOpenKeyExW` at `0x180090b14`
- `ADVAPI32!RegOpenKeyExW` at `0x1800909d2`
- `ADVAPI32!RegOpenKeyExW` at `0x180090b14`
- `ADVAPI32!RegOpenKeyExA` at `0x1800909e1`
- `ADVAPI32!RegOpenKeyExA` at `0x180090b21`
- `ADVAPI32!RegOpenKeyExA` at `0x1800909e1`
- `ADVAPI32!RegOpenKeyExA` at `0x180090b21`
- `ADVAPI32!RegEnumKeyExW` at `0x180090a30`
- `ADVAPI32!RegEnumKeyExW` at `0x180090a30`
- `ADVAPI32!RegQueryValueExA` at `0x180090b7d`
- `ADVAPI32!RegQueryValueExA` at `0x180090b7d`
- `ADVAPI32!RegCloseKey` at `0x180090b9d`
- `ADVAPI32!RegCloseKey` at `0x180090bab`
- `ADVAPI32!RegCloseKey` at `0x180090b9d`
- `ADVAPI32!RegCloseKey` at `0x180090bab`
- `ADVAPI32!RegQueryValueExW` at `0x180090b6e`
- `ADVAPI32!RegQueryValueExW` at `0x180090b6e`

## pseudocode

```c
__int64 __fastcall CW32System::SkipObjectData(__int64 a1, __int64 a2, unsigned int a3)
{
  unsigned __int8 v3; // bl
  unsigned int ModuleFileName; // eax
  int v5; // esi
  unsigned __int16 *v6; // rdi
  int v8; // r15d
  DWORD i; // r14d
  __int64 v10; // rcx
  __int64 v11; // rdx
  DWORD v12; // eax
  unsigned __int64 v13; // rdx
  LSTATUS v14; // eax
  DWORD v17; // [rsp+40h] [rbp-C0h] BYREF
  DWORD cchName; // [rsp+44h] [rbp-BCh] BYREF
  HKEY hKey; // [rsp+48h] [rbp-B8h] BYREF
  DWORD cbData; // [rsp+50h] [rbp-B0h] BYREF
  DWORD Type; // [rsp+54h] [rbp-ACh] BYREF
  HKEY phkResult; // [rsp+58h] [rbp-A8h] BYREF
  CHAR SubKey[272]; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR Name[264]; // [rsp+170h] [rbp+70h] BYREF
  unsigned __int16 v25[264]; // [rsp+380h] [rbp+280h] BYREF

  if ( CW32System::_fCheckExe )
    return CW32System::_fSkipObjectData;
  v3 = 1;
  CW32System::_fSkipObjectData = 0;
  CW32System::_fCheckExe = 1;
  ModuleFileName = CW32System::GetModuleFileName(0, v25, a3);
  if ( !ModuleFileName )
    return CW32System::_fSkipObjectData;
  v5 = 1;
  v6 = &v25[ModuleFileName];
  if ( 2LL * ModuleFileName )
  {
    while ( *v6 != 92 )
    {
      --v6;
      ++v5;
      if ( v6 == v25 )
        goto LABEL_6;
    }
  }
  else
  {
LABEL_6:
    if ( *v6 != 92 )
      goto LABEL_8;
  }
  --v5;
  ++v6;
LABEL_8:
  if ( !v5 )
    return CW32System::_fSkipObjectData;
  hKey = 0;
  if ( !(CW32System::_dwPlatformId == 2
       ? RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\RtfStreamIn\\ObjectBlocking", 0, 9u, &hKey)
       : RegOpenKeyExA(HKEY_LOCAL_MACHINE, "Software\\Microsoft\\RtfStreamIn\\ObjectBlocking", 0, 9u, &hKey)) )
  {
    v8 = 0;
    for ( i = 0; ; ++i )
    {
      cchName = 260;
      Name[0] = 0;
      if ( CW32System::_dwPlatformId == 2 )
      {
        if ( RegEnumKeyExW(hKey, i, Name, &cchName, 0, 0, 0, 0) )
          break;
        v10 = cchName;
      }
      else
      {
        v17 = 260;
        SubKey[0] = 0;
        if ( RegEnumKeyExA(hKey, i, SubKey, &v17, 0, 0, 0, 0) )
          break;
        v12 = CW32System::MBTWC(0, v11, SubKey, v17, Name, 260, 0);
        v10 = v12;
        cchName = v12;
      }
      if ( !(_DWORD)v10 )
        break;
      if ( (unsigned int)v10 >= 0x103 )
      {
        v10 = 259;
        cchName = 259;
      }
      v13 = 2LL * (unsigned int)v10;
      if ( v13 >= 0x208 )
        _report_rangecheckfailure(v10, v13);
      Name[(unsigned int)v10] = 0;
      if ( (_DWORD)v10 + 1 == v5 && !(unsigned int)CW32System::lstrcmpi(v6, Name) )
      {
        phkResult = 0;
        CW32System::_fSkipObjectData = 1;
        if ( CW32System::_dwPlatformId == 2 )
          v14 = RegOpenKeyExW(hKey, Name, 0, 1u, &phkResult);
        else
          v14 = RegOpenKeyExA(hKey, SubKey, 0, 1u, &phkResult);
        if ( !v14 )
        {
          Type = 0;
          v17 = 0;
          cbData = 4;
          if ( !(CW32System::_dwPlatformId == 2
               ? RegQueryValueExW(phkResult, L"SkipObjects", 0, &Type, (LPBYTE)&v17, &cbData)
               : RegQueryValueExA(phkResult, "SkipObjects", 0, &Type, (LPBYTE)&v17, &cbData)) )
            CW32System::_fSkipObjectData = v17 & 1;
        }
        if ( phkResult )
          RegCloseKey(phkResult);
        v8 = 1;
        break;
      }
    }
    RegCloseKey(hKey);
    if ( v8 )
      return CW32System::_fSkipObjectData;
  }
  if ( v5 != 12 || (unsigned int)CW32System::lstrcmpi(v6, L"OUTLOOK.EXE") )
    return CW32System::_fSkipObjectData;
  CW32System::_fSkipObjectData = 1;
  return v3;
}

```

## disassembly

```asm
0x180090900  push    rbp
0x180090902  push    rbx
0x180090903  push    rsi
0x180090904  push    rdi
0x180090905  push    r12
0x180090907  push    r14
0x180090909  push    r15
0x18009090b  lea     rbp, [rsp-4A0h]
0x180090913  sub     rsp, 5A0h
0x18009091a  mov     rax, cs:__security_cookie
0x180090921  xor     rax, rsp
0x180090924  mov     [rbp+4D0h+var_40], rax
0x18009092b  xor     r12d, r12d
0x18009092e  cmp     cs:?_fCheckExe@CW32System@@2EA, r12b; uchar CW32System::_fCheckExe
0x180090935  jnz     loc_180090BDC
0x18009093b  lea     ebx, [r12+1]
0x180090940  mov     cs:?_fSkipObjectData@CW32System@@2EA, r12b; uchar CW32System::_fSkipObjectData
0x180090947  lea     rdx, [rbp+4D0h+var_250]; unsigned __int16 *
0x18009094e  mov     cs:?_fCheckExe@CW32System@@2EA, bl; uchar CW32System::_fCheckExe
0x180090954  xor     ecx, ecx; hModule
0x180090956  call    ?GetModuleFileName@CW32System@@SAKPEAUHINSTANCE__@@PEAGK@Z; CW32System::GetModuleFileName(HINSTANCE__ *,ushort *,ulong)
0x18009095b  test    eax, eax
0x18009095d  jz      loc_180090BDC
0x180090963  mov     eax, eax
0x180090965  lea     rdi, [rbp+4D0h+var_250]
0x18009096c  add     rax, rax
0x18009096f  mov     esi, ebx
0x180090971  lea     rdi, [rdi+rax]
0x180090975  jz      short loc_18009098F
0x180090977  cmp     word ptr [rdi], 5Ch ; '\'
0x18009097b  jz      short loc_180090995
0x18009097d  sub     rdi, 2
0x180090981  lea     rax, [rbp+4D0h+var_250]
0x180090988  add     esi, ebx
0x18009098a  cmp     rdi, rax
0x18009098d  jnz     short loc_180090977
0x18009098f  cmp     word ptr [rdi], 5Ch ; '\'
0x180090993  jnz     short loc_18009099B
0x180090995  dec     esi
0x180090997  add     rdi, 2
0x18009099b  test    esi, esi
0x18009099d  jz      loc_180090BDC
0x1800909a3  xor     r8d, r8d; ulOptions
0x1800909a6  mov     [rsp+5D0h+hKey], r12
0x1800909ab  cmp     cs:?_dwPlatformId@CW32System@@0KA, 2; ulong CW32System::_dwPlatformId
0x1800909b2  lea     rax, [rsp+5D0h+hKey]
0x1800909b7  mov     r9d, 9; samDesired
0x1800909bd  mov     [rsp+5D0h+phkResult], rax; phkResult
0x1800909c2  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800909c9  jnz     short loc_1800909DA
0x1800909cb  lea     rdx, aSoftwareMicros; "Software\\Microsoft\\RtfStreamIn\\Objec"...
0x1800909d2  call    cs:__imp_RegOpenKeyExW
0x1800909d8  jmp     short loc_1800909E7
0x1800909da  lea     rdx, aSoftwareMicros_0; "Software\\Microsoft\\RtfStreamIn\\Objec"...
0x1800909e1  call    cs:__imp_RegOpenKeyExA
0x1800909e7  test    eax, eax
0x1800909e9  jnz     loc_180090BB6
0x1800909ef  mov     r15d, r12d
0x1800909f2  mov     r14d, r12d
0x1800909f5  cmp     cs:?_dwPlatformId@CW32System@@0KA, 2; ulong CW32System::_dwPlatformId
0x1800909fc  mov     edx, r14d; dwIndex
0x1800909ff  mov     rcx, [rsp+5D0h+hKey]; hKey
0x180090a04  mov     [rsp+5D0h+lpftLastWriteTime], r12; lpftLastWriteTime
0x180090a09  mov     [rsp+5D0h+lpcchClass], r12; lpcchClass
0x180090a0e  mov     [rsp+5D0h+lpClass], r12; lpClass
0x180090a13  mov     [rsp+5D0h+phkResult], r12; lpReserved
0x180090a18  mov     [rsp+5D0h+cchName], 104h
0x180090a20  mov     [rbp+4D0h+Name], r12w
0x180090a25  jnz     short loc_180090A44
0x180090a27  lea     r9, [rsp+5D0h+cchName]; lpcchName
0x180090a2c  lea     r8, [rbp+4D0h+Name]; lpName
0x180090a30  call    cs:__imp_RegEnumKeyExW
0x180090a36  test    eax, eax
0x180090a38  jnz     loc_180090BA6
0x180090a3e  mov     ecx, [rsp+5D0h+cchName]
0x180090a42  jmp     short loc_180090A96
0x180090a44  lea     r9, [rsp+5D0h+var_590]; lpcchName
0x180090a49  mov     [rsp+5D0h+var_590], 104h
0x180090a51  lea     r8, [rsp+5D0h+SubKey]; lpName
0x180090a56  mov     [rsp+5D0h+SubKey], r12b
0x180090a5b  call    cs:__imp_RegEnumKeyExA
0x180090a61  test    eax, eax
0x180090a63  jnz     loc_180090BA6
0x180090a69  mov     r9d, [rsp+5D0h+var_590]; int
0x180090a6e  lea     rax, [rbp+4D0h+Name]
0x180090a72  mov     [rsp+5D0h+lpcchClass], r12; int *
0x180090a77  lea     r8, [rsp+5D0h+SubKey]; char *
0x180090a7c  mov     dword ptr [rsp+5D0h+lpClass], 104h; int
0x180090a84  xor     ecx, ecx; int
0x180090a86  mov     [rsp+5D0h+phkResult], rax; LPWSTR
0x180090a8b  call    ?MBTWC@CW32System@@SAHHKPEBDHPEAGHPEAH@Z; CW32System::MBTWC(int,ulong,char const *,int,ushort *,int,int *)
0x180090a90  mov     ecx, eax
0x180090a92  mov     [rsp+5D0h+cchName], eax
0x180090a96  test    ecx, ecx
0x180090a98  jz      loc_180090BA6
0x180090a9e  cmp     ecx, 103h
0x180090aa4  jb      short loc_180090AAF
0x180090aa6  mov     ecx, 103h
0x180090aab  mov     [rsp+5D0h+cchName], ecx
0x180090aaf  mov     eax, ecx
0x180090ab1  lea     rdx, [rax+rax]
0x180090ab5  cmp     rdx, 208h
0x180090abc  jnb     loc_180090BD6
0x180090ac2  lea     eax, [rcx+1]
0x180090ac5  mov     [rbp+rdx+4D0h+Name], r12w
0x180090acb  cmp     eax, esi
0x180090acd  jnz     short loc_180090ADF
0x180090acf  lea     rdx, [rbp+4D0h+Name]; unsigned __int16 *
0x180090ad3  mov     rcx, rdi; unsigned __int16 *
0x180090ad6  call    ?lstrcmpi@CW32System@@SAHPEBG0@Z; CW32System::lstrcmpi(ushort const *,ushort const *)
0x180090adb  test    eax, eax
0x180090add  jz      short loc_180090AE7
0x180090adf  add     r14d, ebx
0x180090ae2  jmp     loc_1800909F5
0x180090ae7  mov     rcx, [rsp+5D0h+hKey]; hKey
0x180090aec  lea     rax, [rsp+5D0h+var_578]
0x180090af1  xor     r8d, r8d; ulOptions
0x180090af4  mov     [rsp+5D0h+var_578], r12
0x180090af9  cmp     cs:?_dwPlatformId@CW32System@@0KA, 2; ulong CW32System::_dwPlatformId
0x180090b00  mov     r9d, ebx; samDesired
0x180090b03  mov     cs:?_fSkipObjectData@CW32System@@2EA, bl; uchar CW32System::_fSkipObjectData
0x180090b09  mov     [rsp+5D0h+phkResult], rax; phkResult
0x180090b0e  jnz     short loc_180090B1C
0x180090b10  lea     rdx, [rbp+4D0h+Name]; lpSubKey
0x180090b14  call    cs:__imp_RegOpenKeyExW
0x180090b1a  jmp     short loc_180090B27
0x180090b1c  lea     rdx, [rsp+5D0h+SubKey]; lpSubKey
0x180090b21  call    cs:__imp_RegOpenKeyExA
0x180090b27  test    eax, eax
0x180090b29  jnz     short loc_180090B93
0x180090b2b  mov     rcx, [rsp+5D0h+var_578]; hKey
0x180090b30  lea     rax, [rsp+5D0h+cbData]
0x180090b35  mov     [rsp+5D0h+lpClass], rax; lpcbData
0x180090b3a  lea     r9, [rsp+5D0h+Type]; lpType
0x180090b3f  xor     r8d, r8d; lpReserved
0x180090b42  mov     [rsp+5D0h+Type], r12d
0x180090b47  cmp     cs:?_dwPlatformId@CW32System@@0KA, 2; ulong CW32System::_dwPlatformId
0x180090b4e  lea     rax, [rsp+5D0h+var_590]
0x180090b53  mov     [rsp+5D0h+phkResult], rax; lpData
0x180090b58  mov     [rsp+5D0h+var_590], r12d
0x180090b5d  mov     [rsp+5D0h+cbData], 4
0x180090b65  jnz     short loc_180090B76
0x180090b67  lea     rdx, aSkipobjects_0; "SkipObjects"
0x180090b6e  call    cs:__imp_RegQueryValueExW
0x180090b74  jmp     short loc_180090B83
0x180090b76  lea     rdx, aSkipobjects; "SkipObjects"
0x180090b7d  call    cs:__imp_RegQueryValueExA
0x180090b83  test    eax, eax
0x180090b85  jnz     short loc_180090B93
0x180090b87  mov     al, byte ptr [rsp+5D0h+var_590]
0x180090b8b  and     al, bl
0x180090b8d  mov     cs:?_fSkipObjectData@CW32System@@2EA, al; uchar CW32System::_fSkipObjectData
0x180090b93  mov     rcx, [rsp+5D0h+var_578]; hKey
0x180090b98  test    rcx, rcx
0x180090b9b  jz      short loc_180090BA3
0x180090b9d  call    cs:__imp_RegCloseKey
0x180090ba3  mov     r15d, ebx
0x180090ba6  mov     rcx, [rsp+5D0h+hKey]; hKey
0x180090bab  call    cs:__imp_RegCloseKey
0x180090bb1  test    r15d, r15d
0x180090bb4  jnz     short loc_180090BDC
0x180090bb6  cmp     esi, 0Ch
0x180090bb9  jnz     short loc_180090BDC
0x180090bbb  lea     rdx, aOutlookExe; "OUTLOOK.EXE"
0x180090bc2  mov     rcx, rdi; unsigned __int16 *
0x180090bc5  call    ?lstrcmpi@CW32System@@SAHPEBG0@Z; CW32System::lstrcmpi(ushort const *,ushort const *)
0x180090bca  test    eax, eax
0x180090bcc  jnz     short loc_180090BDC
0x180090bce  mov     cs:?_fSkipObjectData@CW32System@@2EA, bl; uchar CW32System::_fSkipObjectData
0x180090bd4  jmp     short loc_180090BE2
0x180090bd6  call    __report_rangecheckfailure
0x180090bdc  mov     bl, cs:?_fSkipObjectData@CW32System@@2EA; uchar CW32System::_fSkipObjectData
0x180090be2  movzx   eax, bl
0x180090be5  mov     rcx, [rbp+4D0h+var_40]
0x180090bec  xor     rcx, rsp; StackCookie
0x180090bef  call    __security_check_cookie
0x180090bf4  add     rsp, 5A0h
0x180090bfb  pop     r15
0x180090bfd  pop     r14
0x180090bff  pop     r12
0x180090c01  pop     rdi
0x180090c02  pop     rsi
0x180090c03  pop     rbx
0x180090c04  pop     rbp
0x180090c05  retn
```
