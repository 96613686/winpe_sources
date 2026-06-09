# Windows::Isolation::Implementation::Rtl::DeleteFileDirect(Windows::Isolation::Implementation::Rtl::CWin32FullPath const &,ulong &)

- ea: `0x180020088`
- end: `0x180020114`
- name: `?DeleteFileDirect@Rtl@Implementation@Isolation@Windows@@YAHAEBVCWin32FullPath@1234@AEAK@Z`
- size: `140`
- prototype: `__int64 __fastcall(Windows::Isolation::Implementation::Rtl *__hidden this, const struct Windows::Isolation::Implementation::Rtl::CWin32FullPath *, unsigned int *)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x18001ffb4`

## callees

- `0x1800069e5`
- `0x180020088`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800200f4`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800200f4`
- `api-ms-win-core-file-l1-1-0!DeleteFileA` at `0x1800200c9`
- `api-ms-win-core-file-l1-1-0!DeleteFileA` at `0x1800200c9`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800200bc`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800200e7`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800200bc`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800200e7`

## pseudocode

```c
__int64 __fastcall Windows::Isolation::Implementation::Rtl::DeleteFileDirect(
        Windows::Isolation::Implementation::Rtl *this,
        const struct Windows::Isolation::Implementation::Rtl::CWin32FullPath *a2,
        unsigned int *a3)
{
  char *v3; // rbx
  int v4; // eax
  BOOL v6; // eax
  unsigned int v7; // ebx

  *(_DWORD *)a2 = 0;
  v3 = (char *)this + 48;
  v4 = *((_DWORD *)this + 14);
  if ( v4 == 1 )
  {
    if ( !*(_QWORD *)v3 )
      RaiseException(0xC00000E5, 1u, 0, 0);
    v6 = DeleteFileA(*(LPCSTR *)(*(_QWORD *)v3 + 16LL));
  }
  else
  {
    if ( v4 != 2 || !*(_QWORD *)v3 )
      RaiseException(0xC00000E5, 1u, 0, 0);
    v6 = DeleteFileW(*(LPCWSTR *)(*(_QWORD *)v3 + 16LL));
  }
  v7 = v6;
  if ( !v6 )
    *(_DWORD *)a2 = GetLastError_0();
  return v7;
}

```

## disassembly

```asm
0x180020088  mov     [rsp+arg_0], rbx
0x18002008d  push    rdi
0x18002008e  sub     rsp, 20h
0x180020092  mov     dword ptr [rdx], 0
0x180020098  lea     rbx, [rcx+30h]
0x18002009c  mov     eax, [rcx+38h]
0x18002009f  mov     rdi, rdx
0x1800200a2  mov     edx, 1; dwExceptionFlags
0x1800200a7  cmp     eax, edx
0x1800200a9  jnz     short loc_1800200D1
0x1800200ab  cmp     qword ptr [rbx], 0
0x1800200af  jnz     short loc_1800200C2
0x1800200b1  xor     r9d, r9d; lpArguments
0x1800200b4  xor     r8d, r8d; nNumberOfArguments
0x1800200b7  mov     ecx, 0C00000E5h; dwExceptionCode
0x1800200bc  call    cs:__imp_RaiseException
0x1800200c2  mov     rcx, [rbx]
0x1800200c5  mov     rcx, [rcx+10h]; lpFileName
0x1800200c9  call    cs:__imp_DeleteFileA
0x1800200cf  jmp     short loc_1800200FA
0x1800200d1  cmp     eax, 2
0x1800200d4  jnz     short loc_1800200DC
0x1800200d6  cmp     qword ptr [rbx], 0
0x1800200da  jnz     short loc_1800200ED
0x1800200dc  xor     r9d, r9d; lpArguments
0x1800200df  xor     r8d, r8d; nNumberOfArguments
0x1800200e2  mov     ecx, 0C00000E5h; dwExceptionCode
0x1800200e7  call    cs:__imp_RaiseException
0x1800200ed  mov     rcx, [rbx]
0x1800200f0  mov     rcx, [rcx+10h]; lpFileName
0x1800200f4  call    cs:__imp_DeleteFileW
0x1800200fa  mov     ebx, eax
0x1800200fc  test    eax, eax
0x1800200fe  jnz     short loc_180020107
0x180020100  call    GetLastError_0
0x180020105  mov     [rdi], eax
0x180020107  mov     eax, ebx
0x180020109  mov     rbx, [rsp+28h+arg_0]
0x18002010e  add     rsp, 20h
0x180020112  pop     rdi
0x180020113  retn
```
