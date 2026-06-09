# IsolationAwareLoadLibraryExW

- ea: `0x18000e128`
- end: `0x18000e1e0`
- name: `IsolationAwareLoadLibraryExW`
- size: `184`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000c924`
- `0x18000ccb0`

## callees

- `0x18000e128`
- `0x18000e1e8`

## import_xrefs

- `KERNEL32!LoadLibraryExW` at `0x18000e18c`
- `KERNEL32!LoadLibraryExW` at `0x18000e18c`
- `KERNEL32!DeactivateActCtx` at `0x18000e1c9`
- `KERNEL32!DeactivateActCtx` at `0x18002c71c`
- `KERNEL32!DeactivateActCtx` at `0x18000e1c9`
- `KERNEL32!DeactivateActCtx` at `0x18002c71c`
- `KERNEL32!SetLastError` at `0x18000e1d5`
- `KERNEL32!SetLastError` at `0x18002c728`
- `KERNEL32!SetLastError` at `0x18000e1d5`
- `KERNEL32!SetLastError` at `0x18002c728`
- `KERNEL32!GetLastError` at `0x18000e1b4`
- `KERNEL32!GetLastError` at `0x18002c708`
- `KERNEL32!GetLastError` at `0x18000e1b4`
- `KERNEL32!GetLastError` at `0x18002c708`

## string_xrefs

- `0x18000e185`: `fvecpl.dll`

## pseudocode

```c
HMODULE IsolationAwareLoadLibraryExW()
{
  HMODULE Library; // rax
  HMODULE v2; // rbx
  int v3; // esi
  DWORD LastError; // edi
  ULONG_PTR ulCookie; // [rsp+48h] [rbp+10h] BYREF

  ulCookie = 0;
  if ( !IsolationAwarePrivateT_SAbnPgpgk
    && !IsolationAwarePrivateT_SqbjaYRiRY
    && !(unsigned int)IsolationAwarePrivatenPgViNgRzlnPgpgk(&ulCookie) )
  {
    return 0;
  }
  Library = LoadLibraryExW(L"fvecpl.dll", 0, 0x822u);
  v2 = Library;
  if ( !IsolationAwarePrivateT_SAbnPgpgk || !IsolationAwarePrivateT_SqbjaYRiRY )
  {
    if ( Library )
    {
      v3 = 0;
      LastError = 0;
    }
    else
    {
      v3 = 1;
      LastError = GetLastError();
    }
    DeactivateActCtx(0, ulCookie);
    if ( v3 )
      SetLastError(LastError);
  }
  return v2;
}

```

## disassembly

```asm
0x18000e128  mov     rax, rsp
0x18000e12b  mov     [rax+8], rbx
0x18000e12f  mov     [rax+18h], rsi
0x18000e133  mov     [rax+10h], rdx
0x18000e137  push    rdi
0x18000e138  sub     rsp, 30h
0x18000e13c  mov     qword ptr [rax-18h], 0
0x18000e144  mov     qword ptr [rax+10h], 0
0x18000e14c  cmp     cs:IsolationAwarePrivateT_SAbnPgpgk, 0
0x18000e153  jnz     short loc_18000E17D
0x18000e155  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, 0
0x18000e15c  jnz     short loc_18000E17D
0x18000e15e  lea     rcx, [rax+10h]; lpCookie
0x18000e162  call    IsolationAwarePrivatenPgViNgRzlnPgpgk
0x18000e167  test    eax, eax
0x18000e169  jnz     short loc_18000E17D
0x18000e16b  xor     eax, eax
0x18000e16d  mov     rbx, [rsp+38h+arg_0]
0x18000e172  mov     rsi, [rsp+38h+arg_10]
0x18000e177  add     rsp, 30h
0x18000e17b  pop     rdi
0x18000e17c  retn
0x18000e17d  xor     edx, edx; hFile
0x18000e17f  mov     r8d, 822h; dwFlags
0x18000e185  lea     rcx, LibFileName; "fvecpl.dll"
0x18000e18c  call    cs:__imp_LoadLibraryExW
0x18000e192  mov     rbx, rax
0x18000e195  mov     [rsp+38h+var_18], rax
0x18000e19a  cmp     cs:IsolationAwarePrivateT_SAbnPgpgk, 0
0x18000e1a1  jz      short loc_18000E1AC
0x18000e1a3  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, 0
0x18000e1aa  jnz     short loc_18000E1DB
0x18000e1ac  test    rbx, rbx
0x18000e1af  jnz     short loc_18000E1BE
0x18000e1b1  lea     esi, [rbx+1]
0x18000e1b4  call    cs:__imp_GetLastError
0x18000e1ba  mov     edi, eax
0x18000e1bc  jmp     short loc_18000E1C2
0x18000e1be  xor     esi, esi
0x18000e1c0  xor     edi, edi
0x18000e1c2  mov     rdx, [rsp+38h+ulCookie]; ulCookie
0x18000e1c7  xor     ecx, ecx; dwFlags
0x18000e1c9  call    cs:__imp_DeactivateActCtx
0x18000e1cf  test    esi, esi
0x18000e1d1  jz      short loc_18000E1DB
0x18000e1d3  mov     ecx, edi; dwErrCode
0x18000e1d5  call    cs:__imp_SetLastError
0x18000e1db  mov     rax, rbx
0x18000e1de  jmp     short loc_18000E16D
0x18002c6df  push    rbx
0x18002c6e1  push    rbp
0x18002c6e2  push    rdi
0x18002c6e3  sub     rsp, 20h
0x18002c6e7  mov     rbp, rdx
0x18002c6ea  cmp     cs:IsolationAwarePrivateT_SAbnPgpgk, 0
0x18002c6f1  jz      short loc_18002C6FC
0x18002c6f3  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, 0
0x18002c6fa  jnz     short loc_18002C72F
0x18002c6fc  cmp     qword ptr [rbp+20h], 0
0x18002c701  jnz     short loc_18002C712
0x18002c703  mov     edi, 1
0x18002c708  call    cs:__imp_GetLastError
0x18002c70e  mov     ebx, eax
0x18002c710  jmp     short loc_18002C716
0x18002c712  xor     edi, edi
0x18002c714  xor     ebx, ebx
0x18002c716  mov     rdx, [rbp+48h]; ulCookie
0x18002c71a  xor     ecx, ecx; dwFlags
0x18002c71c  call    cs:__imp_DeactivateActCtx
0x18002c722  test    edi, edi
0x18002c724  jz      short loc_18002C72F
0x18002c726  mov     ecx, ebx; dwErrCode
0x18002c728  call    cs:__imp_SetLastError
0x18002c72e  nop
0x18002c72f  add     rsp, 20h
0x18002c733  pop     rdi
0x18002c734  pop     rbp
0x18002c735  pop     rbx
0x18002c736  retn
```
