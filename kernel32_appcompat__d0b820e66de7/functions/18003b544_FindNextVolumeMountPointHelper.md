# FindNextVolumeMountPointHelper

- ea: `0x18003b544`
- end: `0x18003bb17`
- name: `FindNextVolumeMountPointHelper`
- size: `1491`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18003b2c0`
- `0x180073ed0`
- `0x180074030`

## callees

- `0x18000ccf0`
- `0x18003b544`
- `0x180082751`
- `0x1800827c0`

## import_xrefs

- `ntdll!NtOpenFile` at `0x18003b6cd`
- `ntdll!NtOpenFile` at `0x18003b6cd`
- `ntdll!NtQueryInformationFile` at `0x18003b9a4`
- `ntdll!NtQueryInformationFile` at `0x18003b9a4`
- `ntdll!RtlSetLastWin32Error` at `0x18003b80d`
- `ntdll!RtlSetLastWin32Error` at `0x18003b80d`
- `ntdll!RtlReleasePrivilege` at `0x18003b6e5`
- `ntdll!RtlReleasePrivilege` at `0x18003b6e5`
- `ntdll!RtlAcquirePrivilege` at `0x18003b696`
- `ntdll!RtlAcquirePrivilege` at `0x18003b696`
- `ntdll!NtQueryDirectoryFile` at `0x18003b62b`
- `ntdll!NtQueryDirectoryFile` at `0x18003b62b`
- `ntdll!RtlFreeHeap` at `0x18003b7aa`
- `ntdll!RtlFreeHeap` at `0x18003b944`
- `ntdll!RtlFreeHeap` at `0x18003b9c8`
- `ntdll!RtlFreeHeap` at `0x18003ba51`
- `ntdll!RtlFreeHeap` at `0x18003baab`
- `ntdll!RtlFreeHeap` at `0x18003bae4`
- `ntdll!RtlFreeHeap` at `0x18003b7aa`
- `ntdll!RtlFreeHeap` at `0x18003b944`
- `ntdll!RtlFreeHeap` at `0x18003b9c8`
- `ntdll!RtlFreeHeap` at `0x18003ba51`
- `ntdll!RtlFreeHeap` at `0x18003baab`
- `ntdll!RtlFreeHeap` at `0x18003bae4`
- `ntdll!RtlAllocateHeap` at `0x18003b71a`
- `ntdll!RtlAllocateHeap` at `0x18003b975`
- `ntdll!RtlAllocateHeap` at `0x18003b71a`
- `ntdll!RtlAllocateHeap` at `0x18003b975`
- `KERNELBASE!KernelBaseGetGlobalData` at `0x18003b6f9`
- `KERNELBASE!KernelBaseGetGlobalData` at `0x18003b957`
- `KERNELBASE!KernelBaseGetGlobalData` at `0x18003b6f9`
- `KERNELBASE!KernelBaseGetGlobalData` at `0x18003b957`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003b7bb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003b7fc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003b9d9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003ba62`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003babc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003baf5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003b7bb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003b7fc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003b9d9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003ba62`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003babc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003baf5`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18003b75e`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18003b75e`

## pseudocode

```c
__int64 __fastcall FindNextVolumeMountPointHelper(__int64 a1, void *a2, int a3, int a4)
{
  NTSTATUS v8; // eax
  NTSTATUS v9; // eax
  __int64 v10; // rdx
  __int64 v11; // r8
  __int64 v12; // r9
  PVOID v13; // rcx
  int v14; // ebx
  ULONG *GlobalData; // rax
  unsigned __int16 *Heap; // rax
  void *v17; // rcx
  unsigned __int16 *v18; // rbx
  __int64 v19; // rax
  ULONG v20; // ecx
  __int16 v22; // cx
  ULONG v23; // edi
  __int64 v24; // rdx
  __int64 v25; // rcx
  __int64 v26; // r8
  __int64 v27; // r9
  ULONG *v28; // rax
  unsigned int *v29; // rax
  unsigned int *v30; // rbx
  NTSTATUS v31; // edi
  __int64 v32; // rcx
  __int128 v33; // xmm0
  unsigned __int64 v34; // rax
  void *FileHandle; // [rsp+60h] [rbp-A0h] BYREF
  ULONG Privilege; // [rsp+68h] [rbp-98h] BYREF
  DWORD BytesReturned; // [rsp+70h] [rbp-90h] BYREF
  PVOID ReturnedState; // [rsp+78h] [rbp-88h] BYREF
  struct _UNICODE_STRING FileName; // [rsp+80h] [rbp-80h] BYREF
  __int128 v40; // [rsp+90h] [rbp-70h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+A0h] [rbp-60h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+B0h] [rbp-50h] BYREF
  __int128 FileInformation; // [rsp+E0h] [rbp-20h] BYREF
  _QWORD v44[2]; // [rsp+F0h] [rbp-10h] BYREF

  memset(v44, 0, 12);
  FileHandle = 0;
  BytesReturned = 0;
  ReturnedState = 0;
  FileName = 0;
  IoStatusBlock = 0;
  FileInformation = 0;
  v40 = 0;
  memset(&ObjectAttributes, 0, 44);
  if ( (unsigned __int64)(a1 - 1) <= 0xFFFFFFFFFFFFFFFDuLL && a2 && a3 )
  {
    while ( 1 )
    {
      if ( a4 )
      {
        FileName.Buffer = (PWSTR)v44;
        a4 = 0;
        *(_QWORD *)((char *)v44 + 4) = 0;
        LODWORD(v44[0]) = -1610612733;
        *(_DWORD *)&FileName.Length = 786444;
        v8 = NtQueryDirectoryFile(
               *(HANDLE *)a1,
               0,
               0,
               0,
               &IoStatusBlock,
               &FileInformation,
               0x10u,
               FileReparsePointInformation,
               1u,
               &FileName,
               0);
      }
      else
      {
        if ( *(_DWORD *)(a1 + 16) )
        {
          v33 = *(_OWORD *)(a1 + 8);
          *(_DWORD *)(a1 + 16) = 0;
          FileInformation = v33;
          goto LABEL_8;
        }
        v8 = NtQueryDirectoryFile(
               *(HANDLE *)a1,
               0,
               0,
               0,
               &IoStatusBlock,
               &FileInformation,
               0x10u,
               FileReparsePointInformation,
               1u,
               0,
               0);
      }
      if ( v8 < 0 )
      {
        if ( v8 == -1073741809 )
          v8 = -2147483642;
        v32 = (unsigned int)v8;
        goto LABEL_55;
      }
LABEL_8:
      if ( DWORD2(FileInformation) != -1610612733 )
      {
        v20 = 18;
        goto LABEL_22;
      }
      LODWORD(v40) = 524296;
      *((_QWORD *)&v40 + 1) = &FileInformation;
      ObjectAttributes.RootDirectory = *(HANDLE *)a1;
      ObjectAttributes.Length = 48;
      ObjectAttributes.ObjectName = (PUNICODE_STRING)&v40;
      ObjectAttributes.Attributes = 0;
      Privilege = 17;
      *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
      if ( RtlAcquirePrivilege(&Privilege, 1u, 0, &ReturnedState) < 0 )
        ReturnedState = 0;
      v9 = NtOpenFile(&FileHandle, 0x100000u, &ObjectAttributes, &IoStatusBlock, 7u, 0x206000u);
      v13 = ReturnedState;
      v14 = v9;
      if ( ReturnedState )
        RtlReleasePrivilege(ReturnedState);
      if ( v14 < 0 )
      {
        v32 = (unsigned int)v14;
LABEL_55:
        BaseSetLastNTError(v32);
        return 0;
      }
      GlobalData = (ULONG *)KernelBaseGetGlobalData(v13, v10, v11, v12);
      Heap = (unsigned __int16 *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, *GlobalData, 0x4000u);
      v17 = FileHandle;
      v18 = Heap;
      if ( !Heap )
        goto LABEL_21;
      if ( !DeviceIoControl(FileHandle, 0x900A8u, 0, 0, Heap, 0x4000u, &BytesReturned, 0)
        || *(_DWORD *)v18 != -1610612733 )
      {
        RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v18);
        CloseHandle(FileHandle);
        return 0;
      }
      v19 = v18[4];
      if ( (v18[5] == 96 || v18[5] == 98 && *(unsigned __int16 *)((char *)v18 + v19 + 112) == 92)
        && *(unsigned __int16 *)((char *)v18 + v19 + 16) == 92 )
      {
        v22 = *(unsigned __int16 *)((char *)v18 + v19 + 18);
        if ( (v22 == 63 || v22 == 92)
          && *(unsigned __int16 *)((char *)v18 + v19 + 20) == 63
          && *(unsigned __int16 *)((char *)v18 + v19 + 22) == 92
          && *(unsigned __int16 *)((char *)v18 + v19 + 24) == 86
          && *(unsigned __int16 *)((char *)v18 + v19 + 26) == 111
          && *(unsigned __int16 *)((char *)v18 + v19 + 28) == 108
          && *(unsigned __int16 *)((char *)v18 + v19 + 30) == 117
          && *(unsigned __int16 *)((char *)v18 + v19 + 32) == 109
          && *(unsigned __int16 *)((char *)v18 + v19 + 34) == 101
          && *(unsigned __int16 *)((char *)v18 + v19 + 36) == 123
          && v22 == 63
          && *(unsigned __int16 *)((char *)v18 + v19 + 54) == 45
          && *(unsigned __int16 *)((char *)v18 + v19 + 64) == 45
          && *(unsigned __int16 *)((char *)v18 + v19 + 74) == 45
          && *(unsigned __int16 *)((char *)v18 + v19 + 84) == 45
          && *(unsigned __int16 *)((char *)v18 + v19 + 110) == 125
          && v18[5] == 98 )
        {
          RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v18);
          v23 = 2 * a3 + 2;
          v28 = (ULONG *)KernelBaseGetGlobalData(v25, v24, v26, v27);
          v29 = (unsigned int *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, *v28, v23);
          v17 = FileHandle;
          v30 = v29;
          if ( !v29 )
          {
LABEL_21:
            CloseHandle(v17);
            v20 = 8;
            goto LABEL_22;
          }
          v31 = NtQueryInformationFile(FileHandle, &IoStatusBlock, v29, v23, FileNameInformation);
          if ( v31 < 0 )
          {
            RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v30);
            CloseHandle(FileHandle);
            if ( v31 == -2147483643 )
              *(_OWORD *)(a1 + 8) = FileInformation;
            v32 = (unsigned int)v31;
            goto LABEL_55;
          }
          v34 = *v30;
          if ( v34 < 2 )
          {
            RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v30);
            CloseHandle(FileHandle);
            v20 = 111;
            goto LABEL_22;
          }
          memcpy_0(a2, (char *)v30 + 6, v34 - 2);
          *((_WORD *)a2 + ((unsigned __int64)*v30 >> 1) - 1) = 92;
          *((_WORD *)a2 + ((unsigned __int64)*v30 >> 1)) = 0;
          RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v30);
          CloseHandle(FileHandle);
          return 1;
        }
      }
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v18);
      CloseHandle(FileHandle);
    }
  }
  v20 = 87;
LABEL_22:
  RtlSetLastWin32Error(v20);
  return 0;
}

```

## disassembly

```asm
0x18003b544  mov     [rsp-8+arg_18], rbx
0x18003b549  push    rbp
0x18003b54a  push    rsi
0x18003b54b  push    rdi
0x18003b54c  push    r12
0x18003b54e  push    r13
0x18003b550  push    r14
0x18003b552  push    r15
0x18003b554  lea     rbp, [rsp-10h]
0x18003b559  sub     rsp, 110h
0x18003b560  mov     rax, cs:__security_cookie
0x18003b567  xor     rax, rsp
0x18003b56a  mov     [rbp+40h+var_40], rax
0x18003b56e  xorps   xmm0, xmm0
0x18003b571  xor     eax, eax
0x18003b573  xor     r12d, r12d
0x18003b576  mov     [rbp+40h+var_50], rax
0x18003b57a  xorps   xmm1, xmm1
0x18003b57d  mov     [rbp+40h+var_48], eax
0x18003b580  lea     rax, [rcx-1]
0x18003b584  mov     [rsp+140h+FileHandle], r12
0x18003b589  mov     [rsp+140h+BytesReturned], r12d
0x18003b58e  mov     r15d, r9d
0x18003b591  mov     [rsp+140h+ReturnedState], r12
0x18003b596  mov     edi, r8d
0x18003b599  mov     r14, rdx
0x18003b59c  mov     rsi, rcx
0x18003b59f  movups  xmmword ptr [rbp+40h+ObjectAttributes.ObjectName], xmm0
0x18003b5a3  movups  [rbp+40h+var_C0], xmm0
0x18003b5a7  movups  xmmword ptr [rbp+40h+var_A0], xmm1
0x18003b5ab  movups  [rbp+40h+var_60], xmm0
0x18003b5af  movups  [rbp+40h+var_B0], xmm1
0x18003b5b3  movups  xmmword ptr [rbp+40h+ObjectAttributes.Length], xmm0
0x18003b5b7  movups  xmmword ptr [rbp+40h+ObjectAttributes+1Ch], xmm0
0x18003b5bb  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18003b5bf  ja      loc_18003BB0D
0x18003b5c5  test    rdx, rdx
0x18003b5c8  jz      loc_18003BB0D
0x18003b5ce  test    r8d, r8d
0x18003b5d1  jz      loc_18003BB0D
0x18003b5d7  lea     r13d, [r12+5Ch]
0x18003b5dc  test    r15d, r15d
0x18003b5df  jnz     loc_18003B7CC
0x18003b5e5  cmp     [rsi+10h], r12d
0x18003b5e9  jnz     loc_18003B9FA
0x18003b5ef  mov     [rsp+140h+RestartScan], r12b; RestartScan
0x18003b5f4  mov     [rsp+140h+FileName], r12; FileName
0x18003b5f9  mov     rcx, [rsi]; FileHandle
0x18003b5fc  lea     rax, [rbp+40h+var_60]
0x18003b600  mov     [rsp+140h+ReturnSingleEntry], 1; ReturnSingleEntry
0x18003b605  xor     r9d, r9d; ApcContext
0x18003b608  mov     [rsp+140h+FileInformationClass], 21h ; '!'; FileInformationClass
0x18003b610  xor     r8d, r8d; ApcRoutine
0x18003b613  mov     [rsp+140h+Length], 10h; Length
0x18003b61b  xor     edx, edx; Event
0x18003b61d  mov     [rsp+140h+FileInformation], rax; FileInformation
0x18003b622  lea     rax, [rbp+40h+var_A0]
0x18003b626  mov     [rsp+140h+IoStatusBlock], rax; IoStatusBlock
0x18003b62b  call    cs:__imp_NtQueryDirectoryFile
0x18003b632  nop     dword ptr [rax+rax+00h]
0x18003b637  test    eax, eax
0x18003b639  js      loc_18003BA1B
0x18003b63f  cmp     dword ptr [rbp+40h+var_60+8], 0A0000003h
0x18003b646  jnz     loc_18003B843
0x18003b64c  lea     rax, [rbp+40h+var_60]
0x18003b650  mov     dword ptr [rbp+40h+var_B0], 80008h
0x18003b657  mov     qword ptr [rbp+40h+var_B0+8], rax
0x18003b65b  lea     r9, [rsp+140h+ReturnedState]; ReturnedState
0x18003b660  mov     rax, [rsi]
0x18003b663  lea     rcx, [rsp+140h+Privilege]; Privilege
0x18003b668  xor     r8d, r8d; Flags
0x18003b66b  mov     [rbp+40h+ObjectAttributes.RootDirectory], rax
0x18003b66f  lea     rax, [rbp+40h+var_B0]
0x18003b673  mov     [rbp+40h+ObjectAttributes.Length], 30h ; '0'
0x18003b67a  xorps   xmm0, xmm0
0x18003b67d  mov     [rbp+40h+ObjectAttributes.ObjectName], rax
0x18003b681  mov     [rbp+40h+ObjectAttributes.Attributes], r12d
0x18003b685  lea     edx, [r8+1]; NumPriv
0x18003b689  mov     [rsp+140h+Privilege], 11h
0x18003b691  movdqu  xmmword ptr [rbp+40h+ObjectAttributes.SecurityDescriptor], xmm0
0x18003b696  call    cs:__imp_RtlAcquirePrivilege
0x18003b69d  nop     dword ptr [rax+rax+00h]
0x18003b6a2  test    eax, eax
0x18003b6a4  jns     short loc_18003B6AB
0x18003b6a6  mov     [rsp+140h+ReturnedState], r12
0x18003b6ab  mov     dword ptr [rsp+140h+FileInformation], 206000h; OpenOptions
0x18003b6b3  lea     r9, [rbp+40h+var_A0]; IoStatusBlock
0x18003b6b7  lea     r8, [rbp+40h+ObjectAttributes]; ObjectAttributes
0x18003b6bb  mov     dword ptr [rsp+140h+IoStatusBlock], 7; ShareAccess
0x18003b6c3  mov     edx, 100000h; DesiredAccess
0x18003b6c8  lea     rcx, [rsp+140h+FileHandle]; FileHandle
0x18003b6cd  call    cs:__imp_NtOpenFile
0x18003b6d4  nop     dword ptr [rax+rax+00h]
0x18003b6d9  mov     rcx, [rsp+140h+ReturnedState]; ReturnedState
0x18003b6de  mov     ebx, eax
0x18003b6e0  test    rcx, rcx
0x18003b6e3  jz      short loc_18003B6F1
0x18003b6e5  call    cs:__imp_RtlReleasePrivilege
0x18003b6ec  nop     dword ptr [rax+rax+00h]
0x18003b6f1  test    ebx, ebx
0x18003b6f3  js      loc_18003BB06
0x18003b6f9  call    cs:__imp_KernelBaseGetGlobalData
0x18003b700  nop     dword ptr [rax+rax+00h]
0x18003b705  mov     rcx, gs:60h
0x18003b70e  mov     r8d, 4000h; Size
0x18003b714  mov     edx, [rax]; Flags
0x18003b716  mov     rcx, [rcx+30h]; HeapHandle
0x18003b71a  call    cs:__imp_RtlAllocateHeap
0x18003b721  nop     dword ptr [rax+rax+00h]
0x18003b726  mov     rcx, [rsp+140h+FileHandle]; hObject
0x18003b72b  mov     rbx, rax
0x18003b72e  test    rax, rax
0x18003b731  jz      loc_18003B7FC
0x18003b737  mov     qword ptr [rsp+140h+FileInformationClass], r12; lpOverlapped
0x18003b73c  lea     rax, [rsp+140h+BytesReturned]
0x18003b741  mov     qword ptr [rsp+140h+Length], rax; lpBytesReturned
0x18003b746  xor     r9d, r9d; nInBufferSize
0x18003b749  mov     dword ptr [rsp+140h+FileInformation], 4000h; nOutBufferSize
0x18003b751  xor     r8d, r8d; lpInBuffer
0x18003b754  mov     edx, 900A8h; dwIoControlCode
0x18003b759  mov     [rsp+140h+IoStatusBlock], rbx; lpOutBuffer
0x18003b75e  call    cs:__imp_DeviceIoControl
0x18003b765  nop     dword ptr [rax+rax+00h]
0x18003b76a  test    eax, eax
0x18003b76c  jz      loc_18003BAD2
0x18003b772  cmp     dword ptr [rbx], 0A0000003h
0x18003b778  jnz     loc_18003BAD2
0x18003b77e  cmp     word ptr [rbx+0Ah], 60h ; '`'
0x18003b783  movzx   eax, word ptr [rbx+8]
0x18003b787  jz      loc_18003B856
0x18003b78d  cmp     word ptr [rbx+0Ah], 62h ; 'b'
0x18003b792  jz      loc_18003B84A
0x18003b798  mov     rcx, gs:60h
0x18003b7a1  mov     r8, rbx; P
0x18003b7a4  xor     edx, edx; Flags
0x18003b7a6  mov     rcx, [rcx+30h]; HeapHandle
0x18003b7aa  call    cs:__imp_RtlFreeHeap
0x18003b7b1  nop     dword ptr [rax+rax+00h]
0x18003b7b6  mov     rcx, [rsp+140h+FileHandle]; hObject
0x18003b7bb  call    cs:__imp_CloseHandle
0x18003b7c2  nop     dword ptr [rax+rax+00h]
0x18003b7c7  jmp     loc_18003B5DC
0x18003b7cc  lea     rax, [rbp+40h+var_50]
0x18003b7d0  mov     [rsp+140h+RestartScan], r12b
0x18003b7d5  mov     qword ptr [rbp+40h+var_C0+8], rax
0x18003b7d9  mov     r15d, r12d
0x18003b7dc  lea     rax, [rbp+40h+var_C0]
0x18003b7e0  mov     [rbp+40h+var_50+4], r12
0x18003b7e4  mov     [rsp+140h+FileName], rax
0x18003b7e9  mov     dword ptr [rbp+40h+var_50], 0A0000003h
0x18003b7f0  mov     dword ptr [rbp+40h+var_C0], 0C000Ch
0x18003b7f7  jmp     loc_18003B5F9
0x18003b7fc  call    cs:__imp_CloseHandle
0x18003b803  nop     dword ptr [rax+rax+00h]
0x18003b808  mov     ecx, 8; LastError
0x18003b80d  call    cs:__imp_RtlSetLastWin32Error
0x18003b814  nop     dword ptr [rax+rax+00h]
0x18003b819  xor     eax, eax
0x18003b81b  mov     rcx, [rbp+40h+var_40]
0x18003b81f  xor     rcx, rsp; StackCookie
0x18003b822  call    __security_check_cookie
0x18003b827  mov     rbx, [rsp+140h+arg_18]
0x18003b82f  add     rsp, 110h
0x18003b836  pop     r15
0x18003b838  pop     r14
0x18003b83a  pop     r13
0x18003b83c  pop     r12
0x18003b83e  pop     rdi
0x18003b83f  pop     rsi
0x18003b840  pop     rbp
0x18003b841  retn
0x18003b843  mov     ecx, 12h
0x18003b848  jmp     short loc_18003B80D
0x18003b84a  cmp     [rax+rbx+70h], r13w
0x18003b850  jnz     loc_18003B798
0x18003b856  cmp     [rax+rbx+10h], r13w
0x18003b85c  jnz     loc_18003B798
0x18003b862  movzx   ecx, word ptr [rax+rbx+12h]
0x18003b867  cmp     cx, 3Fh ; '?'
0x18003b86b  jnz     loc_18003BA0C
0x18003b871  cmp     word ptr [rax+rbx+14h], 3Fh ; '?'
0x18003b877  jnz     loc_18003B798
0x18003b87d  cmp     [rax+rbx+16h], r13w
0x18003b883  jnz     loc_18003B798
0x18003b889  cmp     word ptr [rax+rbx+18h], 56h ; 'V'
0x18003b88f  jnz     loc_18003B798
0x18003b895  mov     edx, 6Fh ; 'o'
0x18003b89a  cmp     [rax+rbx+1Ah], dx
0x18003b89f  jnz     loc_18003B798
0x18003b8a5  cmp     word ptr [rax+rbx+1Ch], 6Ch ; 'l'
0x18003b8ab  jnz     loc_18003B798
0x18003b8b1  cmp     word ptr [rax+rbx+1Eh], 75h ; 'u'
0x18003b8b7  jnz     loc_18003B798
0x18003b8bd  cmp     word ptr [rax+rbx+20h], 6Dh ; 'm'
0x18003b8c3  jnz     loc_18003B798
0x18003b8c9  cmp     word ptr [rax+rbx+22h], 65h ; 'e'
0x18003b8cf  jnz     loc_18003B798
0x18003b8d5  cmp     word ptr [rax+rbx+24h], 7Bh ; '{'
0x18003b8db  jnz     loc_18003B798
0x18003b8e1  mov     dx, 2Dh ; '-'
0x18003b8e5  cmp     cx, 3Fh ; '?'
0x18003b8e9  jnz     loc_18003B798
0x18003b8ef  cmp     [rax+rbx+36h], dx
0x18003b8f4  jnz     loc_18003B798
0x18003b8fa  cmp     [rax+rbx+40h], dx
0x18003b8ff  jnz     loc_18003B798
0x18003b905  cmp     [rax+rbx+4Ah], dx
0x18003b90a  jnz     loc_18003B798
0x18003b910  cmp     [rax+rbx+54h], dx
0x18003b915  jnz     loc_18003B798
0x18003b91b  cmp     word ptr [rax+rbx+6Eh], 7Dh ; '}'
0x18003b921  jnz     loc_18003B798
0x18003b927  cmp     word ptr [rbx+0Ah], 62h ; 'b'
0x18003b92c  jnz     loc_18003B798
0x18003b932  mov     rcx, gs:60h
0x18003b93b  mov     r8, rbx; P
0x18003b93e  xor     edx, edx; Flags
0x18003b940  mov     rcx, [rcx+30h]; HeapHandle
0x18003b944  call    cs:__imp_RtlFreeHeap
0x18003b94b  nop     dword ptr [rax+rax+00h]
0x18003b950  lea     edi, ds:2[rdi*2]
0x18003b957  call    cs:__imp_KernelBaseGetGlobalData
0x18003b95e  nop     dword ptr [rax+rax+00h]
0x18003b963  mov     rcx, gs:60h
0x18003b96c  mov     r8d, edi; Size
0x18003b96f  mov     edx, [rax]; Flags
0x18003b971  mov     rcx, [rcx+30h]; HeapHandle
0x18003b975  call    cs:__imp_RtlAllocateHeap
0x18003b97c  nop     dword ptr [rax+rax+00h]
0x18003b981  mov     rcx, [rsp+140h+FileHandle]; FileHandle
0x18003b986  mov     rbx, rax
0x18003b989  test    rax, rax
0x18003b98c  jz      loc_18003B7FC
0x18003b992  mov     r9d, edi; Length
0x18003b995  mov     dword ptr [rsp+140h+IoStatusBlock], 9; FileInformationClass
0x18003b99d  mov     r8, rax; FileInformation
0x18003b9a0  lea     rdx, [rbp+40h+var_A0]; IoStatusBlock
0x18003b9a4  call    cs:__imp_NtQueryInformationFile
0x18003b9ab  nop     dword ptr [rax+rax+00h]
0x18003b9b0  mov     edi, eax
0x18003b9b2  test    eax, eax
0x18003b9b4  jns     short loc_18003BA34
0x18003b9b6  mov     rcx, gs:60h
0x18003b9bf  mov     r8, rbx; P
0x18003b9c2  xor     edx, edx; Flags
0x18003b9c4  mov     rcx, [rcx+30h]; HeapHandle
0x18003b9c8  call    cs:__imp_RtlFreeHeap
0x18003b9cf  nop     dword ptr [rax+rax+00h]
0x18003b9d4  mov     rcx, [rsp+140h+FileHandle]; hObject
0x18003b9d9  call    cs:__imp_CloseHandle
0x18003b9e0  nop     dword ptr [rax+rax+00h]
0x18003b9e5  cmp     edi, 80000005h
0x18003b9eb  jnz     short loc_18003B9F6
0x18003b9ed  movups  xmm0, [rbp+40h+var_60]
0x18003b9f1  movdqu  xmmword ptr [rsi+8], xmm0
0x18003b9f6  mov     ecx, edi
0x18003b9f8  jmp     short loc_18003BA2A
0x18003b9fa  movups  xmm0, xmmword ptr [rsi+8]
0x18003b9fe  mov     [rsi+10h], r12d
0x18003ba02  movdqu  [rbp+40h+var_60], xmm0
0x18003ba07  jmp     loc_18003B63F
0x18003ba0c  cmp     cx, r13w
0x18003ba10  jnz     loc_18003B798
0x18003ba16  jmp     loc_18003B871
0x18003ba1b  mov     ecx, 80000006h
0x18003ba20  cmp     eax, 0C000000Fh
0x18003ba25  cmovz   eax, ecx
0x18003ba28  mov     ecx, eax
0x18003ba2a  call    BaseSetLastNTError
0x18003ba2f  jmp     loc_18003B819
0x18003ba34  mov     eax, [rbx]
0x18003ba36  lea     r8, [rax-2]; Size
0x18003ba3a  cmp     r8, rax
0x18003ba3d  jbe     short loc_18003BA78
0x18003ba3f  mov     rcx, gs:60h
0x18003ba48  mov     r8, rbx; P
0x18003ba4b  xor     edx, edx; Flags
0x18003ba4d  mov     rcx, [rcx+30h]; HeapHandle
0x18003ba51  call    cs:__imp_RtlFreeHeap
0x18003ba58  nop     dword ptr [rax+rax+00h]
0x18003ba5d  mov     rcx, [rsp+140h+FileHandle]; hObject
0x18003ba62  call    cs:__imp_CloseHandle
0x18003ba69  nop     dword ptr [rax+rax+00h]
0x18003ba6e  mov     ecx, 6Fh ; 'o'
0x18003ba73  jmp     loc_18003B80D
0x18003ba78  lea     rdx, [rbx+6]; Src
0x18003ba7c  mov     rcx, r14; void *
0x18003ba7f  call    memcpy_0
0x18003ba84  mov     ecx, [rbx]
0x18003ba86  mov     r8, rbx; P
0x18003ba89  shr     rcx, 1
0x18003ba8c  mov     [r14+rcx*2-2], r13w
0x18003ba92  mov     edx, [rbx]
0x18003ba94  shr     rdx, 1
0x18003ba97  mov     [r14+rdx*2], r12w
0x18003ba9c  xor     edx, edx; Flags
0x18003ba9e  mov     rcx, gs:60h
0x18003baa7  mov     rcx, [rcx+30h]; HeapHandle
0x18003baab  call    cs:__imp_RtlFreeHeap
0x18003bab2  nop     dword ptr [rax+rax+00h]
  ... truncated ...
```
