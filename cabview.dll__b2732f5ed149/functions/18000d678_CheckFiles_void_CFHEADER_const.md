# CheckFiles(void *,CFHEADER const &)

- ea: `0x18000d678`
- end: `0x18000d71e`
- name: `?CheckFiles@@YAHPEAXAEBUCFHEADER@@@Z`
- size: `166`
- prototype: `__int64 __fastcall(HANDLE hFile, const struct CFHEADER *)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x18000f5cc`

## callees

- `0x180002620`
- `0x18000d678`
- `0x18000f500`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18000d6d9`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18000d6d9`

## pseudocode

```c
__int64 __fastcall CheckFiles(HANDLE hFile, const struct CFHEADER *a2)
{
  unsigned __int64 i; // rbx
  unsigned int v5; // r8d
  DWORD NumberOfBytesRead; // [rsp+30h] [rbp-28h] BYREF
  __int128 Buffer; // [rsp+38h] [rbp-20h] BYREF

  NumberOfBytesRead = 0;
  Buffer = 0;
  for ( i = 0; ; ++i )
  {
    v5 = 1;
    if ( i >= *((unsigned __int16 *)a2 + 14) )
      break;
    if ( !ReadFile(hFile, &Buffer, 0x10u, &NumberOfBytesRead, 0)
      || NumberOfBytesRead != 16
      || !(unsigned int)SkipStringInFile(hFile) )
    {
      return 0;
    }
  }
  return v5;
}

```

## disassembly

```asm
0x18000d678  mov     [rsp+arg_8], rbx
0x18000d67d  mov     [rsp+arg_10], rsi
0x18000d682  push    rdi
0x18000d683  sub     rsp, 50h
0x18000d687  mov     rax, cs:__security_cookie
0x18000d68e  xor     rax, rsp
0x18000d691  mov     [rsp+58h+var_10], rax
0x18000d696  xorps   xmm0, xmm0
0x18000d699  mov     [rsp+58h+NumberOfBytesRead], 0
0x18000d6a1  movups  [rsp+58h+Buffer], xmm0
0x18000d6a6  mov     rsi, rdx
0x18000d6a9  mov     rdi, rcx
0x18000d6ac  xor     ebx, ebx
0x18000d6ae  movzx   eax, word ptr [rsi+1Ch]
0x18000d6b2  mov     r8d, 1
0x18000d6b8  cmp     rbx, rax
0x18000d6bb  jnb     short loc_18000D6FE
0x18000d6bd  lea     r9, [rsp+58h+NumberOfBytesRead]; lpNumberOfBytesRead
0x18000d6c2  mov     [rsp+58h+lpOverlapped], 0; lpOverlapped
0x18000d6cb  mov     r8d, 10h; nNumberOfBytesToRead
0x18000d6d1  lea     rdx, [rsp+58h+Buffer]; lpBuffer
0x18000d6d6  mov     rcx, rdi; hFile
0x18000d6d9  call    cs:__imp_ReadFile
0x18000d6df  test    eax, eax
0x18000d6e1  jz      short loc_18000D6FB
0x18000d6e3  cmp     [rsp+58h+NumberOfBytesRead], 10h
0x18000d6e8  jnz     short loc_18000D6FB
0x18000d6ea  mov     rcx, rdi; hFile
0x18000d6ed  call    ?SkipStringInFile@@YAHPEAX@Z; SkipStringInFile(void *)
0x18000d6f2  test    eax, eax
0x18000d6f4  jz      short loc_18000D6FB
0x18000d6f6  inc     rbx
0x18000d6f9  jmp     short loc_18000D6AE
0x18000d6fb  xor     r8d, r8d
0x18000d6fe  mov     eax, r8d
0x18000d701  mov     rcx, [rsp+58h+var_10]
0x18000d706  xor     rcx, rsp; StackCookie
0x18000d709  call    __security_check_cookie
0x18000d70e  mov     rbx, [rsp+58h+arg_8]
0x18000d713  mov     rsi, [rsp+58h+arg_10]
0x18000d718  add     rsp, 50h
0x18000d71c  pop     rdi
0x18000d71d  retn
```
