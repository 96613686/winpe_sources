# XML_WRITER::WriteAttributeString(ushort const *,ushort const *)

- ea: `0x1800230f8`
- end: `0x18002320b`
- name: `?WriteAttributeString@XML_WRITER@@QEAAJPEBG0@Z`
- size: `275`
- prototype: `int(XML_WRITER *__hidden this, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, registry_config`

## callers

- `0x1800228ec`

## callees

- `0x1800230f8`
- `0x180059c30`
- `0x18005b010`

## import_xrefs

- `msvcrt!wcschr` at `0x18002312a`
- `msvcrt!wcschr` at `0x18002312a`
- `iisutil!??1STRU@@QEAA@XZ` at `0x1800231e0`
- `iisutil!??1STRU@@QEAA@XZ` at `0x1800231e0`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x1800231b9`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x1800231b9`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180023176`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180023176`
- `iisutil!?Copy@STRU@@QEAAJPEBGK@Z` at `0x18002319e`
- `iisutil!?Copy@STRU@@QEAAJPEBGK@Z` at `0x18002319e`

## pseudocode

```c
__int64 __fastcall XML_WRITER::WriteAttributeString(
        XML_WRITER *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3)
{
  wchar_t *v6; // rsi
  unsigned __int64 v8; // r8
  int v9; // ebx
  __int64 v10; // rdi
  __int64 (__fastcall *v11)(__int64, unsigned __int16 *, wchar_t *, _QWORD, const unsigned __int16 *); // rbx
  unsigned __int16 *Str; // rax
  _BYTE v13[56]; // [rsp+30h] [rbp-78h] BYREF
  _OWORD v14[2]; // [rsp+68h] [rbp-40h] BYREF

  v6 = wcschr(a2, 0x3Au);
  if ( !v6 )
    return (*(__int64 (__fastcall **)(_QWORD, _QWORD, const unsigned __int16 *, _QWORD, const unsigned __int16 *))(**(_QWORD **)this + 56LL))(
             *(_QWORD *)this,
             0,
             a2,
             0,
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
      v11 = *(__int64 (__fastcall **)(__int64, unsigned __int16 *, wchar_t *, _QWORD, const unsigned __int16 *))(*(_QWORD *)v10 + 56LL);
      Str = STRU::QueryStr((STRU *)v13);
      v9 = v11(v10, Str, v6 + 1, 0, a3);
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
0x1800230f8  mov     [rsp+arg_18], rbx
0x1800230fd  push    rbp
0x1800230fe  push    rsi
0x1800230ff  push    rdi
0x180023100  sub     rsp, 90h
0x180023107  mov     rax, cs:__security_cookie
0x18002310e  xor     rax, rsp
0x180023111  mov     [rsp+0A8h+var_20], rax
0x180023119  mov     rbx, rdx
0x18002311c  mov     rdi, rcx
0x18002311f  mov     rcx, rbx; Str
0x180023122  mov     edx, 3Ah ; ':'; Ch
0x180023127  mov     rbp, r8
0x18002312a  call    cs:__imp_wcschr
0x180023130  mov     rsi, rax
0x180023133  test    rax, rax
0x180023136  jnz     short loc_180023159
0x180023138  mov     rcx, [rdi]
0x18002313b  xor     r9d, r9d
0x18002313e  mov     r8, rbx
0x180023141  mov     [rsp+0A8h+var_88], rbp
0x180023146  xor     edx, edx
0x180023148  mov     rax, [rcx]
0x18002314b  mov     rax, [rax+38h]
0x18002314f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023154  jmp     loc_1800231E8
0x180023159  xorps   xmm0, xmm0
0x18002315c  lea     rdx, [rsp+0A8h+var_40]
0x180023161  mov     r8d, 10h
0x180023167  lea     rcx, [rsp+0A8h+var_78]
0x18002316c  movups  [rsp+0A8h+var_40], xmm0
0x180023171  movups  [rsp+0A8h+var_30], xmm0
0x180023176  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x18002317c  mov     r8, rsi
0x18002317f  mov     eax, 0FFFFFFFFh
0x180023184  sub     r8, rbx
0x180023187  sar     r8, 1
0x18002318a  cmp     r8, rax
0x18002318d  jbe     short loc_180023196
0x18002318f  mov     ebx, 80070216h
0x180023194  jmp     short loc_1800231DB
0x180023196  mov     rdx, rbx
0x180023199  lea     rcx, [rsp+0A8h+var_78]
0x18002319e  call    cs:__imp_?Copy@STRU@@QEAAJPEBGK@Z; STRU::Copy(ushort const *,ulong)
0x1800231a4  mov     ebx, eax
0x1800231a6  test    eax, eax
0x1800231a8  js      short loc_1800231DB
0x1800231aa  mov     rdi, [rdi]
0x1800231ad  lea     rcx, [rsp+0A8h+var_78]
0x1800231b2  mov     rax, [rdi]
0x1800231b5  mov     rbx, [rax+38h]
0x1800231b9  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x1800231bf  lea     r8, [rsi+2]
0x1800231c3  mov     [rsp+0A8h+var_88], rbp
0x1800231c8  mov     rdx, rax
0x1800231cb  xor     r9d, r9d
0x1800231ce  mov     rax, rbx
0x1800231d1  mov     rcx, rdi
0x1800231d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800231d9  mov     ebx, eax
0x1800231db  lea     rcx, [rsp+0A8h+var_78]
0x1800231e0  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x1800231e6  mov     eax, ebx
0x1800231e8  mov     rcx, [rsp+0A8h+var_20]
0x1800231f0  xor     rcx, rsp; StackCookie
0x1800231f3  call    __security_check_cookie
0x1800231f8  mov     rbx, [rsp+0A8h+arg_18]
0x180023200  add     rsp, 90h
0x180023207  pop     rdi
0x180023208  pop     rsi
0x180023209  pop     rbp
0x18002320a  retn
```
