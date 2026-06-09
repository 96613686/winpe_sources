# CLMString::AssignInConstructor(wchar_t const *,uint)

- ea: `0x18000ada0`
- end: `0x18000ae7a`
- name: `?AssignInConstructor@CLMString@@IEAAHPEB_WI@Z`
- size: `218`
- prototype: `__int64 __fastcall(void **this, const wchar_t *, unsigned int)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18001ce74`

## callees

- `0x18000ada0`
- `0x18000b324`
- `0x18000c680`
- `0x18000e7fc`
- `0x18000e878`
- `0x180011135`

## string_xrefs

- `0x18000adbb`: `onecoreuap\base\appmodel\search\common\pkmutild\lmstr.cxx`

## pseudocode

```c
__int64 __fastcall CLMString::AssignInConstructor(void **this, const wchar_t *a2, unsigned int a3)
{
  unsigned __int64 v3; // rbx
  __int64 v6; // rcx
  unsigned __int64 v7; // rax
  unsigned int *v8; // rax
  _WORD *v9; // rax
  int v11; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  unsigned int v13; // [rsp+48h] [rbp+10h] BYREF
  int v14; // [rsp+58h] [rbp+20h] BYREF

  LODWORD(v3) = a3;
  if ( !a2 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x91,
      (unsigned int)"onecoreuap\\base\\appmodel\\search\\common\\pkmutild\\lmstr.cxx",
      (const char *)0x80070057LL,
      v11);
  v6 = 0xFFFFFFFFLL;
  v13 = a3;
  if ( a3 == -1 )
  {
    v3 = -1;
    do
      ++v3;
    while ( a2[v3] );
    if ( v3 > 0xFFFFFFFF )
      goto LABEL_13;
    v13 = v3;
  }
  v7 = (unsigned int)v3 + 1LL;
  if ( v7 > 0xFFFFFFFF )
    goto LABEL_13;
  if ( (unsigned int)v7 > *((_DWORD *)this + 4) )
  {
    v8 = SafeInt<unsigned int,SafeIntInternal::SafeIntExceptionHandler<SafeIntException>>::operator+<int>(&v13, &v14);
    CLMString::GrowInConstructor((CLMString *)this, *v8);
  }
  if ( !is_mul_ok(2u, v3) )
LABEL_13:
    SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow(v6, a2);
  memcpy_0(this[1], a2, (unsigned int)(2 * v3));
  v9 = this[1];
  *((_DWORD *)this + 5) = v3;
  v9[(unsigned int)v3] = 0;
  return *((unsigned int *)this + 5);
}

```

## disassembly

```asm
0x18000ada0  push    rbx
0x18000ada2  push    rbp
0x18000ada3  push    rdi; int
0x18000ada4  sub     rsp, 20h
0x18000ada8  mov     ebx, r8d
0x18000adab  mov     rdi, rdx
0x18000adae  mov     rbp, rcx
0x18000adb1  test    rdx, rdx
0x18000adb4  jnz     short loc_18000ADD3
0x18000adb6  mov     rcx, [rsp+38h]; this
0x18000adbb  lea     r8, aOnecoreuapBase_8; "onecoreuap\\base\\appmodel\\search\\com"...
0x18000adc2  mov     r9d, 80070057h; char *
0x18000adc8  mov     edx, 91h; void *
0x18000adcd  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18000add3  mov     ecx, 0FFFFFFFFh
0x18000add8  mov     [rsp+38h+arg_0], rsi
0x18000addd  mov     [rsp+38h+arg_10], r14
0x18000ade2  mov     [rsp+38h+arg_8], ebx
0x18000ade6  cmp     ebx, ecx
0x18000ade8  jnz     short loc_18000AE04
0x18000adea  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x18000adf1  inc     rbx
0x18000adf4  cmp     word ptr [rdx+rbx*2], 0
0x18000adf9  jnz     short loc_18000ADF1
0x18000adfb  cmp     rbx, rcx
0x18000adfe  ja      short loc_18000AE74
0x18000ae00  mov     [rsp+38h+arg_8], ebx
0x18000ae04  mov     esi, ebx
0x18000ae06  mov     eax, ebx
0x18000ae08  mov     r14d, ebx
0x18000ae0b  lea     rax, [rsi+1]
0x18000ae0f  cmp     rax, rcx
0x18000ae12  ja      short loc_18000AE74
0x18000ae14  cmp     eax, [rbp+10h]
0x18000ae17  jbe     short loc_18000AE32
0x18000ae19  lea     rdx, [rsp+38h+arg_18]
0x18000ae1e  lea     rcx, [rsp+38h+arg_8]
0x18000ae23  call    ??$?HH@?$SafeInt@IV?$SafeIntExceptionHandler@VSafeIntException@@@SafeIntInternal@@@@QEBA?AV0@H@Z; SafeInt<uint,SafeIntInternal::SafeIntExceptionHandler<SafeIntException>>::operator+<int>(int)
0x18000ae28  mov     rcx, rbp; this
0x18000ae2b  mov     edx, [rax]; unsigned int
0x18000ae2d  call    ?GrowInConstructor@CLMString@@IEAAXI@Z; CLMString::GrowInConstructor(uint)
0x18000ae32  add     rsi, rsi
0x18000ae35  mov     rax, rsi
0x18000ae38  shr     rax, 20h
0x18000ae3c  test    eax, eax
0x18000ae3e  jnz     short loc_18000AE74
0x18000ae40  mov     rcx, [rbp+8]; void *
0x18000ae44  mov     rdx, rdi; Src
0x18000ae47  mov     r8d, esi; Size
0x18000ae4a  call    memcpy_0
0x18000ae4f  mov     rax, [rbp+8]
0x18000ae53  xor     edx, edx
0x18000ae55  mov     rsi, [rsp+38h+arg_0]
0x18000ae5a  mov     ecx, r14d
0x18000ae5d  mov     r14, [rsp+38h+arg_10]
0x18000ae62  mov     [rbp+14h], ebx
0x18000ae65  mov     [rax+rcx*2], dx
0x18000ae69  mov     eax, [rbp+14h]
0x18000ae6c  add     rsp, 20h
0x18000ae70  pop     rdi
0x18000ae71  pop     rbp
0x18000ae72  pop     rbx
0x18000ae73  retn
0x18000ae74  call    ?SafeIntOnOverflow@?$SafeIntExceptionHandler@VSafeIntException@@@SafeIntInternal@@SAXXZ; SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow(void)
```
