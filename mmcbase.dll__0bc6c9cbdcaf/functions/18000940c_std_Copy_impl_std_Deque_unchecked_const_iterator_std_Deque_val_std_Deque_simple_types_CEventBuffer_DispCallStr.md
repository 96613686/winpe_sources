# std::_Copy_impl<std::_Deque_unchecked_const_iterator<std::_Deque_val<std::_Deque_simple_types<CEventBuffer::DispCallStr>>>,std::_Deque_unchecked_iterator<std::_Deque_val<std::_Deque_simple_types<CEventBuffer::DispCallStr>>>>(std::_Deque_unchecked_const_iterator<std::_Deque_val<std::_Deque_simple_types<CEventBuffer::DispCallStr>>>,std::_Deque_unchecked_const_iterator<std::_Deque_val<std::_Deque_simple_types<CEventBuffer::DispCallStr>>>,std::_Deque_unchecked_iterator<std::_Deque_val<std::_Deque_simple_types<CEventBuffer::DispCallStr>>>,std::_Nonscalar_ptr_iterator_tag)

- ea: `0x18000940c`
- end: `0x1800094b1`
- name: `??$_Copy_impl@V?$_Deque_unchecked_const_iterator@V?$_Deque_val@U?$_Deque_simple_types@UDispCallStr@CEventBuffer@@@std@@@std@@@std@@V?$_Deque_unchecked_iterator@V?$_Deque_val@U?$_Deque_simple_types@UDispCallStr@CEventBuffer@@@std@@@std@@@2@@std@@YA?AV?$_Deque_unchecked_iterator@V?$_Deque_val@U?$_Deque_simple_types@UDispCallStr@CEventBuffer@@@std@@@std@@@0@V?$_Deque_unchecked_const_iterator@V?$_Deque_val@U?$_Deque_simple_types@UDispCallStr@CEventBuffer@@@std@@@std@@@0@0V10@U_Nonscalar_ptr_iterator_tag@0@@Z`
- size: `165`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1800090a4`

## callees

- `0x180008064`
- `0x18000940c`
- `0x180013c0c`

## pseudocode

```c
_OWORD *__fastcall std::_Copy_impl<std::_Deque_unchecked_const_iterator<std::_Deque_val<std::_Deque_simple_types<CEventBuffer::DispCallStr>>>,std::_Deque_unchecked_iterator<std::_Deque_val<std::_Deque_simple_types<CEventBuffer::DispCallStr>>>>(
        _OWORD *a1,
        _QWORD *a2,
        __int64 a3,
        _QWORD *a4)
{
  __int64 v4; // r13
  __int64 v8; // r15
  __int64 v9; // rsi
  __int64 v10; // rdi
  __int64 v11; // rbx
  _OWORD *result; // rax

  v4 = *(_QWORD *)(a3 + 8);
  while ( 1 )
  {
    v8 = a2[1];
    if ( v8 == v4 )
      break;
    v9 = a4[1];
    v10 = *(_QWORD *)(*(_QWORD *)(*a2 + 8LL) + 8 * (v8 & (*(_QWORD *)(*a2 + 16LL) - 1LL)));
    v11 = *(_QWORD *)(*(_QWORD *)(*a4 + 8LL) + 8 * (v9 & (*(_QWORD *)(*a4 + 16LL) - 1LL)));
    _com_ptr_t<_com_IIID<IDispatch,&__s_GUID const _GUID_00020400_0000_0000_c000_000000000046>>::operator=(
      v11,
      *(_QWORD *)v10);
    *(_DWORD *)(v11 + 8) = *(_DWORD *)(v10 + 8);
    std::vector<ATL::CComVariant>::operator=(v11 + 16, v10 + 16);
    a4[1] = v9 + 1;
    a2[1] = v8 + 1;
  }
  result = a1;
  *a1 = *(_OWORD *)a4;
  return result;
}

```

## disassembly

```asm
0x18000940c  push    rbx
0x18000940e  push    rbp
0x18000940f  push    rsi
0x180009410  push    rdi
0x180009411  push    r12
0x180009413  push    r13
0x180009415  push    r14
0x180009417  push    r15
0x180009419  sub     rsp, 28h
0x18000941d  mov     r13, [r8+8]
0x180009421  mov     r14, r9
0x180009424  mov     r12, rdx
0x180009427  mov     rbp, rcx
0x18000942a  mov     r15, [r12+8]
0x18000942f  cmp     r15, r13
0x180009432  jz      short loc_180009494
0x180009434  mov     rax, [r12]
0x180009438  mov     rsi, [r14+8]
0x18000943c  mov     rcx, [rax+10h]
0x180009440  mov     rax, [rax+8]
0x180009444  dec     rcx
0x180009447  and     rcx, r15
0x18000944a  mov     rdi, [rax+rcx*8]
0x18000944e  mov     rax, [r14]
0x180009451  mov     rdx, [rdi]
0x180009454  mov     rcx, [rax+10h]
0x180009458  mov     rax, [rax+8]
0x18000945c  dec     rcx
0x18000945f  and     rcx, rsi
0x180009462  mov     rbx, [rax+rcx*8]
0x180009466  mov     rcx, rbx
0x180009469  call    ??4?$_com_ptr_t@V?$_com_IIID@UIDispatch@@$1?_GUID_00020400_0000_0000_c000_000000000046@@3U__s_GUID@@B@@@@QEAAAEAV0@PEAUIDispatch@@@Z; _com_ptr_t<_com_IIID<IDispatch,&__s_GUID const _GUID_00020400_0000_0000_c000_000000000046>>::operator=(IDispatch *)
0x18000946e  mov     eax, [rdi+8]
0x180009471  lea     rdx, [rdi+10h]
0x180009475  lea     rcx, [rbx+10h]
0x180009479  mov     [rbx+8], eax
0x18000947c  call    ??4?$vector@VCComVariant@ATL@@V?$allocator@VCComVariant@ATL@@@std@@@std@@QEAAAEAV01@AEBV01@@Z; std::vector<ATL::CComVariant>::operator=(std::vector<ATL::CComVariant> const &)
0x180009481  lea     rax, [rsi+1]
0x180009485  mov     [r14+8], rax
0x180009489  lea     rax, [r15+1]
0x18000948d  mov     [r12+8], rax
0x180009492  jmp     short loc_18000942A
0x180009494  movaps  xmm0, xmmword ptr [r14]
0x180009498  mov     rax, rbp
0x18000949b  movdqu  xmmword ptr [rbp+0], xmm0
0x1800094a0  add     rsp, 28h
0x1800094a4  pop     r15
0x1800094a6  pop     r14
0x1800094a8  pop     r13
0x1800094aa  pop     r12
0x1800094ac  pop     rdi
0x1800094ad  pop     rsi
0x1800094ae  pop     rbp
0x1800094af  pop     rbx
0x1800094b0  retn
```
