# TLMString<32,32,1024>::TLMString<32,32,1024>(wchar_t const *)

- ea: `0x1800098f0`
- end: `0x1800099e3`
- name: `??0?$TLMString@$0CA@$0CA@$0EAA@@@QEAA@PEB_W@Z`
- size: `243`
- prototype: `TLMString<32,32,1024> *__fastcall(TLMString<32,32,1024> *this, _WORD *Src)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000ec40`

## callees

- `0x1800098f0`
- `0x18000b324`
- `0x18000c680`
- `0x18000e7fc`
- `0x18000e878`
- `0x180011135`

## string_xrefs

- `0x1800099b0`: `onecoreuap\base\appmodel\search\common\pkmutild\lmstr.cxx`

## pseudocode

```c
TLMString<32,32,1024> *__fastcall TLMString<32,32,1024>::TLMString<32,32,1024>(TLMString<32,32,1024> *this, _WORD *Src)
{
  unsigned __int64 v4; // rax
  __int64 v5; // rcx
  __int64 v6; // rsi
  unsigned __int64 v7; // rax
  __int64 v8; // rax
  unsigned int *v10; // rax
  int v11; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  TLMString<32,32,1024> *v13; // [rsp+30h] [rbp+8h] BYREF
  int v14; // [rsp+38h] [rbp+10h] BYREF

  v13 = this;
  *((_DWORD *)this + 4) = 33;
  *(_QWORD *)this = &CLMString::`vftable';
  *((_QWORD *)this + 1) = (char *)this + 24;
  if ( !Src )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x91,
      (unsigned int)"onecoreuap\\base\\appmodel\\search\\common\\pkmutild\\lmstr.cxx",
      (const char *)0x80070057LL,
      v11);
  v4 = -1;
  do
    ++v4;
  while ( Src[v4] );
  v5 = 0xFFFFFFFFLL;
  if ( v4 > 0xFFFFFFFF )
    goto LABEL_6;
  v6 = (unsigned int)v4;
  LODWORD(v13) = v4;
  v7 = (unsigned int)v4 + 1LL;
  if ( v7 > 0xFFFFFFFF )
    goto LABEL_6;
  if ( (unsigned int)v7 > 0x21 )
  {
    v10 = SafeInt<unsigned int,SafeIntInternal::SafeIntExceptionHandler<SafeIntException>>::operator+<int>(
            (unsigned int *)&v13,
            &v14);
    CLMString::GrowInConstructor(this, *v10);
  }
  v5 = 2 * v6;
  if ( !is_mul_ok(2u, v6) )
LABEL_6:
    SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow(v5, Src);
  memcpy_0(*((void **)this + 1), Src, (unsigned int)v5);
  v8 = *((_QWORD *)this + 1);
  *((_DWORD *)this + 5) = v6;
  *(_WORD *)(v8 + 2 * v6) = 0;
  *(_QWORD *)this = &TLMString<32,32,1024>::`vftable';
  return this;
}

```

## disassembly

```asm
0x1800098f0  mov     [rsp+arg_18], rbx
0x1800098f5  mov     [rsp+arg_0], rcx
0x1800098fa  push    rdi; int
0x1800098fb  sub     rsp, 20h
0x1800098ff  mov     dword ptr [rcx+10h], 21h ; '!'
0x180009906  lea     rax, ??_7CLMString@@6B@; const CLMString::`vftable'
0x18000990d  mov     [rcx], rax
0x180009910  lea     rax, [rcx+18h]
0x180009914  mov     [rcx+8], rax
0x180009918  mov     rbx, rdx
0x18000991b  mov     rdi, rcx
0x18000991e  test    rdx, rdx
0x180009921  jz      loc_1800099AB
0x180009927  mov     rax, 0FFFFFFFFFFFFFFFFh
0x18000992e  xchg    ax, ax
0x180009930  inc     rax
0x180009933  cmp     word ptr [rdx+rax*2], 0
0x180009938  jnz     short loc_180009930
0x18000993a  mov     ecx, 0FFFFFFFFh
0x18000993f  mov     [rsp+28h+arg_10], rsi
0x180009944  cmp     rax, rcx
0x180009947  ja      short loc_180009958
0x180009949  mov     esi, eax
0x18000994b  mov     dword ptr [rsp+28h+arg_0], esi
0x18000994f  lea     rax, [rsi+1]
0x180009953  cmp     rax, rcx
0x180009956  jbe     short loc_18000995E
0x180009958  call    ?SafeIntOnOverflow@?$SafeIntExceptionHandler@VSafeIntException@@@SafeIntInternal@@SAXXZ; SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow(void)
0x18000995e  cmp     eax, 21h ; '!'
0x180009961  ja      short loc_1800099C8
0x180009963  lea     rcx, [rsi+rsi]
0x180009967  mov     rax, rcx
0x18000996a  shr     rax, 20h
0x18000996e  test    eax, eax
0x180009970  jnz     short loc_180009958
0x180009972  mov     r8d, ecx; Size
0x180009975  mov     rdx, rbx; Src
0x180009978  mov     rcx, [rdi+8]; void *
0x18000997c  call    memcpy_0
0x180009981  mov     rax, [rdi+8]
0x180009985  xor     edx, edx
0x180009987  mov     rbx, [rsp+28h+arg_18]
0x18000998c  mov     [rdi+14h], esi
0x18000998f  mov     [rax+rsi*2], dx
0x180009993  lea     rax, ??_7?$TLMString@$0CA@$0CA@$0EAA@@@6B@; const TLMString<32,32,1024>::`vftable'
0x18000999a  mov     rsi, [rsp+28h+arg_10]
0x18000999f  mov     [rdi], rax
0x1800099a2  mov     rax, rdi
0x1800099a5  add     rsp, 20h
0x1800099a9  pop     rdi
0x1800099aa  retn
0x1800099ab  mov     rcx, [rsp+28h]; this
0x1800099b0  lea     r8, aOnecoreuapBase_8; "onecoreuap\\base\\appmodel\\search\\com"...
0x1800099b7  mov     r9d, 80070057h; char *
0x1800099bd  mov     edx, 91h; void *
0x1800099c2  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800099c8  lea     rdx, [rsp+28h+arg_8]
0x1800099cd  lea     rcx, [rsp+28h+arg_0]
0x1800099d2  call    ??$?HH@?$SafeInt@IV?$SafeIntExceptionHandler@VSafeIntException@@@SafeIntInternal@@@@QEBA?AV0@H@Z; SafeInt<uint,SafeIntInternal::SafeIntExceptionHandler<SafeIntException>>::operator+<int>(int)
0x1800099d7  mov     rcx, rdi; this
0x1800099da  mov     edx, [rax]; unsigned int
0x1800099dc  call    ?GrowInConstructor@CLMString@@IEAAXI@Z; CLMString::GrowInConstructor(uint)
0x1800099e1  jmp     short loc_180009963
```
