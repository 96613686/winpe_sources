# CreateFileStream(ushort const *,bool)

- ea: `0x180037e8c`
- end: `0x180037f50`
- name: `?CreateFileStream@@YAPEAUIStream@@PEBG_N@Z`
- size: `196`
- prototype: `struct IStream *__fastcall(const unsigned __int16 *, unsigned __int8)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x180036f3c`
- `0x1800371c8`

## callees

- `0x180006090`
- `0x180037e8c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180037edd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180037edd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180037f29`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180037f29`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180037ecc`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180037ecc`

## pseudocode

```c
struct IStream *__fastcall CreateFileStream(const unsigned __int16 *a1, unsigned __int8 a2)
{
  HANDLE FileW; // rdi
  _QWORD *v3; // rbx
  signed int LastError; // eax
  signed int v5; // ecx
  struct IStream *result; // rax

  if ( !a1 )
  {
    v5 = -2147024809;
LABEL_9:
    v3 = 0;
    goto LABEL_10;
  }
  FileW = CreateFileW(a1, ((a2 ^ 1u) + 1) << 30, 1u, 0, (a2 ^ 1u) + 2, 0x80u, 0);
  if ( FileW != (HANDLE)-1LL )
  {
    v3 = operator new(0x18u, (const struct std::nothrow_t *)&std::nothrow);
    if ( v3 )
    {
      v3[1] = FileW;
      *v3 = &FileStream::`vftable';
      v5 = 0;
      *((_DWORD *)v3 + 4) = 1;
      goto LABEL_10;
    }
    CloseHandle(FileW);
    v5 = -2147024882;
    goto LABEL_9;
  }
  v3 = 0;
  LastError = GetLastError();
  v5 = LastError;
  if ( LastError > 0 )
    v5 = (unsigned __int16)LastError | 0x80070000;
LABEL_10:
  result = 0;
  if ( v5 >= 0 )
    return (struct IStream *)v3;
  return result;
}

```

## disassembly

```asm
0x180037e8c  mov     [rsp+arg_0], rbx
0x180037e91  push    rdi
0x180037e92  sub     rsp, 40h
0x180037e96  test    rcx, rcx
0x180037e99  jz      loc_180037F36
0x180037e9f  movzx   eax, dl
0x180037ea2  xor     r9d, r9d; lpSecurityAttributes
0x180037ea5  xor     eax, 1
0x180037ea8  mov     [rsp+48h+hTemplateFile], 0; hTemplateFile
0x180037eb1  mov     [rsp+48h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x180037eb9  lea     r8d, [rax+2]
0x180037ebd  lea     edx, [rax+1]
0x180037ec0  mov     [rsp+48h+dwCreationDisposition], r8d; dwCreationDisposition
0x180037ec5  lea     r8d, [r9+1]; dwShareMode
0x180037ec9  shl     edx, 1Eh; dwDesiredAccess
0x180037ecc  call    cs:__imp_CreateFileW
0x180037ed2  mov     rdi, rax
0x180037ed5  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180037ed9  jnz     short loc_180037EF4
0x180037edb  xor     ebx, ebx
0x180037edd  call    cs:__imp_GetLastError
0x180037ee3  mov     ecx, eax
0x180037ee5  test    eax, eax
0x180037ee7  jle     short loc_180037F3D
0x180037ee9  movzx   ecx, ax
0x180037eec  or      ecx, 80070000h
0x180037ef2  jmp     short loc_180037F3D
0x180037ef4  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180037efb  mov     ecx, 18h; unsigned __int64
0x180037f00  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180037f05  mov     rbx, rax
0x180037f08  test    rax, rax
0x180037f0b  jz      short loc_180037F26
0x180037f0d  lea     rax, ??_7FileStream@@6B@; const FileStream::`vftable'
0x180037f14  mov     [rbx+8], rdi
0x180037f18  mov     [rbx], rax
0x180037f1b  xor     ecx, ecx
0x180037f1d  mov     dword ptr [rbx+10h], 1
0x180037f24  jmp     short loc_180037F3D
0x180037f26  mov     rcx, rdi; hObject
0x180037f29  call    cs:__imp_CloseHandle
0x180037f2f  mov     ecx, 8007000Eh
0x180037f34  jmp     short loc_180037F3B
0x180037f36  mov     ecx, 80070057h
0x180037f3b  xor     ebx, ebx
0x180037f3d  xor     eax, eax
0x180037f3f  test    ecx, ecx
0x180037f41  cmovns  rax, rbx
0x180037f45  mov     rbx, [rsp+48h+arg_0]
0x180037f4a  add     rsp, 40h
0x180037f4e  pop     rdi
0x180037f4f  retn
```
