# FindNextVolumeMountPointHelper

- ea: `0x180038774`
- end: `0x180038cbc`
- name: `FindNextVolumeMountPointHelper`
- size: `1352`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180038550`
- `0x18006c8a0`
- `0x18006c9e0`

## callees

- `0x18000f920`
- `0x180038774`
- `0x18007a7d1`
- `0x18007a840`

## import_xrefs

- `ntdll!NtOpenFile` at `0x1800388f1`
- `ntdll!NtOpenFile` at `0x1800388f1`
- `ntdll!NtQueryInformationFile` at `0x180038b7f`
- `ntdll!NtQueryInformationFile` at `0x180038b7f`
- `ntdll!RtlSetLastWin32Error` at `0x180038a01`
- `ntdll!RtlSetLastWin32Error` at `0x180038a01`
- `ntdll!RtlReleasePrivilege` at `0x180038903`
- `ntdll!RtlReleasePrivilege` at `0x180038903`
- `ntdll!RtlAcquirePrivilege` at `0x1800388c0`
- `ntdll!RtlAcquirePrivilege` at `0x1800388c0`
- `ntdll!NtQueryDirectoryFile` at `0x18003885b`
- `ntdll!NtQueryDirectoryFile` at `0x18003885b`
- `ntdll!RtlFreeHeap` at `0x1800389b0`
- `ntdll!RtlFreeHeap` at `0x180038b31`
- `ntdll!RtlFreeHeap` at `0x180038b9d`
- `ntdll!RtlFreeHeap` at `0x180038c1a`
- `ntdll!RtlFreeHeap` at `0x180038c68`
- `ntdll!RtlFreeHeap` at `0x180038c95`
- `ntdll!RtlFreeHeap` at `0x1800389b0`
- `ntdll!RtlFreeHeap` at `0x180038b31`
- `ntdll!RtlFreeHeap` at `0x180038b9d`
- `ntdll!RtlFreeHeap` at `0x180038c1a`
- `ntdll!RtlFreeHeap` at `0x180038c68`
- `ntdll!RtlFreeHeap` at `0x180038c95`
- `ntdll!RtlAllocateHeap` at `0x18003892c`
- `ntdll!RtlAllocateHeap` at `0x180038b56`
- `ntdll!RtlAllocateHeap` at `0x18003892c`
- `ntdll!RtlAllocateHeap` at `0x180038b56`
- `KERNELBASE!KernelBaseGetGlobalData` at `0x180038911`
- `KERNELBASE!KernelBaseGetGlobalData` at `0x180038b3e`
- `KERNELBASE!KernelBaseGetGlobalData` at `0x180038911`
- `KERNELBASE!KernelBaseGetGlobalData` at `0x180038b3e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800389bb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800389f6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180038ba8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180038c25`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180038c73`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180038ca0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800389bb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800389f6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180038ba8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180038c25`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180038c73`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180038ca0`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18003896a`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18003896a`

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
0x180038774  mov     [rsp-8+arg_18], rbx
0x180038779  push    rbp
0x18003877a  push    rsi
0x18003877b  push    rdi
0x18003877c  push    r12
0x18003877e  push    r13
0x180038780  push    r14
0x180038782  push    r15
0x180038784  lea     rbp, [rsp-10h]
0x180038789  sub     rsp, 110h
0x180038790  mov     rax, cs:__security_cookie
0x180038797  xor     rax, rsp
0x18003879a  mov     [rbp+40h+var_40], rax
0x18003879e  xorps   xmm0, xmm0
0x1800387a1  xor     eax, eax
0x1800387a3  xor     r12d, r12d
0x1800387a6  mov     [rbp+40h+var_50], rax
0x1800387aa  xorps   xmm1, xmm1
0x1800387ad  mov     [rbp+40h+var_48], eax
0x1800387b0  lea     rax, [rcx-1]
0x1800387b4  mov     [rsp+140h+FileHandle], r12
0x1800387b9  mov     [rsp+140h+BytesReturned], r12d
0x1800387be  mov     r15d, r9d
0x1800387c1  mov     [rsp+140h+ReturnedState], r12
0x1800387c6  mov     edi, r8d
0x1800387c9  mov     r14, rdx
0x1800387cc  mov     rsi, rcx
0x1800387cf  movups  xmmword ptr [rbp+40h+ObjectAttributes.ObjectName], xmm0
0x1800387d3  movups  [rbp+40h+var_C0], xmm0
0x1800387d7  movups  xmmword ptr [rbp+40h+var_A0], xmm1
0x1800387db  movups  [rbp+40h+var_60], xmm0
0x1800387df  movups  [rbp+40h+var_B0], xmm1
0x1800387e3  movups  xmmword ptr [rbp+40h+ObjectAttributes.Length], xmm0
0x1800387e7  movups  xmmword ptr [rbp+40h+ObjectAttributes+1Ch], xmm0
0x1800387eb  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800387ef  ja      loc_180038CB2
0x1800387f5  test    rdx, rdx
0x1800387f8  jz      loc_180038CB2
0x1800387fe  test    r8d, r8d
0x180038801  jz      loc_180038CB2
0x180038807  lea     r13d, [r12+5Ch]
0x18003880c  test    r15d, r15d
0x18003880f  jnz     loc_1800389C6
0x180038815  cmp     [rsi+10h], r12d
0x180038819  jnz     loc_180038BC3
0x18003881f  mov     [rsp+140h+RestartScan], r12b; RestartScan
0x180038824  mov     [rsp+140h+FileName], r12; FileName
0x180038829  mov     rcx, [rsi]; FileHandle
0x18003882c  lea     rax, [rbp+40h+var_60]
0x180038830  mov     [rsp+140h+ReturnSingleEntry], 1; ReturnSingleEntry
0x180038835  xor     r9d, r9d; ApcContext
0x180038838  mov     [rsp+140h+FileInformationClass], 21h ; '!'; FileInformationClass
0x180038840  xor     r8d, r8d; ApcRoutine
0x180038843  mov     [rsp+140h+Length], 10h; Length
0x18003884b  xor     edx, edx; Event
0x18003884d  mov     [rsp+140h+FileInformation], rax; FileInformation
0x180038852  lea     rax, [rbp+40h+var_A0]
0x180038856  mov     [rsp+140h+IoStatusBlock], rax; IoStatusBlock
0x18003885b  call    cs:__imp_NtQueryDirectoryFile
0x180038861  test    eax, eax
0x180038863  js      loc_180038BE4
0x180038869  cmp     dword ptr [rbp+40h+var_60+8], 0A0000003h
0x180038870  jnz     loc_180038A30
0x180038876  lea     rax, [rbp+40h+var_60]
0x18003887a  mov     dword ptr [rbp+40h+var_B0], 80008h
0x180038881  mov     qword ptr [rbp+40h+var_B0+8], rax
0x180038885  lea     r9, [rsp+140h+ReturnedState]; ReturnedState
0x18003888a  mov     rax, [rsi]
0x18003888d  lea     rcx, [rsp+140h+Privilege]; Privilege
0x180038892  xor     r8d, r8d; Flags
0x180038895  mov     [rbp+40h+ObjectAttributes.RootDirectory], rax
0x180038899  lea     rax, [rbp+40h+var_B0]
0x18003889d  mov     [rbp+40h+ObjectAttributes.Length], 30h ; '0'
0x1800388a4  xorps   xmm0, xmm0
0x1800388a7  mov     [rbp+40h+ObjectAttributes.ObjectName], rax
0x1800388ab  mov     [rbp+40h+ObjectAttributes.Attributes], r12d
0x1800388af  lea     edx, [r8+1]; NumPriv
0x1800388b3  mov     [rsp+140h+Privilege], 11h
0x1800388bb  movdqu  xmmword ptr [rbp+40h+ObjectAttributes.SecurityDescriptor], xmm0
0x1800388c0  call    cs:__imp_RtlAcquirePrivilege
0x1800388c6  test    eax, eax
0x1800388c8  jns     short loc_1800388CF
0x1800388ca  mov     [rsp+140h+ReturnedState], r12
0x1800388cf  mov     dword ptr [rsp+140h+FileInformation], 206000h; OpenOptions
0x1800388d7  lea     r9, [rbp+40h+var_A0]; IoStatusBlock
0x1800388db  lea     r8, [rbp+40h+ObjectAttributes]; ObjectAttributes
0x1800388df  mov     dword ptr [rsp+140h+IoStatusBlock], 7; ShareAccess
0x1800388e7  mov     edx, 100000h; DesiredAccess
0x1800388ec  lea     rcx, [rsp+140h+FileHandle]; FileHandle
0x1800388f1  call    cs:__imp_NtOpenFile
0x1800388f7  mov     rcx, [rsp+140h+ReturnedState]; ReturnedState
0x1800388fc  mov     ebx, eax
0x1800388fe  test    rcx, rcx
0x180038901  jz      short loc_180038909
0x180038903  call    cs:__imp_RtlReleasePrivilege
0x180038909  test    ebx, ebx
0x18003890b  js      loc_180038CAB
0x180038911  call    cs:__imp_KernelBaseGetGlobalData
0x180038917  mov     rcx, gs:60h
0x180038920  mov     r8d, 4000h; Size
0x180038926  mov     edx, [rax]; Flags
0x180038928  mov     rcx, [rcx+30h]; HeapHandle
0x18003892c  call    cs:__imp_RtlAllocateHeap
0x180038932  mov     rcx, [rsp+140h+FileHandle]; hObject
0x180038937  mov     rbx, rax
0x18003893a  test    rax, rax
0x18003893d  jz      loc_1800389F6
0x180038943  mov     qword ptr [rsp+140h+FileInformationClass], r12; lpOverlapped
0x180038948  lea     rax, [rsp+140h+BytesReturned]
0x18003894d  mov     qword ptr [rsp+140h+Length], rax; lpBytesReturned
0x180038952  xor     r9d, r9d; nInBufferSize
0x180038955  mov     dword ptr [rsp+140h+FileInformation], 4000h; nOutBufferSize
0x18003895d  xor     r8d, r8d; lpInBuffer
0x180038960  mov     edx, 900A8h; dwIoControlCode
0x180038965  mov     [rsp+140h+IoStatusBlock], rbx; lpOutBuffer
0x18003896a  call    cs:__imp_DeviceIoControl
0x180038970  test    eax, eax
0x180038972  jz      loc_180038C83
0x180038978  cmp     dword ptr [rbx], 0A0000003h
0x18003897e  jnz     loc_180038C83
0x180038984  cmp     word ptr [rbx+0Ah], 60h ; '`'
0x180038989  movzx   eax, word ptr [rbx+8]
0x18003898d  jz      loc_180038A43
0x180038993  cmp     word ptr [rbx+0Ah], 62h ; 'b'
0x180038998  jz      loc_180038A37
0x18003899e  mov     rcx, gs:60h
0x1800389a7  mov     r8, rbx; P
0x1800389aa  xor     edx, edx; Flags
0x1800389ac  mov     rcx, [rcx+30h]; HeapHandle
0x1800389b0  call    cs:__imp_RtlFreeHeap
0x1800389b6  mov     rcx, [rsp+140h+FileHandle]; hObject
0x1800389bb  call    cs:__imp_CloseHandle
0x1800389c1  jmp     loc_18003880C
0x1800389c6  lea     rax, [rbp+40h+var_50]
0x1800389ca  mov     [rsp+140h+RestartScan], r12b
0x1800389cf  mov     qword ptr [rbp+40h+var_C0+8], rax
0x1800389d3  mov     r15d, r12d
0x1800389d6  lea     rax, [rbp+40h+var_C0]
0x1800389da  mov     [rbp+40h+var_50+4], r12
0x1800389de  mov     [rsp+140h+FileName], rax
0x1800389e3  mov     dword ptr [rbp+40h+var_50], 0A0000003h
0x1800389ea  mov     dword ptr [rbp+40h+var_C0], 0C000Ch
0x1800389f1  jmp     loc_180038829
0x1800389f6  call    cs:__imp_CloseHandle
0x1800389fc  mov     ecx, 8; LastError
0x180038a01  call    cs:__imp_RtlSetLastWin32Error
0x180038a07  xor     eax, eax
0x180038a09  mov     rcx, [rbp+40h+var_40]
0x180038a0d  xor     rcx, rsp; StackCookie
0x180038a10  call    __security_check_cookie
0x180038a15  mov     rbx, [rsp+140h+arg_18]
0x180038a1d  add     rsp, 110h
0x180038a24  pop     r15
0x180038a26  pop     r14
0x180038a28  pop     r13
0x180038a2a  pop     r12
0x180038a2c  pop     rdi
0x180038a2d  pop     rsi
0x180038a2e  pop     rbp
0x180038a2f  retn
0x180038a30  mov     ecx, 12h
0x180038a35  jmp     short loc_180038A01
0x180038a37  cmp     [rax+rbx+70h], r13w
0x180038a3d  jnz     loc_18003899E
0x180038a43  cmp     [rax+rbx+10h], r13w
0x180038a49  jnz     loc_18003899E
0x180038a4f  movzx   ecx, word ptr [rax+rbx+12h]
0x180038a54  cmp     cx, 3Fh ; '?'
0x180038a58  jnz     loc_180038BD5
0x180038a5e  cmp     word ptr [rax+rbx+14h], 3Fh ; '?'
0x180038a64  jnz     loc_18003899E
0x180038a6a  cmp     [rax+rbx+16h], r13w
0x180038a70  jnz     loc_18003899E
0x180038a76  cmp     word ptr [rax+rbx+18h], 56h ; 'V'
0x180038a7c  jnz     loc_18003899E
0x180038a82  mov     edx, 6Fh ; 'o'
0x180038a87  cmp     [rax+rbx+1Ah], dx
0x180038a8c  jnz     loc_18003899E
0x180038a92  cmp     word ptr [rax+rbx+1Ch], 6Ch ; 'l'
0x180038a98  jnz     loc_18003899E
0x180038a9e  cmp     word ptr [rax+rbx+1Eh], 75h ; 'u'
0x180038aa4  jnz     loc_18003899E
0x180038aaa  cmp     word ptr [rax+rbx+20h], 6Dh ; 'm'
0x180038ab0  jnz     loc_18003899E
0x180038ab6  cmp     word ptr [rax+rbx+22h], 65h ; 'e'
0x180038abc  jnz     loc_18003899E
0x180038ac2  cmp     word ptr [rax+rbx+24h], 7Bh ; '{'
0x180038ac8  jnz     loc_18003899E
0x180038ace  mov     dx, 2Dh ; '-'
0x180038ad2  cmp     cx, 3Fh ; '?'
0x180038ad6  jnz     loc_18003899E
0x180038adc  cmp     [rax+rbx+36h], dx
0x180038ae1  jnz     loc_18003899E
0x180038ae7  cmp     [rax+rbx+40h], dx
0x180038aec  jnz     loc_18003899E
0x180038af2  cmp     [rax+rbx+4Ah], dx
0x180038af7  jnz     loc_18003899E
0x180038afd  cmp     [rax+rbx+54h], dx
0x180038b02  jnz     loc_18003899E
0x180038b08  cmp     word ptr [rax+rbx+6Eh], 7Dh ; '}'
0x180038b0e  jnz     loc_18003899E
0x180038b14  cmp     word ptr [rbx+0Ah], 62h ; 'b'
0x180038b19  jnz     loc_18003899E
0x180038b1f  mov     rcx, gs:60h
0x180038b28  mov     r8, rbx; P
0x180038b2b  xor     edx, edx; Flags
0x180038b2d  mov     rcx, [rcx+30h]; HeapHandle
0x180038b31  call    cs:__imp_RtlFreeHeap
0x180038b37  lea     edi, ds:2[rdi*2]
0x180038b3e  call    cs:__imp_KernelBaseGetGlobalData
0x180038b44  mov     rcx, gs:60h
0x180038b4d  mov     r8d, edi; Size
0x180038b50  mov     edx, [rax]; Flags
0x180038b52  mov     rcx, [rcx+30h]; HeapHandle
0x180038b56  call    cs:__imp_RtlAllocateHeap
0x180038b5c  mov     rcx, [rsp+140h+FileHandle]; FileHandle
0x180038b61  mov     rbx, rax
0x180038b64  test    rax, rax
0x180038b67  jz      loc_1800389F6
0x180038b6d  mov     r9d, edi; Length
0x180038b70  mov     dword ptr [rsp+140h+IoStatusBlock], 9; FileInformationClass
0x180038b78  mov     r8, rax; FileInformation
0x180038b7b  lea     rdx, [rbp+40h+var_A0]; IoStatusBlock
0x180038b7f  call    cs:__imp_NtQueryInformationFile
0x180038b85  mov     edi, eax
0x180038b87  test    eax, eax
0x180038b89  jns     short loc_180038BFD
0x180038b8b  mov     rcx, gs:60h
0x180038b94  mov     r8, rbx; P
0x180038b97  xor     edx, edx; Flags
0x180038b99  mov     rcx, [rcx+30h]; HeapHandle
0x180038b9d  call    cs:__imp_RtlFreeHeap
0x180038ba3  mov     rcx, [rsp+140h+FileHandle]; hObject
0x180038ba8  call    cs:__imp_CloseHandle
0x180038bae  cmp     edi, 80000005h
0x180038bb4  jnz     short loc_180038BBF
0x180038bb6  movups  xmm0, [rbp+40h+var_60]
0x180038bba  movdqu  xmmword ptr [rsi+8], xmm0
0x180038bbf  mov     ecx, edi
0x180038bc1  jmp     short loc_180038BF3
0x180038bc3  movups  xmm0, xmmword ptr [rsi+8]
0x180038bc7  mov     [rsi+10h], r12d
0x180038bcb  movdqu  [rbp+40h+var_60], xmm0
0x180038bd0  jmp     loc_180038869
0x180038bd5  cmp     cx, r13w
0x180038bd9  jnz     loc_18003899E
0x180038bdf  jmp     loc_180038A5E
0x180038be4  mov     ecx, 80000006h
0x180038be9  cmp     eax, 0C000000Fh
0x180038bee  cmovz   eax, ecx
0x180038bf1  mov     ecx, eax
0x180038bf3  call    BaseSetLastNTError
0x180038bf8  jmp     loc_180038A07
0x180038bfd  mov     eax, [rbx]
0x180038bff  lea     r8, [rax-2]; Size
0x180038c03  cmp     r8, rax
0x180038c06  jbe     short loc_180038C35
0x180038c08  mov     rcx, gs:60h
0x180038c11  mov     r8, rbx; P
0x180038c14  xor     edx, edx; Flags
0x180038c16  mov     rcx, [rcx+30h]; HeapHandle
0x180038c1a  call    cs:__imp_RtlFreeHeap
0x180038c20  mov     rcx, [rsp+140h+FileHandle]; hObject
0x180038c25  call    cs:__imp_CloseHandle
0x180038c2b  mov     ecx, 6Fh ; 'o'
0x180038c30  jmp     loc_180038A01
0x180038c35  lea     rdx, [rbx+6]; Src
0x180038c39  mov     rcx, r14; void *
0x180038c3c  call    memcpy_0
0x180038c41  mov     ecx, [rbx]
0x180038c43  mov     r8, rbx; P
0x180038c46  shr     rcx, 1
0x180038c49  mov     [r14+rcx*2-2], r13w
0x180038c4f  mov     edx, [rbx]
0x180038c51  shr     rdx, 1
0x180038c54  mov     [r14+rdx*2], r12w
0x180038c59  xor     edx, edx; Flags
0x180038c5b  mov     rcx, gs:60h
0x180038c64  mov     rcx, [rcx+30h]; HeapHandle
0x180038c68  call    cs:__imp_RtlFreeHeap
0x180038c6e  mov     rcx, [rsp+140h+FileHandle]; hObject
0x180038c73  call    cs:__imp_CloseHandle
0x180038c79  mov     eax, 1
0x180038c7e  jmp     loc_180038A09
0x180038c83  mov     rcx, gs:60h
0x180038c8c  mov     r8, rbx; P
0x180038c8f  xor     edx, edx; Flags
0x180038c91  mov     rcx, [rcx+30h]; HeapHandle
0x180038c95  call    cs:__imp_RtlFreeHeap
0x180038c9b  mov     rcx, [rsp+140h+FileHandle]; hObject
0x180038ca0  call    cs:__imp_CloseHandle
0x180038ca6  jmp     loc_180038A07
0x180038cab  mov     ecx, ebx
0x180038cad  jmp     loc_180038BF3
0x180038cb2  mov     ecx, 57h ; 'W'
0x180038cb7  jmp     loc_180038A01
```
