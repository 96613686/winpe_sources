# LogProcessesWithOpenFileHandles(ushort const *,LockedHiveType)

- ea: `0x180038c38`
- end: `0x180038e1b`
- name: `?LogProcessesWithOpenFileHandles@@YAJPEBGW4LockedHiveType@@@Z`
- size: `483`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `11`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180016150`
- `0x180038798`

## callees

- `0x1800084bc`
- `0x18000b060`
- `0x180017fdc`
- `0x18002df48`
- `0x180030ad0`
- `0x1800364c8`
- `0x18003651c`
- `0x180038c38`
- `0x180038e24`
- `0x180040bcc`
- `0x18004f634`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180038cff`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180038cff`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180038ce8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180038ce8`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180038cb3`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180038cb3`
- `ntdll!NtQueryInformationFile` at `0x180038d36`
- `ntdll!NtQueryInformationFile` at `0x180038d36`

## string_xrefs

- `0x180038c72`: `onecore\ds\security\gina\profile\profsvc\util.cpp`
- `0x180038ccc`: `onecore\ds\security\gina\profile\profsvc\util.cpp`
- `0x180038d4a`: `onecore\ds\security\gina\profile\profsvc\util.cpp`
- `0x180038d9c`: `onecore\ds\security\gina\profile\profsvc\util.cpp`
- `0x180038dd8`: `onecore\ds\security\gina\profile\profsvc\util.cpp`

## pseudocode

```c
__int64 __fastcall LogProcessesWithOpenFileHandles(const WCHAR *a1, int a2)
{
  int v4; // eax
  unsigned int LastError; // ebx
  HANDLE FileW; // rax
  const char *v7; // r9
  void *v8; // rbx
  HANDLE ProcessHeap; // rax
  _DWORD *v10; // rax
  _DWORD *v11; // rdi
  NTSTATUS v12; // eax
  __int64 i; // rbx
  int v14; // eax
  DWORD dwCreationDisposition; // [rsp+20h] [rbp-40h]
  DWORD dwCreationDispositiona; // [rsp+20h] [rbp-40h]
  DWORD dwCreationDispositionb; // [rsp+20h] [rbp-40h]
  HANDLE v19; // [rsp+40h] [rbp-20h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+48h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+18h]
  int v22; // [rsp+90h] [rbp+30h] BYREF
  int v23; // [rsp+98h] [rbp+38h] BYREF
  __int16 v24; // [rsp+9Ch] [rbp+3Ch]

  v23 = 20;
  v24 = 0;
  v4 = PrivilegeAdjuster::AdjustPrivilegeIfNecessary((PrivilegeAdjuster *)&v23);
  LastError = v4;
  if ( v4 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x566,
      (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\util.cpp",
      (const char *)(unsigned int)v4,
      dwCreationDisposition);
LABEL_17:
    PrivilegeAdjuster::~PrivilegeAdjuster((PrivilegeAdjuster *)&v23);
    return LastError;
  }
  FileW = CreateFileW(a1, 0x100080u, 7u, 0, 3u, 0x2000000u, 0);
  v8 = FileW;
  if ( FileW == (HANDLE)-1LL )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x56F,
                  (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\util.cpp",
                  v7);
    goto LABEL_17;
  }
  v19 = FileW;
  ProcessHeap = GetProcessHeap();
  v10 = HeapAlloc(ProcessHeap, 0, 0x400u);
  v11 = v10;
  if ( !v10 )
  {
    LastError = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x579,
      (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\util.cpp",
      (const char *)0x8007000ELL,
      dwCreationDispositiona);
    goto LABEL_16;
  }
  IoStatusBlock = 0;
  v12 = NtQueryInformationFile(v8, &IoStatusBlock, v10, 0x400u, FileProcessIdsUsingFileInformation);
  if ( v12 < 0 )
  {
    LastError = wil::details::in1diag3::Return_NtStatus(
                  retaddr,
                  (void *)0x57C,
                  (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\util.cpp",
                  (const char *)(unsigned int)v12,
                  dwCreationDispositionb);
    Windows::Internal::ProcessHeapMemPolicy<unsigned short>::Free(v11);
LABEL_16:
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v19);
    goto LABEL_17;
  }
  if ( *v11 )
  {
    v22 = a2;
    ProfileServiceTelemetry::HiveFileLocked<unsigned long,unsigned long &>(&v22, v11);
  }
  for ( i = 0; (unsigned int)i < *v11; i = (unsigned int)(i + 1) )
  {
    v14 = LogProcessInfo(*(_QWORD *)&v11[2 * i + 2], a1);
    if ( v14 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x585,
        (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\util.cpp",
        (const char *)(unsigned int)v14,
        dwCreationDispositionb);
  }
  Windows::Internal::ProcessHeapMemPolicy<unsigned short>::Free(v11);
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v19);
  PrivilegeAdjuster::~PrivilegeAdjuster((PrivilegeAdjuster *)&v23);
  return 0;
}

```

## disassembly

```asm
0x180038c38  mov     [rsp-18h+arg_0], rbx
0x180038c3d  mov     [rsp-18h+arg_8], rsi
0x180038c42  push    rbp
0x180038c43  push    rdi
0x180038c44  push    r14
0x180038c46  mov     rbp, rsp
0x180038c49  sub     rsp, 60h
0x180038c4d  mov     r14, rcx
0x180038c50  mov     [rbp+arg_18], 14h
0x180038c57  lea     rcx, [rbp+arg_18]; this
0x180038c5b  mov     [rbp+arg_1C], 0
0x180038c61  mov     esi, edx
0x180038c63  call    ?AdjustPrivilegeIfNecessary@PrivilegeAdjuster@@QEAAJXZ; PrivilegeAdjuster::AdjustPrivilegeIfNecessary(void)
0x180038c68  mov     ebx, eax
0x180038c6a  test    eax, eax
0x180038c6c  jns     short loc_180038C8B
0x180038c6e  mov     rcx, [rbp+18h]; this
0x180038c72  lea     r8, aOnecoreDsSecur_14; "onecore\\ds\\security\\gina\\profile\\p"...
0x180038c79  mov     r9d, eax; char *
0x180038c7c  mov     edx, 566h; void *
0x180038c81  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180038c86  jmp     loc_180038DFA
0x180038c8b  xor     r9d, r9d; lpSecurityAttributes
0x180038c8e  mov     [rsp+60h+hTemplateFile], 0; hTemplateFile
0x180038c97  mov     [rsp+60h+dwFlagsAndAttributes], 2000000h; dwFlagsAndAttributes
0x180038c9f  mov     edx, 100080h; dwDesiredAccess
0x180038ca4  mov     rcx, r14; lpFileName
0x180038ca7  mov     [rsp+60h+dwCreationDisposition], 3; int
0x180038caf  lea     r8d, [r9+7]; dwShareMode
0x180038cb3  call    cs:__imp_CreateFileW
0x180038cba  nop     dword ptr [rax+rax+00h]
0x180038cbf  mov     rbx, rax
0x180038cc2  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180038cc6  jnz     short loc_180038CE4
0x180038cc8  mov     rcx, [rbp+18h]; this
0x180038ccc  lea     r8, aOnecoreDsSecur_14; "onecore\\ds\\security\\gina\\profile\\p"...
0x180038cd3  mov     edx, 56Fh; void *
0x180038cd8  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180038cdd  mov     ebx, eax
0x180038cdf  jmp     loc_180038DFA
0x180038ce4  mov     [rbp+var_20], rbx
0x180038ce8  call    cs:__imp_GetProcessHeap
0x180038cef  nop     dword ptr [rax+rax+00h]
0x180038cf4  xor     edx, edx; dwFlags
0x180038cf6  mov     r8d, 400h; dwBytes
0x180038cfc  mov     rcx, rax; hHeap
0x180038cff  call    cs:__imp_HeapAlloc
0x180038d06  nop     dword ptr [rax+rax+00h]
0x180038d0b  mov     rdi, rax
0x180038d0e  test    rax, rax
0x180038d11  jz      loc_180038DD4
0x180038d17  xorps   xmm0, xmm0
0x180038d1a  mov     [rsp+60h+dwCreationDisposition], 2Fh ; '/'; int
0x180038d22  mov     r9d, 400h; Length
0x180038d28  lea     rdx, [rbp+IoStatusBlock]; IoStatusBlock
0x180038d2c  mov     r8, rax; FileInformation
0x180038d2f  mov     rcx, rbx; FileHandle
0x180038d32  movups  xmmword ptr [rbp+IoStatusBlock], xmm0
0x180038d36  call    cs:__imp_NtQueryInformationFile
0x180038d3d  nop     dword ptr [rax+rax+00h]
0x180038d42  test    eax, eax
0x180038d44  jns     short loc_180038D6D
0x180038d46  mov     rcx, [rbp+18h]; this
0x180038d4a  lea     r8, aOnecoreDsSecur_14; "onecore\\ds\\security\\gina\\profile\\p"...
0x180038d51  mov     r9d, eax; char *
0x180038d54  mov     edx, 57Ch; void *
0x180038d59  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x180038d5e  mov     rcx, rdi
0x180038d61  mov     ebx, eax
0x180038d63  call    ?Free@?$ProcessHeapMemPolicy@G@Internal@Windows@@SAXPEAG@Z; Windows::Internal::ProcessHeapMemPolicy<ushort>::Free(ushort *)
0x180038d68  jmp     loc_180038DF1
0x180038d6d  cmp     dword ptr [rdi], 0
0x180038d70  jbe     short loc_180038D81
0x180038d72  mov     rdx, rdi
0x180038d75  mov     [rbp+arg_10], esi
0x180038d78  lea     rcx, [rbp+arg_10]
0x180038d7c  call    ??$HiveFileLocked@KAEAK@ProfileServiceTelemetry@@SAX$$QEAKAEAK@Z; ProfileServiceTelemetry::HiveFileLocked<ulong,ulong &>(ulong &&,ulong &)
0x180038d81  xor     ebx, ebx
0x180038d83  cmp     [rdi], ebx
0x180038d85  jbe     short loc_180038DB6
0x180038d87  mov     rcx, [rdi+rbx*8+8]; dwProcessId
0x180038d8c  mov     rdx, r14; unsigned __int16 *
0x180038d8f  call    ?LogProcessInfo@@YAJ_KPEBG@Z; LogProcessInfo(unsigned __int64,ushort const *)
0x180038d94  test    eax, eax
0x180038d96  jns     short loc_180038DB0
0x180038d98  mov     rcx, [rbp+18h]; this
0x180038d9c  lea     r8, aOnecoreDsSecur_14; "onecore\\ds\\security\\gina\\profile\\p"...
0x180038da3  mov     r9d, eax; char *
0x180038da6  mov     edx, 585h; void *
0x180038dab  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180038db0  inc     ebx
0x180038db2  cmp     ebx, [rdi]
0x180038db4  jb      short loc_180038D87
0x180038db6  mov     rcx, rdi
0x180038db9  call    ?Free@?$ProcessHeapMemPolicy@G@Internal@Windows@@SAXPEAG@Z; Windows::Internal::ProcessHeapMemPolicy<ushort>::Free(ushort *)
0x180038dbe  lea     rcx, [rbp+var_20]
0x180038dc2  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180038dc7  lea     rcx, [rbp+arg_18]; this
0x180038dcb  call    ??1PrivilegeAdjuster@@QEAA@XZ; PrivilegeAdjuster::~PrivilegeAdjuster(void)
0x180038dd0  xor     eax, eax
0x180038dd2  jmp     short loc_180038E05
0x180038dd4  mov     rcx, [rbp+18h]; this
0x180038dd8  lea     r8, aOnecoreDsSecur_14; "onecore\\ds\\security\\gina\\profile\\p"...
0x180038ddf  mov     ebx, 8007000Eh
0x180038de4  mov     edx, 579h; void *
0x180038de9  mov     r9d, ebx; char *
0x180038dec  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180038df1  lea     rcx, [rbp+var_20]
0x180038df5  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180038dfa  lea     rcx, [rbp+arg_18]; this
0x180038dfe  call    ??1PrivilegeAdjuster@@QEAA@XZ; PrivilegeAdjuster::~PrivilegeAdjuster(void)
0x180038e03  mov     eax, ebx
0x180038e05  lea     r11, [rsp+60h+var_s0]
0x180038e0a  mov     rbx, [r11+20h]
0x180038e0e  mov     rsi, [r11+28h]
0x180038e12  mov     rsp, r11
0x180038e15  pop     r14
0x180038e17  pop     rdi
0x180038e18  pop     rbp
0x180038e19  retn
```
