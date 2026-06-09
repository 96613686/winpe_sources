# std::vector<ATL::CComVariant,std::allocator<ATL::CComVariant>>::operator=(std::vector<ATL::CComVariant,std::allocator<ATL::CComVariant>> const &)

- ea: `0x180013c0c`
- end: `0x180013d48`
- name: `??4?$vector@VCComVariant@ATL@@V?$allocator@VCComVariant@ATL@@@std@@@std@@QEAAAEAV01@AEBV01@@Z`
- size: `316`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18000940c`

## callees

- `0x180007b74`
- `0x1800133dc`
- `0x1800136d8`
- `0x180013c0c`
- `0x180013e30`
- `0x180014018`

## import_xrefs

- `MFC42u!__imp_??3@YAXPEAX@Z` at `0x180013d0b`
- `MFC42u!__imp_??3@YAXPEAX@Z` at `0x180013d0b`

## pseudocode

```c
__int64 __fastcall std::vector<ATL::CComVariant>::operator=(__int64 a1, __int64 a2)
{
  struct tagVARIANT *v4; // r9
  void *v6; // rdx
  unsigned __int64 v7; // rcx
  unsigned __int64 v8; // r8
  __int64 v9; // rax
  __int64 v10; // rcx
  struct tagVARIANT *v11; // rbx

  if ( a1 != a2 )
  {
    v4 = *(struct tagVARIANT **)a2;
    if ( *(_QWORD *)a2 == *(_QWORD *)(a2 + 8) )
    {
      std::vector<ATL::CComVariant>::clear();
    }
    else
    {
      v6 = *(void **)a1;
      v7 = 0xAAAAAAAAAAAAAAABuLL * ((__int64)(*(_QWORD *)(a1 + 8) - *(_QWORD *)a1) >> 3);
      v8 = 0xAAAAAAAAAAAAAAABuLL * ((__int64)(*(_QWORD *)(a2 + 8) - (_QWORD)v4) >> 3);
      if ( v8 > v7 )
      {
        if ( v8 > 0xAAAAAAAAAAAAAAABuLL * ((__int64)(*(_QWORD *)(a1 + 16) - (_QWORD)v6) >> 3) )
        {
          if ( v6 )
          {
            std::vector<ATL::CComVariant>::_Destroy(v7, v6, *(_QWORD *)(a1 + 8));
            operator delete(*(void **)a1);
          }
          if ( (unsigned __int8)std::vector<ATL::CComVariant>::_Buy(
                                  a1,
                                  0xAAAAAAAAAAAAAAABuLL * ((__int64)(*(_QWORD *)(a2 + 8) - *(_QWORD *)a2) >> 3)) )
          {
            try
            {
              *(_QWORD *)(a1 + 8) = std::_Uninit_copy<ATL::CComVariant *,ATL::CComVariant *,std::allocator<ATL::CComVariant>>(*(struct tagVARIANT **)a2);
            }
            catch ( ... )
            {
              std::vector<ATL::CComVariant>::_Tidy(a1);
              throw;
            }
          }
        }
        else
        {
          v11 = v4 + v7;
          std::_Copy_impl<ATL::CComVariant *,ATL::CComVariant *>(v4);
          *(_QWORD *)(a1 + 8) = std::_Uninit_copy<ATL::CComVariant *,ATL::CComVariant *,std::allocator<ATL::CComVariant>>(v11);
        }
      }
      else
      {
        v9 = std::_Copy_impl<ATL::CComVariant *,ATL::CComVariant *>(v4);
        std::vector<ATL::CComVariant>::_Destroy(v10, v9, *(_QWORD *)(a1 + 8));
        *(_QWORD *)(a1 + 8) = *(_QWORD *)a1 + 8 * ((__int64)(*(_QWORD *)(a2 + 8) - *(_QWORD *)a2) >> 3);
      }
    }
  }
  return a1;
}

```

## disassembly

```asm
0x180013c0c  mov     [rsp+arg_8], rbx
0x180013c11  mov     [rsp+arg_10], rsi
0x180013c16  mov     [rsp+arg_0], rcx
0x180013c1b  push    rdi
0x180013c1c  sub     rsp, 30h
0x180013c20  mov     rsi, rdx
0x180013c23  mov     rdi, rcx
0x180013c26  cmp     rcx, rdx
0x180013c29  jz      short loc_180013C39
0x180013c2b  mov     r9, [rdx]
0x180013c2e  cmp     r9, [rdx+8]
0x180013c32  jnz     short loc_180013C4C
0x180013c34  call    ?clear@?$vector@VCComVariant@ATL@@V?$allocator@VCComVariant@ATL@@@std@@@std@@QEAAXXZ; std::vector<ATL::CComVariant>::clear(void)
0x180013c39  mov     rax, rdi
0x180013c3c  mov     rbx, [rsp+38h+arg_8]
0x180013c41  mov     rsi, [rsp+38h+arg_10]
0x180013c46  add     rsp, 30h
0x180013c4a  pop     rdi
0x180013c4b  retn
0x180013c4c  mov     rdx, [rcx]
0x180013c4f  mov     rcx, [rcx+8]
0x180013c53  sub     rcx, rdx
0x180013c56  sar     rcx, 3
0x180013c5a  mov     rbx, 0AAAAAAAAAAAAAAABh
0x180013c64  imul    rcx, rbx
0x180013c68  mov     r8, [rsi+8]
0x180013c6c  sub     r8, r9
0x180013c6f  sar     r8, 3
0x180013c73  imul    r8, rbx
0x180013c77  cmp     r8, rcx
0x180013c7a  ja      short loc_180013CB7
0x180013c7c  mov     r8, rdx
0x180013c7f  mov     rdx, [rsi+8]
0x180013c83  mov     rcx, r9; struct tagVARIANT *
0x180013c86  call    ??$_Copy_impl@PEAVCComVariant@ATL@@PEAV12@@std@@YAPEAVCComVariant@ATL@@PEAV12@00@Z; std::_Copy_impl<ATL::CComVariant *,ATL::CComVariant *>(ATL::CComVariant *,ATL::CComVariant *,ATL::CComVariant *)
0x180013c8b  mov     r8, [rdi+8]
0x180013c8f  mov     rdx, rax
0x180013c92  call    ?_Destroy@?$vector@VCComVariant@ATL@@V?$allocator@VCComVariant@ATL@@@std@@@std@@IEAAXPEAVCComVariant@ATL@@0@Z; std::vector<ATL::CComVariant>::_Destroy(ATL::CComVariant *,ATL::CComVariant *)
0x180013c97  mov     rax, [rsi+8]
0x180013c9b  sub     rax, [rsi]
0x180013c9e  sar     rax, 3
0x180013ca2  imul    rax, rbx
0x180013ca6  lea     rcx, [rax+rax*2]
0x180013caa  mov     rax, [rdi]
0x180013cad  lea     rcx, [rax+rcx*8]
0x180013cb1  mov     [rdi+8], rcx
0x180013cb5  jmp     short loc_180013C39
0x180013cb7  mov     rax, [rdi+10h]
0x180013cbb  sub     rax, rdx
0x180013cbe  sar     rax, 3
0x180013cc2  imul    rax, rbx
0x180013cc6  cmp     r8, rax
0x180013cc9  ja      short loc_180013CFA
0x180013ccb  lea     rax, [rcx+rcx*2]
0x180013ccf  lea     rbx, [r9+rax*8]
0x180013cd3  mov     r8, rdx
0x180013cd6  mov     rdx, rbx
0x180013cd9  mov     rcx, r9; struct tagVARIANT *
0x180013cdc  call    ??$_Copy_impl@PEAVCComVariant@ATL@@PEAV12@@std@@YAPEAVCComVariant@ATL@@PEAV12@00@Z; std::_Copy_impl<ATL::CComVariant *,ATL::CComVariant *>(ATL::CComVariant *,ATL::CComVariant *,ATL::CComVariant *)
0x180013ce1  mov     r8, [rdi+8]
0x180013ce5  mov     rdx, [rsi+8]
0x180013ce9  mov     rcx, rbx; struct tagVARIANT *
0x180013cec  call    ??$_Uninit_copy@PEAVCComVariant@ATL@@PEAV12@V?$allocator@VCComVariant@ATL@@@std@@@std@@YAPEAVCComVariant@ATL@@PEAV12@00AEAU?$_Wrap_alloc@V?$allocator@VCComVariant@ATL@@@std@@@0@U_Nonscalar_ptr_iterator_tag@0@@Z; std::_Uninit_copy<ATL::CComVariant *,ATL::CComVariant *,std::allocator<ATL::CComVariant>>(ATL::CComVariant *,ATL::CComVariant *,ATL::CComVariant *,std::_Wrap_alloc<std::allocator<ATL::CComVariant>> &,std::_Nonscalar_ptr_iterator_tag)
0x180013cf1  mov     [rdi+8], rax
0x180013cf5  jmp     loc_180013C39
0x180013cfa  test    rdx, rdx
0x180013cfd  jz      short loc_180013D11
0x180013cff  mov     r8, [rdi+8]
0x180013d03  call    ?_Destroy@?$vector@VCComVariant@ATL@@V?$allocator@VCComVariant@ATL@@@std@@@std@@IEAAXPEAVCComVariant@ATL@@0@Z; std::vector<ATL::CComVariant>::_Destroy(ATL::CComVariant *,ATL::CComVariant *)
0x180013d08  mov     rcx, [rdi]
0x180013d0b  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180013d11  mov     rdx, [rsi+8]
0x180013d15  sub     rdx, [rsi]
0x180013d18  sar     rdx, 3
0x180013d1c  imul    rdx, rbx
0x180013d20  mov     rcx, rdi
0x180013d23  call    ?_Buy@?$vector@VCComVariant@ATL@@V?$allocator@VCComVariant@ATL@@@std@@@std@@IEAA_N_K@Z; std::vector<ATL::CComVariant>::_Buy(unsigned __int64)
0x180013d28  test    al, al
0x180013d2a  jz      loc_180013C39
0x180013d30  mov     r8, [rdi]
0x180013d33  mov     rdx, [rsi+8]
0x180013d37  mov     rcx, [rsi]; struct tagVARIANT *
0x180013d3a  call    ??$_Uninit_copy@PEAVCComVariant@ATL@@PEAV12@V?$allocator@VCComVariant@ATL@@@std@@@std@@YAPEAVCComVariant@ATL@@PEAV12@00AEAU?$_Wrap_alloc@V?$allocator@VCComVariant@ATL@@@std@@@0@U_Nonscalar_ptr_iterator_tag@0@@Z; std::_Uninit_copy<ATL::CComVariant *,ATL::CComVariant *,std::allocator<ATL::CComVariant>>(ATL::CComVariant *,ATL::CComVariant *,ATL::CComVariant *,std::_Wrap_alloc<std::allocator<ATL::CComVariant>> &,std::_Nonscalar_ptr_iterator_tag)
0x180013d3f  mov     [rdi+8], rax
0x180013d43  jmp     loc_180013C39
```
