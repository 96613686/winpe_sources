# WcsGetCalibrationManagementState

- ea: `0x180024ba0`
- end: `0x180024d67`
- name: `WcsGetCalibrationManagementState`
- size: `455`
- prototype: `BOOL __stdcall(BOOL *pbIsEnabled)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18004b680`

## callees

- `0x1800016bc`
- `0x180002874`
- `0x180023a4c`
- `0x180024ba0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180024c89`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180024c89`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180024c26`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180024c4c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180024c26`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180024c4c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180024cb9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180024cc8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180024cb9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180024cc8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180024cd0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180024cd0`

## pseudocode

```c
BOOL __stdcall WcsGetCalibrationManagementState(BOOL *pbIsEnabled)
{
  __int64 v2; // rcx
  __int64 v3; // r8
  __int64 v4; // r9
  LSTATUS v5; // ebx
  LSTATUS v6; // eax
  __int64 v7; // r8
  __int64 v8; // r9
  BOOL v9; // eax
  BOOL v11; // [rsp+40h] [rbp-30h] BYREF
  LSTATUS v12; // [rsp+44h] [rbp-2Ch] BYREF
  __int64 v13; // [rsp+48h] [rbp-28h] BYREF
  HKEY hKey; // [rsp+50h] [rbp-20h] BYREF
  HKEY phkResult; // [rsp+58h] [rbp-18h] BYREF
  __int64 v16; // [rsp+60h] [rbp-10h] BYREF
  DWORD Type; // [rsp+98h] [rbp+28h] BYREF
  DWORD cbData; // [rsp+A0h] [rbp+30h] BYREF
  int Data; // [rsp+A8h] [rbp+38h] BYREF

  hKey = 0;
  phkResult = 0;
  if ( (unsigned int)dword_18009E080 > 5 && (unsigned __int8)tlgKeywordOn(&dword_18009E080, 0x200000000000LL) )
  {
    v13 = 0x2000000;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>>(
      v2,
      (__int64)&dword_180091A9C,
      v3,
      v4,
      (__int64)&v13);
  }
  v5 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, gszICMRegPath, 0, 0x20119u, &hKey);
  if ( !v5 )
  {
    v5 = RegOpenKeyExW(hKey, L"Calibration", 0, 0x20119u, &phkResult);
    if ( !v5 )
    {
      Type = 0;
      Data = 0;
      cbData = 4;
      v6 = RegQueryValueExW(phkResult, L"CalibrationManagementEnabled", 0, &Type, (LPBYTE)&Data, &cbData);
      v5 = v6;
      if ( !v6 )
      {
        if ( Type == 4 && cbData == 4 )
        {
          LOBYTE(v6) = Data != 0;
          *pbIsEnabled = v6;
        }
        else
        {
          v5 = 87;
        }
      }
    }
  }
  if ( hKey )
    RegCloseKey(hKey);
  if ( phkResult )
    RegCloseKey(phkResult);
  SetLastError(v5);
  if ( (unsigned int)dword_18009E080 > 5 && (unsigned __int8)tlgKeywordOn(&dword_18009E080, 0x200000000000LL) )
  {
    v16 = 0x2000000;
    if ( v5 )
      v9 = 0;
    else
      v9 = *pbIsEnabled;
    v11 = v9;
    v12 = v5;
    LODWORD(v13) = v5 == 0;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
      (__int64)&dword_18009E080,
      (__int64)byte_180091971,
      v7,
      v8,
      (__int64)&v13,
      (__int64)&v12,
      (__int64)&v11,
      (__int64)&v16);
  }
  return v5 == 0;
}

```

## disassembly

```asm
0x180024ba0  mov     [rsp-18h+arg_0], rbx
0x180024ba5  push    rbp
0x180024ba6  push    rsi
0x180024ba7  push    rdi
0x180024ba8  mov     rbp, rsp
0x180024bab  sub     rsp, 70h
0x180024baf  mov     eax, cs:dword_18009E080
0x180024bb5  mov     rsi, rcx
0x180024bb8  mov     [rbp+hKey], 0
0x180024bc0  mov     [rbp+var_18], 0
0x180024bc8  cmp     eax, 5
0x180024bcb  jbe     short loc_180024C04
0x180024bcd  mov     rdx, 200000000000h
0x180024bd7  lea     rcx, dword_18009E080
0x180024bde  call    _tlgKeywordOn
0x180024be3  test    al, al
0x180024be5  jz      short loc_180024C04
0x180024be7  lea     rax, [rbp+var_28]
0x180024beb  mov     [rbp+var_28], 2000000h
0x180024bf3  lea     rdx, dword_180091A9C
0x180024bfa  mov     [rsp+70h+phkResult], rax
0x180024bff  call    ??$Write@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &)
0x180024c04  lea     rax, [rbp+hKey]
0x180024c08  mov     edi, 20119h
0x180024c0d  mov     r9d, edi; samDesired
0x180024c10  mov     [rsp+70h+phkResult], rax; phkResult
0x180024c15  xor     r8d, r8d; ulOptions
0x180024c18  lea     rdx, gszICMRegPath; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x180024c1f  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180024c26  call    cs:__imp_RegOpenKeyExW
0x180024c2c  mov     ebx, eax
0x180024c2e  test    eax, eax
0x180024c30  jnz     short loc_180024CB0
0x180024c32  mov     rcx, [rbp+hKey]; hKey
0x180024c36  lea     rax, [rbp+var_18]
0x180024c3a  mov     r9d, edi; samDesired
0x180024c3d  mov     [rsp+70h+phkResult], rax; phkResult
0x180024c42  xor     r8d, r8d; ulOptions
0x180024c45  lea     rdx, SubKey; "Calibration"
0x180024c4c  call    cs:__imp_RegOpenKeyExW
0x180024c52  mov     ebx, eax
0x180024c54  test    eax, eax
0x180024c56  jnz     short loc_180024CB0
0x180024c58  mov     rcx, [rbp+var_18]; hKey
0x180024c5c  lea     r9, [rbp+Type]; lpType
0x180024c60  mov     [rbp+Type], eax
0x180024c63  lea     rdx, ValueName; "CalibrationManagementEnabled"
0x180024c6a  mov     [rbp+Data], eax
0x180024c6d  xor     r8d, r8d; lpReserved
0x180024c70  lea     rax, [rbp+cbData]
0x180024c74  mov     [rbp+cbData], 4
0x180024c7b  mov     [rsp+70h+lpcbData], rax; lpcbData
0x180024c80  lea     rax, [rbp+Data]
0x180024c84  mov     [rsp+70h+phkResult], rax; lpData
0x180024c89  call    cs:__imp_RegQueryValueExW
0x180024c8f  mov     ebx, eax
0x180024c91  test    eax, eax
0x180024c93  jnz     short loc_180024CB0
0x180024c95  cmp     [rbp+Type], 4
0x180024c99  jnz     short loc_180024CAB
0x180024c9b  cmp     [rbp+cbData], 4
0x180024c9f  jnz     short loc_180024CAB
0x180024ca1  cmp     [rbp+Data], eax
0x180024ca4  setnz   al
0x180024ca7  mov     [rsi], eax
0x180024ca9  jmp     short loc_180024CB0
0x180024cab  mov     ebx, 57h ; 'W'
0x180024cb0  mov     rcx, [rbp+hKey]; hKey
0x180024cb4  test    rcx, rcx
0x180024cb7  jz      short loc_180024CBF
0x180024cb9  call    cs:__imp_RegCloseKey
0x180024cbf  mov     rcx, [rbp+var_18]; hKey
0x180024cc3  test    rcx, rcx
0x180024cc6  jz      short loc_180024CCE
0x180024cc8  call    cs:__imp_RegCloseKey
0x180024cce  mov     ecx, ebx; dwErrCode
0x180024cd0  call    cs:__imp_SetLastError
0x180024cd6  mov     eax, cs:dword_18009E080
0x180024cdc  xor     edi, edi
0x180024cde  test    ebx, ebx
0x180024ce0  setz    dil
0x180024ce4  cmp     eax, 5
0x180024ce7  jbe     short loc_180024D55
0x180024ce9  mov     rdx, 200000000000h
0x180024cf3  lea     rcx, dword_18009E080
0x180024cfa  call    _tlgKeywordOn
0x180024cff  test    al, al
0x180024d01  jz      short loc_180024D55
0x180024d03  mov     [rbp+var_10], 2000000h
0x180024d0b  test    ebx, ebx
0x180024d0d  jnz     short loc_180024D13
0x180024d0f  mov     eax, [rsi]
0x180024d11  jmp     short loc_180024D15
0x180024d13  xor     eax, eax
0x180024d15  mov     [rbp+var_30], eax
0x180024d18  lea     rdx, byte_180091971
0x180024d1f  lea     rax, [rbp+var_10]
0x180024d23  mov     [rbp+var_2C], ebx
0x180024d26  mov     [rsp+70h+var_38], rax
0x180024d2b  lea     rcx, dword_18009E080
0x180024d32  lea     rax, [rbp+var_30]
0x180024d36  mov     dword ptr [rbp+var_28], edi
0x180024d39  mov     [rsp+70h+var_40], rax
0x180024d3e  lea     rax, [rbp+var_2C]
0x180024d42  mov     [rsp+70h+lpcbData], rax
0x180024d47  lea     rax, [rbp+var_28]
0x180024d4b  mov     [rsp+70h+phkResult], rax
0x180024d50  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@U1@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@33AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &)
0x180024d55  mov     rbx, [rsp+70h+arg_0]
0x180024d5d  mov     eax, edi
0x180024d5f  add     rsp, 70h
0x180024d63  pop     rdi
0x180024d64  pop     rsi
0x180024d65  pop     rbp
0x180024d66  retn
```
