# DLpLoadEventingFunction(char const *,char const *,void * *)

- ea: `0x180043e48`
- end: `0x180043f02`
- name: `?DLpLoadEventingFunction@@YAKPEBD0PEAPEAX@Z`
- size: `186`
- prototype: `unsigned int __fastcall(LPCSTR lpProcName, const char *, FARPROC *)`
- caller_count: `4`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180001428`
- `0x180043c00`
- `0x180043ca0`
- `0x180043f08`

## callees

- `0x180043e48`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetVersion` at `0x180043e6c`
- `api-ms-win-core-sysinfo-l1-1-0!GetVersion` at `0x180043e6c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180043eba`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180043eba`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180043ea8`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180043ea8`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180043edf`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180043edf`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180043e80`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180043e80`

## string_xrefs

- `0x180043e79`: `ntdll.dll`
- `0x180043e9d`: `advapi32.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
unsigned int __fastcall DLpLoadEventingFunction(LPCSTR lpProcName, const char *a2, FARPROC *a3)
{
  HMODULE ModuleHandleW; // rax
  unsigned int result; // eax
  char v8; // cl
  FARPROC ProcAddress; // rcx

  ModuleHandleW = (HMODULE)qword_180059CB0;
  if ( qword_180059CB0 )
  {
    v8 = byte_180059C98;
  }
  else
  {
    if ( GetVersion() >= 0x6010000 )
    {
      ModuleHandleW = GetModuleHandleW(L"ntdll.dll");
      qword_180059CB0 = (__int64)ModuleHandleW;
      if ( ModuleHandleW )
      {
        byte_180059C98 = 1;
        goto LABEL_11;
      }
    }
    ModuleHandleW = LoadLibraryExW(L"advapi32.dll", 0, 8u);
    qword_180059CB0 = (__int64)ModuleHandleW;
    if ( !ModuleHandleW )
      return GetLastError();
    v8 = 0;
    byte_180059C98 = 0;
  }
  if ( !v8 )
    lpProcName = a2;
LABEL_11:
  ProcAddress = GetProcAddress(ModuleHandleW, lpProcName);
  if ( !ProcAddress )
    return GetLastError();
  result = 0;
  *a3 = ProcAddress;
  return result;
}

```

## disassembly

```asm
0x180043e48  mov     [rsp+arg_0], rbx
0x180043e4d  mov     [rsp+arg_8], rsi
0x180043e52  push    rdi
0x180043e53  sub     rsp, 20h
0x180043e57  mov     rax, cs:qword_180059CB0
0x180043e5e  mov     rsi, r8
0x180043e61  mov     rdi, rdx
0x180043e64  mov     rbx, rcx
0x180043e67  test    rax, rax
0x180043e6a  jnz     short loc_180043ECC
0x180043e6c  call    cs:__imp_GetVersion
0x180043e72  cmp     eax, 6010000h
0x180043e77  jb      short loc_180043E9B
0x180043e79  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x180043e80  call    cs:__imp_GetModuleHandleW
0x180043e86  mov     cs:qword_180059CB0, rax
0x180043e8d  test    rax, rax
0x180043e90  jz      short loc_180043E9B
0x180043e92  mov     cs:byte_180059C98, 1
0x180043e99  jmp     short loc_180043ED9
0x180043e9b  xor     edx, edx; hFile
0x180043e9d  lea     rcx, aAdvapi32Dll; "advapi32.dll"
0x180043ea4  lea     r8d, [rdx+8]; dwFlags
0x180043ea8  call    cs:__imp_LoadLibraryExW
0x180043eae  mov     cs:qword_180059CB0, rax
0x180043eb5  test    rax, rax
0x180043eb8  jnz     short loc_180043EC2
0x180043eba  call    cs:__imp_GetLastError
0x180043ec0  jmp     short loc_180043EF2
0x180043ec2  xor     cl, cl
0x180043ec4  mov     cs:byte_180059C98, cl
0x180043eca  jmp     short loc_180043ED2
0x180043ecc  mov     cl, cs:byte_180059C98
0x180043ed2  test    cl, cl
0x180043ed4  jnz     short loc_180043ED9
0x180043ed6  mov     rbx, rdi
0x180043ed9  mov     rdx, rbx; lpProcName
0x180043edc  mov     rcx, rax; hModule
0x180043edf  call    cs:__imp_GetProcAddress
0x180043ee5  mov     rcx, rax
0x180043ee8  test    rax, rax
0x180043eeb  jz      short loc_180043EBA
0x180043eed  xor     eax, eax
0x180043eef  mov     [rsi], rcx
0x180043ef2  mov     rbx, [rsp+28h+arg_0]
0x180043ef7  mov     rsi, [rsp+28h+arg_8]
0x180043efc  add     rsp, 20h
0x180043f00  pop     rdi
0x180043f01  retn
```
