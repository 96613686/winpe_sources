# MdmLogCollector::CollectRegistryEntries(_iobuf *,ushort const *)

- ea: `0x18010c120`
- end: `0x18010c554`
- name: `?CollectRegistryEntries@MdmLogCollector@@AEAAJPEAU_iobuf@@PEBG@Z`
- size: `1076`
- prototype: `int(MdmLogCollector *__hidden this, struct _iobuf *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops, authz_impersonation, registry_config`

## callers

- `0x18010a908`

## callees

- `0x180019000`
- `0x1800e66dc`
- `0x1800e7124`
- `0x1800e7c08`
- `0x1800e82e4`
- `0x1800ef188`
- `0x1800ef5d8`
- `0x1800ef900`
- `0x1800f9558`
- `0x18010440c`
- `0x18010c120`
- `0x18010e23c`
- `0x1801109fc`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18010c2f1`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18010c2f1`
- `api-ms-win-crt-private-l1-1-0!_o__wfopen_s` at `0x18010c19d`
- `api-ms-win-crt-private-l1-1-0!_o__wfopen_s` at `0x18010c19d`
- `api-ms-win-crt-private-l1-1-0!_o_fclose` at `0x18010c517`
- `api-ms-win-crt-private-l1-1-0!_o_fclose` at `0x18010c517`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18010c177`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18010c177`
- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x18010c38f`
- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x18010c38f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18010c36c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18010c36c`
- `DMCmnUtils!DmGetActiveUserSid` at `0x18010c236`
- `DMCmnUtils!DmGetActiveUserSid` at `0x18010c236`
- `DMCmnUtils!DmRevertToSelf` at `0x18010c46c`
- `DMCmnUtils!DmRevertToSelf` at `0x18010c46c`
- `DMCmnUtils!DmImpersonate` at `0x18010c300`
- `DMCmnUtils!DmImpersonate` at `0x18010c300`
- `DMCmnUtils!DmGetCurrentUserSid` at `0x18010c297`
- `DMCmnUtils!DmGetCurrentUserSid` at `0x18010c297`

## string_xrefs

- `0x18010c159`: `MdmDiagReport_RegistryDump.reg`
- `0x18010c250`: `Failed (HResult:0x%08x) to dump HKLM registry - DmGetActiveUserSid :%s\n`
- `0x18010c1b9`: `Failed (err:%d) to create registry dump output file:%s\n`
- `0x18010c31a`: `Failed (HResult:0x%08x) to dump HKLM registry - DmImpersonate :%s\n`
- `0x18010c2b1`: `Failed (HResult:0x%08x) to dump HKLM registry - DmGetCurrentUserSid :%s\n`
- `0x18010c41c`: `Succeeded to dump HKCU registry:%s\n`
- `0x18010c3b6`: `Failed (HResult:0x%08x) to dump HKLM registry - RegOpenCurrentUser :%s\n`
- `0x18010c482`: `--- %d HKCU registry entries are collected\n`
- `0x18010c430`: `Failed (HResult:0x%08x) to dump HKCU registry:%s\n`
- `0x18010c4e8`: `Failed (HResult:0x%08x) to dump HKLM registry:%s\n`
- `0x18010c4d4`: `Succeeded to dump HKLM registry:%s\n`
- `0x18010c4ff`: `--- %d HKLM registry entries are collected\n`

## pseudocode

```c
// Hidden C++ exception states: #wind=7 #try_helpers=1
__int64 __fastcall MdmLogCollector::CollectRegistryEntries(
        MdmLogCollector *this,
        struct _iobuf *a2,
        const unsigned __int16 *a3)
{
  const WCHAR *v5; // rax
  const wchar_t *v6; // rax
  errno_t v7; // ebx
  __int64 v8; // rax
  unsigned int v10; // r15d
  __int64 v11; // rsi
  __int64 v12; // r13
  int ActiveUserSid; // edi
  __int64 v14; // rax
  int CurrentUserSid; // edi
  __int64 v16; // rax
  int v17; // edi
  __int64 v18; // rax
  HKEY v19; // rdi
  LSTATUS v20; // eax
  signed int v21; // edi
  const unsigned __int16 *v22; // rax
  HKEY v23; // rdx
  int v24; // edi
  __int64 v25; // rax
  unsigned int v26; // esi
  __int64 v27; // rdi
  __int64 v28; // r12
  const unsigned __int16 *v29; // r8
  int v30; // r15d
  __int64 v31; // rax
  char v32; // [rsp+20h] [rbp-B8h] BYREF
  unsigned __int16 *v33; // [rsp+28h] [rbp-B0h] BYREF
  HKEY hKey; // [rsp+30h] [rbp-A8h] BYREF
  unsigned __int16 *v35; // [rsp+38h] [rbp-A0h] BYREF
  FILE *Stream[2]; // [rsp+40h] [rbp-98h] BYREF
  char v37; // [rsp+50h] [rbp-88h]
  _BYTE v38[8]; // [rsp+58h] [rbp-80h] BYREF
  FILE **v39; // [rsp+60h] [rbp-78h]
  char v40; // [rsp+68h] [rbp-70h]
  _BYTE v41[32]; // [rsp+70h] [rbp-68h] BYREF

  std::wstring::wstring(v41, a3);
  std::wstring::append(v41, L"MdmDiagReport_RegistryDump.reg");
  v5 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v41);
  DeleteFileW(v5);
  Stream[0] = 0;
  v6 = (const wchar_t *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v41);
  v7 = _wfopen_s(Stream, v6, L"a+");
  if ( v7 > 0 )
  {
    v8 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v41);
    MdmLogCollector::WriteToFile(a2, L"Failed (err:%d) to create registry dump output file:%s\n", (unsigned int)v7, v8);
    std::wstring::_Tidy_deallocate(v41);
    return 2147549183LL;
  }
  v39 = Stream;
  v40 = 1;
  v10 = 0;
  v11 = *((_QWORD *)this + 7);
  v12 = *((_QWORD *)this + 8);
  while ( v11 != v12 )
  {
    v32 = 0;
    Stream[1] = (FILE *)&v32;
    v37 = 1;
    hKey = 0;
    v33 = 0;
    v35 = 0;
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
      &v33,
      0);
    ActiveUserSid = DmGetActiveUserSid(&v33);
    if ( ActiveUserSid < 0 )
    {
      v14 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v11);
      MdmLogCollector::WriteToFile(
        a2,
        L"Failed (HResult:0x%08x) to dump HKLM registry - DmGetActiveUserSid :%s\n",
        (unsigned int)ActiveUserSid,
        v14);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v35);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v33);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
      goto LABEL_25;
    }
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
      &v35,
      0);
    CurrentUserSid = DmGetCurrentUserSid(&v35);
    if ( CurrentUserSid < 0 )
    {
      v16 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v11);
      MdmLogCollector::WriteToFile(
        a2,
        L"Failed (HResult:0x%08x) to dump HKLM registry - DmGetCurrentUserSid :%s\n",
        (unsigned int)CurrentUserSid,
        v16);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v35);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v33);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
      goto LABEL_25;
    }
    if ( (unsigned int)_o__wcsicmp(v35, v33) )
    {
      v17 = DmImpersonate(v33);
      if ( v17 < 0 )
      {
        v18 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v11);
        MdmLogCollector::WriteToFile(
          a2,
          L"Failed (HResult:0x%08x) to dump HKLM registry - DmImpersonate :%s\n",
          (unsigned int)v17,
          v18);
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v35);
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v33);
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
        goto LABEL_25;
      }
      v32 = 1;
    }
    v19 = hKey;
    if ( hKey )
    {
      wil::last_error_context::last_error_context((wil::last_error_context *)v38);
      RegCloseKey(v19);
      wil::last_error_context::~last_error_context((wil::last_error_context *)v38);
    }
    hKey = 0;
    v20 = RegOpenCurrentUser(0x20019u, &hKey);
    v21 = v20;
    if ( v20 > 0 )
      v21 = (unsigned __int16)v20 | 0x80070000;
    v22 = (const unsigned __int16 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v11);
    if ( v21 >= 0 )
    {
      v23 = HKEY_CURRENT_USER;
      if ( v32 )
        v23 = hKey;
      v24 = MdmLogCollector::DumpRegistryKey(Stream[0], v23, v22);
      v25 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v11);
      if ( v24 < 0 )
        MdmLogCollector::WriteToFile(a2, L"Failed (HResult:0x%08x) to dump HKCU registry:%s\n", (unsigned int)v24, v25);
      else
        MdmLogCollector::WriteToFile(a2, L"Succeeded to dump HKCU registry:%s\n", v25);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v35);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v33);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
    }
    else
    {
      MdmLogCollector::WriteToFile(
        a2,
        L"Failed (HResult:0x%08x) to dump HKLM registry - RegOpenCurrentUser :%s\n",
        (unsigned int)v21,
        v22);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v35);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v33);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
    }
LABEL_25:
    v37 = 0;
    if ( v32 )
      DmRevertToSelf();
    ++v10;
    v11 += 32;
  }
  MdmLogCollector::WriteToFile(a2, L"--- %d HKCU registry entries are collected\n", v10);
  v26 = 0;
  v27 = *((_QWORD *)this + 10);
  v28 = *((_QWORD *)this + 11);
  while ( v27 != v28 )
  {
    v29 = (const unsigned __int16 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v27);
    v30 = MdmLogCollector::DumpRegistryKey(Stream[0], HKEY_LOCAL_MACHINE, v29);
    v31 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v27);
    if ( v30 < 0 )
      MdmLogCollector::WriteToFile(a2, L"Failed (HResult:0x%08x) to dump HKLM registry:%s\n", (unsigned int)v30, v31);
    else
      MdmLogCollector::WriteToFile(a2, L"Succeeded to dump HKLM registry:%s\n", v31);
    ++v26;
    v27 += 32;
  }
  MdmLogCollector::WriteToFile(a2, L"--- %d HKLM registry entries are collected\n", v26);
  if ( Stream[0] )
    fclose(Stream[0]);
  std::wstring::_Tidy_deallocate(v41);
  return 0;
}

```

## disassembly

```asm
0x18010c120  push    rbx
0x18010c122  push    rsi
0x18010c123  push    rdi
0x18010c124  push    r12
0x18010c126  push    r13
0x18010c128  push    r14
0x18010c12a  push    r15
0x18010c12c  sub     rsp, 0A0h
0x18010c133  mov     rax, cs:__security_cookie
0x18010c13a  xor     rax, rsp
0x18010c13d  mov     [rsp+0D8h+var_48], rax
0x18010c145  mov     r14, rdx
0x18010c148  mov     r12, rcx
0x18010c14b  mov     rdx, r8
0x18010c14e  lea     rcx, [rsp+0D8h+var_68]
0x18010c153  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18010c158  nop
0x18010c159  lea     rdx, aMdmdiagreportR; "MdmDiagReport_RegistryDump.reg"
0x18010c160  lea     rcx, [rsp+0D8h+var_68]
0x18010c165  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x18010c16a  lea     rcx, [rsp+0D8h+var_68]
0x18010c16f  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18010c174  mov     rcx, rax; lpFileName
0x18010c177  call    cs:__imp_DeleteFileW
0x18010c17d  xor     edi, edi
0x18010c17f  mov     [rsp+0D8h+Stream], rdi
0x18010c184  lea     rcx, [rsp+0D8h+var_68]
0x18010c189  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18010c18e  mov     rdx, rax; FileName
0x18010c191  lea     r8, aA; "a+"
0x18010c198  lea     rcx, [rsp+0D8h+Stream]; Stream
0x18010c19d  call    cs:__imp__wfopen_s
0x18010c1a3  mov     ebx, eax
0x18010c1a5  test    eax, eax
0x18010c1a7  jle     short loc_18010C1DD
0x18010c1a9  lea     rcx, [rsp+0D8h+var_68]
0x18010c1ae  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18010c1b3  mov     r9, rax
0x18010c1b6  mov     r8d, ebx
0x18010c1b9  lea     rdx, aFailedErrDToCr; "Failed (err:%d) to create registry dump"...
0x18010c1c0  mov     rcx, r14; struct _iobuf *
0x18010c1c3  call    ?WriteToFile@MdmLogCollector@@CAXPEAU_iobuf@@PEBGZZ; MdmLogCollector::WriteToFile(_iobuf *,ushort const *,...)
0x18010c1c8  nop
0x18010c1c9  lea     rcx, [rsp+0D8h+var_68]
0x18010c1ce  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18010c1d3  mov     eax, 8000FFFFh
0x18010c1d8  jmp     loc_18010C530
0x18010c1dd  lea     rbx, [rsp+0D8h+Stream]
0x18010c1e2  mov     [rsp+0D8h+var_78], rbx
0x18010c1e7  mov     [rsp+0D8h+var_70], 1
0x18010c1ec  mov     r15d, edi
0x18010c1ef  mov     rsi, [r12+38h]
0x18010c1f4  mov     r13, [r12+40h]
0x18010c1f9  cmp     rsi, r13
0x18010c1fc  jz      loc_18010C47F
0x18010c202  mov     [rsp+0D8h+var_B8], dil
0x18010c207  lea     rax, [rsp+0D8h+var_B8]
0x18010c20c  mov     [rsp+0D8h+var_90], rax
0x18010c211  mov     [rsp+0D8h+var_88], 1
0x18010c216  mov     [rsp+0D8h+hKey], rdi
0x18010c21b  mov     [rsp+0D8h+var_B0], rdi
0x18010c220  mov     [rsp+0D8h+var_A0], rdi
0x18010c225  xor     edx, edx
0x18010c227  lea     rcx, [rsp+0D8h+var_B0]
0x18010c22c  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18010c231  lea     rcx, [rsp+0D8h+var_B0]
0x18010c236  call    cs:__imp_?DmGetActiveUserSid@@YAJPEAPEAG@Z; DmGetActiveUserSid(ushort * *)
0x18010c23c  mov     edi, eax
0x18010c23e  test    eax, eax
0x18010c240  jns     short loc_18010C286
0x18010c242  mov     rcx, rsi
0x18010c245  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18010c24a  mov     r9, rax
0x18010c24d  mov     r8d, edi
0x18010c250  lea     rdx, aFailedHresult0_2; "Failed (HResult:0x%08x) to dump HKLM re"...
0x18010c257  mov     rcx, r14; struct _iobuf *
0x18010c25a  call    ?WriteToFile@MdmLogCollector@@CAXPEAU_iobuf@@PEBGZZ; MdmLogCollector::WriteToFile(_iobuf *,ushort const *,...)
0x18010c25f  nop
0x18010c260  lea     rcx, [rsp+0D8h+var_A0]
0x18010c265  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18010c26a  nop
0x18010c26b  lea     rcx, [rsp+0D8h+var_B0]
0x18010c270  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18010c275  nop
0x18010c276  lea     rcx, [rsp+0D8h+hKey]
0x18010c27b  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18010c280  nop
0x18010c281  jmp     loc_18010C45E
0x18010c286  xor     edx, edx
0x18010c288  lea     rcx, [rsp+0D8h+var_A0]
0x18010c28d  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18010c292  lea     rcx, [rsp+0D8h+var_A0]
0x18010c297  call    cs:__imp_?DmGetCurrentUserSid@@YAJPEAPEAG@Z; DmGetCurrentUserSid(ushort * *)
0x18010c29d  mov     edi, eax
0x18010c29f  test    eax, eax
0x18010c2a1  jns     short loc_18010C2E7
0x18010c2a3  mov     rcx, rsi
0x18010c2a6  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18010c2ab  mov     r9, rax
0x18010c2ae  mov     r8d, edi
0x18010c2b1  lea     rdx, aFailedHresult0_6; "Failed (HResult:0x%08x) to dump HKLM re"...
0x18010c2b8  mov     rcx, r14; struct _iobuf *
0x18010c2bb  call    ?WriteToFile@MdmLogCollector@@CAXPEAU_iobuf@@PEBGZZ; MdmLogCollector::WriteToFile(_iobuf *,ushort const *,...)
0x18010c2c0  nop
0x18010c2c1  lea     rcx, [rsp+0D8h+var_A0]
0x18010c2c6  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18010c2cb  nop
0x18010c2cc  lea     rcx, [rsp+0D8h+var_B0]
0x18010c2d1  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18010c2d6  nop
0x18010c2d7  lea     rcx, [rsp+0D8h+hKey]
0x18010c2dc  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18010c2e1  nop
0x18010c2e2  jmp     loc_18010C45E
0x18010c2e7  mov     rdx, [rsp+0D8h+var_B0]
0x18010c2ec  mov     rcx, [rsp+0D8h+var_A0]
0x18010c2f1  call    cs:__imp__o__wcsicmp
0x18010c2f7  test    eax, eax
0x18010c2f9  jz      short loc_18010C355
0x18010c2fb  mov     rcx, [rsp+0D8h+var_B0]
0x18010c300  call    cs:__imp_?DmImpersonate@@YAJPEBG@Z; DmImpersonate(ushort const *)
0x18010c306  mov     edi, eax
0x18010c308  test    eax, eax
0x18010c30a  jns     short loc_18010C350
0x18010c30c  mov     rcx, rsi
0x18010c30f  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18010c314  mov     r9, rax
0x18010c317  mov     r8d, edi
0x18010c31a  lea     rdx, aFailedHresult0_4; "Failed (HResult:0x%08x) to dump HKLM re"...
0x18010c321  mov     rcx, r14; struct _iobuf *
0x18010c324  call    ?WriteToFile@MdmLogCollector@@CAXPEAU_iobuf@@PEBGZZ; MdmLogCollector::WriteToFile(_iobuf *,ushort const *,...)
0x18010c329  nop
0x18010c32a  lea     rcx, [rsp+0D8h+var_A0]
0x18010c32f  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18010c334  nop
0x18010c335  lea     rcx, [rsp+0D8h+var_B0]
0x18010c33a  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18010c33f  nop
0x18010c340  lea     rcx, [rsp+0D8h+hKey]
0x18010c345  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18010c34a  nop
0x18010c34b  jmp     loc_18010C45E
0x18010c350  mov     [rsp+0D8h+var_B8], 1
0x18010c355  mov     rdi, [rsp+0D8h+hKey]
0x18010c35a  test    rdi, rdi
0x18010c35d  jz      short loc_18010C37C
0x18010c35f  lea     rcx, [rsp+0D8h+var_80]; this
0x18010c364  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18010c369  mov     rcx, rdi; hKey
0x18010c36c  call    cs:__imp_RegCloseKey
0x18010c372  lea     rcx, [rsp+0D8h+var_80]; this
0x18010c377  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18010c37c  mov     [rsp+0D8h+hKey], 0
0x18010c385  lea     rdx, [rsp+0D8h+hKey]; phkResult
0x18010c38a  mov     ecx, 20019h; samDesired
0x18010c38f  call    cs:__imp_RegOpenCurrentUser
0x18010c395  mov     edi, eax
0x18010c397  test    eax, eax
0x18010c399  jle     short loc_18010C3A4
0x18010c39b  movzx   edi, ax
0x18010c39e  or      edi, 80070000h
0x18010c3a4  mov     rcx, rsi
0x18010c3a7  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18010c3ac  test    edi, edi
0x18010c3ae  jns     short loc_18010C3E9
0x18010c3b0  mov     r9, rax
0x18010c3b3  mov     r8d, edi
0x18010c3b6  lea     rdx, aFailedHresult0_5; "Failed (HResult:0x%08x) to dump HKLM re"...
0x18010c3bd  mov     rcx, r14; struct _iobuf *
0x18010c3c0  call    ?WriteToFile@MdmLogCollector@@CAXPEAU_iobuf@@PEBGZZ; MdmLogCollector::WriteToFile(_iobuf *,ushort const *,...)
0x18010c3c5  nop
0x18010c3c6  lea     rcx, [rsp+0D8h+var_A0]
0x18010c3cb  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18010c3d0  nop
0x18010c3d1  lea     rcx, [rsp+0D8h+var_B0]
0x18010c3d6  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18010c3db  nop
0x18010c3dc  lea     rcx, [rsp+0D8h+hKey]
0x18010c3e1  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18010c3e6  nop
0x18010c3e7  jmp     short loc_18010C45E
0x18010c3e9  mov     rdx, 0FFFFFFFF80000001h
0x18010c3f0  cmp     [rsp+0D8h+var_B8], 0
0x18010c3f5  cmovnz  rdx, [rsp+0D8h+hKey]; HKEY
0x18010c3fb  mov     r8, rax; unsigned __int16 *
0x18010c3fe  mov     rcx, [rsp+0D8h+Stream]; struct _iobuf *
0x18010c403  call    ?DumpRegistryKey@MdmLogCollector@@CAJPEAU_iobuf@@PEAUHKEY__@@PEBG@Z; MdmLogCollector::DumpRegistryKey(_iobuf *,HKEY__ *,ushort const *)
0x18010c408  mov     edi, eax
0x18010c40a  mov     rcx, rsi
0x18010c40d  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18010c412  mov     rcx, r14; struct _iobuf *
0x18010c415  test    edi, edi
0x18010c417  js      short loc_18010C42A
0x18010c419  mov     r8, rax
0x18010c41c  lea     rdx, aSucceededToDum_0; "Succeeded to dump HKCU registry:%s\n"
0x18010c423  call    ?WriteToFile@MdmLogCollector@@CAXPEAU_iobuf@@PEBGZZ; MdmLogCollector::WriteToFile(_iobuf *,ushort const *,...)
0x18010c428  jmp     short loc_18010C43D
0x18010c42a  mov     r9, rax
0x18010c42d  mov     r8d, edi
0x18010c430  lea     rdx, aFailedHresult0_8; "Failed (HResult:0x%08x) to dump HKCU re"...
0x18010c437  call    ?WriteToFile@MdmLogCollector@@CAXPEAU_iobuf@@PEBGZZ; MdmLogCollector::WriteToFile(_iobuf *,ushort const *,...)
0x18010c43c  nop
0x18010c43d  lea     rcx, [rsp+0D8h+var_A0]
0x18010c442  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18010c447  nop
0x18010c448  lea     rcx, [rsp+0D8h+var_B0]
0x18010c44d  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18010c452  nop
0x18010c453  lea     rcx, [rsp+0D8h+hKey]
0x18010c458  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18010c45d  nop
0x18010c45e  xor     edi, edi
0x18010c460  mov     [rsp+0D8h+var_88], dil
0x18010c465  cmp     [rsp+0D8h+var_B8], dil
0x18010c46a  jz      short loc_18010C473
0x18010c46c  call    cs:__imp_?DmRevertToSelf@@YAJXZ; DmRevertToSelf(void)
0x18010c472  nop
0x18010c473  inc     r15d
0x18010c476  add     rsi, 20h ; ' '
0x18010c47a  jmp     loc_18010C1F9
0x18010c47f  mov     r8d, r15d
0x18010c482  lea     rdx, aDHkcuRegistryE; "--- %d HKCU registry entries are collec"...
0x18010c489  mov     rcx, r14; struct _iobuf *
0x18010c48c  call    ?WriteToFile@MdmLogCollector@@CAXPEAU_iobuf@@PEBGZZ; MdmLogCollector::WriteToFile(_iobuf *,ushort const *,...)
0x18010c491  mov     esi, edi
0x18010c493  mov     rdi, [r12+50h]
0x18010c498  mov     r12, [r12+58h]
0x18010c49d  cmp     rdi, r12
0x18010c4a0  jz      short loc_18010C4FC
0x18010c4a2  mov     rcx, rdi
0x18010c4a5  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18010c4aa  mov     r8, rax; unsigned __int16 *
0x18010c4ad  mov     rdx, 0FFFFFFFF80000002h; HKEY
0x18010c4b4  mov     rcx, [rsp+0D8h+Stream]; struct _iobuf *
0x18010c4b9  call    ?DumpRegistryKey@MdmLogCollector@@CAJPEAU_iobuf@@PEAUHKEY__@@PEBG@Z; MdmLogCollector::DumpRegistryKey(_iobuf *,HKEY__ *,ushort const *)
0x18010c4be  mov     r15d, eax
0x18010c4c1  mov     rcx, rdi
0x18010c4c4  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18010c4c9  mov     rcx, r14; struct _iobuf *
0x18010c4cc  test    r15d, r15d
0x18010c4cf  js      short loc_18010C4E2
0x18010c4d1  mov     r8, rax
0x18010c4d4  lea     rdx, aSucceededToDum; "Succeeded to dump HKLM registry:%s\n"
0x18010c4db  call    ?WriteToFile@MdmLogCollector@@CAXPEAU_iobuf@@PEBGZZ; MdmLogCollector::WriteToFile(_iobuf *,ushort const *,...)
0x18010c4e0  jmp     short loc_18010C4F4
0x18010c4e2  mov     r9, rax
0x18010c4e5  mov     r8d, r15d
0x18010c4e8  lea     rdx, aFailedHresult0_3; "Failed (HResult:0x%08x) to dump HKLM re"...
0x18010c4ef  call    ?WriteToFile@MdmLogCollector@@CAXPEAU_iobuf@@PEBGZZ; MdmLogCollector::WriteToFile(_iobuf *,ushort const *,...)
0x18010c4f4  inc     esi
0x18010c4f6  add     rdi, 20h ; ' '
0x18010c4fa  jmp     short loc_18010C49D
0x18010c4fc  mov     r8d, esi
0x18010c4ff  lea     rdx, aDHklmRegistryE; "--- %d HKLM registry entries are collec"...
0x18010c506  mov     rcx, r14; struct _iobuf *
0x18010c509  call    ?WriteToFile@MdmLogCollector@@CAXPEAU_iobuf@@PEBGZZ; MdmLogCollector::WriteToFile(_iobuf *,ushort const *,...)
0x18010c50e  nop
0x18010c50f  mov     rcx, [rbx]; Stream
0x18010c512  test    rcx, rcx
0x18010c515  jz      short loc_18010C51E
0x18010c517  call    cs:__imp_fclose
0x18010c51d  nop
0x18010c51e  lea     rcx, [rsp+0D8h+var_68]
0x18010c523  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18010c528  xor     eax, eax
0x18010c52a  jmp     short loc_18010C530
0x18010c52c  mov     eax, dword ptr [rsp+0D8h+var_B0]
0x18010c530  mov     rcx, [rsp+0D8h+var_48]
0x18010c538  xor     rcx, rsp; StackCookie
0x18010c53b  call    __security_check_cookie
0x18010c540  add     rsp, 0A0h
0x18010c547  pop     r15
0x18010c549  pop     r14
0x18010c54b  pop     r13
0x18010c54d  pop     r12
0x18010c54f  pop     rdi
0x18010c550  pop     rsi
0x18010c551  pop     rbx
0x18010c552  retn
```
