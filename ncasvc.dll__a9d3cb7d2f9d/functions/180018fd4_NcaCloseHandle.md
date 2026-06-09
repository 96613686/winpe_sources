# NcaCloseHandle

- ea: `0x180018fd4`
- end: `0x180018ff4`
- name: `NcaCloseHandle`
- size: `32`
- prototype: `int __fastcall(char *)`
- caller_count: `13`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x180004380`
- `0x180009f1c`
- `0x18000a398`
- `0x18000ae34`
- `0x18000db90`
- `0x180011bc0`
- `0x180011f80`
- `0x1800131ac`
- `0x1800175c8`
- `0x180017708`
- `0x18001a38c`
- `0x18001a564`
- `0x18001c8e0`

## callees

- `0x180018fd4`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180018fe2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180018fe2`

## pseudocode

```c
int __fastcall NcaCloseHandle(char *a1)
{
  int result; // eax

  result = (_DWORD)a1 - 1;
  if ( (unsigned __int64)(a1 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    return CloseHandle(a1);
  return result;
}

```

## disassembly

```asm
0x180018fd4  sub     rsp, 28h
0x180018fd8  lea     rax, [rcx-1]
0x180018fdc  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180018fe0  ja      short loc_180018FEE
0x180018fe2  call    cs:__imp_CloseHandle
0x180018fe9  nop     dword ptr [rax+rax+00h]
0x180018fee  add     rsp, 28h
0x180018ff2  retn
```
