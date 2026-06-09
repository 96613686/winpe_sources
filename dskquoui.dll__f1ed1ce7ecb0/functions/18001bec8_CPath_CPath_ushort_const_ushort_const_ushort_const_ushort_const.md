# CPath::CPath(ushort const *,ushort const *,ushort const *,ushort const *)

- ea: `0x18001bec8`
- end: `0x18001bf52`
- name: `??0CPath@@QEAA@PEBG000@Z`
- size: `138`
- prototype: `CPath *__fastcall(CPath *__hidden this, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `4`
- callee_count: `6`
- tags: ``

## callers

- `0x180011d08`
- `0x1800121a4`
- `0x180013b8c`
- `0x18001c054`

## callees

- `0x180019dd0`
- `0x180019ee0`
- `0x180019fb0`
- `0x18001bec8`
- `0x18001bf58`
- `0x18001c054`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
CPath *__fastcall CPath::CPath(
        CPath *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4)
{
  LPCWSTR *v7; // [rsp+20h] [rbp-18h] BYREF
  __int64 v8; // [rsp+28h] [rbp-10h]

  CString::CString(this);
  *(_QWORD *)this = &CPath::`vftable';
  if ( a2 )
  {
    v8 = *((_QWORD *)this + 1);
    _InterlockedIncrement((volatile signed __int32 *)(v8 + 12));
    v7 = (LPCWSTR *)&CPath::`vftable';
    CPath::RemoveRoot(&v7);
    CString::operator=(this, a2);
    CPath::Append(this, *(LPCWSTR *)v8);
    v7 = (LPCWSTR *)&CPath::`vftable';
    CString::~CString((CString *)&v7);
  }
  return this;
}

```

## disassembly

```asm
0x18001bec8  mov     [rsp+arg_8], rbx
0x18001becd  mov     [rsp+arg_10], rsi
0x18001bed2  mov     [rsp+arg_0], rcx
0x18001bed7  push    rdi
0x18001bed8  sub     rsp, 30h
0x18001bedc  mov     rdi, rdx
0x18001bedf  mov     rbx, rcx
0x18001bee2  call    ??0CString@@QEAA@XZ; CString::CString(void)
0x18001bee7  nop
0x18001bee8  lea     rsi, ??_7CPath@@6B@; const CPath::`vftable'
0x18001beef  mov     [rbx], rsi
0x18001bef2  test    rdi, rdi
0x18001bef5  jz      short loc_18001BF3F
0x18001bef7  mov     rax, [rbx+8]
0x18001befb  mov     [rsp+38h+var_10], rax
0x18001bf00  lock inc dword ptr [rax+0Ch]
0x18001bf04  mov     [rsp+38h+var_18], rsi
0x18001bf09  lea     rcx, [rsp+38h+var_18]; this
0x18001bf0e  call    ?RemoveRoot@CPath@@QEAAXXZ; CPath::RemoveRoot(void)
0x18001bf13  mov     rdx, rdi
0x18001bf16  mov     rcx, rbx
0x18001bf19  call    ??4CString@@QEAAAEAV0@PEBG@Z; CString::operator=(ushort const *)
0x18001bf1e  mov     rdx, [rsp+38h+var_10]
0x18001bf23  mov     rdx, [rdx]; pszMore
0x18001bf26  mov     rcx, rbx; this
0x18001bf29  call    ?Append@CPath@@QEAA_NPEBG@Z; CPath::Append(ushort const *)
0x18001bf2e  nop
0x18001bf2f  mov     [rsp+38h+var_18], rsi
0x18001bf34  lea     rcx, [rsp+38h+var_18]; this
0x18001bf39  call    ??1CString@@UEAA@XZ; CString::~CString(void)
0x18001bf3e  nop
0x18001bf3f  mov     rax, rbx
0x18001bf42  mov     rbx, [rsp+38h+arg_8]
0x18001bf47  mov     rsi, [rsp+38h+arg_10]
0x18001bf4c  add     rsp, 30h
0x18001bf50  pop     rdi
0x18001bf51  retn
```
