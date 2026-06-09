# GetFullFileName

- ea: `0x18009fdc0`
- end: `0x18009ff37`
- name: `GetFullFileName`
- size: `375`
- prototype: `__int64 __fastcall(wchar_t *Path, LPCWSTR lpFileName)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x1800a0db0`
- `0x1800a2770`

## callees

- `0x180003030`
- `0x18009fdc0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18009fea8`
- `KERNEL32!GetLastError` at `0x18009fea8`
- `KERNEL32!CreateFileW` at `0x18009fe9c`
- `KERNEL32!CreateFileW` at `0x18009fe9c`
- `KERNEL32!CloseHandle` at `0x18009ff24`
- `KERNEL32!CloseHandle` at `0x18009ff24`
- `api-ms-win-crt-filesystem-l1-1-0!_wfullpath` at `0x18009fe16`
- `api-ms-win-crt-filesystem-l1-1-0!_wfullpath` at `0x18009fe16`

## pseudocode

```c
__int64 __fastcall GetFullFileName(wchar_t *Path, WCHAR *lpFileName, size_t a3, DWORD a4)
{
  __int64 v6; // rdx
  __int64 v7; // r8
  HANDLE FileW; // rax
  DWORD LastError; // eax

  if ( !*Path )
  {
    if ( (bidGblFlags & 2) != 0 )
    {
      v6 = 3458057;
LABEL_4:
      v7 = 2147680508LL;
      return bidTraceHR(off_180260410[0], v6, v7);
    }
    return 2147680508LL;
  }
  if ( _wfullpath(lpFileName, Path, a3) )
  {
    if ( a4 == 0x80000000 )
      FileW = CreateFileW(lpFileName, a4, 1u, 0, 3u, 0x100080u, 0);
    else
      FileW = CreateFileW(lpFileName, 0xC0000000, 0, 0, 4u, 0x100080u, 0);
    if ( FileW == (HANDLE)-1LL )
    {
      LastError = GetLastError();
      if ( LastError == 123 )
      {
        if ( (bidGblFlags & 2) != 0 )
        {
          v6 = 3503113;
          goto LABEL_4;
        }
        return 2147680508LL;
      }
      if ( LastError == 3 )
      {
        if ( (bidGblFlags & 2) != 0 )
        {
          v6 = 3507209;
          v7 = 2147680259LL;
          return bidTraceHR(off_180260410[0], v6, v7);
        }
        return 2147680259LL;
      }
      else
      {
        if ( (bidGblFlags & 2) != 0 )
        {
          v6 = 3511305;
          v7 = 2147680258LL;
          return bidTraceHR(off_180260410[0], v6, v7);
        }
        return 2147680258LL;
      }
    }
    else
    {
      CloseHandle(FileW);
      return 0;
    }
  }
  else if ( (bidGblFlags & 2) != 0 )
  {
    return bidTraceHR(off_180260410[0], 3463177, 2147500037LL);
  }
  else
  {
    return 2147500037LL;
  }
}

```

## disassembly

```asm
0x18009fdc0  mov     [rsp+arg_0], rbx
0x18009fdc5  push    rdi
0x18009fdc6  sub     rsp, 40h
0x18009fdca  cmp     word ptr [rcx], 0
0x18009fdce  mov     edi, r9d
0x18009fdd1  mov     rbx, rdx
0x18009fdd4  jnz     short loc_18009FE10
0x18009fdd6  test    byte ptr cs:_bidGblFlags, 2
0x18009fddd  jz      short loc_18009FE00
0x18009fddf  mov     edx, 34C409h
0x18009fde4  mov     r8d, 800300FCh; BufferCount
0x18009fdea  mov     rcx, cs:off_180260410; "C:\\__w\\1\\s\\Sql\\Ntdbms\\sqlncli\\ol"...
0x18009fdf1  mov     rbx, [rsp+48h+arg_0]
0x18009fdf6  add     rsp, 40h
0x18009fdfa  pop     rdi
0x18009fdfb  jmp     _bidTraceHR
0x18009fe00  mov     eax, 800300FCh
0x18009fe05  mov     rbx, [rsp+48h+arg_0]
0x18009fe0a  add     rsp, 40h
0x18009fe0e  pop     rdi
0x18009fe0f  retn
0x18009fe10  mov     rdx, rcx; Path
0x18009fe13  mov     rcx, rbx; Buffer
0x18009fe16  call    cs:__imp__wfullpath
0x18009fe1c  test    rax, rax
0x18009fe1f  jnz     short loc_18009FE5B
0x18009fe21  test    byte ptr cs:_bidGblFlags, 2
0x18009fe28  jz      short loc_18009FE4B
0x18009fe2a  mov     rcx, cs:off_180260410; "C:\\__w\\1\\s\\Sql\\Ntdbms\\sqlncli\\ol"...
0x18009fe31  mov     edx, 34D809h
0x18009fe36  mov     r8d, 80004005h
0x18009fe3c  mov     rbx, [rsp+48h+arg_0]
0x18009fe41  add     rsp, 40h
0x18009fe45  pop     rdi
0x18009fe46  jmp     _bidTraceHR
0x18009fe4b  mov     eax, 80004005h
0x18009fe50  mov     rbx, [rsp+48h+arg_0]
0x18009fe55  add     rsp, 40h
0x18009fe59  pop     rdi
0x18009fe5a  retn
0x18009fe5b  xor     r9d, r9d; lpSecurityAttributes
0x18009fe5e  mov     [rsp+48h+hTemplateFile], 0; hTemplateFile
0x18009fe67  mov     [rsp+48h+dwFlagsAndAttributes], 100080h; dwFlagsAndAttributes
0x18009fe6f  mov     rcx, rbx; lpFileName
0x18009fe72  cmp     edi, 80000000h
0x18009fe78  jnz     short loc_18009FE8C
0x18009fe7a  mov     [rsp+48h+dwCreationDisposition], 3
0x18009fe82  mov     edx, edi
0x18009fe84  mov     r8d, 1
0x18009fe8a  jmp     short loc_18009FE9C
0x18009fe8c  mov     [rsp+48h+dwCreationDisposition], 4; dwCreationDisposition
0x18009fe94  xor     r8d, r8d; dwShareMode
0x18009fe97  mov     edx, 0C0000000h; dwDesiredAccess
0x18009fe9c  call    cs:__imp_CreateFileW
0x18009fea2  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18009fea6  jnz     short loc_18009FF21
0x18009fea8  call    cs:__imp_GetLastError
0x18009feae  cmp     eax, 7Bh ; '{'
0x18009feb1  jnz     short loc_18009FECA
0x18009feb3  test    byte ptr cs:_bidGblFlags, 2
0x18009feba  jz      loc_18009FE00
0x18009fec0  mov     edx, 357409h
0x18009fec5  jmp     loc_18009FDE4
0x18009feca  cmp     eax, 3
0x18009fecd  jnz     short loc_18009FEF8
0x18009fecf  test    byte ptr cs:_bidGblFlags, 2
0x18009fed6  jz      short loc_18009FEE8
0x18009fed8  mov     edx, 358409h
0x18009fedd  mov     r8d, 80030003h
0x18009fee3  jmp     loc_18009FDEA
0x18009fee8  mov     eax, 80030003h
0x18009feed  mov     rbx, [rsp+48h+arg_0]
0x18009fef2  add     rsp, 40h
0x18009fef6  pop     rdi
0x18009fef7  retn
0x18009fef8  test    byte ptr cs:_bidGblFlags, 2
0x18009feff  jz      short loc_18009FF11
0x18009ff01  mov     edx, 359409h
0x18009ff06  mov     r8d, 80030002h
0x18009ff0c  jmp     loc_18009FDEA
0x18009ff11  mov     eax, 80030002h
0x18009ff16  mov     rbx, [rsp+48h+arg_0]
0x18009ff1b  add     rsp, 40h
0x18009ff1f  pop     rdi
0x18009ff20  retn
0x18009ff21  mov     rcx, rax; hObject
0x18009ff24  call    cs:__imp_CloseHandle
0x18009ff2a  mov     rbx, [rsp+48h+arg_0]
0x18009ff2f  xor     eax, eax
0x18009ff31  add     rsp, 40h
0x18009ff35  pop     rdi
0x18009ff36  retn
```
