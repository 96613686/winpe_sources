# CAutoInstall::RegistryValue(CAutoArgs &)

- ea: `0x1801928e0`
- end: `0x1801930b8`
- name: `?RegistryValue@CAutoInstall@@QEAAJAEAVCAutoArgs@@@Z`
- size: `2008`
- prototype: `int(CAutoInstall *__hidden this, struct CAutoArgs *)`
- caller_count: `0`
- callee_count: `16`
- tags: `file_ops, registry_config, installer_update`

## callees

- `0x180014288`
- `0x180018ee0`
- `0x180019cc0`
- `0x1800399d0`
- `0x18004a014`
- `0x180172a44`
- `0x180172a84`
- `0x18018becc`
- `0x18018c788`
- `0x18018f544`
- `0x18018f780`
- `0x180190220`
- `0x180191700`
- `0x1801928e0`
- `0x1802651d2`
- `0x180265240`

## import_xrefs

- `ADVAPI32!RegEnumKeyExW` at `0x180192dcd`
- `ADVAPI32!RegEnumKeyExW` at `0x180192dcd`
- `ADVAPI32!RegEnumValueW` at `0x180192d13`
- `ADVAPI32!RegEnumValueW` at `0x180192d13`
- `ADVAPI32!RegQueryInfoKeyW` at `0x180192bfe`
- `ADVAPI32!RegQueryInfoKeyW` at `0x180192c83`
- `ADVAPI32!RegQueryInfoKeyW` at `0x180192bfe`
- `ADVAPI32!RegQueryInfoKeyW` at `0x180192c83`
- `ADVAPI32!RegOpenKeyExW` at `0x180192b22`
- `ADVAPI32!RegOpenKeyExW` at `0x180192b22`
- `ADVAPI32!RegConnectRegistryW` at `0x180192a33`
- `ADVAPI32!RegConnectRegistryW` at `0x180192a33`
- `ADVAPI32!RegCloseKey` at `0x180192a78`
- `ADVAPI32!RegCloseKey` at `0x180192b39`
- `ADVAPI32!RegCloseKey` at `0x180192b5e`
- `ADVAPI32!RegCloseKey` at `0x180192bba`
- `ADVAPI32!RegCloseKey` at `0x180192c96`
- `ADVAPI32!RegCloseKey` at `0x180192d56`
- `ADVAPI32!RegCloseKey` at `0x180192de0`
- `ADVAPI32!RegCloseKey` at `0x180192e38`
- `ADVAPI32!RegCloseKey` at `0x180192e81`
- `ADVAPI32!RegCloseKey` at `0x180192a78`
- `ADVAPI32!RegCloseKey` at `0x180192b39`
- `ADVAPI32!RegCloseKey` at `0x180192b5e`
- `ADVAPI32!RegCloseKey` at `0x180192bba`
- `ADVAPI32!RegCloseKey` at `0x180192c96`
- `ADVAPI32!RegCloseKey` at `0x180192d56`
- `ADVAPI32!RegCloseKey` at `0x180192de0`
- `ADVAPI32!RegCloseKey` at `0x180192e38`
- `ADVAPI32!RegCloseKey` at `0x180192e81`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x180192f67`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x180192f67`

## string_xrefs

- `0x180193003`: `(REG_FULL_RESOURCE_DESCRIPTOR)`
- `0x180193038`: `(REG_LINK)`

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
0x1801928e0  push    rbp
0x1801928e2  push    rbx
0x1801928e3  push    rsi
0x1801928e4  push    rdi
0x1801928e5  push    r12
0x1801928e7  push    r13
0x1801928e9  push    r14
0x1801928eb  push    r15
0x1801928ed  lea     rbp, [rsp-308h]
0x1801928f5  sub     rsp, 408h
0x1801928fc  mov     rax, cs:__security_cookie
0x180192903  xor     rax, rsp
0x180192906  mov     [rbp+340h+var_50], rax
0x18019290d  xor     r12d, r12d
0x180192910  lea     rax, [rbp+340h+var_378]
0x180192914  mov     r14, rdx
0x180192917  mov     [rbp+340h+var_3BC], r12d
0x18019291b  mov     rbx, 0FFFFFFFF80000000h
0x180192922  mov     [rbp+340h+phkResult], r12
0x180192926  xor     r8d, r8d
0x180192929  mov     [rsp+440h+hKey], r12
0x18019292e  lea     r13d, [r12+1]
0x180192933  mov     [rbp+340h+lpSubKey], r12
0x180192937  mov     edx, 208h
0x18019293c  mov     [rbp+340h+nSize], r13d
0x180192940  lea     rcx, [rbp+340h+lpDst]
0x180192944  mov     [rsp+440h+dwIndex], ebx
0x180192948  mov     r15d, r12d
0x18019294b  mov     [rbp+340h+var_3B0], r12
0x18019294f  mov     [rbp+340h+lpDst], rax
0x180192953  call    ?SetSize@?$CAPITempBuffer@G$00@@QEAA_NH_N@Z; CAPITempBuffer<ushort,1>::SetSize(int,bool)
0x180192958  test    al, al
0x18019295a  jz      loc_180192ED5
0x180192960  mov     edx, r13d
0x180192963  mov     [rbp+340h+Type], r12d
0x180192967  mov     rcx, r14
0x18019296a  mov     [rsp+440h+cchValueName], r12d
0x18019296f  call    ??ACAutoArgs@@QEAAAEAVCVariant@@I@Z; CAutoArgs::operator[](uint)
0x180192974  mov     rcx, rax
0x180192977  mov     r10, rax
0x18019297a  call    ?IsNumeric@CVariant@@QEAA?AW4Bool@@XZ; CVariant::IsNumeric(void)
0x18019297f  mov     rcx, r10; this
0x180192982  test    eax, eax
0x180192984  jz      short loc_1801929AF
0x180192986  lea     rdx, [rbp+340h+var_3BC]; int *
0x18019298a  call    ?GetInt@CVariant@@QEAAJAEAH@Z; CVariant::GetInt(int &)
0x18019298f  test    [rbp+340h+var_3BC], 7FFFFFF0h
0x180192996  jnz     loc_180192B7F
0x18019299c  movsxd  rax, [rbp+340h+var_3BC]
0x1801929a0  mov     dil, r12b
0x1801929a3  or      rax, rbx
0x1801929a6  mov     [rbp+340h+phkResult], rax
0x1801929aa  jmp     loc_180192A4C
0x1801929af  lea     rdx, [rsp+440h+cchClass]; unsigned __int16 **
0x1801929b4  mov     qword ptr [rsp+440h+cchClass], r12
0x1801929b9  call    ?GetString@CVariant@@QEAAJAEAPEBG@Z; CVariant::GetString(ushort const * &)
0x1801929be  mov     ebx, eax
0x1801929c0  test    eax, eax
0x1801929c2  jnz     loc_180192EDA
0x1801929c8  mov     rax, qword ptr [rsp+440h+cchClass]
0x1801929cd  test    rax, rax
0x1801929d0  jz      loc_180193086
0x1801929d6  mov     dword ptr [rbp+340h+MachineName], 5C005Ch
0x1801929e0  lea     r8, [rbp+340h+var_25C]
0x1801929e7  movzx   edx, word ptr [rax]
0x1801929ea  test    dx, dx
0x1801929ed  jz      short loc_180192A1D
0x1801929ef  mov     ecx, 102h
0x1801929f4  test    rcx, rcx
0x1801929f7  jz      loc_180193086
0x1801929fd  add     rax, 2
0x180192a01  mov     [r8], dx
0x180192a05  add     r8, 2
0x180192a09  sub     rcx, r13
0x180192a0c  movzx   edx, word ptr [rax]
0x180192a0f  test    dx, dx
0x180192a12  jnz     short loc_1801929F4
0x180192a14  test    rcx, rcx
0x180192a17  jz      loc_180193086
0x180192a1d  mov     [r8], r12w
0x180192a21  lea     rcx, [rbp+340h+MachineName]; lpMachineName
0x180192a28  lea     r8, [rbp+340h+phkResult]; phkResult
0x180192a2c  mov     rdx, 0FFFFFFFF80000002h; hKey
0x180192a33  call    cs:__imp_RegConnectRegistryW
0x180192a3a  nop     dword ptr [rax+rax+00h]
0x180192a3f  mov     ebx, eax
0x180192a41  test    eax, eax
0x180192a43  jnz     loc_180192EDA
0x180192a49  mov     dil, r13b
0x180192a4c  mov     edx, 2
0x180192a51  mov     rcx, r14
0x180192a54  call    ??ACAutoArgs@@QEAAAEAVCVariant@@I@Z; CAutoArgs::operator[](uint)
0x180192a59  lea     rdx, [rbp+340h+lpSubKey]; unsigned __int16 **
0x180192a5d  mov     rcx, rax; this
0x180192a60  call    ?GetString@CVariant@@QEAAJAEAPEBG@Z; CVariant::GetString(ushort const * &)
0x180192a65  mov     ebx, eax
0x180192a67  test    eax, eax
0x180192a69  jz      short loc_180192A89
0x180192a6b  test    dil, dil
0x180192a6e  jz      loc_180192EDA
0x180192a74  mov     rcx, [rbp+340h+phkResult]; hKey
0x180192a78  call    cs:__imp_RegCloseKey
0x180192a7f  nop     dword ptr [rax+rax+00h]
0x180192a84  jmp     loc_180192EDA
0x180192a89  mov     ebx, 3
0x180192a8e  mov     rcx, r14
0x180192a91  mov     edx, ebx
0x180192a93  mov     esi, r13d
0x180192a96  call    ?Present@CAutoArgs@@QEAA?AW4Bool@@I@Z; CAutoArgs::Present(uint)
0x180192a9b  test    eax, eax
0x180192a9d  jz      short loc_180192B07
0x180192a9f  mov     edx, ebx
0x180192aa1  mov     rcx, r14
0x180192aa4  call    ??ACAutoArgs@@QEAAAEAVCVariant@@I@Z; CAutoArgs::operator[](uint)
0x180192aa9  mov     r10, rax
0x180192aac  mov     esi, r12d
0x180192aaf  cmp     [rax], r13b
0x180192ab2  jz      short loc_180192B07
0x180192ab4  mov     rcx, rax
0x180192ab7  call    ?IsNumeric@CVariant@@QEAA?AW4Bool@@XZ; CVariant::IsNumeric(void)
0x180192abc  mov     rcx, r10; this
0x180192abf  test    eax, eax
0x180192ac1  jz      short loc_180192AF0
0x180192ac3  lea     rdx, [rsp+440h+dwIndex]; int *
0x180192ac8  call    ?GetInt@CVariant@@QEAAJAEAH@Z; CVariant::GetInt(int &)
0x180192acd  mov     eax, [rsp+440h+dwIndex]
0x180192ad1  test    eax, eax
0x180192ad3  jnz     short loc_180192ADA
0x180192ad5  lea     esi, [rbx+1]
0x180192ad8  jmp     short loc_180192B07
0x180192ada  jle     short loc_180192AE6
0x180192adc  mov     esi, 2
0x180192ae1  sub     eax, r13d
0x180192ae4  jmp     short loc_180192AEA
0x180192ae6  mov     esi, ebx
0x180192ae8  not     eax
0x180192aea  mov     [rsp+440h+dwIndex], eax
0x180192aee  jmp     short loc_180192B07
0x180192af0  lea     rdx, [rbp+340h+var_3B0]; unsigned __int16 **
0x180192af4  call    ?GetString@CVariant@@QEAAJAEAPEBG@Z; CVariant::GetString(ushort const * &)
0x180192af9  mov     ebx, eax
0x180192afb  test    eax, eax
0x180192afd  jnz     loc_180192A6B
0x180192b03  mov     r15, [rbp+340h+var_3B0]
0x180192b07  mov     rdx, [rbp+340h+lpSubKey]; lpSubKey
0x180192b0b  lea     rax, [rsp+440h+hKey]
0x180192b10  mov     rcx, [rbp+340h+phkResult]; hKey
0x180192b14  mov     r9d, 9; samDesired
0x180192b1a  xor     r8d, r8d; ulOptions
0x180192b1d  mov     [rsp+440h+var_420], rax; phkResult
0x180192b22  call    cs:__imp_RegOpenKeyExW
0x180192b29  nop     dword ptr [rax+rax+00h]
0x180192b2e  mov     ebx, eax
0x180192b30  test    dil, dil
0x180192b33  jz      short loc_180192B45
0x180192b35  mov     rcx, [rbp+340h+phkResult]; hKey
0x180192b39  call    cs:__imp_RegCloseKey
0x180192b40  nop     dword ptr [rax+rax+00h]
0x180192b45  cmp     esi, r13d
0x180192b48  jnz     short loc_180192B7B
0x180192b4a  mov     rcx, r14
0x180192b4d  test    ebx, ebx
0x180192b4f  jnz     short loc_180192B6F
0x180192b51  mov     edx, r13d
0x180192b54  call    ?Assign@CAutoArgs@@QEAAJW4Bool@@@Z; CAutoArgs::Assign(Bool)
0x180192b59  mov     rcx, [rsp+440h+hKey]; hKey
0x180192b5e  call    cs:__imp_RegCloseKey
0x180192b65  nop     dword ptr [rax+rax+00h]
0x180192b6a  jmp     loc_180193079
0x180192b6f  xor     edx, edx
0x180192b71  call    ?Assign@CAutoArgs@@QEAAJW4Bool@@@Z; CAutoArgs::Assign(Bool)
0x180192b76  jmp     loc_180193079
0x180192b7b  test    ebx, ebx
0x180192b7d  jz      short loc_180192B89
0x180192b7f  mov     ebx, 8002000Bh
0x180192b84  jmp     loc_180192EDA
0x180192b89  mov     edx, 82h
0x180192b8e  mov     [rsp+440h+cchValueName], edx
0x180192b92  cmp     esi, 4
0x180192b95  jnz     loc_180192CD9
0x180192b9b  mov     ecx, 20Ah; unsigned __int64
0x180192ba0  mov     [rsp+440h+cchClass], 105h
0x180192ba8  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180192bad  mov     rcx, [rsp+440h+hKey]; hKey
0x180192bb2  mov     rbx, rax
0x180192bb5  test    rax, rax
0x180192bb8  jnz     short loc_180192BCB
0x180192bba  call    cs:__imp_RegCloseKey
0x180192bc1  nop     dword ptr [rax+rax+00h]
0x180192bc6  jmp     loc_180192ED5
0x180192bcb  mov     [rsp+440h+lpftLastWriteTime], r12; lpftLastWriteTime
0x180192bd0  lea     r8, [rsp+440h+cchClass]; lpcchClass
0x180192bd5  mov     [rsp+440h+lpcbSecurityDescriptor], r12; lpcbSecurityDescriptor
0x180192bda  xor     r9d, r9d; lpReserved
0x180192bdd  mov     [rsp+440h+lpcbMaxValueLen], r12; lpcbMaxValueLen
0x180192be2  mov     rdx, rbx; lpClass
0x180192be5  mov     [rsp+440h+lpcbMaxValueNameLen], r12; lpcbMaxValueNameLen
0x180192bea  mov     [rsp+440h+lpcValues], r12; lpcValues
0x180192bef  mov     [rsp+440h+lpcbMaxClassLen], r12; lpcbMaxClassLen
0x180192bf4  mov     [rsp+440h+lpcbMaxSubKeyLen], r12; lpcbMaxSubKeyLen
0x180192bf9  mov     [rsp+440h+var_420], r12; lpcSubKeys
0x180192bfe  call    cs:__imp_RegQueryInfoKeyW
0x180192c05  nop     dword ptr [rax+rax+00h]
0x180192c0a  mov     edi, eax
0x180192c0c  cmp     eax, 0EAh
0x180192c11  jnz     short loc_180192C91
0x180192c13  add     [rsp+440h+cchClass], r13d
0x180192c18  mov     rcx, rbx; void *
0x180192c1b  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180192c20  mov     ecx, [rsp+440h+cchClass]
0x180192c24  mov     eax, 2
0x180192c29  mul     rcx
0x180192c2c  mov     r15, 0FFFFFFFFFFFFFFFFh
0x180192c33  cmovb   rax, r15
0x180192c37  mov     rcx, rax; unsigned __int64
0x180192c3a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180192c3f  mov     rcx, [rsp+440h+hKey]; hKey
0x180192c44  mov     rbx, rax
0x180192c47  test    rax, rax
0x180192c4a  jz      loc_180192BBA
0x180192c50  mov     [rsp+440h+lpftLastWriteTime], r12; lpftLastWriteTime
0x180192c55  lea     r8, [rsp+440h+cchClass]; lpcchClass
0x180192c5a  mov     [rsp+440h+lpcbSecurityDescriptor], r12; lpcbSecurityDescriptor
0x180192c5f  xor     r9d, r9d; lpReserved
0x180192c62  mov     [rsp+440h+lpcbMaxValueLen], r12; lpcbMaxValueLen
0x180192c67  mov     rdx, rax; lpClass
0x180192c6a  mov     [rsp+440h+lpcbMaxValueNameLen], r12; lpcbMaxValueNameLen
0x180192c6f  mov     [rsp+440h+lpcValues], r12; lpcValues
0x180192c74  mov     [rsp+440h+lpcbMaxClassLen], r12; lpcbMaxClassLen
0x180192c79  mov     [rsp+440h+lpcbMaxSubKeyLen], r12; lpcbMaxSubKeyLen
0x180192c7e  mov     [rsp+440h+var_420], r12; lpcSubKeys
0x180192c83  call    cs:__imp_RegQueryInfoKeyW
0x180192c8a  nop     dword ptr [rax+rax+00h]
0x180192c8f  mov     edi, eax
0x180192c91  mov     rcx, [rsp+440h+hKey]; hKey
0x180192c96  call    cs:__imp_RegCloseKey
0x180192c9d  nop     dword ptr [rax+rax+00h]
0x180192ca2  test    edi, edi
0x180192ca4  jz      short loc_180192CB1
0x180192ca6  cmp     [rsp+440h+cchClass], r12d
0x180192cab  jnz     short loc_180192CCC
0x180192cad  mov     [rbx], r12w
0x180192cb1  mov     rdx, rbx; unsigned __int16 *
0x180192cb4  mov     rcx, r14; this
0x180192cb7  call    ?Assign@CAutoArgs@@QEAAJPEBG@Z; CAutoArgs::Assign(ushort const *)
0x180192cbc  mov     rcx, rbx; void *
0x180192cbf  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180192cc4  mov     ebx, r12d
0x180192cc7  jmp     loc_180192EDA
0x180192ccc  mov     rcx, rbx; void *
0x180192ccf  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180192cd4  jmp     loc_180192B7F
0x180192cd9  lea     rdi, [rbp+340h+ValueName]
0x180192cdd  cmp     esi, 2
0x180192ce0  jnz     loc_180192DA2
0x180192ce6  or      r15, 0FFFFFFFFFFFFFFFFh
0x180192cea  mov     edx, [rsp+440h+dwIndex]; dwIndex
0x180192cee  lea     rax, [rbp+340h+Type]
0x180192cf2  mov     rcx, [rsp+440h+hKey]; hKey
0x180192cf7  lea     r9, [rsp+440h+cchValueName]; lpcchValueName
0x180192cfc  mov     [rsp+440h+lpcValues], r12; lpcbData
0x180192d01  mov     r8, rdi; lpValueName
0x180192d04  mov     [rsp+440h+lpcbMaxClassLen], r12; lpData
0x180192d09  mov     [rsp+440h+lpcbMaxSubKeyLen], rax; lpType
0x180192d0e  mov     [rsp+440h+var_420], r12; lpReserved
0x180192d13  call    cs:__imp_RegEnumValueW
0x180192d1a  nop     dword ptr [rax+rax+00h]
0x180192d1f  mov     ebx, eax
0x180192d21  cmp     eax, 0EAh
0x180192d26  jnz     short loc_180192D51
0x180192d28  lea     rax, [rbp+340h+ValueName]
0x180192d2c  cmp     rdi, rax
0x180192d2f  jnz     short loc_180192D51
0x180192d31  mov     ecx, [rsp+440h+cchValueName]
0x180192d35  mov     eax, 2
0x180192d3a  mul     rcx
0x180192d3d  cmovb   rax, r15
0x180192d41  mov     rcx, rax; unsigned __int64
0x180192d44  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180192d49  mov     rdi, rax
0x180192d4c  test    rax, rax
0x180192d4f  jnz     short loc_180192CEA
0x180192d51  mov     rcx, [rsp+440h+hKey]; hKey
0x180192d56  call    cs:__imp_RegCloseKey
0x180192d5d  nop     dword ptr [rax+rax+00h]
0x180192d62  cmp     ebx, 103h
0x180192d68  jnz     short loc_180192D80
0x180192d6a  mov     rcx, [r14+18h]
0x180192d6e  test    rcx, rcx
0x180192d71  jz      loc_180193062
0x180192d77  mov     [rcx], r12w
0x180192d7b  jmp     loc_180193062
0x180192d80  test    ebx, ebx
0x180192d82  jz      loc_18019304D
0x180192d88  lea     rax, [rbp+340h+ValueName]
0x180192d8c  cmp     rdi, rax
0x180192d8f  jz      loc_180192EDA
0x180192d95  mov     rcx, rdi; void *
0x180192d98  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180192d9d  jmp     loc_180192EDA
  ... truncated ...
```
