# DwExceptionFilter(_EXCEPTION_POINTERS * const)

- ea: `0x140043800`
- end: `0x1400439dc`
- name: `?DwExceptionFilter@@YAJQEAU_EXCEPTION_POINTERS@@@Z`
- size: `476`
- prototype: `LONG __stdcall(struct _EXCEPTION_POINTERS *ExceptionInfo)`
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callees

- `0x140001020`
- `0x140001040`
- `0x140042e84`
- `0x140043220`
- `0x140043570`
- `0x1400435ec`
- `0x140043800`
- `0x14006b586`

## import_xrefs

- `KERNEL32!SetErrorMode` at `0x14004396d`
- `KERNEL32!SetErrorMode` at `0x14004396d`
- `KERNEL32!GetErrorMode` at `0x14004395e`
- `KERNEL32!GetErrorMode` at `0x14004395e`
- `KERNEL32!GlobalMemoryStatusEx` at `0x1400438b8`
- `KERNEL32!GlobalMemoryStatusEx` at `0x1400438b8`
- `KERNEL32!IsDebuggerPresent` at `0x140043939`
- `KERNEL32!IsDebuggerPresent` at `0x140043939`
- `KERNEL32!GetCurrentThreadId` at `0x14004386f`
- `KERNEL32!GetCurrentThreadId` at `0x14004386f`
- `KERNEL32!DecodePointer` at `0x140043993`
- `KERNEL32!DecodePointer` at `0x140043993`
- `KERNEL32!GetLastError` at `0x140043863`
- `KERNEL32!GetLastError` at `0x140043889`
- `KERNEL32!GetLastError` at `0x140043863`
- `KERNEL32!GetLastError` at `0x140043889`
- `USER32!PostThreadMessageW` at `0x14004387f`
- `USER32!PostThreadMessageW` at `0x14004387f`
- `PSAPI!GetPerformanceInfo` at `0x1400438e4`
- `PSAPI!GetPerformanceInfo` at `0x1400438e4`

## pseudocode

```c
__int64 __fastcall DwExceptionFilter(struct _EXCEPTION_POINTERS *ExceptionInfo)
{
  int v3; // ebx
  DWORD CurrentThreadId; // eax
  UINT ErrorMode; // eax
  __int64 (__fastcall *v6)(struct _EXCEPTION_POINTERS *); // rax
  __int64 v7; // [rsp+0h] [rbp-F8h] BYREF
  unsigned int v8; // [rsp+20h] [rbp-D8h]
  __int64 *v9; // [rsp+28h] [rbp-D0h]
  _MEMORYSTATUSEX Buffer; // [rsp+30h] [rbp-C8h] BYREF
  _PERFORMANCE_INFORMATION v11; // [rsp+70h] [rbp-88h] BYREF

  v9 = &v7;
  if ( byte_14009F212 )
    return 0;
  v3 = 1;
  byte_14009F212 = 1;
  CollectGDIHandleUsageDiagnostics();
  g_errorPresentBeforePostMessage = GetLastError();
  CurrentThreadId = GetCurrentThreadId();
  if ( !PostThreadMessageW(CurrentThreadId, 0, 0, 0) && GetLastError() == 1816 )
    CollectMessageQueueDiagnostics();
  memset_0(&Buffer, 0, sizeof(Buffer));
  Buffer.dwLength = 64;
  if ( GlobalMemoryStatusEx(&Buffer) )
  {
    memset_0(&v11, 0, sizeof(v11));
    v11.cb = 104;
    if ( (unsigned int)GetPerformanceInfo(&v11, 104) )
    {
      Buffer.ullTotalPageFile = v11.CommitLimit * v11.PageSize;
      Buffer.ullAvailPageFile = v11.PageSize * (v11.CommitLimit - v11.CommitTotal);
    }
    WriteMemoryStatusToRegistry(&Buffer, &v11);
  }
  if ( !ExceptionInfo || ExceptionInfo->ExceptionRecord->ExceptionCode == -2147483645 || IsDebuggerPresent() )
    v3 = 0;
  else
    vGetAdditionalFiles(g_VswExceptionFilterParams, &qword_14009D8F8);
  if ( v3 )
  {
    ErrorMode = GetErrorMode();
    if ( (ErrorMode & 2) != 0 )
      SetErrorMode(ErrorMode & 0xFFFFFFFD);
    local_unwind_0(v9, &loc_140043985);
    return 0;
  }
  else
  {
    v6 = (__int64 (__fastcall *)(struct _EXCEPTION_POINTERS *))DecodePointer(g_pOldTopLevelExceptionFilter);
    if ( v6 )
    {
      v8 = v6(ExceptionInfo);
      local_unwind_0(v9, &loc_1400439B9);
      return v8;
    }
    else
    {
      local_unwind_0(v9, &loc_1400439D4);
      return 0;
    }
  }
}

```

## disassembly

```asm
0x140043800  mov     [rsp+arg_8], rbx
0x140043805  push    rdi
0x140043806  sub     rsp, 0F0h
0x14004380d  mov     rax, cs:__security_cookie
0x140043814  xor     rax, rsp
0x140043817  mov     [rsp+0F8h+var_18], rax
0x14004381f  mov     [rsp+0F8h+var_D0], rsp
0x140043824  mov     rdi, rcx
0x140043827  cmp     cs:byte_14009F212, 0
0x14004382e  jz      short loc_140043853
0x140043830  xor     eax, eax
0x140043832  mov     rcx, [rsp+0F8h+var_18]
0x14004383a  xor     rcx, rsp; StackCookie
0x14004383d  call    __security_check_cookie
0x140043842  mov     rbx, [rsp+0F8h+arg_8]
0x14004384a  add     rsp, 0F0h
0x140043851  pop     rdi
0x140043852  retn
0x140043853  mov     ebx, 1
0x140043858  mov     cs:byte_14009F212, bl
0x14004385e  call    ?CollectGDIHandleUsageDiagnostics@@YAXXZ; CollectGDIHandleUsageDiagnostics(void)
0x140043863  call    cs:__imp_GetLastError
0x140043869  mov     cs:?g_errorPresentBeforePostMessage@@3KA, eax; ulong g_errorPresentBeforePostMessage
0x14004386f  call    cs:__imp_GetCurrentThreadId
0x140043875  mov     ecx, eax; idThread
0x140043877  xor     r9d, r9d; lParam
0x14004387a  xor     r8d, r8d; wParam
0x14004387d  xor     edx, edx; Msg
0x14004387f  call    cs:__imp_PostThreadMessageW
0x140043885  test    eax, eax
0x140043887  jnz     short loc_14004389B
0x140043889  call    cs:__imp_GetLastError
0x14004388f  cmp     eax, 718h
0x140043894  jnz     short loc_14004389B
0x140043896  call    ?CollectMessageQueueDiagnostics@@YAXXZ; CollectMessageQueueDiagnostics(void)
0x14004389b  xor     edx, edx; Val
0x14004389d  lea     r8d, [rdx+40h]; Size
0x1400438a1  lea     rcx, [rsp+0F8h+Buffer]; void *
0x1400438a6  call    memset_0
0x1400438ab  mov     [rsp+0F8h+Buffer.dwLength], 40h ; '@'
0x1400438b3  lea     rcx, [rsp+0F8h+Buffer]; lpBuffer
0x1400438b8  call    cs:__imp_GlobalMemoryStatusEx
0x1400438be  test    eax, eax
0x1400438c0  jz      short loc_140043929
0x1400438c2  xor     edx, edx; Val
0x1400438c4  lea     r8d, [rdx+68h]; Size
0x1400438c8  lea     rcx, [rsp+0F8h+var_88]; void *
0x1400438cd  call    memset_0
0x1400438d2  mov     [rsp+0F8h+var_88.cb], 68h ; 'h'
0x1400438da  mov     edx, 68h ; 'h'
0x1400438df  lea     rcx, [rsp+0F8h+var_88]
0x1400438e4  call    cs:__imp_GetPerformanceInfo
0x1400438ea  test    eax, eax
0x1400438ec  jz      short loc_14004391A
0x1400438ee  mov     rax, [rsp+0F8h+var_88.PageSize]
0x1400438f6  mov     rcx, [rsp+0F8h+var_88.CommitLimit]
0x1400438fe  imul    rax, rcx
0x140043902  mov     [rsp+0F8h+Buffer.ullTotalPageFile], rax
0x140043907  sub     rcx, [rsp+0F8h+var_88.CommitTotal]
0x14004390c  imul    rcx, [rsp+0F8h+var_88.PageSize]
0x140043915  mov     [rsp+0F8h+Buffer.ullAvailPageFile], rcx
0x14004391a  lea     rdx, [rsp+0F8h+var_88]; struct _PERFORMANCE_INFORMATION *
0x14004391f  lea     rcx, [rsp+0F8h+Buffer]; struct _MEMORYSTATUSEX *
0x140043924  call    ?WriteMemoryStatusToRegistry@@YAXAEBU_MEMORYSTATUSEX@@AEBU_PERFORMANCE_INFORMATION@@@Z; WriteMemoryStatusToRegistry(_MEMORYSTATUSEX const &,_PERFORMANCE_INFORMATION const &)
0x140043929  test    rdi, rdi
0x14004392c  jz      short loc_140043958
0x14004392e  mov     rax, [rdi]
0x140043931  cmp     dword ptr [rax], 80000003h
0x140043937  jz      short loc_140043958
0x140043939  call    cs:__imp_IsDebuggerPresent
0x14004393f  test    eax, eax
0x140043941  jnz     short loc_140043958
0x140043943  lea     rdx, qword_14009D8F8; unsigned __int16 *
0x14004394a  mov     rcx, cs:?g_VswExceptionFilterParams@@3U_unnamed_type_g_VswExceptionFilterParams_@@A; unsigned __int16 *
0x140043951  call    ?vGetAdditionalFiles@@YAXPEBG0@Z; vGetAdditionalFiles(ushort const *,ushort const *)
0x140043956  jmp     short loc_14004395A
0x140043958  xor     ebx, ebx
0x14004395a  test    ebx, ebx
0x14004395c  jz      short loc_14004398C
0x14004395e  call    cs:__imp_GetErrorMode
0x140043964  test    al, 2
0x140043966  jz      short loc_140043973
0x140043968  and     eax, 0FFFFFFFDh
0x14004396b  mov     ecx, eax; uMode
0x14004396d  call    cs:__imp_SetErrorMode
0x140043973  lea     rdx, loc_140043985
0x14004397a  mov     rcx, [rsp+0F8h+var_D0]
0x14004397f  call    _local_unwind_0
0x140043984  nop
0x140043985  xor     eax, eax
0x140043987  jmp     loc_140043832
0x14004398c  mov     rcx, cs:?g_pOldTopLevelExceptionFilter@@3PEAXEA; Ptr
0x140043993  call    cs:__imp_DecodePointer
0x140043999  test    rax, rax
0x14004399c  jz      short loc_1400439C2
0x14004399e  mov     rcx, rdi
0x1400439a1  call    rax
0x1400439a3  mov     [rsp+0F8h+var_D8], eax
0x1400439a7  lea     rdx, loc_1400439B9
0x1400439ae  mov     rcx, [rsp+0F8h+var_D0]
0x1400439b3  call    _local_unwind_0
0x1400439b8  nop
0x1400439b9  mov     eax, [rsp+0F8h+var_D8]
0x1400439bd  jmp     loc_140043832
0x1400439c2  lea     rdx, loc_1400439D4
0x1400439c9  mov     rcx, [rsp+0F8h+var_D0]
0x1400439ce  call    _local_unwind_0
0x1400439d3  nop
0x1400439d4  xor     eax, eax
0x1400439d6  jmp     loc_140043832
0x14006bc90  push    rbp
0x14006bc92  sub     rsp, 20h
0x14006bc96  mov     rbp, rdx
0x14006bc99  mov     cs:byte_14009F212, 0
0x14006bca0  add     rsp, 20h
0x14006bca4  pop     rbp
0x14006bca5  retn
```
