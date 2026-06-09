# CLMString::Assign(wchar_t const *,uint,uint)

- ea: `0x180005d40`
- end: `0x180005e9b`
- name: `?Assign@CLMString@@UEAAHPEB_WII@Z`
- size: `347`
- prototype: `__int64 __fastcall(CLMString *this, const wchar_t *, unsigned int, int)`
- caller_count: `3`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800048f0`
- `0x180006cd0`
- `0x1800071c0`

## callees

- `0x180005d40`
- `0x18000e7fc`
- `0x18000e878`
- `0x180011135`
- `0x180027010`

## string_xrefs

- `0x180005e7b`: `onecoreuap\base\appmodel\search\common\pkmutild\lmstr.cxx`

## pseudocode

```c
__int64 __fastcall CLMString::Assign(CLMString *this, const wchar_t *a2, unsigned int a3, int a4)
{
  __int64 v4; // r14
  const wchar_t *v5; // rdi
  CLMString *v6; // rsi
  unsigned __int64 v7; // rbx
  unsigned int v8; // ebp
  __int64 v9; // rax
  __int64 v10; // r9
  unsigned __int64 v11; // rax
  _WORD *v12; // r10
  __int64 result; // rax
  int v14; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  v4 = a3;
  v5 = a2;
  v6 = this;
  if ( !a2 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x36,
      (unsigned int)"onecoreuap\\base\\appmodel\\search\\common\\pkmutild\\lmstr.cxx",
      (const char *)0x80070057LL,
      v14);
  if ( a4 == -1 )
  {
    v7 = -1;
    do
      ++v7;
    while ( a2[v7] );
    if ( v7 > 0xFFFFFFFF )
      goto LABEL_8;
  }
  else
  {
    LODWORD(v7) = a4;
  }
  v8 = v7 + a3;
  if ( (unsigned int)v7 + a3 < a3 )
    goto LABEL_8;
  a2 = (const wchar_t *)(v8 + 1LL);
  if ( (unsigned __int64)a2 > 0xFFFFFFFF )
    goto LABEL_8;
  v9 = *((unsigned int *)this + 4);
  if ( (unsigned int)a2 <= (unsigned int)v9 )
  {
    if ( !a3 )
    {
      this = (CLMString *)*((_QWORD *)this + 1);
      if ( v5 < (const wchar_t *)this || (this = (CLMString *)((char *)this + 2 * v9), v5 >= (const wchar_t *)this) )
      {
        a2 = (const wchar_t *)((unsigned int)v7 + 1LL);
        if ( (unsigned __int64)a2 > 0xFFFFFFFF )
          goto LABEL_8;
        (*(void (__fastcall **)(CLMString *, const wchar_t *, __int64))(*(_QWORD *)v6 + 8LL))(v6, a2, 0xFFFFFFFFLL);
      }
    }
  }
  else
  {
    (**(void (__fastcall ***)(CLMString *, const wchar_t *, __int64))this)(this, a2, 0xFFFFFFFFLL);
  }
  a2 = (const wchar_t *)(2LL * (unsigned int)v7);
  if ( !is_mul_ok(2u, v7)
    || (v10 = 2 * v4, !is_mul_ok(2u, v4))
    || (v11 = (unsigned int)(v10 + (_DWORD)a2), (unsigned int)v11 < (unsigned int)v10) )
  {
LABEL_8:
    SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow(this, a2);
  }
  v12 = (_WORD *)*((_QWORD *)v6 + 1);
  if ( v11 <= 2 * (unsigned __int64)*((unsigned int *)v6 + 4) )
  {
    *((_DWORD *)v6 + 5) = v8;
    memcpy_0(&v12[(unsigned __int64)v10 / 2], v5, (unsigned int)a2);
    *(_WORD *)(*((_QWORD *)v6 + 1) + 2LL * *((unsigned int *)v6 + 5)) = 0;
    return *((unsigned int *)v6 + 5);
  }
  else
  {
    *((_DWORD *)v6 + 5) = 0;
    result = 0;
    *v12 = 0;
  }
  return result;
}

```

## disassembly

```asm
0x180005d40  mov     [rsp+arg_10], rsi
0x180005d45  mov     [rsp+arg_18], rdi
0x180005d4a  push    r14; int
0x180005d4c  sub     rsp, 20h
0x180005d50  mov     r14d, r8d
0x180005d53  mov     rdi, rdx
0x180005d56  mov     rsi, rcx
0x180005d59  test    rdx, rdx
0x180005d5c  jz      loc_180005E76
0x180005d62  mov     r8d, 0FFFFFFFFh
0x180005d68  mov     [rsp+28h+arg_0], rbx
0x180005d6d  mov     [rsp+28h+arg_8], rbp
0x180005d72  cmp     r9d, r8d
0x180005d75  jnz     loc_180005E93
0x180005d7b  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x180005d82  inc     rbx
0x180005d85  cmp     word ptr [rdx+rbx*2], 0
0x180005d8a  jnz     short loc_180005D82
0x180005d8c  cmp     rbx, r8
0x180005d8f  ja      short loc_180005DA4
0x180005d91  lea     ebp, [rbx+r14]
0x180005d95  cmp     ebp, r14d
0x180005d98  jb      short loc_180005DA4
0x180005d9a  mov     edx, ebp
0x180005d9c  inc     rdx
0x180005d9f  cmp     rdx, r8
0x180005da2  jbe     short loc_180005DAA
0x180005da4  call    ?SafeIntOnOverflow@?$SafeIntExceptionHandler@VSafeIntException@@@SafeIntInternal@@SAXXZ; SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow(void)
0x180005daa  mov     eax, [rcx+10h]
0x180005dad  cmp     edx, eax
0x180005daf  jbe     short loc_180005E19
0x180005db1  mov     rax, [rcx]
0x180005db4  mov     rax, [rax]
0x180005db7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005dbc  mov     edx, ebx
0x180005dbe  add     rdx, rdx
0x180005dc1  mov     rax, rdx
0x180005dc4  shr     rax, 20h
0x180005dc8  test    eax, eax
0x180005dca  jnz     short loc_180005DA4
0x180005dcc  lea     r9, [r14+r14]
0x180005dd0  mov     rax, r9
0x180005dd3  shr     rax, 20h
0x180005dd7  test    eax, eax
0x180005dd9  jnz     short loc_180005DA4
0x180005ddb  lea     eax, [r9+rdx]
0x180005ddf  cmp     eax, r9d
0x180005de2  jb      short loc_180005DA4
0x180005de4  mov     ecx, [rsi+10h]
0x180005de7  mov     r10, [rsi+8]
0x180005deb  add     rcx, rcx
0x180005dee  cmp     rax, rcx
0x180005df1  jbe     short loc_180005E44
0x180005df3  xor     edx, edx
0x180005df5  mov     [rsi+14h], edx
0x180005df8  xor     eax, eax
0x180005dfa  mov     [r10], dx
0x180005dfe  mov     rbx, [rsp+28h+arg_0]
0x180005e03  mov     rbp, [rsp+28h+arg_8]
0x180005e08  mov     rsi, [rsp+28h+arg_10]
0x180005e0d  mov     rdi, [rsp+28h+arg_18]
0x180005e12  add     rsp, 20h
0x180005e16  pop     r14
0x180005e18  retn
0x180005e19  test    r14d, r14d
0x180005e1c  jnz     short loc_180005DBC
0x180005e1e  mov     rcx, [rcx+8]
0x180005e22  cmp     rdi, rcx
0x180005e25  jnb     short loc_180005E68
0x180005e27  mov     edx, ebx
0x180005e29  inc     rdx
0x180005e2c  cmp     rdx, r8
0x180005e2f  ja      loc_180005DA4
0x180005e35  mov     rax, [rsi]
0x180005e38  mov     rcx, rsi
0x180005e3b  mov     rax, [rax+8]
0x180005e3f  jmp     loc_180005DB7
0x180005e44  mov     r8d, edx; Size
0x180005e47  lea     rcx, [r9+r10]; void *
0x180005e4b  mov     rdx, rdi; Src
0x180005e4e  mov     [rsi+14h], ebp
0x180005e51  call    memcpy_0
0x180005e56  mov     rax, [rsi+8]
0x180005e5a  xor     edx, edx
0x180005e5c  mov     ecx, [rsi+14h]
0x180005e5f  mov     [rax+rcx*2], dx
0x180005e63  mov     eax, [rsi+14h]
0x180005e66  jmp     short loc_180005DFE
0x180005e68  lea     rcx, [rcx+rax*2]
0x180005e6c  cmp     rdi, rcx
0x180005e6f  jnb     short loc_180005E27
0x180005e71  jmp     loc_180005DBC
0x180005e76  mov     rcx, [rsp+28h]; this
0x180005e7b  lea     r8, aOnecoreuapBase_8; "onecoreuap\\base\\appmodel\\search\\com"...
0x180005e82  mov     r9d, 80070057h; char *
0x180005e88  mov     edx, 36h ; '6'; void *
0x180005e8d  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180005e93  mov     ebx, r9d
0x180005e96  jmp     loc_180005D91
```
