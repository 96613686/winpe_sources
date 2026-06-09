# ProfileIcon::~ProfileIcon(void)

- ea: `0x18004147c`
- end: `0x1800414a6`
- name: `??1ProfileIcon@@QEAA@XZ`
- size: `42`
- prototype: `void __fastcall(ProfileIcon *this)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x180044630`

## callees

- `0x180011844`
- `0x180011cfc`
- `0x18004147c`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180041493`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180041493`

## pseudocode

```c
void __fastcall ProfileIcon::~ProfileIcon(ProfileIcon *this)
{
  const WCHAR *v2; // rax

  if ( this->m_deleteOnDestruct )
  {
    v2 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&this->m_filePath._Mypair._Myval2);
    DeleteFileW(v2);
  }
  std::wstring::_Tidy_deallocate(&this->m_filePath);
}

```

## disassembly

```asm
0x18004147c  push    rbx
0x18004147e  sub     rsp, 20h
0x180041482  cmp     byte ptr [this+20h], 0
0x180041486  mov     rbx, this
0x180041489  jz      short loc_180041499
0x18004148b  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180041490  mov     this, rax; lpFileName
0x180041493  call    cs:__imp_DeleteFileW
0x180041499  mov     this, rbx
0x18004149c  add     rsp, 20h
0x1800414a0  pop     rbx
0x1800414a1  jmp     ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
```
