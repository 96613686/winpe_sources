# CFontFolderData::_CreateFileContents(tagSTGMEDIUM *,long)

- ea: `0x180012230`
- end: `0x1800122df`
- name: `?_CreateFileContents@CFontFolderData@@AEAAJPEAUtagSTGMEDIUM@@J@Z`
- size: `175`
- prototype: `HRESULT __fastcall(CFontFolderData *this, struct tagSTGMEDIUM *, int)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x180011c70`

## callees

- `0x180012230`
- `0x18002265c`
- `0x18003104a`
- `0x180031070`

## import_xrefs

- `SHLWAPI!SHCreateStreamOnFileW` at `0x1800122b0`
- `SHLWAPI!SHCreateStreamOnFileW` at `0x1800122b0`

## pseudocode

```c
HRESULT __fastcall CFontFolderData::_CreateFileContents(CFontFolderData *this, struct tagSTGMEDIUM *a2, int a3)
{
  int v3; // ebx
  unsigned int v6; // r9d
  WCHAR pszFile[264]; // [rsp+20h] [rbp-238h] BYREF

  v3 = a3;
  if ( a3 == -1 )
  {
    if ( *((_DWORD *)this + 310) != 1 )
      return -2147467259;
    v3 = 0;
  }
  a2->tymed = 4;
  a2->pUnkForRelease = 0;
  memset_0(pszFile, 0, 0x208u);
  if ( FID_FileName(*(const struct _ITEMIDLIST **)(*((_QWORD *)this + 154) + 8LL * v3), 0, pszFile, v6) < 0 )
    return -2147024882;
  else
    return SHCreateStreamOnFileW(pszFile, 0, &a2->pstm);
}

```

## disassembly

```asm
0x180012230  push    rbx
0x180012232  push    rsi
0x180012233  push    rdi
0x180012234  sub     rsp, 240h
0x18001223b  mov     rax, cs:__security_cookie
0x180012242  xor     rax, rsp
0x180012245  mov     [rsp+258h+var_28], rax
0x18001224d  mov     ebx, r8d
0x180012250  mov     rdi, rdx
0x180012253  mov     rsi, rcx
0x180012256  cmp     r8d, 0FFFFFFFFh
0x18001225a  jnz     short loc_180012267
0x18001225c  cmp     dword ptr [rcx+4D8h], 1
0x180012263  jnz     short loc_1800122B8
0x180012265  xor     ebx, ebx
0x180012267  mov     dword ptr [rdx], 4
0x18001226d  lea     rcx, [rsp+258h+pszFile]; void *
0x180012272  mov     qword ptr [rdx+10h], 0
0x18001227a  mov     r8d, 208h; Size
0x180012280  xor     edx, edx; Val
0x180012282  call    memset_0
0x180012287  mov     rcx, [rsi+4D0h]
0x18001228e  lea     r8, [rsp+258h+pszFile]; unsigned __int16 *
0x180012293  movsxd  rax, ebx
0x180012296  xor     edx, edx; unsigned int
0x180012298  mov     rcx, [rcx+rax*8]; struct _ITEMIDLIST *
0x18001229c  call    ?FID_FileName@@YAJPEFBU_ITEMIDLIST@@IPEAGI@Z; FID_FileName(_ITEMIDLIST const *,uint,ushort *,uint)
0x1800122a1  test    eax, eax
0x1800122a3  js      short loc_1800122BF
0x1800122a5  lea     r8, [rdi+8]; ppstm
0x1800122a9  xor     edx, edx; grfMode
0x1800122ab  lea     rcx, [rsp+258h+pszFile]; pszFile
0x1800122b0  call    cs:__imp_SHCreateStreamOnFileW
0x1800122b6  jmp     short loc_1800122C4
0x1800122b8  mov     eax, 80004005h
0x1800122bd  jmp     short loc_1800122C4
0x1800122bf  mov     eax, 8007000Eh
0x1800122c4  mov     rcx, [rsp+258h+var_28]
0x1800122cc  xor     rcx, rsp; StackCookie
0x1800122cf  call    __security_check_cookie
0x1800122d4  add     rsp, 240h
0x1800122db  pop     rdi
0x1800122dc  pop     rsi
0x1800122dd  pop     rbx
0x1800122de  retn
```
