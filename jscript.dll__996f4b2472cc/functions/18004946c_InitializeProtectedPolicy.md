# InitializeProtectedPolicy

- ea: `0x18004946c`
- end: `0x180049505`
- name: `InitializeProtectedPolicy`
- size: `153`
- prototype: `int()`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, loader_planting`

## callers

- `0x1800491ac`

## callees

- `0x18004946c`

## import_xrefs

- `KERNEL32!VirtualProtect` at `0x1800494c5`
- `KERNEL32!VirtualProtect` at `0x1800494f2`
- `KERNEL32!VirtualProtect` at `0x1800494c5`
- `KERNEL32!VirtualProtect` at `0x1800494f2`
- `KERNEL32!GetProcAddress` at `0x18004949c`
- `KERNEL32!GetProcAddress` at `0x18004949c`
- `KERNEL32!GetModuleHandleW` at `0x180049481`
- `KERNEL32!GetModuleHandleW` at `0x180049481`

## string_xrefs

- `0x180049472`: `api-ms-win-core-processthreads-l1-1-2.dll`

## pseudocode

```c
// write access to const memory has been detected, the output may be wrong!
int InitializeProtectedPolicy()
{
  HMODULE ModuleHandleW; // rax
  __int64 (__fastcall *v1)(COleScript *__hidden, struct IRemoteDebugApplicationThread *); // rbx
  DWORD flOldProtect; // [rsp+30h] [rbp+8h] BYREF

  flOldProtect = 0;
  ModuleHandleW = GetModuleHandleW(L"api-ms-win-core-processthreads-l1-1-2.dll");
  if ( ModuleHandleW )
  {
    ModuleHandleW = (HMODULE)GetProcAddress(ModuleHandleW, "QueryProtectedPolicy");
    v1 = (__int64 (__fastcall *)(COleScript *__hidden, struct IRemoteDebugApplicationThread *))ModuleHandleW;
    if ( ModuleHandleW )
    {
      LODWORD(ModuleHandleW) = VirtualProtect(&QueryProtectedPolicyPtr, 8u, 4u, &flOldProtect);
      if ( (_DWORD)ModuleHandleW )
      {
        QueryProtectedPolicyPtr = v1;
        LODWORD(ModuleHandleW) = VirtualProtect(&QueryProtectedPolicyPtr, 8u, flOldProtect, &flOldProtect);
      }
    }
  }
  return (int)ModuleHandleW;
}

```

## disassembly

```asm
0x18004946c  push    rbx
0x18004946e  sub     rsp, 20h
0x180049472  lea     rcx, ModuleName; "api-ms-win-core-processthreads-l1-1-2.d"...
0x180049479  mov     [rsp+28h+flOldProtect], 0
0x180049481  call    cs:__imp_GetModuleHandleW
0x180049488  nop     dword ptr [rax+rax+00h]
0x18004948d  test    rax, rax
0x180049490  jz      short loc_1800494FE
0x180049492  lea     rdx, aQueryprotected; "QueryProtectedPolicy"
0x180049499  mov     rcx, rax; hModule
0x18004949c  call    cs:__imp_GetProcAddress
0x1800494a3  nop     dword ptr [rax+rax+00h]
0x1800494a8  mov     rbx, rax
0x1800494ab  test    rax, rax
0x1800494ae  jz      short loc_1800494FE
0x1800494b0  mov     edx, 8; dwSize
0x1800494b5  lea     r9, [rsp+28h+flOldProtect]; lpflOldProtect
0x1800494ba  lea     rcx, QueryProtectedPolicyPtr; lpAddress
0x1800494c1  lea     r8d, [rdx-4]; flNewProtect
0x1800494c5  call    cs:__imp_VirtualProtect
0x1800494cc  nop     dword ptr [rax+rax+00h]
0x1800494d1  test    eax, eax
0x1800494d3  jz      short loc_1800494FE
0x1800494d5  mov     r8d, [rsp+28h+flOldProtect]; flNewProtect
0x1800494da  lea     r9, [rsp+28h+flOldProtect]; lpflOldProtect
0x1800494df  mov     edx, 8; dwSize
0x1800494e4  mov     cs:QueryProtectedPolicyPtr, rbx
0x1800494eb  lea     rcx, QueryProtectedPolicyPtr; lpAddress
0x1800494f2  call    cs:__imp_VirtualProtect
0x1800494f9  nop     dword ptr [rax+rax+00h]
0x1800494fe  add     rsp, 20h
0x180049502  pop     rbx
0x180049503  retn
```
