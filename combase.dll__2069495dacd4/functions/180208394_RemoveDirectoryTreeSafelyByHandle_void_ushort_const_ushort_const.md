# RemoveDirectoryTreeSafelyByHandle(void *,ushort const *,ushort const *)

- ea: `0x180208394`
- end: `0x180208b8e`
- name: `?RemoveDirectoryTreeSafelyByHandle@@YAJPEAXPEBG1@Z`
- size: `2042`
- prototype: `__int64 __fastcall(void *folderHandle, const wchar_t *rootFolderPath, const wchar_t *)`
- caller_count: `2`
- callee_count: `15`
- tags: `file_ops, reparse_path, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1801a3934`
- `0x180208394`

## callees

- `0x180058e20`
- `0x18005ce9c`
- `0x1800d141c`
- `0x180188554`
- `0x1801999b0`
- `0x18019a654`
- `0x18019ad93`
- `0x18019ad9f`
- `0x18019adf8`
- `0x180208048`
- `0x1802081c8`
- `0x180208248`
- `0x180208358`
- `0x180208394`
- `0x180208b94`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!FindClose` at `0x1802084df`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x180208572`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x180208607`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x1802089c4`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x180208a8e`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x180208b07`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x180208b7d`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x1802084df`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x180208572`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x180208607`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x1802089c4`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x180208a8e`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x180208b07`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x180208b7d`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x1802088b9`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x1802088b9`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x180208815`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x180208906`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x180208815`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x180208906`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x18020858b`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x18020858b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1802084c9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18020854d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180208560`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1802085e2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1802085f5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18020861b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1802087fb`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18020889f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1802088db`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1802088ee`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180208981`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18020899f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1802089b2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1802089d9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180208a4b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180208a69`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180208a7c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180208ade`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180208af1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180208b58`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180208b6b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1802084c9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18020854d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180208560`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1802085e2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1802085f5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18020861b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1802087fb`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18020889f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1802088db`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1802088ee`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180208981`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18020899f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1802089b2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1802089d9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180208a4b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180208a69`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180208a7c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180208ade`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180208af1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180208b58`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180208b6b`

## string_xrefs

- `0x180208a20`: `Failed to get file final path for folder %ws`
- `0x180208b2f`: `Failed to create full name for %ws and %ws`
- `0x1802086e8`: `Failed to create handle for %ws`
- `0x1802087d2`: `Failed in RemoveDirectoryTreeSafelyByHandle for folder %ws`
- `0x180208836`: `Failed to set file delete disposition for file %ws`
- `0x180208447`: `onecore\base\appmodel\common\fileutils.cpp`
- `0x180208462`: `onecore\base\appmodel\common\fileutils.cpp`
- `0x180208522`: `Failed to create full name for folder %ws`
- `0x18020849e`: `Failed to get final path for folder %ws`
- `0x180208928`: `Failed to set file delete disposition for folder %ws`

## pseudocode

```c
__int64 __fastcall RemoveDirectoryTreeSafelyByHandle(
        void *folderHandle,
        const wchar_t *rootFolderPath,
        const wchar_t *a3)
{
  const wchar_t *v3; // r14
  void *v4; // r15
  HRESULT v5; // r13d
  wchar_t *v6; // rdi
  HRESULT FileAttributesFromHandle; // ebx
  const wchar_t *v8; // rax
  const wchar_t *v9; // rax
  wchar_t *p; // rbx
  HRESULT v11; // esi
  const wchar_t *v12; // rax
  wchar_t *v13; // rsi
  const wchar_t *v14; // rax
  HRESULT v15; // edi
  HRESULT LastErrorMsg; // r14d
  HANDLE FileW_0; // r14
  const wchar_t *v19; // rax
  HRESULT FinalPathFromHandle; // r15d
  unsigned __int64 v21; // rdx
  wchar_t *v22; // r15
  unsigned __int64 v23; // rax
  const wchar_t *v24; // rax
  const wchar_t *v25; // rax
  const wchar_t *v26; // rax
  __int64 v27; // r8
  const wchar_t *v28; // rax
  const wchar_t *v29; // rax
  const wchar_t *v30; // rax
  const wchar_t *v31; // rax
  const wchar_t *v32; // rax
  void *findNextFileHandle; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int fileAttributes; // [rsp+48h] [rbp-B8h] BYREF
  wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (__cdecl*)(void *),&CloseHandle> > > fileHandle; // [rsp+50h] [rbp-B0h] BYREF
  _FILE_DISPOSITION_INFORMATION_EX dispositionInfo; // [rsp+58h] [rbp-A8h] BYREF
  Common::AutoArray<unsigned short,&Common::AutoArrayDeallocate<unsigned short> > finalFolderPath; // [rsp+60h] [rbp-A0h] BYREF
  Common::AutoArray<unsigned short,&Common::AutoArrayDeallocate<unsigned short> > folderSearchPath; // [rsp+68h] [rbp-98h] BYREF
  Common::AutoArray<unsigned short,&Common::AutoArrayDeallocate<unsigned short> > finalFilePath; // [rsp+70h] [rbp-90h] BYREF
  Common::AutoArray<unsigned short,&Common::AutoArrayDeallocate<unsigned short> > fileToDelete; // [rsp+78h] [rbp-88h] BYREF
  const wchar_t *v41; // [rsp+80h] [rbp-80h]
  void *v42; // [rsp+88h] [rbp-78h]
  wil::details::lambda_call<<lambda_1cdfd8949a4319cbf53437d7f0f8ff46> > cleanup; // [rsp+90h] [rbp-70h]
  _WIN32_FIND_DATAW findData; // [rsp+A0h] [rbp-60h] BYREF
  void *retaddr; // [rsp+338h] [rbp+238h]

  v3 = rootFolderPath;
  v41 = rootFolderPath;
  v4 = folderHandle;
  v42 = folderHandle;
  v5 = 0;
  fileAttributes = 0;
  v6 = 0;
  fileToDelete.p = 0;
  findNextFileHandle = (void *)-1LL;
  memset_0(&findData, 0, sizeof(findData));
  dispositionInfo.Flags = 1;
  cleanup.m_lambda.findNextFileHandle = &findNextFileHandle;
  cleanup.m_call = 1;
  FileAttributesFromHandle = FileUtils::GetFileAttributesFromHandle(v4, &fileAttributes);
  if ( FileAttributesFromHandle < 0 )
  {
    v8 = FileUtils::RemovePIIfromPath(v3);
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      0x59u,
      "onecore\\base\\appmodel\\common\\fileutils.cpp",
      FileAttributesFromHandle,
      "Failed to get file attributes from handle for %ws",
      v8);
    goto LABEL_6;
  }
  if ( (fileAttributes & 0x410) == 0x10 )
  {
    finalFolderPath.p = 0;
    FileAttributesFromHandle = FileUtils::GetFinalPathFromHandle(v4, &finalFolderPath);
    if ( FileAttributesFromHandle < 0 )
    {
      v9 = FileUtils::RemovePIIfromPath(v3);
      wil::details::in1diag3::Return_HrMsg(
        retaddr,
        0x61u,
        "onecore\\base\\appmodel\\common\\fileutils.cpp",
        FileAttributesFromHandle,
        "Failed to get final path for folder %ws",
        v9);
      HeapFree(g_hHeap, 0, finalFolderPath.p);
LABEL_6:
      if ( findNextFileHandle != (void *)-1LL )
        FindClose(findNextFileHandle);
LABEL_17:
      HeapFree(g_hHeap, 0, 0);
      return (unsigned int)FileAttributesFromHandle;
    }
    folderSearchPath.p = 0;
    p = finalFolderPath.p;
    v11 = FileUtils::CreateFullFileName(finalFolderPath.p, L"*", &folderSearchPath);
    if ( v11 < 0 )
    {
      v12 = FileUtils::RemovePIIfromPath(v3);
      wil::details::in1diag3::Return_HrMsg(
        retaddr,
        0x65u,
        "onecore\\base\\appmodel\\common\\fileutils.cpp",
        v11,
        "Failed to create full name for folder %ws",
        v12);
      HeapFree(g_hHeap, 0, folderSearchPath.p);
      HeapFree(g_hHeap, 0, p);
      if ( findNextFileHandle != (void *)-1LL )
        FindClose(findNextFileHandle);
      FileAttributesFromHandle = v11;
      goto LABEL_17;
    }
    v13 = folderSearchPath.p;
    findNextFileHandle = FindFirstFileW(folderSearchPath.p, &findData);
    if ( GetLastError_0() != 2 )
    {
      if ( findNextFileHandle != (void *)-1LL )
      {
        while ( 1 )
        {
          if ( CompareStringOrdinal_0(findData.cFileName, -1, L".", -1, 1) != 2
            && CompareStringOrdinal_0(findData.cFileName, -1, L"..", -1, 1) != 2 )
          {
            LastErrorMsg = FileUtils::CreateFullFileName(p, findData.cFileName, &fileToDelete);
            if ( LastErrorMsg < 0 )
            {
              v32 = FileUtils::RemovePIIfromPath(p);
              wil::details::in1diag3::Return_HrMsg(
                retaddr,
                0x74u,
                "onecore\\base\\appmodel\\common\\fileutils.cpp",
                LastErrorMsg,
                "Failed to create full name for %ws and %ws",
                v32,
                findData.cFileName);
              HeapFree(g_hHeap, 0, v13);
              HeapFree(g_hHeap, 0, p);
              if ( findNextFileHandle != (void *)-1LL )
                FindClose(findNextFileHandle);
              v6 = fileToDelete.p;
              goto LABEL_50;
            }
            v6 = fileToDelete.p;
            FileW_0 = CreateFileW_0(fileToDelete.p, 0x10000u, 1u, 0, 3u, 0x2200000u, 0);
            fileHandle.m_ptr = FileW_0;
            if ( GetLastError_0() == 2 )
            {
              v19 = FileUtils::RemovePIIfromPath(v6);
              wil::details::in1diag3::Log_GetLastErrorMsg(
                retaddr,
                0x81u,
                "onecore\\base\\appmodel\\common\\fileutils.cpp",
                "Failed to create handle for %ws",
                v19);
            }
            else
            {
              if ( FileW_0 == (HANDLE)-1LL )
              {
                v31 = FileUtils::RemovePIIfromPath(v6);
                LastErrorMsg = wil::details::in1diag3::Return_GetLastErrorMsg(
                                 retaddr,
                                 0x84u,
                                 "onecore\\base\\appmodel\\common\\fileutils.cpp",
                                 "Failed to get handle for %ws",
                                 v31);
                goto LABEL_55;
              }
              finalFilePath.p = 0;
              FinalPathFromHandle = FileUtils::GetFinalPathFromHandle(FileW_0, &finalFilePath);
              if ( FinalPathFromHandle < 0 )
              {
                v30 = FileUtils::RemovePIIfromPath(v6);
                wil::details::in1diag3::Return_HrMsg(
                  retaddr,
                  0x88u,
                  "onecore\\base\\appmodel\\common\\fileutils.cpp",
                  FinalPathFromHandle,
                  "Failed to get file final path for folder %ws",
                  v30);
                HeapFree(g_hHeap, 0, finalFilePath.p);
                wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>((wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (__cdecl*)(void *),&CloseHandle> > *)&fileHandle);
                HeapFree(g_hHeap, 0, v13);
                HeapFree(g_hHeap, 0, p);
                if ( findNextFileHandle != (void *)-1LL )
                  FindClose(findNextFileHandle);
                LastErrorMsg = FinalPathFromHandle;
                goto LABEL_50;
              }
              v21 = -1;
              do
                ++v21;
              while ( p[v21] );
              v22 = finalFilePath.p;
              v23 = -1;
              do
                ++v23;
              while ( finalFilePath.p[v23] );
              if ( v21 <= v23 && CompareStringOrdinal_0(finalFilePath.p, v21, p, -1, 1) == 2 )
              {
                fileAttributes = 0;
                v5 = FileUtils::GetFileAttributesFromHandle(FileW_0, &fileAttributes);
                if ( v5 < 0 )
                {
                  v29 = FileUtils::RemovePIIfromPath(v6);
                  wil::details::in1diag3::Return_HrMsg(
                    retaddr,
                    0x94u,
                    "onecore\\base\\appmodel\\common\\fileutils.cpp",
                    v5,
                    "Failed to get file attributes from handle for folder %ws",
                    v29);
                  HeapFree(g_hHeap, 0, v22);
                  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>((wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (__cdecl*)(void *),&CloseHandle> > *)&fileHandle);
                  HeapFree(g_hHeap, 0, v13);
                  HeapFree(g_hHeap, 0, p);
                  goto LABEL_47;
                }
                if ( (fileAttributes & 0x410) == 0x10 )
                {
                  LastErrorMsg = RemoveDirectoryTreeSafelyByHandle(FileW_0, v6, L"*");
                  v5 = 0;
                  if ( LastErrorMsg < 0 )
                  {
                    v24 = FileUtils::RemovePIIfromPath(v6);
                    wil::details::in1diag3::Return_HrMsg(
                      retaddr,
                      0x9Au,
                      "onecore\\base\\appmodel\\common\\fileutils.cpp",
                      LastErrorMsg,
                      "Failed in RemoveDirectoryTreeSafelyByHandle for folder %ws",
                      v24);
                    goto LABEL_35;
                  }
                }
                else
                {
                  v5 = 0;
                  if ( !SetFileInformationByHandle(FileW_0, FileDispositionInfoEx, &dispositionInfo, 4u) )
                  {
                    v25 = FileUtils::RemovePIIfromPath(v6);
                    LastErrorMsg = wil::details::in1diag3::Return_GetLastErrorMsg(
                                     retaddr,
                                     0x9Fu,
                                     "onecore\\base\\appmodel\\common\\fileutils.cpp",
                                     "Failed to set file delete disposition for file %ws",
                                     v25);
LABEL_35:
                    HeapFree(g_hHeap, 0, v22);
LABEL_55:
                    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>((wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (__cdecl*)(void *),&CloseHandle> > *)&fileHandle);
                    HeapFree(g_hHeap, 0, v13);
                    HeapFree(g_hHeap, 0, p);
                    goto LABEL_56;
                  }
                }
              }
              else
              {
                FileUtils::RemovePIIfromPath(p);
                v26 = FileUtils::RemovePIIfromPath(v22);
                wil::details::in1diag3::Log_HrMsg(
                  retaddr,
                  0x8Eu,
                  "onecore\\base\\appmodel\\common\\fileutils.cpp",
                  -2147418113,
                  "File redirection found for %ws and %ws",
                  v26,
                  v27);
              }
              HeapFree(g_hHeap, 0, v22);
            }
            wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>((wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (__cdecl*)(void *),&CloseHandle> > *)&fileHandle);
          }
          if ( !FindNextFileW(findNextFileHandle, &findData) )
          {
            v3 = v41;
            v4 = v42;
            goto LABEL_43;
          }
        }
      }
      v14 = FileUtils::RemovePIIfromPath(v13);
      v15 = wil::details::in1diag3::Return_GetLastErrorMsg(
              retaddr,
              0x6Au,
              "onecore\\base\\appmodel\\common\\fileutils.cpp",
              "Failed to get file handle for %ws",
              v14);
      HeapFree(g_hHeap, 0, v13);
      HeapFree(g_hHeap, 0, p);
      if ( findNextFileHandle != (void *)-1LL )
        FindClose(findNextFileHandle);
      FileAttributesFromHandle = v15;
      goto LABEL_17;
    }
LABEL_43:
    HeapFree(g_hHeap, 0, v13);
    HeapFree(g_hHeap, 0, p);
  }
  if ( SetFileInformationByHandle(v4, FileDispositionInfoEx, &dispositionInfo, 4u) )
  {
LABEL_47:
    if ( findNextFileHandle != (void *)-1LL )
      FindClose(findNextFileHandle);
    LastErrorMsg = v5;
  }
  else
  {
    v28 = FileUtils::RemovePIIfromPath(v3);
    LastErrorMsg = wil::details::in1diag3::Return_GetLastErrorMsg(
                     retaddr,
                     0xA6u,
                     "onecore\\base\\appmodel\\common\\fileutils.cpp",
                     "Failed to set file delete disposition for folder %ws",
                     v28);
LABEL_56:
    if ( findNextFileHandle != (void *)-1LL )
      FindClose(findNextFileHandle);
  }
LABEL_50:
  HeapFree(g_hHeap, 0, v6);
  return (unsigned int)LastErrorMsg;
}

```

## disassembly

```asm
0x180208394  mov     [rsp-8+arg_10], rbx
0x180208399  push    rbp
0x18020839a  push    rsi
0x18020839b  push    rdi
0x18020839c  push    r12
0x18020839e  push    r13
0x1802083a0  push    r14
0x1802083a2  push    r15
0x1802083a4  lea     rbp, [rsp-200h]
0x1802083ac  sub     rsp, 300h
0x1802083b3  mov     rax, cs:__security_cookie
0x1802083ba  xor     rax, rsp
0x1802083bd  mov     [rbp+230h+var_40], rax
0x1802083c4  mov     r14, rootFolderPath
0x1802083c7  mov     [rbp+230h+var_2B0], rootFolderPath
0x1802083cb  mov     r15, folderHandle
0x1802083ce  mov     [rbp+230h+var_2A8], folderHandle
0x1802083d2  xor     r13d, r13d
0x1802083d5  mov     [rsp+330h+fileAttributes], r13d
0x1802083da  mov     edi, r13d
0x1802083dd  mov     [rsp+330h+fileToDelete.p], r13
0x1802083e2  mov     [rsp+330h+findNextFileHandle], 0FFFFFFFFFFFFFFFFh
0x1802083eb  xor     edx, edx; Val
0x1802083ed  mov     r8d, 250h; Size
0x1802083f3  lea     folderHandle, [rbp+230h+findData]; void *
0x1802083f7  call    memset_0
0x1802083fc  mov     [rsp+330h+dispositionInfo.Flags], 1
0x180208404  lea     rax, [rsp+330h+findNextFileHandle]
0x180208409  mov     [rbp+230h+cleanup.m_lambda.findNextFileHandle], rax
0x18020840d  mov     [rbp+230h+cleanup.m_call], 1
0x180208411  lea     rootFolderPath, [rsp+330h+fileAttributes]; fileAttributes
0x180208416  mov     folderHandle, r15; fileHandle
0x180208419  call    ?GetFileAttributesFromHandle@FileUtils@@YAJPEAXPEAK@Z; FileUtils::GetFileAttributesFromHandle(void *,ulong *)
0x18020841e  mov     ebx, eax
0x180208420  test    eax, eax
0x180208422  jns     short loc_180208459
0x180208424  mov     folderHandle, r14; path
0x180208427  call    ?RemovePIIfromPath@FileUtils@@YAPEBGPEBG@Z; FileUtils::RemovePIIfromPath(ushort const *)
0x18020842c  mov     folderHandle, [rbp+238h]; callerReturnAddress
0x180208433  mov     qword ptr [rsp+330h+dwFlagsAndAttributes], rax
0x180208438  lea     rax, aFailedToGetFil; "Failed to get file attributes from hand"...
0x18020843f  mov     [rsp+330h+formatString], rax; formatString
0x180208444  mov     r9d, ebx; hr
0x180208447  lea     r8, aOnecoreBaseApp; "onecore\\base\\appmodel\\common\\fileut"...
0x18020844e  lea     edx, [r13+59h]; lineNumber
0x180208452  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180208457  jmp     short loc_1802084D0
0x180208459  mov     eax, [rsp+330h+fileAttributes]
0x18020845d  and     eax, 410h
0x180208462  lea     r12, aOnecoreBaseApp; "onecore\\base\\appmodel\\common\\fileut"...
0x180208469  cmp     eax, 10h
0x18020846c  jnz     loc_1802088F4
0x180208472  mov     [rsp+330h+finalFolderPath.p], r13
0x180208477  lea     rootFolderPath, [rsp+330h+finalFolderPath]; finalPath
0x18020847c  mov     folderHandle, r15; pathHandle
0x18020847f  call    ?GetFinalPathFromHandle@FileUtils@@YAJPEAXAEAV?$AutoArray@G$1??$AutoArrayDeallocate@G@Common@@YAXPEAG@Z@Common@@@Z; FileUtils::GetFinalPathFromHandle(void *,Common::AutoArray<ushort,&Common::AutoArrayDeallocate<ushort>(ushort *)> &)
0x180208484  mov     ebx, eax
0x180208486  test    eax, eax
0x180208488  jns     short loc_1802084EA
0x18020848a  mov     folderHandle, r14; path
0x18020848d  call    ?RemovePIIfromPath@FileUtils@@YAPEBGPEBG@Z; FileUtils::RemovePIIfromPath(ushort const *)
0x180208492  mov     folderHandle, [rbp+238h]; callerReturnAddress
0x180208499  mov     qword ptr [rsp+330h+dwFlagsAndAttributes], rax
0x18020849e  lea     rax, aFailedToGetFin; "Failed to get final path for folder %ws"
0x1802084a5  mov     [rsp+330h+formatString], rax; formatString
0x1802084aa  mov     r9d, ebx; hr
0x1802084ad  mov     r8, r12; fileName
0x1802084b0  mov     edx, 61h ; 'a'; lineNumber
0x1802084b5  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x1802084ba  nop
0x1802084bb  mov     r8, [rsp+330h+finalFolderPath.p]; lpMem
0x1802084c0  xor     edx, edx; dwFlags
0x1802084c2  mov     folderHandle, cs:?g_hHeap@@3QEAXEA; hHeap
0x1802084c9  call    cs:__imp_HeapFree
0x1802084cf  nop
0x1802084d0  mov     folderHandle, [rsp+330h+findNextFileHandle]; hFindFile
0x1802084d5  cmp     folderHandle, 0FFFFFFFFFFFFFFFFh
0x1802084d9  jz      loc_18020860F
0x1802084df  call    cs:__imp_FindClose
0x1802084e5  jmp     loc_18020860F
0x1802084ea  mov     [rsp+330h+folderSearchPath.p], r13
0x1802084ef  lea     r8, [rsp+330h+folderSearchPath]; fullPath
0x1802084f4  lea     rootFolderPath, folderHandle; "*"
0x1802084fb  mov     rbx, [rsp+330h+finalFolderPath.p]
0x180208500  mov     folderHandle, rbx; startPath
0x180208503  call    ?CreateFullFileName@FileUtils@@YAJPEBG0AEAV?$AutoArray@G$1??$AutoArrayDeallocate@G@Common@@YAXPEAG@Z@Common@@@Z; FileUtils::CreateFullFileName(ushort const *,ushort const *,Common::AutoArray<ushort,&Common::AutoArrayDeallocate<ushort>(ushort *)> &)
0x180208508  mov     esi, eax
0x18020850a  test    eax, eax
0x18020850c  jns     short loc_18020857F
0x18020850e  mov     folderHandle, r14; path
0x180208511  call    ?RemovePIIfromPath@FileUtils@@YAPEBGPEBG@Z; FileUtils::RemovePIIfromPath(ushort const *)
0x180208516  mov     folderHandle, [rbp+238h]; callerReturnAddress
0x18020851d  mov     qword ptr [rsp+330h+dwFlagsAndAttributes], rax
0x180208522  lea     rax, aFailedToCreate_0; "Failed to create full name for folder %"...
0x180208529  mov     [rsp+330h+formatString], rax; formatString
0x18020852e  mov     r9d, esi; hr
0x180208531  mov     r8, r12; fileName
0x180208534  mov     edx, 65h ; 'e'; lineNumber
0x180208539  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18020853e  nop
0x18020853f  mov     r8, [rsp+330h+folderSearchPath.p]; lpMem
0x180208544  xor     edx, edx; dwFlags
0x180208546  mov     folderHandle, cs:?g_hHeap@@3QEAXEA; hHeap
0x18020854d  call    cs:__imp_HeapFree
0x180208553  nop
0x180208554  mov     r8, rbx; lpMem
0x180208557  xor     edx, edx; dwFlags
0x180208559  mov     folderHandle, cs:?g_hHeap@@3QEAXEA; hHeap
0x180208560  call    cs:__imp_HeapFree
0x180208566  nop
0x180208567  mov     folderHandle, [rsp+330h+findNextFileHandle]; hFindFile
0x18020856c  cmp     folderHandle, 0FFFFFFFFFFFFFFFFh
0x180208570  jz      short loc_180208578
0x180208572  call    cs:__imp_FindClose
0x180208578  mov     ebx, esi
0x18020857a  jmp     loc_18020860F
0x18020857f  lea     rootFolderPath, [rbp+230h+findData]; lpFindFileData
0x180208583  mov     rsi, [rsp+330h+folderSearchPath.p]
0x180208588  mov     folderHandle, rsi; lpFileName
0x18020858b  call    cs:__imp_FindFirstFileW
0x180208591  mov     [rsp+330h+findNextFileHandle], rax
0x180208596  call    GetLastError_0
0x18020859b  cmp     eax, 2
0x18020859e  jz      loc_1802088CF
0x1802085a4  cmp     [rsp+330h+findNextFileHandle], 0FFFFFFFFFFFFFFFFh
0x1802085aa  jnz     short loc_180208628
0x1802085ac  mov     folderHandle, rsi; path
0x1802085af  call    ?RemovePIIfromPath@FileUtils@@YAPEBGPEBG@Z; FileUtils::RemovePIIfromPath(ushort const *)
0x1802085b4  mov     folderHandle, [rbp+238h]; callerReturnAddress
0x1802085bb  mov     [rsp+330h+formatString], rax
0x1802085c0  lea     r9, aFailedToGetFil_0; "Failed to get file handle for %ws"
0x1802085c7  mov     r8, r12; fileName
0x1802085ca  mov     edx, 6Ah ; 'j'; lineNumber
0x1802085cf  call    ?Return_GetLastErrorMsg@in1diag3@details@wil@@YAJPEAXIPEBD1ZZ; wil::details::in1diag3::Return_GetLastErrorMsg(void *,uint,char const *,char const *,...)
0x1802085d4  mov     edi, eax
0x1802085d6  mov     r8, rsi; lpMem
0x1802085d9  xor     edx, edx; dwFlags
0x1802085db  mov     folderHandle, cs:?g_hHeap@@3QEAXEA; hHeap
0x1802085e2  call    cs:__imp_HeapFree
0x1802085e8  nop
0x1802085e9  mov     r8, rbx; lpMem
0x1802085ec  xor     edx, edx; dwFlags
0x1802085ee  mov     folderHandle, cs:?g_hHeap@@3QEAXEA; hHeap
0x1802085f5  call    cs:__imp_HeapFree
0x1802085fb  nop
0x1802085fc  mov     folderHandle, [rsp+330h+findNextFileHandle]; hFindFile
0x180208601  cmp     folderHandle, 0FFFFFFFFFFFFFFFFh
0x180208605  jz      short loc_18020860D
0x180208607  call    cs:__imp_FindClose
0x18020860d  mov     ebx, edi
0x18020860f  xor     r8d, r8d; lpMem
0x180208612  xor     edx, edx; dwFlags
0x180208614  mov     folderHandle, cs:?g_hHeap@@3QEAXEA; hHeap
0x18020861b  call    cs:__imp_HeapFree
0x180208621  mov     eax, ebx
0x180208623  jmp     loc_1802089E2
0x180208628  mov     dword ptr [rsp+330h+formatString], 1; bIgnoreCase
0x180208630  or      r9d, 0FFFFFFFFh; cchCount2
0x180208634  lea     r8, asc_1802A9DA0; "."
0x18020863b  or      edx, r9d; cchCount1
0x18020863e  lea     folderHandle, [rbp+230h+findData.cFileName]; lpString1
0x180208642  call    CompareStringOrdinal_0
0x180208647  cmp     eax, 2
0x18020864a  jz      loc_1802088B0
0x180208650  mov     dword ptr [rsp+330h+formatString], 1; bIgnoreCase
0x180208658  or      r9d, 0FFFFFFFFh; cchCount2
0x18020865c  lea     r8, asc_1802E3B00; ".."
0x180208663  or      edx, r9d; cchCount1
0x180208666  lea     folderHandle, [rbp+230h+findData.cFileName]; lpString1
0x18020866a  call    CompareStringOrdinal_0
0x18020866f  cmp     eax, 2
0x180208672  jz      loc_1802088B0
0x180208678  lea     r8, [rsp+330h+fileToDelete]; fullPath
0x18020867d  lea     rootFolderPath, [rbp+230h+findData.cFileName]; fileName
0x180208681  mov     folderHandle, rbx; startPath
0x180208684  call    ?CreateFullFileName@FileUtils@@YAJPEBG0AEAV?$AutoArray@G$1??$AutoArrayDeallocate@G@Common@@YAXPEAG@Z@Common@@@Z; FileUtils::CreateFullFileName(ushort const *,ushort const *,Common::AutoArray<ushort,&Common::AutoArrayDeallocate<ushort>(ushort *)> &)
0x180208689  mov     r14d, eax
0x18020868c  test    eax, eax
0x18020868e  js      loc_180208B12
0x180208694  mov     [rsp+330h+hTemplateFile], r13; hTemplateFile
0x180208699  mov     [rsp+330h+dwFlagsAndAttributes], 2200000h; dwFlagsAndAttributes
0x1802086a1  mov     dword ptr [rsp+330h+formatString], 3; dwCreationDisposition
0x1802086a9  xor     r9d, r9d; lpSecurityAttributes
0x1802086ac  mov     edx, 10000h; dwDesiredAccess
0x1802086b1  lea     r8d, [r9+1]; dwShareMode
0x1802086b5  mov     rdi, [rsp+330h+fileToDelete.p]
0x1802086ba  mov     folderHandle, rdi; lpFileName
0x1802086bd  call    CreateFileW_0
0x1802086c2  mov     r14, rax
0x1802086c5  mov     [rsp+330h+fileHandle.m_ptr], rax
0x1802086ca  call    GetLastError_0
0x1802086cf  cmp     eax, 2
0x1802086d2  jnz     short loc_180208701
0x1802086d4  mov     folderHandle, rdi; path
0x1802086d7  call    ?RemovePIIfromPath@FileUtils@@YAPEBGPEBG@Z; FileUtils::RemovePIIfromPath(ushort const *)
0x1802086dc  mov     folderHandle, [rbp+238h]; callerReturnAddress
0x1802086e3  mov     [rsp+330h+formatString], rax
0x1802086e8  lea     r9, aFailedToCreate_1; "Failed to create handle for %ws"
0x1802086ef  mov     r8, r12; fileName
0x1802086f2  mov     edx, 81h; lineNumber
0x1802086f7  call    ?Log_GetLastErrorMsg@in1diag3@details@wil@@YAKPEAXIPEBD1ZZ; wil::details::in1diag3::Log_GetLastErrorMsg(void *,uint,char const *,char const *,...)
0x1802086fc  jmp     loc_1802088A6
0x180208701  cmp     r14, 0FFFFFFFFFFFFFFFFh
0x180208705  jz      loc_180208A9C
0x18020870b  mov     [rsp+330h+finalFilePath.p], r13
0x180208710  lea     rootFolderPath, [rsp+330h+finalFilePath]; finalPath
0x180208715  mov     folderHandle, r14; pathHandle
0x180208718  call    ?GetFinalPathFromHandle@FileUtils@@YAJPEAXAEAV?$AutoArray@G$1??$AutoArrayDeallocate@G@Common@@YAXPEAG@Z@Common@@@Z; FileUtils::GetFinalPathFromHandle(void *,Common::AutoArray<ushort,&Common::AutoArrayDeallocate<ushort>(ushort *)> &)
0x18020871d  mov     r15d, eax
0x180208720  test    eax, eax
0x180208722  js      loc_180208A0C
0x180208728  or      folderHandle, 0FFFFFFFFFFFFFFFFh
0x18020872c  mov     rootFolderPath, folderHandle
0x18020872f  inc     rootFolderPath; cchCount1
0x180208732  cmp     [rbx+rootFolderPath*2], r13w
0x180208737  jnz     short loc_18020872F
0x180208739  mov     r15, [rsp+330h+finalFilePath.p]
0x18020873e  mov     rax, folderHandle
0x180208741  inc     rax
0x180208744  cmp     [r15+rax*2], r13w
0x180208749  jnz     short loc_180208741
0x18020874b  cmp     rootFolderPath, rax
0x18020874e  ja      loc_18020884F
0x180208754  mov     dword ptr [rsp+330h+formatString], 1; bIgnoreCase
0x18020875c  mov     r9d, ecx; cchCount2
0x18020875f  mov     r8, rbx; lpString2
0x180208762  mov     folderHandle, r15; lpString1
0x180208765  call    CompareStringOrdinal_0
0x18020876a  cmp     eax, 2
0x18020876d  jnz     loc_18020884F
0x180208773  mov     [rsp+330h+fileAttributes], r13d
0x180208778  lea     rootFolderPath, [rsp+330h+fileAttributes]; fileAttributes
0x18020877d  mov     folderHandle, r14; fileHandle
0x180208780  call    ?GetFileAttributesFromHandle@FileUtils@@YAJPEAXPEAK@Z; FileUtils::GetFileAttributesFromHandle(void *,ulong *)
0x180208785  mov     r13d, eax
0x180208788  test    eax, eax
0x18020878a  js      loc_180208944
0x180208790  mov     eax, [rsp+330h+fileAttributes]
0x180208794  and     eax, 410h
0x180208799  mov     folderHandle, r14; hFile
0x18020879c  cmp     eax, 10h
0x18020879f  jnz     short loc_180208806
0x1802087a1  lea     r8, folderHandle; "*"
0x1802087a8  mov     rootFolderPath, rdi; rootFolderPath
0x1802087ab  call    ?RemoveDirectoryTreeSafelyByHandle@@YAJPEAXPEBG1@Z; RemoveDirectoryTreeSafelyByHandle(void *,ushort const *,ushort const *)
0x1802087b0  mov     r14d, eax
0x1802087b3  xor     r13d, r13d
0x1802087b6  test    eax, eax
0x1802087b8  jns     loc_180208893
0x1802087be  mov     folderHandle, rdi; path
0x1802087c1  call    ?RemovePIIfromPath@FileUtils@@YAPEBGPEBG@Z; FileUtils::RemovePIIfromPath(ushort const *)
0x1802087c6  mov     folderHandle, [rbp+238h]; callerReturnAddress
0x1802087cd  mov     qword ptr [rsp+330h+dwFlagsAndAttributes], rax
0x1802087d2  lea     rax, aFailedInRemove; "Failed in RemoveDirectoryTreeSafelyByHa"...
0x1802087d9  mov     [rsp+330h+formatString], rax; formatString
0x1802087de  mov     r9d, r14d; hr
0x1802087e1  mov     r8, r12; fileName
0x1802087e4  mov     edx, 9Ah; lineNumber
0x1802087e9  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x1802087ee  nop
0x1802087ef  mov     r8, r15; lpMem
0x1802087f2  xor     edx, edx; dwFlags
0x1802087f4  mov     folderHandle, cs:?g_hHeap@@3QEAXEA; hHeap
0x1802087fb  call    cs:__imp_HeapFree
0x180208801  jmp     loc_180208AC7
0x180208806  mov     r9d, 4; dwBufferSize
0x18020880c  lea     r8, [rsp+330h+dispositionInfo]; lpFileInformation
0x180208811  lea     edx, [r9+11h]; FileInformationClass
0x180208815  call    cs:__imp_SetFileInformationByHandle
0x18020881b  xor     r13d, r13d
0x18020881e  test    eax, eax
0x180208820  jnz     short loc_180208893
0x180208822  mov     folderHandle, rdi; path
0x180208825  call    ?RemovePIIfromPath@FileUtils@@YAPEBGPEBG@Z; FileUtils::RemovePIIfromPath(ushort const *)
0x18020882a  mov     folderHandle, [rbp+238h]; callerReturnAddress
0x180208831  mov     [rsp+330h+formatString], rax
0x180208836  lea     r9, aFailedToSetFil_0; "Failed to set file delete disposition f"...
0x18020883d  mov     r8, r12; fileName
0x180208840  mov     edx, 9Fh; lineNumber
0x180208845  call    ?Return_GetLastErrorMsg@in1diag3@details@wil@@YAJPEAXIPEBD1ZZ; wil::details::in1diag3::Return_GetLastErrorMsg(void *,uint,char const *,char const *,...)
0x18020884a  mov     r14d, eax
0x18020884d  jmp     short loc_1802087EF
0x18020884f  mov     folderHandle, rbx; path
0x180208852  call    ?RemovePIIfromPath@FileUtils@@YAPEBGPEBG@Z; FileUtils::RemovePIIfromPath(ushort const *)
0x180208857  mov     r8, rax
0x18020885a  mov     folderHandle, r15; path
0x18020885d  call    ?RemovePIIfromPath@FileUtils@@YAPEBGPEBG@Z; FileUtils::RemovePIIfromPath(ushort const *)
0x180208862  mov     folderHandle, [rbp+238h]; callerReturnAddress
0x180208869  mov     [rsp+330h+hTemplateFile], r8
0x18020886e  mov     qword ptr [rsp+330h+dwFlagsAndAttributes], rax
0x180208873  lea     rax, aFileRedirectio; "File redirection found for %ws and %ws"
0x18020887a  mov     [rsp+330h+formatString], rax; formatString
0x18020887f  mov     r9d, 8000FFFFh; hr
0x180208885  mov     r8, r12; fileName
0x180208888  mov     edx, 8Eh; lineNumber
0x18020888d  call    ?Log_HrMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_HrMsg(void *,uint,char const *,long,char const *,...)
0x180208892  nop
0x180208893  mov     r8, r15; lpMem
0x180208896  xor     edx, edx; dwFlags
0x180208898  mov     folderHandle, cs:?g_hHeap@@3QEAXEA; hHeap
  ... truncated ...
```
