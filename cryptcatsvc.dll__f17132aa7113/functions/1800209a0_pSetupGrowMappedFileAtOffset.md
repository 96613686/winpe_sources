# pSetupGrowMappedFileAtOffset

- ea: `0x1800209a0`
- end: `0x180020a0c`
- name: `pSetupGrowMappedFileAtOffset`
- size: `108`
- prototype: `__int64 __usercall@<rax>(HANDLE hFile@<rcx>, int)`
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops, installer_update`

## callers

- `0x180006360`

## callees

- `0x1800209a0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800209f7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800209f7`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x1800209ec`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x1800209ec`

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
0x1800209a0  mov     [rsp+arg_0], rbx
0x1800209a5  push    rdi
0x1800209a6  sub     rsp, 20h
0x1800209aa  mov     rdi, rcx
0x1800209ad  cmp     r9d, edx
0x1800209b0  jbe     short loc_1800209B9
0x1800209b2  mov     eax, 57h ; 'W'
0x1800209b7  jmp     short loc_180020A01
0x1800209b9  mov     r11d, r9d
0x1800209bc  xor     ebx, ebx
0x1800209be  add     r11, r8
0x1800209c1  mov     r8d, edx
0x1800209c4  sub     r8d, r9d
0x1800209c7  mov     r9d, [rsp+28h+arg_20]
0x1800209cc  jmp     short loc_1800209DA
0x1800209ce  mov     al, [r8+r11]
0x1800209d2  lea     ecx, [r8+r9]
0x1800209d6  mov     [rcx+r11], al
0x1800209da  sub     r8d, 1
0x1800209de  jns     short loc_1800209CE
0x1800209e0  add     edx, r9d; lDistanceToMove
0x1800209e3  xor     r8d, r8d; lpDistanceToMoveHigh
0x1800209e6  xor     r9d, r9d; dwMoveMethod
0x1800209e9  mov     rcx, rdi; hFile
0x1800209ec  call    cs:__imp_SetFilePointer
0x1800209f2  cmp     eax, 0FFFFFFFFh
0x1800209f5  jnz     short loc_1800209FF
0x1800209f7  call    cs:__imp_GetLastError
0x1800209fd  mov     ebx, eax
0x1800209ff  mov     eax, ebx
0x180020a01  mov     rbx, [rsp+28h+arg_0]
0x180020a06  add     rsp, 20h
0x180020a0a  pop     rdi
0x180020a0b  retn
```
