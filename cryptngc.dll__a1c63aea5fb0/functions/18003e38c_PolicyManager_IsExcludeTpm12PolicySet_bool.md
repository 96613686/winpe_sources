# PolicyManager::IsExcludeTpm12PolicySet(bool *)

- ea: `0x18003e38c`
- end: `0x18003e67d`
- name: `?IsExcludeTpm12PolicySet@PolicyManager@@YAJPEA_N@Z`
- size: `753`
- prototype: `__int64 __fastcall(PolicyManager *__hidden this, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800213c4`

## callees

- `0x1800046e0`
- `0x180006780`
- `0x180008ab4`
- `0x18000edb0`
- `0x1800158e0`
- `0x180038e9c`
- `0x18003e38c`
- `0x180046ce0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18003e436`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18003e5b8`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18003e436`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18003e5b8`

## string_xrefs

- `0x18003e3e4`: `ExcludeSecurityDevices`
- `0x18003e56f`: `ExcludeSecurityDevices`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall PolicyManager::IsExcludeTpm12PolicySet(PolicyManager *this, bool *a2)
{
  const WCHAR *v3; // rdx
  __int64 v4; // rcx
  int ValueW; // edi
  _DWORD *v6; // rbx
  __int64 v7; // r8
  const WCHAR *v8; // rdx
  LSTATUS v9; // ebx
  int v11; // [rsp+40h] [rbp-39h] BYREF
  int pvData; // [rsp+44h] [rbp-35h] BYREF
  DWORD pcbData; // [rsp+48h] [rbp-31h] BYREF
  _DWORD *v14; // [rsp+50h] [rbp-29h] BYREF
  LPCWSTR Src[4]; // [rsp+58h] [rbp-21h] BYREF
  LPCWSTR lpSubKey[4]; // [rsp+78h] [rbp-1h] BYREF

  *(_BYTE *)this = 0;
  std::wstring::wstring(lpSubKey, L"SOFTWARE\\Policies\\Microsoft\\PassportForWork");
  std::wstring::_Append<unsigned short>(lpSubKey);
  std::wstring::_Append<unsigned short>(lpSubKey);
  pvData = 0;
  pcbData = 4;
  v3 = (const WCHAR *)lpSubKey;
  if ( lpSubKey[3] > (LPCWSTR)7 )
    v3 = lpSubKey[0];
  ValueW = RegGetValueW(HKEY_LOCAL_MACHINE, v3, L"TPM12", 0x10u, 0, &pvData, &pcbData);
  if ( !ValueW )
  {
    *(_BYTE *)this = pvData != 0;
LABEL_21:
    ValueW = 0;
LABEL_30:
    std::wstring::~wstring(lpSubKey);
    return (unsigned int)ValueW;
  }
  if ( ValueW != 2 )
  {
    if ( (unsigned int)dword_18006E000 > 2 )
    {
      v11 = ValueW;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
        (__int64)&dword_18006E000,
        (unsigned __int8 *)byte_18006270B,
        0,
        0,
        (__int64)&v11);
    }
    if ( ValueW > 0 )
      ValueW = (unsigned __int16)ValueW | 0x80070000;
    goto LABEL_30;
  }
  v14 = 0;
  ValueW = DsrGetJoinInfo(v4, &v14);
  if ( ValueW < 0 )
  {
    if ( (unsigned int)dword_18006E000 > 2 )
    {
      v11 = ValueW;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
        (__int64)&dword_18006E000,
        (unsigned __int8 *)byte_1800626D9,
        0,
        0,
        (__int64)&v11);
    }
    goto LABEL_29;
  }
  v6 = v14;
  if ( v14 && *v14 == 1 )
  {
    pcbData = 0;
    std::wstring::wstring(Src, L"SOFTWARE\\Microsoft\\Policies\\PassportForWork");
    std::wstring::_Append<unsigned short>(Src);
    v7 = -1;
    do
      ++v7;
    while ( *(_WORD *)(*((_QWORD *)v6 + 4) + 2 * v7) );
    std::wstring::_Append<unsigned short>(Src);
    std::wstring::_Append<unsigned short>(Src);
    std::wstring::_Append<unsigned short>(Src);
    std::wstring::_Append<unsigned short>(Src);
    v8 = (const WCHAR *)Src;
    if ( Src[3] > (LPCWSTR)7 )
      v8 = Src[0];
    v9 = RegGetValueW(HKEY_LOCAL_MACHINE, v8, L"TPM12", 0x10u, 0, &pvData, &pcbData);
    if ( !v9 )
    {
      *(_BYTE *)this = pvData != 0;
      std::wstring::~wstring(Src);
      wil::details::unique_storage<wil::details::resource_policy<_DSREG_JOIN_INFO *,void (*)(_DSREG_JOIN_INFO *),&void DsrFreeJoinInfo(_DSREG_JOIN_INFO *),wistd::integral_constant<unsigned __int64,0>,_DSREG_JOIN_INFO *,_DSREG_JOIN_INFO *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_DSREG_JOIN_INFO *,void (*)(_DSREG_JOIN_INFO *),&void DsrFreeJoinInfo(_DSREG_JOIN_INFO *),wistd::integral_constant<unsigned __int64,0>,_DSREG_JOIN_INFO *,_DSREG_JOIN_INFO *,0,std::nullptr_t>>(&v14);
      goto LABEL_21;
    }
    if ( v9 != 2 )
    {
      if ( (unsigned int)dword_18006E000 > 2 )
      {
        v11 = v9;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
          (__int64)&dword_18006E000,
          (unsigned __int8 *)byte_18006269F,
          0,
          0,
          (__int64)&v11);
      }
      if ( v9 > 0 )
        ValueW = (unsigned __int16)v9 | 0x80070000;
      else
        ValueW = v9;
    }
    std::wstring::~wstring(Src);
LABEL_29:
    wil::details::unique_storage<wil::details::resource_policy<_DSREG_JOIN_INFO *,void (*)(_DSREG_JOIN_INFO *),&void DsrFreeJoinInfo(_DSREG_JOIN_INFO *),wistd::integral_constant<unsigned __int64,0>,_DSREG_JOIN_INFO *,_DSREG_JOIN_INFO *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_DSREG_JOIN_INFO *,void (*)(_DSREG_JOIN_INFO *),&void DsrFreeJoinInfo(_DSREG_JOIN_INFO *),wistd::integral_constant<unsigned __int64,0>,_DSREG_JOIN_INFO *,_DSREG_JOIN_INFO *,0,std::nullptr_t>>(&v14);
    goto LABEL_30;
  }
  wil::details::unique_storage<wil::details::resource_policy<_DSREG_JOIN_INFO *,void (*)(_DSREG_JOIN_INFO *),&void DsrFreeJoinInfo(_DSREG_JOIN_INFO *),wistd::integral_constant<unsigned __int64,0>,_DSREG_JOIN_INFO *,_DSREG_JOIN_INFO *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_DSREG_JOIN_INFO *,void (*)(_DSREG_JOIN_INFO *),&void DsrFreeJoinInfo(_DSREG_JOIN_INFO *),wistd::integral_constant<unsigned __int64,0>,_DSREG_JOIN_INFO *,_DSREG_JOIN_INFO *,0,std::nullptr_t>>(&v14);
  std::wstring::~wstring(lpSubKey);
  return 0;
}

```

## disassembly

```asm
0x18003e38c  push    rbp
0x18003e38e  push    rbx
0x18003e38f  push    rsi
0x18003e390  push    rdi
0x18003e391  push    r14
0x18003e393  push    r15
0x18003e395  lea     rbp, [rsp-2Fh]
0x18003e39a  sub     rsp, 0A8h
0x18003e3a1  mov     rax, cs:__security_cookie
0x18003e3a8  xor     rax, rsp
0x18003e3ab  mov     [rbp+57h+var_38], rax
0x18003e3af  mov     rsi, rcx
0x18003e3b2  xor     r14d, r14d
0x18003e3b5  mov     [rcx], r14b
0x18003e3b8  lea     rdx, aSoftwarePolici_0; "SOFTWARE\\Policies\\Microsoft\\Passport"...
0x18003e3bf  lea     rcx, [rbp+57h+lpSubKey]
0x18003e3c3  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18003e3c8  nop
0x18003e3c9  lea     r15d, [r14+1]
0x18003e3cd  mov     r8d, r15d
0x18003e3d0  lea     rdx, asc_180050E74; "\\"
0x18003e3d7  lea     rcx, [rbp+57h+lpSubKey]; Src
0x18003e3db  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x18003e3e0  lea     r8d, [r14+16h]
0x18003e3e4  lea     rdx, aExcludesecurit; "ExcludeSecurityDevices"
0x18003e3eb  lea     rcx, [rbp+57h+lpSubKey]; Src
0x18003e3ef  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x18003e3f4  mov     [rbp+57h+var_8C], r14d
0x18003e3f8  mov     [rbp+57h+var_88], 4
0x18003e3ff  lea     rdx, [rbp+57h+lpSubKey]
0x18003e403  cmp     [rbp+57h+var_40], 7
0x18003e408  cmova   rdx, [rbp+57h+lpSubKey]; lpSubKey
0x18003e40d  lea     rax, [rbp+57h+var_88]
0x18003e411  mov     [rsp+0D0h+pcbData], rax; pcbData
0x18003e416  lea     rax, [rbp+57h+var_8C]
0x18003e41a  mov     [rsp+0D0h+pvData], rax; pvData
0x18003e41f  mov     [rsp+0D0h+pdwType], r14; pdwType
0x18003e424  lea     r9d, [r14+10h]; dwFlags
0x18003e428  lea     r8, aTpm12; "TPM12"
0x18003e42f  mov     rcx, 0FFFFFFFF80000002h; hkey
0x18003e436  call    cs:__imp_RegGetValueW
0x18003e43c  mov     edi, eax
0x18003e43e  test    eax, eax
0x18003e440  jnz     short loc_18003E450
0x18003e442  cmp     [rbp+57h+var_8C], r14d
0x18003e446  setnz   al
0x18003e449  mov     [rsi], al
0x18003e44b  jmp     loc_18003E5E0
0x18003e450  cmp     edi, 2
0x18003e453  jz      short loc_18003E49B
0x18003e455  mov     eax, cs:dword_18006E000
0x18003e45b  cmp     eax, 2
0x18003e45e  jbe     short loc_18003E485
0x18003e460  mov     [rbp+57h+var_90], edi
0x18003e463  lea     rax, [rbp+57h+var_90]
0x18003e467  mov     [rsp+0D0h+pdwType], rax
0x18003e46c  xor     r9d, r9d
0x18003e46f  xor     r8d, r8d
0x18003e472  lea     rdx, byte_18006270B
0x18003e479  lea     rcx, dword_18006E000
0x18003e480  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x18003e485  test    edi, edi
0x18003e487  jle     loc_18003E63F
0x18003e48d  movzx   edi, di
0x18003e490  or      edi, 80070000h
0x18003e496  jmp     loc_18003E63F
0x18003e49b  mov     [rbp+57h+var_80], r14
0x18003e49f  lea     rdx, [rbp+57h+var_80]
0x18003e4a3  call    DsrGetJoinInfo
0x18003e4a8  mov     edi, eax
0x18003e4aa  test    eax, eax
0x18003e4ac  jns     short loc_18003E4E7
0x18003e4ae  mov     eax, cs:dword_18006E000
0x18003e4b4  cmp     eax, 2
0x18003e4b7  jbe     loc_18003E635
0x18003e4bd  mov     [rbp+57h+var_90], edi
0x18003e4c0  lea     rax, [rbp+57h+var_90]
0x18003e4c4  mov     [rsp+0D0h+pdwType], rax
0x18003e4c9  xor     r9d, r9d
0x18003e4cc  xor     r8d, r8d
0x18003e4cf  lea     rdx, byte_1800626D9
0x18003e4d6  lea     rcx, dword_18006E000
0x18003e4dd  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x18003e4e2  jmp     loc_18003E635
0x18003e4e7  mov     rbx, [rbp+57h+var_80]
0x18003e4eb  test    rbx, rbx
0x18003e4ee  jz      loc_18003E64C
0x18003e4f4  cmp     [rbx], r15d
0x18003e4f7  jnz     loc_18003E64C
0x18003e4fd  mov     [rbp+57h+var_88], r14d
0x18003e501  lea     rdx, Src; "SOFTWARE\\Microsoft\\Policies\\Passport"...
0x18003e508  lea     rcx, [rbp+57h+Src]
0x18003e50c  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18003e511  nop
0x18003e512  mov     r8, r15
0x18003e515  lea     rdx, asc_180050E74; "\\"
0x18003e51c  lea     rcx, [rbp+57h+Src]; Src
0x18003e520  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x18003e525  mov     rdx, [rbx+20h]
0x18003e529  or      r8, 0FFFFFFFFFFFFFFFFh
0x18003e52d  inc     r8
0x18003e530  cmp     [rdx+r8*2], r14w
0x18003e535  jnz     short loc_18003E52D
0x18003e537  lea     rcx, [rbp+57h+Src]; Src
0x18003e53b  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x18003e540  mov     r8d, 10h
0x18003e546  lea     rdx, aDevicePolicies; "\\Device\\Policies"
0x18003e54d  lea     rcx, [rbp+57h+Src]; Src
0x18003e551  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x18003e556  mov     r8, r15
0x18003e559  lea     rdx, asc_180050E74; "\\"
0x18003e560  lea     rcx, [rbp+57h+Src]; Src
0x18003e564  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x18003e569  mov     r8d, 16h
0x18003e56f  lea     rdx, aExcludesecurit; "ExcludeSecurityDevices"
0x18003e576  lea     rcx, [rbp+57h+Src]; Src
0x18003e57a  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x18003e57f  lea     rdx, [rbp+57h+Src]
0x18003e583  cmp     [rbp+57h+var_60], 7
0x18003e588  cmova   rdx, [rbp+57h+Src]; lpSubKey
0x18003e58d  lea     rax, [rbp+57h+var_88]
0x18003e591  mov     [rsp+0D0h+pcbData], rax; pcbData
0x18003e596  lea     rax, [rbp+57h+var_8C]
0x18003e59a  mov     [rsp+0D0h+pvData], rax; pvData
0x18003e59f  mov     [rsp+0D0h+pdwType], r14; pdwType
0x18003e5a4  mov     r9d, 10h; dwFlags
0x18003e5aa  lea     r8, aTpm12; "TPM12"
0x18003e5b1  mov     rcx, 0FFFFFFFF80000002h; hkey
0x18003e5b8  call    cs:__imp_RegGetValueW
0x18003e5be  mov     ebx, eax
0x18003e5c0  test    eax, eax
0x18003e5c2  jnz     short loc_18003E5E5
0x18003e5c4  cmp     [rbp+57h+var_8C], r14d
0x18003e5c8  setnz   al
0x18003e5cb  mov     [rsi], al
0x18003e5cd  lea     rcx, [rbp+57h+Src]
0x18003e5d1  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18003e5d6  nop
0x18003e5d7  lea     rcx, [rbp+57h+var_80]
0x18003e5db  call    ??1?$unique_storage@U?$resource_policy@PEAU_DSREG_JOIN_INFO@@P6AXPEAU1@@Z$1?DsrFreeJoinInfo@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_DSREG_JOIN_INFO *,void (*)(_DSREG_JOIN_INFO *),&DsrFreeJoinInfo(_DSREG_JOIN_INFO *),wistd::integral_constant<unsigned __int64,0>,_DSREG_JOIN_INFO *,_DSREG_JOIN_INFO *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_DSREG_JOIN_INFO *,void (*)(_DSREG_JOIN_INFO *),&DsrFreeJoinInfo(_DSREG_JOIN_INFO *),wistd::integral_constant<unsigned __int64,0>,_DSREG_JOIN_INFO *,_DSREG_JOIN_INFO *,0,std::nullptr_t>>(void)
0x18003e5e0  mov     edi, r14d
0x18003e5e3  jmp     short loc_18003E63F
0x18003e5e5  cmp     ebx, 2
0x18003e5e8  jz      short loc_18003E62B
0x18003e5ea  mov     eax, cs:dword_18006E000
0x18003e5f0  cmp     eax, 2
0x18003e5f3  jbe     short loc_18003E61A
0x18003e5f5  mov     [rbp+57h+var_90], ebx
0x18003e5f8  lea     rax, [rbp+57h+var_90]
0x18003e5fc  mov     [rsp+0D0h+pdwType], rax
0x18003e601  xor     r9d, r9d
0x18003e604  xor     r8d, r8d
0x18003e607  lea     rdx, byte_18006269F
0x18003e60e  lea     rcx, dword_18006E000
0x18003e615  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x18003e61a  test    ebx, ebx
0x18003e61c  jg      short loc_18003E622
0x18003e61e  mov     edi, ebx
0x18003e620  jmp     short loc_18003E62B
0x18003e622  movzx   edi, bx
0x18003e625  or      edi, 80070000h
0x18003e62b  lea     rcx, [rbp+57h+Src]
0x18003e62f  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18003e634  nop
0x18003e635  lea     rcx, [rbp+57h+var_80]
0x18003e639  call    ??1?$unique_storage@U?$resource_policy@PEAU_DSREG_JOIN_INFO@@P6AXPEAU1@@Z$1?DsrFreeJoinInfo@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_DSREG_JOIN_INFO *,void (*)(_DSREG_JOIN_INFO *),&DsrFreeJoinInfo(_DSREG_JOIN_INFO *),wistd::integral_constant<unsigned __int64,0>,_DSREG_JOIN_INFO *,_DSREG_JOIN_INFO *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_DSREG_JOIN_INFO *,void (*)(_DSREG_JOIN_INFO *),&DsrFreeJoinInfo(_DSREG_JOIN_INFO *),wistd::integral_constant<unsigned __int64,0>,_DSREG_JOIN_INFO *,_DSREG_JOIN_INFO *,0,std::nullptr_t>>(void)
0x18003e63e  nop
0x18003e63f  lea     rcx, [rbp+57h+lpSubKey]
0x18003e643  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18003e648  mov     eax, edi
0x18003e64a  jmp     short loc_18003E661
0x18003e64c  lea     rcx, [rbp+57h+var_80]
0x18003e650  call    ??1?$unique_storage@U?$resource_policy@PEAU_DSREG_JOIN_INFO@@P6AXPEAU1@@Z$1?DsrFreeJoinInfo@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_DSREG_JOIN_INFO *,void (*)(_DSREG_JOIN_INFO *),&DsrFreeJoinInfo(_DSREG_JOIN_INFO *),wistd::integral_constant<unsigned __int64,0>,_DSREG_JOIN_INFO *,_DSREG_JOIN_INFO *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_DSREG_JOIN_INFO *,void (*)(_DSREG_JOIN_INFO *),&DsrFreeJoinInfo(_DSREG_JOIN_INFO *),wistd::integral_constant<unsigned __int64,0>,_DSREG_JOIN_INFO *,_DSREG_JOIN_INFO *,0,std::nullptr_t>>(void)
0x18003e655  nop
0x18003e656  lea     rcx, [rbp+57h+lpSubKey]
0x18003e65a  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18003e65f  xor     eax, eax
0x18003e661  mov     rcx, [rbp+57h+var_38]
0x18003e665  xor     rcx, rsp; StackCookie
0x18003e668  call    __security_check_cookie
0x18003e66d  add     rsp, 0A8h
0x18003e674  pop     r15
0x18003e676  pop     r14
0x18003e678  pop     rdi
0x18003e679  pop     rsi
0x18003e67a  pop     rbx
0x18003e67b  pop     rbp
0x18003e67c  retn
```
