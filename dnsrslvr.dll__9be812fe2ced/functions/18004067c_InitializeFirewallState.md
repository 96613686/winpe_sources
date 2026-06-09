# InitializeFirewallState

- ea: `0x18004067c`
- end: `0x180040766`
- name: `InitializeFirewallState`
- size: `234`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x1800495c0`

## callees

- `0x18004067c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800406ba`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800406ba`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800406d1`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800406ec`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180040707`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18004071b`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180040736`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180040751`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800406d1`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800406ec`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180040707`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18004071b`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180040736`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180040751`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800406a8`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800406a8`

## string_xrefs

- `0x180040684`: `Fwpuclnt.dll`
- `0x1800406c7`: `FwpmEngineOpen0`

## pseudocode

```c
__int64 InitializeFirewallState()
{
  unsigned int v0; // ebx
  HMODULE Library; // rax

  v0 = 0;
  qword_1800ABCC0 = 0;
  qword_1800ABCC8 = 0;
  qword_1800ABCB8 = 0;
  Library = LoadLibraryExW(L"Fwpuclnt.dll", 0, 0x800u);
  hLibModule = Library;
  if ( Library )
  {
    qword_1800ABCC0 = (__int64)GetProcAddress(Library, "FwpmEngineOpen0");
    qword_1800ABCC8 = (__int64)GetProcAddress(hLibModule, "FwpmEngineClose0");
    GetProcAddress(hLibModule, "FwpsAleGetPortStatus0");
    qword_1800ABCD0 = (__int64)GetProcAddress(hLibModule, "FwpiVpnTriggerInitializeNrptTriggering");
    qword_1800ABCD8 = (__int64)GetProcAddress(hLibModule, "FwpiVpnTriggerUninitializeNrptTriggering");
    qword_1800ABCE0 = (__int64)GetProcAddress(hLibModule, "FwpmFreeMemory0");
  }
  else
  {
    return GetLastError();
  }
  return v0;
}

```

## disassembly

```asm
0x18004067c  push    rbx
0x18004067e  sub     rsp, 20h
0x180040682  xor     ebx, ebx
0x180040684  lea     rcx, aFwpuclntDll; "Fwpuclnt.dll"
0x18004068b  xor     edx, edx; hFile
0x18004068d  mov     cs:qword_1800ABCC0, rbx
0x180040694  mov     r8d, 800h; dwFlags
0x18004069a  mov     cs:qword_1800ABCC8, rbx
0x1800406a1  mov     cs:qword_1800ABCB8, rbx
0x1800406a8  call    cs:__imp_LoadLibraryExW
0x1800406ae  mov     cs:hLibModule, rax
0x1800406b5  test    rax, rax
0x1800406b8  jnz     short loc_1800406C7
0x1800406ba  call    cs:__imp_GetLastError
0x1800406c0  mov     ebx, eax
0x1800406c2  jmp     loc_18004075E
0x1800406c7  lea     rdx, ProcName; "FwpmEngineOpen0"
0x1800406ce  mov     rcx, rax; hModule
0x1800406d1  call    cs:__imp_GetProcAddress
0x1800406d7  mov     rcx, cs:hLibModule; hModule
0x1800406de  lea     rdx, aFwpmengineclos; "FwpmEngineClose0"
0x1800406e5  mov     cs:qword_1800ABCC0, rax
0x1800406ec  call    cs:__imp_GetProcAddress
0x1800406f2  mov     rcx, cs:hLibModule; hModule
0x1800406f9  lea     rdx, aFwpsalegetport; "FwpsAleGetPortStatus0"
0x180040700  mov     cs:qword_1800ABCC8, rax
0x180040707  call    cs:__imp_GetProcAddress
0x18004070d  mov     rcx, cs:hLibModule; hModule
0x180040714  lea     rdx, aFwpivpntrigger_0; "FwpiVpnTriggerInitializeNrptTriggering"
0x18004071b  call    cs:__imp_GetProcAddress
0x180040721  mov     rcx, cs:hLibModule; hModule
0x180040728  lea     rdx, aFwpivpntrigger; "FwpiVpnTriggerUninitializeNrptTriggerin"...
0x18004072f  mov     cs:qword_1800ABCD0, rax
0x180040736  call    cs:__imp_GetProcAddress
0x18004073c  mov     rcx, cs:hLibModule; hModule
0x180040743  lea     rdx, aFwpmfreememory; "FwpmFreeMemory0"
0x18004074a  mov     cs:qword_1800ABCD8, rax
0x180040751  call    cs:__imp_GetProcAddress
0x180040757  mov     cs:qword_1800ABCE0, rax
0x18004075e  mov     eax, ebx
0x180040760  add     rsp, 20h
0x180040764  pop     rbx
0x180040765  retn
```
