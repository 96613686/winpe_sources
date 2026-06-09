# CMyUpdateList::RemoveAll(void)

- ea: `0x1800109d0`
- end: `0x180010a3a`
- name: `?RemoveAll@CMyUpdateList@@QEAAEXZ`
- size: `106`
- prototype: `unsigned __int8 __fastcall(CMyUpdateList *__hidden this)`
- caller_count: `3`
- callee_count: `3`
- tags: `file_ops, installer_update`

## callers

- `0x18000b394`
- `0x18000e168`
- `0x1800107a0`

## callees

- `0x180001144`
- `0x1800109d0`
- `0x180019010`

## pseudocode

```c
unsigned __int8 __fastcall CMyUpdateList::RemoveAll(CMyUpdateList *this)
{
  __m128i *v2; // rdi
  __m128i si128; // xmm6
  __m128i *v4; // rbx

  if ( !*((_DWORD *)this + 3) )
    return 0;
  v2 = (__m128i *)*((_QWORD *)this + 4);
  *((_QWORD *)this + 4) = 0;
  if ( v2 )
  {
    si128 = _mm_load_si128((const __m128i *)&_xmm_cccccccccccccccccccccccccccccccc);
    do
    {
      v4 = v2;
      v2 = (__m128i *)v2->m128i_i64[0];
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v4->m128i_i64[1] + 16LL))(v4->m128i_i64[1]);
      *v4 = si128;
      operator delete(v4);
    }
    while ( v2 );
  }
  return 1;
}

```

## disassembly

```asm
0x1800109d0  mov     [rsp+arg_0], rbx
0x1800109d5  push    rdi
0x1800109d6  sub     rsp, 30h
0x1800109da  cmp     dword ptr [rcx+0Ch], 0
0x1800109de  movaps  [rsp+38h+var_18], xmm6
0x1800109e3  jnz     short loc_1800109E9
0x1800109e5  xor     al, al
0x1800109e7  jmp     short loc_180010A2A
0x1800109e9  mov     rdi, [rcx+20h]
0x1800109ed  mov     qword ptr [rcx+20h], 0
0x1800109f5  test    rdi, rdi
0x1800109f8  jz      short loc_180010A28
0x1800109fa  movdqa  xmm6, cs:__xmm@cccccccccccccccccccccccccccccccc
0x180010a02  mov     rbx, rdi
0x180010a05  mov     rdi, [rdi]
0x180010a08  mov     rcx, [rbx+8]
0x180010a0c  mov     rax, [rcx]
0x180010a0f  mov     rax, [rax+10h]
0x180010a13  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010a18  mov     rcx, rbx; Block
0x180010a1b  movups  xmmword ptr [rbx], xmm6
0x180010a1e  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180010a23  test    rdi, rdi
0x180010a26  jnz     short loc_180010A02
0x180010a28  mov     al, 1
0x180010a2a  mov     rbx, [rsp+38h+arg_0]
0x180010a2f  movaps  xmm6, [rsp+38h+var_18]
0x180010a34  add     rsp, 30h
0x180010a38  pop     rdi
0x180010a39  retn
```
