# CreateCoreComponentInput

- ea: `0x18003f2e4`
- end: `0x18003f36b`
- name: `CreateCoreComponentInput`
- size: `135`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18003dd50`

## callees

- `0x18003f2e4`
- `0x180085010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18003f315`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18003f315`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003f328`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003f328`

## string_xrefs

- `0x18003f307`: `windows.ui.dll`

## pseudocode

```c
__int64 __fastcall CreateCoreComponentInput(__int64 a1, __int64 a2, _QWORD *a3)
{
  FARPROC ProcAddress; // rax
  unsigned int v5; // ebx
  HMODULE Library; // rax

  ProcAddress = (FARPROC)qword_1800B70F8;
  *a3 = 0;
  if ( ProcAddress )
    return ((unsigned int (__fastcall *)(__int64, _QWORD, _QWORD, GUID *, _QWORD *))ProcAddress)(
             1,
             0,
             0,
             &GUID_00000000_0000_0000_c000_000000000046,
             a3);
  v5 = -2147467259;
  Library = LoadLibraryExW(L"windows.ui.dll", 0, 0);
  if ( Library )
  {
    ProcAddress = GetProcAddress(Library, (LPCSTR)0x640);
    qword_1800B70F8 = (__int64)ProcAddress;
  }
  else
  {
    ProcAddress = (FARPROC)qword_1800B70F8;
  }
  if ( ProcAddress )
    return ((unsigned int (__fastcall *)(__int64, _QWORD, _QWORD, GUID *, _QWORD *))ProcAddress)(
             1,
             0,
             0,
             &GUID_00000000_0000_0000_c000_000000000046,
             a3);
  return v5;
}

```

## disassembly

```asm
0x18003f2e4  mov     [rsp+arg_0], rbx
0x18003f2e9  push    rdi
0x18003f2ea  sub     rsp, 30h
0x18003f2ee  mov     rax, cs:qword_1800B70F8
0x18003f2f5  mov     rdi, r8
0x18003f2f8  mov     qword ptr [r8], 0
0x18003f2ff  test    rax, rax
0x18003f302  jnz     short loc_18003F343
0x18003f304  xor     r8d, r8d; dwFlags
0x18003f307  lea     rcx, aWindowsUiDll; "windows.ui.dll"
0x18003f30e  xor     edx, edx; hFile
0x18003f310  mov     ebx, 80004005h
0x18003f315  call    cs:__imp_LoadLibraryExW
0x18003f31b  test    rax, rax
0x18003f31e  jz      short loc_18003F337
0x18003f320  mov     edx, 640h; lpProcName
0x18003f325  mov     rcx, rax; hModule
0x18003f328  call    cs:__imp_GetProcAddress
0x18003f32e  mov     cs:qword_1800B70F8, rax
0x18003f335  jmp     short loc_18003F33E
0x18003f337  mov     rax, cs:qword_1800B70F8
0x18003f33e  test    rax, rax
0x18003f341  jz      short loc_18003F35E
0x18003f343  xor     edx, edx
0x18003f345  mov     [rsp+38h+var_18], rdi
0x18003f34a  lea     r9, _GUID_00000000_0000_0000_c000_000000000046
0x18003f351  xor     r8d, r8d
0x18003f354  lea     ecx, [rdx+1]
0x18003f357  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f35c  mov     ebx, eax
0x18003f35e  mov     eax, ebx
0x18003f360  mov     rbx, [rsp+38h+arg_0]
0x18003f365  add     rsp, 30h
0x18003f369  pop     rdi
0x18003f36a  retn
```
