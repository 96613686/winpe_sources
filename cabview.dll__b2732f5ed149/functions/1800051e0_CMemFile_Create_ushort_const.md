# CMemFile::Create(ushort const *)

- ea: `0x1800051e0`
- end: `0x180005276`
- name: `?Create@CMemFile@@QEAAHPEBG@Z`
- size: `150`
- prototype: `int(CMemFile *__hidden this, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x180004a70`
- `0x180004e50`

## callees

- `0x1800051e0`
- `0x18001226c`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x180005207`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x180005207`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180005259`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180005259`

## pseudocode

```c
bool __fastcall CMemFile::Create(CMemFile *this, WCHAR *a2)
{
  _QWORD *v2; // rax
  HGLOBAL *v5; // rbx
  bool v6; // zf

  v2 = (_QWORD *)*((_QWORD *)this + 1);
  if ( !v2 )
  {
    if ( *(_QWORD *)this == -1 )
    {
      if ( !PathIsInvalidW(a2) )
        *(_QWORD *)this = CreateFileW(a2, 0xC0000000, 1u, 0, 2u, 0x80u, 0);
      v6 = *(_QWORD *)this == -1;
      return !v6;
    }
    return 0;
  }
  if ( *v2 )
    return 0;
  v5 = (HGLOBAL *)*((_QWORD *)this + 1);
  *v5 = GlobalAlloc(0, *((unsigned int *)this + 4));
  v6 = **((_QWORD **)this + 1) == 0;
  return !v6;
}

```

## disassembly

```asm
0x1800051e0  mov     [rsp+arg_0], rbx
0x1800051e5  push    rdi
0x1800051e6  sub     rsp, 40h
0x1800051ea  mov     rax, [rcx+8]
0x1800051ee  mov     rbx, rdx
0x1800051f1  mov     rdi, rcx
0x1800051f4  test    rax, rax
0x1800051f7  jz      short loc_18000521B
0x1800051f9  cmp     qword ptr [rax], 0
0x1800051fd  jnz     short loc_180005221
0x1800051ff  mov     edx, [rcx+10h]; dwBytes
0x180005202  mov     rbx, rax
0x180005205  xor     ecx, ecx; uFlags
0x180005207  call    cs:__imp_GlobalAlloc
0x18000520d  mov     [rbx], rax
0x180005210  xor     eax, eax
0x180005212  mov     rcx, [rdi+8]
0x180005216  cmp     [rcx], rax
0x180005219  jmp     short loc_180005268
0x18000521b  cmp     qword ptr [rcx], 0FFFFFFFFFFFFFFFFh
0x18000521f  jz      short loc_180005225
0x180005221  xor     eax, eax
0x180005223  jmp     short loc_18000526B
0x180005225  mov     rcx, rbx; unsigned __int16 *
0x180005228  call    PathIsInvalidW
0x18000522d  test    eax, eax
0x18000522f  jnz     short loc_180005262
0x180005231  mov     [rsp+48h+hTemplateFile], 0; hTemplateFile
0x18000523a  lea     r8d, [rax+1]; dwShareMode
0x18000523e  mov     [rsp+48h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x180005246  xor     r9d, r9d; lpSecurityAttributes
0x180005249  mov     edx, 0C0000000h; dwDesiredAccess
0x18000524e  mov     [rsp+48h+dwCreationDisposition], 2; dwCreationDisposition
0x180005256  mov     rcx, rbx; lpFileName
0x180005259  call    cs:__imp_CreateFileW
0x18000525f  mov     [rdi], rax
0x180005262  xor     eax, eax
0x180005264  cmp     qword ptr [rdi], 0FFFFFFFFFFFFFFFFh
0x180005268  setnz   al
0x18000526b  mov     rbx, [rsp+48h+arg_0]
0x180005270  add     rsp, 40h
0x180005274  pop     rdi
0x180005275  retn
```
