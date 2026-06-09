# _WinSqmGetProc(char const *)

- ea: `0x180078944`
- end: `0x1800789ad`
- name: `?_WinSqmGetProc@@YAP6A_JXZPEBD@Z`
- size: `105`
- prototype: `__int64 (*__fastcall(LPCSTR lpProcName))(void)`
- caller_count: `4`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800786c0`
- `0x180078724`
- `0x180078784`
- `0x1800787f4`

## callees

- `0x180078944`

## import_xrefs

- `KERNEL32!LoadLibraryW` at `0x18007896b`
- `KERNEL32!LoadLibraryW` at `0x18007896b`
- `KERNEL32!FreeLibrary` at `0x180078986`
- `KERNEL32!FreeLibrary` at `0x180078986`
- `KERNEL32!GetProcAddress` at `0x180078996`
- `KERNEL32!GetProcAddress` at `0x180078996`

## string_xrefs

- `0x180078964`: `Ntdll.dll`

## pseudocode

```c
FARPROC __fastcall _WinSqmGetProc(LPCSTR lpProcName)
{
  __int64 v1; // rbx
  HMODULE LibraryW; // rax

  v1 = 0;
  if ( dword_1800B55A4 )
  {
    if ( qword_1800B6148 )
      return GetProcAddress(qword_1800B6148, lpProcName);
    LibraryW = LoadLibraryW(L"Ntdll.dll");
    if ( LibraryW )
    {
      if ( _InterlockedCompareExchange64((volatile signed __int64 *)&qword_1800B6148, (signed __int64)LibraryW, 0) )
        FreeLibrary(LibraryW);
      return GetProcAddress(qword_1800B6148, lpProcName);
    }
  }
  return (FARPROC)v1;
}

```

## disassembly

```asm
0x180078944  mov     [rsp+arg_0], rbx
0x180078949  push    rdi
0x18007894a  sub     rsp, 20h
0x18007894e  xor     ebx, ebx
0x180078950  mov     rdi, rcx
0x180078953  cmp     cs:dword_1800B55A4, ebx
0x180078959  jz      short loc_18007899F
0x18007895b  cmp     cs:qword_1800B6148, rbx
0x180078962  jnz     short loc_18007898C
0x180078964  lea     rcx, aNtdllDll_0; "Ntdll.dll"
0x18007896b  call    cs:__imp_LoadLibraryW
0x180078971  mov     rcx, rax; hLibModule
0x180078974  test    rax, rax
0x180078977  jz      short loc_18007899F
0x180078979  xor     eax, eax
0x18007897b  lock cmpxchg cs:qword_1800B6148, rcx
0x180078984  jz      short loc_18007898C
0x180078986  call    cs:__imp_FreeLibrary
0x18007898c  mov     rcx, cs:qword_1800B6148; hModule
0x180078993  mov     rdx, rdi; lpProcName
0x180078996  call    cs:__imp_GetProcAddress
0x18007899c  mov     rbx, rax
0x18007899f  mov     rax, rbx
0x1800789a2  mov     rbx, [rsp+28h+arg_0]
0x1800789a7  add     rsp, 20h
0x1800789ab  pop     rdi
0x1800789ac  retn
```
