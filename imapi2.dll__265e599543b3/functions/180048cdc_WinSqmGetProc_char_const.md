# _WinSqmGetProc(char const *)

- ea: `0x180048cdc`
- end: `0x180048d45`
- name: `?_WinSqmGetProc@@YAP6A_JXZPEBD@Z`
- size: `105`
- prototype: `__int64 (*__fastcall(LPCSTR lpProcName))(void)`
- caller_count: `5`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800489d0`
- `0x180048a34`
- `0x180048a94`
- `0x180048b14`
- `0x180048b8c`

## callees

- `0x180048cdc`

## import_xrefs

- `KERNEL32!LoadLibraryW` at `0x180048d03`
- `KERNEL32!LoadLibraryW` at `0x180048d03`
- `KERNEL32!GetProcAddress` at `0x180048d2e`
- `KERNEL32!GetProcAddress` at `0x180048d2e`
- `KERNEL32!FreeLibrary` at `0x180048d1e`
- `KERNEL32!FreeLibrary` at `0x180048d1e`

## string_xrefs

- `0x180048cfc`: `Ntdll.dll`

## pseudocode

```c
FARPROC __fastcall _WinSqmGetProc(LPCSTR lpProcName)
{
  __int64 v1; // rbx
  HMODULE LibraryW; // rax

  v1 = 0;
  if ( dword_180061C84 )
  {
    if ( qword_1800627D0 )
      return GetProcAddress(qword_1800627D0, lpProcName);
    LibraryW = LoadLibraryW(L"Ntdll.dll");
    if ( LibraryW )
    {
      if ( _InterlockedCompareExchange64((volatile signed __int64 *)&qword_1800627D0, (signed __int64)LibraryW, 0) )
        FreeLibrary(LibraryW);
      return GetProcAddress(qword_1800627D0, lpProcName);
    }
  }
  return (FARPROC)v1;
}

```

## disassembly

```asm
0x180048cdc  mov     [rsp+arg_0], rbx
0x180048ce1  push    rdi
0x180048ce2  sub     rsp, 20h
0x180048ce6  xor     ebx, ebx
0x180048ce8  mov     rdi, rcx
0x180048ceb  cmp     cs:dword_180061C84, ebx
0x180048cf1  jz      short loc_180048D37
0x180048cf3  cmp     cs:qword_1800627D0, rbx
0x180048cfa  jnz     short loc_180048D24
0x180048cfc  lea     rcx, aNtdllDll_0; "Ntdll.dll"
0x180048d03  call    cs:__imp_LoadLibraryW
0x180048d09  mov     rcx, rax; hLibModule
0x180048d0c  test    rax, rax
0x180048d0f  jz      short loc_180048D37
0x180048d11  xor     eax, eax
0x180048d13  lock cmpxchg cs:qword_1800627D0, rcx
0x180048d1c  jz      short loc_180048D24
0x180048d1e  call    cs:__imp_FreeLibrary
0x180048d24  mov     rcx, cs:qword_1800627D0; hModule
0x180048d2b  mov     rdx, rdi; lpProcName
0x180048d2e  call    cs:__imp_GetProcAddress
0x180048d34  mov     rbx, rax
0x180048d37  mov     rax, rbx
0x180048d3a  mov     rbx, [rsp+28h+arg_0]
0x180048d3f  add     rsp, 20h
0x180048d43  pop     rdi
0x180048d44  retn
```
