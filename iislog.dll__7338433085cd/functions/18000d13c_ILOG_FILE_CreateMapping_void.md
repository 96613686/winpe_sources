# ILOG_FILE::CreateMapping(void)

- ea: `0x18000d13c`
- end: `0x18000d1df`
- name: `?CreateMapping@ILOG_FILE@@AEAAHXZ`
- size: `163`
- prototype: `__int64 __fastcall(ILOG_FILE *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x18000d2f8`
- `0x18000d598`

## callees

- `0x18000d13c`
- `0x18000d1e8`

## import_xrefs

- `KERNEL32!SetLastError` at `0x18000d18d`
- `KERNEL32!SetLastError` at `0x18000d18d`
- `KERNEL32!CreateFileMappingA` at `0x18000d178`
- `KERNEL32!CreateFileMappingA` at `0x18000d178`
- `KERNEL32!MapViewOfFile` at `0x18000d1b6`
- `KERNEL32!MapViewOfFile` at `0x18000d1b6`

## pseudocode

```c
__int64 __fastcall ILOG_FILE::CreateMapping(ILOG_FILE *this)
{
  DWORD v2; // edi
  HANDLE FileMappingA; // rax
  LPVOID v5; // rax
  __int64 dwFileOffsetHigh; // [rsp+40h] [rbp+8h]

  dwFileOffsetHigh = *((_QWORD *)this + 5);
  v2 = dwFileOffsetHigh - (unsigned int)dwFileOffsetHigh % *((_DWORD *)this + 5);
  FileMappingA = CreateFileMappingA(*(HANDLE *)this, 0, 4u, *((_DWORD *)this + 15), *((_DWORD *)this + 14), 0);
  *((_QWORD *)this + 1) = FileMappingA;
  if ( !FileMappingA )
  {
    SetLastError(0x70u);
    return 0;
  }
  *((_DWORD *)this + 8) = *((_DWORD *)this + 10) - v2;
  v5 = MapViewOfFile(FileMappingA, 0xF001Fu, HIDWORD(dwFileOffsetHigh), v2, *((_DWORD *)this + 14) - v2);
  *((_QWORD *)this + 3) = v5;
  if ( !v5 )
  {
    ILOG_FILE::DestroyMapping(this);
    return 0;
  }
  return 1;
}

```

## disassembly

```asm
0x18000d13c  mov     [rsp+arg_8], rbx
0x18000d141  push    rdi
0x18000d142  sub     rsp, 30h
0x18000d146  mov     rax, [rcx+28h]
0x18000d14a  xor     edx, edx
0x18000d14c  mov     r9d, [rcx+3Ch]; dwMaximumSizeHigh
0x18000d150  mov     edi, eax
0x18000d152  mov     qword ptr [rsp+38h+dwFileOffsetHigh], rax
0x18000d157  mov     rbx, rcx
0x18000d15a  div     dword ptr [rcx+14h]
0x18000d15d  mov     eax, [rcx+38h]
0x18000d160  mov     rcx, [rcx]; hFile
0x18000d163  sub     edi, edx
0x18000d165  xor     edx, edx; lpFileMappingAttributes
0x18000d167  mov     [rsp+38h+lpName], 0; lpName
0x18000d170  mov     [rsp+38h+dwMaximumSizeLow], eax; dwMaximumSizeLow
0x18000d174  lea     r8d, [rdx+4]; flProtect
0x18000d178  call    cs:__imp_CreateFileMappingA
0x18000d17e  mov     [rbx+8], rax
0x18000d182  mov     rcx, rax; hFileMappingObject
0x18000d185  test    rax, rax
0x18000d188  jnz     short loc_18000D197
0x18000d18a  lea     ecx, [rax+70h]; dwErrCode
0x18000d18d  call    cs:__imp_SetLastError
0x18000d193  xor     eax, eax
0x18000d195  jmp     short loc_18000D1D4
0x18000d197  mov     eax, [rbx+28h]
0x18000d19a  mov     r9d, edi; dwFileOffsetLow
0x18000d19d  mov     r8d, [rsp+44h]; dwFileOffsetHigh
0x18000d1a2  sub     eax, edi
0x18000d1a4  mov     [rbx+20h], eax
0x18000d1a7  mov     edx, 0F001Fh; dwDesiredAccess
0x18000d1ac  mov     eax, [rbx+38h]
0x18000d1af  sub     eax, edi
0x18000d1b1  mov     qword ptr [rsp+38h+dwMaximumSizeLow], rax; dwNumberOfBytesToMap
0x18000d1b6  call    cs:__imp_MapViewOfFile
0x18000d1bc  mov     [rbx+18h], rax
0x18000d1c0  test    rax, rax
0x18000d1c3  jnz     short loc_18000D1CF
0x18000d1c5  mov     rcx, rbx; this
0x18000d1c8  call    ?DestroyMapping@ILOG_FILE@@AEAAXXZ; ILOG_FILE::DestroyMapping(void)
0x18000d1cd  jmp     short loc_18000D193
0x18000d1cf  mov     eax, 1
0x18000d1d4  mov     rbx, [rsp+38h+arg_8]
0x18000d1d9  add     rsp, 30h
0x18000d1dd  pop     rdi
0x18000d1de  retn
```
