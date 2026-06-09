# CFileReadStream::Open(ushort const *)

- ea: `0x1004082e0`
- end: `0x1004083a9`
- name: `?Open@CFileReadStream@@UEAAJPEBG@Z`
- size: `201`
- prototype: `int(CFileReadStream *__hidden this, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x1004085bc`
- `0x100408cc8`

## callees

- `0x1004082e0`
- `0x1005495d0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x10040835e`
- `KERNEL32!GetLastError` at `0x100408368`
- `KERNEL32!GetLastError` at `0x10040835e`
- `KERNEL32!GetLastError` at `0x100408368`
- `KERNEL32!CreateFileW` at `0x100408339`
- `KERNEL32!CreateFileW` at `0x100408339`
- `KERNEL32!GetFileSize` at `0x100408350`
- `KERNEL32!GetFileSize` at `0x100408350`

## pseudocode

```c
__int64 __fastcall CFileReadStream::Open(CFileReadStream *this, const unsigned __int16 *a2)
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
    (*(void (__fastcall **)(CFileReadStream *))(*(_QWORD *)this + 56LL))(this);
    return v3;
  }
  FileW = CreateFileW(a2, 0x80000000, 1u, 0, 3u, 0x8100080u, 0);
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
0x1004082e0  mov     [rsp+arg_0], rbx
0x1004082e5  mov     [rsp+arg_8], rsi
0x1004082ea  push    rdi
0x1004082eb  sub     rsp, 40h
0x1004082ef  xor     esi, esi
0x1004082f1  mov     rax, rdx
0x1004082f4  mov     rdi, rcx
0x1004082f7  mov     ebx, esi
0x1004082f9  test    rdx, rdx
0x1004082fc  jz      loc_100408382
0x100408302  cmp     [rdx], si
0x100408305  jz      short loc_100408382
0x100408307  cmp     qword ptr [rcx+10h], 0FFFFFFFFFFFFFFFFh
0x10040830c  jz      short loc_100408315
0x10040830e  mov     ebx, 800400CAh
0x100408313  jmp     short loc_100408387
0x100408315  xor     r9d, r9d; lpSecurityAttributes
0x100408318  mov     [rsp+48h+hTemplateFile], rsi; hTemplateFile
0x10040831d  mov     [rsp+48h+dwFlagsAndAttributes], 8100080h; dwFlagsAndAttributes
0x100408325  mov     edx, 80000000h; dwDesiredAccess
0x10040832a  mov     rcx, rax; lpFileName
0x10040832d  mov     [rsp+48h+dwCreationDisposition], 3; dwCreationDisposition
0x100408335  lea     r8d, [r9+1]; dwShareMode
0x100408339  call    cs:__imp_CreateFileW
0x10040833f  mov     [rdi+10h], rax
0x100408343  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x100408347  jz      short loc_100408368
0x100408349  lea     rdx, [rdi+1Ch]; lpFileSizeHigh
0x10040834d  mov     rcx, rax; hFile
0x100408350  call    cs:__imp_GetFileSize
0x100408356  mov     [rdi+18h], eax
0x100408359  cmp     eax, 0FFFFFFFFh
0x10040835c  jnz     short loc_100408397
0x10040835e  call    cs:__imp_GetLastError
0x100408364  test    eax, eax
0x100408366  jz      short loc_100408397
0x100408368  call    cs:__imp_GetLastError
0x10040836e  movzx   ebx, ax
0x100408371  or      ebx, 80070000h
0x100408377  test    eax, eax
0x100408379  cmovle  ebx, eax
0x10040837c  test    ebx, ebx
0x10040837e  jns     short loc_100408397
0x100408380  jmp     short loc_100408387
0x100408382  mov     ebx, 800400C9h
0x100408387  mov     rcx, [rdi]
0x10040838a  mov     rax, [rcx+38h]
0x10040838e  mov     rcx, rdi
0x100408391  call    cs:__guard_dispatch_icall_fptr
0x100408397  mov     rsi, [rsp+48h+arg_8]
0x10040839c  mov     eax, ebx
0x10040839e  mov     rbx, [rsp+48h+arg_0]
0x1004083a3  add     rsp, 40h
0x1004083a7  pop     rdi
0x1004083a8  retn
```
