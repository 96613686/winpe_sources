# StoreNcsiIEProxyString

- ea: `0x180052b04`
- end: `0x180052e2d`
- name: `StoreNcsiIEProxyString`
- size: `809`
- prototype: `__int64 __fastcall(wchar_t *Str, char)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config`

## callers

- `0x180051b7c`

## callees

- `0x180003cf8`
- `0x180011a58`
- `0x180029cf4`
- `0x18002a048`
- `0x18002b2dc`
- `0x18002d6a0`
- `0x18003e9e8`
- `0x180047240`
- `0x180051630`
- `0x1800518ac`
- `0x180052b04`
- `0x180052e34`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180052c86`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180052c86`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180052d90`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180052d90`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180052d31`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180052d31`

## pseudocode

```c
__int64 __fastcall StoreNcsiIEProxyString(wchar_t *Str, char a2)
{
  DWORD cbData; // esi
  const wchar_t *v5; // rax
  signed int v6; // eax
  int v7; // r8d
  int v8; // r9d
  const BYTE *v9; // rbx
  __int64 v10; // rcx
  unsigned __int16 *v11; // rdi
  const WCHAR *v12; // rdx
  LSTATUS v13; // eax
  int v14; // ecx
  int v15; // r8d
  int v16; // r9d
  LSTATUS v17; // eax
  int v18; // r8d
  int v19; // r9d
  unsigned int v20; // ebx
  __int64 v21; // rcx
  __int64 v22; // rdx
  LSTATUS v23; // eax
  int v24; // r8d
  int v25; // r9d
  DWORD v27; // [rsp+40h] [rbp-40h] BYREF
  unsigned __int16 *v28; // [rsp+48h] [rbp-38h] BYREF
  HKEY hKey; // [rsp+50h] [rbp-30h] BYREF
  BYTE *lpData[2]; // [rsp+58h] [rbp-28h] BYREF
  __int64 v31; // [rsp+68h] [rbp-18h]

  cbData = 0;
  v27 = 0;
  *(_OWORD *)lpData = 0;
  v31 = 0;
  if ( !Str )
  {
    v9 = 0;
LABEL_15:
    hKey = 0;
    v11 = (unsigned __int16 *)&qword_18009AAA0;
    v12 = (const WCHAR *)&qword_18009AAA0;
    if ( (unsigned __int64)qword_18009AAB8 > 7 )
      v12 = qword_18009AAA0;
    v13 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, v12, 0, 2u, &hKey);
    if ( v13 )
    {
      if ( (unsigned int)dword_18009A048 > 5 )
      {
        if ( (unsigned __int64)qword_18009AAB8 > 7 )
          v11 = (unsigned __int16 *)qword_18009AAA0;
        v28 = v11;
        v27 = v13;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>>(
          dword_18009A048,
          (unsigned int)&byte_180086647,
          v15,
          v16,
          (__int64)&v27,
          (__int64)&v28);
      }
    }
    else
    {
      if ( (unsigned int)dword_18009A048 > 5 )
      {
        v27 = 0;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
          v14,
          (unsigned int)qword_180086610,
          v15,
          v16,
          (__int64)&v27);
      }
      if ( v9 )
      {
        if ( (unsigned __int8)ContainsRelativePathDoubleDot(Str) )
          goto LABEL_41;
        v17 = RegSetValueExW(hKey, 0, 0, 1u, v9, cbData);
        v20 = v17;
        if ( !v17 )
          goto LABEL_41;
        if ( (unsigned int)dword_18009A048 > 5 )
        {
          v27 = v17;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
            dword_18009A048,
            (unsigned int)&dword_1800865CC,
            v18,
            v19,
            (__int64)&v27);
        }
        v21 = WPP_GLOBAL_Control;
        if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 0x10) == 0
          || *(_BYTE *)(WPP_GLOBAL_Control + 25LL) < 2u )
        {
          goto LABEL_41;
        }
        v22 = 77;
      }
      else
      {
        v23 = RegDeleteValueW(hKey, 0);
        v20 = v23;
        if ( !v23 )
          goto LABEL_41;
        if ( (unsigned int)dword_18009A048 > 5 )
        {
          v27 = v23;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
            dword_18009A048,
            (unsigned int)&byte_180086587,
            v24,
            v25,
            (__int64)&v27);
        }
        v21 = WPP_GLOBAL_Control;
        if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 0x10) == 0
          || *(_BYTE *)(WPP_GLOBAL_Control + 25LL) < 2u )
        {
          goto LABEL_41;
        }
        v22 = 78;
      }
      WPP_SF_d(*(_QWORD *)(v21 + 16), v22, &WPP_5540ffa188b23fc0b8d03d8186783076_Traceguids, v20);
    }
LABEL_41:
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
    return std::vector<unsigned short>::_Tidy(lpData);
  }
  std::vector<unsigned short>::_Resize_reallocate<std::_Value_init_tag>(lpData, 2050);
  if ( lpData[0] == lpData[1] )
  {
    if ( (unsigned int)dword_18009A048 > 5 )
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
        lpData[0],
        word_18008670A);
    return std::vector<unsigned short>::_Tidy(lpData);
  }
  v28 = 0;
  v5 = L"1";
  if ( !a2 )
    v5 = L"0";
  v6 = StringCchPrintfExW((wchar_t *)lpData[0], (lpData[1] - lpData[0]) >> 1, &v28, 0, 0x800u, L"%s%s", v5, Str);
  if ( v6 < 0 )
  {
    if ( (unsigned int)dword_18009A048 > 5 )
    {
      v27 = v6;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
        dword_18009A048,
        (unsigned int)word_1800866C2,
        v7,
        v8,
        (__int64)&v27);
    }
    return std::vector<unsigned short>::_Tidy(lpData);
  }
  v9 = lpData[0];
  if ( (int)LongLongToULong(2 * (((char *)v28 - (char *)lpData[0] + 2) >> 1), &v27) >= 0 )
  {
    cbData = v27;
    goto LABEL_15;
  }
  if ( (unsigned int)dword_18009A048 > 5 )
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      v10,
      word_18008668A);
  return std::vector<unsigned short>::_Tidy(lpData);
}

```

## disassembly

```asm
0x180052b04  mov     [rsp-18h+arg_8], rbx
0x180052b09  mov     [rsp-18h+arg_10], rsi
0x180052b0e  push    rbp
0x180052b0f  push    rdi
0x180052b10  push    r14
0x180052b12  mov     rbp, rsp
0x180052b15  sub     rsp, 80h
0x180052b1c  mov     rax, cs:__security_cookie
0x180052b23  xor     rax, rsp
0x180052b26  mov     [rbp+var_10], rax
0x180052b2a  mov     bl, dl
0x180052b2c  mov     r14, rcx
0x180052b2f  xor     esi, esi
0x180052b31  mov     [rbp+var_40], esi
0x180052b34  xor     eax, eax
0x180052b36  xorps   xmm1, xmm1
0x180052b39  movdqu  xmmword ptr [rbp+lpData], xmm1
0x180052b3e  mov     [rbp+var_18], rax
0x180052b42  test    rcx, rcx
0x180052b45  jz      loc_180052C49
0x180052b4b  mov     edx, 802h
0x180052b50  lea     rcx, [rbp+lpData]
0x180052b54  call    ??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@GV?$allocator@G@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<ushort>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x180052b59  mov     rdx, [rbp+lpData+8]
0x180052b5d  mov     rcx, [rbp+lpData]; Buffer
0x180052b61  cmp     rcx, rdx
0x180052b64  jnz     short loc_180052B86
0x180052b66  mov     eax, cs:dword_18009A048
0x180052b6c  cmp     eax, 5
0x180052b6f  jbe     loc_180052E00
0x180052b75  lea     rdx, word_18008670A
0x180052b7c  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x180052b81  jmp     loc_180052E00
0x180052b86  mov     [rbp+var_38], 0
0x180052b8e  lea     r8, a0; "0"
0x180052b95  lea     rax, a1; "1"
0x180052b9c  test    bl, bl
0x180052b9e  cmovz   rax, r8
0x180052ba2  sub     rdx, rcx
0x180052ba5  sar     rdx, 1; unsigned __int64
0x180052ba8  mov     [rsp+80h+var_48], r14
0x180052bad  mov     [rsp+80h+var_50], rax
0x180052bb2  lea     rax, aSS; "%s%s"
0x180052bb9  mov     qword ptr [rsp+80h+cbData], rax; unsigned __int16 *
0x180052bbe  mov     dword ptr [rsp+80h+phkResult], 800h; unsigned int
0x180052bc6  xor     r9d, r9d; unsigned __int64 *
0x180052bc9  lea     r8, [rbp+var_38]; unsigned __int16 **
0x180052bcd  call    ?StringCchPrintfExW@@YAJPEAG_KPEAPEAGPEA_KKPEBGZZ; StringCchPrintfExW(ushort *,unsigned __int64,ushort * *,unsigned __int64 *,ulong,ushort const *,...)
0x180052bd2  test    eax, eax
0x180052bd4  jns     short loc_180052C02
0x180052bd6  mov     ecx, cs:dword_18009A048
0x180052bdc  cmp     ecx, 5
0x180052bdf  jbe     loc_180052E00
0x180052be5  mov     [rbp+var_40], eax
0x180052be8  lea     rax, [rbp+var_40]
0x180052bec  mov     [rsp+80h+phkResult], rax
0x180052bf1  lea     rdx, word_1800866C2
0x180052bf8  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x180052bfd  jmp     loc_180052E00
0x180052c02  mov     rbx, [rbp+lpData]
0x180052c06  mov     rcx, [rbp+var_38]
0x180052c0a  sub     rcx, rbx
0x180052c0d  add     rcx, 2
0x180052c11  sar     rcx, 1
0x180052c14  add     rcx, rcx; __int64
0x180052c17  lea     rdx, [rbp+var_40]; unsigned int *
0x180052c1b  call    ?LongLongToULong@@YAJ_JPEAK@Z; LongLongToULong(__int64,ulong *)
0x180052c20  test    eax, eax
0x180052c22  jns     short loc_180052C44
0x180052c24  mov     eax, cs:dword_18009A048
0x180052c2a  cmp     eax, 5
0x180052c2d  jbe     loc_180052E00
0x180052c33  lea     rdx, word_18008668A
0x180052c3a  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x180052c3f  jmp     loc_180052E00
0x180052c44  mov     esi, [rbp+var_40]
0x180052c47  jmp     short loc_180052C4B
0x180052c49  xor     ebx, ebx
0x180052c4b  mov     [rbp+hKey], 0
0x180052c53  lea     rdi, qword_18009AAA0
0x180052c5a  mov     rdx, rdi
0x180052c5d  cmp     cs:qword_18009AAB8, 7
0x180052c65  cmova   rdx, cs:qword_18009AAA0; lpSubKey
0x180052c6d  lea     rax, [rbp+hKey]
0x180052c71  mov     [rsp+80h+phkResult], rax; phkResult
0x180052c76  mov     r9d, 2; samDesired
0x180052c7c  xor     r8d, r8d; ulOptions
0x180052c7f  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180052c86  call    cs:__imp_RegOpenKeyExW
0x180052c8c  test    eax, eax
0x180052c8e  jz      short loc_180052CD9
0x180052c90  mov     ecx, cs:dword_18009A048
0x180052c96  cmp     ecx, 5
0x180052c99  jbe     loc_180052DF6
0x180052c9f  cmp     cs:qword_18009AAB8, 7
0x180052ca7  cmova   rdi, cs:qword_18009AAA0
0x180052caf  mov     [rbp+var_38], rdi
0x180052cb3  mov     [rbp+var_40], eax
0x180052cb6  lea     rax, [rbp+var_38]
0x180052cba  mov     qword ptr [rsp+80h+cbData], rax
0x180052cbf  lea     rax, [rbp+var_40]
0x180052cc3  mov     [rsp+80h+phkResult], rax
0x180052cc8  lea     rdx, byte_180086647
0x180052ccf  call    ??$Write@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &)
0x180052cd4  jmp     loc_180052DF6
0x180052cd9  mov     eax, cs:dword_18009A048
0x180052cdf  cmp     eax, 5
0x180052ce2  jbe     short loc_180052D00
0x180052ce4  mov     [rbp+var_40], 0
0x180052ceb  lea     rax, [rbp+var_40]
0x180052cef  mov     [rsp+80h+phkResult], rax
0x180052cf4  lea     rdx, qword_180086610
0x180052cfb  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x180052d00  test    rbx, rbx
0x180052d03  jz      loc_180052D8A
0x180052d09  mov     rcx, r14; Str
0x180052d0c  call    ContainsRelativePathDoubleDot
0x180052d11  test    al, al
0x180052d13  jnz     loc_180052DF6
0x180052d19  mov     [rsp+80h+cbData], esi; cbData
0x180052d1d  mov     [rsp+80h+phkResult], rbx; lpData
0x180052d22  mov     r9d, 1; dwType
0x180052d28  xor     r8d, r8d; Reserved
0x180052d2b  xor     edx, edx; lpValueName
0x180052d2d  mov     rcx, [rbp+hKey]; hKey
0x180052d31  call    cs:__imp_RegSetValueExW
0x180052d37  mov     ebx, eax
0x180052d39  test    eax, eax
0x180052d3b  jz      loc_180052DF6
0x180052d41  mov     ecx, cs:dword_18009A048
0x180052d47  cmp     ecx, 5
0x180052d4a  jbe     short loc_180052D64
0x180052d4c  mov     [rbp+var_40], eax
0x180052d4f  lea     rax, [rbp+var_40]
0x180052d53  mov     [rsp+80h+phkResult], rax
0x180052d58  lea     rdx, dword_1800865CC
0x180052d5f  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x180052d64  lea     rax, WPP_GLOBAL_Control
0x180052d6b  mov     rcx, cs:WPP_GLOBAL_Control
0x180052d72  cmp     rcx, rax
0x180052d75  jz      short loc_180052DF6
0x180052d77  test    byte ptr [rcx+1Ch], 10h
0x180052d7b  jz      short loc_180052DF6
0x180052d7d  cmp     byte ptr [rcx+19h], 2
0x180052d81  jb      short loc_180052DF6
0x180052d83  mov     edx, 4Dh ; 'M'
0x180052d88  jmp     short loc_180052DE3
0x180052d8a  xor     edx, edx; lpValueName
0x180052d8c  mov     rcx, [rbp+hKey]; hKey
0x180052d90  call    cs:__imp_RegDeleteValueW
0x180052d96  mov     ebx, eax
0x180052d98  test    eax, eax
0x180052d9a  jz      short loc_180052DF6
0x180052d9c  mov     ecx, cs:dword_18009A048
0x180052da2  cmp     ecx, 5
0x180052da5  jbe     short loc_180052DBF
0x180052da7  mov     [rbp+var_40], eax
0x180052daa  lea     rax, [rbp+var_40]
0x180052dae  mov     [rsp+80h+phkResult], rax
0x180052db3  lea     rdx, byte_180086587
0x180052dba  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x180052dbf  lea     rax, WPP_GLOBAL_Control
0x180052dc6  mov     rcx, cs:WPP_GLOBAL_Control
0x180052dcd  cmp     rcx, rax
0x180052dd0  jz      short loc_180052DF6
0x180052dd2  test    byte ptr [rcx+1Ch], 10h
0x180052dd6  jz      short loc_180052DF6
0x180052dd8  cmp     byte ptr [rcx+19h], 2
0x180052ddc  jb      short loc_180052DF6
0x180052dde  mov     edx, 4Eh ; 'N'
0x180052de3  mov     r9d, ebx
0x180052de6  lea     r8, WPP_5540ffa188b23fc0b8d03d8186783076_Traceguids
0x180052ded  mov     rcx, [rcx+10h]
0x180052df1  call    WPP_SF_d
0x180052df6  lea     rcx, [rbp+hKey]
0x180052dfa  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180052dff  nop
0x180052e00  lea     rcx, [rbp+lpData]
0x180052e04  call    ?_Tidy@?$vector@GV?$allocator@G@std@@@std@@AEAAXXZ; std::vector<ushort>::_Tidy(void)
0x180052e09  mov     rcx, [rbp+var_10]
0x180052e0d  xor     rcx, rsp; StackCookie
0x180052e10  call    __security_check_cookie
0x180052e15  lea     r11, [rsp+80h+var_s0]
0x180052e1d  mov     rbx, [r11+28h]
0x180052e21  mov     rsi, [r11+30h]
0x180052e25  mov     rsp, r11
0x180052e28  pop     r14
0x180052e2a  pop     rdi
0x180052e2b  pop     rbp
0x180052e2c  retn
```
