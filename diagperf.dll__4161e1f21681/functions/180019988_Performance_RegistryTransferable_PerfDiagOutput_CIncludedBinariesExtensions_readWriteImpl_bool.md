# Performance::RegistryTransferable<PerfDiagOutput::CIncludedBinariesExtensions>::readWriteImpl(bool)

- ea: `0x180019988`
- end: `0x180019f73`
- name: `?readWriteImpl@?$RegistryTransferable@VCIncludedBinariesExtensions@PerfDiagOutput@@@Performance@@AEAAJ_N@Z`
- size: `1515`
- prototype: ``
- caller_count: `2`
- callee_count: `14`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18003b3f0`
- `0x1800c9b80`

## callees

- `0x18001890c`
- `0x180018aa4`
- `0x180019310`
- `0x18001933c`
- `0x180019370`
- `0x180019988`
- `0x180019f7c`
- `0x18001a56c`
- `0x180039b68`
- `0x180041ea8`
- `0x180042fe0`
- `0x180056c14`
- `0x180057836`
- `0x1800d6010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180019ac7`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180019b22`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180019d42`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180019eda`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180019ac7`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180019b22`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180019d42`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180019eda`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180019b6c`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180019c0b`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180019c8b`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180019d95`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180019e23`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180019f11`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180019b6c`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180019c0b`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180019c8b`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180019d95`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180019e23`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180019f11`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180019a1e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180019a7e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180019bac`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180019e5c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180019f58`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180019a1e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180019a7e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180019bac`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180019e5c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180019f58`

## pseudocode

```c
__int64 __fastcall Performance::RegistryTransferable<PerfDiagOutput::CIncludedBinariesExtensions>::readWriteImpl(
        __int64 (__fastcall ***a1)(_QWORD, HKEY *, LPCWSTR *),
        char a2)
{
  char v2; // r12
  __int64 (__fastcall ***v3)(_QWORD, HKEY *, LPCWSTR *); // r14
  __int64 v4; // r15
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
  DWORD v24; // r14d
  BYTE *BufferSetLength; // r12
  unsigned int v26; // edx
  char *v27; // r14
  LSTATUS v28; // eax
  LSTATUS v29; // eax
  void *v30; // rbx
  LSTATUS v31; // eax
  unsigned int v32; // esi
  BYTE *v33; // rcx
  unsigned int lpData; // [rsp+20h] [rbp-98h]
  struct _SECURITY_ATTRIBUTES *v35; // [rsp+30h] [rbp-88h]
  unsigned int *v36; // [rsp+38h] [rbp-80h]
  DWORD Type[2]; // [rsp+40h] [rbp-78h] BYREF
  LPCWSTR lpSubKey; // [rsp+48h] [rbp-70h] BYREF
  HKEY v39; // [rsp+50h] [rbp-68h] BYREF
  __int64 v40; // [rsp+58h] [rbp-60h]
  HKEY hKey[10]; // [rsp+68h] [rbp-50h] BYREF
  DWORD v44; // [rsp+D0h] [rbp+18h] BYREF
  unsigned __int64 Data; // [rsp+D8h] [rbp+20h] BYREF

  v2 = a2;
  v3 = a1;
  v39 = 0;
  lpSubKey = 0;
  v4 = (**a1)(a1, &v39, &lpSubKey);
  memset(hKey, 0, 24);
  v6 = ATL::CRegKey::Create((ATL::CRegKey *)hKey, v39, lpSubKey, v5, lpData, v2 != 0 ? 131103 : 131097, v35, v36);
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
    v40 = v11;
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
      v33 = (BYTE *)v3 + *(int *)(v4 + 24 * v11 + 12);
      if ( v2 )
      {
        LODWORD(Data) = *(_DWORD *)v33;
        Value = RegSetValueExW(v12, v14, 0, 4u, (const BYTE *)&Data, 4u);
      }
      else
      {
        LODWORD(Data) = 0;
        Type[0] = 4;
        Value = RegQueryValueExW(v12, v14, 0, (LPDWORD)&Data, v33, Type);
        if ( !Value )
          Value = (_DWORD)Data != 4 ? 0xD : 0;
      }
      if ( Value )
      {
        if ( Value > 0 )
          Value = (unsigned __int16)Value | 0x80070000;
        goto LABEL_91;
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
    v11 = v40 + 1;
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
  v44 = 0;
  LODWORD(Data) = 0;
  v29 = RegQueryValueExW(v12, v14, 0, (LPDWORD)&Data, 0, &v44);
  Value = v29;
  if ( v29 )
  {
    if ( v29 > 0 )
      goto LABEL_70;
    goto LABEL_71;
  }
  if ( (_DWORD)Data == 3 )
  {
    if ( !(unsigned __int8)ATL::CAutoVectorPtr<unsigned char>::Allocate(Type, v44) )
    {
      operator delete(*(void **)Type);
      Value = -2147024882;
LABEL_91:
      ATL::CRegKey::Close((ATL::CRegKey *)hKey);
      return (unsigned int)Value;
    }
    LODWORD(Data) = 0;
    v30 = *(void **)Type;
    v31 = RegQueryValueExW(v12, *(LPCWSTR *)(v4 + 8 * v13), 0, (LPDWORD)&Data, *(LPBYTE *)Type, &v44);
    v32 = v31;
    if ( v31 )
    {
      if ( v31 <= 0 )
        goto LABEL_80;
      goto LABEL_79;
    }
    if ( (_DWORD)Data != 3 )
    {
      LOWORD(v32) = 13;
LABEL_79:
      v32 = (unsigned __int16)v32 | 0x80070000;
LABEL_80:
      operator delete(v30);
      if ( v12 )
        RegCloseKey(v12);
      return v32;
    }
    std::vector<unsigned long>::resize(v27, (unsigned __int64)v44 >> 2);
    memcpy_0(*(void **)v27, v30, v44);
    operator delete(v30);
    goto LABEL_29;
  }
  LOWORD(Value) = 13;
LABEL_70:
  Value = (unsigned __int16)Value | 0x80070000;
LABEL_71:
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
0x180019988  mov     byte ptr [rsp+arg_8], dl
0x18001998c  mov     r11, rsp
0x18001998f  mov     [r11+8], rcx
0x180019993  push    rbx
0x180019994  push    rsi
0x180019995  push    rdi
0x180019996  push    r12
0x180019998  push    r13
0x18001999a  push    r14
0x18001999c  push    r15
0x18001999e  sub     rsp, 80h
0x1800199a5  mov     r12b, dl
0x1800199a8  mov     r14, rcx
0x1800199ab  xor     r13d, r13d
0x1800199ae  mov     [r11-68h], r13
0x1800199b2  mov     [r11-70h], r13
0x1800199b6  mov     rax, [rcx]
0x1800199b9  lea     r8, [r11-70h]
0x1800199bd  lea     rdx, [r11-68h]
0x1800199c1  mov     rax, [rax]
0x1800199c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800199c9  mov     r15, rax
0x1800199cc  mov     [rsp+0B8h+hKey], r13
0x1800199d1  mov     [rsp+0B8h+var_48], r13
0x1800199d6  mov     [rsp+0B8h+var_40], r13
0x1800199db  mov     cl, r12b
0x1800199de  neg     cl
0x1800199e0  sbb     edx, edx
0x1800199e2  and     edx, 6
0x1800199e5  add     edx, 20019h
0x1800199eb  mov     [rsp+0B8h+cbData], edx; unsigned int
0x1800199ef  mov     r8, [rsp+0B8h+lpSubKey]; lpSubKey
0x1800199f4  mov     rdx, [rsp+0B8h+var_68]; hKey
0x1800199f9  lea     rcx, [rsp+0B8h+hKey]; this
0x1800199fe  call    ?Create@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGPEAGKKPEAU_SECURITY_ATTRIBUTES@@PEAK@Z; ATL::CRegKey::Create(HKEY__ *,ushort const *,ushort *,ulong,ulong,_SECURITY_ATTRIBUTES *,ulong *)
0x180019a03  mov     ebx, eax
0x180019a05  test    eax, eax
0x180019a07  jz      short loc_180019A2B
0x180019a09  jle     short loc_180019A14
0x180019a0b  movzx   ebx, ax
0x180019a0e  or      ebx, 80070000h
0x180019a14  mov     rcx, [rsp+0B8h+hKey]; hKey
0x180019a19  test    rcx, rcx
0x180019a1c  jz      short loc_180019A24
0x180019a1e  call    cs:__imp_RegCloseKey
0x180019a24  mov     eax, ebx
0x180019a26  jmp     loc_180019F60
0x180019a2b  mov     rax, r13
0x180019a2e  mov     rdi, [rsp+0B8h+hKey]
0x180019a33  mov     [rsp+0B8h+var_60], rax
0x180019a38  lea     rsi, [rax+rax*2]
0x180019a3c  mov     rdx, [r15+rsi*8]; unsigned __int16 *
0x180019a40  test    rdx, rdx
0x180019a43  jz      loc_180019F50
0x180019a49  mov     ecx, [r15+rsi*8+8]
0x180019a4e  test    ecx, ecx
0x180019a50  jz      loc_180019EA3
0x180019a56  sub     ecx, 1
0x180019a59  jz      loc_180019D13
0x180019a5f  sub     ecx, 1
0x180019a62  jz      loc_180019BBC
0x180019a68  sub     ecx, 1
0x180019a6b  jz      loc_180019AFB
0x180019a71  cmp     ecx, 1
0x180019a74  jz      short loc_180019A8E
0x180019a76  test    rdi, rdi
0x180019a79  jz      short loc_180019A84
0x180019a7b  mov     rcx, rdi; hKey
0x180019a7e  call    cs:__imp_RegCloseKey
0x180019a84  mov     eax, 8000FFFFh
0x180019a89  jmp     loc_180019F60
0x180019a8e  movsxd  r8, dword ptr [r15+rsi*8+0Ch]
0x180019a93  add     r8, r14; unsigned __int64 *
0x180019a96  test    r12b, r12b
0x180019a99  jz      short loc_180019ACF
0x180019a9b  mov     rax, [r8]
0x180019a9e  mov     [rsp+0B8h+Data], rax
0x180019aa6  mov     [rsp+0B8h+cbData], 8; cbData
0x180019aae  lea     rax, [rsp+0B8h+Data]
0x180019ab6  mov     [rsp+0B8h+lpData], rax; lpData
0x180019abb  mov     r9d, 0Bh; dwType
0x180019ac1  xor     r8d, r8d; Reserved
0x180019ac4  mov     rcx, rdi; hKey
0x180019ac7  call    cs:__imp_RegSetValueExW
0x180019acd  jmp     short loc_180019AD9
0x180019acf  lea     rcx, [rsp+0B8h+hKey]; this
0x180019ad4  call    ?QueryQWORDValue@CRegKey@ATL@@QEAAJPEBGAEA_K@Z; ATL::CRegKey::QueryQWORDValue(ushort const *,unsigned __int64 &)
0x180019ad9  mov     ebx, eax
0x180019adb  test    ebx, ebx
0x180019add  jz      short loc_180019B2E
0x180019adf  jle     short loc_180019AEA
0x180019ae1  movzx   ebx, bx
0x180019ae4  or      ebx, 80070000h
0x180019aea  test    rdi, rdi
0x180019aed  jz      loc_180019A24
0x180019af3  mov     rcx, rdi
0x180019af6  jmp     loc_180019A1E
0x180019afb  movsxd  rcx, dword ptr [r15+rsi*8+0Ch]
0x180019b00  add     rcx, r14
0x180019b03  mov     eax, [r15+rsi*8+10h]
0x180019b08  test    r12b, r12b
0x180019b0b  jz      short loc_180019B43
0x180019b0d  mov     [rsp+0B8h+cbData], eax; cbData
0x180019b11  mov     [rsp+0B8h+lpData], rcx; lpData
0x180019b16  mov     r9d, 3; dwType
0x180019b1c  xor     r8d, r8d; Reserved
0x180019b1f  mov     rcx, rdi; hKey
0x180019b22  call    cs:__imp_RegSetValueExW
0x180019b28  mov     ebx, eax
0x180019b2a  test    eax, eax
0x180019b2c  jnz     short loc_180019B78
0x180019b2e  mov     rax, [rsp+0B8h+var_60]
0x180019b33  inc     rax
0x180019b36  mov     r14, [rsp+0B8h+arg_0]
0x180019b3e  jmp     loc_180019A33
0x180019b43  mov     [rsp+0B8h+Type], eax
0x180019b47  mov     dword ptr [rsp+0B8h+Data], r13d
0x180019b4f  lea     rax, [rsp+0B8h+Type]
0x180019b54  mov     qword ptr [rsp+0B8h+cbData], rax; lpcbData
0x180019b59  mov     [rsp+0B8h+lpData], rcx; lpData
0x180019b5e  lea     r9, [rsp+0B8h+Data]; lpType
0x180019b66  xor     r8d, r8d; lpReserved
0x180019b69  mov     rcx, rdi; hKey
0x180019b6c  call    cs:__imp_RegQueryValueExW
0x180019b72  mov     ebx, eax
0x180019b74  test    eax, eax
0x180019b76  jz      short loc_180019B85
0x180019b78  test    ebx, ebx
0x180019b7a  jle     loc_180019AEA
0x180019b80  jmp     loc_180019AE1
0x180019b85  cmp     dword ptr [rsp+0B8h+Data], 3
0x180019b8d  jz      short loc_180019B99
0x180019b8f  mov     ebx, 0Dh
0x180019b94  jmp     loc_180019AE1
0x180019b99  mov     eax, [r15+rsi*8+10h]
0x180019b9e  cmp     [rsp+0B8h+Type], eax
0x180019ba2  jz      short loc_180019B2E
0x180019ba4  test    rdi, rdi
0x180019ba7  jz      short loc_180019BB2
0x180019ba9  mov     rcx, rdi; hKey
0x180019bac  call    cs:__imp_RegCloseKey
0x180019bb2  mov     eax, 8007000Dh
0x180019bb7  jmp     loc_180019F60
0x180019bbc  movsxd  r13, dword ptr [r15+rsi*8+0Ch]
0x180019bc1  add     r13, r14
0x180019bc4  xor     r14d, r14d
0x180019bc7  test    r12b, r12b
0x180019bca  jz      short loc_180019BE1
0x180019bcc  mov     r8, [r13+0]; unsigned __int16 *
0x180019bd0  lea     rcx, [rsp+0B8h+hKey]; this
0x180019bd5  call    ?SetStringValue@CRegKey@ATL@@QEAAJPEBG0K@Z; ATL::CRegKey::SetStringValue(ushort const *,ushort const *,ulong)
0x180019bda  mov     ebx, eax
0x180019bdc  jmp     loc_180019CBB
0x180019be1  mov     dword ptr [rsp+0B8h+Data], r14d
0x180019be9  mov     [rsp+0B8h+Type], r14d
0x180019bee  lea     rax, [rsp+0B8h+Type]
0x180019bf3  mov     qword ptr [rsp+0B8h+cbData], rax; lpcbData
0x180019bf8  mov     [rsp+0B8h+lpData], r14; lpData
0x180019bfd  lea     r9, [rsp+0B8h+Data]; lpType
0x180019c05  xor     r8d, r8d; lpReserved
0x180019c08  mov     rcx, rdi; hKey
0x180019c0b  call    cs:__imp_RegQueryValueExW
0x180019c11  mov     ebx, eax
0x180019c13  test    eax, eax
0x180019c15  jnz     loc_180019CBB
0x180019c1b  mov     eax, dword ptr [rsp+0B8h+Data]
0x180019c22  dec     eax
0x180019c24  cmp     eax, 1
0x180019c27  jbe     short loc_180019C33
0x180019c29  mov     ebx, 0Dh
0x180019c2e  jmp     loc_180019CBB
0x180019c33  mov     r14d, [rsp+0B8h+Type]
0x180019c38  shr     r14d, 1
0x180019c3b  xor     ebx, ebx
0x180019c3d  mov     rcx, r13
0x180019c40  test    r14d, r14d
0x180019c43  jnz     short loc_180019C4C
0x180019c45  call    ?Empty@?$CSimpleStringT@G$0A@@ATL@@QEAAXXZ; ATL::CSimpleStringT<ushort,0>::Empty(void)
0x180019c4a  jmp     short loc_180019CBB
0x180019c4c  mov     edx, r14d
0x180019c4f  call    ?GetBufferSetLength@?$CSimpleStringT@G$0A@@ATL@@QEAAPEAGH@Z; ATL::CSimpleStringT<ushort,0>::GetBufferSetLength(int)
0x180019c54  mov     r12, rax
0x180019c57  mov     [rsp+0B8h+Type], 0
0x180019c5f  lea     ecx, [r14+r14]
0x180019c63  mov     dword ptr [rsp+0B8h+Data], ecx
0x180019c6a  lea     rax, [rsp+0B8h+Data]
0x180019c72  mov     qword ptr [rsp+0B8h+cbData], rax; lpcbData
0x180019c77  mov     [rsp+0B8h+lpData], r12; lpData
0x180019c7c  lea     r9, [rsp+0B8h+Type]; lpType
0x180019c81  xor     r8d, r8d; lpReserved
0x180019c84  mov     rdx, [r15+rsi*8]; lpValueName
0x180019c88  mov     rcx, rdi; hKey
0x180019c8b  call    cs:__imp_RegQueryValueExW
0x180019c91  mov     ebx, eax
0x180019c93  xor     esi, esi
0x180019c95  test    eax, eax
0x180019c97  jnz     short loc_180019CA9
0x180019c99  mov     eax, [rsp+0B8h+Type]
0x180019c9d  dec     eax
0x180019c9f  cmp     eax, 1
0x180019ca2  jbe     short loc_180019CC3
0x180019ca4  mov     ebx, 0Dh
0x180019ca9  xor     edx, edx
0x180019cab  mov     rcx, r13
0x180019cae  call    ?SetLength@?$CSimpleStringT@G$0A@@ATL@@AEAAXH@Z; ATL::CSimpleStringT<ushort,0>::SetLength(int)
0x180019cb3  mov     r12b, byte ptr [rsp+0B8h+arg_8]
0x180019cbb  xor     r13d, r13d
0x180019cbe  jmp     loc_180019ADB
0x180019cc3  test    r12, r12
0x180019cc6  jz      short loc_180019CEE
0x180019cc8  mov     edx, dword ptr [rsp+0B8h+Data]
0x180019ccf  test    edx, edx
0x180019cd1  jz      short loc_180019CE7
0x180019cd3  test    dl, 1
0x180019cd6  jnz     short loc_180019CA4
0x180019cd8  mov     eax, edx
0x180019cda  shr     rax, 1
0x180019cdd  cmp     [r12+rax*2-2], si
0x180019ce3  jz      short loc_180019CF5
0x180019ce5  jmp     short loc_180019CA4
0x180019ce7  mov     [r12], si
0x180019cec  jmp     short loc_180019CF5
0x180019cee  mov     edx, dword ptr [rsp+0B8h+Data]
0x180019cf5  shr     edx, 1
0x180019cf7  mov     ebx, esi
0x180019cf9  jz      short loc_180019CA9
0x180019cfb  dec     edx
0x180019cfd  mov     rcx, r13
0x180019d00  call    ?ReleaseBuffer@?$CSimpleStringT@G$0A@@ATL@@QEAAXH@Z; ATL::CSimpleStringT<ushort,0>::ReleaseBuffer(int)
0x180019d05  jmp     short loc_180019CB3
0x180019d07  mov     ebx, [rsp+0B8h+arg_8]
0x180019d0e  jmp     loc_180019F41
0x180019d13  movsxd  rax, dword ptr [r15+rsi*8+0Ch]
0x180019d18  add     r14, rax
0x180019d1b  test    r12b, r12b
0x180019d1e  jz      short loc_180019D60
0x180019d20  mov     rcx, [r14]
0x180019d23  mov     rax, [r14+8]
0x180019d27  sub     rax, rcx
0x180019d2a  and     eax, 0FFFFFFFCh
0x180019d2d  mov     [rsp+0B8h+cbData], eax; cbData
0x180019d31  mov     [rsp+0B8h+lpData], rcx; lpData
0x180019d36  mov     r9d, 3; dwType
0x180019d3c  xor     r8d, r8d; Reserved
0x180019d3f  mov     rcx, rdi; hKey
0x180019d42  call    cs:__imp_RegSetValueExW
0x180019d48  mov     ebx, eax
0x180019d4a  test    eax, eax
0x180019d4c  jz      loc_180019B2E
0x180019d52  jle     loc_180019AEA
0x180019d58  movzx   ebx, ax
0x180019d5b  jmp     loc_180019AE4
0x180019d60  mov     qword ptr [rsp+0B8h+Type], r13
0x180019d65  mov     [rsp+0B8h+arg_10], r13d
0x180019d6d  mov     dword ptr [rsp+0B8h+Data], r13d
0x180019d75  lea     rax, [rsp+0B8h+arg_10]
0x180019d7d  mov     qword ptr [rsp+0B8h+cbData], rax; lpcbData
0x180019d82  mov     [rsp+0B8h+lpData], r13; lpData
0x180019d87  lea     r9, [rsp+0B8h+Data]; lpType
0x180019d8f  xor     r8d, r8d; lpReserved
0x180019d92  mov     rcx, rdi; hKey
0x180019d95  call    cs:__imp_RegQueryValueExW
0x180019d9b  mov     ebx, eax
0x180019d9d  test    eax, eax
0x180019d9f  jz      short loc_180019DA5
0x180019da1  jg      short loc_180019DB4
0x180019da3  jmp     short loc_180019DBD
0x180019da5  cmp     dword ptr [rsp+0B8h+Data], 3
0x180019dad  jz      short loc_180019DC9
0x180019daf  mov     ebx, 0Dh
0x180019db4  movzx   ebx, bx
0x180019db7  or      ebx, 80070000h
0x180019dbd  xor     ecx, ecx; Block
0x180019dbf  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180019dc4  jmp     loc_180019AEA
0x180019dc9  mov     edx, [rsp+0B8h+arg_10]
0x180019dd0  lea     rcx, [rsp+0B8h+Type]
0x180019dd5  call    ?Allocate@?$CAutoVectorPtr@E@ATL@@QEAA_N_K@Z; ATL::CAutoVectorPtr<uchar>::Allocate(unsigned __int64)
0x180019dda  test    al, al
0x180019ddc  jnz     short loc_180019DF2
0x180019dde  mov     rcx, qword ptr [rsp+0B8h+Type]; Block
0x180019de3  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180019de8  mov     ebx, 8007000Eh
0x180019ded  jmp     loc_180019F41
0x180019df2  mov     dword ptr [rsp+0B8h+Data], r13d
0x180019dfa  lea     rax, [rsp+0B8h+arg_10]
0x180019e02  mov     qword ptr [rsp+0B8h+cbData], rax; lpcbData
0x180019e07  mov     rbx, qword ptr [rsp+0B8h+Type]
0x180019e0c  mov     [rsp+0B8h+lpData], rbx; lpData
0x180019e11  lea     r9, [rsp+0B8h+Data]; lpType
0x180019e19  xor     r8d, r8d; lpReserved
0x180019e1c  mov     rdx, [r15+rsi*8]; lpValueName
0x180019e20  mov     rcx, rdi; hKey
0x180019e23  call    cs:__imp_RegQueryValueExW
0x180019e29  mov     esi, eax
0x180019e2b  test    eax, eax
0x180019e2d  jz      short loc_180019E33
0x180019e2f  jg      short loc_180019E42
0x180019e31  jmp     short loc_180019E4B
0x180019e33  cmp     dword ptr [rsp+0B8h+Data], 3
  ... truncated ...
```
