# CLMString::GrowStringHelper(uint,uint,uint,wchar_t const *)

- ea: `0x180036f30`
- end: `0x18003705c`
- name: `?GrowStringHelper@CLMString@@IEAAXIIIPEB_W@Z`
- size: `300`
- prototype: `void(CLMString *__hidden this, unsigned int, unsigned int, unsigned int, const wchar_t *)`
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1800160b0`
- `0x1800179d0`

## callees

- `0x180006dd8`
- `0x180016360`
- `0x180036f30`
- `0x180038b28`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180037022`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180037022`
- `api-ms-win-crt-private-l1-1-0!_o_realloc` at `0x180036fb3`
- `api-ms-win-crt-private-l1-1-0!_o_realloc` at `0x180036fb3`

## string_xrefs

- `0x180036f5a`: `onecoreuap\base\appmodel\search\common\pkmutild\lmstr.cxx`
- `0x180036fc6`: `onecoreuap\base\appmodel\search\common\pkmutild\lmstr.cxx`

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
0x180036f30  mov     [rsp+arg_0], rbx
0x180036f35  mov     [rsp+arg_10], rbp
0x180036f3a  push    rsi
0x180036f3b  push    rdi
0x180036f3c  push    r14; unsigned int
0x180036f3e  sub     rsp, 20h
0x180036f42  mov     ebx, edx
0x180036f44  mov     rdi, rcx
0x180036f47  cmp     edx, [rcx+10h]
0x180036f4a  jbe     loc_18003700C
0x180036f50  cmp     edx, r9d
0x180036f53  jbe     short loc_180036F71
0x180036f55  mov     rcx, [rsp+38h]; this
0x180036f5a  lea     r8, aOnecoreuapBase_3; "onecoreuap\\base\\appmodel\\search\\com"...
0x180036f61  mov     r9d, 0CEh; char *
0x180036f67  lea     edx, [r9+4Bh]; void *
0x180036f6b  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x180036f71  cmp     [rcx+10h], r8d
0x180036f75  mov     eax, ebx
0x180036f77  cmovb   r8d, [rcx+10h]
0x180036f7c  xor     edx, edx
0x180036f7e  div     r8d
0x180036f81  test    edx, edx
0x180036f83  jz      short loc_180036F8B
0x180036f85  sub     r8d, edx
0x180036f88  add     ebx, r8d
0x180036f8b  mov     eax, ebx
0x180036f8d  mov     r14d, 0FFFFFFFFh
0x180036f93  add     rax, rax
0x180036f96  cmp     rax, r14
0x180036f99  ja      loc_180037042
0x180036f9f  mov     rcx, [rcx+8]
0x180036fa3  mov     rbp, [rsp+38h+Src]
0x180036fa8  mov     edx, eax
0x180036faa  xor     eax, eax
0x180036fac  cmp     rcx, rbp
0x180036faf  cmovz   rcx, rax
0x180036fb3  call    cs:__imp__o_realloc
0x180036fb9  mov     rsi, rax
0x180036fbc  test    rax, rax
0x180036fbf  jnz     short loc_180036FDD
0x180036fc1  mov     rcx, [rsp+38h]; this
0x180036fc6  lea     r8, aOnecoreuapBase_3; "onecoreuap\\base\\appmodel\\search\\com"...
0x180036fcd  mov     r9d, 0CEh; char *
0x180036fd3  lea     edx, [r9+62h]; void *
0x180036fd7  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x180036fdd  mov     eax, [rdi+14h]
0x180036fe0  lea     ecx, [rax+1]
0x180036fe3  cmp     ecx, eax
0x180036fe5  jb      short loc_18003701F
0x180036fe7  mov     eax, ecx
0x180036fe9  add     rax, rax
0x180036fec  cmp     rax, r14
0x180036fef  ja      short loc_18003701F
0x180036ff1  cmp     [rdi+8], rbp
0x180036ff5  jnz     short loc_180037005
0x180036ff7  mov     r8d, eax; Size
0x180036ffa  mov     rdx, rbp; Src
0x180036ffd  mov     rcx, rsi; void *
0x180037000  call    memcpy_0
0x180037005  mov     [rdi+8], rsi
0x180037009  mov     [rdi+10h], ebx
0x18003700c  mov     rbx, [rsp+38h+arg_0]
0x180037011  mov     rbp, [rsp+38h+arg_10]
0x180037016  add     rsp, 20h
0x18003701a  pop     r14
0x18003701c  pop     rdi
0x18003701d  pop     rsi
0x18003701e  retn
0x18003701f  mov     rcx, rsi; Block
0x180037022  call    cs:__imp_free
0x180037028  lea     rdx, _TI1J; pThrowInfo
0x18003702f  mov     [rsp+38h+pExceptionObject], 80070216h
0x180037037  lea     rcx, [rsp+38h+pExceptionObject]; pExceptionObject
0x18003703c  call    _CxxThrowException_0
0x180037042  lea     rdx, _TI1J; pThrowInfo
0x180037049  mov     [rsp+38h+pExceptionObject], 80070216h
0x180037051  lea     rcx, [rsp+38h+pExceptionObject]; pExceptionObject
0x180037056  call    _CxxThrowException_0
```
