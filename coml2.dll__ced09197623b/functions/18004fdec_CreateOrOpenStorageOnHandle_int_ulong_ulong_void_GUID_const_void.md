# CreateOrOpenStorageOnHandle(int,ulong,ulong,void *,_GUID const &,void * *)

- ea: `0x18004fdec`
- end: `0x18004ff9a`
- name: `?CreateOrOpenStorageOnHandle@@YAHHKKPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `430`
- prototype: `int(int, unsigned int, unsigned int, void *, const struct _GUID *, void **)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x180050250`

## callees

- `0x18001eef0`
- `0x180033ec0`
- `0x180042800`
- `0x18004fc90`
- `0x18004fdec`
- `0x180053e30`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004fe84`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004fec1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004fe84`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004fec1`
- `api-ms-win-core-file-l1-1-0!GetFileInformationByHandle` at `0x18004ff0e`
- `api-ms-win-core-file-l1-1-0!GetFileInformationByHandle` at `0x18004ff0e`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x18004fe7a`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x18004fe7a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004ff45`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004ff54`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004ff45`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004ff54`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18004fe46`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18004fe4f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18004fe46`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18004fe4f`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18004feb2`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18004feb2`

## pseudocode

```c
__int64 __fastcall CreateOrOpenStorageOnHandle(
        __int64 a1,
        unsigned int a2,
        __int64 a3,
        void *a4,
        const struct _GUID *a5,
        void **a6)
{
  __int64 result; // rax
  HANDLE CurrentProcess; // rbx
  HANDLE v10; // rax
  signed int v11; // eax
  unsigned int v12; // ebx
  signed int LastError; // eax
  int IsStorageFileHandle; // eax
  int v15; // ecx
  unsigned int v16; // r8d
  int v17; // eax
  HANDLE TargetHandle; // [rsp+40h] [rbp-49h] BYREF
  struct _OVERLAPPED Overlapped; // [rsp+48h] [rbp-41h] BYREF
  struct _BY_HANDLE_FILE_INFORMATION FileInformation; // [rsp+68h] [rbp-21h] BYREF

  TargetHandle = (HANDLE)-1LL;
  memset(&Overlapped, 0, sizeof(Overlapped));
  result = VerifyPerms(a2, 1);
  if ( (int)result < 0 )
    return result;
  CurrentProcess = GetCurrentProcess();
  v10 = GetCurrentProcess();
  if ( DuplicateHandle(v10, a4, CurrentProcess, &TargetHandle, 0, 0, 2u) )
  {
    Overlapped.hEvent = CreateEventW(0, 1, 0, 0);
    if ( !Overlapped.hEvent )
    {
      LastError = GetLastError();
      v12 = LastError;
      if ( LastError > 0 )
        v12 = (unsigned __int16)LastError | 0x80070000;
      goto LABEL_15;
    }
    IsStorageFileHandle = StgIsStorageFileHandle(TargetHandle, &Overlapped);
    v12 = IsStorageFileHandle;
    if ( IsStorageFileHandle == -2147024895 )
    {
      memset(&FileInformation, 0, sizeof(FileInformation));
      if ( GetFileInformationByHandle(TargetHandle, &FileInformation) && (FileInformation.dwFileAttributes & 0x10) != 0 )
        goto LABEL_12;
    }
    else if ( IsStorageFileHandle >= 0 )
    {
      if ( !IsStorageFileHandle )
      {
        v17 = CreateOrOpenDocfileOnHandle(v15, a2, &TargetHandle, a5, a6);
LABEL_13:
        v12 = v17;
        if ( v17 >= 0 )
          v12 = 0;
        goto LABEL_15;
      }
LABEL_12:
      v17 = NFFOpenOnHandle(v15, a2, v16, &TargetHandle, a5, a6);
      goto LABEL_13;
    }
LABEL_15:
    if ( TargetHandle != (HANDLE)-1LL )
      CloseHandle(TargetHandle);
    goto LABEL_17;
  }
  v11 = GetLastError();
  v12 = v11;
  if ( v11 > 0 )
    v12 = (unsigned __int16)v11 | 0x80070000;
  TargetHandle = (HANDLE)-1LL;
LABEL_17:
  if ( Overlapped.hEvent )
    CloseHandle(Overlapped.hEvent);
  return v12;
}

```

## disassembly

```asm
0x18004fdec  mov     [rsp-8+arg_0], rbx
0x18004fdf1  push    rbp
0x18004fdf2  push    rsi
0x18004fdf3  push    rdi
0x18004fdf4  push    r14
0x18004fdf6  push    r15
0x18004fdf8  lea     rbp, [rsp-27h]
0x18004fdfd  sub     rsp, 0B0h
0x18004fe04  mov     rax, cs:__security_cookie
0x18004fe0b  xor     rax, rsp
0x18004fe0e  mov     [rbp+47h+var_30], rax
0x18004fe12  mov     rsi, [rbp+47h+arg_20]
0x18004fe16  mov     edi, edx
0x18004fe18  mov     r14, [rbp+47h+arg_28]
0x18004fe1c  xorps   xmm0, xmm0
0x18004fe1f  mov     ecx, edi; unsigned int
0x18004fe21  mov     [rbp+47h+TargetHandle], 0FFFFFFFFFFFFFFFFh
0x18004fe29  mov     edx, 1; int
0x18004fe2e  mov     r15, r9
0x18004fe31  movups  xmmword ptr [rbp+47h+Overlapped.Internal], xmm0
0x18004fe35  movups  xmmword ptr [rbp+47h+Overlapped.10h], xmm0
0x18004fe39  call    ?VerifyPerms@@YAJKH@Z; VerifyPerms(ulong,int)
0x18004fe3e  test    eax, eax
0x18004fe40  js      loc_18004FF5C
0x18004fe46  call    cs:__imp_GetCurrentProcess
0x18004fe4c  mov     rbx, rax
0x18004fe4f  call    cs:__imp_GetCurrentProcess
0x18004fe55  mov     [rsp+0D0h+dwOptions], 2; dwOptions
0x18004fe5d  lea     r9, [rbp+47h+TargetHandle]; lpTargetHandle
0x18004fe61  mov     rcx, rax; hSourceProcessHandle
0x18004fe64  mov     [rsp+0D0h+bInheritHandle], 0; bInheritHandle
0x18004fe6c  mov     r8, rbx; hTargetProcessHandle
0x18004fe6f  mov     [rsp+0D0h+dwDesiredAccess], 0; dwDesiredAccess
0x18004fe77  mov     rdx, r15; hSourceHandle
0x18004fe7a  call    cs:__imp_DuplicateHandle
0x18004fe80  test    eax, eax
0x18004fe82  jnz     short loc_18004FEA6
0x18004fe84  call    cs:__imp_GetLastError
0x18004fe8a  mov     ebx, eax
0x18004fe8c  test    eax, eax
0x18004fe8e  jle     short loc_18004FE99
0x18004fe90  movzx   ebx, ax
0x18004fe93  or      ebx, 80070000h
0x18004fe99  mov     [rbp+47h+TargetHandle], 0FFFFFFFFFFFFFFFFh
0x18004fea1  jmp     loc_18004FF4B
0x18004fea6  xor     r9d, r9d; lpName
0x18004fea9  xor     r8d, r8d; bInitialState
0x18004feac  xor     ecx, ecx; lpEventAttributes
0x18004feae  lea     edx, [r9+1]; bManualReset
0x18004feb2  call    cs:__imp_CreateEventW
0x18004feb8  mov     [rbp+47h+Overlapped.hEvent], rax
0x18004febc  test    rax, rax
0x18004febf  jnz     short loc_18004FED8
0x18004fec1  call    cs:__imp_GetLastError
0x18004fec7  mov     ebx, eax
0x18004fec9  test    eax, eax
0x18004fecb  jle     short loc_18004FF3B
0x18004fecd  movzx   ebx, ax
0x18004fed0  or      ebx, 80070000h
0x18004fed6  jmp     short loc_18004FF3B
0x18004fed8  mov     rcx, [rbp+47h+TargetHandle]; hFile
0x18004fedc  lea     rdx, [rbp+47h+Overlapped]; lpOverlapped
0x18004fee0  call    StgIsStorageFileHandle
0x18004fee5  mov     ebx, eax
0x18004fee7  cmp     eax, 80070001h
0x18004feec  jnz     loc_18004FF7F
0x18004fef2  mov     rcx, [rbp+47h+TargetHandle]; hFile
0x18004fef6  lea     rdx, [rbp+47h+FileInformation]; lpFileInformation
0x18004fefa  xorps   xmm0, xmm0
0x18004fefd  xor     eax, eax
0x18004feff  movups  xmmword ptr [rbp+47h+FileInformation.dwFileAttributes], xmm0
0x18004ff03  mov     [rbp+47h+FileInformation.nFileIndexLow], eax
0x18004ff06  movups  xmmword ptr [rbp+47h+FileInformation.ftLastAccessTime.dwHighDateTime], xmm0
0x18004ff0a  movups  xmmword ptr [rbp+47h+FileInformation.nFileSizeHigh], xmm0
0x18004ff0e  call    cs:__imp_GetFileInformationByHandle
0x18004ff14  test    eax, eax
0x18004ff16  jz      short loc_18004FF3B
0x18004ff18  test    byte ptr [rbp+47h+FileInformation.dwFileAttributes], 10h
0x18004ff1c  jz      short loc_18004FF3B
0x18004ff1e  mov     qword ptr [rsp+0D0h+bInheritHandle], r14; void **
0x18004ff23  lea     r9, [rbp+47h+TargetHandle]; void **
0x18004ff27  mov     edx, edi; unsigned int
0x18004ff29  mov     qword ptr [rsp+0D0h+dwDesiredAccess], rsi; struct _GUID *
0x18004ff2e  call    ?NFFOpenOnHandle@@YAJHKKPEAPEAXAEBU_GUID@@0@Z; NFFOpenOnHandle(int,ulong,ulong,void * *,_GUID const &,void * *)
0x18004ff33  mov     ebx, eax
0x18004ff35  test    eax, eax
0x18004ff37  js      short loc_18004FF3B
0x18004ff39  xor     ebx, ebx
0x18004ff3b  mov     rcx, [rbp+47h+TargetHandle]; hObject
0x18004ff3f  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18004ff43  jz      short loc_18004FF4B
0x18004ff45  call    cs:__imp_CloseHandle
0x18004ff4b  mov     rcx, [rbp+47h+Overlapped.hEvent]; hObject
0x18004ff4f  test    rcx, rcx
0x18004ff52  jz      short loc_18004FF5A
0x18004ff54  call    cs:__imp_CloseHandle
0x18004ff5a  mov     eax, ebx
0x18004ff5c  mov     rcx, [rbp+47h+var_30]
0x18004ff60  xor     rcx, rsp; StackCookie
0x18004ff63  call    __security_check_cookie
0x18004ff68  mov     rbx, [rsp+0D0h+arg_0]
0x18004ff70  add     rsp, 0B0h
0x18004ff77  pop     r15
0x18004ff79  pop     r14
0x18004ff7b  pop     rdi
0x18004ff7c  pop     rsi
0x18004ff7d  pop     rbp
0x18004ff7e  retn
0x18004ff7f  test    eax, eax
0x18004ff81  js      short loc_18004FF3B
0x18004ff83  jnz     short loc_18004FF1E
0x18004ff85  mov     r9, rsi; struct _GUID *
0x18004ff88  mov     qword ptr [rsp+0D0h+dwDesiredAccess], r14; void **
0x18004ff8d  lea     r8, [rbp+47h+TargetHandle]; void **
0x18004ff91  mov     edx, edi; unsigned int
0x18004ff93  call    ?CreateOrOpenDocfileOnHandle@@YAHHKPEAPEAXAEBU_GUID@@0@Z; CreateOrOpenDocfileOnHandle(int,ulong,void * *,_GUID const &,void * *)
0x18004ff98  jmp     short loc_18004FF33
```
