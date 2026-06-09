# CMsiPath::GetFileChecksum(ushort const *,ulong *,ulong *)

- ea: `0x180220ae0`
- end: `0x180220dd0`
- name: `?GetFileChecksum@CMsiPath@@UEAAPEAVIMsiRecord@@PEBGPEAK1@Z`
- size: `752`
- prototype: `struct IMsiRecord *(CMsiPath *__hidden this, const unsigned __int16 *, unsigned int *, unsigned int *)`
- caller_count: `0`
- callee_count: `9`
- tags: `file_ops, installer_update`

## callees

- `0x18000c4bc`
- `0x18009cdb8`
- `0x18009d06c`
- `0x18013d2f0`
- `0x18014ae8c`
- `0x180153e68`
- `0x180220928`
- `0x180220ae0`
- `0x180266010`

## import_xrefs

- `KERNEL32!CreateFileMappingW` at `0x180220cc2`
- `KERNEL32!CreateFileMappingW` at `0x180220cc2`
- `KERNEL32!MapViewOfFile` at `0x180220d26`
- `KERNEL32!MapViewOfFile` at `0x180220d26`
- `KERNEL32!UnmapViewOfFile` at `0x180220d7b`
- `KERNEL32!UnmapViewOfFile` at `0x180220d7b`
- `KERNEL32!GetLastError` at `0x180220c89`
- `KERNEL32!GetLastError` at `0x180220cf4`
- `KERNEL32!GetLastError` at `0x180220c89`
- `KERNEL32!GetLastError` at `0x180220cf4`
- `KERNEL32!SetLastError` at `0x180220c57`
- `KERNEL32!SetLastError` at `0x180220c57`
- `KERNEL32!CreateFileW` at `0x180220bb3`
- `KERNEL32!CreateFileW` at `0x180220bb3`
- `KERNEL32!GetFileType` at `0x180220bd6`
- `KERNEL32!GetFileType` at `0x180220bd6`
- `KERNEL32!GetFileSize` at `0x180220d3f`
- `KERNEL32!GetFileSize` at `0x180220d3f`

## string_xrefs

- `0x180220c14`: `Error: This is not a valid file, hence failing to create: %s`

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
0x180220ae0  mov     [rsp-28h+arg_8], rbx
0x180220ae5  mov     [rsp-28h+arg_10], rsi
0x180220aea  push    rbp
0x180220aeb  push    rdi
0x180220aec  push    r12
0x180220aee  push    r14
0x180220af0  push    r15
0x180220af2  mov     rbp, rsp
0x180220af5  sub     rsp, 70h
0x180220af9  mov     rax, [rcx]
0x180220afc  mov     r14, r9
0x180220aff  mov     r15, r8
0x180220b02  mov     rdi, rdx
0x180220b05  mov     rsi, rcx
0x180220b08  mov     rax, [rax+240h]
0x180220b0f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180220b14  mov     rax, [rsi]
0x180220b17  lea     r12, ?s_NullString@MsiString@@0VCMsiStringNullCopy@@A; CMsiStringNullCopy MsiString::s_NullString
0x180220b1e  mov     r8, qword ptr cs:?s_NullString@MsiString@@0VCMsiStringNullCopy@@A; CMsiStringNullCopy MsiString::s_NullString
0x180220b25  mov     rcx, r12
0x180220b28  mov     [rbp+arg_0], r12
0x180220b2c  mov     rbx, [rax+88h]
0x180220b33  mov     rax, [r8+10h]
0x180220b37  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180220b3c  lea     r8, [rbp+arg_0]
0x180220b40  mov     [rbp+arg_0], r12
0x180220b44  mov     rdx, rdi
0x180220b47  mov     rcx, rsi
0x180220b4a  mov     rax, rbx
0x180220b4d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180220b52  xor     r12d, r12d
0x180220b55  mov     rbx, rax
0x180220b58  test    rax, rax
0x180220b5b  jnz     loc_180220DA3
0x180220b61  mov     rax, [rsi]
0x180220b64  mov     rcx, rsi
0x180220b67  mov     rax, [rax+220h]
0x180220b6e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180220b73  mov     dil, al
0x180220b76  test    al, al
0x180220b78  jz      short loc_180220B7F
0x180220b7a  call    ?StartImpersonating@@YA_NXZ; StartImpersonating(void)
0x180220b7f  mov     rcx, [rbp+arg_0]
0x180220b83  mov     rdx, [rcx]
0x180220b86  mov     rax, [rdx+50h]
0x180220b8a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180220b8f  xor     r9d, r9d; lpSecurityAttributes
0x180220b92  mov     [rsp+70h+hTemplateFile], r12; hTemplateFile
0x180220b97  mov     [rsp+70h+dwFlagsAndAttributes], 100000h; dwFlagsAndAttributes
0x180220b9f  mov     edx, 80000000h; dwDesiredAccess
0x180220ba4  mov     rcx, rax; lpFileName
0x180220ba7  mov     [rsp+70h+dwCreationDisposition], 3; dwCreationDisposition
0x180220baf  lea     r8d, [r9+1]; dwShareMode
0x180220bb3  call    cs:__imp_CreateFileW
0x180220bba  nop     dword ptr [rax+rax+00h]
0x180220bbf  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180220bc3  mov     [rbp+var_10], rax
0x180220bc7  mov     rbx, rax
0x180220bca  cmp     rax, rsi
0x180220bcd  jz      loc_180220C67
0x180220bd3  mov     rcx, rax; hFile
0x180220bd6  call    cs:__imp_GetFileType
0x180220bdd  nop     dword ptr [rax+rax+00h]
0x180220be2  add     eax, 0FFFFFFFEh
0x180220be5  cmp     eax, 1
0x180220be8  ja      short loc_180220C67
0x180220bea  cmp     cs:?g_dmDiagnosticMode@@3HA, r12d; int g_dmDiagnosticMode
0x180220bf1  jz      short loc_180220C46
0x180220bf3  mov     rcx, [rbp+arg_0]
0x180220bf7  mov     rax, [rcx]
0x180220bfa  mov     rax, [rax+50h]
0x180220bfe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180220c03  lea     rcx, aNull; "(NULL)"
0x180220c0a  mov     [rsp+70h+var_18], r12; void *
0x180220c0f  mov     [rsp+70h+var_20], r12d; unsigned int
0x180220c14  lea     r9, aErrorThisIsNot; "Error: This is not a valid file, hence "...
0x180220c1b  mov     [rsp+70h+var_28], rcx; unsigned __int16 *
0x180220c20  xor     edx, edx; unsigned __int16
0x180220c22  mov     [rsp+70h+var_30], rcx; unsigned __int16 *
0x180220c27  xor     r8d, r8d; int
0x180220c2a  mov     [rsp+70h+var_38], rcx; unsigned __int16 *
0x180220c2f  mov     [rsp+70h+hTemplateFile], rcx; unsigned __int16 *
0x180220c34  mov     qword ptr [rsp+70h+dwFlagsAndAttributes], rcx; unsigned __int16 *
0x180220c39  lea     ecx, [rsi+0Ah]; int
0x180220c3c  mov     qword ptr [rsp+70h+dwCreationDisposition], rax; unsigned __int16 *
0x180220c41  call    ?DebugString@@YAXHGHPEBG000000KPEAX@Z; DebugString(int,ushort,int,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ulong,void *)
0x180220c46  mov     rdx, rsi
0x180220c49  lea     rcx, [rbp+var_10]
0x180220c4d  call    ??4CHandle@@QEAAXPEAX@Z; CHandle::operator=(void *)
0x180220c52  mov     ecx, 6Eh ; 'n'; dwErrCode
0x180220c57  call    cs:__imp_SetLastError
0x180220c5e  nop     dword ptr [rax+rax+00h]
0x180220c63  mov     rbx, [rbp+var_10]
0x180220c67  cmp     rbx, rsi
0x180220c6a  jnz     short loc_180220CAC
0x180220c6c  test    dil, dil
0x180220c6f  jz      short loc_180220C76
0x180220c71  call    ?StopImpersonating@@YAX_N@Z; StopImpersonating(bool)
0x180220c76  mov     rcx, [rbp+arg_0]
0x180220c7a  mov     rax, [rcx]
0x180220c7d  mov     rax, [rax+50h]
0x180220c81  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180220c86  mov     rbx, rax
0x180220c89  call    cs:__imp_GetLastError
0x180220c90  nop     dword ptr [rax+rax+00h]
0x180220c95  mov     r8, rbx; unsigned __int16 *
0x180220c98  mov     ecx, 914h; int
0x180220c9d  mov     edx, eax; int
0x180220c9f  call    ?PostError@@YAPEAVIMsiRecord@@HHPEBG@Z; PostError(int,int,ushort const *)
0x180220ca4  mov     rbx, rax
0x180220ca7  jmp     loc_180220D9A
0x180220cac  xor     r9d, r9d; dwMaximumSizeHigh
0x180220caf  mov     qword ptr [rsp+70h+dwFlagsAndAttributes], r12; lpName
0x180220cb4  xor     edx, edx; lpFileMappingAttributes
0x180220cb6  mov     [rsp+70h+dwCreationDisposition], r12d; dwMaximumSizeLow
0x180220cbb  mov     rcx, rbx; hFile
0x180220cbe  lea     r8d, [r9+2]; flProtect
0x180220cc2  call    cs:__imp_CreateFileMappingW
0x180220cc9  nop     dword ptr [rax+rax+00h]
0x180220cce  mov     [rbp+var_8], rax
0x180220cd2  cmp     rax, rsi
0x180220cd5  jnz     short loc_180220D14
0x180220cd7  test    dil, dil
0x180220cda  jz      short loc_180220CE1
0x180220cdc  call    ?StopImpersonating@@YAX_N@Z; StopImpersonating(bool)
0x180220ce1  mov     rcx, [rbp+arg_0]
0x180220ce5  mov     rax, [rcx]
0x180220ce8  mov     rax, [rax+50h]
0x180220cec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180220cf1  mov     rbx, rax
0x180220cf4  call    cs:__imp_GetLastError
0x180220cfb  nop     dword ptr [rax+rax+00h]
0x180220d00  mov     r8, rbx; unsigned __int16 *
0x180220d03  mov     ecx, 914h; int
0x180220d08  mov     edx, eax; int
0x180220d0a  call    ?PostError@@YAPEAVIMsiRecord@@HHPEBG@Z; PostError(int,int,ushort const *)
0x180220d0f  mov     rbx, rax
0x180220d12  jmp     short loc_180220D91
0x180220d14  xor     r9d, r9d; dwFileOffsetLow
0x180220d17  mov     qword ptr [rsp+70h+dwCreationDisposition], r12; dwNumberOfBytesToMap
0x180220d1c  xor     r8d, r8d; dwFileOffsetHigh
0x180220d1f  mov     rcx, rax; hFileMappingObject
0x180220d22  lea     edx, [r9+4]; dwDesiredAccess
0x180220d26  call    cs:__imp_MapViewOfFile
0x180220d2d  nop     dword ptr [rax+rax+00h]
0x180220d32  mov     rsi, rax
0x180220d35  test    rax, rax
0x180220d38  jz      short loc_180220CD7
0x180220d3a  xor     edx, edx; lpFileSizeHigh
0x180220d3c  mov     rcx, rbx; hFile
0x180220d3f  call    cs:__imp_GetFileSize
0x180220d46  nop     dword ptr [rax+rax+00h]
0x180220d4b  mov     rcx, [rbp+arg_0]
0x180220d4f  mov     ebx, eax
0x180220d51  mov     rdx, [rcx]
0x180220d54  mov     rax, [rdx+50h]
0x180220d58  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180220d5d  mov     r9d, ebx; int
0x180220d60  mov     qword ptr [rsp+70h+dwFlagsAndAttributes], r14; unsigned int *
0x180220d65  mov     r8, rsi; void *
0x180220d68  mov     qword ptr [rsp+70h+dwCreationDisposition], r15; unsigned int *
0x180220d6d  mov     rdx, rax; unsigned __int16 *
0x180220d70  call    ?GetChecksums@CMsiPath@@IEAAPEAVIMsiRecord@@PEBGPEAXHPEAK2@Z; CMsiPath::GetChecksums(ushort const *,void *,int,ulong *,ulong *)
0x180220d75  mov     rcx, rsi; lpBaseAddress
0x180220d78  mov     rbx, rax
0x180220d7b  call    cs:__imp_UnmapViewOfFile
0x180220d82  nop     dword ptr [rax+rax+00h]
0x180220d87  test    dil, dil
0x180220d8a  jz      short loc_180220D91
0x180220d8c  call    ?StopImpersonating@@YAX_N@Z; StopImpersonating(bool)
0x180220d91  lea     rcx, [rbp+var_8]; this
0x180220d95  call    ??1CHandle@@QEAA@XZ; CHandle::~CHandle(void)
0x180220d9a  lea     rcx, [rbp+var_10]; this
0x180220d9e  call    ??1CHandle@@QEAA@XZ; CHandle::~CHandle(void)
0x180220da3  mov     rcx, [rbp+arg_0]
0x180220da7  mov     rdx, [rcx]
0x180220daa  mov     rax, [rdx+10h]
0x180220dae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180220db3  lea     r11, [rsp+70h+var_s0]
0x180220db8  mov     rax, rbx
0x180220dbb  mov     rbx, [r11+38h]
0x180220dbf  mov     rsi, [r11+40h]
0x180220dc3  mov     rsp, r11
0x180220dc6  pop     r15
0x180220dc8  pop     r14
0x180220dca  pop     r12
0x180220dcc  pop     rdi
0x180220dcd  pop     rbp
0x180220dce  retn
```
