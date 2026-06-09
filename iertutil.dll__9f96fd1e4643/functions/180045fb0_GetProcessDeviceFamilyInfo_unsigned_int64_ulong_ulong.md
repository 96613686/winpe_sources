# GetProcessDeviceFamilyInfo(unsigned __int64 *,ulong *,ulong *)

- ea: `0x180045fb0`
- end: `0x1800460bd`
- name: `?GetProcessDeviceFamilyInfo@@YA_NPEA_KPEAK1@Z`
- size: `269`
- prototype: `bool __fastcall(unsigned __int64 *, unsigned int *, unsigned int *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180045f20`

## callees

- `0x180045fb0`
- `0x1800580a7`
- `0x180083bc2`
- `0x180083c10`
- `0x180085010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180046012`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180046012`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18004602e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18004602e`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x180045fff`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x180045fff`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x18004606e`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x18004606e`
- `api-ms-win-core-errorhandling-l1-1-2!RaiseFailFastException` at `0x1800460b2`
- `api-ms-win-core-errorhandling-l1-1-2!RaiseFailFastException` at `0x1800460b2`

## string_xrefs

- `0x180046009`: `ntdll.dll`

## pseudocode

```c
char __fastcall GetProcessDeviceFamilyInfo(unsigned __int64 *a1, unsigned int *a2, unsigned int *a3)
{
  char v6; // bl
  HMODULE ModuleHandleW; // rbp
  FARPROC ProcAddress; // rax
  const wchar_t *FileNameW; // rax
  WCHAR Filename; // [rsp+20h] [rbp-248h] BYREF
  _BYTE v12[526]; // [rsp+22h] [rbp-246h] BYREF

  Filename = 0;
  memset_0(v12, 0, 0x206u);
  if ( GetModuleFileNameW(0, &Filename, 0x104u) )
  {
    FileNameW = PathFindFileNameW(&Filename);
    if ( !wcsicmp_0(FileNameW, L"iexplore.exe") )
    {
      if ( a1 )
        *a1 = 0;
      if ( a2 )
        *a2 = 3;
      if ( a3 )
        *a3 = 0;
      return 1;
    }
  }
  v6 = 0;
  ModuleHandleW = GetModuleHandleW(L"ntdll.dll");
  if ( !ModuleHandleW )
    RaiseFailFastException(0, 0, 0);
  ProcAddress = GetProcAddress(ModuleHandleW, "RtlGetDeviceFamilyInfoEnum");
  if ( ProcAddress )
  {
    ((void (__fastcall *)(unsigned __int64 *, unsigned int *, unsigned int *))ProcAddress)(a1, a2, a3);
    return 1;
  }
  return v6;
}

```

## disassembly

```asm
0x180045fb0  push    rbx
0x180045fb2  push    rbp
0x180045fb3  push    rsi
0x180045fb4  push    rdi
0x180045fb5  push    r14
0x180045fb7  sub     rsp, 240h
0x180045fbe  mov     rax, cs:__security_cookie
0x180045fc5  xor     rax, rsp
0x180045fc8  mov     [rsp+268h+var_38], rax
0x180045fd0  mov     rdi, r8
0x180045fd3  mov     rsi, rdx
0x180045fd6  mov     r14, rcx
0x180045fd9  xor     eax, eax
0x180045fdb  xor     edx, edx; Val
0x180045fdd  mov     [rsp+268h+Filename], ax
0x180045fe2  mov     r8d, 206h; Size
0x180045fe8  lea     rcx, [rsp+268h+var_246]; void *
0x180045fed  call    memset_0
0x180045ff2  mov     r8d, 104h; nSize
0x180045ff8  lea     rdx, [rsp+268h+Filename]; lpFilename
0x180045ffd  xor     ecx, ecx; hModule
0x180045fff  call    cs:__imp_GetModuleFileNameW
0x180046005  test    eax, eax
0x180046007  jnz     short loc_180046069
0x180046009  lea     rcx, ModuleName; "ntdll.dll"
0x180046010  xor     bl, bl
0x180046012  call    cs:__imp_GetModuleHandleW
0x180046018  mov     rbp, rax
0x18004601b  test    rax, rax
0x18004601e  jz      loc_1800460AB
0x180046024  lea     rdx, aRtlgetdevicefa; "RtlGetDeviceFamilyInfoEnum"
0x18004602b  mov     rcx, rbp; hModule
0x18004602e  call    cs:__imp_GetProcAddress
0x180046034  test    rax, rax
0x180046037  jz      short loc_180046049
0x180046039  mov     r8, rdi
0x18004603c  mov     rdx, rsi
0x18004603f  mov     rcx, r14
0x180046042  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046047  mov     bl, 1
0x180046049  mov     al, bl
0x18004604b  mov     rcx, [rsp+268h+var_38]
0x180046053  xor     rcx, rsp; StackCookie
0x180046056  call    __security_check_cookie
0x18004605b  add     rsp, 240h
0x180046062  pop     r14
0x180046064  pop     rdi
0x180046065  pop     rsi
0x180046066  pop     rbp
0x180046067  pop     rbx
0x180046068  retn
0x180046069  lea     rcx, [rsp+268h+Filename]; pszPath
0x18004606e  call    cs:__imp_PathFindFileNameW
0x180046074  mov     rcx, rax; String1
0x180046077  lea     rdx, aIexploreExe; "iexplore.exe"
0x18004607e  call    _wcsicmp_0
0x180046083  test    eax, eax
0x180046085  jnz     short loc_180046009
0x180046087  test    r14, r14
0x18004608a  jz      short loc_180046093
0x18004608c  mov     qword ptr [r14], 0
0x180046093  test    rsi, rsi
0x180046096  jz      short loc_18004609E
0x180046098  mov     dword ptr [rsi], 3
0x18004609e  test    rdi, rdi
0x1800460a1  jz      short loc_180046047
0x1800460a3  mov     dword ptr [rdi], 0
0x1800460a9  jmp     short loc_180046047
0x1800460ab  xor     r8d, r8d; dwFlags
0x1800460ae  xor     edx, edx; pContextRecord
0x1800460b0  xor     ecx, ecx; pExceptionRecord
0x1800460b2  call    cs:__imp_RaiseFailFastException
0x1800460b8  jmp     loc_180046024
```
