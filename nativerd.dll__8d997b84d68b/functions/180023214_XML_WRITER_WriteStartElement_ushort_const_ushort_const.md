# XML_WRITER::WriteStartElement(ushort const *,ushort const *)

- ea: `0x180023214`
- end: `0x180023323`
- name: `?WriteStartElement@XML_WRITER@@QEAAJPEBG0@Z`
- size: `271`
- prototype: `int(XML_WRITER *__hidden this, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, registry_config`

## callers

- `0x1800228ec`

## callees

- `0x180023214`
- `0x180059c30`
- `0x18005b010`

## import_xrefs

- `msvcrt!wcschr` at `0x180023246`
- `msvcrt!wcschr` at `0x180023246`
- `iisutil!??1STRU@@QEAA@XZ` at `0x1800232f8`
- `iisutil!??1STRU@@QEAA@XZ` at `0x1800232f8`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x1800232d6`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x1800232d6`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180023290`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180023290`
- `iisutil!?Copy@STRU@@QEAAJPEBGK@Z` at `0x1800232b8`
- `iisutil!?Copy@STRU@@QEAAJPEBGK@Z` at `0x1800232b8`

## pseudocode

```c
__int64 __fastcall XML_WRITER::WriteStartElement(
        XML_WRITER *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3)
{
  wchar_t *v6; // rsi
  unsigned __int64 v8; // r8
  int v9; // ebx
  __int64 v10; // rdi
  __int64 (__fastcall *v11)(__int64, unsigned __int16 *, wchar_t *, const unsigned __int16 *); // rbx
  unsigned __int16 *Str; // rax
  _BYTE v13[56]; // [rsp+30h] [rbp-78h] BYREF
  _OWORD v14[2]; // [rsp+68h] [rbp-40h] BYREF

  v6 = wcschr(a2, 0x3Au);
  if ( !v6 )
    return (*(__int64 (__fastcall **)(_QWORD, _QWORD, const unsigned __int16 *, const unsigned __int16 *))(**(_QWORD **)this + 216LL))(
             *(_QWORD *)this,
             0,
             a2,
             a3);
  memset(v14, 0, sizeof(v14));
  STRU::STRU((STRU *)v13, (unsigned __int16 *)v14, 0x10u);
  v8 = v6 - a2;
  if ( v8 <= 0xFFFFFFFF )
  {
    v9 = STRU::Copy((STRU *)v13, a2, v8);
    if ( v9 >= 0 )
    {
      v10 = *(_QWORD *)this;
      v11 = *(__int64 (__fastcall **)(__int64, unsigned __int16 *, wchar_t *, const unsigned __int16 *))(*(_QWORD *)v10 + 216LL);
      Str = STRU::QueryStr((STRU *)v13);
      v9 = v11(v10, Str, v6 + 1, a3);
    }
  }
  else
  {
    v9 = -2147024362;
  }
  STRU::~STRU((STRU *)v13);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180023214  mov     [rsp+arg_18], rbx
0x180023219  push    rbp
0x18002321a  push    rsi
0x18002321b  push    rdi
0x18002321c  sub     rsp, 90h
0x180023223  mov     rax, cs:__security_cookie
0x18002322a  xor     rax, rsp
0x18002322d  mov     [rsp+0A8h+var_20], rax
0x180023235  mov     rbx, rdx
0x180023238  mov     rdi, rcx
0x18002323b  mov     rcx, rbx; Str
0x18002323e  mov     edx, 3Ah ; ':'; Ch
0x180023243  mov     rbp, r8
0x180023246  call    cs:__imp_wcschr
0x18002324c  mov     rsi, rax
0x18002324f  test    rax, rax
0x180023252  jnz     short loc_180023273
0x180023254  mov     rcx, [rdi]
0x180023257  mov     r9, rbp
0x18002325a  mov     r8, rbx
0x18002325d  xor     edx, edx
0x18002325f  mov     rax, [rcx]
0x180023262  mov     rax, [rax+0D8h]
0x180023269  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002326e  jmp     loc_180023300
0x180023273  xorps   xmm0, xmm0
0x180023276  lea     rdx, [rsp+0A8h+var_40]
0x18002327b  mov     r8d, 10h
0x180023281  lea     rcx, [rsp+0A8h+var_78]
0x180023286  movups  [rsp+0A8h+var_40], xmm0
0x18002328b  movups  [rsp+0A8h+var_30], xmm0
0x180023290  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x180023296  mov     r8, rsi
0x180023299  mov     eax, 0FFFFFFFFh
0x18002329e  sub     r8, rbx
0x1800232a1  sar     r8, 1
0x1800232a4  cmp     r8, rax
0x1800232a7  jbe     short loc_1800232B0
0x1800232a9  mov     ebx, 80070216h
0x1800232ae  jmp     short loc_1800232F3
0x1800232b0  mov     rdx, rbx
0x1800232b3  lea     rcx, [rsp+0A8h+var_78]
0x1800232b8  call    cs:__imp_?Copy@STRU@@QEAAJPEBGK@Z; STRU::Copy(ushort const *,ulong)
0x1800232be  mov     ebx, eax
0x1800232c0  test    eax, eax
0x1800232c2  js      short loc_1800232F3
0x1800232c4  mov     rdi, [rdi]
0x1800232c7  lea     rcx, [rsp+0A8h+var_78]
0x1800232cc  mov     rax, [rdi]
0x1800232cf  mov     rbx, [rax+0D8h]
0x1800232d6  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x1800232dc  lea     r8, [rsi+2]
0x1800232e0  mov     r9, rbp
0x1800232e3  mov     rdx, rax
0x1800232e6  mov     rcx, rdi
0x1800232e9  mov     rax, rbx
0x1800232ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800232f1  mov     ebx, eax
0x1800232f3  lea     rcx, [rsp+0A8h+var_78]
0x1800232f8  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x1800232fe  mov     eax, ebx
0x180023300  mov     rcx, [rsp+0A8h+var_20]
0x180023308  xor     rcx, rsp; StackCookie
0x18002330b  call    __security_check_cookie
0x180023310  mov     rbx, [rsp+0A8h+arg_18]
0x180023318  add     rsp, 90h
0x18002331f  pop     rdi
0x180023320  pop     rsi
0x180023321  pop     rbp
0x180023322  retn
```
