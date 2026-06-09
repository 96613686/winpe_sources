# PackageInfo::isAdded(ProvPackage const &)

- ea: `0x180040cb0`
- end: `0x180040fcc`
- name: `?isAdded@PackageInfo@@QEAA_NAEBVProvPackage@@@Z`
- size: `796`
- prototype: `char __fastcall(HKEY *this, const struct ProvPackage *)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, registry_config`

## callers

- `0x180040584`

## callees

- `0x180001af4`
- `0x18000b030`
- `0x18000f840`
- `0x18002f9bc`
- `0x180040cb0`
- `0x180043750`
- `0x180047010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180040d35`
- `msvcrt!??3@YAXPEAX@Z` at `0x180040dd5`
- `msvcrt!??3@YAXPEAX@Z` at `0x180040e4d`
- `msvcrt!??3@YAXPEAX@Z` at `0x180040f56`
- `msvcrt!??3@YAXPEAX@Z` at `0x180040f84`
- `msvcrt!??3@YAXPEAX@Z` at `0x180040d35`
- `msvcrt!??3@YAXPEAX@Z` at `0x180040dd5`
- `msvcrt!??3@YAXPEAX@Z` at `0x180040e4d`
- `msvcrt!??3@YAXPEAX@Z` at `0x180040f56`
- `msvcrt!??3@YAXPEAX@Z` at `0x180040f84`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180040d8c`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180040d8c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180040d1d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180040d1d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180040e76`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180040f95`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180040e76`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180040f95`

## pseudocode

```c
// Hidden C++ exception states: #wind=2 #try_helpers=1
char __fastcall PackageInfo::isAdded(HKEY *this, const struct ProvPackage *a2)
{
  __int64 v4; // rax
  unsigned int v5; // edi
  unsigned int ValueW; // eax
  __int64 v7; // rdx
  unsigned __int64 v8; // r8
  unsigned int v9; // r8d
  const char *v10; // r9
  bool v11; // cc
  __int64 *v13; // rax
  __int64 *v14; // rax
  __int64 v15; // rcx
  __int64 v16; // r8
  __int64 v17; // r9
  __int64 *v18; // rdx
  __int64 **v19; // rsi
  __int64 *v20; // rdi
  __int64 v21; // rax
  __int64 v22; // rax
  __int64 **v23; // rbx
  __int64 v24; // rax
  __int64 v25; // rax
  __int64 **v26; // rax
  __int64 v27; // rcx
  __int64 v28; // r8
  __int64 v29; // r9
  unsigned int phkResult; // [rsp+20h] [rbp-2C8h]
  __int64 v31; // [rsp+0h] [rbp-2E8h] BYREF
  PHKEY phkResulta; // [rsp+20h] [rbp-2C8h]
  HKEY hkey; // [rsp+40h] [rbp-2A8h] BYREF
  __int64 *v34; // [rsp+48h] [rbp-2A0h] BYREF
  int v35; // [rsp+50h] [rbp-298h]
  int v36; // [rsp+54h] [rbp-294h]
  __int64 *v37; // [rsp+58h] [rbp-290h] BYREF
  DWORD pcbData; // [rsp+60h] [rbp-288h] BYREF
  __int64 *v39; // [rsp+68h] [rbp-280h] BYREF
  int v40; // [rsp+70h] [rbp-278h]
  unsigned int v41; // [rsp+74h] [rbp-274h]
  void *v42[2]; // [rsp+78h] [rbp-270h] BYREF
  __int64 v43; // [rsp+88h] [rbp-260h]
  unsigned __int64 v44; // [rsp+90h] [rbp-258h]
  void *v45[5]; // [rsp+98h] [rbp-250h] BYREF
  _WORD Src[264]; // [rsp+C0h] [rbp-228h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2E8h] [rbp+0h]

  v37 = (__int64 *)a2;
  hkey = 0;
  v4 = (*(__int64 (__fastcall **)(const struct ProvPackage *, void **))(*(_QWORD *)a2 + 16LL))(a2, v42);
  if ( *(_QWORD *)(v4 + 24) >= 8u )
    v4 = *(_QWORD *)v4;
  v5 = RegOpenKeyExW(*this, (LPCWSTR)v4, 0, 1u, &hkey);
  if ( v44 >= 8 )
    operator delete(v42[0]);
  if ( v5 == 2 )
    goto LABEL_34;
  if ( v5 )
    wil::details::in1diag3::_Throw_Win32(
      retaddr,
      (void *)0x57,
      (int)"onecoreuap\\admin\\prov\\lib\\packageinfo.cpp",
      (const char *)v5,
      (unsigned int)phkResulta);
  pcbData = 520;
  ValueW = RegGetValueW(hkey, 0, L"PackageVersion", 2u, 0, Src, &pcbData);
  if ( ValueW )
    wil::details::in1diag3::_Throw_Win32(
      retaddr,
      (void *)0x5C,
      (int)"onecoreuap\\admin\\prov\\lib\\packageinfo.cpp",
      (const char *)ValueW,
      (unsigned int)phkResulta);
  try
  {
    v7 = (*(__int64 (__fastcall **)(const struct ProvPackage *, void **))(*(_QWORD *)a2 + 24LL))(a2, v42);
    ProvPackage::PackageVersion::PackageVersion(&v39, v7);
    if ( v44 >= 8 )
      operator delete(v42[0]);
    v44 = 7;
    v43 = 0;
    LOWORD(v42[0]) = 0;
    if ( Src[0] )
    {
      v8 = -1;
      do
        ++v8;
      while ( Src[v8] );
    }
    else
    {
      v8 = 0;
    }
    std::wstring::assign(v42, (char *)Src, v8);
    ProvPackage::PackageVersion::PackageVersion(&v34, v42);
    if ( v44 >= 8 )
      operator delete(v42[0]);
  }
  catch ( ... )
  {
    v18 = &v31;
    if ( (unsigned int)dword_18005A000 > 3 )
    {
      if ( (unsigned __int8)tlgKeywordOn(&dword_18005A000, 0) )
      {
        v19 = (__int64 **)_tlgTypeMapBase<unsigned short *,void>::_tlgWrapAuto(&v34, Src);
        v20 = v37;
        v21 = (*(__int64 (__fastcall **)(__int64 *, void **))(*v37 + 24))(v37, v42);
        v22 = std::wstring::c_str(v21);
        v23 = (__int64 **)_tlgTypeMapBase<unsigned short *,void>::_tlgWrapAuto(&v37, v22);
        v24 = (*(__int64 (__fastcall **)(__int64 *, void **))(*v20 + 16))(v20, v45);
        v25 = std::wstring::c_str(v24);
        v26 = (__int64 **)_tlgTypeMapBase<unsigned short *,void>::_tlgWrapAuto(&v39, v25);
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
          v27,
          (__int64)&unk_180050600,
          v28,
          v29,
          v26,
          v23,
          v19);
        std::pair<std::wstring,unsigned long>::~pair<std::wstring,unsigned long>((__int64)v45);
        std::pair<std::wstring,unsigned long>::~pair<std::wstring,unsigned long>((__int64)v42);
      }
    }
    wil::details::in1diag3::Throw_Win32(retaddr, v18, v9, v10, phkResult);
  }
  v11 = (int)v39 <= (int)v34;
  if ( (_DWORD)v39 == (_DWORD)v34
    && (v11 = SHIDWORD(v39) <= SHIDWORD(v34), HIDWORD(v39) == HIDWORD(v34))
    && (v11 = v40 <= v35, v40 == v35) )
  {
    if ( (int)v41 > v36 )
    {
LABEL_25:
      if ( (unsigned int)dword_18005A000 > 5 )
      {
        v39 = (__int64 *)Src;
        v13 = (__int64 *)(*(__int64 (__fastcall **)(const struct ProvPackage *, void **, _QWORD))(*(_QWORD *)a2 + 24LL))(
                           a2,
                           v45,
                           v41);
        if ( (unsigned __int64)v13[3] >= 8 )
          v13 = (__int64 *)*v13;
        v34 = v13;
        v14 = (__int64 *)(*(__int64 (__fastcall **)(const struct ProvPackage *, void **))(*(_QWORD *)a2 + 16LL))(
                           a2,
                           v42);
        if ( (unsigned __int64)v14[3] >= 8 )
          v14 = (__int64 *)*v14;
        v37 = v14;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
          v15,
          (__int64)byte_180050643,
          v16,
          v17,
          &v37,
          &v34,
          &v39);
        if ( v44 >= 8 )
          operator delete(v42[0]);
        v44 = 7;
        v43 = 0;
        LOWORD(v42[0]) = 0;
        if ( v45[3] >= (void *)8 )
          operator delete(v45[0]);
      }
LABEL_34:
      if ( hkey )
        RegCloseKey(hkey);
      return 0;
    }
  }
  else if ( !v11 )
  {
    goto LABEL_25;
  }
  if ( hkey )
    RegCloseKey(hkey);
  return 1;
}

```

## disassembly

```asm
0x180040cb0  mov     [rsp+arg_10], rbx
0x180040cb5  mov     [rsp+arg_18], rsi
0x180040cba  push    rdi
0x180040cbb  sub     rsp, 2E0h
0x180040cc2  mov     rax, cs:__security_cookie
0x180040cc9  xor     rax, rsp
0x180040ccc  mov     [rsp+2E8h+var_18], rax
0x180040cd4  mov     rbx, rdx
0x180040cd7  mov     rdi, rcx
0x180040cda  mov     [rsp+2E8h+var_290], rdx
0x180040cdf  xor     esi, esi
0x180040ce1  mov     [rsp+2E8h+hkey], rsi
0x180040ce6  mov     rax, [rdx]
0x180040ce9  lea     rdx, [rsp+2E8h+var_270]
0x180040cee  mov     rcx, rbx
0x180040cf1  mov     rax, [rax+10h]
0x180040cf5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040cfa  cmp     qword ptr [rax+18h], 8
0x180040cff  jb      short loc_180040D04
0x180040d01  mov     rax, [rax]
0x180040d04  lea     rcx, [rsp+2E8h+hkey]
0x180040d09  mov     [rsp+2E8h+phkResult], rcx; unsigned int
0x180040d0e  mov     r9d, 1; samDesired
0x180040d14  xor     r8d, r8d; ulOptions
0x180040d17  mov     rdx, rax; lpSubKey
0x180040d1a  mov     rcx, [rdi]; hKey
0x180040d1d  call    cs:__imp_RegOpenKeyExW
0x180040d23  mov     edi, eax
0x180040d25  cmp     [rsp+2E8h+var_258], 8
0x180040d2e  jb      short loc_180040D3B
0x180040d30  mov     rcx, [rsp+2E8h+var_270]
0x180040d35  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180040d3b  mov     r9d, 2; dwFlags
0x180040d41  cmp     edi, r9d
0x180040d44  jz      loc_180040F8B
0x180040d4a  mov     rcx, [rsp+2E8h]; this
0x180040d52  test    edi, edi
0x180040d54  jnz     loc_180040FA2
0x180040d5a  mov     [rsp+2E8h+var_288], 208h
0x180040d62  lea     rax, [rsp+2E8h+var_288]
0x180040d67  mov     [rsp+2E8h+pcbData], rax; pcbData
0x180040d6c  lea     rax, [rsp+2E8h+Src]
0x180040d74  mov     [rsp+2E8h+pvData], rax; pvData
0x180040d79  mov     [rsp+2E8h+phkResult], rsi; unsigned int
0x180040d7e  lea     r8, aPackageversion; "PackageVersion"
0x180040d85  xor     edx, edx; lpSubKey
0x180040d87  mov     rcx, [rsp+2E8h+hkey]; hkey
0x180040d8c  call    cs:__imp_RegGetValueW
0x180040d92  mov     rcx, [rsp+2E8h]; this
0x180040d9a  test    eax, eax
0x180040d9c  jnz     loc_180040FB7
0x180040da2  mov     rax, [rbx]
0x180040da5  lea     rdx, [rsp+2E8h+var_270]
0x180040daa  mov     rcx, rbx
0x180040dad  mov     rax, [rax+18h]
0x180040db1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040db6  nop
0x180040db7  mov     rdx, rax
0x180040dba  lea     rcx, [rsp+2E8h+var_280]
0x180040dbf  call    ??0PackageVersion@ProvPackage@@QEAA@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; ProvPackage::PackageVersion::PackageVersion(std::wstring const &)
0x180040dc4  nop
0x180040dc5  cmp     [rsp+2E8h+var_258], 8
0x180040dce  jb      short loc_180040DDB
0x180040dd0  mov     rcx, [rsp+2E8h+var_270]
0x180040dd5  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180040ddb  mov     edi, 7
0x180040de0  mov     [rsp+2E8h+var_258], rdi
0x180040de8  mov     [rsp+2E8h+var_260], rsi
0x180040df0  mov     word ptr [rsp+2E8h+var_270], si
0x180040df5  cmp     [rsp+2E8h+Src], si
0x180040dfd  jnz     short loc_180040E04
0x180040dff  mov     r8, rsi
0x180040e02  jmp     short loc_180040E1A
0x180040e04  lea     rax, [rsp+2E8h+Src]
0x180040e0c  or      r8, 0FFFFFFFFFFFFFFFFh
0x180040e10  inc     r8
0x180040e13  cmp     [rax+r8*2], si
0x180040e18  jnz     short loc_180040E10
0x180040e1a  lea     rdx, [rsp+2E8h+Src]; Src
0x180040e22  lea     rcx, [rsp+2E8h+var_270]; void *
0x180040e27  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::assign(ushort const *,unsigned __int64)
0x180040e2c  nop
0x180040e2d  lea     rdx, [rsp+2E8h+var_270]
0x180040e32  lea     rcx, [rsp+2E8h+var_2A0]
0x180040e37  call    ??0PackageVersion@ProvPackage@@QEAA@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; ProvPackage::PackageVersion::PackageVersion(std::wstring const &)
0x180040e3c  nop
0x180040e3d  cmp     [rsp+2E8h+var_258], 8
0x180040e46  jb      short loc_180040E53
0x180040e48  mov     rcx, [rsp+2E8h+var_270]
0x180040e4d  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180040e53  mov     edx, dword ptr [rsp+2E8h+var_280]
0x180040e57  mov     ecx, dword ptr [rsp+2E8h+var_280+4]
0x180040e5b  mov     eax, [rsp+2E8h+var_278]
0x180040e5f  mov     r8d, [rsp+2E8h+var_274]
0x180040e64  cmp     edx, dword ptr [rsp+2E8h+var_2A0]
0x180040e68  jz      short loc_180040EA3
0x180040e6a  jg      short loc_180040EB6
0x180040e6c  mov     rcx, [rsp+2E8h+hkey]; hKey
0x180040e71  test    rcx, rcx
0x180040e74  jz      short loc_180040E7C
0x180040e76  call    cs:__imp_RegCloseKey
0x180040e7c  mov     al, 1
0x180040e7e  mov     rcx, [rsp+2E8h+var_18]
0x180040e86  xor     rcx, rsp; StackCookie
0x180040e89  call    __security_check_cookie
0x180040e8e  lea     r11, [rsp+2E8h+var_8]
0x180040e96  mov     rbx, [r11+20h]
0x180040e9a  mov     rsi, [r11+28h]
0x180040e9e  mov     rsp, r11
0x180040ea1  pop     rdi
0x180040ea2  retn
0x180040ea3  cmp     ecx, dword ptr [rsp+2E8h+var_2A0+4]
0x180040ea7  jnz     short loc_180040E6A
0x180040ea9  cmp     eax, [rsp+2E8h+var_298]
0x180040ead  jnz     short loc_180040E6A
0x180040eaf  cmp     r8d, [rsp+2E8h+var_294]
0x180040eb4  jle     short loc_180040E6C
0x180040eb6  mov     eax, cs:dword_18005A000
0x180040ebc  cmp     eax, 5
0x180040ebf  jbe     loc_180040F8B
0x180040ec5  lea     rax, [rsp+2E8h+Src]
0x180040ecd  mov     [rsp+2E8h+var_280], rax
0x180040ed2  mov     rax, [rbx]
0x180040ed5  lea     rdx, [rsp+2E8h+var_250]
0x180040edd  mov     rcx, rbx
0x180040ee0  mov     rax, [rax+18h]
0x180040ee4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040ee9  nop
0x180040eea  cmp     qword ptr [rax+18h], 8
0x180040eef  jb      short loc_180040EF4
0x180040ef1  mov     rax, [rax]
0x180040ef4  mov     [rsp+2E8h+var_2A0], rax
0x180040ef9  mov     rax, [rbx]
0x180040efc  lea     rdx, [rsp+2E8h+var_270]
0x180040f01  mov     rcx, rbx
0x180040f04  mov     rax, [rax+10h]
0x180040f08  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040f0d  cmp     qword ptr [rax+18h], 8
0x180040f12  jb      short loc_180040F17
0x180040f14  mov     rax, [rax]
0x180040f17  mov     [rsp+2E8h+var_290], rax
0x180040f1c  lea     rax, [rsp+2E8h+var_280]
0x180040f21  mov     [rsp+2E8h+pcbData], rax
0x180040f26  lea     rax, [rsp+2E8h+var_2A0]
0x180040f2b  mov     [rsp+2E8h+pvData], rax
0x180040f30  lea     rax, [rsp+2E8h+var_290]
0x180040f35  mov     [rsp+2E8h+phkResult], rax
0x180040f3a  lea     rdx, byte_180050643
0x180040f41  call    ??$Write@U?$_tlgWrapSz@G@@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@33@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x180040f46  cmp     [rsp+2E8h+var_258], 8
0x180040f4f  jb      short loc_180040F5C
0x180040f51  mov     rcx, [rsp+2E8h+var_270]
0x180040f56  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180040f5c  mov     [rsp+2E8h+var_258], rdi
0x180040f64  mov     [rsp+2E8h+var_260], rsi
0x180040f6c  mov     word ptr [rsp+2E8h+var_270], si
0x180040f71  cmp     [rsp+2E8h+var_238], 8
0x180040f7a  jb      short loc_180040F8B
0x180040f7c  mov     rcx, [rsp+2E8h+var_250]
0x180040f84  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180040f8a  nop
0x180040f8b  mov     rcx, [rsp+2E8h+hkey]; hKey
0x180040f90  test    rcx, rcx
0x180040f93  jz      short loc_180040F9B
0x180040f95  call    cs:__imp_RegCloseKey
0x180040f9b  xor     al, al
0x180040f9d  jmp     loc_180040E7E
0x180040fa2  mov     r9d, edi; char *
0x180040fa5  lea     r8, aOnecoreuapAdmi_25; "onecoreuap\\admin\\prov\\lib\\packagein"...
0x180040fac  mov     edx, 57h ; 'W'; void *
0x180040fb1  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x180040fb7  mov     r9d, eax; char *
0x180040fba  lea     r8, aOnecoreuapAdmi_25; "onecoreuap\\admin\\prov\\lib\\packagein"...
0x180040fc1  mov     edx, 5Ch ; '\'; void *
0x180040fc6  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
```
