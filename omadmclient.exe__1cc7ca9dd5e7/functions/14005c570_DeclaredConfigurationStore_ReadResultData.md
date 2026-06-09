# DeclaredConfigurationStore_ReadResultData

- ea: `0x14005c570`
- end: `0x14005cc06`
- name: `DeclaredConfigurationStore_ReadResultData`
- size: `1686`
- prototype: `__int64 __fastcall(int, int, int, int, HKEY, HKEY hKey, LPCWSTR lpValueName, void *Block)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, authz_impersonation, registry_config`

## callers

- `0x140058a5c`

## callees

- `0x1400036e4`
- `0x140003eb4`
- `0x140005864`
- `0x140057e14`
- `0x140058358`
- `0x14005c570`
- `0x14005d570`
- `0x14005d6fc`
- `0x1400647c8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14005c79a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14005c9fc`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14005c79a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14005c9fc`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x14005c7e2`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x14005c881`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x14005c920`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x14005ca44`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x14005cb83`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x14005c7e2`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x14005c881`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x14005c920`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x14005ca44`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x14005cb83`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14005c60b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14005c716`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14005c82a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14005c991`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14005ca8c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14005cb2c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14005cbdf`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14005c60b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14005c716`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14005c82a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14005c991`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14005ca8c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14005cb2c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14005cbdf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14005c5fa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14005c5fa`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14005c619`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14005c619`
- `OLEAUT32!__imp_SysAllocString` at `0x14005c958`
- `OLEAUT32!__imp_SysAllocString` at `0x14005c958`
- `DMOleAutUtils!MultiStringToSafeArray` at `0x14005caf9`
- `DMOleAutUtils!MultiStringToSafeArray` at `0x14005caf9`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall DeclaredConfigurationStore_ReadResultData(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        HKEY lpcbData,
        HKEY hKey,
        LPCWSTR lpValueName,
        unsigned __int16 *Block)
{
  unsigned __int16 *v8; // rdi
  const WCHAR *v9; // r14
  HKEY v10; // r12
  HKEY v11; // r15
  DWORD LastError; // ebx
  int Value; // ebx
  unsigned __int16 *v14; // rbx
  int v15; // edi
  __int64 v17; // r15
  LSTATUS v18; // eax
  HKEY v19; // r15
  LSTATUS v20; // eax
  unsigned __int64 v21; // rbx
  unsigned __int64 v22; // rax
  BYTE *v23; // rax
  BYTE *v24; // rsi
  LSTATUS v25; // eax
  void *v26; // rcx
  LSTATUS v27; // eax
  int v28; // eax
  bool v29; // sf
  BYTE Data[8]; // [rsp+38h] [rbp-30h] BYREF
  HKEY *p_hKey; // [rsp+40h] [rbp-28h]
  HKEY v32; // [rsp+48h] [rbp-20h] BYREF
  char v33; // [rsp+50h] [rbp-18h]
  __int64 Type; // [rsp+C8h] [rbp+60h] BYREF

  Type = a4;
  hKey = 0;
  v8 = Block;
  if ( !Block )
    return 2147942487LL;
  v9 = lpValueName;
  if ( !lpValueName || !a1 || !a2 || !a3 )
    return 2147942487LL;
  p_hKey = &hKey;
  v32 = 0;
  v33 = 1;
  GetResultsEnrollmentIdSidStateDocIdVersionKey(a1, a2, a3, &v32);
  if ( v33 )
  {
    v10 = v32;
    v11 = *p_hKey;
    if ( *p_hKey )
    {
      LastError = GetLastError();
      RegCloseKey(v11);
      SetLastError(LastError);
    }
    *p_hKey = v10;
  }
  switch ( *v8 )
  {
    case 3u:
      LODWORD(Block) = 0;
      LODWORD(Type) = 4;
      LODWORD(lpcbData) = 4;
      if ( hKey )
      {
        Value = RegQueryValueExW(hKey, v9, 0, (LPDWORD)&Type, (LPBYTE)&Block, (LPDWORD)&lpcbData);
        if ( Value )
        {
          v28 = 0;
          v29 = Value < 0;
          if ( Value > 0 )
          {
            Value = (unsigned __int16)Value | 0x80070000;
            v29 = Value < 0;
          }
          if ( v29 )
            goto LABEL_59;
        }
        else
        {
          if ( (_DWORD)Type != 4 )
            goto LABEL_45;
          v28 = (int)Block;
        }
        *v8 = 3;
        *((_DWORD *)v8 + 2) = v28;
        goto LABEL_88;
      }
LABEL_58:
      Value = -2147024809;
      goto LABEL_59;
    case 5u:
      goto LABEL_62;
    case 8u:
      v19 = hKey;
      LODWORD(Block) = 1;
      LODWORD(Type) = 0;
      if ( hKey )
      {
        v20 = RegQueryValueExW(hKey, v9, 0, (LPDWORD)&Block, 0, (LPDWORD)&Type);
        Value = v20;
        if ( v20 )
        {
          if ( v20 > 0 )
            Value = (unsigned __int16)v20 | 0x80070000;
          goto LABEL_55;
        }
        if ( (_DWORD)Block == 1 )
        {
          v21 = ((unsigned __int64)(unsigned int)Type >> 1) + 1;
          v22 = 2 * v21;
          if ( !is_mul_ok(v21, 2u) )
            v22 = -1;
          v23 = (BYTE *)operator new[](v22, (const struct std::nothrow_t *)std::nothrow);
          v24 = v23;
          if ( !v23 )
          {
            Value = -2147024882;
            goto LABEL_59;
          }
          memset_0(v23, 0, v21);
          v25 = RegQueryValueExW(v19, v9, 0, (LPDWORD)&Block, v24, (LPDWORD)&Type);
          Value = v25;
          if ( !v25 )
          {
LABEL_56:
            *v8 = 8;
            *((_QWORD *)v8 + 1) = SysAllocString((const OLECHAR *)v24);
            v26 = v24;
LABEL_57:
            operator delete(v26);
            goto LABEL_88;
          }
          if ( v25 > 0 )
            Value = (unsigned __int16)v25 | 0x80070000;
          operator delete(v24);
LABEL_55:
          v24 = 0;
          if ( Value < 0 )
            goto LABEL_59;
          goto LABEL_56;
        }
LABEL_45:
        Value = -2147418113;
        goto LABEL_59;
      }
      goto LABEL_58;
    case 0x14u:
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_OsConfigurationRegistryProvider>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_OsConfigurationRegistryProvider>::GetImpl'::`2'::impl) )
      {
        v17 = 0;
        *(_QWORD *)Data = 0;
        LODWORD(Type) = 11;
        lpcbData = 0;
        LODWORD(Block) = 8;
        if ( hKey )
        {
          lpcbData = hKey;
          v18 = RegQueryValueExW(hKey, v9, 0, (LPDWORD)&Type, Data, (LPDWORD)&Block);
          Value = v18;
          if ( v18 )
          {
            if ( v18 > 0 )
              Value = (unsigned __int16)v18 | 0x80070000;
          }
          else if ( (_DWORD)Type == 11 )
          {
            Value = 0;
            v17 = *(_QWORD *)Data;
          }
          else
          {
            Value = -2147418113;
          }
        }
        else
        {
          Value = -2147024809;
        }
        if ( Value < 0 )
          goto LABEL_59;
        *v8 = 20;
        goto LABEL_39;
      }
LABEL_62:
      if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_OsConfigurationRegistryProvider>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_OsConfigurationRegistryProvider>::GetImpl'::`2'::impl) )
      {
LABEL_73:
        if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_OsConfigurationRegistryProvider>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_OsConfigurationRegistryProvider>::GetImpl'::`2'::impl) )
          break;
        Block = 0;
        Value = DCCDNUtil_GetRegistryMultiString(hKey, 0, v9, &Block, (unsigned int *)&Type);
        if ( Value >= 0 )
        {
          *v8 = 8200;
          MultiStringToSafeArray(Block, 0, (struct tagSAFEARRAY **)v8 + 1);
          v26 = Block;
          goto LABEL_57;
        }
LABEL_59:
        if ( hKey )
          RegCloseKey(hKey);
        return (unsigned int)Value;
      }
      v17 = 0;
      *(_QWORD *)Data = 0;
      LODWORD(Type) = 11;
      lpcbData = 0;
      LODWORD(Block) = 8;
      if ( hKey )
      {
        lpcbData = hKey;
        v27 = RegQueryValueExW(hKey, v9, 0, (LPDWORD)&Type, Data, (LPDWORD)&Block);
        Value = v27;
        if ( v27 )
        {
          if ( v27 > 0 )
            Value = (unsigned __int16)v27 | 0x80070000;
        }
        else if ( (_DWORD)Type == 11 )
        {
          Value = 0;
          v17 = *(_QWORD *)Data;
        }
        else
        {
          Value = -2147418113;
        }
      }
      else
      {
        Value = -2147024809;
      }
      if ( Value < 0 )
        goto LABEL_59;
      *v8 = 5;
LABEL_39:
      *((_QWORD *)v8 + 1) = v17;
LABEL_88:
      if ( hKey )
        RegCloseKey(hKey);
      return 0;
    case 0x2008u:
      goto LABEL_73;
    case 0x2011u:
      Block = 0;
      LODWORD(Type) = 0;
      Value = DCGetRegistryBinary(hKey, 0, v9, &Block, &Type);
      if ( Value < 0 )
      {
        if ( Block )
          operator delete(Block);
        goto LABEL_59;
      }
      v14 = Block;
      v15 = DCInlineSetBinaryToVariant(Block, (unsigned int)Type, (__int64)v8);
      if ( v15 < 0 )
      {
        if ( v14 )
          operator delete(v14);
        if ( hKey )
          RegCloseKey(hKey);
        return (unsigned int)v15;
      }
      if ( v14 )
        operator delete(v14);
      goto LABEL_88;
  }
  if ( hKey )
    RegCloseKey(hKey);
  return 2147549183LL;
}

```

## disassembly

```asm
0x14005c570  mov     [rsp-40h+Type], r9
0x14005c575  push    rbp
0x14005c576  push    rbx
0x14005c577  push    rsi
0x14005c578  push    rdi
0x14005c579  push    r12
0x14005c57b  push    r13
0x14005c57d  push    r14
0x14005c57f  push    r15
0x14005c581  mov     rbp, rsp
0x14005c584  sub     rsp, 68h
0x14005c588  xor     r13d, r13d
0x14005c58b  mov     [rbp+hKey], r13
0x14005c58f  mov     rdi, [rbp+Block]
0x14005c596  test    rdi, rdi
0x14005c599  jz      loc_14005CBEF
0x14005c59f  mov     r14, [rbp+lpValueName]
0x14005c5a3  test    r14, r14
0x14005c5a6  jz      loc_14005CBEF
0x14005c5ac  test    rcx, rcx
0x14005c5af  jz      loc_14005CBEF
0x14005c5b5  test    rdx, rdx
0x14005c5b8  jz      loc_14005CBEF
0x14005c5be  test    r8, r8
0x14005c5c1  jz      loc_14005CBEF
0x14005c5c7  lea     rax, [rbp+hKey]
0x14005c5cb  mov     [rbp+var_28], rax
0x14005c5cf  mov     [rbp+var_20], r13
0x14005c5d3  lea     esi, [r13+1]
0x14005c5d7  mov     [rbp+var_18], sil
0x14005c5db  lea     r9, [rbp+var_20]
0x14005c5df  call    GetResultsEnrollmentIdSidStateDocIdVersionKey
0x14005c5e4  cmp     [rbp+var_18], r13b
0x14005c5e8  jz      short loc_14005C62D
0x14005c5ea  mov     r12, [rbp+var_20]
0x14005c5ee  mov     rsi, [rbp+var_28]
0x14005c5f2  mov     r15, [rsi]
0x14005c5f5  test    r15, r15
0x14005c5f8  jz      short loc_14005C625
0x14005c5fa  call    cs:__imp_GetLastError
0x14005c601  nop     dword ptr [rax+rax+00h]
0x14005c606  mov     ebx, eax
0x14005c608  mov     rcx, r15; hKey
0x14005c60b  call    cs:__imp_RegCloseKey
0x14005c612  nop     dword ptr [rax+rax+00h]
0x14005c617  mov     ecx, ebx; dwErrCode
0x14005c619  call    cs:__imp_SetLastError
0x14005c620  nop     dword ptr [rax+rax+00h]
0x14005c625  mov     [rsi], r12
0x14005c628  mov     esi, 1
0x14005c62d  mov     rcx, r13; Block
0x14005c630  mov     [rbp+lpSubKey], rcx
0x14005c634  movzx   edx, word ptr [rdi]
0x14005c637  mov     r12d, 2
0x14005c63d  lea     r15d, [r12+1]
0x14005c642  sub     edx, r15d
0x14005c645  jz      loc_14005CB42
0x14005c64b  lea     rbx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_OsConfigurationRegistryProvider@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_OsConfigurationRegistryProvider@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_OsConfigurationRegistryProvider> `wil::Feature<__WilFeatureTraits_Feature_OsConfigurationRegistryProvider>::GetImpl(void)'::`2'::impl
0x14005c652  sub     edx, r12d
0x14005c655  jz      loc_14005C9A4
0x14005c65b  sub     edx, r15d
0x14005c65e  jz      loc_14005C84C
0x14005c664  sub     edx, 0Ch
0x14005c667  jz      loc_14005C742
0x14005c66d  sub     edx, 1FF4h
0x14005c673  jz      loc_14005CAAA
0x14005c679  cmp     edx, 9
0x14005c67c  jnz     loc_14005CB15
0x14005c682  mov     [rbp+Block], r13
0x14005c689  mov     dword ptr [rbp+Type], r13d
0x14005c68d  lea     rax, [rbp+Type]
0x14005c691  mov     [rsp+68h+phkResult], rax
0x14005c696  lea     r9, [rbp+Block]
0x14005c69d  mov     r8, r14
0x14005c6a0  xor     edx, edx
0x14005c6a2  mov     rcx, [rbp+hKey]
0x14005c6a6  call    DCGetRegistryBinary
0x14005c6ab  mov     ebx, eax
0x14005c6ad  test    eax, eax
0x14005c6af  jns     short loc_14005C6CF
0x14005c6b1  mov     rcx, [rbp+Block]; Block
0x14005c6b8  test    rcx, rcx
0x14005c6bb  jz      short loc_14005C6C6
0x14005c6bd  mov     rdx, rsi
0x14005c6c0  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14005c6c5  nop
0x14005c6c6  mov     rcx, [rbp+lpSubKey]
0x14005c6ca  jmp     loc_14005C97A
0x14005c6cf  mov     r8, rdi
0x14005c6d2  mov     edx, dword ptr [rbp+Type]; Size
0x14005c6d5  mov     rbx, [rbp+Block]
0x14005c6dc  mov     rcx, rbx; Src
0x14005c6df  call    DCInlineSetBinaryToVariant
0x14005c6e4  mov     edi, eax
0x14005c6e6  test    eax, eax
0x14005c6e8  jns     short loc_14005C729
0x14005c6ea  test    rbx, rbx
0x14005c6ed  jz      short loc_14005C6FB
0x14005c6ef  mov     rdx, rsi
0x14005c6f2  mov     rcx, rbx; Block
0x14005c6f5  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14005c6fa  nop
0x14005c6fb  mov     rcx, [rbp+lpSubKey]; Block
0x14005c6ff  test    rcx, rcx
0x14005c702  jz      short loc_14005C70D
0x14005c704  mov     rdx, r12
0x14005c707  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14005c70c  nop
0x14005c70d  mov     rcx, [rbp+hKey]; hKey
0x14005c711  test    rcx, rcx
0x14005c714  jz      short loc_14005C722
0x14005c716  call    cs:__imp_RegCloseKey
0x14005c71d  nop     dword ptr [rax+rax+00h]
0x14005c722  mov     eax, edi
0x14005c724  jmp     loc_14005CBF4
0x14005c729  test    rbx, rbx
0x14005c72c  jz      loc_14005CBC4
0x14005c732  mov     rdx, rsi
0x14005c735  mov     rcx, rbx; Block
0x14005c738  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14005c73d  jmp     loc_14005CBC4
0x14005c742  mov     rcx, rbx
0x14005c745  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_OsConfigurationRegistryProvider@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_OsConfigurationRegistryProvider>::__private_IsEnabled(void)
0x14005c74a  test    al, al
0x14005c74c  jz      loc_14005C9A4
0x14005c752  mov     r15, r13
0x14005c755  mov     rsi, [rbp+lpSubKey]
0x14005c759  mov     rcx, [rbp+hKey]; hKey
0x14005c75d  mov     qword ptr [rbp+Data], r13
0x14005c761  mov     dword ptr [rbp+Type], 0Bh
0x14005c768  mov     [rbp+arg_20], r13
0x14005c76c  mov     eax, 8
0x14005c771  mov     dword ptr [rbp+Block], eax
0x14005c777  test    rcx, rcx
0x14005c77a  jz      loc_14005C817
0x14005c780  test    rsi, rsi
0x14005c783  jz      short loc_14005C7BF
0x14005c785  lea     rax, [rbp+arg_20]
0x14005c789  mov     [rsp+68h+phkResult], rax; phkResult
0x14005c78e  mov     r9d, 20119h; samDesired
0x14005c794  xor     r8d, r8d; ulOptions
0x14005c797  mov     rdx, rsi; lpSubKey
0x14005c79a  call    cs:__imp_RegOpenKeyExW
0x14005c7a1  nop     dword ptr [rax+rax+00h]
0x14005c7a6  mov     ebx, eax
0x14005c7a8  test    eax, eax
0x14005c7aa  jz      short loc_14005C7B9
0x14005c7ac  jle     short loc_14005C821
0x14005c7ae  movzx   ebx, ax
0x14005c7b1  or      ebx, 80070000h
0x14005c7b7  jmp     short loc_14005C821
0x14005c7b9  mov     rcx, [rbp+arg_20]
0x14005c7bd  jmp     short loc_14005C7C3
0x14005c7bf  mov     [rbp+arg_20], rcx
0x14005c7c3  lea     rax, [rbp+Block]
0x14005c7ca  mov     [rsp+68h+lpcbData], rax; lpcbData
0x14005c7cf  lea     rax, [rbp+Data]
0x14005c7d3  mov     [rsp+68h+phkResult], rax; lpData
0x14005c7d8  lea     r9, [rbp+Type]; lpType
0x14005c7dc  xor     r8d, r8d; lpReserved
0x14005c7df  mov     rdx, r14; lpValueName
0x14005c7e2  call    cs:__imp_RegQueryValueExW
0x14005c7e9  nop     dword ptr [rax+rax+00h]
0x14005c7ee  mov     ebx, eax
0x14005c7f0  test    eax, eax
0x14005c7f2  jz      short loc_14005C801
0x14005c7f4  jle     short loc_14005C81C
0x14005c7f6  movzx   ebx, ax
0x14005c7f9  or      ebx, 80070000h
0x14005c7ff  jmp     short loc_14005C81C
0x14005c801  cmp     dword ptr [rbp+Type], 0Bh
0x14005c805  jz      short loc_14005C80E
0x14005c807  mov     ebx, 8000FFFFh
0x14005c80c  jmp     short loc_14005C81C
0x14005c80e  mov     ebx, r13d
0x14005c811  mov     r15, qword ptr [rbp+Data]
0x14005c815  jmp     short loc_14005C81C
0x14005c817  mov     ebx, 80070057h
0x14005c81c  test    rsi, rsi
0x14005c81f  jz      short loc_14005C836
0x14005c821  mov     rcx, [rbp+arg_20]; hKey
0x14005c825  test    rcx, rcx
0x14005c828  jz      short loc_14005C836
0x14005c82a  call    cs:__imp_RegCloseKey
0x14005c831  nop     dword ptr [rax+rax+00h]
0x14005c836  test    ebx, ebx
0x14005c838  js      loc_14005C6C6
0x14005c83e  mov     word ptr [rdi], 14h
0x14005c843  mov     [rdi+8], r15
0x14005c847  jmp     loc_14005CBC4
0x14005c84c  mov     r15, [rbp+hKey]
0x14005c850  mov     dword ptr [rbp+Block], esi
0x14005c856  mov     dword ptr [rbp+Type], r13d
0x14005c85a  test    r15, r15
0x14005c85d  jz      loc_14005C975
0x14005c863  lea     rax, [rbp+Type]
0x14005c867  mov     [rsp+68h+lpcbData], rax; lpcbData
0x14005c86c  mov     [rsp+68h+phkResult], r13; lpData
0x14005c871  lea     r9, [rbp+Block]; lpType
0x14005c878  xor     r8d, r8d; lpReserved
0x14005c87b  mov     rdx, r14; lpValueName
0x14005c87e  mov     rcx, r15; hKey
0x14005c881  call    cs:__imp_RegQueryValueExW
0x14005c888  nop     dword ptr [rax+rax+00h]
0x14005c88d  mov     ebx, eax
0x14005c88f  test    eax, eax
0x14005c891  jz      short loc_14005C8A7
0x14005c893  jle     loc_14005C945
0x14005c899  movzx   ebx, ax
0x14005c89c  or      ebx, 80070000h
0x14005c8a2  jmp     loc_14005C945
0x14005c8a7  cmp     dword ptr [rbp+Block], esi
0x14005c8ad  jz      short loc_14005C8BD
0x14005c8af  mov     ebx, 8000FFFFh
0x14005c8b4  mov     rcx, [rbp+lpSubKey]
0x14005c8b8  jmp     loc_14005C97A
0x14005c8bd  mov     ebx, dword ptr [rbp+Type]
0x14005c8c0  shr     rbx, 1
0x14005c8c3  inc     rbx
0x14005c8c6  mov     rax, r12
0x14005c8c9  mul     rbx
0x14005c8cc  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x14005c8d3  cmovb   rax, rcx
0x14005c8d7  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x14005c8de  mov     rcx, rax; unsigned __int64
0x14005c8e1  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x14005c8e6  mov     rsi, rax
0x14005c8e9  test    rax, rax
0x14005c8ec  jnz     short loc_14005C8F5
0x14005c8ee  mov     ebx, 8007000Eh
0x14005c8f3  jmp     short loc_14005C8B4
0x14005c8f5  mov     r8, rbx; Size
0x14005c8f8  xor     edx, edx; Val
0x14005c8fa  mov     rcx, rsi; void *
0x14005c8fd  call    memset_0
0x14005c902  lea     rax, [rbp+Type]
0x14005c906  mov     [rsp+68h+lpcbData], rax; lpcbData
0x14005c90b  mov     [rsp+68h+phkResult], rsi; lpData
0x14005c910  lea     r9, [rbp+Block]; lpType
0x14005c917  xor     r8d, r8d; lpReserved
0x14005c91a  mov     rdx, r14; lpValueName
0x14005c91d  mov     rcx, r15; hKey
0x14005c920  call    cs:__imp_RegQueryValueExW
0x14005c927  nop     dword ptr [rax+rax+00h]
0x14005c92c  mov     ebx, eax
0x14005c92e  test    eax, eax
0x14005c930  jz      short loc_14005C950
0x14005c932  jle     short loc_14005C93D
0x14005c934  movzx   ebx, ax
0x14005c937  or      ebx, 80070000h
0x14005c93d  mov     rcx, rsi; Block
0x14005c940  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14005c945  mov     rsi, r13
0x14005c948  test    ebx, ebx
0x14005c94a  js      loc_14005C8B4
0x14005c950  mov     word ptr [rdi], 8
0x14005c955  mov     rcx, rsi; psz
0x14005c958  call    cs:__imp_SysAllocString
0x14005c95f  nop     dword ptr [rax+rax+00h]
0x14005c964  mov     [rdi+8], rax
0x14005c968  mov     rcx, rsi; Block
0x14005c96b  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14005c970  jmp     loc_14005CBC4
0x14005c975  mov     ebx, 80070057h
0x14005c97a  test    rcx, rcx
0x14005c97d  jz      short loc_14005C988
0x14005c97f  mov     rdx, r12
0x14005c982  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14005c987  nop
0x14005c988  mov     rcx, [rbp+hKey]; hKey
0x14005c98c  test    rcx, rcx
0x14005c98f  jz      short loc_14005C99D
0x14005c991  call    cs:__imp_RegCloseKey
0x14005c998  nop     dword ptr [rax+rax+00h]
0x14005c99d  mov     eax, ebx
0x14005c99f  jmp     loc_14005CBF4
0x14005c9a4  mov     rcx, rbx
0x14005c9a7  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_OsConfigurationRegistryProvider@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_OsConfigurationRegistryProvider>::__private_IsEnabled(void)
0x14005c9ac  test    al, al
0x14005c9ae  jz      loc_14005CAAA
0x14005c9b4  mov     r15, r13
0x14005c9b7  mov     rsi, [rbp+lpSubKey]
0x14005c9bb  mov     rcx, [rbp+hKey]; hKey
0x14005c9bf  mov     qword ptr [rbp+Data], r13
0x14005c9c3  mov     dword ptr [rbp+Type], 0Bh
0x14005c9ca  mov     [rbp+arg_20], r13
0x14005c9ce  mov     eax, 8
0x14005c9d3  mov     dword ptr [rbp+Block], eax
0x14005c9d9  test    rcx, rcx
0x14005c9dc  jz      loc_14005CA79
0x14005c9e2  test    rsi, rsi
0x14005c9e5  jz      short loc_14005CA21
0x14005c9e7  lea     rax, [rbp+arg_20]
0x14005c9eb  mov     [rsp+68h+phkResult], rax; phkResult
0x14005c9f0  mov     r9d, 20119h; samDesired
0x14005c9f6  xor     r8d, r8d; ulOptions
0x14005c9f9  mov     rdx, rsi; lpSubKey
0x14005c9fc  call    cs:__imp_RegOpenKeyExW
0x14005ca03  nop     dword ptr [rax+rax+00h]
0x14005ca08  mov     ebx, eax
  ... truncated ...
```
