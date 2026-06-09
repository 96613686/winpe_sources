# UpdrGetTempPath(ulong,ushort *)

- ea: `0x180069ab4`
- end: `0x180069b48`
- name: `?UpdrGetTempPath@@YAKKPEAG@Z`
- size: `148`
- prototype: `unsigned int(unsigned int, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180069db0`

## callees

- `0x180069ab4`
- `0x180084010`

## import_xrefs

- `api-ms-win-core-file-l1-2-0!GetTempPathW` at `0x180069b18`
- `api-ms-win-core-file-l1-2-0!GetTempPathW` at `0x180069b18`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180069aee`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180069aee`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180069b2e`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180069b2e`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180069ad0`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180069ad0`

## string_xrefs

- `0x180069ae4`: `GetTempPath2W`
- `0x180069ac1`: `kernelbase.dll`

## pseudocode

```c
__int64 __fastcall UpdrGetTempPath(__int64 a1, unsigned __int16 *a2)
{
  HMODULE Library; // rax
  HMODULE v4; // rbx
  FARPROC ProcAddress; // rax
  DWORD TempPathW; // edi

  Library = LoadLibraryExW(L"kernelbase.dll", 0, 0x800u);
  v4 = Library;
  if ( Library )
  {
    ProcAddress = GetProcAddress(Library, "GetTempPath2W");
    if ( ProcAddress )
    {
      TempPathW = ((__int64 (__fastcall *)(__int64, unsigned __int16 *))ProcAddress)(260, a2);
LABEL_5:
      FreeLibrary(v4);
      return TempPathW;
    }
  }
  TempPathW = GetTempPathW(0x104u, a2);
  if ( v4 )
    goto LABEL_5;
  return TempPathW;
}

```

## disassembly

```asm
0x180069ab4  mov     [rsp+arg_0], rbx
0x180069ab9  push    rdi
0x180069aba  sub     rsp, 20h
0x180069abe  mov     rdi, rdx
0x180069ac1  lea     rcx, aKernelbaseDll_0; "kernelbase.dll"
0x180069ac8  xor     edx, edx; hFile
0x180069aca  mov     r8d, 800h; dwFlags
0x180069ad0  call    cs:__imp_LoadLibraryExW
0x180069ad7  nop     dword ptr [rax+rax+00h]
0x180069adc  mov     rbx, rax
0x180069adf  test    rax, rax
0x180069ae2  jz      short loc_180069B10
0x180069ae4  lea     rdx, ProcName; "GetTempPath2W"
0x180069aeb  mov     rcx, rax; hModule
0x180069aee  call    cs:__imp_GetProcAddress
0x180069af5  nop     dword ptr [rax+rax+00h]
0x180069afa  test    rax, rax
0x180069afd  jz      short loc_180069B10
0x180069aff  mov     rdx, rdi
0x180069b02  mov     ecx, 104h
0x180069b07  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180069b0c  mov     edi, eax
0x180069b0e  jmp     short loc_180069B2B
0x180069b10  mov     rdx, rdi; lpBuffer
0x180069b13  mov     ecx, 104h; nBufferLength
0x180069b18  call    cs:__imp_GetTempPathW
0x180069b1f  nop     dword ptr [rax+rax+00h]
0x180069b24  mov     edi, eax
0x180069b26  test    rbx, rbx
0x180069b29  jz      short loc_180069B3A
0x180069b2b  mov     rcx, rbx; hLibModule
0x180069b2e  call    cs:__imp_FreeLibrary
0x180069b35  nop     dword ptr [rax+rax+00h]
0x180069b3a  mov     rbx, [rsp+28h+arg_0]
0x180069b3f  mov     eax, edi
0x180069b41  add     rsp, 20h
0x180069b45  pop     rdi
0x180069b46  retn
```
