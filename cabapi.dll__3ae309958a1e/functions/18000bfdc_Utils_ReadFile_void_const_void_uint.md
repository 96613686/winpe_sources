# Utils::ReadFile(void * const,void *,uint)

- ea: `0x18000bfdc`
- end: `0x18000c02a`
- name: `?ReadFile@Utils@@SAIQEAXPEAXI@Z`
- size: `78`
- prototype: `__int64 __fastcall(void *const, void *, DWORD)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x18000d060`
- `0x18000d470`

## callees

- `0x180001540`
- `0x18000bfdc`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18000c005`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18000c005`

## pseudocode

```c
__int64 __fastcall Utils::ReadFile(void *const a1, void *a2, DWORD a3)
{
  DWORD NumberOfBytesRead; // [rsp+30h] [rbp-18h] BYREF

  NumberOfBytesRead = 0;
  if ( ReadFile(a1, a2, a3, &NumberOfBytesRead, 0) )
    return NumberOfBytesRead;
  else
    return 0xFFFFFFFFLL;
}

```

## disassembly

```asm
0x18000bfdc  sub     rsp, 48h
0x18000bfe0  mov     rax, cs:__security_cookie
0x18000bfe7  xor     rax, rsp
0x18000bfea  mov     [rsp+48h+var_10], rax
0x18000bfef  lea     r9, [rsp+48h+NumberOfBytesRead]; lpNumberOfBytesRead
0x18000bff4  mov     [rsp+48h+NumberOfBytesRead], 0
0x18000bffc  mov     [rsp+48h+lpOverlapped], 0; lpOverlapped
0x18000c005  call    cs:__imp_ReadFile
0x18000c00b  test    eax, eax
0x18000c00d  jnz     short loc_18000C014
0x18000c00f  or      eax, 0FFFFFFFFh
0x18000c012  jmp     short loc_18000C018
0x18000c014  mov     eax, [rsp+48h+NumberOfBytesRead]
0x18000c018  mov     rcx, [rsp+48h+var_10]
0x18000c01d  xor     rcx, rsp; StackCookie
0x18000c020  call    __security_check_cookie
0x18000c025  add     rsp, 48h
0x18000c029  retn
```
