# ODBCCreateFile

- ea: `0x180014814`
- end: `0x180014843`
- name: `ODBCCreateFile`
- size: `47`
- prototype: `HANDLE __fastcall(const WCHAR *, DWORD)`
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x18000e97c`

## callees

- `0x180014814`

## import_xrefs

- `KERNEL32!CreateFileW` at `0x18001483c`

## pseudocode

```c
HANDLE __fastcall ODBCCreateFile(const WCHAR *a1, DWORD a2)
{
  if ( a1 )
    return CreateFileW(a1, a2, 3u, 0, 4u, 0x80u, 0);
  else
    return 0;
}

```

## disassembly

```asm
0x180014814  test    rcx, rcx
0x180014817  jnz     short loc_18001481C
0x180014819  xor     eax, eax
0x18001481b  retn
0x18001481c  xor     r9d, r9d
0x18001481f  mov     [rsp+arg_30], 0
0x180014828  mov     [rsp+arg_28], 80h
0x180014830  mov     [rsp+arg_20], 4
0x180014838  lea     r8d, [r9+3]
0x18001483c  jmp     cs:__imp_CreateFileW
```
