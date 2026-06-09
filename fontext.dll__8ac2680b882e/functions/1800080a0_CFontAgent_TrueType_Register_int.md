# CFontAgent_TrueType::Register(int)

- ea: `0x1800080a0`
- end: `0x180008112`
- name: `?Register@CFontAgent_TrueType@@UEAAJH@Z`
- size: `114`
- prototype: `int(CFontAgent_TrueType *__hidden this, int)`
- caller_count: `0`
- callee_count: `4`
- tags: `service_task`

## callees

- `0x1800080a0`
- `0x1800139f4`
- `0x180026704`
- `0x180026780`

## import_xrefs

- `SHLWAPI!PathFindFileNameW` at `0x1800080d3`
- `SHLWAPI!PathFindFileNameW` at `0x1800080d3`

## pseudocode

```c
__int64 __fastcall CFontAgent_TrueType::Register(CFontAgent_TrueType *this, int a2)
{
  const WCHAR *FileNameW; // rbx
  unsigned int v5; // edi

  FileNameW = (const WCHAR *)((char *)this + 840);
  v5 = -2147467259;
  if ( PathIsInFontsDirectory(1, (const unsigned __int16 *)this + 420) )
    FileNameW = PathFindFileNameW(FileNameW);
  if ( FileNameW )
  {
    if ( *((_WORD *)this + 680) )
      return (unsigned int)Reg_InsertGeneralFontEntry(a2, (const unsigned __int16 *)this + 680, FileNameW);
    else
      return (unsigned int)Reg_InsertTrueTypeFontEntry(a2, (const unsigned __int16 *)this + 4, FileNameW);
  }
  return v5;
}

```

## disassembly

```asm
0x1800080a0  push    rbx
0x1800080a2  push    rbp
0x1800080a3  push    rsi
0x1800080a4  push    rdi
0x1800080a5  push    r14
0x1800080a7  sub     rsp, 20h
0x1800080ab  lea     rbx, [rcx+348h]
0x1800080b2  mov     ebp, edx
0x1800080b4  mov     rsi, rcx
0x1800080b7  mov     rdx, rbx; unsigned __int16 *
0x1800080ba  mov     ecx, 1; int
0x1800080bf  mov     edi, 80004005h
0x1800080c4  call    ?PathIsInFontsDirectory@@YA_NHPEBG@Z; PathIsInFontsDirectory(int,ushort const *)
0x1800080c9  xor     r14d, r14d
0x1800080cc  test    al, al
0x1800080ce  jz      short loc_1800080DC
0x1800080d0  mov     rcx, rbx; pszPath
0x1800080d3  call    cs:__imp_PathFindFileNameW
0x1800080d9  mov     rbx, rax
0x1800080dc  test    rbx, rbx
0x1800080df  jz      short loc_180008105
0x1800080e1  lea     rdx, [rsi+550h]; unsigned __int16 *
0x1800080e8  mov     r8, rbx; unsigned __int16 *
0x1800080eb  mov     ecx, ebp; int
0x1800080ed  cmp     [rdx], r14w
0x1800080f1  jnz     short loc_1800080FE
0x1800080f3  lea     rdx, [rsi+8]; unsigned __int16 *
0x1800080f7  call    ?Reg_InsertTrueTypeFontEntry@@YAJHPEBG0@Z; Reg_InsertTrueTypeFontEntry(int,ushort const *,ushort const *)
0x1800080fc  jmp     short loc_180008103
0x1800080fe  call    ?Reg_InsertGeneralFontEntry@@YAJHPEBG0@Z; Reg_InsertGeneralFontEntry(int,ushort const *,ushort const *)
0x180008103  mov     edi, eax
0x180008105  mov     eax, edi
0x180008107  add     rsp, 20h
0x18000810b  pop     r14
0x18000810d  pop     rdi
0x18000810e  pop     rsi
0x18000810f  pop     rbp
0x180008110  pop     rbx
0x180008111  retn
```
