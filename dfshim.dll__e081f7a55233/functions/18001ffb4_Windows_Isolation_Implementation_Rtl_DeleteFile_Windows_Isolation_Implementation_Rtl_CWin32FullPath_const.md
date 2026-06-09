# Windows::Isolation::Implementation::Rtl::DeleteFile(Windows::Isolation::Implementation::Rtl::CWin32FullPath const &)

- ea: `0x18001ffb4`
- end: `0x180020082`
- name: `?DeleteFile@Rtl@Implementation@Isolation@Windows@@YA?AU_WIN32_FUNCTION_RETURN_STATUS@@AEBVCWin32FullPath@1234@@Z`
- size: `206`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x18001f6fc`
- `0x180021a80`

## callees

- `0x1800069e5`
- `0x18001ffb4`
- `0x180020088`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!SetFileAttributesA` at `0x18002001b`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesA` at `0x18002001b`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x180020050`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x180020050`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180020008`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18002003e`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180020008`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18002003e`

## pseudocode

```c
const struct Windows::Isolation::Implementation::Rtl::CWin32FullPath *__fastcall Windows::Isolation::Implementation::Rtl::DeleteFile(
        const struct Windows::Isolation::Implementation::Rtl::CWin32FullPath *a1,
        __int64 a2,
        unsigned int *a3)
{
  int v5; // eax
  BOOL v6; // eax
  unsigned int *v7; // r8
  __int64 v8; // rsi

  *(_OWORD *)a1 = 0;
  v5 = Windows::Isolation::Implementation::Rtl::DeleteFileDirect((Windows::Isolation::Implementation::Rtl *)a2, a1, a3);
  *((_DWORD *)a1 + 2) = v5;
  if ( !v5 && *(_DWORD *)a1 == 5 )
  {
    if ( *(_DWORD *)(a2 + 56) == 1 )
    {
      if ( !*(_QWORD *)(a2 + 48) )
        RaiseException(0xC00000E5, 1u, 0, 0);
      v6 = SetFileAttributesA(*(LPCSTR *)(*(_QWORD *)(a2 + 48) + 16LL), 0x80u);
    }
    else
    {
      v8 = a2 + 48;
      if ( *(_DWORD *)(a2 + 56) != 2 || !*(_QWORD *)v8 )
        RaiseException(0xC00000E5, 1u, 0, 0);
      v6 = SetFileAttributesW(*(LPCWSTR *)(*(_QWORD *)v8 + 16LL), 0x80u);
    }
    if ( v6 )
      *((_DWORD *)a1 + 2) = Windows::Isolation::Implementation::Rtl::DeleteFileDirect(
                              (Windows::Isolation::Implementation::Rtl *)a2,
                              a1,
                              v7);
    else
      GetLastError_0();
  }
  return a1;
}

```

## disassembly

```asm
0x18001ffb4  mov     [rsp+arg_0], rbx
0x18001ffb9  mov     [rsp+arg_8], rsi
0x18001ffbe  push    rdi
0x18001ffbf  sub     rsp, 20h
0x18001ffc3  mov     rbx, rdx
0x18001ffc6  xorps   xmm0, xmm0
0x18001ffc9  movups  xmmword ptr [rcx], xmm0
0x18001ffcc  mov     rdi, rcx
0x18001ffcf  mov     rdx, rcx; struct Windows::Isolation::Implementation::Rtl::CWin32FullPath *
0x18001ffd2  mov     rcx, rbx; this
0x18001ffd5  call    ?DeleteFileDirect@Rtl@Implementation@Isolation@Windows@@YAHAEBVCWin32FullPath@1234@AEAK@Z; Windows::Isolation::Implementation::Rtl::DeleteFileDirect(Windows::Isolation::Implementation::Rtl::CWin32FullPath const &,ulong &)
0x18001ffda  mov     [rdi+8], eax
0x18001ffdd  test    eax, eax
0x18001ffdf  jnz     loc_18002006F
0x18001ffe5  cmp     dword ptr [rdi], 5
0x18001ffe8  jnz     loc_18002006F
0x18001ffee  lea     edx, [rax+1]; dwExceptionFlags
0x18001fff1  cmp     [rbx+38h], edx
0x18001fff4  jnz     short loc_180020023
0x18001fff6  cmp     qword ptr [rbx+30h], 0
0x18001fffb  jnz     short loc_18002000E
0x18001fffd  xor     r9d, r9d; lpArguments
0x180020000  xor     r8d, r8d; nNumberOfArguments
0x180020003  mov     ecx, 0C00000E5h; dwExceptionCode
0x180020008  call    cs:__imp_RaiseException
0x18002000e  mov     rcx, [rbx+30h]
0x180020012  mov     edx, 80h; dwFileAttributes
0x180020017  mov     rcx, [rcx+10h]; lpFileName
0x18002001b  call    cs:__imp_SetFileAttributesA
0x180020021  jmp     short loc_180020056
0x180020023  cmp     dword ptr [rbx+38h], 2
0x180020027  lea     rsi, [rbx+30h]
0x18002002b  jnz     short loc_180020033
0x18002002d  cmp     qword ptr [rsi], 0
0x180020031  jnz     short loc_180020044
0x180020033  xor     r9d, r9d; lpArguments
0x180020036  xor     r8d, r8d; nNumberOfArguments
0x180020039  mov     ecx, 0C00000E5h; dwExceptionCode
0x18002003e  call    cs:__imp_RaiseException
0x180020044  mov     rcx, [rsi]
0x180020047  mov     edx, 80h; dwFileAttributes
0x18002004c  mov     rcx, [rcx+10h]; lpFileName
0x180020050  call    cs:__imp_SetFileAttributesW
0x180020056  test    eax, eax
0x180020058  jnz     short loc_180020061
0x18002005a  call    GetLastError_0
0x18002005f  jmp     short loc_18002006F
0x180020061  mov     rdx, rdi; struct Windows::Isolation::Implementation::Rtl::CWin32FullPath *
0x180020064  mov     rcx, rbx; this
0x180020067  call    ?DeleteFileDirect@Rtl@Implementation@Isolation@Windows@@YAHAEBVCWin32FullPath@1234@AEAK@Z; Windows::Isolation::Implementation::Rtl::DeleteFileDirect(Windows::Isolation::Implementation::Rtl::CWin32FullPath const &,ulong &)
0x18002006c  mov     [rdi+8], eax
0x18002006f  mov     rbx, [rsp+28h+arg_0]
0x180020074  mov     rax, rdi
0x180020077  mov     rsi, [rsp+28h+arg_8]
0x18002007c  add     rsp, 20h
0x180020080  pop     rdi
0x180020081  retn
```
