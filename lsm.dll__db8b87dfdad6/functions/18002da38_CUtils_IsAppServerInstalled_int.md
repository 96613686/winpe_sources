# CUtils::IsAppServerInstalled(int &)

- ea: `0x18002da38`
- end: `0x18002dbe6`
- name: `?IsAppServerInstalled@CUtils@@SAJAEAH@Z`
- size: `430`
- prototype: `__int64 __fastcall(int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18002d804`

## callees

- `0x180001874`
- `0x180003570`
- `0x18002da38`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002da76`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002da76`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002db12`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002db12`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002dbd4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002dbd4`

## string_xrefs

- `0x18002dae9`: `TSAppCompat`
- `0x18002da8d`: `Unable to open TS key in HKLM`
- `0x18002db90`: `Unable to read APPCOMPAT key`
- `0x18002db3e`: `Successfully read APPCOMPAT key`

## pseudocode

```c
__int64 __fastcall CUtils::IsAppServerInstalled(int *a1)
{
  int v2; // ebx
  unsigned int v3; // eax
  __int64 v4; // r8
  __int64 v5; // r9
  unsigned int v6; // eax
  int v7; // ecx
  const char *v9; // [rsp+40h] [rbp-28h] BYREF
  HKEY hKey; // [rsp+48h] [rbp-20h] BYREF
  const WCHAR *v11; // [rsp+50h] [rbp-18h] BYREF
  const char *v12; // [rsp+58h] [rbp-10h] BYREF
  DWORD cbData; // [rsp+90h] [rbp+28h] BYREF
  DWORD Type; // [rsp+98h] [rbp+30h] BYREF
  int Data; // [rsp+A0h] [rbp+38h] BYREF
  int v16; // [rsp+A8h] [rbp+40h] BYREF

  *a1 = 0;
  hKey = 0;
  v2 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"System\\CurrentControlSet\\Control\\Terminal Server", 0, 0x20019u, &hKey);
  if ( v2 )
  {
    if ( (unsigned int)dword_1800DA020 > 2 )
    {
      v16 = v2;
      v9 = "Unable to open TS key in HKLM";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
        (__int64)&dword_1800DA020,
        (__int64)&byte_1800C8257,
        0,
        0,
        (const unsigned __int16 **)&v9,
        (__int64)&v16);
    }
    if ( v2 > 0 )
      v2 = (unsigned __int16)v2 | 0x80070000;
  }
  else
  {
    cbData = 4;
    v2 = 0;
    Type = 0;
    Data = 0;
    v3 = RegQueryValueExW(hKey, L"TSAppCompat", 0, &Type, (LPBYTE)&Data, &cbData);
    if ( !v3 && cbData == 4 && Type == 4 )
    {
      v6 = dword_1800DA020;
      v7 = Data;
      *a1 = Data;
      if ( v6 > 4 )
      {
        v16 = v7;
        v9 = "Successfully read APPCOMPAT key";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
          (__int64)&dword_1800DA020,
          (__int64)&byte_1800C827F,
          0,
          0,
          (const unsigned __int16 **)&v9,
          (__int64)&v16);
      }
    }
    else if ( (unsigned int)dword_1800DA020 > 4 )
    {
      v16 = *a1;
      v12 = "Unable to read APPCOMPAT key";
      v11 = L"TSAppCompat";
      LODWORD(v9) = v3;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>>(
        v3,
        (__int64)byte_1800C82AB,
        v4,
        v5,
        (const unsigned __int16 **)&v12,
        (__int64)&v9,
        (__int64)&v16,
        (__int64 **)&v11);
    }
  }
  if ( hKey )
    RegCloseKey(hKey);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x18002da38  push    rbp
0x18002da3a  push    rbx
0x18002da3b  push    rdi
0x18002da3c  push    r15
0x18002da3e  mov     rbp, rsp
0x18002da41  sub     rsp, 68h
0x18002da45  mov     rdi, rcx
0x18002da48  mov     dword ptr [rcx], 0
0x18002da4e  lea     rax, [rbp+hKey]
0x18002da52  mov     [rbp+hKey], 0
0x18002da5a  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18002da61  mov     [rsp+68h+phkResult], rax; phkResult
0x18002da66  mov     r9d, 20019h; samDesired
0x18002da6c  lea     rdx, SubKey; "System\\CurrentControlSet\\Control\\Ter"...
0x18002da73  xor     r8d, r8d; ulOptions
0x18002da76  call    cs:__imp_RegOpenKeyExW
0x18002da7c  mov     ebx, eax
0x18002da7e  test    eax, eax
0x18002da80  jz      short loc_18002DADC
0x18002da82  mov     eax, cs:dword_1800DA020
0x18002da88  cmp     eax, 2
0x18002da8b  jbe     short loc_18002DAC6
0x18002da8d  lea     rax, aUnableToOpenTs_0; "Unable to open TS key in HKLM"
0x18002da94  mov     [rbp+arg_18], ebx
0x18002da97  mov     [rbp+var_28], rax
0x18002da9b  lea     rdx, byte_1800C8257
0x18002daa2  lea     rax, [rbp+arg_18]
0x18002daa6  xor     r9d, r9d
0x18002daa9  mov     [rsp+68h+lpcbData], rax
0x18002daae  lea     rcx, dword_1800DA020
0x18002dab5  lea     rax, [rbp+var_28]
0x18002dab9  xor     r8d, r8d
0x18002dabc  mov     [rsp+68h+phkResult], rax
0x18002dac1  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18002dac6  test    ebx, ebx
0x18002dac8  jle     loc_18002DBCB
0x18002dace  movzx   ebx, bx
0x18002dad1  or      ebx, 80070000h
0x18002dad7  jmp     loc_18002DBCB
0x18002dadc  mov     rcx, [rbp+hKey]; hKey
0x18002dae0  lea     rax, [rbp+cbData]
0x18002dae4  mov     [rsp+68h+lpcbData], rax; lpcbData
0x18002dae9  lea     r15, aTsappcompat; "TSAppCompat"
0x18002daf0  lea     rax, [rbp+Data]
0x18002daf4  mov     [rbp+cbData], 4
0x18002dafb  xor     ebx, ebx
0x18002dafd  mov     [rsp+68h+phkResult], rax; lpData
0x18002db02  lea     r9, [rbp+Type]; lpType
0x18002db06  mov     [rbp+Type], ebx
0x18002db09  xor     r8d, r8d; lpReserved
0x18002db0c  mov     [rbp+Data], ebx
0x18002db0f  mov     rdx, r15; lpValueName
0x18002db12  call    cs:__imp_RegQueryValueExW
0x18002db18  mov     ecx, eax
0x18002db1a  test    eax, eax
0x18002db1c  jnz     short loc_18002DB79
0x18002db1e  cmp     [rbp+cbData], 4
0x18002db22  jnz     short loc_18002DB79
0x18002db24  cmp     [rbp+Type], 4
0x18002db28  jnz     short loc_18002DB79
0x18002db2a  mov     eax, cs:dword_1800DA020
0x18002db30  mov     ecx, [rbp+Data]
0x18002db33  mov     [rdi], ecx
0x18002db35  cmp     eax, 4
0x18002db38  jbe     loc_18002DBCB
0x18002db3e  lea     rax, aSuccessfullyRe; "Successfully read APPCOMPAT key"
0x18002db45  mov     [rbp+arg_18], ecx
0x18002db48  mov     [rbp+var_28], rax
0x18002db4c  lea     rdx, byte_1800C827F
0x18002db53  lea     rax, [rbp+arg_18]
0x18002db57  xor     r9d, r9d
0x18002db5a  mov     [rsp+68h+lpcbData], rax
0x18002db5f  lea     rcx, dword_1800DA020
0x18002db66  lea     rax, [rbp+var_28]
0x18002db6a  xor     r8d, r8d
0x18002db6d  mov     [rsp+68h+phkResult], rax
0x18002db72  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18002db77  jmp     short loc_18002DBCB
0x18002db79  mov     eax, cs:dword_1800DA020
0x18002db7f  cmp     eax, 4
0x18002db82  jbe     short loc_18002DBCB
0x18002db84  mov     eax, [rdi]
0x18002db86  lea     rdx, byte_1800C82AB
0x18002db8d  mov     [rbp+arg_18], eax
0x18002db90  lea     rax, aUnableToReadAp; "Unable to read APPCOMPAT key"
0x18002db97  mov     [rbp+var_10], rax
0x18002db9b  lea     rax, [rbp+var_18]
0x18002db9f  mov     [rsp+68h+var_30], rax
0x18002dba4  lea     rax, [rbp+arg_18]
0x18002dba8  mov     [rsp+68h+var_38], rax
0x18002dbad  lea     rax, [rbp+var_28]
0x18002dbb1  mov     [rsp+68h+lpcbData], rax
0x18002dbb6  lea     rax, [rbp+var_10]
0x18002dbba  mov     [rsp+68h+phkResult], rax
0x18002dbbf  mov     [rbp+var_18], r15
0x18002dbc3  mov     dword ptr [rbp+var_28], ecx
0x18002dbc6  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &)
0x18002dbcb  mov     rcx, [rbp+hKey]; hKey
0x18002dbcf  test    rcx, rcx
0x18002dbd2  jz      short loc_18002DBDA
0x18002dbd4  call    cs:__imp_RegCloseKey
0x18002dbda  mov     eax, ebx
0x18002dbdc  add     rsp, 68h
0x18002dbe0  pop     r15
0x18002dbe2  pop     rdi
0x18002dbe3  pop     rbx
0x18002dbe4  pop     rbp
0x18002dbe5  retn
```
