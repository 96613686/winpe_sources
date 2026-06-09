# FileUtil::OpenFileForInfo(void *,_OBJECT_ATTRIBUTES const &,int,ulong,void * &,_FILE_BASIC_INFORMATION &,_FILE_ATTRIBUTE_TAG_INFORMATION &)

- ea: `0x1400bf974`
- end: `0x1400bfbb9`
- name: `?OpenFileForInfo@FileUtil@@SAPEAVFrsStatus@@PEAXAEBU_OBJECT_ATTRIBUTES@@HKAEAPEAXAEAU_FILE_BASIC_INFORMATION@@AEAU_FILE_ATTRIBUTE_TAG_INFORMATION@@@Z`
- size: `581`
- prototype: `struct FrsStatus *__usercall@<rax>(void *@<rcx>, POBJECT_ATTRIBUTES ObjectAttributes@<rdx>, int@<r8d>, unsigned int@<r9d>, PHANDLE FileHandle, struct _FILE_BASIC_INFORMATION *, struct _FILE_ATTRIBUTE_TAG_INFORMATION *)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, loader_planting`

## callers

- `0x1400c0078`

## callees

- `0x1400bf3b8`
- `0x1400bf974`
- `0x1401b9494`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x1400bf9e9`
- `KERNEL32!GetCurrentThreadId` at `0x1400bfa95`
- `KERNEL32!GetCurrentThreadId` at `0x1400bfb0e`
- `KERNEL32!GetCurrentThreadId` at `0x1400bfb5d`
- `KERNEL32!GetCurrentThreadId` at `0x1400bf9e9`
- `KERNEL32!GetCurrentThreadId` at `0x1400bfa95`
- `KERNEL32!GetCurrentThreadId` at `0x1400bfb0e`
- `KERNEL32!GetCurrentThreadId` at `0x1400bfb5d`
- `ntdll!RtlNtStatusToDosError` at `0x1400bf9f9`
- `ntdll!RtlNtStatusToDosError` at `0x1400bfaa5`
- `ntdll!RtlNtStatusToDosError` at `0x1400bfb1e`
- `ntdll!RtlNtStatusToDosError` at `0x1400bf9f9`
- `ntdll!RtlNtStatusToDosError` at `0x1400bfaa5`
- `ntdll!RtlNtStatusToDosError` at `0x1400bfb1e`
- `ntdll!NtQueryInformationFile` at `0x1400bfa87`
- `ntdll!NtQueryInformationFile` at `0x1400bfb00`
- `ntdll!NtQueryInformationFile` at `0x1400bfa87`
- `ntdll!NtQueryInformationFile` at `0x1400bfb00`
- `ntdll!NtCreateFile` at `0x1400bf9db`
- `ntdll!NtCreateFile` at `0x1400bf9db`

## string_xrefs

- `0x1400bfa0a`: `FileUtil::OpenFileForInfo`

## pseudocode

```c
struct FrsStatus *__fastcall FileUtil::OpenFileForInfo(
        void *a1,
        POBJECT_ATTRIBUTES ObjectAttributes,
        __int64 a3,
        __int64 a4,
        PHANDLE FileHandle,
        struct _FILE_BASIC_INFORMATION *FileInformation,
        struct _FILE_ATTRIBUTE_TAG_INFORMATION *a7)
{
  __int64 v7; // rsi
  NTSTATUS v9; // ebx
  DWORD CurrentThreadId; // edi
  ULONG v11; // eax
  __int64 v12; // rcx
  __int64 v13; // rax
  __int64 v14; // rdx
  struct FrsStatus *v15; // rbx
  NTSTATUS v16; // ebx
  DWORD v17; // edi
  ULONG v18; // eax
  __int64 v19; // rcx
  NTSTATUS v20; // ebx
  DWORD v21; // edi
  ULONG v22; // eax
  __int64 v23; // rcx
  DWORD v24; // eax
  __int64 v25; // rcx
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+60h] [rbp-28h] BYREF

  v7 = 0;
  IoStatusBlock = 0;
  v9 = NtCreateFile(FileHandle, 0x100180u, ObjectAttributes, &IoStatusBlock, 0, 0x80u, 7u, 1u, 0x604024u, 0, 0);
  CurrentThreadId = GetCurrentThreadId();
  v11 = RtlNtStatusToDosError(v9);
  v13 = FrsStatusList::PushNewError(
          v12,
          v11,
          0,
          1,
          "base\\fs\\remotefs\\frs\\src\\fs\\fileutil.cpp",
          "FileUtil::OpenFileForInfo",
          884,
          CurrentThreadId,
          0);
  v14 = (__int64)*FileHandle;
  v15 = (struct FrsStatus *)v13;
  if ( !*FileHandle )
  {
    v14 = -1;
    *FileHandle = (void *)-1LL;
  }
  if ( v13 )
    goto LABEL_7;
  v15 = FileUtil::MarkHandle(a1, (void *)v14);
  if ( v15 )
    goto LABEL_7;
  v16 = NtQueryInformationFile(*FileHandle, &IoStatusBlock, FileInformation, 0x28u, FileBasicInformation);
  v17 = GetCurrentThreadId();
  v18 = RtlNtStatusToDosError(v16);
  v15 = (struct FrsStatus *)FrsStatusList::PushNewError(
                              v19,
                              v18,
                              0,
                              1,
                              "base\\fs\\remotefs\\frs\\src\\fs\\fileutil.cpp",
                              "FileUtil::OpenFileForInfo",
                              907,
                              v17,
                              0);
  if ( v15
    || (v20 = NtQueryInformationFile(*FileHandle, &IoStatusBlock, a7, 8u, FileAttributeTagInformation),
        v21 = GetCurrentThreadId(),
        v22 = RtlNtStatusToDosError(v20),
        (v15 = (struct FrsStatus *)FrsStatusList::PushNewError(
                                     v23,
                                     v22,
                                     0,
                                     1,
                                     "base\\fs\\remotefs\\frs\\src\\fs\\fileutil.cpp",
                                     "FileUtil::OpenFileForInfo",
                                     919,
                                     v21,
                                     0)) != 0) )
  {
LABEL_7:
    v24 = GetCurrentThreadId();
    return (struct FrsStatus *)FrsStatusList::PushNewError(
                                 v25,
                                 *((unsigned int *)v15 + 1),
                                 *((unsigned int *)v15 + 2),
                                 *(unsigned int *)v15,
                                 "base\\fs\\remotefs\\frs\\src\\fs\\fileutil.cpp",
                                 "FileUtil::OpenFileForInfo",
                                 922,
                                 v24,
                                 v15);
  }
  return (struct FrsStatus *)v7;
}

```

## disassembly

```asm
0x1400bf974  mov     rax, rsp
0x1400bf977  mov     [rax+8], rbx
0x1400bf97b  mov     [rax+10h], rbp
0x1400bf97f  mov     [rax+18h], rsi
0x1400bf983  mov     [rax+20h], rdi
0x1400bf987  push    r12
0x1400bf989  push    r14
0x1400bf98b  push    r15
0x1400bf98d  sub     rsp, 70h
0x1400bf991  mov     r14, [rsp+88h+FileHandle]
0x1400bf999  lea     r9, [rax-28h]; IoStatusBlock
0x1400bf99d  xor     esi, esi
0x1400bf99f  mov     rbp, rcx
0x1400bf9a2  mov     [rax-38h], esi
0x1400bf9a5  xorps   xmm0, xmm0
0x1400bf9a8  mov     [rax-40h], rsi
0x1400bf9ac  mov     r8, rdx; ObjectAttributes
0x1400bf9af  mov     dword ptr [rax-48h], 604024h
0x1400bf9b6  mov     edx, 100180h; DesiredAccess
0x1400bf9bb  mov     dword ptr [rax-50h], 1
0x1400bf9c2  mov     rcx, r14; FileHandle
0x1400bf9c5  mov     dword ptr [rax-58h], 7
0x1400bf9cc  mov     dword ptr [rax-60h], 80h
0x1400bf9d3  mov     [rax-68h], rsi
0x1400bf9d7  movups  xmmword ptr [rax-28h], xmm0
0x1400bf9db  call    cs:__imp_NtCreateFile
0x1400bf9e2  nop     dword ptr [rax+rax+00h]
0x1400bf9e7  mov     ebx, eax
0x1400bf9e9  call    cs:__imp_GetCurrentThreadId
0x1400bf9f0  nop     dword ptr [rax+rax+00h]
0x1400bf9f5  mov     ecx, ebx; Status
0x1400bf9f7  mov     edi, eax
0x1400bf9f9  call    cs:__imp_RtlNtStatusToDosError
0x1400bfa00  nop     dword ptr [rax+rax+00h]
0x1400bfa05  mov     [rsp+88h+var_48], rsi
0x1400bfa0a  lea     r15, aFileutilOpenfi; "FileUtil::OpenFileForInfo"
0x1400bfa11  mov     [rsp+88h+var_50], edi
0x1400bfa15  lea     r12, aBaseFsRemotefs_24; "base\\fs\\remotefs\\frs\\src\\fs\\fileu"...
0x1400bfa1c  mov     [rsp+88h+var_58], 374h
0x1400bfa24  lea     r9d, [rsi+1]
0x1400bfa28  mov     [rsp+88h+var_60], r15
0x1400bfa2d  xor     r8d, r8d
0x1400bfa30  mov     edx, eax
0x1400bfa32  mov     qword ptr [rsp+88h+FileInformationClass], r12
0x1400bfa37  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x1400bfa3c  mov     rdx, [r14]
0x1400bfa3f  mov     rbx, rax
0x1400bfa42  test    rdx, rdx
0x1400bfa45  jnz     short loc_1400BFA4E
0x1400bfa47  or      rdx, 0FFFFFFFFFFFFFFFFh; void *
0x1400bfa4b  mov     [r14], rdx
0x1400bfa4e  test    rax, rax
0x1400bfa51  jnz     loc_1400BFB5D
0x1400bfa57  mov     rcx, rbp; void *
0x1400bfa5a  call    ?MarkHandle@FileUtil@@SAPEAVFrsStatus@@PEAX0@Z; FileUtil::MarkHandle(void *,void *)
0x1400bfa5f  mov     rbx, rax
0x1400bfa62  test    rax, rax
0x1400bfa65  jnz     loc_1400BFB5D
0x1400bfa6b  mov     r8, [rsp+88h+FileInformation]; FileInformation
0x1400bfa73  lea     r9d, [rax+28h]; Length
0x1400bfa77  mov     rcx, [r14]; FileHandle
0x1400bfa7a  lea     rdx, [rsp+88h+IoStatusBlock]; IoStatusBlock
0x1400bfa7f  mov     [rsp+88h+FileInformationClass], 4; FileInformationClass
0x1400bfa87  call    cs:__imp_NtQueryInformationFile
0x1400bfa8e  nop     dword ptr [rax+rax+00h]
0x1400bfa93  mov     ebx, eax
0x1400bfa95  call    cs:__imp_GetCurrentThreadId
0x1400bfa9c  nop     dword ptr [rax+rax+00h]
0x1400bfaa1  mov     ecx, ebx; Status
0x1400bfaa3  mov     edi, eax
0x1400bfaa5  call    cs:__imp_RtlNtStatusToDosError
0x1400bfaac  nop     dword ptr [rax+rax+00h]
0x1400bfab1  mov     [rsp+88h+var_48], rsi
0x1400bfab6  mov     r9d, 1
0x1400bfabc  mov     [rsp+88h+var_50], edi
0x1400bfac0  xor     r8d, r8d
0x1400bfac3  mov     [rsp+88h+var_58], 38Bh
0x1400bfacb  mov     edx, eax
0x1400bfacd  mov     [rsp+88h+var_60], r15
0x1400bfad2  mov     qword ptr [rsp+88h+FileInformationClass], r12
0x1400bfad7  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x1400bfadc  mov     rbx, rax
0x1400bfadf  test    rax, rax
0x1400bfae2  jnz     short loc_1400BFB5D
0x1400bfae4  mov     r8, [rsp+88h+arg_30]; FileInformation
0x1400bfaec  lea     r9d, [rax+8]; Length
0x1400bfaf0  mov     rcx, [r14]; FileHandle
0x1400bfaf3  lea     rdx, [rsp+88h+IoStatusBlock]; IoStatusBlock
0x1400bfaf8  mov     [rsp+88h+FileInformationClass], 23h ; '#'; FileInformationClass
0x1400bfb00  call    cs:__imp_NtQueryInformationFile
0x1400bfb07  nop     dword ptr [rax+rax+00h]
0x1400bfb0c  mov     ebx, eax
0x1400bfb0e  call    cs:__imp_GetCurrentThreadId
0x1400bfb15  nop     dword ptr [rax+rax+00h]
0x1400bfb1a  mov     ecx, ebx; Status
0x1400bfb1c  mov     edi, eax
0x1400bfb1e  call    cs:__imp_RtlNtStatusToDosError
0x1400bfb25  nop     dword ptr [rax+rax+00h]
0x1400bfb2a  mov     [rsp+88h+var_48], rsi
0x1400bfb2f  mov     r9d, 1
0x1400bfb35  mov     [rsp+88h+var_50], edi
0x1400bfb39  xor     r8d, r8d
0x1400bfb3c  mov     [rsp+88h+var_58], 397h
0x1400bfb44  mov     edx, eax
0x1400bfb46  mov     [rsp+88h+var_60], r15
0x1400bfb4b  mov     qword ptr [rsp+88h+FileInformationClass], r12
0x1400bfb50  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x1400bfb55  mov     rbx, rax
0x1400bfb58  test    rax, rax
0x1400bfb5b  jz      short loc_1400BFB96
0x1400bfb5d  call    cs:__imp_GetCurrentThreadId
0x1400bfb64  nop     dword ptr [rax+rax+00h]
0x1400bfb69  mov     r9d, [rbx]
0x1400bfb6c  mov     r8d, [rbx+8]
0x1400bfb70  mov     edx, [rbx+4]
0x1400bfb73  mov     [rsp+88h+var_48], rbx
0x1400bfb78  mov     [rsp+88h+var_50], eax
0x1400bfb7c  mov     [rsp+88h+var_58], 39Ah
0x1400bfb84  mov     [rsp+88h+var_60], r15
0x1400bfb89  mov     qword ptr [rsp+88h+FileInformationClass], r12
0x1400bfb8e  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x1400bfb93  mov     rsi, rax
0x1400bfb96  lea     r11, [rsp+88h+var_18]
0x1400bfb9b  mov     rax, rsi
0x1400bfb9e  mov     rbx, [r11+20h]
0x1400bfba2  mov     rbp, [r11+28h]
0x1400bfba6  mov     rsi, [r11+30h]
0x1400bfbaa  mov     rdi, [r11+38h]
0x1400bfbae  mov     rsp, r11
0x1400bfbb1  pop     r15
0x1400bfbb3  pop     r14
0x1400bfbb5  pop     r12
0x1400bfbb7  retn
```
