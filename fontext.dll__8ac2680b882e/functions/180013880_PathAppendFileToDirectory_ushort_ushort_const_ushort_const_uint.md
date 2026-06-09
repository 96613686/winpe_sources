# PathAppendFileToDirectory(ushort *,ushort const *,ushort const *,uint)

- ea: `0x180013880`
- end: `0x1800138c0`
- name: `?PathAppendFileToDirectory@@YAJPEAGPEBG1I@Z`
- size: `64`
- prototype: `__int64 __fastcall(LPWSTR pszDest, LPCWSTR pszDir, LPCWSTR pszPath, unsigned int)`
- caller_count: `2`
- callee_count: `1`
- tags: `reparse_path, broker_com_uri`

## callers

- `0x1800085ac`
- `0x1800138c8`

## callees

- `0x180013880`

## import_xrefs

- `SHLWAPI!PathFindFileNameW` at `0x18001389e`
- `SHLWAPI!PathFindFileNameW` at `0x18001389e`
- `SHLWAPI!PathCombineW` at `0x1800138ad`
- `SHLWAPI!PathCombineW` at `0x1800138ad`

## pseudocode

```c
__int64 __fastcall PathAppendFileToDirectory(LPWSTR pszDest, LPCWSTR pszDir, LPCWSTR pszPath)
{
  const WCHAR *FileNameW; // rax

  *pszDest = 0;
  if ( *pszPath )
  {
    FileNameW = PathFindFileNameW(pszPath);
    PathCombineW(pszDest, pszDir, FileNameW);
  }
  return 0;
}

```

## disassembly

```asm
0x180013880  mov     [rsp+arg_0], rbx
0x180013885  push    rdi
0x180013886  sub     rsp, 20h
0x18001388a  xor     eax, eax
0x18001388c  mov     rdi, rdx
0x18001388f  mov     [rcx], ax
0x180013892  mov     rbx, rcx
0x180013895  cmp     ax, [r8]
0x180013899  jz      short loc_1800138B3
0x18001389b  mov     rcx, r8; pszPath
0x18001389e  call    cs:__imp_PathFindFileNameW
0x1800138a4  mov     rdx, rdi; pszDir
0x1800138a7  mov     rcx, rbx; pszDest
0x1800138aa  mov     r8, rax; pszFile
0x1800138ad  call    cs:__imp_PathCombineW
0x1800138b3  mov     rbx, [rsp+28h+arg_0]
0x1800138b8  xor     eax, eax
0x1800138ba  add     rsp, 20h
0x1800138be  pop     rdi
0x1800138bf  retn
```
