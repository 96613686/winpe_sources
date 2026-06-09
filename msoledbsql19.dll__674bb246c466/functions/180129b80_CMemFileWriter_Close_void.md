# CMemFileWriter::Close(void)

- ea: `0x180129b80`
- end: `0x180129c21`
- name: `?Close@CMemFileWriter@@MEAAXXZ`
- size: `161`
- prototype: `void __fastcall(CMemFileWriter *__hidden this)`
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops`

## callees

- `0x180129b80`

## import_xrefs

- `KERNEL32!UnmapViewOfFile` at `0x180129b9e`
- `KERNEL32!UnmapViewOfFile` at `0x180129b9e`
- `KERNEL32!SetFilePointer` at `0x180129bcc`
- `KERNEL32!SetFilePointer` at `0x180129bcc`
- `KERNEL32!SetEndOfFile` at `0x180129bd6`
- `KERNEL32!SetEndOfFile` at `0x180129bd6`
- `KERNEL32!CloseHandle` at `0x180129bac`
- `KERNEL32!CloseHandle` at `0x180129bfd`
- `KERNEL32!CloseHandle` at `0x180129bac`
- `KERNEL32!CloseHandle` at `0x180129bfd`

## pseudocode

```c
void __fastcall CMemFileWriter::Close(CMemFileWriter *this)
{
  const void *v2; // rcx
  void *v3; // rcx
  __int64 v4; // rdx
  void *v5; // rcx
  void *v6; // rcx

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
  *((_DWORD *)this + 6) = 0;
  *((_QWORD *)this + 2) = -1;
}

```

## disassembly

```asm
0x180129b80  mov     [rsp+arg_0], rbx
0x180129b85  push    rdi
0x180129b86  sub     rsp, 20h
0x180129b8a  xor     edi, edi
0x180129b8c  mov     rbx, rcx
0x180129b8f  cmp     [rcx+28h], rdi
0x180129b93  jz      short loc_180129BD2
0x180129b95  mov     rcx, [rcx+30h]; lpBaseAddress
0x180129b99  test    rcx, rcx
0x180129b9c  jz      short loc_180129BA4
0x180129b9e  call    cs:__imp_UnmapViewOfFile
0x180129ba4  mov     rcx, [rbx+28h]; hObject
0x180129ba8  mov     [rbx+30h], rdi
0x180129bac  call    cs:__imp_CloseHandle
0x180129bb2  mov     edx, [rbx+48h]
0x180129bb5  lea     r8, [rbx+44h]; lpDistanceToMoveHigh
0x180129bb9  add     rdx, [rbx+40h]; lDistanceToMove
0x180129bbd  xor     r9d, r9d; dwMoveMethod
0x180129bc0  mov     rcx, [rbx+8]; hFile
0x180129bc4  mov     [rbx+40h], rdx
0x180129bc8  mov     [rbx+28h], rdi
0x180129bcc  call    cs:__imp_SetFilePointer
0x180129bd2  mov     rcx, [rbx+8]; hFile
0x180129bd6  call    cs:__imp_SetEndOfFile
0x180129bdc  mov     rcx, [rbx+8]; hObject
0x180129be0  mov     [rbx+20h], edi
0x180129be3  mov     [rbx+48h], rdi
0x180129be7  mov     qword ptr [rbx+40h], 0FFFFFFFFFFFFFFFFh
0x180129bef  mov     qword ptr [rbx+38h], 0FFFFFFFFFFFFFFFFh
0x180129bf7  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180129bfb  jz      short loc_180129C0B
0x180129bfd  call    cs:__imp_CloseHandle
0x180129c03  mov     qword ptr [rbx+8], 0FFFFFFFFFFFFFFFFh
0x180129c0b  mov     [rbx+18h], edi
0x180129c0e  mov     qword ptr [rbx+10h], 0FFFFFFFFFFFFFFFFh
0x180129c16  mov     rbx, [rsp+28h+arg_0]
0x180129c1b  add     rsp, 20h
0x180129c1f  pop     rdi
0x180129c20  retn
```
