# WriteResFile(void *,ushort *)

- ea: `0x180069b50`
- end: `0x180069d1b`
- name: `?WriteResFile@@YAJPEAXPEAG@Z`
- size: `459`
- prototype: `__int64 __fastcall(HGLOBAL hMem, LPCWSTR lpFileName)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, installer_update`

## callers

- `0x180069db0`

## callees

- `0x180027320`
- `0x180039030`
- `0x18005e844`
- `0x180069b50`
- `0x18008275d`
- `0x1800827c0`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180069c01`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180069cad`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180069c01`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180069cad`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x180069b93`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x180069bb8`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x180069b93`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x180069bb8`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x180069bcc`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x180069c14`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x180069ce5`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x180069bcc`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x180069c14`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x180069ce5`

## pseudocode

```c
ULONG __fastcall WriteResFile(HGLOBAL hMem, LPCWSTR lpFileName)
{
  HGLOBAL *v4; // rax
  HGLOBAL *v5; // rbp
  const WCHAR *v7; // rax
  HFILE FileW; // edi
  UINT v9; // ebx
  unsigned int v10; // r14d
  int v11; // eax
  HFILE v12; // r15d
  _WORD Buffer[30]; // [rsp+40h] [rbp-78h] BYREF
  unsigned int v14; // [rsp+7Ch] [rbp-3Ch]

  memset_0(Buffer, 0, 0x40u);
  v4 = (HGLOBAL *)GlobalLock(hMem);
  v5 = v4;
  if ( !v4 )
    return NtCurrentTeb()->LastErrorValue;
  v7 = (const WCHAR *)GlobalLock(v4[6]);
  if ( !v7 )
  {
    GlobalUnlock(hMem);
    return NtCurrentTeb()->LastErrorValue;
  }
  FileW = (unsigned int)CreateFileW(v7, 0x80000000, 0, 0, 3u, 0x80u, 0);
  GlobalUnlock(v5[6]);
  if ( FileW == -1 )
  {
    v9 = 110;
  }
  else
  {
    v9 = lread(FileW, Buffer, 0x40u);
    if ( v9 == 64 )
    {
      if ( Buffer[0] == 23117 )
      {
        v10 = v14;
        if ( v14 )
        {
          v11 = (unsigned int)CreateFileW(lpFileName, 0xC0000000, 0, 0, 2u, 0x80u, 0);
          v12 = v11;
          if ( v11 != -1 )
          {
            v9 = PEWriteResFile(FileW, v11, v10, (struct _UPDATEDATA *)v5);
            lclose(v12);
          }
          lclose(FileW);
        }
        else
        {
          lclose(FileW);
          v9 = 193;
        }
      }
      else
      {
        lclose(FileW);
        v9 = 191;
      }
    }
    else
    {
      lclose(FileW);
      v9 = 30;
    }
  }
  GlobalUnlock(hMem);
  return v9;
}

```

## disassembly

```asm
0x180069b50  mov     [rsp+arg_10], rbx
0x180069b55  push    rbp
0x180069b56  push    rsi
0x180069b57  push    rdi
0x180069b58  push    r14
0x180069b5a  push    r15
0x180069b5c  sub     rsp, 90h
0x180069b63  mov     rax, cs:__security_cookie
0x180069b6a  xor     rax, rsp
0x180069b6d  mov     [rsp+0B8h+var_38], rax
0x180069b75  mov     r15, rdx
0x180069b78  mov     rsi, rcx
0x180069b7b  mov     r14d, 40h ; '@'
0x180069b81  lea     rcx, [rsp+0B8h+Buffer]; void *
0x180069b86  mov     r8d, r14d; Size
0x180069b89  xor     edx, edx; Val
0x180069b8b  call    memset_0
0x180069b90  mov     rcx, rsi; hMem
0x180069b93  call    cs:__imp_GlobalLock
0x180069b9a  nop     dword ptr [rax+rax+00h]
0x180069b9f  mov     rbp, rax
0x180069ba2  test    rax, rax
0x180069ba5  jnz     short loc_180069BB4
0x180069ba7  mov     eax, gs:68h
0x180069baf  jmp     loc_180069CF3
0x180069bb4  mov     rcx, [rax+30h]; hMem
0x180069bb8  call    cs:__imp_GlobalLock
0x180069bbf  nop     dword ptr [rax+rax+00h]
0x180069bc4  test    rax, rax
0x180069bc7  jnz     short loc_180069BDA
0x180069bc9  mov     rcx, rsi; hMem
0x180069bcc  call    cs:__imp_GlobalUnlock
0x180069bd3  nop     dword ptr [rax+rax+00h]
0x180069bd8  jmp     short loc_180069BA7
0x180069bda  mov     [rsp+0B8h+hTemplateFile], 0; hTemplateFile
0x180069be3  xor     r9d, r9d; lpSecurityAttributes
0x180069be6  mov     [rsp+0B8h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x180069bee  xor     r8d, r8d; dwShareMode
0x180069bf1  mov     edx, 80000000h; dwDesiredAccess
0x180069bf6  mov     [rsp+0B8h+dwCreationDisposition], 3; dwCreationDisposition
0x180069bfe  mov     rcx, rax; lpFileName
0x180069c01  call    cs:__imp_CreateFileW
0x180069c08  nop     dword ptr [rax+rax+00h]
0x180069c0d  mov     rcx, [rbp+30h]; hMem
0x180069c11  mov     rdi, rax
0x180069c14  call    cs:__imp_GlobalUnlock
0x180069c1b  nop     dword ptr [rax+rax+00h]
0x180069c20  cmp     edi, 0FFFFFFFFh
0x180069c23  jnz     short loc_180069C2D
0x180069c25  lea     ebx, [rdi+6Fh]
0x180069c28  jmp     loc_180069CE2
0x180069c2d  mov     r8d, r14d; uBytes
0x180069c30  lea     rdx, [rsp+0B8h+Buffer]; lpBuffer
0x180069c35  mov     ecx, edi; hFile
0x180069c37  call    _lread
0x180069c3c  mov     ebx, eax
0x180069c3e  cmp     eax, r14d
0x180069c41  jz      short loc_180069C54
0x180069c43  mov     ecx, edi; hFile
0x180069c45  call    _lclose
0x180069c4a  mov     ebx, 1Eh
0x180069c4f  jmp     loc_180069CE2
0x180069c54  mov     eax, 5A4Dh
0x180069c59  cmp     [rsp+0B8h+Buffer], ax
0x180069c5e  jz      short loc_180069C6E
0x180069c60  mov     ecx, edi; hFile
0x180069c62  call    _lclose
0x180069c67  mov     ebx, 0BFh
0x180069c6c  jmp     short loc_180069CE2
0x180069c6e  mov     r14d, [rsp+0B8h+var_3C]
0x180069c73  test    r14d, r14d
0x180069c76  jnz     short loc_180069C86
0x180069c78  mov     ecx, edi; hFile
0x180069c7a  call    _lclose
0x180069c7f  mov     ebx, 0C1h
0x180069c84  jmp     short loc_180069CE2
0x180069c86  mov     [rsp+0B8h+hTemplateFile], 0; hTemplateFile
0x180069c8f  xor     r9d, r9d; lpSecurityAttributes
0x180069c92  mov     [rsp+0B8h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x180069c9a  xor     r8d, r8d; dwShareMode
0x180069c9d  mov     edx, 0C0000000h; dwDesiredAccess
0x180069ca2  mov     [rsp+0B8h+dwCreationDisposition], 2; dwCreationDisposition
0x180069caa  mov     rcx, r15; lpFileName
0x180069cad  call    cs:__imp_CreateFileW
0x180069cb4  nop     dword ptr [rax+rax+00h]
0x180069cb9  mov     r15, rax
0x180069cbc  cmp     eax, 0FFFFFFFFh
0x180069cbf  jz      short loc_180069CDB
0x180069cc1  mov     r9, rbp; struct _UPDATEDATA *
0x180069cc4  mov     r8d, r14d; unsigned int
0x180069cc7  mov     edx, r15d; int
0x180069cca  mov     ecx, edi; int
0x180069ccc  call    ?PEWriteResFile@@YAJHHKPEAU_UPDATEDATA@@@Z; PEWriteResFile(int,int,ulong,_UPDATEDATA *)
0x180069cd1  mov     ecx, r15d; hFile
0x180069cd4  mov     ebx, eax
0x180069cd6  call    _lclose
0x180069cdb  mov     ecx, edi; hFile
0x180069cdd  call    _lclose
0x180069ce2  mov     rcx, rsi; hMem
0x180069ce5  call    cs:__imp_GlobalUnlock
0x180069cec  nop     dword ptr [rax+rax+00h]
0x180069cf1  mov     eax, ebx
0x180069cf3  mov     rcx, [rsp+0B8h+var_38]
0x180069cfb  xor     rcx, rsp; StackCookie
0x180069cfe  call    __security_check_cookie
0x180069d03  mov     rbx, [rsp+0B8h+arg_10]
0x180069d0b  add     rsp, 90h
0x180069d12  pop     r15
0x180069d14  pop     r14
0x180069d16  pop     rdi
0x180069d17  pop     rsi
0x180069d18  pop     rbp
0x180069d19  retn
```
