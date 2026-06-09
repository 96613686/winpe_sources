# ErrUtilDeleteFile(x)

- ea: `0x1004650c`
- end: `0x10046562`
- name: `_ErrUtilDeleteFile@4`
- size: `86`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x100179a0`
- `0x1001a570`
- `0x10025c70`

## callees

- `0x10045e80`
- `0x1004650c`
- `0x10123110`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!DeleteFileA` at `0x10046542`
- `api-ms-win-core-file-l1-1-0!DeleteFileA` at `0x10046542`

## pseudocode

```c
int __thiscall ErrUtilDeleteFile(void *this)
{
  int v1; // esi
  CHAR FileName[260]; // [esp+4h] [ebp-108h] BYREF

  v1 = -1811;
  if ( ErrWideToMultiByteCb(this, FileName, 260) >= 0 )
    return DeleteFileA(FileName) ? 0 : -1811;
  return v1;
}

```

## disassembly

```asm
0x1004650c  mov     edi, edi
0x1004650e  push    ebp
0x1004650f  mov     ebp, esp
0x10046511  sub     esp, 108h
0x10046517  mov     eax, ___security_cookie
0x1004651c  xor     eax, ebp
0x1004651e  mov     [ebp+var_4], eax
0x10046521  push    esi
0x10046522  push    104h
0x10046527  lea     edx, [ebp+FileName]
0x1004652d  mov     esi, 0FFFFF8EDh
0x10046532  call    _ErrWideToMultiByteCb@12; ErrWideToMultiByteCb(x,x,x)
0x10046537  test    eax, eax
0x10046539  js      short loc_10046553
0x1004653b  lea     eax, [ebp+FileName]
0x10046541  push    eax; lpFileName
0x10046542  call    ds:__imp__DeleteFileA@4; DeleteFileA(x)
0x10046548  neg     eax
0x1004654a  sbb     eax, eax
0x1004654c  and     eax, 713h
0x10046551  add     esi, eax
0x10046553  mov     ecx, [ebp+var_4]
0x10046556  mov     eax, esi
0x10046558  xor     ecx, ebp; StackCookie
0x1004655a  pop     esi
0x1004655b  call    @__security_check_cookie@4; __security_check_cookie(x)
0x10046560  leave
0x10046561  retn
```
