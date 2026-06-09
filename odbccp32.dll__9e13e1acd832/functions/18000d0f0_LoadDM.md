# LoadDM

- ea: `0x18000d0f0`
- end: `0x18000d1e8`
- name: `LoadDM`
- size: `248`
- prototype: `__int64 __fastcall(HWND hWnd, __int64, __int64, __int64)`
- caller_count: `2`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x18000af80`
- `0x18000dc70`

## callees

- `0x18000b784`
- `0x18000d0f0`
- `0x180013c7c`
- `0x180013f00`
- `0x180015010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18000d182`
- `KERNEL32!GetLastError` at `0x18000d182`
- `KERNEL32!FreeLibrary` at `0x18000d1b2`
- `KERNEL32!FreeLibrary` at `0x18000d1b2`
- `KERNEL32!GetProcAddress` at `0x18000d13b`
- `KERNEL32!GetProcAddress` at `0x18000d13b`

## string_xrefs

- `0x18000d119`: `ODBC32.DLL`
- `0x18000d188`: `ODBC32.DLL`

## pseudocode

```c
__int64 __fastcall LoadDM(HWND hWnd, __int64 a2, __int64 a3, __int64 a4)
{
  HMODULE LibraryPD; // rax
  __int64 (*ProcAddress)(void); // rax
  __int64 v7; // rax
  DWORD LastError; // eax
  __int64 result; // rax

  if ( g_DMhInst )
    return 1;
  PrivateDriverRootInitialized(hinst, a2, a3, a4);
  LibraryPD = (HMODULE)LoadLibraryPD(L"ODBC32.DLL");
  g_DMhInst = LibraryPD;
  if ( LibraryPD )
  {
    ProcAddress = GetProcAddress(LibraryPD, "GetODBCSharedData");
    if ( ProcAddress )
    {
      v7 = ProcAddress();
      if ( v7 )
      {
        dwGlobalTraceVariable = v7;
        dwGlobalPerfMonVariable = v7 + 8;
      }
    }
    if ( g_DMhInst && dwGlobalTraceVariable && dwGlobalPerfMonVariable )
      return 1;
  }
  LastError = GetLastError();
  CpanelError(hWnd, 0x691u, 0x730u, (__int64)L"ODBC32.DLL", LastError);
  if ( g_DMhInst )
  {
    FreeLibrary(g_DMhInst);
    g_DMhInst = 0;
  }
  dwGlobalTraceVariable = 0;
  result = 0;
  dwGlobalPerfMonVariable = 0;
  return result;
}

```

## disassembly

```asm
0x18000d0f0  push    rbx
0x18000d0f2  sub     rsp, 30h
0x18000d0f6  cmp     cs:g_DMhInst, 0
0x18000d0fe  mov     rbx, rcx
0x18000d101  jnz     loc_18000D1DD
0x18000d107  mov     rcx, cs:hinst
0x18000d10e  call    PrivateDriverRootInitialized
0x18000d113  mov     r8d, 800h
0x18000d119  lea     rcx, aOdbc32Dll; "ODBC32.DLL"
0x18000d120  call    LoadLibraryPD
0x18000d125  mov     cs:g_DMhInst, rax
0x18000d12c  test    rax, rax
0x18000d12f  jz      short loc_18000D182
0x18000d131  lea     rdx, aGetodbcsharedd; "GetODBCSharedData"
0x18000d138  mov     rcx, rax; hModule
0x18000d13b  call    cs:__imp_GetProcAddress
0x18000d141  test    rax, rax
0x18000d144  jz      short loc_18000D162
0x18000d146  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d14b  test    rax, rax
0x18000d14e  jz      short loc_18000D162
0x18000d150  mov     cs:dwGlobalTraceVariable, rax
0x18000d157  add     rax, 8
0x18000d15b  mov     cs:dwGlobalPerfMonVariable, rax
0x18000d162  mov     rax, cs:g_DMhInst
0x18000d169  test    rax, rax
0x18000d16c  jz      short loc_18000D182
0x18000d16e  cmp     cs:dwGlobalTraceVariable, 0
0x18000d176  jz      short loc_18000D182
0x18000d178  cmp     cs:dwGlobalPerfMonVariable, 0
0x18000d180  jnz     short loc_18000D1DD
0x18000d182  call    cs:__imp_GetLastError
0x18000d188  lea     r9, aOdbc32Dll; "ODBC32.DLL"
0x18000d18f  mov     edx, 691h
0x18000d194  mov     r8d, 730h
0x18000d19a  mov     [rsp+38h+var_18], eax; int
0x18000d19e  mov     rcx, rbx; hWnd
0x18000d1a1  call    CpanelError
0x18000d1a6  mov     rcx, cs:g_DMhInst; hLibModule
0x18000d1ad  test    rcx, rcx
0x18000d1b0  jz      short loc_18000D1C3
0x18000d1b2  call    cs:__imp_FreeLibrary
0x18000d1b8  mov     cs:g_DMhInst, 0
0x18000d1c3  mov     cs:dwGlobalTraceVariable, 0
0x18000d1ce  xor     eax, eax
0x18000d1d0  mov     cs:dwGlobalPerfMonVariable, 0
0x18000d1db  jmp     short loc_18000D1E2
0x18000d1dd  mov     eax, 1
0x18000d1e2  add     rsp, 30h
0x18000d1e6  pop     rbx
0x18000d1e7  retn
```
