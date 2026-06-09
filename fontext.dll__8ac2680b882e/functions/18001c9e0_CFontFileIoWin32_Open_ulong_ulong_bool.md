# CFontFileIoWin32::Open(ulong,ulong,bool)

- ea: `0x18001c9e0`
- end: `0x18001ca5b`
- name: `?Open@CFontFileIoWin32@@UEAAKKK_N@Z`
- size: `123`
- prototype: `unsigned int(CFontFileIoWin32 *__hidden this, unsigned int, unsigned int, bool)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops`

## callees

- `0x18001c9e0`
- `0x180032010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ca46`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ca46`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18001ca36`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18001ca36`

## pseudocode

```c
__int64 __fastcall CFontFileIoWin32::Open(CFontFileIoWin32 *this, DWORD a2, DWORD a3, unsigned __int8 a4)
{
  int v5; // esi
  unsigned int v9; // ebx
  HANDLE FileW; // rax

  v5 = a4;
  if ( !*((_QWORD *)this + 1) )
    return 8;
  v9 = 0;
  (*(void (__fastcall **)(CFontFileIoWin32 *))(*(_QWORD *)this + 16LL))(this);
  FileW = CreateFileW(*((LPCWSTR *)this + 1), a2, a3, 0, (v5 ^ 1u) + 2, 0, 0);
  *((_QWORD *)this + 2) = FileW;
  if ( FileW == (HANDLE)-1LL )
    return GetLastError();
  return v9;
}

```

## disassembly

```asm
0x18001c9e0  push    rbx
0x18001c9e2  push    rbp
0x18001c9e3  push    rsi
0x18001c9e4  push    rdi
0x18001c9e5  push    r14
0x18001c9e7  sub     rsp, 40h
0x18001c9eb  cmp     qword ptr [rcx+8], 0
0x18001c9f0  mov     ebp, r8d
0x18001c9f3  movzx   esi, r9b
0x18001c9f7  mov     r14d, edx
0x18001c9fa  mov     rdi, rcx
0x18001c9fd  jnz     short loc_18001CA06
0x18001c9ff  mov     eax, 8
0x18001ca04  jmp     short loc_18001CA50
0x18001ca06  mov     rax, [rcx]
0x18001ca09  xor     ebx, ebx
0x18001ca0b  mov     rax, [rax+10h]
0x18001ca0f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ca14  mov     rcx, [rdi+8]; lpFileName
0x18001ca18  mov     eax, esi
0x18001ca1a  xor     eax, 1
0x18001ca1d  mov     [rsp+68h+hTemplateFile], rbx; hTemplateFile
0x18001ca22  add     eax, 2
0x18001ca25  mov     [rsp+68h+dwFlagsAndAttributes], ebx; dwFlagsAndAttributes
0x18001ca29  xor     r9d, r9d; lpSecurityAttributes
0x18001ca2c  mov     [rsp+68h+dwCreationDisposition], eax; dwCreationDisposition
0x18001ca30  mov     r8d, ebp; dwShareMode
0x18001ca33  mov     edx, r14d; dwDesiredAccess
0x18001ca36  call    cs:__imp_CreateFileW
0x18001ca3c  mov     [rdi+10h], rax
0x18001ca40  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18001ca44  jnz     short loc_18001CA4E
0x18001ca46  call    cs:__imp_GetLastError
0x18001ca4c  mov     ebx, eax
0x18001ca4e  mov     eax, ebx
0x18001ca50  add     rsp, 40h
0x18001ca54  pop     r14
0x18001ca56  pop     rdi
0x18001ca57  pop     rsi
0x18001ca58  pop     rbp
0x18001ca59  pop     rbx
0x18001ca5a  retn
```
