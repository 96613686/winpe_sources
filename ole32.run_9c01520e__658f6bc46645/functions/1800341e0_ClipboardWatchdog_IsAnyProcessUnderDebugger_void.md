# ClipboardWatchdog::IsAnyProcessUnderDebugger(void)

- ea: `0x1800341e0`
- end: `0x1800342ff`
- name: `?IsAnyProcessUnderDebugger@ClipboardWatchdog@@CA_NXZ`
- size: `287`
- prototype: `bool __fastcall()`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180034150`

## callees

- `0x1800341e0`
- `0x180039dd4`

## import_xrefs

- `ntdll!NtQuerySystemInformation` at `0x1800341fc`
- `ntdll!NtQuerySystemInformation` at `0x18003423c`
- `ntdll!NtQuerySystemInformation` at `0x1800341fc`
- `ntdll!NtQuerySystemInformation` at `0x18003423c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180034294`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180034294`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18003426c`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18003426c`
- `api-ms-win-core-debug-l1-1-1!CheckRemoteDebuggerPresent` at `0x1800342b1`
- `api-ms-win-core-debug-l1-1-1!CheckRemoteDebuggerPresent` at `0x1800342b1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003420c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003420c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800342d5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800342e8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800342d5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800342e8`

## pseudocode

```c
char __fastcall ClipboardWatchdog::IsAnyProcessUnderDebugger()
{
  unsigned int *v0; // rax
  unsigned int *v1; // rbx
  unsigned int *v2; // rsi
  HANDLE v3; // rax
  void *v4; // rdi
  unsigned int bufferSize; // [rsp+40h] [rbp+8h] BYREF
  int result; // [rsp+48h] [rbp+10h] BYREF
  wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_only_resource_policy<int (__cdecl*)(void *),&CloseHandle> > > processHandle; // [rsp+50h] [rbp+18h] BYREF

  bufferSize = 0;
  NtQuerySystemInformation(SystemProcessInformation, 0, 0, &bufferSize);
  v0 = (unsigned int *)CoTaskMemAlloc(bufferSize);
  v1 = v0;
  if ( v0 )
  {
    if ( bufferSize && !NtQuerySystemInformation(SystemProcessInformation, v0, bufferSize, &bufferSize) )
    {
      v2 = v1;
      while ( v2 )
      {
        result = 0;
        v3 = OpenProcess(0x400u, 0, v2[20]);
        processHandle.m_ptr = v3;
        v4 = v3;
        if ( v3 && CheckRemoteDebuggerPresent(v3, &result) && result )
        {
          wil::details::unique_storage<wil::details::handle_null_only_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_only_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&processHandle);
          CoTaskMemFree(v1);
          return 1;
        }
        if ( *v2 )
          v2 = (unsigned int *)((char *)v2 + *v2);
        else
          v2 = 0;
        if ( v4 )
          CloseHandle(v4);
      }
    }
    CoTaskMemFree(v1);
  }
  return 0;
}

```

## disassembly

```asm
0x1800341e0  push    rbx
0x1800341e2  push    rsi
0x1800341e3  push    rdi
0x1800341e4  sub     rsp, 20h
0x1800341e8  and     [rsp+38h+bufferSize], 0
0x1800341ed  lea     r9, [rsp+38h+bufferSize]; ReturnLength
0x1800341f2  xor     edx, edx; SystemInformation
0x1800341f4  xor     r8d, r8d; SystemInformationLength
0x1800341f7  lea     edi, [rdx+5]
0x1800341fa  mov     ecx, edi; SystemInformationClass
0x1800341fc  call    cs:__imp_NtQuerySystemInformation
0x180034203  nop     dword ptr [rax+rax+00h]
0x180034208  mov     ecx, [rsp+38h+bufferSize]; cb
0x18003420c  call    cs:__imp_CoTaskMemAlloc
0x180034213  nop     dword ptr [rax+rax+00h]
0x180034218  mov     rbx, rax
0x18003421b  test    rax, rax
0x18003421e  jz      loc_1800342F4
0x180034224  mov     r8d, [rsp+38h+bufferSize]; SystemInformationLength
0x180034229  test    r8d, r8d
0x18003422c  jz      loc_1800342E5
0x180034232  lea     r9, [rsp+38h+bufferSize]; ReturnLength
0x180034237  mov     rdx, rax; SystemInformation
0x18003423a  mov     ecx, edi; SystemInformationClass
0x18003423c  call    cs:__imp_NtQuerySystemInformation
0x180034243  nop     dword ptr [rax+rax+00h]
0x180034248  test    eax, eax
0x18003424a  jnz     loc_1800342E5
0x180034250  mov     rsi, rbx
0x180034253  test    rsi, rsi
0x180034256  jz      loc_1800342E5
0x18003425c  and     [rsp+38h+result], 0
0x180034261  xor     edx, edx; bInheritHandle
0x180034263  mov     r8d, [rsi+50h]; dwProcessId
0x180034267  mov     ecx, 400h; dwDesiredAccess
0x18003426c  call    cs:__imp_OpenProcess
0x180034273  nop     dword ptr [rax+rax+00h]
0x180034278  mov     [rsp+38h+processHandle.m_ptr], rax
0x18003427d  mov     rdi, rax
0x180034280  test    rax, rax
0x180034283  jnz     short loc_1800342A9
0x180034285  cmp     dword ptr [rsi], 0
0x180034288  jnz     short loc_1800342A2
0x18003428a  xor     esi, esi
0x18003428c  test    rdi, rdi
0x18003428f  jz      short loc_180034253
0x180034291  mov     rcx, rdi; hObject
0x180034294  call    cs:__imp_CloseHandle
0x18003429b  nop     dword ptr [rax+rax+00h]
0x1800342a0  jmp     short loc_180034253
0x1800342a2  mov     eax, [rsi]
0x1800342a4  add     rsi, rax
0x1800342a7  jmp     short loc_18003428C
0x1800342a9  lea     rdx, [rsp+38h+result]; pbDebuggerPresent
0x1800342ae  mov     rcx, rdi; hProcess
0x1800342b1  call    cs:__imp_CheckRemoteDebuggerPresent
0x1800342b8  nop     dword ptr [rax+rax+00h]
0x1800342bd  test    eax, eax
0x1800342bf  jz      short loc_180034285
0x1800342c1  cmp     [rsp+38h+result], 0
0x1800342c6  jz      short loc_180034285
0x1800342c8  lea     rcx, [rsp+38h+processHandle]; this
0x1800342cd  call    ??1?$unique_storage@U?$handle_null_only_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_only_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_only_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800342d2  mov     rcx, rbx; pv
0x1800342d5  call    cs:__imp_CoTaskMemFree
0x1800342dc  nop     dword ptr [rax+rax+00h]
0x1800342e1  mov     al, 1
0x1800342e3  jmp     short loc_1800342F6
0x1800342e5  mov     rcx, rbx; pv
0x1800342e8  call    cs:__imp_CoTaskMemFree
0x1800342ef  nop     dword ptr [rax+rax+00h]
0x1800342f4  xor     al, al
0x1800342f6  add     rsp, 20h
0x1800342fa  pop     rdi
0x1800342fb  pop     rsi
0x1800342fc  pop     rbx
0x1800342fd  retn
```
