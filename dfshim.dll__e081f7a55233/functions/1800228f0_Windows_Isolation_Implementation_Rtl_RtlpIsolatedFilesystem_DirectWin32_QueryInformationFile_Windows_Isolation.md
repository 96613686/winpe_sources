# Windows::Isolation::Implementation::Rtl::RtlpIsolatedFilesystem_DirectWin32_QueryInformationFile(Windows::Isolation::FsProv::Rtl::_ISOLATED_FILESYSTEM_PROVIDER_FILESYSTEM *,Windows::Isolation::FsProv::Rtl::_PROVIDER_ISOLATED_FILE,_IO_STATUS_BLOCK *,void *,unsigned __int64,_FILE_INFORMATION_CLASS,_RTL_ALTERNATE_STATUS *)

- ea: `0x1800228f0`
- end: `0x180022c0c`
- name: `?RtlpIsolatedFilesystem_DirectWin32_QueryInformationFile@Rtl@Implementation@Isolation@Windows@@YAJPEAU_ISOLATED_FILESYSTEM_PROVIDER_FILESYSTEM@1FsProv@34@T_PROVIDER_ISOLATED_FILE@1634@PEAU_IO_STATUS_BLOCK@@PEAX_KW4_FILE_INFORMATION_CLASS@@PEAU_RTL_ALTERNATE_STATUS@@@Z`
- size: `796`
- prototype: `int __high(struct Windows::Isolation::FsProv::Rtl::_ISOLATED_FILESYSTEM_PROVIDER_FILESYSTEM *, union Windows::Isolation::FsProv::Rtl::_PROVIDER_ISOLATED_FILE, struct _IO_STATUS_BLOCK *, void *, unsigned __int64, enum _FILE_INFORMATION_CLASS, struct _RTL_ALTERNATE_STATUS *)`
- caller_count: `0`
- callee_count: `10`
- tags: `file_ops, broker_com_uri`

## callees

- `0x1800069e5`
- `0x180012950`
- `0x180012b1c`
- `0x180018b30`
- `0x1800228f0`
- `0x180023494`
- `0x1800567b4`
- `0x180127dc0`
- `0x1801281c0`
- `0x18012a030`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!GetFileInformationByHandle` at `0x180022a80`
- `api-ms-win-core-file-l1-1-0!GetFileInformationByHandle` at `0x180022a80`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x180022b30`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x180022b30`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x180022ad8`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x180022ad8`

## string_xrefs

- `0x180022921`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\win32\isofs_direct.cpp`
- `0x180022a0b`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\win32\isofs_direct.cpp`
- `0x180022a99`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\win32\isofs_direct.cpp`

## pseudocode

```c
__int64 __fastcall Windows::Isolation::Implementation::Rtl::RtlpIsolatedFilesystem_DirectWin32_QueryInformationFile(
        const unsigned int *a1,
        __int64 a2,
        __int64 a3,
        _DWORD *a4,
        size_t Size,
        int a6)
{
  int v10; // r9d
  char v11; // r12
  char v12; // dl
  unsigned __int64 v13; // rsi
  int v14; // edi
  __int64 v15; // rdx
  int v16; // r8d
  DWORD v17; // eax
  int v18; // r9d
  void *v19; // rcx
  DWORD v20; // edi
  DWORD LastError_0; // eax
  void *v22; // rcx
  DWORD FileSize; // ecx
  DWORD v24; // eax
  unsigned __int64 v25; // rax
  int InformationFile; // eax
  enum _FILE_INFORMATION_CLASS v28; // [rsp+20h] [rbp-71h]
  LONG DistanceToMoveHigh; // [rsp+2Ch] [rbp-65h] BYREF
  const char *v30; // [rsp+30h] [rbp-61h] BYREF
  int v31; // [rsp+38h] [rbp-59h]
  unsigned int v32; // [rsp+40h] [rbp-51h]
  _BY_HANDLE_FILE_INFORMATION FileInformation; // [rsp+50h] [rbp-41h] BYREF
  DWORD v34; // [rsp+88h] [rbp-9h]
  LONG v35; // [rsp+8Ch] [rbp-5h]

  v32 = -1073741595;
  v30 = "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\win32\\isofs_direct.cpp";
  if ( a4 )
    memset_thunk_772440563353939046(a4, 0, Size);
  if ( a3 )
    *(_OWORD *)a3 = 0;
  if ( a1 != &Windows::Isolation::Implementation::Rtl::RtlpDirectWin32IsolatedFilesystem )
  {
    v31 = 2131;
LABEL_34:
    Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::InternalErrorImmediateAction(
      &v30,
      &v30);
    return v32;
  }
  memset_thunk_772440563353939046(&FileInformation, 0, 0x40u);
  v11 = 0;
  LOBYTE(v28) = 0;
  v12 = 1;
  if ( a6 > 14 )
  {
    switch ( a6 )
    {
      case 16:
        v13 = 4;
        goto LABEL_29;
      case 18:
        v13 = 104;
        goto LABEL_29;
      case 20:
        v13 = 8;
        v12 = 0;
        v11 = 1;
        goto LABEL_29;
      case 34:
        v13 = 56;
        goto LABEL_29;
    }
    goto LABEL_23;
  }
  if ( a6 == 14 )
  {
    v13 = 8;
    LOBYTE(v28) = 1;
    v12 = 0;
    goto LABEL_29;
  }
  v13 = 4;
  switch ( a6 )
  {
    case 4:
      v13 = 40;
      goto LABEL_29;
    case 5:
      v13 = 24;
      goto LABEL_29;
    case 6:
      v13 = 8;
      goto LABEL_29;
  }
  if ( a6 != 8 )
  {
    if ( a6 == 9 )
    {
      v13 = *(_QWORD *)(a2 + 32) + 8LL;
      v12 = 0;
      goto LABEL_29;
    }
LABEL_23:
    v14 = -1073741637;
    v15 = 2146;
    v16 = -1073741637;
LABEL_24:
    Windows::ErrorHandling::COM::ReportNtErrorOrigination(
      (Windows::ErrorHandling::COM *)"onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\win32\\isofs_direct.cpp",
      (const char *)v15,
      v16,
      v10);
    return (unsigned int)v14;
  }
LABEL_29:
  if ( Size < v13 )
  {
    v31 = 2196;
    Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::SetInvalidParameter(&v30);
    return v32;
  }
  if ( !v12 )
    goto LABEL_37;
  if ( v11 )
  {
    v31 = 2198;
    goto LABEL_34;
  }
  if ( GetFileInformationByHandle(*(HANDLE *)(a2 + 72), &FileInformation)
    || (v17 = GetLastError_0(),
        v14 = isowin32_ConvertWin32ErrorToNtStatus(v17),
        Windows::ErrorHandling::COM::ReportNtErrorOrigination(
          (Windows::ErrorHandling::COM *)"onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\win32\\isofs_direct.cpp",
          (const char *)0x307,
          v14,
          v18),
        v14 >= 0) )
  {
LABEL_37:
    if ( (_BYTE)v28 )
    {
      v19 = *(void **)(a2 + 72);
      DistanceToMoveHigh = *(&lDistanceToMove + 1);
      v20 = SetFilePointer(v19, lDistanceToMove, &DistanceToMoveHigh, 1u);
      if ( v20 == -1 && GetLastError_0() )
      {
        LastError_0 = GetLastError_0();
        v14 = isowin32_ConvertWin32ErrorToNtStatus(LastError_0);
        v16 = v14;
        v15 = 2206;
        goto LABEL_24;
      }
      v34 = v20;
      v35 = DistanceToMoveHigh;
    }
    if ( v11 )
    {
      v22 = *(void **)(a2 + 72);
      DistanceToMoveHigh = 0;
      FileSize = GetFileSize(v22, (LPDWORD)&DistanceToMoveHigh);
      if ( FileSize == -1 )
      {
        if ( GetLastError_0() )
        {
          v24 = GetLastError_0();
          v14 = isowin32_ConvertWin32ErrorToNtStatus(v24);
          v16 = v14;
          v15 = 2212;
          goto LABEL_24;
        }
        FileSize = -1;
      }
      FileInformation.nFileSizeHigh = DistanceToMoveHigh;
      FileInformation.nFileSizeLow = FileSize;
    }
    if ( a6 == 9 )
    {
      if ( !a4 )
      {
        v31 = 2222;
        Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::SetInvalidParameter(&v30);
        return v32;
      }
      v25 = *(_QWORD *)(a2 + 32);
      if ( v25 > 0xFFFFFFFF )
        return (unsigned int)-1073741675;
      *a4 = v25;
      memmove(a4 + 1, *(const void **)(a2 + 48), *(_QWORD *)(a2 + 32));
    }
    else
    {
      InformationFile = Windows::Isolation::Implementation::Rtl::isowin32_QueryInformationFile(
                          (Windows::Isolation::Implementation::Rtl *)a2,
                          (struct Windows::Isolation::Implementation::Rtl::CDirectWin32FsObject *)&FileInformation,
                          (const struct Windows::Isolation::Implementation::Rtl::RTLP_BY_HANDLE_INFORMATION *)a4,
                          (void *)(unsigned int)a6,
                          v28);
      v14 = InformationFile;
      if ( InformationFile < 0 )
      {
        v16 = InformationFile;
        v15 = 2229;
        goto LABEL_24;
      }
    }
    if ( a3 )
      *(_QWORD *)(a3 + 8) = v13;
    return 0;
  }
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x1800228f0  mov     [rsp-8+arg_0], rbx
0x1800228f5  push    rbp
0x1800228f6  push    rsi
0x1800228f7  push    rdi
0x1800228f8  push    r12
0x1800228fa  push    r13
0x1800228fc  push    r14
0x1800228fe  push    r15
0x180022900  lea     rbp, [rsp-0Fh]
0x180022905  sub     rsp, 0A0h
0x18002290c  mov     rax, cs:__security_cookie
0x180022913  xor     rax, rsp
0x180022916  mov     [rbp+3Fh+var_40], rax
0x18002291a  mov     [rbp+3Fh+var_90], 0C00000E5h
0x180022921  lea     rax, aOnecoreComNetf_79; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x180022928  mov     [rbp+3Fh+var_A0], rax
0x18002292c  mov     r15, r9
0x18002292f  mov     r13, r8
0x180022932  mov     rbx, rdx
0x180022935  mov     rdi, rcx
0x180022938  test    r9, r9
0x18002293b  jz      short loc_18002294B
0x18002293d  mov     r8, [rbp+3Fh+Size]; Size
0x180022941  xor     edx, edx; Val
0x180022943  mov     rcx, r9; void *
0x180022946  call    memset$thunk$772440563353939046
0x18002294b  test    r13, r13
0x18002294e  jz      short loc_180022958
0x180022950  xorps   xmm0, xmm0
0x180022953  movups  xmmword ptr [r13+0], xmm0
0x180022958  lea     rax, ?RtlpDirectWin32IsolatedFilesystem@Rtl@Implementation@Isolation@Windows@@3U_ISOLATED_FILESYSTEM_PROVIDER_FILESYSTEM@1FsProv@34@B; Windows::Isolation::FsProv::Rtl::_ISOLATED_FILESYSTEM_PROVIDER_FILESYSTEM const Windows::Isolation::Implementation::Rtl::RtlpDirectWin32IsolatedFilesystem
0x18002295f  cmp     rdi, rax
0x180022962  jz      short loc_180022970
0x180022964  mov     [rbp+3Fh+var_98], 853h
0x18002296b  jmp     loc_180022A66
0x180022970  xor     edx, edx; Val
0x180022972  lea     rcx, [rbp+3Fh+FileInformation]; void *
0x180022976  lea     r8d, [rdx+40h]; Size
0x18002297a  call    memset$thunk$772440563353939046
0x18002297f  mov     r14d, dword ptr [rbp+3Fh+arg_28]
0x180022983  xor     r12b, r12b
0x180022986  mov     [rbp+3Fh+var_B0], r12b
0x18002298a  mov     dl, 1
0x18002298c  cmp     r14d, 0Eh
0x180022990  jg      short loc_1800229E6
0x180022992  jz      short loc_1800229D9
0x180022994  mov     ecx, r14d
0x180022997  mov     esi, 4
0x18002299c  sub     ecx, esi
0x18002299e  jz      short loc_1800229D2
0x1800229a0  sub     ecx, 1
0x1800229a3  jz      short loc_1800229CB
0x1800229a5  sub     ecx, 1
0x1800229a8  jz      short loc_1800229C4
0x1800229aa  sub     ecx, 2
0x1800229ad  jz      loc_180022A3B
0x1800229b3  cmp     ecx, 1
0x1800229b6  jnz     short loc_1800229FE
0x1800229b8  mov     rsi, [rbx+20h]
0x1800229bc  add     rsi, 8
0x1800229c0  xor     dl, dl
0x1800229c2  jmp     short loc_180022A3B
0x1800229c4  mov     esi, 8
0x1800229c9  jmp     short loc_180022A3B
0x1800229cb  mov     esi, 18h
0x1800229d0  jmp     short loc_180022A3B
0x1800229d2  mov     esi, 28h ; '('
0x1800229d7  jmp     short loc_180022A3B
0x1800229d9  mov     esi, 8
0x1800229de  mov     [rbp+3Fh+var_B0], 1
0x1800229e2  xor     dl, dl
0x1800229e4  jmp     short loc_180022A3B
0x1800229e6  cmp     r14d, 10h
0x1800229ea  jz      short loc_180022A36
0x1800229ec  cmp     r14d, 12h
0x1800229f0  jz      short loc_180022A2F
0x1800229f2  cmp     r14d, 14h
0x1800229f6  jz      short loc_180022A23
0x1800229f8  cmp     r14d, 22h ; '"'
0x1800229fc  jz      short loc_180022A1C
0x1800229fe  mov     edi, 0C00000BBh
0x180022a03  mov     edx, 862h; char *
0x180022a08  mov     r8d, edi; int
0x180022a0b  lea     rcx, aOnecoreComNetf_79; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x180022a12  call    ?ReportNtErrorOrigination@COM@ErrorHandling@Windows@@YAXPEBDHJ@Z; Windows::ErrorHandling::COM::ReportNtErrorOrigination(char const *,int,long)
0x180022a17  jmp     loc_180022BB7
0x180022a1c  mov     esi, 38h ; '8'
0x180022a21  jmp     short loc_180022A3B
0x180022a23  mov     esi, 8
0x180022a28  xor     dl, dl
0x180022a2a  mov     r12b, 1
0x180022a2d  jmp     short loc_180022A3B
0x180022a2f  mov     esi, 68h ; 'h'
0x180022a34  jmp     short loc_180022A3B
0x180022a36  mov     esi, 4
0x180022a3b  cmp     [rbp+3Fh+Size], rsi
0x180022a3f  jnb     short loc_180022A56
0x180022a41  mov     [rbp+3Fh+var_98], 894h
0x180022a48  lea     rcx, [rbp+3Fh+var_A0]
0x180022a4c  call    ?SetInvalidParameter@?$CBaseFrame@VCVoidRaiseFrame@Nt@ErrorHandling@Windows@@@Nt@ErrorHandling@Windows@@IEAAXXZ; Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::SetInvalidParameter(void)
0x180022a51  jmp     loc_180022B8A
0x180022a56  test    dl, dl
0x180022a58  jz      short loc_180022AB4
0x180022a5a  test    r12b, r12b
0x180022a5d  jz      short loc_180022A78
0x180022a5f  mov     [rbp+3Fh+var_98], 896h
0x180022a66  lea     rdx, [rbp+3Fh+var_A0]
0x180022a6a  lea     rcx, [rbp+3Fh+var_A0]
0x180022a6e  call    ?InternalErrorImmediateAction@?$CBaseFrame@VCVoidRaiseFrame@Nt@ErrorHandling@Windows@@@Nt@ErrorHandling@Windows@@IEAAXAEBVCCallSite@34@@Z; Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::InternalErrorImmediateAction(Windows::ErrorHandling::CCallSite const &)
0x180022a73  jmp     loc_180022B8A
0x180022a78  mov     rcx, [rbx+48h]; hFile
0x180022a7c  lea     rdx, [rbp+3Fh+FileInformation]; lpFileInformation
0x180022a80  call    cs:__imp_GetFileInformationByHandle
0x180022a86  test    eax, eax
0x180022a88  jnz     short loc_180022AB4
0x180022a8a  call    GetLastError_0
0x180022a8f  mov     ecx, eax; unsigned int
0x180022a91  call    ?isowin32_ConvertWin32ErrorToNtStatus@@YAJK@Z; isowin32_ConvertWin32ErrorToNtStatus(ulong)
0x180022a96  mov     r8d, eax; int
0x180022a99  lea     rcx, aOnecoreComNetf_79; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x180022aa0  mov     edx, 307h; char *
0x180022aa5  mov     edi, eax
0x180022aa7  call    ?ReportNtErrorOrigination@COM@ErrorHandling@Windows@@YAXPEBDHJ@Z; Windows::ErrorHandling::COM::ReportNtErrorOrigination(char const *,int,long)
0x180022aac  test    edi, edi
0x180022aae  js      loc_180022BB7
0x180022ab4  cmp     [rbp+3Fh+var_B0], 0
0x180022ab8  mov     edi, 0FFFFFFFFh
0x180022abd  jz      short loc_180022B1B
0x180022abf  mov     rdx, cs:lDistanceToMove; lDistanceToMove
0x180022ac6  lea     r8, [rbp+3Fh+DistanceToMoveHigh]; lpDistanceToMoveHigh
0x180022aca  mov     rcx, [rbx+48h]; hFile
0x180022ace  mov     r9d, 1; dwMoveMethod
0x180022ad4  mov     [rbp-69h], rdx
0x180022ad8  call    cs:__imp_SetFilePointer
0x180022ade  mov     edi, eax
0x180022ae0  mov     eax, 0FFFFFFFFh
0x180022ae5  cmp     edi, eax
0x180022ae7  jnz     short loc_180022B0D
0x180022ae9  call    GetLastError_0
0x180022aee  test    eax, eax
0x180022af0  jz      short loc_180022B0D
0x180022af2  call    GetLastError_0
0x180022af7  mov     ecx, eax; unsigned int
0x180022af9  call    ?isowin32_ConvertWin32ErrorToNtStatus@@YAJK@Z; isowin32_ConvertWin32ErrorToNtStatus(ulong)
0x180022afe  mov     edi, eax
0x180022b00  mov     r8d, eax
0x180022b03  mov     edx, 89Eh
0x180022b08  jmp     loc_180022A0B
0x180022b0d  mov     eax, [rbp+3Fh+DistanceToMoveHigh]
0x180022b10  mov     [rbp+3Fh+var_48], edi
0x180022b13  mov     edi, 0FFFFFFFFh
0x180022b18  mov     [rbp+3Fh+var_44], eax
0x180022b1b  test    r12b, r12b
0x180022b1e  jz      short loc_180022B6F
0x180022b20  mov     rcx, [rbx+48h]; hFile
0x180022b24  lea     rdx, [rbp+3Fh+DistanceToMoveHigh]; lpFileSizeHigh
0x180022b28  mov     qword ptr [rbp-69h], 0
0x180022b30  call    cs:__imp_GetFileSize
0x180022b36  mov     [rbp+3Fh+var_A8], eax
0x180022b39  mov     ecx, eax
0x180022b3b  cmp     eax, edi
0x180022b3d  jnz     short loc_180022B66
0x180022b3f  call    GetLastError_0
0x180022b44  test    eax, eax
0x180022b46  jz      short loc_180022B63
0x180022b48  call    GetLastError_0
0x180022b4d  mov     ecx, eax; unsigned int
0x180022b4f  call    ?isowin32_ConvertWin32ErrorToNtStatus@@YAJK@Z; isowin32_ConvertWin32ErrorToNtStatus(ulong)
0x180022b54  mov     edi, eax
0x180022b56  mov     r8d, eax
0x180022b59  mov     edx, 8A4h
0x180022b5e  jmp     loc_180022A0B
0x180022b63  mov     ecx, [rbp+3Fh+var_A8]
0x180022b66  mov     eax, [rbp+3Fh+DistanceToMoveHigh]
0x180022b69  mov     [rbp+3Fh+FileInformation.nFileSizeHigh], eax
0x180022b6c  mov     [rbp+3Fh+FileInformation.nFileSizeLow], ecx
0x180022b6f  cmp     r14d, 9
0x180022b73  jnz     short loc_180022BE7
0x180022b75  test    r15, r15
0x180022b78  jnz     short loc_180022B8F
0x180022b7a  lea     rcx, [rbp+3Fh+var_A0]
0x180022b7e  mov     [rbp+3Fh+var_98], 8AEh
0x180022b85  call    ?SetInvalidParameter@?$CBaseFrame@VCVoidRaiseFrame@Nt@ErrorHandling@Windows@@@Nt@ErrorHandling@Windows@@IEAAXXZ; Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::SetInvalidParameter(void)
0x180022b8a  mov     edi, [rbp+3Fh+var_90]
0x180022b8d  jmp     short loc_180022BB7
0x180022b8f  mov     rax, [rbx+20h]
0x180022b93  cmp     rax, rdi
0x180022b96  ja      short loc_180022BE0
0x180022b98  mov     [r15], eax
0x180022b9b  lea     rcx, [r15+4]; void *
0x180022b9f  mov     r8, [rbx+20h]; Size
0x180022ba3  mov     rdx, [rbx+30h]; Src
0x180022ba7  call    memmove
0x180022bac  test    r13, r13
0x180022baf  jz      short loc_180022BB5
0x180022bb1  mov     [r13+8], rsi
0x180022bb5  xor     edi, edi
0x180022bb7  mov     eax, edi
0x180022bb9  mov     rcx, [rbp+3Fh+var_40]
0x180022bbd  xor     rcx, rsp; StackCookie
0x180022bc0  call    __security_check_cookie
0x180022bc5  mov     rbx, [rsp+0D0h+arg_0]
0x180022bcd  add     rsp, 0A0h
0x180022bd4  pop     r15
0x180022bd6  pop     r14
0x180022bd8  pop     r13
0x180022bda  pop     r12
0x180022bdc  pop     rdi
0x180022bdd  pop     rsi
0x180022bde  pop     rbp
0x180022bdf  retn
0x180022be0  mov     edi, 0C0000095h
0x180022be5  jmp     short loc_180022BB7
0x180022be7  mov     r9d, r14d; void *
0x180022bea  lea     rdx, [rbp+3Fh+FileInformation]; struct Windows::Isolation::Implementation::Rtl::CDirectWin32FsObject *
0x180022bee  mov     r8, r15; struct Windows::Isolation::Implementation::Rtl::RTLP_BY_HANDLE_INFORMATION *
0x180022bf1  mov     rcx, rbx; this
0x180022bf4  call    ?isowin32_QueryInformationFile@Rtl@Implementation@Isolation@Windows@@YAJPEAVCDirectWin32FsObject@1234@PEBURTLP_BY_HANDLE_INFORMATION@1234@PEAXW4_FILE_INFORMATION_CLASS@@@Z; Windows::Isolation::Implementation::Rtl::isowin32_QueryInformationFile(Windows::Isolation::Implementation::Rtl::CDirectWin32FsObject *,Windows::Isolation::Implementation::Rtl::RTLP_BY_HANDLE_INFORMATION const *,void *,_FILE_INFORMATION_CLASS)
0x180022bf9  mov     edi, eax
0x180022bfb  test    eax, eax
0x180022bfd  jns     short loc_180022BAC
0x180022bff  mov     r8d, eax
0x180022c02  mov     edx, 8B5h
0x180022c07  jmp     loc_180022A0B
```
