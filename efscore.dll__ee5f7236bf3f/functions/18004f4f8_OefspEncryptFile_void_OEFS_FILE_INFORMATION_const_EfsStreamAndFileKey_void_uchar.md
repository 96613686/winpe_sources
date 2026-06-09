# OefspEncryptFile(void *,OEFS_FILE_INFORMATION const &,EfsStreamAndFileKey &,void *,uchar *)

- ea: `0x18004f4f8`
- end: `0x18004f9c5`
- name: `?OefspEncryptFile@@YAJPEAXAEBUOEFS_FILE_INFORMATION@@AEAVEfsStreamAndFileKey@@0PEAE@Z`
- size: `1229`
- prototype: `__int64 __usercall@<rax>(HANDLE FileHandle@<rcx>, const struct OEFS_FILE_INFORMATION *@<rdx>, struct EfsStreamAndFileKey *@<r8>, void *@<r9>, unsigned __int8 *)`
- caller_count: `2`
- callee_count: `14`
- tags: `file_ops, reparse_path, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18004e4c4`
- `0x18004e9e8`

## callees

- `0x18000b10c`
- `0x18000b12c`
- `0x18000dc68`
- `0x18000ef20`
- `0x18001b1d0`
- `0x18001dd98`
- `0x18004c024`
- `0x18004cdec`
- `0x18004cf18`
- `0x18004d09c`
- `0x18004f4f8`
- `0x18004fec8`
- `0x1800505ec`
- `0x180051820`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004f6dd`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004f83f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004f89b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004f993`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004f6dd`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004f83f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004f89b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004f993`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004f6eb`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004f84d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004f8a9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004f9a1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004f6eb`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004f84d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004f8a9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004f9a1`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18004f730`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18004f730`
- `ntdll!NtFsControlFile` at `0x18004f7ca`
- `ntdll!NtFsControlFile` at `0x18004f7ca`
- `ntdll!NtCreateFile` at `0x18004f697`
- `ntdll!NtCreateFile` at `0x18004f697`

## string_xrefs

- `0x18004f57f`: `onecoreuap\ds\security\efs\dll\efsonline.cxx`
- `0x18004f6a6`: `onecoreuap\ds\security\efs\dll\efsonline.cxx`
- `0x18004f741`: `onecoreuap\ds\security\efs\dll\efsonline.cxx`
- `0x18004f77b`: `onecoreuap\ds\security\efs\dll\efsonline.cxx`
- `0x18004f87a`: `onecoreuap\ds\security\efs\dll\efsonline.cxx`
- `0x18004f960`: `onecoreuap\ds\security\efs\dll\efsonline.cxx`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
int __fastcall OefspEncryptFile(
        HANDLE FileHandle,
        const struct OEFS_FILE_INFORMATION *a2,
        struct EfsStreamAndFileKey *a3,
        void *a4,
        unsigned __int8 *a5)
{
  int v8; // eax
  void *v10; // rsi
  __int64 v11; // rax
  NTSTATUS v12; // eax
  __int64 v13; // rdx
  int LastError; // eax
  int v15; // edi
  void *v16; // rbx
  HANDLE ProcessHeap; // rax
  const char *v18; // r9
  int v19; // eax
  unsigned __int8 *v20; // rdi
  HANDLE v21; // rax
  int v22; // esi
  __int64 v23; // rdx
  void *v24; // rbx
  HANDLE v25; // rax
  __int64 v26; // rax
  __int64 v27; // rax
  int v28; // eax
  void *v29; // rbx
  HANDLE v30; // rax
  PLARGE_INTEGER AllocationSize; // [rsp+20h] [rbp-E0h]
  LPVOID lpMem; // [rsp+60h] [rbp-A0h] BYREF
  void *FileHandlea; // [rsp+68h] [rbp-98h] BYREF
  ULONG InputBufferLength; // [rsp+70h] [rbp-90h] BYREF
  DWORD BytesReturned; // [rsp+74h] [rbp-8Ch] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+78h] [rbp-88h] BYREF
  _BYTE v37[40]; // [rsp+88h] [rbp-78h] BYREF
  __int128 v38; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v39; // [rsp+C0h] [rbp-40h]
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+D0h] [rbp-30h] BYREF
  LPVOID *p_lpMem; // [rsp+100h] [rbp+0h]
  char v42; // [rsp+108h] [rbp+8h]
  _BYTE v43[128]; // [rsp+110h] [rbp+10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1B8h] [rbp+B8h]
  __int64 InBuffer; // [rsp+1D8h] [rbp+D8h] BYREF

  if ( a4 )
  {
    InBuffer = *((_QWORD *)a2 + 2);
    AllocationSize = (PLARGE_INTEGER)*((_QWORD *)a2 + 4);
    v8 = EfspCreateLogHeader(a4, *((unsigned int *)a2 + 1), &InBuffer, 0);
    if ( v8 < 0 )
      return wil::details::in1diag3::Return_NtStatus(
               retaddr,
               (void *)0x34D,
               (unsigned int)"onecoreuap\\ds\\security\\efs\\dll\\efsonline.cxx",
               (const char *)(unsigned int)v8,
               (int)AllocationSize);
    if ( dword_1801173AC == 1 )
    {
      if ( a5 )
        *a5 = 1;
      return 0;
    }
  }
  InputBufferLength = 0;
  v10 = 0;
  lpMem = 0;
  p_lpMem = &lpMem;
  v42 = 1;
  IoStatusBlock = 0;
  if ( !*((_BYTE *)a2 + 49) )
  {
    FileHandlea = 0;
    LOWORD(InBuffer) = 0;
    BytesReturned = 0;
    v11 = lambda_c87dce764c99cda538332fbfe22cdb1d_::_lambda_c87dce764c99cda538332fbfe22cdb1d_(
            &v38,
            &FileHandlea,
            &InBuffer,
            &BytesReturned);
    wil::scope_exit__lambda_a1be82231ecfb5f14ff8a6e98e8eae11___(v37, v11);
    if ( (*((_DWORD *)a2 + 6) & 0x800) != 0 )
    {
      *(_QWORD *)&ObjectAttributes.Length = 48;
      *(_QWORD *)&ObjectAttributes.Attributes = 64;
      ObjectAttributes.RootDirectory = 0;
      ObjectAttributes.ObjectName = (PUNICODE_STRING)*((_QWORD *)a2 + 5);
      *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
      wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
        &FileHandlea,
        0);
      v12 = NtCreateFile(&FileHandlea, 0x100183u, &ObjectAttributes, &IoStatusBlock, 0, 0, 7u, 1u, 0x200060u, 0, 0);
      if ( v12 < 0 )
      {
        v13 = 898;
LABEL_11:
        LastError = wil::details::in1diag3::Return_NtStatus(
                      retaddr,
                      (void *)v13,
                      (unsigned int)"onecoreuap\\ds\\security\\efs\\dll\\efsonline.cxx",
                      (const char *)(unsigned int)v12,
                      (int)AllocationSize);
LABEL_12:
        v15 = LastError;
LABEL_13:
        wil::details::lambda_call__lambda_a1be82231ecfb5f14ff8a6e98e8eae11___::_lambda_call__lambda_a1be82231ecfb5f14ff8a6e98e8eae11___(v37);
        wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&FileHandlea);
LABEL_14:
        v16 = lpMem;
        if ( lpMem )
        {
          ProcessHeap = GetProcessHeap();
          HeapFree(ProcessHeap, 0, v16);
        }
        return v15;
      }
      LOWORD(InBuffer) = 0;
      if ( !DeviceIoControl(FileHandlea, 0x9C040u, &InBuffer, 2u, 0, 0, &BytesReturned, 0) )
      {
        LastError = wil::details::in1diag3::Return_GetLastError(
                      retaddr,
                      (void *)0x386,
                      (unsigned int)"onecoreuap\\ds\\security\\efs\\dll\\efsonline.cxx",
                      v18);
        goto LABEL_12;
      }
    }
    v19 = OefspPrepareFsctl(0, a3, &lpMem, &InputBufferLength);
    v15 = v19;
    if ( v19 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x38A,
        (unsigned int)"onecoreuap\\ds\\security\\efs\\dll\\efsonline.cxx",
        (const char *)(unsigned int)v19,
        (int)AllocationSize);
      goto LABEL_13;
    }
    v12 = NtFsControlFile(FileHandle, 0, 0, 0, &IoStatusBlock, 0x900D7u, lpMem, InputBufferLength, 0, 0);
    if ( v12 < 0 )
    {
      v13 = 909;
      goto LABEL_11;
    }
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
      &FileHandlea,
      0);
    if ( dword_1801173AC == 2 && !*((_BYTE *)a2 + 48) )
    {
      wil::details::lambda_call__lambda_a1be82231ecfb5f14ff8a6e98e8eae11___::_lambda_call__lambda_a1be82231ecfb5f14ff8a6e98e8eae11___(v37);
      wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&FileHandlea);
      goto LABEL_45;
    }
    wil::details::lambda_call__lambda_a1be82231ecfb5f14ff8a6e98e8eae11___::_lambda_call__lambda_a1be82231ecfb5f14ff8a6e98e8eae11___(v37);
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&FileHandlea);
    v10 = lpMem;
  }
  v20 = a5;
  if ( a5 )
    *a5 = 1;
  if ( v10 )
  {
    v21 = GetProcessHeap();
    HeapFree(v21, 0, v10);
    lpMem = 0;
  }
  v22 = OefspPrepareFsctl(1, a3, &lpMem, &InputBufferLength);
  if ( v22 >= 0 )
  {
    LOBYTE(InBuffer) = 0;
    v26 = lambda_c87dce764c99cda538332fbfe22cdb1d_::_lambda_c87dce764c99cda538332fbfe22cdb1d_(
            v37,
            &IoStatusBlock,
            &lpMem,
            &InputBufferLength);
    v38 = *(_OWORD *)v26;
    v39 = *(_QWORD *)(v26 + 16);
    v27 = wistd::function_long___cdecl_void____::function_long___cdecl_void______lambda_ac90a4eade63a2f8b1251779080bea26__void_(
            v43,
            &v38);
    v22 = OefspIterateThroughStreams(FileHandle, a2, v27, (char *)&InBuffer);
    if ( v22 >= 0 )
    {
      if ( !(_BYTE)InBuffer && (dword_1801173AC != 4 || *((_BYTE *)a2 + 48)) )
      {
        v28 = EfspSendSkFsctl(0, 0, 9, FileHandle);
        if ( v28 < 0 )
        {
          v15 = wil::details::in1diag3::Return_NtStatus(
                  retaddr,
                  (void *)0x3BC,
                  (unsigned int)"onecoreuap\\ds\\security\\efs\\dll\\efsonline.cxx",
                  (const char *)(unsigned int)v28,
                  590043);
          goto LABEL_14;
        }
        if ( v20 )
          *v20 = byte_1801173B0 != 0;
      }
LABEL_45:
      v29 = lpMem;
      if ( lpMem )
      {
        v30 = GetProcessHeap();
        HeapFree(v30, 0, v29);
      }
      return 0;
    }
    v23 = 944;
  }
  else
  {
    v23 = 934;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v23,
    (unsigned int)"onecoreuap\\ds\\security\\efs\\dll\\efsonline.cxx",
    (const char *)(unsigned int)v22,
    (int)AllocationSize);
  v24 = lpMem;
  if ( lpMem )
  {
    v25 = GetProcessHeap();
    HeapFree(v25, 0, v24);
  }
  return v22;
}

```

## disassembly

```asm
0x18004f4f8  mov     [rsp-8+arg_0], rbx
0x18004f4fd  mov     [rsp-8+arg_8], rsi
0x18004f502  push    rbp
0x18004f503  push    rdi
0x18004f504  push    r12
0x18004f506  push    r14
0x18004f508  push    r15
0x18004f50a  lea     rbp, [rsp-90h]
0x18004f512  sub     rsp, 190h
0x18004f519  mov     r10, r9
0x18004f51c  mov     r15, r8
0x18004f51f  mov     rbx, rdx
0x18004f522  mov     r14, rcx
0x18004f525  xor     r12d, r12d
0x18004f528  test    r9, r9
0x18004f52b  jz      loc_18004F5B6
0x18004f531  mov     rax, [rdx+10h]
0x18004f535  mov     [rbp+0B0h+InBuffer], rax
0x18004f53c  mov     qword ptr [rsp+1B0h+CreateOptions], r12
0x18004f541  mov     [rsp+1B0h+CreateDisposition], r12d
0x18004f546  mov     [rsp+1B0h+ShareAccess], 4
0x18004f54e  mov     qword ptr [rsp+1B0h+FileAttributes], r12
0x18004f553  mov     rax, [rdx+20h]
0x18004f557  mov     [rsp+1B0h+AllocationSize], rax; int
0x18004f55c  xor     r9d, r9d
0x18004f55f  lea     r8, [rbp+0B0h+InBuffer]
0x18004f566  mov     edx, [rdx+4]
0x18004f569  mov     rcx, r10
0x18004f56c  call    EfspCreateLogHeader
0x18004f571  test    eax, eax
0x18004f573  jns     short loc_18004F595
0x18004f575  mov     rcx, [rbp+0B8h]; this
0x18004f57c  mov     r9d, eax; char *
0x18004f57f  lea     r8, aOnecoreuapDsSe_10; "onecoreuap\\ds\\security\\efs\\dll\\efs"...
0x18004f586  mov     edx, 34Dh; void *
0x18004f58b  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x18004f590  jmp     loc_18004F9A9
0x18004f595  cmp     cs:dword_1801173AC, 1
0x18004f59c  jnz     short loc_18004F5B6
0x18004f59e  mov     rax, [rbp+0B0h+arg_20]
0x18004f5a5  test    rax, rax
0x18004f5a8  jz      loc_18004F9A7
0x18004f5ae  mov     byte ptr [rax], 1
0x18004f5b1  jmp     loc_18004F9A7
0x18004f5b6  mov     [rsp+1B0h+InputBufferLength], r12d
0x18004f5bb  mov     rsi, r12
0x18004f5be  mov     [rsp+1B0h+lpMem], r12
0x18004f5c3  lea     rax, [rsp+1B0h+lpMem]
0x18004f5c8  mov     [rbp+0B0h+var_B0], rax
0x18004f5cc  mov     [rbp+0B0h+var_A8], 1
0x18004f5d0  xorps   xmm0, xmm0
0x18004f5d3  movups  xmmword ptr [rsp+1B0h+IoStatusBlock], xmm0
0x18004f5d8  cmp     [rbx+31h], r12b
0x18004f5dc  jnz     loc_18004F82B
0x18004f5e2  mov     [rsp+1B0h+FileHandle], r12
0x18004f5e7  mov     word ptr [rbp+0B0h+InBuffer], r12w
0x18004f5ef  mov     [rsp+1B0h+BytesReturned], r12d
0x18004f5f4  lea     r9, [rsp+1B0h+BytesReturned]
0x18004f5f9  lea     r8, [rbp+0B0h+InBuffer]
0x18004f600  lea     rdx, [rsp+1B0h+FileHandle]
0x18004f605  lea     rcx, [rbp+0B0h+var_100]
0x18004f609  call    _lambda_c87dce764c99cda538332fbfe22cdb1d____lambda_c87dce764c99cda538332fbfe22cdb1d_
0x18004f60e  mov     rdx, rax
0x18004f611  lea     rcx, [rbp+0B0h+var_128]
0x18004f615  call    wil__scope_exit__lambda_a1be82231ecfb5f14ff8a6e98e8eae11___
0x18004f61a  nop
0x18004f61b  test    dword ptr [rbx+18h], 800h
0x18004f622  jz      loc_18004F757
0x18004f628  mov     qword ptr [rbp+0B0h+ObjectAttributes.Length], 30h ; '0'
0x18004f630  mov     qword ptr [rbp+0B0h+ObjectAttributes.Attributes], 40h ; '@'
0x18004f638  mov     [rbp+0B0h+ObjectAttributes.RootDirectory], r12
0x18004f63c  mov     rax, [rbx+28h]
0x18004f640  mov     [rbp+0B0h+ObjectAttributes.ObjectName], rax
0x18004f644  xorps   xmm0, xmm0
0x18004f647  movdqu  xmmword ptr [rbp+0B0h+ObjectAttributes.SecurityDescriptor], xmm0
0x18004f64c  xor     edx, edx
0x18004f64e  lea     rcx, [rsp+1B0h+FileHandle]
0x18004f653  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x18004f658  mov     [rsp+1B0h+EaLength], r12d; EaLength
0x18004f65d  mov     [rsp+1B0h+EaBuffer], r12; EaBuffer
0x18004f662  mov     [rsp+1B0h+CreateOptions], 200060h; CreateOptions
0x18004f66a  mov     [rsp+1B0h+CreateDisposition], 1; CreateDisposition
0x18004f672  mov     [rsp+1B0h+ShareAccess], 7; ShareAccess
0x18004f67a  mov     [rsp+1B0h+FileAttributes], r12d; FileAttributes
0x18004f67f  mov     [rsp+1B0h+AllocationSize], r12; int
0x18004f684  lea     r9, [rsp+1B0h+IoStatusBlock]; IoStatusBlock
0x18004f689  lea     r8, [rbp+0B0h+ObjectAttributes]; ObjectAttributes
0x18004f68d  mov     edx, 100183h; DesiredAccess
0x18004f692  lea     rcx, [rsp+1B0h+FileHandle]; FileHandle
0x18004f697  call    cs:__imp_NtCreateFile
0x18004f69d  test    eax, eax
0x18004f69f  jns     short loc_18004F6F8
0x18004f6a1  mov     edx, 382h; void *
0x18004f6a6  lea     r8, aOnecoreuapDsSe_10; "onecoreuap\\ds\\security\\efs\\dll\\efs"...
0x18004f6ad  mov     r9d, eax; char *
0x18004f6b0  mov     rcx, [rbp+0B8h]; this
0x18004f6b7  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x18004f6bc  mov     edi, eax
0x18004f6be  lea     rcx, [rbp+0B0h+var_128]
0x18004f6c2  call    wil__details__lambda_call__lambda_a1be82231ecfb5f14ff8a6e98e8eae11______lambda_call__lambda_a1be82231ecfb5f14ff8a6e98e8eae11___
0x18004f6c7  nop
0x18004f6c8  lea     rcx, [rsp+1B0h+FileHandle]
0x18004f6cd  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18004f6d2  nop
0x18004f6d3  mov     rbx, [rsp+1B0h+lpMem]
0x18004f6d8  test    rbx, rbx
0x18004f6db  jz      short loc_18004F6F1
0x18004f6dd  call    cs:__imp_GetProcessHeap
0x18004f6e3  mov     r8, rbx; lpMem
0x18004f6e6  xor     edx, edx; dwFlags
0x18004f6e8  mov     rcx, rax; hHeap
0x18004f6eb  call    cs:__imp_HeapFree
0x18004f6f1  mov     eax, edi
0x18004f6f3  jmp     loc_18004F9A9
0x18004f6f8  mov     word ptr [rbp+0B0h+InBuffer], r12w
0x18004f700  mov     qword ptr [rsp+1B0h+CreateDisposition], r12; lpOverlapped
0x18004f705  lea     rax, [rsp+1B0h+BytesReturned]
0x18004f70a  mov     qword ptr [rsp+1B0h+ShareAccess], rax; lpBytesReturned
0x18004f70f  mov     [rsp+1B0h+FileAttributes], r12d; nOutBufferSize
0x18004f714  mov     [rsp+1B0h+AllocationSize], r12; lpOutBuffer
0x18004f719  mov     r9d, 2; nInBufferSize
0x18004f71f  lea     r8, [rbp+0B0h+InBuffer]; lpInBuffer
0x18004f726  mov     edx, 9C040h; dwIoControlCode
0x18004f72b  mov     rcx, [rsp+1B0h+FileHandle]; hDevice
0x18004f730  call    cs:__imp_DeviceIoControl
0x18004f736  test    eax, eax
0x18004f738  jnz     short loc_18004F757
0x18004f73a  mov     rcx, [rbp+0B8h]; this
0x18004f741  lea     r8, aOnecoreuapDsSe_10; "onecoreuap\\ds\\security\\efs\\dll\\efs"...
0x18004f748  mov     edx, 386h; void *
0x18004f74d  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18004f752  jmp     loc_18004F6BC
0x18004f757  lea     r9, [rsp+1B0h+InputBufferLength]
0x18004f75c  lea     r8, [rsp+1B0h+lpMem]
0x18004f761  mov     rdx, r15
0x18004f764  xor     ecx, ecx
0x18004f766  call    ?OefspPrepareFsctl@@YAJW4EfsFsctlOperation@@AEAVEfsStreamAndFileKey@@PEAPEAEPEAK@Z; OefspPrepareFsctl(EfsFsctlOperation,EfsStreamAndFileKey &,uchar * *,ulong *)
0x18004f76b  mov     edi, eax
0x18004f76d  test    eax, eax
0x18004f76f  jns     short loc_18004F791
0x18004f771  mov     rcx, [rbp+0B8h]; this
0x18004f778  mov     r9d, eax; char *
0x18004f77b  lea     r8, aOnecoreuapDsSe_10; "onecoreuap\\ds\\security\\efs\\dll\\efs"...
0x18004f782  mov     edx, 38Ah; void *
0x18004f787  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004f78c  jmp     loc_18004F6BE
0x18004f791  mov     dword ptr [rsp+1B0h+EaBuffer], r12d; OutputBufferLength
0x18004f796  mov     qword ptr [rsp+1B0h+CreateOptions], r12; OutputBuffer
0x18004f79b  mov     eax, [rsp+1B0h+InputBufferLength]
0x18004f79f  mov     [rsp+1B0h+CreateDisposition], eax; InputBufferLength
0x18004f7a3  mov     rax, [rsp+1B0h+lpMem]
0x18004f7a8  mov     qword ptr [rsp+1B0h+ShareAccess], rax; InputBuffer
0x18004f7ad  mov     [rsp+1B0h+FileAttributes], 900D7h; FsControlCode
0x18004f7b5  lea     rax, [rsp+1B0h+IoStatusBlock]
0x18004f7ba  mov     [rsp+1B0h+AllocationSize], rax; int
0x18004f7bf  xor     r9d, r9d; ApcContext
0x18004f7c2  xor     r8d, r8d; ApcRoutine
0x18004f7c5  xor     edx, edx; Event
0x18004f7c7  mov     rcx, r14; FileHandle
0x18004f7ca  call    cs:__imp_NtFsControlFile
0x18004f7d0  test    eax, eax
0x18004f7d2  jns     short loc_18004F7DE
0x18004f7d4  mov     edx, 38Dh
0x18004f7d9  jmp     loc_18004F6A6
0x18004f7de  xor     edx, edx
0x18004f7e0  lea     rcx, [rsp+1B0h+FileHandle]
0x18004f7e5  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x18004f7ea  cmp     cs:dword_1801173AC, 2
0x18004f7f1  jnz     short loc_18004F812
0x18004f7f3  cmp     [rbx+30h], r12b
0x18004f7f7  jnz     short loc_18004F812
0x18004f7f9  lea     rcx, [rbp+0B0h+var_128]
0x18004f7fd  call    wil__details__lambda_call__lambda_a1be82231ecfb5f14ff8a6e98e8eae11______lambda_call__lambda_a1be82231ecfb5f14ff8a6e98e8eae11___
0x18004f802  nop
0x18004f803  lea     rcx, [rsp+1B0h+FileHandle]
0x18004f808  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18004f80d  jmp     loc_18004F989
0x18004f812  lea     rcx, [rbp+0B0h+var_128]
0x18004f816  call    wil__details__lambda_call__lambda_a1be82231ecfb5f14ff8a6e98e8eae11______lambda_call__lambda_a1be82231ecfb5f14ff8a6e98e8eae11___
0x18004f81b  nop
0x18004f81c  lea     rcx, [rsp+1B0h+FileHandle]
0x18004f821  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18004f826  mov     rsi, [rsp+1B0h+lpMem]
0x18004f82b  mov     rdi, [rbp+0B0h+arg_20]
0x18004f832  test    rdi, rdi
0x18004f835  jz      short loc_18004F83A
0x18004f837  mov     byte ptr [rdi], 1
0x18004f83a  test    rsi, rsi
0x18004f83d  jz      short loc_18004F858
0x18004f83f  call    cs:__imp_GetProcessHeap
0x18004f845  mov     r8, rsi; lpMem
0x18004f848  xor     edx, edx; dwFlags
0x18004f84a  mov     rcx, rax; hHeap
0x18004f84d  call    cs:__imp_HeapFree
0x18004f853  mov     [rsp+1B0h+lpMem], r12
0x18004f858  lea     r9, [rsp+1B0h+InputBufferLength]
0x18004f85d  lea     r8, [rsp+1B0h+lpMem]
0x18004f862  mov     rdx, r15
0x18004f865  mov     ecx, 1
0x18004f86a  call    ?OefspPrepareFsctl@@YAJW4EfsFsctlOperation@@AEAVEfsStreamAndFileKey@@PEAPEAEPEAK@Z; OefspPrepareFsctl(EfsFsctlOperation,EfsStreamAndFileKey &,uchar * *,ulong *)
0x18004f86f  mov     esi, eax
0x18004f871  test    eax, eax
0x18004f873  jns     short loc_18004F8B6
0x18004f875  mov     edx, 3A6h; void *
0x18004f87a  lea     r8, aOnecoreuapDsSe_10; "onecoreuap\\ds\\security\\efs\\dll\\efs"...
0x18004f881  mov     r9d, esi; char *
0x18004f884  mov     rcx, [rbp+0B8h]; this
0x18004f88b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004f890  nop
0x18004f891  mov     rbx, [rsp+1B0h+lpMem]
0x18004f896  test    rbx, rbx
0x18004f899  jz      short loc_18004F8AF
0x18004f89b  call    cs:__imp_GetProcessHeap
0x18004f8a1  mov     r8, rbx; lpMem
0x18004f8a4  xor     edx, edx; dwFlags
0x18004f8a6  mov     rcx, rax; hHeap
0x18004f8a9  call    cs:__imp_HeapFree
0x18004f8af  mov     eax, esi
0x18004f8b1  jmp     loc_18004F9A9
0x18004f8b6  mov     byte ptr [rbp+0B0h+InBuffer], r12b
0x18004f8bd  lea     r9, [rsp+1B0h+InputBufferLength]
0x18004f8c2  lea     r8, [rsp+1B0h+lpMem]
0x18004f8c7  lea     rdx, [rsp+1B0h+IoStatusBlock]
0x18004f8cc  lea     rcx, [rbp+0B0h+var_128]
0x18004f8d0  call    _lambda_c87dce764c99cda538332fbfe22cdb1d____lambda_c87dce764c99cda538332fbfe22cdb1d_
0x18004f8d5  movups  xmm0, xmmword ptr [rax]
0x18004f8d8  movaps  [rbp+0B0h+var_100], xmm0
0x18004f8dc  movsd   xmm1, qword ptr [rax+10h]
0x18004f8e1  movsd   [rbp+0B0h+var_F0], xmm1
0x18004f8e6  lea     rdx, [rbp+0B0h+var_100]
0x18004f8ea  lea     rcx, [rbp+0B0h+var_A0]
0x18004f8ee  call    wistd__function_long___cdecl_void______function_long___cdecl_void______lambda_ac90a4eade63a2f8b1251779080bea26__void_
0x18004f8f3  lea     r9, [rbp+0B0h+InBuffer]
0x18004f8fa  mov     r8, rax
0x18004f8fd  mov     rdx, rbx
0x18004f900  mov     rcx, r14; FileHandle
0x18004f903  call    ?OefspIterateThroughStreams@@YAJPEAXAEBUOEFS_FILE_INFORMATION@@V?$function@$$A6AJPEAX@Z@wistd@@PEA_N@Z; OefspIterateThroughStreams(void *,OEFS_FILE_INFORMATION const &,wistd::function<long (void *)>,bool *)
0x18004f908  mov     esi, eax
0x18004f90a  test    eax, eax
0x18004f90c  jns     short loc_18004F918
0x18004f90e  mov     edx, 3B0h
0x18004f913  jmp     loc_18004F87A
0x18004f918  cmp     byte ptr [rbp+0B0h+InBuffer], r12b
0x18004f91f  jnz     short loc_18004F989
0x18004f921  cmp     cs:dword_1801173AC, 4
0x18004f928  jnz     short loc_18004F930
0x18004f92a  cmp     [rbx+30h], r12b
0x18004f92e  jz      short loc_18004F989
0x18004f930  lea     rax, [rsp+1B0h+IoStatusBlock]
0x18004f935  mov     qword ptr [rsp+1B0h+FileAttributes], rax
0x18004f93a  mov     dword ptr [rsp+1B0h+AllocationSize], 900DBh; int
0x18004f942  mov     r9, r14
0x18004f945  xor     edx, edx
0x18004f947  xor     ecx, ecx
0x18004f949  lea     r8d, [rdx+9]
0x18004f94d  call    EfspSendSkFsctl
0x18004f952  test    eax, eax
0x18004f954  jns     short loc_18004F978
0x18004f956  mov     rcx, [rbp+0B8h]; this
0x18004f95d  mov     r9d, eax; char *
0x18004f960  lea     r8, aOnecoreuapDsSe_10; "onecoreuap\\ds\\security\\efs\\dll\\efs"...
0x18004f967  mov     edx, 3BCh; void *
0x18004f96c  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x18004f971  mov     edi, eax
0x18004f973  jmp     loc_18004F6D3
0x18004f978  test    rdi, rdi
0x18004f97b  jz      short loc_18004F989
0x18004f97d  cmp     cs:byte_1801173B0, r12b
0x18004f984  setnz   al
0x18004f987  mov     [rdi], al
0x18004f989  mov     rbx, [rsp+1B0h+lpMem]
0x18004f98e  test    rbx, rbx
0x18004f991  jz      short loc_18004F9A7
0x18004f993  call    cs:__imp_GetProcessHeap
0x18004f999  mov     r8, rbx; lpMem
0x18004f99c  xor     edx, edx; dwFlags
0x18004f99e  mov     rcx, rax; hHeap
0x18004f9a1  call    cs:__imp_HeapFree
0x18004f9a7  xor     eax, eax
0x18004f9a9  lea     r11, [rsp+1B0h+var_20]
0x18004f9b1  mov     rbx, [r11+30h]
0x18004f9b5  mov     rsi, [r11+38h]
0x18004f9b9  mov     rsp, r11
0x18004f9bc  pop     r15
0x18004f9be  pop     r14
0x18004f9c0  pop     r12
0x18004f9c2  pop     rdi
0x18004f9c3  pop     rbp
0x18004f9c4  retn
```
