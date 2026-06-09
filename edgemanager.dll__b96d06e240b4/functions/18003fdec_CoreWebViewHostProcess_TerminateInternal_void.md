# CoreWebViewHostProcess::TerminateInternal(void)

- ea: `0x18003fdec`
- end: `0x18003fe78`
- name: `?TerminateInternal@CoreWebViewHostProcess@@AEAAXXZ`
- size: `140`
- prototype: `void(CoreWebViewHostProcess *__hidden this)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18003f970`
- `0x18003fd80`

## callees

- `0x180036418`
- `0x18003f90c`
- `0x18003fdec`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x18003fe34`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x18003fe34`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003fe16`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003fe3e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003fe16`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003fe3e`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18003fdfe`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18003fdfe`

## pseudocode

```c
void __fastcall CoreWebViewHostProcess::TerminateInternal(CoreWebViewHostProcess *this)
{
  HANDLE v2; // rax
  DWORD LastError; // eax
  unsigned int v4; // r8d
  DWORD v5; // eax
  unsigned int v6; // r8d
  unsigned int v7; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  HANDLE v9; // [rsp+30h] [rbp+8h] BYREF

  v2 = OpenProcess(1u, 0, *((_DWORD *)this + 20));
  v9 = v2;
  if ( (((unsigned __int64)v2 + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
  {
    LastError = GetLastError();
    wil::details::in1diag3::FailFast_Win32(retaddr, (void *)0x163, v4, (const char *)LastError, v7);
  }
  if ( !TerminateProcess(v2, 0) )
  {
    v5 = GetLastError();
    wil::details::in1diag3::FailFast_Win32(retaddr, (void *)0x169, v6, (const char *)v5, v7);
  }
  *((_DWORD *)this + 52) = 3;
  *((_DWORD *)this + 20) = 0;
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v9);
}

```

## disassembly

```asm
0x18003fdec  push    rbx; unsigned int
0x18003fdee  sub     rsp, 20h
0x18003fdf2  mov     r8d, [rcx+50h]; dwProcessId
0x18003fdf6  xor     edx, edx; bInheritHandle
0x18003fdf8  mov     rbx, rcx
0x18003fdfb  lea     ecx, [rdx+1]; dwDesiredAccess
0x18003fdfe  call    cs:__imp_OpenProcess
0x18003fe04  mov     [rsp+28h+arg_0], rax
0x18003fe09  lea     rdx, [rax+1]
0x18003fe0d  test    rdx, 0FFFFFFFFFFFFFFFEh
0x18003fe14  jnz     short loc_18003FE2F
0x18003fe16  call    cs:__imp_GetLastError
0x18003fe1c  mov     rcx, [rsp+28h]; this
0x18003fe21  mov     edx, 163h; void *
0x18003fe26  mov     r9d, eax; char *
0x18003fe29  call    ?FailFast_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::FailFast_Win32(void *,uint,char const *,ulong)
0x18003fe2f  xor     edx, edx; uExitCode
0x18003fe31  mov     rcx, rax; hProcess
0x18003fe34  call    cs:__imp_TerminateProcess
0x18003fe3a  test    eax, eax
0x18003fe3c  jnz     short loc_18003FE57
0x18003fe3e  call    cs:__imp_GetLastError
0x18003fe44  mov     rcx, [rsp+28h]; this
0x18003fe49  mov     edx, 169h; void *
0x18003fe4e  mov     r9d, eax; char *
0x18003fe51  call    ?FailFast_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::FailFast_Win32(void *,uint,char const *,ulong)
0x18003fe57  lea     rcx, [rsp+28h+arg_0]
0x18003fe5c  mov     dword ptr [rbx+0D0h], 3
0x18003fe66  mov     dword ptr [rbx+50h], 0
0x18003fe6d  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18003fe72  add     rsp, 20h
0x18003fe76  pop     rbx
0x18003fe77  retn
```
