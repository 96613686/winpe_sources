# CLMString::GrowStringHelper(uint,uint,uint,wchar_t const *)

- ea: `0x1800224cc`
- end: `0x1800225f8`
- name: `?GrowStringHelper@CLMString@@IEAAXIIIPEB_W@Z`
- size: `300`
- prototype: `void __fastcall(CLMString *this, unsigned int, unsigned int, unsigned int, const wchar_t *Src)`
- caller_count: `4`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18001ba30`
- `0x18001e4d0`
- `0x18001fad0`
- `0x180021a00`

## callees

- `0x180014ffc`
- `0x180020834`
- `0x1800224cc`
- `0x180023388`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800225be`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800225be`
- `api-ms-win-crt-private-l1-1-0!_o_realloc` at `0x18002254f`
- `api-ms-win-crt-private-l1-1-0!_o_realloc` at `0x18002254f`

## string_xrefs

- `0x1800224f6`: `onecoreuap\base\appmodel\search\common\pkmutild\lmstr.cxx`
- `0x180022562`: `onecoreuap\base\appmodel\search\common\pkmutild\lmstr.cxx`

## pseudocode

```c
void __fastcall CLMString::GrowStringHelper(
        CLMString *this,
        unsigned int a2,
        unsigned int a3,
        unsigned int a4,
        const wchar_t *Src)
{
  unsigned int v5; // ebx
  unsigned __int64 v7; // rax
  const wchar_t *v8; // rcx
  const wchar_t *v9; // rbp
  void *v10; // rsi
  unsigned int v11; // eax
  unsigned __int64 v12; // rax
  unsigned int v13; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  int pExceptionObject; // [rsp+48h] [rbp+10h] BYREF

  v5 = a2;
  if ( a2 > *((_DWORD *)this + 4) )
  {
    if ( a2 > a4 )
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0x119,
        (unsigned int)"onecoreuap\\base\\appmodel\\search\\common\\pkmutild\\lmstr.cxx",
        (const char *)0xCE,
        v13);
    if ( *((_DWORD *)this + 4) < a3 )
      a3 = *((_DWORD *)this + 4);
    if ( a2 % a3 )
      v5 = a3 - a2 % a3 + a2;
    v7 = 2LL * v5;
    if ( v7 > 0xFFFFFFFF )
    {
      pExceptionObject = -2147024362;
      throw (long *)&pExceptionObject;
    }
    v8 = (const wchar_t *)*((_QWORD *)this + 1);
    v9 = Src;
    if ( v8 == Src )
      v8 = 0;
    v10 = (void *)_o_realloc(v8, (unsigned int)v7);
    if ( !v10 )
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0x130,
        (unsigned int)"onecoreuap\\base\\appmodel\\search\\common\\pkmutild\\lmstr.cxx",
        (const char *)0xCE,
        v13);
    v11 = *((_DWORD *)this + 5);
    if ( v11 + 1 < v11 || (v12 = 2LL * (v11 + 1), v12 > 0xFFFFFFFF) )
    {
      free(v10);
      pExceptionObject = -2147024362;
      throw (long *)&pExceptionObject;
    }
    if ( *((const wchar_t **)this + 1) == v9 )
      memcpy_0(v10, v9, (unsigned int)v12);
    *((_QWORD *)this + 1) = v10;
    *((_DWORD *)this + 4) = v5;
  }
}

```

## disassembly

```asm
0x1800224cc  mov     [rsp+arg_0], rbx
0x1800224d1  mov     [rsp+arg_10], rbp
0x1800224d6  push    rsi
0x1800224d7  push    rdi
0x1800224d8  push    r14; unsigned int
0x1800224da  sub     rsp, 20h
0x1800224de  mov     ebx, edx
0x1800224e0  mov     rdi, rcx
0x1800224e3  cmp     edx, [rcx+10h]
0x1800224e6  jbe     loc_1800225A8
0x1800224ec  cmp     edx, r9d
0x1800224ef  jbe     short loc_18002250D
0x1800224f1  mov     rcx, [rsp+38h]; this
0x1800224f6  lea     r8, aOnecoreuapBase_2; "onecoreuap\\base\\appmodel\\search\\com"...
0x1800224fd  mov     r9d, 0CEh; char *
0x180022503  lea     edx, [r9+4Bh]; void *
0x180022507  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x18002250d  cmp     [rcx+10h], r8d
0x180022511  mov     eax, ebx
0x180022513  cmovb   r8d, [rcx+10h]
0x180022518  xor     edx, edx
0x18002251a  div     r8d
0x18002251d  test    edx, edx
0x18002251f  jz      short loc_180022527
0x180022521  sub     r8d, edx
0x180022524  add     ebx, r8d
0x180022527  mov     eax, ebx
0x180022529  mov     r14d, 0FFFFFFFFh
0x18002252f  add     rax, rax
0x180022532  cmp     rax, r14
0x180022535  ja      loc_1800225DE
0x18002253b  mov     rcx, [rcx+8]
0x18002253f  mov     rbp, [rsp+38h+Src]
0x180022544  mov     edx, eax
0x180022546  xor     eax, eax
0x180022548  cmp     rcx, rbp
0x18002254b  cmovz   rcx, rax
0x18002254f  call    cs:__imp__o_realloc
0x180022555  mov     rsi, rax
0x180022558  test    rax, rax
0x18002255b  jnz     short loc_180022579
0x18002255d  mov     rcx, [rsp+38h]; this
0x180022562  lea     r8, aOnecoreuapBase_2; "onecoreuap\\base\\appmodel\\search\\com"...
0x180022569  mov     r9d, 0CEh; char *
0x18002256f  lea     edx, [r9+62h]; void *
0x180022573  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x180022579  mov     eax, [rdi+14h]
0x18002257c  lea     ecx, [rax+1]
0x18002257f  cmp     ecx, eax
0x180022581  jb      short loc_1800225BB
0x180022583  mov     eax, ecx
0x180022585  add     rax, rax
0x180022588  cmp     rax, r14
0x18002258b  ja      short loc_1800225BB
0x18002258d  cmp     [rdi+8], rbp
0x180022591  jnz     short loc_1800225A1
0x180022593  mov     r8d, eax; Size
0x180022596  mov     rdx, rbp; Src
0x180022599  mov     rcx, rsi; void *
0x18002259c  call    memcpy_0
0x1800225a1  mov     [rdi+8], rsi
0x1800225a5  mov     [rdi+10h], ebx
0x1800225a8  mov     rbx, [rsp+38h+arg_0]
0x1800225ad  mov     rbp, [rsp+38h+arg_10]
0x1800225b2  add     rsp, 20h
0x1800225b6  pop     r14
0x1800225b8  pop     rdi
0x1800225b9  pop     rsi
0x1800225ba  retn
0x1800225bb  mov     rcx, rsi; Block
0x1800225be  call    cs:__imp_free
0x1800225c4  lea     rdx, _TI1J; pThrowInfo
0x1800225cb  mov     [rsp+38h+pExceptionObject], 80070216h
0x1800225d3  lea     rcx, [rsp+38h+pExceptionObject]; pExceptionObject
0x1800225d8  call    _CxxThrowException_0
0x1800225de  lea     rdx, _TI1J; pThrowInfo
0x1800225e5  mov     [rsp+38h+pExceptionObject], 80070216h
0x1800225ed  lea     rcx, [rsp+38h+pExceptionObject]; pExceptionObject
0x1800225f2  call    _CxxThrowException_0
```
