# DfsOpenReparseIndex(_UNICODE_STRING *,void * *)

- ea: `0x140025f18`
- end: `0x140026011`
- name: `?DfsOpenReparseIndex@@YAKPEAU_UNICODE_STRING@@PEAPEAX@Z`
- size: `249`
- prototype: `unsigned int __fastcall(struct _UNICODE_STRING *, void **)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, reparse_path`

## callers

- `0x140026018`

## callees

- `0x1400011c4`
- `0x1400011d0`
- `0x14001e4bc`
- `0x14001e548`
- `0x140025f18`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140025fdf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140025fdf`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x140025fc9`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x140025fc9`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathAddBackslashW` at `0x140025f83`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathAddBackslashW` at `0x140025f83`

## string_xrefs

- `0x140025f8f`: `$Extend\$Reparse:$R:$INDEX_ALLOCATION`

## pseudocode

```c
__int64 __fastcall DfsOpenReparseIndex(struct _UNICODE_STRING *a1, void **a2)
{
  __int64 Length; // rsi
  DWORD LastError; // ebx
  unsigned __int64 v6; // rsi
  unsigned __int16 *v7; // rax
  WCHAR *v8; // rdi
  int v9; // eax
  HANDLE FileW; // rax

  Length = a1->Length;
  LastError = 0;
  *a2 = (void *)-1LL;
  v6 = Length + 64;
  v7 = (unsigned __int16 *)operator new(saturated_mul(v6, 2u));
  v8 = v7;
  if ( v7 )
  {
    v9 = StringCchCopyW(v7, v6, a1->Buffer);
    if ( v9 < 0
      || (PathAddBackslashW(v8), v9 = StringCchCatW(v8, v6, L"$Extend\\$Reparse:$R:$INDEX_ALLOCATION"), v9 < 0) )
    {
      LastError = (unsigned __int16)v9;
    }
    else
    {
      FileW = CreateFileW(v8, 0x80000000, 1u, 0, 3u, 0x2020000u, 0);
      if ( FileW == (HANDLE)-1LL )
        LastError = GetLastError();
      else
        *a2 = FileW;
    }
    operator delete(v8);
  }
  else
  {
    return 8;
  }
  return LastError;
}

```

## disassembly

```asm
0x140025f18  mov     [rsp+arg_0], rbx
0x140025f1d  mov     [rsp+arg_8], rbp
0x140025f22  mov     [rsp+arg_10], rsi
0x140025f27  push    rdi
0x140025f28  push    r14
0x140025f2a  push    r15
0x140025f2c  sub     rsp, 40h
0x140025f30  movzx   esi, word ptr [rcx]
0x140025f33  or      r15, 0FFFFFFFFFFFFFFFFh
0x140025f37  xor     ebx, ebx
0x140025f39  mov     [rdx], r15
0x140025f3c  mov     r14, rdx
0x140025f3f  mov     rbp, rcx
0x140025f42  add     rsi, 40h ; '@'
0x140025f46  lea     eax, [rbx+2]
0x140025f49  mul     rsi
0x140025f4c  cmovo   rax, r15
0x140025f50  mov     rcx, rax; Size
0x140025f53  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140025f58  mov     rdi, rax
0x140025f5b  test    rax, rax
0x140025f5e  jnz     short loc_140025F68
0x140025f60  lea     ebx, [rax+8]
0x140025f63  jmp     loc_140025FF5
0x140025f68  mov     r8, [rbp+8]; unsigned __int16 *
0x140025f6c  mov     rdx, rsi; unsigned __int64
0x140025f6f  mov     rcx, rdi; unsigned __int16 *
0x140025f72  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x140025f77  test    eax, eax
0x140025f79  jns     short loc_140025F80
0x140025f7b  movzx   ebx, ax
0x140025f7e  jmp     short loc_140025FED
0x140025f80  mov     rcx, rdi; pszPath
0x140025f83  call    cs:__imp_PathAddBackslashW
0x140025f8a  nop     dword ptr [rax+rax+00h]
0x140025f8f  lea     r8, aExtendReparseR; "$Extend\\$Reparse:$R:$INDEX_ALLOCATION"
0x140025f96  mov     rdx, rsi; unsigned __int64
0x140025f99  mov     rcx, rdi; unsigned __int16 *
0x140025f9c  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x140025fa1  test    eax, eax
0x140025fa3  js      short loc_140025F7B
0x140025fa5  xor     r9d, r9d; lpSecurityAttributes
0x140025fa8  mov     [rsp+58h+hTemplateFile], rbx; hTemplateFile
0x140025fad  mov     [rsp+58h+dwFlagsAndAttributes], 2020000h; dwFlagsAndAttributes
0x140025fb5  mov     edx, 80000000h; dwDesiredAccess
0x140025fba  mov     rcx, rdi; lpFileName
0x140025fbd  mov     [rsp+58h+dwCreationDisposition], 3; dwCreationDisposition
0x140025fc5  lea     r8d, [r9+1]; dwShareMode
0x140025fc9  call    cs:__imp_CreateFileW
0x140025fd0  nop     dword ptr [rax+rax+00h]
0x140025fd5  cmp     rax, r15
0x140025fd8  jz      short loc_140025FDF
0x140025fda  mov     [r14], rax
0x140025fdd  jmp     short loc_140025FED
0x140025fdf  call    cs:__imp_GetLastError
0x140025fe6  nop     dword ptr [rax+rax+00h]
0x140025feb  mov     ebx, eax
0x140025fed  mov     rcx, rdi; Block
0x140025ff0  call    ??3@YAXPEAX@Z; operator delete(void *)
0x140025ff5  mov     rbp, [rsp+58h+arg_8]
0x140025ffa  mov     eax, ebx
0x140025ffc  mov     rbx, [rsp+58h+arg_0]
0x140026001  mov     rsi, [rsp+58h+arg_10]
0x140026006  add     rsp, 40h
0x14002600a  pop     r15
0x14002600c  pop     r14
0x14002600e  pop     rdi
0x14002600f  retn
```
