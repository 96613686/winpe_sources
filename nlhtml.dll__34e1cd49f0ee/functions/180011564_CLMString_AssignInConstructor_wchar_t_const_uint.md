# CLMString::AssignInConstructor(wchar_t const *,uint)

- ea: `0x180011564`
- end: `0x180011624`
- name: `?AssignInConstructor@CLMString@@IEAAHPEB_WI@Z`
- size: `192`
- prototype: `int(CLMString *__hidden this, const wchar_t *, unsigned int)`
- caller_count: `2`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000bea0`
- `0x18001f4f4`

## callees

- `0x180010c90`
- `0x180011564`
- `0x180013484`
- `0x180013500`
- `0x180013968`
- `0x180023388`

## string_xrefs

- `0x1800115f1`: `onecoreuap\base\appmodel\search\common\pkmutild\lmstr.cxx`

## pseudocode

```c
__int64 __fastcall CLMString::AssignInConstructor(void **this, const wchar_t *a2, __int64 a3)
{
  unsigned __int64 v5; // rax
  __int64 v6; // rcx
  __int64 v7; // rbx
  unsigned __int64 v8; // rax
  _WORD *v9; // rcx
  unsigned int *v11; // rax
  int v12; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  char v14; // [rsp+48h] [rbp+10h] BYREF
  int v15; // [rsp+50h] [rbp+18h] BYREF

  v15 = a3;
  if ( !a2 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x91,
      (unsigned int)"onecoreuap\\base\\appmodel\\search\\common\\pkmutild\\lmstr.cxx",
      (const char *)0x80070057LL,
      v12);
  v5 = -1;
  do
    ++v5;
  while ( a2[v5] );
  v6 = 0xFFFFFFFFLL;
  if ( v5 > 0xFFFFFFFF )
    goto LABEL_10;
  v7 = (unsigned int)v5;
  v15 = v5;
  v8 = (unsigned int)v5 + 1LL;
  if ( v8 > 0xFFFFFFFF )
    goto LABEL_10;
  if ( (unsigned int)v8 > *((_DWORD *)this + 4) )
  {
    v11 = (unsigned int *)SafeInt<unsigned int,SafeIntInternal::SafeIntExceptionHandler<SafeIntException>>::operator+<int>(
                            &v15,
                            &v14);
    CLMString::GrowInConstructor((CLMString *)this, *v11);
  }
  v6 = 2 * v7;
  if ( !is_mul_ok(2u, v7) )
LABEL_10:
    SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow(v6, a2, a3);
  memcpy_0(this[1], a2, (unsigned int)v6);
  v9 = this[1];
  *((_DWORD *)this + 5) = v7;
  v9[v7] = 0;
  return *((unsigned int *)this + 5);
}

```

## disassembly

```asm
0x180011564  mov     [rsp+arg_0], rbx
0x180011569  mov     [rsp+arg_10], r8d
0x18001156e  push    rbp
0x18001156f  push    rsi
0x180011570  push    rdi; int
0x180011571  sub     rsp, 20h
0x180011575  xor     ebp, ebp
0x180011577  mov     rsi, rdx
0x18001157a  mov     rdi, rcx
0x18001157d  test    rdx, rdx
0x180011580  jz      short loc_1800115EC
0x180011582  or      rax, 0FFFFFFFFFFFFFFFFh
0x180011586  inc     rax
0x180011589  cmp     [rdx+rax*2], bp
0x18001158d  jnz     short loc_180011586
0x18001158f  mov     ecx, 0FFFFFFFFh
0x180011594  cmp     rax, rcx
0x180011597  ja      short loc_1800115E6
0x180011599  mov     ebx, eax
0x18001159b  mov     [rsp+38h+arg_10], ebx
0x18001159f  lea     rax, [rbx+1]
0x1800115a3  cmp     rax, rcx
0x1800115a6  ja      short loc_1800115E6
0x1800115a8  cmp     eax, [rdi+10h]
0x1800115ab  ja      short loc_180011609
0x1800115ad  lea     rcx, [rbx+rbx]
0x1800115b1  mov     rax, rcx
0x1800115b4  shr     rax, 20h
0x1800115b8  test    eax, eax
0x1800115ba  jnz     short loc_1800115E6
0x1800115bc  mov     r8d, ecx; Size
0x1800115bf  mov     rdx, rsi; Src
0x1800115c2  mov     rcx, [rdi+8]; void *
0x1800115c6  call    memcpy_0
0x1800115cb  mov     rcx, [rdi+8]
0x1800115cf  mov     [rdi+14h], ebx
0x1800115d2  mov     [rcx+rbx*2], bp
0x1800115d6  mov     eax, [rdi+14h]
0x1800115d9  mov     rbx, [rsp+38h+arg_0]
0x1800115de  add     rsp, 20h
0x1800115e2  pop     rdi
0x1800115e3  pop     rsi
0x1800115e4  pop     rbp
0x1800115e5  retn
0x1800115e6  call    ?SafeIntOnOverflow@?$SafeIntExceptionHandler@VSafeIntException@@@SafeIntInternal@@SAXXZ; SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow(void)
0x1800115ec  mov     rcx, [rsp+38h]; this
0x1800115f1  lea     r8, aOnecoreuapBase_2; "onecoreuap\\base\\appmodel\\search\\com"...
0x1800115f8  mov     r9d, 80070057h; char *
0x1800115fe  mov     edx, 91h; void *
0x180011603  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180011609  lea     rdx, [rsp+38h+arg_8]
0x18001160e  lea     rcx, [rsp+38h+arg_10]
0x180011613  call    ??$?HH@?$SafeInt@IV?$SafeIntExceptionHandler@VSafeIntException@@@SafeIntInternal@@@@QEBA?AV0@H@Z; SafeInt<uint,SafeIntInternal::SafeIntExceptionHandler<SafeIntException>>::operator+<int>(int)
0x180011618  mov     rcx, rdi; this
0x18001161b  mov     edx, [rax]; unsigned int
0x18001161d  call    ?GrowInConstructor@CLMString@@IEAAXI@Z; CLMString::GrowInConstructor(uint)
0x180011622  jmp     short loc_1800115AD
```
