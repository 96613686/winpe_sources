# xp::XmlReader::CreateFileStream(wchar_t const *,IStream * *)

- ea: `0x180035288`
- end: `0x180035332`
- name: `?CreateFileStream@XmlReader@xp@@SAJPEB_WPEAPEAUIStream@@@Z`
- size: `170`
- prototype: `__int64 __fastcall(const wchar_t *, struct IStream **)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops, registry_config`

## callers

- `0x180039000`
- `0x1800390c8`

## callees

- `0x180020c74`
- `0x18003260c`
- `0x180035288`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800352bd`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800352bd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800352ce`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800352ce`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180035314`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180035314`

## pseudocode

```c
signed int __fastcall xp::XmlReader::CreateFileStream(const wchar_t *a1, struct IStream **a2)
{
  HANDLE FileW; // rdi
  struct IStream *v4; // rbx
  signed int result; // eax
  xp::XmlReader::FileStream *v6; // rax

  FileW = CreateFileW(a1, 0x80000000, 1u, 0, 3u, 0x80u, 0);
  if ( FileW != (HANDLE)-1LL )
  {
    v6 = (xp::XmlReader::FileStream *)operator new(0x18u, (const struct std::nothrow_t *)&std::nothrow);
    if ( v6 )
    {
      v4 = (struct IStream *)xp::XmlReader::FileStream::FileStream(v6, FileW);
      if ( v4 )
      {
        result = 0;
        goto LABEL_9;
      }
    }
    else
    {
      v4 = 0;
    }
    CloseHandle(FileW);
    result = -2147024882;
    goto LABEL_9;
  }
  v4 = 0;
  result = GetLastError();
  if ( result > 0 )
    result = (unsigned __int16)result | 0x80070000;
LABEL_9:
  *a2 = v4;
  return result;
}

```

## disassembly

```asm
0x180035288  mov     rax, rsp
0x18003528b  mov     [rax+8], rbx
0x18003528f  mov     [rax+10h], rsi
0x180035293  push    rdi
0x180035294  sub     rsp, 40h
0x180035298  mov     qword ptr [rax-18h], 0
0x1800352a0  xor     r9d, r9d; lpSecurityAttributes
0x1800352a3  mov     rsi, rdx
0x1800352a6  mov     dword ptr [rax-20h], 80h
0x1800352ad  mov     edx, 80000000h; dwDesiredAccess
0x1800352b2  mov     dword ptr [rax-28h], 3
0x1800352b9  lea     r8d, [r9+1]; dwShareMode
0x1800352bd  call    cs:__imp_CreateFileW
0x1800352c3  mov     rdi, rax
0x1800352c6  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800352ca  jnz     short loc_1800352E2
0x1800352cc  xor     ebx, ebx
0x1800352ce  call    cs:__imp_GetLastError
0x1800352d4  test    eax, eax
0x1800352d6  jle     short loc_18003531F
0x1800352d8  movzx   eax, ax
0x1800352db  or      eax, 80070000h
0x1800352e0  jmp     short loc_18003531F
0x1800352e2  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800352e9  mov     ecx, 18h; unsigned __int64
0x1800352ee  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800352f3  test    rax, rax
0x1800352f6  jz      short loc_18003530F
0x1800352f8  mov     rdx, rdi; void *
0x1800352fb  mov     rcx, rax; this
0x1800352fe  call    ??0FileStream@XmlReader@xp@@QEAA@PEAX@Z; xp::XmlReader::FileStream::FileStream(void *)
0x180035303  mov     rbx, rax
0x180035306  test    rax, rax
0x180035309  jz      short loc_180035311
0x18003530b  xor     eax, eax
0x18003530d  jmp     short loc_18003531F
0x18003530f  xor     ebx, ebx
0x180035311  mov     rcx, rdi; hObject
0x180035314  call    cs:__imp_CloseHandle
0x18003531a  mov     eax, 8007000Eh
0x18003531f  mov     [rsi], rbx
0x180035322  mov     rbx, [rsp+48h+arg_0]
0x180035327  mov     rsi, [rsp+48h+arg_8]
0x18003532c  add     rsp, 40h
0x180035330  pop     rdi
0x180035331  retn
```
