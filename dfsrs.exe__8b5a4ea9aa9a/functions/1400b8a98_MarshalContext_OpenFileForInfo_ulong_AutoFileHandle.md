# MarshalContext::OpenFileForInfo(ulong,AutoFileHandle &)

- ea: `0x1400b8a98`
- end: `0x1400b8d93`
- name: `?OpenFileForInfo@MarshalContext@@IEAAPEAVFrsStatus@@KAEAVAutoFileHandle@@@Z`
- size: `763`
- prototype: `struct FrsStatus *(MarshalContext *__hidden this, unsigned int, struct AutoFileHandle *)`
- caller_count: `2`
- callee_count: `8`
- tags: `file_ops, loader_planting`

## callers

- `0x1400b7364`
- `0x1400b7490`

## callees

- `0x1400036a0`
- `0x14000cdc0`
- `0x14000e34c`
- `0x1400b6eb8`
- `0x1400b8a98`
- `0x1400bf3b8`
- `0x1401b90b4`
- `0x1401b9494`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x1400b8b38`
- `KERNEL32!GetCurrentThreadId` at `0x1400b8c1c`
- `KERNEL32!GetCurrentThreadId` at `0x1400b8d2f`
- `KERNEL32!GetCurrentThreadId` at `0x1400b8b38`
- `KERNEL32!GetCurrentThreadId` at `0x1400b8c1c`
- `KERNEL32!GetCurrentThreadId` at `0x1400b8d2f`
- `ntdll!RtlNtStatusToDosError` at `0x1400b8b48`
- `ntdll!RtlNtStatusToDosError` at `0x1400b8c2c`
- `ntdll!RtlNtStatusToDosError` at `0x1400b8b48`
- `ntdll!RtlNtStatusToDosError` at `0x1400b8c2c`
- `ntdll!NtCreateFile` at `0x1400b8b2a`
- `ntdll!NtCreateFile` at `0x1400b8c0e`
- `ntdll!NtCreateFile` at `0x1400b8b2a`
- `ntdll!NtCreateFile` at `0x1400b8c0e`

## string_xrefs

- `0x1400b8b59`: `MarshalContext::OpenFileForInfo`
- `0x1400b8c3d`: `MarshalContext::OpenFileForInfo`
- `0x1400b8ca6`: `MarshalContext::OpenFileForInfo`

## pseudocode

```c
struct FrsStatus *__fastcall MarshalContext::OpenFileForInfo(MarshalContext *this, ACCESS_MASK a2, void **a3)
{
  bool v3; // cf
  __int64 v5; // r14
  ULONG CreateOptions; // r13d
  __int16 v7; // r12
  NTSTATUS v8; // ebx
  DWORD CurrentThreadId; // edi
  ULONG v10; // eax
  __int64 v11; // rcx
  struct FrsStatus *v12; // rax
  struct FrsStatus *appended; // rsi
  NTSTATUS v14; // ebx
  DWORD v15; // edi
  ULONG v16; // eax
  __int64 v17; // rcx
  FrsStatus *FileInfo; // rax
  MarshalContext *v19; // rcx
  __int64 *v20; // rax
  __int64 v21; // rcx
  DWORD v22; // eax
  __int64 v23; // rcx
  struct FrsStatus *v25; // [rsp+60h] [rbp-49h] BYREF
  POBJECT_ATTRIBUTES ObjectAttributes; // [rsp+68h] [rbp-41h]
  MarshalContext *v27; // [rsp+70h] [rbp-39h]
  const wchar_t *v28; // [rsp+78h] [rbp-31h] BYREF
  int v29; // [rsp+80h] [rbp-29h]
  int v30; // [rsp+84h] [rbp-25h]
  const wchar_t *v31; // [rsp+88h] [rbp-21h]
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+90h] [rbp-19h] BYREF
  struct _FILE_BASIC_INFORMATION v33; // [rsp+A0h] [rbp-9h] BYREF

  v3 = *((_DWORD *)this + 3) != 0;
  v27 = this;
  ObjectAttributes = (POBJECT_ATTRIBUTES)((char *)this + 112);
  v5 = 0;
  CreateOptions = (v3 ? 0x2000 : 0) | 0x604024;
  v7 = a2;
  IoStatusBlock = 0;
  v8 = NtCreateFile(
         a3,
         a2,
         (POBJECT_ATTRIBUTES)((char *)this + 112),
         &IoStatusBlock,
         0,
         0x80u,
         7u,
         1u,
         CreateOptions,
         0,
         0);
  CurrentThreadId = GetCurrentThreadId();
  v10 = RtlNtStatusToDosError(v8);
  v12 = (struct FrsStatus *)FrsStatusList::PushNewError(
                              v11,
                              v10,
                              0,
                              1,
                              "base\\fs\\remotefs\\frs\\src\\fs\\marshaller.cpp",
                              "MarshalContext::OpenFileForInfo",
                              3091,
                              CurrentThreadId,
                              0);
  v25 = v12;
  appended = v12;
  if ( v12 && *((_DWORD *)v12 + 1) == 5 && (v7 & 3) != 0 )
  {
    memset(&v33, 0, sizeof(v33));
    v14 = NtCreateFile(
            a3,
            (v7 & 1) != 0 ? 17956992 : 18612480,
            ObjectAttributes,
            &IoStatusBlock,
            0,
            0x80u,
            7u,
            1u,
            CreateOptions,
            0,
            0);
    v15 = GetCurrentThreadId();
    v16 = RtlNtStatusToDosError(v14);
    FileInfo = (FrsStatus *)FrsStatusList::PushNewError(
                              v17,
                              v16,
                              0,
                              1,
                              "base\\fs\\remotefs\\frs\\src\\fs\\marshaller.cpp",
                              "MarshalContext::OpenFileForInfo",
                              3129,
                              v15,
                              0);
    if ( FileInfo || (FileInfo = MarshalContext::GetFileInfo(v19, (struct AutoFileHandle *)a3, &v33)) != 0 )
    {
      appended = FrsStatus::AppendError(FileInfo, appended);
    }
    else if ( (v33.FileAttributes & 0x4000) != 0 )
    {
      if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 4 )
      {
        v29 = 3149;
        v28 = L"MarshalContext::OpenFileForInfo";
        v30 = 4;
        v31 = L"MRSH";
        dbgobj::DbgPrint<unsigned short,FrsStatus>(&v28, L"(Ignored) %?", appended);
      }
      CLEAR_ERROR(&v25);
      appended = v25;
    }
  }
  if ( appended
    || (v7 & 0x100) != 0
    && ((v20 = (__int64 *)*((_QWORD *)v27 + 37)) == 0 ? (v21 = -1) : (v21 = *v20),
        (appended = FileUtil::MarkHandle((void *)v21, *a3)) != 0) )
  {
    v22 = GetCurrentThreadId();
    return (struct FrsStatus *)FrsStatusList::PushNewError(
                                 v23,
                                 *((unsigned int *)appended + 1),
                                 *((unsigned int *)appended + 2),
                                 *(unsigned int *)appended,
                                 "base\\fs\\remotefs\\frs\\src\\fs\\marshaller.cpp",
                                 "MarshalContext::OpenFileForInfo",
                                 3174,
                                 v22,
                                 appended);
  }
  return (struct FrsStatus *)v5;
}

```

## disassembly

```asm
0x1400b8a98  mov     [rsp-8+arg_18], rbx
0x1400b8a9d  push    rbp
0x1400b8a9e  push    rsi
0x1400b8a9f  push    rdi
0x1400b8aa0  push    r12
0x1400b8aa2  push    r13
0x1400b8aa4  push    r14
0x1400b8aa6  push    r15
0x1400b8aa8  lea     rbp, [rsp-27h]
0x1400b8aad  sub     rsp, 0D0h
0x1400b8ab4  mov     rax, cs:__security_cookie
0x1400b8abb  xor     rax, rsp
0x1400b8abe  mov     [rbp+57h+var_38], rax
0x1400b8ac2  mov     eax, [rcx+0Ch]
0x1400b8ac5  lea     r9, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x1400b8ac9  neg     eax
0x1400b8acb  mov     [rbp+57h+var_90], rcx
0x1400b8acf  lea     rax, [rcx+70h]
0x1400b8ad3  mov     r15, r8
0x1400b8ad6  sbb     r13d, r13d
0x1400b8ad9  mov     [rbp+57h+ObjectAttributes], rax
0x1400b8add  xor     r14d, r14d
0x1400b8ae0  xorps   xmm0, xmm0
0x1400b8ae3  mov     [rsp+100h+EaLength], r14d; EaLength
0x1400b8ae8  and     r13d, 2000h
0x1400b8aef  mov     [rsp+100h+EaBuffer], r14; EaBuffer
0x1400b8af4  or      r13d, 604024h
0x1400b8afb  mov     [rsp+100h+CreateOptions], r13d; CreateOptions
0x1400b8b00  mov     r8, rax; ObjectAttributes
0x1400b8b03  lea     esi, [r14+1]
0x1400b8b07  mov     rcx, r15; FileHandle
0x1400b8b0a  mov     [rsp+100h+CreateDisposition], esi; CreateDisposition
0x1400b8b0e  mov     r12d, edx
0x1400b8b11  mov     [rsp+100h+ShareAccess], 7; ShareAccess
0x1400b8b19  mov     [rsp+100h+FileAttributes], 80h; FileAttributes
0x1400b8b21  mov     [rsp+100h+AllocationSize], r14; AllocationSize
0x1400b8b26  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm0
0x1400b8b2a  call    cs:__imp_NtCreateFile
0x1400b8b31  nop     dword ptr [rax+rax+00h]
0x1400b8b36  mov     ebx, eax
0x1400b8b38  call    cs:__imp_GetCurrentThreadId
0x1400b8b3f  nop     dword ptr [rax+rax+00h]
0x1400b8b44  mov     ecx, ebx; Status
0x1400b8b46  mov     edi, eax
0x1400b8b48  call    cs:__imp_RtlNtStatusToDosError
0x1400b8b4f  nop     dword ptr [rax+rax+00h]
0x1400b8b54  mov     qword ptr [rsp+100h+CreateOptions], r14
0x1400b8b59  lea     rbx, aMarshalcontext_21; "MarshalContext::OpenFileForInfo"
0x1400b8b60  mov     [rsp+100h+CreateDisposition], edi
0x1400b8b64  mov     r9d, esi
0x1400b8b67  mov     [rsp+100h+ShareAccess], 0C13h
0x1400b8b6f  lea     rdi, dwCreationFlags; "base\\fs\\remotefs\\frs\\src\\fs\\marsh"...
0x1400b8b76  mov     qword ptr [rsp+100h+FileAttributes], rbx
0x1400b8b7b  xor     r8d, r8d
0x1400b8b7e  mov     edx, eax
0x1400b8b80  mov     [rsp+100h+AllocationSize], rdi
0x1400b8b85  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x1400b8b8a  mov     [rbp+57h+var_A0], rax
0x1400b8b8e  mov     rsi, rax
0x1400b8b91  test    rax, rax
0x1400b8b94  jz      loc_1400B8CFA
0x1400b8b9a  cmp     dword ptr [rax+4], 5
0x1400b8b9e  jnz     loc_1400B8CFA
0x1400b8ba4  test    r12b, 3
0x1400b8ba8  jz      loc_1400B8CFA
0x1400b8bae  mov     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x1400b8bb2  lea     r9, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x1400b8bb6  mov     [rsp+100h+EaLength], r14d; EaLength
0x1400b8bbb  xor     eax, eax
0x1400b8bbd  mov     [rsp+100h+EaBuffer], r14; EaBuffer
0x1400b8bc2  xorps   xmm0, xmm0
0x1400b8bc5  mov     dword ptr [rbp+57h+var_60+24h], eax
0x1400b8bc8  mov     rcx, r15; FileHandle
0x1400b8bcb  mov     [rsp+100h+CreateOptions], r13d; CreateOptions
0x1400b8bd0  mov     eax, r12d
0x1400b8bd3  mov     [rsp+100h+CreateDisposition], 1; CreateDisposition
0x1400b8bdb  and     al, 1
0x1400b8bdd  neg     al
0x1400b8bdf  mov     [rsp+100h+ShareAccess], 7; ShareAccess
0x1400b8be7  mov     [rsp+100h+FileAttributes], 80h; FileAttributes
0x1400b8bef  sbb     edx, edx
0x1400b8bf1  mov     dword ptr [rbp+57h+var_60.CreationTime], r14d
0x1400b8bf5  and     edx, 0FFF5FF80h
0x1400b8bfb  mov     [rsp+100h+AllocationSize], r14; AllocationSize
0x1400b8c00  add     edx, 11C0100h; DesiredAccess
0x1400b8c06  movups  xmmword ptr [rbp+57h+var_60.CreationTime+4], xmm0
0x1400b8c0a  movups  xmmword ptr [rbp+57h+var_60.LastWriteTime+4], xmm0
0x1400b8c0e  call    cs:__imp_NtCreateFile
0x1400b8c15  nop     dword ptr [rax+rax+00h]
0x1400b8c1a  mov     ebx, eax
0x1400b8c1c  call    cs:__imp_GetCurrentThreadId
0x1400b8c23  nop     dword ptr [rax+rax+00h]
0x1400b8c28  mov     ecx, ebx; Status
0x1400b8c2a  mov     edi, eax
0x1400b8c2c  call    cs:__imp_RtlNtStatusToDosError
0x1400b8c33  nop     dword ptr [rax+rax+00h]
0x1400b8c38  mov     qword ptr [rsp+100h+CreateOptions], r14
0x1400b8c3d  lea     rbx, aMarshalcontext_21; "MarshalContext::OpenFileForInfo"
0x1400b8c44  mov     [rsp+100h+CreateDisposition], edi
0x1400b8c48  lea     r9d, [r14+1]
0x1400b8c4c  mov     [rsp+100h+ShareAccess], 0C39h
0x1400b8c54  lea     rdi, dwCreationFlags; "base\\fs\\remotefs\\frs\\src\\fs\\marsh"...
0x1400b8c5b  mov     qword ptr [rsp+100h+FileAttributes], rbx
0x1400b8c60  xor     r8d, r8d
0x1400b8c63  mov     edx, eax
0x1400b8c65  mov     [rsp+100h+AllocationSize], rdi
0x1400b8c6a  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x1400b8c6f  test    rax, rax
0x1400b8c72  jnz     short loc_1400B8CEC
0x1400b8c74  lea     r8, [rbp+57h+var_60]; struct _FILE_BASIC_INFORMATION *
0x1400b8c78  mov     rdx, r15; struct AutoFileHandle *
0x1400b8c7b  call    ?GetFileInfo@MarshalContext@@IEAAPEAVFrsStatus@@AEAVAutoFileHandle@@AEAU_FILE_BASIC_INFORMATION@@@Z; MarshalContext::GetFileInfo(AutoFileHandle &,_FILE_BASIC_INFORMATION &)
0x1400b8c80  test    rax, rax
0x1400b8c83  jnz     short loc_1400B8CEC
0x1400b8c85  test    [rbp+57h+var_60.FileAttributes], 4000h
0x1400b8c8c  jz      short loc_1400B8CFA
0x1400b8c8e  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x1400b8c95  test    rax, rax
0x1400b8c98  jz      short loc_1400B8CDD
0x1400b8c9a  cmp     [rax+40h], r14d
0x1400b8c9e  jz      short loc_1400B8CDD
0x1400b8ca0  cmp     dword ptr [rax+38h], 4
0x1400b8ca4  jl      short loc_1400B8CDD
0x1400b8ca6  lea     rax, aMarshalcontext_2; "MarshalContext::OpenFileForInfo"
0x1400b8cad  mov     [rbp+57h+var_80], 0C4Dh
0x1400b8cb4  mov     [rbp+57h+var_88], rax
0x1400b8cb8  lea     rdx, aIgnored_0; "(Ignored) %?"
0x1400b8cbf  lea     rax, aMrsh; "MRSH"
0x1400b8cc6  mov     [rbp+57h+var_7C], 4
0x1400b8ccd  mov     r8, rsi
0x1400b8cd0  mov     [rbp+57h+var_78], rax
0x1400b8cd4  lea     rcx, [rbp+57h+var_88]
0x1400b8cd8  call    ??$DbgPrint@GVFrsStatus@@@dbgobj@@QEAA_KPEBGAEBVFrsStatus@@@Z; dbgobj::DbgPrint<ushort,FrsStatus>(ushort const *,FrsStatus const &)
0x1400b8cdd  lea     rcx, [rbp+57h+var_A0]; struct FrsStatus **
0x1400b8ce1  call    ?CLEAR_ERROR@@YAXAEAPEAVFrsStatus@@@Z; CLEAR_ERROR(FrsStatus * &)
0x1400b8ce6  mov     rsi, [rbp+57h+var_A0]
0x1400b8cea  jmp     short loc_1400B8CFA
0x1400b8cec  mov     rdx, rsi; struct FrsStatus *
0x1400b8cef  mov     rcx, rax; this
0x1400b8cf2  call    ?AppendError@FrsStatus@@QEAAPEAV1@PEAV1@@Z; FrsStatus::AppendError(FrsStatus *)
0x1400b8cf7  mov     rsi, rax
0x1400b8cfa  test    rsi, rsi
0x1400b8cfd  jnz     short loc_1400B8D2F
0x1400b8cff  bt      r12d, 8
0x1400b8d04  jnb     short loc_1400B8D68
0x1400b8d06  mov     rax, [rbp+57h+var_90]
0x1400b8d0a  mov     rax, [rax+128h]
0x1400b8d11  test    rax, rax
0x1400b8d14  jz      short loc_1400B8D1B
0x1400b8d16  mov     rcx, [rax]
0x1400b8d19  jmp     short loc_1400B8D1F
0x1400b8d1b  or      rcx, 0FFFFFFFFFFFFFFFFh; void *
0x1400b8d1f  mov     rdx, [r15]; void *
0x1400b8d22  call    ?MarkHandle@FileUtil@@SAPEAVFrsStatus@@PEAX0@Z; FileUtil::MarkHandle(void *,void *)
0x1400b8d27  mov     rsi, rax
0x1400b8d2a  test    rax, rax
0x1400b8d2d  jz      short loc_1400B8D68
0x1400b8d2f  call    cs:__imp_GetCurrentThreadId
0x1400b8d36  nop     dword ptr [rax+rax+00h]
0x1400b8d3b  mov     r9d, [rsi]
0x1400b8d3e  mov     r8d, [rsi+8]
0x1400b8d42  mov     edx, [rsi+4]
0x1400b8d45  mov     qword ptr [rsp+100h+CreateOptions], rsi
0x1400b8d4a  mov     [rsp+100h+CreateDisposition], eax
0x1400b8d4e  mov     [rsp+100h+ShareAccess], 0C66h
0x1400b8d56  mov     qword ptr [rsp+100h+FileAttributes], rbx
0x1400b8d5b  mov     [rsp+100h+AllocationSize], rdi
0x1400b8d60  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x1400b8d65  mov     r14, rax
0x1400b8d68  mov     rax, r14
0x1400b8d6b  mov     rcx, [rbp+57h+var_38]
0x1400b8d6f  xor     rcx, rsp; StackCookie
0x1400b8d72  call    __security_check_cookie
0x1400b8d77  mov     rbx, [rsp+100h+arg_18]
0x1400b8d7f  add     rsp, 0D0h
0x1400b8d86  pop     r15
0x1400b8d88  pop     r14
0x1400b8d8a  pop     r13
0x1400b8d8c  pop     r12
0x1400b8d8e  pop     rdi
0x1400b8d8f  pop     rsi
0x1400b8d90  pop     rbp
0x1400b8d91  retn
```
