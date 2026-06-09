# CopyFileProgressRoutine(_LARGE_INTEGER,_LARGE_INTEGER,_LARGE_INTEGER,_LARGE_INTEGER,ulong,ulong,void *,void *,void *)

- ea: `0x180019bf0`
- end: `0x180019e67`
- name: `?CopyFileProgressRoutine@@YAKT_LARGE_INTEGER@@000KKPEAX11@Z`
- size: `631`
- prototype: `__int64 __fastcall(LARGE_INTEGER TotalFileSize, LARGE_INTEGER TotalBytesTransferred, LARGE_INTEGER StreamSize, LARGE_INTEGER StreamBytesTransferred, DWORD dwStreamNumber, DWORD dwCallbackReason, HANDLE hSourceFile, HANDLE hDestinationFile, _QWORD *lpData)`
- caller_count: `0`
- callee_count: `8`
- tags: `file_ops, reparse_path, installer_update, broker_com_uri`

## callees

- `0x1800041a0`
- `0x180006cb0`
- `0x180006f78`
- `0x18000bf80`
- `0x18000f2b0`
- `0x180019bf0`
- `0x18001a1e8`
- `0x18001a330`

## string_xrefs

- `0x180019ccd`: `CopyFileProgressRoutine failed. Source file redirection found, verified source file Id %s, redirected file Id %s`
- `0x180019cdf`: `CopyFileProgressRoutine`
- `0x180019e3c`: `CopyFileProgressRoutine`
- `0x180019d57`: `CopyFileProgressRoutine failed. Destination file redirection found, verified destination file Id %s, redirected file Id %s`
- `0x180019da0`: `CopyFileProgressRoutine failed. Source file redirection found, verified source file path %s, redirected file path %s`
- `0x180019de9`: `CopyFileProgressRoutine failed. Destination file redirection found, verified destination file path %s, redirected file path %s`
- `0x180019e2f`: `DSUtils::CopyFileProgressCallback failed. Hr=0x%x`

## pseudocode

```c
__int64 __fastcall CopyFileProgressRoutine(
        LARGE_INTEGER TotalFileSize,
        LARGE_INTEGER TotalBytesTransferred,
        LARGE_INTEGER StreamSize,
        LARGE_INTEGER StreamBytesTransferred,
        DWORD dwStreamNumber,
        DWORD dwCallbackReason,
        HANDLE hSourceFile,
        HANDLE hDestinationFile,
        _QWORD *lpData)
{
  __int64 v9; // r8
  int FileIdFromHandle; // ebx
  __int64 v11; // r8
  __int64 v12; // rdx
  __int64 v13; // rcx
  __int64 v14; // r8
  __int64 v15; // r9
  DSLogger *v16; // rax
  __int64 v18; // rdx
  __int64 v19; // rcx
  __int64 v20; // r8
  __int64 v21; // r9
  DSLogger *v22; // rax
  __int64 v23; // rdx
  __int64 v24; // rcx
  __int64 v25; // r8
  __int64 v26; // r9
  DSLogger *v27; // rax
  __int64 v28; // rdx
  __int64 v29; // rcx
  __int64 v30; // r8
  __int64 v31; // r9
  DSLogger *v32; // rax
  __int64 v33; // rdx
  __int64 v34; // rcx
  __int64 v35; // r8
  __int64 v36; // r9
  DSLogger *v37; // rax
  int v38; // [rsp+20h] [rbp-61h]
  _QWORD v39[4]; // [rsp+30h] [rbp-51h] BYREF
  _QWORD v40[4]; // [rsp+50h] [rbp-31h] BYREF
  _QWORD v41[4]; // [rsp+70h] [rbp-11h] BYREF
  _QWORD v42[4]; // [rsp+90h] [rbp+Fh] BYREF

  if ( lpData )
  {
    utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>(v39);
    FileIdFromHandle = DSUtils::GetFileIdFromHandle(hSourceFile, (__int64)v39, v9);
    if ( FileIdFromHandle >= 0 )
    {
      utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>(v40);
      FileIdFromHandle = DSUtils::GetFileIdFromHandle(hDestinationFile, (__int64)v40, v11);
      if ( FileIdFromHandle >= 0 )
      {
        utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>(v41);
        FileIdFromHandle = DSUtils::GetFinalPathFromHandle(hSourceFile, (__int64)v41);
        if ( FileIdFromHandle >= 0 )
        {
          utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>(v42);
          FileIdFromHandle = DSUtils::GetFinalPathFromHandle(hDestinationFile, (__int64)v42);
          if ( FileIdFromHandle >= 0 )
          {
            if ( (unsigned int)utl::_StringTraits<utl::char_traits<unsigned short>>::compare(
                                 *lpData,
                                 (__int64)(lpData[1] - *lpData) >> 1,
                                 v39[0],
                                 (__int64)(v39[1] - v39[0]) >> 1) )
            {
              v16 = (DSLogger *)tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get(
                                  v13,
                                  v12,
                                  v14,
                                  v15);
              DSLogger::LogError(
                v16,
                L"CopyFileProgressRoutine",
                0x234u,
                L"CopyFileProgressRoutine failed. Source file redirection found, verified source file Id %s, redirected file Id %s",
                *lpData,
                v39[0]);
LABEL_8:
              utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(v42);
              utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(v41);
              utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(v40);
              utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(v39);
              return 1;
            }
            if ( (unsigned int)utl::_StringTraits<utl::char_traits<unsigned short>>::compare(
                                 lpData[8],
                                 (__int64)(lpData[9] - lpData[8]) >> 1,
                                 v40[0],
                                 (__int64)(v40[1] - v40[0]) >> 1) )
            {
              v22 = (DSLogger *)tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get(
                                  v19,
                                  v18,
                                  v20,
                                  v21);
              DSLogger::LogError(
                v22,
                L"CopyFileProgressRoutine",
                0x23Cu,
                L"CopyFileProgressRoutine failed. Destination file redirection found, verified destination file Id %s, red"
                 "irected file Id %s",
                lpData[8],
                v40[0]);
              goto LABEL_8;
            }
            if ( (unsigned int)utl::_StringTraits<utl::char_traits<unsigned short>>::compare(
                                 lpData[4],
                                 (__int64)(lpData[5] - lpData[4]) >> 1,
                                 v41[0],
                                 (__int64)(v41[1] - v41[0]) >> 1) )
            {
              v27 = (DSLogger *)tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get(
                                  v24,
                                  v23,
                                  v25,
                                  v26);
              DSLogger::LogError(
                v27,
                L"CopyFileProgressRoutine",
                0x244u,
                L"CopyFileProgressRoutine failed. Source file redirection found, verified source file path %s, redirected file path %s",
                lpData[4],
                v41[0]);
              goto LABEL_8;
            }
            if ( (unsigned int)utl::_StringTraits<utl::char_traits<unsigned short>>::compare(
                                 lpData[12],
                                 (__int64)(lpData[13] - lpData[12]) >> 1,
                                 v42[0],
                                 (__int64)(v42[1] - v42[0]) >> 1) )
            {
              v32 = (DSLogger *)tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get(
                                  v29,
                                  v28,
                                  v30,
                                  v31);
              DSLogger::LogError(
                v32,
                L"CopyFileProgressRoutine",
                0x24Cu,
                L"CopyFileProgressRoutine failed. Destination file redirection found, verified destination file path %s, r"
                 "edirected file path %s",
                lpData[12],
                v42[0]);
              goto LABEL_8;
            }
          }
          utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(v42);
        }
        utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(v41);
      }
      utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(v40);
    }
    utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(v39);
    if ( FileIdFromHandle < 0 )
    {
      v37 = (DSLogger *)tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get(
                          v34,
                          v33,
                          v35,
                          v36);
      v38 = FileIdFromHandle;
      DSLogger::LogError(
        v37,
        L"CopyFileProgressRoutine",
        0x255u,
        L"DSUtils::CopyFileProgressCallback failed. Hr=0x%x",
        v38);
      return 1;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180019bf0  mov     [rsp-8+arg_0], rbx
0x180019bf5  mov     [rsp-8+arg_8], rdi
0x180019bfa  push    rbp
0x180019bfb  lea     rbp, [rsp-2Fh]
0x180019c00  sub     rsp, 0B0h
0x180019c07  mov     rdi, [rbp+2Fh+lpData]
0x180019c0b  test    rdi, rdi
0x180019c0e  jz      loc_180019E50
0x180019c14  lea     rcx, [rbp+2Fh+var_80]
0x180019c18  call    ??0?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA@XZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>(void)
0x180019c1d  nop
0x180019c1e  lea     rdx, [rbp+2Fh+var_80]
0x180019c22  mov     rcx, [rbp+2Fh+hSourceFile]; hFile
0x180019c26  call    ?GetFileIdFromHandle@DSUtils@@YAJPEAXPEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@Z; DSUtils::GetFileIdFromHandle(void *,utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> *)
0x180019c2b  mov     ebx, eax
0x180019c2d  test    eax, eax
0x180019c2f  js      loc_180019E19
0x180019c35  lea     rcx, [rbp+2Fh+var_60]
0x180019c39  call    ??0?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA@XZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>(void)
0x180019c3e  nop
0x180019c3f  lea     rdx, [rbp+2Fh+var_60]
0x180019c43  mov     rcx, [rbp+2Fh+hDestinationFile]; hFile
0x180019c47  call    ?GetFileIdFromHandle@DSUtils@@YAJPEAXPEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@Z; DSUtils::GetFileIdFromHandle(void *,utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> *)
0x180019c4c  mov     ebx, eax
0x180019c4e  test    eax, eax
0x180019c50  js      loc_180019E0F
0x180019c56  lea     rcx, [rbp+2Fh+var_40]
0x180019c5a  call    ??0?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA@XZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>(void)
0x180019c5f  nop
0x180019c60  lea     rdx, [rbp+2Fh+var_40]
0x180019c64  mov     rcx, [rbp+2Fh+hSourceFile]; hFile
0x180019c68  call    ?GetFinalPathFromHandle@DSUtils@@YAJPEAXPEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@Z; DSUtils::GetFinalPathFromHandle(void *,utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> *)
0x180019c6d  mov     ebx, eax
0x180019c6f  test    eax, eax
0x180019c71  js      loc_180019E05
0x180019c77  lea     rcx, [rbp+2Fh+var_20]
0x180019c7b  call    ??0?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA@XZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>(void)
0x180019c80  nop
0x180019c81  lea     rdx, [rbp+2Fh+var_20]
0x180019c85  mov     rcx, [rbp+2Fh+hDestinationFile]; hFile
0x180019c89  call    ?GetFinalPathFromHandle@DSUtils@@YAJPEAXPEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@Z; DSUtils::GetFinalPathFromHandle(void *,utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> *)
0x180019c8e  mov     ebx, eax
0x180019c90  test    eax, eax
0x180019c92  js      loc_180019DFB
0x180019c98  mov     r9, [rbp+2Fh+var_78]
0x180019c9c  mov     r8, [rbp+2Fh+var_80]
0x180019ca0  sub     r9, r8
0x180019ca3  sar     r9, 1
0x180019ca6  mov     rdx, [rdi+8]
0x180019caa  sub     rdx, [rdi]
0x180019cad  sar     rdx, 1
0x180019cb0  mov     rcx, [rdi]
0x180019cb3  call    ?compare@?$_StringTraits@U?$char_traits@G@utl@@@utl@@SAHPEBG_K01@Z; utl::_StringTraits<utl::char_traits<ushort>>::compare(ushort const *,unsigned __int64,ushort const *,unsigned __int64)
0x180019cb8  test    eax, eax
0x180019cba  jz      short loc_180019D20
0x180019cbc  call    ?get@?$_LazyImpl@VDSLogger@@V?$lazy_construct@VDSLogger@@@tlx@@V?$static_lazy@VDSLogger@@$0A@V?$lazy_construct@VDSLogger@@@tlx@@@3@@tlx@@QEAAAEAVDSLogger@@XZ; tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get(void)
0x180019cc1  mov     rcx, [rbp+2Fh+var_80]
0x180019cc5  mov     [rsp+0B0h+var_88], rcx
0x180019cca  mov     rcx, [rdi]
0x180019ccd  lea     r9, aCopyfileprogre_1; "CopyFileProgressRoutine failed. Source "...
0x180019cd4  mov     r8d, 234h; unsigned int
0x180019cda  mov     [rsp+0B0h+var_90], rcx
0x180019cdf  lea     rdx, aCopyfileprogre; "CopyFileProgressRoutine"
0x180019ce6  mov     rcx, rax; this
0x180019ce9  call    ?LogError@DSLogger@@QEAAXPEBGK0ZZ; DSLogger::LogError(ushort const *,ulong,ushort const *,...)
0x180019cee  nop
0x180019cef  lea     rcx, [rbp+2Fh+var_20]
0x180019cf3  call    ?_Uninit@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@AEAAXXZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::_Uninit(void)
0x180019cf8  nop
0x180019cf9  lea     rcx, [rbp+2Fh+var_40]
0x180019cfd  call    ?_Uninit@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@AEAAXXZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::_Uninit(void)
0x180019d02  nop
0x180019d03  lea     rcx, [rbp+2Fh+var_60]
0x180019d07  call    ?_Uninit@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@AEAAXXZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::_Uninit(void)
0x180019d0c  nop
0x180019d0d  lea     rcx, [rbp+2Fh+var_80]
0x180019d11  call    ?_Uninit@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@AEAAXXZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::_Uninit(void)
0x180019d16  mov     eax, 1
0x180019d1b  jmp     loc_180019E52
0x180019d20  mov     rcx, [rdi+40h]
0x180019d24  mov     r9, [rbp+2Fh+var_58]
0x180019d28  mov     r8, [rbp+2Fh+var_60]
0x180019d2c  sub     r9, r8
0x180019d2f  sar     r9, 1
0x180019d32  mov     rdx, [rdi+48h]
0x180019d36  sub     rdx, rcx
0x180019d39  sar     rdx, 1
0x180019d3c  call    ?compare@?$_StringTraits@U?$char_traits@G@utl@@@utl@@SAHPEBG_K01@Z; utl::_StringTraits<utl::char_traits<ushort>>::compare(ushort const *,unsigned __int64,ushort const *,unsigned __int64)
0x180019d41  test    eax, eax
0x180019d43  jz      short loc_180019D69
0x180019d45  call    ?get@?$_LazyImpl@VDSLogger@@V?$lazy_construct@VDSLogger@@@tlx@@V?$static_lazy@VDSLogger@@$0A@V?$lazy_construct@VDSLogger@@@tlx@@@3@@tlx@@QEAAAEAVDSLogger@@XZ; tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get(void)
0x180019d4a  mov     rcx, [rbp+2Fh+var_60]
0x180019d4e  mov     [rsp+0B0h+var_88], rcx
0x180019d53  mov     rcx, [rdi+40h]
0x180019d57  lea     r9, aCopyfileprogre_0; "CopyFileProgressRoutine failed. Destina"...
0x180019d5e  mov     r8d, 23Ch
0x180019d64  jmp     loc_180019CDA
0x180019d69  mov     rcx, [rdi+20h]
0x180019d6d  mov     r9, [rbp+2Fh+var_38]
0x180019d71  mov     r8, [rbp+2Fh+var_40]
0x180019d75  sub     r9, r8
0x180019d78  sar     r9, 1
0x180019d7b  mov     rdx, [rdi+28h]
0x180019d7f  sub     rdx, rcx
0x180019d82  sar     rdx, 1
0x180019d85  call    ?compare@?$_StringTraits@U?$char_traits@G@utl@@@utl@@SAHPEBG_K01@Z; utl::_StringTraits<utl::char_traits<ushort>>::compare(ushort const *,unsigned __int64,ushort const *,unsigned __int64)
0x180019d8a  test    eax, eax
0x180019d8c  jz      short loc_180019DB2
0x180019d8e  call    ?get@?$_LazyImpl@VDSLogger@@V?$lazy_construct@VDSLogger@@@tlx@@V?$static_lazy@VDSLogger@@$0A@V?$lazy_construct@VDSLogger@@@tlx@@@3@@tlx@@QEAAAEAVDSLogger@@XZ; tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get(void)
0x180019d93  mov     rcx, [rbp+2Fh+var_40]
0x180019d97  mov     [rsp+0B0h+var_88], rcx
0x180019d9c  mov     rcx, [rdi+20h]
0x180019da0  lea     r9, aCopyfileprogre_2; "CopyFileProgressRoutine failed. Source "...
0x180019da7  mov     r8d, 244h
0x180019dad  jmp     loc_180019CDA
0x180019db2  mov     rcx, [rdi+60h]
0x180019db6  mov     r9, [rbp+2Fh+var_18]
0x180019dba  mov     r8, [rbp+2Fh+var_20]
0x180019dbe  sub     r9, r8
0x180019dc1  sar     r9, 1
0x180019dc4  mov     rdx, [rdi+68h]
0x180019dc8  sub     rdx, rcx
0x180019dcb  sar     rdx, 1
0x180019dce  call    ?compare@?$_StringTraits@U?$char_traits@G@utl@@@utl@@SAHPEBG_K01@Z; utl::_StringTraits<utl::char_traits<ushort>>::compare(ushort const *,unsigned __int64,ushort const *,unsigned __int64)
0x180019dd3  test    eax, eax
0x180019dd5  jz      short loc_180019DFB
0x180019dd7  call    ?get@?$_LazyImpl@VDSLogger@@V?$lazy_construct@VDSLogger@@@tlx@@V?$static_lazy@VDSLogger@@$0A@V?$lazy_construct@VDSLogger@@@tlx@@@3@@tlx@@QEAAAEAVDSLogger@@XZ; tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get(void)
0x180019ddc  mov     rcx, [rbp+2Fh+var_20]
0x180019de0  mov     [rsp+0B0h+var_88], rcx
0x180019de5  mov     rcx, [rdi+60h]
0x180019de9  lea     r9, aCopyfileprogre_3; "CopyFileProgressRoutine failed. Destina"...
0x180019df0  mov     r8d, 24Ch
0x180019df6  jmp     loc_180019CDA
0x180019dfb  lea     rcx, [rbp+2Fh+var_20]
0x180019dff  call    ?_Uninit@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@AEAAXXZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::_Uninit(void)
0x180019e04  nop
0x180019e05  lea     rcx, [rbp+2Fh+var_40]
0x180019e09  call    ?_Uninit@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@AEAAXXZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::_Uninit(void)
0x180019e0e  nop
0x180019e0f  lea     rcx, [rbp+2Fh+var_60]
0x180019e13  call    ?_Uninit@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@AEAAXXZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::_Uninit(void)
0x180019e18  nop
0x180019e19  lea     rcx, [rbp+2Fh+var_80]
0x180019e1d  call    ?_Uninit@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@AEAAXXZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::_Uninit(void)
0x180019e22  test    ebx, ebx
0x180019e24  jns     short loc_180019E50
0x180019e26  call    ?get@?$_LazyImpl@VDSLogger@@V?$lazy_construct@VDSLogger@@@tlx@@V?$static_lazy@VDSLogger@@$0A@V?$lazy_construct@VDSLogger@@@tlx@@@3@@tlx@@QEAAAEAVDSLogger@@XZ; tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get(void)
0x180019e2b  mov     dword ptr [rsp+0B0h+var_90], ebx
0x180019e2f  lea     r9, aDsutilsCopyfil_2; "DSUtils::CopyFileProgressCallback faile"...
0x180019e36  mov     r8d, 255h; unsigned int
0x180019e3c  lea     rdx, aCopyfileprogre; "CopyFileProgressRoutine"
0x180019e43  mov     rcx, rax; this
0x180019e46  call    ?LogError@DSLogger@@QEAAXPEBGK0ZZ; DSLogger::LogError(ushort const *,ulong,ushort const *,...)
0x180019e4b  jmp     loc_180019D16
0x180019e50  xor     eax, eax
0x180019e52  lea     r11, [rsp+0B0h+var_s0]
0x180019e5a  mov     rbx, [r11+10h]
0x180019e5e  mov     rdi, [r11+18h]
0x180019e62  mov     rsp, r11
0x180019e65  pop     rbp
0x180019e66  retn
```
