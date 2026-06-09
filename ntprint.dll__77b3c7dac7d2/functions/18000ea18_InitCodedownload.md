# InitCodedownload

- ea: `0x18000ea18`
- end: `0x18000eb0a`
- name: `InitCodedownload`
- size: `242`
- prototype: ``
- caller_count: `4`
- callee_count: `4`
- tags: `loader_planting, installer_update`

## callers

- `0x18000ac60`
- `0x18000ca40`
- `0x180013260`
- `0x18002bfc0`

## callees

- `0x18000dadc`
- `0x18000ea18`
- `0x180020820`
- `0x18003a010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000ea7e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000ea92`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000eaa6`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000ea7e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000ea92`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000eaa6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000eaf7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000eaf7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000ea2c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000ea2c`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000ea4e`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000ea4e`

## string_xrefs

- `0x18000ea60`: `wudriver.dll`
- `0x18000ea74`: `OpenCDMContext`
- `0x18000ea87`: `DownloadUpdatedFiles`

## pseudocode

```c
__int64 __fastcall InitCodedownload(__int64 a1)
{
  unsigned int v2; // edi
  HMODULE *v3; // rbx
  HMODULE LibraryUsingFullPath; // rax
  FARPROC ProcAddress; // rax
  HMODULE v6; // rcx
  FARPROC v7; // rax
  HMODULE v8; // rcx
  FARPROC v9; // rax
  bool v10; // zf
  __int64 v11; // rax

  EnterCriticalSection(&CDMCritSect);
  if ( gpCodeDownLoadInfo )
  {
    v2 = 1;
  }
  else
  {
    v3 = (HMODULE *)LocalAlloc(0x40u, 0x28u);
    if ( !v3 )
      goto LABEL_10;
    LibraryUsingFullPath = (HMODULE)LoadLibraryUsingFullPath(L"wudriver.dll");
    *v3 = LibraryUsingFullPath;
    if ( !LibraryUsingFullPath )
      goto LABEL_10;
    ProcAddress = GetProcAddress(LibraryUsingFullPath, "OpenCDMContext");
    v6 = *v3;
    v3[2] = (HMODULE)ProcAddress;
    v7 = GetProcAddress(v6, "DownloadUpdatedFiles");
    v8 = *v3;
    v3[3] = (HMODULE)v7;
    v9 = GetProcAddress(v8, "CloseCDMContext");
    v10 = v3[2] == 0;
    v3[4] = (HMODULE)v9;
    if ( v10 )
      goto LABEL_10;
    if ( v3[3] && v9 && (v11 = ((__int64 (__fastcall *)(__int64))v3[2])(a1), (v3[1] = (HMODULE)v11) != 0) )
    {
      v2 = 1;
      gpCodeDownLoadInfo = v3;
    }
    else
    {
LABEL_10:
      DestroyCodedownload(v3);
      v2 = 0;
    }
  }
  LeaveCriticalSection(&CDMCritSect);
  return v2;
}

```

## disassembly

```asm
0x18000ea18  mov     [rsp+arg_0], rbx
0x18000ea1d  push    rdi
0x18000ea1e  sub     rsp, 20h
0x18000ea22  mov     rdi, rcx
0x18000ea25  lea     rcx, CDMCritSect; lpCriticalSection
0x18000ea2c  call    cs:__imp_EnterCriticalSection
0x18000ea32  cmp     cs:gpCodeDownLoadInfo, 0
0x18000ea3a  jz      short loc_18000EA46
0x18000ea3c  mov     edi, 1
0x18000ea41  jmp     loc_18000EAF0
0x18000ea46  mov     edx, 28h ; '('; uBytes
0x18000ea4b  lea     ecx, [rdx+18h]; uFlags
0x18000ea4e  call    cs:__imp_LocalAlloc
0x18000ea54  mov     rbx, rax
0x18000ea57  test    rax, rax
0x18000ea5a  jz      loc_18000EAE6
0x18000ea60  lea     rcx, aWudriverDll; "wudriver.dll"
0x18000ea67  call    LoadLibraryUsingFullPath
0x18000ea6c  mov     [rbx], rax
0x18000ea6f  test    rax, rax
0x18000ea72  jz      short loc_18000EAE6
0x18000ea74  lea     rdx, aOpencdmcontext; "OpenCDMContext"
0x18000ea7b  mov     rcx, rax; hModule
0x18000ea7e  call    cs:__imp_GetProcAddress
0x18000ea84  mov     rcx, [rbx]; hModule
0x18000ea87  lea     rdx, aDownloadupdate_0; "DownloadUpdatedFiles"
0x18000ea8e  mov     [rbx+10h], rax
0x18000ea92  call    cs:__imp_GetProcAddress
0x18000ea98  mov     rcx, [rbx]; hModule
0x18000ea9b  lea     rdx, aClosecdmcontex; "CloseCDMContext"
0x18000eaa2  mov     [rbx+18h], rax
0x18000eaa6  call    cs:__imp_GetProcAddress
0x18000eaac  cmp     qword ptr [rbx+10h], 0
0x18000eab1  mov     [rbx+20h], rax
0x18000eab5  jz      short loc_18000EAE6
0x18000eab7  cmp     qword ptr [rbx+18h], 0
0x18000eabc  jz      short loc_18000EAE6
0x18000eabe  test    rax, rax
0x18000eac1  jz      short loc_18000EAE6
0x18000eac3  mov     rax, [rbx+10h]
0x18000eac7  mov     rcx, rdi
0x18000eaca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000eacf  mov     [rbx+8], rax
0x18000ead3  test    rax, rax
0x18000ead6  jz      short loc_18000EAE6
0x18000ead8  mov     edi, 1
0x18000eadd  mov     cs:gpCodeDownLoadInfo, rbx
0x18000eae4  jmp     short loc_18000EAF0
0x18000eae6  mov     rcx, rbx; hMem
0x18000eae9  call    DestroyCodedownload
0x18000eaee  xor     edi, edi
0x18000eaf0  lea     rcx, CDMCritSect; lpCriticalSection
0x18000eaf7  call    cs:__imp_LeaveCriticalSection
0x18000eafd  mov     rbx, [rsp+28h+arg_0]
0x18000eb02  mov     eax, edi
0x18000eb04  add     rsp, 20h
0x18000eb08  pop     rdi
0x18000eb09  retn
```
