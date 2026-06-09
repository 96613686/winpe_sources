# FontDownloadQueue::DownloadThreadProc(void *)

- ea: `0x1802359a0`
- end: `0x180235a10`
- name: `?DownloadThreadProc@FontDownloadQueue@@CAKPEAX@Z`
- size: `112`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x18011ed18`
- `0x1802066a4`
- `0x1802359a0`
- `0x180235a18`
- `0x180330010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibraryAndExitThread` at `0x180235a09`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibraryAndExitThread` at `0x180235a09`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x1802359c3`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x1802359c3`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall __noreturn FontDownloadQueue::DownloadThreadProc(FontDownloadQueue *Parameter)
{
  const char *v2; // rdx
  HMODULE phModule; // [rsp+38h] [rbp+10h] BYREF
  FontDownloadQueue *v4; // [rsp+40h] [rbp+18h] BYREF

  phModule = 0;
  if ( !GetModuleHandleExW(4u, (LPCWSTR)FontDownloadQueue::DownloadThreadProc, &phModule) )
  {
    FailAssert(0x7Eu, v2);
    __debugbreak();
  }
  v4 = Parameter;
  if ( Parameter )
    (*(void (__fastcall **)(FontDownloadQueue *))(*(_QWORD *)Parameter + 8LL))(Parameter);
  FontDownloadQueue::ExecuteDownloads(Parameter);
  ComPtr<ClientSideRemoteFileStream>::~ComPtr<ClientSideRemoteFileStream>(&v4);
  FreeLibraryAndExitThread(phModule, 0);
}

```

## disassembly

```asm
0x1802359a0  push    rbx
0x1802359a2  sub     rsp, 20h
0x1802359a6  mov     rbx, rcx
0x1802359a9  mov     [rsp+28h+phModule], 0
0x1802359b2  lea     r8, [rsp+28h+phModule]; phModule
0x1802359b7  lea     rdx, ?DownloadThreadProc@FontDownloadQueue@@CAKPEAX@Z; lpModuleName
0x1802359be  mov     ecx, 4; dwFlags
0x1802359c3  call    cs:__imp_GetModuleHandleExW
0x1802359c9  test    eax, eax
0x1802359cb  jnz     short loc_1802359D6
0x1802359cd  lea     ecx, [rax+7Eh]; unsigned int
0x1802359d0  call    ?FailAssert@@YAXIPEBD@Z; FailAssert(uint,char const *)
0x1802359d5  int     3; Trap to Debugger
0x1802359d6  mov     [rsp+28h+arg_10], rbx
0x1802359db  test    rbx, rbx
0x1802359de  jz      short loc_1802359F0
0x1802359e0  mov     rax, [rbx]
0x1802359e3  mov     rcx, rbx
0x1802359e6  mov     rax, [rax+8]
0x1802359ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802359ef  nop
0x1802359f0  mov     rcx, rbx; this
0x1802359f3  call    ?ExecuteDownloads@FontDownloadQueue@@AEAAXXZ; FontDownloadQueue::ExecuteDownloads(void)
0x1802359f8  lea     rcx, [rsp+28h+arg_10]
0x1802359fd  call    ??1?$ComPtr@VClientSideRemoteFileStream@@@@QEAA@XZ; ComPtr<ClientSideRemoteFileStream>::~ComPtr<ClientSideRemoteFileStream>(void)
0x180235a02  xor     edx, edx; dwExitCode
0x180235a04  mov     rcx, [rsp+28h+phModule]; hLibModule
0x180235a09  call    cs:__imp_FreeLibraryAndExitThread
```
