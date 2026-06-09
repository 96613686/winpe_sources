# MemMapReadOnly::Initialize(void *,uint)

- ea: `0x180089ba0`
- end: `0x180089c02`
- name: `?Initialize@MemMapReadOnly@@AEAAXPEAXI@Z`
- size: `98`
- prototype: `void(MemMapReadOnly *__hidden this, void *, unsigned int)`
- caller_count: `1`
- callee_count: `0`
- tags: `file_ops`

## callers

- `0x180040ea0`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x180089bca`
- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x180089bca`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x180089bed`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x180089bed`

## pseudocode

```c
void __fastcall MemMapReadOnly::Initialize(union _LARGE_INTEGER *this, void *a2, unsigned int a3)
{
  if ( a3 < *(&pdb_internal::cbSysPage + 1) )
    a3 = *(&pdb_internal::cbSysPage + 1);
  this[1].LowPart = a3;
  GetFileSizeEx(a2, this + 4);
  this[2].QuadPart = (LONGLONG)a2;
  this[3].QuadPart = (LONGLONG)CreateFileMappingW(a2, 0, 2u, 0, 0, 0);
}

```

## disassembly

```asm
0x180089ba0  mov     [rsp+arg_0], rbx
0x180089ba5  push    rdi
0x180089ba6  sub     rsp, 30h
0x180089baa  cmp     r8d, dword ptr cs:?cbSysPage@pdb_internal@@3VSysPage@1@A+4; pdb_internal::SysPage pdb_internal::cbSysPage
0x180089bb1  mov     rbx, rdx
0x180089bb4  mov     rdi, rcx
0x180089bb7  lea     rdx, [rcx+20h]; lpFileSize
0x180089bbb  cmovb   r8d, dword ptr cs:?cbSysPage@pdb_internal@@3VSysPage@1@A+4; pdb_internal::SysPage pdb_internal::cbSysPage
0x180089bc3  mov     [rcx+8], r8d
0x180089bc7  mov     rcx, rbx; hFile
0x180089bca  call    cs:__imp_GetFileSizeEx
0x180089bd0  xor     eax, eax
0x180089bd2  mov     [rdi+10h], rbx
0x180089bd6  mov     [rsp+38h+lpName], rax; lpName
0x180089bdb  xor     r9d, r9d; dwMaximumSizeHigh
0x180089bde  xor     edx, edx; lpFileMappingAttributes
0x180089be0  mov     [rsp+38h+dwMaximumSizeLow], eax; dwMaximumSizeLow
0x180089be4  mov     r8d, 2; flProtect
0x180089bea  mov     rcx, rbx; hFile
0x180089bed  call    cs:__imp_CreateFileMappingW
0x180089bf3  mov     rbx, [rsp+38h+arg_0]
0x180089bf8  mov     [rdi+18h], rax
0x180089bfc  add     rsp, 30h
0x180089c00  pop     rdi
0x180089c01  retn
```
