# GetProcessTokenByHandle(HWND__ *,void * *)

- ea: `0x1800ac0a8`
- end: `0x1800ac158`
- name: `?GetProcessTokenByHandle@@YAJPEAUHWND__@@PEAPEAX@Z`
- size: `176`
- prototype: `HRESULT __fastcall(HWND__ *hwnd, void **tokenHandle)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180038f74`

## callees

- `0x180042100`
- `0x18008a56c`
- `0x1800ac0a8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ac0f1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ac0f1`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800ac119`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800ac119`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1800ac0d3`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1800ac0d3`
- `USER32!GetWindowThreadProcessId` at `0x1800ac0bb`
- `USER32!GetWindowThreadProcessId` at `0x1800ac0bb`

## string_xrefs

- `0x1800ac12e`: `com\ole32\ole232\util\utils.cpp`

## pseudocode

```c
__int64 __fastcall GetProcessTokenByHandle(HWND hwnd, void **tokenHandle)
{
  HANDLE v3; // rax
  signed int v4; // eax
  unsigned int LastError; // ebx
  void *retaddr; // [rsp+28h] [rbp+0h]
  unsigned int processID; // [rsp+40h] [rbp+18h] BYREF
  wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (__cdecl*)(void *),&CloseHandle> > > processHandle; // [rsp+48h] [rbp+20h] BYREF

  processID = 0;
  GetWindowThreadProcessId(hwnd, &processID);
  v3 = OpenProcess(0x400u, 0, processID);
  processHandle.m_ptr = v3;
  if ( (((unsigned __int64)v3 + 1) & 0xFFFFFFFFFFFFFFFEuLL) != 0 )
  {
    if ( OpenProcessToken(v3, 8u, tokenHandle) )
      LastError = 0;
    else
      LastError = wil::details::in1diag3::Return_GetLastError(retaddr, 0xA28u, "com\\ole32\\ole232\\util\\utils.cpp");
  }
  else
  {
    v4 = GetLastError();
    LastError = v4;
    if ( v4 > 0 )
      LastError = (unsigned __int16)v4 | 0x80070000;
  }
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&processHandle);
  return LastError;
}

```

## disassembly

```asm
0x1800ac0a8  push    rbx
0x1800ac0aa  sub     rsp, 20h
0x1800ac0ae  and     [rsp+28h+processID], 0
0x1800ac0b3  mov     rbx, tokenHandle
0x1800ac0b6  lea     tokenHandle, [rsp+28h+processID]; lpdwProcessId
0x1800ac0bb  call    cs:__imp_GetWindowThreadProcessId
0x1800ac0c2  nop     dword ptr [rax+rax+00h]
0x1800ac0c7  mov     r8d, [rsp+28h+processID]; dwProcessId
0x1800ac0cc  xor     edx, edx; bInheritHandle
0x1800ac0ce  mov     ecx, 400h; dwDesiredAccess
0x1800ac0d3  call    cs:__imp_OpenProcess
0x1800ac0da  nop     dword ptr [rax+rax+00h]
0x1800ac0df  mov     [rsp+28h+processHandle.m_ptr], rax
0x1800ac0e4  lea     hwnd, [rax+1]
0x1800ac0e8  test    hwnd, 0FFFFFFFFFFFFFFFEh
0x1800ac0ef  jnz     short loc_1800AC10E
0x1800ac0f1  call    cs:__imp_GetLastError
0x1800ac0f8  nop     dword ptr [rax+rax+00h]
0x1800ac0fd  mov     ebx, eax
0x1800ac0ff  test    eax, eax
0x1800ac101  jle     short loc_1800AC145
0x1800ac103  movzx   ebx, ax
0x1800ac106  or      ebx, 80070000h
0x1800ac10c  jmp     short loc_1800AC145
0x1800ac10e  mov     r8, rbx; TokenHandle
0x1800ac111  mov     edx, 8; DesiredAccess
0x1800ac116  mov     hwnd, rax; ProcessHandle
0x1800ac119  call    cs:__imp_OpenProcessToken
0x1800ac120  nop     dword ptr [rax+rax+00h]
0x1800ac125  test    eax, eax
0x1800ac127  jnz     short loc_1800AC143
0x1800ac129  mov     hwnd, [rsp+28h]; callerReturnAddress
0x1800ac12e  lea     r8, aComOle32Ole232_0; "com\\ole32\\ole232\\util\\utils.cpp"
0x1800ac135  mov     edx, 0A28h; lineNumber
0x1800ac13a  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800ac13f  mov     ebx, eax
0x1800ac141  jmp     short loc_1800AC145
0x1800ac143  xor     ebx, ebx
0x1800ac145  lea     hwnd, [rsp+28h+processHandle]; this
0x1800ac14a  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800ac14f  mov     eax, ebx
0x1800ac151  add     rsp, 20h
0x1800ac155  pop     rbx
0x1800ac156  retn
```
