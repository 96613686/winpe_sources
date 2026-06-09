# CFontAgent_General::Register(int)

- ea: `0x180008040`
- end: `0x180008097`
- name: `?Register@CFontAgent_General@@UEAAJH@Z`
- size: `87`
- prototype: `int(CFontAgent_General *__hidden this, int)`
- caller_count: `0`
- callee_count: `3`
- tags: `service_task`

## callees

- `0x180008040`
- `0x1800139f4`
- `0x180026704`

## import_xrefs

- `SHLWAPI!PathFindFileNameW` at `0x18000806e`
- `SHLWAPI!PathFindFileNameW` at `0x18000806e`

## pseudocode

```c
__int64 __fastcall CFontAgent_General::Register(CFontAgent_General *this, int a2)
{
  const WCHAR *FileNameW; // rbx
  unsigned int v5; // edi

  FileNameW = (const WCHAR *)((char *)this + 840);
  v5 = -2147467259;
  if ( PathIsInFontsDirectory(1, (const unsigned __int16 *)this + 420) )
    FileNameW = PathFindFileNameW(FileNameW);
  if ( FileNameW )
    return (unsigned int)Reg_InsertGeneralFontEntry(a2, (const unsigned __int16 *)this + 4, FileNameW);
  return v5;
}

```

## disassembly

```asm
0x180008040  push    rbx
0x180008042  push    rbp
0x180008043  push    rsi
0x180008044  push    rdi
0x180008045  sub     rsp, 28h
0x180008049  lea     rbx, [rcx+348h]
0x180008050  mov     ebp, edx
0x180008052  mov     rsi, rcx
0x180008055  mov     rdx, rbx; unsigned __int16 *
0x180008058  mov     ecx, 1; int
0x18000805d  mov     edi, 80004005h
0x180008062  call    ?PathIsInFontsDirectory@@YA_NHPEBG@Z; PathIsInFontsDirectory(int,ushort const *)
0x180008067  test    al, al
0x180008069  jz      short loc_180008077
0x18000806b  mov     rcx, rbx; pszPath
0x18000806e  call    cs:__imp_PathFindFileNameW
0x180008074  mov     rbx, rax
0x180008077  test    rbx, rbx
0x18000807a  jz      short loc_18000808C
0x18000807c  lea     rdx, [rsi+8]; unsigned __int16 *
0x180008080  mov     r8, rbx; unsigned __int16 *
0x180008083  mov     ecx, ebp; int
0x180008085  call    ?Reg_InsertGeneralFontEntry@@YAJHPEBG0@Z; Reg_InsertGeneralFontEntry(int,ushort const *,ushort const *)
0x18000808a  mov     edi, eax
0x18000808c  mov     eax, edi
0x18000808e  add     rsp, 28h
0x180008092  pop     rdi
0x180008093  pop     rsi
0x180008094  pop     rbp
0x180008095  pop     rbx
0x180008096  retn
```
