# CMsiPath::ReadPEPlatform(ushort const *,bool &,bool &,bool &,ushort &)

- ea: `0x180221390`
- end: `0x180221808`
- name: `?ReadPEPlatform@CMsiPath@@UEAAPEAVIMsiRecord@@PEBGAEA_N11AEAG@Z`
- size: `1144`
- prototype: `struct IMsiRecord *__fastcall(CMsiPath *__hidden this, const unsigned __int16 *, bool *, bool *, bool *, HANDLE hFile)`
- caller_count: `0`
- callee_count: `8`
- tags: `file_ops, loader_planting, service_task, installer_update`

## callees

- `0x18000c4bc`
- `0x18009cdb8`
- `0x18009d06c`
- `0x18013d2f0`
- `0x18014ae8c`
- `0x180153e68`
- `0x180221390`
- `0x180266010`

## import_xrefs

- `ntdll!NtMapViewOfSection` at `0x1802215d5`
- `ntdll!NtMapViewOfSection` at `0x1802215d5`
- `ntdll!NtUnmapViewOfSection` at `0x1802217b1`
- `ntdll!NtUnmapViewOfSection` at `0x1802217b1`
- `KERNEL32!CreateFileMappingW` at `0x180221572`
- `KERNEL32!CreateFileMappingW` at `0x180221572`
- `KERNEL32!GetLastError` at `0x180221766`
- `KERNEL32!GetLastError` at `0x180221766`
- `KERNEL32!SetLastError` at `0x18022153b`
- `KERNEL32!SetLastError` at `0x18022153b`
- `KERNEL32!GetCurrentProcess` at `0x180221597`
- `KERNEL32!GetCurrentProcess` at `0x18022179f`
- `KERNEL32!GetCurrentProcess` at `0x180221597`
- `KERNEL32!GetCurrentProcess` at `0x18022179f`
- `KERNEL32!CreateFileW` at `0x180221491`
- `KERNEL32!CreateFileW` at `0x180221491`
- `KERNEL32!GetFileType` at `0x1802214ba`
- `KERNEL32!GetFileType` at `0x1802214ba`

## string_xrefs

- `0x1802214f7`: `Error: This is not a valid file, hence failing to create: %s`

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
0x180221390  mov     [rsp-38h+arg_8], rbx
0x180221395  mov     [rsp-38h+arg_18], r9
0x18022139a  push    rbp
0x18022139b  push    rsi
0x18022139c  push    rdi
0x18022139d  push    r12
0x18022139f  push    r13
0x1802213a1  push    r14
0x1802213a3  push    r15
0x1802213a5  mov     rbp, rsp
0x1802213a8  sub     rsp, 80h
0x1802213af  mov     r13, [rbp+arg_20]
0x1802213b3  or      rax, 0FFFFFFFFFFFFFFFFh
0x1802213b7  mov     r14, [rbp+hFile]
0x1802213bb  mov     r15, rcx
0x1802213be  mov     [rbp+hFile], rax
0x1802213c2  lea     rcx, ?s_NullString@MsiString@@0VCMsiStringNullCopy@@A; CMsiStringNullCopy MsiString::s_NullString
0x1802213c9  mov     [rbp+SectionHandle], rax
0x1802213cd  mov     rdi, rdx
0x1802213d0  xor     edx, edx
0x1802213d2  mov     [rbp+arg_20], rcx
0x1802213d6  mov     [r9], dl
0x1802213d9  mov     rsi, r8
0x1802213dc  mov     [r13+0], dl
0x1802213e0  mov     r12b, dl
0x1802213e3  mov     word ptr [r14], 0FFFFh
0x1802213e9  mov     rax, [r15]
0x1802213ec  mov     [rbp+BaseAddress], rdx
0x1802213f0  mov     [rbp+var_10], rdx
0x1802213f4  mov     [rbp+ViewSize], rdx
0x1802213f8  mov     rbx, [rax+88h]
0x1802213ff  mov     rax, qword ptr cs:?s_NullString@MsiString@@0VCMsiStringNullCopy@@A; CMsiStringNullCopy MsiString::s_NullString
0x180221406  mov     rax, [rax+10h]
0x18022140a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18022140f  lea     rax, ?s_NullString@MsiString@@0VCMsiStringNullCopy@@A; CMsiStringNullCopy MsiString::s_NullString
0x180221416  mov     rdx, rdi
0x180221419  mov     [rbp+arg_20], rax
0x18022141d  lea     r8, [rbp+arg_20]
0x180221421  mov     rax, rbx
0x180221424  mov     rcx, r15
0x180221427  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18022142c  mov     rbx, rax
0x18022142f  test    rax, rax
0x180221432  jnz     loc_180221796
0x180221438  mov     rax, [r15]
0x18022143b  mov     rcx, r15
0x18022143e  mov     rax, [rax+220h]
0x180221445  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18022144a  mov     r12b, al
0x18022144d  test    al, al
0x18022144f  jz      short loc_180221456
0x180221451  call    ?StartImpersonating@@YA_NXZ; StartImpersonating(void)
0x180221456  mov     rcx, [rbp+arg_20]
0x18022145a  mov     rdx, [rcx]
0x18022145d  mov     rax, [rdx+50h]
0x180221461  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180221466  xor     r9d, r9d; lpSecurityAttributes
0x180221469  mov     [rsp+80h+hTemplateFile], 0; hTemplateFile
0x180221472  mov     [rsp+80h+dwFlagsAndAttributes], 100000h; dwFlagsAndAttributes
0x18022147a  mov     edx, 80000000h; dwDesiredAccess
0x18022147f  mov     rcx, rax; lpFileName
0x180221482  mov     [rsp+80h+dwCreationDisposition], 3; dwCreationDisposition
0x18022148a  lea     edi, [r9+1]
0x18022148e  mov     r8d, edi; dwShareMode
0x180221491  call    cs:__imp_CreateFileW
0x180221498  nop     dword ptr [rax+rax+00h]
0x18022149d  mov     rdx, rax
0x1802214a0  lea     rcx, [rbp+hFile]
0x1802214a4  call    ??4CHandle@@QEAAXPEAX@Z; CHandle::operator=(void *)
0x1802214a9  mov     rbx, [rbp+hFile]
0x1802214ad  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x1802214b1  jz      loc_180221766
0x1802214b7  mov     rcx, rbx; hFile
0x1802214ba  call    cs:__imp_GetFileType
0x1802214c1  nop     dword ptr [rax+rax+00h]
0x1802214c6  add     eax, 0FFFFFFFEh
0x1802214c9  cmp     eax, edi
0x1802214cb  ja      short loc_18022154B
0x1802214cd  xor     ebx, ebx
0x1802214cf  cmp     cs:?g_dmDiagnosticMode@@3HA, ebx; int g_dmDiagnosticMode
0x1802214d5  jz      short loc_180221529
0x1802214d7  mov     rcx, [rbp+arg_20]
0x1802214db  mov     rax, [rcx]
0x1802214de  mov     rax, [rax+50h]
0x1802214e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802214e7  lea     rcx, aNull; "(NULL)"
0x1802214ee  mov     [rsp+80h+var_28], rbx; void *
0x1802214f3  mov     [rsp+80h+var_30], ebx; unsigned int
0x1802214f7  lea     r9, aErrorThisIsNot; "Error: This is not a valid file, hence "...
0x1802214fe  mov     qword ptr [rsp+80h+AccessProtection], rcx; unsigned __int16 *
0x180221503  xor     edx, edx; unsigned __int16
0x180221505  mov     qword ptr [rsp+80h+AllocationType], rcx; unsigned __int16 *
0x18022150a  xor     r8d, r8d; int
0x18022150d  mov     qword ptr [rsp+80h+InheritDisposition], rcx; unsigned __int16 *
0x180221512  mov     [rsp+80h+hTemplateFile], rcx; unsigned __int16 *
0x180221517  mov     qword ptr [rsp+80h+dwFlagsAndAttributes], rcx; unsigned __int16 *
0x18022151c  lea     ecx, [rdi+8]; int
0x18022151f  mov     qword ptr [rsp+80h+dwCreationDisposition], rax; unsigned __int16 *
0x180221524  call    ?DebugString@@YAXHGHPEBG000000KPEAX@Z; DebugString(int,ushort,int,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ulong,void *)
0x180221529  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18022152d  lea     rcx, [rbp+hFile]
0x180221531  call    ??4CHandle@@QEAAXPEAX@Z; CHandle::operator=(void *)
0x180221536  mov     ecx, 6Eh ; 'n'; dwErrCode
0x18022153b  call    cs:__imp_SetLastError
0x180221542  nop     dword ptr [rax+rax+00h]
0x180221547  mov     rbx, [rbp+hFile]
0x18022154b  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x18022154f  jz      loc_180221766
0x180221555  xor     r9d, r9d; dwMaximumSizeHigh
0x180221558  mov     qword ptr [rsp+80h+dwFlagsAndAttributes], 0; lpName
0x180221561  xor     edx, edx; lpFileMappingAttributes
0x180221563  mov     [rsp+80h+dwCreationDisposition], 0; dwMaximumSizeLow
0x18022156b  mov     rcx, rbx; hFile
0x18022156e  lea     r8d, [r9+2]; flProtect
0x180221572  call    cs:__imp_CreateFileMappingW
0x180221579  nop     dword ptr [rax+rax+00h]
0x18022157e  mov     rdx, rax
0x180221581  lea     rcx, [rbp+SectionHandle]
0x180221585  call    ??4CHandle@@QEAAXPEAX@Z; CHandle::operator=(void *)
0x18022158a  mov     rbx, [rbp+SectionHandle]
0x18022158e  test    rbx, rbx
0x180221591  jz      loc_180221766
0x180221597  call    cs:__imp_GetCurrentProcess
0x18022159e  nop     dword ptr [rax+rax+00h]
0x1802215a3  xor     edx, edx
0x1802215a5  mov     [rsp+80h+AccessProtection], 2; AccessProtection
0x1802215ad  mov     [rsp+80h+AllocationType], edx; AllocationType
0x1802215b1  lea     rcx, [rbp+ViewSize]
0x1802215b5  mov     [rsp+80h+InheritDisposition], edi; InheritDisposition
0x1802215b9  lea     r8, [rbp+BaseAddress]; BaseAddress
0x1802215bd  mov     [rsp+80h+hTemplateFile], rcx; ViewSize
0x1802215c2  xor     r9d, r9d; ZeroBits
0x1802215c5  mov     qword ptr [rsp+80h+dwFlagsAndAttributes], rdx; SectionOffset
0x1802215ca  mov     rcx, rbx; SectionHandle
0x1802215cd  mov     qword ptr [rsp+80h+dwCreationDisposition], rdx; CommitSize
0x1802215d2  mov     rdx, rax; ProcessHandle
0x1802215d5  call    cs:__imp_NtMapViewOfSection
0x1802215dc  nop     dword ptr [rax+rax+00h]
0x1802215e1  mov     ebx, eax
0x1802215e3  test    eax, eax
0x1802215e5  js      loc_180221774
0x1802215eb  mov     r8, [rbp+ViewSize]
0x1802215ef  lea     r9, [rbp+var_10]
0x1802215f3  mov     rdx, [rbp+BaseAddress]
0x1802215f7  xor     ecx, ecx
0x1802215f9  mov     rax, cs:?RtlImageNtHeaderEx@NTDLL@@3P6AJKPEAX_KPEAPEAU_IMAGE_NT_HEADERS64@@@ZEA; long (*NTDLL::RtlImageNtHeaderEx)(ulong,void *,unsigned __int64,_IMAGE_NT_HEADERS64 * *)
0x180221600  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180221605  mov     ebx, eax
0x180221607  test    eax, eax
0x180221609  js      loc_180221774
0x18022160f  mov     rcx, [rbp+var_10]
0x180221613  mov     eax, 20Bh
0x180221618  mov     rdx, [rbp+arg_18]
0x18022161c  cmp     [rcx+18h], ax
0x180221620  setz    al
0x180221623  mov     [rdx], al
0x180221625  movzx   edx, word ptr [rcx+4]
0x180221629  sub     edx, 14Ch
0x18022162f  jz      loc_18022174B
0x180221635  sub     edx, 74h ; 't'
0x180221638  jz      loc_18022171D
0x18022163e  sub     edx, 2
0x180221641  jz      loc_18022171D
0x180221647  sub     edx, 2
0x18022164a  jz      loc_18022171D
0x180221650  sub     edx, 3Ch ; '<'
0x180221653  jz      loc_1802216FE
0x180221659  sub     edx, 8464h
0x18022165f  jz      short loc_1802216D0
0x180221661  cmp     edx, 2400h
0x180221667  jz      short loc_180221671
0x180221669  mov     byte ptr [rsi], 0
0x18022166c  jmp     loc_180221762
0x180221671  cmp     cs:?g_fWinNT64@@3_NA, 0; bool g_fWinNT64
0x180221678  mov     eax, 0Ch
0x18022167d  jz      short loc_180221688
0x18022167f  cmp     cs:?g_wArchitecture@@3GA, ax; ushort g_wArchitecture
0x180221686  jz      short loc_18022168B
0x180221688  xor     dil, dil
0x18022168b  mov     rcx, [rbp+arg_20]
0x18022168f  mov     [rsi], dil
0x180221692  mov     [r14], ax
0x180221696  mov     rax, [r15]
0x180221699  mov     rdx, [rcx]
0x18022169c  mov     rbx, [rax+1D0h]
0x1802216a3  mov     rax, [rdx+50h]
0x1802216a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802216ac  mov     rdx, rax
0x1802216af  mov     r8, r13
0x1802216b2  mov     rax, rbx
0x1802216b5  mov     rcx, r15
0x1802216b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802216bd  test    rax, rax
0x1802216c0  jz      loc_180221762
0x1802216c6  mov     byte ptr [r13+0], 0
0x1802216cb  jmp     loc_180221762
0x1802216d0  cmp     cs:?g_fWinNT64@@3_NA, 0; bool g_fWinNT64
0x1802216d7  mov     edx, 9
0x1802216dc  jz      short loc_1802216F2
0x1802216de  movzx   ecx, cs:?g_wArchitecture@@3GA; ushort g_wArchitecture
0x1802216e5  cmp     cx, dx
0x1802216e8  jz      short loc_1802216F5
0x1802216ea  lea     eax, [rdx+3]
0x1802216ed  cmp     cx, ax
0x1802216f0  jz      short loc_1802216F5
0x1802216f2  xor     dil, dil
0x1802216f5  mov     [rsi], dil
0x1802216f8  mov     [r14], dx
0x1802216fc  jmp     short loc_180221762
0x1802216fe  cmp     cs:?g_fWinNT64@@3_NA, 0; bool g_fWinNT64
0x180221705  mov     eax, 6
0x18022170a  jz      short loc_180221715
0x18022170c  cmp     cs:?g_wArchitecture@@3GA, ax; ushort g_wArchitecture
0x180221713  jz      short loc_180221718
0x180221715  xor     dil, dil
0x180221718  mov     [rsi], dil
0x18022171b  jmp     short loc_18022175E
0x18022171d  movzx   edx, cs:?g_wArchitecture@@3GA; ushort g_wArchitecture
0x180221724  mov     ecx, 5
0x180221729  cmp     dx, cx
0x18022172c  jz      short loc_180221742
0x18022172e  cmp     cs:?g_fWinNT64@@3_NA, 0; bool g_fWinNT64
0x180221735  jz      short loc_18022173F
0x180221737  lea     eax, [rcx+7]
0x18022173a  cmp     dx, ax
0x18022173d  jz      short loc_180221742
0x18022173f  xor     dil, dil
0x180221742  mov     [rsi], dil
0x180221745  mov     [r14], cx
0x180221749  jmp     short loc_180221762
0x18022174b  mov     ecx, 5
0x180221750  cmp     cs:?g_wArchitecture@@3GA, cx; ushort g_wArchitecture
0x180221757  setnz   al
0x18022175a  mov     [rsi], al
0x18022175c  xor     eax, eax
0x18022175e  mov     [r14], ax
0x180221762  xor     ebx, ebx
0x180221764  jmp     short loc_180221796
0x180221766  call    cs:__imp_GetLastError
0x18022176d  nop     dword ptr [rax+rax+00h]
0x180221772  mov     ebx, eax
0x180221774  mov     rcx, [rbp+arg_20]
0x180221778  mov     rdx, [rcx]
0x18022177b  mov     rax, [rdx+50h]
0x18022177f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180221784  mov     r8, rax; unsigned __int16 *
0x180221787  mov     edx, ebx; int
0x180221789  mov     ecx, 914h; int
0x18022178e  call    ?PostError@@YAPEAVIMsiRecord@@HHPEBG@Z; PostError(int,int,ushort const *)
0x180221793  mov     rbx, rax
0x180221796  mov     rdi, [rbp+BaseAddress]
0x18022179a  test    rdi, rdi
0x18022179d  jz      short loc_1802217BD
0x18022179f  call    cs:__imp_GetCurrentProcess
0x1802217a6  nop     dword ptr [rax+rax+00h]
0x1802217ab  mov     rcx, rax; ProcessHandle
0x1802217ae  mov     rdx, rdi; BaseAddress
0x1802217b1  call    cs:__imp_NtUnmapViewOfSection
0x1802217b8  nop     dword ptr [rax+rax+00h]
0x1802217bd  test    r12b, r12b
0x1802217c0  jz      short loc_1802217C7
0x1802217c2  call    ?StopImpersonating@@YAX_N@Z; StopImpersonating(bool)
0x1802217c7  lea     rcx, [rbp+SectionHandle]; this
0x1802217cb  call    ??1CHandle@@QEAA@XZ; CHandle::~CHandle(void)
0x1802217d0  lea     rcx, [rbp+hFile]; this
0x1802217d4  call    ??1CHandle@@QEAA@XZ; CHandle::~CHandle(void)
0x1802217d9  mov     rcx, [rbp+arg_20]
0x1802217dd  mov     rax, [rcx]
0x1802217e0  mov     rax, [rax+10h]
0x1802217e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802217e9  mov     rax, rbx
0x1802217ec  mov     rbx, [rsp+80h+arg_8]
0x1802217f4  add     rsp, 80h
0x1802217fb  pop     r15
0x1802217fd  pop     r14
0x1802217ff  pop     r13
0x180221801  pop     r12
0x180221803  pop     rdi
0x180221804  pop     rsi
0x180221805  pop     rbp
0x180221806  retn
```
