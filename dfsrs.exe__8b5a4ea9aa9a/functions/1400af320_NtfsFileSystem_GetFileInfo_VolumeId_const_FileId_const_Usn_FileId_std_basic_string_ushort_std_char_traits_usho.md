# NtfsFileSystem::GetFileInfo(VolumeId const &,FileId const &,Usn *,FileId *,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> *,FilePath *,_BY_HANDLE_FILE_INFORMATION *,_FILE_BASIC_INFORMATION *,_FILE_STANDARD_INFORMATION *)

- ea: `0x1400af320`
- end: `0x1400af619`
- name: `?GetFileInfo@NtfsFileSystem@@UEAAPEAVFrsStatus@@AEBVVolumeId@@AEBVFileId@@PEAVUsn@@PEAV4@PEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAVFilePath@@PEAU_BY_HANDLE_FILE_INFORMATION@@PEAU_FILE_BASIC_INFORMATION@@PEAU_FILE_STANDARD_INFORMATION@@@Z`
- size: `761`
- prototype: ``
- caller_count: `20`
- callee_count: `8`
- tags: `loader_planting`

## callers

- `0x140032320`
- `0x140032a14`
- `0x140038960`
- `0x14003fb40`
- `0x1400a1fd0`
- `0x1400fe434`
- `0x140103d34`
- `0x14010a058`
- `0x14010f2ec`
- `0x14010f9f8`
- `0x140110850`
- `0x1401127a4`
- `0x14011541c`
- `0x14011734c`
- `0x140147090`
- `0x140171298`
- `0x140180fbc`
- `0x1401877d0`
- `0x140188594`
- `0x14019555c`

## callees

- `0x14005c620`
- `0x140089c5c`
- `0x1400af320`
- `0x1400bef20`
- `0x1400bf79c`
- `0x1400bf870`
- `0x1400c03ec`
- `0x1401b9494`

## import_xrefs

- `KERNEL32!GetFileInformationByHandle` at `0x1400af420`
- `KERNEL32!GetFileInformationByHandle` at `0x1400af420`
- `KERNEL32!GetLastError` at `0x1400af43e`
- `KERNEL32!GetLastError` at `0x1400af43e`
- `KERNEL32!GetCurrentThreadId` at `0x1400af430`
- `KERNEL32!GetCurrentThreadId` at `0x1400af4c5`
- `KERNEL32!GetCurrentThreadId` at `0x1400af550`
- `KERNEL32!GetCurrentThreadId` at `0x1400af5a8`
- `KERNEL32!GetCurrentThreadId` at `0x1400af430`
- `KERNEL32!GetCurrentThreadId` at `0x1400af4c5`
- `KERNEL32!GetCurrentThreadId` at `0x1400af550`
- `KERNEL32!GetCurrentThreadId` at `0x1400af5a8`
- `ntdll!RtlNtStatusToDosError` at `0x1400af4d5`
- `ntdll!RtlNtStatusToDosError` at `0x1400af560`
- `ntdll!RtlNtStatusToDosError` at `0x1400af4d5`
- `ntdll!RtlNtStatusToDosError` at `0x1400af560`
- `ntdll!NtQueryInformationFile` at `0x1400af4b7`
- `ntdll!NtQueryInformationFile` at `0x1400af542`
- `ntdll!NtQueryInformationFile` at `0x1400af4b7`
- `ntdll!NtQueryInformationFile` at `0x1400af542`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall NtfsFileSystem::GetFileInfo(
        __int64 a1,
        const struct VolumeId *a2,
        unsigned __int64 *a3,
        __int64 a4,
        __int64 a5,
        void *a6,
        struct FilePath *a7,
        struct _BY_HANDLE_FILE_INFORMATION *lpFileInformation,
        PVOID FileInformation,
        PVOID a10)
{
  __int64 v13; // rdi
  __int64 v14; // rsi
  struct FrsStatus *FullPathFromHandle; // rbx
  DWORD CurrentThreadId; // ebx
  DWORD LastError; // eax
  __int64 v18; // rcx
  NTSTATUS v19; // ebx
  DWORD v20; // edi
  ULONG v21; // eax
  __int64 v22; // rcx
  NTSTATUS v23; // ebx
  DWORD v24; // edi
  ULONG v25; // eax
  __int64 v26; // rcx
  DWORD v27; // eax
  __int64 v28; // rcx
  __int64 *v30; // [rsp+58h] [rbp-39h] BYREF
  HANDLE hFile; // [rsp+60h] [rbp-31h] BYREF
  int v32; // [rsp+68h] [rbp-29h]
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+70h] [rbp-21h] BYREF
  struct _IO_STATUS_BLOCK v34; // [rsp+80h] [rbp-11h] BYREF

  v13 = -1;
  hFile = (HANDLE)-1LL;
  v32 = 1;
  v14 = 0;
  v30 = 0;
  FullPathFromHandle = VolumeHandle::Open((VolumeHandle *)&v30, a2);
  if ( FullPathFromHandle )
    goto LABEL_18;
  if ( v30 )
    v13 = *v30;
  FullPathFromHandle = FileUtil::OpenByReferenceNumber(&hFile, (void *)v13, *a3, 0x100080u, 0x606024u, 7u);
  if ( FullPathFromHandle )
    goto LABEL_18;
  if ( a7 )
  {
    FullPathFromHandle = FileUtil::GetFullPathFromHandle(a7, a2, hFile);
    if ( FullPathFromHandle )
      goto LABEL_18;
  }
  if ( a4 || a5 || a6 )
  {
    FullPathFromHandle = (struct FrsStatus *)FileUtil::ReadUsnData((int)hFile, a4, 0, a5, a6);
    if ( FullPathFromHandle )
      goto LABEL_18;
  }
  if ( lpFileInformation )
  {
    if ( !GetFileInformationByHandle(hFile, lpFileInformation) )
    {
      CurrentThreadId = GetCurrentThreadId();
      LastError = GetLastError();
      FullPathFromHandle = (struct FrsStatus *)FrsStatusList::PushNewError(
                                                 v18,
                                                 LastError,
                                                 0,
                                                 1,
                                                 "base\\fs\\remotefs\\frs\\src\\fs\\ntfsfilesystem.cpp",
                                                 "NtfsFileSystem::GetFileInfo",
                                                 2494,
                                                 CurrentThreadId,
                                                 0);
      if ( FullPathFromHandle )
        goto LABEL_18;
    }
  }
  if ( FileInformation )
  {
    IoStatusBlock = 0;
    v19 = NtQueryInformationFile(hFile, &IoStatusBlock, FileInformation, 0x28u, FileBasicInformation);
    v20 = GetCurrentThreadId();
    v21 = RtlNtStatusToDosError(v19);
    FullPathFromHandle = (struct FrsStatus *)FrsStatusList::PushNewError(
                                               v22,
                                               v21,
                                               0,
                                               1,
                                               "base\\fs\\remotefs\\frs\\src\\fs\\ntfsfilesystem.cpp",
                                               "NtfsFileSystem::GetFileInfo",
                                               2504,
                                               v20,
                                               0);
    if ( FullPathFromHandle )
      goto LABEL_18;
  }
  if ( a10 )
  {
    v34 = 0;
    v23 = NtQueryInformationFile(hFile, &v34, a10, 0x18u, FileStandardInformation);
    v24 = GetCurrentThreadId();
    v25 = RtlNtStatusToDosError(v23);
    FullPathFromHandle = (struct FrsStatus *)FrsStatusList::PushNewError(
                                               v26,
                                               v25,
                                               0,
                                               1,
                                               "base\\fs\\remotefs\\frs\\src\\fs\\ntfsfilesystem.cpp",
                                               "NtfsFileSystem::GetFileInfo",
                                               2515,
                                               v24,
                                               0);
    if ( FullPathFromHandle )
    {
LABEL_18:
      v27 = GetCurrentThreadId();
      v14 = FrsStatusList::PushNewError(
              v28,
              *((unsigned int *)FullPathFromHandle + 1),
              *((unsigned int *)FullPathFromHandle + 2),
              *(unsigned int *)FullPathFromHandle,
              "base\\fs\\remotefs\\frs\\src\\fs\\ntfsfilesystem.cpp",
              "NtfsFileSystem::GetFileInfo",
              2518,
              v27,
              FullPathFromHandle);
    }
  }
  VolumeHandle::~VolumeHandle((VolumeHandle *)&v30);
  CloseHandleEx(&hFile);
  return v14;
}

```

## disassembly

```asm
0x1400af320  mov     rax, rsp
0x1400af323  mov     [rax+8], rbx
0x1400af327  mov     [rax+10h], rsi
0x1400af32b  mov     [rax+18h], rdi
0x1400af32f  push    rbp
0x1400af330  push    r12
0x1400af332  push    r13
0x1400af334  push    r14
0x1400af336  push    r15
0x1400af338  lea     rbp, [rax-2Fh]
0x1400af33c  sub     rsp, 90h
0x1400af343  mov     r14, r9
0x1400af346  mov     r12, r8
0x1400af349  mov     r15, rdx
0x1400af34c  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1400af350  mov     [rbp+27h+hFile], rdi
0x1400af354  mov     [rbp+27h+var_50], 1
0x1400af35b  xor     esi, esi
0x1400af35d  mov     [rbp+27h+var_60], rsi
0x1400af361  lea     rcx, [rbp+27h+var_60]; this
0x1400af365  call    ?Open@VolumeHandle@@QEAAPEAVFrsStatus@@AEBVVolumeId@@@Z; VolumeHandle::Open(VolumeId const &)
0x1400af36a  mov     rbx, rax
0x1400af36d  lea     r13, aNtfsfilesystem_13; "NtfsFileSystem::GetFileInfo"
0x1400af374  test    rax, rax
0x1400af377  jnz     loc_1400AF5A1
0x1400af37d  mov     rax, [rbp+27h+var_60]
0x1400af381  test    rax, rax
0x1400af384  jz      short loc_1400AF389
0x1400af386  mov     rdi, [rax]
0x1400af389  mov     [rsp+0B0h+var_88], 7; unsigned int
0x1400af391  mov     [rsp+0B0h+FileInformationClass], 606024h; unsigned int
0x1400af399  mov     r9d, 100080h; unsigned int
0x1400af39f  mov     r8, [r12]; unsigned __int64
0x1400af3a3  mov     rdx, rdi; void *
0x1400af3a6  lea     rcx, [rbp+27h+hFile]; void **
0x1400af3aa  call    ?OpenByReferenceNumber@FileUtil@@SAPEAVFrsStatus@@AEAPEAXPEAX_KKKK@Z; FileUtil::OpenByReferenceNumber(void * &,void *,unsigned __int64,ulong,ulong,ulong)
0x1400af3af  mov     rbx, rax
0x1400af3b2  test    rax, rax
0x1400af3b5  jnz     loc_1400AF5A1
0x1400af3bb  mov     rcx, [rbp+27h+arg_30]; this
0x1400af3bf  test    rcx, rcx
0x1400af3c2  jz      short loc_1400AF3DC
0x1400af3c4  mov     r8, [rbp+27h+hFile]; void *
0x1400af3c8  mov     rdx, r15; struct VolumeId *
0x1400af3cb  call    ?GetFullPathFromHandle@FileUtil@@SAPEAVFrsStatus@@AEAVFilePath@@AEBVVolumeId@@PEAX@Z; FileUtil::GetFullPathFromHandle(FilePath &,VolumeId const &,void *)
0x1400af3d0  mov     rbx, rax
0x1400af3d3  test    rax, rax
0x1400af3d6  jnz     loc_1400AF5A1
0x1400af3dc  mov     rax, [rbp+27h+arg_28]
0x1400af3e0  mov     r9, [rbp+27h+arg_20]; int
0x1400af3e4  test    r14, r14
0x1400af3e7  jnz     short loc_1400AF3F3
0x1400af3e9  test    r9, r9
0x1400af3ec  jnz     short loc_1400AF3F3
0x1400af3ee  test    rax, rax
0x1400af3f1  jz      short loc_1400AF413
0x1400af3f3  mov     qword ptr [rsp+0B0h+FileInformationClass], rax; void *
0x1400af3f8  xor     r8d, r8d; int
0x1400af3fb  mov     rdx, r14; int
0x1400af3fe  mov     rcx, [rbp+27h+hFile]; int
0x1400af402  call    ?ReadUsnData@FileUtil@@SAPEAVFrsStatus@@PEAXPEAVUsn@@PEAVFileId@@2PEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; FileUtil::ReadUsnData(void *,Usn *,FileId *,FileId *,std::wstring *)
0x1400af407  mov     rbx, rax
0x1400af40a  test    rax, rax
0x1400af40d  jnz     loc_1400AF5A1
0x1400af413  mov     rdx, [rbp+27h+lpFileInformation]; lpFileInformation
0x1400af417  test    rdx, rdx
0x1400af41a  jz      short loc_1400AF48A
0x1400af41c  mov     rcx, [rbp+27h+hFile]; hFile
0x1400af420  call    cs:__imp_GetFileInformationByHandle
0x1400af427  nop     dword ptr [rax+rax+00h]
0x1400af42c  test    eax, eax
0x1400af42e  jnz     short loc_1400AF48A
0x1400af430  call    cs:__imp_GetCurrentThreadId
0x1400af437  nop     dword ptr [rax+rax+00h]
0x1400af43c  mov     ebx, eax
0x1400af43e  call    cs:__imp_GetLastError
0x1400af445  nop     dword ptr [rax+rax+00h]
0x1400af44a  mov     [rsp+0B0h+var_70], rsi
0x1400af44f  mov     dword ptr [rsp+0B0h+var_78], ebx
0x1400af453  mov     [rsp+0B0h+var_80], 9BEh
0x1400af45b  mov     qword ptr [rsp+0B0h+var_88], r13
0x1400af460  lea     r14, aBaseFsRemotefs_106; "base\\fs\\remotefs\\frs\\src\\fs\\ntfsf"...
0x1400af467  mov     qword ptr [rsp+0B0h+FileInformationClass], r14
0x1400af46c  mov     r9d, 1
0x1400af472  xor     r8d, r8d
0x1400af475  mov     edx, eax
0x1400af477  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x1400af47c  mov     rbx, rax
0x1400af47f  test    rax, rax
0x1400af482  jnz     loc_1400AF5A8
0x1400af488  jmp     short loc_1400AF491
0x1400af48a  lea     r14, aBaseFsRemotefs_106; "base\\fs\\remotefs\\frs\\src\\fs\\ntfsf"...
0x1400af491  mov     r8, [rbp+27h+FileInformation]; FileInformation
0x1400af495  test    r8, r8
0x1400af498  jz      short loc_1400AF518
0x1400af49a  xorps   xmm0, xmm0
0x1400af49d  movups  xmmword ptr [rbp+27h+IoStatusBlock], xmm0
0x1400af4a1  mov     [rsp+0B0h+FileInformationClass], 4; FileInformationClass
0x1400af4a9  mov     r9d, 28h ; '('; Length
0x1400af4af  lea     rdx, [rbp+27h+IoStatusBlock]; IoStatusBlock
0x1400af4b3  mov     rcx, [rbp+27h+hFile]; FileHandle
0x1400af4b7  call    cs:__imp_NtQueryInformationFile
0x1400af4be  nop     dword ptr [rax+rax+00h]
0x1400af4c3  mov     ebx, eax
0x1400af4c5  call    cs:__imp_GetCurrentThreadId
0x1400af4cc  nop     dword ptr [rax+rax+00h]
0x1400af4d1  mov     edi, eax
0x1400af4d3  mov     ecx, ebx; Status
0x1400af4d5  call    cs:__imp_RtlNtStatusToDosError
0x1400af4dc  nop     dword ptr [rax+rax+00h]
0x1400af4e1  mov     [rsp+0B0h+var_70], rsi
0x1400af4e6  mov     dword ptr [rsp+0B0h+var_78], edi
0x1400af4ea  mov     [rsp+0B0h+var_80], 9C8h
0x1400af4f2  mov     qword ptr [rsp+0B0h+var_88], r13
0x1400af4f7  mov     qword ptr [rsp+0B0h+FileInformationClass], r14
0x1400af4fc  mov     r9d, 1
0x1400af502  xor     r8d, r8d
0x1400af505  mov     edx, eax
0x1400af507  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x1400af50c  mov     rbx, rax
0x1400af50f  test    rax, rax
0x1400af512  jnz     loc_1400AF5A8
0x1400af518  mov     r8, [rbp+27h+arg_48]; FileInformation
0x1400af51c  test    r8, r8
0x1400af51f  jz      loc_1400AF5E1
0x1400af525  xorps   xmm0, xmm0
0x1400af528  movups  xmmword ptr [rbp+27h+var_38], xmm0
0x1400af52c  mov     [rsp+0B0h+FileInformationClass], 5; FileInformationClass
0x1400af534  mov     r9d, 18h; Length
0x1400af53a  lea     rdx, [rbp+27h+var_38]; IoStatusBlock
0x1400af53e  mov     rcx, [rbp+27h+hFile]; FileHandle
0x1400af542  call    cs:__imp_NtQueryInformationFile
0x1400af549  nop     dword ptr [rax+rax+00h]
0x1400af54e  mov     ebx, eax
0x1400af550  call    cs:__imp_GetCurrentThreadId
0x1400af557  nop     dword ptr [rax+rax+00h]
0x1400af55c  mov     edi, eax
0x1400af55e  mov     ecx, ebx; Status
0x1400af560  call    cs:__imp_RtlNtStatusToDosError
0x1400af567  nop     dword ptr [rax+rax+00h]
0x1400af56c  mov     [rsp+0B0h+var_70], rsi
0x1400af571  mov     dword ptr [rsp+0B0h+var_78], edi
0x1400af575  mov     [rsp+0B0h+var_80], 9D3h
0x1400af57d  mov     qword ptr [rsp+0B0h+var_88], r13
0x1400af582  mov     qword ptr [rsp+0B0h+FileInformationClass], r14
0x1400af587  mov     r9d, 1
0x1400af58d  xor     r8d, r8d
0x1400af590  mov     edx, eax
0x1400af592  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x1400af597  mov     rbx, rax
0x1400af59a  test    rax, rax
0x1400af59d  jnz     short loc_1400AF5A8
0x1400af59f  jmp     short loc_1400AF5E1
0x1400af5a1  lea     r14, aBaseFsRemotefs_106; "base\\fs\\remotefs\\frs\\src\\fs\\ntfsf"...
0x1400af5a8  call    cs:__imp_GetCurrentThreadId
0x1400af5af  nop     dword ptr [rax+rax+00h]
0x1400af5b4  mov     [rsp+0B0h+var_70], rbx
0x1400af5b9  mov     dword ptr [rsp+0B0h+var_78], eax
0x1400af5bd  mov     [rsp+0B0h+var_80], 9D6h
0x1400af5c5  mov     qword ptr [rsp+0B0h+var_88], r13
0x1400af5ca  mov     qword ptr [rsp+0B0h+FileInformationClass], r14
0x1400af5cf  mov     r9d, [rbx]
0x1400af5d2  mov     r8d, [rbx+8]
0x1400af5d6  mov     edx, [rbx+4]
0x1400af5d9  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x1400af5de  mov     rsi, rax
0x1400af5e1  lea     rcx, [rbp+27h+var_60]; this
0x1400af5e5  call    ??1VolumeHandle@@QEAA@XZ; VolumeHandle::~VolumeHandle(void)
0x1400af5ea  nop
0x1400af5eb  lea     rcx, [rbp+27h+hFile]; void **
0x1400af5ef  call    ?CloseHandleEx@@YAXAEAPEAX@Z; CloseHandleEx(void * &)
0x1400af5f4  mov     rax, rsi
0x1400af5f7  lea     r11, [rsp+0B0h+var_20]
0x1400af5ff  mov     rbx, [r11+30h]
0x1400af603  mov     rsi, [r11+38h]
0x1400af607  mov     rdi, [r11+40h]
0x1400af60b  mov     rsp, r11
0x1400af60e  pop     r15
0x1400af610  pop     r14
0x1400af612  pop     r13
0x1400af614  pop     r12
0x1400af616  pop     rbp
0x1400af617  retn
```
