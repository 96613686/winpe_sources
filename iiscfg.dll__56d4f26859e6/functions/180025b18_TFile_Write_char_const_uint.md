# TFile::Write(char const *,uint)

- ea: `0x180025b18`
- end: `0x180025b60`
- name: `?Write@TFile@@QEBAXPEBDI@Z`
- size: `72`
- prototype: `void __fastcall(TFile *__hidden this, const char *, unsigned int)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, registry_config`

## callers

- `0x1800232f0`

## callees

- `0x180017ad8`
- `0x180025b18`

## import_xrefs

- `KERNEL32!WriteFile` at `0x180025b36`
- `KERNEL32!WriteFile` at `0x180025b36`

## string_xrefs

- `0x180025b4e`: `inetsrv\iis\mb\config\src\core\schemagen\tfile.cpp`
- `0x180025b47`: `L"Write File Failed."`

## pseudocode

```c
void __fastcall TFile::Write(TFile *this, const char *a2, DWORD a3)
{
  void *v3; // rcx
  DWORD NumberOfBytesWritten; // [rsp+40h] [rbp+8h] BYREF

  v3 = (void *)*((_QWORD *)this + 1);
  NumberOfBytesWritten = 0;
  if ( !WriteFile(v3, a2, a3, &NumberOfBytesWritten, 0) )
    ThrowException(L"inetsrv\\iis\\mb\\config\\src\\core\\schemagen\\tfile.cpp", L"L\"Write File Failed.\"", 0x27u, 0);
}

```

## disassembly

```asm
0x180025b18  sub     rsp, 38h
0x180025b1c  mov     rcx, [rcx+8]; hFile
0x180025b20  lea     r9, [rsp+38h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x180025b25  mov     [rsp+38h+NumberOfBytesWritten], 0
0x180025b2d  mov     [rsp+38h+lpOverlapped], 0; lpOverlapped
0x180025b36  call    cs:__imp_WriteFile
0x180025b3c  test    eax, eax
0x180025b3e  jnz     short loc_180025B5B
0x180025b40  xor     r9d, r9d; unsigned int
0x180025b43  lea     r8d, [rax+27h]; unsigned int
0x180025b47  lea     rdx, aLWriteFileFail; "L\"Write File Failed.\""
0x180025b4e  lea     rcx, aInetsrvIisMbCo_0; "inetsrv\\iis\\mb\\config\\src\\core\\sc"...
0x180025b55  call    ?ThrowException@@YAXPEBG0II@Z; ThrowException(ushort const *,ushort const *,uint,uint)
0x180025b5b  add     rsp, 38h
0x180025b5f  retn
```
