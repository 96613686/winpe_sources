# CFileCollection::CreateCollectionFileByName(wchar_t const *,_FILECOLLECTION_ACL_TYPE,wchar_t const *,wchar_t const *,int,wchar_t *,tlx::unique_any<tlx::file_handle_traits> *)

- ea: `0x18000a154`
- end: `0x18000a7bb`
- name: `?CreateCollectionFileByName@CFileCollection@@QEAAJPEB_WW4_FILECOLLECTION_ACL_TYPE@@00HPEA_WPEAV?$unique_any@Ufile_handle_traits@tlx@@@tlx@@@Z`
- size: `1639`
- prototype: `__int64 __fastcall(__int64, const wchar_t *, __int64, __int16 *, __int64, BOOL, WCHAR *lpFileName, void **)`
- caller_count: `3`
- callee_count: `9`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x180007db8`
- `0x1800086e0`
- `0x180008be4`

## callees

- `0x180002890`
- `0x180003474`
- `0x180006684`
- `0x180009ed8`
- `0x180009f00`
- `0x18000a154`
- `0x18000a9a4`
- `0x18000b90c`
- `0x18003e5a8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x18000a532`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x18000a532`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a413`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a664`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a6ce`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a413`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a664`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a6ce`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a206`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a652`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a206`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a652`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000a63b`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000a63b`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x18000a68e`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x18000a68e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000a267`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000a3f2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000a78d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000a267`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000a3f2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000a78d`
- `wer!WerpGetStorePath` at `0x18000a28d`
- `wer!WerpGetStorePath` at `0x18000a28d`
- `wer!WerpValidateReportKey` at `0x18000a218`
- `wer!WerpValidateReportKey` at `0x18000a218`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18000a409`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18000a409`

## pseudocode

```c
__int64 __fastcall CFileCollection::CreateCollectionFileByName(
        __int64 a1,
        const wchar_t *a2,
        __int64 a3,
        __int16 *a4,
        __int64 a5,
        BOOL a6,
        WCHAR *lpFileName,
        void **a8)
{
  __int16 *v8; // r14
  int v9; // r15d
  unsigned int v11; // edx
  void *v12; // rcx
  signed int StorePath; // ebx
  _QWORD *v14; // rcx
  __int64 v15; // rdx
  unsigned __int64 v17; // rdx
  unsigned __int64 v18; // rdx
  unsigned __int64 v19; // rdx
  HLOCAL v20; // rcx
  signed int LastError; // eax
  _QWORD *v22; // rcx
  __int64 v23; // rdx
  __int64 v24; // rax
  __int64 v25; // rdx
  _WORD *v26; // r8
  __int16 v27; // cx
  _WORD *v28; // rcx
  __int16 *v29; // rbx
  int v30; // esi
  wchar_t *v31; // rdx
  __int64 v32; // rax
  __int64 v33; // r14
  __int16 v34; // ax
  __int16 v35; // ax
  __int16 v36; // cx
  __int64 i; // rax
  int v38; // esi
  __int64 v39; // r14
  int v40; // eax
  HANDLE v41; // rax
  void *v42; // rcx
  signed int v43; // eax
  DWORD dwFlagsAndAttributes[2]; // [rsp+28h] [rbp-D8h]
  HLOCAL hMem; // [rsp+40h] [rbp-C0h] BYREF
  int v46; // [rsp+48h] [rbp-B8h] BYREF
  _SECURITY_ATTRIBUTES SecurityAttributes; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v48; // [rsp+68h] [rbp-98h]
  _WORD v49[264]; // [rsp+70h] [rbp-90h] BYREF
  wchar_t FileName[264]; // [rsp+280h] [rbp+180h] BYREF

  v8 = a4;
  v9 = a3;
  v48 = a5;
  v46 = 0;
  memset(&SecurityAttributes, 0, sizeof(SecurityAttributes));
  hMem = 0;
  if ( a4 && a5 && lpFileName && a8 )
  {
    memset_0(lpFileName, 0, 0x208u);
    v12 = *a8;
    *a8 = 0;
    if ( (unsigned __int64)v12 + 1 > 1 )
      CloseHandle(v12);
    if ( a2 )
    {
      StorePath = WerpValidateReportKey(a2);
      if ( StorePath < 0 )
      {
        v14 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          goto LABEL_13;
        v15 = 20;
        goto LABEL_12;
      }
      v46 = 260;
      StorePath = WerpGetStorePath(3, FileName, &v46);
      if ( StorePath < 0 )
      {
        v14 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          goto LABEL_13;
        v15 = 21;
        goto LABEL_12;
      }
      StorePath = StringCchCatW(FileName, v17, L"\\");
      if ( StorePath < 0 )
      {
        v14 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          goto LABEL_13;
        v15 = 22;
        goto LABEL_12;
      }
      StorePath = StringCchCatW(FileName, v18, a2);
      if ( StorePath < 0 )
      {
        v14 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          goto LABEL_13;
        v15 = 23;
        goto LABEL_12;
      }
      StorePath = StringCchCatW(FileName, v19, L"\\");
      if ( StorePath < 0 )
      {
        v14 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          goto LABEL_13;
        v15 = 24;
        goto LABEL_12;
      }
    }
    else
    {
      StorePath = UtilGetTempDirPath(FileName, v11);
      if ( StorePath < 0 )
      {
        v14 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          goto LABEL_13;
        v15 = 25;
LABEL_12:
        WPP_SF_d(v14[2], v15, WPP_5830178aa191323d89eeb6488c1e9d69_Traceguids, (unsigned int)StorePath);
        goto LABEL_13;
      }
    }
    SecurityAttributes.nLength = 24;
    SecurityAttributes.bInheritHandle = 0;
    SecurityAttributes.lpSecurityDescriptor = 0;
    if ( v9 == 1 )
    {
      v20 = hMem;
      hMem = 0;
      if ( v20 )
        LocalFree(v20);
      if ( ConvertStringSecurityDescriptorToSecurityDescriptorW(
             L"D:P(A;;GA;;;BA)(A;;GA;;;SY)S:(ML;;NR;;;HI)",
             1u,
             &hMem,
             0) )
      {
        SecurityAttributes.lpSecurityDescriptor = hMem;
      }
      else
      {
        LastError = GetLastError();
        StorePath = LastError;
        if ( LastError > 0 )
          StorePath = (unsigned __int16)LastError | 0x80070000;
        if ( StorePath < 0 )
        {
          v22 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
            goto LABEL_13;
          v23 = 26;
          goto LABEL_47;
        }
      }
    }
    SecurityAttributes.bInheritHandle = a6;
    v24 = 2147483646;
    v25 = 260;
    v26 = v49;
    do
    {
      if ( !v24 )
        break;
      v27 = *v8;
      if ( !*v8 )
        break;
      ++v8;
      *v26++ = v27;
      --v24;
      --v25;
    }
    while ( v25 );
    StorePath = v25 == 0 ? 0x8007007A : 0;
    v28 = v26 - 1;
    if ( v25 )
      v28 = v26;
    *v28 = 0;
    if ( v25 )
    {
      v29 = v49;
      v30 = 0;
      while ( 1 )
      {
        v31 = `UtilSanitizeFileNameComponent'::`2'::arpwszIllegal[v30];
        v32 = -1;
        do
          ++v32;
        while ( v31[v32] );
        v33 = (unsigned int)v32;
        if ( !(unsigned int)_o__wcsnicmp(v49, v31, (unsigned int)v32) )
        {
          v34 = v49[v33];
          if ( !v34 || v34 == 46 )
            break;
        }
        if ( (unsigned int)++v30 >= 0x17 )
        {
          v35 = v49[0];
          goto LABEL_67;
        }
      }
      v35 = 88;
      v49[0] = 88;
LABEL_67:
      if ( v35 )
      {
        do
        {
          v36 = *v29;
          for ( i = 0; i != 12; ++i )
          {
            if ( v36 == `UtilSanitizeFileNameComponent'::`2'::arwchIllegal[i] )
            {
              *v29 = 95;
              v36 = 95;
            }
          }
          if ( (unsigned __int16)(*v29 - 1) <= 0x1Eu )
            *v29 = 95;
          ++v29;
        }
        while ( *v29 );
      }
      v38 = 0;
      v39 = v48;
      do
      {
        if ( v38 )
        {
          dwFlagsAndAttributes[0] = v38;
          v40 = StringCchPrintfW(lpFileName, 0x104u, L"%s%s%d.%s", FileName, v49, *(_QWORD *)dwFlagsAndAttributes, v39);
        }
        else
        {
          v40 = StringCchPrintfW(lpFileName, 0x104u, L"%s%s.%s", FileName, v49, v39);
        }
        StorePath = v40;
        if ( v40 < 0 )
        {
          v22 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            v23 = 28;
            goto LABEL_47;
          }
          goto LABEL_13;
        }
        v41 = CreateFileW(lpFileName, 0xC0010000, 1u, &SecurityAttributes, 1u, 0x80u, 0);
        v42 = *a8;
        *a8 = v41;
        if ( (unsigned __int64)v42 + 1 > 1 )
          CloseHandle(v42);
        if ( (unsigned __int64)*a8 + 1 > 1 )
          break;
        if ( GetLastError() != 80 )
          break;
        ++v38;
      }
      while ( v38 < 10 );
      if ( (unsigned __int64)*a8 + 1 > 1 )
      {
        if ( !SetFileAttributesW(lpFileName, 0x2080u)
          && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 30, WPP_5830178aa191323d89eeb6488c1e9d69_Traceguids);
        }
        StorePath = 0;
        goto LABEL_14;
      }
      v43 = GetLastError();
      StorePath = v43;
      if ( v43 > 0 )
        StorePath = (unsigned __int16)v43 | 0x80070000;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          29,
          WPP_5830178aa191323d89eeb6488c1e9d69_Traceguids,
          (unsigned int)StorePath);
      if ( StorePath >= 0 )
        goto LABEL_14;
      goto LABEL_13;
    }
    v22 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
    {
LABEL_13:
      *lpFileName = 0;
LABEL_14:
      if ( hMem )
        LocalFree(hMem);
      return (unsigned int)StorePath;
    }
    v23 = 27;
LABEL_47:
    WPP_SF_d(v22[2], v23, WPP_5830178aa191323d89eeb6488c1e9d69_Traceguids, (unsigned int)StorePath);
    goto LABEL_13;
  }
  MicrosoftTelemetryAssertTriggeredNoArgs(0, a2, a3, a4);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, WPP_5830178aa191323d89eeb6488c1e9d69_Traceguids);
  return 2147942487LL;
}

```

## disassembly

```asm
0x18000a154  push    rbp
0x18000a156  push    rbx
0x18000a157  push    rsi
0x18000a158  push    rdi
0x18000a159  push    r12
0x18000a15b  push    r13
0x18000a15d  push    r14
0x18000a15f  push    r15
0x18000a161  lea     rbp, [rsp-3A8h]
0x18000a169  sub     rsp, 4A8h
0x18000a170  mov     rax, cs:__security_cookie
0x18000a177  xor     rax, rsp
0x18000a17a  mov     [rbp+3E0h+var_50], rax
0x18000a181  mov     r14, r9
0x18000a184  mov     r15d, r8d
0x18000a187  mov     rsi, rdx
0x18000a18a  mov     r12, [rbp+3E0h+arg_38]
0x18000a191  mov     rax, [rbp+3E0h+arg_20]
0x18000a198  mov     [rsp+4E0h+var_478], rax
0x18000a19d  mov     r13, [rbp+3E0h+lpFileName]
0x18000a1a4  xor     ebx, ebx
0x18000a1a6  mov     [rsp+4E0h+var_498], ebx
0x18000a1aa  xorps   xmm0, xmm0
0x18000a1ad  xor     ecx, ecx
0x18000a1af  movups  xmmword ptr [rsp+4E0h+SecurityAttributes.nLength], xmm0
0x18000a1b4  mov     qword ptr [rsp+4E0h+SecurityAttributes.bInheritHandle], rcx
0x18000a1b9  mov     [rsp+4E0h+hMem], rbx
0x18000a1be  test    r9, r9
0x18000a1c1  jz      loc_18000A74C
0x18000a1c7  test    rax, rax
0x18000a1ca  jz      loc_18000A74C
0x18000a1d0  test    r13, r13
0x18000a1d3  jz      loc_18000A74C
0x18000a1d9  test    r12, r12
0x18000a1dc  jz      loc_18000A74C
0x18000a1e2  xor     edx, edx; Val
0x18000a1e4  mov     r8d, 208h; Size
0x18000a1ea  mov     rcx, r13; void *
0x18000a1ed  call    memset_0
0x18000a1f2  mov     rcx, [r12]; hObject
0x18000a1f6  mov     [r12], rbx
0x18000a1fa  lea     rax, [rcx+1]
0x18000a1fe  lea     edi, [rbx+1]
0x18000a201  cmp     rax, rdi
0x18000a204  jbe     short loc_18000A20C
0x18000a206  call    cs:__imp_CloseHandle
0x18000a20c  test    rsi, rsi
0x18000a20f  jz      loc_18000A381
0x18000a215  mov     rcx, rsi
0x18000a218  call    cs:__imp_WerpValidateReportKey
0x18000a21e  mov     ebx, eax
0x18000a220  test    eax, eax
0x18000a222  jns     short loc_18000A274
0x18000a224  lea     rax, WPP_GLOBAL_Control
0x18000a22b  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a232  cmp     rcx, rax
0x18000a235  jz      short loc_18000A255
0x18000a237  test    [rcx+1Ch], dil
0x18000a23b  jz      short loc_18000A255
0x18000a23d  mov     edx, 14h
0x18000a242  mov     r9d, ebx
0x18000a245  lea     r8, WPP_5830178aa191323d89eeb6488c1e9d69_Traceguids
0x18000a24c  mov     rcx, [rcx+10h]
0x18000a250  call    WPP_SF_d
0x18000a255  xor     r15d, r15d
0x18000a258  mov     [r13+0], r15w
0x18000a25d  mov     rcx, [rsp+4E0h+hMem]; hMem
0x18000a262  test    rcx, rcx
0x18000a265  jz      short loc_18000A26D
0x18000a267  call    cs:__imp_LocalFree
0x18000a26d  mov     eax, ebx
0x18000a26f  jmp     loc_18000A798
0x18000a274  mov     [rsp+4E0h+var_498], 104h
0x18000a27c  lea     r8, [rsp+4E0h+var_498]
0x18000a281  lea     rdx, [rbp+3E0h+FileName]
0x18000a288  mov     ecx, 3
0x18000a28d  call    cs:__imp_WerpGetStorePath
0x18000a293  mov     ebx, eax
0x18000a295  test    eax, eax
0x18000a297  jns     short loc_18000A2B9
0x18000a299  lea     rax, WPP_GLOBAL_Control
0x18000a2a0  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a2a7  cmp     rcx, rax
0x18000a2aa  jz      short loc_18000A255
0x18000a2ac  test    [rcx+1Ch], dil
0x18000a2b0  jz      short loc_18000A255
0x18000a2b2  mov     edx, 15h
0x18000a2b7  jmp     short loc_18000A242
0x18000a2b9  lea     r8, SubBlock; "\\"
0x18000a2c0  lea     rcx, [rbp+3E0h+FileName]; wchar_t *
0x18000a2c7  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x18000a2cc  mov     ebx, eax
0x18000a2ce  test    eax, eax
0x18000a2d0  jns     short loc_18000A2FD
0x18000a2d2  lea     rax, WPP_GLOBAL_Control
0x18000a2d9  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a2e0  cmp     rcx, rax
0x18000a2e3  jz      loc_18000A255
0x18000a2e9  test    [rcx+1Ch], dil
0x18000a2ed  jz      loc_18000A255
0x18000a2f3  mov     edx, 16h
0x18000a2f8  jmp     loc_18000A242
0x18000a2fd  mov     r8, rsi; wchar_t *
0x18000a300  lea     rcx, [rbp+3E0h+FileName]; wchar_t *
0x18000a307  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x18000a30c  mov     ebx, eax
0x18000a30e  test    eax, eax
0x18000a310  jns     short loc_18000A33D
0x18000a312  lea     rax, WPP_GLOBAL_Control
0x18000a319  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a320  cmp     rcx, rax
0x18000a323  jz      loc_18000A255
0x18000a329  test    [rcx+1Ch], dil
0x18000a32d  jz      loc_18000A255
0x18000a333  mov     edx, 17h
0x18000a338  jmp     loc_18000A242
0x18000a33d  lea     r8, SubBlock; "\\"
0x18000a344  lea     rcx, [rbp+3E0h+FileName]; wchar_t *
0x18000a34b  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x18000a350  mov     ebx, eax
0x18000a352  test    eax, eax
0x18000a354  jns     short loc_18000A3BE
0x18000a356  lea     rax, WPP_GLOBAL_Control
0x18000a35d  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a364  cmp     rcx, rax
0x18000a367  jz      loc_18000A255
0x18000a36d  test    [rcx+1Ch], dil
0x18000a371  jz      loc_18000A255
0x18000a377  mov     edx, 18h
0x18000a37c  jmp     loc_18000A242
0x18000a381  lea     rcx, [rbp+3E0h+FileName]; lpFileName
0x18000a388  call    ?UtilGetTempDirPath@@YAJPEA_WK@Z; UtilGetTempDirPath(wchar_t *,ulong)
0x18000a38d  mov     ebx, eax
0x18000a38f  test    eax, eax
0x18000a391  jns     short loc_18000A3BE
0x18000a393  lea     rax, WPP_GLOBAL_Control
0x18000a39a  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a3a1  cmp     rcx, rax
0x18000a3a4  jz      loc_18000A255
0x18000a3aa  test    [rcx+1Ch], dil
0x18000a3ae  jz      loc_18000A255
0x18000a3b4  mov     edx, 19h
0x18000a3b9  jmp     loc_18000A242
0x18000a3be  mov     [rsp+4E0h+SecurityAttributes.nLength], 18h
0x18000a3c6  mov     [rsp+4E0h+SecurityAttributes.bInheritHandle], 0
0x18000a3ce  mov     [rsp+4E0h+SecurityAttributes.lpSecurityDescriptor], 0
0x18000a3d7  cmp     r15d, edi
0x18000a3da  jnz     loc_18000A476
0x18000a3e0  mov     rcx, [rsp+4E0h+hMem]; hMem
0x18000a3e5  xor     r15d, r15d
0x18000a3e8  mov     [rsp+4E0h+hMem], r15
0x18000a3ed  test    rcx, rcx
0x18000a3f0  jz      short loc_18000A3F8
0x18000a3f2  call    cs:__imp_LocalFree
0x18000a3f8  xor     r9d, r9d; SecurityDescriptorSize
0x18000a3fb  lea     r8, [rsp+4E0h+hMem]; SecurityDescriptor
0x18000a400  mov     edx, edi; StringSDRevision
0x18000a402  lea     rcx, StringSecurityDescriptor; "D:P(A;;GA;;;BA)(A;;GA;;;SY)S:(ML;;NR;;;"...
0x18000a409  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x18000a40f  test    eax, eax
0x18000a411  jnz     short loc_18000A46A
0x18000a413  call    cs:__imp_GetLastError
0x18000a419  mov     ebx, eax
0x18000a41b  test    eax, eax
0x18000a41d  jle     short loc_18000A428
0x18000a41f  movzx   ebx, ax
0x18000a422  or      ebx, 80070000h
0x18000a428  test    ebx, ebx
0x18000a42a  jns     short loc_18000A479
0x18000a42c  lea     rax, WPP_GLOBAL_Control
0x18000a433  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a43a  cmp     rcx, rax
0x18000a43d  jz      loc_18000A258
0x18000a443  test    [rcx+1Ch], dil
0x18000a447  jz      loc_18000A258
0x18000a44d  mov     edx, 1Ah
0x18000a452  mov     r9d, ebx
0x18000a455  lea     r8, WPP_5830178aa191323d89eeb6488c1e9d69_Traceguids
0x18000a45c  mov     rcx, [rcx+10h]
0x18000a460  call    WPP_SF_d
0x18000a465  jmp     loc_18000A258
0x18000a46a  mov     rax, [rsp+4E0h+hMem]
0x18000a46f  mov     [rsp+4E0h+SecurityAttributes.lpSecurityDescriptor], rax
0x18000a474  jmp     short loc_18000A479
0x18000a476  xor     r15d, r15d
0x18000a479  mov     eax, [rbp+3E0h+arg_28]
0x18000a47f  mov     [rsp+4E0h+SecurityAttributes.bInheritHandle], eax
0x18000a483  mov     eax, 7FFFFFFEh
0x18000a488  mov     edx, 104h
0x18000a48d  lea     r8, [rsp+4E0h+var_470]
0x18000a492  test    rax, rax
0x18000a495  jz      short loc_18000A4B4
0x18000a497  movzx   ecx, word ptr [r14]
0x18000a49b  test    cx, cx
0x18000a49e  jz      short loc_18000A4B4
0x18000a4a0  add     r14, 2
0x18000a4a4  mov     [r8], cx
0x18000a4a8  add     r8, 2
0x18000a4ac  sub     rax, rdi
0x18000a4af  sub     rdx, rdi
0x18000a4b2  jnz     short loc_18000A492
0x18000a4b4  mov     rax, rdx
0x18000a4b7  neg     rax
0x18000a4ba  sbb     ebx, ebx
0x18000a4bc  not     ebx
0x18000a4be  and     ebx, 8007007Ah
0x18000a4c4  lea     rcx, [r8-2]
0x18000a4c8  test    rdx, rdx
0x18000a4cb  cmovnz  rcx, r8
0x18000a4cf  mov     [rcx], r15w
0x18000a4d3  jnz     short loc_18000A500
0x18000a4d5  lea     rax, WPP_GLOBAL_Control
0x18000a4dc  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a4e3  cmp     rcx, rax
0x18000a4e6  jz      loc_18000A258
0x18000a4ec  test    [rcx+1Ch], dil
0x18000a4f0  jz      loc_18000A258
0x18000a4f6  mov     edx, 1Bh
0x18000a4fb  jmp     loc_18000A452
0x18000a500  lea     rbx, [rsp+4E0h+var_470]
0x18000a505  mov     esi, r15d
0x18000a508  lea     rcx, __ImageBase
0x18000a50f  mov     eax, esi
0x18000a511  mov     rdx, ds:rva ?arpwszIllegal@?1??UtilSanitizeFileNameComponent@@YAXPEA_W@Z@4QBQEB_WB[rcx+rax*8]; wchar_t const * const near * const `UtilSanitizeFileNameComponent(wchar_t *)'::`2'::arpwszIllegal ...
0x18000a519  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000a51d  inc     rax
0x18000a520  cmp     [rdx+rax*2], r15w
0x18000a525  jnz     short loc_18000A51D
0x18000a527  mov     r14d, eax
0x18000a52a  mov     r8d, eax
0x18000a52d  lea     rcx, [rsp+4E0h+var_470]
0x18000a532  call    cs:__imp__o__wcsnicmp
0x18000a538  test    eax, eax
0x18000a53a  jnz     short loc_18000A555
0x18000a53c  movzx   eax, [rsp+r14*2+4E0h+var_470]
0x18000a542  test    ax, ax
0x18000a545  jz      loc_18000A5E7
0x18000a54b  cmp     ax, 2Eh ; '.'
0x18000a54f  jz      loc_18000A5E7
0x18000a555  add     esi, edi
0x18000a557  cmp     esi, 17h
0x18000a55a  jb      short loc_18000A508
0x18000a55c  movzx   eax, [rsp+4E0h+var_470]
0x18000a561  mov     r8d, 1Eh
0x18000a567  test    ax, ax
0x18000a56a  jz      short loc_18000A5AF
0x18000a56c  lea     edx, [r8+41h]
0x18000a570  lea     r9, __ImageBase
0x18000a577  movzx   ecx, word ptr [rbx]
0x18000a57a  mov     rax, r15
0x18000a57d  cmp     cx, ds:rva ?arwchIllegal@?1??UtilSanitizeFileNameComponent@@YAXPEA_W@Z@4QB_WB[r9+rax*2]; wchar_t const near * const `UtilSanitizeFileNameComponent(wchar_t *)'::`2'::arwchIllegal ...
0x18000a586  jnz     short loc_18000A58D
0x18000a588  mov     [rbx], dx
0x18000a58b  mov     ecx, edx
0x18000a58d  add     rax, rdi
0x18000a590  cmp     rax, 0Ch
0x18000a594  jnz     short loc_18000A57D
0x18000a596  movzx   eax, word ptr [rbx]
0x18000a599  sub     ax, di
0x18000a59c  cmp     ax, r8w
0x18000a5a0  ja      short loc_18000A5A5
0x18000a5a2  mov     [rbx], dx
0x18000a5a5  add     rbx, 2
0x18000a5a9  cmp     [rbx], r15w
0x18000a5ad  jnz     short loc_18000A577
0x18000a5af  mov     esi, r15d
0x18000a5b2  mov     r14, [rsp+4E0h+var_478]
0x18000a5b7  lea     rax, [rsp+4E0h+var_470]
0x18000a5bc  lea     r9, [rbp+3E0h+FileName]
0x18000a5c3  mov     edx, 104h; unsigned __int64
0x18000a5c8  mov     rcx, r13; wchar_t *
0x18000a5cb  test    esi, esi
0x18000a5cd  jnz     short loc_18000A5F6
0x18000a5cf  mov     qword ptr [rsp+4E0h+dwFlagsAndAttributes], r14
0x18000a5d4  mov     qword ptr [rsp+4E0h+dwCreationDisposition], rax
0x18000a5d9  lea     r8, aSSS; "%s%s.%s"
0x18000a5e0  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x18000a5e5  jmp     short loc_18000A610
0x18000a5e7  mov     eax, 58h ; 'X'
0x18000a5ec  mov     [rsp+4E0h+var_470], ax
0x18000a5f1  jmp     loc_18000A561
0x18000a5f6  mov     [rsp+4E0h+hTemplateFile], r14
0x18000a5fb  mov     [rsp+4E0h+dwFlagsAndAttributes], esi
0x18000a5ff  mov     qword ptr [rsp+4E0h+dwCreationDisposition], rax
0x18000a604  lea     r8, aSSDS; "%s%s%d.%s"
0x18000a60b  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x18000a610  mov     ebx, eax
0x18000a612  test    eax, eax
0x18000a614  js      loc_18000A721
0x18000a61a  mov     [rsp+4E0h+hTemplateFile], r15; hTemplateFile
0x18000a61f  mov     [rsp+4E0h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x18000a627  mov     [rsp+4E0h+dwCreationDisposition], edi; dwCreationDisposition
0x18000a62b  lea     r9, [rsp+4E0h+SecurityAttributes]; lpSecurityAttributes
0x18000a630  mov     r8d, edi; dwShareMode
0x18000a633  mov     edx, 0C0010000h; dwDesiredAccess
0x18000a638  mov     rcx, r13; lpFileName
0x18000a63b  call    cs:__imp_CreateFileW
0x18000a641  mov     rcx, [r12]; hObject
0x18000a645  mov     [r12], rax
0x18000a649  lea     rax, [rcx+1]
  ... truncated ...
```
