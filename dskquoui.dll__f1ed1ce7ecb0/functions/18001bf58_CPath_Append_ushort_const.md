# CPath::Append(ushort const *)

- ea: `0x18001bf58`
- end: `0x18001bfc2`
- name: `?Append@CPath@@QEAA_NPEBG@Z`
- size: `106`
- prototype: `bool __fastcall(CPath *__hidden this, LPCWSTR pszMore)`
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x18001230c`
- `0x180013b8c`
- `0x18001bec8`

## callees

- `0x18001a5f0`
- `0x18001a708`
- `0x18001a73c`

## import_xrefs

- `SHLWAPI!PathAppendW` at `0x18001bf9d`
- `SHLWAPI!PathAppendW` at `0x18001bf9d`
- `KERNEL32!lstrlenW` at `0x18001bf70`
- `KERNEL32!lstrlenW` at `0x18001bf70`

## pseudocode

```c
bool __fastcall CPath::Append(CPath *this, LPCWSTR pszMore)
{
  int v4; // ebx
  int v5; // edx
  WCHAR *Buffer; // rax
  bool v7; // bl

  v4 = lstrlenW(pszMore);
  v5 = v4 + CString::Length(this) + 3;
  if ( v5 < 260 )
    v5 = 260;
  Buffer = CString::GetBuffer(this, v5);
  v7 = PathAppendW(Buffer, pszMore);
  CString::ReleaseBuffer(this);
  return v7;
}

```

## disassembly

```asm
0x18001bf58  mov     [rsp+arg_0], rbx
0x18001bf5d  mov     [rsp+arg_8], rsi
0x18001bf62  push    rdi
0x18001bf63  sub     rsp, 20h
0x18001bf67  mov     rsi, rcx
0x18001bf6a  mov     rdi, rdx
0x18001bf6d  mov     rcx, rdx; lpString
0x18001bf70  call    cs:__imp_lstrlenW
0x18001bf76  mov     rcx, rsi; this
0x18001bf79  mov     ebx, eax
0x18001bf7b  call    ?Length@CString@@QEBAHXZ; CString::Length(void)
0x18001bf80  mov     rcx, rsi; this
0x18001bf83  lea     edx, [rax+3]
0x18001bf86  mov     eax, 104h
0x18001bf8b  add     edx, ebx
0x18001bf8d  cmp     edx, eax
0x18001bf8f  cmovl   edx, eax; int
0x18001bf92  call    ?GetBuffer@CString@@QEAAPEAGH@Z; CString::GetBuffer(int)
0x18001bf97  mov     rcx, rax; pszPath
0x18001bf9a  mov     rdx, rdi; pszMore
0x18001bf9d  call    cs:__imp_PathAppendW
0x18001bfa3  test    eax, eax
0x18001bfa5  mov     rcx, rsi; this
0x18001bfa8  setnz   bl
0x18001bfab  call    ?ReleaseBuffer@CString@@QEAAXXZ; CString::ReleaseBuffer(void)
0x18001bfb0  mov     rsi, [rsp+28h+arg_8]
0x18001bfb5  mov     al, bl
0x18001bfb7  mov     rbx, [rsp+28h+arg_0]
0x18001bfbc  add     rsp, 20h
0x18001bfc0  pop     rdi
0x18001bfc1  retn
```
