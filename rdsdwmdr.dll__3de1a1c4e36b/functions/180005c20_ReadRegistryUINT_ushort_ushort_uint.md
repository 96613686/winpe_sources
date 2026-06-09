# ReadRegistryUINT(ushort *,ushort *,uint *)

- ea: `0x180005c20`
- end: `0x180005e5a`
- name: `?ReadRegistryUINT@@YAJPEAG0PEAI@Z`
- size: `570`
- prototype: `__int64 __fastcall(LPCWSTR lpSubKey, LPCWSTR lpValueName, unsigned int *, int)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180004cbc`
- `0x18000e738`

## callees

- `0x18000160c`
- `0x180001724`
- `0x180005c20`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180005d8e`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180005d8e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180005da8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180005da8`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180005d55`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180005d55`

## string_xrefs

- `0x180005c5d`: `ReadRegistryUINT`
- `0x180005cdd`: `ReadRegistryUINT`
- `0x180005df6`: `ReadRegistryUINT`
- `0x180005ddd`: `RegOpenKey failed!`

## pseudocode

```c
__int64 __fastcall ReadRegistryUINT(LPCWSTR lpSubKey, LPCWSTR lpValueName, unsigned int *a3, int a4)
{
  signed int v6; // ebx
  __int64 *v7; // rdx
  DWORD *v8; // rax
  LSTATUS v9; // eax
  int v10; // ecx
  int v11; // r8d
  int v12; // r9d
  DWORD *v14; // [rsp+40h] [rbp-40h]
  DWORD Type[2]; // [rsp+50h] [rbp-30h] BYREF
  HKEY hKey; // [rsp+58h] [rbp-28h] BYREF
  const char *v17; // [rsp+60h] [rbp-20h] BYREF
  const char *v18; // [rsp+68h] [rbp-18h] BYREF
  const char *v19; // [rsp+70h] [rbp-10h] BYREF
  unsigned int Data; // [rsp+A8h] [rbp+28h] BYREF
  DWORD cbData; // [rsp+B8h] [rbp+38h] BYREF

  hKey = 0;
  if ( !lpValueName )
  {
    v6 = -2147467261;
    if ( (unsigned int)dword_180044008 <= 2 )
      goto LABEL_12;
    Data = 193;
    *(_QWORD *)Type = "ReadRegistryUINT";
    v7 = qword_180037B58;
    v17 = "clientcore\\termsrv\\rdsdwmdirect\\rdsdwmdr.cpp";
    v18 = "Unexpected NULL object";
    v14 = Type;
    v8 = (DWORD *)&v18;
    goto LABEL_4;
  }
  if ( a3 )
  {
    v9 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, lpSubKey, 0, 0x20019u, &hKey);
    v6 = v9;
    if ( v9 )
    {
      if ( v9 > 0 )
        v6 = (unsigned __int16)v9 | 0x80070000;
      if ( v6 < 0 )
      {
        if ( (unsigned int)dword_180044008 > 2 )
        {
          Data = 227;
          v18 = "RegOpenKey failed!";
          cbData = v6;
          v17 = "ReadRegistryUINT";
          *(_QWORD *)Type = "clientcore\\termsrv\\rdsdwmdirect\\rdsdwmdr.cpp";
          v19 = "Error HResult failed";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
            v10,
            (unsigned int)&word_180037AC6,
            v11,
            v12,
            (__int64)&v19,
            (__int64)&cbData,
            (__int64)Type,
            (__int64)&Data,
            (__int64)&v17,
            (__int64)&v18);
        }
        goto LABEL_12;
      }
    }
    else
    {
      Data = 0;
      Type[0] = 0;
      cbData = 4;
      if ( !RegQueryValueExW(hKey, lpValueName, 0, Type, (LPBYTE)&Data, &cbData) )
        *a3 = Data;
    }
    v6 = 0;
    goto LABEL_12;
  }
  v6 = -2147467261;
  if ( (unsigned int)dword_180044008 > 2 )
  {
    Data = 194;
    v18 = "ReadRegistryUINT";
    v7 = (__int64 *)byte_180037B13;
    v17 = "clientcore\\termsrv\\rdsdwmdirect\\rdsdwmdr.cpp";
    *(_QWORD *)Type = "Unexpected NULL object";
    v14 = (DWORD *)&v18;
    v8 = Type;
LABEL_4:
    cbData = -2147467261;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
      -2147467261,
      (_DWORD)v7,
      (_DWORD)a3,
      a4,
      (__int64)v8,
      (__int64)&cbData,
      (__int64)&v17,
      (__int64)&Data,
      (__int64)v14);
  }
LABEL_12:
  if ( hKey )
    RegCloseKey(hKey);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180005c20  mov     r11, rsp
0x180005c23  mov     [r11+8], rbx
0x180005c27  push    rbp
0x180005c28  push    rsi
0x180005c29  push    rdi
0x180005c2a  mov     rbp, rsp
0x180005c2d  sub     rsp, 80h
0x180005c34  mov     [rbp+hKey], 0
0x180005c3c  mov     rdi, r8
0x180005c3f  mov     rsi, rdx
0x180005c42  test    rdx, rdx
0x180005c45  jnz     short loc_180005CC2
0x180005c47  mov     eax, cs:dword_180044008
0x180005c4d  mov     ecx, 80004003h
0x180005c52  mov     ebx, ecx
0x180005c54  cmp     eax, 2
0x180005c57  jbe     loc_180005D9F
0x180005c5d  lea     rax, aReadregistryui; "ReadRegistryUINT"
0x180005c64  mov     [rbp+Data], 0C1h
0x180005c6b  mov     qword ptr [rbp+Type], rax
0x180005c6f  lea     rdx, qword_180037B58
0x180005c76  lea     rax, aClientcoreTerm_1; "clientcore\\termsrv\\rdsdwmdirect\\rdsd"...
0x180005c7d  mov     [rbp+var_20], rax
0x180005c81  lea     rax, aUnexpectedNull; "Unexpected NULL object"
0x180005c88  mov     [rbp+var_18], rax
0x180005c8c  lea     rax, [rbp+Type]
0x180005c90  mov     [r11-58h], rax
0x180005c94  lea     rax, [rbp+Data]
0x180005c98  mov     [r11-60h], rax
0x180005c9c  lea     rax, [rbp+var_20]
0x180005ca0  mov     [r11-68h], rax
0x180005ca4  lea     rax, [rbp+cbData]
0x180005ca8  mov     [r11-70h], rax
0x180005cac  lea     rax, [rbp+var_18]
0x180005cb0  mov     [rsp+80h+phkResult], rax
0x180005cb5  mov     [rbp+cbData], ecx
0x180005cb8  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x180005cbd  jmp     loc_180005D9F
0x180005cc2  test    rdi, rdi
0x180005cc5  jnz     short loc_180005D39
0x180005cc7  mov     eax, cs:dword_180044008
0x180005ccd  mov     ecx, 80004003h
0x180005cd2  mov     ebx, ecx
0x180005cd4  cmp     eax, 2
0x180005cd7  jbe     loc_180005D9F
0x180005cdd  lea     rax, aReadregistryui; "ReadRegistryUINT"
0x180005ce4  mov     [rbp+Data], 0C2h
0x180005ceb  mov     [rbp+var_18], rax
0x180005cef  lea     rdx, byte_180037B13
0x180005cf6  lea     rax, aClientcoreTerm_1; "clientcore\\termsrv\\rdsdwmdirect\\rdsd"...
0x180005cfd  mov     [rbp+var_20], rax
0x180005d01  lea     rax, aUnexpectedNull; "Unexpected NULL object"
0x180005d08  mov     qword ptr [rbp+Type], rax
0x180005d0c  lea     rax, [rbp+var_18]
0x180005d10  mov     [rsp+80h+var_40], rax
0x180005d15  lea     rax, [rbp+Data]
0x180005d19  mov     [rsp+80h+var_48], rax
0x180005d1e  lea     rax, [rbp+var_20]
0x180005d22  mov     [rsp+80h+var_50], rax
0x180005d27  lea     rax, [rbp+cbData]
0x180005d2b  mov     [rsp+80h+lpcbData], rax
0x180005d30  lea     rax, [rbp+Type]
0x180005d34  jmp     loc_180005CB0
0x180005d39  lea     rax, [rbp+hKey]
0x180005d3d  mov     rdx, rcx; lpSubKey
0x180005d40  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180005d47  mov     [rsp+80h+phkResult], rax; phkResult
0x180005d4c  mov     r9d, 20019h; samDesired
0x180005d52  xor     r8d, r8d; ulOptions
0x180005d55  call    cs:__imp_RegOpenKeyExW
0x180005d5b  mov     ebx, eax
0x180005d5d  test    eax, eax
0x180005d5f  jnz     short loc_180005DC3
0x180005d61  mov     rcx, [rbp+hKey]; hKey
0x180005d65  lea     r9, [rbp+Type]; lpType
0x180005d69  mov     [rbp+Data], eax
0x180005d6c  xor     r8d, r8d; lpReserved
0x180005d6f  mov     [rbp+Type], eax
0x180005d72  mov     rdx, rsi; lpValueName
0x180005d75  lea     rax, [rbp+cbData]
0x180005d79  mov     [rbp+cbData], 4
0x180005d80  mov     [rsp+80h+lpcbData], rax; lpcbData
0x180005d85  lea     rax, [rbp+Data]
0x180005d89  mov     [rsp+80h+phkResult], rax; lpData
0x180005d8e  call    cs:__imp_RegQueryValueExW
0x180005d94  test    eax, eax
0x180005d96  jnz     short loc_180005D9D
0x180005d98  mov     eax, [rbp+Data]
0x180005d9b  mov     [rdi], eax
0x180005d9d  xor     ebx, ebx
0x180005d9f  mov     rcx, [rbp+hKey]; hKey
0x180005da3  test    rcx, rcx
0x180005da6  jz      short loc_180005DAE
0x180005da8  call    cs:__imp_RegCloseKey
0x180005dae  mov     eax, ebx
0x180005db0  mov     rbx, [rsp+80h+arg_0]
0x180005db8  add     rsp, 80h
0x180005dbf  pop     rdi
0x180005dc0  pop     rsi
0x180005dc1  pop     rbp
0x180005dc2  retn
0x180005dc3  jle     short loc_180005DCE
0x180005dc5  movzx   ebx, ax
0x180005dc8  or      ebx, 80070000h
0x180005dce  test    ebx, ebx
0x180005dd0  jns     short loc_180005D9D
0x180005dd2  mov     eax, cs:dword_180044008
0x180005dd8  cmp     eax, 2
0x180005ddb  jbe     short loc_180005D9F
0x180005ddd  lea     rax, aRegopenkeyFail; "RegOpenKey failed!"
0x180005de4  mov     [rbp+Data], 0E3h
0x180005deb  mov     [rbp+var_18], rax
0x180005def  lea     rdx, word_180037AC6
0x180005df6  lea     rax, aReadregistryui; "ReadRegistryUINT"
0x180005dfd  mov     [rbp+cbData], ebx
0x180005e00  mov     [rbp+var_20], rax
0x180005e04  lea     rax, aClientcoreTerm_1; "clientcore\\termsrv\\rdsdwmdirect\\rdsd"...
0x180005e0b  mov     qword ptr [rbp+Type], rax
0x180005e0f  lea     rax, aErrorHresultFa; "Error HResult failed"
0x180005e16  mov     [rbp+var_10], rax
0x180005e1a  lea     rax, [rbp+var_18]
0x180005e1e  mov     [rsp+80h+var_38], rax
0x180005e23  lea     rax, [rbp+var_20]
0x180005e27  mov     [rsp+80h+var_40], rax
0x180005e2c  lea     rax, [rbp+Data]
0x180005e30  mov     [rsp+80h+var_48], rax
0x180005e35  lea     rax, [rbp+Type]
0x180005e39  mov     [rsp+80h+var_50], rax
0x180005e3e  lea     rax, [rbp+cbData]
0x180005e42  mov     [rsp+80h+lpcbData], rax
0x180005e47  lea     rax, [rbp+var_10]
0x180005e4b  mov     [rsp+80h+phkResult], rax
0x180005e50  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3433@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x180005e55  jmp     loc_180005D9F
```
