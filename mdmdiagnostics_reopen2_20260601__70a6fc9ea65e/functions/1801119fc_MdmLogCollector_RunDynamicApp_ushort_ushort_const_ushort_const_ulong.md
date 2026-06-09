# MdmLogCollector::RunDynamicApp(ushort *,ushort const *,ushort const *,ulong)

- ea: `0x1801119fc`
- end: `0x180111bde`
- name: `?RunDynamicApp@MdmLogCollector@@AEAAJPEAGPEBG1K@Z`
- size: `482`
- prototype: `int(MdmLogCollector *__hidden this, unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, unsigned int)`
- caller_count: `4`
- callee_count: `6`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18010a79c`
- `0x18010a94c`
- `0x18010b87c`
- `0x18010c924`

## callees

- `0x18001a054`
- `0x1800ed44c`
- `0x1800fa50c`
- `0x1801055f4`
- `0x180109d50`
- `0x1801119fc`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180111a39`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180111a4d`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180111a39`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180111a4d`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180111aba`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180111aba`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180111b8c`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180111b8c`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x180111b57`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x180111b57`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180111b9c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180111bac`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180111b9c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180111bac`

## string_xrefs

- `0x180111b70`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\dll\mdmlogcollector.cpp`

## pseudocode

```c
__int64 __fastcall MdmLogCollector::RunDynamicApp(
        MdmLogCollector *this,
        unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        DWORD dwMilliseconds)
{
  HANDLE v10; // rax
  const char *v11; // r9
  void *v12; // rbx
  __int64 v13; // rdx
  unsigned int LastError; // ebx
  struct _PROCESS_INFORMATION ProcessInformation; // [rsp+50h] [rbp-61h] BYREF
  struct _SECURITY_ATTRIBUTES SecurityAttributes; // [rsp+68h] [rbp-49h] BYREF
  struct _STARTUPINFOW StartupInfo; // [rsp+80h] [rbp-31h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+108h] [rbp+57h]
  void *v19; // [rsp+110h] [rbp+5Fh] BYREF

  if ( *((_QWORD *)this + 28) != -1 )
    return 1;
  DeleteFileW(a3);
  if ( a4 )
    DeleteFileW(a4);
  MdmLogCollector::AddEntry(a3, (char *)this + 32);
  if ( a4 )
    MdmLogCollector::AddEntry(a4, (char *)this + 32);
  *(_OWORD *)&SecurityAttributes.nLength = 0;
  *(&SecurityAttributes.bInheritHandle + 1) = 0;
  SecurityAttributes.nLength = 24;
  SecurityAttributes.bInheritHandle = 1;
  v19 = 0;
  v10 = CreateFileW(a3, 0x40000000u, 3u, &SecurityAttributes, 2u, 0x80u, 0);
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
    &v19,
    v10);
  v12 = v19;
  if ( v19 == (void *)-1LL )
  {
    v13 = 1220;
  }
  else
  {
    memset_0(&StartupInfo, 0, sizeof(StartupInfo));
    StartupInfo.cb = 104;
    StartupInfo.dwFlags = 256;
    StartupInfo.hStdOutput = v12;
    StartupInfo.hStdError = v12;
    memset(&ProcessInformation, 0, sizeof(ProcessInformation));
    if ( CreateProcessW(0, a2, 0, 0, 1, 0x8000000u, 0, 0, &StartupInfo, &ProcessInformation) )
    {
      if ( ProcessInformation.hProcess )
      {
        WaitForSingleObject(ProcessInformation.hProcess, dwMilliseconds);
        CloseHandle(ProcessInformation.hProcess);
        CloseHandle(ProcessInformation.hThread);
      }
      LastError = 0;
      goto LABEL_15;
    }
    v13 = 1241;
  }
  LastError = wil::details::in1diag3::Return_GetLastError(
                retaddr,
                (void *)v13,
                (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\dll\\mdmlogcollector.cpp",
                v11);
LABEL_15:
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v19);
  return LastError;
}

```

## disassembly

```asm
0x1801119fc  mov     [rsp-8+arg_8], rbx
0x180111a01  mov     [rsp-8+arg_10], rsi
0x180111a06  push    rbp
0x180111a07  push    rdi
0x180111a08  push    r14
0x180111a0a  lea     rbp, [rsp-3Fh]
0x180111a0f  sub     rsp, 0F0h
0x180111a16  cmp     qword ptr [rcx+0E0h], 0FFFFFFFFFFFFFFFFh
0x180111a1e  mov     rbx, r9
0x180111a21  mov     rdi, r8
0x180111a24  mov     r14, rdx
0x180111a27  mov     rsi, rcx
0x180111a2a  jz      short loc_180111A36
0x180111a2c  mov     eax, 1
0x180111a31  jmp     loc_180111BC5
0x180111a36  mov     rcx, rdi; lpFileName
0x180111a39  call    cs:__imp_DeleteFileW
0x180111a40  nop     dword ptr [rax+rax+00h]
0x180111a45  test    rbx, rbx
0x180111a48  jz      short loc_180111A59
0x180111a4a  mov     rcx, rbx; lpFileName
0x180111a4d  call    cs:__imp_DeleteFileW
0x180111a54  nop     dword ptr [rax+rax+00h]
0x180111a59  lea     rdx, [rsi+20h]
0x180111a5d  mov     rcx, rdi
0x180111a60  call    ?AddEntry@MdmLogCollector@@CAJPEBGAEAV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@Z; MdmLogCollector::AddEntry(ushort const *,std::vector<std::wstring> &)
0x180111a65  test    rbx, rbx
0x180111a68  jz      short loc_180111A76
0x180111a6a  lea     rdx, [rsi+20h]
0x180111a6e  mov     rcx, rbx
0x180111a71  call    ?AddEntry@MdmLogCollector@@CAJPEBGAEAV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@Z; MdmLogCollector::AddEntry(ushort const *,std::vector<std::wstring> &)
0x180111a76  xor     eax, eax
0x180111a78  lea     r9, [rbp+4Fh+SecurityAttributes]; lpSecurityAttributes
0x180111a7c  mov     [rsp+100h+hTemplateFile], rax; hTemplateFile
0x180111a81  xorps   xmm0, xmm0
0x180111a84  movups  xmmword ptr [rbp+4Fh+SecurityAttributes.nLength], xmm0
0x180111a88  mov     qword ptr [rbp+4Fh+SecurityAttributes.bInheritHandle], rax
0x180111a8c  mov     edx, 40000000h; dwDesiredAccess
0x180111a91  lea     r8d, [rax+3]; dwShareMode
0x180111a95  mov     [rsp+100h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x180111a9d  mov     rcx, rdi; lpFileName
0x180111aa0  mov     [rbp+4Fh+SecurityAttributes.nLength], 18h
0x180111aa7  mov     [rbp+4Fh+SecurityAttributes.bInheritHandle], 1
0x180111aae  mov     [rbp+4Fh+arg_0], rax
0x180111ab2  mov     [rsp+100h+dwCreationDisposition], 2; dwCreationDisposition
0x180111aba  call    cs:__imp_CreateFileW
0x180111ac1  nop     dword ptr [rax+rax+00h]
0x180111ac6  mov     rdx, rax
0x180111ac9  lea     rcx, [rbp+4Fh+arg_0]
0x180111acd  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x180111ad2  mov     rbx, [rbp+4Fh+arg_0]
0x180111ad6  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x180111ada  jnz     short loc_180111AE6
0x180111adc  mov     edx, 4C4h
0x180111ae1  jmp     loc_180111B6C
0x180111ae6  mov     edi, 68h ; 'h'
0x180111aeb  lea     rcx, [rbp+4Fh+StartupInfo]; void *
0x180111aef  mov     r8d, edi; Size
0x180111af2  xor     edx, edx; Val
0x180111af4  call    memset_0
0x180111af9  xor     eax, eax
0x180111afb  mov     [rbp+4Fh+StartupInfo.cb], edi
0x180111afe  mov     qword ptr [rbp+4Fh+ProcessInformation.dwProcessId], rax
0x180111b02  xorps   xmm0, xmm0
0x180111b05  lea     rax, [rbp+4Fh+ProcessInformation]
0x180111b09  mov     [rbp+4Fh+StartupInfo.dwFlags], 100h
0x180111b10  mov     [rsp+100h+lpProcessInformation], rax; lpProcessInformation
0x180111b15  xor     r9d, r9d; lpThreadAttributes
0x180111b18  lea     rax, [rbp+4Fh+StartupInfo]
0x180111b1c  mov     [rbp+4Fh+StartupInfo.hStdOutput], rbx
0x180111b20  mov     [rsp+100h+lpStartupInfo], rax; lpStartupInfo
0x180111b25  xor     r8d, r8d; lpProcessAttributes
0x180111b28  mov     [rsp+100h+lpCurrentDirectory], 0; lpCurrentDirectory
0x180111b31  mov     rdx, r14; lpCommandLine
0x180111b34  mov     [rsp+100h+hTemplateFile], 0; lpEnvironment
0x180111b3d  xor     ecx, ecx; lpApplicationName
0x180111b3f  mov     [rsp+100h+dwFlagsAndAttributes], 8000000h; dwCreationFlags
0x180111b47  mov     [rsp+100h+dwCreationDisposition], 1; bInheritHandles
0x180111b4f  mov     [rbp+4Fh+StartupInfo.hStdError], rbx
0x180111b53  movups  xmmword ptr [rbp+4Fh+ProcessInformation.hProcess], xmm0
0x180111b57  call    cs:__imp_CreateProcessW
0x180111b5e  nop     dword ptr [rax+rax+00h]
0x180111b63  test    eax, eax
0x180111b65  jnz     short loc_180111B80
0x180111b67  mov     edx, 4D9h; void *
0x180111b6c  mov     rcx, [rbp+57h]; this
0x180111b70  lea     r8, aOnecoreuapAdmi_33; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x180111b77  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180111b7c  mov     ebx, eax
0x180111b7e  jmp     short loc_180111BBA
0x180111b80  mov     rcx, [rbp+4Fh+ProcessInformation.hProcess]; hHandle
0x180111b84  test    rcx, rcx
0x180111b87  jz      short loc_180111BB8
0x180111b89  mov     edx, [rbp+4Fh+dwMilliseconds]; dwMilliseconds
0x180111b8c  call    cs:__imp_WaitForSingleObject
0x180111b93  nop     dword ptr [rax+rax+00h]
0x180111b98  mov     rcx, [rbp+4Fh+ProcessInformation.hProcess]; hObject
0x180111b9c  call    cs:__imp_CloseHandle
0x180111ba3  nop     dword ptr [rax+rax+00h]
0x180111ba8  mov     rcx, [rbp+4Fh+ProcessInformation.hThread]; hObject
0x180111bac  call    cs:__imp_CloseHandle
0x180111bb3  nop     dword ptr [rax+rax+00h]
0x180111bb8  xor     ebx, ebx
0x180111bba  lea     rcx, [rbp+4Fh+arg_0]
0x180111bbe  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180111bc3  mov     eax, ebx
0x180111bc5  lea     r11, [rsp+100h+var_10]
0x180111bcd  mov     rbx, [r11+28h]
0x180111bd1  mov     rsi, [r11+30h]
0x180111bd5  mov     rsp, r11
0x180111bd8  pop     r14
0x180111bda  pop     rdi
0x180111bdb  pop     rbp
0x180111bdc  retn
```
