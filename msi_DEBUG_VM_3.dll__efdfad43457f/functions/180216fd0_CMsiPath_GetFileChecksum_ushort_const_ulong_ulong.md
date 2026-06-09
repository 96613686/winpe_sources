# CMsiPath::GetFileChecksum(ushort const *,ulong *,ulong *)

- ea: `0x180216fd0`
- end: `0x180217289`
- name: `?GetFileChecksum@CMsiPath@@UEAAPEAVIMsiRecord@@PEBGPEAK1@Z`
- size: `697`
- prototype: `struct IMsiRecord *(CMsiPath *__hidden this, const unsigned __int16 *, unsigned int *, unsigned int *)`
- caller_count: `0`
- callee_count: `9`
- tags: `file_ops, installer_update`

## callees

- `0x180025a18`
- `0x180083178`
- `0x1800833ec`
- `0x1801382a0`
- `0x180146548`
- `0x18014e4d4`
- `0x180216e24`
- `0x180216fd0`
- `0x18025c010`

## import_xrefs

- `KERNEL32!CreateFileMappingW` at `0x18021719a`
- `KERNEL32!CreateFileMappingW` at `0x18021719a`
- `KERNEL32!MapViewOfFile` at `0x1802171f2`
- `KERNEL32!MapViewOfFile` at `0x1802171f2`
- `KERNEL32!UnmapViewOfFile` at `0x18021723b`
- `KERNEL32!UnmapViewOfFile` at `0x18021723b`
- `KERNEL32!GetLastError` at `0x180217167`
- `KERNEL32!GetLastError` at `0x1802171c6`
- `KERNEL32!GetLastError` at `0x180217167`
- `KERNEL32!GetLastError` at `0x1802171c6`
- `KERNEL32!SetLastError` at `0x18021713b`
- `KERNEL32!SetLastError` at `0x18021713b`
- `KERNEL32!CreateFileW` at `0x1802170a3`
- `KERNEL32!CreateFileW` at `0x1802170a3`
- `KERNEL32!GetFileType` at `0x1802170c0`
- `KERNEL32!GetFileType` at `0x1802170c0`
- `KERNEL32!GetFileSize` at `0x180217205`
- `KERNEL32!GetFileSize` at `0x180217205`

## string_xrefs

- `0x1802170f8`: `Error: This is not a valid file, hence failing to create: %s`

## pseudocode

```c
struct IMsiRecord *__fastcall CMsiPath::GetFileChecksum(
        CMsiPath *this,
        const unsigned __int16 *a2,
        unsigned int *a3,
        unsigned int *a4)
{
  __int64 v8; // rax
  __int64 (__fastcall *v9)(CMsiPath *, const unsigned __int16 *, void **); // rbx
  struct IMsiRecord *Checksums; // rbx
  char v11; // di
  const WCHAR *v12; // rax
  HANDLE FileW; // rax
  bool v14; // cl
  void *v15; // rbx
  const unsigned __int16 *v16; // rax
  const unsigned __int16 *v17; // rbx
  DWORD LastError; // eax
  HANDLE FileMappingW; // rax
  bool v20; // cl
  const unsigned __int16 *v21; // rbx
  DWORD v22; // eax
  void *v23; // rsi
  DWORD FileSize; // ebx
  const unsigned __int16 *v25; // rax
  CMsiPath *v26; // rcx
  bool v27; // cl
  HANDLE v29; // [rsp+60h] [rbp-10h] BYREF
  HANDLE v30; // [rsp+68h] [rbp-8h] BYREF
  void *v31; // [rsp+A0h] [rbp+30h] BYREF

  (*(void (__fastcall **)(CMsiPath *))(*(_QWORD *)this + 576LL))(this);
  v8 = *(_QWORD *)this;
  v31 = &MsiString::s_NullString;
  v9 = *(__int64 (__fastcall **)(CMsiPath *, const unsigned __int16 *, void **))(v8 + 136);
  (*(void (__fastcall **)(void *))(MsiString::s_NullString + 16LL))(&MsiString::s_NullString);
  v31 = &MsiString::s_NullString;
  Checksums = (struct IMsiRecord *)v9(this, a2, &v31);
  if ( !Checksums )
  {
    v11 = (*(__int64 (__fastcall **)(CMsiPath *))(*(_QWORD *)this + 544LL))(this);
    if ( v11 )
      StartImpersonating();
    v12 = (const WCHAR *)(*(__int64 (__fastcall **)(void *))(*(_QWORD *)v31 + 80LL))(v31);
    FileW = CreateFileW(v12, 0x80000000, 1u, 0, 3u, 0x100000u, 0);
    v29 = FileW;
    v15 = FileW;
    if ( FileW != (HANDLE)-1LL && GetFileType(FileW) - 2 <= 1 )
    {
      if ( g_dmDiagnosticMode )
      {
        v16 = (const unsigned __int16 *)(*(__int64 (__fastcall **)(void *))(*(_QWORD *)v31 + 80LL))(v31);
        DebugString(
          9,
          0,
          0,
          L"Error: This is not a valid file, hence failing to create: %s",
          v16,
          L"(NULL)",
          L"(NULL)",
          L"(NULL)",
          L"(NULL)",
          L"(NULL)",
          0,
          0);
      }
      CHandle::operator=(&v29, -1);
      SetLastError(0x6Eu);
      v15 = v29;
    }
    if ( v15 == (void *)-1LL )
    {
      if ( v11 )
        StopImpersonating(v14);
      v17 = (const unsigned __int16 *)(*(__int64 (__fastcall **)(void *))(*(_QWORD *)v31 + 80LL))(v31);
      LastError = GetLastError();
      Checksums = PostError(2324, LastError, v17);
    }
    else
    {
      FileMappingW = CreateFileMappingW(v15, 0, 2u, 0, 0, 0);
      v30 = FileMappingW;
      if ( FileMappingW == (HANDLE)-1LL || (v23 = MapViewOfFile(FileMappingW, 4u, 0, 0, 0)) == 0 )
      {
        if ( v11 )
          StopImpersonating(v20);
        v21 = (const unsigned __int16 *)(*(__int64 (__fastcall **)(void *))(*(_QWORD *)v31 + 80LL))(v31);
        v22 = GetLastError();
        Checksums = PostError(2324, v22, v21);
      }
      else
      {
        FileSize = GetFileSize(v15, 0);
        v25 = (const unsigned __int16 *)(*(__int64 (__fastcall **)(void *))(*(_QWORD *)v31 + 80LL))(v31);
        Checksums = CMsiPath::GetChecksums(v26, v25, v23, FileSize, a3, a4);
        UnmapViewOfFile(v23);
        if ( v11 )
          StopImpersonating(v27);
      }
      CHandle::~CHandle((CHandle *)&v30);
    }
    CHandle::~CHandle((CHandle *)&v29);
  }
  (*(void (__fastcall **)(void *))(*(_QWORD *)v31 + 16LL))(v31);
  return Checksums;
}

```

## disassembly

```asm
0x180216fd0  mov     [rsp-28h+arg_8], rbx
0x180216fd5  mov     [rsp-28h+arg_10], rsi
0x180216fda  push    rbp
0x180216fdb  push    rdi
0x180216fdc  push    r12
0x180216fde  push    r14
0x180216fe0  push    r15
0x180216fe2  mov     rbp, rsp
0x180216fe5  sub     rsp, 70h
0x180216fe9  mov     rax, [rcx]
0x180216fec  mov     r14, r9
0x180216fef  mov     r15, r8
0x180216ff2  mov     rdi, rdx
0x180216ff5  mov     rsi, rcx
0x180216ff8  mov     rax, [rax+240h]
0x180216fff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180217004  mov     rax, [rsi]
0x180217007  lea     r12, ?s_NullString@MsiString@@0VCMsiStringNullCopy@@A; CMsiStringNullCopy MsiString::s_NullString
0x18021700e  mov     r8, qword ptr cs:?s_NullString@MsiString@@0VCMsiStringNullCopy@@A; CMsiStringNullCopy MsiString::s_NullString
0x180217015  mov     rcx, r12
0x180217018  mov     [rbp+arg_0], r12
0x18021701c  mov     rbx, [rax+88h]
0x180217023  mov     rax, [r8+10h]
0x180217027  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18021702c  lea     r8, [rbp+arg_0]
0x180217030  mov     [rbp+arg_0], r12
0x180217034  mov     rdx, rdi
0x180217037  mov     rcx, rsi
0x18021703a  mov     rax, rbx
0x18021703d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180217042  xor     r12d, r12d
0x180217045  mov     rbx, rax
0x180217048  test    rax, rax
0x18021704b  jnz     loc_18021725D
0x180217051  mov     rax, [rsi]
0x180217054  mov     rcx, rsi
0x180217057  mov     rax, [rax+220h]
0x18021705e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180217063  mov     dil, al
0x180217066  test    al, al
0x180217068  jz      short loc_18021706F
0x18021706a  call    ?StartImpersonating@@YA_NXZ; StartImpersonating(void)
0x18021706f  mov     rcx, [rbp+arg_0]
0x180217073  mov     rdx, [rcx]
0x180217076  mov     rax, [rdx+50h]
0x18021707a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18021707f  xor     r9d, r9d; lpSecurityAttributes
0x180217082  mov     [rsp+70h+hTemplateFile], r12; hTemplateFile
0x180217087  mov     [rsp+70h+dwFlagsAndAttributes], 100000h; dwFlagsAndAttributes
0x18021708f  mov     edx, 80000000h; dwDesiredAccess
0x180217094  mov     rcx, rax; lpFileName
0x180217097  mov     [rsp+70h+dwCreationDisposition], 3; dwCreationDisposition
0x18021709f  lea     r8d, [r9+1]; dwShareMode
0x1802170a3  call    cs:__imp_CreateFileW
0x1802170a9  or      rsi, 0FFFFFFFFFFFFFFFFh
0x1802170ad  mov     [rbp+var_10], rax
0x1802170b1  mov     rbx, rax
0x1802170b4  cmp     rax, rsi
0x1802170b7  jz      loc_180217145
0x1802170bd  mov     rcx, rax; hFile
0x1802170c0  call    cs:__imp_GetFileType
0x1802170c6  add     eax, 0FFFFFFFEh
0x1802170c9  cmp     eax, 1
0x1802170cc  ja      short loc_180217145
0x1802170ce  cmp     cs:?g_dmDiagnosticMode@@3HA, r12d; int g_dmDiagnosticMode
0x1802170d5  jz      short loc_18021712A
0x1802170d7  mov     rcx, [rbp+arg_0]
0x1802170db  mov     rax, [rcx]
0x1802170de  mov     rax, [rax+50h]
0x1802170e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802170e7  lea     rcx, aNull; "(NULL)"
0x1802170ee  mov     [rsp+70h+var_18], r12; void *
0x1802170f3  mov     [rsp+70h+var_20], r12d; unsigned int
0x1802170f8  lea     r9, aErrorThisIsNot; "Error: This is not a valid file, hence "...
0x1802170ff  mov     [rsp+70h+var_28], rcx; unsigned __int16 *
0x180217104  xor     edx, edx; unsigned __int16
0x180217106  mov     [rsp+70h+var_30], rcx; unsigned __int16 *
0x18021710b  xor     r8d, r8d; int
0x18021710e  mov     [rsp+70h+var_38], rcx; unsigned __int16 *
0x180217113  mov     [rsp+70h+hTemplateFile], rcx; unsigned __int16 *
0x180217118  mov     qword ptr [rsp+70h+dwFlagsAndAttributes], rcx; unsigned __int16 *
0x18021711d  lea     ecx, [rsi+0Ah]; int
0x180217120  mov     qword ptr [rsp+70h+dwCreationDisposition], rax; unsigned __int16 *
0x180217125  call    ?DebugString@@YAXHGHPEBG000000KPEAX@Z; DebugString(int,ushort,int,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ulong,void *)
0x18021712a  mov     rdx, rsi
0x18021712d  lea     rcx, [rbp+var_10]
0x180217131  call    ??4CHandle@@QEAAXPEAX@Z; CHandle::operator=(void *)
0x180217136  mov     ecx, 6Eh ; 'n'; dwErrCode
0x18021713b  call    cs:__imp_SetLastError
0x180217141  mov     rbx, [rbp+var_10]
0x180217145  cmp     rbx, rsi
0x180217148  jnz     short loc_180217184
0x18021714a  test    dil, dil
0x18021714d  jz      short loc_180217154
0x18021714f  call    ?StopImpersonating@@YAX_N@Z; StopImpersonating(bool)
0x180217154  mov     rcx, [rbp+arg_0]
0x180217158  mov     rax, [rcx]
0x18021715b  mov     rax, [rax+50h]
0x18021715f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180217164  mov     rbx, rax
0x180217167  call    cs:__imp_GetLastError
0x18021716d  mov     r8, rbx; unsigned __int16 *
0x180217170  mov     ecx, 914h; int
0x180217175  mov     edx, eax; int
0x180217177  call    ?PostError@@YAPEAVIMsiRecord@@HHPEBG@Z; PostError(int,int,ushort const *)
0x18021717c  mov     rbx, rax
0x18021717f  jmp     loc_180217254
0x180217184  xor     r9d, r9d; dwMaximumSizeHigh
0x180217187  mov     qword ptr [rsp+70h+dwFlagsAndAttributes], r12; lpName
0x18021718c  xor     edx, edx; lpFileMappingAttributes
0x18021718e  mov     [rsp+70h+dwCreationDisposition], r12d; dwMaximumSizeLow
0x180217193  mov     rcx, rbx; hFile
0x180217196  lea     r8d, [r9+2]; flProtect
0x18021719a  call    cs:__imp_CreateFileMappingW
0x1802171a0  mov     [rbp+var_8], rax
0x1802171a4  cmp     rax, rsi
0x1802171a7  jnz     short loc_1802171E0
0x1802171a9  test    dil, dil
0x1802171ac  jz      short loc_1802171B3
0x1802171ae  call    ?StopImpersonating@@YAX_N@Z; StopImpersonating(bool)
0x1802171b3  mov     rcx, [rbp+arg_0]
0x1802171b7  mov     rax, [rcx]
0x1802171ba  mov     rax, [rax+50h]
0x1802171be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802171c3  mov     rbx, rax
0x1802171c6  call    cs:__imp_GetLastError
0x1802171cc  mov     r8, rbx; unsigned __int16 *
0x1802171cf  mov     ecx, 914h; int
0x1802171d4  mov     edx, eax; int
0x1802171d6  call    ?PostError@@YAPEAVIMsiRecord@@HHPEBG@Z; PostError(int,int,ushort const *)
0x1802171db  mov     rbx, rax
0x1802171de  jmp     short loc_18021724B
0x1802171e0  xor     r9d, r9d; dwFileOffsetLow
0x1802171e3  mov     qword ptr [rsp+70h+dwCreationDisposition], r12; dwNumberOfBytesToMap
0x1802171e8  xor     r8d, r8d; dwFileOffsetHigh
0x1802171eb  mov     rcx, rax; hFileMappingObject
0x1802171ee  lea     edx, [r9+4]; dwDesiredAccess
0x1802171f2  call    cs:__imp_MapViewOfFile
0x1802171f8  mov     rsi, rax
0x1802171fb  test    rax, rax
0x1802171fe  jz      short loc_1802171A9
0x180217200  xor     edx, edx; lpFileSizeHigh
0x180217202  mov     rcx, rbx; hFile
0x180217205  call    cs:__imp_GetFileSize
0x18021720b  mov     rcx, [rbp+arg_0]
0x18021720f  mov     ebx, eax
0x180217211  mov     rdx, [rcx]
0x180217214  mov     rax, [rdx+50h]
0x180217218  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18021721d  mov     r9d, ebx; int
0x180217220  mov     qword ptr [rsp+70h+dwFlagsAndAttributes], r14; unsigned int *
0x180217225  mov     r8, rsi; void *
0x180217228  mov     qword ptr [rsp+70h+dwCreationDisposition], r15; unsigned int *
0x18021722d  mov     rdx, rax; unsigned __int16 *
0x180217230  call    ?GetChecksums@CMsiPath@@IEAAPEAVIMsiRecord@@PEBGPEAXHPEAK2@Z; CMsiPath::GetChecksums(ushort const *,void *,int,ulong *,ulong *)
0x180217235  mov     rcx, rsi; lpBaseAddress
0x180217238  mov     rbx, rax
0x18021723b  call    cs:__imp_UnmapViewOfFile
0x180217241  test    dil, dil
0x180217244  jz      short loc_18021724B
0x180217246  call    ?StopImpersonating@@YAX_N@Z; StopImpersonating(bool)
0x18021724b  lea     rcx, [rbp+var_8]; this
0x18021724f  call    ??1CHandle@@QEAA@XZ; CHandle::~CHandle(void)
0x180217254  lea     rcx, [rbp+var_10]; this
0x180217258  call    ??1CHandle@@QEAA@XZ; CHandle::~CHandle(void)
0x18021725d  mov     rcx, [rbp+arg_0]
0x180217261  mov     rdx, [rcx]
0x180217264  mov     rax, [rdx+10h]
0x180217268  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18021726d  lea     r11, [rsp+70h+var_s0]
0x180217272  mov     rax, rbx
0x180217275  mov     rbx, [r11+38h]
0x180217279  mov     rsi, [r11+40h]
0x18021727d  mov     rsp, r11
0x180217280  pop     r15
0x180217282  pop     r14
0x180217284  pop     r12
0x180217286  pop     rdi
0x180217287  pop     rbp
0x180217288  retn
```
