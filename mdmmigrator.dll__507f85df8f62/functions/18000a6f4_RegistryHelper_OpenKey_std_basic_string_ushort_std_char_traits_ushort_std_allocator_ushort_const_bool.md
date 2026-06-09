# RegistryHelper::OpenKey(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,bool)

- ea: `0x18000a6f4`
- end: `0x18000a87f`
- name: `?OpenKey@RegistryHelper@@SAPEAUHKEY__@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_N@Z`
- size: `395`
- prototype: `HKEY __fastcall(const WCHAR *lpSubKey, char)`
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x180008940`
- `0x18000a8a8`

## callees

- `0x18000138c`
- `0x18000139c`
- `0x180001628`
- `0x180004224`
- `0x18000a6f4`
- `0x18000a888`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000a783`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000a783`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18000a751`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18000a751`

## string_xrefs

- `0x18000a7de`: `Failed to open regsitry key`
- `0x18000a7ef`: `onecoreuap\admin\enterprisemgmt\migrator\blue2th\lib\registrymigrator.cpp`
- `0x18000a86a`: `onecoreuap\admin\enterprisemgmt\migrator\blue2th\lib\registrymigrator.cpp`
- `0x18000a80a`: `RegistryHelper::OpenKey`

## pseudocode

```c
HKEY __fastcall RegistryHelper::OpenKey(const WCHAR *lpSubKey, char a2)
{
  LSTATUS v2; // eax
  unsigned int v3; // ebx
  const unsigned __int16 **v5; // rax
  const unsigned __int16 **v6; // r8
  const unsigned __int16 **v7; // r9
  unsigned int v8; // eax
  int dwOptions; // [rsp+20h] [rbp-58h]
  _BYTE v10[8]; // [rsp+50h] [rbp-28h] BYREF
  _BYTE v11[8]; // [rsp+58h] [rbp-20h] BYREF
  _BYTE v12[24]; // [rsp+60h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]
  unsigned int v14; // [rsp+88h] [rbp+10h] BYREF
  int v15; // [rsp+90h] [rbp+18h] BYREF
  HKEY phkResult; // [rsp+98h] [rbp+20h] BYREF

  phkResult = 0;
  if ( a2 )
  {
    if ( *((_QWORD *)lpSubKey + 3) > 7u )
      lpSubKey = *(const WCHAR **)lpSubKey;
    v2 = RegCreateKeyExW(HKEY_LOCAL_MACHINE, lpSubKey, 0, 0, 0, 0xF003Fu, 0, &phkResult, 0);
  }
  else
  {
    if ( *((_QWORD *)lpSubKey + 3) > 7u )
      lpSubKey = *(const WCHAR **)lpSubKey;
    v2 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, lpSubKey, 0, 0xF003Fu, &phkResult);
  }
  v3 = v2;
  if ( v2 == 2 )
    return 0;
  if ( v2 )
  {
    if ( v2 > 0 )
      v3 = (unsigned __int16)v2 | 0x80070000;
    if ( (unsigned int)dword_18002B0C0 > 5 )
    {
      if ( (unsigned __int8)tlgKeywordOn(&dword_18002B0C0, 0x400000000000LL) )
      {
        _tlgTypeMapBase<unsigned short *,void>::_tlgWrapAuto(v10, "Failed to open regsitry key");
        v14 = v3;
        _tlgTypeMapBase<unsigned short *,void>::_tlgWrapAuto(
          v11,
          "onecoreuap\\admin\\enterprisemgmt\\migrator\\blue2th\\lib\\registrymigrator.cpp");
        v15 = 54;
        v5 = (const unsigned __int16 **)_tlgTypeMapBase<unsigned short *,void>::_tlgWrapAuto(
                                          v12,
                                          L"RegistryHelper::OpenKey");
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
          (__int64)&v15,
          (__int64)byte_180025623,
          (__int64)v6,
          (__int64)v7,
          v5,
          (__int64)&v15,
          v7,
          (__int64)&v14,
          v6);
      }
    }
    v8 = wil::verify_hresult<long>(v3);
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x36,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\migrator\\blue2th\\lib\\registrymigrator.cpp",
      (const char *)v8,
      dwOptions);
  }
  return phkResult;
}

```

## disassembly

```asm
0x18000a6f4  mov     rax, rsp
0x18000a6f7  push    rbx
0x18000a6f8  sub     rsp, 70h
0x18000a6fc  mov     qword ptr [rax+20h], 0
0x18000a704  test    dl, dl
0x18000a706  jz      short loc_18000A759
0x18000a708  cmp     qword ptr [rcx+18h], 7
0x18000a70d  jbe     short loc_18000A712
0x18000a70f  mov     rcx, [rcx]
0x18000a712  mov     [rsp+78h+lpdwDisposition], 0; lpdwDisposition
0x18000a71b  lea     rax, [rsp+78h+arg_18]
0x18000a723  mov     [rsp+78h+phkResult], rax; phkResult
0x18000a728  mov     rdx, rcx; lpSubKey
0x18000a72b  mov     [rsp+78h+lpSecurityAttributes], 0; lpSecurityAttributes
0x18000a734  xor     r9d, r9d; lpClass
0x18000a737  mov     [rsp+78h+samDesired], 0F003Fh; samDesired
0x18000a73f  xor     r8d, r8d; Reserved
0x18000a742  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000a749  mov     [rsp+78h+dwOptions], 0; dwOptions
0x18000a751  call    cs:__imp_RegCreateKeyExW
0x18000a757  jmp     short loc_18000A789
0x18000a759  cmp     qword ptr [rcx+18h], 7
0x18000a75e  jbe     short loc_18000A763
0x18000a760  mov     rcx, [rcx]
0x18000a763  lea     rax, [rsp+78h+arg_18]
0x18000a76b  mov     rdx, rcx; lpSubKey
0x18000a76e  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000a775  mov     qword ptr [rsp+78h+dwOptions], rax; phkResult
0x18000a77a  mov     r9d, 0F003Fh; samDesired
0x18000a780  xor     r8d, r8d; ulOptions
0x18000a783  call    cs:__imp_RegOpenKeyExW
0x18000a789  mov     ebx, eax
0x18000a78b  cmp     eax, 2
0x18000a78e  jnz     short loc_18000A794
0x18000a790  xor     eax, eax
0x18000a792  jmp     short loc_18000A7A0
0x18000a794  test    ebx, ebx
0x18000a796  jnz     short loc_18000A7A6
0x18000a798  mov     rax, [rsp+78h+arg_18]
0x18000a7a0  add     rsp, 70h
0x18000a7a4  pop     rbx
0x18000a7a5  retn
0x18000a7a6  jle     short loc_18000A7B1
0x18000a7a8  movzx   ebx, bx
0x18000a7ab  or      ebx, 80070000h
0x18000a7b1  mov     eax, cs:dword_18002B0C0
0x18000a7b7  cmp     eax, 5
0x18000a7ba  jbe     loc_18000A85E
0x18000a7c0  mov     rdx, 400000000000h
0x18000a7ca  lea     rcx, dword_18002B0C0
0x18000a7d1  call    _tlgKeywordOn
0x18000a7d6  test    al, al
0x18000a7d8  jz      loc_18000A85E
0x18000a7de  lea     rdx, aFailedToOpenRe; "Failed to open regsitry key"
0x18000a7e5  lea     rcx, [rsp+78h+var_28]
0x18000a7ea  call    ?_tlgWrapAuto@?$_tlgTypeMapBase@PEAGX@@SA?AU?$_tlgWrapSz@G@@PEBG@Z; _tlgTypeMapBase<ushort *,void>::_tlgWrapAuto(ushort const *)
0x18000a7ef  lea     rdx, aOnecoreuapAdmi_1; "onecoreuap\\admin\\enterprisemgmt\\migr"...
0x18000a7f6  mov     [rsp+78h+arg_8], ebx
0x18000a7fd  lea     rcx, [rsp+78h+var_20]
0x18000a802  mov     r8, rax
0x18000a805  call    ?_tlgWrapAuto@?$_tlgTypeMapBase@PEAGX@@SA?AU?$_tlgWrapSz@G@@PEBG@Z; _tlgTypeMapBase<ushort *,void>::_tlgWrapAuto(ushort const *)
0x18000a80a  lea     rdx, aRegistryhelper_1; "RegistryHelper::OpenKey"
0x18000a811  mov     [rsp+78h+arg_10], 36h ; '6'
0x18000a81c  lea     rcx, [rsp+78h+var_18]
0x18000a821  mov     r9, rax
0x18000a824  call    ?_tlgWrapAuto@?$_tlgTypeMapBase@PEAGX@@SA?AU?$_tlgWrapSz@G@@PEBG@Z; _tlgTypeMapBase<ushort *,void>::_tlgWrapAuto(ushort const *)
0x18000a829  mov     [rsp+78h+lpdwDisposition], r8
0x18000a82e  lea     rcx, [rsp+78h+arg_8]
0x18000a836  mov     [rsp+78h+phkResult], rcx
0x18000a83b  lea     rdx, byte_180025623
0x18000a842  mov     [rsp+78h+lpSecurityAttributes], r9
0x18000a847  lea     rcx, [rsp+78h+arg_10]
0x18000a84f  mov     qword ptr [rsp+78h+samDesired], rcx
0x18000a854  mov     qword ptr [rsp+78h+dwOptions], rax; int
0x18000a859  call    ??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@45@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x18000a85e  mov     ecx, ebx
0x18000a860  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x18000a865  mov     rcx, [rsp+78h]; this
0x18000a86a  lea     r8, aOnecoreuapAdmi_1; "onecoreuap\\admin\\enterprisemgmt\\migr"...
0x18000a871  mov     r9d, eax; char *
0x18000a874  mov     edx, 36h ; '6'; void *
0x18000a879  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
