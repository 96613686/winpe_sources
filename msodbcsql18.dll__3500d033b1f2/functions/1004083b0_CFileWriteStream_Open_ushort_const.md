# CFileWriteStream::Open(ushort const *)

- ea: `0x1004083b0`
- end: `0x100408479`
- name: `?Open@CFileWriteStream@@UEAAJPEBG@Z`
- size: `201`
- prototype: `int(CFileWriteStream *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x100409338`

## callees

- `0x1004083b0`
- `0x1005495d0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x10040842e`
- `KERNEL32!GetLastError` at `0x100408438`
- `KERNEL32!GetLastError` at `0x10040842e`
- `KERNEL32!GetLastError` at `0x100408438`
- `KERNEL32!CreateFileW` at `0x100408409`
- `KERNEL32!CreateFileW` at `0x100408409`
- `KERNEL32!GetFileSize` at `0x100408420`
- `KERNEL32!GetFileSize` at `0x100408420`

## pseudocode

```c
__int64 __fastcall CFileWriteStream::Open(CFileWriteStream *this, const unsigned __int16 *a2)
{
  unsigned int v3; // ebx
  HANDLE FileW; // rax
  DWORD FileSize; // eax
  signed int LastError; // eax

  v3 = 0;
  if ( !a2 || !*a2 )
  {
    v3 = -2147221303;
    goto LABEL_13;
  }
  if ( *((_QWORD *)this + 2) != -1 )
  {
    v3 = -2147221302;
LABEL_13:
    (*(void (__fastcall **)(CFileWriteStream *))(*(_QWORD *)this + 56LL))(this);
    return v3;
  }
  FileW = CreateFileW(a2, 0xC0000000, 1u, 0, 2u, 0x8100080u, 0);
  *((_QWORD *)this + 2) = FileW;
  if ( FileW == (HANDLE)-1LL
    || (FileSize = GetFileSize(FileW, (LPDWORD)this + 7), *((_DWORD *)this + 6) = FileSize, FileSize == -1)
    && GetLastError() )
  {
    LastError = GetLastError();
    v3 = (unsigned __int16)LastError | 0x80070000;
    if ( LastError <= 0 )
      v3 = LastError;
    if ( (v3 & 0x80000000) != 0 )
      goto LABEL_13;
  }
  return v3;
}

```

## disassembly

```asm
0x1004083b0  mov     [rsp+arg_0], rbx
0x1004083b5  mov     [rsp+arg_8], rsi
0x1004083ba  push    rdi
0x1004083bb  sub     rsp, 40h
0x1004083bf  xor     esi, esi
0x1004083c1  mov     rax, rdx
0x1004083c4  mov     rdi, rcx
0x1004083c7  mov     ebx, esi
0x1004083c9  test    rdx, rdx
0x1004083cc  jz      loc_100408452
0x1004083d2  cmp     [rdx], si
0x1004083d5  jz      short loc_100408452
0x1004083d7  cmp     qword ptr [rcx+10h], 0FFFFFFFFFFFFFFFFh
0x1004083dc  jz      short loc_1004083E5
0x1004083de  mov     ebx, 800400CAh
0x1004083e3  jmp     short loc_100408457
0x1004083e5  xor     r9d, r9d; lpSecurityAttributes
0x1004083e8  mov     [rsp+48h+hTemplateFile], rsi; hTemplateFile
0x1004083ed  mov     [rsp+48h+dwFlagsAndAttributes], 8100080h; dwFlagsAndAttributes
0x1004083f5  mov     edx, 0C0000000h; dwDesiredAccess
0x1004083fa  mov     rcx, rax; lpFileName
0x1004083fd  mov     [rsp+48h+dwCreationDisposition], 2; dwCreationDisposition
0x100408405  lea     r8d, [r9+1]; dwShareMode
0x100408409  call    cs:__imp_CreateFileW
0x10040840f  mov     [rdi+10h], rax
0x100408413  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x100408417  jz      short loc_100408438
0x100408419  lea     rdx, [rdi+1Ch]; lpFileSizeHigh
0x10040841d  mov     rcx, rax; hFile
0x100408420  call    cs:__imp_GetFileSize
0x100408426  mov     [rdi+18h], eax
0x100408429  cmp     eax, 0FFFFFFFFh
0x10040842c  jnz     short loc_100408467
0x10040842e  call    cs:__imp_GetLastError
0x100408434  test    eax, eax
0x100408436  jz      short loc_100408467
0x100408438  call    cs:__imp_GetLastError
0x10040843e  movzx   ebx, ax
0x100408441  or      ebx, 80070000h
0x100408447  test    eax, eax
0x100408449  cmovle  ebx, eax
0x10040844c  test    ebx, ebx
0x10040844e  jns     short loc_100408467
0x100408450  jmp     short loc_100408457
0x100408452  mov     ebx, 800400C9h
0x100408457  mov     rcx, [rdi]
0x10040845a  mov     rax, [rcx+38h]
0x10040845e  mov     rcx, rdi
0x100408461  call    cs:__guard_dispatch_icall_fptr
0x100408467  mov     rsi, [rsp+48h+arg_8]
0x10040846c  mov     eax, ebx
0x10040846e  mov     rbx, [rsp+48h+arg_0]
0x100408473  add     rsp, 40h
0x100408477  pop     rdi
0x100408478  retn
```
