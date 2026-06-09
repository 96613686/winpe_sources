# CFontAgent_Type1::Register(int)

- ea: `0x180008120`
- end: `0x18000818f`
- name: `?Register@CFontAgent_Type1@@UEAAJH@Z`
- size: `111`
- prototype: `int(CFontAgent_Type1 *__hidden this, int)`
- caller_count: `0`
- callee_count: `3`
- tags: `service_task`

## callees

- `0x180008120`
- `0x1800139f4`
- `0x18002680c`

## import_xrefs

- `SHLWAPI!PathFindFileNameW` at `0x180008150`
- `SHLWAPI!PathFindFileNameW` at `0x18000816d`
- `SHLWAPI!PathFindFileNameW` at `0x180008150`
- `SHLWAPI!PathFindFileNameW` at `0x18000816d`

## pseudocode

```c
__int64 __fastcall CFontAgent_Type1::Register(CFontAgent_Type1 *this, int a2)
{
  const WCHAR *FileNameW; // rdi
  const WCHAR *v5; // rbx

  FileNameW = (const WCHAR *)((char *)this + 840);
  v5 = (const WCHAR *)((char *)this + 1360);
  if ( PathIsInFontsDirectory(1, (const unsigned __int16 *)this + 420) )
    FileNameW = PathFindFileNameW(FileNameW);
  if ( PathIsInFontsDirectory(1, v5) )
    v5 = PathFindFileNameW(v5);
  return Reg_InsertType1FontEntry(a2, (const unsigned __int16 *)this + 4, FileNameW, v5);
}

```

## disassembly

```asm
0x180008120  push    rbx
0x180008122  push    rbp
0x180008123  push    rsi
0x180008124  push    rdi
0x180008125  sub     rsp, 28h
0x180008129  lea     rdi, [rcx+348h]
0x180008130  mov     ebp, edx
0x180008132  mov     rsi, rcx
0x180008135  lea     rbx, [rcx+550h]
0x18000813c  mov     rdx, rdi; unsigned __int16 *
0x18000813f  mov     ecx, 1; int
0x180008144  call    ?PathIsInFontsDirectory@@YA_NHPEBG@Z; PathIsInFontsDirectory(int,ushort const *)
0x180008149  test    al, al
0x18000814b  jz      short loc_180008159
0x18000814d  mov     rcx, rdi; pszPath
0x180008150  call    cs:__imp_PathFindFileNameW
0x180008156  mov     rdi, rax
0x180008159  mov     rdx, rbx; unsigned __int16 *
0x18000815c  mov     ecx, 1; int
0x180008161  call    ?PathIsInFontsDirectory@@YA_NHPEBG@Z; PathIsInFontsDirectory(int,ushort const *)
0x180008166  test    al, al
0x180008168  jz      short loc_180008176
0x18000816a  mov     rcx, rbx; pszPath
0x18000816d  call    cs:__imp_PathFindFileNameW
0x180008173  mov     rbx, rax
0x180008176  lea     rdx, [rsi+8]; unsigned __int16 *
0x18000817a  mov     r9, rbx; unsigned __int16 *
0x18000817d  mov     r8, rdi; unsigned __int16 *
0x180008180  mov     ecx, ebp; int
0x180008182  add     rsp, 28h
0x180008186  pop     rdi
0x180008187  pop     rsi
0x180008188  pop     rbp
0x180008189  pop     rbx
0x18000818a  jmp     ?Reg_InsertType1FontEntry@@YAJHPEBG00@Z; Reg_InsertType1FontEntry(int,ushort const *,ushort const *,ushort const *)
```
