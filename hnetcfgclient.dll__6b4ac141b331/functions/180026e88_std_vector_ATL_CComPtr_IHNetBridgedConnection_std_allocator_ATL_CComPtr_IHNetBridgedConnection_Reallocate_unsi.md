# std::vector<ATL::CComPtr<IHNetBridgedConnection>,std::allocator<ATL::CComPtr<IHNetBridgedConnection>>>::_Reallocate(unsigned __int64)

- ea: `0x180026e88`
- end: `0x180026f2c`
- name: `?_Reallocate@?$vector@V?$CComPtr@UIHNetBridgedConnection@@@ATL@@V?$allocator@V?$CComPtr@UIHNetBridgedConnection@@@ATL@@@std@@@std@@IEAAX_K@Z`
- size: `164`
- prototype: `__int64 *__fastcall(__int64, unsigned __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800273e0`

## callees

- `0x180001274`
- `0x180001418`
- `0x180025c28`
- `0x180026d48`
- `0x180026e88`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180026f09`
- `msvcrt!??3@YAXPEAX@Z` at `0x180026f09`

## pseudocode

```c
__int64 *__fastcall std::vector<ATL::CComPtr<IHNetBridgedConnection>>::_Reallocate(__int64 a1, unsigned __int64 a2)
{
  __int64 *v3; // rbx
  __int64 v4; // r14
  __int64 v5; // rcx
  __int64 v6; // rsi
  __int64 *result; // rax
  __int64 *v8; // [rsp+68h] [rbp+10h]

  v3 = 0;
  v8 = 0;
  if ( a2 )
  {
    if ( a2 > 0x1FFFFFFFFFFFFFFFLL || (v4 = a2, v3 = (__int64 *)operator new(8 * a2), (v8 = v3) == 0) )
      std::_Xbad_alloc();
  }
  else
  {
    v4 = 0;
  }
  try
  {
    std::_Uninit_move<ATL::CComPtr<IHNetBridgedConnection> *,ATL::CComPtr<IHNetBridgedConnection> *,std::allocator<ATL::CComPtr<IHNetBridgedConnection>>,ATL::CComPtr<IHNetBridgedConnection>>(
      *(__int64 **)a1,
      *(__int64 **)(a1 + 8),
      v3);
  }
  catch ( ... )
  {
    operator delete(v8);
    throw;
  }
  v6 = (__int64)(*(_QWORD *)(a1 + 8) - *(_QWORD *)a1) >> 3;
  if ( *(_QWORD *)a1 )
  {
    std::vector<ATL::CComPtr<IHNetBridgedConnection>>::_Destroy(v5, *(__int64 **)a1, *(__int64 **)(a1 + 8));
    operator delete(*(void **)a1);
  }
  *(_QWORD *)(a1 + 16) = &v3[v4];
  result = &v3[v6];
  *(_QWORD *)(a1 + 8) = result;
  *(_QWORD *)a1 = v3;
  return result;
}

```

## disassembly

```asm
0x180026e88  push    rbx
0x180026e8a  push    rsi
0x180026e8b  push    rdi
0x180026e8c  push    r14
0x180026e8e  sub     rsp, 38h
0x180026e92  mov     rdi, rcx
0x180026e95  xor     ebx, ebx
0x180026e97  mov     [rsp+58h+arg_8], rbx
0x180026e9c  test    rdx, rdx
0x180026e9f  jz      short loc_180026ED3
0x180026ea1  mov     rax, 1FFFFFFFFFFFFFFFh
0x180026eab  cmp     rdx, rax
0x180026eae  ja      short loc_180026ECD
0x180026eb0  lea     r14, ds:0[rdx*8]
0x180026eb8  mov     rcx, r14; Size
0x180026ebb  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180026ec0  mov     rbx, rax
0x180026ec3  mov     [rsp+58h+arg_8], rax
0x180026ec8  test    rax, rax
0x180026ecb  jnz     short loc_180026EDB
0x180026ecd  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
0x180026ed3  lea     r14, ds:0[rdx*8]
0x180026edb  mov     r8, rbx
0x180026ede  mov     rdx, [rdi+8]
0x180026ee2  mov     rcx, [rdi]
0x180026ee5  call    ??$_Uninit_move@PEAV?$CComPtr@UIHNetBridgedConnection@@@ATL@@PEAV12@V?$allocator@V?$CComPtr@UIHNetBridgedConnection@@@ATL@@@std@@V12@@std@@YAPEAV?$CComPtr@UIHNetBridgedConnection@@@ATL@@PEAV12@00AEAU?$_Wrap_alloc@V?$allocator@V?$CComPtr@UIHNetBridgedConnection@@@ATL@@@std@@@0@0U_Nonscalar_ptr_iterator_tag@0@@Z; std::_Uninit_move<ATL::CComPtr<IHNetBridgedConnection> *,ATL::CComPtr<IHNetBridgedConnection> *,std::allocator<ATL::CComPtr<IHNetBridgedConnection>>,ATL::CComPtr<IHNetBridgedConnection>>(ATL::CComPtr<IHNetBridgedConnection> *,ATL::CComPtr<IHNetBridgedConnection> *,ATL::CComPtr<IHNetBridgedConnection> *,std::_Wrap_alloc<std::allocator<ATL::CComPtr<IHNetBridgedConnection>>> &,ATL::CComPtr<IHNetBridgedConnection> *,std::_Nonscalar_ptr_iterator_tag)
0x180026eea  nop
0x180026eeb  mov     rdx, [rdi]
0x180026eee  mov     r8, [rdi+8]
0x180026ef2  mov     rsi, r8
0x180026ef5  sub     rsi, rdx
0x180026ef8  sar     rsi, 3
0x180026efc  test    rdx, rdx
0x180026eff  jz      short loc_180026F0F
0x180026f01  call    ?_Destroy@?$vector@V?$CComPtr@UIHNetBridgedConnection@@@ATL@@V?$allocator@V?$CComPtr@UIHNetBridgedConnection@@@ATL@@@std@@@std@@IEAAXPEAV?$CComPtr@UIHNetBridgedConnection@@@ATL@@0@Z; std::vector<ATL::CComPtr<IHNetBridgedConnection>>::_Destroy(ATL::CComPtr<IHNetBridgedConnection> *,ATL::CComPtr<IHNetBridgedConnection> *)
0x180026f06  mov     rcx, [rdi]
0x180026f09  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180026f0f  lea     rax, [r14+rbx]
0x180026f13  mov     [rdi+10h], rax
0x180026f17  lea     rax, [rbx+rsi*8]
0x180026f1b  mov     [rdi+8], rax
0x180026f1f  mov     [rdi], rbx
0x180026f22  add     rsp, 38h
0x180026f26  pop     r14
0x180026f28  pop     rdi
0x180026f29  pop     rsi
0x180026f2a  pop     rbx
0x180026f2b  retn
```
