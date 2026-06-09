# RegistryHelper::Write(ushort const *,ushort const *,uchar const *,ulong,ulong)

- ea: `0x18000a8a8`
- end: `0x18000aa25`
- name: `?Write@RegistryHelper@@SAXPEBG0PEBEKK@Z`
- size: `381`
- prototype: `void __fastcall(const unsigned __int16 *, const unsigned __int16 *, const unsigned __int8 *)`
- caller_count: `2`
- callee_count: `10`
- tags: `registry_config`

## callers

- `0x1800088a4`
- `0x18000c740`

## callees

- `0x18000138c`
- `0x18000139c`
- `0x180001628`
- `0x1800022e0`
- `0x180004224`
- `0x180007720`
- `0x180007b38`
- `0x18000a6f4`
- `0x18000a888`
- `0x18000a8a8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000a937`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000a937`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000a946`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000a946`

## string_xrefs

- `0x18000a9b5`: `onecoreuap\admin\enterprisemgmt\migrator\blue2th\lib\registrymigrator.cpp`
- `0x18000aa16`: `onecoreuap\admin\enterprisemgmt\migrator\blue2th\lib\registrymigrator.cpp`
- `0x18000a99f`: `RegSetValueEx failed.`
- `0x18000a9cb`: `RegistryHelper::Write`

## pseudocode

```c
void __fastcall RegistryHelper::Write(
        const unsigned __int16 *a1,
        const unsigned __int16 *a2,
        const unsigned __int8 *a3)
{
  unsigned __int64 v5; // r8
  HKEY v6; // rbx
  LSTATUS v7; // eax
  unsigned int v8; // edi
  const unsigned __int16 **v9; // rax
  const unsigned __int16 **v10; // r8
  const unsigned __int16 **v11; // r9
  unsigned int v12; // eax
  int lpData; // [rsp+20h] [rbp-51h]
  unsigned int v14; // [rsp+50h] [rbp-21h] BYREF
  int v15; // [rsp+54h] [rbp-1Dh] BYREF
  HKEY v16; // [rsp+58h] [rbp-19h]
  _BYTE v17[8]; // [rsp+60h] [rbp-11h] BYREF
  _BYTE v18[8]; // [rsp+68h] [rbp-9h] BYREF
  _BYTE v19[8]; // [rsp+70h] [rbp-1h] BYREF
  WCHAR SubKey[8]; // [rsp+78h] [rbp+7h] BYREF
  __int128 v21; // [rsp+88h] [rbp+17h]
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+57h]

  *(_OWORD *)SubKey = 0;
  v21 = 0;
  v5 = -1;
  do
    ++v5;
  while ( a1[v5] );
  std::wstring::_Construct<1,unsigned short const *>(SubKey, a1, v5);
  v6 = RegistryHelper::OpenKey(SubKey, 1);
  v16 = v6;
  std::wstring::~wstring((char **)SubKey);
  if ( v6 )
  {
    v7 = RegSetValueExW(v6, a2, 0, 4u, a3, 4u);
    v8 = v7;
    if ( v7 )
    {
      if ( v7 > 0 )
        v8 = (unsigned __int16)v7 | 0x80070000;
      if ( (unsigned int)dword_18002B0C0 > 5 )
      {
        if ( (unsigned __int8)tlgKeywordOn(&dword_18002B0C0, 0x400000000000LL) )
        {
          _tlgTypeMapBase<unsigned short *,void>::_tlgWrapAuto(v17, "RegSetValueEx failed.");
          v14 = v8;
          _tlgTypeMapBase<unsigned short *,void>::_tlgWrapAuto(
            v18,
            "onecoreuap\\admin\\enterprisemgmt\\migrator\\blue2th\\lib\\registrymigrator.cpp");
          v15 = 99;
          v9 = (const unsigned __int16 **)_tlgTypeMapBase<unsigned short *,void>::_tlgWrapAuto(
                                            v19,
                                            L"RegistryHelper::Write");
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
            (__int64)&v15,
            (__int64)&word_1800254AE,
            (__int64)v10,
            (__int64)v11,
            v9,
            (__int64)&v15,
            v11,
            (__int64)&v14,
            v10);
        }
      }
      v12 = wil::verify_hresult<long>(v8);
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x63,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\migrator\\blue2th\\lib\\registrymigrator.cpp",
        (const char *)v12,
        lpData);
    }
    RegCloseKey(v6);
  }
}

```

## disassembly

```asm
0x18000a8a8  push    rbp
0x18000a8aa  push    rbx
0x18000a8ab  push    rsi
0x18000a8ac  push    rdi
0x18000a8ad  push    r14
0x18000a8af  lea     rbp, [rsp-2Fh]
0x18000a8b4  sub     rsp, 0A0h
0x18000a8bb  mov     rax, cs:__security_cookie
0x18000a8c2  xor     rax, rsp
0x18000a8c5  mov     [rbp+4Fh+var_28], rax
0x18000a8c9  mov     rsi, r8
0x18000a8cc  mov     rdi, rdx
0x18000a8cf  xorps   xmm0, xmm0
0x18000a8d2  movups  xmmword ptr [rbp+4Fh+SubKey], xmm0
0x18000a8d6  xorps   xmm1, xmm1
0x18000a8d9  movdqu  [rbp+4Fh+var_38], xmm1
0x18000a8de  or      r8, 0FFFFFFFFFFFFFFFFh
0x18000a8e2  xor     r14d, r14d
0x18000a8e5  inc     r8
0x18000a8e8  cmp     [rcx+r8*2], r14w
0x18000a8ed  jnz     short loc_18000A8E5
0x18000a8ef  mov     rdx, rcx
0x18000a8f2  lea     rcx, [rbp+4Fh+SubKey]
0x18000a8f6  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18000a8fb  nop
0x18000a8fc  mov     dl, 1
0x18000a8fe  lea     rcx, [rbp+4Fh+SubKey]; lpSubKey
0x18000a902  call    ?OpenKey@RegistryHelper@@SAPEAUHKEY__@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_N@Z; RegistryHelper::OpenKey(std::wstring const &,bool)
0x18000a907  mov     rbx, rax
0x18000a90a  mov     [rbp+4Fh+var_68], rax
0x18000a90e  lea     rcx, [rbp+4Fh+SubKey]; void *
0x18000a912  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000a917  test    rbx, rbx
0x18000a91a  jnz     short loc_18000A91E
0x18000a91c  jmp     short loc_18000A94C
0x18000a91e  mov     r9d, 4; dwType
0x18000a924  mov     [rsp+0C0h+cbData], r9d; cbData
0x18000a929  mov     [rsp+0C0h+lpData], rsi; lpData
0x18000a92e  xor     r8d, r8d; Reserved
0x18000a931  mov     rdx, rdi; lpValueName
0x18000a934  mov     rcx, rbx; hKey
0x18000a937  call    cs:__imp_RegSetValueExW
0x18000a93d  mov     edi, eax
0x18000a93f  test    eax, eax
0x18000a941  jnz     short loc_18000A966
0x18000a943  mov     rcx, rbx; hKey
0x18000a946  call    cs:__imp_RegCloseKey
0x18000a94c  mov     rcx, [rbp+4Fh+var_28]
0x18000a950  xor     rcx, rsp; StackCookie
0x18000a953  call    __security_check_cookie
0x18000a958  add     rsp, 0A0h
0x18000a95f  pop     r14
0x18000a961  pop     rdi
0x18000a962  pop     rsi
0x18000a963  pop     rbx
0x18000a964  pop     rbp
0x18000a965  retn
0x18000a966  jle     short loc_18000A971
0x18000a968  movzx   edi, ax
0x18000a96b  or      edi, 80070000h
0x18000a971  mov     eax, cs:dword_18002B0C0
0x18000a977  mov     ebx, 63h ; 'c'
0x18000a97c  cmp     eax, 5
0x18000a97f  jbe     loc_18000AA08
0x18000a985  mov     rdx, 400000000000h
0x18000a98f  lea     rcx, dword_18002B0C0
0x18000a996  call    _tlgKeywordOn
0x18000a99b  test    al, al
0x18000a99d  jz      short loc_18000AA08
0x18000a99f  lea     rdx, aRegsetvalueexF; "RegSetValueEx failed."
0x18000a9a6  lea     rcx, [rbp+4Fh+var_60]
0x18000a9aa  call    ?_tlgWrapAuto@?$_tlgTypeMapBase@PEAGX@@SA?AU?$_tlgWrapSz@G@@PEBG@Z; _tlgTypeMapBase<ushort *,void>::_tlgWrapAuto(ushort const *)
0x18000a9af  mov     r8, rax
0x18000a9b2  mov     [rbp+4Fh+var_70], edi
0x18000a9b5  lea     rdx, aOnecoreuapAdmi_1; "onecoreuap\\admin\\enterprisemgmt\\migr"...
0x18000a9bc  lea     rcx, [rbp+4Fh+var_58]
0x18000a9c0  call    ?_tlgWrapAuto@?$_tlgTypeMapBase@PEAGX@@SA?AU?$_tlgWrapSz@G@@PEBG@Z; _tlgTypeMapBase<ushort *,void>::_tlgWrapAuto(ushort const *)
0x18000a9c5  mov     r9, rax
0x18000a9c8  mov     [rbp+4Fh+var_6C], ebx
0x18000a9cb  lea     rdx, aRegistryhelper; "RegistryHelper::Write"
0x18000a9d2  lea     rcx, [rbp+4Fh+var_50]
0x18000a9d6  call    ?_tlgWrapAuto@?$_tlgTypeMapBase@PEAGX@@SA?AU?$_tlgWrapSz@G@@PEBG@Z; _tlgTypeMapBase<ushort *,void>::_tlgWrapAuto(ushort const *)
0x18000a9db  mov     [rsp+0C0h+var_80], r8
0x18000a9e0  lea     rcx, [rbp+4Fh+var_70]
0x18000a9e4  mov     [rsp+0C0h+var_88], rcx
0x18000a9e9  mov     [rsp+0C0h+var_90], r9
0x18000a9ee  lea     rcx, [rbp+4Fh+var_6C]
0x18000a9f2  mov     qword ptr [rsp+0C0h+cbData], rcx
0x18000a9f7  mov     [rsp+0C0h+lpData], rax; int
0x18000a9fc  lea     rdx, word_1800254AE
0x18000aa03  call    ??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@45@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x18000aa08  mov     ecx, edi
0x18000aa0a  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x18000aa0f  mov     r9d, eax; char *
0x18000aa12  mov     rcx, [rbp+57h]; this
0x18000aa16  lea     r8, aOnecoreuapAdmi_1; "onecoreuap\\admin\\enterprisemgmt\\migr"...
0x18000aa1d  mov     edx, ebx; void *
0x18000aa1f  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
