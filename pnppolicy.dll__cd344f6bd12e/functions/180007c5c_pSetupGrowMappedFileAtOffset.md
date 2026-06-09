# pSetupGrowMappedFileAtOffset

- ea: `0x180007c5c`
- end: `0x180007cc8`
- name: `pSetupGrowMappedFileAtOffset`
- size: `108`
- prototype: `__int64 __usercall@<rax>(HANDLE hFile@<rcx>, int)`
- caller_count: `2`
- callee_count: `1`
- tags: `file_ops, installer_update`

## callers

- `0x1800050b8`
- `0x18000512c`

## callees

- `0x180007c5c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007cb3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007cb3`
- `KERNEL32!SetFilePointer` at `0x180007ca8`
- `KERNEL32!SetFilePointer` at `0x180007ca8`

## pseudocode

```c
__int64 __fastcall pSetupGrowMappedFileAtOffset(HANDLE hFile, unsigned int a2, __int64 a3, unsigned int a4, int a5)
{
  unsigned int v6; // ebx
  __int64 v7; // r11
  unsigned int i; // r8d

  if ( a4 > a2 )
    return 87;
  v6 = 0;
  v7 = a3 + a4;
  for ( i = a2 - a4; (--i & 0x80000000) == 0; *(_BYTE *)(i + a5 + v7) = *(_BYTE *)(i + v7) )
    ;
  if ( SetFilePointer(hFile, a5 + a2, 0, 0) == -1 )
    return GetLastError();
  return v6;
}

```

## disassembly

```asm
0x180007c5c  mov     [rsp+arg_0], rbx
0x180007c61  push    rdi
0x180007c62  sub     rsp, 20h
0x180007c66  mov     rdi, rcx
0x180007c69  cmp     r9d, edx
0x180007c6c  jbe     short loc_180007C75
0x180007c6e  mov     eax, 57h ; 'W'
0x180007c73  jmp     short loc_180007CBD
0x180007c75  mov     r11d, r9d
0x180007c78  xor     ebx, ebx
0x180007c7a  add     r11, r8
0x180007c7d  mov     r8d, edx
0x180007c80  sub     r8d, r9d
0x180007c83  mov     r9d, [rsp+28h+arg_20]
0x180007c88  jmp     short loc_180007C96
0x180007c8a  mov     al, [r8+r11]
0x180007c8e  lea     ecx, [r8+r9]
0x180007c92  mov     [rcx+r11], al
0x180007c96  sub     r8d, 1
0x180007c9a  jns     short loc_180007C8A
0x180007c9c  add     edx, r9d; lDistanceToMove
0x180007c9f  xor     r8d, r8d; lpDistanceToMoveHigh
0x180007ca2  xor     r9d, r9d; dwMoveMethod
0x180007ca5  mov     rcx, rdi; hFile
0x180007ca8  call    cs:__imp_SetFilePointer
0x180007cae  cmp     eax, 0FFFFFFFFh
0x180007cb1  jnz     short loc_180007CBB
0x180007cb3  call    cs:__imp_GetLastError
0x180007cb9  mov     ebx, eax
0x180007cbb  mov     eax, ebx
0x180007cbd  mov     rbx, [rsp+28h+arg_0]
0x180007cc2  add     rsp, 20h
0x180007cc6  pop     rdi
0x180007cc7  retn
```
