# Performance::RegistryTransferable<PerfDiagBoot::CRegistryConfigBase<PerfDiagBoot::CFlatSystemThresholdingConfig>>::readWriteImpl(bool)

- ea: `0x1800193d4`
- end: `0x180019980`
- name: `?readWriteImpl@?$RegistryTransferable@V?$CRegistryConfigBase@UCFlatSystemThresholdingConfig@PerfDiagBoot@@@PerfDiagBoot@@@Performance@@AEAAJ_N@Z`
- size: `1452`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `8`
- callee_count: `15`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x1800166e0`
- `0x1800279d8`
- `0x18002cfe4`
- `0x1800443f0`
- `0x1800b06e0`
- `0x1800b1790`
- `0x1800b67d8`
- `0x1800b94a4`

## callees

- `0x18001890c`
- `0x180018aa4`
- `0x180019310`
- `0x18001933c`
- `0x180019370`
- `0x1800193d4`
- `0x180019f7c`
- `0x18001a3e8`
- `0x18001a56c`
- `0x180039b68`
- `0x180041ea8`
- `0x180042fe0`
- `0x180056c14`
- `0x180057836`
- `0x1800d6010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180019513`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001956e`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001978e`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180019927`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180019513`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001956e`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001978e`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180019927`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800195b8`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180019657`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800196d7`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800197e1`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001986f`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800195b8`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180019657`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800196d7`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800197e1`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001986f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001946a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800194ca`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800195f8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800198a8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180019965`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001946a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800194ca`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800195f8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800198a8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180019965`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall Performance::RegistryTransferable<PerfDiagBoot::CRegistryConfigBase<PerfDiagBoot::CFlatSystemThresholdingConfig>>::readWriteImpl(
        __int64 (__fastcall ***a1)(_QWORD, HKEY *, LPCWSTR *),
        char a2)
{
  char v2; // r12
  __int64 (__fastcall ***v3)(_QWORD, HKEY *, LPCWSTR *); // r15
  __int64 v4; // r14
  unsigned __int16 *v5; // r9
  int v6; // eax
  unsigned int v7; // r9d
  int Value; // ebx
  HKEY v9; // rcx
  __int64 v11; // rax
  HKEY v12; // rdi
  __int64 v13; // rsi
  const WCHAR *v14; // rdx
  int v15; // ecx
  int v16; // ecx
  int v17; // ecx
  int v18; // ecx
  unsigned __int64 *v19; // r8
  LSTATUS QWORDValue; // eax
  BYTE *v21; // rcx
  DWORD v22; // eax
  const unsigned __int16 **v23; // r13
  DWORD v24; // r15d
  BYTE *BufferSetLength; // r12
  unsigned int v26; // edx
  char *v27; // r15
  LSTATUS v28; // eax
  LSTATUS v29; // eax
  void *v30; // rbx
  LSTATUS v31; // eax
  unsigned int v32; // esi
  unsigned int *v33; // r8
  LSTATUS DWORDValue; // eax
  unsigned int lpData; // [rsp+20h] [rbp-98h]
  struct _SECURITY_ATTRIBUTES *v36; // [rsp+30h] [rbp-88h]
  unsigned int *v37; // [rsp+38h] [rbp-80h]
  DWORD Type[2]; // [rsp+40h] [rbp-78h] BYREF
  LPCWSTR lpSubKey; // [rsp+48h] [rbp-70h] BYREF
  HKEY v40; // [rsp+50h] [rbp-68h] BYREF
  __int64 v41; // [rsp+58h] [rbp-60h]
  ATL::CAtlException *v42; // [rsp+60h] [rbp-58h] BYREF
  HKEY hKey[10]; // [rsp+68h] [rbp-50h] BYREF
  DWORD v46; // [rsp+D0h] [rbp+18h] BYREF
  unsigned __int64 Data; // [rsp+D8h] [rbp+20h] BYREF

  v2 = a2;
  v3 = a1;
  v40 = 0;
  lpSubKey = 0;
  v4 = (**a1)(a1, &v40, &lpSubKey);
  memset(hKey, 0, 24);
  v6 = ATL::CRegKey::Create((ATL::CRegKey *)hKey, v40, lpSubKey, v5, lpData, v2 != 0 ? 131103 : 131097, v36, v37);
  Value = v6;
  if ( v6 )
  {
    if ( v6 > 0 )
      Value = (unsigned __int16)v6 | 0x80070000;
    v9 = hKey[0];
    if ( hKey[0] )
      goto LABEL_5;
    return (unsigned int)Value;
  }
  v11 = 0;
  v12 = hKey[0];
  while ( 1 )
  {
    v41 = v11;
    v13 = 3 * v11;
    v14 = *(const WCHAR **)(v4 + 24 * v11);
    if ( !v14 )
    {
      if ( v12 )
        RegCloseKey(v12);
      return 0;
    }
    v15 = *(_DWORD *)(v4 + 24 * v11 + 8);
    if ( !v15 )
    {
      v33 = (unsigned int *)((char *)v3 + *(int *)(v4 + 24 * v11 + 12));
      if ( v2 )
      {
        LODWORD(Data) = *v33;
        DWORDValue = RegSetValueExW(v12, v14, 0, 4u, (const BYTE *)&Data, 4u);
      }
      else
      {
        DWORDValue = ATL::CRegKey::QueryDWORDValue((ATL::CRegKey *)hKey, v14, v33);
      }
      Value = DWORDValue;
      if ( DWORDValue )
      {
        if ( DWORDValue > 0 )
          Value = (unsigned __int16)DWORDValue | 0x80070000;
        goto LABEL_88;
      }
      goto LABEL_29;
    }
    v16 = v15 - 1;
    if ( !v16 )
      break;
    v17 = v16 - 1;
    if ( !v17 )
    {
      v23 = (const unsigned __int16 **)((char *)v3 + *(int *)(v4 + 24 * v11 + 12));
      if ( v2 )
      {
        Value = ATL::CRegKey::SetStringValue((ATL::CRegKey *)hKey, v14, *v23, v7);
        goto LABEL_21;
      }
      LODWORD(Data) = 0;
      Type[0] = 0;
      Value = RegQueryValueExW(v12, v14, 0, (LPDWORD)&Data, 0, Type);
      if ( Value )
      {
LABEL_21:
        if ( Value )
        {
          if ( Value <= 0 )
            goto LABEL_25;
          goto LABEL_23;
        }
        goto LABEL_29;
      }
      if ( (unsigned int)(Data - 1) > 1 )
      {
        Value = 13;
        goto LABEL_21;
      }
      v24 = Type[0] >> 1;
      Value = 0;
      if ( !(Type[0] >> 1) )
      {
        ATL::CSimpleStringT<unsigned short,0>::Empty(v23);
        goto LABEL_21;
      }
      try
      {
        BufferSetLength = (BYTE *)ATL::CSimpleStringT<unsigned short,0>::GetBufferSetLength(v23, v24);
        Type[0] = 0;
        LODWORD(Data) = 2 * v24;
        Value = RegQueryValueExW(v12, *(LPCWSTR *)(v4 + 8 * v13), 0, Type, BufferSetLength, (LPDWORD)&Data);
        if ( Value )
          goto LABEL_49;
        if ( Type[0] - 1 > 1 )
          goto LABEL_48;
        if ( BufferSetLength )
        {
          v26 = Data;
          if ( (_DWORD)Data )
          {
            if ( (Data & 1) != 0 || *(_WORD *)&BufferSetLength[2 * ((unsigned __int64)(unsigned int)Data >> 1) - 2] )
            {
LABEL_48:
              Value = 13;
              goto LABEL_49;
            }
          }
          else
          {
            *(_WORD *)BufferSetLength = 0;
          }
        }
        else
        {
          v26 = Data;
        }
        Value = 0;
        if ( !(v26 >> 1) )
LABEL_49:
          ATL::CSimpleStringT<unsigned short,0>::SetLength(v23, 0);
        else
          ATL::CSimpleStringT<unsigned short,0>::ReleaseBuffer(v23);
        v2 = a2;
      }
      catch ( ATL::CAtlException *v42 )
      {
        Value = *(_DWORD *)v42;
        goto LABEL_88;
      }
      goto LABEL_21;
    }
    v18 = v17 - 1;
    if ( v18 )
    {
      if ( v18 != 1 )
      {
        if ( v12 )
          RegCloseKey(v12);
        return 2147549183LL;
      }
      v19 = (unsigned __int64 *)((char *)v3 + *(int *)(v4 + 24 * v11 + 12));
      if ( v2 )
      {
        Data = *v19;
        QWORDValue = RegSetValueExW(v12, v14, 0, 0xBu, (const BYTE *)&Data, 8u);
      }
      else
      {
        QWORDValue = ATL::CRegKey::QueryQWORDValue((ATL::CRegKey *)hKey, v14, v19);
      }
      Value = QWORDValue;
      goto LABEL_21;
    }
    v21 = (BYTE *)v3 + *(int *)(v4 + 24 * v11 + 12);
    v22 = *(_DWORD *)(v4 + 24 * v11 + 16);
    if ( v2 )
    {
      Value = RegSetValueExW(v12, v14, 0, 3u, v21, *(_DWORD *)(v4 + 8 * v13 + 16));
      if ( Value )
        goto LABEL_31;
    }
    else
    {
      Type[0] = v22;
      LODWORD(Data) = 0;
      Value = RegQueryValueExW(v12, v14, 0, (LPDWORD)&Data, v21, Type);
      if ( Value )
      {
LABEL_31:
        if ( Value <= 0 )
          goto LABEL_25;
        goto LABEL_23;
      }
      if ( (_DWORD)Data != 3 )
      {
        LOWORD(Value) = 13;
LABEL_23:
        Value = (unsigned __int16)Value;
        goto LABEL_24;
      }
      if ( Type[0] != *(_DWORD *)(v4 + 8 * v13 + 16) )
      {
        if ( v12 )
          RegCloseKey(v12);
        return 2147942413LL;
      }
    }
LABEL_29:
    v11 = v41 + 1;
    v3 = a1;
  }
  v27 = (char *)v3 + *(int *)(v4 + 24 * v11 + 12);
  if ( v2 )
  {
    v28 = RegSetValueExW(v12, v14, 0, 3u, *(const BYTE **)v27, (*((_QWORD *)v27 + 1) - *(_QWORD *)v27) & 0xFFFFFFFC);
    Value = v28;
    if ( v28 )
    {
      if ( v28 <= 0 )
        goto LABEL_25;
      Value = (unsigned __int16)v28;
LABEL_24:
      Value |= 0x80070000;
      goto LABEL_25;
    }
    goto LABEL_29;
  }
  *(_QWORD *)Type = 0;
  v46 = 0;
  LODWORD(Data) = 0;
  v29 = RegQueryValueExW(v12, v14, 0, (LPDWORD)&Data, 0, &v46);
  Value = v29;
  if ( v29 )
  {
    if ( v29 > 0 )
      goto LABEL_69;
    goto LABEL_70;
  }
  if ( (_DWORD)Data == 3 )
  {
    if ( !(unsigned __int8)ATL::CAutoVectorPtr<unsigned char>::Allocate(Type, v46) )
    {
LABEL_72:
      operator delete(*(void **)Type);
      Value = -2147024882;
LABEL_88:
      ATL::CRegKey::Close((ATL::CRegKey *)hKey);
      return (unsigned int)Value;
    }
    LODWORD(Data) = 0;
    v30 = *(void **)Type;
    v31 = RegQueryValueExW(v12, *(LPCWSTR *)(v4 + 8 * v13), 0, (LPDWORD)&Data, *(LPBYTE *)Type, &v46);
    v32 = v31;
    if ( v31 )
    {
      if ( v31 <= 0 )
        goto LABEL_79;
      goto LABEL_78;
    }
    if ( (_DWORD)Data != 3 )
    {
      LOWORD(v32) = 13;
LABEL_78:
      v32 = (unsigned __int16)v32 | 0x80070000;
LABEL_79:
      operator delete(v30);
      if ( v12 )
        RegCloseKey(v12);
      return v32;
    }
    try
    {
      std::vector<unsigned long>::resize(v27, (unsigned __int64)v46 >> 2);
      memcpy_0(*(void **)v27, v30, v46);
      operator delete(v30);
    }
    catch ( std::bad_alloc )
    {
      goto LABEL_72;
    }
    goto LABEL_29;
  }
  LOWORD(Value) = 13;
LABEL_69:
  Value = (unsigned __int16)Value | 0x80070000;
LABEL_70:
  operator delete(0);
LABEL_25:
  if ( !v12 )
    return (unsigned int)Value;
  v9 = v12;
LABEL_5:
  RegCloseKey(v9);
  return (unsigned int)Value;
}

```

## disassembly

```asm
0x1800193d4  mov     byte ptr [rsp+arg_8], dl
0x1800193d8  mov     r11, rsp
0x1800193db  mov     [r11+8], rcx
0x1800193df  push    rbx
0x1800193e0  push    rsi
0x1800193e1  push    rdi
0x1800193e2  push    r12
0x1800193e4  push    r13
0x1800193e6  push    r14
0x1800193e8  push    r15
0x1800193ea  sub     rsp, 80h
0x1800193f1  mov     r12b, dl
0x1800193f4  mov     r15, rcx
0x1800193f7  xor     r13d, r13d
0x1800193fa  mov     [r11-68h], r13
0x1800193fe  mov     [r11-70h], r13
0x180019402  mov     rax, [rcx]
0x180019405  lea     r8, [r11-70h]
0x180019409  lea     rdx, [r11-68h]
0x18001940d  mov     rax, [rax]
0x180019410  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019415  mov     r14, rax
0x180019418  mov     [rsp+0B8h+hKey], r13
0x18001941d  mov     [rsp+0B8h+var_48], r13
0x180019422  mov     [rsp+0B8h+var_40], r13
0x180019427  mov     cl, r12b
0x18001942a  neg     cl
0x18001942c  sbb     edx, edx
0x18001942e  and     edx, 6
0x180019431  add     edx, 20019h
0x180019437  mov     [rsp+0B8h+cbData], edx; unsigned int
0x18001943b  mov     r8, [rsp+0B8h+lpSubKey]; lpSubKey
0x180019440  mov     rdx, [rsp+0B8h+var_68]; hKey
0x180019445  lea     rcx, [rsp+0B8h+hKey]; this
0x18001944a  call    ?Create@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGPEAGKKPEAU_SECURITY_ATTRIBUTES@@PEAK@Z; ATL::CRegKey::Create(HKEY__ *,ushort const *,ushort *,ulong,ulong,_SECURITY_ATTRIBUTES *,ulong *)
0x18001944f  mov     ebx, eax
0x180019451  test    eax, eax
0x180019453  jz      short loc_180019477
0x180019455  jle     short loc_180019460
0x180019457  movzx   ebx, ax
0x18001945a  or      ebx, 80070000h
0x180019460  mov     rcx, [rsp+0B8h+hKey]; hKey
0x180019465  test    rcx, rcx
0x180019468  jz      short loc_180019470
0x18001946a  call    cs:__imp_RegCloseKey
0x180019470  mov     eax, ebx
0x180019472  jmp     loc_18001996D
0x180019477  mov     rax, r13
0x18001947a  mov     rdi, [rsp+0B8h+hKey]
0x18001947f  mov     [rsp+0B8h+var_60], rax
0x180019484  lea     rsi, [rax+rax*2]
0x180019488  mov     rdx, [r14+rsi*8]; unsigned __int16 *
0x18001948c  test    rdx, rdx
0x18001948f  jz      loc_18001995D
0x180019495  mov     ecx, [r14+rsi*8+8]
0x18001949a  test    ecx, ecx
0x18001949c  jz      loc_1800198EF
0x1800194a2  sub     ecx, 1
0x1800194a5  jz      loc_18001975F
0x1800194ab  sub     ecx, 1
0x1800194ae  jz      loc_180019608
0x1800194b4  sub     ecx, 1
0x1800194b7  jz      loc_180019547
0x1800194bd  cmp     ecx, 1
0x1800194c0  jz      short loc_1800194DA
0x1800194c2  test    rdi, rdi
0x1800194c5  jz      short loc_1800194D0
0x1800194c7  mov     rcx, rdi; hKey
0x1800194ca  call    cs:__imp_RegCloseKey
0x1800194d0  mov     eax, 8000FFFFh
0x1800194d5  jmp     loc_18001996D
0x1800194da  movsxd  r8, dword ptr [r14+rsi*8+0Ch]
0x1800194df  add     r8, r15; unsigned __int64 *
0x1800194e2  test    r12b, r12b
0x1800194e5  jz      short loc_18001951B
0x1800194e7  mov     rax, [r8]
0x1800194ea  mov     [rsp+0B8h+Data], rax
0x1800194f2  mov     [rsp+0B8h+cbData], 8; cbData
0x1800194fa  lea     rax, [rsp+0B8h+Data]
0x180019502  mov     [rsp+0B8h+lpData], rax; lpData
0x180019507  mov     r9d, 0Bh; dwType
0x18001950d  xor     r8d, r8d; Reserved
0x180019510  mov     rcx, rdi; hKey
0x180019513  call    cs:__imp_RegSetValueExW
0x180019519  jmp     short loc_180019525
0x18001951b  lea     rcx, [rsp+0B8h+hKey]; this
0x180019520  call    ?QueryQWORDValue@CRegKey@ATL@@QEAAJPEBGAEA_K@Z; ATL::CRegKey::QueryQWORDValue(ushort const *,unsigned __int64 &)
0x180019525  mov     ebx, eax
0x180019527  test    ebx, ebx
0x180019529  jz      short loc_18001957A
0x18001952b  jle     short loc_180019536
0x18001952d  movzx   ebx, bx
0x180019530  or      ebx, 80070000h
0x180019536  test    rdi, rdi
0x180019539  jz      loc_180019470
0x18001953f  mov     rcx, rdi
0x180019542  jmp     loc_18001946A
0x180019547  movsxd  rcx, dword ptr [r14+rsi*8+0Ch]
0x18001954c  add     rcx, r15
0x18001954f  mov     eax, [r14+rsi*8+10h]
0x180019554  test    r12b, r12b
0x180019557  jz      short loc_18001958F
0x180019559  mov     [rsp+0B8h+cbData], eax; cbData
0x18001955d  mov     [rsp+0B8h+lpData], rcx; lpData
0x180019562  mov     r9d, 3; dwType
0x180019568  xor     r8d, r8d; Reserved
0x18001956b  mov     rcx, rdi; hKey
0x18001956e  call    cs:__imp_RegSetValueExW
0x180019574  mov     ebx, eax
0x180019576  test    eax, eax
0x180019578  jnz     short loc_1800195C4
0x18001957a  mov     rax, [rsp+0B8h+var_60]
0x18001957f  inc     rax
0x180019582  mov     r15, [rsp+0B8h+arg_0]
0x18001958a  jmp     loc_18001947F
0x18001958f  mov     [rsp+0B8h+Type], eax
0x180019593  mov     dword ptr [rsp+0B8h+Data], r13d
0x18001959b  lea     rax, [rsp+0B8h+Type]
0x1800195a0  mov     qword ptr [rsp+0B8h+cbData], rax; lpcbData
0x1800195a5  mov     [rsp+0B8h+lpData], rcx; lpData
0x1800195aa  lea     r9, [rsp+0B8h+Data]; lpType
0x1800195b2  xor     r8d, r8d; lpReserved
0x1800195b5  mov     rcx, rdi; hKey
0x1800195b8  call    cs:__imp_RegQueryValueExW
0x1800195be  mov     ebx, eax
0x1800195c0  test    eax, eax
0x1800195c2  jz      short loc_1800195D1
0x1800195c4  test    ebx, ebx
0x1800195c6  jle     loc_180019536
0x1800195cc  jmp     loc_18001952D
0x1800195d1  cmp     dword ptr [rsp+0B8h+Data], 3
0x1800195d9  jz      short loc_1800195E5
0x1800195db  mov     ebx, 0Dh
0x1800195e0  jmp     loc_18001952D
0x1800195e5  mov     eax, [r14+rsi*8+10h]
0x1800195ea  cmp     [rsp+0B8h+Type], eax
0x1800195ee  jz      short loc_18001957A
0x1800195f0  test    rdi, rdi
0x1800195f3  jz      short loc_1800195FE
0x1800195f5  mov     rcx, rdi; hKey
0x1800195f8  call    cs:__imp_RegCloseKey
0x1800195fe  mov     eax, 8007000Dh
0x180019603  jmp     loc_18001996D
0x180019608  movsxd  r13, dword ptr [r14+rsi*8+0Ch]
0x18001960d  add     r13, r15
0x180019610  xor     r15d, r15d
0x180019613  test    r12b, r12b
0x180019616  jz      short loc_18001962D
0x180019618  mov     r8, [r13+0]; unsigned __int16 *
0x18001961c  lea     rcx, [rsp+0B8h+hKey]; this
0x180019621  call    ?SetStringValue@CRegKey@ATL@@QEAAJPEBG0K@Z; ATL::CRegKey::SetStringValue(ushort const *,ushort const *,ulong)
0x180019626  mov     ebx, eax
0x180019628  jmp     loc_180019707
0x18001962d  mov     dword ptr [rsp+0B8h+Data], r15d
0x180019635  mov     [rsp+0B8h+Type], r15d
0x18001963a  lea     rax, [rsp+0B8h+Type]
0x18001963f  mov     qword ptr [rsp+0B8h+cbData], rax; lpcbData
0x180019644  mov     [rsp+0B8h+lpData], r15; lpData
0x180019649  lea     r9, [rsp+0B8h+Data]; lpType
0x180019651  xor     r8d, r8d; lpReserved
0x180019654  mov     rcx, rdi; hKey
0x180019657  call    cs:__imp_RegQueryValueExW
0x18001965d  mov     ebx, eax
0x18001965f  test    eax, eax
0x180019661  jnz     loc_180019707
0x180019667  mov     eax, dword ptr [rsp+0B8h+Data]
0x18001966e  dec     eax
0x180019670  cmp     eax, 1
0x180019673  jbe     short loc_18001967F
0x180019675  mov     ebx, 0Dh
0x18001967a  jmp     loc_180019707
0x18001967f  mov     r15d, [rsp+0B8h+Type]
0x180019684  shr     r15d, 1
0x180019687  xor     ebx, ebx
0x180019689  mov     rcx, r13
0x18001968c  test    r15d, r15d
0x18001968f  jnz     short loc_180019698
0x180019691  call    ?Empty@?$CSimpleStringT@G$0A@@ATL@@QEAAXXZ; ATL::CSimpleStringT<ushort,0>::Empty(void)
0x180019696  jmp     short loc_180019707
0x180019698  mov     edx, r15d
0x18001969b  call    ?GetBufferSetLength@?$CSimpleStringT@G$0A@@ATL@@QEAAPEAGH@Z; ATL::CSimpleStringT<ushort,0>::GetBufferSetLength(int)
0x1800196a0  mov     r12, rax
0x1800196a3  mov     [rsp+0B8h+Type], 0
0x1800196ab  lea     ecx, [r15+r15]
0x1800196af  mov     dword ptr [rsp+0B8h+Data], ecx
0x1800196b6  lea     rax, [rsp+0B8h+Data]
0x1800196be  mov     qword ptr [rsp+0B8h+cbData], rax; lpcbData
0x1800196c3  mov     [rsp+0B8h+lpData], r12; lpData
0x1800196c8  lea     r9, [rsp+0B8h+Type]; lpType
0x1800196cd  xor     r8d, r8d; lpReserved
0x1800196d0  mov     rdx, [r14+rsi*8]; lpValueName
0x1800196d4  mov     rcx, rdi; hKey
0x1800196d7  call    cs:__imp_RegQueryValueExW
0x1800196dd  mov     ebx, eax
0x1800196df  xor     esi, esi
0x1800196e1  test    eax, eax
0x1800196e3  jnz     short loc_1800196F5
0x1800196e5  mov     eax, [rsp+0B8h+Type]
0x1800196e9  dec     eax
0x1800196eb  cmp     eax, 1
0x1800196ee  jbe     short loc_18001970F
0x1800196f0  mov     ebx, 0Dh
0x1800196f5  xor     edx, edx
0x1800196f7  mov     rcx, r13
0x1800196fa  call    ?SetLength@?$CSimpleStringT@G$0A@@ATL@@AEAAXH@Z; ATL::CSimpleStringT<ushort,0>::SetLength(int)
0x1800196ff  mov     r12b, byte ptr [rsp+0B8h+arg_8]
0x180019707  xor     r13d, r13d
0x18001970a  jmp     loc_180019527
0x18001970f  test    r12, r12
0x180019712  jz      short loc_18001973A
0x180019714  mov     edx, dword ptr [rsp+0B8h+Data]
0x18001971b  test    edx, edx
0x18001971d  jz      short loc_180019733
0x18001971f  test    dl, 1
0x180019722  jnz     short loc_1800196F0
0x180019724  mov     eax, edx
0x180019726  shr     rax, 1
0x180019729  cmp     [r12+rax*2-2], si
0x18001972f  jz      short loc_180019741
0x180019731  jmp     short loc_1800196F0
0x180019733  mov     [r12], si
0x180019738  jmp     short loc_180019741
0x18001973a  mov     edx, dword ptr [rsp+0B8h+Data]
0x180019741  shr     edx, 1
0x180019743  mov     ebx, esi
0x180019745  jz      short loc_1800196F5
0x180019747  dec     edx
0x180019749  mov     rcx, r13
0x18001974c  call    ?ReleaseBuffer@?$CSimpleStringT@G$0A@@ATL@@QEAAXH@Z; ATL::CSimpleStringT<ushort,0>::ReleaseBuffer(int)
0x180019751  jmp     short loc_1800196FF
0x180019753  mov     ebx, [rsp+0B8h+arg_8]
0x18001975a  jmp     loc_18001994E
0x18001975f  movsxd  rax, dword ptr [r14+rsi*8+0Ch]
0x180019764  add     r15, rax
0x180019767  test    r12b, r12b
0x18001976a  jz      short loc_1800197AC
0x18001976c  mov     rcx, [r15]
0x18001976f  mov     rax, [r15+8]
0x180019773  sub     rax, rcx
0x180019776  and     eax, 0FFFFFFFCh
0x180019779  mov     [rsp+0B8h+cbData], eax; cbData
0x18001977d  mov     [rsp+0B8h+lpData], rcx; lpData
0x180019782  mov     r9d, 3; dwType
0x180019788  xor     r8d, r8d; Reserved
0x18001978b  mov     rcx, rdi; hKey
0x18001978e  call    cs:__imp_RegSetValueExW
0x180019794  mov     ebx, eax
0x180019796  test    eax, eax
0x180019798  jz      loc_18001957A
0x18001979e  jle     loc_180019536
0x1800197a4  movzx   ebx, ax
0x1800197a7  jmp     loc_180019530
0x1800197ac  mov     qword ptr [rsp+0B8h+Type], r13
0x1800197b1  mov     [rsp+0B8h+arg_10], r13d
0x1800197b9  mov     dword ptr [rsp+0B8h+Data], r13d
0x1800197c1  lea     rax, [rsp+0B8h+arg_10]
0x1800197c9  mov     qword ptr [rsp+0B8h+cbData], rax; lpcbData
0x1800197ce  mov     [rsp+0B8h+lpData], r13; lpData
0x1800197d3  lea     r9, [rsp+0B8h+Data]; lpType
0x1800197db  xor     r8d, r8d; lpReserved
0x1800197de  mov     rcx, rdi; hKey
0x1800197e1  call    cs:__imp_RegQueryValueExW
0x1800197e7  mov     ebx, eax
0x1800197e9  test    eax, eax
0x1800197eb  jz      short loc_1800197F1
0x1800197ed  jg      short loc_180019800
0x1800197ef  jmp     short loc_180019809
0x1800197f1  cmp     dword ptr [rsp+0B8h+Data], 3
0x1800197f9  jz      short loc_180019815
0x1800197fb  mov     ebx, 0Dh
0x180019800  movzx   ebx, bx
0x180019803  or      ebx, 80070000h
0x180019809  xor     ecx, ecx; Block
0x18001980b  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180019810  jmp     loc_180019536
0x180019815  mov     edx, [rsp+0B8h+arg_10]
0x18001981c  lea     rcx, [rsp+0B8h+Type]
0x180019821  call    ?Allocate@?$CAutoVectorPtr@E@ATL@@QEAA_N_K@Z; ATL::CAutoVectorPtr<uchar>::Allocate(unsigned __int64)
0x180019826  test    al, al
0x180019828  jnz     short loc_18001983E
0x18001982a  mov     rcx, qword ptr [rsp+0B8h+Type]; Block
0x18001982f  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180019834  mov     ebx, 8007000Eh
0x180019839  jmp     loc_18001994E
0x18001983e  mov     dword ptr [rsp+0B8h+Data], r13d
0x180019846  lea     rax, [rsp+0B8h+arg_10]
0x18001984e  mov     qword ptr [rsp+0B8h+cbData], rax; lpcbData
0x180019853  mov     rbx, qword ptr [rsp+0B8h+Type]
0x180019858  mov     [rsp+0B8h+lpData], rbx; lpData
0x18001985d  lea     r9, [rsp+0B8h+Data]; lpType
0x180019865  xor     r8d, r8d; lpReserved
0x180019868  mov     rdx, [r14+rsi*8]; lpValueName
0x18001986c  mov     rcx, rdi; hKey
0x18001986f  call    cs:__imp_RegQueryValueExW
0x180019875  mov     esi, eax
0x180019877  test    eax, eax
0x180019879  jz      short loc_18001987F
0x18001987b  jg      short loc_18001988E
0x18001987d  jmp     short loc_180019897
0x18001987f  cmp     dword ptr [rsp+0B8h+Data], 3
  ... truncated ...
```
