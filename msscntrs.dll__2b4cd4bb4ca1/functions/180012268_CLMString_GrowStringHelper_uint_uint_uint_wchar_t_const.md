# CLMString::GrowStringHelper(uint,uint,uint,wchar_t const *)

- ea: `0x180012268`
- end: `0x18001238e`
- name: `?GrowStringHelper@CLMString@@IEAAXIIIPEB_W@Z`
- size: `294`
- prototype: `void __fastcall(CLMString *this, unsigned int, unsigned int, const char *, const wchar_t *Src)`
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18000dcd0`
- `0x18000dd00`

## callees

- `0x18000332c`
- `0x180012268`
- `0x1800123dc`
- `0x1800156c8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18001236e`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18001236e`
- `api-ms-win-crt-private-l1-1-0!_o_realloc` at `0x1800122cf`
- `api-ms-win-crt-private-l1-1-0!_o_realloc` at `0x1800122cf`

## string_xrefs

- `0x180012342`: `onecoreuap\base\appmodel\search\common\pkmutild\lmstr.cxx`
- `0x180012359`: `onecoreuap\base\appmodel\search\common\pkmutild\lmstr.cxx`

## pseudocode

```c
void __fastcall CLMString::GrowStringHelper(
        CLMString *this,
        unsigned int a2,
        unsigned int a3,
        const char *a4,
        const wchar_t *Src)
{
  unsigned int v5; // ebx
  unsigned __int64 v7; // rax
  const wchar_t *v8; // rcx
  const wchar_t *v9; // rbp
  void *v10; // rsi
  const char *v11; // r9
  unsigned int v12; // eax
  unsigned __int64 v13; // rax
  unsigned int v14; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  int pExceptionObject; // [rsp+48h] [rbp+10h] BYREF

  v5 = a2;
  if ( a2 > *((_DWORD *)this + 4) )
  {
    if ( a2 > (unsigned int)a4 )
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0x119,
        (unsigned int)"onecoreuap\\base\\appmodel\\search\\common\\pkmutild\\lmstr.cxx",
        a4,
        v14);
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
        v11,
        v14);
    v12 = *((_DWORD *)this + 5);
    if ( v12 + 1 < v12 || (v13 = 2LL * (v12 + 1), v13 > 0xFFFFFFFF) )
    {
      free(v10);
      pExceptionObject = -2147024362;
      throw (long *)&pExceptionObject;
    }
    if ( *((const wchar_t **)this + 1) == v9 )
      memcpy_0(v10, v9, (unsigned int)v13);
    *((_QWORD *)this + 1) = v10;
    *((_DWORD *)this + 4) = v5;
  }
}

```

## disassembly

```asm
0x180012268  mov     [rsp+arg_0], rbx
0x18001226d  mov     [rsp+arg_10], rbp
0x180012272  push    rsi
0x180012273  push    rdi
0x180012274  push    r14; unsigned int
0x180012276  sub     rsp, 20h
0x18001227a  mov     ebx, edx
0x18001227c  mov     rdi, rcx
0x18001227f  cmp     edx, [rcx+10h]
0x180012282  jbe     loc_180012310
0x180012288  cmp     edx, r9d
0x18001228b  ja      loc_18001233D
0x180012291  cmp     [rcx+10h], r8d
0x180012295  mov     eax, ebx
0x180012297  cmovb   r8d, [rcx+10h]
0x18001229c  xor     edx, edx
0x18001229e  div     r8d
0x1800122a1  test    edx, edx
0x1800122a3  jz      short loc_1800122AB
0x1800122a5  sub     r8d, edx
0x1800122a8  add     ebx, r8d
0x1800122ab  mov     eax, ebx
0x1800122ad  mov     r14d, 0FFFFFFFFh
0x1800122b3  add     rax, rax
0x1800122b6  cmp     rax, r14
0x1800122b9  ja      short loc_180012323
0x1800122bb  mov     rcx, [rcx+8]
0x1800122bf  mov     rbp, [rsp+38h+Src]
0x1800122c4  mov     edx, eax
0x1800122c6  xor     eax, eax
0x1800122c8  cmp     rcx, rbp
0x1800122cb  cmovz   rcx, rax
0x1800122cf  call    cs:__imp__o_realloc
0x1800122d5  mov     rsi, rax
0x1800122d8  test    rax, rax
0x1800122db  jz      short loc_180012354
0x1800122dd  mov     eax, [rdi+14h]
0x1800122e0  lea     ecx, [rax+1]
0x1800122e3  cmp     ecx, eax
0x1800122e5  jb      loc_18001236B
0x1800122eb  mov     eax, ecx
0x1800122ed  add     rax, rax
0x1800122f0  cmp     rax, r14
0x1800122f3  ja      short loc_18001236B
0x1800122f5  cmp     [rdi+8], rbp
0x1800122f9  jnz     short loc_180012309
0x1800122fb  mov     r8d, eax; Size
0x1800122fe  mov     rdx, rbp; Src
0x180012301  mov     rcx, rsi; void *
0x180012304  call    memcpy_0
0x180012309  mov     [rdi+8], rsi
0x18001230d  mov     [rdi+10h], ebx
0x180012310  mov     rbx, [rsp+38h+arg_0]
0x180012315  mov     rbp, [rsp+38h+arg_10]
0x18001231a  add     rsp, 20h
0x18001231e  pop     r14
0x180012320  pop     rdi
0x180012321  pop     rsi
0x180012322  retn
0x180012323  lea     rdx, _TI1J; pThrowInfo
0x18001232a  mov     [rsp+38h+pExceptionObject], 80070216h
0x180012332  lea     rcx, [rsp+38h+pExceptionObject]; pExceptionObject
0x180012337  call    _CxxThrowException_0
0x18001233d  mov     rcx, [rsp+38h]; this
0x180012342  lea     r8, aOnecoreuapBase; "onecoreuap\\base\\appmodel\\search\\com"...
0x180012349  mov     edx, 119h; void *
0x18001234e  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x180012354  mov     rcx, [rsp+38h]; this
0x180012359  lea     r8, aOnecoreuapBase; "onecoreuap\\base\\appmodel\\search\\com"...
0x180012360  mov     edx, 130h; void *
0x180012365  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x18001236b  mov     rcx, rsi; Block
0x18001236e  call    cs:__imp_free
0x180012374  lea     rdx, _TI1J; pThrowInfo
0x18001237b  mov     [rsp+38h+pExceptionObject], 80070216h
0x180012383  lea     rcx, [rsp+38h+pExceptionObject]; pExceptionObject
0x180012388  call    _CxxThrowException_0
```
