# CUtils::IsAppServerInstalled(int &)

- ea: `0x18002f9dc`
- end: `0x18002fb9d`
- name: `?IsAppServerInstalled@CUtils@@SAJAEAH@Z`
- size: `449`
- prototype: `__int64 __fastcall(int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18002f7c0`

## callees

- `0x18000187c`
- `0x180003590`
- `0x18002f9dc`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002fa1a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002fa1a`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002fabc`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002fabc`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002fb84`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002fb84`

## string_xrefs

- `0x18002fa37`: `Unable to open TS key in HKLM`
- `0x18002faee`: `Successfully read APPCOMPAT key`
- `0x18002fa93`: `TSAppCompat`
- `0x18002fb40`: `Unable to read APPCOMPAT key`

## pseudocode

```c
__int64 __fastcall CUtils::IsAppServerInstalled(int *a1)
{
  int v2; // ebx
  LSTATUS v3; // ecx
  int v4; // r8d
  int v5; // r9d
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
    if ( (unsigned int)dword_1800DF020 > 2 )
    {
      v16 = v2;
      v9 = "Unable to open TS key in HKLM";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
        (unsigned int)&dword_1800DF020,
        (unsigned int)&byte_1800CD3DF,
        0,
        0,
        (__int64)&v9,
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
      v6 = dword_1800DF020;
      v7 = Data;
      *a1 = Data;
      if ( v6 > 4 )
      {
        v16 = v7;
        v9 = "Successfully read APPCOMPAT key";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
          (unsigned int)&dword_1800DF020,
          (unsigned int)&byte_1800CD407,
          0,
          0,
          (__int64)&v9,
          (__int64)&v16);
      }
    }
    else if ( (unsigned int)dword_1800DF020 > 4 )
    {
      v16 = *a1;
      v12 = "Unable to read APPCOMPAT key";
      v11 = L"TSAppCompat";
      LODWORD(v9) = v3;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>>(
        v3,
        (unsigned int)byte_1800CD433,
        v4,
        v5,
        (__int64)&v12,
        (__int64)&v9,
        (__int64)&v16,
        (__int64)&v11);
    }
  }
  if ( hKey )
    RegCloseKey(hKey);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x18002f9dc  push    rbp
0x18002f9de  push    rbx
0x18002f9df  push    rdi
0x18002f9e0  push    r15
0x18002f9e2  mov     rbp, rsp
0x18002f9e5  sub     rsp, 68h
0x18002f9e9  mov     rdi, rcx
0x18002f9ec  mov     dword ptr [rcx], 0
0x18002f9f2  lea     rax, [rbp+hKey]
0x18002f9f6  mov     [rbp+hKey], 0
0x18002f9fe  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18002fa05  mov     [rsp+68h+phkResult], rax; phkResult
0x18002fa0a  mov     r9d, 20019h; samDesired
0x18002fa10  lea     rdx, SubKey; "System\\CurrentControlSet\\Control\\Ter"...
0x18002fa17  xor     r8d, r8d; ulOptions
0x18002fa1a  call    cs:__imp_RegOpenKeyExW
0x18002fa21  nop     dword ptr [rax+rax+00h]
0x18002fa26  mov     ebx, eax
0x18002fa28  test    eax, eax
0x18002fa2a  jz      short loc_18002FA86
0x18002fa2c  mov     eax, cs:dword_1800DF020
0x18002fa32  cmp     eax, 2
0x18002fa35  jbe     short loc_18002FA70
0x18002fa37  lea     rax, aUnableToOpenTs_0; "Unable to open TS key in HKLM"
0x18002fa3e  mov     [rbp+arg_18], ebx
0x18002fa41  mov     [rbp+var_28], rax
0x18002fa45  lea     rdx, byte_1800CD3DF
0x18002fa4c  lea     rax, [rbp+arg_18]
0x18002fa50  xor     r9d, r9d
0x18002fa53  mov     [rsp+68h+lpcbData], rax
0x18002fa58  lea     rcx, dword_1800DF020
0x18002fa5f  lea     rax, [rbp+var_28]
0x18002fa63  xor     r8d, r8d
0x18002fa66  mov     [rsp+68h+phkResult], rax
0x18002fa6b  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18002fa70  test    ebx, ebx
0x18002fa72  jle     loc_18002FB7B
0x18002fa78  movzx   ebx, bx
0x18002fa7b  or      ebx, 80070000h
0x18002fa81  jmp     loc_18002FB7B
0x18002fa86  mov     rcx, [rbp+hKey]; hKey
0x18002fa8a  lea     rax, [rbp+cbData]
0x18002fa8e  mov     [rsp+68h+lpcbData], rax; lpcbData
0x18002fa93  lea     r15, aTsappcompat; "TSAppCompat"
0x18002fa9a  lea     rax, [rbp+Data]
0x18002fa9e  mov     [rbp+cbData], 4
0x18002faa5  xor     ebx, ebx
0x18002faa7  mov     [rsp+68h+phkResult], rax; lpData
0x18002faac  lea     r9, [rbp+Type]; lpType
0x18002fab0  mov     [rbp+Type], ebx
0x18002fab3  xor     r8d, r8d; lpReserved
0x18002fab6  mov     [rbp+Data], ebx
0x18002fab9  mov     rdx, r15; lpValueName
0x18002fabc  call    cs:__imp_RegQueryValueExW
0x18002fac3  nop     dword ptr [rax+rax+00h]
0x18002fac8  mov     ecx, eax
0x18002faca  test    eax, eax
0x18002facc  jnz     short loc_18002FB29
0x18002face  cmp     [rbp+cbData], 4
0x18002fad2  jnz     short loc_18002FB29
0x18002fad4  cmp     [rbp+Type], 4
0x18002fad8  jnz     short loc_18002FB29
0x18002fada  mov     eax, cs:dword_1800DF020
0x18002fae0  mov     ecx, [rbp+Data]
0x18002fae3  mov     [rdi], ecx
0x18002fae5  cmp     eax, 4
0x18002fae8  jbe     loc_18002FB7B
0x18002faee  lea     rax, aSuccessfullyRe; "Successfully read APPCOMPAT key"
0x18002faf5  mov     [rbp+arg_18], ecx
0x18002faf8  mov     [rbp+var_28], rax
0x18002fafc  lea     rdx, byte_1800CD407
0x18002fb03  lea     rax, [rbp+arg_18]
0x18002fb07  xor     r9d, r9d
0x18002fb0a  mov     [rsp+68h+lpcbData], rax
0x18002fb0f  lea     rcx, dword_1800DF020
0x18002fb16  lea     rax, [rbp+var_28]
0x18002fb1a  xor     r8d, r8d
0x18002fb1d  mov     [rsp+68h+phkResult], rax
0x18002fb22  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18002fb27  jmp     short loc_18002FB7B
0x18002fb29  mov     eax, cs:dword_1800DF020
0x18002fb2f  cmp     eax, 4
0x18002fb32  jbe     short loc_18002FB7B
0x18002fb34  mov     eax, [rdi]
0x18002fb36  lea     rdx, byte_1800CD433
0x18002fb3d  mov     [rbp+arg_18], eax
0x18002fb40  lea     rax, aUnableToReadAp; "Unable to read APPCOMPAT key"
0x18002fb47  mov     [rbp+var_10], rax
0x18002fb4b  lea     rax, [rbp+var_18]
0x18002fb4f  mov     [rsp+68h+var_30], rax
0x18002fb54  lea     rax, [rbp+arg_18]
0x18002fb58  mov     [rsp+68h+var_38], rax
0x18002fb5d  lea     rax, [rbp+var_28]
0x18002fb61  mov     [rsp+68h+lpcbData], rax
0x18002fb66  lea     rax, [rbp+var_10]
0x18002fb6a  mov     [rsp+68h+phkResult], rax
0x18002fb6f  mov     [rbp+var_18], r15
0x18002fb73  mov     dword ptr [rbp+var_28], ecx
0x18002fb76  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &)
0x18002fb7b  mov     rcx, [rbp+hKey]; hKey
0x18002fb7f  test    rcx, rcx
0x18002fb82  jz      short loc_18002FB90
0x18002fb84  call    cs:__imp_RegCloseKey
0x18002fb8b  nop     dword ptr [rax+rax+00h]
0x18002fb90  mov     eax, ebx
0x18002fb92  add     rsp, 68h
0x18002fb96  pop     r15
0x18002fb98  pop     rdi
0x18002fb99  pop     rbx
0x18002fb9a  pop     rbp
0x18002fb9b  retn
```
