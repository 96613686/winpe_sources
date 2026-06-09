# Marshal::Details::WriteObjectXml(Marshal::XmlWriter &,void const *,Marshal::MarshalContext const &,Marshal::Details::ArrayView<Marshal::FieldData>,Marshal::Details::ArrayView<Marshal::Details::BaseTypeData const *>,Marshal::Details::ArrayView<Marshal::Details::XmlTypeData const *>)

- ea: `0x180021190`
- end: `0x180021378`
- name: `?WriteObjectXml@Details@Marshal@@YAXAEAUXmlWriter@2@PEBXAEBVMarshalContext@2@V?$ArrayView@UFieldData@Marshal@@@12@V?$ArrayView@PEBUBaseTypeData@Details@Marshal@@@12@V?$ArrayView@PEBUXmlTypeData@Details@Marshal@@@12@@Z`
- size: `488`
- prototype: ``
- caller_count: `29`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x1800175e8`
- `0x18001771c`
- `0x180017854`
- `0x180017988`
- `0x180017abc`
- `0x180017bf0`
- `0x180017d28`
- `0x180017e5c`
- `0x180017f90`
- `0x1800180c4`
- `0x1800181f8`
- `0x18001832c`
- `0x180018a00`
- `0x180018b40`
- `0x180018c80`
- `0x180018dc0`
- `0x180018f00`
- `0x180019040`
- `0x180019180`
- `0x1800192c0`
- `0x180019400`
- `0x180019540`
- `0x180019680`
- `0x1800197c0`
- `0x180019900`
- `0x180019a40`
- `0x180019b80`
- `0x180019cc0`
- `0x180019e00`

## callees

- `0x18000bdc8`
- `0x180021190`
- `0x180034010`

## string_xrefs

- `0x180021366`: `onecore\internal\vm\inc\MarshalXml.h`

## pseudocode

```c
unsigned __int64 __fastcall Marshal::Details::WriteObjectXml(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        const char *a4,
        _QWORD *a5,
        _QWORD *a6)
{
  __int64 v6; // rbx
  unsigned __int64 v7; // rdi
  __int64 v8; // r14
  char v9; // r12
  unsigned __int64 v10; // rbp
  __int64 v11; // r15
  __int64 v13; // r10
  __int64 v14; // rsi
  __int64 v15; // rbx
  __int64 v16; // r15
  char v17; // al
  unsigned __int64 result; // rax
  __int64 i; // rsi
  __int64 v20; // rdi
  __int64 v21; // rbp
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]
  __int64 v24; // [rsp+80h] [rbp+18h]
  __int64 v25; // [rsp+88h] [rbp+20h]

  v24 = a3;
  v6 = *(_QWORD *)a4;
  v7 = -1;
  v8 = *((_QWORD *)a4 + 1);
  v9 = 0;
  v10 = 0;
  v25 = *(_QWORD *)a4;
  v11 = a3;
  v13 = a1;
  v14 = *(_QWORD *)a4;
  if ( *(_QWORD *)a4 != v8 )
  {
    v15 = a3;
    do
    {
      if ( (*(_BYTE *)(v14 + 12) & 4) != 0 )
      {
        v16 = a2 + *(unsigned int *)(v14 + 8);
        if ( (*(_BYTE *)(v14 + 12) & 1) == 0
          || (v17 = (**(__int64 (__fastcall ***)(__int64, _QWORD))(*a5 + 8 * v10))(
                      a2 + *(unsigned int *)(v14 + 8),
                      *(_QWORD *)(v14 + 16)),
              v13 = a1,
              !v17) )
        {
          LOBYTE(a3) = 1;
          (**(void (__fastcall ***)(__int64, _QWORD, __int64, __int64, __int64))(*a6 + 8 * v10))(
            v13,
            *(_QWORD *)v14,
            a3,
            v16,
            v15);
          v13 = a1;
        }
      }
      else if ( (*(_BYTE *)(v14 + 12) & 8) != 0 )
      {
        v7 = v10;
      }
      else
      {
        v9 = 1;
      }
      ++v10;
      v14 += 32;
    }
    while ( v14 != v8 );
    v6 = v25;
    v11 = v24;
  }
  result = (v8 - v6) >> 5;
  if ( v9 )
  {
    if ( v7 < result )
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0x602,
        (unsigned int)"onecore\\internal\\vm\\inc\\MarshalXml.h",
        a4);
    for ( i = 0; v6 != v8; v6 += 32 )
    {
      if ( (*(_BYTE *)(v6 + 12) & 4) == 0 )
      {
        v20 = 8 * i;
        v21 = a2 + *(unsigned int *)(v6 + 8);
        if ( (*(_BYTE *)(v6 + 12) & 1) == 0
          || (result = (**(__int64 (__fastcall ***)(__int64, _QWORD))(v20 + *a5))(
                         a2 + *(unsigned int *)(v6 + 8),
                         *(_QWORD *)(v6 + 16)),
              !(_BYTE)result) )
        {
          result = (**(__int64 (__fastcall ***)(__int64, _QWORD, _QWORD, __int64, __int64))(v20 + *a6))(
                     a1,
                     *(_QWORD *)v6,
                     0,
                     v21,
                     v11);
        }
      }
      ++i;
    }
  }
  else if ( v7 < result )
  {
    _mm_lfence();
    return (**(__int64 (__fastcall ***)(__int64, _QWORD, _QWORD, __int64, __int64))(*a6 + 8 * v7))(
             v13,
             0,
             0,
             a2 + *(unsigned int *)(32 * v7 + v6 + 8),
             v11);
  }
  return result;
}

```

## disassembly

```asm
0x180021190  mov     rax, rsp
0x180021193  mov     [rax+10h], rbx
0x180021197  mov     [rax+18h], r8
0x18002119b  mov     [rax+8], rcx
0x18002119f  push    rbp
0x1800211a0  push    rsi
0x1800211a1  push    rdi
0x1800211a2  push    r12
0x1800211a4  push    r13
0x1800211a6  push    r14
0x1800211a8  push    r15
0x1800211aa  sub     rsp, 30h
0x1800211ae  mov     rbx, [r9]
0x1800211b1  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1800211b5  mov     r14, [r9+8]
0x1800211b9  xor     r12b, r12b
0x1800211bc  xor     ebp, ebp
0x1800211be  mov     [rsp+68h+arg_18], rbx
0x1800211c6  mov     r15, r8
0x1800211c9  mov     r13, rdx
0x1800211cc  mov     r10, rcx
0x1800211cf  mov     rsi, rbx
0x1800211d2  cmp     rbx, r14
0x1800211d5  jz      loc_180021275
0x1800211db  mov     rbx, r8
0x1800211de  test    byte ptr [rsi+0Ch], 4
0x1800211e2  jz      short loc_180021247
0x1800211e4  mov     r15d, [rsi+8]
0x1800211e8  add     r15, r13
0x1800211eb  test    byte ptr [rsi+0Ch], 1
0x1800211ef  jz      short loc_180021218
0x1800211f1  mov     rax, [rsp+68h+arg_20]
0x1800211f9  mov     rdx, [rsi+10h]
0x1800211fd  mov     rax, [rax]
0x180021200  mov     rcx, [rax+rbp*8]
0x180021204  mov     rax, [rcx]
0x180021207  mov     rcx, r15
0x18002120a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002120f  mov     r10, [rsp+68h+arg_0]
0x180021214  test    al, al
0x180021216  jnz     short loc_180021255
0x180021218  mov     rax, [rsp+68h+arg_28]
0x180021220  mov     r9, r15
0x180021223  mov     rdx, [rsi]
0x180021226  mov     r8b, 1
0x180021229  mov     [rsp+68h+var_48], rbx
0x18002122e  mov     rax, [rax]
0x180021231  mov     rcx, [rax+rbp*8]
0x180021235  mov     rax, [rcx]
0x180021238  mov     rcx, r10
0x18002123b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021240  mov     r10, [rsp+68h+arg_0]
0x180021245  jmp     short loc_180021255
0x180021247  test    byte ptr [rsi+0Ch], 8
0x18002124b  jz      short loc_180021252
0x18002124d  mov     rdi, rbp
0x180021250  jmp     short loc_180021255
0x180021252  mov     r12b, 1
0x180021255  inc     rbp
0x180021258  add     rsi, 20h ; ' '
0x18002125c  cmp     rsi, r14
0x18002125f  jnz     loc_1800211DE
0x180021265  mov     rbx, [rsp+68h+arg_18]
0x18002126d  mov     r15, [rsp+68h+arg_10]
0x180021275  mov     rax, r14
0x180021278  sub     rax, rbx
0x18002127b  sar     rax, 5
0x18002127f  test    r12b, r12b
0x180021282  jz      loc_180021313
0x180021288  cmp     rdi, rax
0x18002128b  jb      loc_180021361
0x180021291  xor     esi, esi
0x180021293  cmp     rbx, r14
0x180021296  jz      loc_18002134B
0x18002129c  mov     r12, [rsp+68h+arg_0]
0x1800212a1  test    byte ptr [rbx+0Ch], 4
0x1800212a5  jnz     short loc_180021305
0x1800212a7  mov     ebp, [rbx+8]
0x1800212aa  lea     rdi, ds:0[rsi*8]
0x1800212b2  add     rbp, r13
0x1800212b5  test    byte ptr [rbx+0Ch], 1
0x1800212b9  jz      short loc_1800212DD
0x1800212bb  mov     rax, [rsp+68h+arg_20]
0x1800212c3  mov     rdx, [rbx+10h]
0x1800212c7  mov     rax, [rax]
0x1800212ca  mov     rcx, [rdi+rax]
0x1800212ce  mov     rax, [rcx]
0x1800212d1  mov     rcx, rbp
0x1800212d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800212d9  test    al, al
0x1800212db  jnz     short loc_180021305
0x1800212dd  mov     rax, [rsp+68h+arg_28]
0x1800212e5  mov     r9, rbp
0x1800212e8  mov     rdx, [rbx]
0x1800212eb  xor     r8d, r8d
0x1800212ee  mov     [rsp+68h+var_48], r15
0x1800212f3  mov     rax, [rax]
0x1800212f6  mov     rcx, [rdi+rax]
0x1800212fa  mov     rax, [rcx]
0x1800212fd  mov     rcx, r12
0x180021300  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021305  inc     rsi
0x180021308  add     rbx, 20h ; ' '
0x18002130c  cmp     rbx, r14
0x18002130f  jnz     short loc_1800212A1
0x180021311  jmp     short loc_18002134B
0x180021313  cmp     rdi, rax
0x180021316  jnb     short loc_18002134B
0x180021318  lfence
0x18002131b  mov     rax, [rsp+68h+arg_28]
0x180021323  xor     r8d, r8d
0x180021326  xor     edx, edx
0x180021328  mov     [rsp+68h+var_48], r15
0x18002132d  mov     rax, [rax]
0x180021330  mov     rcx, [rax+rdi*8]
0x180021334  shl     rdi, 5
0x180021338  mov     rax, [rcx]
0x18002133b  mov     rcx, r10
0x18002133e  mov     r9d, [rdi+rbx+8]
0x180021343  add     r9, r13
0x180021346  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002134b  mov     rbx, [rsp+68h+arg_8]
0x180021350  add     rsp, 30h
0x180021354  pop     r15
0x180021356  pop     r14
0x180021358  pop     r13
0x18002135a  pop     r12
0x18002135c  pop     rdi
0x18002135d  pop     rsi
0x18002135e  pop     rbp
0x18002135f  retn
0x180021361  mov     rcx, [rsp+68h]; this
0x180021366  lea     r8, aOnecoreInterna_2; "onecore\\internal\\vm\\inc\\MarshalXml."...
0x18002136d  mov     edx, 602h; void *
0x180021372  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
```
