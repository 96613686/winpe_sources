# GetFileTimeByName(ushort const *,_FILETIME *)

- ea: `0x1800291d4`
- end: `0x18002926d`
- name: `?GetFileTimeByName@@YAJPEBGPEAU_FILETIME@@@Z`
- size: `153`
- prototype: `int(const unsigned __int16 *, struct _FILETIME *)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x180029890`

## callees

- `0x180018d18`
- `0x1800291d4`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180029255`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180029255`
- `api-ms-win-core-file-l1-1-0!GetFileTime` at `0x180029237`
- `api-ms-win-core-file-l1-1-0!GetFileTime` at `0x180029237`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180029212`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180029212`

## pseudocode

```c
__int64 __fastcall GetFileTimeByName(const unsigned __int16 *a1, struct _FILETIME *a2)
{
  HANDLE FileW; // rdi
  int LastErrorAsHResult; // ebx

  if ( a1 && *a1 && a2 )
  {
    FileW = CreateFileW(a1, 0x80000000, 1u, 0, 3u, 0x80u, 0);
    if ( FileW != (HANDLE)-1LL || (LastErrorAsHResult = GetLastErrorAsHResult(), LastErrorAsHResult >= 0) )
    {
      if ( GetFileTime(FileW, 0, 0, a2) )
        LastErrorAsHResult = 0;
      else
        LastErrorAsHResult = GetLastErrorAsHResult();
      if ( FileW != (HANDLE)-1LL )
        CloseHandle(FileW);
    }
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return (unsigned int)LastErrorAsHResult;
}

```

## disassembly

```asm
0x1800291d4  push    rbx
0x1800291d6  push    rbp
0x1800291d7  push    rsi
0x1800291d8  push    rdi
0x1800291d9  sub     rsp, 48h
0x1800291dd  xor     ebp, ebp
0x1800291df  mov     rsi, rdx
0x1800291e2  test    rcx, rcx
0x1800291e5  jz      short loc_18002925D
0x1800291e7  cmp     [rcx], bp
0x1800291ea  jz      short loc_18002925D
0x1800291ec  test    rdx, rdx
0x1800291ef  jz      short loc_18002925D
0x1800291f1  mov     [rsp+68h+hTemplateFile], rbp; hTemplateFile
0x1800291f6  lea     r8d, [rbp+1]; dwShareMode
0x1800291fa  mov     [rsp+68h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x180029202  xor     r9d, r9d; lpSecurityAttributes
0x180029205  mov     edx, 80000000h; dwDesiredAccess
0x18002920a  mov     [rsp+68h+dwCreationDisposition], 3; dwCreationDisposition
0x180029212  call    cs:__imp_CreateFileW
0x180029218  mov     rdi, rax
0x18002921b  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18002921f  jnz     short loc_18002922C
0x180029221  call    GetLastErrorAsHResult
0x180029226  mov     ebx, eax
0x180029228  test    eax, eax
0x18002922a  js      short loc_180029262
0x18002922c  mov     r9, rsi; lpLastWriteTime
0x18002922f  xor     r8d, r8d; lpLastAccessTime
0x180029232  xor     edx, edx; lpCreationTime
0x180029234  mov     rcx, rdi; hFile
0x180029237  call    cs:__imp_GetFileTime
0x18002923d  test    eax, eax
0x18002923f  jz      short loc_180029245
0x180029241  mov     ebx, ebp
0x180029243  jmp     short loc_18002924C
0x180029245  call    GetLastErrorAsHResult
0x18002924a  mov     ebx, eax
0x18002924c  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x180029250  jz      short loc_180029262
0x180029252  mov     rcx, rdi; hObject
0x180029255  call    cs:__imp_CloseHandle
0x18002925b  jmp     short loc_180029262
0x18002925d  mov     ebx, 80070057h
0x180029262  mov     eax, ebx
0x180029264  add     rsp, 48h
0x180029268  pop     rdi
0x180029269  pop     rsi
0x18002926a  pop     rbp
0x18002926b  pop     rbx
0x18002926c  retn
```
