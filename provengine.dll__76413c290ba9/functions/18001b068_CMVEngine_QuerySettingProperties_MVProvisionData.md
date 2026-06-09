# CMVEngine::QuerySettingProperties(_MVProvisionData &)

- ea: `0x18001b068`
- end: `0x18001b472`
- name: `?QuerySettingProperties@CMVEngine@@AEAAJAEAU_MVProvisionData@@@Z`
- size: `1034`
- prototype: `__int64 __fastcall(CMVEngine *__hidden this, struct _MVProvisionData *)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, registry_config`

## callers

- `0x180018698`

## callees

- `0x1800011ac`
- `0x180009900`
- `0x18000af20`
- `0x18000b030`
- `0x1800115b0`
- `0x18001b068`
- `0x180021e40`
- `0x180043750`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18001b17a`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001b29b`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001b2c1`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001b352`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001b378`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001b3c6`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001b3ec`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001b414`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001b43a`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001b17a`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001b29b`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001b2c1`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001b352`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001b378`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001b3c6`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001b3ec`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001b414`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001b43a`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001b206`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001b2fb`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001b206`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001b2fb`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001b1c9`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001b1c9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001b287`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001b33e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001b3b2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001b400`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001b287`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001b33e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001b3b2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001b400`

## pseudocode

```c
// Hidden C++ exception states: #wind=2 #try_helpers=1
__int64 __fastcall CMVEngine::QuerySettingProperties(CMVEngine *this, struct _MVProvisionData *a2)
{
  char *pvData; // rdi
  char *v6; // rdx
  unsigned __int64 v7; // r8
  const WCHAR *v8; // rdx
  unsigned int v9; // eax
  unsigned int ValueW; // eax
  __int64 v11; // r9
  __int64 *v12; // rax
  unsigned int v13; // ebx
  _DWORD *v14; // rbx
  unsigned int v15; // eax
  unsigned int v16; // ebx
  unsigned int v17; // ebx
  unsigned int phkResult; // [rsp+20h] [rbp-B8h]
  unsigned int phkResulta; // [rsp+20h] [rbp-B8h]
  unsigned int phkResultb; // [rsp+20h] [rbp-B8h]
  DWORD pcbData; // [rsp+40h] [rbp-98h] BYREF
  HKEY hkey; // [rsp+48h] [rbp-90h] BYREF
  __int64 *v23; // [rsp+50h] [rbp-88h] BYREF
  void *v24[2]; // [rsp+58h] [rbp-80h] BYREF
  unsigned __int64 v25; // [rsp+68h] [rbp-70h]
  unsigned __int64 v26; // [rsp+70h] [rbp-68h]
  LPCWSTR lpSubKey[3]; // [rsp+78h] [rbp-60h] BYREF
  unsigned __int64 v28; // [rsp+90h] [rbp-48h]
  void *Src[3]; // [rsp+98h] [rbp-40h] BYREF
  unsigned __int64 v30; // [rsp+B0h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+0h]

  pvData = (char *)a2 + 84;
  *((_DWORD *)a2 + 21) = 0;
  if ( !*((_QWORD *)this + 22) )
    return 0;
  v28 = 7;
  lpSubKey[2] = 0;
  LOWORD(lpSubKey[0]) = 0;
  std::wstring::assign(lpSubKey, (char *)L"SequenceMap\\", 0xCu);
  v6 = (char *)*((_QWORD *)a2 + 5);
  v26 = 7;
  v25 = 0;
  LOWORD(v24[0]) = 0;
  if ( *(_WORD *)v6 )
  {
    v7 = -1;
    do
      ++v7;
    while ( *(_WORD *)&v6[2 * v7] );
  }
  else
  {
    v7 = 0;
  }
  std::wstring::assign(v24, v6, v7);
  if ( v25 > 0x24 )
  {
    v30 = 7;
    Src[2] = 0;
    LOWORD(Src[0]) = 0;
    std::wstring::assign(Src, v24, 0, 0x24u);
    std::wstring::operator=(v24, Src);
    if ( v30 >= 8 )
      operator delete(Src[0]);
  }
  std::wstring::append(lpSubKey, v24, 0, 0xFFFFFFFFFFFFFFFFuLL);
  hkey = 0;
  v8 = (const WCHAR *)lpSubKey;
  if ( v28 >= 8 )
    v8 = lpSubKey[0];
  v9 = RegOpenKeyExW(*((HKEY *)this + 22), v8, 0, 0x20019u, &hkey);
  if ( v9 )
  {
    if ( v9 == 2 )
      goto LABEL_44;
    v17 = wil::details::in1diag3::Return_Win32(
            retaddr,
            (void *)0x542,
            (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\engine\\src\\provisionengine.cpp",
            (const char *)v9,
            phkResult);
    if ( hkey )
      RegCloseKey(hkey);
    if ( v26 >= 8 )
      operator delete(v24[0]);
    v26 = 7;
    v25 = 0;
    LOWORD(v24[0]) = 0;
    if ( v28 >= 8 )
      operator delete((void *)lpSubKey[0]);
    return v17;
  }
  else
  {
    pcbData = 4;
    ValueW = RegGetValueW(hkey, 0, L"Level", 0x10u, 0, pvData, &pcbData);
    if ( ValueW == 2 )
    {
      if ( (unsigned int)dword_18005A000 > 3 )
      {
        v12 = (__int64 *)lpSubKey;
        if ( v28 >= 8 )
          v12 = (__int64 *)lpSubKey[0];
        v23 = v12;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
          (__int64)&dword_18005A000,
          (__int64)&dword_18004F3D4,
          0,
          v11,
          &v23);
      }
    }
    else if ( ValueW )
    {
      v13 = wil::details::in1diag3::Return_Win32(
              retaddr,
              (void *)0x534,
              (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\engine\\src\\provisionengine.cpp",
              (const char *)ValueW,
              phkResulta);
      if ( hkey )
        RegCloseKey(hkey);
      if ( v26 >= 8 )
        operator delete(v24[0]);
      v26 = 7;
      v25 = 0;
      LOWORD(v24[0]) = 0;
      if ( v28 >= 8 )
        operator delete((void *)lpSubKey[0]);
      return v13;
    }
    pcbData = 4;
    v14 = (_DWORD *)((char *)a2 + 80);
    v15 = RegGetValueW(hkey, 0, L"RequiresReboot", 0x10u, 0, v14, &pcbData);
    if ( v15 == 2 )
    {
      *v14 = 0;
LABEL_44:
      if ( hkey )
        RegCloseKey(hkey);
      if ( v26 >= 8 )
        operator delete(v24[0]);
      v26 = 7;
      v25 = 0;
      LOWORD(v24[0]) = 0;
      if ( v28 >= 8 )
        operator delete((void *)lpSubKey[0]);
      return 0;
    }
    if ( !v15 )
      goto LABEL_44;
    v16 = wil::details::in1diag3::Return_Win32(
            retaddr,
            (void *)0x53E,
            (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\engine\\src\\provisionengine.cpp",
            (const char *)v15,
            phkResultb);
    if ( hkey )
      RegCloseKey(hkey);
    if ( v26 >= 8 )
      operator delete(v24[0]);
    v26 = 7;
    v25 = 0;
    LOWORD(v24[0]) = 0;
    if ( v28 >= 8 )
      operator delete((void *)lpSubKey[0]);
    return v16;
  }
}

```

## disassembly

```asm
0x18001b068  mov     [rsp+arg_10], rbx
0x18001b06d  mov     [rsp+arg_18], rsi
0x18001b072  push    rdi
0x18001b073  push    r14
0x18001b075  push    r15
0x18001b077  sub     rsp, 0C0h
0x18001b07e  mov     rax, cs:__security_cookie
0x18001b085  xor     rax, rsp
0x18001b088  mov     [rsp+0D8h+var_20], rax
0x18001b090  mov     rbx, rdx
0x18001b093  mov     rsi, rcx
0x18001b096  xor     r14d, r14d
0x18001b099  lea     rdi, [rdx+54h]
0x18001b09d  mov     [rdi], r14d
0x18001b0a0  cmp     [rcx+0B0h], r14
0x18001b0a7  jnz     short loc_18001B0B0
0x18001b0a9  xor     eax, eax
0x18001b0ab  jmp     loc_18001B448
0x18001b0b0  mov     r15d, 7
0x18001b0b6  mov     [rsp+0D8h+var_48], r15
0x18001b0be  mov     [rsp+0D8h+var_50], r14
0x18001b0c6  mov     word ptr [rsp+0D8h+lpSubKey], r14w
0x18001b0cc  lea     r8d, [r15+5]
0x18001b0d0  lea     rdx, aSequencemap; "SequenceMap\\"
0x18001b0d7  lea     rcx, [rsp+0D8h+lpSubKey]; void *
0x18001b0dc  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::assign(ushort const *,unsigned __int64)
0x18001b0e1  nop
0x18001b0e2  mov     rdx, [rbx+28h]; Src
0x18001b0e6  mov     [rsp+0D8h+var_68], r15
0x18001b0eb  mov     [rsp+0D8h+var_70], r14
0x18001b0f0  mov     word ptr [rsp+0D8h+var_80], r14w
0x18001b0f6  cmp     [rdx], r14w
0x18001b0fa  jnz     short loc_18001B101
0x18001b0fc  mov     r8, r14
0x18001b0ff  jmp     short loc_18001B10F
0x18001b101  or      r8, 0FFFFFFFFFFFFFFFFh
0x18001b105  inc     r8
0x18001b108  cmp     [rdx+r8*2], r14w
0x18001b10d  jnz     short loc_18001B105
0x18001b10f  lea     rcx, [rsp+0D8h+var_80]; void *
0x18001b114  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::assign(ushort const *,unsigned __int64)
0x18001b119  nop
0x18001b11a  mov     r9d, 24h ; '$'
0x18001b120  cmp     [rsp+0D8h+var_70], r9
0x18001b125  jbe     short loc_18001B180
0x18001b127  mov     [rsp+0D8h+var_28], r15
0x18001b12f  mov     [rsp+0D8h+var_30], r14
0x18001b137  mov     word ptr [rsp+0D8h+Src], r14w
0x18001b140  xor     r8d, r8d
0x18001b143  lea     rdx, [rsp+0D8h+var_80]
0x18001b148  lea     rcx, [rsp+0D8h+Src]; void *
0x18001b150  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::wstring::assign(std::wstring const &,unsigned __int64,unsigned __int64)
0x18001b155  lea     rdx, [rsp+0D8h+Src]; Src
0x18001b15d  lea     rcx, [rsp+0D8h+var_80]; void *
0x18001b162  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18001b167  cmp     [rsp+0D8h+var_28], 8
0x18001b170  jb      short loc_18001B180
0x18001b172  mov     rcx, [rsp+0D8h+Src]
0x18001b17a  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18001b180  or      r9, 0FFFFFFFFFFFFFFFFh
0x18001b184  xor     r8d, r8d
0x18001b187  lea     rdx, [rsp+0D8h+var_80]
0x18001b18c  lea     rcx, [rsp+0D8h+lpSubKey]
0x18001b191  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::wstring::append(std::wstring const &,unsigned __int64,unsigned __int64)
0x18001b196  mov     [rsp+0D8h+hkey], r14
0x18001b19b  lea     rdx, [rsp+0D8h+lpSubKey]
0x18001b1a0  cmp     [rsp+0D8h+var_48], 8
0x18001b1a9  cmovnb  rdx, [rsp+0D8h+lpSubKey]; lpSubKey
0x18001b1af  lea     rax, [rsp+0D8h+hkey]
0x18001b1b4  mov     [rsp+0D8h+phkResult], rax; unsigned int
0x18001b1b9  mov     r9d, 20019h; samDesired
0x18001b1bf  xor     r8d, r8d; ulOptions
0x18001b1c2  mov     rcx, [rsi+0B0h]; hKey
0x18001b1c9  call    cs:__imp_RegOpenKeyExW
0x18001b1cf  test    eax, eax
0x18001b1d1  jnz     loc_18001B385
0x18001b1d7  lea     esi, [rax+4]
0x18001b1da  mov     [rsp+0D8h+var_98], esi
0x18001b1de  lea     rax, [rsp+0D8h+var_98]
0x18001b1e3  mov     [rsp+0D8h+pcbData], rax; pcbData
0x18001b1e8  mov     [rsp+0D8h+pvData], rdi; pvData
0x18001b1ed  mov     [rsp+0D8h+phkResult], r14; unsigned int
0x18001b1f2  lea     edi, [rsi+0Ch]
0x18001b1f5  mov     r9d, edi; dwFlags
0x18001b1f8  lea     r8, aLevel; "Level"
0x18001b1ff  xor     edx, edx; lpSubKey
0x18001b201  mov     rcx, [rsp+0D8h+hkey]; hkey
0x18001b206  call    cs:__imp_RegGetValueW
0x18001b20c  cmp     eax, 2
0x18001b20f  jnz     short loc_18001B25B
0x18001b211  mov     eax, cs:dword_18005A000
0x18001b217  cmp     eax, 3
0x18001b21a  jbe     loc_18001B2CE
0x18001b220  lea     rax, [rsp+0D8h+lpSubKey]
0x18001b225  cmp     [rsp+0D8h+var_48], 8
0x18001b22e  cmovnb  rax, [rsp+0D8h+lpSubKey]
0x18001b234  mov     [rsp+0D8h+var_88], rax
0x18001b239  lea     rax, [rsp+0D8h+var_88]
0x18001b23e  mov     [rsp+0D8h+phkResult], rax
0x18001b243  xor     r8d, r8d
0x18001b246  lea     rdx, dword_18004F3D4
0x18001b24d  lea     rcx, dword_18005A000
0x18001b254  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x18001b259  jmp     short loc_18001B2CE
0x18001b25b  test    eax, eax
0x18001b25d  jz      short loc_18001B2CE
0x18001b25f  mov     rcx, [rsp+0D8h]; this
0x18001b267  mov     r9d, eax; char *
0x18001b26a  lea     r8, aOnecoreuapAdmi_18; "onecoreuap\\admin\\prov\\multivariant\\"...
0x18001b271  mov     edx, 534h; void *
0x18001b276  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18001b27b  mov     ebx, eax
0x18001b27d  mov     rcx, [rsp+0D8h+hkey]; hKey
0x18001b282  test    rcx, rcx
0x18001b285  jz      short loc_18001B28E
0x18001b287  call    cs:__imp_RegCloseKey
0x18001b28d  nop
0x18001b28e  cmp     [rsp+0D8h+var_68], 8
0x18001b294  jb      short loc_18001B2A1
0x18001b296  mov     rcx, [rsp+0D8h+var_80]
0x18001b29b  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18001b2a1  mov     [rsp+0D8h+var_68], r15
0x18001b2a6  mov     [rsp+0D8h+var_70], r14
0x18001b2ab  mov     word ptr [rsp+0D8h+var_80], r14w
0x18001b2b1  cmp     [rsp+0D8h+var_48], 8
0x18001b2ba  jb      short loc_18001B2C7
0x18001b2bc  mov     rcx, [rsp+0D8h+lpSubKey]
0x18001b2c1  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18001b2c7  mov     eax, ebx
0x18001b2c9  jmp     loc_18001B448
0x18001b2ce  mov     [rsp+0D8h+var_98], esi
0x18001b2d2  add     rbx, 50h ; 'P'
0x18001b2d6  lea     rax, [rsp+0D8h+var_98]
0x18001b2db  mov     [rsp+0D8h+pcbData], rax; pcbData
0x18001b2e0  mov     [rsp+0D8h+pvData], rbx; pvData
0x18001b2e5  mov     [rsp+0D8h+phkResult], r14; unsigned int
0x18001b2ea  mov     r9d, edi; dwFlags
0x18001b2ed  lea     r8, aRequiresreboot; "RequiresReboot"
0x18001b2f4  xor     edx, edx; lpSubKey
0x18001b2f6  mov     rcx, [rsp+0D8h+hkey]; hkey
0x18001b2fb  call    cs:__imp_RegGetValueW
0x18001b301  cmp     eax, 2
0x18001b304  jnz     short loc_18001B30E
0x18001b306  mov     [rbx], r14d
0x18001b309  jmp     loc_18001B3F6
0x18001b30e  test    eax, eax
0x18001b310  jz      loc_18001B3F6
0x18001b316  mov     rcx, [rsp+0D8h]; this
0x18001b31e  mov     r9d, eax; char *
0x18001b321  lea     r8, aOnecoreuapAdmi_18; "onecoreuap\\admin\\prov\\multivariant\\"...
0x18001b328  mov     edx, 53Eh; void *
0x18001b32d  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18001b332  mov     ebx, eax
0x18001b334  mov     rcx, [rsp+0D8h+hkey]; hKey
0x18001b339  test    rcx, rcx
0x18001b33c  jz      short loc_18001B345
0x18001b33e  call    cs:__imp_RegCloseKey
0x18001b344  nop
0x18001b345  cmp     [rsp+0D8h+var_68], 8
0x18001b34b  jb      short loc_18001B358
0x18001b34d  mov     rcx, [rsp+0D8h+var_80]
0x18001b352  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18001b358  mov     [rsp+0D8h+var_68], r15
0x18001b35d  mov     [rsp+0D8h+var_70], r14
0x18001b362  mov     word ptr [rsp+0D8h+var_80], r14w
0x18001b368  cmp     [rsp+0D8h+var_48], 8
0x18001b371  jb      short loc_18001B37E
0x18001b373  mov     rcx, [rsp+0D8h+lpSubKey]
0x18001b378  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18001b37e  mov     eax, ebx
0x18001b380  jmp     loc_18001B448
0x18001b385  cmp     eax, 2
0x18001b388  jz      short loc_18001B3F6
0x18001b38a  mov     rcx, [rsp+0D8h]; this
0x18001b392  mov     r9d, eax; char *
0x18001b395  lea     r8, aOnecoreuapAdmi_18; "onecoreuap\\admin\\prov\\multivariant\\"...
0x18001b39c  mov     edx, 542h; void *
0x18001b3a1  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18001b3a6  mov     ebx, eax
0x18001b3a8  mov     rcx, [rsp+0D8h+hkey]; hKey
0x18001b3ad  test    rcx, rcx
0x18001b3b0  jz      short loc_18001B3B9
0x18001b3b2  call    cs:__imp_RegCloseKey
0x18001b3b8  nop
0x18001b3b9  cmp     [rsp+0D8h+var_68], 8
0x18001b3bf  jb      short loc_18001B3CC
0x18001b3c1  mov     rcx, [rsp+0D8h+var_80]
0x18001b3c6  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18001b3cc  mov     [rsp+0D8h+var_68], r15
0x18001b3d1  mov     [rsp+0D8h+var_70], r14
0x18001b3d6  mov     word ptr [rsp+0D8h+var_80], r14w
0x18001b3dc  cmp     [rsp+0D8h+var_48], 8
0x18001b3e5  jb      short loc_18001B3F2
0x18001b3e7  mov     rcx, [rsp+0D8h+lpSubKey]
0x18001b3ec  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18001b3f2  mov     eax, ebx
0x18001b3f4  jmp     short loc_18001B448
0x18001b3f6  mov     rcx, [rsp+0D8h+hkey]; hKey
0x18001b3fb  test    rcx, rcx
0x18001b3fe  jz      short loc_18001B407
0x18001b400  call    cs:__imp_RegCloseKey
0x18001b406  nop
0x18001b407  cmp     [rsp+0D8h+var_68], 8
0x18001b40d  jb      short loc_18001B41A
0x18001b40f  mov     rcx, [rsp+0D8h+var_80]
0x18001b414  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18001b41a  mov     [rsp+0D8h+var_68], r15
0x18001b41f  mov     [rsp+0D8h+var_70], r14
0x18001b424  mov     word ptr [rsp+0D8h+var_80], r14w
0x18001b42a  cmp     [rsp+0D8h+var_48], 8
0x18001b433  jb      short loc_18001B440
0x18001b435  mov     rcx, [rsp+0D8h+lpSubKey]
0x18001b43a  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18001b440  xor     eax, eax
0x18001b442  jmp     short loc_18001B448
0x18001b444  mov     eax, [rsp+0D8h+var_98]
0x18001b448  mov     rcx, [rsp+0D8h+var_20]
0x18001b450  xor     rcx, rsp; StackCookie
0x18001b453  call    __security_check_cookie
0x18001b458  lea     r11, [rsp+0D8h+var_18]
0x18001b460  mov     rbx, [r11+30h]
0x18001b464  mov     rsi, [r11+38h]
0x18001b468  mov     rsp, r11
0x18001b46b  pop     r15
0x18001b46d  pop     r14
0x18001b46f  pop     rdi
0x18001b470  retn
```
