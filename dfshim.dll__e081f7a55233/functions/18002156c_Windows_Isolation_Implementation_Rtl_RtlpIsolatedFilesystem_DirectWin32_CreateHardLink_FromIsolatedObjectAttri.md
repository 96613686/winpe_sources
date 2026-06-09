# Windows::Isolation::Implementation::Rtl::RtlpIsolatedFilesystem_DirectWin32_CreateHardLink_FromIsolatedObjectAttributes(Windows::Isolation::Rtl::_ISOLATED_OBJECT_ATTRIBUTES const &,Windows::Isolation::Rtl::_ISOLATED_OBJECT_ATTRIBUTES const &,_RTL_ALTERNATE_STATUS *)

- ea: `0x18002156c`
- end: `0x180021a75`
- name: `?RtlpIsolatedFilesystem_DirectWin32_CreateHardLink_FromIsolatedObjectAttributes@Rtl@Implementation@Isolation@Windows@@YAJAEBU_ISOLATED_OBJECT_ATTRIBUTES@134@0PEAU_RTL_ALTERNATE_STATUS@@@Z`
- size: `1289`
- prototype: `__int64 __fastcall(Windows::Isolation::Implementation::Rtl *__hidden this, const struct Windows::Isolation::Rtl::_ISOLATED_OBJECT_ATTRIBUTES *, const struct Windows::Isolation::Rtl::_ISOLATED_OBJECT_ATTRIBUTES *, struct _RTL_ALTERNATE_STATUS *)`
- caller_count: `2`
- callee_count: `17`
- tags: `reparse_path, loader_planting, broker_com_uri`

## callers

- `0x180021400`
- `0x180023040`

## callees

- `0x18000699d`
- `0x1800069b5`
- `0x1800069c1`
- `0x1800069cd`
- `0x1800069d9`
- `0x1800069e5`
- `0x180006aa5`
- `0x180012950`
- `0x180012b1c`
- `0x180018b30`
- `0x18001fa68`
- `0x18002156c`
- `0x1800567b4`
- `0x180056968`
- `0x1800b8a90`
- `0x1800fe440`
- `0x18012a020`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18002195a`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180021988`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18002195a`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180021988`

## string_xrefs

- `0x180021828`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\win32\isoob_direct.h`
- `0x1800215a4`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\win32\isofs_direct.cpp`
- `0x18002166e`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\win32\isofs_direct.cpp`
- `0x18002176c`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\win32\isofs_direct.cpp`
- `0x1800219c9`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\win32\isofs_direct.cpp`
- `0x1800216ff`: `CreateHardLinkW`
- `0x1800215b8`: `kernel32.dll`

## pseudocode

```c
__int64 __fastcall Windows::Isolation::Implementation::Rtl::RtlpIsolatedFilesystem_DirectWin32_CreateHardLink_FromIsolatedObjectAttributes(
        Windows::Isolation::Implementation::Rtl *this,
        const struct Windows::Isolation::Rtl::_ISOLATED_OBJECT_ATTRIBUTES *a2,
        const struct Windows::Isolation::Rtl::_ISOLATED_OBJECT_ATTRIBUTES *a3,
        struct _RTL_ALTERNATE_STATUS *a4)
{
  unsigned int (__fastcall *v4)(_QWORD, _QWORD, _QWORD); // r12
  HMODULE v8; // rbx
  int v9; // esi
  int v10; // eax
  __int64 v11; // r9
  CHAR *v12; // rdi
  HMODULE Library; // rax
  HANDLE ProcessHeap_0; // rax
  DWORD LastError_0; // eax
  int v16; // edi
  int v17; // r9d
  int v18; // eax
  CHAR *v19; // rsi
  FARPROC ProcAddress_0; // rax
  DWORD v21; // edi
  DWORD v22; // eax
  HANDLE v23; // rax
  DWORD v24; // eax
  int v25; // r9d
  void *v26; // rcx
  void *v27; // rcx
  int v28; // eax
  int v29; // eax
  void *v30; // rcx
  void *v31; // rcx
  void *v32; // rcx
  void *v33; // rcx
  __int64 v34; // rcx
  __int64 *v35; // rsi
  __int64 v36; // rdi
  __int64 v37; // rcx
  DWORD v38; // eax
  int v39; // eax
  int v40; // r9d
  void *v41; // rcx
  void *v42; // rcx
  void *v43; // rcx
  __int64 v45; // [rsp+20h] [rbp-B9h] BYREF
  __int64 v46; // [rsp+28h] [rbp-B1h]
  void *v47; // [rsp+30h] [rbp-A9h]
  __int64 v48; // [rsp+38h] [rbp-A1h]
  __int64 v49; // [rsp+40h] [rbp-99h]
  void *lpMem; // [rsp+48h] [rbp-91h]
  __int64 v51; // [rsp+50h] [rbp-89h]
  int v52; // [rsp+58h] [rbp-81h]
  __int64 v53; // [rsp+60h] [rbp-79h] BYREF
  __int64 v54; // [rsp+68h] [rbp-71h]
  void *v55; // [rsp+70h] [rbp-69h]
  __int64 v56; // [rsp+78h] [rbp-61h]
  __int64 v57; // [rsp+80h] [rbp-59h]
  void *v58; // [rsp+88h] [rbp-51h]
  __int64 v59; // [rsp+90h] [rbp-49h]
  int v60; // [rsp+98h] [rbp-41h]
  __int64 v61; // [rsp+A0h] [rbp-39h] BYREF
  __int64 v62; // [rsp+A8h] [rbp-31h]
  __int64 v63; // [rsp+B0h] [rbp-29h]
  __int64 *v64; // [rsp+B8h] [rbp-21h]
  const char *v65; // [rsp+C0h] [rbp-19h] BYREF
  int v66; // [rsp+C8h] [rbp-11h]
  unsigned int v67; // [rsp+D0h] [rbp-9h]
  const char *v68; // [rsp+D8h] [rbp-1h] BYREF
  int v69; // [rsp+E0h] [rbp+7h]
  int v70; // [rsp+E8h] [rbp+Fh]
  LPCSTR lpLibFileName; // [rsp+158h] [rbp+7Fh] BYREF

  v4 = 0;
  v67 = -1073741595;
  v54 = 0;
  v53 = 0;
  v55 = 0;
  v57 = 0;
  v65 = "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\win32\\isofs_direct.cpp";
  v56 = 0;
  v58 = 0;
  v8 = 0;
  v59 = 0;
  v60 = 0;
  v9 = 0;
  v47 = 0;
  v49 = 0;
  v48 = 0;
  lpMem = 0;
  v51 = 0;
  v52 = 0;
  v64 = 0;
  v61 = 24;
  v63 = 0;
  v62 = 0;
  lpLibFileName = 0;
  v10 = BCL::Win32::CNullTerminatedString<char>::Assign(&lpLibFileName, "kernel32.dll", 12, a4, 0, 0);
  v12 = (CHAR *)lpLibFileName;
  if ( v10 )
  {
    Library = LoadLibraryExA_0(lpLibFileName, 0, 0);
    if ( Library )
    {
      v8 = Library;
      v9 = 1;
    }
  }
  if ( v12 )
  {
    ProcessHeap_0 = GetProcessHeap_0();
    HeapFree_0(ProcessHeap_0, 0, v12);
  }
  if ( !v9 )
  {
    LastError_0 = GetLastError_0();
    v16 = isowin32_ConvertWin32ErrorToNtStatus(LastError_0);
    Windows::ErrorHandling::COM::ReportNtErrorOrigination(
      (Windows::ErrorHandling::COM *)"onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\win32\\isofs_direct.cpp",
      (const char *)0x56A,
      v16,
      v17);
    goto LABEL_65;
  }
  lpLibFileName = 0;
  v18 = BCL::Win32::CNullTerminatedString<char>::Assign(&lpLibFileName, "CreateHardLinkW", 15, v11, v45, v46);
  v19 = (CHAR *)lpLibFileName;
  if ( v18 && (ProcAddress_0 = GetProcAddress_0(v8, lpLibFileName)) != 0 )
  {
    v4 = (unsigned int (__fastcall *)(_QWORD, _QWORD, _QWORD))ProcAddress_0;
    v21 = 0;
  }
  else
  {
    v22 = GetLastError_0();
    v21 = v22;
    if ( v22 )
      SetLastError_0(v22);
  }
  if ( v19 )
  {
    v23 = GetProcessHeap_0();
    HeapFree_0(v23, 0, v19);
  }
  if ( v21 )
  {
    v24 = GetLastError_0();
    v16 = isowin32_ConvertWin32ErrorToNtStatus(v24);
    Windows::ErrorHandling::COM::ReportNtErrorOrigination(
      (Windows::ErrorHandling::COM *)"onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\win32\\isofs_direct.cpp",
      (const char *)0x56C,
      v16,
      v25);
LABEL_18:
    v26 = v58;
    if ( v58 )
    {
      v57 = 0;
      v56 = 0;
      v58 = 0;
      IsolationFreeStringRoutine(v26);
    }
    v27 = v55;
    if ( !v55 )
      goto LABEL_65;
    v54 = 0;
    v53 = 0;
    v55 = 0;
    goto LABEL_64;
  }
  v16 = Windows::Isolation::Implementation::Rtl::CWin32FullPath::Initialize(
          (Windows::Isolation::Implementation::Rtl::CWin32FullPath *)&v53,
          this);
  if ( v16 < 0 )
    goto LABEL_18;
  v16 = Windows::Isolation::Implementation::Rtl::CWin32FullPath::Initialize(
          (Windows::Isolation::Implementation::Rtl::CWin32FullPath *)&v45,
          a2);
  if ( v16 < 0 )
    goto LABEL_56;
  v70 = -1073741595;
  v68 = "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\win32\\isoob_direct.h";
  if ( !this )
  {
    v69 = 101;
    Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::SetInvalidParameter(&v68);
    v16 = v70;
    goto LABEL_32;
  }
  v28 = *((_DWORD *)this + 6) & 2;
  if ( v28 )
    LODWORD(v63) = 1;
  if ( *((_QWORD *)this + 4) )
  {
    v62 = *((_QWORD *)this + 4);
LABEL_30:
    v64 = &v61;
    goto LABEL_31;
  }
  if ( v28 )
    goto LABEL_30;
LABEL_31:
  v16 = 0;
LABEL_32:
  if ( v16 < 0 )
    goto LABEL_56;
  v29 = v52;
  if ( v52 == 2 )
  {
    if ( v60 != 2 )
    {
      v66 = 1395;
      goto LABEL_35;
    }
    v34 = v59;
    v35 = v64;
    if ( !v59 )
    {
      RaiseException(0xC00000E5, 1u, 0, 0);
      v34 = v59;
      v29 = v52;
    }
    v36 = *(_QWORD *)(v34 + 16);
    if ( v29 != 2 || (v37 = v51) == 0 )
    {
      RaiseException(0xC00000E5, 1u, 0, 0);
      v37 = v51;
    }
    if ( v4(*(_QWORD *)(v37 + 16), v36, v35)
      || (v38 = GetLastError_0(), v39 = isowin32private_Win32ErrorAltStatusHelper(v38, a3), v16 = v39, v39 >= 0) )
    {
      v16 = 0;
    }
    else
    {
      Windows::ErrorHandling::COM::ReportNtErrorOrigination(
        (Windows::ErrorHandling::COM *)"onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\win32\\isofs_direct.cpp",
        (const char *)0x57A,
        v39,
        v40);
    }
LABEL_56:
    v41 = lpMem;
    if ( lpMem )
    {
      v49 = 0;
      v48 = 0;
      lpMem = 0;
      IsolationFreeStringRoutine(v41);
    }
    v42 = v47;
    if ( v47 )
    {
      v46 = 0;
      v45 = 0;
      v47 = 0;
      IsolationFreeStringRoutine(v42);
    }
    v43 = v58;
    if ( v58 )
    {
      v57 = 0;
      v56 = 0;
      v58 = 0;
      IsolationFreeStringRoutine(v43);
    }
    v27 = v55;
    if ( !v55 )
      goto LABEL_65;
    v54 = 0;
    v53 = 0;
    v55 = 0;
LABEL_64:
    IsolationFreeStringRoutine(v27);
LABEL_65:
    if ( v8 )
      FreeLibrary_0(v8);
    return (unsigned int)v16;
  }
  v66 = 1394;
LABEL_35:
  v30 = lpMem;
  if ( lpMem )
  {
    v49 = 0;
    v48 = 0;
    lpMem = 0;
    IsolationFreeStringRoutine(v30);
  }
  v31 = v47;
  if ( v47 )
  {
    v46 = 0;
    v45 = 0;
    v47 = 0;
    IsolationFreeStringRoutine(v31);
  }
  v32 = v58;
  if ( v58 )
  {
    v57 = 0;
    v56 = 0;
    v58 = 0;
    IsolationFreeStringRoutine(v32);
  }
  v33 = v55;
  if ( v55 )
  {
    v54 = 0;
    v53 = 0;
    v55 = 0;
    IsolationFreeStringRoutine(v33);
  }
  if ( v8 )
    FreeLibrary_0(v8);
  Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::InternalErrorImmediateAction(
    &v65,
    &v65);
  return v67;
}

```

## disassembly

```asm
0x18002156c  push    rbp
0x18002156e  push    rbx
0x18002156f  push    rsi
0x180021570  push    rdi
0x180021571  push    r12
0x180021573  push    r13
0x180021575  push    r14
0x180021577  push    r15
0x180021579  lea     rbp, [rsp-1Fh]
0x18002157e  sub     rsp, 0F8h
0x180021585  xor     r12d, r12d
0x180021588  mov     [rbp+57h+var_60], 0C00000E5h
0x18002158f  mov     r13, r8
0x180021592  mov     [rbp+57h+var_C8], r12
0x180021596  mov     r15, rdx
0x180021599  mov     [rbp+57h+var_D0], r12
0x18002159d  mov     r14, rcx
0x1800215a0  mov     [rbp+57h+var_C0], r12
0x1800215a4  lea     rax, aOnecoreComNetf_79; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x1800215ab  mov     [rbp+57h+var_B0], r12
0x1800215af  lea     r8d, [r12+0Ch]
0x1800215b4  mov     [rbp+57h+var_70], rax
0x1800215b8  lea     rdx, g_RGCH_kernel32_dot_dll; "kernel32.dll"
0x1800215bf  mov     [rbp+57h+var_B8], r12
0x1800215c3  lea     rcx, [rbp+57h+lpLibFileName]
0x1800215c7  mov     [rbp+57h+var_A8], r12
0x1800215cb  mov     ebx, r12d
0x1800215ce  mov     [rbp+57h+var_A0], r12
0x1800215d2  mov     [rbp+57h+var_98], r12d
0x1800215d6  mov     esi, r12d
0x1800215d9  mov     [rsp+130h+var_108], r12
0x1800215de  mov     [rsp+130h+var_110], r12
0x1800215e3  mov     [rsp+130h+var_100], r12
0x1800215e8  mov     [rsp+130h+var_F0], r12
0x1800215ed  mov     [rsp+130h+var_F8], r12
0x1800215f2  mov     [rsp+130h+lpMem], r12
0x1800215f7  mov     [rsp+130h+var_E0], r12
0x1800215fc  mov     [rsp+130h+var_D8], r12d
0x180021601  mov     [rbp+57h+var_78], r12
0x180021605  mov     [rbp+57h+var_90], 18h
0x18002160d  mov     [rbp+57h+var_80], r12
0x180021611  mov     [rbp+57h+var_88], r12
0x180021615  mov     [rbp+57h+lpLibFileName], r12
0x180021619  call    ?Assign@?$CNullTerminatedString@D@Win32@BCL@@QEAAHPEBD_K@Z; BCL::Win32::CNullTerminatedString<char>::Assign(char const *,unsigned __int64)
0x18002161e  mov     rdi, [rbp+57h+lpLibFileName]
0x180021622  test    eax, eax
0x180021624  jz      short loc_180021640
0x180021626  xor     r8d, r8d; dwFlags
0x180021629  xor     edx, edx; hFile
0x18002162b  mov     rcx, rdi; lpLibFileName
0x18002162e  call    LoadLibraryExA_0
0x180021633  test    rax, rax
0x180021636  jz      short loc_180021640
0x180021638  mov     rbx, rax
0x18002163b  lea     esi, [r12+1]
0x180021640  test    rdi, rdi
0x180021643  jz      short loc_180021657
0x180021645  call    GetProcessHeap_0
0x18002164a  mov     r8, rdi; lpMem
0x18002164d  xor     edx, edx; dwFlags
0x18002164f  mov     rcx, rax; hHeap
0x180021652  call    HeapFree_0
0x180021657  test    esi, esi
0x180021659  jnz     loc_1800216F5
0x18002165f  call    GetLastError_0
0x180021664  mov     ecx, eax; unsigned int
0x180021666  call    ?isowin32_ConvertWin32ErrorToNtStatus@@YAJK@Z; isowin32_ConvertWin32ErrorToNtStatus(ulong)
0x18002166b  mov     r8d, eax; int
0x18002166e  lea     rcx, aOnecoreComNetf_79; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x180021675  mov     edx, 56Ah; char *
0x18002167a  mov     edi, eax
0x18002167c  call    ?ReportNtErrorOrigination@COM@ErrorHandling@Windows@@YAXPEBDHJ@Z; Windows::ErrorHandling::COM::ReportNtErrorOrigination(char const *,int,long)
0x180021681  mov     rcx, [rsp+130h+lpMem]; lpMem
0x180021686  test    rcx, rcx
0x180021689  jz      short loc_18002169F
0x18002168b  mov     [rsp+130h+var_F0], r12
0x180021690  mov     [rsp+130h+var_F8], r12
0x180021695  mov     [rsp+130h+lpMem], r12
0x18002169a  call    ?IsolationFreeStringRoutine@@YAXPEAX@Z; IsolationFreeStringRoutine(void *)
0x18002169f  mov     rcx, [rsp+130h+var_100]; lpMem
0x1800216a4  test    rcx, rcx
0x1800216a7  jz      short loc_1800216BD
0x1800216a9  mov     [rsp+130h+var_108], r12
0x1800216ae  mov     [rsp+130h+var_110], r12
0x1800216b3  mov     [rsp+130h+var_100], r12
0x1800216b8  call    ?IsolationFreeStringRoutine@@YAXPEAX@Z; IsolationFreeStringRoutine(void *)
0x1800216bd  mov     rcx, [rbp+57h+var_A8]; lpMem
0x1800216c1  test    rcx, rcx
0x1800216c4  jz      short loc_1800216D7
0x1800216c6  mov     [rbp+57h+var_B0], r12
0x1800216ca  mov     [rbp+57h+var_B8], r12
0x1800216ce  mov     [rbp+57h+var_A8], r12
0x1800216d2  call    ?IsolationFreeStringRoutine@@YAXPEAX@Z; IsolationFreeStringRoutine(void *)
0x1800216d7  mov     rcx, [rbp+57h+var_C0]
0x1800216db  test    rcx, rcx
0x1800216de  jz      loc_180021A4A
0x1800216e4  mov     [rbp+57h+var_C8], r12
0x1800216e8  mov     [rbp+57h+var_D0], r12
0x1800216ec  mov     [rbp+57h+var_C0], r12
0x1800216f0  jmp     loc_180021A45
0x1800216f5  mov     r8d, 0Fh
0x1800216fb  mov     [rbp+57h+lpLibFileName], r12
0x1800216ff  lea     rdx, g_RGCH_CreateHardLinkW; "CreateHardLinkW"
0x180021706  lea     rcx, [rbp+57h+lpLibFileName]
0x18002170a  call    ?Assign@?$CNullTerminatedString@D@Win32@BCL@@QEAAHPEBD_K@Z; BCL::Win32::CNullTerminatedString<char>::Assign(char const *,unsigned __int64)
0x18002170f  mov     rsi, [rbp+57h+lpLibFileName]
0x180021713  test    eax, eax
0x180021715  jz      short loc_18002172E
0x180021717  mov     rdx, rsi; lpProcName
0x18002171a  mov     rcx, rbx; hModule
0x18002171d  call    GetProcAddress_0
0x180021722  test    rax, rax
0x180021725  jz      short loc_18002172E
0x180021727  mov     r12, rax
0x18002172a  xor     edi, edi
0x18002172c  jmp     short loc_180021740
0x18002172e  call    GetLastError_0
0x180021733  mov     edi, eax
0x180021735  test    eax, eax
0x180021737  jz      short loc_180021740
0x180021739  mov     ecx, eax; dwErrCode
0x18002173b  call    SetLastError_0
0x180021740  test    rsi, rsi
0x180021743  jz      short loc_180021757
0x180021745  call    GetProcessHeap_0
0x18002174a  mov     r8, rsi; lpMem
0x18002174d  xor     edx, edx; dwFlags
0x18002174f  mov     rcx, rax; hHeap
0x180021752  call    HeapFree_0
0x180021757  xor     esi, esi
0x180021759  test    edi, edi
0x18002175b  jz      short loc_180021781
0x18002175d  call    GetLastError_0
0x180021762  mov     ecx, eax; unsigned int
0x180021764  call    ?isowin32_ConvertWin32ErrorToNtStatus@@YAJK@Z; isowin32_ConvertWin32ErrorToNtStatus(ulong)
0x180021769  mov     r8d, eax; int
0x18002176c  lea     rcx, aOnecoreComNetf_79; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x180021773  mov     edx, 56Ch; char *
0x180021778  mov     edi, eax
0x18002177a  call    ?ReportNtErrorOrigination@COM@ErrorHandling@Windows@@YAXPEBDHJ@Z; Windows::ErrorHandling::COM::ReportNtErrorOrigination(char const *,int,long)
0x18002177f  jmp     short loc_180021793
0x180021781  mov     rdx, r14; struct Windows::Isolation::Rtl::_ISOLATED_OBJECT_ATTRIBUTES *
0x180021784  lea     rcx, [rbp+57h+var_D0]; this
0x180021788  call    ?Initialize@CWin32FullPath@Rtl@Implementation@Isolation@Windows@@QEAAJAEBU_ISOLATED_OBJECT_ATTRIBUTES@245@@Z; Windows::Isolation::Implementation::Rtl::CWin32FullPath::Initialize(Windows::Isolation::Rtl::_ISOLATED_OBJECT_ATTRIBUTES const &)
0x18002178d  mov     edi, eax
0x18002178f  test    eax, eax
0x180021791  jns     short loc_180021807
0x180021793  mov     rcx, [rsp+130h+lpMem]; lpMem
0x180021798  test    rcx, rcx
0x18002179b  jz      short loc_1800217B1
0x18002179d  mov     [rsp+130h+var_F0], rsi
0x1800217a2  mov     [rsp+130h+var_F8], rsi
0x1800217a7  mov     [rsp+130h+lpMem], rsi
0x1800217ac  call    ?IsolationFreeStringRoutine@@YAXPEAX@Z; IsolationFreeStringRoutine(void *)
0x1800217b1  mov     rcx, [rsp+130h+var_100]; lpMem
0x1800217b6  test    rcx, rcx
0x1800217b9  jz      short loc_1800217CF
0x1800217bb  mov     [rsp+130h+var_108], rsi
0x1800217c0  mov     [rsp+130h+var_110], rsi
0x1800217c5  mov     [rsp+130h+var_100], rsi
0x1800217ca  call    ?IsolationFreeStringRoutine@@YAXPEAX@Z; IsolationFreeStringRoutine(void *)
0x1800217cf  mov     rcx, [rbp+57h+var_A8]; lpMem
0x1800217d3  test    rcx, rcx
0x1800217d6  jz      short loc_1800217E9
0x1800217d8  mov     [rbp+57h+var_B0], rsi
0x1800217dc  mov     [rbp+57h+var_B8], rsi
0x1800217e0  mov     [rbp+57h+var_A8], rsi
0x1800217e4  call    ?IsolationFreeStringRoutine@@YAXPEAX@Z; IsolationFreeStringRoutine(void *)
0x1800217e9  mov     rcx, [rbp+57h+var_C0]
0x1800217ed  test    rcx, rcx
0x1800217f0  jz      loc_180021A4A
0x1800217f6  mov     [rbp+57h+var_C8], rsi
0x1800217fa  mov     [rbp+57h+var_D0], rsi
0x1800217fe  mov     [rbp+57h+var_C0], rsi
0x180021802  jmp     loc_180021A45
0x180021807  mov     rdx, r15; struct Windows::Isolation::Rtl::_ISOLATED_OBJECT_ATTRIBUTES *
0x18002180a  lea     rcx, [rsp+130h+var_110]; this
0x18002180f  call    ?Initialize@CWin32FullPath@Rtl@Implementation@Isolation@Windows@@QEAAJAEBU_ISOLATED_OBJECT_ATTRIBUTES@245@@Z; Windows::Isolation::Implementation::Rtl::CWin32FullPath::Initialize(Windows::Isolation::Rtl::_ISOLATED_OBJECT_ATTRIBUTES const &)
0x180021814  xor     r15d, r15d
0x180021817  mov     edi, eax
0x180021819  test    eax, eax
0x18002181b  js      loc_1800219DA
0x180021821  mov     [rbp+57h+var_48], 0C00000E5h
0x180021828  lea     rax, aOnecoreComNetf_1; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x18002182f  mov     [rbp+57h+var_58], rax
0x180021833  test    r14, r14
0x180021836  jnz     short loc_18002184D
0x180021838  lea     rcx, [rbp+57h+var_58]
0x18002183c  mov     [rbp+57h+var_50], 65h ; 'e'
0x180021843  call    ?SetInvalidParameter@?$CBaseFrame@VCVoidRaiseFrame@Nt@ErrorHandling@Windows@@@Nt@ErrorHandling@Windows@@IEAAXXZ; Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::SetInvalidParameter(void)
0x180021848  mov     edi, [rbp+57h+var_48]
0x18002184b  jmp     short loc_18002187B
0x18002184d  mov     eax, [r14+18h]
0x180021851  and     eax, 2
0x180021854  jz      short loc_18002185D
0x180021856  mov     dword ptr [rbp+57h+var_80], 1
0x18002185d  mov     rcx, [r14+20h]
0x180021861  test    rcx, rcx
0x180021864  jz      short loc_18002186C
0x180021866  mov     [rbp+57h+var_88], rcx
0x18002186a  jmp     short loc_180021870
0x18002186c  test    eax, eax
0x18002186e  jz      short loc_180021878
0x180021870  lea     rax, [rbp+57h+var_90]
0x180021874  mov     [rbp+57h+var_78], rax
0x180021878  mov     edi, r15d
0x18002187b  test    edi, edi
0x18002187d  js      loc_1800219DA
0x180021883  mov     eax, [rsp+130h+var_D8]
0x180021887  cmp     eax, 2
0x18002188a  jz      loc_180021929
0x180021890  mov     [rbp+57h+var_68], 572h
0x180021897  mov     rcx, [rsp+130h+lpMem]; lpMem
0x18002189c  test    rcx, rcx
0x18002189f  jz      short loc_1800218B5
0x1800218a1  mov     [rsp+130h+var_F0], r15
0x1800218a6  mov     [rsp+130h+var_F8], r15
0x1800218ab  mov     [rsp+130h+lpMem], r15
0x1800218b0  call    ?IsolationFreeStringRoutine@@YAXPEAX@Z; IsolationFreeStringRoutine(void *)
0x1800218b5  mov     rcx, [rsp+130h+var_100]; lpMem
0x1800218ba  test    rcx, rcx
0x1800218bd  jz      short loc_1800218D3
0x1800218bf  mov     [rsp+130h+var_108], r15
0x1800218c4  mov     [rsp+130h+var_110], r15
0x1800218c9  mov     [rsp+130h+var_100], r15
0x1800218ce  call    ?IsolationFreeStringRoutine@@YAXPEAX@Z; IsolationFreeStringRoutine(void *)
0x1800218d3  mov     rcx, [rbp+57h+var_A8]; lpMem
0x1800218d7  test    rcx, rcx
0x1800218da  jz      short loc_1800218ED
0x1800218dc  mov     [rbp+57h+var_B0], r15
0x1800218e0  mov     [rbp+57h+var_B8], r15
0x1800218e4  mov     [rbp+57h+var_A8], r15
0x1800218e8  call    ?IsolationFreeStringRoutine@@YAXPEAX@Z; IsolationFreeStringRoutine(void *)
0x1800218ed  mov     rcx, [rbp+57h+var_C0]; lpMem
0x1800218f1  test    rcx, rcx
0x1800218f4  jz      short loc_180021907
0x1800218f6  mov     [rbp+57h+var_C8], r15
0x1800218fa  mov     [rbp+57h+var_D0], r15
0x1800218fe  mov     [rbp+57h+var_C0], r15
0x180021902  call    ?IsolationFreeStringRoutine@@YAXPEAX@Z; IsolationFreeStringRoutine(void *)
0x180021907  test    rbx, rbx
0x18002190a  jz      short loc_180021914
0x18002190c  mov     rcx, rbx; hLibModule
0x18002190f  call    FreeLibrary_0
0x180021914  lea     rdx, [rbp+57h+var_70]
0x180021918  lea     rcx, [rbp+57h+var_70]
0x18002191c  call    ?InternalErrorImmediateAction@?$CBaseFrame@VCVoidRaiseFrame@Nt@ErrorHandling@Windows@@@Nt@ErrorHandling@Windows@@IEAAXAEBVCCallSite@34@@Z; Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::InternalErrorImmediateAction(Windows::ErrorHandling::CCallSite const &)
0x180021921  mov     edi, [rbp+57h+var_60]
0x180021924  jmp     loc_180021A57
0x180021929  cmp     [rbp+57h+var_98], 2
0x18002192d  jz      short loc_18002193B
0x18002192f  mov     [rbp+57h+var_68], 573h
0x180021936  jmp     loc_180021897
0x18002193b  mov     rcx, [rbp+57h+var_A0]
0x18002193f  mov     r14d, 0C00000E5h
0x180021945  mov     rsi, [rbp+57h+var_78]
0x180021949  test    rcx, rcx
0x18002194c  jnz     short loc_180021968
0x18002194e  lea     edx, [rcx+1]; dwExceptionFlags
0x180021951  xor     r9d, r9d; lpArguments
0x180021954  mov     ecx, r14d; dwExceptionCode
0x180021957  xor     r8d, r8d; nNumberOfArguments
0x18002195a  call    cs:__imp_RaiseException
0x180021960  mov     rcx, [rbp+57h+var_A0]
0x180021964  mov     eax, [rsp+130h+var_D8]
0x180021968  mov     rdi, [rcx+10h]
0x18002196c  cmp     eax, 2
0x18002196f  jnz     short loc_18002197B
0x180021971  mov     rcx, [rsp+130h+var_E0]
0x180021976  test    rcx, rcx
0x180021979  jnz     short loc_180021993
0x18002197b  xor     r9d, r9d; lpArguments
0x18002197e  xor     r8d, r8d; nNumberOfArguments
0x180021981  mov     ecx, r14d; dwExceptionCode
0x180021984  lea     edx, [r9+1]; dwExceptionFlags
0x180021988  call    cs:__imp_RaiseException
0x18002198e  mov     rcx, [rsp+130h+var_E0]
0x180021993  mov     rcx, [rcx+10h]
0x180021997  mov     r8, rsi
0x18002199a  mov     rdx, rdi
0x18002199d  mov     rax, r12
0x1800219a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800219a5  test    eax, eax
0x1800219a7  jnz     loc_180021A6D
0x1800219ad  call    GetLastError_0
0x1800219b2  mov     ecx, eax; unsigned int
0x1800219b4  mov     rdx, r13; struct _RTL_ALTERNATE_STATUS *
0x1800219b7  call    ?isowin32private_Win32ErrorAltStatusHelper@@YAJKPEAU_RTL_ALTERNATE_STATUS@@@Z; isowin32private_Win32ErrorAltStatusHelper(ulong,_RTL_ALTERNATE_STATUS *)
0x1800219bc  mov     edi, eax
0x1800219be  test    eax, eax
0x1800219c0  jns     loc_180021A6D
0x1800219c6  mov     r8d, eax; int
0x1800219c9  lea     rcx, aOnecoreComNetf_79; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x1800219d0  mov     edx, 57Ah; char *
0x1800219d5  call    ?ReportNtErrorOrigination@COM@ErrorHandling@Windows@@YAXPEBDHJ@Z; Windows::ErrorHandling::COM::ReportNtErrorOrigination(char const *,int,long)
0x1800219da  mov     rcx, [rsp+130h+lpMem]; lpMem
0x1800219df  test    rcx, rcx
0x1800219e2  jz      short loc_1800219F8
0x1800219e4  mov     [rsp+130h+var_F0], r15
0x1800219e9  mov     [rsp+130h+var_F8], r15
  ... truncated ...
```
