# DSUtils::CopyFileWithProgress(ushort const *,void *,void *,void *)

- ea: `0x180019e70`
- end: `0x180019fe1`
- name: `?CopyFileWithProgress@DSUtils@@YAJPEBGPEAX11@Z`
- size: `369`
- prototype: `__int64 __fastcall(DSUtils *this, unsigned __int16 *, void *, void *)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, reparse_path`

## callers

- `0x18000ca4c`

## callees

- `0x180006cb0`
- `0x180006f78`
- `0x18000bf80`
- `0x180019e70`
- `0x18001a330`
- `0x18001a518`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019f6c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019f6c`
- `api-ms-win-core-file-l2-1-0!CopyFileExW` at `0x180019f62`
- `api-ms-win-core-file-l2-1-0!CopyFileExW` at `0x180019f62`

## string_xrefs

- `0x180019f1c`: `DSUtils::CopyFileWithProgress: Found target hardlink file path %s`
- `0x180019f29`: `DSUtils::CopyFileWithProgress`
- `0x180019fae`: `DSUtils::CopyFileWithProgress`
- `0x180019fa1`: `DSUtils::CopyFileWithProgress: Failed to copy file for token %s from source file %s to destination file %s. hr=0x%x`

## pseudocode

```c
__int64 __fastcall DSUtils::CopyFileWithProgress(DSUtils *this, unsigned __int16 *a2, void *a3, void *a4)
{
  int FinalPathFromHandle; // ebx
  bool *v8; // r8
  __int64 v9; // rdx
  __int64 v10; // rcx
  __int64 v11; // r8
  __int64 v12; // r9
  DSLogger *v13; // rax
  signed int LastError; // eax
  __int64 v15; // rdx
  __int64 v16; // rcx
  __int64 v17; // r8
  __int64 v18; // r9
  DSLogger *v19; // rax
  _BYTE v21[4]; // [rsp+40h] [rbp-19h] BYREF
  WINBOOL pbCancel; // [rsp+44h] [rbp-15h] BYREF
  LPCWSTR lpNewFileName[2]; // [rsp+48h] [rbp-11h] BYREF
  _WORD v24[8]; // [rsp+58h] [rbp-1h] BYREF
  LPCWSTR lpExistingFileName[2]; // [rsp+68h] [rbp+Fh] BYREF
  _WORD v26[28]; // [rsp+78h] [rbp+1Fh] BYREF

  pbCancel = 0;
  lpExistingFileName[0] = v26;
  lpExistingFileName[1] = v26;
  v26[0] = 0;
  lpNewFileName[0] = v24;
  lpNewFileName[1] = v24;
  v24[0] = 0;
  FinalPathFromHandle = DSUtils::GetFinalPathFromHandle(a2, (__int64)lpExistingFileName);
  if ( FinalPathFromHandle >= 0 )
  {
    FinalPathFromHandle = DSUtils::GetFinalPathFromHandle(a3, (__int64)lpNewFileName);
    if ( FinalPathFromHandle >= 0 )
    {
      v21[0] = 0;
      FinalPathFromHandle = DSUtils::IsHardLinkFile(a3, v21, v8);
      if ( FinalPathFromHandle >= 0 )
      {
        if ( v21[0] )
        {
          v13 = (DSLogger *)tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get(
                              v10,
                              v9,
                              v11,
                              v12);
          DSLogger::LogError(
            v13,
            L"DSUtils::CopyFileWithProgress",
            0x273u,
            L"DSUtils::CopyFileWithProgress: Found target hardlink file path %s",
            lpNewFileName[0]);
          FinalPathFromHandle = -1055719416;
        }
        else if ( !CopyFileExW(
                     lpExistingFileName[0],
                     lpNewFileName[0],
                     (LPPROGRESS_ROUTINE)CopyFileProgressRoutine,
                     a4,
                     &pbCancel,
                     0) )
        {
          LastError = GetLastError();
          FinalPathFromHandle = LastError;
          if ( LastError > 0 )
            FinalPathFromHandle = (unsigned __int16)LastError | 0x80070000;
          v19 = (DSLogger *)tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get(
                              v16,
                              v15,
                              v17,
                              v18);
          DSLogger::LogError(
            v19,
            L"DSUtils::CopyFileWithProgress",
            0x284u,
            L"DSUtils::CopyFileWithProgress: Failed to copy file for token %s from source file %s to destination file %s. hr=0x%x",
            this,
            lpExistingFileName[0],
            lpNewFileName[0],
            FinalPathFromHandle);
        }
      }
    }
  }
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(lpNewFileName);
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(lpExistingFileName);
  return (unsigned int)FinalPathFromHandle;
}

```

## disassembly

```asm
0x180019e70  push    rbp
0x180019e72  push    rbx
0x180019e73  push    rsi
0x180019e74  push    rdi
0x180019e75  push    r14
0x180019e77  lea     rbp, [rsp-37h]
0x180019e7c  sub     rsp, 90h
0x180019e83  mov     rsi, r9
0x180019e86  mov     rdi, r8
0x180019e89  mov     r10, rdx
0x180019e8c  mov     r14, rcx
0x180019e8f  mov     [rbp+57h+var_6C], 0
0x180019e96  lea     rax, [rbp+57h+var_38]
0x180019e9a  mov     [rbp+57h+lpExistingFileName], rax
0x180019e9e  lea     rax, [rbp+57h+var_38]
0x180019ea2  mov     [rbp+57h+var_40], rax
0x180019ea6  xor     eax, eax
0x180019ea8  mov     [rbp+57h+var_38], ax
0x180019eac  lea     rax, [rbp+57h+var_58]
0x180019eb0  mov     [rbp+57h+lpNewFileName], rax
0x180019eb4  lea     rax, [rbp+57h+var_58]
0x180019eb8  mov     [rbp+57h+var_60], rax
0x180019ebc  xor     eax, eax
0x180019ebe  mov     [rbp+57h+var_58], ax
0x180019ec2  lea     rdx, [rbp+57h+lpExistingFileName]
0x180019ec6  mov     rcx, r10; hFile
0x180019ec9  call    ?GetFinalPathFromHandle@DSUtils@@YAJPEAXPEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@Z; DSUtils::GetFinalPathFromHandle(void *,utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> *)
0x180019ece  mov     ebx, eax
0x180019ed0  test    eax, eax
0x180019ed2  js      loc_180019FBE
0x180019ed8  lea     rdx, [rbp+57h+lpNewFileName]
0x180019edc  mov     rcx, rdi; hFile
0x180019edf  call    ?GetFinalPathFromHandle@DSUtils@@YAJPEAXPEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@Z; DSUtils::GetFinalPathFromHandle(void *,utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> *)
0x180019ee4  mov     ebx, eax
0x180019ee6  test    eax, eax
0x180019ee8  js      loc_180019FBE
0x180019eee  mov     [rbp+57h+var_70], 0
0x180019ef2  lea     rdx, [rbp+57h+var_70]; void *
0x180019ef6  mov     rcx, rdi; hFile
0x180019ef9  call    ?IsHardLinkFile@DSUtils@@YAJPEAXPEA_N@Z; DSUtils::IsHardLinkFile(void *,bool *)
0x180019efe  mov     ebx, eax
0x180019f00  test    eax, eax
0x180019f02  js      loc_180019FBE
0x180019f08  cmp     [rbp+57h+var_70], 0
0x180019f0c  jz      short loc_180019F3F
0x180019f0e  call    ?get@?$_LazyImpl@VDSLogger@@V?$lazy_construct@VDSLogger@@@tlx@@V?$static_lazy@VDSLogger@@$0A@V?$lazy_construct@VDSLogger@@@tlx@@@3@@tlx@@QEAAAEAVDSLogger@@XZ; tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get(void)
0x180019f13  mov     rcx, [rbp+57h+lpNewFileName]
0x180019f17  mov     [rsp+0B0h+pbCancel], rcx
0x180019f1c  lea     r9, aDsutilsCopyfil; "DSUtils::CopyFileWithProgress: Found ta"...
0x180019f23  mov     r8d, 273h; unsigned int
0x180019f29  lea     rdx, aDsutilsCopyfil_0; "DSUtils::CopyFileWithProgress"
0x180019f30  mov     rcx, rax; this
0x180019f33  call    ?LogError@DSLogger@@QEAAXPEBGK0ZZ; DSLogger::LogError(ushort const *,ulong,ushort const *,...)
0x180019f38  mov     ebx, 0C1130008h
0x180019f3d  jmp     short loc_180019FBE
0x180019f3f  mov     [rsp+0B0h+dwCopyFlags], 0; dwCopyFlags
0x180019f47  lea     rax, [rbp+57h+var_6C]
0x180019f4b  mov     [rsp+0B0h+pbCancel], rax; pbCancel
0x180019f50  mov     r9, rsi; lpData
0x180019f53  lea     r8, ?CopyFileProgressRoutine@@YAKT_LARGE_INTEGER@@000KKPEAX11@Z; lpProgressRoutine
0x180019f5a  mov     rdx, [rbp+57h+lpNewFileName]; lpNewFileName
0x180019f5e  mov     rcx, [rbp+57h+lpExistingFileName]; lpExistingFileName
0x180019f62  call    cs:__imp_CopyFileExW
0x180019f68  test    eax, eax
0x180019f6a  jnz     short loc_180019FBE
0x180019f6c  call    cs:__imp_GetLastError
0x180019f72  mov     ebx, eax
0x180019f74  test    eax, eax
0x180019f76  jle     short loc_180019F81
0x180019f78  movzx   ebx, ax
0x180019f7b  or      ebx, 80070000h
0x180019f81  call    ?get@?$_LazyImpl@VDSLogger@@V?$lazy_construct@VDSLogger@@@tlx@@V?$static_lazy@VDSLogger@@$0A@V?$lazy_construct@VDSLogger@@@tlx@@@3@@tlx@@QEAAAEAVDSLogger@@XZ; tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get(void)
0x180019f86  mov     [rsp+0B0h+var_78], ebx
0x180019f8a  mov     rcx, [rbp+57h+lpNewFileName]
0x180019f8e  mov     [rsp+0B0h+var_80], rcx
0x180019f93  mov     rcx, [rbp+57h+lpExistingFileName]
0x180019f97  mov     qword ptr [rsp+0B0h+dwCopyFlags], rcx
0x180019f9c  mov     [rsp+0B0h+pbCancel], r14
0x180019fa1  lea     r9, aDsutilsCopyfil_1; "DSUtils::CopyFileWithProgress: Failed t"...
0x180019fa8  mov     r8d, 284h; unsigned int
0x180019fae  lea     rdx, aDsutilsCopyfil_0; "DSUtils::CopyFileWithProgress"
0x180019fb5  mov     rcx, rax; this
0x180019fb8  call    ?LogError@DSLogger@@QEAAXPEBGK0ZZ; DSLogger::LogError(ushort const *,ulong,ushort const *,...)
0x180019fbd  nop
0x180019fbe  lea     rcx, [rbp+57h+lpNewFileName]
0x180019fc2  call    ?_Uninit@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@AEAAXXZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::_Uninit(void)
0x180019fc7  nop
0x180019fc8  lea     rcx, [rbp+57h+lpExistingFileName]
0x180019fcc  call    ?_Uninit@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@AEAAXXZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::_Uninit(void)
0x180019fd1  mov     eax, ebx
0x180019fd3  add     rsp, 90h
0x180019fda  pop     r14
0x180019fdc  pop     rdi
0x180019fdd  pop     rsi
0x180019fde  pop     rbx
0x180019fdf  pop     rbp
0x180019fe0  retn
```
