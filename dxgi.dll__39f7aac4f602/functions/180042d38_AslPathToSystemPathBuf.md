# AslPathToSystemPathBuf

- ea: `0x180042d38`
- end: `0x180042e32`
- name: `AslPathToSystemPathBuf`
- size: `250`
- prototype: ``
- caller_count: `4`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x180041250`
- `0x180061380`
- `0x1800bd7e0`
- `0x1800bd914`

## callees

- `0x18004281c`
- `0x180042d38`
- `0x180042e38`
- `0x180042e7c`
- `0x180076f20`
- `0x1800cb010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180042d8f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180042d8f`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180042d77`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180042d77`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180042da5`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180042da5`

## string_xrefs

- `0x180042d65`: `ntdll.dll`
- `0x180042dc6`: `Failed to get system root directory [%x]`
- `0x180042dd7`: `AslPathToSystemPathBuf`
- `0x180042e0f`: `AslPathToSystemPathBuf`

## pseudocode

```c
__int64 __fastcall AslPathToSystemPathBuf(void *a1, __int64 a2, __int64 a3)
{
  __int64 v6; // rbx
  HMODULE Library; // rax
  HMODULE v8; // rdi
  __int64 (*ProcAddress)(void); // rax
  int v10; // eax
  unsigned int v11; // ebx
  int v12; // eax

  memset_0(a1, 0, 2 * a2);
  v6 = (__int64)Src;
  if ( !Src )
  {
    v6 = 2147352624;
    Library = LoadLibraryExW(L"ntdll.dll", 0, 0x800u);
    v8 = Library;
    if ( Library )
    {
      ProcAddress = GetProcAddress(Library, "RtlGetNtSystemRoot");
      if ( ProcAddress )
        v6 = ProcAddress();
      FreeLibrary(v8);
    }
    Src = (wchar_t *)v6;
  }
  v10 = RtlStringCchCopyW(a1, a2, v6);
  v11 = v10;
  if ( v10 >= 0 )
  {
    v12 = RtlStringCchCatW(a1, a2, a3);
    v11 = v12;
    if ( v12 < 0 )
    {
      AslLogCallPrintf(1, "AslPathToSystemPathBuf", 1488, "Failed to cat string [%x]", v12);
      return (unsigned int)-1073741811;
    }
  }
  else
  {
    AslLogCallPrintf(1, "AslPathToSystemPathBuf", 1477, "Failed to get system root directory [%x]", v10);
  }
  return v11;
}

```

## disassembly

```asm
0x180042d38  push    rbx
0x180042d3a  push    rbp
0x180042d3b  push    rsi
0x180042d3c  push    rdi
0x180042d3d  push    r14
0x180042d3f  sub     rsp, 30h
0x180042d43  mov     r14, r8
0x180042d46  mov     rsi, rdx
0x180042d49  lea     r8, [rdx+rdx]; Size
0x180042d4d  mov     rbp, rcx
0x180042d50  xor     edx, edx; Val
0x180042d52  call    memset_0
0x180042d57  mov     rbx, cs:Src
0x180042d5e  test    rbx, rbx
0x180042d61  jnz     short loc_180042DB2
0x180042d63  xor     edx, edx; hFile
0x180042d65  lea     rcx, aNtdllDll_1; "ntdll.dll"
0x180042d6c  mov     r8d, 800h; dwFlags
0x180042d72  mov     ebx, 7FFE0030h
0x180042d77  call    cs:__imp_LoadLibraryExW
0x180042d7d  mov     rdi, rax
0x180042d80  test    rax, rax
0x180042d83  jz      short loc_180042DAB
0x180042d85  lea     rdx, aRtlgetntsystem; "RtlGetNtSystemRoot"
0x180042d8c  mov     rcx, rax; hModule
0x180042d8f  call    cs:__imp_GetProcAddress
0x180042d95  test    rax, rax
0x180042d98  jz      short loc_180042DA2
0x180042d9a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042d9f  mov     rbx, rax
0x180042da2  mov     rcx, rdi; hLibModule
0x180042da5  call    cs:__imp_FreeLibrary
0x180042dab  mov     cs:Src, rbx
0x180042db2  mov     r8, rbx
0x180042db5  mov     rdx, rsi
0x180042db8  mov     rcx, rbp
0x180042dbb  call    RtlStringCchCopyW
0x180042dc0  mov     ebx, eax
0x180042dc2  test    eax, eax
0x180042dc4  jns     short loc_180042DEA
0x180042dc6  lea     r9, aFailedToGetSys; "Failed to get system root directory [%x"...
0x180042dcd  mov     [rsp+58h+var_38], eax
0x180042dd1  mov     r8d, 5C5h
0x180042dd7  lea     rdx, aAslpathtosyste_0; "AslPathToSystemPathBuf"
0x180042dde  mov     ecx, 1
0x180042de3  call    AslLogCallPrintf
0x180042de8  jmp     short loc_180042E25
0x180042dea  mov     r8, r14
0x180042ded  mov     rdx, rsi
0x180042df0  mov     rcx, rbp
0x180042df3  call    RtlStringCchCatW
0x180042df8  mov     ebx, eax
0x180042dfa  test    eax, eax
0x180042dfc  jns     short loc_180042E25
0x180042dfe  lea     r9, aFailedToCatStr; "Failed to cat string [%x]"
0x180042e05  mov     [rsp+58h+var_38], eax
0x180042e09  mov     r8d, 5D0h
0x180042e0f  lea     rdx, aAslpathtosyste_0; "AslPathToSystemPathBuf"
0x180042e16  mov     ecx, 1
0x180042e1b  call    AslLogCallPrintf
0x180042e20  mov     ebx, 0C000000Dh
0x180042e25  mov     eax, ebx
0x180042e27  add     rsp, 30h
0x180042e2b  pop     r14
0x180042e2d  pop     rdi
0x180042e2e  pop     rsi
0x180042e2f  pop     rbp
0x180042e30  pop     rbx
0x180042e31  retn
```
