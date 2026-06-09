# ErrUtilDeleteFile(x)

- ea: `0x1004638c`
- end: `0x100463e2`
- name: `_ErrUtilDeleteFile@4`
- size: `86`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x10017860`
- `0x1001a430`
- `0x10025b10`

## callees

- `0x10045d00`
- `0x1004638c`
- `0x10122f60`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!DeleteFileA` at `0x100463c2`
- `api-ms-win-core-file-l1-1-0!DeleteFileA` at `0x100463c2`

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
0x1004638c  mov     edi, edi
0x1004638e  push    ebp
0x1004638f  mov     ebp, esp
0x10046391  sub     esp, 108h
0x10046397  mov     eax, ___security_cookie
0x1004639c  xor     eax, ebp
0x1004639e  mov     [ebp+var_4], eax
0x100463a1  push    esi
0x100463a2  push    104h
0x100463a7  lea     edx, [ebp+FileName]
0x100463ad  mov     esi, 0FFFFF8EDh
0x100463b2  call    _ErrWideToMultiByteCb@12; ErrWideToMultiByteCb(x,x,x)
0x100463b7  test    eax, eax
0x100463b9  js      short loc_100463D3
0x100463bb  lea     eax, [ebp+FileName]
0x100463c1  push    eax; lpFileName
0x100463c2  call    ds:__imp__DeleteFileA@4; DeleteFileA(x)
0x100463c8  neg     eax
0x100463ca  sbb     eax, eax
0x100463cc  and     eax, 713h
0x100463d1  add     esi, eax
0x100463d3  mov     ecx, [ebp+var_4]
0x100463d6  mov     eax, esi
0x100463d8  xor     ecx, ebp; StackCookie
0x100463da  pop     esi
0x100463db  call    @__security_check_cookie@4; __security_check_cookie(x)
0x100463e0  leave
0x100463e1  retn
```
