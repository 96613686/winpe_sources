# Microsoft::Diagnostics::Utils::Os::BuildInheritHandleAttributeList(gsl::span<void * const,-1>)

- ea: `0x1801b18c0`
- end: `0x1801b1a3f`
- name: `?BuildInheritHandleAttributeList@Os@Utils@Diagnostics@Microsoft@@CA?AUAttributeListAndMemory@1234@V?$span@QEAX$0?0@gsl@@@Z`
- size: `383`
- prototype: ``
- caller_count: `2`
- callee_count: `8`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1801b0f48`
- `0x1801e24d4`

## callees

- `0x18001b510`
- `0x1800a8ed4`
- `0x1800f7b34`
- `0x180105ad8`
- `0x18010e55c`
- `0x18010f9b8`
- `0x1801b18c0`
- `0x1801b2084`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_terminate` at `0x1801b19d9`
- `api-ms-win-crt-private-l1-1-0!_o_terminate` at `0x1801b19d9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801b1904`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801b1904`
- `api-ms-win-core-processthreads-l1-1-0!DeleteProcThreadAttributeList` at `0x1801b19a2`
- `api-ms-win-core-processthreads-l1-1-0!UpdateProcThreadAttribute` at `0x1801b1a0b`
- `api-ms-win-core-processthreads-l1-1-0!UpdateProcThreadAttribute` at `0x1801b1a0b`
- `api-ms-win-core-processthreads-l1-1-0!InitializeProcThreadAttributeList` at `0x1801b18f6`
- `api-ms-win-core-processthreads-l1-1-0!InitializeProcThreadAttributeList` at `0x1801b1969`
- `api-ms-win-core-processthreads-l1-1-0!InitializeProcThreadAttributeList` at `0x1801b18f6`
- `api-ms-win-core-processthreads-l1-1-0!InitializeProcThreadAttributeList` at `0x1801b1969`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Microsoft::Diagnostics::Utils::Os::BuildInheritHandleAttributeList(__int64 a1, __int64 a2)
{
  const char *v4; // r9
  __int64 v5; // rax
  const char *v6; // r9
  struct _PROC_THREAD_ATTRIBUTE_LIST *v7; // rdi
  const char *v8; // r9
  void (__stdcall *v10)(LPPROC_THREAD_ATTRIBUTE_LIST); // [rsp+48h] [rbp-18h] BYREF
  _BYTE v11[16]; // [rsp+50h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+18h]
  ULONG_PTR Size; // [rsp+90h] [rbp+30h] BYREF
  __int64 v14; // [rsp+98h] [rbp+38h] BYREF

  Size = 0;
  if ( !InitializeProcThreadAttributeList(0, 1u, 0, &Size) && GetLastError() != 122 )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0xE4D,
      (unsigned int)"onecore\\base\\telemetry\\utc\\include\\OsUtils.h",
      v4);
  *(_QWORD *)a1 = 0;
  *(_QWORD *)(a1 + 8) = 0;
  v5 = std::make_unique<unsigned char [0],0>(&v14);
  std::unique_ptr<enum gsl::byte [0]>::operator=<std::default_delete<enum gsl::byte [0]>,0>(a1, v5);
  std::unique_ptr<void * [0]>::~unique_ptr<void * [0]>(&v14);
  if ( !InitializeProcThreadAttributeList(*(LPPROC_THREAD_ATTRIBUTE_LIST *)a1, 1u, 0, &Size) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0xE57,
      (unsigned int)"onecore\\base\\telemetry\\utc\\include\\OsUtils.h",
      v6);
  v7 = *(struct _PROC_THREAD_ATTRIBUTE_LIST **)a1;
  if ( *(_QWORD *)(a1 + 8) )
  {
    v14 = *(_QWORD *)(a1 + 8);
    wil::last_error_context::last_error_context((wil::last_error_context *)v11);
    v10 = DeleteProcThreadAttributeList;
    wistd::invoke<void * (*)(void *),void * &>(&v10, &v14);
    wil::last_error_context::~last_error_context((wil::last_error_context *)v11);
  }
  *(_QWORD *)(a1 + 8) = v7;
  if ( *(_QWORD *)a2 >= 0x1FFFFFFFFFFFFFFFuLL )
  {
    _o_terminate();
    __debugbreak();
  }
  if ( !UpdateProcThreadAttribute(v7, 0, 0x20002u, *(PVOID *)(a2 + 8), 8 * (unsigned int)*(_QWORD *)a2, 0, 0) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0xE63,
      (unsigned int)"onecore\\base\\telemetry\\utc\\include\\OsUtils.h",
      v8);
  return a1;
}

```

## disassembly

```asm
0x1801b18c0  mov     [rsp-18h+arg_8], rbx
0x1801b18c5  mov     [rsp-18h+arg_0], rcx
0x1801b18ca  push    rbp
0x1801b18cb  push    rsi
0x1801b18cc  push    rdi
0x1801b18cd  mov     rbp, rsp
0x1801b18d0  sub     rsp, 60h
0x1801b18d4  mov     rsi, rdx
0x1801b18d7  mov     rbx, rcx
0x1801b18da  mov     [rbp+var_20], 0
0x1801b18e1  mov     [rbp+Size], 0
0x1801b18e9  lea     r9, [rbp+Size]; lpSize
0x1801b18ed  xor     r8d, r8d; dwFlags
0x1801b18f0  lea     edx, [r8+1]; dwAttributeCount
0x1801b18f4  xor     ecx, ecx; lpAttributeList
0x1801b18f6  call    cs:__imp_InitializeProcThreadAttributeList
0x1801b18fc  test    eax, eax
0x1801b18fe  jnz     short loc_1801B1924
0x1801b1900  mov     rdi, [rbp+18h]
0x1801b1904  call    cs:__imp_GetLastError
0x1801b190a  cmp     eax, 7Ah ; 'z'
0x1801b190d  jz      short loc_1801B1924
0x1801b190f  lea     r8, aOnecoreBaseTel_240; "onecore\\base\\telemetry\\utc\\include"...
0x1801b1916  mov     edx, 0E4Dh; void *
0x1801b191b  mov     rcx, rdi; this
0x1801b191e  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1801b1924  mov     qword ptr [rbx], 0
0x1801b192b  mov     qword ptr [rbx+8], 0
0x1801b1933  mov     [rbp+var_20], 1
0x1801b193a  mov     rdx, [rbp+Size]
0x1801b193e  lea     rcx, [rbp+arg_18]
0x1801b1942  call    ??$make_unique@$$BY0A@E$0A@@std@@YA?AV?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@std@@@0@_K@Z; std::make_unique<uchar [0],0>(unsigned __int64)
0x1801b1947  mov     rdx, rax
0x1801b194a  mov     rcx, rbx
0x1801b194d  call    ??$?4U?$default_delete@$$BY0A@W4byte@gsl@@@std@@$0A@@?$unique_ptr@$$BY0A@W4byte@gsl@@U?$default_delete@$$BY0A@W4byte@gsl@@@std@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::unique_ptr<gsl::byte [0]>::operator=<std::default_delete<gsl::byte [0]>,0>(std::unique_ptr<gsl::byte [0]> &&)
0x1801b1952  lea     rcx, [rbp+arg_18]
0x1801b1956  call    ??1?$unique_ptr@$$BY0A@PEAXU?$default_delete@$$BY0A@PEAX@std@@@std@@QEAA@XZ; std::unique_ptr<void * [0]>::~unique_ptr<void * [0]>(void)
0x1801b195b  lea     r9, [rbp+Size]; lpSize
0x1801b195f  xor     r8d, r8d; dwFlags
0x1801b1962  lea     edx, [r8+1]; dwAttributeCount
0x1801b1966  mov     rcx, [rbx]; lpAttributeList
0x1801b1969  call    cs:__imp_InitializeProcThreadAttributeList
0x1801b196f  test    eax, eax
0x1801b1971  jnz     short loc_1801B1989
0x1801b1973  mov     rcx, [rbp+18h]; this
0x1801b1977  lea     r8, aOnecoreBaseTel_240; "onecore\\base\\telemetry\\utc\\include"...
0x1801b197e  mov     edx, 0E57h; void *
0x1801b1983  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1801b1989  mov     rdi, [rbx]
0x1801b198c  mov     rax, [rbx+8]
0x1801b1990  test    rax, rax
0x1801b1993  jz      short loc_1801B19C3
0x1801b1995  mov     [rbp+arg_18], rax
0x1801b1999  lea     rcx, [rbp+var_10]; this
0x1801b199d  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x1801b19a2  mov     rax, cs:__imp_DeleteProcThreadAttributeList
0x1801b19a9  mov     [rbp+var_18], rax
0x1801b19ad  lea     rdx, [rbp+arg_18]
0x1801b19b1  lea     rcx, [rbp+var_18]
0x1801b19b5  call    ??$invoke@P6APEAXPEAX@ZAEAPEAX@wistd@@YAPEAX$$QEAP6APEAXPEAX@ZAEAPEAX@Z; wistd::invoke<void * (*)(void *),void * &>(void * (*&&)(void *),void * &)
0x1801b19ba  lea     rcx, [rbp+var_10]; this
0x1801b19be  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x1801b19c3  mov     [rbx+8], rdi
0x1801b19c7  mov     rax, [rsi]
0x1801b19ca  mov     rcx, 1FFFFFFFFFFFFFFFh
0x1801b19d4  cmp     rax, rcx
0x1801b19d7  jb      short loc_1801B19E0
0x1801b19d9  call    cs:__imp__o_terminate
0x1801b19df  int     3; Trap to Debugger
0x1801b19e0  shl     eax, 3
0x1801b19e3  mov     edx, eax
0x1801b19e5  mov     [rsp+60h+lpReturnSize], 0; lpReturnSize
0x1801b19ee  mov     [rsp+60h+lpPreviousValue], 0; lpPreviousValue
0x1801b19f7  mov     [rsp+60h+cbSize], rdx; cbSize
0x1801b19fc  mov     r9, [rsi+8]; lpValue
0x1801b1a00  xor     edx, edx; dwFlags
0x1801b1a02  mov     r8d, 20002h; Attribute
0x1801b1a08  mov     rcx, rdi; lpAttributeList
0x1801b1a0b  call    cs:__imp_UpdateProcThreadAttribute
0x1801b1a11  test    eax, eax
0x1801b1a13  jnz     short loc_1801B1A2B
0x1801b1a15  mov     rcx, [rbp+18h]; this
0x1801b1a19  lea     r8, aOnecoreBaseTel_240; "onecore\\base\\telemetry\\utc\\include"...
0x1801b1a20  mov     edx, 0E63h; void *
0x1801b1a25  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1801b1a2b  mov     rax, rbx
0x1801b1a2e  mov     rbx, [rsp+60h+arg_8]
0x1801b1a36  add     rsp, 60h
0x1801b1a3a  pop     rdi
0x1801b1a3b  pop     rsi
0x1801b1a3c  pop     rbp
0x1801b1a3d  retn
```
