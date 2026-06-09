# CTSSecurityDescriptor::GetSDValueFromRegistry(ushort const *,ushort const *,uchar * *,ulong *)

- ea: `0x18003dfdc`
- end: `0x18003e33b`
- name: `?GetSDValueFromRegistry@CTSSecurityDescriptor@@IEAAJPEBG0PEAPEAEPEAK@Z`
- size: `863`
- prototype: `int(CTSSecurityDescriptor *__hidden this, const unsigned __int16 *, const unsigned __int16 *, unsigned __int8 **, unsigned int *)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800198c4`

## callees

- `0x180001008`
- `0x180001120`
- `0x1800014cc`
- `0x18000345c`
- `0x180004234`
- `0x18003dfdc`
- `0x18004b86c`
- `0x18004bd84`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003e045`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003e045`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18003e0cd`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18003e195`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18003e0cd`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18003e195`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003e30a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003e30a`

## string_xrefs

- `0x18003e1c1`: `GetSDValueFromRegistry`
- `0x18003e2a0`: `GetSDValueFromRegistry`
- `0x18003e0f5`: `Registry entry not found`
- `0x18003e06d`: `Failed to open key`
- `0x18003e24f`: `Invalid security descriptor in registry`

## pseudocode

```c
__int64 __fastcall CTSSecurityDescriptor::GetSDValueFromRegistry(
        CTSSecurityDescriptor *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        unsigned __int8 **a4,
        unsigned int *a5)
{
  BYTE *v5; // rdi
  unsigned int *v9; // rsi
  LSTATUS v10; // eax
  int v11; // ecx
  int v12; // r8d
  int v13; // r9d
  signed int v14; // ebx
  LSTATUS v15; // eax
  int v16; // ecx
  int v17; // r8d
  int v18; // r9d
  LSTATUS v19; // eax
  int v20; // ecx
  int v21; // r8d
  int v22; // r9d
  unsigned int v23; // eax
  int v25; // [rsp+58h] [rbp-11h] BYREF
  HKEY hKey; // [rsp+60h] [rbp-9h] BYREF
  const unsigned __int16 *v27; // [rsp+68h] [rbp-1h] BYREF
  const char *v28; // [rsp+70h] [rbp+7h] BYREF
  const char *v29; // [rsp+78h] [rbp+Fh] BYREF
  const char *v30; // [rsp+80h] [rbp+17h] BYREF
  _QWORD v31[2]; // [rsp+88h] [rbp+1Fh] BYREF
  CTSSecurityDescriptor *cbData; // [rsp+C8h] [rbp+5Fh] BYREF
  DWORD Type; // [rsp+E0h] [rbp+77h] BYREF

  cbData = this;
  v5 = 0;
  hKey = 0;
  if ( a4 && (v9 = a5) != 0 )
  {
    *a4 = 0;
    *v9 = 0;
    v10 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, a2, 0, 0x20019u, &hKey);
    v14 = v10;
    if ( v10 > 0 )
      v14 = (unsigned __int16)v10 | 0x80070000;
    if ( v14 >= 0 )
    {
      Type = 0;
      LODWORD(cbData) = 0;
      v15 = RegQueryValueExW(hKey, a3, 0, &Type, 0, (LPDWORD)&cbData);
      v14 = v15;
      if ( v15 > 0 )
        v14 = (unsigned __int16)v15 | 0x80070000;
      if ( v14 >= 0 )
      {
        if ( Type == 3 && (v16 = (int)cbData, (unsigned int)((_DWORD)cbData - 40) <= 0xFFD7) )
        {
          v5 = (BYTE *)operator new((unsigned int)cbData, (const struct std::nothrow_t *)&std::nothrow);
          if ( v5 )
          {
            v19 = RegQueryValueExW(hKey, a3, 0, &Type, v5, (LPDWORD)&cbData);
            v14 = v19;
            if ( v19 > 0 )
              v14 = (unsigned __int16)v19 | 0x80070000;
            if ( v14 >= 0 )
            {
              v23 = (unsigned int)cbData;
              *a4 = v5;
              v5 = 0;
              *v9 = v23;
            }
            else if ( (unsigned int)dword_1800DA020 > 3 )
            {
              v29 = (const char *)a3;
              v27 = (const unsigned __int16 *)"GetSDValueFromRegistry";
              v28 = (const char *)a2;
              v30 = "RegQueryValueEx failed after we queried it the 2nd time";
              v31[0] = "Warning HResult failed";
              v25 = v14;
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
                v20,
                (unsigned int)&byte_1800CAB4F,
                v21,
                v22,
                (__int64)v31,
                (__int64)&v30,
                (__int64)&v25,
                (__int64)&v27,
                (__int64)&v28,
                (__int64)&v29);
            }
          }
          else
          {
            v14 = -2147024882;
          }
        }
        else
        {
          if ( (unsigned int)dword_1800DA020 > 2 )
          {
            v31[0] = a3;
            v29 = "Invalid security descriptor in registry";
            v30 = (const char *)a2;
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
              v16,
              (unsigned int)&word_1800CA8DE,
              v17,
              v18,
              (__int64)&v29,
              (__int64)&v30,
              (__int64)v31);
          }
          v14 = -2147023558;
        }
      }
      else if ( (unsigned int)dword_1800DA020 > 5 )
      {
        v25 = v14;
        v29 = "Registry entry not found";
        v28 = (const char *)a2;
        v27 = a3;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
          v16,
          (unsigned int)word_1800CAAEA,
          v17,
          v18,
          (__int64)&v29,
          (__int64)&v27,
          (__int64)&v28,
          (__int64)&v25);
      }
    }
    else if ( (unsigned int)dword_1800DA020 > 3 )
    {
      v25 = v14;
      v28 = "Failed to open key";
      v27 = a2;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
        v11,
        (unsigned int)byte_1800CA881,
        v12,
        v13,
        (__int64)&v28,
        (__int64)&v27,
        (__int64)&v25);
    }
  }
  else
  {
    v14 = -2147024809;
    if ( (unsigned int)dword_1800DA020 > 3 )
    {
      v25 = -2147024809;
      v31[0] = "GetSDValueFromRegistry";
      v30 = "Invalid parameters";
      v29 = "Warning HResult failed";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        (unsigned int)&dword_1800DA020,
        (unsigned int)&unk_1800CA980,
        0,
        0,
        (__int64)&v29,
        (__int64)&v30,
        (__int64)&v25,
        (__int64)v31);
    }
  }
  if ( hKey )
    RegCloseKey(hKey);
  if ( v5 )
    operator delete(v5);
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x18003dfdc  mov     rax, rsp
0x18003dfdf  mov     [rax+10h], rbx
0x18003dfe3  mov     [rax+18h], rsi
0x18003dfe7  mov     [rax+8], rcx
0x18003dfeb  push    rbp
0x18003dfec  push    rdi
0x18003dfed  push    r12
0x18003dfef  push    r14
0x18003dff1  push    r15
0x18003dff3  lea     rbp, [rax-57h]
0x18003dff7  sub     rsp, 90h
0x18003dffe  xor     edi, edi
0x18003e000  mov     [rbp+4Fh+hKey], 0
0x18003e008  mov     r12, r9
0x18003e00b  mov     r15, r8
0x18003e00e  mov     r14, rdx
0x18003e011  test    r9, r9
0x18003e014  jz      loc_18003E290
0x18003e01a  mov     rsi, [rbp+4Fh+arg_20]
0x18003e01e  test    rsi, rsi
0x18003e021  jz      loc_18003E290
0x18003e027  mov     [r9], rdi
0x18003e02a  lea     rax, [rbp+4Fh+hKey]
0x18003e02e  mov     r9d, 20019h; samDesired
0x18003e034  mov     [rsp+0B0h+phkResult], rax; phkResult
0x18003e039  xor     r8d, r8d; ulOptions
0x18003e03c  mov     [rsi], edi
0x18003e03e  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18003e045  call    cs:__imp_RegOpenKeyExW
0x18003e04b  mov     ebx, eax
0x18003e04d  test    eax, eax
0x18003e04f  jle     short loc_18003E05A
0x18003e051  movzx   ebx, ax
0x18003e054  or      ebx, 80070000h
0x18003e05a  test    ebx, ebx
0x18003e05c  jns     short loc_18003E0AB
0x18003e05e  mov     eax, cs:dword_1800DA020
0x18003e064  cmp     eax, 3
0x18003e067  jbe     loc_18003E301
0x18003e06d  lea     rax, aFailedToOpenKe; "Failed to open key"
0x18003e074  mov     [rbp+4Fh+var_60], ebx
0x18003e077  mov     [rbp+4Fh+var_48], rax
0x18003e07b  lea     rdx, byte_1800CA881
0x18003e082  lea     rax, [rbp+4Fh+var_60]
0x18003e086  mov     [rbp+4Fh+var_50], r14
0x18003e08a  mov     [rsp+0B0h+var_80], rax
0x18003e08f  lea     rax, [rbp+4Fh+var_50]
0x18003e093  mov     [rsp+0B0h+lpcbData], rax
0x18003e098  lea     rax, [rbp+4Fh+var_48]
0x18003e09c  mov     [rsp+0B0h+phkResult], rax
0x18003e0a1  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x18003e0a6  jmp     loc_18003E301
0x18003e0ab  mov     rcx, [rbp+4Fh+hKey]; hKey
0x18003e0af  lea     rax, [rbp+4Fh+cbData]
0x18003e0b3  mov     [rsp+0B0h+lpcbData], rax; lpcbData
0x18003e0b8  lea     r9, [rbp+4Fh+Type]; lpType
0x18003e0bc  xor     r8d, r8d; lpReserved
0x18003e0bf  mov     [rsp+0B0h+phkResult], rdi; lpData
0x18003e0c4  mov     rdx, r15; lpValueName
0x18003e0c7  mov     [rbp+4Fh+Type], edi
0x18003e0ca  mov     dword ptr [rbp+4Fh+cbData], edi
0x18003e0cd  call    cs:__imp_RegQueryValueExW
0x18003e0d3  mov     ebx, eax
0x18003e0d5  test    eax, eax
0x18003e0d7  jle     short loc_18003E0E2
0x18003e0d9  movzx   ebx, ax
0x18003e0dc  or      ebx, 80070000h
0x18003e0e2  test    ebx, ebx
0x18003e0e4  jns     short loc_18003E140
0x18003e0e6  mov     eax, cs:dword_1800DA020
0x18003e0ec  cmp     eax, 5
0x18003e0ef  jbe     loc_18003E301
0x18003e0f5  lea     rax, aRegistryEntryN; "Registry entry not found"
0x18003e0fc  mov     [rbp+4Fh+var_60], ebx
0x18003e0ff  mov     [rbp+4Fh+var_40], rax
0x18003e103  lea     rdx, word_1800CAAEA
0x18003e10a  lea     rax, [rbp+4Fh+var_60]
0x18003e10e  mov     [rbp+4Fh+var_48], r14
0x18003e112  mov     [rsp+0B0h+var_78], rax
0x18003e117  lea     rax, [rbp+4Fh+var_48]
0x18003e11b  mov     [rsp+0B0h+var_80], rax
0x18003e120  lea     rax, [rbp+4Fh+var_50]
0x18003e124  mov     [rsp+0B0h+lpcbData], rax
0x18003e129  lea     rax, [rbp+4Fh+var_40]
0x18003e12d  mov     [rsp+0B0h+phkResult], rax
0x18003e132  mov     [rbp+4Fh+var_50], r15
0x18003e136  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapSz@G@@U2@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapSz@G@@4AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x18003e13b  jmp     loc_18003E301
0x18003e140  cmp     [rbp+4Fh+Type], 3
0x18003e144  jnz     loc_18003E244
0x18003e14a  mov     ecx, dword ptr [rbp+4Fh+cbData]; unsigned __int64
0x18003e14d  lea     eax, [rcx-28h]
0x18003e150  cmp     eax, 0FFD7h
0x18003e155  ja      loc_18003E244
0x18003e15b  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18003e162  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18003e167  mov     rdi, rax
0x18003e16a  test    rax, rax
0x18003e16d  jnz     short loc_18003E179
0x18003e16f  mov     ebx, 8007000Eh
0x18003e174  jmp     loc_18003E301
0x18003e179  mov     rcx, [rbp+4Fh+hKey]; hKey
0x18003e17d  lea     rax, [rbp+4Fh+cbData]
0x18003e181  mov     [rsp+0B0h+lpcbData], rax; lpcbData
0x18003e186  lea     r9, [rbp+4Fh+Type]; lpType
0x18003e18a  xor     r8d, r8d; lpReserved
0x18003e18d  mov     [rsp+0B0h+phkResult], rdi; lpData
0x18003e192  mov     rdx, r15; lpValueName
0x18003e195  call    cs:__imp_RegQueryValueExW
0x18003e19b  mov     ebx, eax
0x18003e19d  test    eax, eax
0x18003e19f  jle     short loc_18003E1AA
0x18003e1a1  movzx   ebx, ax
0x18003e1a4  or      ebx, 80070000h
0x18003e1aa  test    ebx, ebx
0x18003e1ac  jns     loc_18003E234
0x18003e1b2  mov     eax, cs:dword_1800DA020
0x18003e1b8  cmp     eax, 3
0x18003e1bb  jbe     loc_18003E301
0x18003e1c1  lea     rax, aGetsdvaluefrom; "GetSDValueFromRegistry"
0x18003e1c8  mov     [rbp+4Fh+var_40], r15
0x18003e1cc  mov     [rbp+4Fh+var_50], rax
0x18003e1d0  lea     rdx, byte_1800CAB4F
0x18003e1d7  lea     rax, aRegqueryvaluee; "RegQueryValueEx failed after we queried"...
0x18003e1de  mov     [rbp+4Fh+var_48], r14
0x18003e1e2  mov     [rbp+4Fh+var_38], rax
0x18003e1e6  lea     rax, aWarningHresult; "Warning HResult failed"
0x18003e1ed  mov     [rbp+4Fh+var_30], rax
0x18003e1f1  lea     rax, [rbp+4Fh+var_40]
0x18003e1f5  mov     [rsp+0B0h+var_68], rax
0x18003e1fa  lea     rax, [rbp+4Fh+var_48]
0x18003e1fe  mov     [rsp+0B0h+var_70], rax
0x18003e203  lea     rax, [rbp+4Fh+var_50]
0x18003e207  mov     [rsp+0B0h+var_78], rax
0x18003e20c  lea     rax, [rbp+4Fh+var_60]
0x18003e210  mov     [rsp+0B0h+var_80], rax
0x18003e215  lea     rax, [rbp+4Fh+var_38]
0x18003e219  mov     [rsp+0B0h+lpcbData], rax
0x18003e21e  lea     rax, [rbp+4Fh+var_30]
0x18003e222  mov     [rsp+0B0h+phkResult], rax
0x18003e227  mov     [rbp+4Fh+var_60], ebx
0x18003e22a  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@U1@U?$_tlgWrapSz@G@@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@3AEBU?$_tlgWrapSz@G@@5@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x18003e22f  jmp     loc_18003E301
0x18003e234  mov     eax, dword ptr [rbp+4Fh+cbData]
0x18003e237  mov     [r12], rdi
0x18003e23b  xor     edi, edi
0x18003e23d  mov     [rsi], eax
0x18003e23f  jmp     loc_18003E301
0x18003e244  mov     eax, cs:dword_1800DA020
0x18003e24a  cmp     eax, 2
0x18003e24d  jbe     short loc_18003E289
0x18003e24f  lea     rax, aInvalidSecurit_0; "Invalid security descriptor in registry"
0x18003e256  mov     [rbp+4Fh+var_30], r15
0x18003e25a  mov     [rbp+4Fh+var_40], rax
0x18003e25e  lea     rdx, word_1800CA8DE
0x18003e265  lea     rax, [rbp+4Fh+var_30]
0x18003e269  mov     [rbp+4Fh+var_38], r14
0x18003e26d  mov     [rsp+0B0h+var_80], rax
0x18003e272  lea     rax, [rbp+4Fh+var_38]
0x18003e276  mov     [rsp+0B0h+lpcbData], rax
0x18003e27b  lea     rax, [rbp+4Fh+var_40]
0x18003e27f  mov     [rsp+0B0h+phkResult], rax
0x18003e284  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapSz@G@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapSz@G@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x18003e289  mov     ebx, 8007053Ah
0x18003e28e  jmp     short loc_18003E301
0x18003e290  mov     eax, cs:dword_1800DA020
0x18003e296  mov     ebx, 80070057h
0x18003e29b  cmp     eax, 3
0x18003e29e  jbe     short loc_18003E301
0x18003e2a0  lea     rax, aGetsdvaluefrom; "GetSDValueFromRegistry"
0x18003e2a7  mov     [rbp+4Fh+var_60], ebx
0x18003e2aa  mov     [rbp+4Fh+var_30], rax
0x18003e2ae  lea     rdx, unk_1800CA980
0x18003e2b5  lea     rax, aInvalidParamet; "Invalid parameters"
0x18003e2bc  xor     r9d, r9d
0x18003e2bf  mov     [rbp+4Fh+var_38], rax
0x18003e2c3  lea     rcx, dword_1800DA020
0x18003e2ca  lea     rax, aWarningHresult; "Warning HResult failed"
0x18003e2d1  xor     r8d, r8d
0x18003e2d4  mov     [rbp+4Fh+var_40], rax
0x18003e2d8  lea     rax, [rbp+4Fh+var_30]
0x18003e2dc  mov     [rsp+0B0h+var_78], rax
0x18003e2e1  lea     rax, [rbp+4Fh+var_60]
0x18003e2e5  mov     [rsp+0B0h+var_80], rax
0x18003e2ea  lea     rax, [rbp+4Fh+var_38]
0x18003e2ee  mov     [rsp+0B0h+lpcbData], rax
0x18003e2f3  lea     rax, [rbp+4Fh+var_40]
0x18003e2f7  mov     [rsp+0B0h+phkResult], rax
0x18003e2fc  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x18003e301  mov     rcx, [rbp+4Fh+hKey]; hKey
0x18003e305  test    rcx, rcx
0x18003e308  jz      short loc_18003E310
0x18003e30a  call    cs:__imp_RegCloseKey
0x18003e310  test    rdi, rdi
0x18003e313  jz      short loc_18003E31D
0x18003e315  mov     rcx, rdi; Block
0x18003e318  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18003e31d  lea     r11, [rsp+0B0h+var_20]
0x18003e325  mov     eax, ebx
0x18003e327  mov     rbx, [r11+38h]
0x18003e32b  mov     rsi, [r11+40h]
0x18003e32f  mov     rsp, r11
0x18003e332  pop     r15
0x18003e334  pop     r14
0x18003e336  pop     r12
0x18003e338  pop     rdi
0x18003e339  pop     rbp
0x18003e33a  retn
```
