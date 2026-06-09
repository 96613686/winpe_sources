# CFileAccessor::OpenOplockedHandleInternal(wchar_t const *,ulong,ulong)

- ea: `0x1800048f0`
- end: `0x180004e59`
- name: `?OpenOplockedHandleInternal@CFileAccessor@@AEAAJPEB_WKK@Z`
- size: `1385`
- prototype: `__int64 __fastcall(char *Context, wchar_t *, ACCESS_MASK DesiredAccess, char)`
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops, reparse_path, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180004890`

## callees

- `0x180002ee0`
- `0x1800048f0`
- `0x180004e60`
- `0x180004ec4`
- `0x180004f60`
- `0x180005720`
- `0x180005d40`
- `0x180005eb0`
- `0x1800090b0`
- `0x18000a1d0`
- `0x18000e9cc`
- `0x18000fcd0`
- `0x180022178`
- `0x180027010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180004b09`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180004b8e`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180004bf9`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180004b09`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180004b8e`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180004bf9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004a93`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004abf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004b23`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004c10`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004d1f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004a93`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004abf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004b23`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004c10`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004d1f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004a61`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004aa6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004b36`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004c23`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004a61`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004aa6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004b36`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004c23`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004a2d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004a9e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004b2e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004c1b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004a2d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004a9e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004b2e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004c1b`
- `api-ms-win-core-kernel32-legacy-l1-1-0!RegisterWaitForSingleObject` at `0x180004d85`
- `api-ms-win-core-kernel32-legacy-l1-1-0!RegisterWaitForSingleObject` at `0x180004d85`
- `ntdll!RtlNtStatusToDosError` at `0x180004a3c`
- `ntdll!RtlNtStatusToDosError` at `0x180004a3c`
- `ntdll!RtlInitUnicodeString` at `0x1800049a3`
- `ntdll!RtlInitUnicodeString` at `0x1800049a3`
- `ntdll!NtCreateFile` at `0x180004a19`
- `ntdll!NtCreateFile` at `0x180004a19`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180004d19`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180004d19`

## string_xrefs

- `0x180004b5d`: `[SrchPHFile] Could not create event for oplock %ls, 0x%08x`
- `0x180004bce`: `[SrchPHFile] Could not create event for oplock %ls, 0x%08x`
- `0x180004c47`: `[SrchPHFile] Could not create event for oplock %ls, 0x%08x`
- `0x180004adc`: `[SrchPHFile] Could not open file for oplock %ls - 0x%08x`
- `0x180004d48`: `[SrchPHFile] Created oplock for %ls`
- `0x180004ddc`: `[SrchPHFile] Failed to create oplock for %ls, last err %d`

## pseudocode

```c
__int64 __fastcall CFileAccessor::OpenOplockedHandleInternal(
        char *Context,
        wchar_t *a2,
        ACCESS_MASK DesiredAccess,
        char a4)
{
  int v7; // edi
  _BOOL8 is_extended_length_path; // rbx
  NTSTATUS v9; // eax
  NTSTATUS v10; // ebx
  DWORD v11; // ecx
  ULONG v12; // eax
  char *v13; // rdi
  char *v14; // rsi
  DWORD LastError; // ebx
  signed int Error; // ebx
  DWORD v17; // eax
  HANDLE EventW; // rsi
  char *v19; // r13
  DWORD v20; // edi
  HANDLE v21; // rbx
  char *v22; // rcx
  HANDLE v23; // rdi
  char *v24; // rsi
  DWORD v25; // ebx
  signed int v26; // eax
  __int64 result; // rax
  PLARGE_INTEGER AllocationSize; // [rsp+20h] [rbp-E0h]
  PLARGE_INTEGER AllocationSizea; // [rsp+20h] [rbp-E0h]
  void *FileHandle; // [rsp+60h] [rbp-A0h] BYREF
  _UNICODE_STRING DestinationString; // [rsp+68h] [rbp-98h] BYREF
  _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+78h] [rbp-88h] BYREF
  _IO_STATUS_BLOCK IoStatusBlock; // [rsp+A8h] [rbp-58h] BYREF
  void **v34; // [rsp+C0h] [rbp-40h] BYREF
  PCWSTR SourceString; // [rsp+C8h] [rbp-38h]
  __int64 v36; // [rsp+D0h] [rbp-30h]
  wchar_t v37[68]; // [rsp+D8h] [rbp-28h] BYREF

  v7 = (a4 & 1) << 16;
  is_extended_length_path = wil::is_extended_length_path((wil *)a2, a2);
  SourceString = v37;
  v36 = 65;
  v37[0] = 0;
  v34 = &TLMString<64,64,32767>::`vftable';
  CLMString::Assign((CLMString *)&v34, L"\\??\\", 0, 0xFFFFFFFF);
  ((void (__fastcall *)(void ***, const wchar_t *, _QWORD, __int64))v34[4])(
    &v34,
    &a2[4 * is_extended_length_path],
    HIDWORD(v36),
    0xFFFFFFFFLL);
  DestinationString = 0;
  RtlInitUnicodeString(&DestinationString, SourceString);
  *(_QWORD *)&ObjectAttributes.Length = 48;
  *(_QWORD *)&ObjectAttributes.Attributes = 64;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.ObjectName = &DestinationString;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  IoStatusBlock = 0;
  FileHandle = 0;
  v9 = NtCreateFile(
         &FileHandle,
         DesiredAccess,
         &ObjectAttributes,
         &IoStatusBlock,
         0,
         0x80u,
         7u,
         1u,
         v7 | 0x204000,
         0,
         0);
  v10 = v9;
  if ( v9 == 264 )
  {
    CloseHandle(FileHandle);
    v11 = 32;
  }
  else
  {
    v12 = RtlNtStatusToDosError(v9);
    v11 = v12;
    if ( !v12 )
      goto LABEL_8;
    if ( v10 == -1073739511 )
      v12 = 32;
    v11 = v12;
  }
  FileHandle = (void *)-1LL;
LABEL_8:
  SetLastError(v11);
  v13 = (char *)FileHandle;
  v34 = &TLMString<64,64,32767>::`vftable';
  CLMString::DeleteBuf((CLMString *)&v34, v37);
  v14 = (char *)*((_QWORD *)Context + 13);
  if ( (unsigned __int64)(v14 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    LastError = GetLastError();
    CloseHandle(v14);
    SetLastError(LastError);
  }
  *((_QWORD *)Context + 13) = v13;
  if ( (unsigned __int64)(v13 - 1) > 0xFFFFFFFFFFFFFFFDuLL )
  {
    v17 = GetLastError();
    Error = HResultFromFileStatus(v17, Context + 696);
    LODWORD(AllocationSize) = Error;
    SearchIndexerTrace::Warning(
      (wchar_t *)L"\"onecoreuap\\\\base\\\\appmodel\\\\search\\\\mssph\\\\file\\\\fileacc.cxx\"",
      (const wchar_t *)0x4F0,
      (unsigned int)L"[SrchPHFile] Could not open file for oplock %ls - 0x%08x",
      a2,
      AllocationSize);
    if ( Error < 0 )
      goto LABEL_38;
  }
  else
  {
    Error = 0;
  }
  EventW = CreateEventW(0, 1, 0, 0);
  v19 = (char *)*((_QWORD *)Context + 25);
  if ( (unsigned __int64)(v19 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    v20 = GetLastError();
    CloseHandle(v19);
    SetLastError(v20);
  }
  *((_QWORD *)Context + 25) = EventW;
  if ( (((unsigned __int64)EventW + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
  {
    Error = ResultFromKnownLastError();
    LODWORD(AllocationSize) = Error;
    SearchIndexerTrace::Warning(
      (wchar_t *)L"\"onecoreuap\\\\base\\\\appmodel\\\\search\\\\mssph\\\\file\\\\fileacc.cxx\"",
      (const wchar_t *)0x4FA,
      (unsigned int)L"[SrchPHFile] Could not create event for oplock %ls, 0x%08x",
      a2,
      AllocationSize);
  }
  if ( Error < 0 )
    goto LABEL_38;
  v21 = CreateEventW(0, 1, 0, 0);
  v22 = (char *)*((_QWORD *)Context + 26);
  if ( (unsigned __int64)(v22 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    wil::details::close_invoke_helper<1,int (*)(void *),&int CloseHandle(void *),void *>::close_reset(v22);
  *((_QWORD *)Context + 26) = v21;
  if ( (((unsigned __int64)v21 + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
  {
    Error = ResultFromKnownLastError();
    LODWORD(AllocationSize) = Error;
    SearchIndexerTrace::Warning(
      (wchar_t *)L"\"onecoreuap\\\\base\\\\appmodel\\\\search\\\\mssph\\\\file\\\\fileacc.cxx\"",
      (const wchar_t *)0x505,
      (unsigned int)L"[SrchPHFile] Could not create event for oplock %ls, 0x%08x",
      a2,
      AllocationSize);
    if ( Error < 0 )
      goto LABEL_38;
  }
  v23 = CreateEventW(0, 1, 0, 0);
  v24 = (char *)*((_QWORD *)Context + 12);
  if ( (unsigned __int64)(v24 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    v25 = GetLastError();
    CloseHandle(v24);
    SetLastError(v25);
  }
  *((_QWORD *)Context + 12) = v23;
  if ( (((unsigned __int64)v23 + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
  {
    Error = ResultFromKnownLastError();
    LODWORD(AllocationSize) = Error;
    SearchIndexerTrace::Warning(
      (wchar_t *)L"\"onecoreuap\\\\base\\\\appmodel\\\\search\\\\mssph\\\\file\\\\fileacc.cxx\"",
      (const wchar_t *)0x50F,
      (unsigned int)L"[SrchPHFile] Could not create event for oplock %ls, 0x%08x",
      a2,
      AllocationSize);
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
      Context + 104,
      -1);
    if ( Error < 0 )
      goto LABEL_38;
  }
  *((_QWORD *)Context + 14) = 0;
  *((_QWORD *)Context + 15) = 0;
  *((_QWORD *)Context + 16) = 0;
  *((_QWORD *)Context + 17) = *((_QWORD *)Context + 12);
  LODWORD(FileHandle) = 0;
  *(_OWORD *)(Context + 164) = 0;
  *(_QWORD *)(Context + 180) = 0;
  *((_WORD *)Context + 82) = 1;
  *((_WORD *)Context + 83) = 24;
  *((_WORD *)Context + 76) = 1;
  *((_WORD *)Context + 77) = 12;
  *((_DWORD *)Context + 39) = 3;
  *((_DWORD *)Context + 40) = 1;
  DeviceIoControl(
    *((HANDLE *)Context + 13),
    0x90240u,
    Context + 152,
    0xCu,
    Context + 164,
    0x18u,
    (LPDWORD)&FileHandle,
    (LPOVERLAPPED)(Context + 112));
  v26 = GetLastError();
  Error = v26;
  if ( v26 > 0 )
    Error = (unsigned __int16)v26 | 0x80070000;
  if ( Error != -2147023899 )
  {
    if ( Error == -2147024809 )
      return 0;
    if ( Error >= 0 )
      return (unsigned int)Error;
    if ( (Microsoft_Windows_Search_ProtocolHandlersEnableBits & 0x10) != 0 )
      McTemplateU0z_EventWriteTransfer(
        Microsoft_Windows_Search_ProtocolHandlers_Context,
        MSSearchTraceId_FilterOplockFail,
        a2);
    LODWORD(AllocationSizea) = Error;
    SearchIndexerTrace::Warning(
      (wchar_t *)L"\"onecoreuap\\\\base\\\\appmodel\\\\search\\\\mssph\\\\file\\\\fileacc.cxx\"",
      (const wchar_t *)0x551,
      (unsigned int)L"[SrchPHFile] Failed to create oplock for %ls, last err %d",
      a2,
      AllocationSizea);
    goto LABEL_38;
  }
  Error = 0;
  *((_DWORD *)Context + 36) = 1;
  SearchIndexerTrace::Verbose(
    (wchar_t *)L"\"onecoreuap\\\\base\\\\appmodel\\\\search\\\\mssph\\\\file\\\\fileacc.cxx\"",
    (const wchar_t *)0x537,
    (unsigned int)L"[SrchPHFile] Created oplock for %ls",
    a2);
  if ( RegisterWaitForSingleObject(
         (PHANDLE)Context + 24,
         *((HANDLE *)Context + 12),
         CFileAccessor::s_OplockBrokenCallback,
         Context,
         0xFFFFFFFF,
         8u) )
  {
    return (unsigned int)Error;
  }
  result = ResultFromLastError();
  Error = result;
  if ( (int)result < 0 )
  {
LABEL_38:
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
      Context + 104,
      -1);
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
      Context + 96,
      0);
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
      Context + 208,
      -1);
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
      Context + 200,
      0);
    return (unsigned int)Error;
  }
  return result;
}

```

## disassembly

```asm
0x1800048f0  mov     [rsp-8+arg_18], rbx
0x1800048f5  push    rbp
0x1800048f6  push    rsi
0x1800048f7  push    rdi
0x1800048f8  push    r12
0x1800048fa  push    r13
0x1800048fc  push    r14
0x1800048fe  push    r15
0x180004900  lea     rbp, [rsp-70h]
0x180004905  sub     rsp, 170h
0x18000490c  mov     rax, cs:__security_cookie
0x180004913  xor     rax, rsp
0x180004916  mov     [rbp+0A0h+var_40], rax
0x18000491a  mov     edi, r9d
0x18000491d  mov     esi, r8d
0x180004920  mov     r12, rdx
0x180004923  mov     r14, rcx
0x180004926  and     edi, 1
0x180004929  shl     edi, 10h
0x18000492c  mov     rcx, rdx; this
0x18000492f  call    ?is_extended_length_path@wil@@YA_NPEB_W@Z; wil::is_extended_length_path(wchar_t const *)
0x180004934  movzx   ebx, al
0x180004937  lea     rax, [rbp+0A0h+var_C8]
0x18000493b  mov     [rbp+0A0h+SourceString], rax
0x18000493f  mov     [rbp+0A0h+var_D0], 41h ; 'A'
0x180004947  xor     r13d, r13d
0x18000494a  mov     [rbp+0A0h+var_C8], r13w
0x18000494f  lea     rax, ??_7?$TLMString@$0EA@$0EA@$0HPPP@@@6B@; const TLMString<64,64,32767>::`vftable'
0x180004956  mov     [rbp+0A0h+var_E0], rax
0x18000495a  mov     r9d, 0FFFFFFFFh; unsigned int
0x180004960  xor     r8d, r8d; unsigned int
0x180004963  lea     rdx, asc_18002A8A8; "\\??\\"
0x18000496a  lea     rcx, [rbp+0A0h+var_E0]; this
0x18000496e  call    ?Assign@CLMString@@UEAAHPEB_WII@Z; CLMString::Assign(wchar_t const *,uint,uint)
0x180004973  lea     rdx, [r12+rbx*8]
0x180004977  mov     rax, [rbp+0A0h+var_E0]
0x18000497b  mov     r9d, 0FFFFFFFFh
0x180004981  mov     r8d, dword ptr [rbp+0A0h+var_D0+4]
0x180004985  lea     rcx, [rbp+0A0h+var_E0]
0x180004989  mov     rax, [rax+20h]
0x18000498d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004992  xorps   xmm0, xmm0
0x180004995  movups  xmmword ptr [rsp+1A0h+DestinationString.Length], xmm0
0x18000499a  mov     rdx, [rbp+0A0h+SourceString]; SourceString
0x18000499e  lea     rcx, [rsp+1A0h+DestinationString]; DestinationString
0x1800049a3  call    cs:__imp_RtlInitUnicodeString
0x1800049a9  mov     qword ptr [rsp+1A0h+ObjectAttributes.Length], 30h ; '0'
0x1800049b2  mov     qword ptr [rbp+0A0h+ObjectAttributes.Attributes], 40h ; '@'
0x1800049ba  mov     [rbp+0A0h+ObjectAttributes.RootDirectory], r13
0x1800049be  lea     rax, [rsp+1A0h+DestinationString]
0x1800049c3  mov     [rbp+0A0h+ObjectAttributes.ObjectName], rax
0x1800049c7  xorps   xmm0, xmm0
0x1800049ca  movdqu  xmmword ptr [rbp+0A0h+ObjectAttributes.SecurityDescriptor], xmm0
0x1800049cf  movups  xmmword ptr [rbp+0A0h+IoStatusBlock], xmm0
0x1800049d3  mov     [rsp+1A0h+FileHandle], r13
0x1800049d8  or      edi, 204000h
0x1800049de  mov     [rsp+1A0h+EaLength], r13d; EaLength
0x1800049e3  mov     [rsp+1A0h+EaBuffer], r13; EaBuffer
0x1800049e8  mov     [rsp+1A0h+CreateOptions], edi; CreateOptions
0x1800049ec  mov     [rsp+1A0h+CreateDisposition], 1; CreateDisposition
0x1800049f4  mov     [rsp+1A0h+ShareAccess], 7; ShareAccess
0x1800049fc  mov     [rsp+1A0h+FileAttributes], 80h; FileAttributes
0x180004a04  mov     [rsp+1A0h+AllocationSize], r13; AllocationSize
0x180004a09  lea     r9, [rbp+0A0h+IoStatusBlock]; IoStatusBlock
0x180004a0d  lea     r8, [rsp+1A0h+ObjectAttributes]; ObjectAttributes
0x180004a12  mov     edx, esi; DesiredAccess
0x180004a14  lea     rcx, [rsp+1A0h+FileHandle]; FileHandle
0x180004a19  call    cs:__imp_NtCreateFile
0x180004a1f  mov     ebx, eax
0x180004a21  cmp     eax, 108h
0x180004a26  jnz     short loc_180004A3A
0x180004a28  mov     rcx, [rsp+1A0h+FileHandle]; hObject
0x180004a2d  call    cs:__imp_CloseHandle
0x180004a33  mov     ecx, 20h ; ' '
0x180004a38  jmp     short loc_180004A58
0x180004a3a  mov     ecx, ebx; Status
0x180004a3c  call    cs:__imp_RtlNtStatusToDosError
0x180004a42  mov     ecx, eax
0x180004a44  test    eax, eax
0x180004a46  jz      short loc_180004A61
0x180004a48  mov     ecx, 20h ; ' '
0x180004a4d  cmp     ebx, 0C0000909h
0x180004a53  cmovz   eax, ecx
0x180004a56  mov     ecx, eax; dwErrCode
0x180004a58  mov     [rsp+1A0h+FileHandle], 0FFFFFFFFFFFFFFFFh
0x180004a61  call    cs:__imp_SetLastError
0x180004a67  mov     rdi, [rsp+1A0h+FileHandle]
0x180004a6c  lea     rax, ??_7?$TLMString@$0EA@$0EA@$0HPPP@@@6B@; const TLMString<64,64,32767>::`vftable'
0x180004a73  mov     [rbp+0A0h+var_E0], rax
0x180004a77  lea     rdx, [rbp+0A0h+var_C8]; wchar_t *
0x180004a7b  lea     rcx, [rbp+0A0h+var_E0]; this
0x180004a7f  call    ?DeleteBuf@CLMString@@IEAAXPEB_W@Z; CLMString::DeleteBuf(wchar_t const *)
0x180004a84  nop
0x180004a85  mov     rsi, [r14+68h]
0x180004a89  lea     rax, [rsi-1]
0x180004a8d  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180004a91  ja      short loc_180004AAC
0x180004a93  call    cs:__imp_GetLastError
0x180004a99  mov     ebx, eax
0x180004a9b  mov     rcx, rsi; hObject
0x180004a9e  call    cs:__imp_CloseHandle
0x180004aa4  mov     ecx, ebx; dwErrCode
0x180004aa6  call    cs:__imp_SetLastError
0x180004aac  mov     [r14+68h], rdi
0x180004ab0  lea     rax, [rdi-1]
0x180004ab4  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180004ab8  ja      short loc_180004ABF
0x180004aba  mov     ebx, r13d
0x180004abd  jmp     short loc_180004AFC
0x180004abf  call    cs:__imp_GetLastError
0x180004ac5  mov     ecx, eax
0x180004ac7  lea     rdx, [r14+2B8h]
0x180004ace  call    ?HResultFromFileStatus@@YAJKAEAV?$TLMString@$0EA@$0EA@$0HPPP@@@@Z; HResultFromFileStatus(ulong,TLMString<64,64,32767> &)
0x180004ad3  mov     ebx, eax
0x180004ad5  mov     dword ptr [rsp+1A0h+AllocationSize], eax
0x180004ad9  mov     r9, r12; wchar_t *
0x180004adc  lea     r8, aSrchphfileCoul; "[SrchPHFile] Could not open file for op"...
0x180004ae3  mov     edx, 4F0h; wchar_t *
0x180004ae8  lea     rcx, aOnecoreuapBase_11; "\"onecoreuap\\\\base\\\\appmodel\\\\sea"...
0x180004aef  call    ?Warning@SearchIndexerTrace@@YAXPEB_WI0ZZ; SearchIndexerTrace::Warning(wchar_t const *,uint,wchar_t const *,...)
0x180004af4  test    ebx, ebx
0x180004af6  js      loc_180004DF4
0x180004afc  xor     r9d, r9d; lpName
0x180004aff  xor     r8d, r8d; bInitialState
0x180004b02  mov     edx, 1; bManualReset
0x180004b07  xor     ecx, ecx; lpEventAttributes
0x180004b09  call    cs:__imp_CreateEventW
0x180004b0f  mov     rsi, rax
0x180004b12  mov     r13, [r14+0C8h]
0x180004b19  lea     rdx, [r13-1]
0x180004b1d  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x180004b21  ja      short loc_180004B3C
0x180004b23  call    cs:__imp_GetLastError
0x180004b29  mov     edi, eax
0x180004b2b  mov     rcx, r13; hObject
0x180004b2e  call    cs:__imp_CloseHandle
0x180004b34  mov     ecx, edi; dwErrCode
0x180004b36  call    cs:__imp_SetLastError
0x180004b3c  mov     [r14+0C8h], rsi
0x180004b43  lea     rax, [rsi+1]
0x180004b47  test    rax, 0FFFFFFFFFFFFFFFEh
0x180004b4d  jnz     short loc_180004B75
0x180004b4f  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180004b54  mov     ebx, eax
0x180004b56  mov     dword ptr [rsp+1A0h+AllocationSize], eax
0x180004b5a  mov     r9, r12; wchar_t *
0x180004b5d  lea     r8, aSrchphfileCoul_0; "[SrchPHFile] Could not create event for"...
0x180004b64  mov     edx, 4FAh; wchar_t *
0x180004b69  lea     rcx, aOnecoreuapBase_11; "\"onecoreuap\\\\base\\\\appmodel\\\\sea"...
0x180004b70  call    ?Warning@SearchIndexerTrace@@YAXPEB_WI0ZZ; SearchIndexerTrace::Warning(wchar_t const *,uint,wchar_t const *,...)
0x180004b75  test    ebx, ebx
0x180004b77  js      loc_180004DF4
0x180004b7d  xor     r9d, r9d; lpName
0x180004b80  xor     r8d, r8d; bInitialState
0x180004b83  mov     r13d, 1
0x180004b89  mov     edx, r13d; bManualReset
0x180004b8c  xor     ecx, ecx; lpEventAttributes
0x180004b8e  call    cs:__imp_CreateEventW
0x180004b94  mov     rbx, rax
0x180004b97  mov     rcx, [r14+0D0h]; hObject
0x180004b9e  lea     rdx, [rcx-1]
0x180004ba2  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x180004ba6  ja      short loc_180004BAD
0x180004ba8  call    ?close_reset@?$close_invoke_helper@$00P6AHPEAX@Z$1?CloseHandle@@YAH0@ZPEAX@details@wil@@SAXPEAX@Z; wil::details::close_invoke_helper<1,int (*)(void *),&CloseHandle(void *),void *>::close_reset(void *)
0x180004bad  mov     [r14+0D0h], rbx
0x180004bb4  lea     rax, [rbx+1]
0x180004bb8  test    rax, 0FFFFFFFFFFFFFFFEh
0x180004bbe  jnz     short loc_180004BEE
0x180004bc0  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180004bc5  mov     ebx, eax
0x180004bc7  mov     dword ptr [rsp+1A0h+AllocationSize], eax
0x180004bcb  mov     r9, r12; wchar_t *
0x180004bce  lea     r8, aSrchphfileCoul_0; "[SrchPHFile] Could not create event for"...
0x180004bd5  mov     edx, 505h; wchar_t *
0x180004bda  lea     rcx, aOnecoreuapBase_11; "\"onecoreuap\\\\base\\\\appmodel\\\\sea"...
0x180004be1  call    ?Warning@SearchIndexerTrace@@YAXPEB_WI0ZZ; SearchIndexerTrace::Warning(wchar_t const *,uint,wchar_t const *,...)
0x180004be6  test    ebx, ebx
0x180004be8  js      loc_180004DF4
0x180004bee  xor     r9d, r9d; lpName
0x180004bf1  xor     r8d, r8d; bInitialState
0x180004bf4  mov     edx, r13d; bManualReset
0x180004bf7  xor     ecx, ecx; lpEventAttributes
0x180004bf9  call    cs:__imp_CreateEventW
0x180004bff  mov     rdi, rax
0x180004c02  mov     rsi, [r14+60h]
0x180004c06  lea     rdx, [rsi-1]
0x180004c0a  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x180004c0e  ja      short loc_180004C29
0x180004c10  call    cs:__imp_GetLastError
0x180004c16  mov     ebx, eax
0x180004c18  mov     rcx, rsi; hObject
0x180004c1b  call    cs:__imp_CloseHandle
0x180004c21  mov     ecx, ebx; dwErrCode
0x180004c23  call    cs:__imp_SetLastError
0x180004c29  mov     [r14+60h], rdi
0x180004c2d  lea     rax, [rdi+1]
0x180004c31  test    rax, 0FFFFFFFFFFFFFFFEh
0x180004c37  jnz     short loc_180004C77
0x180004c39  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180004c3e  mov     ebx, eax
0x180004c40  mov     dword ptr [rsp+1A0h+AllocationSize], eax
0x180004c44  mov     r9, r12; wchar_t *
0x180004c47  lea     r8, aSrchphfileCoul_0; "[SrchPHFile] Could not create event for"...
0x180004c4e  mov     edx, 50Fh; wchar_t *
0x180004c53  lea     rcx, aOnecoreuapBase_11; "\"onecoreuap\\\\base\\\\appmodel\\\\sea"...
0x180004c5a  call    ?Warning@SearchIndexerTrace@@YAXPEB_WI0ZZ; SearchIndexerTrace::Warning(wchar_t const *,uint,wchar_t const *,...)
0x180004c5f  mov     rdx, 0FFFFFFFFFFFFFFFFh
0x180004c66  lea     rcx, [r14+68h]
0x180004c6a  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x180004c6f  test    ebx, ebx
0x180004c71  js      loc_180004DF4
0x180004c77  mov     qword ptr [r14+70h], 0
0x180004c7f  mov     qword ptr [r14+78h], 0
0x180004c87  mov     qword ptr [r14+80h], 0
0x180004c92  mov     rax, [r14+60h]
0x180004c96  mov     [r14+88h], rax
0x180004c9d  mov     dword ptr [rsp+1A0h+FileHandle], 0
0x180004ca5  lea     rdx, [r14+0A4h]
0x180004cac  xorps   xmm0, xmm0
0x180004caf  xor     eax, eax
0x180004cb1  movups  xmmword ptr [rdx], xmm0
0x180004cb4  mov     [rdx+10h], rax
0x180004cb8  mov     [rdx], r13w
0x180004cbc  mov     ecx, 18h
0x180004cc1  mov     [r14+0A6h], cx
0x180004cc9  lea     r8, [r14+98h]; lpInBuffer
0x180004cd0  mov     [r8], r13w
0x180004cd4  mov     r9d, 0Ch; nInBufferSize
0x180004cda  mov     [r14+9Ah], r9w
0x180004ce2  mov     dword ptr [r14+9Ch], 3
0x180004ced  mov     [r14+0A0h], r13d
0x180004cf4  lea     rax, [r14+70h]
0x180004cf8  mov     qword ptr [rsp+1A0h+CreateDisposition], rax; lpOverlapped
0x180004cfd  lea     rax, [rsp+1A0h+FileHandle]
0x180004d02  mov     qword ptr [rsp+1A0h+ShareAccess], rax; lpBytesReturned
0x180004d07  mov     [rsp+1A0h+FileAttributes], ecx; nOutBufferSize
0x180004d0b  mov     [rsp+1A0h+AllocationSize], rdx; lpOutBuffer
0x180004d10  mov     edx, 90240h; dwIoControlCode
0x180004d15  mov     rcx, [r14+68h]; hDevice
0x180004d19  call    cs:__imp_DeviceIoControl
0x180004d1f  call    cs:__imp_GetLastError
0x180004d25  mov     ebx, eax
0x180004d27  test    eax, eax
0x180004d29  jle     short loc_180004D34
0x180004d2b  movzx   ebx, ax
0x180004d2e  or      ebx, 80070000h
0x180004d34  cmp     ebx, 800703E5h
0x180004d3a  jnz     short loc_180004DA3
0x180004d3c  xor     ebx, ebx
0x180004d3e  mov     [r14+90h], r13d
0x180004d45  mov     r9, r12; wchar_t *
0x180004d48  lea     r8, aSrchphfileCrea; "[SrchPHFile] Created oplock for %ls"
0x180004d4f  mov     edx, 537h; wchar_t *
0x180004d54  lea     rcx, aOnecoreuapBase_11; "\"onecoreuap\\\\base\\\\appmodel\\\\sea"...
0x180004d5b  call    ?Verbose@SearchIndexerTrace@@YAXPEB_WI0ZZ; SearchIndexerTrace::Verbose(wchar_t const *,uint,wchar_t const *,...)
0x180004d60  lea     rcx, [r14+0C0h]; phNewWaitObject
0x180004d67  mov     [rsp+1A0h+FileAttributes], 8; dwFlags
0x180004d6f  mov     dword ptr [rsp+1A0h+AllocationSize], 0FFFFFFFFh; dwMilliseconds
0x180004d77  mov     r9, r14; Context
0x180004d7a  lea     r8, ?s_OplockBrokenCallback@CFileAccessor@@SAXPEAXE@Z; Callback
0x180004d81  mov     rdx, [r14+60h]; hObject
0x180004d85  call    cs:__imp_RegisterWaitForSingleObject
0x180004d8b  test    eax, eax
0x180004d8d  jnz     loc_180004E30
0x180004d93  call    ?ResultFromLastError@@YAJXZ; ResultFromLastError(void)
0x180004d98  mov     ebx, eax
0x180004d9a  test    eax, eax
0x180004d9c  js      short loc_180004DF4
0x180004d9e  jmp     loc_180004E32
0x180004da3  cmp     ebx, 80070057h
0x180004da9  jnz     short loc_180004DB2
0x180004dab  xor     eax, eax
0x180004dad  jmp     loc_180004E32
0x180004db2  test    ebx, ebx
0x180004db4  jns     short loc_180004E30
0x180004db6  test    cs:Microsoft_Windows_Search_ProtocolHandlersEnableBits, 10h
0x180004dbd  jz      short loc_180004DD5
0x180004dbf  mov     r8, r12
0x180004dc2  lea     rdx, MSSearchTraceId_FilterOplockFail
0x180004dc9  lea     rcx, Microsoft_Windows_Search_ProtocolHandlers_Context
0x180004dd0  call    McTemplateU0z_EventWriteTransfer
0x180004dd5  mov     dword ptr [rsp+1A0h+AllocationSize], ebx
0x180004dd9  mov     r9, r12; wchar_t *
0x180004ddc  lea     r8, aSrchphfileFail; "[SrchPHFile] Failed to create oplock fo"...
0x180004de3  mov     edx, 551h; wchar_t *
0x180004de8  lea     rcx, aOnecoreuapBase_11; "\"onecoreuap\\\\base\\\\appmodel\\\\sea"...
0x180004def  call    ?Warning@SearchIndexerTrace@@YAXPEB_WI0ZZ; SearchIndexerTrace::Warning(wchar_t const *,uint,wchar_t const *,...)
0x180004df4  mov     rdx, 0FFFFFFFFFFFFFFFFh
0x180004dfb  lea     rcx, [r14+68h]
0x180004dff  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x180004e04  lea     rcx, [r14+60h]
0x180004e08  xor     edx, edx
0x180004e0a  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x180004e0f  lea     rcx, [r14+0D0h]
0x180004e16  mov     rdx, 0FFFFFFFFFFFFFFFFh
0x180004e1d  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x180004e22  lea     rcx, [r14+0C8h]
0x180004e29  xor     edx, edx
0x180004e2b  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x180004e30  mov     eax, ebx
  ... truncated ...
```
