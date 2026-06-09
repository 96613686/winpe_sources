# CPath::RemoveRoot(void)

- ea: `0x18001c054`
- end: `0x18001c0be`
- name: `?RemoveRoot@CPath@@QEAAXXZ`
- size: `106`
- prototype: `void __fastcall(CPath *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18001bec8`

## callees

- `0x180019ee0`
- `0x180019f38`
- `0x18001bec8`
- `0x18001c054`

## import_xrefs

- `SHLWAPI!PathSkipRootW` at `0x18001c064`
- `SHLWAPI!PathSkipRootW` at `0x18001c064`

## pseudocode

```c
void __fastcall CPath::RemoveRoot(LPCWSTR **this)
{
  const unsigned __int16 *v2; // rax
  _QWORD v3[3]; // [rsp+30h] [rbp-18h] BYREF

  v2 = PathSkipRootW(*this[1]);
  if ( v2 )
  {
    CPath::CPath((CPath *)v3, v2, 0, 0, 0);
    if ( this != v3 )
      CString::operator=(this, v3);
    v3[0] = &CPath::`vftable';
    CString::~CString((CString *)v3);
  }
}

```

## disassembly

```asm
0x18001c054  push    rbx
0x18001c056  sub     rsp, 40h
0x18001c05a  mov     rbx, rcx
0x18001c05d  mov     rcx, [rcx+8]
0x18001c061  mov     rcx, [rcx]; pszPath
0x18001c064  call    cs:__imp_PathSkipRootW
0x18001c06a  test    rax, rax
0x18001c06d  jz      short loc_18001C0B8
0x18001c06f  xor     r9d, r9d; unsigned __int16 *
0x18001c072  mov     [rsp+48h+var_28], 0; unsigned __int16 *
0x18001c07b  xor     r8d, r8d; unsigned __int16 *
0x18001c07e  lea     rcx, [rsp+48h+var_18]; this
0x18001c083  mov     rdx, rax; unsigned __int16 *
0x18001c086  call    ??0CPath@@QEAA@PEBG000@Z; CPath::CPath(ushort const *,ushort const *,ushort const *,ushort const *)
0x18001c08b  lea     rax, [rsp+48h+var_18]
0x18001c090  cmp     rbx, rax
0x18001c093  jz      short loc_18001C0A2
0x18001c095  lea     rdx, [rsp+48h+var_18]
0x18001c09a  mov     rcx, rbx
0x18001c09d  call    ??4CString@@QEAAAEAV0@AEBV0@@Z; CString::operator=(CString const &)
0x18001c0a2  lea     rax, ??_7CPath@@6B@; const CPath::`vftable'
0x18001c0a9  lea     rcx, [rsp+48h+var_18]; this
0x18001c0ae  mov     [rsp+48h+var_18], rax
0x18001c0b3  call    ??1CString@@UEAA@XZ; CString::~CString(void)
0x18001c0b8  add     rsp, 40h
0x18001c0bc  pop     rbx
0x18001c0bd  retn
```
