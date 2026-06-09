# CDriverMap::RemoveDeletedDriverPackages(void)

- ea: `0x180048300`
- end: `0x1800488de`
- name: `?RemoveDeletedDriverPackages@CDriverMap@@AEAAKXZ`
- size: `1502`
- prototype: `unsigned int __fastcall(CDriverMap *__hidden this)`
- caller_count: `1`
- callee_count: `21`
- tags: `file_ops`

## callers

- `0x180044f20`

## callees

- `0x180005e40`
- `0x180006210`
- `0x180006d02`
- `0x180006eb8`
- `0x180006ec4`
- `0x180007014`
- `0x18000fa50`
- `0x1800103e0`
- `0x180016440`
- `0x180017600`
- `0x180017adc`
- `0x180018778`
- `0x18001d750`
- `0x180025da0`
- `0x18003244c`
- `0x180038d4c`
- `0x180048300`
- `0x18004af5c`
- `0x18004b860`
- `0x18006041c`
- `0x180066c10`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800483be`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004864a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800483be`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004864a`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x1800483b4`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x1800483b4`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x1800484ac`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x1800484ac`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x180048640`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x180048640`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x180048890`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x180048890`

## string_xrefs

- `0x18004872a`: `TelCacheProvider::RemoveItem failed [%#x]`
- `0x1800484ea`: `CDriverMap::RemoveDeletedDriverPackages`
- `0x18004873d`: `CDriverMap::RemoveDeletedDriverPackages`
- `0x1800487ed`: `CDriverMap::RemoveDeletedDriverPackages`
- `0x1800483c6`: `GetSystemDirectory failed with [%d]`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CDriverMap::RemoveDeletedDriverPackages(CDriverMap *this)
{
  __int64 FirstFileW; // r15
  __int64 v3; // r8
  DWORD LastError; // esi
  const char *v5; // rbx
  __int64 v6; // r13
  _QWORD *v7; // r14
  _QWORD *v8; // rdi
  __int64 *v9; // rsi
  __int64 *v10; // rbx
  unsigned __int64 v11; // rdx
  LPCWSTR *v12; // rdi
  __int64 v13; // rbx
  const WCHAR *v14; // rcx
  __int64 v15; // r8
  LPCWSTR *v16; // rcx
  FILE *v17; // rax
  LPCWSTR *v18; // rbx
  FILE *v19; // rax
  FILE *v20; // rax
  LPCWSTR *v21; // r8
  LPCWSTR *v22; // rax
  unsigned __int64 v23; // rdx
  void **v24; // rdi
  __int64 v25; // rbx
  DWORD v26; // eax
  int i; // eax
  _QWORD *v28; // rdx
  __int64 v29; // r8
  __int64 *v30; // rax
  __int64 v31; // rdi
  __int64 v32; // rbx
  int v33; // eax
  int v34; // ebx
  FILE *v35; // rax
  FILE *v36; // rax
  FILE *v37; // rax
  FILE *v38; // rax
  FILE *v39; // rax
  FILE *v40; // rax
  __int64 v42; // [rsp+20h] [rbp-E0h]
  __int64 v43; // [rsp+28h] [rbp-D8h]
  _BYTE v44[8]; // [rsp+30h] [rbp-D0h] BYREF
  LPCWSTR lpFileName[2]; // [rsp+38h] [rbp-C8h] BYREF
  unsigned __int64 v46; // [rsp+48h] [rbp-B8h]
  unsigned __int64 v47; // [rsp+50h] [rbp-B0h]
  void *v48[2]; // [rsp+58h] [rbp-A8h] BYREF
  unsigned __int64 v49; // [rsp+68h] [rbp-98h]
  unsigned __int64 v50; // [rsp+70h] [rbp-90h]
  __int128 v51; // [rsp+78h] [rbp-88h] BYREF
  __int64 v52; // [rsp+88h] [rbp-78h]
  __int64 v53; // [rsp+90h] [rbp-70h]
  _WIN32_FIND_DATAW FindFileData; // [rsp+A0h] [rbp-60h] BYREF
  _BYTE v55[128]; // [rsp+2F0h] [rbp+1F0h] BYREF
  _QWORD v56[70]; // [rsp+370h] [rbp+270h] BYREF
  WCHAR Buffer[264]; // [rsp+5A0h] [rbp+4A0h] BYREF

  *(_OWORD *)lpFileName = 0;
  v46 = 0;
  v47 = 7;
  LOWORD(lpFileName[0]) = 0;
  *(_OWORD *)v48 = 0;
  v49 = 0;
  v50 = 7;
  LOWORD(v48[0]) = 0;
  FirstFileW = -1;
  memset_0(&FindFileData, 0, sizeof(FindFileData));
  CDriverPackage::CDriverPackage((CDriverPackage *)v55);
  memset_0(Buffer, 0, 0x208u);
  if ( !qword_1801572C8 )
  {
    LastError = 6;
    v5 = "DriverPackageStore store is not initialized [%d]";
    v6 = 225;
    goto LABEL_59;
  }
  if ( !GetSystemDirectoryW(Buffer, 0x104u) )
  {
    LastError = GetLastError();
    v5 = "GetSystemDirectory failed with [%d]";
    v6 = 232;
LABEL_59:
    AslLogCallPrintf(2, "CDriverMap::RemoveDeletedDriverPackages", v6, v5, LastError);
    if ( EnableDevInvStdErrLog )
    {
      v38 = o___acrt_iob_func_0(2u);
      fprintf(v38, "Error: %s, %u: ", "CDriverMap::RemoveDeletedDriverPackages", v6);
      v39 = o___acrt_iob_func_0(2u);
      fprintf(v39, v5, LastError);
      v40 = o___acrt_iob_func_0(2u);
      fprintf(v40, "\n");
    }
    if ( g_DeviceMapLogFunction )
      TraceMessageCallback(0x2000000, v5, LastError);
    LODWORD(v42) = LastError;
    AslLogCallPrintf(1, "CDriverMap::RemoveDeletedDriverPackages", v6, v5, v42);
    goto LABEL_64;
  }
  v7 = (_QWORD *)((char *)this + 152);
  v8 = (_QWORD *)*v7;
  v9 = *(__int64 **)(*v7 + 8LL);
  while ( !*((_BYTE *)v9 + 25) )
  {
    std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,CDriverPackage *>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<std::wstring const,CDriverPackage *>,void *>>>(
      v7,
      v7,
      v9[2]);
    v10 = v9;
    v9 = (__int64 *)*v9;
    std::wstring::~wstring(v10 + 4);
    operator delete(v10);
  }
  v8[1] = v8;
  *v8 = v8;
  v8[2] = v8;
  v7[1] = 0;
  v11 = -1;
  do
    ++v11;
  while ( Buffer[v11] );
  if ( v11 > v47 )
  {
    std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(
      lpFileName,
      v11,
      v3,
      Buffer);
  }
  else
  {
    v12 = lpFileName;
    if ( v47 > 7 )
      v12 = (LPCWSTR *)lpFileName[0];
    v46 = v11;
    v13 = 2 * v11;
    memmove_0(v12, Buffer, 2 * v11);
    *(_WORD *)((char *)v12 + v13) = 0;
  }
  std::wstring::append(lpFileName, L"\\DriverStore\\FileRepository\\*");
  v14 = (const WCHAR *)lpFileName;
  if ( v47 > 7 )
    v14 = lpFileName[0];
  FirstFileW = (__int64)FindFirstFileW(v14, &FindFileData);
  if ( FirstFileW == -1 )
  {
    LastError = 2;
    v16 = lpFileName;
    if ( v47 > 7 )
      v16 = (LPCWSTR *)lpFileName[0];
    AslLogCallPrintf(2, "CDriverMap::RemoveDeletedDriverPackages", 246, "No driver package file in: %ws [%d]", v16, 2);
    if ( EnableDevInvStdErrLog )
    {
      v17 = o___acrt_iob_func_0(2u);
      fprintf(v17, "Error: %s, %u: ", "CDriverMap::RemoveDeletedDriverPackages", 246);
      v18 = lpFileName;
      if ( v47 > 7 )
        v18 = (LPCWSTR *)lpFileName[0];
      v19 = o___acrt_iob_func_0(2u);
      fprintf(v19, "No driver package file in: %ws [%d]", v18, 2);
      v20 = o___acrt_iob_func_0(2u);
      fprintf(v20, "\n");
    }
    if ( g_DeviceMapLogFunction )
    {
      v21 = lpFileName;
      if ( v47 > 7 )
        v21 = (LPCWSTR *)lpFileName[0];
      TraceMessageCallback(0x2000000, "No driver package file in: %ws [%d]", v21, 2);
    }
    v22 = lpFileName;
    if ( v47 > 7 )
      v22 = (LPCWSTR *)lpFileName[0];
    LODWORD(v43) = 2;
    AslLogCallPrintf(1, "CDriverMap::RemoveDeletedDriverPackages", 246, "No driver package file in: %ws [%d]", v22, v43);
  }
  else
  {
    do
    {
      if ( (FindFileData.dwFileAttributes & 0x10) != 0 )
      {
        v23 = -1;
        do
          ++v23;
        while ( FindFileData.cFileName[v23] );
        if ( v23 > v50 )
        {
          std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(
            v48,
            v23,
            v15,
            FindFileData.cFileName);
        }
        else
        {
          v24 = v48;
          if ( v50 > 7 )
            v24 = (void **)v48[0];
          v49 = v23;
          v25 = 2 * v23;
          memmove_0(v24, FindFileData.cFileName, 2 * v23);
          *(_WORD *)((char *)v24 + v25) = 0;
        }
        *(_DWORD *)std::map<std::wstring,unsigned long>::operator[](v7, v48) = 1;
      }
    }
    while ( FindNextFileW((HANDLE)FirstFileW, &FindFileData) );
    v26 = GetLastError();
    LastError = v26;
    if ( v26 && v26 != 18 )
    {
      v5 = "Get subfolder failed: [%d]";
      v6 = 268;
      goto LABEL_59;
    }
    LastError = 0;
    for ( i = TelCacheProvider::GetFirstItem((TelCacheProvider *)g_DriverPackageStore, (struct IAmiInventoryItem *)v55);
          i >= 0;
          i = TelCacheProvider::GetNextItem((TelCacheProvider *)g_DriverPackageStore, (struct IAmiInventoryItem *)v55) )
    {
      v28 = v56;
      if ( v56[3] > 7u )
        v28 = (_QWORD *)v56[0];
      v51 = 0;
      v52 = 0;
      v53 = 0;
      v29 = -1;
      do
        ++v29;
      while ( *((_WORD *)v28 + v29) );
      std::wstring::_Construct<1,unsigned short const *>(&v51, v28, v29);
      v30 = (__int64 *)std::_Tree<std::_Tmap_traits<std::wstring,int,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,int>>,0>>::find(
                         v7,
                         v44,
                         &v51);
      v31 = *v7;
      v32 = *v30;
      std::wstring::~wstring(&v51);
      if ( v32 == v31 )
      {
        v33 = TelCacheProvider::RemoveItem((TelCacheProvider *)g_DriverPackageStore, (struct IAmiInventoryItem *)v55);
        v34 = v33;
        if ( v33 < 0 )
        {
          AslLogCallPrintf(
            2,
            "CDriverMap::RemoveDeletedDriverPackages",
            283,
            "TelCacheProvider::RemoveItem failed [%#x]",
            v33);
          if ( EnableDevInvStdErrLog )
          {
            v35 = o___acrt_iob_func_0(2u);
            fprintf(v35, "Error: %s, %u: ", "CDriverMap::RemoveDeletedDriverPackages", 283);
            v36 = o___acrt_iob_func_0(2u);
            fprintf(v36, "TelCacheProvider::RemoveItem failed [%#x]", v34);
            v37 = o___acrt_iob_func_0(2u);
            fprintf(v37, "\n");
          }
          if ( g_DeviceMapLogFunction )
            TraceMessageCallback(0x2000000, "TelCacheProvider::RemoveItem failed [%#x]", v34);
          AslLogCallPrintf(
            1,
            "CDriverMap::RemoveDeletedDriverPackages",
            283,
            "TelCacheProvider::RemoveItem failed [%#x]",
            v34);
          LastError = (unsigned __int16)v34;
          break;
        }
      }
    }
  }
LABEL_64:
  FindClose((HANDLE)FirstFileW);
  CDriverPackage::~CDriverPackage((CDriverPackage *)v55);
  std::wstring::~wstring(v48);
  std::wstring::~wstring(lpFileName);
  return LastError;
}

```

## disassembly

```asm
0x180048300  push    rbp
0x180048302  push    rbx
0x180048303  push    rsi
0x180048304  push    rdi
0x180048305  push    r12
0x180048307  push    r13
0x180048309  push    r14
0x18004830b  push    r15
0x18004830d  lea     rbp, [rsp-6C8h]
0x180048315  sub     rsp, 7C8h
0x18004831c  mov     rax, cs:__security_cookie
0x180048323  xor     rax, rsp
0x180048326  mov     [rbp+700h+var_50], rax
0x18004832d  mov     r14, rcx
0x180048330  xorps   xmm0, xmm0
0x180048333  movups  xmmword ptr [rsp+800h+lpFileName], xmm0
0x180048338  xor     r12d, r12d
0x18004833b  mov     [rsp+800h+var_7B8], r12
0x180048340  lea     r13d, [r12+7]
0x180048345  mov     [rsp+800h+var_7B0], r13
0x18004834a  mov     word ptr [rsp+800h+lpFileName], r12w
0x180048350  movups  xmmword ptr [rsp+800h+var_7A8], xmm0
0x180048355  mov     [rsp+800h+var_798], r12
0x18004835a  mov     [rsp+800h+var_790], r13
0x18004835f  mov     word ptr [rsp+800h+var_7A8], r12w
0x180048365  or      r15, 0FFFFFFFFFFFFFFFFh
0x180048369  xor     edx, edx; Val
0x18004836b  mov     r8d, 250h; Size
0x180048371  lea     rcx, [rbp+700h+FindFileData]; void *
0x180048375  call    memset_0
0x18004837a  lea     rcx, [rbp+700h+var_510]; this
0x180048381  call    ??0CDriverPackage@@QEAA@XZ; CDriverPackage::CDriverPackage(void)
0x180048386  nop
0x180048387  xor     edx, edx; Val
0x180048389  mov     r8d, 208h; Size
0x18004838f  lea     rcx, [rbp+700h+Buffer]; void *
0x180048396  call    memset_0
0x18004839b  cmp     cs:qword_1801572C8, r12
0x1800483a2  jz      loc_1800487DB
0x1800483a8  mov     edx, 104h; uSize
0x1800483ad  lea     rcx, [rbp+700h+Buffer]; lpBuffer
0x1800483b4  call    cs:__imp_GetSystemDirectoryW
0x1800483ba  test    eax, eax
0x1800483bc  jnz     short loc_1800483D8
0x1800483be  call    cs:__imp_GetLastError
0x1800483c4  mov     esi, eax
0x1800483c6  lea     rbx, aGetsystemdirec; "GetSystemDirectory failed with [%d]"
0x1800483cd  mov     r13d, 0E8h
0x1800483d3  jmp     loc_1800487ED
0x1800483d8  add     r14, 98h
0x1800483df  mov     rdi, [r14]
0x1800483e2  mov     rsi, [rdi+8]
0x1800483e6  jmp     short loc_180048413
0x1800483e8  mov     r8, [rsi+10h]
0x1800483ec  mov     rdx, r14
0x1800483ef  mov     rcx, r14
0x1800483f2  call    ??$_Erase_tree@V?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAVCDriverPackage@@@std@@PEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAVCDriverPackage@@@std@@@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAVCDriverPackage@@@std@@PEAX@std@@@1@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAVCDriverPackage@@@std@@PEAX@1@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,CDriverPackage *>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<std::wstring const,CDriverPackage *>,void *>>>(std::allocator<std::_Tree_node<std::pair<std::wstring const,CDriverPackage *>,void *>> &,std::_Tree_node<std::pair<std::wstring const,CDriverPackage *>,void *> *)
0x1800483f7  mov     rbx, rsi
0x1800483fa  mov     rsi, [rsi]
0x1800483fd  lea     rcx, [rbx+20h]; void *
0x180048401  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180048406  mov     edx, 48h ; 'H'
0x18004840b  mov     rcx, rbx; Block
0x18004840e  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180048413  cmp     [rsi+19h], r12b
0x180048417  jz      short loc_1800483E8
0x180048419  mov     [rdi+8], rdi
0x18004841d  mov     [rdi], rdi
0x180048420  mov     [rdi+10h], rdi
0x180048424  mov     [r14+8], r12
0x180048428  lea     rax, [rbp+700h+Buffer]
0x18004842f  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180048433  inc     rdx
0x180048436  cmp     [rax+rdx*2], r12w
0x18004843b  jnz     short loc_180048433
0x18004843d  cmp     rdx, [rsp+800h+var_7B0]
0x180048442  ja      short loc_180048476
0x180048444  lea     rdi, [rsp+800h+lpFileName]
0x180048449  cmp     [rsp+800h+var_7B0], r13
0x18004844e  cmova   rdi, [rsp+800h+lpFileName]
0x180048454  mov     [rsp+800h+var_7B8], rdx
0x180048459  lea     rbx, [rdx+rdx]
0x18004845d  mov     r8, rbx; Size
0x180048460  lea     rdx, [rbp+700h+Buffer]; Src
0x180048467  mov     rcx, rdi; void *
0x18004846a  call    memmove_0
0x18004846f  mov     [rdi+rbx], r12w
0x180048474  jmp     short loc_180048487
0x180048476  lea     r9, [rbp+700h+Buffer]
0x18004847d  lea     rcx, [rsp+800h+lpFileName]
0x180048482  call    ??$_Reallocate_for@V_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@Z; std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *>(unsigned __int64,_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *)
0x180048487  lea     rdx, aDriverstoreFil; "\\DriverStore\\FileRepository\\*"
0x18004848e  lea     rcx, [rsp+800h+lpFileName]; Src
0x180048493  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x180048498  lea     rcx, [rsp+800h+lpFileName]
0x18004849d  cmp     [rsp+800h+var_7B0], r13
0x1800484a2  cmova   rcx, [rsp+800h+lpFileName]; lpFileName
0x1800484a8  lea     rdx, [rbp+700h+FindFileData]; lpFindFileData
0x1800484ac  call    cs:__imp_FindFirstFileW
0x1800484b2  mov     r15, rax
0x1800484b5  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800484b9  jnz     loc_1800485CA
0x1800484bf  lea     edi, [rax+3]
0x1800484c2  mov     esi, edi
0x1800484c4  lea     rcx, [rsp+800h+lpFileName]
0x1800484c9  cmp     [rsp+800h+var_7B0], r13
0x1800484ce  cmova   rcx, [rsp+800h+lpFileName]
0x1800484d4  mov     dword ptr [rsp+800h+var_7D8], edi
0x1800484d8  mov     [rsp+800h+var_7E0], rcx
0x1800484dd  lea     r9, aNoDriverPackag; "No driver package file in: %ws [%d]"
0x1800484e4  mov     r8d, 0F6h
0x1800484ea  lea     r14, aCdrivermapRemo; "CDriverMap::RemoveDeletedDriverPackages"
0x1800484f1  mov     rdx, r14
0x1800484f4  mov     ecx, edi
0x1800484f6  call    AslLogCallPrintf
0x1800484fb  cmp     cs:EnableDevInvStdErrLog, r12d
0x180048502  jz      short loc_180048565
0x180048504  mov     ecx, edi; Ix
0x180048506  call    _o___acrt_iob_func_0
0x18004850b  mov     rcx, rax; Stream
0x18004850e  mov     r9d, 0F6h
0x180048514  mov     r8, r14
0x180048517  lea     rdx, Format; "Error: %s, %u: "
0x18004851e  call    fprintf
0x180048523  lea     rbx, [rsp+800h+lpFileName]
0x180048528  cmp     [rsp+800h+var_7B0], r13
0x18004852d  cmova   rbx, [rsp+800h+lpFileName]
0x180048533  mov     ecx, edi; Ix
0x180048535  call    _o___acrt_iob_func_0
0x18004853a  mov     r9d, edi
0x18004853d  mov     r8, rbx
0x180048540  lea     rdx, aNoDriverPackag; "No driver package file in: %ws [%d]"
0x180048547  mov     rcx, rax; Stream
0x18004854a  call    fprintf
0x18004854f  mov     ecx, edi; Ix
0x180048551  call    _o___acrt_iob_func_0
0x180048556  mov     rcx, rax; Stream
0x180048559  lea     rdx, asc_18011EAD8; "\n"
0x180048560  call    fprintf
0x180048565  cmp     cs:g_DeviceMapLogFunction, r12
0x18004856c  jz      short loc_180048592
0x18004856e  lea     r8, [rsp+800h+lpFileName]
0x180048573  cmp     [rsp+800h+var_7B0], r13
0x180048578  cmova   r8, [rsp+800h+lpFileName]
0x18004857e  mov     r9d, edi
0x180048581  lea     rdx, aNoDriverPackag; "No driver package file in: %ws [%d]"
0x180048588  mov     ecx, 2000000h
0x18004858d  call    TraceMessageCallback
0x180048592  lea     rax, [rsp+800h+lpFileName]
0x180048597  cmp     [rsp+800h+var_7B0], r13
0x18004859c  cmova   rax, [rsp+800h+lpFileName]
0x1800485a2  mov     dword ptr [rsp+800h+var_7D8], edi
0x1800485a6  mov     [rsp+800h+var_7E0], rax
0x1800485ab  lea     r9, aNoDriverPackag; "No driver package file in: %ws [%d]"
0x1800485b2  mov     r8d, 0F6h
0x1800485b8  mov     rdx, r14
0x1800485bb  mov     ecx, 1
0x1800485c0  call    AslLogCallPrintf
0x1800485c5  jmp     loc_18004888D
0x1800485ca  test    byte ptr [rbp+700h+FindFileData.dwFileAttributes], 10h
0x1800485ce  jz      short loc_180048639
0x1800485d0  lea     rax, [rbp+700h+FindFileData.cFileName]
0x1800485d4  or      rdx, 0FFFFFFFFFFFFFFFFh
0x1800485d8  inc     rdx
0x1800485db  cmp     [rax+rdx*2], r12w
0x1800485e0  jnz     short loc_1800485D8
0x1800485e2  cmp     rdx, [rsp+800h+var_790]
0x1800485e7  ja      short loc_180048618
0x1800485e9  lea     rdi, [rsp+800h+var_7A8]
0x1800485ee  cmp     [rsp+800h+var_790], r13
0x1800485f3  cmova   rdi, [rsp+800h+var_7A8]
0x1800485f9  mov     [rsp+800h+var_798], rdx
0x1800485fe  lea     rbx, [rdx+rdx]
0x180048602  mov     r8, rbx; Size
0x180048605  lea     rdx, [rbp+700h+FindFileData.cFileName]; Src
0x180048609  mov     rcx, rdi; void *
0x18004860c  call    memmove_0
0x180048611  mov     [rdi+rbx], r12w
0x180048616  jmp     short loc_180048626
0x180048618  lea     r9, [rbp+700h+FindFileData.cFileName]
0x18004861c  lea     rcx, [rsp+800h+var_7A8]
0x180048621  call    ??$_Reallocate_for@V_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@Z; std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *>(unsigned __int64,_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *)
0x180048626  lea     rdx, [rsp+800h+var_7A8]
0x18004862b  mov     rcx, r14
0x18004862e  call    ??A?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@KU?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@std@@@2@@std@@QEAAAEAKAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::map<std::wstring,ulong>::operator[](std::wstring const &)
0x180048633  mov     dword ptr [rax], 1
0x180048639  lea     rdx, [rbp+700h+FindFileData]; lpFindFileData
0x18004863d  mov     rcx, r15; hFindFile
0x180048640  call    cs:__imp_FindNextFileW
0x180048646  test    eax, eax
0x180048648  jnz     short loc_1800485CA
0x18004864a  call    cs:__imp_GetLastError
0x180048650  mov     esi, eax
0x180048652  test    eax, eax
0x180048654  jz      short loc_18004866D
0x180048656  cmp     eax, 12h
0x180048659  jz      short loc_18004866D
0x18004865b  lea     rbx, aGetSubfolderFa; "Get subfolder failed: [%d]"
0x180048662  mov     r13d, 10Ch
0x180048668  jmp     loc_1800487ED
0x18004866d  mov     esi, r12d
0x180048670  lea     rdx, [rbp+700h+var_510]; struct IAmiInventoryItem *
0x180048677  lea     rcx, ?g_DriverPackageStore@@3VTelCacheProvider@@A; this
0x18004867e  call    ?GetFirstItem@TelCacheProvider@@QEAAJPEAVIAmiInventoryItem@@@Z; TelCacheProvider::GetFirstItem(IAmiInventoryItem *)
0x180048683  jmp     loc_180048719
0x180048688  lea     rdx, [rbp+700h+var_490]
0x18004868f  cmp     [rbp+700h+var_478], r13
0x180048696  cmova   rdx, [rbp+700h+var_490]
0x18004869e  xorps   xmm0, xmm0
0x1800486a1  movups  [rsp+800h+var_788], xmm0
0x1800486a6  mov     [rbp+700h+var_778], r12
0x1800486aa  mov     [rbp+700h+var_770], r12
0x1800486ae  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800486b2  inc     r8
0x1800486b5  cmp     [rdx+r8*2], r12w
0x1800486ba  jnz     short loc_1800486B2
0x1800486bc  lea     rcx, [rsp+800h+var_788]
0x1800486c1  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x1800486c6  lea     r8, [rsp+800h+var_788]
0x1800486cb  lea     rdx, [rsp+800h+var_7D0]
0x1800486d0  mov     rcx, r14
0x1800486d3  call    ?find@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@HU?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@H@std@@@2@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@H@std@@@std@@@std@@@2@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::_Tree<std::_Tmap_traits<std::wstring,int,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,int>>,0>>::find(std::wstring const &)
0x1800486d8  mov     rdi, [r14]
0x1800486db  mov     rbx, [rax]
0x1800486de  lea     rcx, [rsp+800h+var_788]; void *
0x1800486e3  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800486e8  cmp     rbx, rdi
0x1800486eb  jnz     short loc_180048706
0x1800486ed  lea     rdx, [rbp+700h+var_510]; struct IAmiInventoryItem *
0x1800486f4  lea     rcx, ?g_DriverPackageStore@@3VTelCacheProvider@@A; this
0x1800486fb  call    ?RemoveItem@TelCacheProvider@@QEAAJPEAVIAmiInventoryItem@@@Z; TelCacheProvider::RemoveItem(IAmiInventoryItem *)
0x180048700  mov     ebx, eax
0x180048702  test    eax, eax
0x180048704  js      short loc_180048726
0x180048706  lea     rdx, [rbp+700h+var_510]; struct IAmiInventoryItem *
0x18004870d  lea     rcx, ?g_DriverPackageStore@@3VTelCacheProvider@@A; this
0x180048714  call    ?GetNextItem@TelCacheProvider@@QEAAJPEAVIAmiInventoryItem@@@Z; TelCacheProvider::GetNextItem(IAmiInventoryItem *)
0x180048719  test    eax, eax
0x18004871b  jns     loc_180048688
0x180048721  jmp     loc_18004888D
0x180048726  mov     dword ptr [rsp+800h+var_7E0], ebx
0x18004872a  lea     rsi, aTelcacheprovid_16; "TelCacheProvider::RemoveItem failed [%#"...
0x180048731  mov     r9, rsi
0x180048734  mov     r13d, 11Bh
0x18004873a  mov     r8d, r13d
0x18004873d  lea     r14, aCdrivermapRemo; "CDriverMap::RemoveDeletedDriverPackages"
0x180048744  mov     rdx, r14
0x180048747  mov     edi, 2
0x18004874c  mov     ecx, edi
0x18004874e  call    AslLogCallPrintf
0x180048753  cmp     cs:EnableDevInvStdErrLog, r12d
0x18004875a  jz      short loc_1800487A3
0x18004875c  mov     ecx, edi; Ix
0x18004875e  call    _o___acrt_iob_func_0
0x180048763  mov     rcx, rax; Stream
0x180048766  mov     r9d, r13d
0x180048769  mov     r8, r14
0x18004876c  lea     rdx, Format; "Error: %s, %u: "
0x180048773  call    fprintf
0x180048778  mov     ecx, edi; Ix
0x18004877a  call    _o___acrt_iob_func_0
0x18004877f  mov     rcx, rax; Stream
0x180048782  mov     r8d, ebx
0x180048785  mov     rdx, rsi; Format
0x180048788  call    fprintf
0x18004878d  mov     ecx, edi; Ix
0x18004878f  call    _o___acrt_iob_func_0
0x180048794  mov     rcx, rax; Stream
0x180048797  lea     rdx, asc_18011EAD8; "\n"
0x18004879e  call    fprintf
0x1800487a3  cmp     cs:g_DeviceMapLogFunction, r12
0x1800487aa  jz      short loc_1800487BC
0x1800487ac  mov     r8d, ebx
0x1800487af  mov     rdx, rsi
0x1800487b2  mov     ecx, 2000000h
0x1800487b7  call    TraceMessageCallback
0x1800487bc  mov     dword ptr [rsp+800h+var_7E0], ebx
0x1800487c0  mov     r9, rsi
0x1800487c3  mov     r8, r13
0x1800487c6  mov     rdx, r14
0x1800487c9  mov     ecx, 1
0x1800487ce  call    AslLogCallPrintf
0x1800487d3  movzx   esi, bx
0x1800487d6  jmp     loc_18004888D
0x1800487db  mov     esi, 6
0x1800487e0  lea     rbx, aDriverpackages_0; "DriverPackageStore store is not initial"...
0x1800487e7  mov     r13d, 0E1h
0x1800487ed  lea     r14, aCdrivermapRemo; "CDriverMap::RemoveDeletedDriverPackages"
0x1800487f4  mov     edi, 2
0x1800487f9  mov     dword ptr [rsp+800h+var_7E0], esi
0x1800487fd  mov     r9, rbx
0x180048800  mov     r8, r13
0x180048803  mov     rdx, r14
0x180048806  mov     ecx, edi
0x180048808  call    AslLogCallPrintf
0x18004880d  cmp     cs:EnableDevInvStdErrLog, r12d
0x180048814  jz      short loc_18004885D
0x180048816  mov     ecx, edi; Ix
0x180048818  call    _o___acrt_iob_func_0
0x18004881d  mov     r9d, r13d
  ... truncated ...
```
