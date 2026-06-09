# Windows::Isolation::Implementation::Rtl::RtlpIsolatedFilesystem_DirectWin32_CopyFile(ulong,Windows::Isolation::FsProv::Rtl::_ISOLATED_FILESYSTEM_PROVIDER_FILESYSTEM *,Windows::Isolation::Rtl::_ISOLATED_OBJECT_ATTRIBUTES const *,Windows::Isolation::Rtl::_ISOLATED_OBJECT_ATTRIBUTES const *,ulong *,_RTL_ALTERNATE_STATUS *)

- ea: `0x180020960`
- end: `0x180020bfd`
- name: `?RtlpIsolatedFilesystem_DirectWin32_CopyFile@Rtl@Implementation@Isolation@Windows@@YAJKPEAU_ISOLATED_FILESYSTEM_PROVIDER_FILESYSTEM@1FsProv@34@PEBU_ISOLATED_OBJECT_ATTRIBUTES@134@1PEAKPEAU_RTL_ALTERNATE_STATUS@@@Z`
- size: `669`
- prototype: `int(Windows::Isolation::Implementation::Rtl *__hidden this, unsigned int, struct Windows::Isolation::FsProv::Rtl::_ISOLATED_FILESYSTEM_PROVIDER_FILESYSTEM *, const struct Windows::Isolation::Rtl::_ISOLATED_OBJECT_ATTRIBUTES *, const struct Windows::Isolation::Rtl::_ISOLATED_OBJECT_ATTRIBUTES *, unsigned int *, struct _RTL_ALTERNATE_STATUS *)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180021400`

## callees

- `0x1800069e5`
- `0x180012b1c`
- `0x180018b30`
- `0x18001fd88`
- `0x180020960`
- `0x180056968`
- `0x1800b8a90`
- `0x1800fe440`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!SetFileAttributesA` at `0x180020b26`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesA` at `0x180020b26`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x180020b59`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x180020b59`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180020aec`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180020b13`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180020b46`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180020aec`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180020b13`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180020b46`

## string_xrefs

- `0x180020980`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\win32\isofs_direct.cpp`

## pseudocode

```c
__int64 __fastcall Windows::Isolation::Implementation::Rtl::RtlpIsolatedFilesystem_DirectWin32_CopyFile(
        Windows::Isolation::Implementation::Rtl *this,
        __int64 a2,
        struct Windows::Isolation::FsProv::Rtl::_ISOLATED_FILESYSTEM_PROVIDER_FILESYSTEM *a3,
        const struct Windows::Isolation::Rtl::_ISOLATED_OBJECT_ATTRIBUTES *a4,
        const struct Windows::Isolation::Rtl::_ISOLATED_OBJECT_ATTRIBUTES *a5,
        struct _RTL_ALTERNATE_STATUS *a6)
{
  int v7; // ebx
  unsigned int *v8; // rax
  int v9; // eax
  int v10; // r9d
  __int64 v11; // rdx
  int v12; // ecx
  int v13; // eax
  __int64 v14; // rcx
  BOOL v15; // eax
  __int64 v16; // rcx
  DWORD LastError_0; // eax
  void *v18; // rcx
  void *v19; // rcx
  void *v20; // rcx
  void *v21; // rcx
  __int64 v23; // [rsp+20h] [rbp-79h] BYREF
  __int64 v24; // [rsp+28h] [rbp-71h]
  void *v25; // [rsp+30h] [rbp-69h]
  __int64 v26; // [rsp+38h] [rbp-61h]
  __int64 v27; // [rsp+40h] [rbp-59h]
  void *lpMem; // [rsp+48h] [rbp-51h]
  __int64 v29; // [rsp+50h] [rbp-49h]
  int v30; // [rsp+58h] [rbp-41h]
  __int64 v31; // [rsp+60h] [rbp-39h] BYREF
  __int64 v32; // [rsp+68h] [rbp-31h]
  void *v33; // [rsp+70h] [rbp-29h]
  __int64 v34; // [rsp+78h] [rbp-21h]
  __int64 v35; // [rsp+80h] [rbp-19h]
  void *v36; // [rsp+88h] [rbp-11h]
  __int64 v37; // [rsp+90h] [rbp-9h]
  int v38; // [rsp+98h] [rbp-1h]
  const char *v39; // [rsp+A0h] [rbp+7h] BYREF
  int v40; // [rsp+A8h] [rbp+Fh]
  unsigned int v41; // [rsp+B0h] [rbp+17h]

  v41 = -1073741595;
  v32 = 0;
  v39 = "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\win32\\isofs_direct.cpp";
  v31 = 0;
  v33 = 0;
  v35 = 0;
  v34 = 0;
  v36 = 0;
  v37 = 0;
  v38 = 0;
  v24 = 0;
  v23 = 0;
  v25 = 0;
  v27 = 0;
  v26 = 0;
  lpMem = 0;
  v29 = 0;
  v30 = 0;
  if ( !a3 )
  {
    v40 = 1449;
LABEL_3:
    Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::SetInvalidParameter(&v39);
    return v41;
  }
  if ( !a4 )
  {
    v40 = 1450;
    goto LABEL_3;
  }
  v7 = Windows::Isolation::Implementation::Rtl::CWin32FullPath::Initialize(
         (Windows::Isolation::Implementation::Rtl::CWin32FullPath *)&v31,
         a3);
  if ( v7 >= 0 )
  {
    v7 = Windows::Isolation::Implementation::Rtl::CWin32FullPath::Initialize(
           (Windows::Isolation::Implementation::Rtl::CWin32FullPath *)&v23,
           a4);
    if ( v7 >= 0 )
    {
      v8 = (unsigned int *)Windows::Isolation::Implementation::Rtl::CopyFile(&v39, &v31, &v23);
      if ( v8[2] )
      {
        v12 = v38;
        v13 = v30;
        if ( v38 != v30 )
        {
          RaiseException(0xC00000E5, 1u, 0, 0);
          v12 = v38;
          v13 = v30;
        }
        if ( v12 == 1 )
        {
          if ( v13 != 1 || (v14 = v29) == 0 )
          {
            RaiseException(0xC00000E5, 1u, 0, 0);
            v14 = v29;
          }
          v15 = SetFileAttributesA(*(LPCSTR *)(v14 + 16), 0x80u);
        }
        else
        {
          if ( v13 != 2 || (v16 = v29) == 0 )
          {
            RaiseException(0xC00000E5, 1u, 0, 0);
            v16 = v29;
          }
          v15 = SetFileAttributesW(*(LPCWSTR *)(v16 + 16), 0x80u);
        }
        if ( !v15 )
        {
          LastError_0 = GetLastError_0();
          v9 = isowin32private_Win32ErrorAltStatusHelper(LastError_0, a6);
          v7 = v9;
          if ( v9 < 0 )
          {
            v11 = 1480;
            goto LABEL_11;
          }
        }
      }
      else
      {
        v9 = isowin32private_Win32ErrorAltStatusHelper(*v8, a6);
        v7 = v9;
        if ( v9 < 0 )
        {
          v11 = 1460;
LABEL_11:
          Windows::ErrorHandling::COM::ReportNtErrorOrigination(
            (Windows::ErrorHandling::COM *)"onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\win32\\isofs_direct.cpp",
            (const char *)v11,
            v9,
            v10);
          goto LABEL_27;
        }
      }
      v7 = 0;
    }
  }
LABEL_27:
  v18 = lpMem;
  if ( lpMem )
  {
    v27 = 0;
    v26 = 0;
    lpMem = 0;
    IsolationFreeStringRoutine(v18);
  }
  v19 = v25;
  if ( v25 )
  {
    v24 = 0;
    v23 = 0;
    v25 = 0;
    IsolationFreeStringRoutine(v19);
  }
  v20 = v36;
  if ( v36 )
  {
    v35 = 0;
    v34 = 0;
    v36 = 0;
    IsolationFreeStringRoutine(v20);
  }
  v21 = v33;
  if ( v33 )
  {
    v33 = 0;
    v31 = 0;
    v32 = 0;
    IsolationFreeStringRoutine(v21);
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180020960  push    rbp
0x180020962  push    rbx
0x180020963  push    rsi
0x180020964  push    rdi
0x180020965  push    r14
0x180020967  lea     rbp, [rsp-27h]
0x18002096c  sub     rsp, 0C0h
0x180020973  xor     esi, esi
0x180020975  mov     [rbp+47h+var_30], 0C00000E5h
0x18002097c  mov     [rbp+47h+var_78], rsi
0x180020980  lea     r14, aOnecoreComNetf_79; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x180020987  mov     [rbp+47h+var_40], r14
0x18002098b  mov     rdi, r9
0x18002098e  mov     [rbp+47h+var_80], rsi
0x180020992  mov     [rbp+47h+var_70], rsi
0x180020996  mov     [rbp+47h+var_60], rsi
0x18002099a  mov     [rbp+47h+var_68], rsi
0x18002099e  mov     [rbp+47h+var_58], rsi
0x1800209a2  mov     [rbp+47h+var_50], rsi
0x1800209a6  mov     [rbp+47h+var_48], esi
0x1800209a9  mov     [rbp+47h+var_B8], rsi
0x1800209ad  mov     [rbp+47h+var_C0], rsi
0x1800209b1  mov     [rbp+47h+var_B0], rsi
0x1800209b5  mov     [rbp+47h+var_A0], rsi
0x1800209b9  mov     [rbp+47h+var_A8], rsi
0x1800209bd  mov     [rbp+47h+lpMem], rsi
0x1800209c1  mov     [rbp+47h+var_90], rsi
0x1800209c5  mov     [rbp+47h+var_88], esi
0x1800209c8  test    r8, r8
0x1800209cb  jnz     loc_180020A51
0x1800209d1  mov     [rbp+47h+var_38], 5A9h
0x1800209d8  lea     rcx, [rbp+47h+var_40]
0x1800209dc  call    ?SetInvalidParameter@?$CBaseFrame@VCVoidRaiseFrame@Nt@ErrorHandling@Windows@@@Nt@ErrorHandling@Windows@@IEAAXXZ; Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::SetInvalidParameter(void)
0x1800209e1  mov     rcx, [rbp+47h+lpMem]; lpMem
0x1800209e5  test    rcx, rcx
0x1800209e8  jz      short loc_1800209FB
0x1800209ea  mov     [rbp+47h+var_A0], rsi
0x1800209ee  mov     [rbp+47h+var_A8], rsi
0x1800209f2  mov     [rbp+47h+lpMem], rsi
0x1800209f6  call    ?IsolationFreeStringRoutine@@YAXPEAX@Z; IsolationFreeStringRoutine(void *)
0x1800209fb  mov     rcx, [rbp+47h+var_B0]; lpMem
0x1800209ff  test    rcx, rcx
0x180020a02  jz      short loc_180020A15
0x180020a04  mov     [rbp+47h+var_B8], rsi
0x180020a08  mov     [rbp+47h+var_C0], rsi
0x180020a0c  mov     [rbp+47h+var_B0], rsi
0x180020a10  call    ?IsolationFreeStringRoutine@@YAXPEAX@Z; IsolationFreeStringRoutine(void *)
0x180020a15  mov     rcx, [rbp+47h+var_58]; lpMem
0x180020a19  test    rcx, rcx
0x180020a1c  jz      short loc_180020A2F
0x180020a1e  mov     [rbp+47h+var_60], rsi
0x180020a22  mov     [rbp+47h+var_68], rsi
0x180020a26  mov     [rbp+47h+var_58], rsi
0x180020a2a  call    ?IsolationFreeStringRoutine@@YAXPEAX@Z; IsolationFreeStringRoutine(void *)
0x180020a2f  mov     rcx, [rbp+47h+var_70]; lpMem
0x180020a33  test    rcx, rcx
0x180020a36  jz      short loc_180020A49
0x180020a38  mov     [rbp+47h+var_78], rsi
0x180020a3c  mov     [rbp+47h+var_80], rsi
0x180020a40  mov     [rbp+47h+var_70], rsi
0x180020a44  call    ?IsolationFreeStringRoutine@@YAXPEAX@Z; IsolationFreeStringRoutine(void *)
0x180020a49  mov     ebx, [rbp+47h+var_30]
0x180020a4c  jmp     loc_180020BED
0x180020a51  test    rdi, rdi
0x180020a54  jnz     short loc_180020A62
0x180020a56  mov     [rbp+47h+var_38], 5AAh
0x180020a5d  jmp     loc_1800209D8
0x180020a62  mov     rdx, r8; struct Windows::Isolation::Rtl::_ISOLATED_OBJECT_ATTRIBUTES *
0x180020a65  lea     rcx, [rbp+47h+var_80]; this
0x180020a69  call    ?Initialize@CWin32FullPath@Rtl@Implementation@Isolation@Windows@@QEAAJAEBU_ISOLATED_OBJECT_ATTRIBUTES@245@@Z; Windows::Isolation::Implementation::Rtl::CWin32FullPath::Initialize(Windows::Isolation::Rtl::_ISOLATED_OBJECT_ATTRIBUTES const &)
0x180020a6e  mov     ebx, eax
0x180020a70  test    eax, eax
0x180020a72  js      loc_180020B85
0x180020a78  mov     rdx, rdi; struct Windows::Isolation::Rtl::_ISOLATED_OBJECT_ATTRIBUTES *
0x180020a7b  lea     rcx, [rbp+47h+var_C0]; this
0x180020a7f  call    ?Initialize@CWin32FullPath@Rtl@Implementation@Isolation@Windows@@QEAAJAEBU_ISOLATED_OBJECT_ATTRIBUTES@245@@Z; Windows::Isolation::Implementation::Rtl::CWin32FullPath::Initialize(Windows::Isolation::Rtl::_ISOLATED_OBJECT_ATTRIBUTES const &)
0x180020a84  mov     ebx, eax
0x180020a86  test    eax, eax
0x180020a88  js      loc_180020B85
0x180020a8e  lea     r8, [rbp+47h+var_C0]
0x180020a92  lea     rdx, [rbp+47h+var_80]
0x180020a96  lea     rcx, [rbp+47h+var_40]
0x180020a9a  call    ?CopyFile@Rtl@Implementation@Isolation@Windows@@YA?AU_WIN32_FUNCTION_RETURN_STATUS@@AEBVCWin32FullPath@1234@0_N@Z; Windows::Isolation::Implementation::Rtl::CopyFile(Windows::Isolation::Implementation::Rtl::CWin32FullPath const &,Windows::Isolation::Implementation::Rtl::CWin32FullPath const &,bool)
0x180020a9f  cmp     [rax+8], esi
0x180020aa2  jnz     short loc_180020ACE
0x180020aa4  mov     rdx, [rbp+47h+arg_28]; struct _RTL_ALTERNATE_STATUS *
0x180020aa8  mov     ecx, [rax]; unsigned int
0x180020aaa  call    ?isowin32private_Win32ErrorAltStatusHelper@@YAJKPEAU_RTL_ALTERNATE_STATUS@@@Z; isowin32private_Win32ErrorAltStatusHelper(ulong,_RTL_ALTERNATE_STATUS *)
0x180020aaf  mov     ebx, eax
0x180020ab1  test    eax, eax
0x180020ab3  jns     loc_180020B83
0x180020ab9  mov     edx, 5B4h; char *
0x180020abe  mov     r8d, eax; int
0x180020ac1  mov     rcx, r14; this
0x180020ac4  call    ?ReportNtErrorOrigination@COM@ErrorHandling@Windows@@YAXPEBDHJ@Z; Windows::ErrorHandling::COM::ReportNtErrorOrigination(char const *,int,long)
0x180020ac9  jmp     loc_180020B85
0x180020ace  mov     ecx, [rbp+47h+var_48]
0x180020ad1  mov     ebx, 1
0x180020ad6  mov     eax, [rbp+47h+var_88]
0x180020ad9  mov     edi, 0C00000E5h
0x180020ade  cmp     ecx, eax
0x180020ae0  jz      short loc_180020AF8
0x180020ae2  xor     r9d, r9d; lpArguments
0x180020ae5  xor     r8d, r8d; nNumberOfArguments
0x180020ae8  mov     edx, ebx; dwExceptionFlags
0x180020aea  mov     ecx, edi; dwExceptionCode
0x180020aec  call    cs:__imp_RaiseException
0x180020af2  mov     ecx, [rbp+47h+var_48]
0x180020af5  mov     eax, [rbp+47h+var_88]
0x180020af8  cmp     ecx, ebx
0x180020afa  jnz     short loc_180020B2E
0x180020afc  cmp     eax, ebx
0x180020afe  jnz     short loc_180020B09
0x180020b00  mov     rcx, [rbp+47h+var_90]
0x180020b04  test    rcx, rcx
0x180020b07  jnz     short loc_180020B1D
0x180020b09  xor     r9d, r9d; lpArguments
0x180020b0c  xor     r8d, r8d; nNumberOfArguments
0x180020b0f  mov     edx, ebx; dwExceptionFlags
0x180020b11  mov     ecx, edi; dwExceptionCode
0x180020b13  call    cs:__imp_RaiseException
0x180020b19  mov     rcx, [rbp+47h+var_90]
0x180020b1d  mov     rcx, [rcx+10h]; lpFileName
0x180020b21  mov     edx, 80h; dwFileAttributes
0x180020b26  call    cs:__imp_SetFileAttributesA
0x180020b2c  jmp     short loc_180020B5F
0x180020b2e  cmp     eax, 2
0x180020b31  jnz     short loc_180020B3C
0x180020b33  mov     rcx, [rbp+47h+var_90]
0x180020b37  test    rcx, rcx
0x180020b3a  jnz     short loc_180020B50
0x180020b3c  xor     r9d, r9d; lpArguments
0x180020b3f  xor     r8d, r8d; nNumberOfArguments
0x180020b42  mov     edx, ebx; dwExceptionFlags
0x180020b44  mov     ecx, edi; dwExceptionCode
0x180020b46  call    cs:__imp_RaiseException
0x180020b4c  mov     rcx, [rbp+47h+var_90]
0x180020b50  mov     rcx, [rcx+10h]; lpFileName
0x180020b54  mov     edx, 80h; dwFileAttributes
0x180020b59  call    cs:__imp_SetFileAttributesW
0x180020b5f  test    eax, eax
0x180020b61  jnz     short loc_180020B83
0x180020b63  call    GetLastError_0
0x180020b68  mov     rdx, [rbp+47h+arg_28]; struct _RTL_ALTERNATE_STATUS *
0x180020b6c  mov     ecx, eax; unsigned int
0x180020b6e  call    ?isowin32private_Win32ErrorAltStatusHelper@@YAJKPEAU_RTL_ALTERNATE_STATUS@@@Z; isowin32private_Win32ErrorAltStatusHelper(ulong,_RTL_ALTERNATE_STATUS *)
0x180020b73  mov     ebx, eax
0x180020b75  test    eax, eax
0x180020b77  jns     short loc_180020B83
0x180020b79  mov     edx, 5C8h
0x180020b7e  jmp     loc_180020ABE
0x180020b83  mov     ebx, esi
0x180020b85  mov     rcx, [rbp+47h+lpMem]; lpMem
0x180020b89  test    rcx, rcx
0x180020b8c  jz      short loc_180020B9F
0x180020b8e  mov     [rbp+47h+var_A0], rsi
0x180020b92  mov     [rbp+47h+var_A8], rsi
0x180020b96  mov     [rbp+47h+lpMem], rsi
0x180020b9a  call    ?IsolationFreeStringRoutine@@YAXPEAX@Z; IsolationFreeStringRoutine(void *)
0x180020b9f  mov     rcx, [rbp+47h+var_B0]; lpMem
0x180020ba3  test    rcx, rcx
0x180020ba6  jz      short loc_180020BB9
0x180020ba8  mov     [rbp+47h+var_B8], rsi
0x180020bac  mov     [rbp+47h+var_C0], rsi
0x180020bb0  mov     [rbp+47h+var_B0], rsi
0x180020bb4  call    ?IsolationFreeStringRoutine@@YAXPEAX@Z; IsolationFreeStringRoutine(void *)
0x180020bb9  mov     rcx, [rbp+47h+var_58]; lpMem
0x180020bbd  test    rcx, rcx
0x180020bc0  jz      short loc_180020BD3
0x180020bc2  mov     [rbp+47h+var_60], rsi
0x180020bc6  mov     [rbp+47h+var_68], rsi
0x180020bca  mov     [rbp+47h+var_58], rsi
0x180020bce  call    ?IsolationFreeStringRoutine@@YAXPEAX@Z; IsolationFreeStringRoutine(void *)
0x180020bd3  mov     rcx, [rbp+47h+var_70]; lpMem
0x180020bd7  test    rcx, rcx
0x180020bda  jz      short loc_180020BED
0x180020bdc  mov     [rbp+47h+var_70], rsi
0x180020be0  mov     [rbp+47h+var_80], rsi
0x180020be4  mov     [rbp+47h+var_78], rsi
0x180020be8  call    ?IsolationFreeStringRoutine@@YAXPEAX@Z; IsolationFreeStringRoutine(void *)
0x180020bed  mov     eax, ebx
0x180020bef  add     rsp, 0C0h
0x180020bf6  pop     r14
0x180020bf8  pop     rdi
0x180020bf9  pop     rsi
0x180020bfa  pop     rbx
0x180020bfb  pop     rbp
0x180020bfc  retn
```
