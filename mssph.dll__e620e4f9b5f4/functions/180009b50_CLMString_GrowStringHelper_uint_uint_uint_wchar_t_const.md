# CLMString::GrowStringHelper(uint,uint,uint,wchar_t const *)

- ea: `0x180009b50`
- end: `0x180009c88`
- name: `?GrowStringHelper@CLMString@@IEAAXIIIPEB_W@Z`
- size: `312`
- prototype: `void __fastcall(CLMString *__hidden this, unsigned int, unsigned int, unsigned int, const wchar_t *Src)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18001ddd0`

## callees

- `0x180009b50`
- `0x180010b38`
- `0x180011135`
- `0x18001e194`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180009c4e`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180009c4e`
- `api-ms-win-crt-private-l1-1-0!_o_realloc` at `0x180009bdb`
- `api-ms-win-crt-private-l1-1-0!_o_realloc` at `0x180009bdb`

## string_xrefs

- `0x180009b75`: `onecoreuap\base\appmodel\search\common\pkmutild\lmstr.cxx`
- `0x180009bee`: `onecoreuap\base\appmodel\search\common\pkmutild\lmstr.cxx`

## pseudocode

```c
void __fastcall CLMString::GrowStringHelper(
        CLMString *this,
        unsigned int a2,
        unsigned int a3,
        unsigned int a4,
        const wchar_t *Src)
{
  unsigned int v5; // eax
  int v9; // edx
  unsigned int v10; // edi
  unsigned __int64 v11; // rax
  const wchar_t *v12; // rcx
  const wchar_t *v13; // rbp
  void *v14; // rsi
  unsigned int v15; // eax
  unsigned __int64 v16; // rax
  unsigned int v17; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  int pExceptionObject; // [rsp+48h] [rbp+10h] BYREF

  v5 = *((_DWORD *)this + 4);
  if ( a2 > v5 )
  {
    if ( a2 > a4 )
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0x119,
        (unsigned int)"onecoreuap\\base\\appmodel\\search\\common\\pkmutild\\lmstr.cxx",
        (const char *)0xCE,
        v17);
    if ( v5 < a3 )
      a3 = *((_DWORD *)this + 4);
    v9 = a2 % a3;
    v10 = a2 + a3 - a2 % a3;
    if ( !v9 )
      v10 = a2;
    v11 = 2LL * v10;
    if ( v11 > 0xFFFFFFFF )
    {
      pExceptionObject = -2147024362;
      throw (long *)&pExceptionObject;
    }
    v12 = (const wchar_t *)*((_QWORD *)this + 1);
    v13 = Src;
    if ( v12 == Src )
      v12 = 0;
    v14 = (void *)_o_realloc(v12, (unsigned int)v11);
    if ( !v14 )
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0x130,
        (unsigned int)"onecoreuap\\base\\appmodel\\search\\common\\pkmutild\\lmstr.cxx",
        (const char *)0xCE,
        v17);
    v15 = *((_DWORD *)this + 5);
    if ( v15 + 1 < v15 || (v16 = 2LL * (v15 + 1), v16 > 0xFFFFFFFF) )
    {
      free(v14);
      pExceptionObject = -2147024362;
      throw (long *)&pExceptionObject;
    }
    if ( *((const wchar_t **)this + 1) == v13 )
      memcpy_0(v14, v13, (unsigned int)v16);
    *((_QWORD *)this + 1) = v14;
    *((_DWORD *)this + 4) = v10;
  }
}

```

## disassembly

```asm
0x180009b50  push    rbx
0x180009b52  push    rdi
0x180009b53  sub     rsp, 28h
0x180009b57  mov     eax, [rcx+10h]
0x180009b5a  mov     edi, r8d
0x180009b5d  mov     r8d, edx
0x180009b60  mov     rbx, rcx
0x180009b63  cmp     edx, eax
0x180009b65  jbe     loc_180009C44
0x180009b6b  cmp     edx, r9d
0x180009b6e  jbe     short loc_180009B8D
0x180009b70  mov     rcx, [rsp+38h]; this
0x180009b75  lea     r8, aOnecoreuapBase_8; "onecoreuap\\base\\appmodel\\search\\com"...
0x180009b7c  mov     r9d, 0CEh; char *
0x180009b82  mov     edx, 119h; void *
0x180009b87  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x180009b8d  cmp     eax, edi
0x180009b8f  mov     qword ptr [rsp+38h+var_18], r14; unsigned int
0x180009b94  mov     r14d, 0FFFFFFFFh
0x180009b9a  cmovb   edi, eax
0x180009b9d  xor     edx, edx
0x180009b9f  mov     eax, r8d
0x180009ba2  div     edi
0x180009ba4  sub     edi, edx
0x180009ba6  add     edi, r8d
0x180009ba9  test    edx, edx
0x180009bab  cmovz   edi, r8d
0x180009baf  mov     eax, edi
0x180009bb1  add     rax, rax
0x180009bb4  cmp     rax, r14
0x180009bb7  ja      loc_180009C6E
0x180009bbd  mov     rcx, [rcx+8]
0x180009bc1  mov     [rsp+38h+arg_0], rbp
0x180009bc6  mov     rbp, [rsp+38h+Src]
0x180009bcb  mov     edx, eax
0x180009bcd  xor     eax, eax
0x180009bcf  cmp     rcx, rbp
0x180009bd2  mov     [rsp+38h+arg_10], rsi
0x180009bd7  cmovz   rcx, rax
0x180009bdb  call    cs:__imp__o_realloc
0x180009be1  mov     rsi, rax
0x180009be4  test    rax, rax
0x180009be7  jnz     short loc_180009C06
0x180009be9  mov     rcx, [rsp+38h]; this
0x180009bee  lea     r8, aOnecoreuapBase_8; "onecoreuap\\base\\appmodel\\search\\com"...
0x180009bf5  mov     r9d, 0CEh; char *
0x180009bfb  mov     edx, 130h; void *
0x180009c00  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x180009c06  mov     eax, [rbx+14h]
0x180009c09  lea     ecx, [rax+1]
0x180009c0c  cmp     ecx, eax
0x180009c0e  jb      short loc_180009C4B
0x180009c10  mov     eax, ecx
0x180009c12  add     rax, rax
0x180009c15  cmp     rax, r14
0x180009c18  ja      short loc_180009C4B
0x180009c1a  cmp     [rbx+8], rbp
0x180009c1e  jnz     short loc_180009C2E
0x180009c20  mov     r8d, eax; Size
0x180009c23  mov     rdx, rbp; Src
0x180009c26  mov     rcx, rsi; void *
0x180009c29  call    memcpy_0
0x180009c2e  mov     rbp, [rsp+38h+arg_0]
0x180009c33  mov     r14, qword ptr [rsp+38h+var_18]
0x180009c38  mov     [rbx+8], rsi
0x180009c3c  mov     rsi, [rsp+38h+arg_10]
0x180009c41  mov     [rbx+10h], edi
0x180009c44  add     rsp, 28h
0x180009c48  pop     rdi
0x180009c49  pop     rbx
0x180009c4a  retn
0x180009c4b  mov     rcx, rsi; Block
0x180009c4e  call    cs:__imp_free
0x180009c54  lea     rdx, _TI1J; pThrowInfo
0x180009c5b  mov     [rsp+38h+pExceptionObject], 80070216h
0x180009c63  lea     rcx, [rsp+38h+pExceptionObject]; pExceptionObject
0x180009c68  call    _CxxThrowException_0
0x180009c6e  lea     rdx, _TI1J; pThrowInfo
0x180009c75  mov     [rsp+38h+pExceptionObject], 80070216h
0x180009c7d  lea     rcx, [rsp+38h+pExceptionObject]; pExceptionObject
0x180009c82  call    _CxxThrowException_0
```
