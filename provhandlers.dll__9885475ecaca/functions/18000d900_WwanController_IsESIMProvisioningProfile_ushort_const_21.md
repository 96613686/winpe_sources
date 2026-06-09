# WwanController::_IsESIMProvisioningProfile(ushort const (&)[21])

- ea: `0x18000d900`
- end: `0x18000dd6f`
- name: `?_IsESIMProvisioningProfile@WwanController@@CAKAEAY0BF@$$CBG@Z`
- size: `1135`
- prototype: `__int64 __fastcall(unsigned __int16 (*Src)[21])`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x18000c26c`

## callees

- `0x180001264`
- `0x180001338`
- `0x180001518`
- `0x180001700`
- `0x18000d900`
- `0x18000dfb0`
- `0x18000e0b0`
- `0x18000e1f8`
- `0x18000e308`
- `0x18003b9a0`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18000da83`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000da9a`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000dd14`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000dd31`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000da83`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000da9a`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000dd14`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000dd31`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000dd40`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000dd40`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000dba6`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000dba6`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000dac4`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000dac4`

## string_xrefs

- `0x18000daec`: `reg Key path for the ICCID is not present`
- `0x18000db46`: `failed to open reg Key path for the ICC`
- `0x18000dc29`: `failed to open reg Key value for the ICC`

## pseudocode

```c
__int64 __fastcall WwanController::_IsESIMProvisioningProfile(unsigned __int16 (*Src)[21])
{
  __int64 v1; // r8
  unsigned int v2; // edi
  void **v3; // rax
  void **v4; // r8
  void **v5; // rbx
  __int64 v6; // rcx
  const wchar_t *v7; // rax
  __int64 v8; // rbx
  void **v9; // rdx
  int v10; // ebx
  void **v11; // rax
  const WCHAR *v12; // rdx
  __int64 v13; // rcx
  LSTATUS ValueW; // ebx
  __int64 v15; // r8
  __int64 v16; // r9
  unsigned int v17; // eax
  __int64 v18; // rcx
  __int64 v19; // r8
  __int64 v20; // r9
  unsigned int v21; // eax
  const char *v23; // [rsp+40h] [rbp-89h] BYREF
  const char *v24; // [rsp+48h] [rbp-81h] BYREF
  const char *v25; // [rsp+50h] [rbp-79h] BYREF
  DWORD pcbData; // [rsp+58h] [rbp-71h] BYREF
  int pvData; // [rsp+5Ch] [rbp-6Dh] BYREF
  HKEY hkey; // [rsp+60h] [rbp-69h] BYREF
  LPCWSTR lpSubKey[2]; // [rsp+68h] [rbp-61h] BYREF
  __int64 v30; // [rsp+78h] [rbp-51h]
  unsigned __int64 v31; // [rsp+80h] [rbp-49h]
  void *v32[2]; // [rsp+88h] [rbp-41h] BYREF
  __int64 v33; // [rsp+98h] [rbp-31h]
  unsigned __int64 v34; // [rsp+A0h] [rbp-29h]
  void *v35[3]; // [rsp+A8h] [rbp-21h] BYREF
  unsigned __int64 v36; // [rsp+C0h] [rbp-9h]
  void *v37[3]; // [rsp+C8h] [rbp-1h] BYREF
  unsigned __int64 v38; // [rsp+E0h] [rbp+17h]

  LODWORD(v23) = 0;
  pvData = 0;
  hkey = 0;
  v34 = 7;
  v33 = 0;
  LOWORD(v32[0]) = 0;
  if ( (*Src)[0] )
  {
    v1 = -1;
    do
      ++v1;
    while ( (*Src)[v1] );
  }
  std::wstring::assign(v32, Src);
  v2 = 1;
  if ( !v33 )
    goto LABEL_17;
  v3 = v32;
  if ( v34 >= 8 )
    v3 = (void **)v32[0];
  v4 = (void **)((char *)v3 + 2 * v33);
  v5 = v32;
  if ( v34 >= 8 )
    v5 = (void **)v32[0];
  while ( 2 )
  {
    if ( v5 < v4 )
    {
      v6 = 2;
      v7 = L"Ff";
      while ( *v7 != *(_WORD *)v5 )
      {
        ++v7;
        if ( !--v6 )
          goto LABEL_15;
      }
      if ( !v7 )
      {
LABEL_15:
        v5 = (void **)((char *)v5 + 2);
        continue;
      }
      v11 = v32;
      if ( v34 >= 8 )
        v11 = (void **)v32[0];
      v8 = ((char *)v5 - (char *)v11) >> 1;
    }
    else
    {
LABEL_17:
      v8 = -1;
    }
    break;
  }
  v31 = 7;
  v30 = 0;
  LOWORD(lpSubKey[0]) = 0;
  std::wstring::assign(lpSubKey, L"Software\\Microsoft\\Wlpasvc\\Profiles");
  std::wstring::append(lpSubKey, L"\\");
  if ( v8 == -1 )
  {
    v38 = 7;
    v37[2] = 0;
    LOWORD(v37[0]) = 0;
    std::wstring::assign(v37);
    v9 = v37;
    v10 = 1;
  }
  else
  {
    v36 = 7;
    v35[2] = 0;
    LOWORD(v35[0]) = 0;
    std::wstring::assign(v35);
    v9 = v35;
    v10 = 6;
  }
  LODWORD(v23) = v10;
  std::wstring::append(lpSubKey, v9, 0, -1);
  if ( (v10 & 2) != 0 )
  {
    LOBYTE(v10) = v10 & 0xFD;
    if ( v36 >= 8 )
      operator delete(v35[0]);
  }
  if ( (v10 & 1) != 0 && v38 >= 8 )
    operator delete(v37[0]);
  v12 = (const WCHAR *)lpSubKey;
  if ( v31 >= 8 )
    v12 = lpSubKey[0];
  ValueW = RegOpenKeyExW(HKEY_LOCAL_MACHINE, v12, 0, 1u, &hkey);
  if ( ValueW == 2 )
  {
    if ( (unsigned int)dword_180052170 > 5 )
    {
      v24 = "WwanController::_IsESIMProvisioningProfile";
      v23 = "reg Key path for the ICCID is not present";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>>(
        v13,
        (__int64)word_180048412,
        v15,
        v16,
        (const unsigned __int16 **)&v23,
        (const unsigned __int16 **)&v24);
    }
  }
  else if ( ValueW )
  {
    if ( (unsigned int)dword_180052170 > 2 )
    {
      if ( ValueW > 0 )
        v17 = (unsigned __int16)ValueW | 0x80070000;
      else
        v17 = ValueW;
      LODWORD(v23) = v17;
      v24 = "WwanController::_IsESIMProvisioningProfile";
      v25 = "failed to open reg Key path for the ICC";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
        v13,
        (__int64)byte_180048AD3,
        v15,
        v16,
        (const unsigned __int16 **)&v25,
        (const unsigned __int16 **)&v24,
        (__int64)&v23);
    }
  }
  else
  {
    pcbData = 4;
    ValueW = RegGetValueW(hkey, 0, L"Class", 0x18u, 0, &pvData, &pcbData);
    if ( ValueW == 2 )
    {
      if ( (unsigned int)dword_180052170 > 5 )
      {
        v25 = "WwanController::_IsESIMProvisioningProfile";
        v24 = "reg Key value for the ICCID is not present";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>>(
          v18,
          (__int64)&dword_180048654,
          v19,
          v20,
          (const unsigned __int16 **)&v24,
          (const unsigned __int16 **)&v25);
      }
    }
    else if ( ValueW )
    {
      if ( (unsigned int)dword_180052170 > 2 )
      {
        if ( ValueW > 0 )
          v21 = (unsigned __int16)ValueW | 0x80070000;
        else
          v21 = ValueW;
        LODWORD(v23) = v21;
        v25 = "WwanController::_IsESIMProvisioningProfile";
        v24 = "failed to open reg Key value for the ICC";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
          v18,
          (__int64)&unk_1800483B0,
          v19,
          v20,
          (const unsigned __int16 **)&v24,
          (const unsigned __int16 **)&v25,
          (__int64)&v23);
      }
    }
    else if ( pcbData == 4 )
    {
      if ( (unsigned int)dword_180052170 > 5 )
      {
        v25 = "WwanController::_IsESIMProvisioningProfile";
        LODWORD(v24) = pvData;
        v23 = "eSIM profile Class is";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
          v18,
          (__int64)byte_180048263,
          v19,
          v20,
          (const unsigned __int16 **)&v23,
          (__int64)&v24,
          (const unsigned __int16 **)&v25);
      }
    }
    else
    {
      ValueW = 11;
      if ( (unsigned int)dword_180052170 > 2 )
      {
        LODWORD(v23) = -2147024885;
        v25 = "WwanController::_IsESIMProvisioningProfile";
        LODWORD(v24) = pcbData;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
          v18,
          (__int64)byte_180048561,
          v19,
          v20,
          (__int64)&v24,
          (const unsigned __int16 **)&v25,
          (__int64)&v23);
      }
    }
  }
  if ( v31 >= 8 )
    operator delete((void *)lpSubKey[0]);
  v31 = 7;
  v30 = 0;
  LOWORD(lpSubKey[0]) = 0;
  if ( v34 >= 8 )
    operator delete(v32[0]);
  if ( hkey )
    RegCloseKey(hkey);
  if ( ValueW || pvData != 1 )
    return 0;
  return v2;
}

```

## disassembly

```asm
0x18000d900  push    rbp
0x18000d902  push    rbx
0x18000d903  push    rsi
0x18000d904  push    rdi
0x18000d905  push    r12
0x18000d907  push    r13
0x18000d909  lea     rbp, [rsp-2Fh]
0x18000d90e  sub     rsp, 0F8h
0x18000d915  mov     rax, cs:__security_cookie
0x18000d91c  xor     rax, rsp
0x18000d91f  mov     [rbp+57h+var_38], rax
0x18000d923  xor     esi, esi
0x18000d925  mov     dword ptr [rsp+120h+var_E0], esi
0x18000d929  mov     [rbp+57h+var_C4], esi
0x18000d92c  mov     [rbp+57h+hkey], rsi
0x18000d930  lea     r13d, [rsi+7]
0x18000d934  mov     [rbp+57h+var_80], r13
0x18000d938  mov     [rbp+57h+var_88], rsi
0x18000d93c  mov     word ptr [rbp+57h+var_98], si
0x18000d940  or      r12, 0FFFFFFFFFFFFFFFFh
0x18000d944  cmp     [rcx], si
0x18000d947  jnz     short loc_18000D94E
0x18000d949  mov     r8d, esi
0x18000d94c  jmp     short loc_18000D95B
0x18000d94e  mov     r8, r12
0x18000d951  inc     r8
0x18000d954  cmp     [rcx+r8*2], si
0x18000d959  jnz     short loc_18000D951
0x18000d95b  mov     rdx, rcx; Src
0x18000d95e  lea     rcx, [rbp+57h+var_98]; void *
0x18000d962  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::assign(ushort const *,unsigned __int64)
0x18000d967  nop
0x18000d968  mov     edi, 1
0x18000d96d  mov     rcx, [rbp+57h+var_88]
0x18000d971  test    rcx, rcx
0x18000d974  jz      short loc_18000D9C5
0x18000d976  lea     rax, [rbp+57h+var_98]
0x18000d97a  mov     r9, [rbp+57h+var_98]
0x18000d97e  mov     r10, [rbp+57h+var_80]
0x18000d982  cmp     r10, 8
0x18000d986  cmovnb  rax, r9
0x18000d98a  lea     r8, [rax+rcx*2]
0x18000d98e  lea     rbx, [rbp+57h+var_98]
0x18000d992  cmovnb  rbx, r9
0x18000d996  jmp     short loc_18000D9C0
0x18000d998  mov     ecx, 2
0x18000d99d  lea     rax, aFf; "Ff"
0x18000d9a4  movzx   edx, word ptr [rbx]
0x18000d9a7  cmp     [rax], dx
0x18000d9aa  jz      short loc_18000D9B7
0x18000d9ac  add     rax, 2
0x18000d9b0  sub     rcx, rdi
0x18000d9b3  jnz     short loc_18000D9A7
0x18000d9b5  jmp     short loc_18000D9BC
0x18000d9b7  test    rax, rax
0x18000d9ba  jnz     short loc_18000DA27
0x18000d9bc  add     rbx, 2
0x18000d9c0  cmp     rbx, r8
0x18000d9c3  jb      short loc_18000D998
0x18000d9c5  mov     rbx, r12
0x18000d9c8  mov     [rbp+57h+var_A0], r13
0x18000d9cc  mov     [rbp+57h+var_A8], rsi
0x18000d9d0  mov     word ptr [rbp+57h+lpSubKey], si
0x18000d9d4  mov     r8d, 23h ; '#'
0x18000d9da  lea     rdx, aSoftwareMicros_2; "Software\\Microsoft\\Wlpasvc\\Profiles"
0x18000d9e1  lea     rcx, [rbp+57h+lpSubKey]; void *
0x18000d9e5  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::assign(ushort const *,unsigned __int64)
0x18000d9ea  nop
0x18000d9eb  lea     rdx, asc_180043768; "\\"
0x18000d9f2  lea     rcx, [rbp+57h+lpSubKey]; Src
0x18000d9f6  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z; std::wstring::append(ushort const *)
0x18000d9fb  xor     r8d, r8d
0x18000d9fe  lea     rdx, [rbp+57h+var_98]
0x18000da02  cmp     rbx, r12
0x18000da05  jnz     short loc_18000DA3B
0x18000da07  mov     [rbp+57h+var_40], r13
0x18000da0b  mov     [rbp+57h+var_48], rsi
0x18000da0f  mov     word ptr [rbp+57h+var_58], si
0x18000da13  mov     r9, r12
0x18000da16  lea     rcx, [rbp+57h+var_58]; void *
0x18000da1a  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::wstring::assign(std::wstring const &,unsigned __int64,unsigned __int64)
0x18000da1f  lea     rdx, [rbp+57h+var_58]
0x18000da23  mov     ebx, edi
0x18000da25  jmp     short loc_18000DA5C
0x18000da27  lea     rax, [rbp+57h+var_98]
0x18000da2b  cmp     r10, 8
0x18000da2f  cmovnb  rax, r9
0x18000da33  sub     rbx, rax
0x18000da36  sar     rbx, 1
0x18000da39  jmp     short loc_18000D9C8
0x18000da3b  mov     [rbp+57h+var_60], r13
0x18000da3f  mov     [rbp+57h+var_68], rsi
0x18000da43  mov     word ptr [rbp+57h+var_78], si
0x18000da47  mov     r9, rbx
0x18000da4a  lea     rcx, [rbp+57h+var_78]; void *
0x18000da4e  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::wstring::assign(std::wstring const &,unsigned __int64,unsigned __int64)
0x18000da53  lea     rdx, [rbp+57h+var_78]
0x18000da57  mov     ebx, 6
0x18000da5c  mov     dword ptr [rsp+120h+var_E0], ebx
0x18000da60  mov     r9, r12
0x18000da63  xor     r8d, r8d
0x18000da66  lea     rcx, [rbp+57h+lpSubKey]
0x18000da6a  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::wstring::append(std::wstring const &,unsigned __int64,unsigned __int64)
0x18000da6f  nop
0x18000da70  test    bl, 2
0x18000da73  jz      short loc_18000DA8A
0x18000da75  and     ebx, 0FFFFFFFDh
0x18000da78  cmp     [rbp+57h+var_60], 8
0x18000da7d  jb      short loc_18000DA8A
0x18000da7f  mov     rcx, [rbp+57h+var_78]
0x18000da83  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000da89  nop
0x18000da8a  test    dil, bl
0x18000da8d  jz      short loc_18000DAA0
0x18000da8f  cmp     [rbp+57h+var_40], 8
0x18000da94  jb      short loc_18000DAA0
0x18000da96  mov     rcx, [rbp+57h+var_58]
0x18000da9a  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000daa0  lea     rdx, [rbp+57h+lpSubKey]
0x18000daa4  cmp     [rbp+57h+var_A0], 8
0x18000daa9  cmovnb  rdx, [rbp+57h+lpSubKey]; lpSubKey
0x18000daae  lea     rax, [rbp+57h+hkey]
0x18000dab2  mov     [rsp+120h+phkResult], rax; phkResult
0x18000dab7  mov     r9d, edi; samDesired
0x18000daba  xor     r8d, r8d; ulOptions
0x18000dabd  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000dac4  call    cs:__imp_RegOpenKeyExW
0x18000daca  mov     ebx, eax
0x18000dacc  cmp     eax, 2
0x18000dacf  jnz     short loc_18000DB13
0x18000dad1  mov     eax, cs:dword_180052170
0x18000dad7  cmp     eax, 5
0x18000dada  jbe     loc_18000DD09
0x18000dae0  lea     rax, aWwancontroller_10; "WwanController::_IsESIMProvisioningProf"...
0x18000dae7  mov     [rsp+120h+var_D8], rax
0x18000daec  lea     rax, aRegKeyPathForT; "reg Key path for the ICCID is not prese"...
0x18000daf3  mov     [rsp+120h+var_E0], rax
0x18000daf8  lea     rax, [rsp+120h+var_D8]
0x18000dafd  mov     [rsp+120h+pvData], rax
0x18000db02  lea     rax, [rsp+120h+var_E0]
0x18000db07  lea     rdx, word_180048412
0x18000db0e  jmp     loc_18000DBEE
0x18000db13  test    ebx, ebx
0x18000db15  jz      short loc_18000DB75
0x18000db17  mov     eax, cs:dword_180052170
0x18000db1d  cmp     eax, 2
0x18000db20  jbe     loc_18000DD09
0x18000db26  test    ebx, ebx
0x18000db28  jg      short loc_18000DB2E
0x18000db2a  mov     eax, ebx
0x18000db2c  jmp     short loc_18000DB36
0x18000db2e  movzx   eax, bx
0x18000db31  or      eax, 80070000h
0x18000db36  mov     dword ptr [rsp+120h+var_E0], eax
0x18000db3a  lea     rax, aWwancontroller_10; "WwanController::_IsESIMProvisioningProf"...
0x18000db41  mov     [rsp+120h+var_D8], rax
0x18000db46  lea     rax, aFailedToOpenRe; "failed to open reg Key path for the ICC"
0x18000db4d  mov     [rbp+57h+var_D0], rax
0x18000db51  lea     rax, [rsp+120h+var_E0]
0x18000db56  mov     [rsp+120h+pcbData], rax
0x18000db5b  lea     rax, [rsp+120h+var_D8]
0x18000db60  mov     [rsp+120h+pvData], rax
0x18000db65  lea     rax, [rbp+57h+var_D0]
0x18000db69  lea     rdx, byte_180048AD3
0x18000db70  jmp     loc_18000DC54
0x18000db75  mov     [rbp+57h+var_C8], 4
0x18000db7c  lea     rax, [rbp+57h+var_C8]
0x18000db80  mov     [rsp+120h+pcbData], rax; pcbData
0x18000db85  lea     rax, [rbp+57h+var_C4]
0x18000db89  mov     [rsp+120h+pvData], rax; pvData
0x18000db8e  mov     [rsp+120h+phkResult], rsi; pdwType
0x18000db93  mov     r9d, 18h; dwFlags
0x18000db99  lea     r8, Value; "Class"
0x18000dba0  xor     edx, edx; lpSubKey
0x18000dba2  mov     rcx, [rbp+57h+hkey]; hkey
0x18000dba6  call    cs:__imp_RegGetValueW
0x18000dbac  mov     ebx, eax
0x18000dbae  cmp     eax, 2
0x18000dbb1  mov     eax, cs:dword_180052170
0x18000dbb7  jnz     short loc_18000DBFD
0x18000dbb9  cmp     eax, 5
0x18000dbbc  jbe     loc_18000DD09
0x18000dbc2  lea     rax, aWwancontroller_10; "WwanController::_IsESIMProvisioningProf"...
0x18000dbc9  mov     [rbp+57h+var_D0], rax
0x18000dbcd  lea     rax, aRegKeyValueFor; "reg Key value for the ICCID is not pres"...
0x18000dbd4  mov     [rsp+120h+var_D8], rax
0x18000dbd9  lea     rax, [rbp+57h+var_D0]
0x18000dbdd  mov     [rsp+120h+pvData], rax
0x18000dbe2  lea     rax, [rsp+120h+var_D8]
0x18000dbe7  lea     rdx, dword_180048654
0x18000dbee  mov     [rsp+120h+phkResult], rax
0x18000dbf3  call    ??$Write@U?$_tlgWrapSz@D@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x18000dbf8  jmp     loc_18000DD09
0x18000dbfd  test    ebx, ebx
0x18000dbff  jz      short loc_18000DC63
0x18000dc01  cmp     eax, 2
0x18000dc04  jbe     loc_18000DD09
0x18000dc0a  test    ebx, ebx
0x18000dc0c  jg      short loc_18000DC12
0x18000dc0e  mov     eax, ebx
0x18000dc10  jmp     short loc_18000DC1A
0x18000dc12  movzx   eax, bx
0x18000dc15  or      eax, 80070000h
0x18000dc1a  mov     dword ptr [rsp+120h+var_E0], eax
0x18000dc1e  lea     rax, aWwancontroller_10; "WwanController::_IsESIMProvisioningProf"...
0x18000dc25  mov     [rbp+57h+var_D0], rax
0x18000dc29  lea     rax, aFailedToOpenRe_0; "failed to open reg Key value for the IC"...
0x18000dc30  mov     [rsp+120h+var_D8], rax
0x18000dc35  lea     rax, [rsp+120h+var_E0]
0x18000dc3a  mov     [rsp+120h+pcbData], rax
0x18000dc3f  lea     rax, [rbp+57h+var_D0]
0x18000dc43  mov     [rsp+120h+pvData], rax
0x18000dc48  lea     rax, [rsp+120h+var_D8]
0x18000dc4d  lea     rdx, unk_1800483B0
0x18000dc54  mov     [rsp+120h+phkResult], rax
0x18000dc59  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18000dc5e  jmp     loc_18000DD09
0x18000dc63  cmp     [rbp+57h+var_C8], 4
0x18000dc67  jz      short loc_18000DCBC
0x18000dc69  mov     ebx, 0Bh
0x18000dc6e  cmp     eax, 2
0x18000dc71  jbe     loc_18000DD09
0x18000dc77  mov     dword ptr [rsp+120h+var_E0], 8007000Bh
0x18000dc7f  lea     rax, aWwancontroller_10; "WwanController::_IsESIMProvisioningProf"...
0x18000dc86  mov     [rbp+57h+var_D0], rax
0x18000dc8a  mov     eax, [rbp+57h+var_C8]
0x18000dc8d  mov     dword ptr [rsp+120h+var_D8], eax
0x18000dc91  lea     rax, [rsp+120h+var_E0]
0x18000dc96  mov     [rsp+120h+pcbData], rax
0x18000dc9b  lea     rax, [rbp+57h+var_D0]
0x18000dc9f  mov     [rsp+120h+pvData], rax
0x18000dca4  lea     rax, [rsp+120h+var_D8]
0x18000dca9  mov     [rsp+120h+phkResult], rax
0x18000dcae  lea     rdx, byte_180048561
0x18000dcb5  call    ??$Write@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18000dcba  jmp     short loc_18000DD09
0x18000dcbc  cmp     eax, 5
0x18000dcbf  jbe     short loc_18000DD09
0x18000dcc1  lea     rax, aWwancontroller_10; "WwanController::_IsESIMProvisioningProf"...
0x18000dcc8  mov     [rbp+57h+var_D0], rax
0x18000dccc  mov     eax, [rbp+57h+var_C4]
0x18000dccf  mov     dword ptr [rsp+120h+var_D8], eax
0x18000dcd3  lea     rax, aEsimProfileCla; "eSIM profile Class is"
0x18000dcda  mov     [rsp+120h+var_E0], rax
0x18000dcdf  lea     rax, [rbp+57h+var_D0]
0x18000dce3  mov     [rsp+120h+pcbData], rax
0x18000dce8  lea     rax, [rsp+120h+var_D8]
0x18000dced  mov     [rsp+120h+pvData], rax
0x18000dcf2  lea     rax, [rsp+120h+var_E0]
0x18000dcf7  mov     [rsp+120h+phkResult], rax
0x18000dcfc  lea     rdx, byte_180048263
0x18000dd03  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x18000dd08  nop
0x18000dd09  cmp     [rbp+57h+var_A0], 8
0x18000dd0e  jb      short loc_18000DD1A
0x18000dd10  mov     rcx, [rbp+57h+lpSubKey]
0x18000dd14  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000dd1a  mov     [rbp+57h+var_A0], r13
0x18000dd1e  mov     [rbp+57h+var_A8], rsi
0x18000dd22  mov     word ptr [rbp+57h+lpSubKey], si
0x18000dd26  cmp     [rbp+57h+var_80], 8
0x18000dd2b  jb      short loc_18000DD37
0x18000dd2d  mov     rcx, [rbp+57h+var_98]
0x18000dd31  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000dd37  mov     rcx, [rbp+57h+hkey]; hKey
0x18000dd3b  test    rcx, rcx
0x18000dd3e  jz      short loc_18000DD46
0x18000dd40  call    cs:__imp_RegCloseKey
0x18000dd46  test    ebx, ebx
0x18000dd48  jnz     short loc_18000DD4F
0x18000dd4a  cmp     [rbp+57h+var_C4], edi
0x18000dd4d  jz      short loc_18000DD51
0x18000dd4f  mov     edi, esi
0x18000dd51  mov     eax, edi
0x18000dd53  mov     rcx, [rbp+57h+var_38]
0x18000dd57  xor     rcx, rsp; StackCookie
0x18000dd5a  call    __security_check_cookie
0x18000dd5f  add     rsp, 0F8h
0x18000dd66  pop     r13
0x18000dd68  pop     r12
0x18000dd6a  pop     rdi
0x18000dd6b  pop     rsi
0x18000dd6c  pop     rbx
0x18000dd6d  pop     rbp
0x18000dd6e  retn
```
