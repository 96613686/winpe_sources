# FileUtil::CreateJunctionPointWithAttributes(ushort const *,ushort const *,ulong)

- ea: `0x1400bd7b0`
- end: `0x1400bdc12`
- name: `?CreateJunctionPointWithAttributes@FileUtil@@SAPEAVFrsStatus@@PEBG0K@Z`
- size: `1122`
- prototype: `struct FrsStatus *__fastcall(const unsigned __int16 *, PCWSTR DosPathName, unsigned int)`
- caller_count: `2`
- callee_count: `16`
- tags: `file_ops, reparse_path, loader_planting`

## callers

- `0x14010dba0`
- `0x1401f7400`

## callees

- `0x1400036a0`
- `0x14000bbc5`
- `0x14000ee94`
- `0x14001cfa0`
- `0x140022ce4`
- `0x14002c548`
- `0x14005c620`
- `0x1400bd7b0`
- `0x1400be540`
- `0x1400c0e50`
- `0x1401af7b0`
- `0x1401b9494`
- `0x1401c0b7c`
- `0x1401c1858`
- `0x1401c22f8`
- `0x1401c27b4`

## import_xrefs

- `KERNEL32!DeviceIoControl` at `0x1400bdafd`
- `KERNEL32!DeviceIoControl` at `0x1400bdafd`
- `KERNEL32!GetLastError` at `0x1400bdb0d`
- `KERNEL32!GetLastError` at `0x1400bdb0d`
- `KERNEL32!GetCurrentThreadId` at `0x1400bd8ab`
- `KERNEL32!GetCurrentThreadId` at `0x1400bd958`
- `KERNEL32!GetCurrentThreadId` at `0x1400bd984`
- `KERNEL32!GetCurrentThreadId` at `0x1400bd9f7`
- `KERNEL32!GetCurrentThreadId` at `0x1400bdb1b`
- `KERNEL32!GetCurrentThreadId` at `0x1400bdb8b`
- `KERNEL32!GetCurrentThreadId` at `0x1400bd8ab`
- `KERNEL32!GetCurrentThreadId` at `0x1400bd958`
- `KERNEL32!GetCurrentThreadId` at `0x1400bd984`
- `KERNEL32!GetCurrentThreadId` at `0x1400bd9f7`
- `KERNEL32!GetCurrentThreadId` at `0x1400bdb1b`
- `KERNEL32!GetCurrentThreadId` at `0x1400bdb8b`
- `ntdll!RtlGetFullPathName_U` at `0x1400bd945`
- `ntdll!RtlGetFullPathName_U` at `0x1400bd945`
- `ntdll!RtlFreeUnicodeString` at `0x1400bdb70`
- `ntdll!RtlFreeUnicodeString` at `0x1400bdb70`
- `ntdll!RtlDosPathNameToNtPathName_U` at `0x1400bd897`
- `ntdll!RtlDosPathNameToNtPathName_U` at `0x1400bd897`

## string_xrefs

- `0x1400bd839`: `FileUtil::CreateJunctionPointWithAttributes`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
struct FrsStatus *__fastcall FileUtil::CreateJunctionPointWithAttributes(
        const unsigned __int16 *a1,
        PCWSTR DosPathName,
        unsigned int a3)
{
  __int64 v6; // r14
  __int64 v7; // rax
  struct FrsStatus *v8; // r15
  DWORD CurrentThreadId; // eax
  __int64 v10; // rcx
  __int64 DisplayName; // rax
  ULONG FullPathName_U; // eax
  unsigned __int16 v13; // r12
  __int64 v14; // rcx
  __int64 v15; // rax
  __int64 v16; // rcx
  int v17; // eax
  __int64 v18; // r11
  unsigned int v19; // ebx
  DWORD v20; // eax
  __int64 v21; // rcx
  unsigned __int16 v22; // bx
  char *v23; // rdi
  DWORD LastError; // ebx
  DWORD v25; // eax
  __int64 v26; // rcx
  DWORD v27; // eax
  __int64 v28; // rcx
  DWORD lpOverlapped; // [rsp+38h] [rbp-C8h]
  DWORD lpOverlappeda; // [rsp+38h] [rbp-C8h]
  struct _UNICODE_STRING NtPathName; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v33; // [rsp+60h] [rbp-A0h] BYREF
  DWORD BytesReturned; // [rsp+68h] [rbp-98h] BYREF
  HANDLE hDevice; // [rsp+70h] [rbp-90h] BYREF
  char *v36; // [rsp+78h] [rbp-88h] BYREF
  void **v37; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v38[8]; // [rsp+88h] [rbp-78h] BYREF
  _BYTE v39[8]; // [rsp+90h] [rbp-70h] BYREF
  __int128 v40; // [rsp+98h] [rbp-68h] BYREF
  WCHAR Buffer[264]; // [rsp+B0h] [rbp-50h] BYREF

  NtPathName = 0;
  v40 = 0;
  v6 = 0;
  v36 = 0;
  BytesReturned = 0;
  hDevice = 0;
  Win32FilePath::Win32FilePath((Win32FilePath *)&v37);
  v7 = FrsStringImpl<unsigned short,char>::FrsStringImpl<unsigned short,char>(v39, DosPathName);
  v8 = (struct FrsStatus *)Win32FilePath::SetNoConvert(&v37, v7);
  FrsStringImpl<char,unsigned short>::ReleaseBody(v39);
  if ( v8 )
    goto LABEL_19;
  v8 = FileUtil::FrsCreateFile(a1, 2u, a3, 7u, 3u, 0x204001u, &hDevice);
  if ( v8 )
    goto LABEL_19;
  if ( !RtlDosPathNameToNtPathName_U(DosPathName, &NtPathName, 0, 0) )
  {
    CurrentThreadId = GetCurrentThreadId();
    v8 = (struct FrsStatus *)FrsStatusList::PushNewError(
                               v10,
                               3,
                               0,
                               1,
                               "base\\fs\\remotefs\\frs\\src\\fs\\fileutil.cpp",
                               "FileUtil::CreateJunctionPointWithAttributes",
                               1060,
                               CurrentThreadId,
                               0);
    if ( v8 )
      goto LABEL_19;
  }
  FrsStringImpl<unsigned short,char>::FrsStringImpl<unsigned short,char>(&v33, DosPathName);
  if ( (unsigned int)Win32FilePath::Win32FilePathHelper::HasVolumeGuidPrefix(v38) )
  {
    v17 = StringCchCopyNW(Buffer, 0x105u, (const unsigned __int16 *)(v33 + 18), *(_QWORD *)(v33 + 8));
    v19 = v17;
    if ( v17 >= 0 )
    {
      v13 = 2 * *(_QWORD *)(v18 + 8);
    }
    else
    {
      if ( (v17 & 0x1FFF0000) == 0x70000 )
        v19 = (unsigned __int16)v17;
      v20 = GetCurrentThreadId();
      v8 = (struct FrsStatus *)FrsStatusList::PushNewError(
                                 v21,
                                 v19,
                                 0,
                                 1,
                                 "base\\fs\\remotefs\\frs\\src\\fs\\fileutil.cpp",
                                 "FileUtil::CreateJunctionPointWithAttributes",
                                 1102,
                                 v20,
                                 0);
      v13 = v40;
    }
    goto LABEL_16;
  }
  DisplayName = Win32FilePath::GetDisplayName((Win32FilePath *)&v37);
  FrsStringImpl<unsigned short,char>::Set(&v33, DisplayName);
  FrsStringImpl<char,unsigned short>::ReleaseBody(&v40);
  FullPathName_U = RtlGetFullPathName_U((PCWSTR)(v33 + 18), 0x20Au, Buffer, 0);
  v13 = FullPathName_U;
  if ( !FullPathName_U )
  {
    lpOverlapped = GetCurrentThreadId();
    v15 = FrsStatusList::PushNewError(
            v14,
            161,
            0,
            1,
            "base\\fs\\remotefs\\frs\\src\\fs\\fileutil.cpp",
            "FileUtil::CreateJunctionPointWithAttributes",
            1087,
            lpOverlapped,
            0);
LABEL_10:
    v8 = (struct FrsStatus *)v15;
    goto LABEL_16;
  }
  if ( FullPathName_U > 0x20A )
  {
    lpOverlappeda = GetCurrentThreadId();
    v15 = FrsStatusList::PushNewError(
            v16,
            111,
            0,
            1,
            "base\\fs\\remotefs\\frs\\src\\fs\\fileutil.cpp",
            "FileUtil::CreateJunctionPointWithAttributes",
            1091,
            lpOverlappeda,
            0);
    goto LABEL_10;
  }
LABEL_16:
  FrsStringImpl<char,unsigned short>::ReleaseBody(&v33);
  if ( !v8 )
  {
    v22 = v13 + NtPathName.Length + 12;
    v23 = (char *)operator_new((unsigned int)v22 + 8);
    v36 = v23;
    *((_WORD *)v23 + 2) = v22;
    *(_DWORD *)v23 = -1610612733;
    *(_DWORD *)(v23 + 6) = 0;
    *((_WORD *)v23 + 5) = NtPathName.Length;
    *((_WORD *)v23 + 6) = NtPathName.Length + 2;
    *((_WORD *)v23 + 7) = v13;
    memcpy_0(v23 + 16, NtPathName.Buffer, NtPathName.Length);
    *(_WORD *)&v23[NtPathName.Length + 16] = 0;
    memcpy_0(&v23[NtPathName.Length + 18], Buffer, v13);
    if ( !DeviceIoControl(hDevice, 0x900A4u, v23, v22 + 8, 0, 0, &BytesReturned, 0) )
    {
      LastError = GetLastError();
      v25 = GetCurrentThreadId();
      v8 = (struct FrsStatus *)FrsStatusList::PushNewError(
                                 v26,
                                 LastError,
                                 0,
                                 1,
                                 "base\\fs\\remotefs\\frs\\src\\fs\\fileutil.cpp",
                                 "FileUtil::CreateJunctionPointWithAttributes",
                                 1164,
                                 v25,
                                 0);
    }
  }
LABEL_19:
  if ( NtPathName.Length )
    RtlFreeUnicodeString(&NtPathName);
  CloseHandleEx(&hDevice);
  if ( v8 )
  {
    v27 = GetCurrentThreadId();
    v6 = FrsStatusList::PushNewError(
           v28,
           *((unsigned int *)v8 + 1),
           *((unsigned int *)v8 + 2),
           *(unsigned int *)v8,
           "base\\fs\\remotefs\\frs\\src\\fs\\fileutil.cpp",
           "FileUtil::CreateJunctionPointWithAttributes",
           1177,
           v27,
           v8);
  }
  v37 = &BaseFilePath::`vftable';
  FrsStringImpl<char,unsigned short>::ReleaseBody(v38);
  scoped_any<_FRS_RDC_SOURCE_NEED *,close_delete_array,null_t,0>::~scoped_any<_FRS_RDC_SOURCE_NEED *,close_delete_array,null_t,0>(&v36);
  return (struct FrsStatus *)v6;
}

```

## disassembly

```asm
0x1400bd7b0  mov     [rsp-8+arg_18], rbx
0x1400bd7b5  push    rbp
0x1400bd7b6  push    rsi
0x1400bd7b7  push    rdi
0x1400bd7b8  push    r12
0x1400bd7ba  push    r13
0x1400bd7bc  push    r14
0x1400bd7be  push    r15
0x1400bd7c0  lea     rbp, [rsp-1D0h]
0x1400bd7c8  sub     rsp, 2D0h
0x1400bd7cf  mov     rax, cs:__security_cookie
0x1400bd7d6  xor     rax, rsp
0x1400bd7d9  mov     [rbp+200h+var_40], rax
0x1400bd7e0  mov     esi, r8d
0x1400bd7e3  mov     rbx, rdx
0x1400bd7e6  mov     rdi, rcx
0x1400bd7e9  xorps   xmm0, xmm0
0x1400bd7ec  movups  xmmword ptr [rsp+300h+NtPathName.Length], xmm0
0x1400bd7f1  xorps   xmm1, xmm1
0x1400bd7f4  movups  [rbp+200h+var_268], xmm1
0x1400bd7f8  xor     r14d, r14d
0x1400bd7fb  mov     [rsp+300h+var_288], r14
0x1400bd800  mov     [rsp+300h+BytesReturned], r14d
0x1400bd805  mov     [rsp+300h+hDevice], r14
0x1400bd80a  lea     rcx, [rbp+200h+var_280]; this
0x1400bd80e  call    ??0Win32FilePath@@QEAA@XZ; Win32FilePath::Win32FilePath(void)
0x1400bd813  nop
0x1400bd814  mov     rdx, rbx
0x1400bd817  lea     rcx, [rbp+200h+var_270]
0x1400bd81b  call    ??0?$FrsStringImpl@GD@@QEAA@PEBG@Z; FrsStringImpl<ushort,char>::FrsStringImpl<ushort,char>(ushort const *)
0x1400bd820  nop
0x1400bd821  mov     rdx, rax
0x1400bd824  lea     rcx, [rbp+200h+var_280]
0x1400bd828  call    ?SetNoConvert@Win32FilePath@@QEAAPEAVFrsStatus@@AEBV?$FrsStringImpl@GD@@@Z; Win32FilePath::SetNoConvert(FrsStringImpl<ushort,char> const &)
0x1400bd82d  mov     r15, rax
0x1400bd830  lea     rcx, [rbp+200h+var_270]
0x1400bd834  call    ?ReleaseBody@?$FrsStringImpl@DG@@AEAAXXZ; FrsStringImpl<char,ushort>::ReleaseBody(void)
0x1400bd839  lea     r13, aFileutilCreate; "FileUtil::CreateJunctionPointWithAttrib"...
0x1400bd840  lea     r12, aBaseFsRemotefs_24; "base\\fs\\remotefs\\frs\\src\\fs\\fileu"...
0x1400bd847  test    r15, r15
0x1400bd84a  jnz     loc_1400BDB63
0x1400bd850  lea     rax, [rsp+300h+hDevice]
0x1400bd855  mov     [rsp+300h+lpBytesReturned], rax; void **
0x1400bd85a  mov     [rsp+300h+nOutBufferSize], 204001h; unsigned int
0x1400bd862  mov     dword ptr [rsp+300h+lpOutBuffer], 3; unsigned int
0x1400bd86a  lea     r9d, [r14+7]; unsigned int
0x1400bd86e  mov     r8d, esi; unsigned int
0x1400bd871  lea     edx, [r14+2]; unsigned int
0x1400bd875  mov     rcx, rdi; unsigned __int16 *
0x1400bd878  call    ?FrsCreateFile@FileUtil@@SAPEAVFrsStatus@@PEBGKKKKKPEAPEAX@Z; FileUtil::FrsCreateFile(ushort const *,ulong,ulong,ulong,ulong,ulong,void * *)
0x1400bd87d  mov     r15, rax
0x1400bd880  test    rax, rax
0x1400bd883  jnz     loc_1400BDB63
0x1400bd889  xor     r9d, r9d; DirectoryInfo
0x1400bd88c  xor     r8d, r8d; NtFileNamePart
0x1400bd88f  lea     rdx, [rsp+300h+NtPathName]; NtPathName
0x1400bd894  mov     rcx, rbx; DosPathName
0x1400bd897  call    cs:__imp_RtlDosPathNameToNtPathName_U
0x1400bd89e  nop     dword ptr [rax+rax+00h]
0x1400bd8a3  lea     edi, [r14+1]
0x1400bd8a7  test    al, al
0x1400bd8a9  jnz     short loc_1400BD8EC
0x1400bd8ab  call    cs:__imp_GetCurrentThreadId
0x1400bd8b2  nop     dword ptr [rax+rax+00h]
0x1400bd8b7  mov     [rsp+300h+var_2C0], r14
0x1400bd8bc  mov     dword ptr [rsp+300h+lpOverlapped], eax
0x1400bd8c0  mov     dword ptr [rsp+300h+lpBytesReturned], 424h
0x1400bd8c8  mov     qword ptr [rsp+300h+nOutBufferSize], r13
0x1400bd8cd  mov     [rsp+300h+lpOutBuffer], r12
0x1400bd8d2  mov     r9d, edi
0x1400bd8d5  xor     r8d, r8d
0x1400bd8d8  lea     edx, [rdi+2]
0x1400bd8db  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x1400bd8e0  mov     r15, rax
0x1400bd8e3  test    rax, rax
0x1400bd8e6  jnz     loc_1400BDB63
0x1400bd8ec  mov     rdx, rbx
0x1400bd8ef  lea     rcx, [rsp+300h+var_2A0]
0x1400bd8f4  call    ??0?$FrsStringImpl@GD@@QEAA@PEBG@Z; FrsStringImpl<ushort,char>::FrsStringImpl<ushort,char>(ushort const *)
0x1400bd8f9  nop
0x1400bd8fa  lea     rcx, [rbp+200h+var_278]
0x1400bd8fe  call    ?HasVolumeGuidPrefix@Win32FilePathHelper@Win32FilePath@@SAHAEBV?$FrsStringImpl@GD@@@Z; Win32FilePath::Win32FilePathHelper::HasVolumeGuidPrefix(FrsStringImpl<ushort,char> const &)
0x1400bd903  test    eax, eax
0x1400bd905  jnz     loc_1400BD9C7
0x1400bd90b  lea     rdx, [rbp+200h+var_268]
0x1400bd90f  lea     rcx, [rbp+200h+var_280]; this
0x1400bd913  call    ?GetDisplayName@Win32FilePath@@QEBA?AV?$FrsStringImpl@GD@@XZ; Win32FilePath::GetDisplayName(void)
0x1400bd918  mov     rdx, rax
0x1400bd91b  lea     rcx, [rsp+300h+var_2A0]
0x1400bd920  call    ?Set@?$FrsStringImpl@GD@@QEAA_NAEBV1@@Z; FrsStringImpl<ushort,char>::Set(FrsStringImpl<ushort,char> const &)
0x1400bd925  lea     rcx, [rbp+200h+var_268]
0x1400bd929  call    ?ReleaseBody@?$FrsStringImpl@DG@@AEAAXXZ; FrsStringImpl<char,ushort>::ReleaseBody(void)
0x1400bd92e  mov     rcx, [rsp+300h+var_2A0]
0x1400bd933  add     rcx, 12h; FileName
0x1400bd937  xor     r9d, r9d; ShortName
0x1400bd93a  lea     r8, [rbp+200h+Buffer]; Buffer
0x1400bd93e  mov     ebx, 20Ah
0x1400bd943  mov     edx, ebx; Size
0x1400bd945  call    cs:__imp_RtlGetFullPathName_U
0x1400bd94c  nop     dword ptr [rax+rax+00h]
0x1400bd951  mov     r12d, eax
0x1400bd954  test    eax, eax
0x1400bd956  jnz     short loc_1400BD97C
0x1400bd958  call    cs:__imp_GetCurrentThreadId
0x1400bd95f  nop     dword ptr [rax+rax+00h]
0x1400bd964  mov     [rsp+300h+var_2C0], r14
0x1400bd969  mov     dword ptr [rsp+300h+lpOverlapped], eax
0x1400bd96d  mov     dword ptr [rsp+300h+lpBytesReturned], 43Fh
0x1400bd975  mov     edx, 0A1h
0x1400bd97a  jmp     short loc_1400BD9A6
0x1400bd97c  cmp     eax, ebx
0x1400bd97e  jbe     loc_1400BDA3D
0x1400bd984  call    cs:__imp_GetCurrentThreadId
0x1400bd98b  nop     dword ptr [rax+rax+00h]
0x1400bd990  mov     [rsp+300h+var_2C0], r14
0x1400bd995  mov     dword ptr [rsp+300h+lpOverlapped], eax
0x1400bd999  mov     dword ptr [rsp+300h+lpBytesReturned], 443h
0x1400bd9a1  mov     edx, 6Fh ; 'o'
0x1400bd9a6  mov     qword ptr [rsp+300h+nOutBufferSize], r13
0x1400bd9ab  lea     rax, aBaseFsRemotefs_24; "base\\fs\\remotefs\\frs\\src\\fs\\fileu"...
0x1400bd9b2  xor     r8d, r8d
0x1400bd9b5  mov     r9d, edi
0x1400bd9b8  mov     [rsp+300h+lpOutBuffer], rax
0x1400bd9bd  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x1400bd9c2  mov     r15, rax
0x1400bd9c5  jmp     short loc_1400BDA3D
0x1400bd9c7  mov     r11, [rsp+300h+var_2A0]
0x1400bd9cc  lea     r8, [r11+12h]; unsigned __int16 *
0x1400bd9d0  mov     r9, [r11+8]; unsigned __int64
0x1400bd9d4  mov     edx, 105h; unsigned __int64
0x1400bd9d9  lea     rcx, [rbp+200h+Buffer]; unsigned __int16 *
0x1400bd9dd  call    ?StringCchCopyNW@@YAJPEAG_KPEBG1@Z; StringCchCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)
0x1400bd9e2  mov     ebx, eax
0x1400bd9e4  test    eax, eax
0x1400bd9e6  jns     short loc_1400BDA35
0x1400bd9e8  and     eax, 1FFF0000h
0x1400bd9ed  cmp     eax, 70000h
0x1400bd9f2  jnz     short loc_1400BD9F7
0x1400bd9f4  movzx   ebx, bx
0x1400bd9f7  call    cs:__imp_GetCurrentThreadId
0x1400bd9fe  nop     dword ptr [rax+rax+00h]
0x1400bda03  mov     [rsp+300h+var_2C0], r14
0x1400bda08  mov     dword ptr [rsp+300h+lpOverlapped], eax
0x1400bda0c  mov     dword ptr [rsp+300h+lpBytesReturned], 44Eh
0x1400bda14  mov     qword ptr [rsp+300h+nOutBufferSize], r13
0x1400bda19  mov     [rsp+300h+lpOutBuffer], r12
0x1400bda1e  mov     r9d, edi
0x1400bda21  xor     r8d, r8d
0x1400bda24  mov     edx, ebx
0x1400bda26  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x1400bda2b  mov     r15, rax
0x1400bda2e  movzx   r12d, word ptr [rbp+200h+var_268]
0x1400bda33  jmp     short loc_1400BDA3D
0x1400bda35  mov     rax, [r11+8]
0x1400bda39  lea     r12d, [rax+rax]
0x1400bda3d  lea     rcx, [rsp+300h+var_2A0]
0x1400bda42  call    ?ReleaseBody@?$FrsStringImpl@DG@@AEAAXXZ; FrsStringImpl<char,ushort>::ReleaseBody(void)
0x1400bda47  test    r15, r15
0x1400bda4a  jnz     loc_1400BDB5C
0x1400bda50  movzx   ebx, [rsp+300h+NtPathName.Length]
0x1400bda55  add     bx, 0Ch
0x1400bda59  add     bx, r12w
0x1400bda5d  movzx   esi, bx
0x1400bda60  add     esi, 8
0x1400bda63  mov     ecx, esi; unsigned __int64
0x1400bda65  call    ?operator_new@@YAPEAX_K@Z; operator_new(unsigned __int64)
0x1400bda6a  mov     rdi, rax
0x1400bda6d  mov     [rsp+300h+var_288], rax
0x1400bda72  mov     [rax+4], bx
0x1400bda76  mov     dword ptr [rax], 0A0000003h
0x1400bda7c  mov     [rax+6], r14d
0x1400bda80  movzx   ecx, [rsp+300h+NtPathName.Length]
0x1400bda85  mov     [rax+0Ah], cx
0x1400bda89  movzx   ecx, [rsp+300h+NtPathName.Length]
0x1400bda8e  add     cx, 2
0x1400bda92  mov     [rax+0Ch], cx
0x1400bda96  mov     [rax+0Eh], r12w
0x1400bda9b  movzx   r8d, [rsp+300h+NtPathName.Length]; Size
0x1400bdaa1  lea     rcx, [rax+10h]; void *
0x1400bdaa5  mov     rdx, [rsp+300h+NtPathName.Buffer]; Src
0x1400bdaaa  call    memcpy_0
0x1400bdaaf  movzx   eax, [rsp+300h+NtPathName.Length]
0x1400bdab4  xor     ecx, ecx
0x1400bdab6  mov     [rax+rdi+10h], cx
0x1400bdabb  movzx   r8d, r12w; Size
0x1400bdabf  movzx   ecx, [rsp+300h+NtPathName.Length]
0x1400bdac4  add     rcx, 12h
0x1400bdac8  add     rcx, rdi; void *
0x1400bdacb  lea     rdx, [rbp+200h+Buffer]; Src
0x1400bdacf  call    memcpy_0
0x1400bdad4  mov     [rsp+300h+lpOverlapped], r14; lpOverlapped
0x1400bdad9  lea     rax, [rsp+300h+BytesReturned]
0x1400bdade  mov     [rsp+300h+lpBytesReturned], rax; lpBytesReturned
0x1400bdae3  mov     [rsp+300h+nOutBufferSize], r14d; nOutBufferSize
0x1400bdae8  mov     [rsp+300h+lpOutBuffer], r14; lpOutBuffer
0x1400bdaed  mov     r9d, esi; nInBufferSize
0x1400bdaf0  mov     r8, rdi; lpInBuffer
0x1400bdaf3  mov     edx, 900A4h; dwIoControlCode
0x1400bdaf8  mov     rcx, [rsp+300h+hDevice]; hDevice
0x1400bdafd  call    cs:__imp_DeviceIoControl
0x1400bdb04  nop     dword ptr [rax+rax+00h]
0x1400bdb09  test    eax, eax
0x1400bdb0b  jnz     short loc_1400BDB5C
0x1400bdb0d  call    cs:__imp_GetLastError
0x1400bdb14  nop     dword ptr [rax+rax+00h]
0x1400bdb19  mov     ebx, eax
0x1400bdb1b  call    cs:__imp_GetCurrentThreadId
0x1400bdb22  nop     dword ptr [rax+rax+00h]
0x1400bdb27  mov     [rsp+300h+var_2C0], r14
0x1400bdb2c  mov     dword ptr [rsp+300h+lpOverlapped], eax
0x1400bdb30  mov     dword ptr [rsp+300h+lpBytesReturned], 48Ch
0x1400bdb38  mov     qword ptr [rsp+300h+nOutBufferSize], r13
0x1400bdb3d  lea     r12, aBaseFsRemotefs_24; "base\\fs\\remotefs\\frs\\src\\fs\\fileu"...
0x1400bdb44  mov     [rsp+300h+lpOutBuffer], r12
0x1400bdb49  lea     r9d, [r15+1]
0x1400bdb4d  xor     r8d, r8d
0x1400bdb50  mov     edx, ebx
0x1400bdb52  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x1400bdb57  mov     r15, rax
0x1400bdb5a  jmp     short loc_1400BDB63
0x1400bdb5c  lea     r12, aBaseFsRemotefs_24; "base\\fs\\remotefs\\frs\\src\\fs\\fileu"...
0x1400bdb63  cmp     [rsp+300h+NtPathName.Length], r14w
0x1400bdb69  jbe     short loc_1400BDB7C
0x1400bdb6b  lea     rcx, [rsp+300h+NtPathName]; UnicodeString
0x1400bdb70  call    cs:__imp_RtlFreeUnicodeString
0x1400bdb77  nop     dword ptr [rax+rax+00h]
0x1400bdb7c  lea     rcx, [rsp+300h+hDevice]; void **
0x1400bdb81  call    ?CloseHandleEx@@YAXAEAPEAX@Z; CloseHandleEx(void * &)
0x1400bdb86  test    r15, r15
0x1400bdb89  jz      short loc_1400BDBC5
0x1400bdb8b  call    cs:__imp_GetCurrentThreadId
0x1400bdb92  nop     dword ptr [rax+rax+00h]
0x1400bdb97  mov     [rsp+300h+var_2C0], r15
0x1400bdb9c  mov     dword ptr [rsp+300h+lpOverlapped], eax
0x1400bdba0  mov     dword ptr [rsp+300h+lpBytesReturned], 499h
0x1400bdba8  mov     qword ptr [rsp+300h+nOutBufferSize], r13
0x1400bdbad  mov     [rsp+300h+lpOutBuffer], r12
0x1400bdbb2  mov     r9d, [r15]
0x1400bdbb5  mov     r8d, [r15+8]
0x1400bdbb9  mov     edx, [r15+4]
0x1400bdbbd  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x1400bdbc2  mov     r14, rax
0x1400bdbc5  lea     rax, ??_7BaseFilePath@@6B@; const BaseFilePath::`vftable'
0x1400bdbcc  mov     [rbp+200h+var_280], rax
0x1400bdbd0  lea     rcx, [rbp+200h+var_278]
0x1400bdbd4  call    ?ReleaseBody@?$FrsStringImpl@DG@@AEAAXXZ; FrsStringImpl<char,ushort>::ReleaseBody(void)
0x1400bdbd9  nop
0x1400bdbda  lea     rcx, [rsp+300h+var_288]
0x1400bdbdf  call    ??1?$scoped_any@PEAU_FRS_RDC_SOURCE_NEED@@Uclose_delete_array@@Unull_t@@$0A@@@QEAA@XZ; scoped_any<_FRS_RDC_SOURCE_NEED *,close_delete_array,null_t,0>::~scoped_any<_FRS_RDC_SOURCE_NEED *,close_delete_array,null_t,0>(void)
0x1400bdbe4  mov     rax, r14
0x1400bdbe7  mov     rcx, [rbp+200h+var_40]
0x1400bdbee  xor     rcx, rsp; StackCookie
0x1400bdbf1  call    __security_check_cookie
0x1400bdbf6  mov     rbx, [rsp+300h+arg_18]
0x1400bdbfe  add     rsp, 2D0h
0x1400bdc05  pop     r15
0x1400bdc07  pop     r14
0x1400bdc09  pop     r13
0x1400bdc0b  pop     r12
0x1400bdc0d  pop     rdi
0x1400bdc0e  pop     rsi
0x1400bdc0f  pop     rbp
0x1400bdc10  retn
```
