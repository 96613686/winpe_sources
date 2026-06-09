# std::vector<std::shared_ptr<CMvExtensionKey>,std::allocator<std::shared_ptr<CMvExtensionKey>>>::_Reallocate(unsigned __int64)

- ea: `0x18001495c`
- end: `0x180014a66`
- name: `?_Reallocate@?$vector@V?$shared_ptr@VCMvExtensionKey@@@std@@V?$allocator@V?$shared_ptr@VCMvExtensionKey@@@std@@@2@@std@@IEAAX_K@Z`
- size: `266`
- prototype: `void __fastcall(__int64, unsigned __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, loader_planting`

## callers

- `0x180014b20`

## callees

- `0x180002034`
- `0x180013a74`
- `0x18001495c`
- `0x18003f010`

## import_xrefs

- `msvcp110_win!?_Xbad_alloc@std@@YAXXZ` at `0x1800149ad`
- `msvcp110_win!?_Xbad_alloc@std@@YAXXZ` at `0x1800149ad`
- `msvcrt!??3@YAXPEAX@Z` at `0x180014a30`
- `msvcrt!??3@YAXPEAX@Z` at `0x180014a30`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall std::vector<std::shared_ptr<CMvExtensionKey>>::_Reallocate(__int64 a1, unsigned __int64 a2)
{
  __int64 *v4; // rbx
  __int64 v5; // rcx
  __int64 *v6; // r13
  __int64 *v7; // r12
  unsigned __int64 v8; // rsi
  volatile signed __int32 *v9; // r14
  __int64 **v10; // r14
  __int64 *v11; // [rsp+68h] [rbp+10h]

  v4 = 0;
  v11 = 0;
  if ( a2 )
  {
    if ( a2 > 0xFFFFFFFFFFFFFFFLL || (v4 = (__int64 *)operator new(16 * a2), (v11 = v4) == 0) )
      std::_Xbad_alloc();
  }
  try
  {
    v10 = (__int64 **)(a1 + 8);
    std::_Uninit_move<std::shared_ptr<CMvExtensionKey> *,std::shared_ptr<CMvExtensionKey> *,std::allocator<std::shared_ptr<CMvExtensionKey>>,std::shared_ptr<CMvExtensionKey>>(
      *(__int64 **)a1,
      *(__int64 **)(a1 + 8),
      v4);
  }
  catch ( ... )
  {
    std::_Wrap_alloc<std::allocator<unsigned short>>::deallocate(v5, v11);
    throw;
  }
  v6 = *(__int64 **)a1;
  v7 = *v10;
  v8 = (unsigned __int64)*v10 - *(_QWORD *)a1;
  if ( *(_QWORD *)a1 )
  {
    if ( v6 != v7 )
    {
      do
      {
        v9 = (volatile signed __int32 *)v6[1];
        if ( v9 )
        {
          if ( _InterlockedExchangeAdd(v9 + 2, 0xFFFFFFFF) == 1 )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v9)(v9);
            if ( _InterlockedExchangeAdd(v9 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v9 + 8LL))(v9);
          }
        }
        v6 += 2;
      }
      while ( v6 != v7 );
      v10 = (__int64 **)(a1 + 8);
    }
    operator delete(*(void **)a1);
  }
  *(_QWORD *)(a1 + 16) = &v4[2 * a2];
  *v10 = (__int64 *)((char *)v4 + (v8 & 0xFFFFFFFFFFFFFFF0uLL));
  *(_QWORD *)a1 = v4;
}

```

## disassembly

```asm
0x18001495c  mov     [rsp+arg_0], rbx
0x180014961  mov     [rsp+arg_10], rsi
0x180014966  push    rdi
0x180014967  push    r12
0x180014969  push    r13
0x18001496b  push    r14
0x18001496d  push    r15
0x18001496f  sub     rsp, 30h
0x180014973  mov     rdi, rdx
0x180014976  mov     r15, rcx
0x180014979  xor     ebx, ebx
0x18001497b  mov     [rsp+58h+arg_8], rbx
0x180014980  test    rdx, rdx
0x180014983  jz      short loc_1800149B4
0x180014985  mov     rax, 0FFFFFFFFFFFFFFFh
0x18001498f  cmp     rdx, rax
0x180014992  ja      short loc_1800149AD
0x180014994  mov     rcx, rdx
0x180014997  shl     rcx, 4; Size
0x18001499b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800149a0  mov     rbx, rax
0x1800149a3  mov     [rsp+58h+arg_8], rax
0x1800149a8  test    rax, rax
0x1800149ab  jnz     short loc_1800149B4
0x1800149ad  call    cs:__imp_?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
0x1800149b3  nop
0x1800149b4  lea     r14, [r15+8]
0x1800149b8  mov     r8, rbx
0x1800149bb  mov     rdx, [r14]
0x1800149be  mov     rcx, [r15]
0x1800149c1  call    ??$_Uninit_move@PEAV?$shared_ptr@VCMvExtensionKey@@@std@@PEAV12@V?$allocator@V?$shared_ptr@VCMvExtensionKey@@@std@@@2@V12@@std@@YAPEAV?$shared_ptr@VCMvExtensionKey@@@0@PEAV10@00AEAU?$_Wrap_alloc@V?$allocator@V?$shared_ptr@VCMvExtensionKey@@@std@@@std@@@0@0U_Nonscalar_ptr_iterator_tag@0@@Z; std::_Uninit_move<std::shared_ptr<CMvExtensionKey> *,std::shared_ptr<CMvExtensionKey> *,std::allocator<std::shared_ptr<CMvExtensionKey>>,std::shared_ptr<CMvExtensionKey>>(std::shared_ptr<CMvExtensionKey> *,std::shared_ptr<CMvExtensionKey> *,std::shared_ptr<CMvExtensionKey> *,std::_Wrap_alloc<std::allocator<std::shared_ptr<CMvExtensionKey>>> &,std::shared_ptr<CMvExtensionKey> *,std::_Nonscalar_ptr_iterator_tag)
0x1800149c6  nop
0x1800149c7  mov     r13, [r15]
0x1800149ca  mov     r12, [r14]
0x1800149cd  mov     rsi, r12
0x1800149d0  sub     rsi, r13
0x1800149d3  test    r13, r13
0x1800149d6  jz      short loc_180014A36
0x1800149d8  cmp     r13, r12
0x1800149db  jz      short loc_180014A2D
0x1800149dd  mov     r14, [r13+8]
0x1800149e1  test    r14, r14
0x1800149e4  jz      short loc_180014A20
0x1800149e6  or      eax, 0FFFFFFFFh
0x1800149e9  lock xadd [r14+8], eax
0x1800149ef  cmp     eax, 1
0x1800149f2  jnz     short loc_180014A20
0x1800149f4  mov     rax, [r14]
0x1800149f7  mov     rcx, r14
0x1800149fa  mov     rax, [rax]
0x1800149fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014a02  or      eax, 0FFFFFFFFh
0x180014a05  lock xadd [r14+0Ch], eax
0x180014a0b  cmp     eax, 1
0x180014a0e  jnz     short loc_180014A20
0x180014a10  mov     rax, [r14]
0x180014a13  mov     rcx, r14
0x180014a16  mov     rax, [rax+8]
0x180014a1a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014a1f  nop
0x180014a20  add     r13, 10h
0x180014a24  cmp     r13, r12
0x180014a27  jnz     short loc_1800149DD
0x180014a29  lea     r14, [r15+8]
0x180014a2d  mov     rcx, [r15]
0x180014a30  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180014a36  shl     rdi, 4
0x180014a3a  add     rdi, rbx
0x180014a3d  mov     [r15+10h], rdi
0x180014a41  and     rsi, 0FFFFFFFFFFFFFFF0h
0x180014a45  add     rsi, rbx
0x180014a48  mov     [r14], rsi
0x180014a4b  mov     [r15], rbx
0x180014a4e  mov     rbx, [rsp+58h+arg_0]
0x180014a53  mov     rsi, [rsp+58h+arg_10]
0x180014a58  add     rsp, 30h
0x180014a5c  pop     r15
0x180014a5e  pop     r14
0x180014a60  pop     r13
0x180014a62  pop     r12
0x180014a64  pop     rdi
0x180014a65  retn
```
