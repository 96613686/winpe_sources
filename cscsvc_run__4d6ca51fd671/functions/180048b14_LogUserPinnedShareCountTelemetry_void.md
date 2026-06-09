# LogUserPinnedShareCountTelemetry(void)

- ea: `0x180048b14`
- end: `0x180048d00`
- name: `?LogUserPinnedShareCountTelemetry@@YAXXZ`
- size: `492`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18003e060`

## callees

- `0x180001008`
- `0x180001080`
- `0x180036394`
- `0x18003c488`
- `0x18003c4e8`
- `0x180047f04`
- `0x180048b14`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180048b79`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180048b79`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180048bae`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180048bae`
- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x180048b4b`
- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x180048b4b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180048c7e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180048cc4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180048c7e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180048cc4`

## pseudocode

```c
void LogUserPinnedShareCountTelemetry(void)
{
  unsigned int v0; // eax
  LSTATUS v1; // eax
  unsigned int v2; // eax
  __int64 v3; // rdx
  __int64 v4; // rcx
  unsigned int DomainHash; // eax
  __int64 v6; // rdx
  int v7; // ecx
  int v8; // r8d
  int v9; // r9d
  int v10; // [rsp+30h] [rbp-20h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-18h] BYREF
  HKEY phkResult; // [rsp+40h] [rbp-10h] BYREF
  DWORD Type; // [rsp+60h] [rbp+10h] BYREF
  int Data; // [rsp+68h] [rbp+18h] BYREF
  DWORD cbData; // [rsp+70h] [rbp+20h] BYREF
  int v16; // [rsp+78h] [rbp+28h] BYREF

  Data = 0;
  Type = 0;
  cbData = 4;
  phkResult = 0;
  hKey = 0;
  v0 = RegOpenCurrentUser(1u, &phkResult);
  if ( v0 )
  {
    if ( WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 31, WPP_65174b6254cf30406df57586ff17ec03_Traceguids, v0);
    }
  }
  else
  {
    v1 = RegOpenKeyExW(phkResult, L"Software\\Microsoft\\UserData\\OfflineFiles", 0, 1u, &hKey);
    if ( v1 )
    {
      if ( WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
      {
        WPP_SF_Sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          30,
          (unsigned int)WPP_65174b6254cf30406df57586ff17ec03_Traceguids,
          (unsigned int)L"Software\\Microsoft\\UserData\\OfflineFiles",
          v1);
      }
    }
    else
    {
      v2 = RegQueryValueExW(hKey, L"UserPinnedShareCount", 0, &Type, (LPBYTE)&Data, &cbData);
      if ( v2 || Type != 4 )
      {
        if ( WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
        {
          WPP_SF_Sd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            29,
            (unsigned int)WPP_65174b6254cf30406df57586ff17ec03_Traceguids,
            (unsigned int)L"UserPinnedShareCount",
            v2);
        }
      }
      else
      {
        DomainHash = GetDomainHash(v4, v3, v2);
        if ( (unsigned int)dword_1800B6928 > 5
          && (unsigned __int8)tlgKeywordOn((unsigned int)dword_1800B6928, v6, DomainHash) )
        {
          v10 = Data;
          v16 = v8;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
            v7,
            (unsigned int)&word_1800AD286,
            v8,
            v9,
            (__int64)&v10,
            (__int64)&v16);
        }
        if ( WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
        {
          WPP_SF_S(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            28,
            WPP_65174b6254cf30406df57586ff17ec03_Traceguids,
            L"UserPinnedShareCount");
        }
      }
      RegCloseKey(hKey);
    }
    RegCloseKey(phkResult);
  }
}

```

## disassembly

```asm
0x180048b14  push    rbp
0x180048b16  mov     rbp, rsp
0x180048b19  sub     rsp, 50h
0x180048b1d  lea     rdx, [rbp+phkResult]; phkResult
0x180048b21  mov     [rbp+Data], 0
0x180048b28  mov     ecx, 1; samDesired
0x180048b2d  mov     [rbp+Type], 0
0x180048b34  mov     [rbp+cbData], 4
0x180048b3b  mov     [rbp+phkResult], 0
0x180048b43  mov     [rbp+hKey], 0
0x180048b4b  call    cs:__imp_RegOpenCurrentUser
0x180048b51  mov     r9d, eax
0x180048b54  test    eax, eax
0x180048b56  jnz     loc_180048CCC
0x180048b5c  mov     rcx, [rbp+phkResult]; hKey
0x180048b60  lea     rax, [rbp+hKey]
0x180048b64  mov     r9d, 1; samDesired
0x180048b6a  mov     [rsp+50h+var_30], rax; phkResult
0x180048b6f  xor     r8d, r8d; ulOptions
0x180048b72  lea     rdx, aSoftwareMicros_1; "Software\\Microsoft\\UserData\\OfflineF"...
0x180048b79  call    cs:__imp_RegOpenKeyExW
0x180048b7f  mov     r8d, eax
0x180048b82  test    eax, eax
0x180048b84  jnz     loc_180048C86
0x180048b8a  mov     rcx, [rbp+hKey]; hKey
0x180048b8e  lea     rax, [rbp+cbData]
0x180048b92  mov     [rsp+50h+lpcbData], rax; lpcbData
0x180048b97  lea     r9, [rbp+Type]; lpType
0x180048b9b  lea     rax, [rbp+Data]
0x180048b9f  xor     r8d, r8d; lpReserved
0x180048ba2  lea     rdx, aUserpinnedshar; "UserPinnedShareCount"
0x180048ba9  mov     [rsp+50h+var_30], rax; lpData
0x180048bae  call    cs:__imp_RegQueryValueExW
0x180048bb4  mov     r8d, eax
0x180048bb7  test    eax, eax
0x180048bb9  jnz     loc_180048C40
0x180048bbf  cmp     [rbp+Type], 4
0x180048bc3  jnz     short loc_180048C40
0x180048bc5  call    GetDomainHash
0x180048bca  mov     ecx, cs:dword_1800B6928
0x180048bd0  mov     r8d, eax
0x180048bd3  cmp     ecx, 5
0x180048bd6  jbe     short loc_180048C09
0x180048bd8  call    _tlgKeywordOn
0x180048bdd  test    al, al
0x180048bdf  jz      short loc_180048C09
0x180048be1  mov     eax, [rbp+Data]
0x180048be4  lea     rdx, word_1800AD286
0x180048beb  mov     [rbp+var_20], eax
0x180048bee  lea     rax, [rbp+arg_18]
0x180048bf2  mov     [rsp+50h+lpcbData], rax
0x180048bf7  lea     rax, [rbp+var_20]
0x180048bfb  mov     [rsp+50h+var_30], rax
0x180048c00  mov     [rbp+arg_18], r8d
0x180048c04  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180048c09  mov     rcx, cs:WPP_GLOBAL_Control
0x180048c10  lea     rax, WPP_GLOBAL_Control
0x180048c17  cmp     rcx, rax
0x180048c1a  jz      short loc_180048C7A
0x180048c1c  test    byte ptr [rcx+1Ch], 20h
0x180048c20  jz      short loc_180048C7A
0x180048c22  mov     rcx, [rcx+10h]
0x180048c26  lea     r9, aUserpinnedshar; "UserPinnedShareCount"
0x180048c2d  mov     edx, 1Ch
0x180048c32  lea     r8, WPP_65174b6254cf30406df57586ff17ec03_Traceguids
0x180048c39  call    WPP_SF_S
0x180048c3e  jmp     short loc_180048C7A
0x180048c40  mov     rcx, cs:WPP_GLOBAL_Control
0x180048c47  lea     rax, WPP_GLOBAL_Control
0x180048c4e  cmp     rcx, rax
0x180048c51  jz      short loc_180048C7A
0x180048c53  test    byte ptr [rcx+1Ch], 20h
0x180048c57  jz      short loc_180048C7A
0x180048c59  mov     rcx, [rcx+10h]
0x180048c5d  lea     r9, aUserpinnedshar; "UserPinnedShareCount"
0x180048c64  mov     dword ptr [rsp+50h+var_30], r8d
0x180048c69  mov     edx, 1Dh
0x180048c6e  lea     r8, WPP_65174b6254cf30406df57586ff17ec03_Traceguids
0x180048c75  call    WPP_SF_Sd
0x180048c7a  mov     rcx, [rbp+hKey]; hKey
0x180048c7e  call    cs:__imp_RegCloseKey
0x180048c84  jmp     short loc_180048CC0
0x180048c86  mov     rcx, cs:WPP_GLOBAL_Control
0x180048c8d  lea     rax, WPP_GLOBAL_Control
0x180048c94  cmp     rcx, rax
0x180048c97  jz      short loc_180048CC0
0x180048c99  test    byte ptr [rcx+1Ch], 20h
0x180048c9d  jz      short loc_180048CC0
0x180048c9f  mov     rcx, [rcx+10h]
0x180048ca3  lea     r9, aSoftwareMicros_1; "Software\\Microsoft\\UserData\\OfflineF"...
0x180048caa  mov     dword ptr [rsp+50h+var_30], r8d
0x180048caf  mov     edx, 1Eh
0x180048cb4  lea     r8, WPP_65174b6254cf30406df57586ff17ec03_Traceguids
0x180048cbb  call    WPP_SF_Sd
0x180048cc0  mov     rcx, [rbp+phkResult]; hKey
0x180048cc4  call    cs:__imp_RegCloseKey
0x180048cca  jmp     short loc_180048CFA
0x180048ccc  mov     rcx, cs:WPP_GLOBAL_Control
0x180048cd3  lea     rax, WPP_GLOBAL_Control
0x180048cda  cmp     rcx, rax
0x180048cdd  jz      short loc_180048CFA
0x180048cdf  test    byte ptr [rcx+1Ch], 20h
0x180048ce3  jz      short loc_180048CFA
0x180048ce5  mov     rcx, [rcx+10h]
0x180048ce9  lea     r8, WPP_65174b6254cf30406df57586ff17ec03_Traceguids
0x180048cf0  mov     edx, 1Fh
0x180048cf5  call    WPP_SF_d
0x180048cfa  add     rsp, 50h
0x180048cfe  pop     rbp
0x180048cff  retn
```
