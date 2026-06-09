# CMapViewOfFile::MapView(void)

- ea: `0x1801b4498`
- end: `0x1801b453b`
- name: `?MapView@CMapViewOfFile@@IEAAJXZ`
- size: `163`
- prototype: `__int64 __fastcall(CMapViewOfFile *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x1801b4594`

## callees

- `0x1801b4498`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801b451d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801b451d`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x1801b4502`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x1801b4502`
- `api-ms-win-core-kernel32-legacy-l1-1-0!CreateFileMappingA` at `0x1801b44d0`
- `api-ms-win-core-kernel32-legacy-l1-1-0!CreateFileMappingA` at `0x1801b44d0`

## pseudocode

```c
__int64 __fastcall CMapViewOfFile::MapView(CMapViewOfFile *this)
{
  void *v2; // rcx
  HANDLE FileMappingA; // rax
  LPVOID v4; // rax
  signed int LastError; // eax

  v2 = (void *)*((_QWORD *)this + 67);
  if ( v2 != (void *)-1LL )
  {
    FileMappingA = (HANDLE)*((_QWORD *)this + 69);
    if ( FileMappingA
      || (FileMappingA = CreateFileMappingA(v2, 0, 2u, 0, 0, 0), (*((_QWORD *)this + 69) = FileMappingA) != 0) )
    {
      if ( *((_QWORD *)this + 70) )
        return *((unsigned int *)this + 3);
      v4 = MapViewOfFile(FileMappingA, 4u, 0, 0, 0);
      *((_QWORD *)this + 70) = v4;
      if ( v4 )
      {
        *((_DWORD *)this + 3) = 0;
        return *((unsigned int *)this + 3);
      }
    }
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    *((_DWORD *)this + 3) = LastError;
  }
  return *((unsigned int *)this + 3);
}

```

## disassembly

```asm
0x1801b4498  push    rbx
0x1801b449a  sub     rsp, 30h
0x1801b449e  mov     rbx, rcx
0x1801b44a1  mov     rcx, [rcx+218h]; hFile
0x1801b44a8  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1801b44ac  jz      loc_1801B4532
0x1801b44b2  mov     rax, [rbx+228h]
0x1801b44b9  test    rax, rax
0x1801b44bc  jnz     short loc_1801B44E2
0x1801b44be  mov     [rsp+38h+lpName], rax; lpName
0x1801b44c3  lea     r8d, [rax+2]; flProtect
0x1801b44c7  xor     r9d, r9d; dwMaximumSizeHigh
0x1801b44ca  mov     [rsp+38h+dwMaximumSizeLow], eax; dwMaximumSizeLow
0x1801b44ce  xor     edx, edx; lpFileMappingAttributes
0x1801b44d0  call    cs:__imp_CreateFileMappingA
0x1801b44d6  mov     [rbx+228h], rax
0x1801b44dd  test    rax, rax
0x1801b44e0  jz      short loc_1801B451D
0x1801b44e2  cmp     qword ptr [rbx+230h], 0
0x1801b44ea  jnz     short loc_1801B4532
0x1801b44ec  xor     r9d, r9d; dwFileOffsetLow
0x1801b44ef  mov     qword ptr [rsp+38h+dwMaximumSizeLow], 0; dwNumberOfBytesToMap
0x1801b44f8  xor     r8d, r8d; dwFileOffsetHigh
0x1801b44fb  mov     rcx, rax; hFileMappingObject
0x1801b44fe  lea     edx, [r9+4]; dwDesiredAccess
0x1801b4502  call    cs:__imp_MapViewOfFile
0x1801b4508  mov     [rbx+230h], rax
0x1801b450f  test    rax, rax
0x1801b4512  jz      short loc_1801B451D
0x1801b4514  mov     dword ptr [rbx+0Ch], 0
0x1801b451b  jmp     short loc_1801B4532
0x1801b451d  call    cs:__imp_GetLastError
0x1801b4523  test    eax, eax
0x1801b4525  jle     short loc_1801B452F
0x1801b4527  movzx   eax, ax
0x1801b452a  or      eax, 80070000h
0x1801b452f  mov     [rbx+0Ch], eax
0x1801b4532  mov     eax, [rbx+0Ch]
0x1801b4535  add     rsp, 30h
0x1801b4539  pop     rbx
0x1801b453a  retn
```
