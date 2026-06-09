# LoadHelperDLL

- ea: `0x180008a30`
- end: `0x180008ab2`
- name: `LoadHelperDLL`
- size: `130`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800088fc`

## callees

- `0x180008958`
- `0x180008a30`

## import_xrefs

- `msvcrt!free` at `0x180008a6c`
- `msvcrt!free` at `0x180008a6c`
- `KERNEL32!GetLastError` at `0x180008a77`
- `KERNEL32!GetLastError` at `0x180008a77`
- `KERNEL32!FreeLibrary` at `0x180008a9f`
- `KERNEL32!FreeLibrary` at `0x180008a9f`
- `KERNEL32!LoadLibraryExW` at `0x180008a60`
- `KERNEL32!LoadLibraryExW` at `0x180008a60`

## pseudocode

```c
signed int LoadHelperDLL()
{
  const WCHAR *HelperDllFullPath; // rax
  WCHAR *v1; // rbx
  signed int result; // eax
  HMODULE Library; // rdi

  if ( g_hHelper )
    return 0;
  HelperDllFullPath = (const WCHAR *)GetHelperDllFullPath();
  v1 = (WCHAR *)HelperDllFullPath;
  if ( !HelperDllFullPath )
    return 1;
  Library = LoadLibraryExW(HelperDllFullPath, 0, 0);
  free(v1);
  if ( Library )
  {
    if ( _InterlockedCompareExchange64((volatile signed __int64 *)&g_hHelper, (signed __int64)Library, 0) )
      FreeLibrary(g_hHelper);
    return 0;
  }
  result = GetLastError();
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x180008a30  mov     [rsp+arg_0], rbx
0x180008a35  push    rdi
0x180008a36  sub     rsp, 20h
0x180008a3a  mov     rax, cs:g_hHelper
0x180008a41  test    rax, rax
0x180008a44  jnz     short loc_180008AA5
0x180008a46  call    GetHelperDllFullPath
0x180008a4b  mov     rbx, rax
0x180008a4e  test    rax, rax
0x180008a51  jnz     short loc_180008A58
0x180008a53  lea     eax, [rbx+1]
0x180008a56  jmp     short loc_180008AA7
0x180008a58  xor     r8d, r8d; dwFlags
0x180008a5b  xor     edx, edx; hFile
0x180008a5d  mov     rcx, rbx; lpLibFileName
0x180008a60  call    cs:__imp_LoadLibraryExW
0x180008a66  mov     rcx, rbx; Block
0x180008a69  mov     rdi, rax
0x180008a6c  call    cs:__imp_free
0x180008a72  test    rdi, rdi
0x180008a75  jnz     short loc_180008A8B
0x180008a77  call    cs:__imp_GetLastError
0x180008a7d  test    eax, eax
0x180008a7f  jle     short loc_180008AA7
0x180008a81  movzx   eax, ax
0x180008a84  or      eax, 80070000h
0x180008a89  jmp     short loc_180008AA7
0x180008a8b  xor     eax, eax
0x180008a8d  lock cmpxchg cs:g_hHelper, rdi
0x180008a96  jz      short loc_180008AA5
0x180008a98  mov     rcx, cs:g_hHelper; hLibModule
0x180008a9f  call    cs:__imp_FreeLibrary
0x180008aa5  xor     eax, eax
0x180008aa7  mov     rbx, [rsp+28h+arg_0]
0x180008aac  add     rsp, 20h
0x180008ab0  pop     rdi
0x180008ab1  retn
```
