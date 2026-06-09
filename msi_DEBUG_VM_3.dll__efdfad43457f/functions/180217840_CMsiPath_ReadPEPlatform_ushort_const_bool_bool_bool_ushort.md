# CMsiPath::ReadPEPlatform(ushort const *,bool &,bool &,bool &,ushort &)

- ea: `0x180217840`
- end: `0x180217c81`
- name: `?ReadPEPlatform@CMsiPath@@UEAAPEAVIMsiRecord@@PEBGAEA_N11AEAG@Z`
- size: `1089`
- prototype: `struct IMsiRecord *__fastcall(CMsiPath *__hidden this, const unsigned __int16 *, bool *, bool *, bool *, HANDLE hFile)`
- caller_count: `0`
- callee_count: `8`
- tags: `file_ops, loader_planting, service_task, installer_update`

## callees

- `0x180025a18`
- `0x180083178`
- `0x1800833ec`
- `0x1801382a0`
- `0x180146548`
- `0x18014e4d4`
- `0x180217840`
- `0x18025c010`

## import_xrefs

- `ntdll!NtMapViewOfSection` at `0x180217a67`
- `ntdll!NtMapViewOfSection` at `0x180217a67`
- `ntdll!NtUnmapViewOfSection` at `0x180217c31`
- `ntdll!NtUnmapViewOfSection` at `0x180217c31`
- `KERNEL32!CreateFileMappingW` at `0x180217a10`
- `KERNEL32!CreateFileMappingW` at `0x180217a10`
- `KERNEL32!GetLastError` at `0x180217bf2`
- `KERNEL32!GetLastError` at `0x180217bf2`
- `KERNEL32!SetLastError` at `0x1802179df`
- `KERNEL32!SetLastError` at `0x1802179df`
- `KERNEL32!GetCurrentProcess` at `0x180217a2f`
- `KERNEL32!GetCurrentProcess` at `0x180217c25`
- `KERNEL32!GetCurrentProcess` at `0x180217a2f`
- `KERNEL32!GetCurrentProcess` at `0x180217c25`
- `KERNEL32!CreateFileW` at `0x180217941`
- `KERNEL32!CreateFileW` at `0x180217941`
- `KERNEL32!GetFileType` at `0x180217964`
- `KERNEL32!GetFileType` at `0x180217964`

## string_xrefs

- `0x18021799b`: `Error: This is not a valid file, hence failing to create: %s`

## pseudocode

```c
struct IMsiRecord *__fastcall CMsiPath::ReadPEPlatform(
        CMsiPath *this,
        const unsigned __int16 *a2,
        bool *a3,
        bool *a4,
        bool *a5,
        __int64 hFile)
{
  bool *v6; // r13
  _WORD *v7; // r14
  char v11; // r12
  __int64 v12; // rax
  __int64 (__fastcall *v13)(CMsiPath *, const unsigned __int16 *, bool **); // rbx
  __int64 v14; // rcx
  struct IMsiRecord *v15; // rbx
  const WCHAR *v16; // rax
  bool v17; // di
  HANDLE FileW; // rax
  HANDLE v19; // rbx
  const unsigned __int16 *v20; // rax
  HANDLE FileMappingW; // rax
  HANDLE v22; // rbx
  HANDLE CurrentProcess; // rax
  int LastError; // ebx
  bool *v25; // rcx
  __int64 (__fastcall *v26)(CMsiPath *, __int64, bool *); // rbx
  __int64 v27; // rax
  __int16 v28; // ax
  const unsigned __int16 *v29; // rax
  PVOID v30; // rdi
  HANDLE v31; // rax
  HANDLE SectionHandle; // [rsp+60h] [rbp-20h] BYREF
  ULONG_PTR ViewSize; // [rsp+68h] [rbp-18h] BYREF
  __int64 v35; // [rsp+70h] [rbp-10h] BYREF
  PVOID BaseAddress; // [rsp+C0h] [rbp+40h] BYREF
  bool *v37; // [rsp+D8h] [rbp+58h]

  v37 = a4;
  v6 = a5;
  v7 = (_WORD *)hFile;
  hFile = -1;
  SectionHandle = (HANDLE)-1LL;
  a5 = (bool *)&MsiString::s_NullString;
  *a4 = 0;
  *v6 = 0;
  v11 = 0;
  *v7 = -1;
  v12 = *(_QWORD *)this;
  BaseAddress = 0;
  v35 = 0;
  ViewSize = 0;
  v13 = *(__int64 (__fastcall **)(CMsiPath *, const unsigned __int16 *, bool **))(v12 + 136);
  (*(void (**)(void))(MsiString::s_NullString + 16LL))();
  a5 = (bool *)&MsiString::s_NullString;
  v15 = (struct IMsiRecord *)v13(this, a2, &a5);
  if ( !v15 )
  {
    v11 = (*(__int64 (__fastcall **)(CMsiPath *))(*(_QWORD *)this + 544LL))(this);
    if ( v11 )
      StartImpersonating();
    v16 = (const WCHAR *)(*(__int64 (__fastcall **)(bool *))(*(_QWORD *)a5 + 80LL))(a5);
    v17 = 1;
    FileW = CreateFileW(v16, 0x80000000, 1u, 0, 3u, 0x100000u, 0);
    CHandle::operator=(&hFile, FileW);
    v19 = (HANDLE)hFile;
    if ( hFile == -1 )
      goto LABEL_43;
    if ( GetFileType((HANDLE)hFile) - 2 <= 1 )
    {
      if ( g_dmDiagnosticMode )
      {
        v20 = (const unsigned __int16 *)(*(__int64 (__fastcall **)(bool *))(*(_QWORD *)a5 + 80LL))(a5);
        DebugString(
          9,
          0,
          0,
          L"Error: This is not a valid file, hence failing to create: %s",
          v20,
          L"(NULL)",
          L"(NULL)",
          L"(NULL)",
          L"(NULL)",
          L"(NULL)",
          0,
          0);
      }
      CHandle::operator=(&hFile, -1);
      SetLastError(0x6Eu);
      v19 = (HANDLE)hFile;
    }
    if ( v19 == (HANDLE)-1LL
      || (FileMappingW = CreateFileMappingW(v19, 0, 2u, 0, 0, 0),
          CHandle::operator=(&SectionHandle, FileMappingW),
          (v22 = SectionHandle) == 0) )
    {
LABEL_43:
      LastError = GetLastError();
    }
    else
    {
      CurrentProcess = GetCurrentProcess();
      LastError = NtMapViewOfSection(v22, CurrentProcess, &BaseAddress, 0, 0, 0, &ViewSize, ViewShare, 0, 2u);
      if ( LastError >= 0 )
      {
        LastError = ((__int64 (__fastcall *)(_QWORD, PVOID, ULONG_PTR, __int64 *))NTDLL::RtlImageNtHeaderEx)(
                      0,
                      BaseAddress,
                      ViewSize,
                      &v35);
        if ( LastError >= 0 )
        {
          v14 = v35;
          *v37 = *(_WORD *)(v35 + 24) == 523;
          switch ( *(_WORD *)(v14 + 4) )
          {
            case 0x14C:
              LOBYTE(v14) = 5;
              *a3 = g_wArchitecture != 5;
              v28 = 0;
              break;
            case 0x1C0:
            case 0x1C2:
            case 0x1C4:
              LOBYTE(v14) = 5;
              if ( g_wArchitecture != 5 && (!g_fWinNT64 || g_wArchitecture != 12) )
                v17 = 0;
              *a3 = v17;
              *v7 = 5;
              goto LABEL_42;
            case 0x200:
              v28 = 6;
              if ( !g_fWinNT64 || g_wArchitecture != 6 )
                v17 = 0;
              *a3 = v17;
              break;
            default:
              if ( *(unsigned __int16 *)(v14 + 4) == 34404 )
              {
                if ( !g_fWinNT64 || (LOBYTE(v14) = g_wArchitecture, g_wArchitecture != 9) && g_wArchitecture != 12 )
                  v17 = 0;
                *a3 = v17;
                *v7 = 9;
              }
              else if ( *(unsigned __int16 *)(v14 + 4) == 43620 )
              {
                if ( !g_fWinNT64 || g_wArchitecture != 12 )
                  v17 = 0;
                v25 = a5;
                *a3 = v17;
                *v7 = 12;
                v26 = *(__int64 (__fastcall **)(CMsiPath *, __int64, bool *))(*(_QWORD *)this + 464LL);
                v27 = (*(__int64 (__fastcall **)(bool *))(*(_QWORD *)v25 + 80LL))(v25);
                if ( v26(this, v27, v6) )
                  *v6 = 0;
              }
              else
              {
                *a3 = 0;
              }
              goto LABEL_42;
          }
          *v7 = v28;
LABEL_42:
          v15 = 0;
          goto LABEL_45;
        }
      }
    }
    v29 = (const unsigned __int16 *)(*(__int64 (__fastcall **)(bool *))(*(_QWORD *)a5 + 80LL))(a5);
    v15 = PostError(2324, LastError, v29);
  }
LABEL_45:
  v30 = BaseAddress;
  if ( BaseAddress )
  {
    v31 = GetCurrentProcess();
    NtUnmapViewOfSection(v31, v30);
  }
  if ( v11 )
    StopImpersonating(v14);
  CHandle::~CHandle((CHandle *)&SectionHandle);
  CHandle::~CHandle((CHandle *)&hFile);
  (*(void (__fastcall **)(bool *))(*(_QWORD *)a5 + 16LL))(a5);
  return v15;
}

```

## disassembly

```asm
0x180217840  mov     [rsp-38h+arg_8], rbx
0x180217845  mov     [rsp-38h+arg_18], r9
0x18021784a  push    rbp
0x18021784b  push    rsi
0x18021784c  push    rdi
0x18021784d  push    r12
0x18021784f  push    r13
0x180217851  push    r14
0x180217853  push    r15
0x180217855  mov     rbp, rsp
0x180217858  sub     rsp, 80h
0x18021785f  mov     r13, [rbp+arg_20]
0x180217863  or      rax, 0FFFFFFFFFFFFFFFFh
0x180217867  mov     r14, [rbp+hFile]
0x18021786b  mov     r15, rcx
0x18021786e  mov     [rbp+hFile], rax
0x180217872  lea     rcx, ?s_NullString@MsiString@@0VCMsiStringNullCopy@@A; CMsiStringNullCopy MsiString::s_NullString
0x180217879  mov     [rbp+SectionHandle], rax
0x18021787d  mov     rdi, rdx
0x180217880  xor     edx, edx
0x180217882  mov     [rbp+arg_20], rcx
0x180217886  mov     [r9], dl
0x180217889  mov     rsi, r8
0x18021788c  mov     [r13+0], dl
0x180217890  mov     r12b, dl
0x180217893  mov     word ptr [r14], 0FFFFh
0x180217899  mov     rax, [r15]
0x18021789c  mov     [rbp+BaseAddress], rdx
0x1802178a0  mov     [rbp+var_10], rdx
0x1802178a4  mov     [rbp+ViewSize], rdx
0x1802178a8  mov     rbx, [rax+88h]
0x1802178af  mov     rax, qword ptr cs:?s_NullString@MsiString@@0VCMsiStringNullCopy@@A; CMsiStringNullCopy MsiString::s_NullString
0x1802178b6  mov     rax, [rax+10h]
0x1802178ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802178bf  lea     rax, ?s_NullString@MsiString@@0VCMsiStringNullCopy@@A; CMsiStringNullCopy MsiString::s_NullString
0x1802178c6  mov     rdx, rdi
0x1802178c9  mov     [rbp+arg_20], rax
0x1802178cd  lea     r8, [rbp+arg_20]
0x1802178d1  mov     rax, rbx
0x1802178d4  mov     rcx, r15
0x1802178d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802178dc  mov     rbx, rax
0x1802178df  test    rax, rax
0x1802178e2  jnz     loc_180217C1C
0x1802178e8  mov     rax, [r15]
0x1802178eb  mov     rcx, r15
0x1802178ee  mov     rax, [rax+220h]
0x1802178f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802178fa  mov     r12b, al
0x1802178fd  test    al, al
0x1802178ff  jz      short loc_180217906
0x180217901  call    ?StartImpersonating@@YA_NXZ; StartImpersonating(void)
0x180217906  mov     rcx, [rbp+arg_20]
0x18021790a  mov     rdx, [rcx]
0x18021790d  mov     rax, [rdx+50h]
0x180217911  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180217916  xor     r9d, r9d; lpSecurityAttributes
0x180217919  mov     [rsp+80h+hTemplateFile], 0; hTemplateFile
0x180217922  mov     [rsp+80h+dwFlagsAndAttributes], 100000h; dwFlagsAndAttributes
0x18021792a  mov     edx, 80000000h; dwDesiredAccess
0x18021792f  mov     rcx, rax; lpFileName
0x180217932  mov     [rsp+80h+dwCreationDisposition], 3; dwCreationDisposition
0x18021793a  lea     edi, [r9+1]
0x18021793e  mov     r8d, edi; dwShareMode
0x180217941  call    cs:__imp_CreateFileW
0x180217947  mov     rdx, rax
0x18021794a  lea     rcx, [rbp+hFile]
0x18021794e  call    ??4CHandle@@QEAAXPEAX@Z; CHandle::operator=(void *)
0x180217953  mov     rbx, [rbp+hFile]
0x180217957  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x18021795b  jz      loc_180217BF2
0x180217961  mov     rcx, rbx; hFile
0x180217964  call    cs:__imp_GetFileType
0x18021796a  add     eax, 0FFFFFFFEh
0x18021796d  cmp     eax, edi
0x18021796f  ja      short loc_1802179E9
0x180217971  xor     ebx, ebx
0x180217973  cmp     cs:?g_dmDiagnosticMode@@3HA, ebx; int g_dmDiagnosticMode
0x180217979  jz      short loc_1802179CD
0x18021797b  mov     rcx, [rbp+arg_20]
0x18021797f  mov     rax, [rcx]
0x180217982  mov     rax, [rax+50h]
0x180217986  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18021798b  lea     rcx, aNull; "(NULL)"
0x180217992  mov     [rsp+80h+var_28], rbx; void *
0x180217997  mov     [rsp+80h+var_30], ebx; unsigned int
0x18021799b  lea     r9, aErrorThisIsNot; "Error: This is not a valid file, hence "...
0x1802179a2  mov     qword ptr [rsp+80h+AccessProtection], rcx; unsigned __int16 *
0x1802179a7  xor     edx, edx; unsigned __int16
0x1802179a9  mov     qword ptr [rsp+80h+AllocationType], rcx; unsigned __int16 *
0x1802179ae  xor     r8d, r8d; int
0x1802179b1  mov     qword ptr [rsp+80h+InheritDisposition], rcx; unsigned __int16 *
0x1802179b6  mov     [rsp+80h+hTemplateFile], rcx; unsigned __int16 *
0x1802179bb  mov     qword ptr [rsp+80h+dwFlagsAndAttributes], rcx; unsigned __int16 *
0x1802179c0  lea     ecx, [rdi+8]; int
0x1802179c3  mov     qword ptr [rsp+80h+dwCreationDisposition], rax; unsigned __int16 *
0x1802179c8  call    ?DebugString@@YAXHGHPEBG000000KPEAX@Z; DebugString(int,ushort,int,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ulong,void *)
0x1802179cd  or      rdx, 0FFFFFFFFFFFFFFFFh
0x1802179d1  lea     rcx, [rbp+hFile]
0x1802179d5  call    ??4CHandle@@QEAAXPEAX@Z; CHandle::operator=(void *)
0x1802179da  mov     ecx, 6Eh ; 'n'; dwErrCode
0x1802179df  call    cs:__imp_SetLastError
0x1802179e5  mov     rbx, [rbp+hFile]
0x1802179e9  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x1802179ed  jz      loc_180217BF2
0x1802179f3  xor     r9d, r9d; dwMaximumSizeHigh
0x1802179f6  mov     qword ptr [rsp+80h+dwFlagsAndAttributes], 0; lpName
0x1802179ff  xor     edx, edx; lpFileMappingAttributes
0x180217a01  mov     [rsp+80h+dwCreationDisposition], 0; dwMaximumSizeLow
0x180217a09  mov     rcx, rbx; hFile
0x180217a0c  lea     r8d, [r9+2]; flProtect
0x180217a10  call    cs:__imp_CreateFileMappingW
0x180217a16  mov     rdx, rax
0x180217a19  lea     rcx, [rbp+SectionHandle]
0x180217a1d  call    ??4CHandle@@QEAAXPEAX@Z; CHandle::operator=(void *)
0x180217a22  mov     rbx, [rbp+SectionHandle]
0x180217a26  test    rbx, rbx
0x180217a29  jz      loc_180217BF2
0x180217a2f  call    cs:__imp_GetCurrentProcess
0x180217a35  xor     edx, edx
0x180217a37  mov     [rsp+80h+AccessProtection], 2; AccessProtection
0x180217a3f  mov     [rsp+80h+AllocationType], edx; AllocationType
0x180217a43  lea     rcx, [rbp+ViewSize]
0x180217a47  mov     [rsp+80h+InheritDisposition], edi; InheritDisposition
0x180217a4b  lea     r8, [rbp+BaseAddress]; BaseAddress
0x180217a4f  mov     [rsp+80h+hTemplateFile], rcx; ViewSize
0x180217a54  xor     r9d, r9d; ZeroBits
0x180217a57  mov     qword ptr [rsp+80h+dwFlagsAndAttributes], rdx; SectionOffset
0x180217a5c  mov     rcx, rbx; SectionHandle
0x180217a5f  mov     qword ptr [rsp+80h+dwCreationDisposition], rdx; CommitSize
0x180217a64  mov     rdx, rax; ProcessHandle
0x180217a67  call    cs:__imp_NtMapViewOfSection
0x180217a6d  mov     ebx, eax
0x180217a6f  test    eax, eax
0x180217a71  js      loc_180217BFA
0x180217a77  mov     r8, [rbp+ViewSize]
0x180217a7b  lea     r9, [rbp+var_10]
0x180217a7f  mov     rdx, [rbp+BaseAddress]
0x180217a83  xor     ecx, ecx
0x180217a85  mov     rax, cs:?RtlImageNtHeaderEx@NTDLL@@3P6AJKPEAX_KPEAPEAU_IMAGE_NT_HEADERS64@@@ZEA; long (*NTDLL::RtlImageNtHeaderEx)(ulong,void *,unsigned __int64,_IMAGE_NT_HEADERS64 * *)
0x180217a8c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180217a91  mov     ebx, eax
0x180217a93  test    eax, eax
0x180217a95  js      loc_180217BFA
0x180217a9b  mov     rcx, [rbp+var_10]
0x180217a9f  mov     eax, 20Bh
0x180217aa4  mov     rdx, [rbp+arg_18]
0x180217aa8  cmp     [rcx+18h], ax
0x180217aac  setz    al
0x180217aaf  mov     [rdx], al
0x180217ab1  movzx   edx, word ptr [rcx+4]
0x180217ab5  sub     edx, 14Ch
0x180217abb  jz      loc_180217BD7
0x180217ac1  sub     edx, 74h ; 't'
0x180217ac4  jz      loc_180217BA9
0x180217aca  sub     edx, 2
0x180217acd  jz      loc_180217BA9
0x180217ad3  sub     edx, 2
0x180217ad6  jz      loc_180217BA9
0x180217adc  sub     edx, 3Ch ; '<'
0x180217adf  jz      loc_180217B8A
0x180217ae5  sub     edx, 8464h
0x180217aeb  jz      short loc_180217B5C
0x180217aed  cmp     edx, 2400h
0x180217af3  jz      short loc_180217AFD
0x180217af5  mov     byte ptr [rsi], 0
0x180217af8  jmp     loc_180217BEE
0x180217afd  cmp     cs:?g_fWinNT64@@3_NA, 0; bool g_fWinNT64
0x180217b04  mov     eax, 0Ch
0x180217b09  jz      short loc_180217B14
0x180217b0b  cmp     cs:?g_wArchitecture@@3GA, ax; ushort g_wArchitecture
0x180217b12  jz      short loc_180217B17
0x180217b14  xor     dil, dil
0x180217b17  mov     rcx, [rbp+arg_20]
0x180217b1b  mov     [rsi], dil
0x180217b1e  mov     [r14], ax
0x180217b22  mov     rax, [r15]
0x180217b25  mov     rdx, [rcx]
0x180217b28  mov     rbx, [rax+1D0h]
0x180217b2f  mov     rax, [rdx+50h]
0x180217b33  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180217b38  mov     rdx, rax
0x180217b3b  mov     r8, r13
0x180217b3e  mov     rax, rbx
0x180217b41  mov     rcx, r15
0x180217b44  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180217b49  test    rax, rax
0x180217b4c  jz      loc_180217BEE
0x180217b52  mov     byte ptr [r13+0], 0
0x180217b57  jmp     loc_180217BEE
0x180217b5c  cmp     cs:?g_fWinNT64@@3_NA, 0; bool g_fWinNT64
0x180217b63  mov     edx, 9
0x180217b68  jz      short loc_180217B7E
0x180217b6a  movzx   ecx, cs:?g_wArchitecture@@3GA; ushort g_wArchitecture
0x180217b71  cmp     cx, dx
0x180217b74  jz      short loc_180217B81
0x180217b76  lea     eax, [rdx+3]
0x180217b79  cmp     cx, ax
0x180217b7c  jz      short loc_180217B81
0x180217b7e  xor     dil, dil
0x180217b81  mov     [rsi], dil
0x180217b84  mov     [r14], dx
0x180217b88  jmp     short loc_180217BEE
0x180217b8a  cmp     cs:?g_fWinNT64@@3_NA, 0; bool g_fWinNT64
0x180217b91  mov     eax, 6
0x180217b96  jz      short loc_180217BA1
0x180217b98  cmp     cs:?g_wArchitecture@@3GA, ax; ushort g_wArchitecture
0x180217b9f  jz      short loc_180217BA4
0x180217ba1  xor     dil, dil
0x180217ba4  mov     [rsi], dil
0x180217ba7  jmp     short loc_180217BEA
0x180217ba9  movzx   edx, cs:?g_wArchitecture@@3GA; ushort g_wArchitecture
0x180217bb0  mov     ecx, 5
0x180217bb5  cmp     dx, cx
0x180217bb8  jz      short loc_180217BCE
0x180217bba  cmp     cs:?g_fWinNT64@@3_NA, 0; bool g_fWinNT64
0x180217bc1  jz      short loc_180217BCB
0x180217bc3  lea     eax, [rcx+7]
0x180217bc6  cmp     dx, ax
0x180217bc9  jz      short loc_180217BCE
0x180217bcb  xor     dil, dil
0x180217bce  mov     [rsi], dil
0x180217bd1  mov     [r14], cx
0x180217bd5  jmp     short loc_180217BEE
0x180217bd7  mov     ecx, 5
0x180217bdc  cmp     cs:?g_wArchitecture@@3GA, cx; ushort g_wArchitecture
0x180217be3  setnz   al
0x180217be6  mov     [rsi], al
0x180217be8  xor     eax, eax
0x180217bea  mov     [r14], ax
0x180217bee  xor     ebx, ebx
0x180217bf0  jmp     short loc_180217C1C
0x180217bf2  call    cs:__imp_GetLastError
0x180217bf8  mov     ebx, eax
0x180217bfa  mov     rcx, [rbp+arg_20]
0x180217bfe  mov     rdx, [rcx]
0x180217c01  mov     rax, [rdx+50h]
0x180217c05  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180217c0a  mov     r8, rax; unsigned __int16 *
0x180217c0d  mov     edx, ebx; int
0x180217c0f  mov     ecx, 914h; int
0x180217c14  call    ?PostError@@YAPEAVIMsiRecord@@HHPEBG@Z; PostError(int,int,ushort const *)
0x180217c19  mov     rbx, rax
0x180217c1c  mov     rdi, [rbp+BaseAddress]
0x180217c20  test    rdi, rdi
0x180217c23  jz      short loc_180217C37
0x180217c25  call    cs:__imp_GetCurrentProcess
0x180217c2b  mov     rcx, rax; ProcessHandle
0x180217c2e  mov     rdx, rdi; BaseAddress
0x180217c31  call    cs:__imp_NtUnmapViewOfSection
0x180217c37  test    r12b, r12b
0x180217c3a  jz      short loc_180217C41
0x180217c3c  call    ?StopImpersonating@@YAX_N@Z; StopImpersonating(bool)
0x180217c41  lea     rcx, [rbp+SectionHandle]; this
0x180217c45  call    ??1CHandle@@QEAA@XZ; CHandle::~CHandle(void)
0x180217c4a  lea     rcx, [rbp+hFile]; this
0x180217c4e  call    ??1CHandle@@QEAA@XZ; CHandle::~CHandle(void)
0x180217c53  mov     rcx, [rbp+arg_20]
0x180217c57  mov     rax, [rcx]
0x180217c5a  mov     rax, [rax+10h]
0x180217c5e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180217c63  mov     rax, rbx
0x180217c66  mov     rbx, [rsp+80h+arg_8]
0x180217c6e  add     rsp, 80h
0x180217c75  pop     r15
0x180217c77  pop     r14
0x180217c79  pop     r13
0x180217c7b  pop     r12
0x180217c7d  pop     rdi
0x180217c7e  pop     rsi
0x180217c7f  pop     rbp
0x180217c80  retn
```
