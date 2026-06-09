# _open_osfhandle

- ea: `0x1800200c0`
- end: `0x1800201c3`
- name: `_open_osfhandle`
- size: `259`
- prototype: `int __cdecl(intptr_t OSFileHandle, int Flags)`
- caller_count: `0`
- callee_count: `7`
- tags: ``

## callees

- `0x180007e80`
- `0x180007ea8`
- `0x180007f00`
- `0x18001fd30`
- `0x1800200c0`
- `0x1800201cc`
- `0x18002026c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002010c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002010c`
- `api-ms-win-core-file-l1-1-0!GetFileType` at `0x180020102`
- `api-ms-win-core-file-l1-1-0!GetFileType` at `0x180020102`

## pseudocode

```c
int __cdecl open_osfhandle(intptr_t OSFileHandle, int Flags)
{
  char v3; // r8
  char v4; // bl
  DWORD FileType; // eax
  __int64 v6; // rdx
  __int64 v7; // rcx
  __int64 v8; // r8
  __int64 v9; // r9
  DWORD LastError; // eax
  unsigned int v12; // eax
  __int64 v13; // rdi
  __int64 v14; // rcx

  v3 = (4 * (Flags & 8)) | 0x80;
  if ( (Flags & 0x4000) == 0 )
    v3 = 4 * (Flags & 8);
  v4 = v3 | 0x10;
  if ( (Flags & 0x80u) == 0 )
    v4 = v3;
  FileType = GetFileType((HANDLE)OSFileHandle);
  switch ( FileType )
  {
    case 0u:
      LastError = GetLastError();
      dosmaperr(LastError);
      return -1;
    case 2u:
      v4 |= 0x40u;
      break;
    case 3u:
      v4 |= 8u;
      break;
  }
  v12 = alloc_osfhnd(v7, v6, v8, v9);
  v13 = (int)v12;
  if ( v12 == -1 )
  {
    *errno() = 24;
    *_doserrno() = 0;
    return -1;
  }
  set_osfhnd(v12, OSFileHandle);
  v14 = 56 * (v13 & 0x1F);
  *(_BYTE *)(_pioinfo[v13 >> 5] + v14 + 8) = v4 | 1;
  *(_DWORD *)(_pioinfo[v13 >> 5] + v14 + 12) &= 0xFFFFFFFC;
  *(_DWORD *)(_pioinfo[v13 >> 5] + v14 + 12) &= ~8u;
  unlock_fhandle((unsigned int)v13);
  return v13;
}

```

## disassembly

```asm
0x1800200c0  mov     [rsp+arg_0], rbx
0x1800200c5  mov     [rsp+arg_10], rsi
0x1800200ca  push    rdi
0x1800200cb  sub     rsp, 30h
0x1800200cf  mov     rsi, rcx
0x1800200d2  mov     al, dl
0x1800200d4  and     al, 8
0x1800200d6  shl     al, 2
0x1800200d9  movzx   r10d, al
0x1800200dd  mov     al, r10b
0x1800200e0  or      al, 80h
0x1800200e2  movzx   r8d, al
0x1800200e6  bt      edx, 0Eh
0x1800200ea  cmovnb  r8d, r10d
0x1800200ee  movzx   ecx, r8b
0x1800200f2  mov     al, cl
0x1800200f4  or      al, 10h
0x1800200f6  movzx   ebx, al
0x1800200f9  test    dl, 80h
0x1800200fc  cmovz   ebx, ecx
0x1800200ff  mov     rcx, rsi; hFile
0x180020102  call    cs:__imp_GetFileType
0x180020108  test    eax, eax
0x18002010a  jnz     short loc_18002012C
0x18002010c  call    cs:__imp_GetLastError
0x180020112  mov     ecx, eax
0x180020114  call    _dosmaperr
0x180020119  or      eax, 0FFFFFFFFh
0x18002011c  mov     rbx, [rsp+38h+arg_0]
0x180020121  mov     rsi, [rsp+38h+arg_10]
0x180020126  add     rsp, 30h
0x18002012a  pop     rdi
0x18002012b  retn
0x18002012c  mov     [rsp+38h+var_18], 0
0x180020134  cmp     eax, 2
0x180020137  jnz     short loc_18002013E
0x180020139  or      bl, 40h
0x18002013c  jmp     short loc_180020146
0x18002013e  cmp     eax, 3
0x180020141  jnz     short loc_180020146
0x180020143  or      bl, 8
0x180020146  call    _alloc_osfhnd
0x18002014b  movsxd  rdi, eax
0x18002014e  mov     [rsp+38h+arg_8], edi
0x180020152  cmp     edi, 0FFFFFFFFh
0x180020155  jnz     short loc_18002016F
0x180020157  call    _errno
0x18002015c  mov     dword ptr [rax], 18h
0x180020162  call    __doserrno
0x180020167  mov     dword ptr [rax], 0
0x18002016d  jmp     short loc_180020119
0x18002016f  mov     rdx, rsi
0x180020172  mov     ecx, edi
0x180020174  call    _set_osfhnd
0x180020179  mov     rdx, rdi
0x18002017c  sar     rdx, 5
0x180020180  lea     r8, __pioinfo
0x180020187  mov     eax, edi
0x180020189  and     eax, 1Fh
0x18002018c  imul    rcx, rax, 38h ; '8'
0x180020190  or      bl, 1
0x180020193  mov     rax, [r8+rdx*8]
0x180020197  mov     [rax+rcx+8], bl
0x18002019b  mov     rax, [r8+rdx*8]
0x18002019f  and     dword ptr [rax+rcx+0Ch], 0FFFFFFFCh
0x1800201a4  mov     rax, [r8+rdx*8]
0x1800201a8  and     dword ptr [rax+rcx+0Ch], 0FFFFFFF7h
0x1800201ad  mov     [rsp+38h+var_18], 1
0x1800201b5  mov     ecx, edi
0x1800201b7  call    _unlock_fhandle
0x1800201bc  mov     eax, edi
0x1800201be  jmp     loc_18002011C
0x18007b9b7  push    rbp
0x18007b9b9  sub     rsp, 20h
0x18007b9bd  mov     rbp, rdx
0x18007b9c0  cmp     dword ptr [rbp+20h], 0
0x18007b9c4  jnz     short loc_18007BA10
0x18007b9c6  movsxd  r9, dword ptr [rbp+48h]
0x18007b9ca  mov     rdx, r9
0x18007b9cd  sar     rdx, 5
0x18007b9d1  lea     r8, __pioinfo
0x18007b9d8  mov     eax, r9d
0x18007b9db  and     eax, 1Fh
0x18007b9de  imul    rcx, rax, 38h ; '8'
0x18007b9e2  mov     rax, [r8+rdx*8]
0x18007b9e6  mov     r8b, [rax+rcx+8]
0x18007b9eb  and     r8b, 0FEh
0x18007b9ef  mov     rdx, r9
0x18007b9f2  sar     rdx, 5
0x18007b9f6  lea     r10, __pioinfo
0x18007b9fd  mov     eax, r9d
0x18007ba00  and     eax, 1Fh
0x18007ba03  imul    rcx, rax, 38h ; '8'
0x18007ba07  mov     rax, [r10+rdx*8]
0x18007ba0b  mov     [rax+rcx+8], r8b
0x18007ba10  mov     ecx, [rbp+48h]
0x18007ba13  call    _unlock_fhandle
0x18007ba18  nop
0x18007ba19  add     rsp, 20h
0x18007ba1d  pop     rbp
0x18007ba1e  retn
```
