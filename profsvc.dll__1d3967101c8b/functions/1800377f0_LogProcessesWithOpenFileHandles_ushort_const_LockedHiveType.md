# LogProcessesWithOpenFileHandles(ushort const *,LockedHiveType)

- ea: `0x1800377f0`
- end: `0x1800379ba`
- name: `?LogProcessesWithOpenFileHandles@@YAJPEBGW4LockedHiveType@@@Z`
- size: `458`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `11`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180011200`
- `0x18003735c`

## callees

- `0x1800053a0`
- `0x18000a9b8`
- `0x180015458`
- `0x18002aef0`
- `0x18002d2d8`
- `0x18002db38`
- `0x180035f88`
- `0x1800377f0`
- `0x1800379c0`
- `0x18003f42c`
- `0x18004c620`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800378ab`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800378ab`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003789a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003789a`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18003786b`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18003786b`
- `ntdll!NtQueryInformationFile` at `0x1800378dc`
- `ntdll!NtQueryInformationFile` at `0x1800378dc`

## string_xrefs

- `0x18003782a`: `onecore\ds\security\gina\profile\profsvc\util.cpp`
- `0x18003787e`: `onecore\ds\security\gina\profile\profsvc\util.cpp`
- `0x1800378ea`: `onecore\ds\security\gina\profile\profsvc\util.cpp`
- `0x18003793c`: `onecore\ds\security\gina\profile\profsvc\util.cpp`
- `0x180037978`: `onecore\ds\security\gina\profile\profsvc\util.cpp`

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
  int *v10; // rax
  int *v11; // rdi
  NTSTATUS v12; // eax
  __int64 i; // rbx
  int v14; // eax
  DWORD dwCreationDisposition; // [rsp+20h] [rbp-40h]
  DWORD dwCreationDispositiona; // [rsp+20h] [rbp-40h]
  DWORD dwCreationDispositionb; // [rsp+20h] [rbp-40h]
  void *v19; // [rsp+40h] [rbp-20h] BYREF
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
  v10 = (int *)HeapAlloc(ProcessHeap, 0, 0x400u);
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
        (int)"onecore\\ds\\security\\gina\\profile\\profsvc\\util.cpp",
        (const char *)(unsigned int)v14);
  }
  Windows::Internal::ProcessHeapMemPolicy<unsigned short>::Free(v11);
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v19);
  PrivilegeAdjuster::~PrivilegeAdjuster((PrivilegeAdjuster *)&v23);
  return 0;
}

```

## disassembly

```asm
0x1800377f0  mov     [rsp-18h+arg_0], rbx
0x1800377f5  mov     [rsp-18h+arg_8], rsi
0x1800377fa  push    rbp
0x1800377fb  push    rdi
0x1800377fc  push    r14
0x1800377fe  mov     rbp, rsp
0x180037801  sub     rsp, 60h
0x180037805  mov     r14, rcx
0x180037808  mov     [rbp+arg_18], 14h
0x18003780f  lea     rcx, [rbp+arg_18]; this
0x180037813  mov     [rbp+arg_1C], 0
0x180037819  mov     esi, edx
0x18003781b  call    ?AdjustPrivilegeIfNecessary@PrivilegeAdjuster@@QEAAJXZ; PrivilegeAdjuster::AdjustPrivilegeIfNecessary(void)
0x180037820  mov     ebx, eax
0x180037822  test    eax, eax
0x180037824  jns     short loc_180037843
0x180037826  mov     rcx, [rbp+18h]; this
0x18003782a  lea     r8, aOnecoreDsSecur_14; "onecore\\ds\\security\\gina\\profile\\p"...
0x180037831  mov     r9d, eax; char *
0x180037834  mov     edx, 566h; void *
0x180037839  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003783e  jmp     loc_18003799A
0x180037843  xor     r9d, r9d; lpSecurityAttributes
0x180037846  mov     [rsp+60h+hTemplateFile], 0; hTemplateFile
0x18003784f  mov     [rsp+60h+dwFlagsAndAttributes], 2000000h; dwFlagsAndAttributes
0x180037857  mov     edx, 100080h; dwDesiredAccess
0x18003785c  mov     rcx, r14; lpFileName
0x18003785f  mov     [rsp+60h+dwCreationDisposition], 3; int
0x180037867  lea     r8d, [r9+7]; dwShareMode
0x18003786b  call    cs:__imp_CreateFileW
0x180037871  mov     rbx, rax
0x180037874  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180037878  jnz     short loc_180037896
0x18003787a  mov     rcx, [rbp+18h]; this
0x18003787e  lea     r8, aOnecoreDsSecur_14; "onecore\\ds\\security\\gina\\profile\\p"...
0x180037885  mov     edx, 56Fh; void *
0x18003788a  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18003788f  mov     ebx, eax
0x180037891  jmp     loc_18003799A
0x180037896  mov     [rbp+var_20], rbx
0x18003789a  call    cs:__imp_GetProcessHeap
0x1800378a0  xor     edx, edx; dwFlags
0x1800378a2  mov     r8d, 400h; dwBytes
0x1800378a8  mov     rcx, rax; hHeap
0x1800378ab  call    cs:__imp_HeapAlloc
0x1800378b1  mov     rdi, rax
0x1800378b4  test    rax, rax
0x1800378b7  jz      loc_180037974
0x1800378bd  xorps   xmm0, xmm0
0x1800378c0  mov     [rsp+60h+dwCreationDisposition], 2Fh ; '/'; int
0x1800378c8  mov     r9d, 400h; Length
0x1800378ce  lea     rdx, [rbp+IoStatusBlock]; IoStatusBlock
0x1800378d2  mov     r8, rax; FileInformation
0x1800378d5  mov     rcx, rbx; FileHandle
0x1800378d8  movups  xmmword ptr [rbp+IoStatusBlock], xmm0
0x1800378dc  call    cs:__imp_NtQueryInformationFile
0x1800378e2  test    eax, eax
0x1800378e4  jns     short loc_18003790D
0x1800378e6  mov     rcx, [rbp+18h]; this
0x1800378ea  lea     r8, aOnecoreDsSecur_14; "onecore\\ds\\security\\gina\\profile\\p"...
0x1800378f1  mov     r9d, eax; char *
0x1800378f4  mov     edx, 57Ch; void *
0x1800378f9  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x1800378fe  mov     rcx, rdi
0x180037901  mov     ebx, eax
0x180037903  call    ?Free@?$ProcessHeapMemPolicy@G@Internal@Windows@@SAXPEAG@Z; Windows::Internal::ProcessHeapMemPolicy<ushort>::Free(ushort *)
0x180037908  jmp     loc_180037991
0x18003790d  cmp     dword ptr [rdi], 0
0x180037910  jbe     short loc_180037921
0x180037912  mov     rdx, rdi
0x180037915  mov     [rbp+arg_10], esi
0x180037918  lea     rcx, [rbp+arg_10]
0x18003791c  call    ??$HiveFileLocked@KAEAK@ProfileServiceTelemetry@@SAX$$QEAKAEAK@Z; ProfileServiceTelemetry::HiveFileLocked<ulong,ulong &>(ulong &&,ulong &)
0x180037921  xor     ebx, ebx
0x180037923  cmp     [rdi], ebx
0x180037925  jbe     short loc_180037956
0x180037927  mov     rcx, [rdi+rbx*8+8]; dwProcessId
0x18003792c  mov     rdx, r14; unsigned __int16 *
0x18003792f  call    ?LogProcessInfo@@YAJ_KPEBG@Z; LogProcessInfo(unsigned __int64,ushort const *)
0x180037934  test    eax, eax
0x180037936  jns     short loc_180037950
0x180037938  mov     rcx, [rbp+18h]; this
0x18003793c  lea     r8, aOnecoreDsSecur_14; "onecore\\ds\\security\\gina\\profile\\p"...
0x180037943  mov     r9d, eax; char *
0x180037946  mov     edx, 585h; void *
0x18003794b  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180037950  inc     ebx
0x180037952  cmp     ebx, [rdi]
0x180037954  jb      short loc_180037927
0x180037956  mov     rcx, rdi
0x180037959  call    ?Free@?$ProcessHeapMemPolicy@G@Internal@Windows@@SAXPEAG@Z; Windows::Internal::ProcessHeapMemPolicy<ushort>::Free(ushort *)
0x18003795e  lea     rcx, [rbp+var_20]
0x180037962  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180037967  lea     rcx, [rbp+arg_18]; this
0x18003796b  call    ??1PrivilegeAdjuster@@QEAA@XZ; PrivilegeAdjuster::~PrivilegeAdjuster(void)
0x180037970  xor     eax, eax
0x180037972  jmp     short loc_1800379A5
0x180037974  mov     rcx, [rbp+18h]; this
0x180037978  lea     r8, aOnecoreDsSecur_14; "onecore\\ds\\security\\gina\\profile\\p"...
0x18003797f  mov     ebx, 8007000Eh
0x180037984  mov     edx, 579h; void *
0x180037989  mov     r9d, ebx; char *
0x18003798c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180037991  lea     rcx, [rbp+var_20]
0x180037995  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18003799a  lea     rcx, [rbp+arg_18]; this
0x18003799e  call    ??1PrivilegeAdjuster@@QEAA@XZ; PrivilegeAdjuster::~PrivilegeAdjuster(void)
0x1800379a3  mov     eax, ebx
0x1800379a5  lea     r11, [rsp+60h+var_s0]
0x1800379aa  mov     rbx, [r11+20h]
0x1800379ae  mov     rsi, [r11+28h]
0x1800379b2  mov     rsp, r11
0x1800379b5  pop     r14
0x1800379b7  pop     rdi
0x1800379b8  pop     rbp
0x1800379b9  retn
```
