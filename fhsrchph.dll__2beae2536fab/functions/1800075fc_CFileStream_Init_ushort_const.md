# CFileStream::Init(ushort const *)

- ea: `0x1800075fc`
- end: `0x18000765c`
- name: `?Init@CFileStream@@QEAAJPEBG@Z`
- size: `96`
- prototype: `int __fastcall(CFileStream *this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x1800069b0`

## callees

- `0x1800075fc`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18000763c`
- `KERNEL32!GetLastError` at `0x18000763c`
- `KERNEL32!CreateFileW` at `0x180007630`
- `KERNEL32!CreateFileW` at `0x180007630`

## pseudocode

```c
int __fastcall CFileStream::Init(CFileStream *this, const unsigned __int16 *a2)
{
  HANDLE FileW; // rax
  int result; // eax

  FileW = CreateFileW(a2, 0x80100000, 7u, 0, 3u, 0x200080u, 0);
  if ( FileW == (HANDLE)-1LL )
  {
    result = GetLastError();
    if ( result > 0 )
      return (unsigned __int16)result | 0x80070000;
  }
  else
  {
    *((_QWORD *)this + 3) = FileW;
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x1800075fc  push    rbx
0x1800075fe  sub     rsp, 40h
0x180007602  mov     rax, rdx
0x180007605  mov     [rsp+48h+hTemplateFile], 0; hTemplateFile
0x18000760e  xor     r9d, r9d; lpSecurityAttributes
0x180007611  mov     [rsp+48h+dwFlagsAndAttributes], 200080h; dwFlagsAndAttributes
0x180007619  mov     rbx, rcx
0x18000761c  mov     [rsp+48h+dwCreationDisposition], 3; dwCreationDisposition
0x180007624  mov     edx, 80100000h; dwDesiredAccess
0x180007629  mov     rcx, rax; lpFileName
0x18000762c  lea     r8d, [r9+7]; dwShareMode
0x180007630  call    cs:__imp_CreateFileW
0x180007636  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000763a  jnz     short loc_180007650
0x18000763c  call    cs:__imp_GetLastError
0x180007642  test    eax, eax
0x180007644  jle     short loc_180007656
0x180007646  movzx   eax, ax
0x180007649  or      eax, 80070000h
0x18000764e  jmp     short loc_180007656
0x180007650  mov     [rbx+18h], rax
0x180007654  xor     eax, eax
0x180007656  add     rsp, 40h
0x18000765a  pop     rbx
0x18000765b  retn
```
