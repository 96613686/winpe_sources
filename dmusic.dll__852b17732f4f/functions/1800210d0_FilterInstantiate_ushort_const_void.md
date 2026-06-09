# FilterInstantiate(ushort const *,void * *)

- ea: `0x1800210d0`
- end: `0x1800211c5`
- name: `?FilterInstantiate@@YAJPEBGPEAPEAX@Z`
- size: `245`
- prototype: `__int64 __fastcall(const unsigned __int16 *, void **)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x18001e2b0`
- `0x18001f51c`

## callees

- `0x180007684`
- `0x1800210d0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002111c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002111c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002116d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180021182`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002116d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180021182`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180021104`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180021104`

## pseudocode

```c
__int64 __fastcall FilterInstantiate(const unsigned __int16 *a1, void **a2)
{
  char *FileW; // rbx
  signed int LastError; // eax
  unsigned int v5; // edi
  int v7; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  FileW = (char *)CreateFileW(a1, 0xC0000000, 0, 0, 3u, 0x40000080u, 0);
  if ( ((unsigned __int64)(FileW + 1) & 0xFFFFFFFFFFFFFFFEuLL) != 0 )
    goto LABEL_15;
  LastError = GetLastError();
  v5 = LastError;
  if ( LastError )
  {
    if ( LastError <= 0 )
      goto LABEL_6;
  }
  else
  {
    LOWORD(v5) = 31;
  }
  v5 = (unsigned __int16)v5 | 0x80070000;
LABEL_6:
  if ( (v5 & 0x80000000) != 0 )
  {
    if ( v5 + 2147024894 <= 1 )
    {
      if ( (unsigned __int64)(FileW - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
        CloseHandle(FileW);
      if ( v5 + 2147024894 <= 1 )
        return v5;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x47D,
        (unsigned int)"avcore\\audiocore\\lib\\kslib\\kslib.cpp",
        (const char *)v5,
        v7);
      if ( (unsigned __int64)(FileW - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
        CloseHandle(FileW);
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x4A3,
      (unsigned int)"avcore\\audiocore\\lib\\kslib\\kslib.cpp",
      (const char *)v5,
      v7);
    return v5;
  }
LABEL_15:
  *a2 = FileW;
  return 0;
}

```

## disassembly

```asm
0x1800210d0  mov     rax, rsp
0x1800210d3  mov     [rax+8], rbx
0x1800210d7  mov     [rax+10h], rsi
0x1800210db  push    rdi
0x1800210dc  sub     rsp, 40h
0x1800210e0  mov     qword ptr [rax-18h], 0
0x1800210e8  mov     rsi, rdx
0x1800210eb  mov     dword ptr [rax-20h], 40000080h
0x1800210f2  mov     edx, 0C0000000h; dwDesiredAccess
0x1800210f7  xor     r9d, r9d; lpSecurityAttributes
0x1800210fa  mov     dword ptr [rax-28h], 3
0x180021101  xor     r8d, r8d; dwShareMode
0x180021104  call    cs:__imp_CreateFileW
0x18002110a  mov     rbx, rax
0x18002110d  inc     rax
0x180021110  test    rax, 0FFFFFFFFFFFFFFFEh
0x180021116  jnz     loc_1800211B0
0x18002111c  call    cs:__imp_GetLastError
0x180021122  mov     edi, eax
0x180021124  test    eax, eax
0x180021126  jnz     short loc_18002112D
0x180021128  lea     edi, [rax+1Fh]
0x18002112b  jmp     short loc_18002112F
0x18002112d  jle     short loc_180021138
0x18002112f  movzx   edi, di
0x180021132  or      edi, 80070000h
0x180021138  test    edi, edi
0x18002113a  jns     short loc_1800211B0
0x18002113c  lea     eax, [rdi+7FF8FFFEh]
0x180021142  cmp     eax, 1
0x180021145  jbe     short loc_180021175
0x180021147  mov     rcx, [rsp+48h]; this
0x18002114c  lea     r8, aAvcoreAudiocor; "avcore\\audiocore\\lib\\kslib\\kslib.cp"...
0x180021153  mov     r9d, edi; char *
0x180021156  mov     edx, 47Dh; void *
0x18002115b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180021160  lea     rax, [rbx-1]
0x180021164  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180021168  ja      short loc_180021193
0x18002116a  mov     rcx, rbx; hObject
0x18002116d  call    cs:__imp_CloseHandle
0x180021173  jmp     short loc_180021193
0x180021175  lea     rax, [rbx-1]
0x180021179  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18002117d  ja      short loc_180021188
0x18002117f  mov     rcx, rbx; hObject
0x180021182  call    cs:__imp_CloseHandle
0x180021188  lea     ecx, [rdi+7FF8FFFEh]
0x18002118e  cmp     ecx, 1
0x180021191  jbe     short loc_1800211AC
0x180021193  mov     rcx, [rsp+48h]; this
0x180021198  lea     r8, aAvcoreAudiocor; "avcore\\audiocore\\lib\\kslib\\kslib.cp"...
0x18002119f  mov     r9d, edi; char *
0x1800211a2  mov     edx, 4A3h; void *
0x1800211a7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800211ac  mov     eax, edi
0x1800211ae  jmp     short loc_1800211B5
0x1800211b0  mov     [rsi], rbx
0x1800211b3  xor     eax, eax
0x1800211b5  mov     rbx, [rsp+48h+arg_0]
0x1800211ba  mov     rsi, [rsp+48h+arg_8]
0x1800211bf  add     rsp, 40h
0x1800211c3  pop     rdi
0x1800211c4  retn
```
