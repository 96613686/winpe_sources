# InitializeProtectedPolicy

- ea: `0x180048d78`
- end: `0x180048df8`
- name: `InitializeProtectedPolicy`
- size: `128`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, loader_planting`

## callers

- `0x180048d00`

## callees

- `0x180048d78`

## import_xrefs

- `KERNEL32!VirtualProtect` at `0x180048dc5`
- `KERNEL32!VirtualProtect` at `0x180048dec`
- `KERNEL32!VirtualProtect` at `0x180048dc5`
- `KERNEL32!VirtualProtect` at `0x180048dec`
- `KERNEL32!GetProcAddress` at `0x180048da2`
- `KERNEL32!GetProcAddress` at `0x180048da2`
- `KERNEL32!GetModuleHandleW` at `0x180048d8d`
- `KERNEL32!GetModuleHandleW` at `0x180048d8d`

## string_xrefs

- `0x180048d7e`: `api-ms-win-core-processthreads-l1-1-2.dll`

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
0x180048d78  push    rbx
0x180048d7a  sub     rsp, 20h
0x180048d7e  lea     rcx, ModuleName; "api-ms-win-core-processthreads-l1-1-2.d"...
0x180048d85  mov     [rsp+28h+flOldProtect], 0
0x180048d8d  call    cs:__imp_GetModuleHandleW
0x180048d93  test    rax, rax
0x180048d96  jz      short loc_180048DF2
0x180048d98  lea     rdx, aQueryprotected; "QueryProtectedPolicy"
0x180048d9f  mov     rcx, rax; hModule
0x180048da2  call    cs:__imp_GetProcAddress
0x180048da8  mov     rbx, rax
0x180048dab  test    rax, rax
0x180048dae  jz      short loc_180048DF2
0x180048db0  mov     edx, 8; dwSize
0x180048db5  lea     r9, [rsp+28h+flOldProtect]; lpflOldProtect
0x180048dba  lea     rcx, QueryProtectedPolicyPtr; lpAddress
0x180048dc1  lea     r8d, [rdx-4]; flNewProtect
0x180048dc5  call    cs:__imp_VirtualProtect
0x180048dcb  test    eax, eax
0x180048dcd  jz      short loc_180048DF2
0x180048dcf  mov     r8d, [rsp+28h+flOldProtect]; flNewProtect
0x180048dd4  lea     r9, [rsp+28h+flOldProtect]; lpflOldProtect
0x180048dd9  mov     edx, 8; dwSize
0x180048dde  mov     cs:QueryProtectedPolicyPtr, rbx
0x180048de5  lea     rcx, QueryProtectedPolicyPtr; lpAddress
0x180048dec  call    cs:__imp_VirtualProtect
0x180048df2  add     rsp, 20h
0x180048df6  pop     rbx
0x180048df7  retn
```
