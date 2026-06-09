# CMemFileWriter::~CMemFileWriter(void)

- ea: `0x180129710`
- end: `0x1801297d3`
- name: `??1CMemFileWriter@@UEAA@XZ`
- size: `195`
- prototype: `void __fastcall(CMemFileWriter *__hidden this)`
- caller_count: `3`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x1801089a0`
- `0x180108a70`
- `0x180108be0`

## callees

- `0x180129710`

## import_xrefs

- `KERNEL32!UnmapViewOfFile` at `0x180129738`
- `KERNEL32!UnmapViewOfFile` at `0x180129738`
- `KERNEL32!SetFilePointer` at `0x180129766`
- `KERNEL32!SetFilePointer` at `0x180129766`
- `KERNEL32!SetEndOfFile` at `0x180129770`
- `KERNEL32!SetEndOfFile` at `0x180129770`
- `KERNEL32!CloseHandle` at `0x180129746`
- `KERNEL32!CloseHandle` at `0x180129797`
- `KERNEL32!CloseHandle` at `0x180129746`
- `KERNEL32!CloseHandle` at `0x180129797`

## pseudocode

```c
void __fastcall CMemFileWriter::~CMemFileWriter(CMemFileWriter *this)
{
  const void *v2; // rcx
  void *v3; // rcx
  __int64 v4; // rdx
  void *v5; // rcx
  void *v6; // rcx

  *(_QWORD *)this = &CMemFileWriter::`vftable';
  if ( *((_QWORD *)this + 5) )
  {
    v2 = (const void *)*((_QWORD *)this + 6);
    if ( v2 )
      UnmapViewOfFile(v2);
    v3 = (void *)*((_QWORD *)this + 5);
    *((_QWORD *)this + 6) = 0;
    CloseHandle(v3);
    v4 = *((_QWORD *)this + 8) + *((unsigned int *)this + 18);
    v5 = (void *)*((_QWORD *)this + 1);
    *((_QWORD *)this + 8) = v4;
    *((_QWORD *)this + 5) = 0;
    SetFilePointer(v5, v4, (PLONG)this + 17, 0);
  }
  SetEndOfFile(*((HANDLE *)this + 1));
  v6 = (void *)*((_QWORD *)this + 1);
  *((_DWORD *)this + 8) = 0;
  *((_QWORD *)this + 9) = 0;
  *((_QWORD *)this + 8) = -1;
  *((_QWORD *)this + 7) = -1;
  if ( v6 != (void *)-1LL )
  {
    CloseHandle(v6);
    *((_QWORD *)this + 1) = -1;
  }
  *((_QWORD *)this + 2) = -1;
  *((_DWORD *)this + 6) = 0;
  *(_QWORD *)this = &CFileWriter::`vftable';
  *((_QWORD *)this + 2) = -1;
  *((_DWORD *)this + 6) = 0;
}

```

## disassembly

```asm
0x180129710  mov     [rsp+arg_0], rbx
0x180129715  push    rdi
0x180129716  sub     rsp, 20h
0x18012971a  xor     edi, edi
0x18012971c  lea     rax, ??_7CMemFileWriter@@6B@; const CMemFileWriter::`vftable'
0x180129723  mov     rbx, rcx
0x180129726  mov     [rcx], rax
0x180129729  cmp     [rcx+28h], rdi
0x18012972d  jz      short loc_18012976C
0x18012972f  mov     rcx, [rcx+30h]; lpBaseAddress
0x180129733  test    rcx, rcx
0x180129736  jz      short loc_18012973E
0x180129738  call    cs:__imp_UnmapViewOfFile
0x18012973e  mov     rcx, [rbx+28h]; hObject
0x180129742  mov     [rbx+30h], rdi
0x180129746  call    cs:__imp_CloseHandle
0x18012974c  mov     edx, [rbx+48h]
0x18012974f  lea     r8, [rbx+44h]; lpDistanceToMoveHigh
0x180129753  add     rdx, [rbx+40h]; lDistanceToMove
0x180129757  xor     r9d, r9d; dwMoveMethod
0x18012975a  mov     rcx, [rbx+8]; hFile
0x18012975e  mov     [rbx+40h], rdx
0x180129762  mov     [rbx+28h], rdi
0x180129766  call    cs:__imp_SetFilePointer
0x18012976c  mov     rcx, [rbx+8]; hFile
0x180129770  call    cs:__imp_SetEndOfFile
0x180129776  mov     rcx, [rbx+8]; hObject
0x18012977a  mov     [rbx+20h], edi
0x18012977d  mov     [rbx+48h], rdi
0x180129781  mov     qword ptr [rbx+40h], 0FFFFFFFFFFFFFFFFh
0x180129789  mov     qword ptr [rbx+38h], 0FFFFFFFFFFFFFFFFh
0x180129791  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180129795  jz      short loc_1801297A5
0x180129797  call    cs:__imp_CloseHandle
0x18012979d  mov     qword ptr [rbx+8], 0FFFFFFFFFFFFFFFFh
0x1801297a5  lea     rcx, [rbx+10h]
0x1801297a9  mov     r10, 0FFFFFFFFFFFFFFFFh
0x1801297b0  mov     [rcx], r10
0x1801297b3  lea     rdx, [rbx+18h]
0x1801297b7  mov     [rdx], edi
0x1801297b9  lea     rax, ??_7CFileWriter@@6B@; const CFileWriter::`vftable'
0x1801297c0  mov     [rbx], rax
0x1801297c3  mov     rbx, [rsp+28h+arg_0]
0x1801297c8  mov     [rcx], r10
0x1801297cb  mov     [rdx], edi
0x1801297cd  add     rsp, 20h
0x1801297d1  pop     rdi
0x1801297d2  retn
```
