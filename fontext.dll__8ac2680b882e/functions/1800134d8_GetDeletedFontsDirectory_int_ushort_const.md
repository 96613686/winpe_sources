# GetDeletedFontsDirectory(int,ushort const * *)

- ea: `0x1800134d8`
- end: `0x1800135d4`
- name: `?GetDeletedFontsDirectory@@YAJHPEAPEBG@Z`
- size: `252`
- prototype: `__int64 __fastcall(int, const unsigned __int16 **)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x1800085ac`

## callees

- `0x180006598`
- `0x180006624`
- `0x1800134d8`
- `0x1800135dc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013591`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013591`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180013568`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180013587`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180013568`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180013587`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x1800135b8`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x1800135b8`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18001357a`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18001357a`

## string_xrefs

- `0x18001354d`: `\Deleted`

## pseudocode

```c
__int64 __fastcall GetDeletedFontsDirectory(int a1, unsigned __int16 **a2)
{
  __int16 v2; // r8
  unsigned __int16 *v3; // rdi
  signed int FontsDirectory; // ebx
  unsigned int v6; // r11d
  DWORD FileAttributesW; // esi
  signed int LastError; // eax
  unsigned __int16 *v10; // [rsp+58h] [rbp+10h] BYREF

  v2 = FileName;
  v3 = (unsigned __int16 *)&word_1800475F0;
  if ( a1 )
    v2 = word_1800475F0;
  else
    v3 = &FileName;
  FontsDirectory = 0;
  if ( v2 )
    goto LABEL_17;
  v10 = 0;
  FontsDirectory = GetFontsDirectory(a1, (const unsigned __int16 **)&v10);
  if ( FontsDirectory < 0 )
    goto LABEL_16;
  FontsDirectory = StringCchCopyW(v3, 0x104u, v10);
  if ( FontsDirectory < 0 )
    goto LABEL_16;
  FontsDirectory = StringCchCatW(v3, v6, L"\\Deleted");
  if ( FontsDirectory < 0 )
    goto LABEL_16;
  FileAttributesW = GetFileAttributesW(v3);
  if ( FileAttributesW != -1 )
    goto LABEL_14;
  if ( !CreateDirectoryW(v3, 0) )
  {
    LastError = GetLastError();
    FontsDirectory = LastError;
    if ( LastError > 0 )
      FontsDirectory = (unsigned __int16)LastError | 0x80070000;
    if ( FontsDirectory >= 0 )
      goto LABEL_14;
LABEL_16:
    *v3 = 0;
    goto LABEL_17;
  }
  FileAttributesW = GetFileAttributesW(v3);
LABEL_14:
  if ( (FileAttributesW & 2) == 0 )
    SetFileAttributesW(v3, FileAttributesW | 2);
LABEL_17:
  *a2 = v3;
  return (unsigned int)FontsDirectory;
}

```

## disassembly

```asm
0x1800134d8  push    rbx
0x1800134da  push    rsi
0x1800134db  push    rdi
0x1800134dc  push    r14
0x1800134de  sub     rsp, 28h
0x1800134e2  movzx   r8d, cs:FileName
0x1800134ea  lea     rax, FileName
0x1800134f1  test    ecx, ecx
0x1800134f3  lea     rdi, word_1800475F0
0x1800134fa  mov     r14, rdx
0x1800134fd  cmovnz  r8w, cs:word_1800475F0
0x180013506  cmovz   rdi, rax
0x18001350a  xor     ebx, ebx
0x18001350c  xor     eax, eax
0x18001350e  cmp     ax, r8w
0x180013512  jnz     loc_1800135C5
0x180013518  lea     rdx, [rsp+48h+arg_8]; unsigned __int16 **
0x18001351d  mov     [rsp+48h+arg_8], rax
0x180013522  call    ?GetFontsDirectory@@YAJHPEAPEBG@Z; GetFontsDirectory(int,ushort const * *)
0x180013527  mov     ebx, eax
0x180013529  test    eax, eax
0x18001352b  js      loc_1800135C0
0x180013531  mov     r8, [rsp+48h+arg_8]; unsigned __int16 *
0x180013536  mov     r11d, 104h
0x18001353c  mov     edx, r11d; unsigned __int64
0x18001353f  mov     rcx, rdi; unsigned __int16 *
0x180013542  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180013547  mov     ebx, eax
0x180013549  test    eax, eax
0x18001354b  js      short loc_1800135C0
0x18001354d  lea     r8, aDeleted; "\\Deleted"
0x180013554  mov     edx, r11d; unsigned __int64
0x180013557  mov     rcx, rdi; unsigned __int16 *
0x18001355a  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18001355f  mov     ebx, eax
0x180013561  test    eax, eax
0x180013563  js      short loc_1800135C0
0x180013565  mov     rcx, rdi; lpFileName
0x180013568  call    cs:__imp_GetFileAttributesW
0x18001356e  mov     esi, eax
0x180013570  cmp     eax, 0FFFFFFFFh
0x180013573  jnz     short loc_1800135AA
0x180013575  xor     edx, edx; lpSecurityAttributes
0x180013577  mov     rcx, rdi; lpPathName
0x18001357a  call    cs:__imp_CreateDirectoryW
0x180013580  test    eax, eax
0x180013582  jz      short loc_180013591
0x180013584  mov     rcx, rdi; lpFileName
0x180013587  call    cs:__imp_GetFileAttributesW
0x18001358d  mov     esi, eax
0x18001358f  jmp     short loc_1800135AA
0x180013591  call    cs:__imp_GetLastError
0x180013597  mov     ebx, eax
0x180013599  test    eax, eax
0x18001359b  jle     short loc_1800135A6
0x18001359d  movzx   ebx, ax
0x1800135a0  or      ebx, 80070000h
0x1800135a6  test    ebx, ebx
0x1800135a8  js      short loc_1800135C0
0x1800135aa  test    sil, 2
0x1800135ae  jnz     short loc_1800135C5
0x1800135b0  or      esi, 2
0x1800135b3  mov     rcx, rdi; lpFileName
0x1800135b6  mov     edx, esi; dwFileAttributes
0x1800135b8  call    cs:__imp_SetFileAttributesW
0x1800135be  jmp     short loc_1800135C5
0x1800135c0  xor     eax, eax
0x1800135c2  mov     [rdi], ax
0x1800135c5  mov     [r14], rdi
0x1800135c8  mov     eax, ebx
0x1800135ca  add     rsp, 28h
0x1800135ce  pop     r14
0x1800135d0  pop     rdi
0x1800135d1  pop     rsi
0x1800135d2  pop     rbx
0x1800135d3  retn
```
