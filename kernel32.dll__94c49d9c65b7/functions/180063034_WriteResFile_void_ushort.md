# WriteResFile(void *,ushort *)

- ea: `0x180063034`
- end: `0x1800631d4`
- name: `?WriteResFile@@YAJPEAXPEAG@Z`
- size: `416`
- prototype: `__int64 __fastcall(HGLOBAL hMem, LPCWSTR lpFileName)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, installer_update`

## callers

- `0x180063250`

## callees

- `0x180029340`
- `0x1800367f0`
- `0x180059128`
- `0x180063034`
- `0x18007a7dd`
- `0x18007a840`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800630d3`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180063173`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800630d3`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180063173`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x180063077`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x180063096`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x180063077`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x180063096`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x1800630a4`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x1800630e0`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x1800631a5`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x1800630a4`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x1800630e0`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x1800631a5`

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
0x180063034  mov     [rsp+arg_10], rbx
0x180063039  push    rbp
0x18006303a  push    rsi
0x18006303b  push    rdi
0x18006303c  push    r14
0x18006303e  push    r15
0x180063040  sub     rsp, 90h
0x180063047  mov     rax, cs:__security_cookie
0x18006304e  xor     rax, rsp
0x180063051  mov     [rsp+0B8h+var_38], rax
0x180063059  mov     r15, rdx
0x18006305c  mov     rsi, rcx
0x18006305f  mov     r14d, 40h ; '@'
0x180063065  lea     rcx, [rsp+0B8h+Buffer]; void *
0x18006306a  mov     r8d, r14d; Size
0x18006306d  xor     edx, edx; Val
0x18006306f  call    memset_0
0x180063074  mov     rcx, rsi; hMem
0x180063077  call    cs:__imp_GlobalLock
0x18006307d  mov     rbp, rax
0x180063080  test    rax, rax
0x180063083  jnz     short loc_180063092
0x180063085  mov     eax, gs:68h
0x18006308d  jmp     loc_1800631AD
0x180063092  mov     rcx, [rax+30h]; hMem
0x180063096  call    cs:__imp_GlobalLock
0x18006309c  test    rax, rax
0x18006309f  jnz     short loc_1800630AC
0x1800630a1  mov     rcx, rsi; hMem
0x1800630a4  call    cs:__imp_GlobalUnlock
0x1800630aa  jmp     short loc_180063085
0x1800630ac  mov     [rsp+0B8h+hTemplateFile], 0; hTemplateFile
0x1800630b5  xor     r9d, r9d; lpSecurityAttributes
0x1800630b8  mov     [rsp+0B8h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x1800630c0  xor     r8d, r8d; dwShareMode
0x1800630c3  mov     edx, 80000000h; dwDesiredAccess
0x1800630c8  mov     [rsp+0B8h+dwCreationDisposition], 3; dwCreationDisposition
0x1800630d0  mov     rcx, rax; lpFileName
0x1800630d3  call    cs:__imp_CreateFileW
0x1800630d9  mov     rcx, [rbp+30h]; hMem
0x1800630dd  mov     rdi, rax
0x1800630e0  call    cs:__imp_GlobalUnlock
0x1800630e6  cmp     edi, 0FFFFFFFFh
0x1800630e9  jnz     short loc_1800630F3
0x1800630eb  lea     ebx, [rdi+6Fh]
0x1800630ee  jmp     loc_1800631A2
0x1800630f3  mov     r8d, r14d; uBytes
0x1800630f6  lea     rdx, [rsp+0B8h+Buffer]; lpBuffer
0x1800630fb  mov     ecx, edi; hFile
0x1800630fd  call    _lread
0x180063102  mov     ebx, eax
0x180063104  cmp     eax, r14d
0x180063107  jz      short loc_18006311A
0x180063109  mov     ecx, edi; hFile
0x18006310b  call    _lclose
0x180063110  mov     ebx, 1Eh
0x180063115  jmp     loc_1800631A2
0x18006311a  mov     eax, 5A4Dh
0x18006311f  cmp     [rsp+0B8h+Buffer], ax
0x180063124  jz      short loc_180063134
0x180063126  mov     ecx, edi; hFile
0x180063128  call    _lclose
0x18006312d  mov     ebx, 0BFh
0x180063132  jmp     short loc_1800631A2
0x180063134  mov     r14d, [rsp+0B8h+var_3C]
0x180063139  test    r14d, r14d
0x18006313c  jnz     short loc_18006314C
0x18006313e  mov     ecx, edi; hFile
0x180063140  call    _lclose
0x180063145  mov     ebx, 0C1h
0x18006314a  jmp     short loc_1800631A2
0x18006314c  mov     [rsp+0B8h+hTemplateFile], 0; hTemplateFile
0x180063155  xor     r9d, r9d; lpSecurityAttributes
0x180063158  mov     [rsp+0B8h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x180063160  xor     r8d, r8d; dwShareMode
0x180063163  mov     edx, 0C0000000h; dwDesiredAccess
0x180063168  mov     [rsp+0B8h+dwCreationDisposition], 2; dwCreationDisposition
0x180063170  mov     rcx, r15; lpFileName
0x180063173  call    cs:__imp_CreateFileW
0x180063179  mov     r15, rax
0x18006317c  cmp     eax, 0FFFFFFFFh
0x18006317f  jz      short loc_18006319B
0x180063181  mov     r9, rbp; struct _UPDATEDATA *
0x180063184  mov     r8d, r14d; unsigned int
0x180063187  mov     edx, r15d; int
0x18006318a  mov     ecx, edi; int
0x18006318c  call    ?PEWriteResFile@@YAJHHKPEAU_UPDATEDATA@@@Z; PEWriteResFile(int,int,ulong,_UPDATEDATA *)
0x180063191  mov     ecx, r15d; hFile
0x180063194  mov     ebx, eax
0x180063196  call    _lclose
0x18006319b  mov     ecx, edi; hFile
0x18006319d  call    _lclose
0x1800631a2  mov     rcx, rsi; hMem
0x1800631a5  call    cs:__imp_GlobalUnlock
0x1800631ab  mov     eax, ebx
0x1800631ad  mov     rcx, [rsp+0B8h+var_38]
0x1800631b5  xor     rcx, rsp; StackCookie
0x1800631b8  call    __security_check_cookie
0x1800631bd  mov     rbx, [rsp+0B8h+arg_10]
0x1800631c5  add     rsp, 90h
0x1800631cc  pop     r15
0x1800631ce  pop     r14
0x1800631d0  pop     rdi
0x1800631d1  pop     rsi
0x1800631d2  pop     rbp
0x1800631d3  retn
```
