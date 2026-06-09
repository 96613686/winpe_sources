# CTSSession::SetIsolationConfigId(void)

- ea: `0x180071830`
- end: `0x180071bad`
- name: `?SetIsolationConfigId@CTSSession@@AEAAXXZ`
- size: `893`
- prototype: `void __fastcall(CTSSession *__hidden this)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x18006f300`

## callees

- `0x1800027e8`
- `0x1800029a0`
- `0x18001eb00`
- `0x1800288ac`
- `0x180049204`
- `0x180049228`
- `0x18005312c`
- `0x180053174`
- `0x180071830`
- `0x18009c010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180071996`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180071996`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800719d2`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800719d2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180071902`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180071902`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180071944`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180071944`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180071927`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180071927`

## string_xrefs

- `0x180071988`: `SYSTEM\CurrentControlSet\Services\IsoEnvBroker\ConfigIds`
- `0x180071871`: `Isolation config ID already set`
- `0x180071b0f`: `Failed to read Agent User SID`
- `0x180071a0f`: `Read Config ID registry key`
- `0x180071a82`: `Isolation config ID registry key is invalid`
- `0x180071ab2`: `Failed to read Isolation Config ID registry key`
- `0x180071b5c`: `Set Isolation Session Config ID`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CTSSession::SetIsolationConfigId(CTSSession *this, __int64 a2, int a3, int a4)
{
  int v5; // edi
  __int64 v6; // rcx
  bool v7; // si
  LSTATUS Value; // ecx
  int v9; // r8d
  int v10; // r9d
  int v11; // esi
  int *v12; // r14
  int v13; // esi
  const char *v14; // rax
  char *v15; // rdx
  HLOCAL hMem; // [rsp+40h] [rbp-30h] BYREF
  HKEY hKey; // [rsp+48h] [rbp-28h] BYREF
  HLOCAL v18; // [rsp+50h] [rbp-20h] BYREF
  __int64 v19; // [rsp+58h] [rbp-18h] BYREF
  _QWORD v20[2]; // [rsp+60h] [rbp-10h] BYREF
  PSID Sid; // [rsp+A0h] [rbp+30h] BYREF
  const char *cbData; // [rsp+A8h] [rbp+38h] BYREF
  const char *Type; // [rsp+B0h] [rbp+40h] BYREF
  const char *v24; // [rsp+B8h] [rbp+48h] BYREF

  if ( *((_DWORD *)this + 526) )
  {
    if ( (unsigned int)dword_1800DF020 > 2 )
    {
      LODWORD(Sid) = *((_DWORD *)this + 526);
      cbData = (const char *)*((int *)this + 436);
      Type = "Isolation config ID already set";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(
        (_DWORD)this,
        (unsigned int)&unk_1800C8A20,
        a3,
        a4,
        (__int64)&Type,
        (__int64)&cbData,
        (__int64)&Sid);
    }
    return;
  }
  hMem = 0;
  v5 = 2;
  v6 = *((_QWORD *)this + 741);
  if ( !v6 )
    goto LABEL_24;
  Sid = 0;
  (*(void (__fastcall **)(__int64, PSID *))(*(_QWORD *)v6 + 72LL))(v6, &Sid);
  LODWORD(v6) = (_DWORD)Sid;
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
    if ( (unsigned int)dword_1800DF020 > 2 )
    {
      Sid = (PSID)*((int *)this + 436);
      cbData = "Failed to read Agent User SID";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>>(
        v6,
        (unsigned int)byte_1800C89ED,
        a3,
        a4,
        (__int64)&cbData,
        (__int64)&Sid);
    }
    v13 = 0;
    goto LABEL_27;
  }
  LODWORD(Type) = 4;
  LODWORD(cbData) = 4;
  LODWORD(Sid) = 0;
  hKey = 0;
  Value = RegOpenKeyExW(
            HKEY_LOCAL_MACHINE,
            L"SYSTEM\\CurrentControlSet\\Services\\IsoEnvBroker\\ConfigIds",
            0,
            0x20019u,
            &hKey);
  if ( Value
    || (Value = (int)hKey, hKey)
    && (Value = RegQueryValueExW(hKey, (LPCWSTR)hMem, 0, (LPDWORD)&Type, (LPBYTE)&Sid, (LPDWORD)&cbData)) != 0 )
  {
    if ( (unsigned int)dword_1800DF020 > 2 )
    {
      LODWORD(v24) = Value;
      v20[0] = hMem;
      v19 = *((int *)this + 436);
      v14 = "Failed to read Isolation Config ID registry key";
      v15 = byte_1800C8911;
      goto LABEL_21;
    }
LABEL_22:
    v13 = 0;
    goto LABEL_23;
  }
  v11 = (int)Sid;
  if ( (unsigned int)dword_1800DF020 <= 4 )
  {
    v12 = (int *)((char *)this + 1744);
  }
  else
  {
    LODWORD(v24) = (_DWORD)Sid;
    v18 = hMem;
    v12 = (int *)((char *)this + 1744);
    v19 = *((int *)this + 436);
    v20[0] = "Read Config ID registry key";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
      Value,
      (unsigned int)&unk_1800C89A8,
      v9,
      v10,
      (__int64)v20,
      (__int64)&v19,
      (__int64)&v18,
      (__int64)&v24);
  }
  if ( (unsigned int)Sid > 3 )
  {
    if ( (unsigned int)dword_1800DF020 > 3 )
    {
      LODWORD(v24) = v11;
      v20[0] = hMem;
      v19 = *v12;
      v14 = "Isolation config ID registry key is invalid";
      v15 = byte_1800C8963;
LABEL_21:
      v18 = (HLOCAL)v14;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
        Value,
        (_DWORD)v15,
        v9,
        v10,
        (__int64)&v18,
        (__int64)&v19,
        (__int64)v20,
        (__int64)&v24);
      goto LABEL_22;
    }
    goto LABEL_22;
  }
  v5 = v11;
  v13 = 1;
LABEL_23:
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
LABEL_27:
  *((_DWORD *)this + 526) = v5;
  if ( (unsigned int)dword_1800DF020 > 4 )
  {
    LODWORD(Sid) = v13;
    LODWORD(cbData) = v5;
    Type = (const char *)*((int *)this + 436);
    v24 = "Set Isolation Session Config ID";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      v6,
      (unsigned int)word_1800C88C2,
      a3,
      a4,
      (__int64)&v24,
      (__int64)&Type,
      (__int64)&cbData,
      (__int64)&Sid);
  }
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&hMem);
}

```

## disassembly

```asm
0x180071830  push    rbp
0x180071832  push    rbx
0x180071833  push    rsi
0x180071834  push    rdi
0x180071835  push    r14
0x180071837  mov     rbp, rsp
0x18007183a  sub     rsp, 70h
0x18007183e  mov     rbx, rcx
0x180071841  cmp     dword ptr [rcx+838h], 0
0x180071848  jz      short loc_1800718A8
0x18007184a  mov     eax, cs:dword_1800DF020
0x180071850  mov     edi, 2
0x180071855  cmp     eax, edi
0x180071857  jbe     loc_180071BA1
0x18007185d  mov     eax, [rcx+838h]
0x180071863  mov     dword ptr [rbp+Sid], eax
0x180071866  movsxd  rax, dword ptr [rcx+6D0h]
0x18007186d  mov     [rbp+cbData], rax
0x180071871  lea     rax, aIsolationConfi_0; "Isolation config ID already set"
0x180071878  mov     [rbp+Type], rax
0x18007187c  lea     rax, [rbp+Sid]
0x180071880  mov     [rsp+70h+var_40], rax
0x180071885  lea     rax, [rbp+cbData]
0x180071889  mov     [rsp+70h+lpcbData], rax
0x18007188e  lea     rax, [rbp+Type]
0x180071892  mov     [rsp+70h+phkResult], rax
0x180071897  lea     rdx, unk_1800C8A20
0x18007189e  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &)
0x1800718a3  jmp     loc_180071BA1
0x1800718a8  mov     [rbp+hMem], 0
0x1800718b0  mov     edi, 2
0x1800718b5  mov     rcx, [rcx+1728h]
0x1800718bc  test    rcx, rcx
0x1800718bf  jz      loc_180071AFA
0x1800718c5  mov     [rbp+Sid], 0
0x1800718cd  mov     rax, [rcx]
0x1800718d0  lea     rdx, [rbp+Sid]
0x1800718d4  mov     rax, [rax+48h]
0x1800718d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800718dd  mov     rcx, [rbp+Sid]
0x1800718e1  test    rcx, rcx
0x1800718e4  jz      loc_180071AFA
0x1800718ea  xor     sil, sil
0x1800718ed  mov     r14, [rbp+hMem]
0x1800718f1  test    r14, r14
0x1800718f4  jz      short loc_18007191B
0x1800718f6  lea     rcx, [rbp+cbData]; this
0x1800718fa  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x1800718ff  mov     rcx, r14; hMem
0x180071902  call    cs:__imp_LocalFree
0x180071909  nop     dword ptr [rax+rax+00h]
0x18007190e  lea     rcx, [rbp+cbData]; this
0x180071912  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180071917  mov     rcx, [rbp+Sid]; Sid
0x18007191b  mov     [rbp+hMem], 0
0x180071923  lea     rdx, [rbp+hMem]; StringSid
0x180071927  call    cs:__imp_ConvertSidToStringSidW
0x18007192e  nop     dword ptr [rax+rax+00h]
0x180071933  test    eax, eax
0x180071935  jz      short loc_180071940
0x180071937  cmp     [rbp+hMem], 0
0x18007193c  setnz   sil
0x180071940  mov     rcx, [rbp+Sid]; pv
0x180071944  call    cs:__imp_CoTaskMemFree
0x18007194b  nop     dword ptr [rax+rax+00h]
0x180071950  test    sil, sil
0x180071953  jz      loc_180071AFA
0x180071959  mov     dword ptr [rbp+Type], 4
0x180071960  mov     dword ptr [rbp+cbData], 4
0x180071967  mov     dword ptr [rbp+Sid], 0
0x18007196e  mov     [rbp+hKey], 0
0x180071976  lea     rax, [rbp+hKey]
0x18007197a  mov     [rsp+70h+phkResult], rax; phkResult
0x18007197f  mov     r9d, 20019h; samDesired
0x180071985  xor     r8d, r8d; ulOptions
0x180071988  lea     rdx, aSystemCurrentc_7; "SYSTEM\\CurrentControlSet\\Services\\Is"...
0x18007198f  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180071996  call    cs:__imp_RegOpenKeyExW
0x18007199d  nop     dword ptr [rax+rax+00h]
0x1800719a2  mov     ecx, eax
0x1800719a4  test    eax, eax
0x1800719a6  jnz     loc_180071A92
0x1800719ac  mov     rcx, [rbp+hKey]; hKey
0x1800719b0  test    rcx, rcx
0x1800719b3  jz      short loc_1800719E8
0x1800719b5  lea     rax, [rbp+cbData]
0x1800719b9  mov     [rsp+70h+lpcbData], rax; lpcbData
0x1800719be  lea     rax, [rbp+Sid]
0x1800719c2  mov     [rsp+70h+phkResult], rax; lpData
0x1800719c7  lea     r9, [rbp+Type]; lpType
0x1800719cb  xor     r8d, r8d; lpReserved
0x1800719ce  mov     rdx, [rbp+hMem]; lpValueName
0x1800719d2  call    cs:__imp_RegQueryValueExW
0x1800719d9  nop     dword ptr [rax+rax+00h]
0x1800719de  mov     ecx, eax
0x1800719e0  test    eax, eax
0x1800719e2  jnz     loc_180071A92
0x1800719e8  mov     esi, dword ptr [rbp+Sid]
0x1800719eb  mov     eax, cs:dword_1800DF020
0x1800719f1  cmp     eax, 4
0x1800719f4  jbe     short loc_180071A4C
0x1800719f6  mov     dword ptr [rbp+arg_18], esi
0x1800719f9  mov     rax, [rbp+hMem]
0x1800719fd  mov     [rbp+var_20], rax
0x180071a01  lea     r14, [rbx+6D0h]
0x180071a08  movsxd  rax, dword ptr [r14]
0x180071a0b  mov     [rbp+var_18], rax
0x180071a0f  lea     rax, aReadConfigIdRe; "Read Config ID registry key"
0x180071a16  mov     [rbp+var_10], rax
0x180071a1a  lea     rax, [rbp+arg_18]
0x180071a1e  mov     [rsp+70h+var_38], rax
0x180071a23  lea     rax, [rbp+var_20]
0x180071a27  mov     [rsp+70h+var_40], rax
0x180071a2c  lea     rax, [rbp+var_18]
0x180071a30  mov     [rsp+70h+lpcbData], rax
0x180071a35  lea     rax, [rbp+var_10]
0x180071a39  mov     [rsp+70h+phkResult], rax
0x180071a3e  lea     rdx, unk_1800C89A8
0x180071a45  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x180071a4a  jmp     short loc_180071A53
0x180071a4c  lea     r14, [rbx+6D0h]
0x180071a53  cmp     dword ptr [rbp+Sid], 3
0x180071a57  ja      short loc_180071A65
0x180071a59  mov     edi, esi
0x180071a5b  mov     esi, 1
0x180071a60  jmp     loc_180071AEF
0x180071a65  mov     eax, cs:dword_1800DF020
0x180071a6b  cmp     eax, 3
0x180071a6e  jbe     short loc_180071AED
0x180071a70  mov     dword ptr [rbp+arg_18], esi
0x180071a73  mov     rax, [rbp+hMem]
0x180071a77  mov     [rbp+var_10], rax
0x180071a7b  movsxd  rax, dword ptr [r14]
0x180071a7e  mov     [rbp+var_18], rax
0x180071a82  lea     rax, aIsolationConfi; "Isolation config ID registry key is inv"...
0x180071a89  lea     rdx, byte_1800C8963
0x180071a90  jmp     short loc_180071AC0
0x180071a92  mov     eax, cs:dword_1800DF020
0x180071a98  cmp     eax, edi
0x180071a9a  jbe     short loc_180071AED
0x180071a9c  mov     dword ptr [rbp+arg_18], ecx
0x180071a9f  mov     rax, [rbp+hMem]
0x180071aa3  mov     [rbp+var_10], rax
0x180071aa7  movsxd  rax, dword ptr [rbx+6D0h]
0x180071aae  mov     [rbp+var_18], rax
0x180071ab2  lea     rax, aFailedToReadIs; "Failed to read Isolation Config ID regi"...
0x180071ab9  lea     rdx, byte_1800C8911
0x180071ac0  mov     [rbp+var_20], rax
0x180071ac4  lea     rax, [rbp+arg_18]
0x180071ac8  mov     [rsp+70h+var_38], rax
0x180071acd  lea     rax, [rbp+var_10]
0x180071ad1  mov     [rsp+70h+var_40], rax
0x180071ad6  lea     rax, [rbp+var_18]
0x180071ada  mov     [rsp+70h+lpcbData], rax
0x180071adf  lea     rax, [rbp+var_20]
0x180071ae3  mov     [rsp+70h+phkResult], rax
0x180071ae8  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x180071aed  xor     esi, esi
0x180071aef  lea     rcx, [rbp+hKey]
0x180071af3  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180071af8  jmp     short loc_180071B3A
0x180071afa  mov     eax, cs:dword_1800DF020
0x180071b00  cmp     eax, edi
0x180071b02  jbe     short loc_180071B38
0x180071b04  movsxd  rax, dword ptr [rbx+6D0h]
0x180071b0b  mov     [rbp+Sid], rax
0x180071b0f  lea     rax, aFailedToReadAg; "Failed to read Agent User SID"
0x180071b16  mov     [rbp+cbData], rax
0x180071b1a  lea     rax, [rbp+Sid]
0x180071b1e  mov     [rsp+70h+lpcbData], rax
0x180071b23  lea     rax, [rbp+cbData]
0x180071b27  mov     [rsp+70h+phkResult], rax
0x180071b2c  lea     rdx, byte_1800C89ED
0x180071b33  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &)
0x180071b38  xor     esi, esi
0x180071b3a  mov     [rbx+838h], edi
0x180071b40  mov     eax, cs:dword_1800DF020
0x180071b46  cmp     eax, 4
0x180071b49  jbe     short loc_180071B98
0x180071b4b  mov     dword ptr [rbp+Sid], esi
0x180071b4e  mov     dword ptr [rbp+cbData], edi
0x180071b51  movsxd  rax, dword ptr [rbx+6D0h]
0x180071b58  mov     [rbp+Type], rax
0x180071b5c  lea     rax, aSetIsolationSe; "Set Isolation Session Config ID"
0x180071b63  mov     [rbp+arg_18], rax
0x180071b67  lea     rax, [rbp+Sid]
0x180071b6b  mov     [rsp+70h+var_38], rax
0x180071b70  lea     rax, [rbp+cbData]
0x180071b74  mov     [rsp+70h+var_40], rax
0x180071b79  lea     rax, [rbp+Type]
0x180071b7d  mov     [rsp+70h+lpcbData], rax
0x180071b82  lea     rax, [rbp+arg_18]
0x180071b86  mov     [rsp+70h+phkResult], rax
0x180071b8b  lea     rdx, word_1800C88C2
0x180071b92  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@5@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180071b97  nop
0x180071b98  lea     rcx, [rbp+hMem]
0x180071b9c  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180071ba1  add     rsp, 70h
0x180071ba5  pop     r14
0x180071ba7  pop     rdi
0x180071ba8  pop     rsi
0x180071ba9  pop     rbx
0x180071baa  pop     rbp
0x180071bab  retn
```
