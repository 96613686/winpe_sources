# DSUtils::DuplicateFileHandle(void *,ulong,void * *)

- ea: `0x18001a06c`
- end: `0x18001a1e0`
- name: `?DuplicateFileHandle@DSUtils@@YAJPEAXKPEAPEAX@Z`
- size: `372`
- prototype: `__int64 __fastcall(HANDLE hSourceHandle, DWORD dwProcessId, LPHANDLE lpTargetHandle, void **)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation`

## callers

- `0x18000d3e4`

## callees

- `0x180006b84`
- `0x180006f78`
- `0x18000bf80`
- `0x18001a06c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a10f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a138`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a174`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a10f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a138`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a174`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18001a0c0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18001a0c0`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18001a09f`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18001a09f`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x18001a101`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x18001a101`

## pseudocode

```c
__int64 __fastcall DSUtils::DuplicateFileHandle(
        HANDLE hSourceHandle,
        DWORD dwProcessId,
        LPHANDLE lpTargetHandle,
        void **a4)
{
  HANDLE v7; // rsi
  HANDLE CurrentProcess; // rdi
  unsigned int v9; // ebx
  signed int v10; // eax
  __int64 v11; // rdx
  __int64 v12; // rcx
  __int64 v13; // r8
  __int64 v14; // r9
  DSLogger *v15; // rax
  const unsigned __int16 *v16; // r9
  unsigned int v17; // r8d
  signed int LastError; // eax
  __int64 v19; // rdx
  __int64 v20; // rcx
  __int64 v21; // r8
  __int64 v22; // r9
  signed int v23; // eax
  __int64 v24; // rdx
  __int64 v25; // rcx
  __int64 v26; // r8
  __int64 v27; // r9
  DSLogger *v28; // rax
  __int64 dwDesiredAccess; // [rsp+20h] [rbp-48h]
  void *v31[5]; // [rsp+40h] [rbp-28h] BYREF
  void *v32; // [rsp+88h] [rbp+20h] BYREF

  v31[0] = 0;
  v32 = 0;
  v7 = OpenProcess(0x40u, 0, dwProcessId);
  if ( v7 )
  {
    tlx::auto_xxx<void *,int (*)(void *),&int CloseHandle(void *),0>::_Delete(v31);
    v31[0] = v7;
    CurrentProcess = GetCurrentProcess();
    if ( !CurrentProcess )
    {
      LastError = GetLastError();
      v9 = LastError;
      if ( LastError > 0 )
        v9 = (unsigned __int16)LastError | 0x80070000;
      v15 = (DSLogger *)tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get(
                          v20,
                          v19,
                          v21,
                          v22);
      v16 = L"Failed to get current process handle! HR=0x%x";
      v17 = 163;
      goto LABEL_10;
    }
    tlx::auto_xxx<void *,int (*)(void *),&int CloseHandle(void *),0>::_Delete(&v32);
    v32 = CurrentProcess;
    v9 = 0;
    if ( !DuplicateHandle(CurrentProcess, hSourceHandle, v7, lpTargetHandle, 0, 0, 2u) )
    {
      v10 = GetLastError();
      v9 = v10;
      if ( v10 > 0 )
        v9 = (unsigned __int16)v10 | 0x80070000;
      v15 = (DSLogger *)tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get(
                          v12,
                          v11,
                          v13,
                          v14);
      v16 = L"Failed to duplicate file handle! HR=0x%x";
      v17 = 170;
LABEL_10:
      LODWORD(dwDesiredAccess) = v9;
      DSLogger::LogError(v15, L"DSUtils::DuplicateFileHandle", v17, v16, dwDesiredAccess);
    }
  }
  else
  {
    v23 = GetLastError();
    v9 = v23;
    if ( v23 > 0 )
      v9 = (unsigned __int16)v23 | 0x80070000;
    v28 = (DSLogger *)tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get(
                        v25,
                        v24,
                        v26,
                        v27);
    DSLogger::LogError(
      v28,
      L"DSUtils::DuplicateFileHandle",
      0x9Bu,
      L"Failed to get target process (PID %d) handle! HR=0x%x",
      dwProcessId,
      v9);
  }
  tlx::auto_xxx<void *,int (*)(void *),&int CloseHandle(void *),0>::_Delete(&v32);
  tlx::auto_xxx<void *,int (*)(void *),&int CloseHandle(void *),0>::_Delete(v31);
  return v9;
}

```

## disassembly

```asm
0x18001a06c  mov     rax, rsp
0x18001a06f  mov     [rax+8], rbx
0x18001a073  mov     [rax+10h], rbp
0x18001a077  push    rsi
0x18001a078  push    rdi
0x18001a079  push    r14
0x18001a07b  sub     rsp, 50h
0x18001a07f  mov     rbp, r8
0x18001a082  mov     edi, edx
0x18001a084  mov     r14, rcx
0x18001a087  mov     qword ptr [rax-28h], 0
0x18001a08f  mov     qword ptr [rax+20h], 0
0x18001a097  mov     r8d, edx; dwProcessId
0x18001a09a  xor     edx, edx; bInheritHandle
0x18001a09c  lea     ecx, [rdx+40h]; dwDesiredAccess
0x18001a09f  call    cs:__imp_OpenProcess
0x18001a0a5  mov     rsi, rax
0x18001a0a8  test    rax, rax
0x18001a0ab  jz      loc_18001A174
0x18001a0b1  lea     rcx, [rsp+68h+var_28]
0x18001a0b6  call    ?_Delete@?$auto_xxx@PEAXP6AHPEAX@Z$1?CloseHandle@@YAH0@Z$0A@@tlx@@AEAAXXZ; tlx::auto_xxx<void *,int (*)(void *),&CloseHandle(void *),0>::_Delete(void)
0x18001a0bb  mov     [rsp+68h+var_28], rsi
0x18001a0c0  call    cs:__imp_GetCurrentProcess
0x18001a0c6  mov     rdi, rax
0x18001a0c9  test    rax, rax
0x18001a0cc  jz      short loc_18001A138
0x18001a0ce  lea     rcx, [rsp+68h+arg_18]
0x18001a0d6  call    ?_Delete@?$auto_xxx@PEAXP6AHPEAX@Z$1?CloseHandle@@YAH0@Z$0A@@tlx@@AEAAXXZ; tlx::auto_xxx<void *,int (*)(void *),&CloseHandle(void *),0>::_Delete(void)
0x18001a0db  mov     [rsp+68h+arg_18], rdi
0x18001a0e3  xor     ebx, ebx
0x18001a0e5  mov     [rsp+68h+dwOptions], 2; dwOptions
0x18001a0ed  mov     [rsp+68h+bInheritHandle], ebx; bInheritHandle
0x18001a0f1  mov     dword ptr [rsp+68h+dwDesiredAccess], ebx; dwDesiredAccess
0x18001a0f5  mov     r9, rbp; lpTargetHandle
0x18001a0f8  mov     r8, rsi; hTargetProcessHandle
0x18001a0fb  mov     rdx, r14; hSourceHandle
0x18001a0fe  mov     rcx, rdi; hSourceProcessHandle
0x18001a101  call    cs:__imp_DuplicateHandle
0x18001a107  test    eax, eax
0x18001a109  jnz     loc_18001A1B3
0x18001a10f  call    cs:__imp_GetLastError
0x18001a115  mov     ebx, eax
0x18001a117  test    eax, eax
0x18001a119  jle     short loc_18001A124
0x18001a11b  movzx   ebx, ax
0x18001a11e  or      ebx, 80070000h
0x18001a124  call    ?get@?$_LazyImpl@VDSLogger@@V?$lazy_construct@VDSLogger@@@tlx@@V?$static_lazy@VDSLogger@@$0A@V?$lazy_construct@VDSLogger@@@tlx@@@3@@tlx@@QEAAAEAVDSLogger@@XZ; tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get(void)
0x18001a129  lea     r9, aFailedToDuplic; "Failed to duplicate file handle! HR=0x%"...
0x18001a130  mov     r8d, 0AAh
0x18001a136  jmp     short loc_18001A15F
0x18001a138  call    cs:__imp_GetLastError
0x18001a13e  mov     ebx, eax
0x18001a140  test    eax, eax
0x18001a142  jle     short loc_18001A14D
0x18001a144  movzx   ebx, ax
0x18001a147  or      ebx, 80070000h
0x18001a14d  call    ?get@?$_LazyImpl@VDSLogger@@V?$lazy_construct@VDSLogger@@@tlx@@V?$static_lazy@VDSLogger@@$0A@V?$lazy_construct@VDSLogger@@@tlx@@@3@@tlx@@QEAAAEAVDSLogger@@XZ; tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get(void)
0x18001a152  lea     r9, aFailedToGetCur; "Failed to get current process handle! H"...
0x18001a159  mov     r8d, 0A3h; unsigned int
0x18001a15f  mov     dword ptr [rsp+68h+dwDesiredAccess], ebx
0x18001a163  lea     rdx, aDsutilsDuplica; "DSUtils::DuplicateFileHandle"
0x18001a16a  mov     rcx, rax; this
0x18001a16d  call    ?LogError@DSLogger@@QEAAXPEBGK0ZZ; DSLogger::LogError(ushort const *,ulong,ushort const *,...)
0x18001a172  jmp     short loc_18001A1B3
0x18001a174  call    cs:__imp_GetLastError
0x18001a17a  mov     ebx, eax
0x18001a17c  test    eax, eax
0x18001a17e  jle     short loc_18001A189
0x18001a180  movzx   ebx, ax
0x18001a183  or      ebx, 80070000h
0x18001a189  call    ?get@?$_LazyImpl@VDSLogger@@V?$lazy_construct@VDSLogger@@@tlx@@V?$static_lazy@VDSLogger@@$0A@V?$lazy_construct@VDSLogger@@@tlx@@@3@@tlx@@QEAAAEAVDSLogger@@XZ; tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get(void)
0x18001a18e  mov     [rsp+68h+bInheritHandle], ebx
0x18001a192  mov     dword ptr [rsp+68h+dwDesiredAccess], edi
0x18001a196  lea     r9, aFailedToGetTar; "Failed to get target process (PID %d) h"...
0x18001a19d  mov     r8d, 9Bh; unsigned int
0x18001a1a3  lea     rdx, aDsutilsDuplica; "DSUtils::DuplicateFileHandle"
0x18001a1aa  mov     rcx, rax; this
0x18001a1ad  call    ?LogError@DSLogger@@QEAAXPEBGK0ZZ; DSLogger::LogError(ushort const *,ulong,ushort const *,...)
0x18001a1b2  nop
0x18001a1b3  lea     rcx, [rsp+68h+arg_18]
0x18001a1bb  call    ?_Delete@?$auto_xxx@PEAXP6AHPEAX@Z$1?CloseHandle@@YAH0@Z$0A@@tlx@@AEAAXXZ; tlx::auto_xxx<void *,int (*)(void *),&CloseHandle(void *),0>::_Delete(void)
0x18001a1c0  nop
0x18001a1c1  lea     rcx, [rsp+68h+var_28]
0x18001a1c6  call    ?_Delete@?$auto_xxx@PEAXP6AHPEAX@Z$1?CloseHandle@@YAH0@Z$0A@@tlx@@AEAAXXZ; tlx::auto_xxx<void *,int (*)(void *),&CloseHandle(void *),0>::_Delete(void)
0x18001a1cb  mov     eax, ebx
0x18001a1cd  mov     rbx, [rsp+68h+arg_0]
0x18001a1d2  mov     rbp, [rsp+68h+arg_8]
0x18001a1d7  add     rsp, 50h
0x18001a1db  pop     r14
0x18001a1dd  pop     rdi
0x18001a1de  pop     rsi
0x18001a1df  retn
```
