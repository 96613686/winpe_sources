# CreateDuplicationProcessHandle(void * *)

- ea: `0x180022df0`
- end: `0x180022e76`
- name: `?CreateDuplicationProcessHandle@@YAJPEAPEAX@Z`
- size: `134`
- prototype: `int(void **)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, registry_config`

## callers

- `0x18002271c`
- `0x180023870`

## callees

- `0x180003620`
- `0x18000b18c`
- `0x180022df0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180022df9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180022df9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022e22`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022e22`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180022e0a`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180022e0a`

## pseudocode

```c
__int64 __fastcall CreateDuplicationProcessHandle(void **a1)
{
  DWORD CurrentProcessId; // eax
  HANDLE v3; // rax
  signed int LastError; // eax
  unsigned int v5; // ebx
  int v7; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  HANDLE v9; // [rsp+38h] [rbp+10h] BYREF

  CurrentProcessId = GetCurrentProcessId();
  v3 = OpenProcess(0x40u, 1, CurrentProcessId);
  v9 = v3;
  if ( (((unsigned __int64)v3 + 1) & 0xFFFFFFFFFFFFFFFEuLL) != 0 )
  {
    *a1 = v3;
    v5 = 0;
    v9 = 0;
  }
  else
  {
    LastError = GetLastError();
    v5 = LastError;
    if ( LastError > 0 )
      v5 = (unsigned __int16)LastError | 0x80070000;
    if ( (v5 & 0x80000000) != 0 )
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x19,
        (unsigned int)"onecoreuap\\windows\\dwm\\capture\\api\\lib\\ProcessHelper.h",
        (const char *)v5,
        v7);
  }
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v9);
  return v5;
}

```

## disassembly

```asm
0x180022df0  push    rbx; int
0x180022df2  sub     rsp, 20h
0x180022df6  mov     rbx, rcx
0x180022df9  call    cs:__imp_GetCurrentProcessId
0x180022dff  mov     edx, 1; bInheritHandle
0x180022e04  mov     r8d, eax; dwProcessId
0x180022e07  lea     ecx, [rdx+3Fh]; dwDesiredAccess
0x180022e0a  call    cs:__imp_OpenProcess
0x180022e10  mov     [rsp+28h+arg_8], rax
0x180022e15  lea     rdx, [rax+1]
0x180022e19  test    rdx, 0FFFFFFFFFFFFFFFEh
0x180022e20  jnz     short loc_180022E56
0x180022e22  call    cs:__imp_GetLastError
0x180022e28  mov     ebx, eax
0x180022e2a  test    eax, eax
0x180022e2c  jle     short loc_180022E37
0x180022e2e  movzx   ebx, ax
0x180022e31  or      ebx, 80070000h
0x180022e37  test    ebx, ebx
0x180022e39  jns     short loc_180022E64
0x180022e3b  mov     rcx, [rsp+28h]; this
0x180022e40  lea     r8, aOnecoreuapWind_2; "onecoreuap\\windows\\dwm\\capture\\api"...
0x180022e47  mov     r9d, ebx; char *
0x180022e4a  mov     edx, 19h; void *
0x180022e4f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180022e54  jmp     short loc_180022E64
0x180022e56  mov     [rbx], rax
0x180022e59  xor     ebx, ebx
0x180022e5b  mov     [rsp+28h+arg_8], 0
0x180022e64  lea     rcx, [rsp+28h+arg_8]
0x180022e69  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180022e6e  mov     eax, ebx
0x180022e70  add     rsp, 20h
0x180022e74  pop     rbx
0x180022e75  retn
```
