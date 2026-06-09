# Utils::WriteFile(void * const,void const *,uint)

- ea: `0x18000c48c`
- end: `0x18000c4da`
- name: `?WriteFile@Utils@@SAIQEAXPEBXI@Z`
- size: `78`
- prototype: `__int64 __fastcall(void *const, const void *, DWORD)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x18000d0b0`
- `0x18000d520`

## callees

- `0x180001540`
- `0x18000c48c`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18000c4b5`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18000c4b5`

## pseudocode

```c
__int64 __fastcall Utils::WriteFile(void *const a1, const void *a2, DWORD a3)
{
  DWORD NumberOfBytesWritten; // [rsp+30h] [rbp-18h] BYREF

  NumberOfBytesWritten = 0;
  if ( WriteFile(a1, a2, a3, &NumberOfBytesWritten, 0) )
    return NumberOfBytesWritten;
  else
    return 0xFFFFFFFFLL;
}

```

## disassembly

```asm
0x18000c48c  sub     rsp, 48h
0x18000c490  mov     rax, cs:__security_cookie
0x18000c497  xor     rax, rsp
0x18000c49a  mov     [rsp+48h+var_10], rax
0x18000c49f  lea     r9, [rsp+48h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18000c4a4  mov     [rsp+48h+NumberOfBytesWritten], 0
0x18000c4ac  mov     [rsp+48h+lpOverlapped], 0; lpOverlapped
0x18000c4b5  call    cs:__imp_WriteFile
0x18000c4bb  test    eax, eax
0x18000c4bd  jnz     short loc_18000C4C4
0x18000c4bf  or      eax, 0FFFFFFFFh
0x18000c4c2  jmp     short loc_18000C4C8
0x18000c4c4  mov     eax, [rsp+48h+NumberOfBytesWritten]
0x18000c4c8  mov     rcx, [rsp+48h+var_10]
0x18000c4cd  xor     rcx, rsp; StackCookie
0x18000c4d0  call    __security_check_cookie
0x18000c4d5  add     rsp, 48h
0x18000c4d9  retn
```
