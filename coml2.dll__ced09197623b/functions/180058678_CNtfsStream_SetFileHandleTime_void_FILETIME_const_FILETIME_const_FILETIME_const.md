# CNtfsStream::SetFileHandleTime(void *,_FILETIME const *,_FILETIME const *,_FILETIME const *)

- ea: `0x180058678`
- end: `0x1800586ab`
- name: `?SetFileHandleTime@CNtfsStream@@CAJPEAXPEBU_FILETIME@@11@Z`
- size: `51`
- prototype: `__int64 __fastcall(void *, const struct _FILETIME *, const struct _FILETIME *, const struct _FILETIME *)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x1800548e0`

## callees

- `0x180026bc4`
- `0x180058678`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180058694`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180058694`
- `api-ms-win-core-file-l1-1-0!SetFileTime` at `0x18005868a`
- `api-ms-win-core-file-l1-1-0!SetFileTime` at `0x18005868a`

## pseudocode

```c
__int64 __fastcall CNtfsStream::SetFileHandleTime(
        void *a1,
        const struct _FILETIME *a2,
        const struct _FILETIME *a3,
        const struct _FILETIME *a4)
{
  unsigned int v5; // ebx
  DWORD LastError; // eax

  if ( a1 == (void *)-1LL )
    return 0;
  v5 = 0;
  if ( !SetFileTime(a1, a2, a3, a4) )
  {
    LastError = GetLastError();
    return (unsigned int)Win32ErrorToScode(LastError);
  }
  return v5;
}

```

## disassembly

```asm
0x180058678  push    rbx
0x18005867a  sub     rsp, 20h
0x18005867e  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180058682  jnz     short loc_180058688
0x180058684  xor     eax, eax
0x180058686  jmp     short loc_1800586A5
0x180058688  xor     ebx, ebx
0x18005868a  call    cs:__imp_SetFileTime
0x180058690  test    eax, eax
0x180058692  jnz     short loc_1800586A3
0x180058694  call    cs:__imp_GetLastError
0x18005869a  mov     ecx, eax; unsigned int
0x18005869c  call    ?Win32ErrorToScode@@YAJK@Z; Win32ErrorToScode(ulong)
0x1800586a1  mov     ebx, eax
0x1800586a3  mov     eax, ebx
0x1800586a5  add     rsp, 20h
0x1800586a9  pop     rbx
0x1800586aa  retn
```
