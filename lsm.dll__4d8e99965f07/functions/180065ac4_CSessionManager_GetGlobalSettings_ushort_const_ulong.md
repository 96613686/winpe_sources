# CSessionManager::GetGlobalSettings(ushort * const,ulong *)

- ea: `0x180065ac4`
- end: `0x180065d6e`
- name: `?GetGlobalSettings@CSessionManager@@AEAAJQEAGPEAK@Z`
- size: `682`
- prototype: `int(CSessionManager *__hidden this, unsigned __int16 *const, unsigned int *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x1800637cc`

## callees

- `0x1800077a0`
- `0x180009580`
- `0x18002772c`
- `0x180028bd8`
- `0x18004e850`
- `0x180065ac4`
- `0x1800660d4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180065c01`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180065c01`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180065c56`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180065c56`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180065d2a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180065d2a`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180065c9e`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180065c9e`
- `RPCRT4!UuidToStringW` at `0x180065b7d`
- `RPCRT4!UuidToStringW` at `0x180065b7d`
- `RPCRT4!RpcStringFreeW` at `0x180065d41`
- `RPCRT4!RpcStringFreeW` at `0x180065d41`
- `RPCRT4!UuidCreate` at `0x180065b28`
- `RPCRT4!UuidCreate` at `0x180065b28`

## string_xrefs

- `0x180065b55`: `UuidCreate failed: 0x%x in %s`
- `0x180065c1f`: `RegOpenKeyEx failed: 0x%x in %s`
- `0x180065cba`: `RegSetValueEx failed: 0x%x in %s`
- `0x180065cff`: `CachedSessionMode value was read`

## pseudocode

```c
__int64 __fastcall CSessionManager::GetGlobalSettings(
        CSessionManager *this,
        unsigned __int16 *const a2,
        unsigned int *a3)
{
  RPC_STATUS v6; // eax
  signed int v7; // ebx
  const char *v8; // rdx
  RPC_STATUS v9; // eax
  int v10; // eax
  int v11; // edi
  LSTATUS v12; // eax
  unsigned int v13; // eax
  HKEY v14; // rcx
  LSTATUS v15; // eax
  int v16; // ecx
  int v17; // r8d
  int v18; // r9d
  BYTE Data[8]; // [rsp+30h] [rbp-50h] BYREF
  RPC_WSTR StringUuid; // [rsp+38h] [rbp-48h] BYREF
  DWORD cbData; // [rsp+40h] [rbp-40h] BYREF
  unsigned __int64 v23; // [rsp+48h] [rbp-38h] BYREF
  HKEY hKey; // [rsp+50h] [rbp-30h] BYREF
  DWORD Type; // [rsp+58h] [rbp-28h] BYREF
  const char *v26; // [rsp+60h] [rbp-20h] BYREF
  UUID Uuid; // [rsp+68h] [rbp-18h] BYREF

  StringUuid = 0;
  hKey = 0;
  v23 = 0;
  Uuid = 0;
  *(_DWORD *)Data = 0;
  cbData = 0;
  Type = 0;
  v6 = UuidCreate(&Uuid);
  v7 = v6;
  if ( v6 && v6 != 1824 )
  {
    if ( v6 > 0 )
      v7 = (unsigned __int16)v6 | 0x80070000;
    if ( v7 < 0 )
    {
      v8 = "UuidCreate failed: 0x%x in %s";
LABEL_7:
      _DbgPrintMessage(8, v8, (unsigned int)v7, "CSessionManager::GetGlobalSettings");
      goto LABEL_32;
    }
  }
  v9 = UuidToStringW(&Uuid, &StringUuid);
  v7 = v9;
  if ( v9 )
  {
    if ( v9 > 0 )
      v7 = (unsigned __int16)v9 | 0x80070000;
    if ( v7 < 0 )
    {
      v8 = "UuidToString failed: 0x%x in %s";
      goto LABEL_7;
    }
  }
  v10 = StringCchLengthW(StringUuid, 0x7FFFFFFFu, &v23);
  v7 = v10;
  if ( v10 < 0 )
  {
    _DbgPrintMessage(8, "StringCchLength failed: 0x%x in %s", (unsigned int)v10, "CSessionManager::GetGlobalSettings");
    goto LABEL_32;
  }
  v11 = v23;
  if ( v23 > 0x1F )
  {
    v11 = 31;
    StringUuid[31] = 0;
  }
  v12 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"System\\CurrentControlSet\\Control\\Terminal Server", 0, 0x20006u, &hKey);
  v7 = v12;
  if ( v12 )
  {
    if ( v12 > 0 )
      v7 = (unsigned __int16)v12 | 0x80070000;
    if ( v7 < 0 )
    {
      v8 = "RegOpenKeyEx failed: 0x%x in %s";
      goto LABEL_7;
    }
  }
  cbData = 4;
  if ( RegQueryValueExW(hKey, L"LSMGlobalSetting", 0, &Type, Data, &cbData)
    || (v13 = *(_DWORD *)Data, *(_DWORD *)Data != 4) )
  {
    v13 = 0;
    *(_DWORD *)Data = 0;
  }
  v14 = hKey;
  *a3 = v13;
  v15 = RegSetValueExW(v14, L"InstanceID", 0, 1u, (const BYTE *)StringUuid, 2 * v11 + 2);
  v7 = v15;
  if ( v15 > 0 )
    v7 = (unsigned __int16)v15 | 0x80070000;
  if ( v7 < 0 )
  {
    v8 = "RegSetValueEx failed: 0x%x in %s";
    goto LABEL_7;
  }
  v7 = StringCchCopyW(a2, 0x20u, StringUuid);
  *((_DWORD *)this + 424) = CandidateAccountManagerPolicy::IsCachedSessionEnabled();
  if ( (unsigned int)dword_1800DF020 > 4 )
  {
    LODWORD(v23) = *((_DWORD *)this + 424);
    v26 = "CachedSessionMode value was read";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      v16,
      (unsigned int)word_1800C745A,
      v17,
      v18,
      (__int64)&v26,
      (__int64)&v23);
  }
LABEL_32:
  if ( hKey )
    RegCloseKey(hKey);
  if ( StringUuid )
    RpcStringFreeW(&StringUuid);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180065ac4  push    rbp
0x180065ac6  push    rbx
0x180065ac7  push    rsi
0x180065ac8  push    rdi
0x180065ac9  push    r13
0x180065acb  push    r14
0x180065acd  push    r15
0x180065acf  mov     rbp, rsp
0x180065ad2  sub     rsp, 80h
0x180065ad9  mov     rax, cs:__security_cookie
0x180065ae0  xor     rax, rsp
0x180065ae3  mov     [rbp+var_8], rax
0x180065ae7  mov     rsi, rcx
0x180065aea  mov     [rbp+StringUuid], 0
0x180065af2  xorps   xmm0, xmm0
0x180065af5  mov     [rbp+hKey], 0
0x180065afd  lea     rcx, [rbp+Uuid]; Uuid
0x180065b01  mov     [rbp+var_38], 0
0x180065b09  movups  xmmword ptr [rbp+Uuid.Data1], xmm0
0x180065b0d  mov     r14, r8
0x180065b10  mov     dword ptr [rbp+Data], 0
0x180065b17  mov     r15, rdx
0x180065b1a  mov     [rbp+cbData], 0
0x180065b21  mov     [rbp+Type], 0
0x180065b28  call    cs:__imp_UuidCreate
0x180065b2f  nop     dword ptr [rax+rax+00h]
0x180065b34  mov     ebx, eax
0x180065b36  mov     r13d, 80070000h
0x180065b3c  test    eax, eax
0x180065b3e  jz      short loc_180065B75
0x180065b40  cmp     eax, 720h
0x180065b45  jz      short loc_180065B75
0x180065b47  test    eax, eax
0x180065b49  jle     short loc_180065B51
0x180065b4b  movzx   ebx, ax
0x180065b4e  or      ebx, r13d
0x180065b51  test    ebx, ebx
0x180065b53  jns     short loc_180065B75
0x180065b55  lea     rdx, aUuidcreateFail; "UuidCreate failed: 0x%x in %s"
0x180065b5c  mov     r8d, ebx
0x180065b5f  lea     r9, aCsessionmanage; "CSessionManager::GetGlobalSettings"
0x180065b66  mov     ecx, 8; int
0x180065b6b  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180065b70  jmp     loc_180065D21
0x180065b75  lea     rdx, [rbp+StringUuid]; StringUuid
0x180065b79  lea     rcx, [rbp+Uuid]; Uuid
0x180065b7d  call    cs:__imp_UuidToStringW
0x180065b84  nop     dword ptr [rax+rax+00h]
0x180065b89  mov     ebx, eax
0x180065b8b  test    eax, eax
0x180065b8d  jz      short loc_180065BA4
0x180065b8f  jle     short loc_180065B97
0x180065b91  movzx   ebx, ax
0x180065b94  or      ebx, r13d
0x180065b97  test    ebx, ebx
0x180065b99  jns     short loc_180065BA4
0x180065b9b  lea     rdx, aUuidtostringFa; "UuidToString failed: 0x%x in %s"
0x180065ba2  jmp     short loc_180065B5C
0x180065ba4  mov     rcx, [rbp+StringUuid]; unsigned __int16 *
0x180065ba8  lea     r8, [rbp+var_38]; unsigned __int64 *
0x180065bac  mov     edx, 7FFFFFFFh; unsigned __int64
0x180065bb1  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x180065bb6  mov     ebx, eax
0x180065bb8  test    eax, eax
0x180065bba  jns     short loc_180065BC8
0x180065bbc  mov     r8d, eax
0x180065bbf  lea     rdx, aStringcchlengt; "StringCchLength failed: 0x%x in %s"
0x180065bc6  jmp     short loc_180065B5F
0x180065bc8  mov     rdi, [rbp+var_38]
0x180065bcc  cmp     rdi, 1Fh
0x180065bd0  jbe     short loc_180065BE1
0x180065bd2  mov     rax, [rbp+StringUuid]
0x180065bd6  xor     ecx, ecx
0x180065bd8  mov     edi, 1Fh
0x180065bdd  mov     [rax+3Eh], cx
0x180065be1  lea     rax, [rbp+hKey]
0x180065be5  mov     r9d, 20006h; samDesired
0x180065beb  xor     r8d, r8d; ulOptions
0x180065bee  mov     [rsp+80h+phkResult], rax; phkResult
0x180065bf3  lea     rdx, SubKey; "System\\CurrentControlSet\\Control\\Ter"...
0x180065bfa  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180065c01  call    cs:__imp_RegOpenKeyExW
0x180065c08  nop     dword ptr [rax+rax+00h]
0x180065c0d  mov     ebx, eax
0x180065c0f  test    eax, eax
0x180065c11  jz      short loc_180065C2B
0x180065c13  jle     short loc_180065C1B
0x180065c15  movzx   ebx, ax
0x180065c18  or      ebx, r13d
0x180065c1b  test    ebx, ebx
0x180065c1d  jns     short loc_180065C2B
0x180065c1f  lea     rdx, aRegopenkeyexFa; "RegOpenKeyEx failed: 0x%x in %s"
0x180065c26  jmp     loc_180065B5C
0x180065c2b  mov     rcx, [rbp+hKey]; hKey
0x180065c2f  lea     rax, [rbp+cbData]
0x180065c33  mov     [rsp+80h+lpcbData], rax; lpcbData
0x180065c38  lea     r9, [rbp+Type]; lpType
0x180065c3c  lea     rax, [rbp+Data]
0x180065c40  mov     [rbp+cbData], 4
0x180065c47  xor     r8d, r8d; lpReserved
0x180065c4a  mov     [rsp+80h+phkResult], rax; lpData
0x180065c4f  lea     rdx, aLsmglobalsetti; "LSMGlobalSetting"
0x180065c56  call    cs:__imp_RegQueryValueExW
0x180065c5d  nop     dword ptr [rax+rax+00h]
0x180065c62  test    eax, eax
0x180065c64  jnz     short loc_180065C6E
0x180065c66  mov     eax, dword ptr [rbp+Data]
0x180065c69  cmp     eax, 4
0x180065c6c  jz      short loc_180065C73
0x180065c6e  xor     eax, eax
0x180065c70  mov     dword ptr [rbp+Data], eax
0x180065c73  mov     rcx, [rbp+hKey]; hKey
0x180065c77  lea     rdx, aInstanceid_0; "InstanceID"
0x180065c7e  mov     [r14], eax
0x180065c81  mov     r9d, 1; dwType
0x180065c87  lea     eax, ds:2[rdi*2]
0x180065c8e  xor     r8d, r8d; Reserved
0x180065c91  mov     dword ptr [rsp+80h+lpcbData], eax; cbData
0x180065c95  mov     rax, [rbp+StringUuid]
0x180065c99  mov     [rsp+80h+phkResult], rax; lpData
0x180065c9e  call    cs:__imp_RegSetValueExW
0x180065ca5  nop     dword ptr [rax+rax+00h]
0x180065caa  mov     ebx, eax
0x180065cac  test    eax, eax
0x180065cae  jle     short loc_180065CB6
0x180065cb0  movzx   ebx, ax
0x180065cb3  or      ebx, r13d
0x180065cb6  test    ebx, ebx
0x180065cb8  jns     short loc_180065CC6
0x180065cba  lea     rdx, aRegsetvalueexF; "RegSetValueEx failed: 0x%x in %s"
0x180065cc1  jmp     loc_180065B5C
0x180065cc6  mov     r8, [rbp+StringUuid]; unsigned __int16 *
0x180065cca  mov     edx, 20h ; ' '; unsigned __int64
0x180065ccf  mov     rcx, r15; unsigned __int16 *
0x180065cd2  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180065cd7  mov     ebx, eax
0x180065cd9  call    ?IsCachedSessionEnabled@CandidateAccountManagerPolicy@@SAHXZ; CandidateAccountManagerPolicy::IsCachedSessionEnabled(void)
0x180065cde  mov     [rsi+6A0h], eax
0x180065ce4  mov     eax, cs:dword_1800DF020
0x180065cea  cmp     eax, 4
0x180065ced  jbe     short loc_180065D21
0x180065cef  mov     eax, [rsi+6A0h]
0x180065cf5  lea     rdx, word_1800C745A
0x180065cfc  mov     dword ptr [rbp+var_38], eax
0x180065cff  lea     rax, aCachedsessionm; "CachedSessionMode value was read"
0x180065d06  mov     [rbp+var_20], rax
0x180065d0a  lea     rax, [rbp+var_38]
0x180065d0e  mov     [rsp+80h+lpcbData], rax
0x180065d13  lea     rax, [rbp+var_20]
0x180065d17  mov     [rsp+80h+phkResult], rax
0x180065d1c  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x180065d21  mov     rcx, [rbp+hKey]; hKey
0x180065d25  test    rcx, rcx
0x180065d28  jz      short loc_180065D36
0x180065d2a  call    cs:__imp_RegCloseKey
0x180065d31  nop     dword ptr [rax+rax+00h]
0x180065d36  cmp     [rbp+StringUuid], 0
0x180065d3b  jz      short loc_180065D4D
0x180065d3d  lea     rcx, [rbp+StringUuid]; String
0x180065d41  call    cs:__imp_RpcStringFreeW
0x180065d48  nop     dword ptr [rax+rax+00h]
0x180065d4d  mov     eax, ebx
0x180065d4f  mov     rcx, [rbp+var_8]
0x180065d53  xor     rcx, rsp; StackCookie
0x180065d56  call    __security_check_cookie
0x180065d5b  add     rsp, 80h
0x180065d62  pop     r15
0x180065d64  pop     r14
0x180065d66  pop     r13
0x180065d68  pop     rdi
0x180065d69  pop     rsi
0x180065d6a  pop     rbx
0x180065d6b  pop     rbp
0x180065d6c  retn
```
