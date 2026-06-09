# std::_Optimistic_temporary_buffer<GDI::MatchingAxisValueRecord>::_Optimistic_temporary_buffer<GDI::MatchingAxisValueRecord>(__int64)

- ea: `0x14009323c`
- end: `0x1400932e9`
- name: `??$?0_J@?$_Optimistic_temporary_buffer@UMatchingAxisValueRecord@GDI@@@std@@QEAA@_J@Z`
- size: `173`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x140059bec`
- `0x14005dedc`

## callees

- `0x140076620`
- `0x140076db4`
- `0x14009323c`

## pseudocode

```c
_QWORD *__fastcall std::_Optimistic_temporary_buffer<GDI::MatchingAxisValueRecord>::_Optimistic_temporary_buffer<GDI::MatchingAxisValueRecord>(
        _QWORD *a1,
        unsigned __int64 a2)
{
  unsigned __int64 v3; // rax
  __int64 v4; // rbx
  __int64 *v5; // rsi
  void *v6; // rax
  _QWORD *result; // rax

  v3 = a2;
  v4 = a2;
  if ( a2 == 0x7FFFFFFFFFFFFFFFLL )
    v3 = 0x7FFFFFFFFFFFFFFFLL;
  if ( a2 > 0x80 )
  {
    v4 = v3;
    if ( v3 <= 0x7FFFFFFFFFFFFFFLL )
    {
      while ( v4 > 0 )
      {
        v6 = operator new(32 * v4, (const struct std::nothrow_t *)&std::nothrow);
        if ( v6 )
        {
          v5 = a1 + 1;
          if ( (unsigned __int64)v4 > 0x80 )
            goto LABEL_14;
          goto LABEL_12;
        }
        v4 /= 2;
      }
    }
    v6 = 0;
    v5 = a1 + 1;
LABEL_12:
    operator delete(v6);
    v4 = 128;
  }
  else
  {
    v5 = a1 + 1;
  }
  v6 = a1 + 2;
LABEL_14:
  *a1 = v6;
  result = a1;
  *v5 = v4;
  return result;
}

```

## disassembly

```asm
0x14009323c  push    rbx
0x14009323e  push    rbp
0x14009323f  push    rsi
0x140093240  push    rdi
0x140093241  push    r14
0x140093243  sub     rsp, 20h
0x140093247  mov     rdi, rcx
0x14009324a  mov     rax, rdx
0x14009324d  mov     rcx, 7FFFFFFFFFFFFFFFh
0x140093257  mov     ebp, 80h
0x14009325c  cmp     rdx, rcx
0x14009325f  mov     rbx, rdx
0x140093262  mov     r14, rdi
0x140093265  cmovge  rax, rcx
0x140093269  cmp     rdx, rbp
0x14009326c  ja      short loc_140093274
0x14009326e  lea     rsi, [rdi+8]
0x140093272  jmp     short loc_1400932D1
0x140093274  mov     rbx, rax
0x140093277  mov     rax, 7FFFFFFFFFFFFFFh
0x140093281  cmp     rbx, rax
0x140093284  ja      short loc_1400932C0
0x140093286  test    rbx, rbx
0x140093289  jle     short loc_1400932C0
0x14009328b  mov     rcx, rbx
0x14009328e  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x140093295  shl     rcx, 5; unsigned __int64
0x140093299  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x14009329e  test    rax, rax
0x1400932a1  jnz     short loc_1400932B5
0x1400932a3  mov     rax, rbx
0x1400932a6  mov     ecx, 2
0x1400932ab  cqo
0x1400932ad  idiv    rcx
0x1400932b0  mov     rbx, rax
0x1400932b3  jmp     short loc_140093286
0x1400932b5  lea     rsi, [rdi+8]
0x1400932b9  cmp     rbx, rbp
0x1400932bc  ja      short loc_1400932D5
0x1400932be  jmp     short loc_1400932C6
0x1400932c0  xor     eax, eax
0x1400932c2  lea     rsi, [rdi+8]
0x1400932c6  mov     rcx, rax; Block
0x1400932c9  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1400932ce  mov     rbx, rbp
0x1400932d1  lea     rax, [rdi+10h]
0x1400932d5  mov     [r14], rax
0x1400932d8  mov     rax, rdi
0x1400932db  mov     [rsi], rbx
0x1400932de  add     rsp, 20h
0x1400932e2  pop     r14
0x1400932e4  pop     rdi
0x1400932e5  pop     rsi
0x1400932e6  pop     rbp
0x1400932e7  pop     rbx
0x1400932e8  retn
```
