# CTSSecurityDescriptor::GetSDValueFromRegistry(ushort const *,ushort const *,uchar * *,ulong *)

- ea: `0x18004072c`
- end: `0x180040aa4`
- name: `?GetSDValueFromRegistry@CTSSecurityDescriptor@@IEAAJPEBG0PEAPEAEPEAK@Z`
- size: `888`
- prototype: `int(CTSSecurityDescriptor *__hidden this, const unsigned __int16 *, const unsigned __int16 *, unsigned __int8 **, unsigned int *)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18000a66c`

## callees

- `0x180001008`
- `0x180001120`
- `0x1800014d0`
- `0x180003478`
- `0x18000425c`
- `0x18004072c`
- `0x18004ec5c`
- `0x18004f174`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180040795`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180040795`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180040823`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800408f1`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180040823`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800408f1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180040a6c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180040a6c`

## string_xrefs

- `0x180040923`: `GetSDValueFromRegistry`
- `0x180040a02`: `GetSDValueFromRegistry`
- `0x1800407c3`: `Failed to open key`
- `0x1800409b1`: `Invalid security descriptor in registry`
- `0x180040851`: `Registry entry not found`

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
            else if ( (unsigned int)dword_1800DF020 > 3 )
            {
              v29 = (const char *)a3;
              v27 = (const unsigned __int16 *)"GetSDValueFromRegistry";
              v28 = (const char *)a2;
              v30 = "RegQueryValueEx failed after we queried it the 2nd time";
              v31[0] = "Warning HResult failed";
              v25 = v14;
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
                v20,
                (unsigned int)&byte_1800CFCD7,
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
          if ( (unsigned int)dword_1800DF020 > 2 )
          {
            v31[0] = a3;
            v29 = "Invalid security descriptor in registry";
            v30 = (const char *)a2;
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
              v16,
              (unsigned int)&word_1800CFA66,
              v17,
              v18,
              (__int64)&v29,
              (__int64)&v30,
              (__int64)v31);
          }
          v14 = -2147023558;
        }
      }
      else if ( (unsigned int)dword_1800DF020 > 5 )
      {
        v25 = v14;
        v29 = "Registry entry not found";
        v28 = (const char *)a2;
        v27 = a3;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
          v16,
          (unsigned int)word_1800CFC72,
          v17,
          v18,
          (__int64)&v29,
          (__int64)&v27,
          (__int64)&v28,
          (__int64)&v25);
      }
    }
    else if ( (unsigned int)dword_1800DF020 > 3 )
    {
      v25 = v14;
      v28 = "Failed to open key";
      v27 = a2;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
        v11,
        (unsigned int)byte_1800CFA09,
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
    if ( (unsigned int)dword_1800DF020 > 3 )
    {
      v25 = -2147024809;
      v31[0] = "GetSDValueFromRegistry";
      v30 = "Invalid parameters";
      v29 = "Warning HResult failed";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        (unsigned int)&dword_1800DF020,
        (unsigned int)&unk_1800CFB08,
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
0x18004072c  mov     rax, rsp
0x18004072f  mov     [rax+10h], rbx
0x180040733  mov     [rax+18h], rsi
0x180040737  mov     [rax+8], rcx
0x18004073b  push    rbp
0x18004073c  push    rdi
0x18004073d  push    r12
0x18004073f  push    r14
0x180040741  push    r15
0x180040743  lea     rbp, [rax-57h]
0x180040747  sub     rsp, 90h
0x18004074e  xor     edi, edi
0x180040750  mov     [rbp+4Fh+hKey], 0
0x180040758  mov     r12, r9
0x18004075b  mov     r15, r8
0x18004075e  mov     r14, rdx
0x180040761  test    r9, r9
0x180040764  jz      loc_1800409F2
0x18004076a  mov     rsi, [rbp+4Fh+arg_20]
0x18004076e  test    rsi, rsi
0x180040771  jz      loc_1800409F2
0x180040777  mov     [r9], rdi
0x18004077a  lea     rax, [rbp+4Fh+hKey]
0x18004077e  mov     r9d, 20019h; samDesired
0x180040784  mov     [rsp+0B0h+phkResult], rax; phkResult
0x180040789  xor     r8d, r8d; ulOptions
0x18004078c  mov     [rsi], edi
0x18004078e  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180040795  call    cs:__imp_RegOpenKeyExW
0x18004079c  nop     dword ptr [rax+rax+00h]
0x1800407a1  mov     ebx, eax
0x1800407a3  test    eax, eax
0x1800407a5  jle     short loc_1800407B0
0x1800407a7  movzx   ebx, ax
0x1800407aa  or      ebx, 80070000h
0x1800407b0  test    ebx, ebx
0x1800407b2  jns     short loc_180040801
0x1800407b4  mov     eax, cs:dword_1800DF020
0x1800407ba  cmp     eax, 3
0x1800407bd  jbe     loc_180040A63
0x1800407c3  lea     rax, aFailedToOpenKe; "Failed to open key"
0x1800407ca  mov     [rbp+4Fh+var_60], ebx
0x1800407cd  mov     [rbp+4Fh+var_48], rax
0x1800407d1  lea     rdx, byte_1800CFA09
0x1800407d8  lea     rax, [rbp+4Fh+var_60]
0x1800407dc  mov     [rbp+4Fh+var_50], r14
0x1800407e0  mov     [rsp+0B0h+var_80], rax
0x1800407e5  lea     rax, [rbp+4Fh+var_50]
0x1800407e9  mov     [rsp+0B0h+lpcbData], rax
0x1800407ee  lea     rax, [rbp+4Fh+var_48]
0x1800407f2  mov     [rsp+0B0h+phkResult], rax
0x1800407f7  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x1800407fc  jmp     loc_180040A63
0x180040801  mov     rcx, [rbp+4Fh+hKey]; hKey
0x180040805  lea     rax, [rbp+4Fh+cbData]
0x180040809  mov     [rsp+0B0h+lpcbData], rax; lpcbData
0x18004080e  lea     r9, [rbp+4Fh+Type]; lpType
0x180040812  xor     r8d, r8d; lpReserved
0x180040815  mov     [rsp+0B0h+phkResult], rdi; lpData
0x18004081a  mov     rdx, r15; lpValueName
0x18004081d  mov     [rbp+4Fh+Type], edi
0x180040820  mov     dword ptr [rbp+4Fh+cbData], edi
0x180040823  call    cs:__imp_RegQueryValueExW
0x18004082a  nop     dword ptr [rax+rax+00h]
0x18004082f  mov     ebx, eax
0x180040831  test    eax, eax
0x180040833  jle     short loc_18004083E
0x180040835  movzx   ebx, ax
0x180040838  or      ebx, 80070000h
0x18004083e  test    ebx, ebx
0x180040840  jns     short loc_18004089C
0x180040842  mov     eax, cs:dword_1800DF020
0x180040848  cmp     eax, 5
0x18004084b  jbe     loc_180040A63
0x180040851  lea     rax, aRegistryEntryN; "Registry entry not found"
0x180040858  mov     [rbp+4Fh+var_60], ebx
0x18004085b  mov     [rbp+4Fh+var_40], rax
0x18004085f  lea     rdx, word_1800CFC72
0x180040866  lea     rax, [rbp+4Fh+var_60]
0x18004086a  mov     [rbp+4Fh+var_48], r14
0x18004086e  mov     [rsp+0B0h+var_78], rax
0x180040873  lea     rax, [rbp+4Fh+var_48]
0x180040877  mov     [rsp+0B0h+var_80], rax
0x18004087c  lea     rax, [rbp+4Fh+var_50]
0x180040880  mov     [rsp+0B0h+lpcbData], rax
0x180040885  lea     rax, [rbp+4Fh+var_40]
0x180040889  mov     [rsp+0B0h+phkResult], rax
0x18004088e  mov     [rbp+4Fh+var_50], r15
0x180040892  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapSz@G@@U2@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapSz@G@@4AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x180040897  jmp     loc_180040A63
0x18004089c  cmp     [rbp+4Fh+Type], 3
0x1800408a0  jnz     loc_1800409A6
0x1800408a6  mov     ecx, dword ptr [rbp+4Fh+cbData]; unsigned __int64
0x1800408a9  lea     eax, [rcx-28h]
0x1800408ac  cmp     eax, 0FFD7h
0x1800408b1  ja      loc_1800409A6
0x1800408b7  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800408be  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800408c3  mov     rdi, rax
0x1800408c6  test    rax, rax
0x1800408c9  jnz     short loc_1800408D5
0x1800408cb  mov     ebx, 8007000Eh
0x1800408d0  jmp     loc_180040A63
0x1800408d5  mov     rcx, [rbp+4Fh+hKey]; hKey
0x1800408d9  lea     rax, [rbp+4Fh+cbData]
0x1800408dd  mov     [rsp+0B0h+lpcbData], rax; lpcbData
0x1800408e2  lea     r9, [rbp+4Fh+Type]; lpType
0x1800408e6  xor     r8d, r8d; lpReserved
0x1800408e9  mov     [rsp+0B0h+phkResult], rdi; lpData
0x1800408ee  mov     rdx, r15; lpValueName
0x1800408f1  call    cs:__imp_RegQueryValueExW
0x1800408f8  nop     dword ptr [rax+rax+00h]
0x1800408fd  mov     ebx, eax
0x1800408ff  test    eax, eax
0x180040901  jle     short loc_18004090C
0x180040903  movzx   ebx, ax
0x180040906  or      ebx, 80070000h
0x18004090c  test    ebx, ebx
0x18004090e  jns     loc_180040996
0x180040914  mov     eax, cs:dword_1800DF020
0x18004091a  cmp     eax, 3
0x18004091d  jbe     loc_180040A63
0x180040923  lea     rax, aGetsdvaluefrom; "GetSDValueFromRegistry"
0x18004092a  mov     [rbp+4Fh+var_40], r15
0x18004092e  mov     [rbp+4Fh+var_50], rax
0x180040932  lea     rdx, byte_1800CFCD7
0x180040939  lea     rax, aRegqueryvaluee; "RegQueryValueEx failed after we queried"...
0x180040940  mov     [rbp+4Fh+var_48], r14
0x180040944  mov     [rbp+4Fh+var_38], rax
0x180040948  lea     rax, aWarningHresult; "Warning HResult failed"
0x18004094f  mov     [rbp+4Fh+var_30], rax
0x180040953  lea     rax, [rbp+4Fh+var_40]
0x180040957  mov     [rsp+0B0h+var_68], rax
0x18004095c  lea     rax, [rbp+4Fh+var_48]
0x180040960  mov     [rsp+0B0h+var_70], rax
0x180040965  lea     rax, [rbp+4Fh+var_50]
0x180040969  mov     [rsp+0B0h+var_78], rax
0x18004096e  lea     rax, [rbp+4Fh+var_60]
0x180040972  mov     [rsp+0B0h+var_80], rax
0x180040977  lea     rax, [rbp+4Fh+var_38]
0x18004097b  mov     [rsp+0B0h+lpcbData], rax
0x180040980  lea     rax, [rbp+4Fh+var_30]
0x180040984  mov     [rsp+0B0h+phkResult], rax
0x180040989  mov     [rbp+4Fh+var_60], ebx
0x18004098c  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@U1@U?$_tlgWrapSz@G@@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@3AEBU?$_tlgWrapSz@G@@5@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x180040991  jmp     loc_180040A63
0x180040996  mov     eax, dword ptr [rbp+4Fh+cbData]
0x180040999  mov     [r12], rdi
0x18004099d  xor     edi, edi
0x18004099f  mov     [rsi], eax
0x1800409a1  jmp     loc_180040A63
0x1800409a6  mov     eax, cs:dword_1800DF020
0x1800409ac  cmp     eax, 2
0x1800409af  jbe     short loc_1800409EB
0x1800409b1  lea     rax, aInvalidSecurit_0; "Invalid security descriptor in registry"
0x1800409b8  mov     [rbp+4Fh+var_30], r15
0x1800409bc  mov     [rbp+4Fh+var_40], rax
0x1800409c0  lea     rdx, word_1800CFA66
0x1800409c7  lea     rax, [rbp+4Fh+var_30]
0x1800409cb  mov     [rbp+4Fh+var_38], r14
0x1800409cf  mov     [rsp+0B0h+var_80], rax
0x1800409d4  lea     rax, [rbp+4Fh+var_38]
0x1800409d8  mov     [rsp+0B0h+lpcbData], rax
0x1800409dd  lea     rax, [rbp+4Fh+var_40]
0x1800409e1  mov     [rsp+0B0h+phkResult], rax
0x1800409e6  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapSz@G@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapSz@G@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x1800409eb  mov     ebx, 8007053Ah
0x1800409f0  jmp     short loc_180040A63
0x1800409f2  mov     eax, cs:dword_1800DF020
0x1800409f8  mov     ebx, 80070057h
0x1800409fd  cmp     eax, 3
0x180040a00  jbe     short loc_180040A63
0x180040a02  lea     rax, aGetsdvaluefrom; "GetSDValueFromRegistry"
0x180040a09  mov     [rbp+4Fh+var_60], ebx
0x180040a0c  mov     [rbp+4Fh+var_30], rax
0x180040a10  lea     rdx, unk_1800CFB08
0x180040a17  lea     rax, aInvalidParamet; "Invalid parameters"
0x180040a1e  xor     r9d, r9d
0x180040a21  mov     [rbp+4Fh+var_38], rax
0x180040a25  lea     rcx, dword_1800DF020
0x180040a2c  lea     rax, aWarningHresult; "Warning HResult failed"
0x180040a33  xor     r8d, r8d
0x180040a36  mov     [rbp+4Fh+var_40], rax
0x180040a3a  lea     rax, [rbp+4Fh+var_30]
0x180040a3e  mov     [rsp+0B0h+var_78], rax
0x180040a43  lea     rax, [rbp+4Fh+var_60]
0x180040a47  mov     [rsp+0B0h+var_80], rax
0x180040a4c  lea     rax, [rbp+4Fh+var_38]
0x180040a50  mov     [rsp+0B0h+lpcbData], rax
0x180040a55  lea     rax, [rbp+4Fh+var_40]
0x180040a59  mov     [rsp+0B0h+phkResult], rax
0x180040a5e  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x180040a63  mov     rcx, [rbp+4Fh+hKey]; hKey
0x180040a67  test    rcx, rcx
0x180040a6a  jz      short loc_180040A78
0x180040a6c  call    cs:__imp_RegCloseKey
0x180040a73  nop     dword ptr [rax+rax+00h]
0x180040a78  test    rdi, rdi
0x180040a7b  jz      short loc_180040A85
0x180040a7d  mov     rcx, rdi; Block
0x180040a80  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180040a85  lea     r11, [rsp+0B0h+var_20]
0x180040a8d  mov     eax, ebx
0x180040a8f  mov     rbx, [r11+38h]
0x180040a93  mov     rsi, [r11+40h]
0x180040a97  mov     rsp, r11
0x180040a9a  pop     r15
0x180040a9c  pop     r14
0x180040a9e  pop     r12
0x180040aa0  pop     rdi
0x180040aa1  pop     rbp
0x180040aa2  retn
```
