# Windows::Isolation::Implementation::Rtl::RtlpIsolatedFilesystem_DirectWin32_SetInformationFile(Windows::Isolation::FsProv::Rtl::_ISOLATED_FILESYSTEM_PROVIDER_FILESYSTEM *,Windows::Isolation::FsProv::Rtl::_PROVIDER_ISOLATED_FILE,_IO_STATUS_BLOCK *,void *,unsigned __int64,_FILE_INFORMATION_CLASS,_RTL_ALTERNATE_STATUS *)

- ea: `0x180023040`
- end: `0x18002336a`
- name: `?RtlpIsolatedFilesystem_DirectWin32_SetInformationFile@Rtl@Implementation@Isolation@Windows@@YAJPEAU_ISOLATED_FILESYSTEM_PROVIDER_FILESYSTEM@1FsProv@34@T_PROVIDER_ISOLATED_FILE@1634@PEAU_IO_STATUS_BLOCK@@PEAX_KW4_FILE_INFORMATION_CLASS@@PEAU_RTL_ALTERNATE_STATUS@@@Z`
- size: `810`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `file_ops, reparse_path, broker_com_uri`

## callees

- `0x1800069e5`
- `0x180012950`
- `0x180012b1c`
- `0x180018b30`
- `0x18002156c`
- `0x180023040`
- `0x180056968`
- `0x1800b8b0c`
- `0x1800fe440`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!SetFileAttributesA` at `0x180023293`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesA` at `0x180023293`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x1800232c9`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x1800232c9`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180023283`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800232b9`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180023283`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800232b9`

## string_xrefs

- `0x180023061`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\win32\isofs_direct.cpp`

## pseudocode

```c
__int64 __fastcall Windows::Isolation::Implementation::Rtl::RtlpIsolatedFilesystem_DirectWin32_SetInformationFile(
        const unsigned int *a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        unsigned __int64 a5,
        unsigned int a6,
        struct _RTL_ALTERNATE_STATUS *a7)
{
  int HardLink_FromIsolatedObjectAttributes; // ebx
  int v9; // eax
  unsigned __int64 v10; // r8
  unsigned __int64 v11; // rcx
  __int64 v12; // rax
  void *v13; // rcx
  void *v14; // rcx
  DWORD v15; // ebx
  __int64 v16; // rcx
  BOOL v17; // eax
  __int64 v18; // rcx
  DWORD LastError_0; // eax
  int v20; // eax
  int v21; // r9d
  void *v22; // rcx
  void *v23; // rcx
  const char *v25; // [rsp+20h] [rbp-71h] BYREF
  unsigned __int64 v26; // [rsp+28h] [rbp-69h]
  __int64 v27; // [rsp+30h] [rbp-61h]
  __int64 v28; // [rsp+40h] [rbp-51h] BYREF
  __int64 v29; // [rsp+48h] [rbp-49h]
  void *v30; // [rsp+50h] [rbp-41h]
  __int64 v31; // [rsp+58h] [rbp-39h]
  void *lpMem[2]; // [rsp+60h] [rbp-31h]
  __int64 v33; // [rsp+70h] [rbp-21h]
  int v34; // [rsp+78h] [rbp-19h]
  _QWORD v35[3]; // [rsp+80h] [rbp-11h] BYREF
  int v36; // [rsp+98h] [rbp+7h]
  __int128 v37; // [rsp+A0h] [rbp+Fh]

  LODWORD(v27) = -1073741595;
  v25 = "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\win32\\isofs_direct.cpp";
  if ( a1 != &Windows::Isolation::Implementation::Rtl::RtlpDirectWin32IsolatedFilesystem )
  {
    LODWORD(v26) = 1588;
LABEL_15:
    Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::InternalErrorImmediateAction(
      &v25,
      &v25);
    return (unsigned int)v27;
  }
  if ( !a2 )
  {
    LODWORD(v26) = 1589;
    Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::SetInvalidParameter(&v25);
    return (unsigned int)v27;
  }
  if ( a6 > 0xD || (v9 = 10256, !_bittest(&v9, a6)) )
  {
    HardLink_FromIsolatedObjectAttributes = -1073740756;
    Windows::ErrorHandling::COM::ReportNtErrorOrigination(
      (Windows::ErrorHandling::COM *)"onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\win32\\isofs_direct.cpp",
      (const char *)0x63C,
      -1073740756,
      a4);
    return (unsigned int)HardLink_FromIsolatedObjectAttributes;
  }
  if ( (a5 & 0xFFFFFFFFFFFFFFE0uLL) == 0 && a5 != 1 )
  {
    LODWORD(v26) = 1601;
LABEL_30:
    Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::SetInvalidParameter(&v25);
    return (unsigned int)v27;
  }
  if ( a6 != 4 )
  {
    if ( a6 == 11 )
    {
      if ( a5 < 0x20 )
      {
        LODWORD(v26) = 1629;
        goto LABEL_30;
      }
      v10 = *(_QWORD *)(a4 + 16);
      v11 = v10 + 32;
      if ( v10 + 32 < v10 || v11 < 0x20 )
        return (unsigned int)-1073741675;
      if ( a5 != v11 )
      {
        LODWORD(v26) = 1636;
        goto LABEL_30;
      }
      v29 = a2;
      v25 = (const char *)v10;
      v26 = v10;
      v30 = &g_LUNICODE_STRING__empty_;
      LODWORD(v31) = 64;
      v27 = a4 + 24;
      v35[2] = &v25;
      v12 = *(_QWORD *)(a4 + 8);
      v36 = 64;
      v35[1] = v12;
      v28 = 48;
      *(_OWORD *)lpMem = 0;
      v35[0] = 48;
      v37 = 0;
      HardLink_FromIsolatedObjectAttributes = Windows::Isolation::Implementation::Rtl::RtlpIsolatedFilesystem_DirectWin32_CreateHardLink_FromIsolatedObjectAttributes(
                                                (Windows::Isolation::Implementation::Rtl *)&v28,
                                                (const struct Windows::Isolation::Rtl::_ISOLATED_OBJECT_ATTRIBUTES *)v35,
                                                a7,
                                                (struct _RTL_ALTERNATE_STATUS *)0x30);
      if ( HardLink_FromIsolatedObjectAttributes < 0 )
        return (unsigned int)HardLink_FromIsolatedObjectAttributes;
    }
    else
    {
      if ( a6 != 13 )
      {
        LODWORD(v26) = 1652;
        goto LABEL_15;
      }
      if ( a5 != 1 )
      {
        LODWORD(v26) = 1647;
        goto LABEL_30;
      }
      *(_BYTE *)(a2 + 57) = *(_BYTE *)a4 != 0;
    }
    return 0;
  }
  v29 = 0;
  v28 = 0;
  v30 = 0;
  lpMem[0] = 0;
  v31 = 0;
  lpMem[1] = 0;
  v33 = 0;
  v34 = 0;
  if ( a5 != 40 )
  {
    LODWORD(v26) = 1610;
    goto LABEL_30;
  }
  HardLink_FromIsolatedObjectAttributes = Windows::Isolation::Implementation::Rtl::CWin32FullPath::Initialize(
                                            (Windows::Isolation::Implementation::Rtl::CWin32FullPath *)&v28,
                                            (const struct _LUNICODE_STRING *)(a2 + 8));
  if ( HardLink_FromIsolatedObjectAttributes >= 0 )
  {
    v15 = *(_DWORD *)(a4 + 32);
    if ( v34 == 1 )
    {
      v16 = v33;
      if ( !v33 )
      {
        RaiseException(0xC00000E5, 1u, 0, 0);
        v16 = v33;
      }
      v17 = SetFileAttributesA(*(LPCSTR *)(v16 + 16), v15);
    }
    else
    {
      if ( v34 != 2 || (v18 = v33) == 0 )
      {
        RaiseException(0xC00000E5, 1u, 0, 0);
        v18 = v33;
      }
      v17 = SetFileAttributesW(*(LPCWSTR *)(v18 + 16), v15);
    }
    if ( v17 )
    {
      v22 = lpMem[1];
      if ( lpMem[1] )
      {
        lpMem[0] = 0;
        v31 = 0;
        lpMem[1] = 0;
        IsolationFreeStringRoutine(v22);
      }
      v23 = v30;
      if ( v30 )
      {
        v29 = 0;
        v28 = 0;
        v30 = 0;
        IsolationFreeStringRoutine(v23);
      }
      return 0;
    }
    LastError_0 = GetLastError_0();
    v20 = isowin32private_Win32ErrorAltStatusHelper(LastError_0, a7);
    HardLink_FromIsolatedObjectAttributes = v20;
    if ( v20 >= 0 )
      HardLink_FromIsolatedObjectAttributes = 0;
    else
      Windows::ErrorHandling::COM::ReportNtErrorOrigination(
        (Windows::ErrorHandling::COM *)"onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\win32\\isofs_direct.cpp",
        (const char *)0x656,
        v20,
        v21);
  }
  v13 = lpMem[1];
  if ( lpMem[1] )
  {
    lpMem[0] = 0;
    v31 = 0;
    lpMem[1] = 0;
    IsolationFreeStringRoutine(v13);
  }
  v14 = v30;
  if ( v30 )
  {
    v29 = 0;
    v28 = 0;
    v30 = 0;
    IsolationFreeStringRoutine(v14);
  }
  return (unsigned int)HardLink_FromIsolatedObjectAttributes;
}

```

## disassembly

```asm
0x180023040  push    rbp
0x180023042  push    rbx
0x180023043  push    rsi
0x180023044  push    rdi
0x180023045  push    r14
0x180023047  lea     rbp, [rsp-1Fh]
0x18002304c  sub     rsp, 0B0h
0x180023053  lea     rax, ?RtlpDirectWin32IsolatedFilesystem@Rtl@Implementation@Isolation@Windows@@3U_ISOLATED_FILESYSTEM_PROVIDER_FILESYSTEM@1FsProv@34@B; Windows::Isolation::FsProv::Rtl::_ISOLATED_FILESYSTEM_PROVIDER_FILESYSTEM const Windows::Isolation::Implementation::Rtl::RtlpDirectWin32IsolatedFilesystem
0x18002305a  mov     dword ptr [rbp+3Fh+var_A0], 0C00000E5h
0x180023061  lea     r14, aOnecoreComNetf_79; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x180023068  mov     rdi, r9
0x18002306b  mov     [rbp+3Fh+var_B0], r14
0x18002306f  cmp     rcx, rax
0x180023072  jz      short loc_18002307D
0x180023074  mov     dword ptr [rbp+3Fh+var_A8], 634h
0x18002307b  jmp     short loc_1800230EE
0x18002307d  xor     esi, esi
0x18002307f  test    rdx, rdx
0x180023082  jnz     short loc_18002309C
0x180023084  lea     rcx, [rbp+3Fh+var_B0]
0x180023088  mov     dword ptr [rbp+3Fh+var_A8], 635h
0x18002308f  call    ?SetInvalidParameter@?$CBaseFrame@VCVoidRaiseFrame@Nt@ErrorHandling@Windows@@@Nt@ErrorHandling@Windows@@IEAAXXZ; Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::SetInvalidParameter(void)
0x180023094  mov     ebx, dword ptr [rbp+3Fh+var_A0]
0x180023097  jmp     loc_18002335A
0x18002309c  mov     ecx, [rbp+3Fh+arg_28]
0x18002309f  cmp     ecx, 0Dh
0x1800230a2  ja      loc_180023345
0x1800230a8  mov     eax, 2810h
0x1800230ad  bt      eax, ecx
0x1800230b0  jnb     loc_180023345
0x1800230b6  mov     rax, [rbp+3Fh+arg_20]
0x1800230ba  test    rax, 0FFFFFFFFFFFFFFE0h
0x1800230c0  jnz     short loc_1800230D4
0x1800230c2  cmp     rax, 1
0x1800230c6  jz      short loc_1800230D4
0x1800230c8  mov     dword ptr [rbp+3Fh+var_A8], 641h
0x1800230cf  jmp     loc_180023205
0x1800230d4  cmp     ecx, 4
0x1800230d7  jz      loc_1800231D9
0x1800230dd  cmp     ecx, 0Bh
0x1800230e0  jz      short loc_18002311D
0x1800230e2  cmp     ecx, 0Dh
0x1800230e5  jz      short loc_1800230FD
0x1800230e7  mov     dword ptr [rbp+3Fh+var_A8], 674h
0x1800230ee  lea     rdx, [rbp+3Fh+var_B0]
0x1800230f2  lea     rcx, [rbp+3Fh+var_B0]
0x1800230f6  call    ?InternalErrorImmediateAction@?$CBaseFrame@VCVoidRaiseFrame@Nt@ErrorHandling@Windows@@@Nt@ErrorHandling@Windows@@IEAAXAEBVCCallSite@34@@Z; Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::InternalErrorImmediateAction(Windows::ErrorHandling::CCallSite const &)
0x1800230fb  jmp     short loc_180023094
0x1800230fd  cmp     rax, 1
0x180023101  jz      short loc_18002310F
0x180023103  mov     dword ptr [rbp+3Fh+var_A8], 66Fh
0x18002310a  jmp     loc_180023205
0x18002310f  cmp     [r9], sil
0x180023112  setnz   al
0x180023115  mov     [rdx+39h], al
0x180023118  jmp     loc_180023341
0x18002311d  cmp     rax, 20h ; ' '
0x180023121  jnb     short loc_18002312F
0x180023123  mov     dword ptr [rbp+3Fh+var_A8], 65Dh
0x18002312a  jmp     loc_180023205
0x18002312f  mov     r8, [r9+10h]
0x180023133  lea     rcx, [r8+20h]
0x180023137  cmp     rcx, r8
0x18002313a  jb      loc_1800231CF
0x180023140  cmp     rcx, 20h ; ' '
0x180023144  jb      loc_1800231CF
0x18002314a  cmp     rax, rcx
0x18002314d  jz      short loc_18002315B
0x18002314f  mov     dword ptr [rbp+3Fh+var_A8], 664h
0x180023156  jmp     loc_180023205
0x18002315b  mov     r9d, 30h ; '0'; struct _RTL_ALTERNATE_STATUS *
0x180023161  mov     [rbp+3Fh+var_88], rdx
0x180023165  xorps   xmm0, xmm0
0x180023168  mov     [rbp+3Fh+var_B0], r8
0x18002316c  lea     rax, g_LUNICODE_STRING__empty_
0x180023173  mov     [rbp+3Fh+var_A8], r8
0x180023177  mov     r8, [rbp+3Fh+arg_30]; struct Windows::Isolation::Rtl::_ISOLATED_OBJECT_ATTRIBUTES *
0x18002317b  lea     rdx, [rbp+3Fh+var_50]; struct Windows::Isolation::Rtl::_ISOLATED_OBJECT_ATTRIBUTES *
0x18002317f  mov     [rbp+3Fh+var_80], rax
0x180023183  lea     ecx, [r9+10h]
0x180023187  lea     rax, [rdi+18h]
0x18002318b  mov     dword ptr [rbp+3Fh+var_78], ecx
0x18002318e  mov     [rbp+3Fh+var_A0], rax
0x180023192  lea     rax, [rbp+3Fh+var_B0]
0x180023196  mov     [rbp+3Fh+var_40], rax
0x18002319a  mov     rax, [rdi+8]
0x18002319e  mov     [rbp+3Fh+var_38], ecx
0x1800231a1  lea     rcx, [rbp+3Fh+var_90]; this
0x1800231a5  mov     [rbp+3Fh+var_48], rax
0x1800231a9  mov     [rbp+3Fh+var_90], r9
0x1800231ad  movdqu  xmmword ptr [rbp+3Fh+lpMem], xmm0
0x1800231b2  mov     [rbp+3Fh+var_50], r9
0x1800231b6  movdqu  [rbp+3Fh+var_30], xmm0
0x1800231bb  call    ?RtlpIsolatedFilesystem_DirectWin32_CreateHardLink_FromIsolatedObjectAttributes@Rtl@Implementation@Isolation@Windows@@YAJAEBU_ISOLATED_OBJECT_ATTRIBUTES@134@0PEAU_RTL_ALTERNATE_STATUS@@@Z; Windows::Isolation::Implementation::Rtl::RtlpIsolatedFilesystem_DirectWin32_CreateHardLink_FromIsolatedObjectAttributes(Windows::Isolation::Rtl::_ISOLATED_OBJECT_ATTRIBUTES const &,Windows::Isolation::Rtl::_ISOLATED_OBJECT_ATTRIBUTES const &,_RTL_ALTERNATE_STATUS *)
0x1800231c0  mov     ebx, eax
0x1800231c2  test    eax, eax
0x1800231c4  jns     loc_180023341
0x1800231ca  jmp     loc_18002335A
0x1800231cf  mov     ebx, 0C0000095h
0x1800231d4  jmp     loc_18002335A
0x1800231d9  mov     [rbp+3Fh+var_88], rsi
0x1800231dd  mov     [rbp+3Fh+var_90], rsi
0x1800231e1  mov     [rbp+3Fh+var_80], rsi
0x1800231e5  mov     [rbp+3Fh+lpMem], rsi
0x1800231e9  mov     [rbp+3Fh+var_78], rsi
0x1800231ed  mov     [rbp+3Fh+lpMem+8], rsi
0x1800231f1  mov     [rbp+3Fh+var_60], rsi
0x1800231f5  mov     [rbp+3Fh+var_58], esi
0x1800231f8  cmp     rax, 28h ; '('
0x1800231fc  jz      short loc_180023213
0x1800231fe  mov     dword ptr [rbp+3Fh+var_A8], 64Ah
0x180023205  lea     rcx, [rbp+3Fh+var_B0]
0x180023209  call    ?SetInvalidParameter@?$CBaseFrame@VCVoidRaiseFrame@Nt@ErrorHandling@Windows@@@Nt@ErrorHandling@Windows@@IEAAXXZ; Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::SetInvalidParameter(void)
0x18002320e  jmp     loc_180023094
0x180023213  add     rdx, 8; struct _LUNICODE_STRING *
0x180023217  lea     rcx, [rbp+3Fh+var_90]; this
0x18002321b  call    ?Initialize@CWin32FullPath@Rtl@Implementation@Isolation@Windows@@QEAAJAEBU_LUNICODE_STRING@@@Z; Windows::Isolation::Implementation::Rtl::CWin32FullPath::Initialize(_LUNICODE_STRING const &)
0x180023220  mov     ebx, eax
0x180023222  test    eax, eax
0x180023224  jns     short loc_180023263
0x180023226  mov     rcx, [rbp+3Fh+lpMem+8]; lpMem
0x18002322a  test    rcx, rcx
0x18002322d  jz      short loc_180023240
0x18002322f  mov     [rbp+3Fh+lpMem], rsi
0x180023233  mov     [rbp+3Fh+var_78], rsi
0x180023237  mov     [rbp+3Fh+lpMem+8], rsi
0x18002323b  call    ?IsolationFreeStringRoutine@@YAXPEAX@Z; IsolationFreeStringRoutine(void *)
0x180023240  mov     rcx, [rbp+3Fh+var_80]; lpMem
0x180023244  test    rcx, rcx
0x180023247  jz      loc_18002335A
0x18002324d  mov     [rbp+3Fh+var_88], rsi
0x180023251  mov     [rbp+3Fh+var_90], rsi
0x180023255  mov     [rbp+3Fh+var_80], rsi
0x180023259  call    ?IsolationFreeStringRoutine@@YAXPEAX@Z; IsolationFreeStringRoutine(void *)
0x18002325e  jmp     loc_18002335A
0x180023263  cmp     [rbp+3Fh+var_58], 1
0x180023267  mov     ebx, [rdi+20h]
0x18002326a  jnz     short loc_18002329B
0x18002326c  mov     rcx, [rbp+3Fh+var_60]
0x180023270  test    rcx, rcx
0x180023273  jnz     short loc_18002328D
0x180023275  lea     edx, [rcx+1]; dwExceptionFlags
0x180023278  xor     r9d, r9d; lpArguments
0x18002327b  mov     ecx, 0C00000E5h; dwExceptionCode
0x180023280  xor     r8d, r8d; nNumberOfArguments
0x180023283  call    cs:__imp_RaiseException
0x180023289  mov     rcx, [rbp+3Fh+var_60]
0x18002328d  mov     rcx, [rcx+10h]; lpFileName
0x180023291  mov     edx, ebx; dwFileAttributes
0x180023293  call    cs:__imp_SetFileAttributesA
0x180023299  jmp     short loc_1800232CF
0x18002329b  cmp     [rbp+3Fh+var_58], 2
0x18002329f  jnz     short loc_1800232AA
0x1800232a1  mov     rcx, [rbp+3Fh+var_60]
0x1800232a5  test    rcx, rcx
0x1800232a8  jnz     short loc_1800232C3
0x1800232aa  xor     r9d, r9d; lpArguments
0x1800232ad  xor     r8d, r8d; nNumberOfArguments
0x1800232b0  mov     ecx, 0C00000E5h; dwExceptionCode
0x1800232b5  lea     edx, [r9+1]; dwExceptionFlags
0x1800232b9  call    cs:__imp_RaiseException
0x1800232bf  mov     rcx, [rbp+3Fh+var_60]
0x1800232c3  mov     rcx, [rcx+10h]; lpFileName
0x1800232c7  mov     edx, ebx; dwFileAttributes
0x1800232c9  call    cs:__imp_SetFileAttributesW
0x1800232cf  mov     ebx, eax
0x1800232d1  mov     eax, esi
0x1800232d3  test    ebx, ebx
0x1800232d5  jnz     short loc_18002330D
0x1800232d7  call    GetLastError_0
0x1800232dc  test    ebx, ebx
0x1800232de  jnz     short loc_18002330D
0x1800232e0  mov     rdx, [rbp+3Fh+arg_30]; struct _RTL_ALTERNATE_STATUS *
0x1800232e4  mov     ecx, eax; unsigned int
0x1800232e6  call    ?isowin32private_Win32ErrorAltStatusHelper@@YAJKPEAU_RTL_ALTERNATE_STATUS@@@Z; isowin32private_Win32ErrorAltStatusHelper(ulong,_RTL_ALTERNATE_STATUS *)
0x1800232eb  mov     ebx, eax
0x1800232ed  test    eax, eax
0x1800232ef  jns     short loc_180023306
0x1800232f1  mov     r8d, eax; int
0x1800232f4  mov     edx, 656h; char *
0x1800232f9  mov     rcx, r14; this
0x1800232fc  call    ?ReportNtErrorOrigination@COM@ErrorHandling@Windows@@YAXPEBDHJ@Z; Windows::ErrorHandling::COM::ReportNtErrorOrigination(char const *,int,long)
0x180023301  jmp     loc_180023226
0x180023306  mov     ebx, esi
0x180023308  jmp     loc_180023226
0x18002330d  mov     rcx, [rbp+3Fh+lpMem+8]; lpMem
0x180023311  test    rcx, rcx
0x180023314  jz      short loc_180023327
0x180023316  mov     [rbp+3Fh+lpMem], rsi
0x18002331a  mov     [rbp+3Fh+var_78], rsi
0x18002331e  mov     [rbp+3Fh+lpMem+8], rsi
0x180023322  call    ?IsolationFreeStringRoutine@@YAXPEAX@Z; IsolationFreeStringRoutine(void *)
0x180023327  mov     rcx, [rbp+3Fh+var_80]; lpMem
0x18002332b  test    rcx, rcx
0x18002332e  jz      short loc_180023341
0x180023330  mov     [rbp+3Fh+var_88], rsi
0x180023334  mov     [rbp+3Fh+var_90], rsi
0x180023338  mov     [rbp+3Fh+var_80], rsi
0x18002333c  call    ?IsolationFreeStringRoutine@@YAXPEAX@Z; IsolationFreeStringRoutine(void *)
0x180023341  mov     ebx, esi
0x180023343  jmp     short loc_18002335A
0x180023345  mov     ebx, 0C000042Ch
0x18002334a  mov     edx, 63Ch; char *
0x18002334f  mov     r8d, ebx; int
0x180023352  mov     rcx, r14; this
0x180023355  call    ?ReportNtErrorOrigination@COM@ErrorHandling@Windows@@YAXPEBDHJ@Z; Windows::ErrorHandling::COM::ReportNtErrorOrigination(char const *,int,long)
0x18002335a  mov     eax, ebx
0x18002335c  add     rsp, 0B0h
0x180023363  pop     r14
0x180023365  pop     rdi
0x180023366  pop     rsi
0x180023367  pop     rbx
0x180023368  pop     rbp
0x180023369  retn
```
