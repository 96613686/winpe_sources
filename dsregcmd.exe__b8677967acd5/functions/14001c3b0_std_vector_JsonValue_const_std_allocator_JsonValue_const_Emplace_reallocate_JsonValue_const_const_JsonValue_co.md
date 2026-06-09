# std::vector<JsonValue const *,std::allocator<JsonValue const *>>::_Emplace_reallocate<JsonValue const * const &>(JsonValue const * * const,JsonValue const * const &)

- ea: `0x14001c3b0`
- end: `0x14001c537`
- name: `??$_Emplace_reallocate@AEBQEBVJsonValue@@@?$vector@PEBVJsonValue@@V?$allocator@PEBVJsonValue@@@std@@@std@@AEAAPEAPEBVJsonValue@@QEAPEBV2@AEBQEBV2@@Z`
- size: `391`
- prototype: `char *__fastcall(_QWORD *, _BYTE *, _QWORD *)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, registry_config`

## callers

- `0x14001cda4`

## callees

- `0x1400017d4`
- `0x1400028ac`
- `0x1400041a4`
- `0x140014020`
- `0x14001c3b0`
- `0x14002c40c`

## pseudocode

```c
char *__fastcall std::vector<JsonValue const *>::_Emplace_reallocate<JsonValue const * const &>(
        _QWORD *a1,
        _BYTE *a2,
        _QWORD *a3)
{
  _BYTE *v3; // rbp
  __int64 v6; // r9
  unsigned __int64 v8; // rcx
  unsigned __int64 v9; // rdx
  __int64 v10; // r12
  unsigned __int64 v11; // rsi
  size_t v12; // rsi
  _QWORD *v13; // rbx
  void *v14; // rax
  _QWORD *v15; // r15
  void *v16; // rcx
  _BYTE *v17; // r8
  _BYTE *v18; // rdx
  size_t v19; // r8
  _BYTE *v20; // rcx
  _BYTE *v21; // rax
  char *result; // rax

  v3 = (_BYTE *)*a1;
  v6 = (__int64)(a1[1] - *a1) >> 3;
  if ( v6 == 0x1FFFFFFFFFFFFFFFLL )
    std::vector<WSTrustMEX::PolicyInfo>::_Xlength();
  v8 = (__int64)(a1[2] - (_QWORD)v3) >> 3;
  v9 = v8 >> 1;
  if ( v8 > 0x1FFFFFFFFFFFFFFFLL - (v8 >> 1) )
    goto LABEL_24;
  v10 = v6 + 1;
  v11 = v6 + 1;
  if ( v8 + v9 >= v6 + 1 )
    v11 = v8 + v9;
  if ( v11 > 0x1FFFFFFFFFFFFFFFLL )
    goto LABEL_24;
  v12 = 8 * v11;
  if ( !v12 )
  {
    v13 = 0;
    goto LABEL_13;
  }
  if ( v12 < 0x1000 )
  {
    v13 = operator new(v12);
    goto LABEL_13;
  }
  if ( v12 + 39 < v12 )
LABEL_24:
    std::_Throw_bad_array_new_length();
  v14 = operator new(v12 + 39);
  if ( !v14 )
    goto LABEL_19;
  v13 = (_QWORD *)(((unsigned __int64)v14 + 39) & 0xFFFFFFFFFFFFFFE0uLL);
  *(v13 - 1) = v14;
LABEL_13:
  v15 = &v13[(a2 - v3) >> 3];
  *v15 = *a3;
  v16 = v13;
  v17 = (_BYTE *)a1[1];
  v18 = (_BYTE *)*a1;
  if ( a2 == v17 )
  {
    v19 = v17 - v18;
  }
  else
  {
    memmove_0(v13, v18, (size_t)&a2[-*a1]);
    v16 = v15 + 1;
    v19 = a1[1] - (_QWORD)a2;
    v18 = a2;
  }
  memmove_0(v16, v18, v19);
  v20 = (_BYTE *)*a1;
  if ( *a1 )
  {
    if ( (unsigned __int64)(8 * ((__int64)(a1[2] - (_QWORD)v20) >> 3)) < 0x1000 )
    {
      v21 = (_BYTE *)*a1;
    }
    else
    {
      v21 = (_BYTE *)*((_QWORD *)v20 - 1);
      if ( (unsigned __int64)(v20 - v21 - 8) > 0x1F )
LABEL_19:
        __fastfail(5u);
    }
    operator delete(v21);
  }
  *a1 = v13;
  a1[1] = &v13[v10];
  result = (char *)&v13[(a2 - v3) >> 3];
  a1[2] = &v13[v12 / 8];
  return result;
}

```

## disassembly

```asm
0x14001c3b0  push    rbx
0x14001c3b2  push    rbp
0x14001c3b3  push    rsi
0x14001c3b4  push    rdi
0x14001c3b5  push    r12
0x14001c3b7  push    r13
0x14001c3b9  push    r14
0x14001c3bb  push    r15
0x14001c3bd  sub     rsp, 28h
0x14001c3c1  mov     rbp, [rcx]
0x14001c3c4  mov     r13, r8
0x14001c3c7  mov     r9, [rcx+8]
0x14001c3cb  mov     r8, 1FFFFFFFFFFFFFFFh
0x14001c3d5  sub     r9, rbp
0x14001c3d8  mov     r14, rdx
0x14001c3db  sar     r9, 3
0x14001c3df  mov     rdi, rcx
0x14001c3e2  cmp     r9, r8
0x14001c3e5  jz      loc_14001C52B
0x14001c3eb  mov     rcx, [rcx+10h]
0x14001c3ef  mov     rax, r8
0x14001c3f2  sub     rcx, rbp
0x14001c3f5  sar     rcx, 3
0x14001c3f9  mov     rdx, rcx
0x14001c3fc  shr     rdx, 1
0x14001c3ff  sub     rax, rdx
0x14001c402  cmp     rcx, rax
0x14001c405  ja      loc_14001C531
0x14001c40b  lea     r12, [r9+1]
0x14001c40f  lea     rax, [rcx+rdx]
0x14001c413  mov     rsi, r12
0x14001c416  cmp     rax, r12
0x14001c419  cmovnb  rsi, rax
0x14001c41d  cmp     rsi, r8
0x14001c420  ja      loc_14001C531
0x14001c426  shl     rsi, 3
0x14001c42a  test    rsi, rsi
0x14001c42d  jnz     short loc_14001C433
0x14001c42f  xor     ebx, ebx
0x14001c431  jmp     short loc_14001C470
0x14001c433  cmp     rsi, 1000h
0x14001c43a  jb      short loc_14001C465
0x14001c43c  lea     rcx, [rsi+27h]; Size
0x14001c440  cmp     rcx, rsi
0x14001c443  jbe     loc_14001C531
0x14001c449  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14001c44e  test    rax, rax
0x14001c451  jz      loc_14001C4F2
0x14001c457  lea     rbx, [rax+27h]
0x14001c45b  and     rbx, 0FFFFFFFFFFFFFFE0h
0x14001c45f  mov     [rbx-8], rax
0x14001c463  jmp     short loc_14001C470
0x14001c465  mov     rcx, rsi; Size
0x14001c468  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14001c46d  mov     rbx, rax
0x14001c470  mov     rcx, r14
0x14001c473  sub     rcx, rbp
0x14001c476  sar     rcx, 3
0x14001c47a  lea     r15, [rbx+rcx*8]
0x14001c47e  mov     rcx, [r13+0]
0x14001c482  mov     [r15], rcx
0x14001c485  mov     rcx, rbx; void *
0x14001c488  mov     r8, [rdi+8]
0x14001c48c  mov     rdx, [rdi]; Src
0x14001c48f  cmp     r14, r8
0x14001c492  jnz     short loc_14001C499
0x14001c494  sub     r8, rdx
0x14001c497  jmp     short loc_14001C4B2
0x14001c499  mov     r8, r14
0x14001c49c  sub     r8, [rdi]; Size
0x14001c49f  call    memmove_0
0x14001c4a4  mov     r8, [rdi+8]
0x14001c4a8  lea     rcx, [r15+8]; void *
0x14001c4ac  sub     r8, r14; Size
0x14001c4af  mov     rdx, r14; Src
0x14001c4b2  call    memmove_0
0x14001c4b7  mov     rcx, [rdi]
0x14001c4ba  test    rcx, rcx
0x14001c4bd  jz      short loc_14001C504
0x14001c4bf  mov     rax, [rdi+10h]
0x14001c4c3  sub     rax, rcx
0x14001c4c6  sar     rax, 3
0x14001c4ca  lea     rdx, ds:0[rax*8]
0x14001c4d2  cmp     rdx, 1000h
0x14001c4d9  jb      short loc_14001C4F9
0x14001c4db  mov     rax, [rcx-8]
0x14001c4df  sub     rcx, rax
0x14001c4e2  sub     rcx, 8
0x14001c4e6  cmp     rcx, 1Fh
0x14001c4ea  ja      short loc_14001C4F2
0x14001c4ec  add     rdx, 27h ; '''
0x14001c4f0  jmp     short loc_14001C4FC
0x14001c4f2  mov     ecx, 5
0x14001c4f7  int     29h; Win8: RtlFailFast(ecx)
0x14001c4f9  mov     rax, rcx
0x14001c4fc  mov     rcx, rax; Block
0x14001c4ff  call    ??3@YAXPEAXHPEBDH@Z; operator delete(void *,int,char const *,int)
0x14001c504  lea     rcx, [rbx+r12*8]
0x14001c508  mov     [rdi], rbx
0x14001c50b  mov     [rdi+8], rcx
0x14001c50f  mov     rax, r15
0x14001c512  lea     rcx, [rsi+rbx]
0x14001c516  mov     [rdi+10h], rcx
0x14001c51a  add     rsp, 28h
0x14001c51e  pop     r15
0x14001c520  pop     r14
0x14001c522  pop     r13
0x14001c524  pop     r12
0x14001c526  pop     rdi
0x14001c527  pop     rsi
0x14001c528  pop     rbp
0x14001c529  pop     rbx
0x14001c52a  retn
0x14001c52b  call    ?_Xlength@?$vector@UPolicyInfo@WSTrustMEX@@V?$allocator@UPolicyInfo@WSTrustMEX@@@std@@@std@@CAXXZ; std::vector<WSTrustMEX::PolicyInfo>::_Xlength(void)
0x14001c531  call    ?_Throw_bad_array_new_length@std@@YAXXZ; std::_Throw_bad_array_new_length(void)
```
