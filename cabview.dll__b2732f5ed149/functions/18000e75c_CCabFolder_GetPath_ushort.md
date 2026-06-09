# CCabFolder::GetPath(ushort *)

- ea: `0x18000e75c`
- end: `0x18000e79c`
- name: `?GetPath@CCabFolder@@QEAAHPEAG@Z`
- size: `64`
- prototype: `int(CCabFolder *__hidden this, unsigned __int16 *)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x18000bfa4`
- `0x18000eb9c`
- `0x18000ef20`
- `0x180010440`

## callees

- `0x18000e75c`

## import_xrefs

- `SHELL32!SHGetPathFromIDListW` at `0x18000e76e`
- `SHELL32!SHGetPathFromIDListW` at `0x18000e76e`
- `api-ms-win-core-file-l1-1-0!GetShortPathNameW` at `0x18000e784`
- `api-ms-win-core-file-l1-1-0!GetShortPathNameW` at `0x18000e784`

## pseudocode

```c
__int64 __fastcall CCabFolder::GetPath(CCabFolder *this, unsigned __int16 *a2)
{
  const ITEMIDLIST *v2; // rcx
  __int64 result; // rax

  v2 = (const ITEMIDLIST *)*((_QWORD *)this + 6);
  if ( v2 && SHGetPathFromIDListW(v2, a2) )
  {
    GetShortPathNameW(a2, a2, 0x104u);
    return 1;
  }
  else
  {
    result = 0;
    *a2 = 0;
  }
  return result;
}

```

## disassembly

```asm
0x18000e75c  push    rbx
0x18000e75e  sub     rsp, 20h
0x18000e762  mov     rcx, [rcx+30h]; pidl
0x18000e766  mov     rbx, rdx
0x18000e769  test    rcx, rcx
0x18000e76c  jz      short loc_18000E791
0x18000e76e  call    cs:__imp_SHGetPathFromIDListW
0x18000e774  test    eax, eax
0x18000e776  jz      short loc_18000E791
0x18000e778  mov     r8d, 104h; cchBuffer
0x18000e77e  mov     rdx, rbx; lpszShortPath
0x18000e781  mov     rcx, rbx; lpszLongPath
0x18000e784  call    cs:__imp_GetShortPathNameW
0x18000e78a  mov     eax, 1
0x18000e78f  jmp     short loc_18000E796
0x18000e791  xor     eax, eax
0x18000e793  mov     [rbx], ax
0x18000e796  add     rsp, 20h
0x18000e79a  pop     rbx
0x18000e79b  retn
```
