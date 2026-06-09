# ReadRegistrySTRING(ushort *,ushort *,ushort *,ulong *)

- ea: `0x180005918`
- end: `0x180005c17`
- name: `?ReadRegistrySTRING@@YAJPEAG00PEAK@Z`
- size: `767`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int16 *, BYTE *, unsigned int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180004cbc`

## callees

- `0x18000160c`
- `0x180001724`
- `0x180005918`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180005a8d`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180005a8d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180005acb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180005acb`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180005a5d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180005a5d`

## string_xrefs

- `0x180005ba4`: `RegOpenKey failed!`
- `0x180005961`: `ReadRegistrySTRING`
- `0x1800059e1`: `ReadRegistrySTRING`
- `0x180005b1e`: `ReadRegistrySTRING`
- `0x180005bbd`: `ReadRegistrySTRING`

## pseudocode

```c
__int64 __fastcall ReadRegistrySTRING(unsigned __int16 *a1, unsigned __int16 *a2, BYTE *a3, unsigned int *a4)
{
  signed int v6; // ebx
  int *v7; // rdx
  const char **v8; // rax
  LSTATUS v9; // eax
  int v10; // ecx
  int v11; // r8d
  int v12; // r9d
  LSTATUS Value; // eax
  int v14; // ecx
  int v15; // r8d
  int v16; // r9d
  const char **v18; // [rsp+40h] [rbp-40h]
  const char *v19; // [rsp+50h] [rbp-30h] BYREF
  HKEY hKey; // [rsp+58h] [rbp-28h] BYREF
  const char *v21; // [rsp+60h] [rbp-20h] BYREF
  const char *v22; // [rsp+68h] [rbp-18h] BYREF
  const char *v23; // [rsp+70h] [rbp-10h] BYREF
  const char *v24; // [rsp+78h] [rbp-8h] BYREF
  unsigned __int16 *v25; // [rsp+A0h] [rbp+20h] BYREF
  unsigned __int16 *Type; // [rsp+A8h] [rbp+28h] BYREF

  Type = a2;
  v25 = a1;
  hKey = 0;
  if ( !a3 )
  {
    v6 = -2147467261;
    if ( (unsigned int)dword_180044008 <= 2 )
      goto LABEL_16;
    LODWORD(Type) = 255;
    v19 = "ReadRegistrySTRING";
    v7 = (int *)byte_180037A81;
    v21 = "clientcore\\termsrv\\rdsdwmdirect\\rdsdwmdr.cpp";
    v22 = "Unexpected NULL object";
    v18 = &v19;
    v8 = &v22;
    goto LABEL_4;
  }
  if ( a4 )
  {
    v9 = RegOpenKeyExW(
           HKEY_LOCAL_MACHINE,
           L"SYSTEM\\CurrentControlSet\\Control\\Terminal Server\\WinStations",
           0,
           0x20019u,
           &hKey);
    v6 = v9;
    if ( v9 )
    {
      if ( v9 > 0 )
        v6 = (unsigned __int16)v9 | 0x80070000;
      if ( v6 < 0 )
      {
        if ( (unsigned int)dword_180044008 > 2 )
        {
          LODWORD(Type) = 308;
          v24 = "RegOpenKey failed!";
          LODWORD(v25) = v6;
          v23 = "ReadRegistrySTRING";
          v22 = "clientcore\\termsrv\\rdsdwmdirect\\rdsdwmdr.cpp";
          v21 = "Error HResult failed";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
            v10,
            (unsigned int)word_1800379A2,
            v11,
            v12,
            (__int64)&v21,
            (__int64)&v25,
            (__int64)&v22,
            (__int64)&Type,
            (__int64)&v23,
            (__int64)&v24);
        }
        goto LABEL_16;
      }
LABEL_15:
      v6 = 0;
      goto LABEL_16;
    }
    LODWORD(Type) = 0;
    Value = RegQueryValueExW(hKey, L"DwmdirectDumpFrames", 0, (LPDWORD)&Type, a3, a4);
    v6 = Value;
    if ( Value )
    {
      if ( Value <= 0 )
        goto LABEL_21;
    }
    else if ( (_DWORD)Type == 1 )
    {
      if ( (*(_BYTE *)a4 & 1) == 0 && !*(_WORD *)&a3[2 * ((unsigned __int64)*a4 >> 1) - 2] )
        goto LABEL_15;
      LOWORD(v6) = 1610;
    }
    else
    {
      LOWORD(v6) = 1010;
    }
    v6 = (unsigned __int16)v6 | 0x80070000;
LABEL_21:
    if ( v6 < 0 )
    {
      if ( (unsigned int)dword_180044008 > 2 )
      {
        LODWORD(v25) = 302;
        v22 = "RegQueryValueExW failed!";
        LODWORD(v19) = v6;
        v21 = "ReadRegistrySTRING";
        v23 = "clientcore\\termsrv\\rdsdwmdirect\\rdsdwmdr.cpp";
        v24 = "Error HResult failed";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
          v14,
          (unsigned int)&byte_1800379EF,
          v15,
          v16,
          (__int64)&v24,
          (__int64)&v19,
          (__int64)&v23,
          (__int64)&v25,
          (__int64)&v21,
          (__int64)&v22);
      }
      goto LABEL_16;
    }
    goto LABEL_15;
  }
  v6 = -2147467261;
  if ( (unsigned int)dword_180044008 > 2 )
  {
    LODWORD(Type) = 256;
    v22 = "ReadRegistrySTRING";
    v7 = &dword_180037A3C;
    v21 = "clientcore\\termsrv\\rdsdwmdirect\\rdsdwmdr.cpp";
    v19 = "Unexpected NULL object";
    v18 = &v22;
    v8 = &v19;
LABEL_4:
    LODWORD(v25) = -2147467261;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
      -2147467261,
      (_DWORD)v7,
      (_DWORD)a3,
      (_DWORD)a4,
      (__int64)v8,
      (__int64)&v25,
      (__int64)&v21,
      (__int64)&Type,
      (__int64)v18);
  }
LABEL_16:
  if ( hKey )
    RegCloseKey(hKey);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180005918  mov     r11, rsp
0x18000591b  mov     [r11+18h], rbx
0x18000591f  mov     [r11+20h], rsi
0x180005923  mov     [r11+10h], rdx
0x180005927  mov     [r11+8], rcx
0x18000592b  push    rbp
0x18000592c  push    rdi
0x18000592d  push    r14
0x18000592f  mov     rbp, rsp
0x180005932  sub     rsp, 80h
0x180005939  xor     r14d, r14d
0x18000593c  mov     rdi, r9
0x18000593f  mov     [rbp+hKey], r14
0x180005943  mov     rsi, r8
0x180005946  test    r8, r8
0x180005949  jnz     short loc_1800059C6
0x18000594b  mov     eax, cs:dword_180044008
0x180005951  mov     ecx, 80004003h
0x180005956  mov     ebx, ecx
0x180005958  cmp     eax, 2
0x18000595b  jbe     loc_180005AC2
0x180005961  lea     rax, aReadregistryst; "ReadRegistrySTRING"
0x180005968  mov     dword ptr [rbp+Type], 0FFh
0x18000596f  mov     [rbp+var_30], rax
0x180005973  lea     rdx, byte_180037A81
0x18000597a  lea     rax, aClientcoreTerm_1; "clientcore\\termsrv\\rdsdwmdirect\\rdsd"...
0x180005981  mov     [rbp+var_20], rax
0x180005985  lea     rax, aUnexpectedNull; "Unexpected NULL object"
0x18000598c  mov     [rbp+var_18], rax
0x180005990  lea     rax, [rbp+var_30]
0x180005994  mov     [r11-58h], rax
0x180005998  lea     rax, [rbp+Type]
0x18000599c  mov     [r11-60h], rax
0x1800059a0  lea     rax, [rbp+var_20]
0x1800059a4  mov     [r11-68h], rax
0x1800059a8  lea     rax, [rbp+arg_0]
0x1800059ac  mov     [r11-70h], rax
0x1800059b0  lea     rax, [rbp+var_18]
0x1800059b4  mov     [rsp+80h+phkResult], rax
0x1800059b9  mov     dword ptr [rbp+arg_0], ecx
0x1800059bc  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x1800059c1  jmp     loc_180005AC2
0x1800059c6  test    rdi, rdi
0x1800059c9  jnz     short loc_180005A3D
0x1800059cb  mov     eax, cs:dword_180044008
0x1800059d1  mov     ecx, 80004003h
0x1800059d6  mov     ebx, ecx
0x1800059d8  cmp     eax, 2
0x1800059db  jbe     loc_180005AC2
0x1800059e1  lea     rax, aReadregistryst; "ReadRegistrySTRING"
0x1800059e8  mov     dword ptr [rbp+Type], 100h
0x1800059ef  mov     [rbp+var_18], rax
0x1800059f3  lea     rdx, dword_180037A3C
0x1800059fa  lea     rax, aClientcoreTerm_1; "clientcore\\termsrv\\rdsdwmdirect\\rdsd"...
0x180005a01  mov     [rbp+var_20], rax
0x180005a05  lea     rax, aUnexpectedNull; "Unexpected NULL object"
0x180005a0c  mov     [rbp+var_30], rax
0x180005a10  lea     rax, [rbp+var_18]
0x180005a14  mov     [rsp+80h+var_40], rax
0x180005a19  lea     rax, [rbp+Type]
0x180005a1d  mov     [rsp+80h+var_48], rax
0x180005a22  lea     rax, [rbp+var_20]
0x180005a26  mov     [rsp+80h+var_50], rax
0x180005a2b  lea     rax, [rbp+arg_0]
0x180005a2f  mov     [rsp+80h+lpcbData], rax
0x180005a34  lea     rax, [rbp+var_30]
0x180005a38  jmp     loc_1800059B4
0x180005a3d  lea     rax, [rbp+hKey]
0x180005a41  mov     r9d, 20019h; samDesired
0x180005a47  xor     r8d, r8d; ulOptions
0x180005a4a  mov     [rsp+80h+phkResult], rax; phkResult
0x180005a4f  lea     rdx, SubKey; "SYSTEM\\CurrentControlSet\\Control\\Ter"...
0x180005a56  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180005a5d  call    cs:__imp_RegOpenKeyExW
0x180005a63  mov     ebx, eax
0x180005a65  test    eax, eax
0x180005a67  jnz     loc_180005B82
0x180005a6d  mov     rcx, [rbp+hKey]; hKey
0x180005a71  lea     r9, [rbp+Type]; lpType
0x180005a75  mov     [rsp+80h+lpcbData], rdi; lpcbData
0x180005a7a  lea     rdx, ValueName; "DwmdirectDumpFrames"
0x180005a81  xor     r8d, r8d; lpReserved
0x180005a84  mov     [rsp+80h+phkResult], rsi; lpData
0x180005a89  mov     dword ptr [rbp+Type], r14d
0x180005a8d  call    cs:__imp_RegQueryValueExW
0x180005a93  mov     ebx, eax
0x180005a95  test    eax, eax
0x180005a97  jnz     short loc_180005AEB
0x180005a99  cmp     dword ptr [rbp+Type], 1
0x180005a9d  jz      short loc_180005AA6
0x180005a9f  mov     ebx, 3F2h
0x180005aa4  jmp     short loc_180005AED
0x180005aa6  test    byte ptr [rdi], 1
0x180005aa9  jz      short loc_180005AB2
0x180005aab  mov     ebx, 64Ah
0x180005ab0  jmp     short loc_180005AED
0x180005ab2  mov     eax, [rdi]
0x180005ab4  shr     rax, 1
0x180005ab7  cmp     [rsi+rax*2-2], r14w
0x180005abd  jnz     short loc_180005AAB
0x180005abf  mov     ebx, r14d
0x180005ac2  mov     rcx, [rbp+hKey]; hKey
0x180005ac6  test    rcx, rcx
0x180005ac9  jz      short loc_180005AD1
0x180005acb  call    cs:__imp_RegCloseKey
0x180005ad1  lea     r11, [rsp+80h+var_s0]
0x180005ad9  mov     eax, ebx
0x180005adb  mov     rbx, [r11+30h]
0x180005adf  mov     rsi, [r11+38h]
0x180005ae3  mov     rsp, r11
0x180005ae6  pop     r14
0x180005ae8  pop     rdi
0x180005ae9  pop     rbp
0x180005aea  retn
0x180005aeb  jle     short loc_180005AF6
0x180005aed  movzx   ebx, bx
0x180005af0  or      ebx, 80070000h
0x180005af6  test    ebx, ebx
0x180005af8  jns     short loc_180005ABF
0x180005afa  mov     eax, cs:dword_180044008
0x180005b00  cmp     eax, 2
0x180005b03  jbe     short loc_180005AC2
0x180005b05  lea     rax, aRegqueryvaluee; "RegQueryValueExW failed!"
0x180005b0c  mov     dword ptr [rbp+arg_0], 12Eh
0x180005b13  mov     [rbp+var_18], rax
0x180005b17  lea     rdx, byte_1800379EF
0x180005b1e  lea     rax, aReadregistryst; "ReadRegistrySTRING"
0x180005b25  mov     dword ptr [rbp+var_30], ebx
0x180005b28  mov     [rbp+var_20], rax
0x180005b2c  lea     rax, aClientcoreTerm_1; "clientcore\\termsrv\\rdsdwmdirect\\rdsd"...
0x180005b33  mov     [rbp+var_10], rax
0x180005b37  lea     rax, aErrorHresultFa; "Error HResult failed"
0x180005b3e  mov     [rbp+var_8], rax
0x180005b42  lea     rax, [rbp+var_18]
0x180005b46  mov     [rsp+80h+var_38], rax
0x180005b4b  lea     rax, [rbp+var_20]
0x180005b4f  mov     [rsp+80h+var_40], rax
0x180005b54  lea     rax, [rbp+arg_0]
0x180005b58  mov     [rsp+80h+var_48], rax
0x180005b5d  lea     rax, [rbp+var_10]
0x180005b61  mov     [rsp+80h+var_50], rax
0x180005b66  lea     rax, [rbp+var_30]
0x180005b6a  mov     [rsp+80h+lpcbData], rax
0x180005b6f  lea     rax, [rbp+var_8]
0x180005b73  mov     [rsp+80h+phkResult], rax
0x180005b78  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3433@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x180005b7d  jmp     loc_180005AC2
0x180005b82  jle     short loc_180005B8D
0x180005b84  movzx   ebx, ax
0x180005b87  or      ebx, 80070000h
0x180005b8d  test    ebx, ebx
0x180005b8f  jns     loc_180005ABF
0x180005b95  mov     eax, cs:dword_180044008
0x180005b9b  cmp     eax, 2
0x180005b9e  jbe     loc_180005AC2
0x180005ba4  lea     rax, aRegopenkeyFail; "RegOpenKey failed!"
0x180005bab  mov     dword ptr [rbp+Type], 134h
0x180005bb2  mov     [rbp+var_8], rax
0x180005bb6  lea     rdx, word_1800379A2
0x180005bbd  lea     rax, aReadregistryst; "ReadRegistrySTRING"
0x180005bc4  mov     dword ptr [rbp+arg_0], ebx
0x180005bc7  mov     [rbp+var_10], rax
0x180005bcb  lea     rax, aClientcoreTerm_1; "clientcore\\termsrv\\rdsdwmdirect\\rdsd"...
0x180005bd2  mov     [rbp+var_18], rax
0x180005bd6  lea     rax, aErrorHresultFa; "Error HResult failed"
0x180005bdd  mov     [rbp+var_20], rax
0x180005be1  lea     rax, [rbp+var_8]
0x180005be5  mov     [rsp+80h+var_38], rax
0x180005bea  lea     rax, [rbp+var_10]
0x180005bee  mov     [rsp+80h+var_40], rax
0x180005bf3  lea     rax, [rbp+Type]
0x180005bf7  mov     [rsp+80h+var_48], rax
0x180005bfc  lea     rax, [rbp+var_18]
0x180005c00  mov     [rsp+80h+var_50], rax
0x180005c05  lea     rax, [rbp+arg_0]
0x180005c09  mov     [rsp+80h+lpcbData], rax
0x180005c0e  lea     rax, [rbp+var_20]
0x180005c12  jmp     loc_180005B73
```
