# CFontIcon::GetIconLocation(uint,ushort *,uint,int *,uint *)

- ea: `0x180020b20`
- end: `0x180020bd7`
- name: `?GetIconLocation@CFontIcon@@UEAAJIPEAGIPEAHPEAI@Z`
- size: `183`
- prototype: `int(CFontIcon *__hidden this, unsigned int, unsigned __int16 *, unsigned int, int *, unsigned int *)`
- caller_count: `0`
- callee_count: `3`
- tags: `reparse_path, loader_planting`

## callees

- `0x180020b20`
- `0x180022810`
- `0x180022c58`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x180020b6d`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x180020b6d`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x180020b83`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x180020b83`

## string_xrefs

- `0x180020b79`: `fontext.dll`

## pseudocode

```c
__int64 __fastcall CFontIcon::GetIconLocation(
        const struct _ITEMIDLIST **this,
        __int64 a2,
        unsigned __int16 *a3,
        UINT a4,
        int *a5,
        unsigned int *a6)
{
  HRESULT v9; // ebx
  int v10; // r9d
  int v11; // eax

  v9 = -2147024809;
  if ( a3 )
  {
    if ( a4 )
    {
      if ( a5 )
      {
        if ( a6 )
        {
          v9 = -2147467259;
          if ( GetSystemDirectoryW(a3, a4) )
          {
            v9 = PathCchAppend(a3, a4, L"fontext.dll");
            if ( v9 >= 0 )
            {
              FID_IsFolder(this[2]);
              if ( FID_GetActivationStatus(this[2]) == 1 )
                v11 = -(v10 != 0) - 421;
              else
                v11 = -(v10 != 0) - 419;
              *a5 = v11;
              *a6 = 0;
            }
          }
        }
      }
    }
  }
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180020b20  push    rbx
0x180020b22  push    rbp
0x180020b23  push    rsi
0x180020b24  push    rdi
0x180020b25  push    r14
0x180020b27  push    r15
0x180020b29  sub     rsp, 28h
0x180020b2d  mov     edi, r9d
0x180020b30  mov     rbp, r8
0x180020b33  mov     r15, rcx
0x180020b36  mov     ebx, 80070057h
0x180020b3b  test    r8, r8
0x180020b3e  jz      loc_180020BC8
0x180020b44  test    r9d, r9d
0x180020b47  jz      short loc_180020BC8
0x180020b49  mov     rsi, [rsp+58h+arg_20]
0x180020b51  test    rsi, rsi
0x180020b54  jz      short loc_180020BC8
0x180020b56  mov     r14, [rsp+58h+arg_28]
0x180020b5e  test    r14, r14
0x180020b61  jz      short loc_180020BC8
0x180020b63  mov     edx, edi; uSize
0x180020b65  mov     rcx, r8; lpBuffer
0x180020b68  mov     ebx, 80004005h
0x180020b6d  call    cs:__imp_GetSystemDirectoryW
0x180020b73  test    eax, eax
0x180020b75  jz      short loc_180020BC8
0x180020b77  mov     edx, edi; cchPath
0x180020b79  lea     r8, c_szFontextDll; "fontext.dll"
0x180020b80  mov     rcx, rbp; pszPath
0x180020b83  call    cs:__imp_PathCchAppend
0x180020b89  mov     ebx, eax
0x180020b8b  test    eax, eax
0x180020b8d  js      short loc_180020BC8
0x180020b8f  mov     rcx, [r15+10h]; struct _ITEMIDLIST *
0x180020b93  call    ?FID_IsFolder@@YAHPEFBU_ITEMIDLIST@@@Z; FID_IsFolder(_ITEMIDLIST const *)
0x180020b98  mov     rcx, [r15+10h]; struct _ITEMIDLIST *
0x180020b9c  mov     r9d, eax
0x180020b9f  call    ?FID_GetActivationStatus@@YAKPEFBU_ITEMIDLIST@@@Z; FID_GetActivationStatus(_ITEMIDLIST const *)
0x180020ba4  cmp     eax, 1
0x180020ba7  jnz     short loc_180020BB5
0x180020ba9  neg     r9d
0x180020bac  sbb     eax, eax
0x180020bae  add     eax, 0FFFFFE5Bh
0x180020bb3  jmp     short loc_180020BBF
0x180020bb5  neg     r9d
0x180020bb8  sbb     eax, eax
0x180020bba  add     eax, 0FFFFFE5Dh
0x180020bbf  mov     [rsi], eax
0x180020bc1  mov     dword ptr [r14], 0
0x180020bc8  mov     eax, ebx
0x180020bca  add     rsp, 28h
0x180020bce  pop     r15
0x180020bd0  pop     r14
0x180020bd2  pop     rdi
0x180020bd3  pop     rsi
0x180020bd4  pop     rbp
0x180020bd5  pop     rbx
0x180020bd6  retn
```
