# CDNDownload_DeleteAllRecordsForEnrollmentId(ushort const *)

- ea: `0x18002c3b4`
- end: `0x18002c63f`
- name: `?CDNDownload_DeleteAllRecordsForEnrollmentId@@YAJPEBG@Z`
- size: `651`
- prototype: `__int64 __fastcall(char *)`
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x180067c90`

## callees

- `0x1800071c0`
- `0x180011938`
- `0x18002c3b4`
- `0x18002c648`
- `0x18002c664`
- `0x18002e1a0`
- `0x18002e570`
- `0x180033468`
- `0x180067a90`
- `0x180067ac4`
- `0x18006828c`
- `0x1800761d4`
- `0x1800769ac`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18002c551`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18002c551`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x18002c5c2`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x18002c5c2`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18002c4e5`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18002c4e5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002c4a1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002c50c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002c615`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002c4a1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002c50c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002c615`

## pseudocode

```c
// Hidden C++ exception states: #wind=6 #try_helpers=1
__int64 __fastcall CDNDownload_DeleteAllRecordsForEnrollmentId(char *a1)
{
  int v2; // eax
  unsigned int v3; // ebx
  int v5; // r8d
  int v6; // eax
  unsigned int v7; // r14d
  HKEY v8; // rbx
  DWORD i; // esi
  __int64 v10; // rdx
  int CDNRecordString; // edi
  unsigned __int16 *v12; // rax
  int v13; // r8d
  int v14; // ecx
  void *v15; // rcx
  int lpcSubKeys; // [rsp+20h] [rbp-E0h]
  DWORD cSubKeys; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v18; // [rsp+68h] [rbp-98h] BYREF
  DWORD cchName; // [rsp+70h] [rbp-90h] BYREF
  void *Block; // [rsp+78h] [rbp-88h] BYREF
  HKEY hKey; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v22[8]; // [rsp+88h] [rbp-78h] BYREF
  void **p_Block; // [rsp+90h] [rbp-70h] BYREF
  __int64 v24; // [rsp+98h] [rbp-68h] BYREF
  char v25; // [rsp+A0h] [rbp-60h]
  WCHAR Name[264]; // [rsp+B0h] [rbp-50h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+308h] [rbp+208h]

  hKey = 0;
  cSubKeys = 0;
  cchName = 260;
  v18 = 0;
  v2 = _create___mutex_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJPEBGKKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(
         &v18,
         L"Global\\CDNDownloadMutex");
  v3 = v2;
  if ( v2 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x5D8,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\cdndownload\\objectmodel\\lib\\cdndownloadapi.cpp",
      (const char *)(unsigned int)v2,
      lpcSubKeys);
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v18);
    return v3;
  }
  _acquire___mutex_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEBA_AV__unique_any_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil___2_PEAKKH_Z(
    &v18,
    v22,
    0,
    0xFFFFFFFFLL);
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
    &hKey,
    0);
  v6 = DCCDNUtil_GetHKey(qword_1800B07C8, &hKey, v5);
  v7 = v6;
  if ( v6 < 0 )
  {
    v3 = 0;
    if ( v6 != -2147024893 )
      v3 = v6;
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v22);
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v18);
    if ( hKey )
      RegCloseKey(hKey);
    return v3;
  }
  v8 = hKey;
  if ( RegQueryInfoKeyW(hKey, 0, 0, 0, &cSubKeys, 0, 0, 0, 0, 0, 0, 0) )
  {
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v22);
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v18);
    if ( v8 )
      RegCloseKey(v8);
    return 0;
  }
  else
  {
    for ( i = 0; i < cSubKeys; ++i )
    {
      cchName = 260;
      if ( !RegEnumKeyExW(v8, i, Name, &cchName, 0, 0, 0, 0) )
      {
        Block = 0;
        p_Block = &Block;
        v24 = 0;
        v25 = 1;
        CDNRecordString = GetCDNRecordString(Name, v10, &v24);
        wil::details::out_param_t<std::unique_ptr<unsigned short>>::~out_param_t<std::unique_ptr<unsigned short>>(&p_Block);
        if ( CDNRecordString >= 0 )
        {
          v12 = (unsigned __int16 *)Block;
          do
          {
            v13 = *(unsigned __int16 *)((char *)v12 + a1 - (_BYTE *)Block);
            v14 = *v12 - v13;
            if ( v14 )
              break;
            ++v12;
          }
          while ( v13 );
          if ( !v14 )
            RegDeleteTreeW(v8, Name);
        }
        v15 = Block;
        Block = 0;
        if ( v15 )
          operator delete(v15);
        std::unique_ptr<unsigned short>::~unique_ptr<unsigned short>(&Block);
      }
    }
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v22);
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v18);
    if ( v8 )
      RegCloseKey(v8);
    return v7;
  }
}

```

## disassembly

```asm
0x18002c3b4  push    rbp
0x18002c3b6  push    rbx
0x18002c3b7  push    rsi
0x18002c3b8  push    rdi
0x18002c3b9  push    r12
0x18002c3bb  push    r14
0x18002c3bd  push    r15
0x18002c3bf  lea     rbp, [rsp-1D0h]
0x18002c3c7  sub     rsp, 2D0h
0x18002c3ce  mov     rax, cs:__security_cookie
0x18002c3d5  xor     rax, rsp
0x18002c3d8  mov     [rbp+200h+var_40], rax
0x18002c3df  mov     r15, rcx
0x18002c3e2  xor     r12d, r12d
0x18002c3e5  mov     [rbp+200h+hKey], r12
0x18002c3e9  mov     [rsp+300h+cSubKeys], r12d
0x18002c3ee  mov     [rsp+300h+cchName], 104h
0x18002c3f6  mov     [rsp+300h+var_298], r12
0x18002c3fb  lea     rdx, aGlobalCdndownl; "Global\\CDNDownloadMutex"
0x18002c402  lea     rcx, [rsp+300h+var_298]
0x18002c407  call    ?create@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJPEBGKKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x18002c40c  mov     ebx, eax
0x18002c40e  test    eax, eax
0x18002c410  jns     short loc_18002C440
0x18002c412  mov     rcx, [rbp+208h]; this
0x18002c419  mov     r9d, eax; char *
0x18002c41c  lea     r8, aOnecoreuapAdmi_10; "onecoreuap\\admin\\enterprisemgmt\\cdnd"...
0x18002c423  mov     edx, 5D8h; void *
0x18002c428  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002c42d  nop
0x18002c42e  lea     rcx, [rsp+300h+var_298]
0x18002c433  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18002c438  nop
0x18002c439  mov     eax, ebx
0x18002c43b  jmp     loc_18002C61E
0x18002c440  or      r9d, 0FFFFFFFFh
0x18002c444  xor     r8d, r8d
0x18002c447  lea     rdx, [rbp+200h+var_278]
0x18002c44b  lea     rcx, [rsp+300h+var_298]
0x18002c450  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x18002c455  nop
0x18002c456  xor     edx, edx
0x18002c458  lea     rcx, [rbp+200h+hKey]
0x18002c45c  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x18002c461  lea     rdx, [rbp+200h+hKey]; HKEY *
0x18002c465  mov     rcx, cs:qword_1800B07C8; lpSubKey
0x18002c46c  call    ?DCCDNUtil_GetHKey@@YAJPEBGPEAPEAUHKEY__@@H@Z; DCCDNUtil_GetHKey(ushort const *,HKEY__ * *,int)
0x18002c471  mov     r14d, eax
0x18002c474  test    eax, eax
0x18002c476  jns     short loc_18002C4A9
0x18002c478  mov     ebx, r12d
0x18002c47b  cmp     eax, 80070003h
0x18002c480  cmovnz  ebx, eax
0x18002c483  lea     rcx, [rbp+200h+var_278]
0x18002c487  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18002c48c  nop
0x18002c48d  lea     rcx, [rsp+300h+var_298]
0x18002c492  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18002c497  nop
0x18002c498  mov     rcx, [rbp+200h+hKey]; hKey
0x18002c49c  test    rcx, rcx
0x18002c49f  jz      short loc_18002C439
0x18002c4a1  call    cs:__imp_RegCloseKey
0x18002c4a7  jmp     short loc_18002C439
0x18002c4a9  mov     [rsp+300h+lpftLastWriteTime], r12; lpftLastWriteTime
0x18002c4ae  mov     [rsp+300h+lpcbSecurityDescriptor], r12; lpcbSecurityDescriptor
0x18002c4b3  mov     [rsp+300h+lpcbMaxValueLen], r12; lpcbMaxValueLen
0x18002c4b8  mov     [rsp+300h+lpcbMaxValueNameLen], r12; lpcbMaxValueNameLen
0x18002c4bd  mov     [rsp+300h+lpcValues], r12; lpcValues
0x18002c4c2  mov     [rsp+300h+lpcbMaxClassLen], r12; lpcbMaxClassLen
0x18002c4c7  mov     [rsp+300h+lpcbMaxSubKeyLen], r12; lpcbMaxSubKeyLen
0x18002c4cc  lea     rax, [rsp+300h+cSubKeys]
0x18002c4d1  mov     [rsp+300h+lpcSubKeys], rax; lpcSubKeys
0x18002c4d6  xor     r9d, r9d; lpReserved
0x18002c4d9  xor     r8d, r8d; lpcchClass
0x18002c4dc  xor     edx, edx; lpClass
0x18002c4de  mov     rbx, [rbp+200h+hKey]
0x18002c4e2  mov     rcx, rbx; hKey
0x18002c4e5  call    cs:__imp_RegQueryInfoKeyW
0x18002c4eb  test    eax, eax
0x18002c4ed  jz      short loc_18002C519
0x18002c4ef  lea     rcx, [rbp+200h+var_278]
0x18002c4f3  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18002c4f8  nop
0x18002c4f9  lea     rcx, [rsp+300h+var_298]
0x18002c4fe  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18002c503  nop
0x18002c504  test    rbx, rbx
0x18002c507  jz      short loc_18002C512
0x18002c509  mov     rcx, rbx; hKey
0x18002c50c  call    cs:__imp_RegCloseKey
0x18002c512  xor     eax, eax
0x18002c514  jmp     loc_18002C61E
0x18002c519  mov     esi, r12d
0x18002c51c  cmp     [rsp+300h+cSubKeys], r12d
0x18002c521  jbe     loc_18002C5F8
0x18002c527  mov     [rsp+300h+cchName], 104h
0x18002c52f  mov     [rsp+300h+lpcValues], r12; lpftLastWriteTime
0x18002c534  mov     [rsp+300h+lpcbMaxClassLen], r12; lpcchClass
0x18002c539  mov     [rsp+300h+lpcbMaxSubKeyLen], r12; lpClass
0x18002c53e  mov     [rsp+300h+lpcSubKeys], r12; lpReserved
0x18002c543  lea     r9, [rsp+300h+cchName]; lpcchName
0x18002c548  lea     r8, [rbp+200h+Name]; lpName
0x18002c54c  mov     edx, esi; dwIndex
0x18002c54e  mov     rcx, rbx; hKey
0x18002c551  call    cs:__imp_RegEnumKeyExW
0x18002c557  test    eax, eax
0x18002c559  jnz     loc_18002C5EC
0x18002c55f  mov     [rsp+300h+Block], r12
0x18002c564  lea     rax, [rsp+300h+Block]
0x18002c569  mov     [rbp+200h+var_270], rax
0x18002c56d  mov     [rbp+200h+var_268], r12
0x18002c571  mov     [rbp+200h+var_260], 1
0x18002c575  lea     r8, [rbp+200h+var_268]
0x18002c579  lea     rcx, [rbp+200h+Name]
0x18002c57d  call    GetCDNRecordString
0x18002c582  mov     edi, eax
0x18002c584  lea     rcx, [rbp+200h+var_270]
0x18002c588  call    ??1?$out_param_t@V?$unique_ptr@GU?$default_delete@G@std@@@std@@@details@wil@@QEAA@XZ; wil::details::out_param_t<std::unique_ptr<ushort>>::~out_param_t<std::unique_ptr<ushort>>(void)
0x18002c58d  shr     edi, 1Fh
0x18002c590  xor     dil, 1
0x18002c594  jz      short loc_18002C5C8
0x18002c596  mov     rax, [rsp+300h+Block]
0x18002c59b  mov     rdx, r15
0x18002c59e  sub     rdx, rax
0x18002c5a1  movzx   ecx, word ptr [rax]
0x18002c5a4  movzx   r8d, word ptr [rax+rdx]
0x18002c5a9  sub     ecx, r8d
0x18002c5ac  jnz     short loc_18002C5B7
0x18002c5ae  add     rax, 2
0x18002c5b2  test    r8d, r8d
0x18002c5b5  jnz     short loc_18002C5A1
0x18002c5b7  test    ecx, ecx
0x18002c5b9  jnz     short loc_18002C5C8
0x18002c5bb  lea     rdx, [rbp+200h+Name]; lpSubKey
0x18002c5bf  mov     rcx, rbx; hKey
0x18002c5c2  call    cs:__imp_RegDeleteTreeW
0x18002c5c8  mov     rcx, [rsp+300h+Block]; Block
0x18002c5cd  mov     [rsp+300h+Block], r12
0x18002c5d2  test    rcx, rcx
0x18002c5d5  jz      short loc_18002C5E2
0x18002c5d7  mov     edx, 2
0x18002c5dc  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18002c5e1  nop
0x18002c5e2  lea     rcx, [rsp+300h+Block]
0x18002c5e7  call    ??1?$unique_ptr@GU?$default_delete@G@std@@@std@@QEAA@XZ; std::unique_ptr<ushort>::~unique_ptr<ushort>(void)
0x18002c5ec  inc     esi
0x18002c5ee  cmp     esi, [rsp+300h+cSubKeys]
0x18002c5f2  jb      loc_18002C527
0x18002c5f8  lea     rcx, [rbp+200h+var_278]
0x18002c5fc  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18002c601  nop
0x18002c602  lea     rcx, [rsp+300h+var_298]
0x18002c607  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18002c60c  nop
0x18002c60d  test    rbx, rbx
0x18002c610  jz      short loc_18002C61B
0x18002c612  mov     rcx, rbx; hKey
0x18002c615  call    cs:__imp_RegCloseKey
0x18002c61b  mov     eax, r14d
0x18002c61e  mov     rcx, [rbp+200h+var_40]
0x18002c625  xor     rcx, rsp; StackCookie
0x18002c628  call    __security_check_cookie
0x18002c62d  add     rsp, 2D0h
0x18002c634  pop     r15
0x18002c636  pop     r14
0x18002c638  pop     r12
0x18002c63a  pop     rdi
0x18002c63b  pop     rsi
0x18002c63c  pop     rbx
0x18002c63d  pop     rbp
0x18002c63e  retn
```
