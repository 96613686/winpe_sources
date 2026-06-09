# TLMString<64,64,32767>::TLMString<64,64,32767>(TLMString<64,64,32767> const &)

- ea: `0x18000bf0c`
- end: `0x18000bfee`
- name: `??0?$TLMString@$0EA@$0EA@$0HPPP@@@QEAA@AEBV0@@Z`
- size: `226`
- prototype: `TLMString<64,64,32767> *__fastcall(TLMString<64,64,32767> *this, __int64)`
- caller_count: `2`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180002aa0`
- `0x180006660`

## callees

- `0x18000b324`
- `0x18000bf0c`
- `0x18000c680`
- `0x18000e7fc`
- `0x18000e878`
- `0x180011135`

## string_xrefs

- `0x18000bf49`: `onecoreuap\base\appmodel\search\common\pkmutild\lmstr.cxx`

## pseudocode

```c
TLMString<64,64,32767> *__fastcall TLMString<64,64,32767>::TLMString<64,64,32767>(
        TLMString<64,64,32767> *this,
        __int64 a2)
{
  _WORD *v2; // rsi
  unsigned __int64 v4; // rax
  __int64 v5; // rcx
  __int64 v6; // rdi
  unsigned __int64 v7; // rax
  unsigned int *v8; // rax
  __int64 v9; // rcx
  int v11; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  TLMString<64,64,32767> *v13; // [rsp+40h] [rbp+8h] BYREF
  int v14; // [rsp+48h] [rbp+10h] BYREF

  v13 = this;
  v2 = *(_WORD **)(a2 + 8);
  *(_QWORD *)this = &CLMString::`vftable';
  *((_DWORD *)this + 4) = 65;
  *((_QWORD *)this + 1) = (char *)this + 24;
  if ( !v2 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x91,
      (unsigned int)"onecoreuap\\base\\appmodel\\search\\common\\pkmutild\\lmstr.cxx",
      (const char *)0x80070057LL,
      v11);
  v4 = -1;
  do
    ++v4;
  while ( v2[v4] );
  v5 = 0xFFFFFFFFLL;
  if ( v4 > 0xFFFFFFFF )
    goto LABEL_11;
  v6 = (unsigned int)v4;
  LODWORD(v13) = v4;
  v7 = (unsigned int)v4 + 1LL;
  if ( v7 > 0xFFFFFFFF )
    goto LABEL_11;
  if ( (unsigned int)v7 > 0x41 )
  {
    v8 = SafeInt<unsigned int,SafeIntInternal::SafeIntExceptionHandler<SafeIntException>>::operator+<int>(
           (unsigned int *)&v13,
           &v14);
    CLMString::GrowInConstructor(this, *v8);
  }
  v5 = 2 * v6;
  if ( !is_mul_ok(2u, v6) )
LABEL_11:
    SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow(v5, a2);
  memcpy_0(*((void **)this + 1), v2, (unsigned int)v5);
  v9 = *((_QWORD *)this + 1);
  *((_DWORD *)this + 5) = v6;
  *(_WORD *)(v9 + 2 * v6) = 0;
  *(_QWORD *)this = &TLMString<64,64,32767>::`vftable';
  return this;
}

```

## disassembly

```asm
0x18000bf0c  mov     [rsp+arg_10], rbx
0x18000bf11  mov     [rsp+arg_0], rcx
0x18000bf16  push    rbp
0x18000bf17  push    rsi
0x18000bf18  push    rdi; int
0x18000bf19  sub     rsp, 20h
0x18000bf1d  mov     rsi, [rdx+8]
0x18000bf21  lea     rax, ??_7CLMString@@6B@; const CLMString::`vftable'
0x18000bf28  mov     [rcx], rax
0x18000bf2b  xor     ebp, ebp
0x18000bf2d  mov     dword ptr [rcx+10h], 41h ; 'A'
0x18000bf34  lea     rax, [rcx+18h]
0x18000bf38  mov     [rcx+8], rax
0x18000bf3c  mov     rbx, rcx
0x18000bf3f  test    rsi, rsi
0x18000bf42  jnz     short loc_18000BF61
0x18000bf44  mov     rcx, [rsp+38h]; this
0x18000bf49  lea     r8, aOnecoreuapBase_8; "onecoreuap\\base\\appmodel\\search\\com"...
0x18000bf50  mov     r9d, 80070057h; char *
0x18000bf56  mov     edx, 91h; void *
0x18000bf5b  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18000bf61  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000bf65  inc     rax
0x18000bf68  cmp     [rsi+rax*2], bp
0x18000bf6c  jnz     short loc_18000BF65
0x18000bf6e  mov     ecx, 0FFFFFFFFh
0x18000bf73  cmp     rax, rcx
0x18000bf76  ja      short loc_18000BFE8
0x18000bf78  mov     edi, eax
0x18000bf7a  mov     dword ptr [rsp+38h+arg_0], edi
0x18000bf7e  lea     rax, [rdi+1]
0x18000bf82  cmp     rax, rcx
0x18000bf85  ja      short loc_18000BFE8
0x18000bf87  cmp     eax, 41h ; 'A'
0x18000bf8a  jbe     short loc_18000BFA5
0x18000bf8c  lea     rdx, [rsp+38h+arg_8]
0x18000bf91  lea     rcx, [rsp+38h+arg_0]
0x18000bf96  call    ??$?HH@?$SafeInt@IV?$SafeIntExceptionHandler@VSafeIntException@@@SafeIntInternal@@@@QEBA?AV0@H@Z; SafeInt<uint,SafeIntInternal::SafeIntExceptionHandler<SafeIntException>>::operator+<int>(int)
0x18000bf9b  mov     rcx, rbx; this
0x18000bf9e  mov     edx, [rax]; unsigned int
0x18000bfa0  call    ?GrowInConstructor@CLMString@@IEAAXI@Z; CLMString::GrowInConstructor(uint)
0x18000bfa5  lea     rcx, [rdi+rdi]
0x18000bfa9  mov     rax, rcx
0x18000bfac  shr     rax, 20h
0x18000bfb0  test    eax, eax
0x18000bfb2  jnz     short loc_18000BFE8
0x18000bfb4  mov     r8d, ecx; Size
0x18000bfb7  mov     rdx, rsi; Src
0x18000bfba  mov     rcx, [rbx+8]; void *
0x18000bfbe  call    memcpy_0
0x18000bfc3  mov     rcx, [rbx+8]
0x18000bfc7  lea     rax, ??_7?$TLMString@$0EA@$0EA@$0HPPP@@@6B@; const TLMString<64,64,32767>::`vftable'
0x18000bfce  mov     [rbx+14h], edi
0x18000bfd1  mov     [rcx+rdi*2], bp
0x18000bfd5  mov     [rbx], rax
0x18000bfd8  mov     rax, rbx
0x18000bfdb  mov     rbx, [rsp+38h+arg_10]
0x18000bfe0  add     rsp, 20h
0x18000bfe4  pop     rdi
0x18000bfe5  pop     rsi
0x18000bfe6  pop     rbp
0x18000bfe7  retn
0x18000bfe8  call    ?SafeIntOnOverflow@?$SafeIntExceptionHandler@VSafeIntException@@@SafeIntInternal@@SAXXZ; SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow(void)
```
