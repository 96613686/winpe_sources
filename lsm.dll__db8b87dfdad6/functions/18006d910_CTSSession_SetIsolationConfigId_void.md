# CTSSession::SetIsolationConfigId(void)

- ea: `0x18006d910`
- end: `0x18006dc6e`
- name: `?SetIsolationConfigId@CTSSession@@AEAAXXZ`
- size: `862`
- prototype: `void __fastcall(CTSSession *__hidden this)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x18006b480`

## callees

- `0x1800027d4`
- `0x180002988`
- `0x18001eab0`
- `0x1800267c4`
- `0x180046298`
- `0x1800462b8`
- `0x18004fb80`
- `0x18004fbc0`
- `0x18006d910`
- `0x180097010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18006da64`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18006da64`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18006da9a`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18006da9a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006d9e2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006d9e2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006da18`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006da18`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18006da01`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18006da01`

## string_xrefs

- `0x18006da56`: `SYSTEM\CurrentControlSet\Services\IsoEnvBroker\ConfigIds`
- `0x18006d951`: `Isolation config ID already set`
- `0x18006dbd1`: `Failed to read Agent User SID`
- `0x18006dad1`: `Read Config ID registry key`
- `0x18006db44`: `Isolation config ID registry key is invalid`
- `0x18006db74`: `Failed to read Isolation Config ID registry key`
- `0x18006dc1e`: `Set Isolation Session Config ID`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CTSSession::SetIsolationConfigId(CTSSession *this, __int64 a2, __int64 a3, __int64 a4)
{
  int v5; // edi
  PSID v6; // rcx
  bool v7; // si
  unsigned int v8; // eax
  __int64 v9; // r8
  __int64 v10; // r9
  __int64 v11; // rcx
  unsigned int Value; // eax
  int v13; // esi
  int *v14; // r14
  int v15; // esi
  const char *v16; // rax
  char *v17; // rdx
  HLOCAL hMem; // [rsp+40h] [rbp-30h] BYREF
  HKEY hKey; // [rsp+48h] [rbp-28h] BYREF
  __int64 *v20; // [rsp+50h] [rbp-20h] BYREF
  __int64 v21; // [rsp+58h] [rbp-18h] BYREF
  __int64 *v22[2]; // [rsp+60h] [rbp-10h] BYREF
  PSID Sid; // [rsp+A0h] [rbp+30h] BYREF
  const char *cbData; // [rsp+A8h] [rbp+38h] BYREF
  const char *Type; // [rsp+B0h] [rbp+40h] BYREF
  const char *v26; // [rsp+B8h] [rbp+48h] BYREF

  if ( *((_DWORD *)this + 526) )
  {
    if ( (unsigned int)dword_1800DA020 > 2 )
    {
      LODWORD(Sid) = *((_DWORD *)this + 526);
      cbData = (const char *)*((int *)this + 436);
      Type = "Isolation config ID already set";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(
        (__int64)this,
        (unsigned __int8 *)&unk_1800C3898,
        a3,
        a4,
        (const unsigned __int16 **)&Type,
        (__int64)&cbData,
        (__int64)&Sid);
    }
    return;
  }
  hMem = 0;
  v5 = 2;
  v6 = (PSID)*((_QWORD *)this + 741);
  if ( !v6 )
    goto LABEL_24;
  Sid = 0;
  (*(void (__fastcall **)(PSID, PSID *))(*(_QWORD *)v6 + 72LL))(v6, &Sid);
  v6 = Sid;
  if ( !Sid )
    goto LABEL_24;
  v7 = 0;
  hMem = 0;
  if ( ConvertSidToStringSidW(Sid, (LPWSTR *)&hMem) )
    v7 = hMem != 0;
  CoTaskMemFree(Sid);
  if ( !v7 )
  {
LABEL_24:
    if ( (unsigned int)dword_1800DA020 > 2 )
    {
      Sid = (PSID)*((int *)this + 436);
      cbData = "Failed to read Agent User SID";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>>(
        (__int64)v6,
        (unsigned __int8 *)byte_1800C3865,
        a3,
        a4,
        (const unsigned __int16 **)&cbData,
        (__int64)&Sid);
    }
    v15 = 0;
    goto LABEL_27;
  }
  LODWORD(Type) = 4;
  LODWORD(cbData) = 4;
  LODWORD(Sid) = 0;
  hKey = 0;
  v8 = RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"SYSTEM\\CurrentControlSet\\Services\\IsoEnvBroker\\ConfigIds",
         0,
         0x20019u,
         &hKey);
  v11 = v8;
  if ( v8
    || (v11 = (__int64)hKey) != 0
    && (Value = RegQueryValueExW(hKey, (LPCWSTR)hMem, 0, (LPDWORD)&Type, (LPBYTE)&Sid, (LPDWORD)&cbData),
        (v11 = Value) != 0) )
  {
    if ( (unsigned int)dword_1800DA020 > 2 )
    {
      LODWORD(v26) = v11;
      v22[0] = (__int64 *)hMem;
      v21 = *((int *)this + 436);
      v16 = "Failed to read Isolation Config ID registry key";
      v17 = byte_1800C3789;
      goto LABEL_21;
    }
LABEL_22:
    v15 = 0;
    goto LABEL_23;
  }
  v13 = (int)Sid;
  if ( (unsigned int)dword_1800DA020 <= 4 )
  {
    v14 = (int *)((char *)this + 1744);
  }
  else
  {
    LODWORD(v26) = (_DWORD)Sid;
    v20 = (__int64 *)hMem;
    v14 = (int *)((char *)this + 1744);
    v21 = *((int *)this + 436);
    v22[0] = (__int64 *)"Read Config ID registry key";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
      v11,
      (int)&unk_1800C3820,
      v9,
      v10,
      (const unsigned __int16 **)v22,
      (__int64)&v21,
      &v20,
      (__int64)&v26);
  }
  if ( (unsigned int)Sid > 3 )
  {
    if ( (unsigned int)dword_1800DA020 > 3 )
    {
      LODWORD(v26) = v13;
      v22[0] = (__int64 *)hMem;
      v21 = *v14;
      v16 = "Isolation config ID registry key is invalid";
      v17 = byte_1800C37DB;
LABEL_21:
      v20 = (__int64 *)v16;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
        v11,
        (int)v17,
        v9,
        v10,
        (const unsigned __int16 **)&v20,
        (__int64)&v21,
        v22,
        (__int64)&v26);
      goto LABEL_22;
    }
    goto LABEL_22;
  }
  v5 = v13;
  v15 = 1;
LABEL_23:
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
LABEL_27:
  *((_DWORD *)this + 526) = v5;
  if ( (unsigned int)dword_1800DA020 > 4 )
  {
    LODWORD(Sid) = v15;
    LODWORD(cbData) = v5;
    Type = (const char *)*((int *)this + 436);
    v26 = "Set Isolation Session Config ID";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      (__int64)v6,
      (int)word_1800C373A,
      a3,
      a4,
      (const unsigned __int16 **)&v26,
      (__int64)&Type,
      (__int64)&cbData,
      (__int64)&Sid);
  }
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&hMem);
}

```

## disassembly

```asm
0x18006d910  push    rbp
0x18006d912  push    rbx
0x18006d913  push    rsi
0x18006d914  push    rdi
0x18006d915  push    r14
0x18006d917  mov     rbp, rsp
0x18006d91a  sub     rsp, 70h
0x18006d91e  mov     rbx, rcx
0x18006d921  cmp     dword ptr [rcx+838h], 0
0x18006d928  jz      short loc_18006D988
0x18006d92a  mov     eax, cs:dword_1800DA020
0x18006d930  mov     edi, 2
0x18006d935  cmp     eax, edi
0x18006d937  jbe     loc_18006DC63
0x18006d93d  mov     eax, [rcx+838h]
0x18006d943  mov     dword ptr [rbp+Sid], eax
0x18006d946  movsxd  rax, dword ptr [rcx+6D0h]
0x18006d94d  mov     [rbp+cbData], rax
0x18006d951  lea     rax, aIsolationConfi_0; "Isolation config ID already set"
0x18006d958  mov     [rbp+Type], rax
0x18006d95c  lea     rax, [rbp+Sid]
0x18006d960  mov     [rsp+70h+var_40], rax
0x18006d965  lea     rax, [rbp+cbData]
0x18006d969  mov     [rsp+70h+lpcbData], rax
0x18006d96e  lea     rax, [rbp+Type]
0x18006d972  mov     [rsp+70h+phkResult], rax
0x18006d977  lea     rdx, unk_1800C3898
0x18006d97e  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &)
0x18006d983  jmp     loc_18006DC63
0x18006d988  mov     [rbp+hMem], 0
0x18006d990  mov     edi, 2
0x18006d995  mov     rcx, [rcx+1728h]
0x18006d99c  test    rcx, rcx
0x18006d99f  jz      loc_18006DBBC
0x18006d9a5  mov     [rbp+Sid], 0
0x18006d9ad  mov     rax, [rcx]
0x18006d9b0  lea     rdx, [rbp+Sid]
0x18006d9b4  mov     rax, [rax+48h]
0x18006d9b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006d9bd  mov     rcx, [rbp+Sid]
0x18006d9c1  test    rcx, rcx
0x18006d9c4  jz      loc_18006DBBC
0x18006d9ca  xor     sil, sil
0x18006d9cd  mov     r14, [rbp+hMem]
0x18006d9d1  test    r14, r14
0x18006d9d4  jz      short loc_18006D9F5
0x18006d9d6  lea     rcx, [rbp+cbData]; this
0x18006d9da  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18006d9df  mov     rcx, r14; hMem
0x18006d9e2  call    cs:__imp_LocalFree
0x18006d9e8  lea     rcx, [rbp+cbData]; this
0x18006d9ec  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18006d9f1  mov     rcx, [rbp+Sid]; Sid
0x18006d9f5  mov     [rbp+hMem], 0
0x18006d9fd  lea     rdx, [rbp+hMem]; StringSid
0x18006da01  call    cs:__imp_ConvertSidToStringSidW
0x18006da07  test    eax, eax
0x18006da09  jz      short loc_18006DA14
0x18006da0b  cmp     [rbp+hMem], 0
0x18006da10  setnz   sil
0x18006da14  mov     rcx, [rbp+Sid]; pv
0x18006da18  call    cs:__imp_CoTaskMemFree
0x18006da1e  test    sil, sil
0x18006da21  jz      loc_18006DBBC
0x18006da27  mov     dword ptr [rbp+Type], 4
0x18006da2e  mov     dword ptr [rbp+cbData], 4
0x18006da35  mov     dword ptr [rbp+Sid], 0
0x18006da3c  mov     [rbp+hKey], 0
0x18006da44  lea     rax, [rbp+hKey]
0x18006da48  mov     [rsp+70h+phkResult], rax; phkResult
0x18006da4d  mov     r9d, 20019h; samDesired
0x18006da53  xor     r8d, r8d; ulOptions
0x18006da56  lea     rdx, aSystemCurrentc_7; "SYSTEM\\CurrentControlSet\\Services\\Is"...
0x18006da5d  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18006da64  call    cs:__imp_RegOpenKeyExW
0x18006da6a  mov     ecx, eax
0x18006da6c  test    eax, eax
0x18006da6e  jnz     loc_18006DB54
0x18006da74  mov     rcx, [rbp+hKey]; hKey
0x18006da78  test    rcx, rcx
0x18006da7b  jz      short loc_18006DAAA
0x18006da7d  lea     rax, [rbp+cbData]
0x18006da81  mov     [rsp+70h+lpcbData], rax; lpcbData
0x18006da86  lea     rax, [rbp+Sid]
0x18006da8a  mov     [rsp+70h+phkResult], rax; lpData
0x18006da8f  lea     r9, [rbp+Type]; lpType
0x18006da93  xor     r8d, r8d; lpReserved
0x18006da96  mov     rdx, [rbp+hMem]; lpValueName
0x18006da9a  call    cs:__imp_RegQueryValueExW
0x18006daa0  mov     ecx, eax
0x18006daa2  test    eax, eax
0x18006daa4  jnz     loc_18006DB54
0x18006daaa  mov     esi, dword ptr [rbp+Sid]
0x18006daad  mov     eax, cs:dword_1800DA020
0x18006dab3  cmp     eax, 4
0x18006dab6  jbe     short loc_18006DB0E
0x18006dab8  mov     dword ptr [rbp+arg_18], esi
0x18006dabb  mov     rax, [rbp+hMem]
0x18006dabf  mov     [rbp+var_20], rax
0x18006dac3  lea     r14, [rbx+6D0h]
0x18006daca  movsxd  rax, dword ptr [r14]
0x18006dacd  mov     [rbp+var_18], rax
0x18006dad1  lea     rax, aReadConfigIdRe; "Read Config ID registry key"
0x18006dad8  mov     [rbp+var_10], rax
0x18006dadc  lea     rax, [rbp+arg_18]
0x18006dae0  mov     [rsp+70h+var_38], rax
0x18006dae5  lea     rax, [rbp+var_20]
0x18006dae9  mov     [rsp+70h+var_40], rax
0x18006daee  lea     rax, [rbp+var_18]
0x18006daf2  mov     [rsp+70h+lpcbData], rax
0x18006daf7  lea     rax, [rbp+var_10]
0x18006dafb  mov     [rsp+70h+phkResult], rax
0x18006db00  lea     rdx, unk_1800C3820
0x18006db07  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x18006db0c  jmp     short loc_18006DB15
0x18006db0e  lea     r14, [rbx+6D0h]
0x18006db15  cmp     dword ptr [rbp+Sid], 3
0x18006db19  ja      short loc_18006DB27
0x18006db1b  mov     edi, esi
0x18006db1d  mov     esi, 1
0x18006db22  jmp     loc_18006DBB1
0x18006db27  mov     eax, cs:dword_1800DA020
0x18006db2d  cmp     eax, 3
0x18006db30  jbe     short loc_18006DBAF
0x18006db32  mov     dword ptr [rbp+arg_18], esi
0x18006db35  mov     rax, [rbp+hMem]
0x18006db39  mov     [rbp+var_10], rax
0x18006db3d  movsxd  rax, dword ptr [r14]
0x18006db40  mov     [rbp+var_18], rax
0x18006db44  lea     rax, aIsolationConfi; "Isolation config ID registry key is inv"...
0x18006db4b  lea     rdx, byte_1800C37DB
0x18006db52  jmp     short loc_18006DB82
0x18006db54  mov     eax, cs:dword_1800DA020
0x18006db5a  cmp     eax, edi
0x18006db5c  jbe     short loc_18006DBAF
0x18006db5e  mov     dword ptr [rbp+arg_18], ecx
0x18006db61  mov     rax, [rbp+hMem]
0x18006db65  mov     [rbp+var_10], rax
0x18006db69  movsxd  rax, dword ptr [rbx+6D0h]
0x18006db70  mov     [rbp+var_18], rax
0x18006db74  lea     rax, aFailedToReadIs; "Failed to read Isolation Config ID regi"...
0x18006db7b  lea     rdx, byte_1800C3789
0x18006db82  mov     [rbp+var_20], rax
0x18006db86  lea     rax, [rbp+arg_18]
0x18006db8a  mov     [rsp+70h+var_38], rax
0x18006db8f  lea     rax, [rbp+var_10]
0x18006db93  mov     [rsp+70h+var_40], rax
0x18006db98  lea     rax, [rbp+var_18]
0x18006db9c  mov     [rsp+70h+lpcbData], rax
0x18006dba1  lea     rax, [rbp+var_20]
0x18006dba5  mov     [rsp+70h+phkResult], rax
0x18006dbaa  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x18006dbaf  xor     esi, esi
0x18006dbb1  lea     rcx, [rbp+hKey]
0x18006dbb5  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18006dbba  jmp     short loc_18006DBFC
0x18006dbbc  mov     eax, cs:dword_1800DA020
0x18006dbc2  cmp     eax, edi
0x18006dbc4  jbe     short loc_18006DBFA
0x18006dbc6  movsxd  rax, dword ptr [rbx+6D0h]
0x18006dbcd  mov     [rbp+Sid], rax
0x18006dbd1  lea     rax, aFailedToReadAg; "Failed to read Agent User SID"
0x18006dbd8  mov     [rbp+cbData], rax
0x18006dbdc  lea     rax, [rbp+Sid]
0x18006dbe0  mov     [rsp+70h+lpcbData], rax
0x18006dbe5  lea     rax, [rbp+cbData]
0x18006dbe9  mov     [rsp+70h+phkResult], rax
0x18006dbee  lea     rdx, byte_1800C3865
0x18006dbf5  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &)
0x18006dbfa  xor     esi, esi
0x18006dbfc  mov     [rbx+838h], edi
0x18006dc02  mov     eax, cs:dword_1800DA020
0x18006dc08  cmp     eax, 4
0x18006dc0b  jbe     short loc_18006DC5A
0x18006dc0d  mov     dword ptr [rbp+Sid], esi
0x18006dc10  mov     dword ptr [rbp+cbData], edi
0x18006dc13  movsxd  rax, dword ptr [rbx+6D0h]
0x18006dc1a  mov     [rbp+Type], rax
0x18006dc1e  lea     rax, aSetIsolationSe; "Set Isolation Session Config ID"
0x18006dc25  mov     [rbp+arg_18], rax
0x18006dc29  lea     rax, [rbp+Sid]
0x18006dc2d  mov     [rsp+70h+var_38], rax
0x18006dc32  lea     rax, [rbp+cbData]
0x18006dc36  mov     [rsp+70h+var_40], rax
0x18006dc3b  lea     rax, [rbp+Type]
0x18006dc3f  mov     [rsp+70h+lpcbData], rax
0x18006dc44  lea     rax, [rbp+arg_18]
0x18006dc48  mov     [rsp+70h+phkResult], rax
0x18006dc4d  lea     rdx, word_1800C373A
0x18006dc54  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@5@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18006dc59  nop
0x18006dc5a  lea     rcx, [rbp+hMem]
0x18006dc5e  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18006dc63  add     rsp, 70h
0x18006dc67  pop     r14
0x18006dc69  pop     rdi
0x18006dc6a  pop     rsi
0x18006dc6b  pop     rbx
0x18006dc6c  pop     rbp
0x18006dc6d  retn
```
