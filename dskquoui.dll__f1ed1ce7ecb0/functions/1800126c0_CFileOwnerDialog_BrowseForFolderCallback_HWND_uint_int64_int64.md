# CFileOwnerDialog::BrowseForFolderCallback(HWND__ *,uint,__int64,__int64)

- ea: `0x1800126c0`
- end: `0x180012703`
- name: `?BrowseForFolderCallback@CFileOwnerDialog@@CAHPEAUHWND__@@I_J1@Z`
- size: `67`
- prototype: `static int(HWND, unsigned int, __int64, __int64)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x1800126c0`
- `0x18001a5f0`
- `0x18001a73c`

## import_xrefs

- `SHELL32!SHGetPathFromIDListW` at `0x1800126e8`
- `SHELL32!SHGetPathFromIDListW` at `0x1800126e8`

## pseudocode

```c
__int64 __fastcall CFileOwnerDialog::BrowseForFolderCallback(HWND a1, int a2, const ITEMIDLIST *a3, CString *a4)
{
  WCHAR *Buffer; // rax

  if ( a2 == 2 )
  {
    Buffer = CString::GetBuffer(a4, 260);
    SHGetPathFromIDListW(a3, Buffer);
    CString::ReleaseBuffer(a4);
  }
  return 0;
}

```

## disassembly

```asm
0x1800126c0  mov     [rsp+arg_0], rbx
0x1800126c5  push    rdi
0x1800126c6  sub     rsp, 20h
0x1800126ca  mov     rbx, r9
0x1800126cd  mov     rdi, r8
0x1800126d0  cmp     edx, 2
0x1800126d3  jnz     short loc_1800126F6
0x1800126d5  mov     edx, 104h; int
0x1800126da  mov     rcx, rbx; this
0x1800126dd  call    ?GetBuffer@CString@@QEAAPEAGH@Z; CString::GetBuffer(int)
0x1800126e2  mov     rdx, rax; pszPath
0x1800126e5  mov     rcx, rdi; pidl
0x1800126e8  call    cs:__imp_SHGetPathFromIDListW
0x1800126ee  mov     rcx, rbx; this
0x1800126f1  call    ?ReleaseBuffer@CString@@QEAAXXZ; CString::ReleaseBuffer(void)
0x1800126f6  mov     rbx, [rsp+28h+arg_0]
0x1800126fb  xor     eax, eax
0x1800126fd  add     rsp, 20h
0x180012701  pop     rdi
0x180012702  retn
```
