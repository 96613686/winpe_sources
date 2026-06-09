# TMetaInferrence::ValidateStringAsLegalVariableName(ushort const *,ushort const *,bool)

- ea: `0x180020c1c`
- end: `0x180020d46`
- name: `?ValidateStringAsLegalVariableName@TMetaInferrence@@AEAAXPEBG0_N@Z`
- size: `298`
- prototype: `void(TMetaInferrence *__hidden this, const unsigned __int16 *, const unsigned __int16 *, bool)`
- caller_count: `6`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18001e074`
- `0x18001e9d4`
- `0x18001ec74`
- `0x18001ee28`
- `0x18001ff10`
- `0x180020a68`

## callees

- `0x180017ad8`
- `0x180020c1c`
- `0x180030010`

## import_xrefs

- `msvcrt!wcsspn` at `0x180020ce8`
- `msvcrt!wcsspn` at `0x180020ce8`

## string_xrefs

- `0x180020c92`: `inetsrv\iis\mb\config\src\core\schemagen\tmetainferrence.cpp`
- `0x180020cd0`: `inetsrv\iis\mb\config\src\core\schemagen\tmetainferrence.cpp`
- `0x180020d29`: `inetsrv\iis\mb\config\src\core\schemagen\tmetainferrence.cpp`

## pseudocode

```c
void __fastcall TMetaInferrence::ValidateStringAsLegalVariableName(
        TMetaInferrence *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        char a4)
{
  const wchar_t *v4; // r10
  __int64 v7; // rdx
  const unsigned __int16 *v8; // rdx

  v4 = L"_abcdefghijklmnopqrstuvwxyzABCDEFGHIJKLMNOPQRSTUVWXYZ0123456789";
  if ( a3 )
    v4 = a3;
  v7 = -1;
  do
    ++v7;
  while ( a2[v7] );
  if ( !a4 && (unsigned __int16)(*a2 - 65) > 0x19u && (unsigned __int16)(*a2 - 97) > 0x19u )
  {
    (***((void (****)(_QWORD, const wchar_t *, ...))this + 2))(
      *((_QWORD *)this + 2),
      L"Error - Bogus String (%s).  This String must be a legal C++ variable name (begins with an alpha and contains only "
       "alpha (or '_') and numerics.\n",
      a2);
    ThrowException(
      L"inetsrv\\iis\\mb\\config\\src\\core\\schemagen\\tmetainferrence.cpp",
      L"ERROR - BOGUS NAME",
      0x50Eu,
      0);
  }
  if ( a2[v7 - 1] == 95 )
  {
    (***((void (****)(_QWORD, const wchar_t *, ...))this + 2))(
      *((_QWORD *)this + 2),
      L"Error - Bogus String (%s).  This String must be a legal WMI name (cannot end with underscore).\n",
      a2);
    ThrowException(
      L"inetsrv\\iis\\mb\\config\\src\\core\\schemagen\\tmetainferrence.cpp",
      L"ERROR - BOGUS NAME",
      0x516u,
      0);
  }
  if ( a2 )
  {
    v8 = &a2[wcsspn(a2, v4)];
    if ( *v8 )
    {
      if ( v8 )
      {
        (***((void (****)(_QWORD, const wchar_t *, ...))this + 2))(
          *((_QWORD *)this + 2),
          L"Error - Bogus String (%s).  This string should not contain the character '%c'.\n",
          a2,
          (unsigned int)*(char *)v8);
        ThrowException(
          L"inetsrv\\iis\\mb\\config\\src\\core\\schemagen\\tmetainferrence.cpp",
          L"ERROR - BAD NAME",
          0x51Du,
          0);
      }
    }
  }
}

```

## disassembly

```asm
0x180020c1c  mov     [rsp+arg_0], rbx
0x180020c21  mov     [rsp+arg_8], rsi
0x180020c26  push    rdi
0x180020c27  sub     rsp, 30h
0x180020c2b  xor     esi, esi
0x180020c2d  lea     r10, aAbcdefghijklmn; "_abcdefghijklmnopqrstuvwxyzABCDEFGHIJKL"...
0x180020c34  test    r8, r8
0x180020c37  mov     rbx, rdx
0x180020c3a  mov     rdi, rcx
0x180020c3d  cmovnz  r10, r8
0x180020c41  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180020c45  inc     rdx
0x180020c48  cmp     [rbx+rdx*2], si
0x180020c4c  jnz     short loc_180020C45
0x180020c4e  test    r9b, r9b
0x180020c51  jnz     short loc_180020C9F
0x180020c53  movzx   ecx, word ptr [rbx]
0x180020c56  lea     eax, [rcx-41h]
0x180020c59  cmp     ax, 19h
0x180020c5d  jbe     short loc_180020C9F
0x180020c5f  sub     cx, 61h ; 'a'
0x180020c63  cmp     cx, 19h
0x180020c67  jbe     short loc_180020C9F
0x180020c69  mov     rcx, [rdi+10h]
0x180020c6d  lea     rdx, aErrorBogusStri_0; "Error - Bogus String (%s).  This String"...
0x180020c74  mov     r8, rbx
0x180020c77  mov     rax, [rcx]
0x180020c7a  mov     rax, [rax]
0x180020c7d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020c82  xor     r9d, r9d; unsigned int
0x180020c85  lea     rdx, aErrorBogusName; "ERROR - BOGUS NAME"
0x180020c8c  mov     r8d, 50Eh; unsigned int
0x180020c92  lea     rcx, aInetsrvIisMbCo_13; "inetsrv\\iis\\mb\\config\\src\\core\\sc"...
0x180020c99  call    ?ThrowException@@YAXPEBG0II@Z; ThrowException(ushort const *,ushort const *,uint,uint)
0x180020c9f  cmp     word ptr [rbx+rdx*2-2], 5Fh ; '_'
0x180020ca5  jnz     short loc_180020CDD
0x180020ca7  mov     rcx, [rdi+10h]
0x180020cab  lea     rdx, aErrorBogusStri; "Error - Bogus String (%s).  This String"...
0x180020cb2  mov     r8, rbx
0x180020cb5  mov     rax, [rcx]
0x180020cb8  mov     rax, [rax]
0x180020cbb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020cc0  xor     r9d, r9d; unsigned int
0x180020cc3  lea     rdx, aErrorBogusName; "ERROR - BOGUS NAME"
0x180020cca  mov     r8d, 516h; unsigned int
0x180020cd0  lea     rcx, aInetsrvIisMbCo_13; "inetsrv\\iis\\mb\\config\\src\\core\\sc"...
0x180020cd7  call    ?ThrowException@@YAXPEBG0II@Z; ThrowException(ushort const *,ushort const *,uint,uint)
0x180020cdd  test    rbx, rbx
0x180020ce0  jz      short loc_180020D36
0x180020ce2  mov     rdx, r10; Control
0x180020ce5  mov     rcx, rbx; String
0x180020ce8  call    cs:__imp_wcsspn
0x180020cee  lea     rdx, [rbx+rax*2]
0x180020cf2  cmp     [rdx], si
0x180020cf5  jz      short loc_180020D36
0x180020cf7  test    rdx, rdx
0x180020cfa  jz      short loc_180020D36
0x180020cfc  mov     rcx, [rdi+10h]
0x180020d00  mov     r8, rbx
0x180020d03  movsx   r9d, byte ptr [rdx]
0x180020d07  lea     rdx, aErrorBogusStri_1; "Error - Bogus String (%s).  This string"...
0x180020d0e  mov     rax, [rcx]
0x180020d11  mov     rax, [rax]
0x180020d14  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020d19  xor     r9d, r9d; unsigned int
0x180020d1c  lea     rdx, aErrorBadName; "ERROR - BAD NAME"
0x180020d23  mov     r8d, 51Dh; unsigned int
0x180020d29  lea     rcx, aInetsrvIisMbCo_13; "inetsrv\\iis\\mb\\config\\src\\core\\sc"...
0x180020d30  call    ?ThrowException@@YAXPEBG0II@Z; ThrowException(ushort const *,ushort const *,uint,uint)
0x180020d36  mov     rbx, [rsp+38h+arg_0]
0x180020d3b  mov     rsi, [rsp+38h+arg_8]
0x180020d40  add     rsp, 30h
0x180020d44  pop     rdi
0x180020d45  retn
```
