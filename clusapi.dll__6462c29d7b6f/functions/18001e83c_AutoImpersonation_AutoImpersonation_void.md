# AutoImpersonation::~AutoImpersonation(void)

- ea: `0x18001e83c`
- end: `0x18001e8e1`
- name: `??1AutoImpersonation@@QEAA@XZ`
- size: `165`
- prototype: `void __fastcall(AutoImpersonation *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18001f15c`

## callees

- `0x18001e83c`
- `0x18006f910`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e85b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e881`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e85b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e881`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18001e8b1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18001e8b1`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x18001e8bf`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x18001e8bf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001e8ce`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001e8ce`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18001e877`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18001e877`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18001e851`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18001e851`

## string_xrefs

- `0x18001e865`: `Handle Impersonation - Failed to revert to self - %d`
- `0x18001e89d`: `AutoImpersonation::~AutoImpersonation`
- `0x18001e88b`: `Handle Impersonation - Failed to revert to old thread token - %d`

## pseudocode

```c
void __fastcall AutoImpersonation::~AutoImpersonation(AutoImpersonation *this)
{
  HANDLE CurrentProcess; // rax
  DWORD LastError; // [rsp+28h] [rbp-10h]
  DWORD v4; // [rsp+28h] [rbp-10h]

  if ( !*((_BYTE *)this + 8) )
    goto LABEL_8;
  if ( *(_QWORD *)this == -1 )
  {
    if ( RevertToSelf() )
      goto LABEL_8;
    LastError = GetLastError();
    TraceMsg(
      2,
      7,
      L"AutoImpersonation::~AutoImpersonation",
      8825,
      L"Handle Impersonation - Failed to revert to self - %d",
      LastError);
  }
  else
  {
    if ( ImpersonateLoggedOnUser(*(HANDLE *)this) )
      goto LABEL_8;
    v4 = GetLastError();
    TraceMsg(
      2,
      7,
      L"AutoImpersonation::~AutoImpersonation",
      8834,
      L"Handle Impersonation - Failed to revert to old thread token - %d",
      v4);
  }
  CurrentProcess = GetCurrentProcess();
  TerminateProcess(CurrentProcess, 1u);
LABEL_8:
  if ( *(_QWORD *)this != -1 )
  {
    CloseHandle(*(HANDLE *)this);
    *(_QWORD *)this = -1;
  }
}

```

## disassembly

```asm
0x18001e83c  push    rbx
0x18001e83e  sub     rsp, 30h
0x18001e842  mov     rbx, rcx
0x18001e845  cmp     byte ptr [rcx+8], 0
0x18001e849  jz      short loc_18001E8C5
0x18001e84b  cmp     qword ptr [rcx], 0FFFFFFFFFFFFFFFFh
0x18001e84f  jnz     short loc_18001E874
0x18001e851  call    cs:__imp_RevertToSelf
0x18001e857  test    eax, eax
0x18001e859  jnz     short loc_18001E8C5
0x18001e85b  call    cs:__imp_GetLastError
0x18001e861  mov     [rsp+38h+var_10], eax
0x18001e865  lea     rax, aHandleImperson_1; "Handle Impersonation - Failed to revert"...
0x18001e86c  mov     r9d, 2279h
0x18001e872  jmp     short loc_18001E898
0x18001e874  mov     rcx, [rcx]; hToken
0x18001e877  call    cs:__imp_ImpersonateLoggedOnUser
0x18001e87d  test    eax, eax
0x18001e87f  jnz     short loc_18001E8C5
0x18001e881  call    cs:__imp_GetLastError
0x18001e887  mov     [rsp+38h+var_10], eax
0x18001e88b  lea     rax, aHandleImperson; "Handle Impersonation - Failed to revert"...
0x18001e892  mov     r9d, 2282h
0x18001e898  mov     [rsp+38h+var_18], rax
0x18001e89d  lea     r8, aAutoimpersonat_0; "AutoImpersonation::~AutoImpersonation"
0x18001e8a4  mov     edx, 7
0x18001e8a9  lea     ecx, [rdx-5]
0x18001e8ac  call    ?TraceMsg@@YAXEW4_TraceType@Trace@@PEA_WK1ZZ; TraceMsg(uchar,Trace::_TraceType,wchar_t *,ulong,wchar_t *,...)
0x18001e8b1  call    cs:__imp_GetCurrentProcess
0x18001e8b7  mov     edx, 1; uExitCode
0x18001e8bc  mov     rcx, rax; hProcess
0x18001e8bf  call    cs:__imp_TerminateProcess
0x18001e8c5  cmp     qword ptr [rbx], 0FFFFFFFFFFFFFFFFh
0x18001e8c9  jz      short loc_18001E8DB
0x18001e8cb  mov     rcx, [rbx]; hObject
0x18001e8ce  call    cs:__imp_CloseHandle
0x18001e8d4  mov     qword ptr [rbx], 0FFFFFFFFFFFFFFFFh
0x18001e8db  add     rsp, 30h
0x18001e8df  pop     rbx
0x18001e8e0  retn
```
