# MdmLogCollector::CollectRegistryEntries(_iobuf *,ushort const *)

- ea: `0x18010d5a0`
- end: `0x18010da10`
- name: `?CollectRegistryEntries@MdmLogCollector@@AEAAJPEAU_iobuf@@PEBG@Z`
- size: `1136`
- prototype: `int(MdmLogCollector *__hidden this, struct _iobuf *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops, authz_impersonation, registry_config`

## callers

- `0x18010bd00`

## callees

- `0x180019080`
- `0x1800e68b0`
- `0x1800e734c`
- `0x1800e7de8`
- `0x1800e8508`
- `0x1800ef8c4`
- `0x1800efd9c`
- `0x1800f00e4`
- `0x1800fa538`
- `0x18010562c`
- `0x18010d5a0`
- `0x18010f7ac`
- `0x180111ec4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18010d789`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18010d789`
- `api-ms-win-crt-private-l1-1-0!_o__wfopen_s` at `0x18010d623`
- `api-ms-win-crt-private-l1-1-0!_o__wfopen_s` at `0x18010d623`
- `api-ms-win-crt-private-l1-1-0!_o_fclose` at `0x18010d9cd`
- `api-ms-win-crt-private-l1-1-0!_o_fclose` at `0x18010d9cd`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18010d5f7`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18010d5f7`
- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x18010d839`
- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x18010d839`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18010d810`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18010d810`
- `DMCmnUtils!DmGetActiveUserSid` at `0x18010d6c2`
- `DMCmnUtils!DmGetActiveUserSid` at `0x18010d6c2`
- `DMCmnUtils!DmRevertToSelf` at `0x18010d91c`
- `DMCmnUtils!DmRevertToSelf` at `0x18010d91c`
- `DMCmnUtils!DmImpersonate` at `0x18010d79e`
- `DMCmnUtils!DmImpersonate` at `0x18010d79e`
- `DMCmnUtils!DmGetCurrentUserSid` at `0x18010d729`
- `DMCmnUtils!DmGetCurrentUserSid` at `0x18010d729`

## string_xrefs

- `0x18010d5d9`: `MdmDiagReport_RegistryDump.reg`
- `0x18010d6e2`: `Failed (HResult:0x%08x) to dump HKLM registry - DmGetActiveUserSid :%s\n`
- `0x18010d645`: `Failed (err:%d) to create registry dump output file:%s\n`
- `0x18010d7be`: `Failed (HResult:0x%08x) to dump HKLM registry - DmImpersonate :%s\n`
- `0x18010d749`: `Failed (HResult:0x%08x) to dump HKLM registry - DmGetCurrentUserSid :%s\n`
- `0x18010d8cc`: `Succeeded to dump HKCU registry:%s\n`
- `0x18010d866`: `Failed (HResult:0x%08x) to dump HKLM registry - RegOpenCurrentUser :%s\n`
- `0x18010d938`: `--- %d HKCU registry entries are collected\n`
- `0x18010d8e0`: `Failed (HResult:0x%08x) to dump HKCU registry:%s\n`
- `0x18010d99e`: `Failed (HResult:0x%08x) to dump HKLM registry:%s\n`
- `0x18010d98a`: `Succeeded to dump HKLM registry:%s\n`
- `0x18010d9b5`: `--- %d HKLM registry entries are collected\n`

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
0x18010d5a0  push    rbx
0x18010d5a2  push    rsi
0x18010d5a3  push    rdi
0x18010d5a4  push    r12
0x18010d5a6  push    r13
0x18010d5a8  push    r14
0x18010d5aa  push    r15
0x18010d5ac  sub     rsp, 0A0h
0x18010d5b3  mov     rax, cs:__security_cookie
0x18010d5ba  xor     rax, rsp
0x18010d5bd  mov     [rsp+0D8h+var_48], rax
0x18010d5c5  mov     r14, rdx
0x18010d5c8  mov     r12, rcx
0x18010d5cb  mov     rdx, r8
0x18010d5ce  lea     rcx, [rsp+0D8h+var_68]
0x18010d5d3  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18010d5d8  nop
0x18010d5d9  lea     rdx, aMdmdiagreportR; "MdmDiagReport_RegistryDump.reg"
0x18010d5e0  lea     rcx, [rsp+0D8h+var_68]
0x18010d5e5  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x18010d5ea  lea     rcx, [rsp+0D8h+var_68]
0x18010d5ef  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18010d5f4  mov     rcx, rax; lpFileName
0x18010d5f7  call    cs:__imp_DeleteFileW
0x18010d5fe  nop     dword ptr [rax+rax+00h]
0x18010d603  xor     edi, edi
0x18010d605  mov     [rsp+0D8h+Stream], rdi
0x18010d60a  lea     rcx, [rsp+0D8h+var_68]
0x18010d60f  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18010d614  mov     rdx, rax; FileName
0x18010d617  lea     r8, aA; "a+"
0x18010d61e  lea     rcx, [rsp+0D8h+Stream]; Stream
0x18010d623  call    cs:__imp__wfopen_s
0x18010d62a  nop     dword ptr [rax+rax+00h]
0x18010d62f  mov     ebx, eax
0x18010d631  test    eax, eax
0x18010d633  jle     short loc_18010D669
0x18010d635  lea     rcx, [rsp+0D8h+var_68]
0x18010d63a  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18010d63f  mov     r9, rax
0x18010d642  mov     r8d, ebx
0x18010d645  lea     rdx, aFailedErrDToCr; "Failed (err:%d) to create registry dump"...
0x18010d64c  mov     rcx, r14; struct _iobuf *
0x18010d64f  call    ?WriteToFile@MdmLogCollector@@CAXPEAU_iobuf@@PEBGZZ; MdmLogCollector::WriteToFile(_iobuf *,ushort const *,...)
0x18010d654  nop
0x18010d655  lea     rcx, [rsp+0D8h+var_68]
0x18010d65a  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18010d65f  mov     eax, 8000FFFFh
0x18010d664  jmp     loc_18010D9EC
0x18010d669  lea     rbx, [rsp+0D8h+Stream]
0x18010d66e  mov     [rsp+0D8h+var_78], rbx
0x18010d673  mov     [rsp+0D8h+var_70], 1
0x18010d678  mov     r15d, edi
0x18010d67b  mov     rsi, [r12+38h]
0x18010d680  mov     r13, [r12+40h]
0x18010d685  cmp     rsi, r13
0x18010d688  jz      loc_18010D935
0x18010d68e  mov     [rsp+0D8h+var_B8], dil
0x18010d693  lea     rax, [rsp+0D8h+var_B8]
0x18010d698  mov     [rsp+0D8h+var_90], rax
0x18010d69d  mov     [rsp+0D8h+var_88], 1
0x18010d6a2  mov     [rsp+0D8h+hKey], rdi
0x18010d6a7  mov     [rsp+0D8h+var_B0], rdi
0x18010d6ac  mov     [rsp+0D8h+var_A0], rdi
0x18010d6b1  xor     edx, edx
0x18010d6b3  lea     rcx, [rsp+0D8h+var_B0]
0x18010d6b8  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18010d6bd  lea     rcx, [rsp+0D8h+var_B0]
0x18010d6c2  call    cs:__imp_?DmGetActiveUserSid@@YAJPEAPEAG@Z; DmGetActiveUserSid(ushort * *)
0x18010d6c9  nop     dword ptr [rax+rax+00h]
0x18010d6ce  mov     edi, eax
0x18010d6d0  test    eax, eax
0x18010d6d2  jns     short loc_18010D718
0x18010d6d4  mov     rcx, rsi
0x18010d6d7  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18010d6dc  mov     r9, rax
0x18010d6df  mov     r8d, edi
0x18010d6e2  lea     rdx, aFailedHresult0_2; "Failed (HResult:0x%08x) to dump HKLM re"...
0x18010d6e9  mov     rcx, r14; struct _iobuf *
0x18010d6ec  call    ?WriteToFile@MdmLogCollector@@CAXPEAU_iobuf@@PEBGZZ; MdmLogCollector::WriteToFile(_iobuf *,ushort const *,...)
0x18010d6f1  nop
0x18010d6f2  lea     rcx, [rsp+0D8h+var_A0]
0x18010d6f7  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18010d6fc  nop
0x18010d6fd  lea     rcx, [rsp+0D8h+var_B0]
0x18010d702  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18010d707  nop
0x18010d708  lea     rcx, [rsp+0D8h+hKey]
0x18010d70d  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18010d712  nop
0x18010d713  jmp     loc_18010D90E
0x18010d718  xor     edx, edx
0x18010d71a  lea     rcx, [rsp+0D8h+var_A0]
0x18010d71f  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18010d724  lea     rcx, [rsp+0D8h+var_A0]
0x18010d729  call    cs:__imp_?DmGetCurrentUserSid@@YAJPEAPEAG@Z; DmGetCurrentUserSid(ushort * *)
0x18010d730  nop     dword ptr [rax+rax+00h]
0x18010d735  mov     edi, eax
0x18010d737  test    eax, eax
0x18010d739  jns     short loc_18010D77F
0x18010d73b  mov     rcx, rsi
0x18010d73e  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18010d743  mov     r9, rax
0x18010d746  mov     r8d, edi
0x18010d749  lea     rdx, aFailedHresult0_6; "Failed (HResult:0x%08x) to dump HKLM re"...
0x18010d750  mov     rcx, r14; struct _iobuf *
0x18010d753  call    ?WriteToFile@MdmLogCollector@@CAXPEAU_iobuf@@PEBGZZ; MdmLogCollector::WriteToFile(_iobuf *,ushort const *,...)
0x18010d758  nop
0x18010d759  lea     rcx, [rsp+0D8h+var_A0]
0x18010d75e  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18010d763  nop
0x18010d764  lea     rcx, [rsp+0D8h+var_B0]
0x18010d769  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18010d76e  nop
0x18010d76f  lea     rcx, [rsp+0D8h+hKey]
0x18010d774  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18010d779  nop
0x18010d77a  jmp     loc_18010D90E
0x18010d77f  mov     rdx, [rsp+0D8h+var_B0]
0x18010d784  mov     rcx, [rsp+0D8h+var_A0]
0x18010d789  call    cs:__imp__o__wcsicmp
0x18010d790  nop     dword ptr [rax+rax+00h]
0x18010d795  test    eax, eax
0x18010d797  jz      short loc_18010D7F9
0x18010d799  mov     rcx, [rsp+0D8h+var_B0]
0x18010d79e  call    cs:__imp_?DmImpersonate@@YAJPEBG@Z; DmImpersonate(ushort const *)
0x18010d7a5  nop     dword ptr [rax+rax+00h]
0x18010d7aa  mov     edi, eax
0x18010d7ac  test    eax, eax
0x18010d7ae  jns     short loc_18010D7F4
0x18010d7b0  mov     rcx, rsi
0x18010d7b3  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18010d7b8  mov     r9, rax
0x18010d7bb  mov     r8d, edi
0x18010d7be  lea     rdx, aFailedHresult0_4; "Failed (HResult:0x%08x) to dump HKLM re"...
0x18010d7c5  mov     rcx, r14; struct _iobuf *
0x18010d7c8  call    ?WriteToFile@MdmLogCollector@@CAXPEAU_iobuf@@PEBGZZ; MdmLogCollector::WriteToFile(_iobuf *,ushort const *,...)
0x18010d7cd  nop
0x18010d7ce  lea     rcx, [rsp+0D8h+var_A0]
0x18010d7d3  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18010d7d8  nop
0x18010d7d9  lea     rcx, [rsp+0D8h+var_B0]
0x18010d7de  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18010d7e3  nop
0x18010d7e4  lea     rcx, [rsp+0D8h+hKey]
0x18010d7e9  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18010d7ee  nop
0x18010d7ef  jmp     loc_18010D90E
0x18010d7f4  mov     [rsp+0D8h+var_B8], 1
0x18010d7f9  mov     rdi, [rsp+0D8h+hKey]
0x18010d7fe  test    rdi, rdi
0x18010d801  jz      short loc_18010D826
0x18010d803  lea     rcx, [rsp+0D8h+var_80]; this
0x18010d808  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18010d80d  mov     rcx, rdi; hKey
0x18010d810  call    cs:__imp_RegCloseKey
0x18010d817  nop     dword ptr [rax+rax+00h]
0x18010d81c  lea     rcx, [rsp+0D8h+var_80]; this
0x18010d821  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18010d826  mov     [rsp+0D8h+hKey], 0
0x18010d82f  lea     rdx, [rsp+0D8h+hKey]; phkResult
0x18010d834  mov     ecx, 20019h; samDesired
0x18010d839  call    cs:__imp_RegOpenCurrentUser
0x18010d840  nop     dword ptr [rax+rax+00h]
0x18010d845  mov     edi, eax
0x18010d847  test    eax, eax
0x18010d849  jle     short loc_18010D854
0x18010d84b  movzx   edi, ax
0x18010d84e  or      edi, 80070000h
0x18010d854  mov     rcx, rsi
0x18010d857  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18010d85c  test    edi, edi
0x18010d85e  jns     short loc_18010D899
0x18010d860  mov     r9, rax
0x18010d863  mov     r8d, edi
0x18010d866  lea     rdx, aFailedHresult0_5; "Failed (HResult:0x%08x) to dump HKLM re"...
0x18010d86d  mov     rcx, r14; struct _iobuf *
0x18010d870  call    ?WriteToFile@MdmLogCollector@@CAXPEAU_iobuf@@PEBGZZ; MdmLogCollector::WriteToFile(_iobuf *,ushort const *,...)
0x18010d875  nop
0x18010d876  lea     rcx, [rsp+0D8h+var_A0]
0x18010d87b  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18010d880  nop
0x18010d881  lea     rcx, [rsp+0D8h+var_B0]
0x18010d886  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18010d88b  nop
0x18010d88c  lea     rcx, [rsp+0D8h+hKey]
0x18010d891  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18010d896  nop
0x18010d897  jmp     short loc_18010D90E
0x18010d899  mov     rdx, 0FFFFFFFF80000001h
0x18010d8a0  cmp     [rsp+0D8h+var_B8], 0
0x18010d8a5  cmovnz  rdx, [rsp+0D8h+hKey]; HKEY
0x18010d8ab  mov     r8, rax; unsigned __int16 *
0x18010d8ae  mov     rcx, [rsp+0D8h+Stream]; struct _iobuf *
0x18010d8b3  call    ?DumpRegistryKey@MdmLogCollector@@CAJPEAU_iobuf@@PEAUHKEY__@@PEBG@Z; MdmLogCollector::DumpRegistryKey(_iobuf *,HKEY__ *,ushort const *)
0x18010d8b8  mov     edi, eax
0x18010d8ba  mov     rcx, rsi
0x18010d8bd  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18010d8c2  mov     rcx, r14; struct _iobuf *
0x18010d8c5  test    edi, edi
0x18010d8c7  js      short loc_18010D8DA
0x18010d8c9  mov     r8, rax
0x18010d8cc  lea     rdx, aSucceededToDum_0; "Succeeded to dump HKCU registry:%s\n"
0x18010d8d3  call    ?WriteToFile@MdmLogCollector@@CAXPEAU_iobuf@@PEBGZZ; MdmLogCollector::WriteToFile(_iobuf *,ushort const *,...)
0x18010d8d8  jmp     short loc_18010D8ED
0x18010d8da  mov     r9, rax
0x18010d8dd  mov     r8d, edi
0x18010d8e0  lea     rdx, aFailedHresult0_8; "Failed (HResult:0x%08x) to dump HKCU re"...
0x18010d8e7  call    ?WriteToFile@MdmLogCollector@@CAXPEAU_iobuf@@PEBGZZ; MdmLogCollector::WriteToFile(_iobuf *,ushort const *,...)
0x18010d8ec  nop
0x18010d8ed  lea     rcx, [rsp+0D8h+var_A0]
0x18010d8f2  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18010d8f7  nop
0x18010d8f8  lea     rcx, [rsp+0D8h+var_B0]
0x18010d8fd  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18010d902  nop
0x18010d903  lea     rcx, [rsp+0D8h+hKey]
0x18010d908  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18010d90d  nop
0x18010d90e  xor     edi, edi
0x18010d910  mov     [rsp+0D8h+var_88], dil
0x18010d915  cmp     [rsp+0D8h+var_B8], dil
0x18010d91a  jz      short loc_18010D929
0x18010d91c  call    cs:__imp_?DmRevertToSelf@@YAJXZ; DmRevertToSelf(void)
0x18010d923  nop     dword ptr [rax+rax+00h]
0x18010d928  nop
0x18010d929  inc     r15d
0x18010d92c  add     rsi, 20h ; ' '
0x18010d930  jmp     loc_18010D685
0x18010d935  mov     r8d, r15d
0x18010d938  lea     rdx, aDHkcuRegistryE; "--- %d HKCU registry entries are collec"...
0x18010d93f  mov     rcx, r14; struct _iobuf *
0x18010d942  call    ?WriteToFile@MdmLogCollector@@CAXPEAU_iobuf@@PEBGZZ; MdmLogCollector::WriteToFile(_iobuf *,ushort const *,...)
0x18010d947  mov     esi, edi
0x18010d949  mov     rdi, [r12+50h]
0x18010d94e  mov     r12, [r12+58h]
0x18010d953  cmp     rdi, r12
0x18010d956  jz      short loc_18010D9B2
0x18010d958  mov     rcx, rdi
0x18010d95b  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18010d960  mov     r8, rax; unsigned __int16 *
0x18010d963  mov     rdx, 0FFFFFFFF80000002h; HKEY
0x18010d96a  mov     rcx, [rsp+0D8h+Stream]; struct _iobuf *
0x18010d96f  call    ?DumpRegistryKey@MdmLogCollector@@CAJPEAU_iobuf@@PEAUHKEY__@@PEBG@Z; MdmLogCollector::DumpRegistryKey(_iobuf *,HKEY__ *,ushort const *)
0x18010d974  mov     r15d, eax
0x18010d977  mov     rcx, rdi
0x18010d97a  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18010d97f  mov     rcx, r14; struct _iobuf *
0x18010d982  test    r15d, r15d
0x18010d985  js      short loc_18010D998
0x18010d987  mov     r8, rax
0x18010d98a  lea     rdx, aSucceededToDum; "Succeeded to dump HKLM registry:%s\n"
0x18010d991  call    ?WriteToFile@MdmLogCollector@@CAXPEAU_iobuf@@PEBGZZ; MdmLogCollector::WriteToFile(_iobuf *,ushort const *,...)
0x18010d996  jmp     short loc_18010D9AA
0x18010d998  mov     r9, rax
0x18010d99b  mov     r8d, r15d
0x18010d99e  lea     rdx, aFailedHresult0_3; "Failed (HResult:0x%08x) to dump HKLM re"...
0x18010d9a5  call    ?WriteToFile@MdmLogCollector@@CAXPEAU_iobuf@@PEBGZZ; MdmLogCollector::WriteToFile(_iobuf *,ushort const *,...)
0x18010d9aa  inc     esi
0x18010d9ac  add     rdi, 20h ; ' '
0x18010d9b0  jmp     short loc_18010D953
0x18010d9b2  mov     r8d, esi
0x18010d9b5  lea     rdx, aDHklmRegistryE; "--- %d HKLM registry entries are collec"...
0x18010d9bc  mov     rcx, r14; struct _iobuf *
0x18010d9bf  call    ?WriteToFile@MdmLogCollector@@CAXPEAU_iobuf@@PEBGZZ; MdmLogCollector::WriteToFile(_iobuf *,ushort const *,...)
0x18010d9c4  nop
0x18010d9c5  mov     rcx, [rbx]; Stream
0x18010d9c8  test    rcx, rcx
0x18010d9cb  jz      short loc_18010D9DA
0x18010d9cd  call    cs:__imp_fclose
0x18010d9d4  nop     dword ptr [rax+rax+00h]
0x18010d9d9  nop
0x18010d9da  lea     rcx, [rsp+0D8h+var_68]
0x18010d9df  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18010d9e4  xor     eax, eax
0x18010d9e6  jmp     short loc_18010D9EC
0x18010d9e8  mov     eax, dword ptr [rsp+0D8h+var_B0]
0x18010d9ec  mov     rcx, [rsp+0D8h+var_48]
0x18010d9f4  xor     rcx, rsp; StackCookie
0x18010d9f7  call    __security_check_cookie
0x18010d9fc  add     rsp, 0A0h
0x18010da03  pop     r15
0x18010da05  pop     r14
0x18010da07  pop     r13
0x18010da09  pop     r12
0x18010da0b  pop     rdi
0x18010da0c  pop     rsi
0x18010da0d  pop     rbx
0x18010da0e  retn
```
