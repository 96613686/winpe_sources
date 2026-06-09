# PathExtractFileName(ushort const *,ushort *,uint)

- ea: `0x180013920`
- end: `0x1800139c7`
- name: `?PathExtractFileName@@YAJPEBGPEAGI@Z`
- size: `167`
- prototype: `__int64 __fastcall(LPCWSTR pszPath, unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x1800087d0`

## callees

- `0x180006624`
- `0x180013920`
- `0x18003104a`
- `0x180031070`

## import_xrefs

- `SHLWAPI!PathFindFileNameW` at `0x18001395a`
- `SHLWAPI!PathFindFileNameW` at `0x18001395a`
- `SHLWAPI!PathRemoveExtensionW` at `0x180013979`
- `SHLWAPI!PathRemoveExtensionW` at `0x180013979`
- `KERNEL32!lstrlenW` at `0x180013984`
- `KERNEL32!lstrlenW` at `0x180013984`

## pseudocode

```c
__int64 __fastcall PathExtractFileName(LPCWSTR pszPath, unsigned __int16 *a2)
{
  const unsigned __int16 *FileNameW; // rax
  WCHAR pszPatha[264]; // [rsp+20h] [rbp-228h] BYREF

  memset_0(pszPatha, 0, 0x208u);
  FileNameW = PathFindFileNameW(pszPath);
  StringCchCopyW(pszPatha, 0x104u, FileNameW);
  PathRemoveExtensionW(pszPatha);
  if ( lstrlenW(pszPatha) >= 260 )
    return 2147942522LL;
  StringCchCopyW(a2, 0x104u, pszPatha);
  return 0;
}

```

## disassembly

```asm
0x180013920  mov     [rsp+arg_10], rbx
0x180013925  push    rdi
0x180013926  sub     rsp, 240h
0x18001392d  mov     rax, cs:__security_cookie
0x180013934  xor     rax, rsp
0x180013937  mov     [rsp+248h+var_18], rax
0x18001393f  mov     rdi, rdx
0x180013942  mov     rbx, rcx
0x180013945  xor     edx, edx; Val
0x180013947  lea     rcx, [rsp+248h+pszPath]; void *
0x18001394c  mov     r8d, 208h; Size
0x180013952  call    memset_0
0x180013957  mov     rcx, rbx; pszPath
0x18001395a  call    cs:__imp_PathFindFileNameW
0x180013960  mov     ebx, 104h
0x180013965  lea     rcx, [rsp+248h+pszPath]; unsigned __int16 *
0x18001396a  mov     r8, rax; unsigned __int16 *
0x18001396d  mov     edx, ebx; unsigned __int64
0x18001396f  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180013974  lea     rcx, [rsp+248h+pszPath]; pszPath
0x180013979  call    cs:__imp_PathRemoveExtensionW
0x18001397f  lea     rcx, [rsp+248h+pszPath]; lpString
0x180013984  call    cs:__imp_lstrlenW
0x18001398a  cmp     eax, ebx
0x18001398c  jge     short loc_1800139A1
0x18001398e  lea     r8, [rsp+248h+pszPath]; unsigned __int16 *
0x180013993  mov     edx, ebx; unsigned __int64
0x180013995  mov     rcx, rdi; unsigned __int16 *
0x180013998  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18001399d  xor     eax, eax
0x18001399f  jmp     short loc_1800139A6
0x1800139a1  mov     eax, 8007007Ah
0x1800139a6  mov     rcx, [rsp+248h+var_18]
0x1800139ae  xor     rcx, rsp; StackCookie
0x1800139b1  call    __security_check_cookie
0x1800139b6  mov     rbx, [rsp+248h+arg_10]
0x1800139be  add     rsp, 240h
0x1800139c5  pop     rdi
0x1800139c6  retn
```
