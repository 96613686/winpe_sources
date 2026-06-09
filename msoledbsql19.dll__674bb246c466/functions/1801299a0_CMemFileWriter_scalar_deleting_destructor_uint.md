# CMemFileWriter::`scalar deleting destructor'(uint)

- ea: `0x1801299a0`
- end: `0x180129a9b`
- name: `??_GCMemFileWriter@@UEAAPEAXI@Z`
- size: `251`
- prototype: `void *__fastcall(CMemFileWriter *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops`

## callees

- `0x180003824`
- `0x1801299a0`

## import_xrefs

- `KERNEL32!UnmapViewOfFile` at `0x1801299d4`
- `KERNEL32!UnmapViewOfFile` at `0x1801299d4`
- `KERNEL32!SetFilePointer` at `0x180129a02`
- `KERNEL32!SetFilePointer` at `0x180129a02`
- `KERNEL32!SetEndOfFile` at `0x180129a0c`
- `KERNEL32!SetEndOfFile` at `0x180129a0c`
- `KERNEL32!CloseHandle` at `0x1801299e2`
- `KERNEL32!CloseHandle` at `0x180129a33`
- `KERNEL32!CloseHandle` at `0x1801299e2`
- `KERNEL32!CloseHandle` at `0x180129a33`

## pseudocode

```c
CMemFileWriter *__fastcall CMemFileWriter::`scalar deleting destructor'(CMemFileWriter *this, char a2)
{
  const void *v4; // rcx
  void *v5; // rcx
  __int64 v6; // rdx
  void *v7; // rcx
  void *v8; // rcx

  *(_QWORD *)this = &CMemFileWriter::`vftable';
  if ( *((_QWORD *)this + 5) )
  {
    v4 = (const void *)*((_QWORD *)this + 6);
    if ( v4 )
      UnmapViewOfFile(v4);
    v5 = (void *)*((_QWORD *)this + 5);
    *((_QWORD *)this + 6) = 0;
    CloseHandle(v5);
    v6 = *((_QWORD *)this + 8) + *((unsigned int *)this + 18);
    v7 = (void *)*((_QWORD *)this + 1);
    *((_QWORD *)this + 8) = v6;
    *((_QWORD *)this + 5) = 0;
    SetFilePointer(v7, v6, (PLONG)this + 17, 0);
  }
  SetEndOfFile(*((HANDLE *)this + 1));
  v8 = (void *)*((_QWORD *)this + 1);
  *((_DWORD *)this + 8) = 0;
  *((_QWORD *)this + 9) = 0;
  *((_QWORD *)this + 8) = -1;
  *((_QWORD *)this + 7) = -1;
  if ( v8 != (void *)-1LL )
  {
    CloseHandle(v8);
    *((_QWORD *)this + 1) = -1;
  }
  *((_QWORD *)this + 2) = -1;
  *((_DWORD *)this + 6) = 0;
  *(_QWORD *)this = &CFileWriter::`vftable';
  *((_QWORD *)this + 2) = -1;
  *((_DWORD *)this + 6) = 0;
  if ( (a2 & 1) != 0 )
    operator delete(this, 0x50u);
  return this;
}

```

## disassembly

```asm
0x1801299a0  mov     [rsp+arg_0], rbx
0x1801299a5  mov     [rsp+arg_8], rbp
0x1801299aa  mov     [rsp+arg_10], rsi
0x1801299af  push    rdi
0x1801299b0  sub     rsp, 20h
0x1801299b4  xor     ebp, ebp
0x1801299b6  lea     rax, ??_7CMemFileWriter@@6B@; const CMemFileWriter::`vftable'
0x1801299bd  mov     esi, edx
0x1801299bf  mov     rbx, rcx
0x1801299c2  mov     [rcx], rax
0x1801299c5  cmp     [rcx+28h], rbp
0x1801299c9  jz      short loc_180129A08
0x1801299cb  mov     rcx, [rcx+30h]; lpBaseAddress
0x1801299cf  test    rcx, rcx
0x1801299d2  jz      short loc_1801299DA
0x1801299d4  call    cs:__imp_UnmapViewOfFile
0x1801299da  mov     rcx, [rbx+28h]; hObject
0x1801299de  mov     [rbx+30h], rbp
0x1801299e2  call    cs:__imp_CloseHandle
0x1801299e8  mov     edx, [rbx+48h]
0x1801299eb  lea     r8, [rbx+44h]; lpDistanceToMoveHigh
0x1801299ef  add     rdx, [rbx+40h]; lDistanceToMove
0x1801299f3  xor     r9d, r9d; dwMoveMethod
0x1801299f6  mov     rcx, [rbx+8]; hFile
0x1801299fa  mov     [rbx+40h], rdx
0x1801299fe  mov     [rbx+28h], rbp
0x180129a02  call    cs:__imp_SetFilePointer
0x180129a08  mov     rcx, [rbx+8]; hFile
0x180129a0c  call    cs:__imp_SetEndOfFile
0x180129a12  mov     rcx, [rbx+8]; hObject
0x180129a16  mov     [rbx+20h], ebp
0x180129a19  mov     [rbx+48h], rbp
0x180129a1d  mov     qword ptr [rbx+40h], 0FFFFFFFFFFFFFFFFh
0x180129a25  mov     qword ptr [rbx+38h], 0FFFFFFFFFFFFFFFFh
0x180129a2d  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180129a31  jz      short loc_180129A41
0x180129a33  call    cs:__imp_CloseHandle
0x180129a39  mov     qword ptr [rbx+8], 0FFFFFFFFFFFFFFFFh
0x180129a41  lea     rcx, [rbx+10h]
0x180129a45  mov     r11, 0FFFFFFFFFFFFFFFFh
0x180129a4c  mov     [rcx], r11
0x180129a4f  lea     rdx, [rbx+18h]
0x180129a53  mov     [rdx], ebp
0x180129a55  lea     rax, ??_7CFileWriter@@6B@; const CFileWriter::`vftable'
0x180129a5c  mov     [rbx], rax
0x180129a5f  mov     rdi, rcx
0x180129a62  mov     [rcx], r11
0x180129a65  mov     r10, rdx
0x180129a68  mov     [rdx], ebp
0x180129a6a  mov     r9d, ebp
0x180129a6d  mov     r8, rbx
0x180129a70  test    sil, 1
0x180129a74  jz      short loc_180129A83
0x180129a76  mov     edx, 50h ; 'P'; unsigned __int64
0x180129a7b  mov     rcx, rbx; void *
0x180129a7e  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180129a83  mov     rbp, [rsp+28h+arg_8]
0x180129a88  mov     rax, rbx
0x180129a8b  mov     rbx, [rsp+28h+arg_0]
0x180129a90  mov     rsi, [rsp+28h+arg_10]
0x180129a95  add     rsp, 20h
0x180129a99  pop     rdi
0x180129a9a  retn
```
