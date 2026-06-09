# CFileStream::ReadAt_FromFile(unsigned __int64,void *,ulong,ulong *)

- ea: `0x1800351dc`
- end: `0x1800352d1`
- name: `?ReadAt_FromFile@CFileStream@@AEAAJ_KPEAXKPEAK@Z`
- size: `245`
- prototype: `int(CFileStream *__hidden this, unsigned __int64, void *, unsigned int, unsigned int *)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x180025840`

## callees

- `0x180026bc4`
- `0x1800351dc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800352b7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800352c2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800352b7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800352c2`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18003525f`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18003529b`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18003525f`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18003529b`

## pseudocode

```c
__int64 __fastcall CFileStream::ReadAt_FromFile(
        CFileStream *this,
        char *a2,
        void *a3,
        DWORD a4,
        unsigned int *lpNumberOfBytesRead)
{
  __int64 v7; // rcx
  int v8; // eax
  void *v9; // rcx
  __int64 v10; // rcx
  DWORD LastError; // eax
  struct _OVERLAPPED Overlapped; // [rsp+30h] [rbp-28h] BYREF

  if ( !a4 )
  {
    *lpNumberOfBytesRead = 0;
    return 0;
  }
  v7 = *((_QWORD *)this + 6);
  v8 = 0;
  if ( v7 )
    LOBYTE(v8) = a2 == *(char **)(v7 + 48);
  v9 = (void *)*((_QWORD *)this + 8);
  if ( !v8 )
  {
    Overlapped.Internal = 0;
    Overlapped.InternalHigh = 0;
    Overlapped.Pointer = a2;
    Overlapped.hEvent = 0;
    if ( !ReadFile(v9, a3, a4, lpNumberOfBytesRead, &Overlapped) && GetLastError() != 38 )
      goto LABEL_14;
    goto LABEL_6;
  }
  if ( ReadFile(v9, a3, a4, lpNumberOfBytesRead, 0) )
  {
LABEL_6:
    if ( *lpNumberOfBytesRead )
    {
      v10 = *((_QWORD *)this + 6);
      if ( v10 )
        *(_QWORD *)(v10 + 48) = &a2[*lpNumberOfBytesRead];
    }
    return 0;
  }
LABEL_14:
  LastError = GetLastError();
  return Win32ErrorToScode(LastError);
}

```

## disassembly

```asm
0x1800351dc  mov     [rsp+arg_0], rbx
0x1800351e1  mov     [rsp+arg_8], rsi
0x1800351e6  push    rdi
0x1800351e7  sub     rsp, 50h
0x1800351eb  mov     r10d, r9d
0x1800351ee  mov     r11, r8
0x1800351f1  mov     rdi, rdx
0x1800351f4  mov     rbx, rcx
0x1800351f7  test    r9d, r9d
0x1800351fa  jz      loc_1800352A7
0x180035200  mov     rcx, [rcx+30h]
0x180035204  xor     eax, eax
0x180035206  test    rcx, rcx
0x180035209  jz      short loc_180035212
0x18003520b  cmp     rdx, [rcx+30h]
0x18003520f  setz    al
0x180035212  mov     rsi, [rsp+58h+lpNumberOfBytesRead]
0x18003521a  mov     r8d, r10d; nNumberOfBytesToRead
0x18003521d  mov     rcx, [rbx+40h]; hFile
0x180035221  mov     r9, rsi; lpNumberOfBytesRead
0x180035224  mov     rdx, r11; lpBuffer
0x180035227  test    eax, eax
0x180035229  jnz     short loc_180035292
0x18003522b  mov     rax, rdi
0x18003522e  mov     [rsp+58h+Overlapped.Internal], 0
0x180035237  shr     rax, 20h
0x18003523b  mov     dword ptr [rsp+58h+Overlapped.10h+4], eax
0x18003523f  lea     rax, [rsp+58h+Overlapped]
0x180035244  mov     [rsp+58h+lpOverlapped], rax; lpOverlapped
0x180035249  mov     [rsp+58h+Overlapped.InternalHigh], 0
0x180035252  mov     dword ptr [rsp+58h+Overlapped.10h], edi
0x180035256  mov     [rsp+58h+Overlapped.hEvent], 0
0x18003525f  call    cs:__imp_ReadFile
0x180035265  test    eax, eax
0x180035267  jz      short loc_1800352B7
0x180035269  cmp     dword ptr [rsi], 0
0x18003526c  jbe     short loc_180035280
0x18003526e  mov     rcx, [rbx+30h]
0x180035272  test    rcx, rcx
0x180035275  jz      short loc_180035280
0x180035277  mov     eax, [rsi]
0x180035279  add     rax, rdi
0x18003527c  mov     [rcx+30h], rax
0x180035280  xor     eax, eax
0x180035282  mov     rbx, [rsp+58h+arg_0]
0x180035287  mov     rsi, [rsp+58h+arg_8]
0x18003528c  add     rsp, 50h
0x180035290  pop     rdi
0x180035291  retn
0x180035292  mov     [rsp+58h+lpOverlapped], 0; lpOverlapped
0x18003529b  call    cs:__imp_ReadFile
0x1800352a1  test    eax, eax
0x1800352a3  jnz     short loc_180035269
0x1800352a5  jmp     short loc_1800352C2
0x1800352a7  mov     rax, [rsp+58h+lpNumberOfBytesRead]
0x1800352af  mov     dword ptr [rax], 0
0x1800352b5  jmp     short loc_180035280
0x1800352b7  call    cs:__imp_GetLastError
0x1800352bd  cmp     eax, 26h ; '&'
0x1800352c0  jz      short loc_180035269
0x1800352c2  call    cs:__imp_GetLastError
0x1800352c8  mov     ecx, eax; unsigned int
0x1800352ca  call    ?Win32ErrorToScode@@YAJK@Z; Win32ErrorToScode(ulong)
0x1800352cf  jmp     short loc_180035282
```
