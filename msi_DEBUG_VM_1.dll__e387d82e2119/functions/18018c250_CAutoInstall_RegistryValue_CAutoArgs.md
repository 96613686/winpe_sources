# CAutoInstall::RegistryValue(CAutoArgs &)

- ea: `0x18018c250`
- end: `0x18018c9c4`
- name: `?RegistryValue@CAutoInstall@@QEAAJAEAVCAutoArgs@@@Z`
- size: `1908`
- prototype: `int(CAutoInstall *__hidden this, struct CAutoArgs *)`
- caller_count: `0`
- callee_count: `16`
- tags: `file_ops, registry_config, installer_update`

## callees

- `0x180025688`
- `0x18004ceb0`
- `0x180050cf0`
- `0x180061334`
- `0x1800620e4`
- `0x18016c98c`
- `0x18016c9c8`
- `0x1801857fc`
- `0x1801860a8`
- `0x180188e44`
- `0x180189080`
- `0x180189b10`
- `0x18018b030`
- `0x18018c250`
- `0x18025ab12`
- `0x18025ab80`

## import_xrefs

- `ADVAPI32!RegEnumKeyExW` at `0x18018c6fb`
- `ADVAPI32!RegEnumKeyExW` at `0x18018c6fb`
- `ADVAPI32!RegEnumValueW` at `0x18018c64d`
- `ADVAPI32!RegEnumValueW` at `0x18018c64d`
- `ADVAPI32!RegQueryInfoKeyW` at `0x18018c54a`
- `ADVAPI32!RegQueryInfoKeyW` at `0x18018c5c9`
- `ADVAPI32!RegQueryInfoKeyW` at `0x18018c54a`
- `ADVAPI32!RegQueryInfoKeyW` at `0x18018c5c9`
- `ADVAPI32!RegOpenKeyExW` at `0x18018c486`
- `ADVAPI32!RegOpenKeyExW` at `0x18018c486`
- `ADVAPI32!RegConnectRegistryW` at `0x18018c3a3`
- `ADVAPI32!RegConnectRegistryW` at `0x18018c3a3`
- `ADVAPI32!RegCloseKey` at `0x18018c3e2`
- `ADVAPI32!RegCloseKey` at `0x18018c497`
- `ADVAPI32!RegCloseKey` at `0x18018c4b6`
- `ADVAPI32!RegCloseKey` at `0x18018c50c`
- `ADVAPI32!RegCloseKey` at `0x18018c5d6`
- `ADVAPI32!RegCloseKey` at `0x18018c68a`
- `ADVAPI32!RegCloseKey` at `0x18018c708`
- `ADVAPI32!RegCloseKey` at `0x18018c75a`
- `ADVAPI32!RegCloseKey` at `0x18018c79a`
- `ADVAPI32!RegCloseKey` at `0x18018c3e2`
- `ADVAPI32!RegCloseKey` at `0x18018c497`
- `ADVAPI32!RegCloseKey` at `0x18018c4b6`
- `ADVAPI32!RegCloseKey` at `0x18018c50c`
- `ADVAPI32!RegCloseKey` at `0x18018c5d6`
- `ADVAPI32!RegCloseKey` at `0x18018c68a`
- `ADVAPI32!RegCloseKey` at `0x18018c708`
- `ADVAPI32!RegCloseKey` at `0x18018c75a`
- `ADVAPI32!RegCloseKey` at `0x18018c79a`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x18018c87a`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x18018c87a`

## string_xrefs

- `0x18018c910`: `(REG_FULL_RESOURCE_DESCRIPTOR)`
- `0x18018c945`: `(REG_LINK)`

## pseudocode

```c
__int64 __fastcall CAutoInstall::RegistryValue(CAutoInstall *this, struct CAutoArgs *a2)
{
  unsigned __int16 *v3; // r15
  __int64 v4; // rax
  CVariant *v5; // r10
  char v6; // di
  unsigned int String; // ebx
  __int16 *v8; // rax
  char *v9; // r8
  __int16 v10; // dx
  __int64 v11; // rcx
  CVariant *v12; // rax
  int v13; // esi
  _BYTE *v14; // rax
  CVariant *v15; // r10
  DWORD v16; // eax
  LSTATUS v17; // ebx
  WCHAR *v18; // rax
  HKEY v19; // rcx
  WCHAR *v20; // rbx
  LSTATUS InfoKeyW; // edi
  WCHAR *v22; // rax
  WCHAR *v23; // rdi
  _WORD *v24; // rcx
  _WORD *v25; // rcx
  DWORD v26; // esi
  int Value; // ebx
  size_t v28; // rbx
  int v30; // r15d
  const wchar_t *v31; // rbx
  DWORD v32; // r8d
  WCHAR *v33; // rsi
  DWORD v34; // eax
  _WORD *v35; // rcx
  int v36; // esi
  WCHAR *v37; // rax
  const unsigned __int16 *v38; // rdx
  DWORD cchValueName; // [rsp+60h] [rbp-A0h] BYREF
  HKEY hKey; // [rsp+68h] [rbp-98h] BYREF
  DWORD dwIndex; // [rsp+70h] [rbp-90h] BYREF
  DWORD cchClass[2]; // [rsp+78h] [rbp-88h] BYREF
  DWORD Type; // [rsp+80h] [rbp-80h] BYREF
  int v44; // [rsp+84h] [rbp-7Ch] BYREF
  HKEY phkResult; // [rsp+88h] [rbp-78h] BYREF
  unsigned __int16 *v46; // [rsp+90h] [rbp-70h] BYREF
  LPCWSTR lpSubKey; // [rsp+98h] [rbp-68h] BYREF
  void *Src; // [rsp+A0h] [rbp-60h] BYREF
  int v49; // [rsp+A8h] [rbp-58h]
  int v50; // [rsp+ACh] [rbp-54h]
  char v51; // [rsp+B0h] [rbp-50h] BYREF
  LPWSTR lpDst; // [rsp+B8h] [rbp-48h] BYREF
  DWORD nSize; // [rsp+C0h] [rbp-40h]
  char v54; // [rsp+C8h] [rbp-38h] BYREF
  WCHAR ValueName[136]; // [rsp+D0h] [rbp-30h] BYREF
  WCHAR MachineName[2]; // [rsp+1E0h] [rbp+E0h] BYREF
  char v57; // [rsp+1E4h] [rbp+E4h] BYREF

  v44 = 0;
  phkResult = 0;
  hKey = 0;
  lpSubKey = 0;
  nSize = 1;
  dwIndex = 0x80000000;
  v3 = 0;
  v46 = 0;
  lpDst = (LPWSTR)&v54;
  if ( !(unsigned __int8)CAPITempBuffer<unsigned short,1>::SetSize(&lpDst, 520, 0) )
    goto LABEL_74;
  Type = 0;
  cchValueName = 0;
  v4 = CAutoArgs::operator[](a2, 1);
  if ( (unsigned int)CVariant::IsNumeric(v4) )
  {
    CVariant::GetInt(v5, &v44);
    if ( (v44 & 0x7FFFFFF0) != 0 )
      goto LABEL_35;
    v6 = 0;
    phkResult = (HKEY)(v44 | 0xFFFFFFFF80000000uLL);
    goto LABEL_14;
  }
  *(_QWORD *)cchClass = 0;
  String = CVariant::GetString(v5, (const unsigned __int16 **)cchClass);
  if ( String )
    goto LABEL_75;
  v8 = *(__int16 **)cchClass;
  if ( *(_QWORD *)cchClass )
  {
    *(_DWORD *)MachineName = 6029404;
    v9 = &v57;
    v10 = **(_WORD **)cchClass;
    if ( !**(_WORD **)cchClass )
    {
LABEL_12:
      *(_WORD *)v9 = 0;
      String = RegConnectRegistryW(MachineName, HKEY_LOCAL_MACHINE, &phkResult);
      if ( String )
        goto LABEL_75;
      v6 = 1;
LABEL_14:
      v12 = (CVariant *)CAutoArgs::operator[](a2, 2);
      String = CVariant::GetString(v12, &lpSubKey);
      if ( String )
        goto LABEL_15;
      v13 = 1;
      if ( (unsigned int)CAutoArgs::Present(a2, 3) )
      {
        v14 = (_BYTE *)CAutoArgs::operator[](a2, 3);
        v13 = 0;
        if ( *v14 != 1 )
        {
          if ( (unsigned int)CVariant::IsNumeric(v14) )
          {
            CVariant::GetInt(v15, (int *)&dwIndex);
            if ( dwIndex )
            {
              if ( (int)dwIndex <= 0 )
              {
                v13 = 3;
                v16 = ~dwIndex;
              }
              else
              {
                v13 = 2;
                v16 = dwIndex - 1;
              }
              dwIndex = v16;
            }
            else
            {
              v13 = 4;
            }
          }
          else
          {
            String = CVariant::GetString(v15, (const unsigned __int16 **)&v46);
            if ( String )
            {
LABEL_15:
              if ( v6 )
                RegCloseKey(phkResult);
              goto LABEL_75;
            }
            v3 = v46;
          }
        }
      }
      v17 = RegOpenKeyExW(phkResult, lpSubKey, 0, 9u, &hKey);
      if ( v6 )
        RegCloseKey(phkResult);
      if ( v13 == 1 )
      {
        if ( v17 )
        {
          CAutoArgs::Assign(a2, 0);
        }
        else
        {
          CAutoArgs::Assign(a2, 1);
          RegCloseKey(hKey);
        }
LABEL_120:
        CAPITempBuffer<unsigned short,1>::Destroy(&lpDst);
        return 0;
      }
      if ( v17 )
        goto LABEL_35;
      cchValueName = 130;
      if ( v13 == 4 )
      {
        cchClass[0] = 261;
        v18 = (WCHAR *)operator new(0x20Au);
        v19 = hKey;
        v20 = v18;
        if ( !v18 )
        {
LABEL_38:
          RegCloseKey(v19);
LABEL_74:
          String = -2147024882;
          goto LABEL_75;
        }
        InfoKeyW = RegQueryInfoKeyW(hKey, v18, cchClass, 0, 0, 0, 0, 0, 0, 0, 0, 0);
        if ( InfoKeyW == 234 )
        {
          ++cchClass[0];
          operator delete(v20);
          v22 = (WCHAR *)operator new(saturated_mul(cchClass[0], 2u));
          v19 = hKey;
          v20 = v22;
          if ( !v22 )
            goto LABEL_38;
          InfoKeyW = RegQueryInfoKeyW(hKey, v22, cchClass, 0, 0, 0, 0, 0, 0, 0, 0, 0);
        }
        RegCloseKey(hKey);
        if ( !InfoKeyW )
        {
LABEL_45:
          CAutoArgs::Assign(a2, v20);
          operator delete(v20);
          String = 0;
          goto LABEL_75;
        }
        if ( !cchClass[0] )
        {
          *v20 = 0;
          goto LABEL_45;
        }
        operator delete(v20);
LABEL_35:
        String = -2147352565;
        goto LABEL_75;
      }
      v23 = ValueName;
      if ( v13 == 2 )
      {
        do
        {
          String = RegEnumValueW(hKey, dwIndex, v23, &cchValueName, 0, &Type, 0, 0);
          if ( String != 234 )
            break;
          if ( v23 != ValueName )
            break;
          v23 = (WCHAR *)operator new(saturated_mul(cchValueName, 2u));
        }
        while ( v23 );
        RegCloseKey(hKey);
        if ( String == 259 )
        {
          v24 = (_WORD *)*((_QWORD *)a2 + 3);
          if ( v24 )
            *v24 = 0;
          goto LABEL_117;
        }
        if ( String )
        {
          if ( v23 != ValueName )
            operator delete(v23);
          goto LABEL_75;
        }
        goto LABEL_113;
      }
      if ( v13 == 3 )
      {
        String = RegEnumKeyExW(hKey, dwIndex, ValueName, &cchValueName, 0, 0, 0, 0);
        RegCloseKey(hKey);
        if ( String == 259 )
        {
          v25 = (_WORD *)*((_QWORD *)a2 + 3);
          if ( v25 )
            *v25 = 0;
          goto LABEL_120;
        }
        if ( String )
        {
LABEL_75:
          CAPITempBuffer<unsigned short,1>::Destroy(&lpDst);
          return String;
        }
LABEL_113:
        v38 = v23;
        goto LABEL_116;
      }
      v49 = 1;
      Src = &v51;
      if ( !(unsigned __int8)CAPITempBuffer<unsigned short,1>::SetSize(&Src, 130, 0) )
      {
        RegCloseKey(hKey);
LABEL_73:
        CAPITempBuffer<unsigned short,1>::Destroy(&Src);
        goto LABEL_74;
      }
      v50 = 1;
      cchClass[0] = 2 * v49;
      v26 = 260;
      Value = MsiRegQueryValueExW(hKey, v3, (__int64)&Src, (__int64)cchClass);
      RegCloseKey(hKey);
      if ( Value )
      {
        if ( Value == 14 )
          goto LABEL_73;
        if ( v3 )
        {
          CAPITempBuffer<unsigned short,1>::Destroy(&Src);
          goto LABEL_35;
        }
        Type = 0;
      }
      else
      {
        v28 = cchClass[0];
        if ( cchClass[0] )
        {
          if ( cchClass[0] > 0x104 )
          {
            v26 = cchClass[0];
            v23 = (WCHAR *)operator new(cchClass[0]);
            if ( !v23 )
              goto LABEL_73;
          }
          memcpy_0(v23, Src, v28);
        }
      }
      v30 = 0;
      v31 = 0;
      if ( Type > 5 )
      {
        switch ( Type )
        {
          case 6u:
            v31 = L"(REG_LINK)";
            break;
          case 7u:
            v36 = v26 >> 1;
            v37 = v23;
            if ( (unsigned int)v36 > 2 )
            {
              do
              {
                --v36;
                if ( !*v37 )
                  *v37 = 10;
                ++v37;
              }
              while ( v36 > 2 );
            }
            goto LABEL_93;
          case 8u:
            v31 = L"(REG_RESOURCE_LIST)";
            break;
          case 9u:
            v31 = L"(REG_FULL_RESOURCE_DESCRIPTOR)";
            break;
          case 0xAu:
            v31 = L"(REG_RESOURCE_REQUIREMENTS_LIST)";
            break;
          default:
            v31 = L"(REG_??)";
            break;
        }
      }
      else
      {
        if ( Type == 5 )
        {
          v31 = L"(REG_DWORD_BIG_ENDIAN)";
          goto LABEL_112;
        }
        if ( Type )
        {
          if ( Type != 1 )
          {
            if ( Type != 2 )
            {
              if ( Type == 3 )
                v31 = L"(REG_BINARY)";
              else
                CAutoArgs::Assign(a2, *(_DWORD *)v23);
              goto LABEL_112;
            }
            v32 = nSize;
            v33 = lpDst;
            for ( cchValueName = nSize; ; v32 = cchValueName )
            {
              v34 = ExpandEnvironmentStringsW(v23, v33, v32);
              cchValueName = v34;
              if ( v34 <= nSize )
                break;
              if ( v33 != lpDst )
                break;
              v33 = (WCHAR *)operator new(saturated_mul(v34, 2u));
              if ( !v33 )
                break;
            }
            if ( v23 != ValueName )
              operator delete(v23);
            v23 = v33;
          }
LABEL_93:
          v30 = 1;
          goto LABEL_112;
        }
        v35 = (_WORD *)*((_QWORD *)a2 + 3);
        if ( v35 )
          *v35 = 0;
      }
LABEL_112:
      CAPITempBuffer<unsigned short,1>::Destroy(&Src);
      if ( !v30 )
      {
        if ( !v31 )
        {
LABEL_117:
          if ( v23 != ValueName && v23 != lpDst )
            operator delete(v23);
          goto LABEL_120;
        }
        v38 = v31;
LABEL_116:
        CAutoArgs::Assign(a2, v38);
        goto LABEL_117;
      }
      goto LABEL_113;
    }
    v11 = 258;
    while ( v11 )
    {
      ++v8;
      *(_WORD *)v9 = v10;
      v9 += 2;
      --v11;
      v10 = *v8;
      if ( !*v8 )
      {
        if ( !v11 )
          break;
        goto LABEL_12;
      }
    }
  }
  CAPITempBuffer<unsigned short,1>::Destroy(&lpDst);
  return 2147942487LL;
}

```

## disassembly

```asm
0x18018c250  push    rbp
0x18018c252  push    rbx
0x18018c253  push    rsi
0x18018c254  push    rdi
0x18018c255  push    r12
0x18018c257  push    r13
0x18018c259  push    r14
0x18018c25b  push    r15
0x18018c25d  lea     rbp, [rsp-308h]
0x18018c265  sub     rsp, 408h
0x18018c26c  mov     rax, cs:__security_cookie
0x18018c273  xor     rax, rsp
0x18018c276  mov     [rbp+340h+var_50], rax
0x18018c27d  xor     r12d, r12d
0x18018c280  lea     rax, [rbp+340h+var_378]
0x18018c284  mov     r14, rdx
0x18018c287  mov     [rbp+340h+var_3BC], r12d
0x18018c28b  mov     rbx, 0FFFFFFFF80000000h
0x18018c292  mov     [rbp+340h+phkResult], r12
0x18018c296  xor     r8d, r8d
0x18018c299  mov     [rsp+440h+hKey], r12
0x18018c29e  lea     r13d, [r12+1]
0x18018c2a3  mov     [rbp+340h+lpSubKey], r12
0x18018c2a7  mov     edx, 208h
0x18018c2ac  mov     [rbp+340h+nSize], r13d
0x18018c2b0  lea     rcx, [rbp+340h+lpDst]
0x18018c2b4  mov     [rsp+440h+dwIndex], ebx
0x18018c2b8  mov     r15d, r12d
0x18018c2bb  mov     [rbp+340h+var_3B0], r12
0x18018c2bf  mov     [rbp+340h+lpDst], rax
0x18018c2c3  call    ?SetSize@?$CAPITempBuffer@G$00@@QEAA_NH_N@Z; CAPITempBuffer<ushort,1>::SetSize(int,bool)
0x18018c2c8  test    al, al
0x18018c2ca  jz      loc_18018C7E8
0x18018c2d0  mov     edx, r13d
0x18018c2d3  mov     [rbp+340h+Type], r12d
0x18018c2d7  mov     rcx, r14
0x18018c2da  mov     [rsp+440h+cchValueName], r12d
0x18018c2df  call    ??ACAutoArgs@@QEAAAEAVCVariant@@I@Z; CAutoArgs::operator[](uint)
0x18018c2e4  mov     rcx, rax
0x18018c2e7  mov     r10, rax
0x18018c2ea  call    ?IsNumeric@CVariant@@QEAA?AW4Bool@@XZ; CVariant::IsNumeric(void)
0x18018c2ef  mov     rcx, r10; this
0x18018c2f2  test    eax, eax
0x18018c2f4  jz      short loc_18018C31F
0x18018c2f6  lea     rdx, [rbp+340h+var_3BC]; int *
0x18018c2fa  call    ?GetInt@CVariant@@QEAAJAEAH@Z; CVariant::GetInt(int &)
0x18018c2ff  test    [rbp+340h+var_3BC], 7FFFFFF0h
0x18018c306  jnz     loc_18018C4D1
0x18018c30c  movsxd  rax, [rbp+340h+var_3BC]
0x18018c310  mov     dil, r12b
0x18018c313  or      rax, rbx
0x18018c316  mov     [rbp+340h+phkResult], rax
0x18018c31a  jmp     loc_18018C3B6
0x18018c31f  lea     rdx, [rsp+440h+cchClass]; unsigned __int16 **
0x18018c324  mov     qword ptr [rsp+440h+cchClass], r12
0x18018c329  call    ?GetString@CVariant@@QEAAJAEAPEBG@Z; CVariant::GetString(ushort const * &)
0x18018c32e  mov     ebx, eax
0x18018c330  test    eax, eax
0x18018c332  jnz     loc_18018C7ED
0x18018c338  mov     rax, qword ptr [rsp+440h+cchClass]
0x18018c33d  test    rax, rax
0x18018c340  jz      loc_18018C993
0x18018c346  mov     dword ptr [rbp+340h+MachineName], 5C005Ch
0x18018c350  lea     r8, [rbp+340h+var_25C]
0x18018c357  movzx   edx, word ptr [rax]
0x18018c35a  test    dx, dx
0x18018c35d  jz      short loc_18018C38D
0x18018c35f  mov     ecx, 102h
0x18018c364  test    rcx, rcx
0x18018c367  jz      loc_18018C993
0x18018c36d  add     rax, 2
0x18018c371  mov     [r8], dx
0x18018c375  add     r8, 2
0x18018c379  sub     rcx, r13
0x18018c37c  movzx   edx, word ptr [rax]
0x18018c37f  test    dx, dx
0x18018c382  jnz     short loc_18018C364
0x18018c384  test    rcx, rcx
0x18018c387  jz      loc_18018C993
0x18018c38d  mov     [r8], r12w
0x18018c391  lea     rcx, [rbp+340h+MachineName]; lpMachineName
0x18018c398  lea     r8, [rbp+340h+phkResult]; phkResult
0x18018c39c  mov     rdx, 0FFFFFFFF80000002h; hKey
0x18018c3a3  call    cs:__imp_RegConnectRegistryW
0x18018c3a9  mov     ebx, eax
0x18018c3ab  test    eax, eax
0x18018c3ad  jnz     loc_18018C7ED
0x18018c3b3  mov     dil, r13b
0x18018c3b6  mov     edx, 2
0x18018c3bb  mov     rcx, r14
0x18018c3be  call    ??ACAutoArgs@@QEAAAEAVCVariant@@I@Z; CAutoArgs::operator[](uint)
0x18018c3c3  lea     rdx, [rbp+340h+lpSubKey]; unsigned __int16 **
0x18018c3c7  mov     rcx, rax; this
0x18018c3ca  call    ?GetString@CVariant@@QEAAJAEAPEBG@Z; CVariant::GetString(ushort const * &)
0x18018c3cf  mov     ebx, eax
0x18018c3d1  test    eax, eax
0x18018c3d3  jz      short loc_18018C3ED
0x18018c3d5  test    dil, dil
0x18018c3d8  jz      loc_18018C7ED
0x18018c3de  mov     rcx, [rbp+340h+phkResult]; hKey
0x18018c3e2  call    cs:__imp_RegCloseKey
0x18018c3e8  jmp     loc_18018C7ED
0x18018c3ed  mov     ebx, 3
0x18018c3f2  mov     rcx, r14
0x18018c3f5  mov     edx, ebx
0x18018c3f7  mov     esi, r13d
0x18018c3fa  call    ?Present@CAutoArgs@@QEAA?AW4Bool@@I@Z; CAutoArgs::Present(uint)
0x18018c3ff  test    eax, eax
0x18018c401  jz      short loc_18018C46B
0x18018c403  mov     edx, ebx
0x18018c405  mov     rcx, r14
0x18018c408  call    ??ACAutoArgs@@QEAAAEAVCVariant@@I@Z; CAutoArgs::operator[](uint)
0x18018c40d  mov     r10, rax
0x18018c410  mov     esi, r12d
0x18018c413  cmp     [rax], r13b
0x18018c416  jz      short loc_18018C46B
0x18018c418  mov     rcx, rax
0x18018c41b  call    ?IsNumeric@CVariant@@QEAA?AW4Bool@@XZ; CVariant::IsNumeric(void)
0x18018c420  mov     rcx, r10; this
0x18018c423  test    eax, eax
0x18018c425  jz      short loc_18018C454
0x18018c427  lea     rdx, [rsp+440h+dwIndex]; int *
0x18018c42c  call    ?GetInt@CVariant@@QEAAJAEAH@Z; CVariant::GetInt(int &)
0x18018c431  mov     eax, [rsp+440h+dwIndex]
0x18018c435  test    eax, eax
0x18018c437  jnz     short loc_18018C43E
0x18018c439  lea     esi, [rbx+1]
0x18018c43c  jmp     short loc_18018C46B
0x18018c43e  jle     short loc_18018C44A
0x18018c440  mov     esi, 2
0x18018c445  sub     eax, r13d
0x18018c448  jmp     short loc_18018C44E
0x18018c44a  mov     esi, ebx
0x18018c44c  not     eax
0x18018c44e  mov     [rsp+440h+dwIndex], eax
0x18018c452  jmp     short loc_18018C46B
0x18018c454  lea     rdx, [rbp+340h+var_3B0]; unsigned __int16 **
0x18018c458  call    ?GetString@CVariant@@QEAAJAEAPEBG@Z; CVariant::GetString(ushort const * &)
0x18018c45d  mov     ebx, eax
0x18018c45f  test    eax, eax
0x18018c461  jnz     loc_18018C3D5
0x18018c467  mov     r15, [rbp+340h+var_3B0]
0x18018c46b  mov     rdx, [rbp+340h+lpSubKey]; lpSubKey
0x18018c46f  lea     rax, [rsp+440h+hKey]
0x18018c474  mov     rcx, [rbp+340h+phkResult]; hKey
0x18018c478  mov     r9d, 9; samDesired
0x18018c47e  xor     r8d, r8d; ulOptions
0x18018c481  mov     [rsp+440h+var_420], rax; phkResult
0x18018c486  call    cs:__imp_RegOpenKeyExW
0x18018c48c  mov     ebx, eax
0x18018c48e  test    dil, dil
0x18018c491  jz      short loc_18018C49D
0x18018c493  mov     rcx, [rbp+340h+phkResult]; hKey
0x18018c497  call    cs:__imp_RegCloseKey
0x18018c49d  cmp     esi, r13d
0x18018c4a0  jnz     short loc_18018C4CD
0x18018c4a2  mov     rcx, r14
0x18018c4a5  test    ebx, ebx
0x18018c4a7  jnz     short loc_18018C4C1
0x18018c4a9  mov     edx, r13d
0x18018c4ac  call    ?Assign@CAutoArgs@@QEAAJW4Bool@@@Z; CAutoArgs::Assign(Bool)
0x18018c4b1  mov     rcx, [rsp+440h+hKey]; hKey
0x18018c4b6  call    cs:__imp_RegCloseKey
0x18018c4bc  jmp     loc_18018C986
0x18018c4c1  xor     edx, edx
0x18018c4c3  call    ?Assign@CAutoArgs@@QEAAJW4Bool@@@Z; CAutoArgs::Assign(Bool)
0x18018c4c8  jmp     loc_18018C986
0x18018c4cd  test    ebx, ebx
0x18018c4cf  jz      short loc_18018C4DB
0x18018c4d1  mov     ebx, 8002000Bh
0x18018c4d6  jmp     loc_18018C7ED
0x18018c4db  mov     edx, 82h
0x18018c4e0  mov     [rsp+440h+cchValueName], edx
0x18018c4e4  cmp     esi, 4
0x18018c4e7  jnz     loc_18018C613
0x18018c4ed  mov     ecx, 20Ah; unsigned __int64
0x18018c4f2  mov     [rsp+440h+cchClass], 105h
0x18018c4fa  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18018c4ff  mov     rcx, [rsp+440h+hKey]; hKey
0x18018c504  mov     rbx, rax
0x18018c507  test    rax, rax
0x18018c50a  jnz     short loc_18018C517
0x18018c50c  call    cs:__imp_RegCloseKey
0x18018c512  jmp     loc_18018C7E8
0x18018c517  mov     [rsp+440h+lpftLastWriteTime], r12; lpftLastWriteTime
0x18018c51c  lea     r8, [rsp+440h+cchClass]; lpcchClass
0x18018c521  mov     [rsp+440h+lpcbSecurityDescriptor], r12; lpcbSecurityDescriptor
0x18018c526  xor     r9d, r9d; lpReserved
0x18018c529  mov     [rsp+440h+lpcbMaxValueLen], r12; lpcbMaxValueLen
0x18018c52e  mov     rdx, rbx; lpClass
0x18018c531  mov     [rsp+440h+lpcbMaxValueNameLen], r12; lpcbMaxValueNameLen
0x18018c536  mov     [rsp+440h+lpcValues], r12; lpcValues
0x18018c53b  mov     [rsp+440h+lpcbMaxClassLen], r12; lpcbMaxClassLen
0x18018c540  mov     [rsp+440h+lpcbMaxSubKeyLen], r12; lpcbMaxSubKeyLen
0x18018c545  mov     [rsp+440h+var_420], r12; lpcSubKeys
0x18018c54a  call    cs:__imp_RegQueryInfoKeyW
0x18018c550  mov     edi, eax
0x18018c552  cmp     eax, 0EAh
0x18018c557  jnz     short loc_18018C5D1
0x18018c559  add     [rsp+440h+cchClass], r13d
0x18018c55e  mov     rcx, rbx; void *
0x18018c561  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18018c566  mov     ecx, [rsp+440h+cchClass]
0x18018c56a  mov     eax, 2
0x18018c56f  mul     rcx
0x18018c572  mov     r15, 0FFFFFFFFFFFFFFFFh
0x18018c579  cmovb   rax, r15
0x18018c57d  mov     rcx, rax; unsigned __int64
0x18018c580  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18018c585  mov     rcx, [rsp+440h+hKey]; hKey
0x18018c58a  mov     rbx, rax
0x18018c58d  test    rax, rax
0x18018c590  jz      loc_18018C50C
0x18018c596  mov     [rsp+440h+lpftLastWriteTime], r12; lpftLastWriteTime
0x18018c59b  lea     r8, [rsp+440h+cchClass]; lpcchClass
0x18018c5a0  mov     [rsp+440h+lpcbSecurityDescriptor], r12; lpcbSecurityDescriptor
0x18018c5a5  xor     r9d, r9d; lpReserved
0x18018c5a8  mov     [rsp+440h+lpcbMaxValueLen], r12; lpcbMaxValueLen
0x18018c5ad  mov     rdx, rax; lpClass
0x18018c5b0  mov     [rsp+440h+lpcbMaxValueNameLen], r12; lpcbMaxValueNameLen
0x18018c5b5  mov     [rsp+440h+lpcValues], r12; lpcValues
0x18018c5ba  mov     [rsp+440h+lpcbMaxClassLen], r12; lpcbMaxClassLen
0x18018c5bf  mov     [rsp+440h+lpcbMaxSubKeyLen], r12; lpcbMaxSubKeyLen
0x18018c5c4  mov     [rsp+440h+var_420], r12; lpcSubKeys
0x18018c5c9  call    cs:__imp_RegQueryInfoKeyW
0x18018c5cf  mov     edi, eax
0x18018c5d1  mov     rcx, [rsp+440h+hKey]; hKey
0x18018c5d6  call    cs:__imp_RegCloseKey
0x18018c5dc  test    edi, edi
0x18018c5de  jz      short loc_18018C5EB
0x18018c5e0  cmp     [rsp+440h+cchClass], r12d
0x18018c5e5  jnz     short loc_18018C606
0x18018c5e7  mov     [rbx], r12w
0x18018c5eb  mov     rdx, rbx; unsigned __int16 *
0x18018c5ee  mov     rcx, r14; this
0x18018c5f1  call    ?Assign@CAutoArgs@@QEAAJPEBG@Z; CAutoArgs::Assign(ushort const *)
0x18018c5f6  mov     rcx, rbx; void *
0x18018c5f9  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18018c5fe  mov     ebx, r12d
0x18018c601  jmp     loc_18018C7ED
0x18018c606  mov     rcx, rbx; void *
0x18018c609  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18018c60e  jmp     loc_18018C4D1
0x18018c613  lea     rdi, [rbp+340h+ValueName]
0x18018c617  cmp     esi, 2
0x18018c61a  jnz     loc_18018C6D0
0x18018c620  or      r15, 0FFFFFFFFFFFFFFFFh
0x18018c624  mov     edx, [rsp+440h+dwIndex]; dwIndex
0x18018c628  lea     rax, [rbp+340h+Type]
0x18018c62c  mov     rcx, [rsp+440h+hKey]; hKey
0x18018c631  lea     r9, [rsp+440h+cchValueName]; lpcchValueName
0x18018c636  mov     [rsp+440h+lpcValues], r12; lpcbData
0x18018c63b  mov     r8, rdi; lpValueName
0x18018c63e  mov     [rsp+440h+lpcbMaxClassLen], r12; lpData
0x18018c643  mov     [rsp+440h+lpcbMaxSubKeyLen], rax; lpType
0x18018c648  mov     [rsp+440h+var_420], r12; lpReserved
0x18018c64d  call    cs:__imp_RegEnumValueW
0x18018c653  mov     ebx, eax
0x18018c655  cmp     eax, 0EAh
0x18018c65a  jnz     short loc_18018C685
0x18018c65c  lea     rax, [rbp+340h+ValueName]
0x18018c660  cmp     rdi, rax
0x18018c663  jnz     short loc_18018C685
0x18018c665  mov     ecx, [rsp+440h+cchValueName]
0x18018c669  mov     eax, 2
0x18018c66e  mul     rcx
0x18018c671  cmovb   rax, r15
0x18018c675  mov     rcx, rax; unsigned __int64
0x18018c678  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18018c67d  mov     rdi, rax
0x18018c680  test    rax, rax
0x18018c683  jnz     short loc_18018C624
0x18018c685  mov     rcx, [rsp+440h+hKey]; hKey
0x18018c68a  call    cs:__imp_RegCloseKey
0x18018c690  cmp     ebx, 103h
0x18018c696  jnz     short loc_18018C6AE
0x18018c698  mov     rcx, [r14+18h]
0x18018c69c  test    rcx, rcx
0x18018c69f  jz      loc_18018C96F
0x18018c6a5  mov     [rcx], r12w
0x18018c6a9  jmp     loc_18018C96F
0x18018c6ae  test    ebx, ebx
0x18018c6b0  jz      loc_18018C95A
0x18018c6b6  lea     rax, [rbp+340h+ValueName]
0x18018c6ba  cmp     rdi, rax
0x18018c6bd  jz      loc_18018C7ED
0x18018c6c3  mov     rcx, rdi; void *
0x18018c6c6  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18018c6cb  jmp     loc_18018C7ED
0x18018c6d0  cmp     esi, 3
0x18018c6d3  jnz     short loc_18018C739
0x18018c6d5  mov     edx, [rsp+440h+dwIndex]; dwIndex
0x18018c6d9  lea     r9, [rsp+440h+cchValueName]; lpcchName
0x18018c6de  mov     rcx, [rsp+440h+hKey]; hKey
0x18018c6e3  lea     r8, [rbp+340h+ValueName]; lpName
0x18018c6e7  mov     [rsp+440h+lpcValues], r12; lpftLastWriteTime
0x18018c6ec  mov     [rsp+440h+lpcbMaxClassLen], r12; lpcchClass
0x18018c6f1  mov     [rsp+440h+lpcbMaxSubKeyLen], r12; lpClass
0x18018c6f6  mov     [rsp+440h+var_420], r12; lpReserved
0x18018c6fb  call    cs:__imp_RegEnumKeyExW
  ... truncated ...
```
