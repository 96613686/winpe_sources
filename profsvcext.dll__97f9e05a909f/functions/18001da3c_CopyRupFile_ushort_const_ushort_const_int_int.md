# CopyRupFile(ushort const *,ushort const *,int,int)

- ea: `0x18001da3c`
- end: `0x18001dd1a`
- name: `?CopyRupFile@@YAJPEBG0HH@Z`
- size: `734`
- prototype: `__int64 __fastcall(const char *, unsigned __int16 *, int, int)`
- caller_count: `2`
- callee_count: `11`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x180008818`
- `0x180018a3c`

## callees

- `0x180008b1c`
- `0x180008ea0`
- `0x180013dc0`
- `0x1800172a4`
- `0x18001da3c`
- `0x18001de54`
- `0x18001de9c`
- `0x18001df18`
- `0x18001e0e4`
- `0x18001e2dc`
- `0x18001e364`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001dcde`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001dcde`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001da7f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001dcd0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001da7f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001dcd0`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001da91`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001da91`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001dc0d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001dc9b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001dc0d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001dc9b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001db7b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001db7b`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18001dc63`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18001dc63`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x18001dc56`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x18001dc56`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18001db60`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18001db60`
- `api-ms-win-core-file-l1-1-0!FlushFileBuffers` at `0x18001db72`
- `api-ms-win-core-file-l1-1-0!FlushFileBuffers` at `0x18001db72`
- `api-ms-win-core-kernel32-private-l1-1-1!PrivCopyFileExW` at `0x18001db20`
- `api-ms-win-core-kernel32-private-l1-1-1!PrivCopyFileExW` at `0x18001db20`

## string_xrefs

- `0x18001dab6`: `onecore\ds\security\gina\profile\proflib\dir.cpp`
- `0x18001dbc6`: `onecore\ds\security\gina\profile\proflib\dir.cpp`
- `0x18001dc42`: `onecore\ds\security\gina\profile\proflib\dir.cpp`
- `0x18001dc81`: `onecore\ds\security\gina\profile\proflib\dir.cpp`
- `0x18001dcb7`: `onecore\ds\security\gina\profile\proflib\dir.cpp`
- `0x18001dceb`: `onecore\ds\security\gina\profile\proflib\dir.cpp`
- `0x18001dac4`: `_GetTempFileName failed for <%ws>.`
- `0x18001dbba`: `Failed to rename %ws to %ws`
- `0x18001dc24`: `Failed to copy %ws to %ws`
- `0x18001dc6e`: `Failed to delete %ws`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CopyRupFile(const char *a1, unsigned __int16 *a2, int a3, int a4)
{
  unsigned __int16 *v7; // rdi
  HANDLE ProcessHeap; // rax
  char *v9; // rax
  unsigned __int64 v10; // r9
  WCHAR *v11; // rbx
  const char *TempFileName; // rdi
  HANDLE FileW; // rax
  void *v14; // rdi
  __int64 v15; // rdx
  __int64 v16; // rcx
  unsigned int v17; // eax
  __int64 v18; // rdx
  __int64 v19; // rcx
  signed int LastError; // eax
  BOOL v21; // eax
  DWORD v22; // eax
  HANDLE v23; // rax
  int dwCreationDisposition; // [rsp+20h] [rbp-48h]
  unsigned __int64 v26[5]; // [rsp+40h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]
  int v28; // [rsp+88h] [rbp+20h] BYREF

  v28 = a4;
  v26[0] = 0;
  StringCchLengthW(a2, 0x7FFFFFFFu, v26);
  v7 = (unsigned __int16 *)(v26[0] + 45);
  ProcessHeap = GetProcessHeap();
  v9 = (char *)HeapAlloc(ProcessHeap, 8u, 2LL * (_QWORD)v7);
  v11 = (WCHAR *)v9;
  if ( v9 )
  {
    TempFileName = (const char *)(unsigned int)proflib::_GetTempFileName((proflib *)a2, v9, v7, v10);
    if ( wil::details::in1diag3::Log_IfFailedMsg(
           retaddr,
           (void *)0x12B,
           (unsigned int)"onecore\\ds\\security\\gina\\profile\\proflib\\dir.cpp",
           TempFileName,
           (int)"_GetTempFileName failed for <%ws>.",
           (const char *)a2) >= 0 )
    {
      v28 = 0;
      if ( (unsigned int)PrivCopyFileExW(a1, v11, CopyProgressRoutine, 0, &v28, a3 != 0 ? 512 : 1552) )
      {
        LODWORD(v26[0]) = 0;
        FileW = CreateFileW(v11, 0x40000000u, 0, 0, 3u, 0x80u, 0);
        v14 = FileW;
        if ( FileW != (HANDLE)-1LL )
        {
          FlushFileBuffers(FileW);
          CloseHandle(v14);
        }
        if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::GetImpl'::`2'::impl)
          && (Microsoft_Windows_User_Profiles_GeneralEnableBits & 8) != 0 )
        {
          McTemplateU0zz_EventWriteTransfer(v16, v15, a1, v11);
        }
        v17 = RenameFile((char *)v11, (char *)a2);
        LODWORD(TempFileName) = wil::details::in1diag3::Log_IfFailedMsg(
                                  retaddr,
                                  (void *)0x150,
                                  (unsigned int)"onecore\\ds\\security\\gina\\profile\\proflib\\dir.cpp",
                                  (const char *)v17,
                                  (int)"Failed to rename %ws to %ws",
                                  (const char *)v11,
                                  a2);
        if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::GetImpl'::`2'::impl)
          && (int)TempFileName >= 0
          && (Microsoft_Windows_User_Profiles_GeneralEnableBits & 8) != 0 )
        {
          McTemplateU0z_EventWriteTransfer(v19, v18, a2);
        }
      }
      else
      {
        LastError = GetLastError();
        if ( LastError > 0 )
          LastError = (unsigned __int16)LastError | 0x80070000;
        LODWORD(TempFileName) = wil::details::in1diag3::Log_IfFailedMsg(
                                  retaddr,
                                  (void *)0x15C,
                                  (unsigned int)"onecore\\ds\\security\\gina\\profile\\proflib\\dir.cpp",
                                  (const char *)(unsigned int)LastError,
                                  (int)"Failed to copy %ws to %ws",
                                  a1,
                                  v11);
      }
      if ( SetFileAttributesW(v11, 0x80u) )
      {
        v21 = DeleteFileW(v11);
        wil::details::in1diag3::Log_GetLastErrorIfMsg(
          retaddr,
          (void *)0x162,
          (unsigned int)"onecore\\ds\\security\\gina\\profile\\proflib\\dir.cpp",
          (const char *)!v21,
          (bool)"Failed to delete %ws",
          (const char *)v11);
      }
      else
      {
        v22 = GetLastError();
        if ( v22 != 2 )
          wil::details::in1diag3::Log_Win32Msg(
            retaddr,
            (void *)0x169,
            (unsigned int)"onecore\\ds\\security\\gina\\profile\\proflib\\dir.cpp",
            (const char *)v22,
            (unsigned int)"Failed to set attributes for %ws",
            (const char *)v11);
      }
    }
    v23 = GetProcessHeap();
    HeapFree(v23, 0, v11);
  }
  else
  {
    LODWORD(TempFileName) = wil::details::in1diag3::Log_Hr(
                              retaddr,
                              (void *)0x172,
                              (unsigned int)"onecore\\ds\\security\\gina\\profile\\proflib\\dir.cpp",
                              (const char *)0x8007000ELL,
                              dwCreationDisposition);
  }
  return (unsigned int)TempFileName;
}

```

## disassembly

```asm
0x18001da3c  mov     rax, rsp
0x18001da3f  mov     [rax+8], rbx
0x18001da43  mov     [rax+10h], rbp
0x18001da47  mov     [rax+20h], r9d
0x18001da4b  push    rdi
0x18001da4c  push    r14
0x18001da4e  push    r15
0x18001da50  sub     rsp, 50h
0x18001da54  mov     rbp, rdx
0x18001da57  mov     qword ptr [rax-28h], 0
0x18001da5f  mov     r14, rcx
0x18001da62  mov     r15d, r8d
0x18001da65  mov     rcx, rbp; unsigned __int16 *
0x18001da68  lea     r8, [rax-28h]; unsigned __int64 *
0x18001da6c  mov     edx, 7FFFFFFFh; unsigned __int64
0x18001da71  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x18001da76  mov     rdi, [rsp+68h+var_28]
0x18001da7b  add     rdi, 2Dh ; '-'
0x18001da7f  call    cs:__imp_GetProcessHeap
0x18001da85  lea     r8, [rdi+rdi]; dwBytes
0x18001da89  mov     edx, 8; dwFlags
0x18001da8e  mov     rcx, rax; hHeap
0x18001da91  call    cs:__imp_HeapAlloc
0x18001da97  mov     rbx, rax
0x18001da9a  test    rax, rax
0x18001da9d  jz      loc_18001DCE6
0x18001daa3  mov     r8, rdi; unsigned __int16 *
0x18001daa6  mov     rdx, rax; char *
0x18001daa9  mov     rcx, rbp; this
0x18001daac  call    ?_GetTempFileName@proflib@@YAJPEBGPEAG_K@Z; proflib::_GetTempFileName(ushort const *,ushort *,unsigned __int64)
0x18001dab1  mov     rcx, [rsp+68h]; this
0x18001dab6  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\gina\\profile\\p"...
0x18001dabd  mov     edi, eax
0x18001dabf  mov     qword ptr [rsp+68h+dwFlagsAndAttributes], rbp; char *
0x18001dac4  lea     rax, aGettempfilenam; "_GetTempFileName failed for <%ws>."
0x18001dacb  mov     r9d, edi; char *
0x18001dace  mov     edx, 12Bh; void *
0x18001dad3  mov     qword ptr [rsp+68h+dwCreationDisposition], rax; int
0x18001dad8  call    ?Log_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x18001dadd  test    eax, eax
0x18001dadf  js      loc_18001DCD0
0x18001dae5  neg     r15d
0x18001dae8  mov     [rsp+68h+arg_18], 0
0x18001daf3  lea     r8, _CopyProgressRoutine
0x18001dafa  mov     rdx, rbx
0x18001dafd  sbb     eax, eax
0x18001daff  mov     rcx, r14
0x18001db02  and     eax, 0FFFFFBF0h
0x18001db07  xor     r9d, r9d
0x18001db0a  add     eax, 610h
0x18001db0f  mov     [rsp+68h+dwFlagsAndAttributes], eax
0x18001db13  lea     rax, [rsp+68h+arg_18]
0x18001db1b  mov     qword ptr [rsp+68h+dwCreationDisposition], rax
0x18001db20  call    cs:__imp_PrivCopyFileExW
0x18001db26  mov     r15d, 80h
0x18001db2c  test    eax, eax
0x18001db2e  jz      loc_18001DC0D
0x18001db34  mov     [rsp+68h+hTemplateFile], 0; hTemplateFile
0x18001db3d  xor     r9d, r9d; lpSecurityAttributes
0x18001db40  mov     [rsp+68h+dwFlagsAndAttributes], r15d; dwFlagsAndAttributes
0x18001db45  xor     r8d, r8d; dwShareMode
0x18001db48  mov     edx, 40000000h; dwDesiredAccess
0x18001db4d  mov     [rsp+68h+dwCreationDisposition], 3; dwCreationDisposition
0x18001db55  mov     rcx, rbx; lpFileName
0x18001db58  mov     dword ptr [rsp+68h+var_28], 0
0x18001db60  call    cs:__imp_CreateFileW
0x18001db66  mov     rdi, rax
0x18001db69  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18001db6d  jz      short loc_18001DB81
0x18001db6f  mov     rcx, rax; hFile
0x18001db72  call    cs:__imp_FlushFileBuffers
0x18001db78  mov     rcx, rdi; hObject
0x18001db7b  call    cs:__imp_CloseHandle
0x18001db81  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Profile_Service_ETW_Logging@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Profile_Service_ETW_Logging@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging> `wil::Feature<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::GetImpl(void)'::`2'::impl
0x18001db88  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Profile_Service_ETW_Logging@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::__private_IsEnabled(void)
0x18001db8d  test    al, al
0x18001db8f  jz      short loc_18001DBA5
0x18001db91  test    cs:Microsoft_Windows_User_Profiles_GeneralEnableBits, 8
0x18001db98  jz      short loc_18001DBA5
0x18001db9a  mov     r9, rbx
0x18001db9d  mov     r8, r14
0x18001dba0  call    McTemplateU0zz_EventWriteTransfer
0x18001dba5  lea     r8, [rsp+68h+var_28]
0x18001dbaa  mov     rdx, rbp; char *
0x18001dbad  mov     rcx, rbx; char *
0x18001dbb0  call    _RenameFile
0x18001dbb5  mov     rcx, [rsp+68h]; this
0x18001dbba  lea     rdx, aFailedToRename; "Failed to rename %ws to %ws"
0x18001dbc1  mov     [rsp+68h+hTemplateFile], rbp
0x18001dbc6  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\gina\\profile\\p"...
0x18001dbcd  mov     qword ptr [rsp+68h+dwFlagsAndAttributes], rbx; char *
0x18001dbd2  mov     r9d, eax; char *
0x18001dbd5  mov     qword ptr [rsp+68h+dwCreationDisposition], rdx; int
0x18001dbda  mov     edx, 150h; void *
0x18001dbdf  call    ?Log_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x18001dbe4  mov     edi, eax
0x18001dbe6  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Profile_Service_ETW_Logging@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Profile_Service_ETW_Logging@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging> `wil::Feature<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::GetImpl(void)'::`2'::impl
0x18001dbed  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Profile_Service_ETW_Logging@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::__private_IsEnabled(void)
0x18001dbf2  test    al, al
0x18001dbf4  jz      short loc_18001DC50
0x18001dbf6  test    edi, edi
0x18001dbf8  js      short loc_18001DC50
0x18001dbfa  test    cs:Microsoft_Windows_User_Profiles_GeneralEnableBits, 8
0x18001dc01  jz      short loc_18001DC50
0x18001dc03  mov     r8, rbp
0x18001dc06  call    McTemplateU0z_EventWriteTransfer
0x18001dc0b  jmp     short loc_18001DC50
0x18001dc0d  call    cs:__imp_GetLastError
0x18001dc13  test    eax, eax
0x18001dc15  jle     short loc_18001DC1F
0x18001dc17  movzx   eax, ax
0x18001dc1a  or      eax, 80070000h
0x18001dc1f  mov     rcx, [rsp+68h]; this
0x18001dc24  lea     r8, aFailedToCopyWs_0; "Failed to copy %ws to %ws"
0x18001dc2b  mov     [rsp+68h+hTemplateFile], rbx
0x18001dc30  mov     r9d, eax; char *
0x18001dc33  mov     qword ptr [rsp+68h+dwFlagsAndAttributes], r14; char *
0x18001dc38  mov     edx, 15Ch; void *
0x18001dc3d  mov     qword ptr [rsp+68h+dwCreationDisposition], r8; int
0x18001dc42  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\gina\\profile\\p"...
0x18001dc49  call    ?Log_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x18001dc4e  mov     edi, eax
0x18001dc50  mov     edx, r15d; dwFileAttributes
0x18001dc53  mov     rcx, rbx; lpFileName
0x18001dc56  call    cs:__imp_SetFileAttributesW
0x18001dc5c  test    eax, eax
0x18001dc5e  jz      short loc_18001DC9B
0x18001dc60  mov     rcx, rbx; lpFileName
0x18001dc63  call    cs:__imp_DeleteFileW
0x18001dc69  mov     rcx, [rsp+68h]; this
0x18001dc6e  lea     rdx, aFailedToDelete; "Failed to delete %ws"
0x18001dc75  test    eax, eax
0x18001dc77  mov     qword ptr [rsp+68h+dwFlagsAndAttributes], rbx; char *
0x18001dc7c  mov     qword ptr [rsp+68h+dwCreationDisposition], rdx; bool
0x18001dc81  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\gina\\profile\\p"...
0x18001dc88  setz    al
0x18001dc8b  mov     edx, 162h; void *
0x18001dc90  movzx   r9d, al; char *
0x18001dc94  call    ?Log_GetLastErrorIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBD_N1ZZ; wil::details::in1diag3::Log_GetLastErrorIfMsg(void *,uint,char const *,bool,char const *,...)
0x18001dc99  jmp     short loc_18001DCD0
0x18001dc9b  call    cs:__imp_GetLastError
0x18001dca1  cmp     eax, 2
0x18001dca4  jz      short loc_18001DCD0
0x18001dca6  mov     rcx, [rsp+68h]; this
0x18001dcab  lea     rdx, aFailedToSetAtt; "Failed to set attributes for %ws"
0x18001dcb2  mov     qword ptr [rsp+68h+dwFlagsAndAttributes], rbx; char *
0x18001dcb7  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\gina\\profile\\p"...
0x18001dcbe  mov     qword ptr [rsp+68h+dwCreationDisposition], rdx; unsigned int
0x18001dcc3  mov     r9d, eax; char *
0x18001dcc6  mov     edx, 169h; void *
0x18001dccb  call    ?Log_Win32Msg@in1diag3@details@wil@@YAKPEAXIPEBDK1ZZ; wil::details::in1diag3::Log_Win32Msg(void *,uint,char const *,ulong,char const *,...)
0x18001dcd0  call    cs:__imp_GetProcessHeap
0x18001dcd6  mov     r8, rbx; lpMem
0x18001dcd9  xor     edx, edx; dwFlags
0x18001dcdb  mov     rcx, rax; hHeap
0x18001dcde  call    cs:__imp_HeapFree
0x18001dce4  jmp     short loc_18001DD04
0x18001dce6  mov     rcx, [rsp+68h]; this
0x18001dceb  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\gina\\profile\\p"...
0x18001dcf2  mov     r9d, 8007000Eh; char *
0x18001dcf8  mov     edx, 172h; void *
0x18001dcfd  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x18001dd02  mov     edi, eax
0x18001dd04  mov     rbx, [rsp+68h+arg_0]
0x18001dd09  mov     eax, edi
0x18001dd0b  mov     rbp, [rsp+68h+arg_8]
0x18001dd10  add     rsp, 50h
0x18001dd14  pop     r15
0x18001dd16  pop     r14
0x18001dd18  pop     rdi
0x18001dd19  retn
```
