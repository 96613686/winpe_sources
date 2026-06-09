# CoCreateTaskScheduler

- ea: `0x14005fdac`
- end: `0x14005fe79`
- name: `CoCreateTaskScheduler`
- size: `205`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x1400601fc`

## callees

- `0x14005fdac`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x14005fdfa`
- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x14005fdfa`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x14005fe1a`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x14005fe1a`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x14005fdd7`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x14005fe3f`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x14005fdd7`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x14005fe3f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14005fe5a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14005fe5a`

## string_xrefs

- `0x14005fdec`: `Global\SC_AutoStartComplete`

## pseudocode

```c
__int64 __fastcall CoCreateTaskScheduler(__int64 a1, __int64 a2, LPVOID *ppv)
{
  unsigned int Instance; // edi
  char *v5; // rbx

  Instance = CoCreateInstance(&CLSID_TaskScheduler, 0, 1u, &GUID_2faba4c7_4da9_4013_9697_20cc3fd40f85, ppv);
  if ( Instance == -2147221164 )
  {
    v5 = (char *)OpenEventW(0x100000u, 0, L"Global\\SC_AutoStartComplete");
    if ( (unsigned __int64)(v5 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
      WaitForSingleObject(v5, 0x3A98u);
    Instance = CoCreateInstance(&CLSID_TaskScheduler, 0, 1u, &GUID_2faba4c7_4da9_4013_9697_20cc3fd40f85, ppv);
    if ( (unsigned __int64)(v5 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
      CloseHandle(v5);
  }
  return Instance;
}

```

## disassembly

```asm
0x14005fdac  mov     [rsp+arg_0], rbx
0x14005fdb1  mov     [rsp+arg_8], rsi
0x14005fdb6  push    rdi
0x14005fdb7  sub     rsp, 30h
0x14005fdbb  xor     edx, edx; pUnkOuter
0x14005fdbd  mov     [rsp+38h+ppv], r8; ppv
0x14005fdc2  mov     rsi, r8
0x14005fdc5  lea     r9, _GUID_2faba4c7_4da9_4013_9697_20cc3fd40f85; riid
0x14005fdcc  lea     rcx, CLSID_TaskScheduler; rclsid
0x14005fdd3  lea     r8d, [rdx+1]; dwClsContext
0x14005fdd7  call    cs:__imp_CoCreateInstance
0x14005fdde  nop     dword ptr [rax+rax+00h]
0x14005fde3  mov     edi, eax
0x14005fde5  cmp     eax, 80040154h
0x14005fdea  jnz     short loc_14005FE66
0x14005fdec  lea     r8, aGlobalScAutost; "Global\\SC_AutoStartComplete"
0x14005fdf3  xor     edx, edx; bInheritHandle
0x14005fdf5  mov     ecx, 100000h; dwDesiredAccess
0x14005fdfa  call    cs:__imp_OpenEventW
0x14005fe01  nop     dword ptr [rax+rax+00h]
0x14005fe06  mov     rbx, rax
0x14005fe09  dec     rax
0x14005fe0c  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x14005fe10  ja      short loc_14005FE26
0x14005fe12  mov     edx, 3A98h; dwMilliseconds
0x14005fe17  mov     rcx, rbx; hHandle
0x14005fe1a  call    cs:__imp_WaitForSingleObject
0x14005fe21  nop     dword ptr [rax+rax+00h]
0x14005fe26  xor     edx, edx; pUnkOuter
0x14005fe28  mov     [rsp+38h+ppv], rsi; ppv
0x14005fe2d  lea     r9, _GUID_2faba4c7_4da9_4013_9697_20cc3fd40f85; riid
0x14005fe34  lea     rcx, CLSID_TaskScheduler; rclsid
0x14005fe3b  lea     r8d, [rdx+1]; dwClsContext
0x14005fe3f  call    cs:__imp_CoCreateInstance
0x14005fe46  nop     dword ptr [rax+rax+00h]
0x14005fe4b  mov     edi, eax
0x14005fe4d  lea     rax, [rbx-1]
0x14005fe51  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x14005fe55  ja      short loc_14005FE66
0x14005fe57  mov     rcx, rbx; hObject
0x14005fe5a  call    cs:__imp_CloseHandle
0x14005fe61  nop     dword ptr [rax+rax+00h]
0x14005fe66  mov     rbx, [rsp+38h+arg_0]
0x14005fe6b  mov     eax, edi
0x14005fe6d  mov     rsi, [rsp+38h+arg_8]
0x14005fe72  add     rsp, 30h
0x14005fe76  pop     rdi
0x14005fe77  retn
```
