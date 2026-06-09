# CPath::GetPath(CPath *)

- ea: `0x18001bfc8`
- end: `0x18001c04e`
- name: `?GetPath@CPath@@QEBA_NPEAV1@@Z`
- size: `134`
- prototype: `bool(CPath *__hidden this, struct CPath *)`
- caller_count: `2`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x180012b10`
- `0x180014220`

## callees

- `0x180019ee0`
- `0x180019f38`
- `0x18001a5f0`
- `0x18001a708`
- `0x18001a73c`
- `0x18001bfc8`

## import_xrefs

- `SHLWAPI!PathRemoveFileSpecW` at `0x18001bffd`
- `SHLWAPI!PathRemoveFileSpecW` at `0x18001bffd`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
bool __fastcall CPath::GetPath(CPath *this, void ***a2)
{
  WCHAR *Buffer; // rax
  bool v4; // bl
  void **v6; // [rsp+20h] [rbp-18h] BYREF
  __int64 v7; // [rsp+28h] [rbp-10h]

  v7 = *((_QWORD *)this + 1);
  _InterlockedIncrement((volatile signed __int32 *)(v7 + 12));
  v6 = &CPath::`vftable';
  Buffer = CString::GetBuffer((CString *)&v6, -1);
  PathRemoveFileSpecW(Buffer);
  CString::ReleaseBuffer((CString *)&v6);
  if ( a2 != &v6 )
    CString::operator=(a2, &v6);
  v4 = (int)CString::Length((CString *)a2) > 0;
  v6 = &CPath::`vftable';
  CString::~CString((CString *)&v6);
  return v4;
}

```

## disassembly

```asm
0x18001bfc8  mov     r11, rsp
0x18001bfcb  mov     [r11+8], rbx
0x18001bfcf  push    rdi
0x18001bfd0  sub     rsp, 30h
0x18001bfd4  mov     rbx, rdx
0x18001bfd7  mov     rax, [rcx+8]
0x18001bfdb  mov     [r11-10h], rax
0x18001bfdf  lock inc dword ptr [rax+0Ch]
0x18001bfe3  lea     rdi, ??_7CPath@@6B@; const CPath::`vftable'
0x18001bfea  mov     [r11-18h], rdi
0x18001bfee  or      edx, 0FFFFFFFFh; int
0x18001bff1  lea     rcx, [r11-18h]; this
0x18001bff5  call    ?GetBuffer@CString@@QEAAPEAGH@Z; CString::GetBuffer(int)
0x18001bffa  mov     rcx, rax; pszPath
0x18001bffd  call    cs:__imp_PathRemoveFileSpecW
0x18001c003  lea     rcx, [rsp+38h+var_18]; this
0x18001c008  call    ?ReleaseBuffer@CString@@QEAAXXZ; CString::ReleaseBuffer(void)
0x18001c00d  lea     rax, [rsp+38h+var_18]
0x18001c012  cmp     rbx, rax
0x18001c015  jz      short loc_18001C024
0x18001c017  lea     rdx, [rsp+38h+var_18]
0x18001c01c  mov     rcx, rbx
0x18001c01f  call    ??4CString@@QEAAAEAV0@AEBV0@@Z; CString::operator=(CString const &)
0x18001c024  mov     rcx, rbx; this
0x18001c027  call    ?Length@CString@@QEBAHXZ; CString::Length(void)
0x18001c02c  nop
0x18001c02d  test    eax, eax
0x18001c02f  setnle  bl
0x18001c032  mov     [rsp+38h+var_18], rdi
0x18001c037  lea     rcx, [rsp+38h+var_18]; this
0x18001c03c  call    ??1CString@@UEAA@XZ; CString::~CString(void)
0x18001c041  mov     al, bl
0x18001c043  mov     rbx, [rsp+38h+arg_0]
0x18001c048  add     rsp, 30h
0x18001c04c  pop     rdi
0x18001c04d  retn
```
