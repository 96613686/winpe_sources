# LPA::Lui::ValidateCatalogSignedByMicrosoft(ushort const *)

- ea: `0x1800ce57c`
- end: `0x1800ce80a`
- name: `?ValidateCatalogSignedByMicrosoft@Lui@LPA@@CAJPEBG@Z`
- size: `654`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800cea1c`

## callees

- `0x18000df90`
- `0x18000ebf4`
- `0x18005fa18`
- `0x18006ba8c`
- `0x1800715d0`
- `0x18007516c`
- `0x1800ce12c`
- `0x1800ce57c`
- `0x1800cedd0`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800ce670`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800ce670`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800ce5ec`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800ce5ec`
- `WINTRUST!CryptCATAdminAcquireContext` at `0x1800ce688`
- `WINTRUST!CryptCATAdminAcquireContext` at `0x1800ce688`
- `WINTRUST!CryptCATAdminReleaseContext` at `0x1800ce7d3`
- `WINTRUST!CryptCATAdminReleaseContext` at `0x1800ce7d3`
- `WINTRUST!CryptCATAdminEnumCatalogFromHash` at `0x1800ce744`
- `WINTRUST!CryptCATAdminEnumCatalogFromHash` at `0x1800ce744`
- `WINTRUST!CryptCATCatalogInfoFromContext` at `0x1800ce75e`
- `WINTRUST!CryptCATCatalogInfoFromContext` at `0x1800ce75e`
- `WINTRUST!CryptCATAdminCalcHashFromFileHandle` at `0x1800ce618`
- `WINTRUST!CryptCATAdminCalcHashFromFileHandle` at `0x1800ce656`
- `WINTRUST!CryptCATAdminCalcHashFromFileHandle` at `0x1800ce618`
- `WINTRUST!CryptCATAdminCalcHashFromFileHandle` at `0x1800ce656`
- `WINTRUST!WinVerifyTrust` at `0x1800ce784`
- `WINTRUST!WinVerifyTrust` at `0x1800ce7b9`
- `WINTRUST!WinVerifyTrust` at `0x1800ce784`
- `WINTRUST!WinVerifyTrust` at `0x1800ce7b9`

## pseudocode

```c
__int64 __fastcall LPA::Lui::ValidateCatalogSignedByMicrosoft(LPCWSTR lpFileName)
{
  signed int LastErrorToHResultAndForceFailure; // edi
  CommonUtil *v3; // rcx
  HANDLE FileW; // rbx
  CommonUtil *v5; // rcx
  DWORD v6; // eax
  CommonUtil *v7; // rcx
  CommonUtil *v8; // rcx
  HCATINFO v9; // rax
  CommonUtil *v10; // rcx
  LONG v11; // eax
  DWORD pcbHash; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v14[4]; // [rsp+44h] [rbp-BCh] BYREF
  HCATADMIN phCatAdmin; // [rsp+48h] [rbp-B8h] BYREF
  HCATINFO phPrevCatInfo; // [rsp+50h] [rbp-B0h] BYREF
  BYTE *pbHash; // [rsp+58h] [rbp-A8h] BYREF
  int v18; // [rsp+60h] [rbp-A0h]
  WINTRUST_CATALOG_INFO_ v19; // [rsp+70h] [rbp-90h] BYREF
  struct _WINTRUST_DATA pWVTData; // [rsp+C0h] [rbp-40h] BYREF
  GUID pgActionID; // [rsp+120h] [rbp+20h] BYREF
  CATALOG_INFO psCatInfo; // [rsp+130h] [rbp+30h] BYREF

  std::_Hash_vec<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<PipeManager::PipeImplementation *>>,std::_Iterator_base0>>>::_Hash_vec<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<PipeManager::PipeImplementation *>>,std::_Iterator_base0>>>(&pbHash);
  pcbHash = 0;
  phCatAdmin = 0;
  LastErrorToHResultAndForceFailure = 0;
  FileW = CreateFileW(lpFileName, 0x80000000, 1u, 0, 3u, 0x80u, 0);
  if ( FileW == (HANDLE)-1LL )
  {
    LastErrorToHResultAndForceFailure = CommonUtil::GetLastErrorToHResultAndForceFailure(v3);
    if ( LastErrorToHResultAndForceFailure < 0 )
      goto LABEL_24;
  }
  CryptCATAdminCalcHashFromFileHandle(FileW, &pcbHash, 0, 0);
  v6 = pcbHash;
  if ( pcbHash )
    goto LABEL_6;
  LastErrorToHResultAndForceFailure = CommonUtil::GetLastErrorToHResultAndForceFailure(v5);
  if ( LastErrorToHResultAndForceFailure >= 0 )
  {
    v6 = pcbHash;
LABEL_6:
    std::vector<unsigned char>::_Resize<std::_Value_init_tag>(&pbHash, v6, v14);
    if ( !CryptCATAdminCalcHashFromFileHandle(FileW, &pcbHash, pbHash, 0) )
      LastErrorToHResultAndForceFailure = CommonUtil::GetLastErrorToHResultAndForceFailure(v7);
  }
  if ( FileW != (HANDLE)-1LL )
    CloseHandle(FileW);
  if ( LastErrorToHResultAndForceFailure >= 0 )
  {
    if ( !CryptCATAdminAcquireContext(&phCatAdmin, 0, 0) )
      LastErrorToHResultAndForceFailure = CommonUtil::GetLastErrorToHResultAndForceFailure(v8);
    if ( LastErrorToHResultAndForceFailure >= 0 )
    {
      memset_0(&pWVTData, 0, 0x58u);
      memset_0(&v19, 0, 0x48u);
      phPrevCatInfo = 0;
      pgActionID.Data1 = 11191659;
      *(_DWORD *)&pgActionID.Data2 = 298896708;
      *(_DWORD *)pgActionID.Data4 = -1073692020;
      *(_DWORD *)&pgActionID.Data4[4] = -292175281;
      v19.cbStruct = 72;
      v19.pbCalculatedFileHash = pbHash;
      v19.cbCalculatedFileHash = v18 - (_DWORD)pbHash;
      LPA::Lui::PopulateWintrustData(&pWVTData, 0, &v19);
      LastErrorToHResultAndForceFailure = -2147024891;
      do
      {
        memset_0(&psCatInfo, 0, sizeof(psCatInfo));
        v9 = CryptCATAdminEnumCatalogFromHash(phCatAdmin, pbHash, v18 - (int)pbHash, 0, &phPrevCatInfo);
        phPrevCatInfo = v9;
        if ( !v9 )
          break;
        if ( CryptCATCatalogInfoFromContext(v9, &psCatInfo, 0) )
        {
          v19.pcwszCatalogFilePath = psCatInfo.wszCatalogFile;
          v11 = WinVerifyTrust(0, &pgActionID, &pWVTData);
          LastErrorToHResultAndForceFailure = v11;
          if ( v11 > 0 )
            LastErrorToHResultAndForceFailure = (unsigned __int16)v11 | 0x80070000;
          if ( LastErrorToHResultAndForceFailure >= 0 )
            LastErrorToHResultAndForceFailure = LPA::Lui::VerifySignedByMicrosoft(&pWVTData);
          pWVTData.dwStateAction = 2;
          WinVerifyTrust(0, &pgActionID, &pWVTData);
        }
        else
        {
          LastErrorToHResultAndForceFailure = CommonUtil::GetLastErrorToHResultAndForceFailure(v10);
        }
      }
      while ( LastErrorToHResultAndForceFailure < 0 );
    }
  }
LABEL_24:
  if ( phCatAdmin )
    CryptCATAdminReleaseContext(phCatAdmin, 0);
  std::vector<unsigned char>::_Tidy(&pbHash);
  return (unsigned int)LastErrorToHResultAndForceFailure;
}

```

## disassembly

```asm
0x1800ce57c  mov     [rsp-8+arg_8], rbx
0x1800ce581  mov     [rsp-8+arg_10], rdi
0x1800ce586  push    rbp
0x1800ce587  lea     rbp, [rsp-250h]
0x1800ce58f  sub     rsp, 350h
0x1800ce596  mov     rax, cs:__security_cookie
0x1800ce59d  xor     rax, rsp
0x1800ce5a0  mov     [rbp+250h+var_10], rax
0x1800ce5a7  mov     rbx, rcx
0x1800ce5aa  lea     rcx, [rsp+350h+pbHash]
0x1800ce5af  call    ??$?0AEBV?$allocator@U?$_List_node@PEAVPipeImplementation@PipeManager@@PEAX@std@@@std@@$0A@@?$_Hash_vec@V?$allocator@V?$_List_unchecked_const_iterator@V?$_List_val@U?$_List_simple_types@PEAVPipeImplementation@PipeManager@@@std@@@std@@U_Iterator_base0@2@@std@@@std@@@std@@QEAA@AEBV?$allocator@U?$_List_node@PEAVPipeImplementation@PipeManager@@PEAX@std@@@1@@Z; std::_Hash_vec<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<PipeManager::PipeImplementation *>>,std::_Iterator_base0>>>::_Hash_vec<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<PipeManager::PipeImplementation *>>,std::_Iterator_base0>>>(std::allocator<std::_List_node<PipeManager::PipeImplementation *,void *>> const &)
0x1800ce5b4  nop
0x1800ce5b5  mov     [rsp+350h+pcbHash], 0
0x1800ce5bd  mov     [rsp+350h+phCatAdmin], 0
0x1800ce5c6  xor     edi, edi
0x1800ce5c8  mov     [rsp+350h+hTemplateFile], rdi; hTemplateFile
0x1800ce5cd  mov     [rsp+350h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x1800ce5d5  mov     [rsp+350h+dwCreationDisposition], 3; dwCreationDisposition
0x1800ce5dd  xor     r9d, r9d; lpSecurityAttributes
0x1800ce5e0  mov     edx, 80000000h; dwDesiredAccess
0x1800ce5e5  lea     r8d, [rdi+1]; dwShareMode
0x1800ce5e9  mov     rcx, rbx; lpFileName
0x1800ce5ec  call    cs:__imp_CreateFileW
0x1800ce5f2  mov     rbx, rax
0x1800ce5f5  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800ce5f9  jnz     short loc_1800CE60A
0x1800ce5fb  call    ?GetLastErrorToHResultAndForceFailure@CommonUtil@@YAJXZ; CommonUtil::GetLastErrorToHResultAndForceFailure(void)
0x1800ce600  mov     edi, eax
0x1800ce602  test    eax, eax
0x1800ce604  js      loc_1800CE7C7
0x1800ce60a  xor     r9d, r9d; dwFlags
0x1800ce60d  xor     r8d, r8d; pbHash
0x1800ce610  lea     rdx, [rsp+350h+pcbHash]; pcbHash
0x1800ce615  mov     rcx, rbx; hFile
0x1800ce618  call    cs:__imp_CryptCATAdminCalcHashFromFileHandle
0x1800ce61e  mov     eax, [rsp+350h+pcbHash]
0x1800ce622  test    eax, eax
0x1800ce624  jnz     short loc_1800CE635
0x1800ce626  call    ?GetLastErrorToHResultAndForceFailure@CommonUtil@@YAJXZ; CommonUtil::GetLastErrorToHResultAndForceFailure(void)
0x1800ce62b  mov     edi, eax
0x1800ce62d  test    eax, eax
0x1800ce62f  js      short loc_1800CE667
0x1800ce631  mov     eax, [rsp+350h+pcbHash]
0x1800ce635  mov     edx, eax
0x1800ce637  lea     r8, [rsp+350h+var_30C]
0x1800ce63c  lea     rcx, [rsp+350h+pbHash]
0x1800ce641  call    ??$_Resize@U_Value_init_tag@std@@@?$vector@EV?$allocator@E@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<uchar>::_Resize<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x1800ce646  xor     r9d, r9d; dwFlags
0x1800ce649  mov     r8, [rsp+350h+pbHash]; pbHash
0x1800ce64e  lea     rdx, [rsp+350h+pcbHash]; pcbHash
0x1800ce653  mov     rcx, rbx; hFile
0x1800ce656  call    cs:__imp_CryptCATAdminCalcHashFromFileHandle
0x1800ce65c  test    eax, eax
0x1800ce65e  jnz     short loc_1800CE667
0x1800ce660  call    ?GetLastErrorToHResultAndForceFailure@CommonUtil@@YAJXZ; CommonUtil::GetLastErrorToHResultAndForceFailure(void)
0x1800ce665  mov     edi, eax
0x1800ce667  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x1800ce66b  jz      short loc_1800CE676
0x1800ce66d  mov     rcx, rbx; hObject
0x1800ce670  call    cs:__imp_CloseHandle
0x1800ce676  test    edi, edi
0x1800ce678  js      loc_1800CE7C7
0x1800ce67e  xor     r8d, r8d; dwFlags
0x1800ce681  xor     edx, edx; pgSubsystem
0x1800ce683  lea     rcx, [rsp+350h+phCatAdmin]; phCatAdmin
0x1800ce688  call    cs:__imp_CryptCATAdminAcquireContext
0x1800ce68e  test    eax, eax
0x1800ce690  jnz     short loc_1800CE699
0x1800ce692  call    ?GetLastErrorToHResultAndForceFailure@CommonUtil@@YAJXZ; CommonUtil::GetLastErrorToHResultAndForceFailure(void)
0x1800ce697  mov     edi, eax
0x1800ce699  test    edi, edi
0x1800ce69b  js      loc_1800CE7C7
0x1800ce6a1  xor     edx, edx; Val
0x1800ce6a3  lea     r8d, [rdx+58h]; Size
0x1800ce6a7  lea     rcx, [rbp+250h+pWVTData]; void *
0x1800ce6ab  call    memset_0
0x1800ce6b0  mov     ebx, 48h ; 'H'
0x1800ce6b5  mov     r8d, ebx; Size
0x1800ce6b8  xor     edx, edx; Val
0x1800ce6ba  lea     rcx, [rsp+350h+var_2E0]; void *
0x1800ce6bf  call    memset_0
0x1800ce6c4  mov     [rsp+350h+phPrevCatInfo], 0
0x1800ce6cd  mov     [rbp+250h+pgActionID.Data1], 0AAC56Bh
0x1800ce6d4  mov     dword ptr [rbp+250h+pgActionID.Data2], 11D0CD44h
0x1800ce6db  mov     dword ptr [rbp+250h+pgActionID.Data4], 0C000C28Ch
0x1800ce6e2  mov     dword ptr [rbp+250h+pgActionID.Data4+4], 0EE95C24Fh
0x1800ce6e9  mov     [rsp+350h+var_2E0.cbStruct], ebx
0x1800ce6ed  mov     rcx, [rsp+350h+pbHash]
0x1800ce6f2  mov     [rbp+250h+var_2E0.pbCalculatedFileHash], rcx
0x1800ce6f6  mov     eax, [rsp+350h+var_2F0]
0x1800ce6fa  sub     eax, ecx
0x1800ce6fc  mov     [rbp+250h+var_2E0.cbCalculatedFileHash], eax
0x1800ce6ff  lea     r8, [rsp+350h+var_2E0]; struct WINTRUST_CATALOG_INFO_ *
0x1800ce704  xor     edx, edx; struct WINTRUST_FILE_INFO_ *
0x1800ce706  lea     rcx, [rbp+250h+pWVTData]; struct _WINTRUST_DATA *
0x1800ce70a  call    ?PopulateWintrustData@Lui@LPA@@CAXAEAU_WINTRUST_DATA@@PEBUWINTRUST_FILE_INFO_@@PEBUWINTRUST_CATALOG_INFO_@@@Z; LPA::Lui::PopulateWintrustData(_WINTRUST_DATA &,WINTRUST_FILE_INFO_ const *,WINTRUST_CATALOG_INFO_ const *)
0x1800ce70f  mov     edi, 80070005h
0x1800ce714  xor     edx, edx; Val
0x1800ce716  mov     r8d, 20Ch; Size
0x1800ce71c  lea     rcx, [rbp+250h+psCatInfo]; void *
0x1800ce720  call    memset_0
0x1800ce725  mov     rdx, [rsp+350h+pbHash]; pbHash
0x1800ce72a  mov     r8d, [rsp+350h+var_2F0]
0x1800ce72f  sub     r8d, edx; cbHash
0x1800ce732  lea     rax, [rsp+350h+phPrevCatInfo]
0x1800ce737  mov     qword ptr [rsp+350h+dwCreationDisposition], rax; phPrevCatInfo
0x1800ce73c  xor     r9d, r9d; dwFlags
0x1800ce73f  mov     rcx, [rsp+350h+phCatAdmin]; hCatAdmin
0x1800ce744  call    cs:__imp_CryptCATAdminEnumCatalogFromHash
0x1800ce74a  mov     [rsp+350h+phPrevCatInfo], rax
0x1800ce74f  test    rax, rax
0x1800ce752  jz      short loc_1800CE7C7
0x1800ce754  xor     r8d, r8d; dwFlags
0x1800ce757  lea     rdx, [rbp+250h+psCatInfo]; psCatInfo
0x1800ce75b  mov     rcx, rax; hCatInfo
0x1800ce75e  call    cs:__imp_CryptCATCatalogInfoFromContext
0x1800ce764  test    eax, eax
0x1800ce766  jnz     short loc_1800CE771
0x1800ce768  call    ?GetLastErrorToHResultAndForceFailure@CommonUtil@@YAJXZ; CommonUtil::GetLastErrorToHResultAndForceFailure(void)
0x1800ce76d  mov     edi, eax
0x1800ce76f  jmp     short loc_1800CE7BF
0x1800ce771  lea     rax, [rbp+250h+psCatInfo.wszCatalogFile]
0x1800ce775  mov     [rsp+350h+var_2E0.pcwszCatalogFilePath], rax
0x1800ce77a  lea     r8, [rbp+250h+pWVTData]; pWVTData
0x1800ce77e  lea     rdx, [rbp+250h+pgActionID]; pgActionID
0x1800ce782  xor     ecx, ecx; hwnd
0x1800ce784  call    cs:__imp_WinVerifyTrust
0x1800ce78a  mov     edi, eax
0x1800ce78c  test    eax, eax
0x1800ce78e  jle     short loc_1800CE799
0x1800ce790  movzx   edi, ax
0x1800ce793  or      edi, 80070000h
0x1800ce799  test    edi, edi
0x1800ce79b  js      short loc_1800CE7A8
0x1800ce79d  lea     rcx, [rbp+250h+pWVTData]; struct _WINTRUST_DATA *
0x1800ce7a1  call    ?VerifySignedByMicrosoft@Lui@LPA@@CAJAEAU_WINTRUST_DATA@@@Z; LPA::Lui::VerifySignedByMicrosoft(_WINTRUST_DATA &)
0x1800ce7a6  mov     edi, eax
0x1800ce7a8  mov     [rbp+250h+var_260], 2
0x1800ce7af  lea     r8, [rbp+250h+pWVTData]; pWVTData
0x1800ce7b3  lea     rdx, [rbp+250h+pgActionID]; pgActionID
0x1800ce7b7  xor     ecx, ecx; hwnd
0x1800ce7b9  call    cs:__imp_WinVerifyTrust
0x1800ce7bf  test    edi, edi
0x1800ce7c1  js      loc_1800CE714
0x1800ce7c7  mov     rcx, [rsp+350h+phCatAdmin]; hCatAdmin
0x1800ce7cc  test    rcx, rcx
0x1800ce7cf  jz      short loc_1800CE7DA
0x1800ce7d1  xor     edx, edx; dwFlags
0x1800ce7d3  call    cs:__imp_CryptCATAdminReleaseContext
0x1800ce7d9  nop
0x1800ce7da  lea     rcx, [rsp+350h+pbHash]
0x1800ce7df  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x1800ce7e4  mov     eax, edi
0x1800ce7e6  mov     rcx, [rbp+250h+var_10]
0x1800ce7ed  xor     rcx, rsp; StackCookie
0x1800ce7f0  call    __security_check_cookie
0x1800ce7f5  lea     r11, [rsp+350h+var_s0]
0x1800ce7fd  mov     rbx, [r11+18h]
0x1800ce801  mov     rdi, [r11+20h]
0x1800ce805  mov     rsp, r11
0x1800ce808  pop     rbp
0x1800ce809  retn
```
