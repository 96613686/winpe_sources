# Windows::Isolation::Implementation::Rtl::RemoveDirectory(Windows::Isolation::Implementation::Rtl::CWin32FullPath const &)

- ea: `0x1800208c0`
- end: `0x18002094e`
- name: `?RemoveDirectory@Rtl@Implementation@Isolation@Windows@@YA?AU_WIN32_FUNCTION_RETURN_STATUS@@AEBVCWin32FullPath@1234@@Z`
- size: `142`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x18001f6fc`
- `0x180021a80`

## callees

- `0x1800069e5`
- `0x1800208c0`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!RemoveDirectoryA` at `0x180020901`
- `api-ms-win-core-file-l1-1-0!RemoveDirectoryA` at `0x180020901`
- `api-ms-win-core-file-l1-1-0!RemoveDirectoryW` at `0x18002092c`
- `api-ms-win-core-file-l1-1-0!RemoveDirectoryW` at `0x18002092c`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800208f4`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18002091f`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800208f4`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18002091f`

## pseudocode

```c
__int64 __fastcall Windows::Isolation::Implementation::Rtl::RemoveDirectory(__int64 a1, __int64 a2)
{
  __int64 v2; // rbx
  int v3; // eax
  BOOL v5; // eax

  v2 = a2 + 48;
  *(_OWORD *)a1 = 0;
  v3 = *(_DWORD *)(a2 + 56);
  if ( v3 == 1 )
  {
    if ( !*(_QWORD *)v2 )
      RaiseException(0xC00000E5, 1u, 0, 0);
    v5 = RemoveDirectoryA(*(LPCSTR *)(*(_QWORD *)v2 + 16LL));
  }
  else
  {
    if ( v3 != 2 || !*(_QWORD *)v2 )
      RaiseException(0xC00000E5, 1u, 0, 0);
    v5 = RemoveDirectoryW(*(LPCWSTR *)(*(_QWORD *)v2 + 16LL));
  }
  *(_DWORD *)(a1 + 8) = v5;
  if ( !v5 )
    *(_DWORD *)a1 = GetLastError_0();
  return a1;
}

```

## disassembly

```asm
0x1800208c0  mov     [rsp+arg_0], rbx
0x1800208c5  push    rdi
0x1800208c6  sub     rsp, 20h
0x1800208ca  xorps   xmm0, xmm0
0x1800208cd  lea     rbx, [rdx+30h]
0x1800208d1  movups  xmmword ptr [rcx], xmm0
0x1800208d4  mov     eax, [rdx+38h]
0x1800208d7  mov     rdi, rcx
0x1800208da  mov     edx, 1; dwExceptionFlags
0x1800208df  cmp     eax, edx
0x1800208e1  jnz     short loc_180020909
0x1800208e3  cmp     qword ptr [rbx], 0
0x1800208e7  jnz     short loc_1800208FA
0x1800208e9  xor     r9d, r9d; lpArguments
0x1800208ec  xor     r8d, r8d; nNumberOfArguments
0x1800208ef  mov     ecx, 0C00000E5h; dwExceptionCode
0x1800208f4  call    cs:__imp_RaiseException
0x1800208fa  mov     rcx, [rbx]
0x1800208fd  mov     rcx, [rcx+10h]; lpPathName
0x180020901  call    cs:__imp_RemoveDirectoryA
0x180020907  jmp     short loc_180020932
0x180020909  cmp     eax, 2
0x18002090c  jnz     short loc_180020914
0x18002090e  cmp     qword ptr [rbx], 0
0x180020912  jnz     short loc_180020925
0x180020914  xor     r9d, r9d; lpArguments
0x180020917  xor     r8d, r8d; nNumberOfArguments
0x18002091a  mov     ecx, 0C00000E5h; dwExceptionCode
0x18002091f  call    cs:__imp_RaiseException
0x180020925  mov     rcx, [rbx]
0x180020928  mov     rcx, [rcx+10h]; lpPathName
0x18002092c  call    cs:__imp_RemoveDirectoryW
0x180020932  mov     [rdi+8], eax
0x180020935  test    eax, eax
0x180020937  jnz     short loc_180020940
0x180020939  call    GetLastError_0
0x18002093e  mov     [rdi], eax
0x180020940  mov     rbx, [rsp+28h+arg_0]
0x180020945  mov     rax, rdi
0x180020948  add     rsp, 20h
0x18002094c  pop     rdi
0x18002094d  retn
```
